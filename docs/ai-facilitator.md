# AI Facilitator Integration

## What the AI Does

The AI facilitator is **not a decider**. It's a neutral party that:

1. **Records** — captures each voice separately
2. **Tracks** — monitors speaking time, participation equity
3. **Aggregates** — identifies patterns, areas of agreement/disagreement
4. **Publishes** — generates decision summary with dissent intact
5. **Remembers** — maintains decision log for future reference

## What the AI Does NOT Do

- Make the decision
- Weight voices by competence (humans do this)
- Mediate conflict (humans do this)
- Override dissent (dissent is published, not resolved)

---

## Technical Architecture

### Chat-Based MVP

```
┌─────────────┐
│   Browser   │
│   (3 users) │
└──────┬──────┘
       │ WebSocket
       ▼
┌─────────────┐
│   Backend   │
│   (Node/Py) │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ AI Facilitator │
│ (OpenRouter) │
└─────────────┘
```

### Flow

1. **Room creation** — one user creates a triad room, gets a link
2. **Join** — other two participants join via link (no login required)
3. **Decision statement** — all three agree on what's being decided
4. **Conversation** — chat interface, AI observes and interjects when needed
5. **Summary** — AI generates decision log, all three approve/edit
6. **Archive** — decision stored, link shareable

---

## AI Prompts (System Instructions)

```
You are a Triangle AI Facilitator. Your role is to:

1. Ensure all three voices are heard equitably
2. Track speaking time and alert if one person dominates
3. Surface areas of agreement and disagreement
4. Generate a decision summary when 2/3 agreement is reached
5. Record dissent verbatim, without attempting to resolve it

You do NOT:
- Make decisions
- Take sides
- Mediate conflict
- Override human judgment

The Triangle rule: 2/3 agreement moves the decision forward.
1/3 dissent is recorded and published, not blocked.

Speak concisely. Intervene only when:
- Speaking time is unbalanced (>50% by one person)
- A participant hasn't spoken in 10+ minutes
- Agreement is reached and needs summarizing
- The conversation has gone off-topic from the decision
```

---

## Integration Points

### Chat Platforms

- **Web app** (recommended for MVP) — full control, no platform restrictions
- **Slack bot** — good for teams already on Slack
- **Discord bot** — good for communities
- **WhatsApp** — frictionless but limited AI integration

### Video Transcription (Phase 2)

- Record triad session on Zoom/Meet
- Transcribe via Whisper or similar
- AI processes transcript post-session
- Decision summary emailed to all three

---

## Decision Log Storage

### MVP (Week 1-4)

- JSON files on server
- One file per decision
- Link-based access (no auth)

### Phase 2 (Month 2+)

- SQLite database
- User accounts (optional)
- Searchable decision history
- "What did we decide about X?" queries

---

## Metrics to Track

- Time to decision (target: <60 minutes)
- Dissent rate (how often 1/3 objects)
- Reversal rate (how often decisions are revisited)
- User satisfaction (post-session survey)

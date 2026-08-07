# Quick Start

## For First-Time Users

### Step 1: Is this a triad decision?

Ask:
- Does this affect others' work?
- Is this reversible?
- Does this commit significant resources?
- Will this create precedent?

If **2+ yes** → use a triad.

### Step 2: Gather three people

Choose:
- Diverse perspectives
- Relevant competence
- At least one person who can execute the decision

### Step 3: Set up the session

- Timebox: 30-60 minutes
- Format: in-person, video call, or chat-based
- AI facilitator: optional but recommended

### Step 4: Run the session

1. State the decision (one sentence)
2. Each person speaks uninterrupted (2-3 minutes each)
3. Open discussion (AI tracks equity)
4. AI surfaces agreement/disagreement
5. Decision called when 2/3 aligned

### Step 5: Publish the decision

Within 24 hours:
- Send summary to all three
- Include dissent verbatim
- Note review date if reversible

---

## For Organisations

### Pilot Programme (4 weeks)

**Week 1:** Train 3 triads on low-stakes decisions
**Week 2:** Debrief, refine facilitation
**Week 3:** Apply to medium-stakes decisions
**Week 4:** Review decision log, measure satisfaction

### Success Metrics

- Time to decision (target: <60 minutes)
- User satisfaction (target: >4/5)
- Reversal rate (target: <20%)
- Dissent rate (target: 30-50% — healthy disagreement)

---

## For Developers

### Building the AI Facilitator

See [AI Facilitator Integration](./docs/ai-facilitator.md) for:
- System prompts
- Architecture diagram
- Integration points

### Quick Deploy

```bash
# Clone the reference implementation
git clone https://github.com/[your-repo]/triangle-facilitator

# Install dependencies
npm install  # or pip install -r requirements.txt

# Configure AI provider
cp .env.example .env
# Add your OpenRouter/API key

# Run locally
npm start  # or python main.py

# Deploy to Vercel/Render
```

---

## Common Questions

**Q: What if we only have 2 people available?**
A: Use a dyad. If stuck, bring in a third person specifically for tiebreaking.

**Q: Can the AI facilitator be one of the three voices?**
A: No. AI facilitates, humans decide. The triad must be three humans.

**Q: What if 2/3 agreement is reached but feels wrong?**
A: Either dissenter can call for a reconvene with new information. The 2/3 rule moves decisions, it doesn't prevent review.

**Q: Do we need to use the AI facilitator?**
A: No. Human facilitation works. AI adds equity tracking, automatic summarization, and decision logging.

**Q: How do we handle ongoing decisions (not one-offs)?**
A: Form a standing triad for that domain (e.g., "technical triad" for architecture decisions). Same rules apply.

---

## Next Steps

- Read [Core Concepts](./docs/concepts.md) for deeper understanding
- Review [Facilitator Guide](./docs/facilitator.md) for session scripts
- Explore [Case Studies](./docs/case-studies.md) for real-world patterns
- Build or integrate the [AI Facilitator](./docs/ai-facilitator.md)

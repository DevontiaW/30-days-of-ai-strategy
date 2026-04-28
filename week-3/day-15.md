# Day 15: AI Talent Strategy — Buy, Build, or Borrow

## The Idea

Welcome to Week 3. Last week we obsessed over the technology — pilots, architecture, metrics. This week we shift to the harder problem: people. And the first question on the people side is the one that costs organizations the most when they get it wrong: where do the actual humans who will do this work come from?

Most leaders frame this as a hiring problem. *"We need to hire AI talent."* That framing is the first mistake. AI talent isn't a single role you hire. It's a set of capabilities you assemble — and the right mix of buy, build, and borrow depends on where you are in your AI journey, not on what's trending on LinkedIn.

I've watched companies torch six figures trying to hire a "Head of AI" before they had a single use case in production. I've also watched companies hand their entire AI strategy to a consulting firm and end up with a beautiful slide deck and zero internal capability. Both failure modes start with the wrong framing of the talent question.

## In Practice

A regional bank decided in early 2024 they needed to "build an AI team." The CHRO opened five rec slots: a Chief AI Officer, two senior ML engineers, an AI product manager, and a data scientist. The hiring window was six months. The market was brutal — every senior ML engineer they interviewed had three competing offers from FAANG companies paying $400K base.

After six months, they'd filled two of the five roles: a mid-level data scientist and an AI PM with limited technical depth. The Chief AI Officer search was still open. They'd burned through $180K in recruiter fees and lost a year of momentum.

We restructured the approach. Instead of buying five new people, we did three things in parallel:

**Built:** Took two strong existing data analysts and put them through a 12-week internal AI bootcamp combined with mentored pair-work on a real use case. Total cost: $40K each in training and 25% productivity loss for the quarter. Output: two functioning AI engineers a year later, deeply embedded in the business.

**Borrowed:** Engaged a specialist AI consulting firm for a 90-day intensive on the first three use cases. Outcome wasn't just delivery — it was knowledge transfer. The consultants worked side-by-side with the internal team and documented every architectural decision.

**Bought:** Hired one experienced AI/ML lead — not at the C-suite level, at the staff engineer level. She came from a mid-tier tech company at a more reasonable comp band, had real production AI experience, and became the durable technical anchor.

Eighteen months later, that bank had four AI initiatives in production, an internal team of seven, and roughly half the cost of their original "buy everything" plan.

## Framework

**The Buy / Build / Borrow Matrix:**

```
                    SPEED TO VALUE
                         │
                         │
        BORROW           │            BUY
   ──────────────────────┼──────────────────────
   Consulting partner   │ Senior hire from market
   Embedded vendor      │ Acquihire a small AI shop
   Outsourced pilots    │ Recruit from FAANG/labs
                         │
   Fast, expensive,     │ Fast, very expensive,
   knowledge leaks      │ retention risk
                         │
   ──────────────────────┼──────────────────────
                         │
        BUILD            │
   ──────────────────────┤
   Upskill existing     │
   Internal bootcamps   │
   Mentored pair-work   │
                         │
   Slow, cheap,         │
   durable, sticky      │
                         │
                    DURABILITY OF CAPABILITY
```

**When to lean which way:**

- **Lean BUY** when you have a high-stakes use case launching in <6 months, no internal AI talent, and the budget to compete with tech giants. Watch for: retention risk (your $400K hire will be poached in 18 months), cultural integration, and the "lone genius" failure mode where one person becomes a single point of failure.

- **Lean BUILD** when you have strong analytical talent already (data analysts, BI engineers, software engineers with strong fundamentals), a 12+ month time horizon, and a culture that supports learning. This is the highest-ROI option for most organizations — it's just slow. Watch for: under-investing in real training, treating it as "self-serve learning," and not protecting team capacity during the upskilling period.

- **Lean BORROW** when you need to move fast on a specific scoped initiative AND you're explicit about knowledge transfer. The fatal mistake is borrowing without building — you outsource the work and never develop internal capability. Every consulting engagement should produce two outputs: the deliverable and the documentation/training that lets you do it next time without them.

## The AI Talent Triad

Whatever mix you choose, you need three roles working together. Not three teams — three roles, often blended into fewer people at smaller orgs:

**1. Technical depth.** Someone who can reason about model selection, training data, evaluation, and production deployment. This person doesn't need to be a research scientist. They need to know enough about ML to make good architectural decisions and call BS on vendor pitches.

**2. Domain expertise.** Someone who deeply understands the problem space — the workflows, the customers, the regulatory landscape, the data sources. Without this person, your technical team builds elegant solutions to the wrong problem.

**3. Operational pragmatism.** Someone who can ship — project management, stakeholder navigation, scope discipline, and the political skill to keep the initiative alive when it hits the valley of disillusionment from Day 13.

Pure technical teams build demos. Pure domain teams build PowerPoints. Pure operational teams build process. You need all three.

**Hot take:** If you're a company under 5,000 employees, do NOT hire a Chief AI Officer. The role becomes a strategy consultant disconnected from real implementation. Hire a hands-on AI/ML lead instead, and let the strategy emerge from real production experience. Title inflation is a leading indicator of innovation theater.

## Your Move

List your current AI talent inventory. For each person involved in an AI initiative, mark which of the three triad roles they cover (technical / domain / operational). Then identify your gaps.

Now do the harder exercise: for each gap, decide the appropriate path — buy, build, or borrow — based on time horizon, budget, and durability needs. Be honest about what you can realistically afford. Most "buy" decisions die at compensation review; most "build" decisions die at the 90-day mark when the upskilling pace feels slow.

Document the plan in a one-page talent strategy doc. Share it with HR and the executive sponsor. The fact that it's written down makes it 10x more likely to actually happen.

## Go Deeper

- [McKinsey, "The State of AI"](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai) — Annual survey with hard data on AI talent acquisition trends, compensation benchmarks, and retention rates by industry.
- [Andrew Ng, "AI Transformation Playbook"](https://landing.ai/wp-content/uploads/2020/05/LandingAI_Transformation_Playbook_11-19.pdf) — Free PDF. Chapter 3 on AI talent is the most practical, no-nonsense framing I've seen on this topic, written by someone who's actually built large AI teams.
- [HBR, "The Skills That Matter for AI-Era Leaders"](https://hbr.org/2023/09/the-c-suite-skills-that-matter-most) — Useful read on the meta-question: what skills do *leaders* need (not just IC contributors) to manage AI-augmented teams.

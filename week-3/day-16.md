# Day 16: Upskilling at Scale

## The Idea

Yesterday we talked about hiring. Today we talk about the 95% of your workforce who *aren't* hired in for AI but whose jobs are about to change anyway.

Most upskilling programs fail because they treat AI literacy as a single curriculum applied uniformly. A junior accountant and the CFO get the same "Intro to AI" e-learning module, and somehow this is supposed to transform the organization. It doesn't. The accountant resents the time; the CFO learns nothing they didn't already know; HR claims a 78% completion rate; nothing changes.

The organizations that actually upskill at scale segment their workforce by what kind of AI fluency each role needs, then invest accordingly. They treat this as workforce strategy, not training-as-a-checkbox.

## In Practice

A 12,000-person insurance company decided in mid-2024 that "everyone needs to learn AI." Their first attempt: a mandatory 4-hour e-learning course pushed to all employees with a 90-day completion deadline. Completion rate hit 81%. Net change in actual AI usage in the business: roughly zero.

The post-mortem was instructive. Frontline claims adjusters didn't use AI more — they hadn't been given access to any AI tools that fit their workflow. Engineers had already been using Copilot for months — the course was beneath their level. Senior leaders nodded politely at the videos but had no framework for evaluating an AI investment proposal coming up to their desk. Everyone "completed training." No one's behavior changed.

The company restarted with a tiered approach. They split the workforce into three populations and built distinct programs for each. Eighteen months later, they had measurable shifts: claim adjustment cycle time down 22% (driven by AI-assisted document review the adjusters now actively used), engineering velocity up materially (Copilot + Claude with structured training on context engineering), and a leadership team that could actually evaluate AI investment proposals using a shared framework.

The lesson: AI literacy isn't one skill. It's three.

## Framework

**The Three-Tier AI Fluency Model:**

```
                    LEVEL OF DEPTH
                         │
                         │
   ┌─────────────────────┼─────────────────────┐
   │                     │                     │
   │      AI-AWARE       │     AI-FLUENT       │
   │   (everyone, ~90%   │   (managers, IC     │
   │    of workforce)    │    leads, ~9%)      │
   │                     │                     │
   │   • What can AI do  │   • Use AI tools    │
   │   • What can't it   │     effectively in  │
   │     do (limits,     │     daily work      │
   │     hallucination)  │   • Evaluate AI     │
   │   • How to use the  │     vendor claims   │
   │     tools we deploy │   • Understand      │
   │   • What "prompt    │     basic ROI       │
   │     hygiene" means  │     calculations    │
   │                     │   • Lead teams      │
   │   2-4 hours of      │     using AI        │
   │   training, role-   │                     │
   │   specific examples │   8-16 hours +      │
   │                     │   monthly practice  │
   │                     │                     │
   └─────────────────────┼─────────────────────┘
                         │
                  AI-BUILDERS
              (~1% of workforce)
                         │
   • Build, deploy, and maintain AI systems
   • Make architectural decisions
   • Train models or fine-tune them
   • Lead technical AI initiatives
                         │
   100+ hours of training, mentored work,
   real production experience
```

**The numbers are illustrative but the ratio matters.** In a 5,000-person company:
- ~4,500 people need AI-aware training (low cost, broad reach)
- ~450 people need AI-fluent training (moderate cost, role-specific)
- ~50 people need AI-builder training (high cost, deep technical)

If you flip this — most companies do — you spend disproportionate budget on building a small group while the rest of the workforce stays AI-illiterate. Your ML team builds great systems that nobody uses.

## Designing Each Tier

**AI-Aware (the bottom 90%):**

What it isn't: a generic "What is AI?" e-learning module from 2019 about machine learning history.

What it is: role-specific examples of how AI shows up in their actual work. A claims adjuster sees how AI-assisted document review changes their workflow — what it does well, where it makes mistakes, when to override it. A salesperson sees how to use AI to research prospects, draft outreach, and *not* hallucinate competitor names. A nurse sees the limits of AI clinical decision support in their specialty.

The format matters: 30-minute role-specific micro-courses beat 4-hour mandatory modules. People remember things they did, not things they watched.

The output you want: every employee can answer two questions confidently. *"What AI tools do I have access to in my role?"* and *"What's the limit — when do I escalate or override?"*

**AI-Fluent (managers and IC leads, ~9%):**

This tier needs deeper skills. They're the layer that decides whether to greenlight an AI initiative, evaluate a vendor pitch, or set expectations for their team's AI usage.

The curriculum: prompt design (real depth, not just "be specific"), AI evaluation frameworks (how do you tell if a model is actually working?), basic ROI math (cost per inference, time saved per task), and risk awareness (where does this hurt customers? where does it create regulatory exposure?).

The format: cohort-based, with peer learning. People at this level learn better from each other than from videos. Run quarterly cohorts of 15-25 people.

The output you want: each manager can run an "AI strategy session" for their team — picking 1-2 use cases, scoping a small pilot, and reporting back on what worked.

**AI-Builders (the technical core, ~1%):**

This is where you invest in real depth. ML fundamentals, MLOps, model evaluation, production deployment, fine-tuning, agent design. These people are also your evangelists — they teach the AI-fluent tier and consult with everyone else.

The format: mix of formal training (Coursera, fast.ai, university courses) and mentored work on real production systems. Pair junior builders with senior ones. Pull in external experts for specific deep dives.

The output you want: a small core team that can ship AI systems, evaluate vendor models, and translate business problems into technical specs.

## The Investment Mix

**Hot take:** Most companies under-invest in the AI-aware tier and over-invest in the AI-builder tier. The ratio is backwards. You'll get 10x more business impact from making 4,500 employees AI-aware than from making 5 more employees AI-builders. The bottleneck isn't model capability — it's adoption.

For a typical mid-market company spending $1M annually on AI upskilling, a healthy split looks like:

- **AI-Aware:** $300K-400K (broad reach, role-specific micro-content, internal champions)
- **AI-Fluent:** $400K-500K (cohort programs, manager workshops, hands-on labs)
- **AI-Builder:** $200K-300K (deep technical training for the small core)

The cheap thing — the broad foundational layer — has the highest ROI because it determines whether your AI investments actually get used.

## Your Move

Take your org chart. Map your population into the three tiers. Be conservative — 90/9/1 is roughly right for most companies, though the AI-fluent tier may run higher in tech-forward industries.

For each tier, write down:
1. The current state (what training exists today, completion rates, evidence of behavior change)
2. The target state (what does "good" look like 12 months from now)
3. The gap (what's missing — content, time, manager buy-in, tools)
4. The first 90-day investment (what gets done first)

If you've never done this exercise, expect to find that 80% of your training budget is going to the wrong tier.

## Go Deeper

- [BCG, "Closing the AI Skills Gap"](https://www.bcg.com/publications/2024/closing-the-ai-skill-gap) — Useful framework on workforce segmentation for AI literacy and the cost-of-inaction analysis.
- [WEF, "Future of Jobs Report 2025"](https://www.weforum.org/publications/the-future-of-jobs-report-2025/) — The macro view: which roles are being augmented vs. replaced, and which AI skills are most in demand by industry.
- [Lattice, "AI Upskilling Playbook"](https://lattice.com/library/the-ultimate-guide-to-ai-upskilling) — Free, practical guide focused specifically on people-leader curriculum design. Skip the marketing intro; the middle 60% is genuinely useful.

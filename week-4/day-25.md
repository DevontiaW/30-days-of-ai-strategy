# Day 25: AI Operating Models

## The Idea

If yesterday's post (org design) was about *who* sits where, today's is about *how the work flows*. Operating model is the connective tissue — the processes, decisions, and handoffs that govern what happens between "we have an AI idea" and "we have an AI system reliably producing value."

Most organizations have org charts but not operating models. They have AI engineers and data scientists but no documented intake process for AI requests, no clear stage gates, no defined ownership for production AI systems, no escalation paths when things break. The work happens — but it happens through ad-hoc relationships and tribal knowledge that doesn't scale.

When a company tells me they "can't seem to get AI moving faster," nine times out of ten the bottleneck isn't talent or technology. It's the operating model. There's no clear path from idea to production, so every initiative reinvents the path itself. That's where the months go.

## In Practice

A regional retailer had been "doing AI" for eighteen months. They had a 14-person AI team, a strong CTO, and three business unit leaders who were eager AI adopters. Yet the time from "VP wants something" to "shipped to production" was averaging 11 months across the projects we audited.

When we mapped the actual flow of work, the problem became clear. There was no intake process. VPs would email the CTO with AI ideas. The CTO would forward them to the AI team lead. The AI team lead would informally assess feasibility and schedule a "scoping conversation" two weeks out. The scoping conversation would generate a list of follow-up questions. Two weeks later, a follow-up conversation. Three weeks after that, an estimate. Then the project would enter a roadmap discussion that happened quarterly. Then it would wait for engineers to free up from existing work.

The shortest path from "VP has idea" to "engineering capacity allocated" was about four months. None of which was actual building.

We documented the operating model. Built an intake form (10 fields, 15 minutes to complete). Established weekly triage. Defined four stage gates with explicit criteria. Wrote a one-page RACI for AI projects clarifying who decides what. Set up monthly portfolio reviews using the framework from Day 22.

Six months later, the average idea-to-production time had dropped to four months. Not because anyone worked harder. Because the operating model stopped being the bottleneck.

## Framework

**The AI Work Lifecycle:**

```
   ┌───────────┐    ┌───────────┐    ┌───────────┐    ┌───────────┐
   │           │    │           │    │           │    │           │
   │  INTAKE   │───▶│ TRIAGE +  │───▶│ EXECUTION │───▶│ MONITOR + │
   │           │    │ PRIORITIZE│    │           │    │ MAINTAIN  │
   │           │    │           │    │           │    │           │
   └───────────┘    └───────────┘    └───────────┘    └───────────┘
        │                │                │                │
        │                │                │                │
        ▼                ▼                ▼                ▼

   • Submission    • Stage gates    • Execution     • Performance
     mechanism       (Day 22)         (Weeks 1-2)     monitoring
   • Standardized  • Quarterly      • RACI clarity  • Drift detection
     intake form     portfolio      • Decision      • Quarterly
   • Service-level   review            cadence        review
     expectation   • Kill criteria  • Escalation    • Maintenance
                                     paths           ownership
```

Each stage has its own discipline. Skip any stage and the work either stalls or ships and rots.

## Stage 1: Intake

**The bad version:** Email the CTO. Hope it gets attention.

**The good version:** A standardized intake form (could be a Google Form, Notion database, ServiceNow ticket — platform doesn't matter, discipline does) with these fields:

- **Submitter** + business unit
- **Problem statement** (one paragraph: what's broken or what could be better, in business terms not technology terms)
- **Affected users / scope** (rough numbers)
- **Current cost / time of the existing process** (rough estimate)
- **Why now** (what's the trigger?)
- **Proposed AI capability** (what kind of AI seems to fit?) — optional, often blank
- **Sponsor** (who at the leadership level is championing this?)
- **Desired timeline / urgency** (specific dates if relevant)

Plus a service-level expectation: "Submissions get an initial response within five business days. A scoping conversation, if warranted, within two weeks of submission."

The form does two things: it ensures the requester has thought through the basics before submitting, and it produces a queryable database of all the AI demand in the organization. The second is more valuable than people realize. After 12 months, the intake database is your most accurate read on where the business actually wants AI to go.

## Stage 2: Triage and Prioritize

**The bad version:** Every request goes to the CTO. CTO decides ad hoc which ones get attention.

**The good version:** A weekly triage meeting (45 minutes) attended by the AI team lead, a senior business representative, and a finance partner. They review every new intake against three criteria:

1. **Strategic fit:** Does it align with the organization's top priorities? (Reference the strategy from Day 01.)
2. **Feasibility:** Is the data available? Is the technical approach known? Is the affected workflow understood?
3. **ROI plausibility:** Is there a credible business case? (Reference Day 23 — most aren't.)

Each request gets one of three dispositions:

- **Promote to scoping** — eligible for a deeper feasibility study
- **Park** — interesting but not now; revisited at quarterly portfolio review
- **Decline** — not a fit, with explicit feedback to the submitter about why

Most requests should be parked or declined. That's a feature, not a bug. The portfolio model from Day 22 only works if intake is filtered.

## Stage 3: Execution

This is where most organizations have the most documented process — and where they often have the wrong process. Three things matter:

**RACI clarity for AI work.** Who's Responsible (does the work), Accountable (signs off), Consulted (provides input), and Informed (kept aware)? Write this down. AI projects suffer from "everyone's accountable" syndrome more than most other initiatives.

A working RACI template:

```
   DECISION                R    A    C         I
   ────────────────────────────────────────────────────────
   Use case selection     PM   VP   AI Lead    CTO
   Model architecture     ML   AI   Domain SME PM
   Training data sources  ML   AI   Legal      PM
   Evaluation criteria    ML   AI   Domain SME PM, VP
   Deployment go/no-go    AI   VP   ML, Legal  CTO
   Production fixes       MLOps AI  ML, Domain PM
   Kill / pivot decision  VP   CTO  AI, Finance Board
```

**Decision cadence.** Weekly tactical, monthly portfolio, quarterly strategic. Each layer makes different decisions. Without explicit cadence, every decision becomes ad hoc and dependent on the most senior person being available.

**Escalation paths.** When does an issue go from the project team to the AI lead to the CTO to the CEO? Document this. Most AI escalation happens too late, when the issue has already damaged stakeholder trust.

## Stage 4: Monitor and Maintain

The stage organizations forget exists. Operating an AI system in production is a different discipline than building one. It requires:

**Performance monitoring.** Is the model still producing accurate output as the underlying data distribution shifts? Most production AI systems experience "drift" within 6-12 months — performance degrades silently because the world has changed.

**Drift detection.** Automated checks that flag when the model's input distribution or output distribution moves materially from the training baseline. If you don't have these in place, you'll discover model degradation through angry users.

**Quarterly business review of production AI.** For every AI system in production, a 30-minute quarterly review: are the business outcomes still tracking? Is the system still aligned with the original use case? Is anyone using it less than expected? This is the equivalent of operations review for AI.

**Maintenance ownership.** Someone owns the production system. Their name is on it. They get paged when it breaks. They get credit when it ships improvements. Without explicit maintenance ownership, production AI rots — slowly, then suddenly.

**Hot take:** Most AI organizations spend 80% of their attention on building and 20% on operating. The successful long-term AI organizations flip that — once they have systems in production, 60% of attention goes to operating and improving, 40% to building. The reason: a maintained production system generating $2M of value beats a half-built new project that *might* generate $5M someday.

This is a cultural shift. AI engineers like building new things, not maintaining old ones. The org that gets this right makes maintenance prestigious — pays well for MLOps roles, celebrates production reliability publicly, and gives engineers career paths through operations work, not just new builds.

If your top engineers all want to be on greenfield projects and nobody wants to maintain production systems, your operating model has a structural problem.

## Your Move

Document your AI operating model. One page. Cover all four stages:

1. **Intake:** What's the form, what's the SLA, where does it go?
2. **Triage:** Who attends, what cadence, what criteria?
3. **Execution:** What's the RACI for AI work, what decisions happen at what cadence?
4. **Monitor and maintain:** Who owns production systems, how is drift detected, what's the quarterly review process?

If you can't answer these in writing, your operating model isn't documented — it's tribal knowledge held by 2-3 senior people. That's a single point of failure and a serious scaling constraint.

Share the draft with your AI team lead, your business unit sponsors, and your CFO. Their feedback identifies the gaps that matter most.

## Go Deeper

- [Google's MLOps Whitepaper](https://cloud.google.com/architecture/mlops-continuous-delivery-and-automation-pipelines-in-machine-learning) — The standard reference for AI/ML operating practices. Heavy on the technical side, but the framework for monitor + maintain (Stage 4) is the best free resource available.
- [HBR, "Building the AI-Powered Organization"](https://hbr.org/2019/07/building-the-ai-powered-organization) — Covers operating model design, with practical RACI and intake templates from companies that have done this well at scale.
- [Martin Fowler, "Continuous Delivery for Machine Learning"](https://martinfowler.com/articles/cd4ml.html) — Free, technical-but-accessible primer on the operating discipline of running AI systems in production. Sets the bar for what mature MLOps looks like.

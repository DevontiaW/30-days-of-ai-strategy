# Day 09: Building the Right Team

## The Idea

Here's a pattern I've seen at least a dozen times: An organization gets excited about AI, opens three headcount requisitions for data scientists, and starts interviewing candidates with PhDs. Six months later, they've got expensive talent sitting around waiting for clean data that doesn't exist, working on use cases that were never validated with the business.

The team question isn't "who do we hire?" It's "what problem are we solving, and what's the minimum team that can prove it works?"

The full-stack AI team is a myth — at least at the start. Google needs a full-stack AI team. You need 3-5 people who are clear on the problem, have access to the data, and can ship something real in 90 days.

## In Practice

Two healthcare organizations. Same industry, similar size, same ambition: use AI to reduce patient readmission rates.

**Organization A** went big. They posted roles for a Head of AI, two ML engineers, a data scientist, a data engineer, and an MLOps specialist. It took seven months to fill four of the six roles (the MLOps specialist search is still open). By the time the team was assembled, the original executive sponsor had moved to a different division. The new sponsor had different priorities. Nine months in, the team had built a solid data pipeline and a proof-of-concept model, but it had never been validated against an actual clinical workflow. Budget review killed the initiative.

**Organization B** started with two people: a clinical informatics analyst who already understood the data and a senior developer from IT who'd taken a machine learning course. They pulled in a nurse manager as their domain expert — two hours a week, no title change. They used an off-the-shelf ML platform, focused on one specific readmission scenario (heart failure patients within 30 days), and had a working pilot in 14 weeks. It wasn't perfect. But it was real, it was validated with clinicians, and it gave them the evidence to build a proper team around a proven use case.

Organization B's "team" cost a fraction of what Organization A spent. More importantly, they had something to show for it.

## The Roles You Actually Need

Forget the 15-person org chart the consulting firm showed you. For an AI pilot, you need five roles. Note: roles, not headcount. One person can cover multiple roles, especially early on.

```
┌──────────────────────────────────────────────────────────┐
│                   MINIMUM PILOT TEAM                     │
│                      (3-5 people)                        │
├──────────────────────────────────────────────────────────┤
│                                                          │
│   ┌──────────────┐        ┌──────────────┐              │
│   │   PRODUCT     │        │   DOMAIN      │             │
│   │   OWNER       │◄──────►│   EXPERT      │             │
│   │  (business)   │        │  (the user)   │             │
│   └──────┬───────┘        └──────┬───────┘              │
│          │                       │                       │
│          ▼                       ▼                       │
│   ┌──────────────────────────────────────┐              │
│   │          TRANSLATOR                   │              │
│   │   (speaks business AND tech)          │              │
│   └──────────────┬───────────────────────┘              │
│                  │                                       │
│          ┌───────┴───────┐                              │
│          ▼               ▼                              │
│   ┌──────────────┐ ┌──────────────┐                    │
│   │    DATA       │ │  ML / DATA   │                    │
│   │   ENGINEER    │ │  SCIENTIST   │                    │
│   └──────────────┘ └──────────────┘                    │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

**Product Owner (Business Side):** Owns the problem definition, success criteria, and ROI case. This person decides what "good enough" looks like and shields the team from scope creep. Not a tech person — a business person who cares about outcomes.

**Domain Expert:** The person who actually does the work today. If you're automating claims processing, this is your best claims analyst. If you're predicting equipment failure, this is your maintenance lead. They know the edge cases no dataset will reveal. Two hours a week is enough — but those two hours are non-negotiable.

**The Translator:** This is the role most organizations miss entirely. The translator speaks both languages — they can explain gradient boosting to a VP of Operations and explain why the business needs Tuesday delivery by EOD to an ML engineer. Sometimes this is a product manager with technical depth. Sometimes it's a data scientist with business instincts. It's rare, and it's the single most important role on the team.

**Data Engineer:** Hot take time. Your first technical hire for an AI initiative should not be a data scientist. It should be a data engineer. Here's why: every AI project is a data project first. If you can't access, clean, and pipeline the data, it doesn't matter how good your model is. Data scientists spend 60-80% of their time on data prep when there's no data engineer. That's a terrible use of expensive talent. A good data engineer makes everything downstream faster.

**ML Engineer / Data Scientist:** Builds and validates the model. For a pilot, you might not even need this full-time — especially if you're using a managed ML platform. Many first AI initiatives use pre-built models or AutoML tools and don't require deep ML expertise until you're optimizing and scaling.

## How the Team Evolves

As you move from pilot to production to scale, the team grows — but it grows around proven value, not speculative org charts.

```
  PILOT (0-6 mo)          PRODUCTION (6-18 mo)         SCALE (18+ mo)
  ─────────────           ──────────────────           ──────────────
  3-5 people              8-12 people                  15-25+ people

  Product Owner           Product Owner                Product Manager(s)
  Domain Expert           Domain Expert(s)             Domain Experts
  Translator              Translator / PM              AI Product Managers
  Data Engineer           Data Engineers (2-3)         Data Eng Team
  ML Eng (part-time)      ML Engineers (2-3)           ML Eng Team
                          MLOps Engineer               MLOps Team
                          Change Champion              Change Mgmt Lead
                                                       Ethics / Governance
                                                       AI Platform Team
```

Don't hire for the "Scale" column when you're still in "Pilot." That's how you end up with Organization A.

## The Hire vs. Upskill vs. Contract Decision

Not every role needs a full-time hire. Here's a simple framework:

```
                    STRATEGIC IMPORTANCE
                    Low              High
                ┌────────────────┬────────────────┐
       Short    │   CONTRACT     │   CONTRACT     │
  TIME TO       │   (Staff aug,  │   (Specialist  │
  VALUE         │    freelance)  │    consulting) │
                ├────────────────┼────────────────┤
       Long     │   AUTOMATE     │   HIRE or      │
                │   (or skip)    │   UPSKILL      │
                │                │                │
                └────────────────┴────────────────┘
```

**Contract** when you need speed or specialized expertise you won't need long-term. Initial data pipeline setup, model validation, cloud architecture design — these are all good candidates for contractors.

**Upskill** when someone internal already has 60%+ of the needed capability and the role is long-term strategic. Your best SQL developer can learn data engineering. Your analytics lead can learn ML fundamentals. Upskilling is slower but builds organizational muscle.

**Hire** when the role is core to your long-term AI capability and you can't develop it internally fast enough. Data engineering and the Translator role are the two most common first hires.

## Org Structure: Four Models

Once you're past the pilot phase, you need to decide where AI talent lives in the organization.

```
1. CENTER OF EXCELLENCE       2. EMBEDDED MODEL
   (Centralized)                 (Decentralized)

   ┌─────────┐                   BU1    BU2    BU3
   │  AI CoE  │                  ┌──┐   ┌──┐   ┌──┐
   │ ┌─┐┌─┐┌─┐│                 │AI│   │AI│   │AI│
   │ │ ││ ││ ││                  └──┘   └──┘   └──┘
   │ └─┘└─┘└─┘│
   └─────┬─────┘                 No central team.
         │                       Each BU hires its own.
   ┌─────┼─────┐
   BU1  BU2  BU3                 + Close to business
                                 - Duplication, no standards
   + Standards, shared learning
   - Can become an ivory tower


3. HUB AND SPOKE               4. FEDERATED
   (Hybrid)                       (Networked)

   ┌─────────┐                      BU1──────BU2
   │   Hub    │                      │ \    / │
   │(platform,│                      │  CoP   │
   │standards)│                      │ /    \ │
   └────┬─────┘                      BU3──────BU4
    ┌───┼───┐
   ┌┴┐ ┌┴┐ ┌┴┐                  Community of Practice
   │S│ │S│ │S│                   coordinates loosely.
   │p│ │p│ │p│                   Shared tools + standards,
   │o│ │o│ │o│                   but talent stays in BUs.
   │k│ │k│ │k│
   │e│ │e│ │e│                   + Flexibility + standards
   └─┘ └─┘ └─┘                  - Requires strong culture
                                 - Needs mature org
   + Best of both worlds
   - Harder to manage
```

**My recommendation for most organizations:** Start with a Center of Excellence for your first 1-2 pilots, then evolve to Hub-and-Spoke as you scale. The CoE builds the playbook, the shared platform, and the governance framework. The spokes embed AI talent in business units where they stay close to real problems. The hub keeps standards consistent and prevents every team from reinventing the wheel.

The Federated model sounds appealing — it's democratic and decentralized. In practice, it only works in organizations with very mature engineering cultures. If you're reading a 30-day AI strategy guide, you're probably not there yet. And that's fine.

## Your Move

Map your current AI initiative against the pilot team structure above. For each of the five roles, write down: (1) who fills this role today (or "nobody"), (2) whether that's a hire, upskill, or contract decision, and (3) the one role gap that's most likely to sink your pilot. If you have a "nobody" next to Translator or Data Engineer, fix that first.

## Go Deeper

- [Harvard Business Review, "Building the AI-Powered Organization"](https://hbr.org/2019/07/building-the-ai-powered-organization) — Thorough look at how organizational structure determines AI success more than technology choices.
- [Andreessen Horowitz, "Emerging Architectures for Modern Data Infrastructure"](https://a16z.com/emerging-architectures-for-modern-data-infrastructure/) — Understanding the technical landscape your data engineer will be navigating.
- [DJ Patil & Hilary Mason, "Data Driven"](https://www.oreilly.com/library/view/data-driven/9781491925454/) — Practical guide to building data science teams, written by people who've actually done it at scale.

# Day 11: Stakeholder Management & Expectation Setting

## The Idea

Here's a stat that should reframe how you think about AI projects: according to multiple industry surveys, 70-85% of AI initiatives fail. The common assumption is that they fail for technical reasons — bad data, wrong algorithm, insufficient compute. But when you actually autopsy failed AI projects, the leading cause of death is organizational, not technical.

The model worked. The pipeline was solid. But the compliance team killed it because nobody talked to them until month four. Or the sales team refused to adopt it because they felt threatened. Or the CEO expected a production system in six weeks because someone showed them a ChatGPT demo at a dinner party.

AI strategy is a people problem dressed in technical clothing. And the people problem has a name: stakeholder management.

**Hot take:** The biggest threat to your AI pilot isn't bad data or wrong algorithms. It's the VP who saw a ChatGPT demo and now thinks you can ship in 6 weeks.

## In Practice

A mid-size financial services firm kicked off an AI initiative to automate portions of their loan underwriting process. The data science team built a solid model, the engineering team had a deployment plan, and the project sponsor (the CTO) was fully bought in.

Six months in, the compliance team found out about the project. Not through a briefing — through a hallway conversation.

What followed was predictable: the compliance team flagged fair lending risks, demanded a full audit of the model's decision factors, required explainability documentation that didn't exist, and escalated to the Chief Risk Officer. The project was frozen for four months while the team retrofitted compliance requirements that should have been baked in from day one.

The kicker? The compliance team wasn't anti-AI. When they were eventually brought into the conversation, they had genuinely useful input about regulatory requirements that improved the model. Their resistance wasn't ideological — it was procedural. Nobody had respected them enough to ask.

Total cost of the stakeholder failure: four months of delay, $800K in additional compliance engineering, and a damaged relationship between the data science and compliance teams that took over a year to repair.

The model was never the problem.

## Framework

### The Stakeholder Map

Before you build anything, map the humans. Every AI initiative has four types of stakeholders:

- **Champions** — They get it, they want it, they'll fight for resources. Your job: arm them with facts, not hype.
- **Skeptics** — They have legitimate concerns. Maybe they've seen AI projects fail before. Maybe they understand the operational risk better than you do. Your job: listen first, address concerns with evidence, not enthusiasm.
- **Fence-sitters** — They're waiting to see which way the wind blows. They're not against you, but they won't stick their neck out either. Your job: reduce their risk of supporting you.
- **Blockers** — They will actively work against the initiative. Sometimes for good reasons (compliance, security), sometimes for political ones (budget competition, turf protection). Your job: understand their motivation before trying to change their mind.

Now map these against influence. This is where it gets strategic:

```
                    STAKEHOLDER ENGAGEMENT MATRIX

               Low Support              High Support
          ┌─────────────────────┬─────────────────────┐
          │                     │                     │
          │    MANAGE CLOSELY   │   EMPOWER + ARM     │
  High    │                     │                     │
Influence │  - Understand fears │  - Give them data   │
          │  - Address concerns │  - Make them heroes  │
          │  - Regular 1:1s     │  - Early access      │
          │  - Find common      │  - Let them present  │
          │    ground           │    wins to peers     │
          │                     │                     │
          ├─────────────────────┼─────────────────────┤
          │                     │                     │
          │    MONITOR          │   KEEP INFORMED     │
  Low     │                     │                     │
Influence │  - Don't ignore     │  - Regular updates   │
          │  - Watch for        │  - Invite feedback   │
          │    influence shifts │  - Build goodwill    │
          │  - Neutralize       │  - Future champions  │
          │    misinformation   │    as they grow      │
          │                     │                     │
          └─────────────────────┴─────────────────────┘
```

The quadrant that kills most AI projects is the top-left: **high influence, low support**. That's your compliance officer who wasn't consulted. That's the department head who sees AI as a threat to headcount. That's the VP who controls budget approval and thinks the whole thing is overhyped.

You cannot afford to ignore that quadrant. And you cannot convert them with a slide deck. You convert them with early involvement, genuine listening, and demonstrated respect for their expertise.

### The Expectation Gap

There's a persistent gap in most organizations between two narratives:

```
  C-Suite Mental Model          Reality on the Ground
  ─────────────────────         ──────────────────────
  "AI will transform            "We're cleaning data
   everything"                   in spreadsheets"

  "ChatGPT does this in         "Production ML systems
   seconds"                      need monitoring, retraining,
                                 edge case handling..."

  "Our competitors are          "Our competitors are also
   ahead of us"                  struggling with this"

  "This should take             "This will take 6-9 months
   6 weeks"                      to do properly"
```

This gap creates what I call the **Demo Trap**. Here's how it works: your team builds a proof of concept. It looks impressive in a conference room. The demo uses clean data, handles the happy path, and has a polished UI. Leadership sees the demo and mentally marks the project as 80% done.

In reality, the demo represents maybe 10-15% of the total work. The remaining 85% — edge case handling, data pipeline reliability, monitoring, retraining infrastructure, integration with existing systems, security review, compliance sign-off — is invisible to anyone who hasn't built production ML systems before.

The fix is simple but uncomfortable: **set expectations before the demo, not after.** Show a slide like this before you show anything that works:

```
  ┌───────────────────────────────────────────┐
  │  WHAT YOU'RE ABOUT TO SEE:                │
  │  - Proof of concept on clean data         │
  │  - Happy path only                        │
  │  - ~15% of total production effort        │
  │                                           │
  │  WHAT'S STILL NEEDED:                     │
  │  - Edge case handling (est. 6 weeks)      │
  │  - Data pipeline hardening (est. 4 weeks) │
  │  - Security + compliance review (est. 3w) │
  │  - Integration testing (est. 4 weeks)     │
  │  - Monitoring + alerting (est. 2 weeks)   │
  └───────────────────────────────────────────┘
```

Yes, this makes the demo less exciting. That's the point. You're trading short-term enthusiasm for long-term credibility.

### Communication Cadence

Different stakeholders need different information at different frequencies. Here's a template:

```
  STAKEHOLDER COMMUNICATION PLAN
  ═══════════════════════════════════════════════════════
  AUDIENCE        FREQUENCY    FORMAT         CONTENT
  ───────────────────────────────────────────────────────
  Executive       Bi-weekly    1-page brief   Business metrics,
  Sponsor                                     risks, decisions
                                              needed
  ───────────────────────────────────────────────────────
  Steering        Monthly      30-min         Progress vs. plan,
  Committee                    meeting        blockers, resource
                                              needs, go/no-go
  ───────────────────────────────────────────────────────
  Affected        Weekly       Email +        What's changing,
  Teams                        office hours   timeline, how it
                                              affects their work
  ───────────────────────────────────────────────────────
  Compliance /    Bi-weekly    Working        Technical details,
  Legal / Risk                 session        risk assessment,
                                              documentation
  ───────────────────────────────────────────────────────
  End Users       At           Workshop +     Hands-on training,
                  milestones   feedback       Q&A, feedback
                               session        collection
  ───────────────────────────────────────────────────────
```

Two rules for this cadence:

1. **Never surprise stakeholders.** If something is going wrong, they should hear it from you first, not discover it in a quarterly review.
2. **Match the format to the audience.** Executives want a one-page brief with decisions needed. Engineers want technical detail. End users want to know "what does this mean for my job?"

### Managing the "AI Will Take My Job" Fear

This is the elephant in every room where AI gets discussed. And most leaders handle it badly — either by ignoring it ("nobody's losing their job") or by being accidentally threatening ("AI will make us 10x more efficient," which everyone correctly translates to "we'll need fewer people").

What actually works:

- **Be honest about what will change.** Roles will evolve. Some tasks will be automated. New tasks will emerge. Don't pretend otherwise.
- **Involve affected teams in the design.** The people doing the work today understand the edge cases better than anyone. When they help design the AI system, they see themselves as co-creators, not targets.
- **Show the "AI + Human" workflow, not the "AI replaces Human" workflow.** Most successful AI implementations augment human work rather than replace it entirely. Emphasize this — and mean it.
- **Invest in reskilling early.** Don't wait until the system is deployed to figure out training. Start upskilling the affected team from day one. This is both the ethical thing to do and the practical thing to do — they'll be better at managing the AI system than anyone you could hire.

The financial services firm from the example above eventually got this right. When they relaunched the underwriting project, they embedded two senior underwriters on the development team. Those underwriters became the system's biggest advocates — because they helped build it, they understood it, and they could see how it made their expertise more valuable, not less.

## Your Move

Map your stakeholders for your top AI use case. Put every person who can influence the project's success on the 2x2 matrix (influence vs. support). For each person in the top-left quadrant (high influence, low support), write down: (1) what's their likely concern, (2) what would move them to neutral, and (3) when's the last time someone talked to them about this initiative. If the answer to #3 is "never" or "months ago," that's your first action item — not building a model, not cleaning data. A conversation.

## Go Deeper

- [Kotter's 8-Step Change Management Model](https://www.kotterinc.com/methodology/8-steps/) — The classic framework for organizational change. AI initiatives are change initiatives first and technology projects second.
- [HBR: Why So Many High-Profile Digital Transformations Fail](https://hbr.org/2018/03/why-so-many-high-profile-digital-transformations-fail) — Spoiler: it's not the technology. Organizational resistance and misaligned expectations show up in nearly every failure case.
- [Mendelow's Stakeholder Matrix](https://www.mindtools.com/a3ht0n9/stakeholder-analysis) — The original power/interest grid that the engagement matrix above is adapted from. Worth understanding the academic foundation.

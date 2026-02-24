# Day 14: Week 2 Reflection + Pilot Readiness Checklist

## The Idea

You've spent a full week in the trenches of implementation planning. Pilot design, team composition, architecture decisions, stakeholder dynamics, metrics, and the emotional reality of the "valley of disillusionment." That's a lot of ground.

Before we move into Week 3, we need to do two things: consolidate what you've learned into an honest self-assessment, and give you a concrete checklist to determine whether your pilot is actually ready to launch.

This is where most AI initiatives quietly fail. Not from bad technology, but from launching before the foundation is set. A 30-minute pause here can save you three months of rework later.

## Week 2 Recap

| Day | Core Concept | Key Takeaway |
|-----|-------------|-------------|
| 08 | Pilot Design | A good pilot has a clear hypothesis, a control group, and a kill criteria. Design it like an experiment, not a demo. |
| 09 | Team Building | You need a triad: technical talent, domain expertise, and executive sponsorship. Missing any one of these is a project risk, not a gap you'll fill later. |
| 10 | Technical Architecture | Make reversible decisions. Start with managed services, keep your options open, and don't over-engineer for scale you haven't earned yet. |
| 11 | Stakeholder Management | Map your stakeholders by influence and attitude. Skeptics need evidence, not enthusiasm. Champions need realistic expectations, not hype. |
| 12 | Success Metrics | If your only metrics are technical (accuracy, latency, F1 score), you're measuring the wrong things. Business outcomes and adoption metrics are what determine if the pilot was actually worth it. |
| 13 | Valley of Disillusionment | Every AI initiative hits a low point where results disappoint and enthusiasm fades. Expecting it, naming it, and planning for it is half the battle. |

## Self-Assessment

Answer these five questions honestly. If you're working with a team, have each person answer independently first, then compare. Disagreements are useful data.

### 1. Can you state your pilot hypothesis in one sentence?

"We believe that [AI capability] applied to [specific process] will [measurable outcome] within [timeframe]."

If you can't fill in those blanks with specific, concrete answers, your pilot isn't ready. "We believe AI will improve efficiency" is not a hypothesis. "We believe automated invoice classification will reduce manual processing time by 40% within 90 days" is.

### 2. Do you have the right people, or just the available people?

Look at the team you've assembled. Do you have genuine domain expertise from someone who does the work today? Do you have a technical lead who's built something similar before? Do you have an executive sponsor who will spend political capital when things get hard?

If you staffed this project with whoever had bandwidth, that's a warning sign. The right team with a mediocre use case outperforms a mediocre team with a great use case.

### 3. Have you established a real baseline?

Not a rough sense of how things work today. An actual measured baseline of the process you're trying to improve. How long does it take now? What's the error rate? What does it cost?

Without a baseline, you can't prove your pilot did anything. You'll end up in a meeting saying "we think it's faster" instead of "we reduced processing time from 12 minutes to 4 minutes per case."

### 4. Who's going to resist this, and what's your plan for them?

Every AI pilot creates winners and losers, real or perceived. If you haven't identified the people whose jobs, authority, or workflows will be disrupted, you're planning for a technical success and an organizational failure.

Resistance isn't irrational. It's information about what you haven't addressed yet.

### 5. What would make you kill this pilot?

If you don't have explicit kill criteria, you'll never pull the plug. Failed pilots don't announce themselves; they slowly drain budget and attention while everyone avoids the conversation. Define your "walk away" conditions now, while you're still objective.

## Common Patterns After Week 2

After working through these concepts, most people land in one of four places. Recognizing which one you're in helps you focus your energy.

**"We don't have the right team yet."** This is the most common gap, and the most dangerous to ignore. A pilot without domain expertise builds the wrong thing. A pilot without executive sponsorship dies at the first budget review. If you're missing a critical role, fill it before you launch. Launching short-staffed to hit a deadline is how you end up with a technically impressive system that nobody uses.

**"Our metrics are all technical."** You designed your success criteria around model accuracy, processing speed, or uptime. Those matter, but they're not what your CFO cares about. Go back to Day 12 and add at least two business outcome metrics and one adoption metric. If you can't connect your technical metrics to dollars, hours, or customer impact, the pilot will "succeed" technically and fail strategically.

**"We need to reset stakeholder expectations."** You realize that somewhere between the vendor demo and today, expectations got inflated. Someone thinks the pilot will be fully automated. Someone thinks it'll be done in six weeks. Someone thinks it'll handle edge cases it was never designed for. Better to have the uncomfortable conversation now than the devastating one later.

**"We're over-scoped."** You started with one clear use case and it's grown. Scope creep in AI pilots is insidious because every addition sounds reasonable in isolation. "While we're at it, could it also..." is the most expensive sentence in AI project management. Cut back to the minimum viable pilot. You can always expand after you've proven value.

## Pilot Readiness Checklist

Copy this. Print it out if you have to. Don't launch until you can check off the critical items.

### Problem Definition
- [ ] Hypothesis is stated in one clear sentence
- [ ] Baseline metrics are measured (not estimated)
- [ ] Success criteria are defined with specific numbers
- [ ] Kill criteria are defined and agreed upon
- [ ] Scope is explicitly bounded (what's IN and what's OUT)

### Team
- [ ] Technical lead identified and committed
- [ ] Domain expert(s) engaged with dedicated time
- [ ] Executive sponsor identified and briefed
- [ ] Roles and responsibilities documented
- [ ] Team has worked together before (or has a plan for the forming period)

### Data
- [ ] Required data sources identified
- [ ] Data is accessible (not just theoretically available — actually accessible)
- [ ] Data quality has been assessed on a real sample
- [ ] Data pipeline designed (how does data flow from source to model?)
- [ ] Privacy and compliance requirements reviewed
- [ ] Data gaps identified with a plan to address them

### Technical
- [ ] Architecture approach chosen (build, buy, or hybrid)
- [ ] Development and testing environment set up
- [ ] Integration path to existing systems documented
- [ ] Performance requirements defined (latency, throughput, availability)
- [ ] Vendor selected (if applicable) with PoC completed on real data
- [ ] Fallback plan exists if the AI component fails

### Organizational
- [ ] Key stakeholders mapped by influence and attitude
- [ ] Communication plan drafted (who hears what, when)
- [ ] Change management approach defined for affected workflows
- [ ] End users have been consulted (not just informed)
- [ ] Training plan exists for people who will interact with the system

### Governance
- [ ] Risk assessment completed (what can go wrong?)
- [ ] Bias and fairness testing plan in place
- [ ] Escalation path defined for edge cases and failures
- [ ] Monitoring plan for post-deployment performance drift
- [ ] Regulatory and compliance review completed (if applicable)
- [ ] Documentation standards established

### Decision Gate
- [ ] Go/no-go criteria defined with specific thresholds
- [ ] Timeline established with milestones (not just an end date)
- [ ] Budget approved with contingency
- [ ] Review cadence set (weekly check-ins, monthly steering)
- [ ] Post-pilot decision framework clear (scale, pivot, or kill)

If you checked everything, you're in better shape than 90% of AI pilots I've seen. If you have gaps, that's the work for the next few days before you launch.

If you have more than five unchecked items in the critical categories (Problem Definition, Team, Data), seriously consider delaying your launch. A two-week delay to get the foundation right is almost always cheaper than a two-month delay caused by avoidable problems.

## Looking Ahead: Week 3

We're shifting gears. Week 2 was about the mechanics of implementation — how to design, build, and measure your first pilot. Week 3 is about the harder problem: the organization.

Technology is maybe 20% of what makes AI initiatives succeed or fail. The other 80% is people. Talent strategy, upskilling, change management, culture, cross-functional collaboration, and building the internal capabilities that let you do this repeatedly instead of as a one-off.

We'll cover how to find and retain AI talent (spoiler: it's not just about salary), how to upskill your existing workforce, how to manage the change that AI creates in people's daily work, and how to build a culture where AI adoption isn't a mandate from above but a pull from the people doing the work.

If Week 2 felt technical, Week 3 will feel personal. That's by design.

## Your Move

Take 30 minutes and write a one-page Pilot Charter. Use the checklist above as your structure, but turn it into a narrative document:

- **What** you're piloting and why (the hypothesis)
- **Who** is on the team and who sponsors it
- **How** you'll measure success (and failure)
- **When** the key milestones and decision gates are
- **What's out of scope** (be explicit)

Keep it to one page. If you can't explain your pilot in one page, you don't understand it well enough yet. This document becomes your anchor when scope creeps, stakeholders ask "what are we doing again?", and the valley of disillusionment hits.

Share it with your executive sponsor before you launch. Their feedback — or their blank stare — will tell you everything you need to know about organizational alignment.

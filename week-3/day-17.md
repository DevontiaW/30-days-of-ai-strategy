# Day 17: Change Management for AI

## The Idea

Change management is a tired phrase. Every consulting deck has it. Most change management programs are box-checking exercises that generate slide decks and town halls and quarterly pulse surveys, then quietly accomplish nothing.

AI change management is different — and harder — than the change management you've done before. Here's why: AI changes the *shape* of work, not just the tools used to do it. ERP rollouts changed which screen people stared at. Cloud migrations changed where the data lived. AI changes what the human is actually for in the workflow.

When you tell a paralegal that AI will draft the first version of routine contracts, you're not just changing their software. You're telling them the part of their job that took 40 hours a week is now done by a machine in 15 minutes. The remaining job — review, judgment, exception handling, client communication — is what they'll do all day. That's a different job.

You can't change-manage your way through that with a Slack channel and a kickoff video.

## In Practice

A mid-market law firm rolled out an AI contract review tool to its 80-person corporate practice. Leadership made the rollout announcement at the all-hands meeting. They emphasized that "AI will augment your work, not replace it." They sent a polished email with FAQ. They scheduled a single training session. They opened a #ai-help Slack channel.

Six months in, adoption was at 23%. The tool was technically working — it was identifying problematic clauses with 94% accuracy on test data. But most associates were either ignoring it or using it for show. When senior partners reviewed work, they couldn't tell which contracts had been AI-screened and which hadn't. Quality wasn't materially different.

The post-mortem revealed the real story. Junior associates were terrified the tool would make them obsolete. They'd watched the firm's marketing materials shift from "we have the best people" to "we use cutting-edge AI." They could read the writing on the wall — and their response was to make the AI invisible in their workflow so the partners would still see them as essential.

Senior partners weren't using the tool because they didn't want to look like they needed help reading a contract. Their identity was wrapped up in being the experts who could spot the dangerous clause. Letting AI find it first felt like an admission that they weren't necessary either.

The firm's change management plan had addressed exactly none of this. It treated the rollout as a software implementation. It was actually an identity reorganization across three layers of seniority, and nobody had the conversation about what each layer's job was *for* in the new world.

The fix took twelve months. It involved redefining the associate's role around judgment and client interaction, redesigning the partner's review process to explicitly use AI output as a starting point, restructuring how associate work was evaluated (from hours billed to outcomes delivered), and a series of difficult conversations about what the firm valued. Adoption climbed to 78% by month 18. But the cost of getting it wrong the first time was real — they lost three top associates to firms with better-handled AI rollouts.

## Why AI Change is Different

Most change management frameworks (Kotter, ADKAR, Prosci) were developed for organizational changes that altered process or technology but kept the underlying jobs intact. AI change is different in three specific ways:

**1. It targets the cognitive core of work, not the tools around it.** When you migrate from on-prem to cloud, the accountant is still doing accounting. When you deploy AI document review, the paralegal's first-draft work is gone. The change isn't to their environment — it's to the substance of what they do.

**2. The threat is identity, not skill.** Skills can be retrained. Identity reorganization is harder. People whose self-image is "I'm the expert who reads contracts" don't easily transition to "I'm the expert who reviews AI-drafted contracts." Same skill at the surface; very different sense of self underneath.

**3. The change accelerates over time.** ERP rollouts hit a steady state. AI capabilities expand monthly. The first version of your AI contract tool reads contracts. The next version drafts them. The next version negotiates them. Every six months, the affected workforce has to recalibrate again. That's exhausting and corrosive if not managed deliberately.

These three factors mean traditional change management — communication plans, training schedules, sponsor announcements — gets you maybe 30% of the way. The other 70% is identity work, narrative work, and structural redesign.

## Framework

**The AI Change Management Stack:**

```
   ┌───────────────────────────────────────────────┐
   │         IDENTITY LAYER (top of stack)         │
   │   Who am I in the org now? What's my value?   │
   │   What does "expert" look like in this role?  │
   ├───────────────────────────────────────────────┤
   │              NARRATIVE LAYER                  │
   │   What's the story leadership is telling?     │
   │   Does it match what people are experiencing? │
   ├───────────────────────────────────────────────┤
   │            STRUCTURAL LAYER                   │
   │   How is work measured, rewarded, promoted?   │
   │   Do incentives match the new reality?        │
   ├───────────────────────────────────────────────┤
   │            PROCESS LAYER                      │
   │   How do workflows change day-to-day?         │
   │   What's the new RACI? What's automated?      │
   ├───────────────────────────────────────────────┤
   │             TOOLS LAYER (base)                │
   │   What software is being deployed?            │
   │   How is it accessed, trained on, governed?   │
   └───────────────────────────────────────────────┘
```

Most AI rollouts address only the bottom two layers (tools and process). The change "fails" because the top three layers (structural, narrative, identity) silently undermine adoption.

**You can't address the top of the stack without addressing the bottom.** But addressing the bottom alone is the most common failure mode.

## The Five Conversations You Have to Have

Whether you call this change management or organizational design, these five conversations need to happen explicitly:

**1. The "what's my job for" conversation.** With every affected role: what is the human contribution after AI takes the routine work? If you can't answer this clearly, the role is at genuine risk and you're not being honest with people.

**2. The "what gets measured now" conversation.** If associates are evaluated on hours billed, AI that reduces hours is a threat. If they're evaluated on client outcomes, AI is an enabler. Most organizations don't update their measurement systems before the AI rollout, then wonder why behavior didn't change.

**3. The "what's the new floor" conversation.** With AI in the workflow, what's the minimum competency expected of every person in the role? If your AI does first-draft contract review with 94% accuracy, you can't have associates who can't catch the 6%. Your hiring bar and competency expectations probably need to rise.

**4. The "what happens when it fails" conversation.** Who's responsible when the AI is wrong? In most organizations, this is silently the person closest to the work. That's a huge risk — both for them and for the org. Make liability explicit, not implicit.

**5. The "what does promotion look like now" conversation.** If the work AI handles was the path to seniority (junior associates building expertise through volume), what's the new path? Most organizations haven't thought this through. The result: a hollowing out where senior people retire and there's no pipeline behind them.

These conversations are uncomfortable. That's why most leaders skip them. That's why most rollouts fail.

## Hot Take

**Hot take:** If your AI rollout plan doesn't include an honest conversation about which jobs are at risk, you're lying to your workforce — and they know it. The "AI will augment, not replace" framing is sometimes true and sometimes false, and treating it as universally true makes you untrustworthy when the layoffs eventually come.

The organizations handling this best are explicit: *"This rollout will change [X role] significantly. We expect [X% reduction / restructuring] over [Y timeframe]. Here's what we're doing for affected employees: [reskilling, transitions, severance]."* The honesty is uncomfortable, but it builds the trust that makes change actually possible.

Pretending the change isn't happening — or pretending it's purely additive — guarantees the rollout becomes a slow-motion trust collapse.

## Your Move

For your most significant AI initiative, work through the AI Change Management Stack from top to bottom:

1. **Identity layer:** What does each affected role's identity look like 12 months from now? Write it as a paragraph for each role, not a bullet point.
2. **Narrative layer:** What story is leadership telling? Test it with three randomly selected affected employees — do they believe it?
3. **Structural layer:** What measurement, reward, and promotion changes are needed to align incentives with the new reality? Schedule those conversations with HR.
4. **Process layer:** What's the new workflow? Write the new RACI.
5. **Tools layer:** Which AI tools, what training, what support? (You probably already have this part planned.)

If you can answer all five layers in detail, you're ready to roll out. If you can answer only the bottom two, you're not — even if leadership thinks you are.

## Go Deeper

- [Kotter, "Leading Change"](https://www.kotterinc.com/8-steps-process-for-leading-change/) — The classic 8-step framework. Still useful for the structural/process layers; insufficient alone for AI's identity layer challenges.
- [HBR, "How to Manage AI's Disruption to the Workforce"](https://hbr.org/2024/05/how-to-manage-ais-disruption-of-jobs) — Practical guidance on the layoff/restructuring conversations most leaders avoid, with case studies from companies that handled them well.
- [MIT Sloan Management Review, "Why So Many Companies Are Stuck on Their AI Journey"](https://sloanreview.mit.edu/article/the-cultural-benefits-of-artificial-intelligence-in-the-enterprise/) — Research on why technical AI deployments succeed but organizational adoption stalls. The data backs everything in today's post.

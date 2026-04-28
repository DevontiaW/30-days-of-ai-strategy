# Day 18: AI Ethics in Practice (Not Theory)

## The Idea

Most AI ethics content is unbearable. It's either philosophy department abstractions ("the trolley problem applied to autonomous vehicles") or corporate-speak fog ("we are committed to responsible AI development"). Neither helps anyone make a real decision on a real Tuesday afternoon when their model is about to ship.

Practical AI ethics is mundane. It's a checklist of five or six things you actually do — bias testing, transparency, data minimization, audit trails, escalation paths, kill switches — applied with discipline to every AI system you put in production. The frameworks aren't sexy. The discipline is what separates organizations that get hauled in front of a regulator from organizations that don't.

Think of AI ethics the way you think of code review or security testing. Not as a moral position. As a hygiene practice.

## In Practice

A regional retailer deployed an AI-powered hiring screening tool in 2023. The tool ranked applicants for retail floor positions based on a model trained on five years of historical hiring data. It worked technically — it processed applications in seconds, the rankings correlated with their existing interviewer scores at about 0.6, and it cut their cost-per-hire by half.

In 2024, an internal audit caught a problem. The model was systematically downranking applicants from certain ZIP codes — which mapped almost perfectly onto majority-minority neighborhoods. The historical training data reflected past hiring biases. The model had absorbed and operationalized them at scale.

The retailer pulled the tool. They disclosed to the EEOC. They paid a settlement to a class of applicants who'd been screened out. Total cost: roughly $4M in direct costs, plus reputational damage that took 18 months to repair.

Here's what's important about this story: every single ethical issue was visible *before* deployment if anyone had looked. The training data hadn't been audited for protected-class disparities. There was no bias testing in the model evaluation phase. There was no human-in-the-loop on the final ranking. There was no transparent disclosure to applicants that AI was scoring them.

The model wasn't unethical because of bad intent. It was unethical because of skipped checklist items. The same checklist items that, if applied as routine practice, would have caught the issue in the validation phase and saved the company millions.

## The Five Things You Actually Do

Forget the abstract frameworks. These are the five concrete practices that make up practical AI ethics:

**1. Bias testing on real protected-class dimensions.**

Before any AI system that affects people goes to production — hiring, lending, pricing, content moderation, healthcare triage, criminal justice — you test it on subgroups defined by protected classes (race, gender, age, disability status, geographic markers that proxy for any of the above).

You're looking for **disparate impact** — the model performing materially differently across subgroups. The standard threshold from EEOC's "four-fifths rule" is a useful starting point: if the selection rate for any group is less than 80% of the rate for the highest group, you have a problem worth investigating.

This isn't perfect, but it's a defensible bar. The point is to *test* — to know whether the disparity exists. Most organizations don't even check.

**2. Transparency to the people affected.**

If an AI system is making a decision about a person — accepting their loan application, ranking their resume, denying their insurance claim — they should know AI was involved. This is now law in some jurisdictions (EU AI Act, NYC Local Law 144 for hiring tools, Colorado AI Act); it should be policy everywhere.

Transparency doesn't mean revealing the model's weights. It means: (1) AI was used in this decision, (2) here are the factors it considered, (3) here is how to request human review.

**3. Data minimization.**

The training data and the input features should be the minimum necessary to do the task. Not the maximum available. Most organizations default to "throw everything in and let the model sort it out" — which violates data protection law in the EU, creates regulatory exposure in the US, and bakes irrelevant correlations into the model.

For every feature in your model, ask: *would I be comfortable defending this in front of a regulator?* If the answer is no, remove it.

**4. Audit trails for every consequential decision.**

For any AI decision that affects a person or a meaningful business outcome, you need a logged record: what input was used, what version of the model produced the output, what the output was, and what action was taken downstream.

This serves three purposes: regulatory defense (you can prove what happened), debugging (you can trace failures), and continuous improvement (you can learn from edge cases).

If you can't reconstruct an AI decision a year later, you don't have an audit trail. You have a black box and a liability.

**5. A kill switch.**

Every AI system in production needs a documented, tested process to turn it off. Not just disable the API — fully revert the workflow to its pre-AI state. If your AI system fails badly tomorrow morning, can you switch back to the manual process within 24 hours?

This is the hardest one to maintain because the manual process atrophies. People forget how the old workflow worked. Documentation goes stale. The fallback path silently rots.

Test your kill switch quarterly. Run a fire drill. If you can't actually go back to the pre-AI process, the kill switch is theatrical — and you've lost the ability to walk away when you need to.

## Framework

**The AI Ethics Hygiene Stack:**

```
   ┌────────────────────────────────────────────────┐
   │                                                │
   │   PRE-DEPLOYMENT (gates before launch)         │
   │   ──────────────────────────────────────       │
   │   • Bias testing on protected classes          │
   │   • Data minimization audit                    │
   │   • Stakeholder review (legal, compliance,     │
   │     affected user advocate)                    │
   │   • Kill switch documented & tested            │
   │                                                │
   ├────────────────────────────────────────────────┤
   │                                                │
   │   AT DEPLOYMENT (transparency to users)        │
   │   ──────────────────────────────────────       │
   │   • Disclosure that AI is in the loop          │
   │   • Explanation of factors considered          │
   │   • Path to human review / appeal              │
   │                                                │
   ├────────────────────────────────────────────────┤
   │                                                │
   │   POST-DEPLOYMENT (ongoing operations)         │
   │   ──────────────────────────────────────       │
   │   • Audit trail logging every decision         │
   │   • Quarterly bias re-testing                  │
   │   • Kill-switch fire drill (quarterly)         │
   │   • Edge case review (monthly)                 │
   │                                                │
   └────────────────────────────────────────────────┘
```

Build this once. Apply it to every AI system. Document the application. The cost of the discipline is real but small — perhaps 5-10% of project time. The cost of skipping it can be a $4M settlement and a year of brand repair.

## The Hard Cases

The five practices above are easy in the abstract and hard in the specific. Three places where teams routinely struggle:

**"We don't have the data to test for bias."** Common in B2B contexts where you don't collect demographic data on customers. The answer isn't to skip the testing — it's to use proxies (zip code, name patterns, language) carefully and acknowledge the limitations. Some bias testing beats none.

**"Disclosure will hurt adoption."** Sometimes true. Customers don't want to be told they're being scored by AI. The answer is not to hide it. The answer is to design AI use cases where disclosure is a feature, not a bug — and to be very cautious about deploying AI in contexts where you'd rather customers not know.

**"The kill switch is impossible because we've already retired the old process."** This is a serious risk and a sign of poor change management. If you've burned the boats, you have a single point of failure with no recovery. The answer is to invest in maintaining a viable manual process — even if it's slower and more expensive — until the AI system has earned a year of clean operating history.

## Hot Take

**Hot take:** "AI ethics committee" without "AI ethics checklist" is theater. Most ethics committees meet quarterly, debate principles in the abstract, and produce position papers nobody reads. They have no power to halt deployments. They get briefed on AI initiatives after the fact. They are designed to manage reputational risk, not actual ethical risk.

The organizations that handle AI ethics seriously embed the five practices above into their deployment process — bias testing happens before the QA gate, kill switches are reviewed at launch, audit logs are part of the build pipeline. They have an ethics review process, not an ethics committee. The committee's role is to handle the edge cases the process doesn't cover.

## Your Move

For your most consequential AI system in production (or planned), audit it against the five practices:

1. Has it been tested for bias on protected classes? Document the result.
2. Are people affected by it told that AI is in the loop? Show me the disclosure language.
3. What features does it use, and can you defend each one to a regulator?
4. Is there an audit log of every consequential decision it makes?
5. Is the kill switch documented, tested in the last 90 days, and able to revert to a viable manual process?

If you can't say yes with evidence on all five, you have an exposure. Schedule the work to close the gaps before the next regulatory cycle, customer incident, or audit forces you to.

## Go Deeper

- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) — The most credible US-government-blessed framework. Practical, implementable, and free. If you build your AI ethics program around one external reference, this is it.
- [EU AI Act, plain-English summary](https://artificialintelligenceact.eu/) — The most comprehensive AI regulation globally. Even if your org doesn't operate in the EU, it's becoming the template that other jurisdictions copy.
- [ACM, "Algorithmic Accountability Reporting"](https://dl.acm.org/doi/10.1145/3287560.3287588) — Academic but readable. Lays out the audit trail and accountability structures that mature AI deployments need. Good source for your governance documentation.

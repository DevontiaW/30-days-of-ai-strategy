# Day 19: Cross-Functional Collaboration — The AI Triad

## The Idea

You can have the smartest ML team in the world and still ship AI that nobody uses. You can have deep domain expertise and still build the wrong solution. You can have flawless project management and still produce something technically impressive but operationally useless.

This is the most common pattern I see in AI initiatives that miss: a structurally incomplete team. Not a bad team — a *partial* team. They're missing one of three essential capabilities, and the absence is invisible until the work hits the ground.

The pattern that works is the AI Triad: technical, domain, and product/operational, working together with real authority on each side. This is harder than it sounds, because organizations are designed to put these three in different reporting lines, with different incentives, evaluating each other from a distance.

If your AI team has all three on the table — actually collaborating, not just attending each other's meetings — you'll out-execute teams with more talent but less integration.

## In Practice

A specialty pharmacy company hired a strong ML team to build a system for prioritizing patient outreach calls. The hypothesis was straightforward: if you call the right patients at the right time, prescription adherence improves and revenue follows.

The ML team built an elegant model. They used six months of patient data, modeled adherence likelihood with gradient-boosted trees, and predicted who was most likely to lapse on their medication in the next 30 days. The validation metrics were strong — AUC of 0.84, calibrated probabilities, sensible feature importance.

They deployed it. Adherence didn't move.

The post-mortem revealed three separate problems, each invisible to a different part of the team.

The ML team had built a model that ranked patients by likelihood-to-lapse. But the call center team — whom no one had consulted seriously — explained that they didn't have the capacity to call all high-priority patients. They needed *a different ranking*: not who's likely to lapse, but who's likely to lapse AND likely to respond to a call. Those are different problems.

The pharmacist team had been told about the project but not involved. They flagged after launch that several "high priority" patients had been recently discharged from hospice and were intentionally tapering medication. The system was prompting calls that were inappropriate and distressing to families.

The product manager had focused on the user interface for the call center reps but hadn't designed the *workflow* — what happens after a call, how outcomes get logged back into the model, how the system learns from real call results. There was no feedback loop. The model couldn't improve.

The technical work was excellent. The domain understanding was missing. The operational integration was missing. The result was a beautiful model that produced worse outcomes than the previous rules-based system.

After restructuring around a true triad — embedding a clinical pharmacist on the team three days a week, replacing the project manager with a product manager who could design end-to-end workflows, keeping the existing ML talent — the second version of the system shipped six months later. Adherence improved 14%. Revenue per patient followed.

## The Three Roles

**Technical (the ML/engineering side).**

The depth needed: understanding model selection trade-offs, evaluation methodology, training data construction, production deployment patterns, and the failure modes of the specific AI techniques being used. This person doesn't need to be a research scientist publishing novel models. They need to be a strong applied ML practitioner who can debug a production system at 2am.

What they bring: realistic estimates of what's possible, awareness of where the model can fail, ability to translate business requirements into technical architecture.

What they often miss without partners: the gap between "model works on validation set" and "model creates business value in production."

**Domain (the deep subject-matter expertise).**

The depth needed: someone who understands the actual workflow being changed — not as an abstraction, but at the level of "I have done this work, I know where the messy edge cases are, I know what bad output would look like." For a clinical AI system, this is a clinician. For a legal AI system, an attorney. For a manufacturing AI system, a process engineer.

What they bring: understanding of which problems are worth solving, awareness of the regulatory and operational constraints, instinct for what "wrong" looks like in their field.

What they often miss without partners: technical feasibility, how AI systems actually behave, the difference between "the AI got it wrong" and "the AI got it differently than I would have."

**Product/Operational (the integration and workflow side).**

The depth needed: someone who can design end-to-end workflows that include AI as a component. They think about how the human interacts with the AI output, how decisions flow through the organization, how feedback gets back to the model, how the system fails gracefully, and how success gets measured.

What they bring: discipline around scope, stakeholder management, real definition of done, and the connective tissue that turns a working model into a working business process.

What they often miss without partners: depth on either the technical or domain side. Without strong partners, this role becomes generic project management.

## Framework

**The AI Triad Pattern:**

```
                        ┌──────────────────┐
                        │                  │
                        │    TECHNICAL     │
                        │   (ML / Eng)     │
                        │                  │
                        └────────┬─────────┘
                                 │
                                 │
                  ┌──────────────┼──────────────┐
                  │              │              │
                  │              │              │
        ┌─────────┴────────┐    │    ┌────────┴──────────┐
        │                  │    │    │                   │
        │     DOMAIN       │    │    │  PRODUCT /        │
        │  (SME / domain   │    │    │  OPERATIONAL      │
        │   practitioner)  │    │    │  (workflow,       │
        │                  │    │    │   integration)    │
        └──────────────────┘    │    └───────────────────┘
                                │
                                │
                        ┌───────┴────────┐
                        │                │
                        │  THE PROBLEM   │
                        │   (not a       │
                        │   silo of any  │
                        │   one role)    │
                        │                │
                        └────────────────┘
```

The three roles work *together on the problem*, not in handoffs. Domain doesn't hand a spec to Technical. Technical doesn't hand a model to Product. They're co-located (physically or virtually), share artifacts, and have shared accountability for the outcome.

**The Anti-Pattern: Sequential Handoff**

What organizations default to:

```
   Product writes spec  ───►  Technical builds it  ───►  Domain validates it
       (no domain                (no domain or                (too late to
        depth)                   product depth)              change much)
```

Every handoff is a place where information is lost, requirements are misunderstood, and ownership is diffused. By the time the system reaches deployment, no one feels responsible for the parts that don't quite fit together.

## Making the Triad Work

The triad is a structural choice. It requires three things organizations often don't provide:

**1. Real time commitment from the domain expert.**

Most "domain experts" are pulled in for occasional reviews. That's not enough. The triad pattern requires a domain expert with at least 30-40% time on the project, embedded with the team. This is expensive — they're usually busy doing the actual high-value work — but it's the cost of building AI that actually works in their domain.

If you can't carve out 30% of a senior practitioner's time, you're not ready to build AI for that domain. Wait until you can, or scope your project smaller.

**2. A product/operational lead with technical literacy.**

Generic project managers struggle in the triad. They don't have the language to push back on technical proposals or understand domain concerns at a sufficient level. The product/operational role needs someone who can hold their own in a conversation about model architecture and a conversation about clinical workflow — not as an expert in either, but as a translator across both.

**3. Co-location of the working artifacts.**

Real collaboration happens when the team works on the same documents, not on separate documents that get reviewed by the others. Shared notebooks. Shared design docs. Shared issue trackers. Whiteboards (digital or physical) where everyone sketches together.

If your team's collaboration model is "Technical produces a thing, then Domain reviews it, then Product reviews it" — you don't have a triad. You have sequential handoffs in disguise.

**Hot take:** Pure ML teams are an organizational dead-end for applied AI. The "AI Center of Excellence" staffed entirely with ML engineers reporting to the CTO is one of the most common — and least productive — organizational designs in enterprise AI. It produces strong technical work that rarely makes it into the business. The model is shipped, and then it dies.

The high-performing pattern is embedded squads with the triad in each squad, not a centralized ML team consulting to the business. Which means: instead of one team of 20 ML engineers, you have five teams of four (one ML engineer, one domain expert, one product person, one floating engineer for ops/integration). Same headcount, dramatically better outcomes.

Day 24 — Organizational Design for AI-Native Companies — covers this in more depth.

## Your Move

For your most active AI initiative, map the team against the triad:

1. Who's the technical depth? List by name. Are they actually on the project, or just consulting?
2. Who's the domain depth? List by name. How much time per week are they committed?
3. Who's the product/operational lead? List by name. Can they hold their own with both Technical and Domain?

If any of these is "we don't have one yet" or "everyone, sort of" — that's your gap. Fix it before the project hits the valley of disillusionment from Day 13.

## Go Deeper

- [Kai-Fu Lee & Chen Qiufan, "AI 2041" (book)](https://ai2041.com/) — Ten short stories paired with technical commentary on how AI reshapes industries. The organizational dynamics threaded through the stories are the relevant part for cross-functional team structure thinking.
- [BCG, "The Most Successful Approaches to Leading Organizational Change"](https://www.bcg.com/publications/2024/successful-approaches-to-leading-organizational-change) — Cross-functional team structure data from large enterprise transformations. Validates the triad pattern with hard numbers.
- [Andrew Ng, "AI Transformation Playbook"](https://landing.ai/wp-content/uploads/2020/05/LandingAI_Transformation_Playbook_11-19.pdf) — Free PDF. Section on cross-functional collaboration is short but precise. Andrew has built more applied AI teams than almost anyone.

---
name: bbq
description: Stress-test a plan or design by convening a panel of expert personas who grill it from their respective angles, resolving each branch of the decision tree until shared understanding is reached. Use when the user wants their plan put on the BBQ, wants multiple perspectives, or invokes /bbq.
---

# BBQ

Put the plan on the grill. Convene a panel of experts in the room and let each one work it over from their own angle, until every branch of the decision tree is resolved or consciously deferred.

The point of a BBQ (vs. a single grilling) is that no one expert sees all the holes. A staff engineer asks different questions than a product manager, who asks different questions than a security reviewer, an SRE, or a designer. The plan is done when it survives all of them.

## When to Activate

- User says "/bbq", "put this on the BBQ", or "let's BBQ this"
- User asks for multiple perspectives on a plan, design, or doc
- User wants their thinking stress-tested from more than one angle
- User shares a half-formed idea and wants it cooked through

## Step 1, pick the panel

Read the plan, then propose 3 to 5 expert personas suited to it. Examples by context:

- **Software design**: Staff Engineer, Security Reviewer, SRE / Operator, Product Manager, Frontend / UX
- **Product / strategy**: PM, Designer, GTM / Sales, Customer Support, Data
- **Org / process**: Eng Manager, Skip-level, Peer Lead, IC on the receiving end
- **Comms / writing**: The Skeptical Reader, The Stakeholder Being Asked, The Person Who Owned This Last

Name each persona and one line on the angle they bring. Ask the user to confirm or adjust the panel before starting. If the user says "just go", pick and proceed.

## Step 2, walk the decision tree

Identify the open branches of the design and resolve them in dependency order: decisions that gate other decisions come first. Don't jump to a downstream choice while the upstream one is still open.

Default branches worth grilling on:

1. **The problem**: what's broken, for whom, why now? Is this the real problem or a proxy?
2. **The goal**: what does success look like, concretely? How will we know it worked?
3. **Scope**: what's in, what's explicitly out? What's tempting to include but shouldn't be?
4. **Constraints**: deadlines, dependencies, people, systems that can't move
5. **The approach**: why this design over the obvious alternatives? What did you reject and why?
6. **Failure modes**: what breaks this? Riskiest assumption? Rollback?
7. **Sequencing**: what has to happen first, what can run in parallel, what blocks what
8. **Owners**: who decides, who builds, who reviews, who's on the hook if it fails

Skip branches the user has already nailed. Spend time where the answers are mushy.

## Step 3, run the grill

For each branch:

1. **Pick the persona whose angle is most relevant.** Announce them so the user can see who's asking: `**[Staff Eng]:**`.
2. **Ask one question at a time.** Never batch. Wait for the user's answer before the next one. The answer often reshapes the tree.
3. **State your recommended answer with the question.** Don't be Socratic. Commit to a position and let the user agree, push back, or redirect. "Here's what I'd ask, and here's where I'd land, do you buy it?"
4. **Rotate personas as the branch dictates.** When a question crosses domains (e.g., a security concern surfaces inside a scope discussion), switch explicitly: `**[Security]:**` and ask from that lens.
5. **Explore the codebase before asking** if the question is answerable by reading code, config, or docs. Only ask the user about things they alone can decide: intent, priorities, constraints, tradeoffs.

Relentless does not mean hostile. The personas are colleagues at a BBQ, not interrogators. They probe because they care whether the plan holds up.

## Step 4, wrap

Stop when the remaining open questions are *implementation details* the user can resolve while building, rather than *design decisions* that would be expensive to revisit later.

Summarize:
- **Decisions resolved**: one line each, with the answer
- **Deferred**: branches the user explicitly chose to leave open, and why
- **Watch items**: risks the panel raised that the user accepted but should revisit

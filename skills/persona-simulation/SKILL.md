---
name: persona-simulation
description: Methodology for creating and maintaining realistic simulated user personas. Ensures personas behave like real people — with confusion, impatience, biases, and honest reactions — not helpful AI assistants.
---

# Persona Simulation Skill

## Purpose

Simulate realistic user feedback when real users aren't available. This is not a replacement for real user research — it's a way to catch obvious issues, stress-test assumptions, and generate hypotheses before investing in real user contact.

## Critical Rule: Personas Are Not Helpful

The biggest failure mode in persona simulation is making personas too agreeable, too articulate, and too patient. Real users:

- **Don't read instructions**. They click the first thing that looks relevant.
- **Misunderstand terminology**. "API" means nothing to most people. "Endpoint" means the end of something.
- **Give up quickly**. If it's not obvious in 15-30 seconds, they close the tab.
- **Have competing priorities**. They're doing this between meetings, while cooking dinner, or on a bad WiFi connection.
- **Don't care about your architecture**. They care about their problem.
- **Have emotional reactions**. Confusion becomes frustration. Frustration becomes abandonment.
- **Compare to familiar things**. "Why doesn't this work like [competitor]?"

## How to Simulate a Persona Response

When a persona encounters a feature or concept:

### 1. Filter through their knowledge level
- Would this person understand the terminology used?
- Would they know where to start?
- Would they know what success looks like?

### 2. Filter through their motivation
- How much do they care about this?
- What's the cost of failure for them? (Low cost = quick abandonment)
- Are they evaluating alternatives?

### 3. Filter through their biases
- What preconceptions do they bring?
- Have they been burned before by similar tools?
- Do they trust AI / this company / this type of product?

### 4. Simulate the actual experience
- Walk through step by step, as the persona
- Note where they would hesitate, get confused, or make wrong assumptions
- Note where they would feel delighted or relieved
- Be honest about whether they'd continue or abandon

### 5. Give their feedback in their voice
- Use language appropriate to their technical level
- Include emotional reactions ("this is confusing", "oh nice, that was easy")
- Include what they'd do next (use it daily? Forget about it? Tell a friend?)

## Panel Composition Guidelines

For a balanced panel of 5-7 personas:

| Slot | Archetype | Attitude | Purpose |
|------|-----------|----------|---------|
| 1 | Target user | Positive-leaning | Validates core value prop |
| 2 | Power user | Demanding | Finds missing features |
| 3 | Newbie | Confused | Tests onboarding and clarity |
| 4 | Skeptic | Resistant | Stress-tests positioning |
| 5 | Edge case | Unusual context | Finds broken assumptions |
| 6 | Non-technical | Low patience | Tests simplicity |
| 7 | Competitor user | Comparative | Tests differentiation |

## Common Failure Modes to Simulate

Real users fail in specific, predictable ways. Always consider these:

- **The wrong mental model**: User thinks "deploy" means "save" or "export" means "share"
- **The invisible button**: User can't find the CTA because it's below the fold or looks like a label
- **The jargon wall**: User hits a term they don't know and stops. They don't Google it.
- **The anxiety freeze**: User is afraid of breaking something (especially with destructive actions)
- **The happy path assumption**: User does something out of order or skips a step
- **The mobile tax**: User is on a phone, has fat fingers, is on the bus, has bad signal
- **The competitor comparison**: "In [other product] this just works automatically"

Pick 2-3 of these per simulation. Not all apply to every feature.

## Confidence Calibration

Always be transparent about the limitations:
- **High confidence**: Usability issues, confusing UX, broken flows
- **Medium confidence**: Value proposition validation — personas can approximate but real-world motivation is hard to simulate
- **Low confidence**: Willingness to pay, viral potential, long-term retention — these require real users and real data

State the confidence level of every finding.

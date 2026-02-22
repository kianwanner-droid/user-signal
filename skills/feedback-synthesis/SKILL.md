---
name: feedback-synthesis
description: Methodology for synthesising user feedback (real or simulated) into clear, actionable build decisions. Produces structured output that Claude Code can act on directly.
---

# Feedback Synthesis Skill

## Purpose

Turn messy, contradictory user feedback into a clear build recommendation. The output of synthesis should be something a developer (or Claude Code) can immediately act on — not a report that sits in a doc.

## The Synthesis Process

### 1. Cluster Feedback by Theme

Group all feedback into themes. A theme is a pattern that 2+ users mentioned independently. Ignore one-off comments unless they reveal a critical safety or usability issue.

Example themes:
- "Confusing onboarding" (4/7 personas struggled)
- "Missing feature X" (3/7 personas asked for it)
- "Pricing unclear" (2/7 personas mentioned it)

### 2. Rank by Impact

For each theme, ask one question: **If we don't fix this, how many users bounce?**

- **Most bounce** → fix first
- **Some bounce** → fix second
- **Annoyed but stay** → fix later
- **Nobody noticed** → don't fix

Skip the Frequency × Severity × Actionability formula. It's slower than just asking "who bounces?"

### 3. Identify Contradictions

When personas disagree, that's signal — not noise. Common patterns:

- **Power users vs newbies**: Power users want more options; newbies want simplicity → Consider progressive disclosure
- **Technical vs non-technical**: Different mental models of the same feature → Consider multiple entry points
- **Enthusiasts vs skeptics**: Core value prop works for some, not others → Narrow your target, don't try to please everyone

Document contradictions explicitly. They're where the hardest product decisions live.

### 4. Produce the Build Recommendation

#### Verdict (pick one):

- **BUILD** — Clear signal that this solves a real problem. Proceed with the validated scope below.
- **PIVOT** — The problem is real but the solution needs rethinking. Here's what to change.
- **KILL** — Insufficient evidence of demand, or the problem isn't painful enough. Spend your time elsewhere.
- **NEEDS MORE DATA** — Simulated feedback is inconclusive on key questions. Talk to real users before proceeding.

#### Confidence Level:

- **High** — 5+ personas agree, findings align with known behaviour patterns
- **Medium** — 3-4 personas agree, some contradictions but clear direction
- **Low** — Split panel, novel use case, or findings that depend heavily on simulated vs real behaviour

#### Validated Requirements:

List only requirements that the panel confirmed. Format as user stories:

```
As a [persona], I want [feature], so that [outcome].
Priority: Must-have / Should-have / Nice-to-have
Evidence: [which personas, what they said]
```

#### Recommended MVP Scope:

The absolute minimum you could build to test the most important hypothesis. Not "v1" — the smallest experiment that generates learning.

#### What NOT to Build:

Equally important. List features or ideas that came up but that the panel didn't actually validate. These are traps — they sound good but aren't worth building yet.

## Output Format for Claude Code

When the developer wants to proceed with building, produce a structured spec:

```
## Feature: [Name]
## Validated by: User Signal research panel ([date])
## Verdict: BUILD (confidence: high/medium/low)

### Problem Statement
[1-2 sentences, in user language]

### Target User
[Specific description]

### Requirements (Priority Order)
1. [Must-have requirement] — [evidence]
2. [Must-have requirement] — [evidence]
3. [Should-have requirement] — [evidence]

### Out of Scope (explicitly)
- [Thing we're NOT building and why]

### Success Criteria
- [How we'll know this worked]

### Known Risks
- [Contradictions or low-confidence findings to watch]
```

This format is designed to be directly usable as a prompt for Claude Code to implement.

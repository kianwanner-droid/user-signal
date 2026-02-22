---
name: user-research
description: Domain knowledge for running effective user research within the development loop. Claude draws on this skill automatically when the developer is making product decisions, discussing features, or considering what to build.
---

# User Research Skill

## When to activate

Activate this skill when the developer is:
- Discussing what to build next
- Debating between feature approaches
- Making assumptions about what users want ("users will love this")
- About to start building without validating

**Do NOT activate when:**
- Developer is debugging existing code
- Developer is doing routine tasks (formatting, refactoring, tests)
- Developer has already validated and is just implementing
- The conversation is about technical architecture, not product decisions

You don't need to run the full `/research` command every time. Sometimes a quick nudge is enough: "Who specifically would use this, and how are they solving it today?"

## Core Principles

### 1. The Build Trap
The biggest risk in AI-assisted development isn't building slowly — it's building the wrong thing fast. Code is cheap. User insight is expensive. Always validate before committing.

### 2. Problem Before Solution
Never research a solution without first confirming the problem is real. "Would you use a feature that does X?" is a bad question. "Tell me about the last time you struggled with Y" is a good one.

### 3. Behaviour Over Opinion
What users say they want and what they actually do are different things. Research should focus on observed behaviour, current workarounds, and real pain points — not hypothetical preferences.

### 4. The Mom Test
Questions should pass the Mom Test: even your mom couldn't give you a false positive. Bad: "Do you think this is a good idea?" Good: "When was the last time you had this problem, and what did you do about it?"

### 5. Small N, High Signal
You don't need statistical significance. 5 good user conversations surface 80% of usability issues. The goal is insight, not proof.

## Research Methods (Lightweight)

### For early ideas (pre-build):
- **Problem interviews**: Do people actually have this problem?
- **Solution sketches**: Show a rough concept, watch reactions
- **Competitive analysis**: What exists? Why isn't it good enough?
- **Jobs-to-be-done**: What job is the user hiring this product to do?

### For prototypes (during build):
- **Walkthrough testing**: Watch someone use it for the first time
- **Think-aloud protocol**: "Tell me what you're thinking as you try to..."
- **Five-second test**: Show the UI for 5 seconds. What did they remember?
- **Task completion**: Can they do the thing without help?

### For shipped features (post-build):
- **Usage data analysis**: Are people actually using it?
- **Follow-up interviews**: Why / why not?
- **Feature retention**: Do they come back?

## How to Synthesise Research

1. **Pattern match** — What did 3+ people say independently?
2. **Surprise findings** — What contradicted your assumptions?
3. **Severity rank** — Blocker > major pain > nice-to-have
4. **Actionability** — Can we fix this? Is it in scope?
5. **Clear recommendation** — Build / pivot / kill. No sitting on the fence.

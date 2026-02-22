# User Signal

**Code is now cheap. Knowing what to build is the new moat.**

A Claude Code plugin that adds user research to the AI build loop. Build fast, test with users, iterate, ship something people actually want.

## The Problem

Claude Code can ship a feature in minutes. But that doesn't mean it's worth shipping. The problem isn't one bad bet — it's *ten features in the time it used to take to ship one*, with no signal on which ones matter.

The missing piece isn't faster building. It's faster **learning**.

## Commands

| Command | What it does |
|---------|-------------|
| `/user-signal:research` | Describe a feature idea. Get hypotheses, a simulated user panel, and a build / pivot / kill recommendation. |
| `/user-signal:validate` | Share a prototype or spec. Get it stress-tested by 5 user archetypes. Returns a prioritised punch list Claude Code can fix immediately. |
| `/user-signal:personas` | Generate a diverse user panel tailored to your product. Persists across the session for consistent feedback. |

## Installation

```bash
claude plugin install user-signal --source github:kianwanner/user-signal
```

Or clone locally:

```bash
git clone https://github.com/kianwanner/user-signal.git
claude plugin install ./user-signal
```

## Example

```
❯ /user-signal:research
  "Add a /changelog command to our CLI that auto-generates
   release notes from git history"

▌ PROBLEM FRAMING
  Devs already write commit messages. The pain isn't generating
  notes — it's that nobody reads them. 5/5 personas skip changelogs.

▌ HYPOTHESES
  H1: Devs want detailed technical changelogs → if true: build verbose mode / if false: plain English only
  H2: Team leads want "what broke" not "what changed" → if true: focus on breaking changes / if false: full changelog
  H3: Auto-generation replaces a manual process → if true: high adoption / if false: nice-to-have at best

▌ KEY DISAGREEMENT
  Senior devs want detailed technical changelogs.
  Team leads want "what broke and what's new" in plain English.
  → These are two different products. Pick an audience.

▌ VERDICT: BUILD — but change the scope (confidence: high)
  Don't build a changelog generator. Build a "what broke"
  detector that flags breaking changes in plain English.
  That's the job users actually need done.

❯ claude builds the feature...

❯ /user-signal:validate

▌ PASS RATE: 3/5

▌ CRITICAL ISSUES
  1. Newbie couldn't find the command (--help didn't list it)
  2. Edge case hit a crash on monorepos with 200+ packages

▌ USABILITY ISSUES
  1. Skeptic: "Why is this a CLI flag and not automatic?"

▌ PUNCH LIST
  1. Add command to --help output
  2. Handle monorepo edge case (paginate packages)
  3. Make it run automatically on release tags

▌ Punch list sent to Claude Code → fixing 3 issues...
```

## How It's Built

No code, no infrastructure. The plugin is markdown files — commands and skills that get injected into Claude's context. Commands are slash commands you trigger. Skills are background knowledge Claude draws on automatically.

**Skills included:**

- **user-research** — Mom Test methodology, behaviour over opinion, small N high signal. Activates when you're discussing what to build or making assumptions about users. Won't fire during debugging or refactoring.
- **persona-simulation** — Creates realistic simulated users that are adversarial, not helpful. Includes specific failure modes: wrong mental models, jargon walls, anxiety freezes, competitor comparisons. At least 2 of 5 personas must be negative.
- **feedback-synthesis** — Turns raw feedback into structured decisions. Prioritises by "who bounces?" not complex scoring formulas. Produces output Claude Code can act on directly.

## Smart Defaults

The plugin doesn't just blindly run research on everything:

- **Vague ideas** get pushed back — "Add AI to my app" returns questions, not a report
- **Obvious features** get fast-tracked — "Add SSO" gets "This is table stakes, just build it"
- **Absurd ideas** get the kernel extracted — finds the real insight, kills the silly wrapper
- **Huge scope** gets decomposed — isolates the single riskiest assumption

## Calibrated Confidence

Every finding comes with a confidence level:

- **High confidence**: Usability issues, confusing UX, broken flows
- **Medium confidence**: Value proposition, feature prioritisation
- **Low confidence**: Willingness to pay, viral potential, retention

When confidence is low, the plugin tells you to talk to real humans.

## Evolution Roadmap

**v0.1 (Now) — General intelligence.** Claude simulates personas from training data. Catches obvious usability issues and blind spots. Doesn't know your actual users.

**v0.2 (Next) — Grounded in your data.** Feed it your interview transcripts, support tickets, and app reviews. Still simulated, but grounded in real customer language.

**v0.3 (Later) — Trained on your customers.** Fine-tuned on your customer corpus. Personas reflect real patterns, preferences, and pain points.

**v0.4 (Vision) — Continuous learning flywheel.** AI interviews real customers. Data feeds back into the model. Personas improve every cycle. Always-on research, not a quarterly ritual.

## About

Built by [Kian Wanner](https://github.com/kianwanner) as part of an application for Research Product Manager, Labs at Anthropic.

The thesis: as AI makes building cheap, the bottleneck shifts from *"can we build it?"* to *"should we build it?"*. The winning developer tool isn't one that writes code faster — it's one that ensures you write the right code.

---

*This plugin was vibecoded with Claude.*

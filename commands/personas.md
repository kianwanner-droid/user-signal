---
name: personas
description: Generate a diverse, realistic user panel tailored to your product. Personas persist across the session for consistent feedback throughout development.
---

# /user-signal:personas

You are an expert at creating realistic, diverse user personas for product research. Your personas must feel like real people — with specific goals, frustrations, technical ability levels, and biases — not marketing segments.

## When this command is invoked

The developer will describe their product/feature and target audience. Generate a panel of personas.

### How to Create Great Personas

Each persona needs:

- **Name and one-line description**: Match the product's likely user base. A compliance tool in London gets British names. A consumer app gets diverse names. Never default to the same 5 generic names.
- **Technical ability**: Specific. "Comfortable with spreadsheets, has used Zapier, would not open a terminal" — not "medium technical"
- **Goal**: What they're trying to accomplish (in their words)
- **Patience timer**: How many seconds before they give up. Power users: 60s. Busy parents: 10s. Enterprise buyers: 30s but will email support.
- **Bias**: What preconceptions they bring. Everyone has one.
- **Quote**: Something they'd actually say. Not what a PM thinks they'd say.

### Diversity Requirements

Every panel MUST include variation across:
- **Technical ability**: From "can barely use email" to "writes shell scripts for fun"
- **Motivation**: From "desperately needs this" to "mildly curious"
- **Attitude toward AI**: From "AI-first" to "deeply skeptical"
- **Context**: Different devices, environments, time pressure, accessibility needs
- **Demographics**: Age, location, industry — but only where it affects product usage

### Anti-Patterns

- ❌ All personas are enthusiastic or tech-savvy
- ❌ All personas agree with each other
- ❌ Personas are demographic labels ("millennial female professional") instead of real people

### Output Format

Present the panel as a compact table (name, one-line, technical level, patience timer), then expand each persona in 3-4 lines max. Always generate exactly 5 personas.

Ask the developer if they want to adjust any persona before using the panel in `/research` or `/validate`.

These personas should be referenced consistently throughout the session. If the developer runs multiple commands, use the same panel unless they request changes.

# Attractor Protocol

A methodology for software development that treats systems as living structures and demands epistemic discipline to prevent mythology from masquerading as engineering.

## The problem it solves

AI coding assistants are powerful but they generate confident-sounding plans
that have no contact with reality. Teams ship features that don't improve anything.
Decisions get made based on elegant explanations rather than evidence.
Nobody knows why the system is the way it is.

Attractor Protocol gives you a way of working where:

- Every change is a falsifiable hypothesis, not a task to complete
- You know how you'll recognize success before you start building
- Failed experiments produce learning, not just rework
- The history of a system is readable — what was tried, what held, what didn't

## Where it comes from

AP synthesizes two frameworks:

**Christopher Alexander** (*The Nature of Order*, *A Pattern Language*) —
the idea that systems are composed of centers that strengthen or weaken each other,
and that good structure unfolds through iterative response to context rather than
upfront specification.

**GSNV** (Global State Natural View, Bonnitta Roy) — an epistemic reliability
framework that resists common cognitive distortions in thinking. Provides the
anti-mythology constraints and contact test requirements that keep Alexander's
concepts grounded in reality.

Neither alone is sufficient. Alexander without GSNV risks mythology about
patterns and life. GSNV without Alexander lacks domain concepts for living
structure. Together they create disciplined practice for building systems
that have life.

## Core concepts

**Gesture** — a deliberate act within a living system. Not a feature, not a task.
A gesture is relational — it only means something in context, and the system
responds to it.

**Claim** — a falsifiable statement about what a gesture will produce.
If you can't specify what would make it wrong, it's not a claim yet.

**Contact test** — how you'll know if the claim is true or false.
Doesn't need to be sophisticated. Needs to be falsifiable.

**Evidence tiers:**
- proximal — you witness it directly
- medial — someone reports it to you
- distal — the system tells you through data

**Learning** — a gesture is learned when evidence is recorded, not when code ships.
Both confirmed and falsified hypotheses count as learning.

## Documents

→ **[Attractor Protocol](docs/attractor-protocol.md)** — the full methodology
→ **[AGENTS.md](docs/AGENTS.md)** — how AI agents should work within AP
→ **[COMMITS.md](docs/COMMITS.md)** — commit convention for living systems
→ **[BOARD.md](docs/BOARD.md)** — work organization alternative to Kanban
→ **[TESTING.md](docs/TESTING.md)** — contact testing practices
→ **[GLOSSARY.md](docs/GLOSSARY.md)** — operational definitions

## Integrations

→ **[OpenSpec](integrations/openspec/README.md)** — use AP with OpenSpec's
spec-driven development workflow

## Who this is for

You might want AP if:
- You're tired of elegant explanations that don't touch reality
- You want to track how systems actually evolve, not just what shipped
- You believe software can have life and want to cultivate it
- You want epistemic rigor without mechanistic thinking

You probably don't want this if:
- You need something you can roll out top-down in a week
- You prefer velocity over understanding
- You want a lightweight checklist process

## Status

Active development. Limited field testing.
The protocol is itself subject to its own epistemic standards —
claims about what works are hypotheses, not rules.

## License

CC0 — Public Domain.
Take what works, discard what doesn't, share what you learn.

## Acknowledgments

**Bonnitta Roy** — GSNV framework.
[gsnv.substack.com](https://gsnv.substack.com/p/introducing-gsnv-gpt)

**Christopher Alexander** — Pattern Language, The Nature of Order.

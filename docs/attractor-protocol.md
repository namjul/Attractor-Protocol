# Attractor Protocol
**Building software as living structure through evaluative dialogue**

---

## What Is This?

Attractor Protocol is a methodology for software development that treats systems as **living structures** rather than mechanical assemblies, and demands **epistemic discipline** to prevent mythology from masquerading as engineering.

It synthesizes:
- **GSNV** (Global State Natural View) — epistemic reliability framework that resists cognitive malware
- **Christopher Alexander** — pattern language thinking about living systems and wholeness

The result is a way of working that:
- Takes "life in systems" seriously as an observable quality
- Refuses to accept claims without evidence
- Treats code, commits, and conversations as participants in an evolving whole
- Maintains contact with reality through measurement and revision

---

## Who Is This For?

**You might want Attractor Protocol if:**
- You're tired of elegant explanations that don't touch reality
- You want to track how systems actually evolve, not just what features shipped
- You believe software can have "life" and want to cultivate it
- You're skeptical of both pure rationalism and pure intuition
- You want epistemic rigor without mechanistic thinking

**You probably don't want this if:**
- You're satisfied with conventional development practices
- You prefer velocity over understanding
- You want a lightweight process
- You need something you can roll out top-down in a week

---

## Core Documents

### [AGENTS.md](./attractor-protocol.AGENTS.md) — Protocol for AI Development Agents
**Use when:** Working with AI coding assistants (Cursor, Copilot, Claude, etc.)

Guides AI agents to:
- Understand systems as living structures composed of centers
- Plan interventions using the EAI Socratic Loop
- Identify and flag mythology before it becomes code
- Track co-variance (how changes propagate)
- Revise understanding when evidence contradicts assumptions

**Key concepts:** Centers, fields, gestures, unfolding, mandatory planning phase

---

### [COMMITS.md](./attractor-protocol.COMMITS.md) — Commit Convention
**Use when:** Recording changes in version control

A living systems alternative to Conventional Commits that organizes work by:
- **Center impact** (what are you strengthening/creating/dissolving?)
- **Contact tests** (how will you know if it worked?)
- **Evidence gathering** (validation vs. falsification)

**Commit types:** `strengthen`, `create`, `dissolve`, `revision`, `unfolding`, `simplify`, `field`, `repair`

**Key difference from Conventional Commits:** Types describe interventions in living systems, not categories of mechanical changes.

---

### [BOARD.md](./attractor-protocol.BOARD.md) — Work Organization
**Use when:** Planning and tracking work

Living systems alternative to Kanban that organizes by:
- Evidence state (not status)
- Center impact (not feature completion)
- Contact tests (not acceptance criteria)

**Columns:** Proposed → Field Preparation → Active Intervention → Evidence Gathering → Validated & Monitoring (+ Revision Required)

---

### [TESTING.md](./attractor-protocol.TESTING.md) — Contact Testing
**Use when:** Verifying claims about improvements

Prevents mythology by requiring falsifiable tests for all improvement claims.

**Core principle:** The test doesn't need to be sophisticated—it needs to be **falsifiable**.

**12 self-evident examples** showing how to match evidence patterns to available resources.

---

### [GLOSSARY.md](./attractor-protocol.GLOSSARY.md) — Terminology & Concepts
**Use when:** You encounter unfamiliar terms or need operational definitions

Defines 50+ terms with:
- Operational definitions (observable criteria)
- Contact tests (how to verify presence/absence)
- Examples (what counts, what doesn't)

**Key terms:** Center, field, co-variance, mythology, contact test, exploratory capacity, trophic lift, up-hierarchy

Terms are ordered pedagogically—foundational concepts first, dependent concepts later.

---

## Quick Start

### For AI-Assisted Development

1. Read [AGENTS.md](./attractor-protocol.AGENTS.md) (45 min)
2. Copy AGENTS.md to your repository
3. Configure AI: Add as system prompt or project context
4. Practice on one small subsystem
5. Observe: Does the AI flag mythology? Ask for contact tests? Identify centers?

### For Team Adoption

1. Read [Glossary](./attractor-protocol.GLOSSARY.md) sections on GSNV and Alexander
2. Pick one protocol: Start with commits OR agent protocol, not both
3. Practice on one project (don't roll out organization-wide)
4. Gather evidence: Does it improve understanding? Reduce mythology? Track evolution?
5. Revise: Adapt based on your observations

### For Individual Practice

1. Start with commits (easier to adopt solo)
2. Write one commit per day using Attractor format
3. Track: Do you catch yourself making unsupported claims?
4. Notice: Does requiring contact tests change what you build?
5. Expand: Add agent protocol once commits feel natural

---

## Theoretical Foundations

### Christopher Alexander: Living Structure

Christopher Alexander's work (*The Nature of Order*, *A Pattern Language*) provides the vocabulary for talking about "life" in systems.

**Key insights:**
- Systems are composed of **centers** that strengthen or weaken each other
- Good design **unfolds** through iterative response to context
- **Wholeness** emerges from relationships, not assembly
- **Patterns** are observations, not prescriptions
- Structure has degrees of **life** (observable, not mystical)

**What we take:** Domain concepts (centers, fields, living structure, coherence)

**What we add:** Contact tests to prevent these concepts from becoming mythology

---

### GSNV: Global State Natural View

GSNV is an epistemic reliability framework developed by Bonnitta Roy that resists "malware" in thinking.

**Source:** [Introducing GSNV-GPT](https://gsnv.substack.com/p/introducing-gsnv-gpt)

**The 7 cognitive malwares:**
1. **Darwinian Attitude** — discrete agents optimizing in fitness landscapes
2. **Stratified Reality** — layers with "lower = more real"
3. **Misplaced Concreteness** — confusing abstractions with concretes
4. **Substance Hierarchy** — smaller parts are the real story
5. **De-Animation** — agency only at privileged levels
6. **Newtonian Causality** — linear pushing and pulling
7. **Isolated Variables** — properties detached from fields

**GSNV's alternative:**
- Think in **evaluative gradients** and **co-variant fields**
- Use **up-hierarchical integration** (wholes and parts co-constitute)
- Treat causation as **field resolution**, not mechanical forcing
- Demand **contact tests** to prevent theories floating free of reality

**What we take:** Epistemic discipline (contact tests, anti-mythology, revision ritual)

**What we add:** Application to software development and AI-assisted coding

---

### The Synthesis

**Alexander without GSNV** risks mythology about patterns and life.
**GSNV without Alexander** lacks domain concepts for living structure.
**Together** they create disciplined practice for building systems that have life.

---

## Example: Attractor Protocol in Action

### Scenario: Adding a color picker to a drawing app

**Conventional approach:**
```
feat(ui): add color picker

Added color picker component with RGB sliders and preset swatches.
Closes #234
```

**Attractor Protocol approach:**

**Planning phase (AGENTS.md):**
```
Aim: Increase color usage in drawings from current 11% to >30%

Claim: Users avoid color because mode-switching breaks flow

Assumptions:
- Color is meaningful to users (not proven)
- Current picker is the barrier (not lack of interest in color)
- Mode-switching is the specific problem (vs. discoverability, complexity, etc.)

Contact tests needed:
- Session recordings: do users attempt to access color picker?
- Analytics: what % of strokes use non-default colors?
- Interviews: why don't users use color?

Competing hypotheses:
1. Mode-switching friction
2. Picker too complex
3. Color not relevant to user tasks
4. Picker not discoverable

Next step: Gather evidence to distinguish these before building
```

**Commit (COMMITS.md):**
```
create(color-access): add inline color selection during gestures

Aim: Reduce mode-switching friction in color selection

Claim: Gesture-based color selection will increase color usage
from 11% to >30% of strokes without interfering with drawing precision

Assumptions:
- Users can learn velocity-based selection quickly
- Gestural selection won't interfere with drawing precision
- Color IS meaningful (users want it, picker blocks access)

Evidence motivating this:
- Session recordings: 89% never open current picker
- Heatmaps: cursor never approaches picker location
- Interviews: 5/7 mentioned wanting "easier color access"

Center-Impact:
  Created: gesture-color - velocity-based color selection
  Strengthened: drawing-flow - no mode switching required
  Weakened: color-picker-UI - reduced to 8 swatches

Contact:
  Success-if: Color usage >30%, accidental triggers <5%
  Failure-if: Users confused, high error rate, revert to black
  Measurement: Stroke color analytics + accidental trigger rate
  Timeline: Evaluate after 100 user sessions (~2 weeks)

Co-Variance:
  - gesture-handlers (velocity detection logic added)
  - persistence-layer (gesture-color state storage)
  - undo-stack (tracks color in gesture history)

Closes: #234
```

**Revision after evidence (COMMITS.md):**
```
revision(color-access): revert gesture-based selection

Aim: Restore drawing precision after failed experiment

Previous Claim No Longer Holds:
Hypothesis that gestural color selection could be both accessible
and non-interfering was falsified by evidence.

Evidence (revision trigger):
- Accidental color changes: 23% of strokes (target was <5%)
- User feedback: 12/15 reported "frustrating" or "unpredictable"
- Session duration dropped 18%
- New user abandonment: 34% left after <3 minutes

Updated Understanding:
Color selection and drawing are competing centers at this
interaction scale. Users cannot simultaneously think about
drawing intent and color-selection gestures. The problem is
not "mode-switching cost" but "discoverability."

Center-Impact:
  Dissolved: gesture-color (failed as center, interfered with drawing)
  Strengthened: drawing-center (precision restored)
  Weakened: color-accessibility (back to original problem)

Next Step:
Investigate discoverability solutions that don't require
in-gesture interaction:
- Always-visible minimal palette
- Keyboard shortcuts
- Separate input device (pen button, touch)

BREAKING CHANGE: Gesture-based color selection removed

Closes: #234 (original feature)
Refs: #678 (user feedback issue)
```

**Key difference:**
- Conventional: Ship feature, move on
- Attractor: State hypothesis, gather evidence, revise when falsified, track learning

---

## Common Questions

### "Isn't this just good software engineering?"

Partially. The practices aren't novel (testing, documentation, revision), but the **ontology** is:

**Conventional thinking:** Systems are assemblies of features
**Attractor thinking:** Systems are living structures composed of centers

This ontological shift changes what you measure (center strength vs. feature completeness), what counts as progress (coherence vs. shipped features), and when you delete code (dead structure vs. working code).

### "Do I need to use all the documents?"

No. They work together but can be adopted independently:

- **Just COMMITS.md:** Improves how you think about changes
- **Just AGENTS.md:** Improves AI collaboration
- **Just GLOSSARY.md:** Shared vocabulary for team
- **All together:** Full methodology

### "Can I use this with Agile/Scrum/etc.?"

The protocol is philosophically incompatible with purely mechanical methodologies but can coexist with practices that value iterative development, continuous feedback, sustainable pace, and adaptability.

**Tension points:** Story points vs. center impact, velocity tracking vs. coherence tracking, upfront decomposition vs. emergent unfolding.

Some teams use Attractor Protocol for *how* they work while maintaining Agile for *when* (sprints, standups, etc.)

### "What if my team thinks 'centers' are too abstract?"

Start with the epistemic discipline, not the vocabulary:

**Instead of:** "We need to identify centers"
**Try:** "What would show this change succeeded? What would show it failed?"

The vocabulary helps, but the **contact test requirement** is the core.

### "How is this different from DDD/Clean Architecture?"

Those focus on **structure** (how to organize code).
Attractor Protocol focuses on **epistemology** (how to know if structure is working).

**They're compatible:** Use DDD for architecture, Attractor for verification.

### "Can AI actually follow this protocol?"

Current evidence (limited):
- Claude with AGENTS.md context does flag mythology
- GPT-4 can write Attractor-format commits when prompted
- Both struggle with genuine center identification (need human guidance)

**Best results:** Human identifies centers, AI maintains discipline around contact tests and mythology detection.

### "This seems like overhead?"

**Contact test for the protocol itself:**

**Success-if:** Catches mythology before it becomes code, prevents dead structure from accumulating, enables faster learning from failed experiments

**Failure-if:** Ritual compliance without understanding, slows down without improving quality, team resents the process

If it's overhead, stop using it.

---

## Protocol Governance

### This Protocol Is a Living Document

**Evolution principle:** Protocols evolve based on observations from users at all levels.

**How to propose changes:**
1. Document your observation (what pattern doesn't fit?)
2. Specify contact test (how would we validate the change?)
3. Discuss evidence (does community have similar observations?)
4. Experiment in limited scope
5. Update if evidence supports

**Anti-pattern:** Protocol becomes unchangeable via authority ("that's the protocol, don't question it")

**See:** [AGENTS.md Protocol Governance](./attractor-protocol.AGENTS.md#protocol-governance--evolution) for full process

### Disagreement Resolution

**Principle:** Resolve by evidence, not authority.

When patterns conflict:
1. Both parties specify observations and evidence
2. Identify distinguishing observables
3. Design contact test
4. Run smallest experiment
5. Update understanding based on results

**Red flags:**
- "I'm senior, we do it this way"
- "The protocol says X" (without explaining why)
- Power predicts whose pattern wins

**See:** [AGENTS.md Disagreement Resolution](./attractor-protocol.AGENTS.md#disagreement-resolution-process) for full process

---

## Current Status

**Version:** 1.0
**Last updated:** 2026-01-31
**Status:** Active development, seeking early adopters

**Documents:**
- ✅ AGENTS.md (complete)
- ✅ COMMITS.md (complete)
- ✅ BOARD.md (complete)
- ✅ TESTING.md (complete)
- ✅ GLOSSARY.md (complete)

**Known limitations:**
- Limited field testing (needs real-world validation)
- AI agent integration still experimental
- Tooling support minimal (no automated linters, etc.)

**Seeking:**
- Teams willing to experiment and provide feedback
- Evidence of what works/doesn't work
- Observations of patterns we missed
- Revisions based on your context

---

## Getting Help

**Questions about:**
- **Concepts:** See [GLOSSARY.md](./attractor-protocol.GLOSSARY.md)
- **AI agents:** See [AGENTS.md](./attractor-protocol.AGENTS.md)
- **Commits:** See [COMMITS.md](./attractor-protocol.COMMITS.md)
- **Board:** See [BOARD.md](./attractor-protocol.BOARD.md)
- **Testing:** See [TESTING.md](./attractor-protocol.TESTING.md)
- **Disagreements:** See [AGENTS.md Governance](./attractor-protocol.AGENTS.md#protocol-governance--evolution)

---

## License

CC0 - Public Domain

This protocol exists to be used, modified, and evolved. Take what works, discard what doesn't, share what you learn.

---

## Acknowledgments

**Theoretical foundations:**

- **Bonnitta Roy** — Developer of GSNV (Global State Natural View), an epistemic reliability framework that provides the anti-mythology constraints and contact test requirements central to this protocol. GSNV's identification of the 7 cognitive malwares and its alternative framework of evaluative gradients, co-variant fields, and up-hierarchical integration form the epistemic backbone of Attractor Protocol. [gsnv.substack.com](https://gsnv.substack.com/p/introducing-gsnv-gpt)

- **Christopher Alexander** — Pattern Language, The Nature of Order. Alexander's work on living structure, centers, wholeness, and unfolding provides the domain vocabulary for understanding software systems as living structures rather than mechanical assemblies.

**Inspiration:**
- Conventional Commits (which we conceptually replace)
- Domain-Driven Design (complementary approach)
- Systems thinking traditions
- Resilience theory (back-loop, collapse-aware design)

---

**The system is living to the extent that it can surprise us.**

If all behavior is predictable, the system is mechanical.
If all explanations are elegant, they are probably mythological.
Contact with reality—through evidence, measurement, and revision—is required.

**Welcome to Attractor Protocol.**

# Glossary

**Operational definitions for Attractor Protocol terms.**

Terms are ordered pedagogically—foundational concepts first, dependent concepts later.

---

## Epistemic Foundation Terms

### Observable
Something that can be directly perceived or measured by multiple observers independently.

**Example:** "Button click rate dropped 40%" (observable) vs. "Users feel frustrated" (inference).

---

### Operational Definition
A definition specifying observable criteria for membership.

**Format:** "By [term] I mean [criteria]. This counts: [example]. This doesn't: [counterexample]."

**Example:** "By 'strong center' I mean: attracts >60% of user interactions, removal causes >30% drop in task completion. This counts: undo button. This doesn't: decorative header."

---

### Measurable Indicator
A quantifiable signal tracking intervention success.

**Required:** What to measure, how to measure it, success threshold, failure threshold.

**Example:** "Stroke latency <16ms measured via frame time analytics" (measurable) vs. "Better performance" (vague).

---

### Falsifiable
A claim that can be proven wrong through observation.

**Contact test:** Ask "What would make this false?" If no answer, claim may be mythology.

**Example:** "Color usage will exceed 30%" (falsifiable) vs. "This improves user experience" (unfalsifiable).

---

### Contact Test
A reality-contact mechanism specifying how to verify or falsify a claim.

**Required forms (at least one):**
- Falsifiable example: "This would show the claim is wrong: [scenario]"
- Counterexample: "This case doesn't fit: [case]"
- Measurable indicator: "We measure [X] to test this"
- Minimal experiment: "Smallest test: [action]"
- Real-world constraint: "Must account for [limitation]"

See [TESTING.md](./attractor-protocol.TESTING.md) for detailed patterns.

---

### Mythology
Coherent explanation without operational meaning, falsifiability, or evidence.

**Contact test:** Ask "What would make this false?" If no answer, it's mythology.

**Example:** "Creates flow and synergy" (mythology) vs. "Reduces action-to-feedback time from 200ms to 50ms" (operational).

---

## Epistemic Discipline Terms

### Fact
Observed, documented, or measured phenomenon verifiable by others.

**Example:** "Average session duration is 12 minutes" (fact) vs. "System feels sluggish" (subjective).

---

### Evidence
Observed data, documented behavior, or measured outcomes. Not assumptions or inferences.

**Example:** "89% of users disable feature X" (evidence) vs. "Users probably want Y" (speculation).

---

### Assumption
A belief stipulated for analysis that may or may not be true. Always label explicitly.

**Format:** "Assumption: Users prefer X over Y" (not "Users prefer X").

**Requires:** Contact test to verify.

---

### Inference
Conclusion derived from facts plus assumptions. Show your work.

**Format:** "Given [facts] and [assumptions], we infer [conclusion]."

---

### Speculation
Hypothetical possibility not yet tested. Always label as speculation.

**Example:** "Speculation: Users might want constraint-based tools despite low current usage."

---

### Revision
Required update when new evidence contradicts previous assumptions or claims.

**Mandatory elements:**
1. State what changed (new evidence)
2. State what no longer holds (falsified assumption)
3. State new belief (updated understanding)
4. Explain the update (why this matters)

**Anti-pattern:** Ego-preserving narratives ("I was right in spirit").

---

### Term Drift
Gradual change in word meaning over a conversation, causing confusion.

**Prevention:** Define terms operationally at first use, flag definition changes as explicit revisions.

---

## Core GSNV Concepts

### Field
The relational context in which centers exist and interact.

**Contact test:** Does changing field X alter what kinds of actions users produce? If not, it's inert structure.

---

### Evaluative Gradient
A directional tension in the field that guides resolution toward coherence without external selection pressure.

**Not:** Fitness landscapes, optimization targets, or goal states.

---

### Co-Variance
Mutual dependence where changes to one element necessarily propagate to related elements.

**Contact test:** If you can change X without touching semantically-related Y, coupling has been lost.

---

### Complex Potential States
The field of possible forms that could arise from current tensions, not yet resolved into actualized structure.

**Not:** Pre-existing options waiting to be selected.

---

### Trophic Lift
How background conditions enable foreground events.

**Example:** Drawing gesture requires: thermodynamics → life → evolution → nervous systems → culture → software → this interface.

---

### Up-Hierarchy
Relational structure where wholes integrate parts and parts participate in wholes, with neither ontologically privileged.

**Not:** Substance hierarchy (smaller = more fundamental).

**Contact test:** If you can fully explain the whole by describing parts, it's not an up-hierarchy.

---

### Global State Natural View (GSNV)
Epistemic framework treating reality as co-variant fields resolving tensions, not discrete agents optimizing in external environments.

**Core commitment:** Relations precede entities; wholes and parts mutually constitute each other.

**Source:** Bonnitta Roy - [Introducing GSNV-GPT](https://gsnv.substack.com/p/introducing-gsnv-gpt)

---

## Christopher Alexander Concepts

### Center
A focal point that attracts attention, organizes surrounding elements, and gains strength through interaction.

**Operational definition:**
- Attracts attention (measurable: dwell time, repeated interaction)
- Organizes surrounding elements (testable: removal weakens neighbors)
- Gains strength through use (observable: usage patterns over time)

**Contact test:** If removing X causes no degradation in surrounding coherence or usage, X is not functioning as a center.

---

### Center-Impact
Specification of how an intervention affects existing or creates new centers.

**Required elements:**
- Center name (operational, not vague)
- Type of impact (strengthened/weakened/created/dissolved)
- How/why (mechanism or observable outcome)

**Format:**
```
Center-Impact:
  Strengthened: [center-name] - [how/why]
  Weakened: [center-name] - [how/why]
  Created: [center-name] - [what it organizes]
  Dissolved: [center-name] - [why removal increases coherence]
```

**Good examples:**
- "Strengthened: error-recovery - reduced retry latency from 200ms to 50ms"
- "Dissolved: grid-overlay - 89% disabled it, removal improved drawing flow"

**Bad examples (mythology):**
- "Strengthened: user experience"
- "Enhanced synergy between components"

---

### Coherence
The quality of fitting together without contradiction; mutual support among parts creating stable whole.

**Contact test:** Does simplifying by removal increase or decrease system stability?

**Measurable:** Reduced cognitive load, faster time-to-competence, fewer user errors.

---

### Wholeness
Integrated quality where parts mutually reinforce rather than compete.

**Contact test:** Does the system have emergent properties unpredictable from isolated part descriptions?

---

### Living Structure
Organization that supports new, unplanned uses and adapts without breaking.

**Contact test:** Did users discover uses you didn't anticipate?

**Measurable:** Users create workflows not in documentation, feature composition yields unexpected value.

---

### Dead Structure
Organization that blocks adaptation, serves no function, or exists only as historical residue.

**Contact tests:**
- No usage in interaction logs
- Documented user confusion or abandonment
- Blocks planned evolution paths
- Removal requires no compensating changes

---

### Gesture
Time-based user action that operates on fields to create or transform centers.

**Required qualities:**
- Legible: Users predict outcomes before completion
- Reversible: Undo preserves context, not just state
- Context-sensitive: Same gesture produces different results in different fields

**Contact test:** If gesture feels identical regardless of context, it's operating mechanically not relationally.

---

### Pattern
Observed regularity in successful structures, not a rule to apply mechanically.

**Critical distinction:** Patterns describe what works, not prescribe what to build.

**Contact test:** Can you name valid exceptions? If not, you're treating it as a rule.

---

### Unfolding
Incremental, context-sensitive evolution where each step enables the next without upfront specification.

**Not:** Assembly (combining pre-designed parts) or execution (following a plan).

**Contact test:** Did the final form surprise you? If it exactly matched initial vision, it was assembly not unfolding.

---

## Interaction & System Quality Terms

### Feedback Loop
A cycle where action produces information that informs the next action.

**Quality measures:**
- Latency: Time from action to feedback (<16ms ideal)
- Legibility: Clarity of cause-effect relationship
- Completeness: Does feedback guide next step?

**Contact test:** Does removing feedback cause more errors or longer task time?

---

### Legibility
Making cause-effect relationships visible and predictable.

**Contact test:** Can new users predict outcomes before acting?

**Measurable:** Time-to-competence, error rate in first sessions.

---

### Reversibility
Ability to undo actions while preserving context, not just state.

**Good:** Undo in drawing restores stroke, color, tool state, viewport.

**Poor:** Undo removes stroke but loses what tool was active, zoom level, scroll position.

**Contact test:** After undo, can users continue immediately without reorientation?

---

### Mode-Switching
Transition between interaction contexts requiring mental reorientation.

**Contact test:** Do users make errors immediately after mode switches? Do they avoid features requiring mode changes?

---

### Exploratory Capacity
System's ability to support unplanned, user-discovered interactions and workflows.

**Contact test:** Did users create workflows not documented or anticipated?

**Trade-off:** Precision often reduces exploratory capacity.

---

## Anti-Pattern Terms

### Inert Structure
Organization that exists but doesn't participate in active relationships.

**Contact test:** If removing X requires updating nothing else, X is inert.

---

### Premature Abstraction
Creating generality before concrete cases validate the need.

**Contact test:** Can you point to three concrete cases this abstraction serves? If not, it's premature.

---

### Complexity Debt
Accumulated abstractions, dependencies, or indirections increasing maintenance burden without proportional value.

**Contact test:** Can a new contributor understand this without explanation?

**Measurable:** Lines of code per feature, dependency count, time-to-competence.

---

## Process & Change Terms

### Intervention
Deliberate change to system structure, not just content.

**Example:** Changing how undo tracks state (intervention) vs. fixing UI text typo (not intervention).

---

### Incremental Change
Small, reversible modifications allowing learning before commitment.

**Contact test:** Can you revert this change in <1 hour?

---

### Co-Variant Change
Change where modifying one element requires updating related elements to maintain coherence.

**Contact test:** If you change module X without updating semantically related Y, does system lose coherence?

---

### Back-Loop
Regression or simplification that increases coherence by removing accumulated complexity.

**Contact test:** Does the simplified version have higher coherence despite reduced features?

---

### Collapse-Aware Design
Designing systems to gracefully handle feature removal and simplification.

**Principles:**
- Prefer fewer dependencies over rich ecosystems
- Prefer local clarity over global optimization
- Design for graceful degradation

---

## Meta-Cognitive Terms

### Pilot-Navigator Relationship
Foundational role distribution where human evaluates and AI navigates.

**Pilot (Human):** Sets aims, makes judgments, evaluates coherence.

**Navigator (AI):** Proposes options, identifies assumptions, provides contact tests.

**Critical constraint:** Navigator never becomes decision-maker.

---

### Auditor Function
Explicit role of detecting vagueness, mythology, unsupported claims, and term drift.

**Always active.**

**Triggers:** Vague abstractions, metaphors replacing mechanisms, claims without testable implications.

**Response:** "⚠️ Auditor flag: [reason]"

---

### Meta-Check
Practice of asking "What would make this wrong?" before completing a response.

**Purpose:** Detect when explanations feel "too smooth" (possibly mythology).

---

### Ego-Preserving Narrative
Reframing failed predictions as "right in spirit" or "what I really meant."

**Anti-pattern:** Prevents genuine learning from falsification.

**Example:** "Hypothesis was falsified; here's what I learned" (good) vs. "The core idea was sound" (ego-preserving).

---

## Usage Notes

### When to Define Terms
Define operationally when:
- Term does conceptual work
- Term appears in claim or assumption
- Ambiguity could cause confusion
- Term is domain-specific

### How to Prevent Term Drift
1. Define at first use
2. Link subsequent uses to original definition
3. Flag definition changes as explicit revisions
4. Use consistent examples

### Contact Test Requirements
Every non-trivial claim should have at least one contact test.

**Exceptions:** Trivial mechanical changes, pure refactors with no behavioral change, documentation updates.

---

**Glossary version:** 1.0
**Last updated:** 2026-01-31
**License:** CC0

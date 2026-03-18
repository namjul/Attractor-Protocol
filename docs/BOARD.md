# Work Organization Board
## Attractor Protocol for Living Systems

**Part of [Attractor Protocol](./attractor-protocol.md)** — Organizing work by center impact and evidence gathering.

**Related documents:**
- [Development Agents Protocol](./attractor-protocol.AGENTS.md) — Planning phase integrates with board
- [Commit Convention](./attractor-protocol.COMMITS.md) — Work items become commits
- [Contact Testing](./attractor-protocol.TESTING.md) — Validation methods for work items
- [Glossary](./attractor-protocol.GLOSSARY.md) — Operational definitions

---

## What Is This?

A **living systems alternative to Kanban** that organizes work by:
- **Center impact** (not feature completion)
- **Evidence state** (not mechanical status)
- **Interventions** (not tasks)
- **Contact tests** (not acceptance criteria)

---

## Why Not Kanban?

**Kanban organizes by status:** To Do → In Progress → Done
- Focus: completion of discrete units
- Metaphor: assembly line, throughput
- Encodes mechanical thinking: work items are independent units, progress = movement through pipeline

**Living systems boards organize by understanding:** Proposed → Field Preparation → Intervention → Validation → Integrated
- Focus: evolution of centers through evidence
- Metaphor: cultivation, unfolding
- Encodes living systems thinking: work items are interventions in coherent whole, progress = increased understanding + validated hypotheses

---

## Core Principles

### 1. Work Items Are Interventions

**Not:** "Add color picker feature"
**But:** "Strengthen drawing-flow by reducing color-selection friction"

**Every work item must specify:**
- Which center is being affected
- What kind of intervention (strengthen, create, dissolve, etc.)
- How we'll know if it worked

### 2. Columns Represent Evidence State

**Not:** Status (To Do, In Progress, Done)
**But:** Understanding + validation state

**Columns track:** What do we know? What are we testing? What has been validated?

### 3. Movement Requires Evidence

**Not:** "I finished the code, moving to Done"
**But:** "Contact test validated, moving to Integrated"

**Can't move forward without:**
- Contact test specified (to leave Proposed)
- Field dependencies met (to start Intervention)
- Evidence gathered (to claim Validated)

### 4. Failed Tests Are Learning

**Not:** "This didn't work, let's hide it"
**But:** "Contact test failed → Revision Required → Update understanding"

**Failure is valuable:** Falsified hypotheses inform next moves, revision ritual documents learning, system understanding improves.

---

## Board Structure

```
┌─────────────┬─────────────┬─────────────┬─────────────┬─────────────┐
│  Proposed   │   Field     │   Active    │  Evidence   │  Validated  │
│Interventions│ Preparation │Intervention │  Gathering  │& Monitoring │
├─────────────┼─────────────┼─────────────┼─────────────┼─────────────┤
│ Hypothesis  │ Building    │ Changing    │ Measuring   │ Confirmed   │
│ stated      │ enabling    │ system      │ against     │& watching   │
│ Contact test│ conditions  │ actively    │ contact     │ for co-     │
│ defined     │             │             │ test        │ variance    │
└─────────────┴─────────────┴─────────────┴─────────────┴─────────────┘
                                                               ↓
                                                     ┌─────────────────┐
                                                     │    Revision     │
                                                     │    Required     │
                                                     ├─────────────────┤
                                                     │ Contact test    │
                                                     │ failed          │
                                                     │ Needs rethink   │
                                                     └─────────────────┘
```

---

## Column Definitions

### Column 1: Proposed Interventions

**Purpose:** Hypotheses waiting to be validated or started.

**Entry criteria:**
- Center impact identified
- Intervention type clear
- Contact test specified
- Claim stated

**Exit criteria:**
- All field dependencies met → Move to Active Intervention
- Field not ready → Move to Field Preparation
- Deprioritized → Archive with reason

**WIP limit:** None (can propose unlimited hypotheses)

---

### Column 2: Field Preparation

**Purpose:** Building enabling conditions before intervention.

**Entry criteria:** Intervention identified but field not ready (missing dependencies, context, or prerequisites)

**Examples:** Setting up analytics before measuring feature impact, refactoring to make change possible, gathering user feedback to validate hypothesis

**Exit criteria:**
- Field ready → Move to Active Intervention
- Realize intervention not needed → Archive
- Blocked indefinitely → Flag for team discussion

**WIP limit:** 2-3 items (field work can be time-consuming)

---

### Column 3: Active Intervention

**Purpose:** Currently changing the system.

**Entry criteria:**
- Field dependencies met
- Contact test specified
- One person actively working on it

**Exit criteria:**
- Change deployed/testable → Move to Evidence Gathering
- Realize approach won't work → Move to Revision Required
- Blocked → Move back to Field Preparation

**WIP limit:** 1 per person (focus on completing before starting new)

**Center constraint:** Only one intervention per center at a time (prevents conflicting changes)

---

### Column 4: Evidence Gathering

**Purpose:** Testing hypothesis against reality.

**Entry criteria:**
- Intervention deployed/testable
- Contact test can now be run
- Measurement instrumentation in place

**Examples:** Monitoring analytics for 2 weeks, running A/B test, collecting user feedback, observing usage patterns

**Exit criteria:**
- Contact test passed → Move to Validated & Monitoring
- Contact test failed → Move to Revision Required
- Contact test was inadequate → Move to Revision Required (fix test)

**WIP limit:** Unlimited (many things can gather evidence simultaneously)

**Timeline enforcement:** Each item must have evaluation date

---

### Column 5: Validated & Monitoring

**Purpose:** Contact test passed, monitoring for co-variance.

**Entry criteria:**
- Contact test passed
- Evidence supports original claim
- Hypothesis validated

**Monitoring for:** Co-variance effects appearing later, edge cases not caught initially, usage patterns stabilizing, integration with other changes

**Exit criteria:**
- Stable after monitoring period → Archive as Complete
- Issues discovered → Move to Revision Required
- New hypothesis emerges → Create new Proposed item

**WIP limit:** Unlimited (monitoring is passive)

**Monitoring period:** Typically 1-4 weeks depending on change scope

---

### Special Column: Revision Required

**Purpose:** Contact test failed or hypothesis falsified.

**Entry criteria:**
- Contact test failed
- Evidence contradicts claim
- Assumptions proven wrong
- Contact test itself was inadequate

**Required actions:**
1. Document what failed (evidence)
2. Explain why hypothesis was wrong
3. Update understanding (what we learned)
4. Propose alternative approach OR archive

**Exit criteria:**
- New hypothesis → Move to Proposed
- Not worth pursuing → Archive with learning documented
- Quick fix identified → Move to Active Intervention

**WIP limit:** None (failures are learning opportunities, handle promptly)

**This is not a failure state—it's a learning state.**

---

## Work Item Format

### Required Fields

**Title:**
```
[intervention-type]([center]): [what's being done]
```

**Examples:**
- `strengthen(drawing-flow): reduce color-selection friction`
- `create(gesture-color): velocity-based color selection`
- `dissolve(grid-overlay): remove unused grid`
- `revision(color-picker): fix accidental-trigger issue`

---

**Description:**

```markdown
**Aim:** [What problem are we solving?]

**Claim:** [What will this enable/improve?]

**Assumptions:**
- [Load-bearing belief 1]
- [Load-bearing belief 2]

**Center Impact:**
  Strengthened: [center] - [how/why]
  Weakened: [center] - [how/why]
  Created: [center] - [what it organizes]
  Dissolved: [center] - [why removal helps]

**Contact Test:**
  Success-if: [Observable outcome]
  Failure-if: [Observable failure]
  Measurement: [How we'll check]
  Timeline: [When we'll evaluate]

**Field Dependencies:**
- [Prerequisite 1]
- [Prerequisite 2]

**Co-Variance:**
- [Other center/module that will be affected]
- [Another affected area]
```

---

## Workflow Rules

### Rule 1: Entering "Active Intervention"

**Required:**
- Center impact identified
- Contact test specified (with timeline)
- Field dependencies met
- Only one active intervention per center

If field dependencies not met, move to Field Preparation first.

---

### Rule 2: Moving to "Evidence Gathering"

**Required:**
- Change deployed or testable
- Measurement instrumentation working
- Timeline for evaluation set
- Team knows when to check results

---

### Rule 3: Declaring "Validated"

**Required:**
- Contact test actually run (not just deployed)
- Evidence gathered and reviewed
- Success criteria met based on real data
- Monitoring plan defined for co-variance

**Cannot claim validated:**
- Before timeline elapsed
- Without checking actual evidence
- Based on "seems to work"

---

### Rule 4: Handling "Revision Required"

**When contact test fails:**
1. Move to Revision Required immediately
2. Document evidence of failure
3. Run revision ritual (what changed, what no longer holds, new belief)
4. Either propose new hypothesis or archive with learning

---

### Rule 5: Center Capacity

**Limit:** Maximum 1 active intervention per center at a time

**Rationale:** Multiple simultaneous changes to same center create conflicting modifications, unclear attribution of effects, tangled co-variance.

**If two people want to change same center:** Coordinate approach (one intervention, pair work), sequence interventions, or split into different sub-centers if possible.

---

## Anti-Patterns to Detect

### Anti-Pattern 1: "Doneness" Without Evidence

**What it looks like:** Card moved to "Validated" without running contact test, "Looks good to me" without measurement

**Flag:** "Where's the evidence? When did we evaluate the contact test?"

**Fix:** Move back to Evidence Gathering, set timeline, actually measure

---

### Anti-Pattern 2: Mythology in Work Items

**What it looks like:**
```markdown
Title: enhance(user-experience): improve drawing holistically
Claim: Create more fluid, natural drawing feel
Contact Test: Users will feel it's better
```

**Red flags:** Vague center, unfalsifiable claim, no measurable contact test

**Fix:** Require operational definitions and measurable outcomes

---

### Anti-Pattern 3: Zombie Cards

**What it looks like:** Card stuck in Active Intervention for >2 weeks, no progress, no evidence

**Causes:** Field not actually ready, intervention too large, blocked but not flagged

**Fix:** Weekly review of Active Intervention column, move cards appropriately

---

## Metrics (Not Traditional Kanban Metrics)

### Validation Rate
```
% of interventions where contact test passed
```
**Target:** 60-80% (not 100% - means we're learning)

**If too high (>90%):** Tests may be too easy
**If too low (<50%):** Hypotheses poorly formed

---

### Revision Frequency
```
How often items move to Revision Required
```
**Target:** 20-40% of interventions require revision

**This is GOOD:** Means we're testing real hypotheses, learning from failures.

---

### Center Stability
```
How often validated changes need rework
```
**Target:** <10% of validated changes revert or need fixes

---

## Visual Design Considerations

**Color coding:**
- 🟦 Blue: Hypothesis (Proposed, Field Prep)
- 🟨 Yellow: Active Intervention
- 🟧 Orange: Evidence Gathering (waiting for timeline)
- 🟩 Green: Validated (contact test passed)
- 🟥 Red: Revision Required (contact test failed)

**Timeline visibility:**
Show evaluation dates on Evidence Gathering cards:
```
┌─────────────────────────┐
│ strengthen(drawing-     │
│ flow): color selection  │
│                         │
│ 📊 Evidence Gathering   │
│ ⏱️  Eval: Feb 15, 2026  │
│ (5 days remaining)      │
└─────────────────────────┘
```

---

## Tool Integration

### GitHub Projects Template

```yaml
Columns:
  - name: "Proposed Interventions"
  - name: "Field Preparation"
  - name: "Active Intervention"
  - name: "Evidence Gathering"
  - name: "Validated & Monitoring"
  - name: "Revision Required"

Card Template:
  Title: "[type]([center]): [what]"
  Body: |
    **Aim:** 
    **Claim:** 
    **Assumptions:**
    **Center Impact:**
    **Contact Test:**
    **Field Dependencies:**
    **Co-Variance:**
```

**Adapt this template for other tools** (Jira, Linear, etc.) by mapping columns and adding custom fields for Center Impact and Contact Test.

---

## Migration from Kanban

**This is a worldview shift** - treat as learning process, not rollout.

### Phase 1: Awareness (1-2 weeks)
- Read AGENTS.md sections on centers
- Discuss: "What are the centers in our system?"
- Map existing work to centers
- **Deliverable:** Shared center map

### Phase 2: Hybrid Board (1 month)
- Keep existing Kanban columns
- Add minimal tracking: Which center? What's our contact test?
- Use standard Kanban for mechanical work (dependencies, chores)
- Use living systems format for interventions (features, refactors)
- **Goal:** Practice identifying centers and writing contact tests

### Phase 3: Column Migration (1 month)
- Replace "To Do" → "Proposed Interventions"
- Replace "In Progress" → "Active Intervention" + "Field Preparation"
- Replace "Done" → "Evidence Gathering" + "Validated & Monitoring"
- Add "Revision Required" column
- **Key change:** Items can't move to "Validated" without evidence

### Phase 4: Full Adoption
- All interventions use living systems format
- Team fluent in: identifying centers, writing contact tests, running revision ritual, mapping co-variance

### Minimal Compliance (If Full Adoption Not Possible)

**Minimum:**
1. Add "Center Impact" field to cards
2. Add "Contact Test" field to cards
3. Create "Revision Required" column

This preserves center-awareness without full process change.

**However:** Minimal compliance loses most value. The power comes from organizing by evidence state, actually running contact tests, revision when falsified, tracking co-variance.

---

## When NOT to Use This Board

**Skip this board for:**

1. **Pure mechanical work** - Dependency updates, infrastructure maintenance, chores with no center impact
2. **Exploratory prototyping** - When you don't know what centers exist yet, use exploration mode
3. **Trivial changes** - Typo fixes, one-line changes, no hypothesis to test
4. **Very small teams (<3 people)** - Overhead may exceed value, direct communication might suffice

**General rule:** If you're making claims about improvement, use this board structure. If not, simpler tools may suffice.

---

## FAQ

### "This seems like a lot of overhead?"

**Contact test for the board itself:**

**Success-if:** Catches mythology before it becomes work, prevents building things that don't improve system, team learns faster from failures

**Failure-if:** Pure bureaucracy with no learning, slows team without improving quality, items skip evidence gathering

**If overhead without benefit: Stop using it.**

---

### "Can we use traditional Kanban alongside this?"

**Yes, with separation:**

- **Living Systems Board:** For interventions (hypotheses about improvement)
- **Kanban Board:** For mechanical work (dependencies, chores, known tasks)

Don't mix—trying to use one board for both creates confusion.

---

### "What if we can't measure contact tests?"

See [TESTING.md](./attractor-protocol.TESTING.md) for evidence patterns.

**Key insight:** Contact tests don't require sophisticated analytics.

**Valid evidence:** Self-observation, team feedback, binary outcomes, proxy signals.

Match evidence pattern to available resources.

---

### "How do we handle dependencies between work items?"

**Two types:**

**1. Field dependencies (same item):**
- Listed in "Field Dependencies" section
- Blocks moving to Active Intervention
- Resolved via Field Preparation column

**2. Co-variance (different items):**
- Listed in "Co-Variance" section
- Doesn't block (but indicates relationship)
- Tracked to understand propagation

---

### "What about urgent bugs?"

**Bugs are interventions too:**

**Title:** `repair(undo-stack): fix color persistence bug`

**Move through board:**
1. Proposed: Identify bug, write contact test ("bug not reproducible")
2. Active: Fix bug
3. Evidence: Verify fix works, test for 2-3 days
4. Validated: Bug confirmed fixed

**Urgency doesn't bypass evidence gathering** - but timeline can be shorter (days not weeks).

---

## Summary

**This board structure prevents:**
- Building features without knowing if they work
- Claiming completion without evidence
- Hiding failed experiments
- Accumulating dead structure
- Mythology about "improvement"

**This board structure enables:**
- Center-aware development
- Evidence-based decision making
- Learning from failures
- Tracking system evolution
- Coherence over feature count

**Core principle:** Work organized by center impact and evidence state, not mechanical status.

**The practice:** Before claiming something improved the system, gather evidence.

---

**Board version:** 1.0  
**Last updated:** 2026-01-31  
**Part of Attractor Protocol**  
**License:** CC0

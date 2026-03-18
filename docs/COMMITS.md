# Commit Convention
## Living Systems Alternative to Conventional Commits

**Part of [Attractor Protocol](./attractor-protocol.md)**

**Related documents:**
- [Development Agents Protocol](./attractor-protocol.AGENTS.md) — Planning phase produces commit content
- [Work Organization Board](./attractor-protocol.BOARD.md) — Work items become commits
- [Glossary](./attractor-protocol.GLOSSARY.md) — Operational definitions

---

## What Is This?

A commit format for recording changes in living systems that organizes work by:
- **Center impact** (not feature categories)
- **Contact tests** (how will we know if it worked?)
- **Evidence** (what motivated this change?)

**Conceptual replacement for Conventional Commits:**
- Different types (`strengthen`, `create`, `dissolve` vs. `feat`, `fix`)
- Different philosophy (interventions in living systems vs. mechanical changes)
- Different requirements (`Center-Impact`, `Contact` sections vs. optional body)

**Technical compatibility:**
- Preserves base format structure for tooling
- Maintains footer conventions (`BREAKING CHANGE:`, `Closes:`, `Refs:`)

---

## Format

```
<type>(<scope>): <subject>

<body>

<center-impact>

<contact>

<footer>
```

---

## Components

### 1. Type (Required)

**Standard types:**
- `strengthen`: Enhances an existing center
- `create`: Introduces a new center
- `dissolve`: Removes a center (intentionally)
- `repair`: Fixes broken feedback loops or dead structure
- `refactor`: Restructures without changing observable behavior
- `test`: Adds or modifies contact tests
- `docs`: Documentation changes
- `chore`: Maintenance work

**Living systems types:**
- `unfolding`: Incremental evolution of structure
- `revision`: Updates based on new evidence/contact
- `simplify`: Reduces complexity (collapse-aware)
- `field`: Modifies relational context
- `feedback`: Improves or adds feedback mechanisms

**Breaking changes:** Add `!` after type/scope: `strengthen(canvas)!:`

### 2. Scope (Optional)

The center or field being affected.

**Examples:** `(drawing-cursor)`, `(undo-stack)`, `(color-picker)`, `(gesture-field)`, `(persistence)`

### 3. Subject (Required)

Short imperative summary (≤50 chars).

**Good:** `strengthen: reduce stroke latency to <16ms`

**Avoid mythology:** ❌ `strengthen: make drawing feel more alive`

### 4. Body (Optional but Recommended)

**Structure using EAI elements:**

```
Aim: [What problem is this solving?]

Claim: [What does this change enable?]

Assumptions: [What beliefs are load-bearing?]

Evidence: [What observation/data motivated this?]
```

### 5. Center Impact (Required for non-trivial changes)

Specify which centers are strengthened, weakened, or created.

**Format:**
```
Center-Impact:
  Strengthened: [center-name] - [how/why]
  Weakened: [center-name] - [how/why]
  Created: [center-name] - [what it organizes]
  Dissolved: [center-name] - [why removal increases coherence]
```

**For trivial changes:** `Center-Impact: None (mechanical change)`

### 6. Contact (Required for substantial changes)

How will we know if this worked? What would falsify it?

**Format:**
```
Contact:
  Success-if: [measurable outcome]
  Failure-if: [observable indication of failure]
  Measurement: [how we'll measure]
  Timeline: [when we'll evaluate]
```

**For refactors/chores:**
```
Contact:
  Success-if: Tests pass, no behavior change observed
  Failure-if: User reports of broken functionality
```

### 7. Footer (Standard Conventional Commits)

```
Co-Variance: [list affected modules/centers]
BREAKING CHANGE: [description]
Closes: #123
Refs: #456
```

**Co-Variance is GSNV-specific:**
Lists modules/centers that changed as a result of this commit, tracking propagation effects.

```
Co-Variance:
  - gesture-handlers (updated for new color logic)
  - persistence-layer (stores gesture-color state)
  - undo-stack (tracks color as part of gesture)
```

---

## Complete Examples

### Example 1: Feature Addition (Strengthening)

```
strengthen(drawing-flow): add gesture-based color selection

Aim: Reduce mode-switching friction in color selection

Claim: Users can select colors without leaving drawing mode,
increasing color usage from 11% to >40% of strokes

Assumptions:
- Color is meaningful but current picker creates friction
- Users can learn velocity-based selection quickly
- Gestural selection won't interfere with drawing precision

Evidence:
- Session recordings: 89% never open current picker
- User interviews: 5/7 mentioned wanting "easier color"
- Heatmaps: cursor never approaches picker location

Center-Impact:
  Strengthened: drawing-flow - eliminates mode-switching
  Weakened: color-picker-UI - reduced to 8 swatches
  Created: gesture-color - velocity-based selection

Contact:
  Success-if: Color usage >30%, <5% accidental triggers
  Failure-if: Users confused, revert to black, or abandon feature
  Measurement: Stroke color analytics + error rate tracking
  Timeline: Evaluate after 100 sessions (est. 2 weeks)

Co-Variance:
  - gesture-handlers (velocity detection added)
  - persistence (stores gesture-color mappings)
  - undo-stack (tracks color in gesture history)

Closes: #234
```

### Example 2: Revision Based on Evidence

```
revision(color-picker): revert velocity-based selection

Aim: Restore drawing precision after failed experiment

Claim: Velocity-based color selection interferes with
drawing flow despite solving mode-switching problem

Assumptions (original):
- Users could learn velocity-based selection quickly ❌
- Gestural selection wouldn't interfere with precision ❌

Evidence (revision):
- Accidental color changes: 23% of strokes (target was <5%)
- User feedback: 12/15 reported "frustrating" or "unpredictable"
- Session time: avg. session duration dropped 18%
- Abandonment: 34% of new users left after <3 minutes

Previous Claim No Longer Holds:
The hypothesis that gestural color selection could be both
accessible and non-interfering was falsified. Users cannot
simultaneously think about drawing intent and color-selection
gestures.

Updated Understanding:
Color selection and drawing are competing centers at this
interaction scale. They need separation, not integration.
The problem is not "mode-switching" but "discoverability."

Center-Impact:
  Dissolved: gesture-color (failed as center)
  Strengthened: drawing-center (restored precision)
  Weakened: color-accessibility (back to original problem)

Contact:
  Success-if: Drawing precision restored, session time recovers
  Failure-if: Users still complain about color access
  Measurement: Error rate, session duration, user feedback
  Timeline: Immediate (already validated by failure data)

Next Step:
Investigate discoverability solutions that don't require
in-gesture interaction (e.g., always-visible palette,
keyboard shortcuts, pressure-based selection on separate input)

Co-Variance:
  - gesture-handlers (velocity detection removed)
  - persistence (gesture-color state removed)
  - undo-stack (simplified to exclude color metadata)

BREAKING CHANGE: Gesture-based color selection removed.
Users must return to manual picker interaction.

Closes: #234 (original feature)
Refs: #678 (user feedback issue)
```

---

## Guidelines

### When to Use Each Type

**strengthen:** Enhancing existing, validated centers

**create:** New centers with hypothesized organizing power. Always requires strong contact test.

**dissolve:** Removing failed hypotheses, eliminating inert structure, collapse-aware simplification

**revision:** Changes based on new evidence, falsification of previous assumptions, updates to system understanding

**unfolding:** Incremental evolution without breaking changes, gradual emergence of form, small steps that enable next steps

**simplify:** Reducing complexity, removing unused abstractions, back-loop moves toward coherence

---

## Anti-Patterns in Commit Messages

❌ **Mythology:**
```
strengthen(canvas): enhance the holistic drawing experience
through more fluid gestural dynamics
```

✅ **Operational:**
```
strengthen(canvas): reduce stroke latency from 28ms to 12ms

Contact:
  Success-if: Users report "smoother" drawing
  Measurement: Frame time analytics
```

---

❌ **Vague center claims:**
```
create(workflow): add new drawing workflow

Center-Impact:
  Created: workflow - improves user experience
```

✅ **Specific center definition:**
```
create(session-memory): persist last 10 strokes across sessions

Center-Impact:
  Created: session-memory - allows continuation after close
  Strengthened: drawing-continuity - reduces restart friction

Contact:
  Success-if: >50% of users resume previous session
  Measurement: Session continuation analytics
```

---

❌ **Missing contact test:**
```
refactor(rendering): improve performance
```

✅ **With contact test:**
```
refactor(rendering): batch stroke updates to reduce redraws

Contact:
  Success-if: FPS increases by >20%, no visual artifacts
  Failure-if: Flickering, dropped strokes, or frame drops
  Measurement: Chrome DevTools performance profiling
```

---

## Integration with Git Workflow

### Commit Message Template

Create `.gitmessage`:

```
# Type(scope): subject (≤50 chars)
#
# Aim: [What problem is this solving?]
#
# Claim: [What does this change enable?]
#
# Assumptions: [What beliefs are load-bearing?]
#
# Evidence: [What observation/data motivated this?]
#
# Center-Impact:
#   Strengthened: [center] - [how/why]
#   Weakened: [center] - [how/why]
#   Created: [center] - [what it organizes]
#   Dissolved: [center] - [why removal increases coherence]
#
# Contact:
#   Success-if: [measurable outcome]
#   Failure-if: [observable failure]
#   Measurement: [how we'll measure]
#   Timeline: [when we'll evaluate]
#
# Co-Variance:
#   - [affected module/center]
#
# Closes: #
# Refs: #
```

Configure git to use it:
```bash
git config commit.template .gitmessage
```

---

## Rationale

This format replaces Conventional Commits' mechanical worldview with living systems thinking:

1. **Epistemic discipline** (GSNV)
   - Contact tests prevent mythology
   - Evidence requirements ground claims
   - Revision ritual tracks learning

2. **Living systems awareness** (Alexander)
   - Center impact makes relationships explicit
   - Co-variance tracks propagation
   - Types distinguish strengthening from creating

3. **Audit trail for system evolution**
   - Track which hypotheses succeeded/failed
   - Document assumptions at commit time
   - Enable future revision based on evidence

4. **Prevents common failure modes**
   - Mythology in commit messages
   - Untracked center interactions
   - Claims without falsifiability
   - Complexity accumulation without measurement

**Why not just extend Conventional Commits?**

Conventional Commits encodes a mechanical view: features are added, bugs are fixed, code is refactored. This language treats systems as assemblies of parts.

Living Systems Commits encodes an organismic view: centers are strengthened, structure unfolds, hypotheses are revised. This language treats systems as coherent wholes.

The two worldviews are incommensurable. Technical compatibility is preserved only to ease tooling migration, not to support hybrid usage.

---

## Migration from Conventional Commits

**This is a worldview shift, not incremental adoption.**

### Migration Path

**Phase 1: Awareness (1-2 weeks)**
- Read AGENTS.md and glossary
- Discuss: "What are the centers in our system?"
- Identify one subsystem to practice on

**Phase 2: Dual Format (1 month)**
- Conventional Commits for mechanical changes (dependencies, typos)
- Living Systems Commits for interventions (features, refactoring, simplification)
- Gradually increase Living Systems usage

**Phase 3: Full Adoption**
- All non-trivial commits use Living Systems format
- Mechanical changes use `chore` type with minimal Center-Impact
- Team fluent in identifying centers and contact tests

### Minimal Compliance

If full adoption not possible:

```
<conventional-type>(<scope>): <subject>

<body>

Center-Impact: [brief statement or "None - mechanical change"]
```

This preserves center-awareness without requiring full EAI structure.

**However:** Minimal compliance loses most value. The protocol's power comes from epistemic discipline, not just tracking center impact.

---

## Tooling Suggestions

### Commit Message Linter

Extend [commitlint](https://commitlint.js.org/) with GSNV rules:

```javascript
module.exports = {
  extends: ['@commitlint/config-conventional'],
  rules: {
    'type-enum': [2, 'always', [
      'strengthen', 'create', 'dissolve', 'repair',
      'refactor', 'test', 'docs', 'chore',
      'unfolding', 'revision', 'simplify', 'field', 'feedback'
    ]],
    'center-impact-required': [2, 'always'],
    'contact-required-for-features': [1, 'always'],
  },
  plugins: [
    {
      rules: {
        'center-impact-required': (parsed) => {
          const impactfulTypes = ['strengthen', 'create', 'dissolve',
                                   'revision', 'unfolding', 'simplify'];
          if (impactfulTypes.includes(parsed.type)) {
            return [
              parsed.body.includes('Center-Impact:'),
              'Non-trivial commits must include Center-Impact section'
            ];
          }
          return [true];
        }
      }
    }
  ]
};
```

### Changelog Generation

Generate changelogs grouped by center impact:

```markdown
# Changelog

## Centers Strengthened
- **drawing-flow**: Reduced stroke latency (commit abc123)
- **undo-stack**: Added color persistence (commit def456)

## Centers Created
- **gesture-color**: Velocity-based selection (commit ghi789)

## Centers Dissolved
- **grid-overlay**: Removed unused feature (commit jkl012)

## Revisions
- **color-picker**: Reverted velocity selection after evidence
  of interference (commit mno345)
```

---

**Protocol status:** ACTIVE
**Format version:** 1.0
**Relationship to Conventional Commits:** Conceptual replacement, technical extension
**License:** CC0

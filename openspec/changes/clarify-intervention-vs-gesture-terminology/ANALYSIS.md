# Intervention vs Gesture Terminology Analysis

## Current State

Found 30 occurrences of "intervention" across templates, schema, and docs.

## Categorization

### Category 1: References to current gesture (should likely change)

**Templates referencing "this intervention":**
- `templates/gesture.md:22` — "What do you believe this intervention will produce?"
- `templates/gesture.md:40` — "the whole intervention falls apart"
- `templates/specs.md:13` — "behavior that will work differently after this intervention"
- `templates/specs.md:30` — "understand the boundaries of this intervention"
- `templates/design.md:57` — "If this intervention introduces delay..."
- `templates/evidence.md:5,48` — "Did the intervention pass or fail?"
- `templates/explore.md:20,25` — "Not a full intervention", "worth a full intervention"

**Rationale for change:** These are within templates used to document a gesture. Saying "this intervention" while filling out gesture.md creates terminology mismatch.

**Proposed change:** Replace with "gesture"

---

### Category 2: Artifact name errors (definitely change)

- `templates/tasks.md:30` — "load-bearing assumption from intervention.md or design.md"
- `templates/evidence.md:53` — "in the next intervention.md"

**Rationale:** The artifact was renamed from intervention.md to gesture.md. These are broken references.

**Proposed change:** → gesture.md

---

### Category 3: Schema/README description (should likely change)

- `schema.yaml:5` — "Living systems intervention workflow"
- `README.md:3` — "A living systems intervention workflow"

**Rationale:** These describe the protocol. If the protocol uses "gesture" as its primary term, the description should match.

**Proposed change:** "Living systems gesture workflow" or "Living systems workflow for gestures"

---

### Category 4: Technical glossary definitions (keep)

**docs/GLOSSARY.md:**
- Line 28 — "A quantifiable signal tracking intervention success"
- Line 197 — "Specification of how an intervention affects existing or creates new centers"
- Line 366-369 — Full definition entry for "Intervention"

```markdown
### Intervention
Deliberate change to system structure, not just content.
**Example:** Changing how undo tracks state (intervention) vs. fixing UI text typo (not intervention).
```

**Rationale:** These are glossary definitions. "Intervention" may be a valid technical term distinct from "gesture."

**Question:** Should the glossary explain the relationship between "intervention" and "gesture"?

---

### Category 5: Workflow rules and constraints (ambiguous)

**docs/BOARD.md:**
- Line 47 — "What kind of intervention (strengthen, create, dissolve, etc.)"
- Line 124 — "Building enabling conditions before intervention"
- Line 155 — "Only one intervention per center at a time"
- Line 236 — `[intervention-type]([center]): [description]` (commit format)
- Line 289 — "Only one active intervention per center"
- Line 332 — "Maximum 1 active intervention per center at a time"
- Line 336 — "Coordinate approach (one intervention, pair work)"
- Line 371 — "intervention too large"

**docs/AGENTS.md:**
- Line 13 — "disciplined intervention in code, structure, and design"
- Line 164 — "It's a structural hypothesis, not a validated intervention"
- Line 255 — "What kind of intervention (strengthen, create, dissolve, reorganize)"
- Line 512 — "Which centers? What intervention?"

**Rationale:** These use "intervention" to describe workflow rules and planning patterns. Could mean:
- The general category (keep "intervention")
- The protocol artifact (change to "gesture")

**Question:** Is there value in keeping "intervention" as the general category term, with "gesture" as the protocol-specific instance?

---

## Decision Options

### Option A: Full Replacement
Replace all uses of "intervention" with "gesture" except the GLOSSARY definition, which explains that "intervention" is the general category that this protocol calls "gesture."

**Pros:**
- Simple, consistent
- Less cognitive load
- Clear migration path

**Cons:**
- Loses semantic distinction between category and instance
- "Gesture" in general workflow rules might feel overly specific

---

### Option B: Semantic Distinction
Keep "intervention" as general category, use "gesture" for protocol-specific references.

**Distinction:**
- **Intervention** = Any deliberate structural change to a system (general term)
- **Gesture** = The protocol's specific instantiation of an intervention (artifact + workflow)

**This would mean:**
- Templates: "gesture" (referring to the artifact being created)
- Workflow rules: "intervention" (referring to the general category)
- GLOSSARY: Both defined, with clear relationship

**Pros:**
- Preserves technical vocabulary precision
- Allows discussing interventions in systems generally
- Clear category/instance hierarchy

**Cons:**
- Two overlapping terms to maintain
- Requires documenting the distinction
- More complex for new users

---

### Option C: Hybrid
- Templates and artifact references: "gesture"
- Workflow rules: Could go either way based on what feels clearer
- GLOSSARY: Keep "intervention" definition, add note about "gesture"

---

## Questions for Decision

1. **Does "intervention" serve a distinct purpose as a general category term?** Or is "gesture" sufficient for all uses?

2. **For workflow rules like "one intervention per center," does "intervention" or "gesture" feel more natural?**

3. **Should the GLOSSARY maintain both terms with a documented relationship? Or simplify to just "gesture"?**

4. **For commit message format, which reads better?**
   - `strengthen(drawing-flow): add gesture smoothing`
   - `intervention(drawing-flow): add gesture smoothing`

5. **Is the added precision of maintaining "intervention" as a category worth the cognitive overhead of having two related terms?**

---

## Recommendation

Waiting for user decision on whether to pursue Option A (full replacement) or Option B (semantic distinction).

Once decided, can map exact line-by-line changes needed.

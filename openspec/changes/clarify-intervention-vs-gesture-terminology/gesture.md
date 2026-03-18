# Gesture: clarify-intervention-vs-gesture-terminology

## Gesture type

simplify

## What are we gesturing toward?

The terminology in templates, schema description, and documentation. Specifically, the inconsistent use of "intervention" after shifting the primary term to "gesture."

## Claim

Systematically reviewing where "intervention" remains and clarifying whether it should be replaced with "gesture" or kept as a distinct technical term will reduce cognitive friction and make the protocol's vocabulary clearer.

## What made us do this?

While working on the optional-artifacts gesture, noticed that "intervention" still appears in 30+ places across templates, schema, and docs. Some uses feel like artifacts from before the terminology shift. Others might be intentional—using "intervention" as a general category with "gesture" as the protocol-specific instantiation.

**Current unclear cases:**
- Templates say "this intervention" when referring to the current gesture
- tasks.md references "intervention.md" (artifact no longer exists—should be gesture.md)
- evidence.md says "Did the intervention pass or fail the contact test?"
- GLOSSARY.md defines "Intervention" as a separate term
- BOARD.md uses "intervention per center" in workflow rules
- Schema description says "Living systems intervention workflow"

Not clear if this is:
- Incomplete migration from old terminology
- Intentional distinction (intervention = category, gesture = instance)
- Mixed—some should change, some shouldn't

## What are our load-bearing assumptions?

1. **The distinction between intervention and gesture, if it exists, is not currently clear.** If "intervention" is meant to be the general category and "gesture" the protocol-specific artifact, that distinction is nowhere documented and readers will be confused.

2. **Template consistency matters more than vocabulary precision.** When templates reference "this intervention" in the context of filling out gesture.md, the mismatch creates friction. Better to be consistently "gesture" than technically precise about categories.

3. **Some uses are clearly wrong (e.g., intervention.md).** References to an artifact that no longer exists should be updated regardless of broader terminology decisions.

## Spec files this gesture touches

None—this is a terminology/documentation gesture with no system behavior changes.

## Co-variance: what else might this touch?

- User mental model of what "gesture" means vs what "intervention" means
- Whether GLOSSARY.md needs both terms defined or just one
- Commit message formats (currently suggest `[intervention-type]([center])`)
- AGENTS.md planning patterns that reference "intervention"
- Future contributors' understanding of the vocabulary system

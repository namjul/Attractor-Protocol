# Gesture: make-implementation-artifacts-optional

## Gesture type

simplify

## What are we gesturing toward?

The schema artifact sequence. Specifically, the constraint that specs/, design.md, and tasks.md must exist for every change, even when the gesture produces no implementation.

## Claim

Making specs/, design.md, and tasks.md optional will allow purely conceptual gestures (vocabulary decisions, structural document changes, methodology adjustments) to flow through the protocol naturally without forcing empty implementation artifacts.

## What made us do this?

Noticed that not all gestures produce code. Some gestures ARE the decision itself:
- "Rename 'intervention' to 'gesture' throughout"
- "Make evidence tier proximal/medial/distal instead of hard/medium/soft"
- "Change schema artifact ordering"

These have no implementation, no delta specs, no tasks. Their "implementation" happens in the proposal phase. Forcing empty specs/design/tasks artifacts creates dead structure.

## What are our load-bearing assumptions?

1. **OpenSpec's `optional: true` works on non-first artifacts.** The schema format supports marking any artifact optional, not just explore.md.

2. **Soft dependencies are sufficient.** When evidence.md depends on tasks.md but tasks is optional and skipped, OpenSpec will warn but not block. This is the right behavior - a warning that you're skipping recommended context.

3. **The workflow bifurcation is natural.** Two paths emerging from contact-test (implementation vs. conceptual) is a clarification, not a complication. Users will intuitively know which path their gesture needs.

## Spec files this gesture touches

None. This gesture is itself an example of a conceptual gesture - it changes the schema structure but has no delta specs describing system behavior changes.

## Co-variance: what else might this touch?

- The README.md documentation of the artifact sequence
- User expectations about what constitutes a "complete" change
- How `openspec instructions apply` behaves (currently hardcoded to require tasks - will warn/fail for conceptual gestures)
- Archive behavior (might need `--skip-specs` flag for conceptual gestures)

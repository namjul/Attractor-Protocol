# Contact Test: make-implementation-artifacts-optional

## Evidence tier

proximal — will use the schema directly to create a conceptual gesture and observe whether the workflow feels natural.

## What would success look like?

After making the artifacts optional:
1. Create a conceptual gesture (e.g., vocabulary change, documentation restructure)
2. Skip specs/design/tasks naturally without friction
3. Jump directly to evidence.md when appropriate
4. The warnings OpenSpec gives feel informative, not blocking
5. The schema change itself serves as proof-of-concept - this very gesture completes without needing specs/design/tasks

## What would falsify this claim?

1. OpenSpec's validation fails or blocks when artifacts are marked optional
2. Skipping specs/design/tasks creates confusion about change completeness
3. The bifurcated workflow (implementation vs. conceptual) feels forced or adds cognitive overhead
4. Users try to create specs/design/tasks anyway "just to be complete" even when they're empty
5. The `requires` chain breaks in unexpected ways (e.g., can't create evidence without tasks existing)

## How will we check?

1. Make the schema changes (mark specs/design/tasks as optional)
2. Validate the schema with `openspec schema validate`
3. Complete this very change as a conceptual gesture - skip directly to evidence.md
4. Observe whether the flow feels natural or forced
5. Check if OpenSpec's warnings/errors make sense

## When will we check?

Immediately after making the schema change. This gesture completes when evidence.md is filled in, which will happen within the same session as the schema modification.

If successful: evidence.md will exist without specs/design/tasks, and the change will feel complete.
If false: will encounter blocking errors or the workflow will feel incomplete without those artifacts.

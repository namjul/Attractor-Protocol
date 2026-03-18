# Contact Test: clarify-intervention-vs-gesture-terminology

## Evidence tier

proximal — will review each occurrence of "intervention" in the codebase and evaluate whether the terminology feels clear or confusing in context.

## What would success look like?

After clarification:
1. Template files consistently use "gesture" when referring to the current change being documented
2. Artifact name references (intervention.md) are corrected to gesture.md
3. Either:
   - "Intervention" is removed from all non-glossary documentation, OR
   - "Intervention" remains but its relationship to "gesture" is explicitly documented
4. Reading through templates and docs, the vocabulary feels consistent and intentional rather than mixed

## What would falsify this claim?

1. After review, no clear pattern emerges—some uses should stay "intervention" but it's arbitrary which ones
2. The distinction between "intervention" and "gesture" cannot be articulated clearly
3. Trying to enforce a distinction creates more cognitive load than just using one term
4. Template consistency doesn't actually matter—users don't notice or care about the terminology mismatch
5. Changing "intervention" breaks something conceptually that wasn't obvious

## How will we check?

1. Review the 30+ occurrences of "intervention" found by grep
2. Categorize them:
   - References to the current gesture (should likely change)
   - Artifact name errors (definitely change)
   - General category uses (might keep)
   - Technical glossary definitions (might keep)
   - Ambiguous cases (needs decision)
3. For each category, test whether "gesture" or "intervention" feels clearer
4. Check if maintaining both terms requires documentation that doesn't yet exist
5. Make a decision: full replacement, semantic distinction, or hybrid

## When will we check?

Immediately during this session. The evidence gathering is the categorization exercise—once we've mapped where "intervention" appears and why, we'll know whether the distinction is valuable or vestigial.

Success = clear decision about each occurrence, documented in evidence.md
Failure = still unclear which term to use where, or documentation required is too heavy for the value gained

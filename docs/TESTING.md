# Contact Testing
## Attractor Protocol Testing Practices

**Part of [Attractor Protocol](./attractor-protocol.md)** — Preventing mythology through reality contact.

**Related documents:**
- [Development Agents Protocol](./attractor-protocol.AGENTS.md) — Uses contact tests in planning
- [Commit Convention](./attractor-protocol.COMMITS.md) — Requires contact tests in commits
- [Glossary](./attractor-protocol.GLOSSARY.md) — Operational definitions

---

## What Are Contact Tests?

**Contact tests** are reality-contact mechanisms that specify how to verify or falsify a claim.

**Core principle:** The test doesn't need to be sophisticated—it needs to be **falsifiable**.

**A contact test must answer:** "What would make this claim wrong?"

If you cannot specify what would falsify your claim, you're about to ship mythology.

---

## The Falsifiability Principle

### Valid Contact Test (Simple but Falsifiable)

```
Claim: This code is understandable
Success-if: I can modify it after 1 week without re-reading the whole thing
Failure-if: I need to trace through the logic to remember what it does
Measurement: Wait 1 week, attempt a change, honest assessment
```

**Why this works:**
- Specifies what would prove it wrong
- Commits to honest observation
- Actually could fail
- No metrics required

---

### Invalid "Test" (Sophisticated but Unfalsifiable)

```
Claim: This improves user experience holistically
Success-if: Engagement metrics trend positively
Failure-if: [not specified]
Measurement: Analytics dashboard
```

**Why this fails:**
- "Trend positively" is vague (how much? over what time?)
- No failure condition specified
- "Holistically" has no operational meaning

---

### The Real Distinction

**Not:** Quantitative = good, Qualitative = bad

**Actually:** Falsifiable = valid, Unfalsifiable = mythology

**Key insight:** You can have sophisticated metrics that measure nothing meaningful, and simple observations that catch real problems.

---

## What Makes a Contact Test Valid

### Required Elements

**1. Explicit Claim**
Not: "This improves things"
But: "This reduces steps from 5 to 3"

**2. Success Condition**
Observable outcome that would confirm claim

**3. Failure Condition** ← Critical
Observable outcome that would contradict claim

**4. Measurement Method**
How you'll check (doesn't need to be sophisticated)

**5. Honesty Commitment**
Will actually evaluate, not rationalize

---

### The Failure Condition Test

**Ask:** "What would I observe if this claim is wrong?"

**If you can't answer:**
- Claim is too vague
- Claim is unfalsifiable
- You're about to ship mythology

**Examples:**

| Claim | What would show it's wrong? |
|-------|----------------------------|
| "Code is readable" | "Reviewer asks what it does" |
| "Feature is useful" | "Nobody uses it" |
| "This is faster" | "Takes same time or longer" |
| "Bug is fixed" | "Issue still reproducible" |

**If you can answer → you have a contact test.**

---

## Contact Test Patterns: 12 Self-Evident Examples

**These examples require no infrastructure—just honest observation.**

Each shows the falsifiability principle: *What would make this wrong?*

---

### Pattern A: Self-Experience (No Infrastructure)

**What it is:** Test by using it yourself, honest self-assessment.

**When to use:** Solo dev, prototype, or you are a primary user.

---

**Example 1: Code Comprehension Test**
```
Claim: Code is understandable
Success-if: I can modify it 1 week later without re-reading implementation
Failure-if: Need to trace through logic to remember what it does
Measurement: Wait 1 week, attempt modification, be honest
Timeline: 1 week
```

---

**Example 2: Function Naming Test**
```
Claim: Function name is clear
Success-if: Function does exactly what name suggests, no surprises
Failure-if: Need to read implementation to know what it does
Measurement: Cover name, predict behavior, verify
Timeline: Immediate
```

---

**Example 3: Performance Feel Test**
```
Claim: Faster than before
Success-if: Noticeably snappier in actual use
Failure-if: Feels same speed or slower
Measurement: Honest subjective before/after comparison
Timeline: Immediate
```

---

**Example 4: Actual Usage Test**
```
Claim: Tool is valuable to me
Success-if: I use it in actual work (not just demos)
Failure-if: I avoid using it myself
Measurement: Check own behavior honestly over 1 week
Timeline: 1 week
```

---

### Pattern B: Binary Outcomes (Clear Yes/No)

**What it is:** Success and failure are unambiguous states.

**When to use:** Success and failure are objectively distinguishable.

---

**Example 5: Feature Existence Test**
```
Claim: Feature is accessible
Success-if: Feature exists and is callable
Failure-if: Feature not accessible or throws error
Measurement: Attempt to invoke, check result
Timeline: Immediate
```

---

**Example 6: Bug Fix Validation**
```
Claim: Bug is fixed
Success-if: Issue not reproducible
Failure-if: Issue still occurs
Measurement: Attempt to reproduce bug
Timeline: Immediate
```

---

### Pattern C: Comparative (Before vs After)

**What it is:** Compare new version to old, measure delta.

**When to use:** Improvement matters, not absolute values.

---

**Example 7: Code Simplicity Test**
```
Claim: Simpler implementation
Success-if: Fewer lines of code than previous version
Failure-if: More lines or same complexity
Measurement: Line count comparison (wc -l)
Timeline: Immediate
```

---

**Example 8: Workflow Efficiency Test**
```
Claim: Easier workflow
Success-if: Fewer steps required than before (counted)
Failure-if: Same or more steps
Measurement: Count user actions for same task
Timeline: Immediate
```

---

### Pattern D: Counting & Thresholds (Simple Observation)

**What it is:** Count occurrences, check against threshold.

**When to use:** Can count events and have meaningful threshold.

---

**Example 9: Code Review Clarity Test**
```
Claim: Code is readable
Success-if: Zero "what does this do?" comments in code review
Failure-if: Reviewer asks for clarification
Measurement: Count questions in review feedback
Timeline: Next code review
```

---

**Example 10: Crash Frequency Test**
```
Claim: Stable implementation
Success-if: Zero crashes in 1 week of actual use
Failure-if: Any crashes or data corruption
Measurement: Error logs, user reports
Timeline: 1 week
```

---

### Pattern E: Small-N Qualitative (Minimal Infrastructure)

**What it is:** Gather feedback from 1-10 people.

**When to use:** Small team, qualitative aspects matter.

---

**Example 11: Team Preference Test**
```
Claim: Better user experience
Success-if: 3/4 team members prefer new version in blind test
Failure-if: Majority prefer old version
Measurement: A/B preference test with team
Timeline: 1 day
```

---

### Pattern F: Reversal Tests (Powerful Insight)

**What it is:** Remove/disable change, see if things get worse.

**When to use:** Verify something actually provides value.

---

**Example 12: Necessity Validation Test**
```
Claim: Feature is valuable
Success-if: Removing it makes workflow harder (team complains)
Failure-if: Removal has no impact, nobody notices
Measurement: Temporarily disable, observe reaction
Timeline: 1 day
```

---

## Choosing Your Evidence Pattern

**Decision tree:**

**Have no infrastructure at all?**
→ Pattern A (Self-Experience)
→ Pattern B (Binary Outcomes)

**Solo or tiny team (1-3 people)?**
→ Pattern A (Self-Experience)
→ Pattern C (Comparative)

**Small team (3-10 people)?**
→ Pattern E (Small-N Qualitative)
→ Pattern D (Counting)

**Want to verify it actually matters?**
→ Pattern F (Reversal)

**The key:** Pick the simplest pattern that can falsify your claim.

Don't over-engineer measurement. Match evidence to what's available.

---

## Matching Tests to Available Resources

### High Infrastructure Version
```
Success-if:
  - Color usage >30% of strokes
  - Accidental triggers <5%
  - A/B test: 50/50 split, 1000+ users

Failure-if:
  - Color usage <20%
  - Accidental triggers >10%
  - Session abandonment increases

Measurement: Analytics, error tracking, A/B test
Timeline: 2 weeks
```

### Medium Infrastructure Version
```
Success-if:
  - 6/8 beta users report using color more
  - No bug reports about accidental color changes

Failure-if:
  - Users say "confusing" or "annoying"
  - Bug reports about unwanted changes

Measurement: User interviews, bug tracker
Timeline: 2 weeks beta test
```

### Low Infrastructure Version
```
Success-if:
  - I use color in my own drawings (within 2 days)
  - Teammate tries color without being told
  - No accidental color changes in my testing

Failure-if:
  - I avoid using color myself
  - Colors change when I don't intend them to

Measurement: My own usage, watch teammate
Timeline: 1 week
```

**All three are valid contact tests—matched to available evidence.**

---

## Anti-Patterns

### Anti-Pattern 1: No Failure Condition

❌ **Bad:**
```
Success-if: System is better
Failure-if: [not specified]
```

✅ **Good:**
```
Success-if: Load time <2 seconds
Failure-if: Load time >5 seconds or worse than before
```

---

### Anti-Pattern 2: Vague Measurements

❌ **Bad:**
```
Measurement: Check if users like it
```

✅ **Good:**
```
Measurement: Ask 5 users "Do you prefer this?" Count yes/no.
```

---

### Anti-Pattern 3: Moving Goalposts

❌ **Bad:** After test fails: "Well, I meant a different kind of improvement..."

✅ **Good:** After test fails: "Contact test failed. Claim was wrong. Here's what I learned: [revision]"

---

## Contact Tests in Different Contexts

### For Developer Tools/Libraries

**You have:** No end users, developer adoption signals, code quality metrics.

**Good contact tests:**
```
Success-if:
  - 2/3 teammates adopt it for new code
  - Reduces boilerplate from 20 lines to <5 lines
  - Zero "how does this work?" questions in code review

Failure-if:
  - Teammates continue using old approach
  - Still need same amount of code
```

---

### For Early Prototypes

**You have:** No users yet, hypothesis about value, self-observation only.

**Good contact tests:**
```
Success-if:
  - I use it myself in actual work (not just demo)
  - Can show it to someone and they get it immediately
  - I'd be willing to maintain this code

Failure-if:
  - I don't actually use it
  - Requires extensive explanation
```

---

### For Refactoring

**You have:** Before/after comparison, test suite, code metrics.

**Good contact tests:**
```
Success-if:
  - All tests pass
  - Code is shorter (fewer lines)
  - Next feature takes less time to add (try it)

Failure-if:
  - Tests fail
  - Code is longer or same length
```

---

## Integrating Contact Tests Into Workflow

### In Planning (AGENTS.md)

**Before starting work:**
```
Aim: [What we're trying to do]
Claim: [What we believe will happen]
Assumptions: [Load-bearing beliefs]
Contact Test: [How we'll know if we're right]
```

**Don't write code until you can specify the contact test.**

---

### In Commits (COMMITS.md)

**When recording changes:**
```
Contact:
  Success-if: [observable outcome]
  Failure-if: [observable failure]
  Measurement: [how we'll check]
  Timeline: [when we'll evaluate]
```

---

### In Code Review

**Reviewer asks:**
- "What's the contact test for this claim?"
- "How will we know if it worked?"
- "What would show this didn't improve things?"

**If answer is "trust me" or "we'll see," request contact test.**

---

### After Implementation

**Evaluation ritual:**
1. Wait for timeline (1 week, 1 month, etc.)
2. Gather specified evidence
3. Compare to success/failure conditions
4. Document outcome in revision commit or log
5. Update understanding based on results

**If test passed:**
```
revision: Validated [claim] via contact test

Evidence gathered: [what we observed]
Contact test result: Success
Claim confirmed: [restate claim]
```

**If test failed:**
```
revision: Falsified [claim] via contact test

Evidence gathered: [what we observed]
Contact test result: Failure
Claim was wrong: [what we believed]
Learned: [updated understanding]
Next: [alternative approach]
```

---

## When Contact Tests Aren't Needed

**Skip contact tests for:**

1. **Trivial mechanical changes** - Typo fixes, formatting, renaming with clear scope
2. **Pure deletions** - Removing unused code (contact test: "does anything break?")
3. **Obvious failures** - Compilation errors, test failures (already has feedback)
4. **Exploratory work** - "I don't know what will happen, investigating"

**General rule:** If you're making a claim about improvement, you need a contact test.

---

## FAQ

### "Isn't this just testing?"

**No.**

**Traditional testing:** Verify code does what it's supposed to do.

**Contact testing:** Verify claims about improvement are true.

**Example:**
- Test: "Color picker allows color selection" (functionality)
- Contact test: "Color usage increases >30%" (improvement claim)

Both matter. Contact tests prevent shipping features that technically work but don't improve anything.

---

### "What if I can't think of a contact test?"

**Three possibilities:**

1. **Claim is too vague** → Make it specific ("Improve UX" → "Reduce steps from 5 to 3")
2. **Claim is unfalsifiable (mythology)** → Revise or abandon
3. **You need to explore first** → Mark as exploration ("I don't know yet, investigating")

**If you truly can't specify a contact test, you're probably about to ship mythology.**

---

### "Can contact tests be wrong?"

**Yes.**

You might test the wrong thing, measure vanity metrics, or miss important failure modes.

**This is fine.** Contact tests are hypotheses about what matters. You'll learn through iteration.

**Better to have imperfect contact test than none at all.**

---

### "How do I handle long-term effects?"

**Use staged contact tests:**

**Immediate:** Feature functions without errors (implementation day)
**Short-term:** I still use it, no bugs found (1 week)
**Medium-term:** Usage continues, no support issues (1 month)
**Long-term:** Becomes part of standard workflow (3 months)

Start with short-term tests. Add long-term tests if short-term passes.

---

## Summary

**Contact tests prevent mythology by requiring claims to touch reality.**

**Key principles:**

1. **Match test to available evidence** (high/medium/low infrastructure)
2. **Specify both success and failure** (falsifiability required)
3. **Write test before building** (not post-hoc justification)
4. **Actually evaluate** (don't write tests you never check)
5. **Revise when wrong** (failure is learning, not shame)

**The goal:** Make it impossible to ship elegant explanations that don't actually improve anything.

**The practice:** Before you claim something is better, specify how you'll know.

---

**Testing version:** 1.0  
**Last updated:** 2026-01-31  
**Part of Attractor Protocol**  
**License:** CC0

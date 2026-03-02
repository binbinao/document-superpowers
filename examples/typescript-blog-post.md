# Example: Writing a Technical Blog Post

This is a complete walkthrough of using Document Superpowers to write a blog post.

## Initial Request

```
User: "I want to write a blog post about the benefits of using TypeScript"
```

## Stage 1: Brainstorming

The agent invokes the `brainstorming` skill automatically:

### Question 1
```
Agent: "Let me understand what you're building. Who's your target audience?"
```

Options presented:
- A) JavaScript developers considering TypeScript
- B) Beginners learning their first language  
- C) Engineering managers evaluating tools
- D) TypeScript users wanting advanced tips

```
User: "A - JavaScript devs considering it"
```

### Question 2
```
Agent: "What do you want readers to do after reading?"
```

Options:
- A) Try TypeScript on a new project
- B) Migrate an existing project
- C) Just understand what it is
- D) Advocate for TypeScript in their team

```
User: "A - Try it on a new project"
```

### Question 3
```
Agent: "What's your main argument for TypeScript?"
```

```
User: "It catches bugs early and makes refactoring safer"
```

### Question 4
```
Agent: "Any constraints on length or tone?"
```

```
User: "Around 1200 words, conversational but technical"
```

### Brief Presentation

```
Agent: "Here's the topic brief based on our discussion:

## Audience
JavaScript developers with 1-3 years experience who've heard about TypeScript 
but haven't tried it. Comfortable with ES6+, familiar with npm/build tools.

## Purpose
Convince readers to try TypeScript on their next greenfield project by showing
concrete examples of how types catch common JavaScript bugs early.

## Core Message
TypeScript adds guardrails that catch bugs at compile-time instead of runtime,
making your code more reliable without significantly slowing down development.

## Key Points
1. Common JS bugs that TypeScript prevents (undefined, typos, API changes)
2. Real-world example: before/after TypeScript migration
3. Learning curve is gentle - start simple, add types gradually

## Tone & Style
Conversational, peer-to-peer advice. Use concrete examples. Acknowledge 
trade-offs honestly. No TypeScript evangelism.

## Constraints
- Length: ~1200 words
- Format: Blog post with code examples
- No prerequisites beyond JavaScript knowledge

Does this capture what you want to write?"
```

```
User: "Yes, looks good!"
```

### Brief Saved

```
Agent: "Great! Saved topic brief to docs/writing/2026-03-02-typescript-benefits-brief.md

Next, I'll create the article plan. This will take a moment..."

[Invokes writing-article-plan skill]
```

## Stage 2: Planning

```
Agent: "I'm using the writing-article-plan skill to create the article outline."
```

### Plan Created

```markdown
# Why TypeScript Might Be Worth Your Time - Writing Plan

> **For Claude:** REQUIRED SUB-SKILL: Use document-superpowers:executing-article-plan

**Date**: 2026-03-02
**Audience:** JavaScript developers (1-3 years experience)
**Goal:** Convince readers to try TypeScript on next greenfield project
**Total Length:** 1200 words
**Tone:** Conversational, peer-to-peer, honest about trade-offs
**Core Message:** TypeScript catches bugs at compile-time, making code more reliable without major slowdown

---

## Article Structure Overview

1. **Introduction** (150 words) - Hook + thesis
2. **Section 1: The Problem** (300 words) - Common JS bugs
3. **Section 2: The Solution** (300 words) - How TypeScript helps
4. **Section 3: Getting Started** (300 words) - Practical first steps
5. **Conclusion** (150 words) - Call to action

Total: ~1200 words

---

## Section 1: Introduction (150 words)

**Purpose:** Hook readers and present the core message clearly

**Key Points:**
1. Opening: "You've deployed a fix for the same undefined error three times this month"
2. TypeScript as guardrails, not handcuffs
3. Thesis: Catches bugs at compile-time, gentle learning curve
4. Roadmap: common bugs → how TS helps → getting started

**Supporting Evidence:**
- Personal experience with JS undefined errors

**Tone Notes:**
Start with relatable pain point

**Transitions:**
- **To next:** Lead into catalog of common JS bugs

**Self-Check Questions:**
- Does the hook grab attention immediately?
- Is the thesis clear?
- Will JS devs feel understood (not judged)?

---

## Section 2: The Problem - Common JavaScript Bugs (300 words)

**Purpose:** Catalog concrete examples of bugs TypeScript prevents

**Key Points:**
1. Typos in property names (user.nmae vs user.name)
2. Null/undefined access (API returns null, code assumes object)
3. API contract changes (function signature changes, calls not updated)
4. Each example shows: the bug, when it manifests, debugging pain

**Supporting Evidence:**
- Code examples of each bug type
- Quick note: these are runtime errors in JS

**Tone Notes:**
Empathy - we've all written these bugs

**Transitions:**
- **From previous:** Introduction mentions bugs
- **To next:** "So how does TypeScript help?"

**Research Needed:**
- [ ] Find statistic on most common JS runtime errors (if available)

**Self-Check Questions:**
- Are examples concrete and relatable?
- Does the pain point come through?
- Any JS developer would recognize these?

---

## Section 3: The Solution - How TypeScript Prevents These (300 words)

**Purpose:** Show how TypeScript catches each bug at compile-time

**Key Points:**
1. Same examples from Section 2, now with TypeScript
2. Red squiggly lines catch typos immediately
3. Type annotations force null checking
4. Refactoring tools find all call sites automatically
5. Key insight: move bug discovery from production → IDE

**Supporting Evidence:**
- Side-by-side code comparisons (JS vs TS)
- Screenshot or description of IDE error message

**Tone Notes:**
Explanatory, not preachy. Show, don't tell.

**Transitions:**
- **From previous:** "For each of these bugs, TypeScript..."
- **To next:** "Convinced? Here's how to start."

**Research Needed:**
- [ ] Verify TypeScript syntax for examples

**Self-Check Questions:**
- Are the before/after comparisons clear?
- Is the value proposition obvious?
- Any jargon that needs explanation?

---

## Section 4: Getting Started (300 words)

**Purpose:** Lower the barrier to trying TypeScript

**Key Points:**
1. Start simple: add TypeScript to one new file
2. Use `any` type initially - gradually add proper types
3. Don't migrate existing projects first (too much friction)
4. Recommended learning path: TS playground → new side project → work project
5. Common pitfall: trying to be too strict too fast

**Supporting Evidence:**
- Simple getting-started code snippet
- Link to TypeScript playground

**Tone Notes:**
Encouraging, permission to start simple

**Transitions:**
- **From previous:** Solution is compelling, now make it actionable
- **To next:** Conclusion will reinforce "try it" message

**Research Needed:**
- [ ] Current TypeScript playground URL
- [ ] Simple tsconfig.json example

**Self-Check Questions:**
- Are next steps concrete and achievable?
- Did we address "too hard to start" objection?
- Is the learning path realistic?

---

## Section 5: Conclusion (150 words)

**Purpose:** Reinforce core message and give clear call to action

**Key Points:**
1. Recap: TypeScript = compile-time bug catching
2. Honest acknowledgment: yes, there's a learning curve
3. But: the curve is gentle, and the payoff is immediate
4. CTA: Try it on your next new project (not existing codebase)
5. Close: "Your future self will thank you"

**Tone Notes:**
Friendly encouragement, not overselling

**Transitions:**
- **From previous:** Getting started was covered, now close the loop

**Self-Check Questions:**
- Is the CTA specific and achievable?
- Did we acknowledge concerns honestly?
- Memorable closing?

---

## Research Summary

**Priority 1 (Must Have):**
- [ ] Verify TypeScript syntax for code examples
- [ ] TypeScript playground URL

**Priority 2 (Nice to Have):**
- [ ] Statistics on common JS errors
- [ ] Real-world migration example

---

## Style Guidelines

**Do:**
- Use active voice
- Include runnable code examples
- Keep paragraphs under 4 sentences
- Acknowledge trade-offs honestly

**Avoid:**
- TypeScript evangelism
- "You should" language
- Overwhelming beginners with advanced features
- Long explanations without code

---

Saved to: docs/writing/2026-03-02-typescript-benefits-plan.md
```

### Execution Choice

```
Agent: "Article plan complete! Two execution options:

1. **Batch Execution** - Write 2-3 sections at a time, checkpoint for review
2. **Subagent-Driven** - Fresh subagent per section, two-stage review, tight feedback loop

Which approach?"
```

```
User: "Batch execution"
```

## Stage 3: Execution

```
Agent: "I'm using the executing-article-plan skill to write this article."
```

### Batch 1: Sections 1-2

```
Agent: [Writes Introduction and Section 2: The Problem]

## Checkpoint: Sections 1-2 Complete

**Sections written:**
- Section 1: Introduction (147 words) ✓
- Section 2: The Problem (312 words) ✓

**Self-check summary:**
- Word counts: 459 / 1200 (38% of plan)
- All key points covered: ✓
- Transitions smooth: ✓
- Tone consistent: ✓
- Code examples included: ✓

**Preview (Section 1):**
> You've deployed a fix for the same "Cannot read property 'name' of undefined" 
> error three times this month. Each time, it's a slightly different scenario, 
> but the root cause is always the same: JavaScript's flexibility biting you in 
> production. What if these bugs showed up in your editor instead...

**What's next:**
- Section 3: The Solution (how TypeScript prevents these bugs)

**Your options:**
1. **Continue** - Proceed to next batch
2. **Revise** - Make changes to these sections  
3. **Pause** - Stop here and review later
```

```
User: "Continue"
```

### Batch 2: Sections 3-4

```
Agent: [Writes Section 3: The Solution and Section 4: Getting Started]

## Checkpoint: Sections 3-4 Complete

**Sections written:**
- Section 3: The Solution (295 words) ✓
- Section 4: Getting Started (308 words) ✓

**Self-check summary:**
- Word counts: 1062 / 1200 (89% of plan)
- All key points covered: ✓
- Code examples clear: ✓
- Transitions smooth: ✓

**What's next:**
- Section 5: Conclusion

Continue?
```

```
User: "Yes"
```

### Final Section

```
Agent: [Writes Section 5: Conclusion]

Full draft complete! Saved to docs/writing/2026-03-02-typescript-benefits-draft.md

**Draft stats:**
- Total words: 1218 (target: 1200, +1.5%)
- Sections: 5
- Code examples: 6
- Tone: Conversational/technical

**Next step:** Invoke reviewing-article skill for multi-pass review

Ready to proceed with review?
```

```
User: "Yes"
```

## Stage 4: Review

```
Agent: "I'm using the reviewing-article skill for systematic review."
```

### Four-Pass Review

```markdown
# Why TypeScript Might Be Worth Your Time - Review Log

**Date:** 2026-03-02
**Draft Version:** 2026-03-02-typescript-benefits-draft.md
**Review Duration:** ~8 minutes

---

## Executive Summary

**Overall Assessment:** Good - Ready with minor fixes

**Critical Issues:** 0
**Moderate Issues:** 2  
**Minor Issues:** 4

**Estimated Fix Time:** 10 minutes

**Recommendation:** Fix moderate issues, publish

---

## Pass 1: Logic Check

**Issues Found:** None

**Strengths:**
- Clear argument progression (problem → solution → action)
- Thesis well-supported by examples
- No logical contradictions
- Conclusion ties back to introduction effectively

---

## Pass 2: Evidence Check

**Issues Found:**

**[MODERATE]** Section 2, paragraph 2
- **Issue:** Code example missing
- **Current:** "Consider this common scenario..."
- **Problem:** Paragraph describes bug but doesn't show code
- **Fix:** Add inline code example

**[MODERATE]** Section 4, paragraph 3
- **Issue:** TypeScript playground link missing
- **Current:** "Try the TypeScript playground"
- **Problem:** No URL provided
- **Fix:** Add https://www.typescriptlang.org/play

**Strengths:**
- Code examples are clear and runnable
- Examples progress from simple to complex appropriately
- All claims about TypeScript features are accurate

---

## Pass 3: Flow Check

**Issues Found:**

**[MINOR]** Section 2 → Section 3 transition
- **Issue:** Slightly abrupt
- **Current:** Section 2 ends, Section 3 starts "Let's see how TypeScript helps"
- **Fix:** Add one transition sentence at end of Section 2

**[MINOR]** Section 3, paragraphs 2-4
- **Issue:** All paragraphs same structure (example → explanation)
- **Fix:** Vary paragraph structure for one of them

**Strengths:**
- Overall arc is clear and compelling
- Introduction hooks effectively
- Pacing is appropriate

---

## Pass 4: Polish

**Issues Found:**

**[MINOR]** Throughout
- 3 instances of passive voice (marked in text)
- Inconsistent code fence language tags (js vs javascript)

**[MINOR]** Section 4, paragraph 1
- **Issue:** Typo "dont" → "don't"

**Formatting:**
- Code blocks: need consistent ``` javascript ``` tags
- Headers: all good
- Lists: consistent formatting

**Word Count:**
- Current: 1218 words
- Target: 1200 words  
- Overrun: 18 words (1.5%)
- Action: Acceptable, within tolerance

**Strengths:**
- Clean, professional language
- Good use of code examples
- Technical terms explained clearly
- Conversational tone maintained

---

## Priority Fix List

### Must Fix Before Publishing
1. Section 2: Add missing code example in paragraph 2
2. Section 4: Add TypeScript playground URL

### Should Fix (Improves Quality)
1. Section 2→3: Add transition sentence
2. Fix typo in Section 4 ("dont" → "don't")
3. Standardize code block language tags to ``` typescript ```
4. Convert 3 passive voice instances to active

### Nice to Have (Optional)
1. Vary paragraph structure in Section 3

---

## Strengths to Preserve

- Opening hook is extremely effective
- Code examples are practical and clear
- Honest acknowledgment of learning curve
- Concrete "getting started" steps
- Memorable conclusion

---
```

### Applying Fixes

```
Agent: "Review complete! Found 2 moderate and 4 minor issues.

Applying fixes now:

1. ✅ Added code example to Section 2
2. ✅ Added TypeScript playground URL  
3. ✅ Added transition sentence (Section 2→3)
4. ✅ Fixed typo (dont → don't)
5. ✅ Standardized code blocks to typescript
6. ✅ Converted passive voice to active (3 instances)

Final article saved to: docs/writing/2026-03-02-typescript-benefits-final.md
Review log saved to: docs/writing/2026-03-02-typescript-benefits-review.md
```

## Final Result

```
Agent: "Article complete! 📝

**Final Stats:**
- Word count: 1221
- Reading time: ~5 minutes
- Status: Ready for publication

**Files created:**
- docs/writing/2026-03-02-typescript-benefits-brief.md (topic brief)
- docs/writing/2026-03-02-typescript-benefits-plan.md (outline)
- docs/writing/2026-03-02-typescript-benefits-draft.md (initial draft)
- docs/writing/2026-03-02-typescript-benefits-review.md (review log)
- docs/writing/2026-03-02-typescript-benefits-final.md (publication-ready)

Would you like me to:
1. Export to Medium/WordPress format
2. Generate social media snippets
3. Create a summary/abstract
4. Something else"
```

```
User: "Looks great, thanks!"
```

---

## Key Takeaways

This example demonstrates:

1. **Structured brainstorming** - One question at a time, building understanding
2. **Detailed planning** - Every section planned before writing
3. **Incremental execution** - Checkpoints prevent wasted effort
4. **Systematic review** - Four passes catch different issue types
5. **Complete documentation** - Every stage is saved and traceable

The whole process took about 30-40 minutes but produced a publication-ready article that would typically require multiple draft-and-rewrite cycles.

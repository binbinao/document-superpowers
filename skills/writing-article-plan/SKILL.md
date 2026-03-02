---
name: writing-article-plan
description: "Use when you have an approved topic brief. Creates detailed article outline with section structure, key points, word counts, and research needs before writing."
---

# Writing Article Plans

## Overview

Write comprehensive article outlines that break writing into manageable sections. Document everything needed: section themes, key points, supporting evidence, transitions, word counts. Assume the writer will execute this section-by-section with minimal context switching.

**Announce at start:** "I'm using the writing-article-plan skill to create the article outline."

**Context:** This should follow an approved topic brief from the brainstorming skill.

**Save plans to:** `docs/writing/YYYY-MM-DD-<topic>-plan.md`

## Section Granularity

**Each section is one focused piece (150-400 words):**
- Introduction: Hook + thesis
- Body Section 1: One key argument
- Body Section 2: Another key argument
- Body Section 3: Third key argument
- Conclusion: Summary + call to action

**Why this size?** Long enough to develop an idea, short enough to write in one sitting (15-30 minutes).

## Plan Document Header

**Every plan MUST start with this header:**

```markdown
# [Article Title] - Writing Plan

> **For Claude:** REQUIRED SUB-SKILL: Use document-superpowers:executing-article-plan to write this article section-by-section.

**Date**: YYYY-MM-DD

**Audience:** [target readers from brief]

**Goal:** [what readers should think/do after reading]

**Total Length:** [target word count]

**Tone:** [formal/casual/technical/conversational]

**Core Message:** [one sentence from brief]

---
```

## Section Structure

```markdown
## Section N: [Section Title] (target: XXX words)

**Purpose:** [What this section achieves in the article's argument]

**Key Points:**
1. [First key point with supporting detail]
2. [Second key point with example/evidence]
3. [Transition to next section]

**Supporting Evidence:**
- [Statistic/study/quote with source]
- [Example/case study]
- [Data point]

**Tone Notes:**
[Any specific style guidance for this section]

**Transitions:**
- **From previous:** [How this connects to prior section]
- **To next:** [How this leads into next section]

**Research Needed:**
- [ ] Find statistic for claim X
- [ ] Locate example of Y
- [ ] Verify quote from Z

**Self-Check Questions:**
- Does this support the core message?
- Is the logic clear and well-supported?
- Does it flow naturally from the previous section?
```

## Complete Plan Template

```markdown
# [Article Title] - Writing Plan

> **For Claude:** REQUIRED SUB-SKILL: Use document-superpowers:executing-article-plan

**Date**: YYYY-MM-DD
**Audience:** [target readers]
**Goal:** [desired outcome]
**Total Length:** [word count]
**Tone:** [style]
**Core Message:** [one sentence]

---

## Article Structure Overview

1. **Introduction** (150 words) - Hook + thesis
2. **Section 1** (300 words) - First key argument
3. **Section 2** (300 words) - Second key argument
4. **Section 3** (300 words) - Third key argument
5. **Conclusion** (150 words) - Summary + CTA

Total: ~1200 words

---

## Section 1: Introduction (150 words)

**Purpose:** Hook readers and present the core message clearly

**Key Points:**
1. Opening hook (question/statistic/story)
2. Why this matters to the reader
3. Thesis statement (core message)
4. Brief roadmap of what's coming

**Supporting Evidence:**
- [Compelling statistic or example for hook]

**Tone Notes:**
Start strong - grab attention immediately

**Transitions:**
- **To next:** Lead into first key argument

**Research Needed:**
- [ ] Find attention-grabbing opening statistic

**Self-Check Questions:**
- Does the hook grab attention in the first sentence?
- Is the thesis clear and compelling?
- Will readers want to keep reading?

---

[Repeat for each section...]

---

## Research Summary

**Priority 1 (Must Have):**
- [ ] [Critical source/data point]

**Priority 2 (Should Have):**
- [ ] [Supporting example]

**Priority 3 (Nice to Have):**
- [ ] [Additional context]

---

## Style Guidelines

**Do:**
- Use active voice
- Keep paragraphs under 4 sentences
- Include concrete examples
- [Specific style preferences]

**Avoid:**
- Jargon without explanation
- Long-winded sentences
- Vague generalizations
- [Specific things to avoid]
```

## Remember
- Each section has clear purpose and word target
- All claims need supporting evidence
- Transitions connect sections smoothly
- Research checklist prevents mid-writing gaps
- Style guidelines ensure consistency

## Execution Handoff

After saving the plan, offer execution choice:

**"Article plan complete and saved to `docs/writing/<filename>.md`. Two execution options:**

**1. Subagent-Driven (this session)** - I dispatch fresh subagent per section, review between sections, iterate quickly

**2. Batch Execution (focused writing)** - Write all sections with checkpoints after every 2-3 sections

**Which approach?"**

**If Subagent-Driven chosen:**
- **REQUIRED SUB-SKILL:** Use document-superpowers:subagent-driven-writing
- Stay in this session
- Fresh subagent per section + content review

**If Batch Execution chosen:**
- **REQUIRED SUB-SKILL:** Use document-superpowers:executing-article-plan
- Stay in this session
- Write sections in batches with human checkpoints

## Quality Checklist

Before finalizing the plan, verify:
- [ ] Every section has a clear purpose
- [ ] Word counts add up to target length (±10%)
- [ ] Transitions between sections are logical
- [ ] Research needs are identified upfront
- [ ] Style guidelines match the brief's tone
- [ ] Each section has self-check questions

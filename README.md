# Document Superpowers

A complete document writing workflow for your AI writing agents, inspired by [obra/superpowers](https://github.com/obra/superpowers) code development methodology.

## Overview

Document Superpowers transforms your AI from a "just write something" tool into a systematic writing partner. It enforces a proven four-stage process that produces higher-quality articles, blog posts, and documentation.

## How It Works

When you ask your AI to write something, it doesn't just start typing. Instead:

1. **Brainstorming** - It steps back and asks what you're really trying to communicate. Who's the audience? What's the core message? What should readers do after reading?

2. **Planning** - Once it understands the topic, it creates a detailed outline breaking the article into manageable sections (150-400 words each), complete with key points, evidence needs, and transitions.

3. **Execution** - It writes section by section, with self-checks and validation at each step. You get checkpoints every 2-3 sections to review progress.

4. **Review** - Systematic four-pass review covering logic, evidence, flow, and polish. Every issue gets categorized, documented, and fixed.

The result? Professional-quality writing that's actually readable, well-structured, and achieves its purpose.

## The Four-Stage Workflow

```
💡 Brainstorming → 📋 Planning → ✍️ Execution → 🔍 Review
```

Each stage has strict gates - you can't skip ahead without completing the previous stage. No more "I'll just wing it" articles.

## Skills Library

### Core Workflow
- **brainstorming** - Socratic topic exploration and brief creation
- **writing-article-plan** - Detailed section-by-section outline with research checklist
- **executing-article-plan** - Batch writing with human checkpoints
- **reviewing-article** - Multi-pass systematic review (logic → evidence → flow → polish)

### Advanced
- **subagent-driven-writing** - Fast iteration with fresh subagent per section and two-stage review

## Philosophy

- **Structured over ad-hoc** - Process prevents wasted effort
- **Incremental validation** - Catch issues early with frequent checkpoints
- **Evidence-based** - Every claim needs support
- **Reader-first** - Always know who you're writing for and what they need
- **YAGNI for content** - Cut ruthlessly, say only what matters

## Installation

### Claude Code

```bash
# Clone to Claude Code global skills directory
git clone https://github.com/binbinao/document-superpowers.git ~/.claude/skills/document-superpowers
```

After cloning, add skill references in `~/.claude/CLAUDE.md` or your project's `.claude/CLAUDE.md`:

```markdown
## Skills
- ~/.claude/skills/document-superpowers/skills/brainstorming/SKILL.md
- ~/.claude/skills/document-superpowers/skills/writing-article-plan/SKILL.md
- ~/.claude/skills/document-superpowers/skills/executing-article-plan/SKILL.md
- ~/.claude/skills/document-superpowers/skills/reviewing-article/SKILL.md
- ~/.claude/skills/document-superpowers/skills/subagent-driven-writing/SKILL.md
```

### Cursor

```bash
# Clone to Cursor global skills directory
git clone https://github.com/binbinao/document-superpowers.git ~/.cursor/skills/document-superpowers

# Or clone to project-level directory
git clone https://github.com/binbinao/document-superpowers.git .cursor/skills/document-superpowers
```

After cloning, add the skill paths in Cursor's Rules or Agent Settings.

### Codebuddy (CLI)

```bash
# Clone to Codebuddy global skills directory
git clone https://github.com/binbinao/document-superpowers.git ~/.codebuddy/skills/document-superpowers

# Or clone to project-level directory
git clone https://github.com/binbinao/document-superpowers.git .codebuddy/skills/document-superpowers
```

After cloning, add the skill paths in Codebuddy's configuration.

### Gemini CLI

```bash
# Clone to Gemini CLI config directory
git clone https://github.com/binbinao/document-superpowers.git ~/.gemini/skills/document-superpowers
```

Add skill references in `~/.gemini/GEMINI.md` or your project's `GEMINI.md`:

```markdown
## Skills
- ~/.gemini/skills/document-superpowers/skills/brainstorming/SKILL.md
- ~/.gemini/skills/document-superpowers/skills/writing-article-plan/SKILL.md
- ~/.gemini/skills/document-superpowers/skills/executing-article-plan/SKILL.md
- ~/.gemini/skills/document-superpowers/skills/reviewing-article/SKILL.md
- ~/.gemini/skills/document-superpowers/skills/subagent-driven-writing/SKILL.md
```

### OpenClaw

```bash
# Option 1: Clone to your workspace skills directory
git clone https://github.com/binbinao/document-superpowers.git ~/.openclaw/skills/document-superpowers

# Option 2: Install via OpenClaw skills manager (if available)
openclaw skills install document-superpowers
```

### Other Platforms

Copy the `skills/` directory into your AI agent's skills folder according to your platform's documentation.

## Quick Start

### 1. Start with an Idea

```
"I want to write about [topic]"
```

Your agent will automatically invoke the brainstorming skill and start asking questions.

### 2. Answer Questions

The agent asks one question at a time to understand:
- Who's your audience?
- What's the main message?
- What action should readers take?
- Any constraints (length, tone, format)?

### 3. Review the Brief

Once it understands your topic, it presents a brief covering:
- Audience persona
- Purpose and core message
- Key supporting points
- Tone and style

Approve or request revisions.

### 4. Get the Plan

After brief approval, it creates a detailed outline:
- Section breakdown with word counts
- Key points per section
- Supporting evidence needs
- Transitions between sections

### 5. Choose Execution Mode

**Batch execution** (default):
- Write 2-3 sections at a time
- Checkpoint for review
- Continue until complete
- Good for: straightforward articles, focused writing sessions

**Subagent-driven** (advanced):
- Fresh subagent per section
- Two-stage review (spec + quality)
- Tight feedback loop
- Good for: complex articles, high-stakes content

### 6. Review and Polish

Systematic four-pass review:
1. **Logic** - Is the argument sound?
2. **Evidence** - Are claims supported?
3. **Flow** - Does it read smoothly?
4. **Polish** - Grammar, formatting, style

Issues get categorized (critical/moderate/minor) and fixed systematically.

### 7. Publish

Your final article is saved with:
- Full review log documenting all changes
- Metadata (word count, reading time, audience)
- Ready-to-publish format

## Example Workflow

```
User: "I want to write a blog post about why engineers should write documentation"

Agent: [invokes brainstorming]
"Let me understand what you're building. Who's your target audience - junior engineers, senior engineers, or engineering managers?"

User: "Senior engineers who hate writing docs"

Agent: "Got it. What do you want them to do after reading - start writing better docs, advocate for documentation culture, or something else?"

User: "Change their mind that documentation is valuable"

Agent: [continues questions...]
Agent: [presents brief...]
Agent: [gets approval...]
Agent: [creates plan...]
Agent: [offers execution choice...]

User: "Batch execution"

Agent: [writes sections 1-3...]
Agent: "Checkpoint: Sections 1-3 complete (612 words). Continue?"

User: "Yes"

Agent: [writes sections 4-5...]
Agent: "Draft complete! Ready for review?"

User: "Yes"

Agent: [runs four-pass review...]
Agent: "Review complete. 2 critical issues found and fixed. Final article ready!"
```

## Documentation

Additional documentation is available in the `docs/` directory:

```
docs/
├── DEVELOPMENT.md                      # Development overview & architecture details
├── SUMMARY.md                          # Implementation summary & project statistics
└── examples/
    └── typescript-blog-post.md         # Complete end-to-end writing walkthrough
```

| Document | Description |
|---|---|
| [DEVELOPMENT.md](docs/DEVELOPMENT.md) | In-depth development guide covering project architecture, skill design, workflow details, and extension points |
| [SUMMARY.md](docs/SUMMARY.md) | Implementation summary with project statistics, file inventory, and feature highlights |
| [typescript-blog-post.md](docs/examples/typescript-blog-post.md) | A complete example walkthrough: writing a TypeScript blog post from brainstorming to final review |

## Writing Project File Structure

During a writing project, the workflow generates the following files:

```
docs/writing/
├── YYYY-MM-DD-topic-brief.md          # Approved topic brief
├── YYYY-MM-DD-topic-plan.md           # Detailed outline
├── drafts/
│   └── YYYY-MM-DD-topic/
│       ├── section-1-intro.md         # Individual section drafts
│       ├── section-2-argument.md
│       └── ...
├── YYYY-MM-DD-topic-draft.md          # Merged full draft
├── YYYY-MM-DD-topic-review.md         # Review log
└── YYYY-MM-DD-topic-final.md          # Published version
```

Everything is version-controlled and traceable.

## Comparison to Code Superpowers

| Code (superpowers) | Content (document-superpowers) |
|---|---|
| brainstorming → design doc | brainstorming → topic brief |
| writing-plans → implementation plan | writing-article-plan → article outline |
| executing-plans → code | executing-article-plan → draft |
| requesting-code-review | reviewing-article |
| TDD (red-green-refactor) | write-check-revise |
| Git worktrees | Section drafts |
| Subagent per task | Subagent per section |

## Key Principles

### 1. No "Just Write It"

Every article goes through the full process, even "simple" blog posts. Simple topics can have short briefs (a few sentences), but you MUST present and approve the brief before writing.

### 2. One Question at a Time

The agent never overwhelms you with multiple questions. Brainstorming is a conversation, not a form to fill out.

### 3. Bite-Sized Sections

Sections are 150-400 words - small enough to write in one sitting (15-30 minutes), large enough to develop an idea.

### 4. Checkpoints, Not Marathons

Review after every 2-3 sections. Catch issues early rather than discovering problems in a 3000-word wall of text.

### 5. Four-Pass Review

Each pass focuses on one dimension:
- Logic (is it sound?)
- Evidence (is it supported?)
- Flow (is it smooth?)
- Polish (is it clean?)

Mixing concerns makes issues harder to spot.

### 6. Document Everything

Every stage produces artifacts:
- Brief (topic understanding)
- Plan (writing blueprint)
- Section drafts (incremental progress)
- Review log (all issues and fixes)
- Final article (publication-ready)

## Tips for Success

### For Writers

**Trust the process** - It feels slower at first, but produces better results faster than iterative rewrites.

**Be specific in brainstorming** - The clearer your answers, the better the brief.

**Review checkpoints seriously** - Don't just rubber-stamp. Actually read the sections.

**Save the review log** - It's valuable documentation of your writing decisions.

### For AI Agents

**Enforce the gates** - Never skip brainstorming, even for "simple" articles.

**Ask better questions** - Multiple choice > open-ended when possible.

**Self-check rigorously** - Catch your own issues before human review.

**Preserve what works** - Don't over-edit during review. Fix problems, keep strengths.

## Advanced Usage

### Custom Templates

Create templates for specific document types:

```
skills/brainstorming/templates/
├── blog-post.md
├── technical-guide.md
├── api-documentation.md
└── research-paper.md
```

### Style Guides

Add organization-specific style guidelines:

```
skills/reviewing-article/style-guides/
├── ap-style.md
├── company-voice.md
└── technical-writing.md
```

### Integration

Use with other skills:
- **research skills** - Gather evidence during planning
- **SEO skills** - Optimize during review
- **publishing skills** - Deploy after finalization

## Contributing

Skills live directly in this repository. To contribute:

1. Fork the repository
2. Create a branch for your improvement
3. Follow the existing skill structure (see `skills/writing-skills/` in obra/superpowers for guidelines)
4. Test with real writing projects
5. Submit a PR

## Troubleshooting

**Agent skips brainstorming:**
- Check that skill descriptions are properly registered
- Ensure HARD-GATE instructions are present in SKILL.md

**Sections too long/short:**
- Adjust word targets in the plan
- Review if key points need more/less development

**Review finds nothing:**
- This might indicate shallow review
- Try providing specific examples of what to look for

**Subagent fails repeatedly:**
- Plan may be unclear - revise specifications
- Task brief may need more context
- Consider switching to batch execution

## License

MIT License - see LICENSE file for details

## Inspiration

This project is heavily inspired by [obra/superpowers](https://github.com/obra/superpowers) by Jesse Vincent. The systematic, gate-driven approach from code development translates beautifully to content creation.

## Support

- Issues: [GitHub Issues](https://github.com/binbinao/document-superpowers/issues)
- Discussions: [GitHub Discussions](https://github.com/binbinao/document-superpowers/discussions)

---

**Happy writing! 📝**

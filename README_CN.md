# Document Superpowers

一套完整的 AI 写作代理文档工作流，灵感来自 [obra/superpowers](https://github.com/obra/superpowers) 的代码开发方法论。

## 概述

Document Superpowers 将你的 AI 从一个"随便写点东西"的工具，转变为一个系统化的写作伙伴。它强制执行经过验证的四阶段流程，产出更高质量的文章、博客和技术文档。

## 工作原理

当你让 AI 写东西时，它不会直接开始输出文字，而是：

1. **头脑风暴** - 退后一步，了解你真正想要表达什么。目标读者是谁？核心信息是什么？读者读完后应该做什么？

2. **规划** - 在理解主题后，创建详细大纲，将文章拆分为可管理的章节（每节 150-400 词），包含要点、论据需求和过渡衔接。

3. **执行** - 逐节撰写，每一步都有自检和验证。每写完 2-3 个章节会设置检查点供你审阅。

4. **审阅** - 系统化的四轮审阅，涵盖逻辑、论据、流畅度和润色。每个问题都会被分类、记录和修正。

最终成果？专业品质的写作——可读性强、结构清晰、目标明确。

## 四阶段工作流

```
💡 头脑风暴 → 📋 规划 → ✍️ 执行 → 🔍 审阅
```

每个阶段都有严格的关卡——必须完成上一阶段才能进入下一阶段。不再有"先写了再说"的文章。

## 技能库

### 核心工作流
- **brainstorming** - 苏格拉底式主题探索与简报创建
- **writing-article-plan** - 逐节的详细大纲与调研清单
- **executing-article-plan** - 分批写作，设置人工检查点
- **reviewing-article** - 多轮系统化审阅（逻辑 → 论据 → 流畅度 → 润色）

### 进阶
- **subagent-driven-writing** - 每节使用独立子代理快速迭代，配合两阶段审阅

## 设计理念

- **系统化优于随意性** - 流程防止无效劳动
- **增量验证** - 通过频繁检查点及早发现问题
- **循证为本** - 每个论点都需要支撑
- **读者优先** - 始终明确读者是谁以及他们的需求
- **内容 YAGNI** - 大胆删减，只说重要的

## 安装

### Claude Code（通过 Plugin Marketplace）

在 Claude Code 中，先注册 marketplace：

```
/plugin marketplace add obra/superpowers-marketplace
```

然后从 marketplace 安装插件：

```
/plugin install superpowers@superpowers-marketplace
```

### Claude Code（手动安装）

```bash
# 克隆到 Claude Code 全局技能目录
git clone https://github.com/binbinao/document-superpowers.git ~/.claude/skills/document-superpowers
```

安装后在 `~/.claude/CLAUDE.md` 中添加技能引用，或在项目的 `.claude/CLAUDE.md` 中引用：

```markdown
## Skills
- ~/.claude/skills/document-superpowers/skills/brainstorming/SKILL.md
- ~/.claude/skills/document-superpowers/skills/writing-article-plan/SKILL.md
- ~/.claude/skills/document-superpowers/skills/executing-article-plan/SKILL.md
- ~/.claude/skills/document-superpowers/skills/reviewing-article/SKILL.md
- ~/.claude/skills/document-superpowers/skills/subagent-driven-writing/SKILL.md
```

### Cursor / Codebuddy (CLI)

```bash
# 克隆到 Cursor 全局技能目录
git clone https://github.com/binbinao/document-superpowers.git ~/.cursor/skills/document-superpowers

# 或克隆到项目级目录
git clone https://github.com/binbinao/document-superpowers.git .cursor/skills/document-superpowers
```

安装后在 Cursor 的 Rules 或 Agent Settings 中添加技能路径引用即可使用。

### Gemini CLI

```bash
# 克隆到 Gemini CLI 配置目录
git clone https://github.com/binbinao/document-superpowers.git ~/.gemini/skills/document-superpowers
```

在 `~/.gemini/GEMINI.md` 或项目根目录的 `GEMINI.md` 中引用技能：

```markdown
## Skills
- ~/.gemini/skills/document-superpowers/skills/brainstorming/SKILL.md
- ~/.gemini/skills/document-superpowers/skills/writing-article-plan/SKILL.md
- ~/.gemini/skills/document-superpowers/skills/executing-article-plan/SKILL.md
- ~/.gemini/skills/document-superpowers/skills/reviewing-article/SKILL.md
- ~/.gemini/skills/document-superpowers/skills/subagent-driven-writing/SKILL.md
```

### OpenClaw 平台

```bash
# 方式一：克隆到工作区技能目录
git clone https://github.com/binbinao/document-superpowers.git ~/.openclaw/skills/document-superpowers

# 方式二：通过 OpenClaw 技能管理器安装（如支持）
openclaw skills install document-superpowers
```

### 其他平台

根据你所使用平台的文档，将 `skills/` 目录复制到 AI 代理的技能文件夹中。

## 快速开始

### 1. 从一个想法开始

```
"我想写一篇关于 [主题] 的文章"
```

你的代理会自动调用头脑风暴技能并开始提问。

### 2. 回答问题

代理每次只问一个问题，逐步了解：
- 你的目标读者是谁？
- 核心信息是什么？
- 读者读完后应采取什么行动？
- 有什么约束条件（长度、语气、格式）？

### 3. 审阅简报

在充分了解你的主题后，代理会呈现一份简报，涵盖：
- 读者画像
- 目的与核心信息
- 关键论点
- 语气与风格

你可以批准或要求修改。

### 4. 获取计划

简报获批后，代理会创建详细大纲：
- 章节拆分及字数规划
- 每节的关键要点
- 所需论据支撑
- 章节间的过渡衔接

### 5. 选择执行模式

**分批执行**（默认）：
- 每次写 2-3 个章节
- 设置检查点供审阅
- 直到完成
- 适用于：结构清晰的文章、专注写作场景

**子代理驱动**（进阶）：
- 每节使用独立的子代理
- 两阶段审阅（规范 + 质量）
- 紧密的反馈循环
- 适用于：复杂文章、高要求内容

### 6. 审阅与润色

系统化的四轮审阅：
1. **逻辑** - 论证是否严密？
2. **论据** - 观点是否有支撑？
3. **流畅度** - 阅读是否顺畅？
4. **润色** - 语法、格式、风格

问题按严重程度分类（关键/中等/轻微）并系统化修正。

### 7. 发布

最终文章包含：
- 完整的审阅日志，记录所有修改
- 元数据（字数、阅读时长、目标读者）
- 可直接发布的格式

## 工作流示例

```
用户："我想写一篇博客文章，讲讲为什么工程师应该写文档"

代理：[调用头脑风暴]
"让我先了解你的想法。你的目标读者是谁——初级工程师、高级工程师，还是工程管理者？"

用户："讨厌写文档的高级工程师"

代理："明白了。你希望他们读完后做什么——开始写更好的文档、倡导文档文化，还是其他？"

用户："改变他们的看法，让他们认为文档是有价值的"

代理：[继续提问...]
代理：[呈现简报...]
代理：[获得批准...]
代理：[创建计划...]
代理：[提供执行模式选择...]

用户："分批执行"

代理：[撰写第 1-3 节...]
代理："检查点：第 1-3 节完成（612 词）。继续？"

用户："是"

代理：[撰写第 4-5 节...]
代理："初稿完成！准备好审阅了吗？"

用户："是"

代理：[运行四轮审阅...]
代理："审阅完成。发现并修复了 2 个关键问题。最终文章已就绪！"
```

## 项目文档

更多文档位于 `docs/` 目录下：

```
docs/
├── DEVELOPMENT.md                      # 开发概述与架构详解
├── SUMMARY.md                          # 实现总结与项目统计
└── examples/
    └── typescript-blog-post.md         # 完整的端到端写作示例
```

| 文档 | 说明 |
|---|---|
| [DEVELOPMENT.md](docs/DEVELOPMENT.md) | 深入的开发指南，涵盖项目架构、技能设计、工作流细节和扩展点 |
| [SUMMARY.md](docs/SUMMARY.md) | 实现总结，包含项目统计数据、文件清单和功能亮点 |
| [typescript-blog-post.md](docs/examples/typescript-blog-post.md) | 完整示例：从头脑风暴到最终审阅，完成一篇 TypeScript 博客文章 |

## 写作项目文件结构

在写作项目中，工作流会生成以下文件：

```
docs/writing/
├── YYYY-MM-DD-主题-brief.md          # 已批准的主题简报
├── YYYY-MM-DD-主题-plan.md           # 详细大纲
├── drafts/
│   └── YYYY-MM-DD-主题/
│       ├── section-1-intro.md         # 各章节草稿
│       ├── section-2-argument.md
│       └── ...
├── YYYY-MM-DD-主题-draft.md          # 合并后的完整草稿
├── YYYY-MM-DD-主题-review.md         # 审阅日志
└── YYYY-MM-DD-主题-final.md          # 发布版本
```

所有内容都有版本控制和可追溯性。

## 与代码 Superpowers 的对比

| 代码（superpowers） | 内容（document-superpowers） |
|---|---|
| 头脑风暴 → 设计文档 | 头脑风暴 → 主题简报 |
| 编写计划 → 实现方案 | 文章规划 → 文章大纲 |
| 执行计划 → 代码 | 执行文章计划 → 草稿 |
| 请求代码审阅 | 审阅文章 |
| TDD（红-绿-重构） | 写作-检查-修订 |
| Git 工作树 | 章节草稿 |
| 每个任务一个子代理 | 每个章节一个子代理 |

## 核心原则

### 1. 禁止"直接写"

每篇文章都要走完整流程，即使是"简单"的博客文章。简单主题可以有简短的简报（几句话即可），但**必须**在写作前呈现并获得简报批准。

### 2. 一次一个问题

代理不会用一堆问题轰炸你。头脑风暴是一场对话，不是一张需要填写的表格。

### 3. 小而精的章节

每节 150-400 词——小到可以一次写完（15-30 分钟），大到足以展开一个观点。

### 4. 检查点，而非马拉松

每写完 2-3 个章节就审阅一次。及早发现问题，而不是在 3000 词的长文中才发现问题。

### 5. 四轮审阅

每轮专注一个维度：
- 逻辑（是否严密？）
- 论据（是否有支撑？）
- 流畅度（是否顺畅？）
- 润色（是否整洁？）

混合关注点会让问题更难发现。

### 6. 记录一切

每个阶段都会产出文档：
- 简报（主题理解）
- 计划（写作蓝图）
- 章节草稿（增量进展）
- 审阅日志（所有问题和修正）
- 最终文章（可发布版本）

## 成功秘诀

### 对写作者

**相信流程** - 一开始可能感觉更慢，但比反复重写更快地产出更好的结果。

**在头脑风暴中尽量具体** - 你的回答越清晰，简报就越好。

**认真审阅检查点** - 不要草率通过。真正阅读每个章节。

**保存审阅日志** - 它是你写作决策的宝贵记录。

### 对 AI 代理

**严格执行关卡** - 即使是"简单"的文章也不要跳过头脑风暴。

**提出更好的问题** - 能用选择题就不用开放式问题。

**严格自检** - 在人工审阅之前先发现自己的问题。

**保留有效内容** - 审阅时不要过度编辑。修复问题，保留优点。

## 进阶用法

### 自定义模板

为特定文档类型创建模板：

```
skills/brainstorming/templates/
├── blog-post.md
├── technical-guide.md
├── api-documentation.md
└── research-paper.md
```

### 风格指南

添加组织特定的风格指南：

```
skills/reviewing-article/style-guides/
├── ap-style.md
├── company-voice.md
└── technical-writing.md
```

### 集成

与其他技能配合使用：
- **调研技能** - 在规划阶段收集论据
- **SEO 技能** - 在审阅阶段进行优化
- **发布技能** - 定稿后进行部署

## 贡献

技能直接存放在本仓库中。如需贡献：

1. Fork 本仓库
2. 为你的改进创建一个分支
3. 遵循现有的技能结构（参考 obra/superpowers 中的 `skills/writing-skills/`）
4. 在真实写作项目中测试
5. 提交 PR

## 常见问题排查

**代理跳过了头脑风暴：**
- 检查技能描述是否正确注册
- 确保 SKILL.md 中包含 HARD-GATE 指令

**章节过长/过短：**
- 在计划中调整字数目标
- 审视关键要点是否需要更多/更少的展开

**审阅没有发现问题：**
- 这可能意味着审阅不够深入
- 尝试提供具体的审阅关注点

**子代理反复失败：**
- 计划可能不够清晰——修改规范
- 任务简报可能需要更多上下文
- 考虑切换到分批执行模式

## 许可证

MIT 许可证 - 详见 LICENSE 文件

## 灵感来源

本项目深受 Jesse Vincent 的 [obra/superpowers](https://github.com/obra/superpowers) 启发。代码开发中系统化、关卡驱动的方法论完美适用于内容创作。

## 支持

- Issues: [GitHub Issues](https://github.com/binbinao/document-superpowers/issues)
- 讨论区: [GitHub Discussions](https://github.com/binbinao/document-superpowers/discussions)

---

**祝写作愉快！📝**

# Document Superpowers - 开发概述

## 1. 项目简介

**Document Superpowers** 是一套面向 AI 写作代理的结构化文档写作工作流技能框架，灵感来自 [obra/superpowers](https://github.com/obra/superpowers) 的代码开发方法论。

项目将 AI 从"随意写作"工具转变为系统化写作伙伴，通过强制执行四阶段流程，产出结构清晰、论据充分、可发布级别的文章、博客和技术文档。

**仓库地址：** `git@github.com:binbinao/document-superpowers.git`

**项目类型：** 纯文档型 AI Agent 技能框架（无代码逻辑、无构建系统）

---

## 2. 核心架构

### 2.1 四阶段写作流水线

```
💡 头脑风暴 (Brainstorming) → 📋 规划 (Planning) → ✍️ 执行 (Execution) → 🔍 审阅 (Review)
```

每个阶段由独立的技能模块（SKILL.md）驱动，并设有严格的阶段门禁（Gate），前一阶段未完成且未获用户批准，不能进入下一阶段。

### 2.2 技能模块总览

| 阶段 | 技能模块 | 路径 | 职责 |
|------|---------|------|------|
| 1. 头脑风暴 | `brainstorming` | `skills/brainstorming/SKILL.md` | 苏格拉底式提问，明确受众/目的/核心信息，产出 Topic Brief |
| 2. 规划 | `writing-article-plan` | `skills/writing-article-plan/SKILL.md` | 逐节拆分大纲，确定字数/要点/证据/过渡 |
| 3a. 执行（批量） | `executing-article-plan` | `skills/executing-article-plan/SKILL.md` | 按批次（2-3 节）写作，带人工检查点 |
| 3b. 执行（子代理） | `subagent-driven-writing` | `skills/subagent-driven-writing/SKILL.md` | 每节生成独立子代理，两阶段审查（规格+质量） |
| 4. 审阅 | `reviewing-article` | `skills/reviewing-article/SKILL.md` | 四轮审阅：逻辑 → 证据 → 流畅度 → 润色 |

### 2.3 技能调用链

```
SKILL.md（入口）
  └─→ brainstorming/SKILL.md
        └─→ writing-article-plan/SKILL.md
              ├─→ executing-article-plan/SKILL.md（批量模式）
              └─→ subagent-driven-writing/SKILL.md（子代理模式）
                    └─→ reviewing-article/SKILL.md
```

---

## 3. 项目结构

```
document-superpowers/
├── README.md                              # 完整的用户文档（安装、使用、哲学、故障排除）
├── SKILL.md                               # 技能入口点（触发条件、四阶段概览、反模式）
├── SUMMARY.md                             # 实现总结（统计、设计原则、后续计划）
├── DEVELOPMENT.md                         # 本文件 - 开发概述
├── examples/
│   └── typescript-blog-post.md            # 完整的四阶段写作示例
└── skills/
    ├── brainstorming/
    │   └── SKILL.md                       # 阶段 1：话题探索与摘要生成
    ├── writing-article-plan/
    │   └── SKILL.md                       # 阶段 2：详细大纲规划
    ├── executing-article-plan/
    │   └── SKILL.md                       # 阶段 3a：批量执行模式
    ├── subagent-driven-writing/
    │   └── SKILL.md                       # 阶段 3b：子代理驱动模式
    └── reviewing-article/
        └── SKILL.md                       # 阶段 4：多轮系统审阅
```

### 文件统计

| 文件 | 行数 | 大小 |
|------|------|------|
| `examples/typescript-blog-post.md` | 632 | 15.7 KB |
| `skills/reviewing-article/SKILL.md` | 382 | 9.3 KB |
| `README.md` | 336 | 10.3 KB |
| `skills/subagent-driven-writing/SKILL.md` | 276 | 7.8 KB |
| `SKILL.md` | 273 | 8.0 KB |
| `SUMMARY.md` | 263 | — |
| `skills/writing-article-plan/SKILL.md` | 214 | 5.6 KB |
| `skills/executing-article-plan/SKILL.md` | 201 | 5.3 KB |
| `skills/brainstorming/SKILL.md` | 137 | 5.4 KB |
| **总计** | **~2,714** | — |

---

## 4. 技术栈与依赖

| 维度 | 详情 |
|------|------|
| **语言** | 纯 Markdown |
| **构建工具** | 无 |
| **依赖管理** | 无（无 package.json / requirements.txt） |
| **测试框架** | 无（通过真实写作项目手动验证） |
| **CI/CD** | 无 |
| **版本控制** | Git（2 次提交，单一 `main` 分支） |
| **许可证** | MIT（README 中提及，尚未创建 LICENSE 文件） |
| **目标平台** | OpenClaw、Cursor、Claude Code 等 AI Agent 技能平台 |

### 技能文件格式

每个 SKILL.md 采用统一结构：

- **YAML Frontmatter**：定义 `name`（技能名称）和 `description`（触发描述）
- **Markdown 正文**：流程说明、检查清单、模板
- **DOT 语法流程图**：可视化阶段流转逻辑

---

## 5. 核心设计原则

### 5.1 HARD-GATE 门禁机制

头脑风暴阶段设有硬性门禁标记 `<HARD-GATE>`，强制要求：
- 不可跳过头脑风暴，即使"简单"文章也必须产出并获批 Brief
- 前一阶段未完成，不能进入下一阶段

### 5.2 一次一问

头脑风暴阶段每条消息只问一个问题，优先使用选择题，避免信息过载。

### 5.3 小节写作

每个写作小节控制在 150-400 字，既能充分展开一个论点，又可在 15-30 分钟内完成。

### 5.4 检查点机制

批量执行模式下每 2-3 个小节设人工检查点，子代理模式下每节两阶段审查（规格合规 + 内容质量）。

### 5.5 四轮分离式审阅

审阅阶段将关注点分离为四次独立扫描：

| 轮次 | 关注点 | 核心问题 |
|------|--------|---------|
| Pass 1 | 逻辑 (Logic) | 论证是否连贯？有无逻辑谬误？ |
| Pass 2 | 证据 (Evidence) | 每个论点是否有数据/引用支撑？ |
| Pass 3 | 流畅度 (Flow) | 段落过渡是否自然？节奏是否合适？ |
| Pass 4 | 润色 (Polish) | 语法、格式、风格是否一致？ |

问题按严重程度分级：**Critical**（阻断发布）→ **Moderate**（影响质量）→ **Minor**（可选修复）。

### 5.6 全过程文档化

每个阶段产出可追溯的工件文件：

| 阶段产出 | 文件路径 |
|----------|---------|
| 话题摘要 | `docs/writing/YYYY-MM-DD-<topic>-brief.md` |
| 写作计划 | `docs/writing/YYYY-MM-DD-<topic>-plan.md` |
| 分节草稿 | `docs/writing/drafts/YYYY-MM-DD-<topic>/section-N-*.md` |
| 合并草稿 | `docs/writing/YYYY-MM-DD-<topic>-draft.md` |
| 审阅日志 | `docs/writing/YYYY-MM-DD-<topic>-review.md` |
| 最终成稿 | `docs/writing/YYYY-MM-DD-<topic>-final.md` |

---

## 6. 两种执行模式对比

| 维度 | 批量执行 (Batch) | 子代理驱动 (Subagent) |
|------|-----------------|---------------------|
| 粒度 | 每批 2-3 节 | 每节独立子代理 |
| 审查频率 | 批次结束后人工检查 | 每节两阶段审查 |
| 反馈循环 | 较长 | 紧密 |
| 适用场景 | 简单直接的文章 | 复杂/高风险内容 |
| 开销 | 较低 | 较高（频繁生成子代理） |
| 优势 | 连贯写作，减少中断 | 新鲜视角，易于纠偏 |

---

## 7. 与 obra/superpowers 的映射关系

本项目将代码开发中的工程方法论适配到文档写作领域：

| 代码开发 (superpowers) | 文档写作 (document-superpowers) |
|----------------------|-------------------------------|
| brainstorming → 设计文档 | brainstorming → 话题摘要 (Brief) |
| writing-plans → 实现计划 | writing-article-plan → 文章大纲 |
| executing-plans → 编码 | executing-article-plan → 草稿写作 |
| requesting-code-review → 代码审查 | reviewing-article → 文章审阅 |
| TDD（红-绿-重构）| 写作-自检-修订 |
| Git worktrees | 分节草稿目录 |
| 每任务子代理 | 每节子代理 |

---

## 8. 安装与使用

### 安装方式

```bash
# OpenClaw 平台
git clone git@github.com:binbinao/document-superpowers.git ~/.openclaw/skills/document-superpowers

# Cursor / 其他平台
# 将 skills/ 目录复制到对应的 AI Agent 技能目录
```

### 触发方式

用户向 AI Agent 发出写作意图即可自动触发：

- "Write a blog post about..."
- "I want to write about..."
- "Help me write an article..."
- "I need to create documentation for..."

### 快速流程

1. 用户提出写作主题
2. Agent 自动调用 `brainstorming` 技能，逐一提问
3. 用户确认 Brief 后，Agent 生成写作计划
4. 用户选择执行模式（批量 / 子代理），Agent 逐节写作
5. 草稿完成后自动进入四轮审阅
6. 产出可发布的最终成稿

---

## 9. Git 历史

| 提交 | 消息 |
|------|------|
| `27b0081` | `feat: initial implementation of document-superpowers` |
| `4684624` | `docs: add implementation summary` |

- **分支：** `main`（唯一分支）
- **远程仓库：** `origin` → `git@github.com:binbinao/document-superpowers.git`

---

## 10. 后续演进计划

### Phase 2（可选增强）

- [ ] 文档类型模板（博客 / 技术指南 / 报告 / 学术论文）
- [ ] 组织风格指南集成（AP / 企业特定风格）
- [ ] SEO 优化审阅轮次
- [ ] 导出格式化器（Medium / WordPress / 多种 Markdown 变体）
- [ ] 社交媒体摘要生成器
- [ ] 研究技能集成
- [ ] 多作者协作模式

### Phase 3（高级功能）

- [ ] 引用管理集成
- [ ] 查重检测
- [ ] 可读性评分（Flesch-Kincaid）
- [ ] 标题 A/B 测试
- [ ] 发布工作流集成
- [ ] 分析指标集成
- [ ] 版本对比工具

---

## 11. 已知事项与注意点

| 事项 | 说明 |
|------|------|
| LICENSE 文件缺失 | README 提及 MIT 许可，但仓库中尚无 LICENSE 文件 |
| .gitignore 缺失 | 建议添加以排除不必要的文件 |
| 无自动化测试 | 项目为纯文档，通过真实写作任务手动验证 |
| 安装链接占位符 | README 中 GitHub URL 仍使用 `[your-username]` 占位符 |

---

*文档生成日期：2026-03-02*

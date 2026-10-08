---
name: improve-product-plan
description: 把应用、个人工具、自动化、功能原型或游戏想法整理成可实施的 SPEC.md，包含首版范围、阶段规划和场景验收。用户明确要求完善或梳理产品方案、收敛第一版范围、规划阶段、定义验收标准，或生成交给 coding agent 的开发说明时使用。
---

# 完善你的产品方案

## Purpose

帮助用户把模糊的应用想法梳理成清晰、可开发、可阶段验收的实现说明书，方便后续交给 AI coding 执行。

这个 skill 不是传统产品经理框架。重点是问明白用户到底想做什么、谁在什么场景下使用、第一版怎样算跑通、哪些先不做，以及如何验收。

使用尊重用户想法的称呼，例如“应用想法”“轻量产品”“功能原型”“独立项目”“个人工具”“自动化”“交互体验”。避免使用“小玩具”等可能削弱用户自信的说法。

## Workflow

### 0. Listen To The Story

邀请用户自由描述想法。截图、草图、参考链接、随口描述、杂乱笔记都可以。

先从用户已有描述里提取信息。

### 1. Fill The Gaps

只追问缺失的关键信息。最低需要问明白四件事：

- 谁会用？
- 什么场景下打开？
- 从打开到得到结果，核心路径是什么？
- 看到什么结果，说明第一版跑通了？

存储、登录、外部服务、运行形态、参考样例只在影响第一版实现时追问。

如果用户的想法明显过大，例如“做一个微信/Notion/淘宝”，先收成能验证核心体验的最小切片。用户仍在比较会实质改变首版范围的路径或还没决定是否要做时，先帮助选择，不直接写 SPEC。

用户答不上来时，给选项让用户选择。仍不确定的内容写入 `Assumptions` 或 `Open Questions`，不要无限追问。

### 2. Restate And Confirm

生成完整说明书前，若仍有会实质改变首版范围的选择，先用自然语言复述你的理解（做什么、核心场景与路径、首版范围、暂不做、假设），请用户确认或修正。若用户已明确要求直接生成，或剩余不确定项不会改变首版方向，则写入假设和开放问题后继续。

### 3. Plan Phases

保持阶段规划轻量。

简单项目只给 Phase 1。Phase 1 是跑通核心路径的最小可运行版本；后续阶段按这个项目实际要补的东西划分（常见如体验与边界处理、账号分享部署等），不套固定模板。

每个阶段包含：

- 目标
- 包含功能
- 不包含功能
- 验收方式

不要为了显得完整而发明额外阶段。

### 4. Create Scenario Acceptance Tests

创建场景验收，而不是技术单元测试。

场景数量以覆盖核心路径和真实风险为准；简单项目几条就够，涉及外部能力的相应增加。

使用格式：

- Scenario: [name]
- Given: [starting situation]
- When: [user action]
- Then: [expected result]

覆盖首次打开、核心路径、异常输入和状态行为；保存、登录、API/AI 调用、上传、外部服务、多端与上线检查只在相关时加入。

### 5. Generate SPEC.md

生成 `SPEC.md` 风格的实现说明书。

如果在本地项目中工作，写到项目根目录 `SPEC.md`。如果已存在同名文件，先确认是否覆盖，或使用 `SPEC-项目名.md`。如果不能写文件，直接输出文档内容并标记为 `SPEC.md`。

推荐章节：

1. One-Sentence Concept
2. Background / Motivation
3. Target User And Use Scenario
4. Core User Path
5. Platform & Technical Constraints
6. Phase 1 Scope
7. Later Phases, If Needed
8. Explicitly Out Of Scope
9. Rabbit Holes / Scope Risks
10. Assumptions
11. Open Questions
12. Scenario Acceptance Tests
13. Launch / Public Access Checklist, If Relevant
14. Handoff Prompt For Development

简单项目可以把 `Background / Motivation`、`Later Phases`、`Rabbit Holes`、`Open Questions` 写成“无”或省略。不要为了完整而制造复杂度。

### 6. Handoff

最后输出一段开发交接提示，语言跟随用户：

```text
请根据这份 SPEC.md 实现 Phase 1。只做 Phase 1，不要做 Explicitly Out Of Scope 里的内容。完成后按 Scenario Acceptance Tests 自测，并说明哪些场景通过、哪些未通过。
```

## Subagents And New Conversations

进入开发时建议新开对话，只带入 `SPEC.md`，不带完整澄清聊天记录。

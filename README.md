# 完善你的产品方案

一个给 Claude Code / Codex 等 AI Agent 使用的 Skill：帮助用户把模糊的应用想法、轻量产品、功能原型、个人工具或 AI coding 项目，梳理成清晰、可开发、可验收的 `SPEC.md`。

它不是传统产品经理框架，不默认追问 KPI、商业价值、市场规模或复杂上线治理。它专注于把用户脑子里的想法问明白：谁会用、什么场景下用、第一版先跑通什么、哪些先不做，以及上线前用什么场景验收。

## 适合什么情况

- 你有一个应用想法，但还没讲清楚需求
- 你想用 AI coding 做一个个人工具、自动化、功能原型或交互体验
- 你希望先生成一份能交给 coding agent 执行的 `SPEC.md`
- 你需要把第一版范围、后续阶段和验收场景先定下来

## 它会产出什么

- 项目一句话定义
- 目标用户和使用场景
- 核心路径
- Phase 1 最小可运行范围
- 后续阶段建议
- 明确不做的内容
- 容易失控的范围风险
- 假设和开放问题
- 场景验收测试
- 开发交接提示

## 安装

### Claude Code

```bash
git clone https://github.com/ruodou233/improve-product-plan.git ~/.claude/skills/improve-product-plan
```

### Codex / 其他 Agent

克隆到对应的 skills 目录，或在 prompt 中引用 `SKILL.md` 全文即可。

## 使用

对你的 Agent 说：

```text
帮我完善这个产品方案：我想做一个……
```

或者：

```text
帮我把这个应用想法梳理成 SPEC.md。
```

## 反馈与作者

这个 skill 我长期维护。如果你有修改方案、发现问题、或者改出了更好的版本，欢迎通过以下任一渠道找到我：

- GitHub：本仓库提 issue 或 PR
- 小红书：错误乱码
- 微信公众号：能工智人错误乱码
- B站：若逗道人

## 相关 Skill 推荐

<!-- 本表由维护脚本生成，勿手工编辑 -->
- [wisdom-roundtable](https://github.com/ruodou233/wisdom-roundtable)：智慧圆桌：11 位思想家并行独立分析你的决策
- [domain-explorer](https://github.com/ruodou233/domain-explorer)：速通新领域：四线并行调研，产出交互式知识地图
- [de-ai-taste](https://github.com/ruodou233/de-ai-taste)：中文去 AI 味：逐条检测 AI 生成痕迹并给修改建议

完整目录见 [GitHub 主页](https://github.com/ruodou233)。

## License

MIT

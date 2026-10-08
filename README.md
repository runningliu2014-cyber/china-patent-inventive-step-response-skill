# 中国专利创造性答辩 Skill

**China Patent Inventive Step Response Skill**

从项目 AGENTS.md 提炼的独立工作规范 Skill，用于中国专利创造性审查意见分析、答复方案设计、正式意见陈述、驳回复盘和复审前分析。

## 内容范围

- 按任务范围选择工作流或专项 Skill。
- 区分事实核查、创造性分析、答复方案、权利要求修改、法律写作及保守校对。
- 保留证据定位、待核实事项、保护范围和修改依据等约束。
- 采用审慎、准确的正式法律表达，遵循明确的表达偏好。
- 可选外部核查按用户明确要求启用，并保留外发授权边界。

本仓库仅打包 AGENTS.md 中的工作约定，不包含案件材料、账号凭据、原项目历史或配套专项 Skill 的实体判断规则。与 `patent-response-workflow` 独立维护。

## 目录

```text
china-patent-inventive-step-response/
├─ SKILL.md
└─ agents/
   └─ openai.yaml
```

## 使用

将 `china-patent-inventive-step-response` 文件夹放入目标工具支持的 Skill 目录，以 `$china-patent-inventive-step-response` 调用。Skill 保持默认自动匹配。原项目继续以 `.opencode/skills` 为内容源；原项目中不要创建 `.agents/skills`。

此包可以独立提供共同工作规范。需要完整的实体判断流程时，应同时提供其中列出的配套工作流和专项 Skill；缺少依赖时说明缺项及影响，不声称已执行缺失模块。DeepSeek 核查另需配套入口、工具及本次任务的用户授权。

## 版本

初始版本：2026-10-08。

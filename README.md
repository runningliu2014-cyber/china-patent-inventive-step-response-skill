# 中国专利创造性答辩 Skill

**China Patent Inventive Step Response Skill**

本仓库提供从项目 AGENTS.md 提炼的工作规范，以及配套的创造性答辩工作流、10 个专项 Skill 和旧名称兼容入口。用于中国专利创造性审查意见分析、答复方案设计、正式意见陈述、驳回复盘和复审前分析。

与 `patent-response-workflow` 独立维护；不包含案件材料、账号凭据或原项目历史。

## 模块

| Skill | 用途 |
|---|---|
| [china-patent-inventive-step-response](china-patent-inventive-step-response/SKILL.md) | 工作规范与共同约束 |
| [inventive-step-answer-workflow](inventive-step-answer-workflow/SKILL.md) | 完整创造性答辩工作流 |
| [office-action-analysis](office-action-analysis/SKILL.md) | 审查意见论证链 |
| [closest-prior-art](closest-prior-art/SKILL.md) | 最接近现有技术 |
| [distinguishing-features](distinguishing-features/SKILL.md) | 区别特征、技术效果与技术问题 |
| [obviousness-assessment](obviousness-assessment/SKILL.md) | 技术启示与显而易见性 |
| [secondary-considerations](secondary-considerations/SKILL.md) | 其他创造性因素 |
| [challenge-examiner-reasoning](challenge-examiner-reasoning/SKILL.md) | 答复论点组织 |
| [claim-amendment-strategies](claim-amendment-strategies/SKILL.md) | 权利要求修改 |
| [legal-writing-style](legal-writing-style/SKILL.md) | 正式法律写作 |
| [patent-prose-polish](patent-prose-polish/SKILL.md) | 成稿保守校对 |
| [biotech-inventive-step](biotech-inventive-step/SKILL.md) | 生物技术专题 |
| [inventive-step-overview](inventive-step-overview/SKILL.md) | 旧名称兼容入口 |

工作流参考和生物技术专题参考随各模块提供，按当前任务读取。

## 使用

下载并解压根目录的 `china-patent-inventive-step-response-skill.zip`，将其中的 13 个同名 Skill 文件夹作为同级目录放入目标工具支持的 Skill 目录；也可以直接从本仓库复制这些文件夹。保留各模块内部的 `references` 和 `agents` 目录。

从 `$china-patent-inventive-step-response` 进入共同工作规范；完整案件使用 `$inventive-step-answer-workflow`，单一问题按路由直接使用专项 Skill。

原项目继续以 `.opencode/skills` 为内容源，原项目中不要创建 `.agents/skills`。移植到其他环境时，按该环境的发现机制选择安装位置。普通案件任务不一次加载全部模块。

DeepSeek 核查属于可选功能，只在用户明确要求时启用；工具实现、密钥、核查使用说明及核查任务目标须由目标环境另行配置，本仓库保留操作规范和外发授权边界。

## 版本

2026-10-08：在工作规范入口基础上补齐配套工作流、10 个专项模块、兼容入口与必要参考。

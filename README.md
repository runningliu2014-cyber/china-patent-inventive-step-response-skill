# 中国专利创造性答辩 Skill

**China Patent Inventive Step Response Skill**

用于中国专利创造性审查意见分析、答复方案设计、正式意见陈述、驳回复盘和复审前分析。以一个主 Skill 作为统一入口，按任务引用包内的工作流和专项子 Skill。

与 `patent-response-workflow` 独立维护，不包含案件材料、账号凭据或原项目历史。

## 结构

```text
china-patent-inventive-step-response/
├── SKILL.md                 主入口：任务路由、共同约束、表达偏好
├── agents/openai.yaml       主入口的展示信息
└── subskills/
    ├── inventive-step-answer-workflow/  完整答复流程与参考
    ├── office-action-analysis/          审查意见分析
    ├── closest-prior-art/               最接近现有技术
    ├── distinguishing-features/         区别特征、效果与问题
    ├── obviousness-assessment/          显而易见性
    ├── secondary-considerations/        其他因素
    ├── challenge-examiner-reasoning/     答复论点
    ├── claim-amendment-strategies/       权利要求修改
    ├── legal-writing-style/             正式法律写作
    ├── patent-prose-polish/              成稿校对
    ├── biotech-inventive-step/           生物技术专题与参考
    └── inventive-step-overview/          旧名称路由参考
```

主入口：[SKILL.md](china-patent-inventive-step-response/SKILL.md)。子 Skill 保留各自指引和必要参考，通过相对路径按需读取。

## 使用

下载并解压 [完整安装包](china-patent-inventive-step-response-skill.zip)，将其中一个 `china-patent-inventive-step-response/` 文件夹整体放入目标工具支持的 Skill 目录，也可以直接复制仓库中这个文件夹。保留内部 `subskills/`、`references/` 和 `agents/` 层级。

使用 `$china-patent-inventive-step-response` 进入主 Skill。主入口根据当前目标读取完整工作流或专项子 Skill，无需把内部子 Skill 拆开安装。普通案件任务只加载本次所需模块。

原项目继续以 `.opencode/skills` 为内容源，原项目中不要创建 `.agents/skills`。移植到其他环境时，按该环境的发现机制选择安装位置。

DeepSeek 核查仅在用户明确要求时启用；工具实现及授权凭据由目标环境另行配置。本包保留核查操作规范和外发授权边界。

## 子 Skill

| 子 Skill | 用途 |
|---|---|
| [inventive-step-answer-workflow](china-patent-inventive-step-response/subskills/inventive-step-answer-workflow/SKILL.md) | 完整答复工作流 |
| [office-action-analysis](china-patent-inventive-step-response/subskills/office-action-analysis/SKILL.md) | 审查意见论证链 |
| [closest-prior-art](china-patent-inventive-step-response/subskills/closest-prior-art/SKILL.md) | 最接近现有技术 |
| [distinguishing-features](china-patent-inventive-step-response/subskills/distinguishing-features/SKILL.md) | 区别特征、技术效果与技术问题 |
| [obviousness-assessment](china-patent-inventive-step-response/subskills/obviousness-assessment/SKILL.md) | 技术启示与显而易见性 |
| [secondary-considerations](china-patent-inventive-step-response/subskills/secondary-considerations/SKILL.md) | 其他创造性因素 |
| [challenge-examiner-reasoning](china-patent-inventive-step-response/subskills/challenge-examiner-reasoning/SKILL.md) | 答复论点组织 |
| [claim-amendment-strategies](china-patent-inventive-step-response/subskills/claim-amendment-strategies/SKILL.md) | 权利要求修改 |
| [legal-writing-style](china-patent-inventive-step-response/subskills/legal-writing-style/SKILL.md) | 正式法律写作 |
| [patent-prose-polish](china-patent-inventive-step-response/subskills/patent-prose-polish/SKILL.md) | 成稿保守校对 |
| [biotech-inventive-step](china-patent-inventive-step-response/subskills/biotech-inventive-step/SKILL.md) | 生物技术专题 |
| [inventive-step-overview](china-patent-inventive-step-response/subskills/inventive-step-overview/SKILL.md) | 旧名称路由参考 |

# 中国专利创造性答辩 Skill

*China Patent Inventive Step Response Skill*

面向中国发明专利的创造性审查意见答复，支持从材料核查、争点分析、答复方案到正式意见陈述与成稿校对的完整过程。

**安装一个主 Skill，即可按任务使用包内的工作流和专项子 Skill。**

[快速开始](#快速开始) · [工作流程](#工作流程) · [模块索引](#模块索引) · [可选外部核查](#可选外部核查)

## 能帮你做什么

- **分析审查意见**：梳理审查员的论证链，核查最接近现有技术、区别特征、技术效果、实际技术问题及技术启示。
- **设计答复方案**：组织有证据支持的论点，比较权利要求修改路径，说明原始依据、保护范围影响和方案风险。
- **起草与校对**：将已核实的分析写成正式意见陈述和修改说明，检查表达、引用及前后一致性。
- **处理后续或专题任务**：支持后续审查意见、驳回复盘、复审前分析，以及生物技术主题的专项判断。

## 快速开始

### 1. 安装

**由 Codex agent 安装**

将下面的请求发送给 Codex：

```text
请使用 $skill-installer 安装这个 Skill：
https://github.com/runningliu2014-cyber/china-patent-inventive-step-response-skill/tree/main/china-patent-inventive-step-response

请整体安装该目录，保留内部子 Skill 和参考文件。
```

安装环境需要能够访问仓库；私有仓库还需要相应的 GitHub 访问权限。

**手动安装**

下载 [完整安装包](china-patent-inventive-step-response-skill.zip)，解压后，将 `china-patent-inventive-step-response/` 文件夹整体放入目标工具支持的 Skill 目录。保留内部目录层级，所有子 Skill 会随主入口一起安装。

### 2. 准备材料

完整案件分析通常需要：

- 审查意见正文及附件；
- 当前有效权利要求、原始说明书与附图；
- 审查员引用的对比文件；后续答复还应提供前次答复及修改文本。

可以注明本次目标，例如“只分析争点”“比较修改方案”“起草意见陈述”或“校对已有成稿”。材料缺失时，Skill 会列明待核实事项，继续处理能够独立完成的部分。

### 3. 开始使用

在 Codex 中使用 `$china-patent-inventive-step-response`，并说明本次任务。

**完整分析示例**

```text
使用 $china-patent-inventive-step-response，根据所附审查意见、
当前权利要求、原始申请文件和对比文件，分析创造性争点，
提出答复方案，并列出需要核实的事项。
```

**成稿校对示例**

```text
使用 $china-patent-inventive-step-response，校对这份意见陈述书，
保留权利要求、事实、引文、证据位置和结论强度，
另列发现的实体疑问。
```

主入口会根据任务读取所需子 Skill；完整分析、单一争点和局部校对各按相应范围执行。

## 工作流程

```text
材料与证据核查 → 创造性分析 → 答复方案 → 正式写作 → 保守校对
                                │
                                └─ 涉及权利要求修改时，复核修改后的创造性
```

只要求分析或建议时，交付结论、依据、风险和方案。需要正式成稿时，再进入写作与校对。

整个过程遵循以下原则：

- **事实可核查**：关键判断定位到申请文件、审查意见或对比文件；区分文件记载、技术推断和待核实事项。
- **评价整体方案**：以当前权利要求限定的技术方案为对象，分析特征之间的关系及其技术贡献。
- **修改有依据**：逐项检查原始依据、保护范围影响、从属关系及超范围风险。
- **成稿保持准确**：采用正式、审慎的法律表达；校对保留事实、术语、证据和结论强度。
- **外发须获授权**：向外部系统发送材料或提交文件，需要用户授权。

## 模块索引

主入口：[中国专利创造性答辩](china-patent-inventive-step-response/SKILL.md)。它负责共同约束、任务路由和表达要求。

| 子 Skill | 负责的任务 |
|---|---|
| [完整答复工作流](china-patent-inventive-step-response/subskills/inventive-step-answer-workflow/SKILL.md) | 衔接材料核查、分析、方案、成稿和交付 |
| [审查意见分析](china-patent-inventive-step-response/subskills/office-action-analysis/SKILL.md) | 复原审查员论证链，标记待核查环节 |
| [最接近现有技术](china-patent-inventive-step-response/subskills/closest-prior-art/SKILL.md) | 评价 D1 是否适合作为分析起点 |
| [区别特征与技术问题](china-patent-inventive-step-response/subskills/distinguishing-features/SKILL.md) | 建立区别特征、效果与实际技术问题的推导 |
| [技术启示与显而易见性](china-patent-inventive-step-response/subskills/obviousness-assessment/SKILL.md) | 核查结合动机、相容性与合理成功预期 |
| [其他创造性因素](china-patent-inventive-step-response/subskills/secondary-considerations/SKILL.md) | 评价预料不到效果、技术偏见等辅助因素 |
| [答复论点组织](china-patent-inventive-step-response/subskills/challenge-examiner-reasoning/SKILL.md) | 从已核实分析中选择并组织答复论点 |
| [权利要求修改](china-patent-inventive-step-response/subskills/claim-amendment-strategies/SKILL.md) | 设计修改方案，核查依据、范围与风险 |
| [正式法律写作](china-patent-inventive-step-response/subskills/legal-writing-style/SKILL.md) | 起草意见陈述和修改说明 |
| [成稿保守校对](china-patent-inventive-step-response/subskills/patent-prose-polish/SKILL.md) | 核对表达与一致性，保留实体含义 |
| [生物技术专题](china-patent-inventive-step-response/subskills/biotech-inventive-step/SKILL.md) | 在通用分析上叠加生物技术判断规则 |

包内另保留 [旧名称兼容索引](china-patent-inventive-step-response/subskills/inventive-step-overview/SKILL.md)，供已有调用迁移参考。

### 目录结构

```text
china-patent-inventive-step-response/
├── SKILL.md            统一入口与共同约束
├── agents/             主入口的展示信息
└── subskills/          工作流及专项子 Skill
    └── 各模块目录/
        ├── SKILL.md    模块指引
        └── references/ 按需提供的参考文件
```

## 可选外部核查

需要 DeepSeek 核查时，用户应明确提出，并由目标环境配置可用工具和授权凭据。启用后按 [可选核查说明](china-patent-inventive-step-response/subskills/inventive-step-answer-workflow/references/09-可选DeepSeek核查.md) 处理指定材料；普通分析、写作与校对使用主流程。

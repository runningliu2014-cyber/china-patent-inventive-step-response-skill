---
name: china-patent-inventive-step-response
description: "Apply China patent inventive-step response guidelines when analyzing an office action, designing a response, drafting formal arguments, or reviewing an existing response; includes task routing, evidence constraints, amendment review, and writing preferences."
---

# 中国专利创造性答辩

## Skill 入口与维护

本 Skill 提供中国专利创造性答辩的工作规范，适用于审查意见分析、答复方案设计、正式成稿、驳回复盘及复审前分析。内容来源于项目 AGENTS.md，覆盖任务路由、阶段衔接、表达偏好及共同约束。

本 Skill 是整包的统一入口。工作流及专项子 Skill 随包保存在 `subskills/` 中，通过下面的相对路径读取，不依赖目标环境单独发现或注册子 Skill。先读取本入口，再完整读取本次选中的子 Skill，按其路由读取必要参考；普通案件任务不一次加载全部子 Skill。

安装时保留整个 `china-patent-inventive-step-response/` 文件夹及内部层级。子 Skill 提供按需加载的工作指引；读取子 Skill 不代表创建子 agent，也不要求独立调用命令。

在原项目中，`.opencode/skills` 是项目 Skill 的唯一内容源；移植到其他环境时，按该环境的 Skill 发现机制选择安装位置。

- 原项目位于中文 Windows 路径下，`.agents/skills` 会触发当前受控命令环境的刷新故障；不要创建该目录，待兼容性修复后再迁移。
- `.codex/config.toml` 的 `skills.config` 只能启停已发现的 Skill，不能用于注册 `.opencode` 中的新 Skill。
- Skill 文件统一按 UTF-8 读取和保存；未经明确授权，不修改项目外部的 Skill 源文件。
- 维护 Skill 使用 Codex 系统提供的 `skill-creator`；原项目旧版不参与路由。

## 任务路由

完整的创造性审查意见分析、答复方案设计、意见陈述书起草、驳回复盘或复审前分析，读取 [完整答复工作流](subskills/inventive-step-answer-workflow/SKILL.md)。狭窄问题直接读取下表对应专项子 Skill。

| 任务 | Skill |
|---|---|
| 提取审查员论证链、标记待核查环节 | [office-action-analysis](subskills/office-action-analysis/SKILL.md) |
| 判断 D1 是否适合作为起点 | [closest-prior-art](subskills/closest-prior-art/SKILL.md) |
| 确定区别特征、效果和实际技术问题 | [distinguishing-features](subskills/distinguishing-features/SKILL.md) |
| 判断技术启示、结合动机和显而易见性 | [obviousness-assessment](subskills/obviousness-assessment/SKILL.md) |
| 评价预料不到效果、技术偏见等其他因素 | [secondary-considerations](subskills/secondary-considerations/SKILL.md) |
| 将已核实的分析组织为答复论点 | [challenge-examiner-reasoning](subskills/challenge-examiner-reasoning/SKILL.md) |
| 设计权利要求修改方案 | [claim-amendment-strategies](subskills/claim-amendment-strategies/SKILL.md) |
| 将已核实分析写成正式法律文本 | [legal-writing-style](subskills/legal-writing-style/SKILL.md) |
| 对既有专利成稿做保守校对 | [patent-prose-polish](subskills/patent-prose-polish/SKILL.md) |
| 生物技术主题的特殊判断 | 通用模块叠加 [biotech-inventive-step](subskills/biotech-inventive-step/SKILL.md) |

[inventive-step-overview](subskills/inventive-step-overview/SKILL.md) 仅兼容旧名称，不承载实体判断规则。通用 `humanizer` 仅在明确要求通用文案自然化、AI 痕迹分析或特定语气改写时使用；不得默认用于专利答辩。

## 分工与交付

```text
事实与证据核查 → 创造性分析 → 答复方案
                                ├─ 需要修改：拟定权利要求 → 重新分析
                                └─ 无需修改：沿用已确认的权利要求
→ legal-writing-style → patent-prose-polish → 按要求交付
```

只要求分析或建议时，交付结论、依据、风险和方案，不修改案件文件。需要成稿时再进入写作；已有可靠分析可复用，只复核本次变化及其影响。单纯校对按局部任务处理，不强制重跑完整流程。

- 本 Skill 管入口、共同约束与用户偏好；工作流管阶段衔接和交付；专项 Skill 管各自的判断与产物。
- 分析记录保留审查员主张、独立核查、证据缺口和方案风险；正式文本按争点选取所需论述，不照搬内部检查表或策略记录。
- 技术问题和非显而易见性须在分析阶段论证清楚；写作和润色发现实体缺口时，退回相应模块核实。

## 可选外部核查

DeepSeek（DS）核查仅在用户明确要求使用或明确选择该功能时启用。用户未主动要求时，不调用该工具、不准备外发材料包，也不主动询问是否开启；普通检查、复核、校对及笼统的子agent请求不自动触发外部DS核查。仅在启用该功能时读取 [可选核查操作说明](subskills/inventive-step-answer-workflow/references/09-可选DeepSeek核查.md)；缺少核查工具时说明限制，不假定已具备核查能力。本包不包含核查工具及其授权凭据。授权限定于用户指定的当前案件、文本和范围，外发继续遵循下述共同约束。

## 表达偏好

- 分析、建议、成稿和日常回复均直接陈述事实、判断及依据。默认不用“不是……而是……”“并非……而是……”“不在于……而在于……”“真正的……是……”及“不仅……更……”等修辞性对照；不以同义替换保留同类逻辑。
- 正式意见陈述以正面论述为主，围绕技术方案、对比文件、效果和启示展开。非必要时不直接或委婉评判审查意见的对错；确需澄清关键认定或提出具体请求时，中性、简要地回应并注明出处。
- 正式成稿采用法言法语：概念准确、论证严谨、措辞审慎、请求清楚。具体标准由 [legal-writing-style](subskills/legal-writing-style/SKILL.md) 维护；日常沟通保持清楚自然。
- 保留有实体意义的否定判断及必要事实对比。直接引文和权利要求文字保持原样，不为文风改变事实、术语、数字、日期、证据位置、结论强度或法律依据。

## 共同约束

- 以当前权利要求限定的整体技术方案为评价对象；说明书中未进入权利要求的内容另列为潜在修改素材。
- 关键事实定位到申请文件、审查意见或对比文件的准确位置；区分文件记载、技术推断和待核实事项。无法确认时标记“待核实”，不补造事实或出处。
- 区分“被公开”“存在技术启示”“有结合动机”“具有合理成功预期”；技能摘要不替代现行法律和审查指南，涉及具体适用时核验版本与原文。
- 修改逐项核查原始依据、保护范围影响、专利法第三十三条风险及从属关系。仅在实质方案取舍尚未获得用户指示时请求选择；先完成可供比较的方案和依据，继续不受该选择影响的工作。
- 向申请人、审查员或任何外部系统发送信息、提交文件或拨打电话，必须另行取得用户授权。

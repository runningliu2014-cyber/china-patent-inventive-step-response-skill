---
name: inventive-step-overview
description: >-
  兼容旧调用名称的中国专利创造性 Skill 索引。仅在用户明确点名 inventive-step-overview 时使用；完整案件改用 inventive-step-answer-workflow。
---

# 创造性答辩兼容索引

本 Skill 不保存实体判断规则，只把旧调用转到当前模块。

| 任务 | 使用 Skill |
|---|---|
| 完整审查意见分析、方案和成稿 | `inventive-step-answer-workflow` |
| 审查员论证链 | `office-action-analysis` |
| 最接近的现有技术 | `closest-prior-art` |
| 区别特征、技术效果和实际技术问题 | `distinguishing-features` |
| 技术启示和显而易见性 | `obviousness-assessment` |
| 其他因素 | `secondary-considerations` |
| 将已核实分析组织为答复论点 | `challenge-examiner-reasoning` |
| 权利要求修改 | `claim-amendment-strategies` |
| 正式法律语言 | `legal-writing-style` |
| 成稿保守校对 | `patent-prose-polish` |
| 生物技术专题 | `biotech-inventive-step` |

只询问单一问题时，不运行完整流程，也不加载无关模块。


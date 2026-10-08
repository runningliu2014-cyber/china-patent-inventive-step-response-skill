# 仓库协作入口

本仓库以 `china-patent-inventive-step-response/` 为唯一发布包，文件统一使用 UTF-8。

处理中国专利创造性答辩任务时，完整读取 [主 Skill](china-patent-inventive-step-response/SKILL.md)，按其路由读取 `subskills/` 中本次所需的子 Skill 及参考文件。共同约束、表达偏好和外发授权边界由主 Skill 维护。

维护 Skill 使用 Codex 系统提供的 `skill-creator`。调整模块后检查相对引用、路由及内容一致性，并同步更新发布压缩包。

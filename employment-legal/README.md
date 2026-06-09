# 劳动法务（employment-legal）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。基于 Anthropic claude-for-legal（Apache-2.0）二次开发。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 技能（3 项）

| 技能 | 说明 |
|---|---|
| `/labor-arbitration` | 劳动仲裁应对全流程技能，覆盖案情分析、证据收集、胜负概率评估、答辩状撰写、举证质证意见与重点风险提示。 |
| `/labor-contract` | "劳动合同定制生成。 |
| `/severance-calc` | 劳动经济补偿与赔偿金测算助手。 |

## 配置与护栏

- 首次使用：按 `CLAUDE.md` 模板填写实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/employment-legal/CLAUDE.md`（不进仓库）。
- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。
- 核心法条库占位见 `references/employment-legal-core.md`，须官方源核验后填充。

# 劳动法务（employment-legal）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。基于 Anthropic claude-for-legal（Apache-2.0）二次开发。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 首次使用

运行 `/employment-legal:cold-start-interview`（2 分钟速启 / 15 分钟完整）建立实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/employment-legal/CLAUDE.md`（不进仓库）。之后可用 `/employment-legal:customize` 单项调整、`/employment-legal:matter-workspace` 管理多客户事项隔离。

## 技能（6 项）

| 技能 | 说明 |
|---|---|
| `/employment-legal:cold-start-interview` | 首次配置访谈——建立你的劳动法务实务画像并写入用户配置路径。 |
| `/employment-legal:customize` | 引导式定制你的劳动法务实务画像——修改一项配置而不重新运行完整冷启动访谈。 |
| `/employment-legal:labor-arbitration` | 劳动仲裁应对全流程技能，覆盖案情分析、证据收集、胜负概率评估、答辩状撰写、举证质证意见与重点风险提示。 |
| `/employment-legal:labor-contract` | "劳动合同定制生成。 |
| `/employment-legal:matter-workspace` | 管理事项工作区——新建、列表、切换、关闭或脱离（实务级）。 |
| `/employment-legal:severance-calc` | 劳动经济补偿与赔偿金测算助手。 |

## 护栏与法条库

- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。
- 核心法条库占位见 `references/employment-legal-core.md`，须官方源核验后填充。

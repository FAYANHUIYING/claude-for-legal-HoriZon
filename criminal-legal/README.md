# 刑事法务（criminal-legal）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。基于 Anthropic claude-for-legal（Apache-2.0）二次开发。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 技能（2 项）

| 技能 | 说明 |
|---|---|
| `/criminal-defense` | 刑事辩护全流程工具集，按需求路由生成各类辩护工作产品。 |
| `/sentencing` | 以五步法对刑事个案进行量刑测算与量刑建议拟定的专业工作流。 |

## 配置与护栏

- 首次使用：按 `CLAUDE.md` 模板填写实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/criminal-legal/CLAUDE.md`（不进仓库）。
- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。
- 核心法条库占位见 `references/criminal-legal-core.md`，须官方源核验后填充。

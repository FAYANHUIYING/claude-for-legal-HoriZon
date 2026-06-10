# 刑事法务（criminal-legal）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 首次使用

运行 `/criminal-legal:cold-start-interview`（2 分钟速启 / 15 分钟完整）建立实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/criminal-legal/CLAUDE.md`（不进仓库）。之后可用 `/criminal-legal:customize` 单项调整、`/criminal-legal:matter-workspace` 管理多客户事项隔离。

## 技能（5 项）

| 技能 | 说明 |
|---|---|
| `/criminal-legal:cold-start-interview` | 首次配置访谈——建立你的刑事法务实务画像并写入用户配置路径。 |
| `/criminal-legal:criminal-defense` | 刑事辩护全流程工具集，按需求路由生成各类辩护工作产品。 |
| `/criminal-legal:customize` | 引导式定制你的刑事法务实务画像——修改一项配置而不重新运行完整冷启动访谈。 |
| `/criminal-legal:matter-workspace` | 管理事项工作区——新建、列表、切换、关闭或脱离（实务级）。 |
| `/criminal-legal:sentencing` | 以五步法对刑事个案进行量刑测算与量刑建议拟定的专业工作流。 |

## 护栏与法条库

- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。
- 核心法条库占位见 `references/criminal-legal-core.md`，须官方源核验后填充。

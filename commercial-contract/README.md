# 商事合同（commercial-contract）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 首次使用

运行 `/commercial-contract:cold-start-interview`（2 分钟速启 / 15 分钟完整）建立实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/commercial-contract/CLAUDE.md`（不进仓库）。之后可用 `/commercial-contract:customize` 单项调整、`/commercial-contract:matter-workspace` 管理多客户事项隔离。

## 技能（5 项）

| 技能 | 说明 |
|---|---|
| `/commercial-contract:cold-start-interview` | 首次配置访谈——建立你的商事合同实务画像并写入用户配置路径。 |
| `/commercial-contract:contract-drafting` | 从零起草各类合同的专业技能，覆盖买卖、服务、技术、许可、合作、建设工程等常见类型，按六步法推进（需求确认→法律调研→框架搭建→条款设计→风险扫描→文档生成），内置谈判立场三级分档与多维风险扫描。 |
| `/commercial-contract:contract-review` | 合同审查助手。 |
| `/commercial-contract:customize` | 引导式定制你的商事合同实务画像——修改一项配置而不重新运行完整冷启动访谈。 |
| `/commercial-contract:matter-workspace` | 管理事项工作区——新建、列表、切换、关闭或脱离（实务级）。 |

## 护栏与法条库

- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。
- 核心法条库占位见 `references/commercial-contract-core.md`，须官方源核验后填充。

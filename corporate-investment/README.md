# 公司与投融资（corporate-investment）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 首次使用

运行 `/corporate-investment:cold-start-interview`（2 分钟速启 / 15 分钟完整）建立实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/corporate-investment/CLAUDE.md`（不进仓库）。之后可用 `/corporate-investment:customize` 单项调整、`/corporate-investment:matter-workspace` 管理多客户事项隔离。

## 技能（5 项）

| 技能 | 说明 |
|---|---|
| `/corporate-investment:cold-start-interview` | 首次配置访谈——建立你的公司与投融资实务画像并写入用户配置路径。 |
| `/corporate-investment:corporate-docs` | 公司治理文件起草助手——覆盖股东会决议、董事会决议、公司章程、股东协议、出资协议、增资协议的起草。 |
| `/corporate-investment:customize` | 引导式定制你的公司与投融资实务画像——修改一项配置而不重新运行完整冷启动访谈。 |
| `/corporate-investment:legal-opinion` | 出具法律意见书。 |
| `/corporate-investment:matter-workspace` | 管理事项工作区——新建、列表、切换、关闭或脱离（实务级）。 |

## 护栏与法条库

- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。
- 核心法条库占位见 `references/corporate-investment-core.md`，须官方源核验后填充。

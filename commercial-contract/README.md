# 商事合同（commercial-contract）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。基于 Anthropic claude-for-legal（Apache-2.0）二次开发。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 技能（2 项）

| 技能 | 说明 |
|---|---|
| `/contract-drafting` | 从零起草各类合同的专业技能，覆盖买卖、服务、技术、许可、合作、建设工程等常见类型，按六步法推进（需求确认→法律调研→框架搭建→条款设计→风险扫描→文档生成），内置谈判立场三级分档与多维风险扫描。 |
| `/contract-review` | 合同审查助手。 |

## 配置与护栏

- 首次使用：按 `CLAUDE.md` 模板填写实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/commercial-contract/CLAUDE.md`（不进仓库）。
- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。
- 核心法条库占位见 `references/commercial-contract-core.md`，须官方源核验后填充。

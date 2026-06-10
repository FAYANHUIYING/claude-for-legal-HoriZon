# 宏志底座（原子能力）（hongzhi-core）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。基于 Anthropic claude-for-legal（Apache-2.0）二次开发。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 首次使用

运行 `/hongzhi-core:cold-start-interview`（2 分钟速启 / 15 分钟完整）建立实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/hongzhi-core/CLAUDE.md`（不进仓库）。之后可用 `/hongzhi-core:customize` 单项调整、`/hongzhi-core:matter-workspace` 管理多客户事项隔离。

## 技能（11 项）

| 技能 | 说明 |
|---|---|
| `/hongzhi-core:cold-start-interview` | 首次配置访谈——建立你的底座原子能力实务画像并写入用户配置路径。 |
| `/hongzhi-core:customize` | 引导式定制你的底座原子能力实务画像——修改一项配置而不重新运行完整冷启动访谈。 |
| `/hongzhi-core:document-summarization` | 当需要对判决书、裁定书、调解书、仲裁裁决书、行政处罚决定书等法律文书进行客观、结构化摘要时启用本技能。 |
| `/hongzhi-core:evidence-argument-chain` | 用于将案件中的各项证据与法律主张系统性地对应挂钩、构建完整证据链时触发。 |
| `/hongzhi-core:evidence-evaluation` | 当需要对案件证据进行真实性、合法性、关联性（"三性"）及证明力评估时使用本技能。 |
| `/hongzhi-core:legal-analysis` | 用于中国法语境下的法律问题结构化分析。 |
| `/hongzhi-core:legal-consequence` | 在已确认的法律事实、已厘清的法律关系与已锁定的法律规范基础上，推导出具体而可操作的法律后果时使用本技能。 |
| `/hongzhi-core:legal-terminology` | 用于在起草、修改或审查各类法律文本（合同、起诉状、答辩状、法律意见书、备忘录、裁判文书、合规文件等）时，对其中的用语进行规范化处理，使其准确、无歧义、符合法律文体。 |
| `/hongzhi-core:matter-workspace` | 管理事项工作区——新建、列表、切换、关闭或脱离（实务级）。 |
| `/hongzhi-core:rigorous-answer` | 法律问题严谨回答四步法：检索梳理依据→相似度排序→交叉验证→专业作答。 |
| `/hongzhi-core:risk-prioritization` | "面对多个法律风险点、可能结论或争议焦点时，按发生概率与影响程度对其系统排序，帮助决策者锁定关键风险、把有限资源投向最要紧处。 |

## 护栏与法条库

- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。

# 合规（compliance）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 首次使用

运行 `/compliance:cold-start-interview`（2 分钟速启 / 15 分钟完整）建立实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/compliance/CLAUDE.md`（不进仓库）。之后可用 `/compliance:customize` 单项调整、`/compliance:matter-workspace` 管理多客户事项隔离。

## 技能（5 项）

| 技能 | 说明 |
|---|---|
| `/compliance:ai-compliance` | 面向中国法语境的人工智能与算法合规辅助技能，协助进行AI相关法律法规适用、合规义务梳理、合规风险评估与监管政策解读，覆盖算法备案、生成式AI、数据合规、AI著作权与侵权、科技伦理等议题。 |
| `/compliance:cold-start-interview` | 首次配置访谈——建立你的合规实务画像并写入用户配置路径。 |
| `/compliance:customize` | 引导式定制你的合规实务画像——修改一项配置而不重新运行完整冷启动访谈。 |
| `/compliance:matter-workspace` | 管理事项工作区——新建、列表、切换、关闭或脱离（实务级）。 |
| `/compliance:privacy-policy` | 按产品事实生成最小合规版隐私协议（隐私政策），并配套个人信息清单、第三方/SDK清单、后续完善事项与复查报告。 |

## 护栏与法条库

- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。
- 核心法条库占位见 `references/compliance-core.md`，须官方源核验后填充。

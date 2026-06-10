# 知识产权（ip-legal）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 首次使用

运行 `/ip-legal:cold-start-interview`（2 分钟速启 / 15 分钟完整）建立实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/ip-legal/CLAUDE.md`（不进仓库）。之后可用 `/ip-legal:customize` 单项调整、`/ip-legal:matter-workspace` 管理多客户事项隔离。

## 技能（7 项）

| 技能 | 说明 |
|---|---|
| `/ip-legal:cold-start-interview` | 首次配置访谈——建立你的知识产权实务画像并写入用户配置路径。 |
| `/ip-legal:customize` | 引导式定制你的知识产权实务画像——修改一项配置而不重新运行完整冷启动访谈。 |
| `/ip-legal:ip-advisor` | 知识产权综合法务助手，覆盖著作权（版权）、商标、专利、商业秘密与不正当竞争等知产事务。 |
| `/ip-legal:matter-workspace` | 管理事项工作区——新建、列表、切换、关闭或脱离（实务级）。 |
| `/ip-legal:patent` | 用于系统化分析专利文件、解析权利要求、提取技术特征并评估侵权与稳定性。 |
| `/ip-legal:trademark` | 面向中国商标申请的全流程辅助技能：依据尼斯分类进行类别规划、对拟申请商标做可注册性初筛、准备申请材料（商品/服务清单、商标说明），并以结构化方式输出建议与风险分级。 |
| `/ip-legal:trademark-infringement` | 商标侵权判断与风险分析技能。 |

## 护栏与法条库

- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。
- 核心法条库占位见 `references/ip-legal-core.md`，须官方源核验后填充。

# 知识产权（ip-legal）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。基于 Anthropic claude-for-legal（Apache-2.0）二次开发。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 技能（4 项）

| 技能 | 说明 |
|---|---|
| `/ip-advisor` | 知识产权综合法务助手，覆盖著作权（版权）、商标、专利、商业秘密与不正当竞争等知产事务。 |
| `/patent` | 用于系统化分析专利文件、解析权利要求、提取技术特征并评估侵权与稳定性。 |
| `/trademark` | 面向中国商标申请的全流程辅助技能：依据尼斯分类进行类别规划、对拟申请商标做可注册性初筛、准备申请材料（商品/服务清单、商标说明），并以结构化方式输出建议与风险分级。 |
| `/trademark-infringement` | 商标侵权判断与风险分析技能。 |

## 配置与护栏

- 首次使用：按 `CLAUDE.md` 模板填写实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/ip-legal/CLAUDE.md`（不进仓库）。
- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。
- 核心法条库占位见 `references/ip-legal-core.md`，须官方源核验后填充。

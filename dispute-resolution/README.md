# 商事争议解决（dispute-resolution）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。基于 Anthropic claude-for-legal（Apache-2.0）二次开发。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 技能（13 项）

| 技能 | 说明 |
|---|---|
| `/agent-brief` | 撰写庭审用代理词与辩论意见，以民商事案件为主、兼顾通用诉讼。 |
| `/appeal-petition` | 撰写民事上诉状或再审申请书。 |
| `/case-analysis` | 对中文案件材料进行案情梳理与风险评估。 |
| `/case-chronology` | 制作案件大事记、梳理诉讼时间轴。 |
| `/case-intake` | 用于在动笔写任何法律文书之前，先对接收到的案件材料进行系统拆解、整理与分析。 |
| `/civil-complaint-drafting` | 协助按法定结构撰写民事起诉状。 |
| `/defense-statement` | 撰写民事答辩状，针对原告诉讼请求逐项答辩，组织事实抗辩与法律抗辩、反驳对方证据与请求权基础并提出己方主张。 |
| `/judgment-analysis` | 判决书深度拆解与法律错误识别工具，评估上诉策略与再审事由并输出救济路径建议。 |
| `/lawyer-letter` | 起草律师函、催告函与律师声明的专项技能。 |
| `/litigation-full-process` | 诉讼案件全流程分析与策略辅助。 |
| `/litigation-visualization` | 把案件事实转成可打印的可视化图表。 |
| `/retrial-analysis` | 民事再审可行性分析 — 读取生效判决书、原审证据与庭审笔录，识别原审事实、证据、论理、法律适用方面的错误与瑕疵，逐项匹配《民事诉讼法》法定再审事由，输出再审可行性分析报告。 |
| `/settlement` | 起草和解协议与调解协议的专业技能。 |

## 配置与护栏

- 首次使用：按 `CLAUDE.md` 模板填写实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/dispute-resolution/CLAUDE.md`（不进仓库）。
- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。
- 核心法条库占位见 `references/dispute-resolution-core.md`，须官方源核验后填充。

# 商事争议解决（dispute-resolution）

> 宏志法律智能体（claude-for-legal · HoriZon 版）业务插件之一。
> **所有输出均为供执业律师审查的草稿，不构成法律意见。**

## 首次使用

运行 `/dispute-resolution:cold-start-interview`（2 分钟速启 / 15 分钟完整）建立实务画像，写入 `~/.claude/plugins/config/claude-for-legal-horizon/dispute-resolution/CLAUDE.md`（不进仓库）。之后可用 `/dispute-resolution:customize` 单项调整、`/dispute-resolution:matter-workspace` 管理多客户事项隔离。

## 技能（19 项）

| 技能 | 说明 |
|---|---|
| `/dispute-resolution:agent-brief` | 撰写庭审用代理词与辩论意见，以民商事案件为主、兼顾通用诉讼。 |
| `/dispute-resolution:appeal-petition` | 撰写民事上诉状或再审申请书。 |
| `/dispute-resolution:case-analysis` | 对中文案件材料进行案情梳理与风险评估。 |
| `/dispute-resolution:case-chronology` | 制作案件大事记、梳理诉讼时间轴。 |
| `/dispute-resolution:case-intake` | 用于在动笔写任何法律文书之前，先对接收到的案件材料进行系统拆解、整理与分析。 |
| `/dispute-resolution:civil-complaint-drafting` | 协助按法定结构撰写民事起诉状。 |
| `/dispute-resolution:cold-start-interview` | 首次配置访谈——建立你的商事争议解决实务画像并写入用户配置路径。 |
| `/dispute-resolution:customize` | 引导式定制你的商事争议解决实务画像——修改一项配置而不重新运行完整冷启动访谈。 |
| `/dispute-resolution:deadline-tracker` | 诉讼/仲裁期限台账管理——录入、查看、完结开庭/举证/答辩/管辖权异议/上诉/再审/ |
| `/dispute-resolution:defense-statement` | 撰写民事答辩状，针对原告诉讼请求逐项答辩，组织事实抗辩与法律抗辩、反驳对方证据与请求权基础并提出己方主张。 |
| `/dispute-resolution:element-analysis` | 要件分析表——以请求权基础为纲，把每项诉讼请求拆解为构成要件，逐要件映射证据 |
| `/dispute-resolution:judgment-analysis` | 判决书深度拆解与法律错误识别工具，评估上诉策略与再审事由并输出救济路径建议。 |
| `/dispute-resolution:lawyer-letter` | 起草律师函、催告函与律师声明的专项技能。 |
| `/dispute-resolution:litigation-full-process` | 诉讼案件全流程分析与策略辅助。 |
| `/dispute-resolution:litigation-visualization` | 把案件事实转成可打印的可视化图表。 |
| `/dispute-resolution:matter-workspace` | 管理事项工作区——新建、列表、切换、关闭或脱离（实务级）。 |
| `/dispute-resolution:portfolio-status` | 组合视图——把全部在办事项的进展拼成一张总表：每案的阶段、最近动态、停滞天数、 |
| `/dispute-resolution:retrial-analysis` | 民事再审可行性分析 — 读取生效判决书、原审证据与庭审笔录，识别原审事实、证据、论理、法律适用方面的错误与瑕疵，逐项匹配《民事诉讼法》法定再审事由，输出再审可行性分析报告。 |
| `/dispute-resolution:settlement` | 起草和解协议与调解协议的专业技能。 |

## 期限监控代理（deadline-watcher）

跟踪开庭、举证期限、答辩/管辖权异议、上诉期、再审申请、申请执行、保全续封续冻、仲裁时效等硬性期限，在届满**之前**输出"决策点"预警（立即/本周/即将三档；未核验期限按"可能更早"对待）。台账由 `/dispute-resolution:deadline-tracker` 维护。建议每周一运行，开庭或期限落在 14 天内的事项每日运行。代理不会自我调度——设一个循环提醒来调用它。

## 护栏与法条库

- 统一护栏见本插件 `CLAUDE.md`「共享护栏」节：来源标签 / 检索内容信任边界 / 目的地检查 / 风险四要素 / 决策树 / 非法律意见声明。
- 核心法条库占位见 `references/dispute-resolution-core.md`，须官方源核验后填充。

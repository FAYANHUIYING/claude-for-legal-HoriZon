# Claude for legal (HoriZon)

> **宏志法律智能体** · **宏志律师事务所** 中国法实务 Claude 智能体插件集（HoriZon 架构版）。
> 面向中国律所实务：底座原子能力 × 八大业务领域的四层技能架构，64 项技能开箱即装。

## ⚠️ 重要声明（使用前必读）

- **草稿版（v0.1.0-hz）**：技能骨架已就位，宏志五类经验资产（实务画像 / 范本库 / 逐条 playbook / 裁判口径 / 核验过的法条 core）多为占位，须按"提炼流水线"逐插件灌入并由合伙人审定。
- **AI 辅助内容**：技能为 AI 辅助生成，法条 core 库目前为占位待核验。**所有输出均为供执业律师审查的草稿，不构成法律意见；引用的法条、司法解释、数值须经权威数据库（北大法宝 / 元典 / 官方法规库）核实后方可依赖。**
- **非官方**：非 Anthropic 官方产品，未获其背书，不代表其法律立场。"Claude" 为 Anthropic 商标，本项目仅作兼容性描述使用。

## 架构（四层 · 9 插件 · 64 技能）

```
编排/业务层  8 个业务插件，面向律师一句话发起
检索/数据层  元典 / 北大法宝 / 飞书（仅接已开通者；官方源兜底）
底座层       hongzhi-core 原子能力，被各业务插件反复调用
```

| 插件 | 领域 | 技能数 | 代表技能 |
|---|---|---|---|
| `hongzhi-core`（底座） | 原子能力 | 11 | 术语规范 · 法律后果推导 · 证据三性评估 · 证据链映射 · 风险优先级 · 法律分析 · 文书摘要 · 严谨作答 |
| `commercial-contract`（商事合同） | 合同全生命周期 | 5 | 合同起草（六步法） · 合同审查（五阶段法/速查表/A·B·C 方案） |
| `dispute-resolution`（商事争议） | 诉讼/仲裁全流程 | 16 | 全流程编排 · 拆案 · 案情分析 · 大事记 · 起诉/答辩/上诉/再审/代理词 · 判决拆解 · 再审分析 · 可视化 · 律师函 · 和解 |
| `corporate-investment`（公司投融资） | 公司治理与交易 | 5 | 公司治理文件起草 · 法律意见书 |
| `due-diligence`（尽调） | 尽职调查 | 4 | 六维尽调清单 + IRL + RedFlag |
| `compliance`（合规） | 数据/AI/隐私 | 5 | AI与算法合规 · 隐私政策（最小合规版） |
| `ip-legal`（知产） | 知识产权 | 7 | 知产顾问 · 专利/FTO · 商标可注册性 · 商标侵权判断 |
| `employment-legal`（劳动） | 劳动用工 | 6 | 劳动仲裁应对 · 劳动合同定制 · 补偿/赔偿测算 |
| `criminal-legal`（刑事） | 刑事辩护 | 5 | 刑事辩护全流程 · 量刑测算 |

每个插件均含运营三件套：`cold-start-interview`（首次配置访谈，2 分钟速启/15 分钟完整）、`customize`（单项调整）、`matter-workspace`（多客户事项隔离）。

> 家事 / 保险领域见姊妹仓库 `hongzhi-legal-agents`。

## 安装

```bash
claude plugin marketplace add https://github.com/FAYANHUIYING/claude-for-legal-HoriZon
# 先装底座，再按需装业务插件
claude plugin install --scope user hongzhi-core@claude-for-legal-horizon
claude plugin install --scope user commercial-contract@claude-for-legal-horizon
claude plugin install --scope user dispute-resolution@claude-for-legal-horizon
# …其余插件同理
```

安装后重启 Claude Code。首次使用先运行各插件的 `/<插件>:cold-start-interview` 建立实务画像（写入 `~/.claude/plugins/config/claude-for-legal-horizon/`，**不进仓库**）。

## 把"29 年经验"装进技能（差异化壁垒）

每个业务技能 = **流程骨架（已就位）＋ 宏志五类经验资产（待灌入，决定上限）**：

| 经验资产 | 落到技能哪里 |
|---|---|
| ① 实务画像（立场/风险姿态/上报链/行文） | 各插件 `CLAUDE.md` 模板 |
| ② 范本库（定稿文书脱敏） | `references/templates/` |
| ③ 逐条审查 playbook（立场分级/让步底线/话术） | `skills/<技能>/references/*-playbook.md` |
| ④ 裁判口径 / 典型案库 | `references/<插件>-cases.md` |
| ⑤ 现行法条 core（带"已验证-日期"） | `references/<插件>-core.md` |

**提炼流水线**：选领域资深合伙人 → 1 次 cold-start 访谈定实务画像 → 提供 5–10 份定稿范本 → AI 抽取条款/口径草拟 playbook → 合伙人订正 → 法条联网核验打日期 → 律师试用反馈闭环。

## 数据源连接器（真实可用）

| 连接器 | 能力 | 接入 |
|---|---|---|
| **元典法律检索**（默认内置） | 法规/法条语义检索 · 裁判文书 · 企业工商与涉诉 | `npx yuandian-mcp-server`（随插件自动加载）+ 环境变量 `YUANDIAN_API_KEY` |
| **北大法宝 MCP** | 法规/司法解释/案例语义检索 | [mcp.pkulaw.com](https://mcp.pkulaw.com/) 注册取 Token，按 `CONNECTORS.md` 配置 |
| **天眼查 MCP** | 企业工商 · 风险 · 知产 | [mcp.tianyancha.com](https://mcp.tianyancha.com/) 托管接入 |
| **飞书** | 消息/云文档协作 | 官方 `@larksuiteoapi/lark-mcp`（需企业自建应用凭证） |

**逐步接入指南见 [`CONNECTORS.md`](CONNECTORS.md)**（约 5 分钟）。未接任何检索源时技能不会瞎编：引用一律标 `[模型知识—需验证]` 并提示官方源（flk.npc.gov.cn / wenshu.court.gov.cn / gsxt.gov.cn）兜底。

## 统一安全护栏

各插件 `CLAUDE.md`「共享护栏」节字节一致：律师工作成果页眉 · 来源标签体系 · 飞行前引用检查 · 检索内容信任边界 · 目的地（保密）检查 · 跨技能严重度下限 · 风险四要素 · 下一步决策树 · 非法律意见声明。

## 许可与署名

- 遵循 **Apache License 2.0**（见 `LICENSE`）；第三方组件与许可声明见 `NOTICE`。
- 维护：宏志律师事务所。

## 维护

- 跟踪 Claude Code 插件规范与连接器生态变化，保持兼容。
- 维护"中国法 currency-watch"：民法典合同编/婚姻家庭编/继承编司法解释、公司法、劳动争议司法解释（二）法释〔2025〕12号、反不正当竞争法（2025）、个人信息保护法配套规定、量刑指导意见等修法动态，刷新各 `references/*-core.md` 的"已验证"日期。

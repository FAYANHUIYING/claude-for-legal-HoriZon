# CLAUDE.md — 维护指引（claude-for-legal · HoriZon · 宏志法律智能体）

本仓库是一个 **Claude Code 插件 marketplace**：宏志律师事务所中国法实务插件集，采用"底座原子能力 + 八大业务领域"的四层架构。绝大多数工作是编辑**提示内容**（技能、实务画像、法条库），而非应用代码。

> 非 Anthropic 官方产品；所有输出为**律师审查草稿，非法律意见**。

## 目录结构

```
.claude-plugin/marketplace.json   # marketplace 清单，每插件一条（共 9 条）
<插件>/                            # hongzhi-core + 8 业务插件
  .claude-plugin/plugin.json       # 插件清单（name/version/description/author）
  .mcp.json                        # 该插件连接的 MCP（默认内置元典；hongzhi-core 无。接入指南见 CONNECTORS.md）
  CLAUDE.md                        # 实务画像模板 + 共享护栏（各插件「共享护栏」节字节一致）
  README.md                        # 插件说明（技能清单自动生成）
  skills/<名>/SKILL.md             # 一目录一技能
  hooks/hooks.json                 # 空桩 {"hooks":{}}
  agents/<名>.md                    # 监控代理（目前：dispute-resolution/deadline-watcher）
  references/<插件>-core.md         # 该领域中国法核心法条库（占位，待官方源核验）
  references/company-profile-template.md  # 共享所务画像模板（cold-start 首个插件时写入共享画像）
references/                        # 跨插件共享模板（company-profile / dashboard）
```

四层架构：**底座层** `hongzhi-core`（被各业务插件反复调用的原子能力）→ **业务层** 8 插件 → **检索/数据层**（元典/北大法宝/飞书，仅接已开通者）。

## 插件与技能（9 插件 / 65 技能 / 1 代理）

三件套 = cold-start-interview / customize / matter-workspace（每插件均含，按领域定制）。

| 插件 | 技能数 |
|---|---|
| hongzhi-core | 11（三件套 + legal-terminology, legal-consequence, evidence-evaluation, evidence-argument-chain, risk-prioritization, legal-analysis, document-summarization, rigorous-answer） |
| commercial-contract | 5（三件套 + contract-drafting, contract-review） |
| dispute-resolution | 17（三件套 + deadline-tracker, litigation-full-process, case-intake, case-analysis, case-chronology, civil-complaint-drafting, defense-statement, appeal-petition, agent-brief, judgment-analysis, retrial-analysis, litigation-visualization, lawyer-letter, settlement） |
| corporate-investment | 5（三件套 + corporate-docs, legal-opinion） |
| due-diligence | 4（三件套 + due-diligence-checklist） |
| compliance | 5（三件套 + ai-compliance, privacy-policy） |
| ip-legal | 7（三件套 + ip-advisor, patent, trademark, trademark-infringement） |
| employment-legal | 6（三件套 + labor-arbitration, labor-contract, severance-calc） |
| criminal-legal | 5（三件套 + criminal-defense, sentencing） |

## 发布/改动前校验

```bash
claude plugin validate .claude-plugin/marketplace.json
claude plugin validate hongzhi-core   # 其余 8 插件同
```
各插件根 `CLAUDE.md` 会有 "CLAUDE.md ... not loaded as project context" 的 warning——这是**预期**的（模板设计如此），勿"修复"为把内容塞进技能。

## 约定

- `marketplace.json` 的 `name`/`description`/`author` 应与各插件 `plugin.json` 一致。
- 用户配置命名空间为 `claude-for-legal-horizon`：cold-start 把各插件 `CLAUDE.md` 复制到 `~/.claude/plugins/config/claude-for-legal-horizon/<插件>/CLAUDE.md`；**绝不在模板里写入真实客户数据**。
- SKILL.md 里写给用户的 `/命令` 必须是真实的 `skills/<名>` 目录名。
- **法条改动须核验**：条号/日期/阈值改动须对官方源（npc.gov.cn / court.gov.cn / 北大法宝 / 元典）核实，并更新 `[已验证—YYYY-MM-DD]`。
- **不要从各插件 `CLAUDE.md` 删除「共享护栏」节**（来源标签 / 检索内容信任边界 / 目的地检查 / 决策树 / 风险四要素）；该节各插件字节一致。
- 格式：JSON 两空格缩进；文件末尾留换行；无行尾空格。

## 经验灌入流水线（决定技能上限）

技能骨架已就位，价值取决于宏志五类经验资产的灌入（见 README）。每个技能 SOP：
**骨架定型 → 灌宏志五类资产（画像/范本/playbook/案库/法条core）→ 法条核验 → 护栏齐全 → validate → 律师试用 → 上架。**

## 合规

- 遵循 **Apache License 2.0**（见 `LICENSE`）；第三方组件与许可声明见 `NOTICE`。
- 编入技能的第三方来源许可证须在对外打包前逐一核验；含 NC（禁商用）/ND（禁改）者不得直接商用打包。

## 维护

- 跟踪 Claude Code 插件规范与连接器生态变化，保持兼容。
- 维护"中国法 currency-watch"：民法典各编司法解释、公司法、劳动争议司法解释（二）法释〔2025〕12号、反不正当竞争法（2025）、个人信息保护法配套规定、量刑指导意见等——纳入对应 `references/*-core.md` 复核并刷新"已验证"日期。

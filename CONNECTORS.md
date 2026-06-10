# CONNECTORS.md — 数据源接入指南（约 5 分钟）

本插件集的法律检索、企业查询能力依赖 MCP 连接器。**不接任何连接器也能用**——技能会自动降级：引用一律标 `[模型知识—需验证]`，并提示用官方源核实（法规：[flk.npc.gov.cn](https://flk.npc.gov.cn) · 裁判文书：[wenshu.court.gov.cn](https://wenshu.court.gov.cn) · 企业工商：[gsxt.gov.cn](https://www.gsxt.gov.cn)）。接上连接器后，引用可实时核验、自动打来源标签。

接好任一连接器后，在对应插件里运行 `/<插件>:cold-start-interview --check-integrations` 验证连通（只有工具调用真正成功才会报 ✓）。

---

## 1. 元典法律检索（默认内置，推荐首选）

**能力**：法规/法条语义检索、裁判文书案例检索、企业工商与涉诉信息融合查询（基本信息/股权/涉诉/被执行/行政处罚/知产等）。
**已内置**：各业务插件的 `.mcp.json` 已配置 `npx -y yuandian-mcp-server`，安装插件后自动加载，无需手工配置服务器。

**你只需要做两件事：**

1. **确认 Node.js ≥ 18 已安装**（`node -v` 检查；没有则到 [nodejs.org](https://nodejs.org) 装 LTS 版）。
2. **申请并设置 API Key**：
   - 到元典开放平台注册并创建应用，获取 API Key（接口文档站：[apiplatform.legalmind.cn](https://apiplatform.legalmind.cn)，开放接口域名 open.chineselaw.com）。
   - 设置环境变量 `YUANDIAN_API_KEY`：
     - **Windows**（PowerShell，一次性永久生效）：
       ```powershell
       [Environment]::SetEnvironmentVariable('YUANDIAN_API_KEY','你的key','User')
       ```
     - **macOS / Linux**（写入 `~/.zshrc` 或 `~/.bashrc`）：
       ```bash
       export YUANDIAN_API_KEY="你的key"
       ```
   - 重启 Claude Code 使变量生效。

**验证**：任一插件内问"检索一下竞业限制经济补偿的现行规定"——返回带 `[元典检索]` 标签即接通；若提示 Missing API key，说明环境变量未生效。

---

## 2. 北大法宝 MCP（法规/司法解释/案例，可选）

**能力**：基于北大法宝法规库的语义检索（法规、司法解释、案例）。
**接入**（官方托管，按账号下发专属地址）：

1. 到 [mcp.pkulaw.com](https://mcp.pkulaw.com/) 注册，在控制台获取你的 **服务地址**（形如 `https://apim-gw.pkulaw.com/<你的SERVICE_ID>/mcp`）与 **Token**。
2. 把以下配置加入你的用户级 MCP 配置（Claude Code 中运行 `/mcp` 添加，或编辑 `~/.claude.json`）：

   ```json
   {
     "mcpServers": {
       "pkulaw": {
         "type": "http",
         "url": "https://apim-gw.pkulaw.com/<你的SERVICE_ID>/mcp",
         "headers": { "Authorization": "Bearer <你的Token>" }
       }
     }
   }
   ```

注意：服务地址含你的专属 SERVICE_ID，**没有全局公共端点**，所以本仓库不在 `.mcp.json` 里预置占位地址（避免假连通）。计费见其[定价页](https://mcp.pkulaw.com/pricing)。

---

## 3. 天眼查 MCP（企业工商/风险/知产，可选）

**能力**：企业注册信息、股权结构、变更记录、法律诉讼、失信被执行、行政处罚、专利商标等。
**接入**：到 [mcp.tianyancha.com](https://mcp.tianyancha.com/) 开通（官方托管，支持 StreamableHTTP / SSE），按其控制台给出的地址与鉴权信息加入 `/mcp` 配置。开放平台见 [open.tianyancha.com](https://open.tianyancha.com/)。

与元典的企业融合接口功能有重叠——二选一即可；尽调（due-diligence）与公司投融资（corporate-investment）场景建议至少接一个。

---

## 4. 飞书（消息/云文档协作，可选）

**能力**：搜索消息、读取云文档——审查结论入群、从云文档拉取合同与制度文件。
**接入**（飞书官方 MCP，npm 包 `@larksuiteoapi/lark-mcp`）：

1. 在[飞书开放平台](https://open.feishu.cn)创建**企业自建应用**，记下 App ID / App Secret，按需开通消息、云文档权限。
2. 加入用户级 MCP 配置：

   ```json
   {
     "mcpServers": {
       "feishu": {
         "type": "stdio",
         "command": "npx",
         "args": ["-y", "@larksuiteoapi/lark-mcp", "mcp", "-a", "<App ID>", "-s", "<App Secret>"]
       }
     }
   }
   ```

---

## 常见问题

- **为什么 `.mcp.json` 里只预置了元典？** 北大法宝/天眼查的接入地址含用户专属 ID 或 Token，无法预置一个"对所有人可用"的地址；预置假地址会让连接器看起来配好了实际不通——这正是本插件集护栏明令禁止的（"绝不仅凭配置就报告 ✓"）。
- **公司内网/代理环境 npx 拉不动包？** 先 `npm config set registry https://registry.npmmirror.com` 换国内镜像，再重启 Claude Code。
- **接了多个检索源冲突吗？** 不冲突。技能按"飞行前引用检查"逐个探测，用真正响应的那个，并在输出的来源标签里注明（`[元典检索]` / `[北大法宝]`）。

# 免费可用的 Agent 产品与开源框架对比（Muse / dots 替代方案）

调研日期：2026-10-09。仅做调研，未注册、安装、付费或联系任何一方。
"已核实"= 本次在官方页面/GitHub 页面看到；"未核实"= 仅第三方或未能确认。
**falcon 列：依据 falcon-core 仓库的 README 与架构/运行时/安全文档整理，仅写高层能力；未读源码实现，未公开说明的项不写。**

## 一、为什么 Muse / dots 用不了
- Muse（Meta）：目前仅美国、加拿大（第三方报道，未在官方页确认完整国家列表）。https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/ ；区域说明：https://www.aiagentslibrary.com/blog/meta-muse-availability/
- dots（OpenAI）：ChatGPT 付费档位功能，由 GPT-6 Astra 驱动。https://openai.com/index/introducing-dots/ ；https://help.openai.com/en/articles/20001530-getting-started-with-your-dot
- 以下均为"自托管 + 自带模型 API Key"为主，软件本身免费，**模型调用费用另算**（可用本地模型或国内模型的免费额度，额度政策未核实）。

## 二、对比表

| 名称 | 类型 | 官方链接 | 获取/成本 | 港/陆可用性 | 集成面 (API/SDK/MCP) | 许可 | 成熟度 |
|---|---|---|---|---|---|---|---|
| OpenClaw | 常驻个人助理（最像 Muse/dots 的开源品） | https://github.com/openclaw/openclaw ，https://openclaw.ai | 自托管，免费；模型自备 | 软件本地运行，不依赖区域；聊天渠道（WhatsApp/Telegram 等）在大陆可达性需自测（未核实） | Gateway、渠道插件、可换模型/harness；MCP 细节未核实 | MIT（GitHub 页显示；另一页显示 "Other"，使用前读 LICENSE） | 约 39 万 star，2025-11 创建，更名多次，迭代快，稳定性需评估 |
| Hermes Agent（Nous Research） | 常驻个人 agent，持久记忆、自动生成 skill、定时任务、子 agent | https://github.com/NousResearch/hermes-agent ，https://hermes-agent.nousresearch.com | 一行脚本安装，免费；模型自备 | 本地运行；模型/渠道可达性自测 | 多渠道 gateway、子 agent 委派；MCP 未核实 | MIT | 约 25 万 star，2026-02 发布 |
| Goose（Block，现 aaif-goose） | 通用本地 agent（桌面/CLI/API） | https://github.com/aaif-goose/goose ，https://goose-docs.ai | 免费；任意 LLM | 本地运行 | 70+ MCP 扩展，MCP 原生 | Apache-2.0 | 约 5.4 万 star，较成熟 |
| OpenHands | 编码 / 软件工程 agent，有沙箱 | https://github.com/OpenHands/OpenHands ，SDK: https://github.com/OpenHands/software-agent-sdk | 自托管免费；有托管版（价格未核实） | 本地运行 | Python SDK、CLI；MCP 未核实 | MIT | 约 9 万 star，成熟 |
| Cline | VS Code 编码 agent | https://codepick.dev/en/compare/cline-vs-roo-code/ （第三方对比，官方仓库未单独核实） | 免费，自带 API Key | 本地 | MCP 支持（第三方说法） | 开源（具体许可未核实） | 高下载量 |
| Roo Code | VS Code 编码 agent（多模式） | https://github.com/RooCodeInc/Roo-Code | 免费 | 本地 | MCP 支持 | Apache-2.0 | **仓库已标记 ARCHIVED，不建议作为新基础** |
| Open-AutoGLM（智谱） | 手机端 GUI agent（ADB + 视觉模型） | https://github.com/zai-org/Open-AutoGLM | 开源免费；需模型（可用智谱 API 或本地部署，价格未核实） | 智谱为中国公司，国内可用 | 框架+模型；MCP 未核实 | Apache-2.0 | 约 2.6 万 star，2025-12 发布 |
| Qwen-Agent（阿里） | 开源 agent 框架：function calling、MCP、代码解释器、RAG | https://github.com/QwenLM/Qwen-Agent | pip 安装，免费；Qwen 模型本地或阿里云 API（免费额度未核实） | 国内可用 | Python SDK，MCP 支持（官方 README） | Apache-2.0 | 约 1.7 万 star |
| Coze Studio / Coze Loop（字节扣子开源版） | 可视化 agent 开发平台（Prompt/RAG/Plugin/Workflow） | https://github.com/coze-dev/coze-studio ，https://www.coze.cn | 开源版自托管免费；扣子 coze.cn 云端免费额度未核实 | 国内可用 | 插件、工作流、API 发布；MCP 未核实 | Apache-2.0（中文报道称） | 2025-07 开源，较新 |
| Dify | 低代码 agent / 工作流 / RAG 平台 | https://github.com/langgenius/dify | 自托管免费 | 本地/私有化，不受区域限制 | API、插件、MCP（未核实细节） | 改良版 Apache-2.0，附加商用条件（如多租户限制），需读 LICENSE | 成熟，社区大 |
| Kimi Agent（OK Computer）| 通用云端 agent 产品 | https://www.kimi.com/en/help/agent/agent-overview | 网页/App 使用；免费额度与收费（未核实） | 国内可用 | 产品使用为主；Kimi K2 模型开放（API 付费情况未核实） | 产品闭源；K2 权重开放 | 2025-09 起，持续迭代 |
| Manus | 通用云端 agent | https://manus.im ；香港 App Store 有上架 https://apps.apple.com/hk/app/manus-ai/id6740909540 | 免费 + 内购积分 | 香港 App Store 可见；有报道称官网对部分地区显示 "not available in your region"，大陆可用性未核实 | 产品使用为主 | 闭源 | 较成熟，但区域政策易变 |
| falcon（Thor 团队私有框架） | 私有 agent 运行平台：控制面 + RuntimeGateway + AgentInstance | 私有仓库，不公开链接 | 内部使用 | 自托管，不受区域限制 | 渠道入口 HTTP 接口、Runtime Instance API、MCP 工具接入（具体对外范围暂不公开说明） | 私有 | 自用生产环境 |
| LangGraph / CrewAI / OpenAI Agents SDK | 通用 agent 编排框架（与 falcon 最可比） | https://github.com/langchain-ai/langgraph 等；对比文：https://effloow.com/articles/ai-agent-frameworks-compared-2026 | 免费 | 本地，不受区域限制 | 第三方称主流 Python 框架均原生支持 MCP | LangGraph: MIT；其余未逐一核实 | 成熟 |

## 三、与通用 agent 框架的对比维度（falcon 列由 Thor 填）

| 维度 | OpenClaw | Hermes | Goose | OpenHands | Qwen-Agent | Coze Studio / Dify | falcon |
|---|---|---|---|---|---|---|---|
| 编排 | 单 gateway + 渠道 | 单 agent + 子 agent 委派、定时 | 单 agent + 扩展 | 编码任务循环 + 沙箱 | 函数调用+工具循环 | 可视化工作流 | 控制面（Control Plane）发布 AgentConfig/部署；RuntimeGateway 接收请求、固定配置版本、调度在线 AgentInstance；会话粘性调度，有运行台账与恢复机制 |
| 工具 / MCP | 插件（MCP 未核实） | 工具/skill（MCP 未核实） | MCP 原生 | SDK 工具（MCP 未核实） | MCP 支持 | 插件/工作流（MCP 未核实） | 原生工具/skill 注册；MCP 工具支持按需发现（tool_search，需在 Agent 配置里显式启用）；有代码执行模式（Code Mode） |
| 记忆 | 本地状态/记忆 | 持久记忆 + 自动 skill | 未核实 | 会话级为主（未核实） | RAG | 知识库 RAG | Postgres 长期记忆，显式写入/检索；RuntimeGateway 目前不自动写入或检索长期记忆；会话摘要与上下文压缩 |
| 多 agent | 未核实 | 隔离子 agent | 未核实 | 有（SDK，未核实细节） | 有（未核实细节） | 工作流内多节点 | 以 AgentInstance 为多实例/多 Agent 部署单元，由网关统一调度；agent 内子 agent 委派暂不公开说明 |
| 部署 | 自托管，多平台 | 自托管，Linux/macOS/Windows | 桌面/CLI | Docker/本地 | pip | Docker 自托管 | 自托管；Docker/Kubernetes manifest 生成，AgentInstance 作为外部进程/容器运行；依赖 PostgreSQL + Redis；自动扩缩容为策略评估，不直接创建副本 |
| 安全 | 数据留本地，提示词发往所配模型商 | 未核实 | 本地执行，需自行限权 | 沙箱 | 代码解释器需隔离 | 私有化 | 实例不持有模型密钥，模型/工具/skill 调用经 RuntimeGateway 代理；密钥加密存储；渠道入口鉴权与渠道身份信任（现支持 Telegram）；工具权限分级 |

## 四、建议（初步，供 Thor 判断）
1. 想要"Muse/dots 式常驻个人 agent"体验：先看 OpenClaw、Hermes Agent（都是 MIT，本地运行）。
2. 想和 falcon 做集成/对标：Goose（MCP 原生）、Qwen-Agent（国内模型友好、有 MCP）、LangGraph。
3. 只想看产品形态：Kimi Agent（国内）；Manus 区域不确定。
4. 避免：Roo Code（已归档）。
5. 提醒：这些项目迭代很快，star 数和许可以 GitHub 当前页为准；选定后安装前再读一遍 LICENSE 和安全说明。OpenClaw 类 agent 会持有邮箱/聊天等凭据，权限要收紧。

## 来源
GitHub 页面：openclaw/openclaw、NousResearch/hermes-agent、aaif-goose/goose、OpenHands/OpenHands、RooCodeInc/Roo-Code、zai-org/Open-AutoGLM、QwenLM/Qwen-Agent、coze-dev/coze-studio、langgenius/dify、langchain-ai/langgraph；官方页：hermes-agent.nousresearch.com、goose-docs.ai、kimi.com 帮助中心；Muse/dots 官方与第三方页见第一节。


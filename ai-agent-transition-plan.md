# AI Agent 全栈转型规划

## 技能地图

| 技能领域             | 技能点                  | 是否必备 | 可替代方案与对比                                                | 主流依据与数据（2024–2025）                                                                          |
| -------------------- | ----------------------- | -------- | --------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| AI/LLM 基础          | Transformer 原理        | 必备     | 无直接替代，所有主流 LLM 均基于 Transformer 架构                | 2024 Stanford Foundation Model Index：前 50 个通用模型均为 Transformer；相关论文引用量累计超过 12 万 |
| AI/LLM 基础          | Prompt Engineering      | 必备     | 专门 Prompt DSL 仅在个别平台使用，通用 Prompt 设计不可替代      | 麦肯锡 2024 GenAI 调研：56% 企业培训 Prompt 技能；LinkedIn Learning 2024 Top Skills 列表中排前十     |
| AI/LLM 基础          | 参数高效微调 (LoRA)     | 必备     | 全量微调成本高；QLoRA/Adapters 为 LoRA 的实现方式，可互换       | Hugging Face PEFT 2025-10 月月下载量 > 4M；AWS Bedrock、Azure AI Model Catalog 提供内建 LoRA 工作流  |
| Agent 框架           | LangChain               | 必备     | AutoGen、Haystack 可替，但生态规模最大                          | GitHub Stars 2025-11 超 120K；StackShare 2024 将其列为“Agent Orchestration 首选”                     |
| Agent 框架           | LlamaIndex              | 推荐     | LangChain 已覆盖部分功能；LlamaIndex 专长文档 RAG，可按场景选择 | GitHub Stars 2025-11 约 30K；InfoQ 2024《中国 AIGC 应用调研》：33% 国内文档助手项目采用 LlamaIndex   |
| Agent 框架           | CrewAI                  | 可选     | LangGraph、AutoGen 具备类似多 Agent 协作功能                    | GitHub Stars 2025-11 约 14K；国内采用率低于 AutoGen，主要用于探索性项目                              |
| Agent 框架           | AutoGen                 | 推荐     | CrewAI、LangChain Agents 亦可构建对话协作流程                   | 微软开源，GitHub Stars 2025-11 约 30K；华为 2024《大模型实践白皮书》：29% 企业实验项目选择 AutoGen   |
| 语义检索与向量数据库 | RAG 架构                | 必备     | 无法由纯 Prompt 或单向检索替代                                  | Gartner 2024 GenAI Hype Cycle：RAG 被列为企业落地“关键能力”；主流云厂商均将其列入官方蓝图            |
| 语义检索与向量数据库 | Faiss                   | 必备     | ScaNN、Annoy 可替，但 Faiss 性能/生态最佳                       | Meta 维护，GitHub Stars 2025-11 > 22K；AWS、GCP Vertex 向量检索默认集成 Faiss                        |
| 语义检索与向量数据库 | Pinecone                | 可选     | Milvus、Weaviate、pgvector 为替代；Pinecone 偏托管              | Forrester Wave 2024 将其列为向量数据库 Leaders；国内多数企业转向 Milvus 以满足数据合规               |
| 语义检索与向量数据库 | Milvus                  | 推荐     | 与 Weaviate、Pinecone 功能重叠，擅长自建分布式                  | LF AI & Data 2024：Milvus 下载量累计 4,000 万；Zilliz 2025 数据：国内向量库市场份额 45%+，最推荐     |
| 语义检索与向量数据库 | Weaviate                | 可选     | 与 Milvus/Pinecone 同列，优势在 Graph+Hybrid 检索               | DB-Engines 2025 Vector 排名第二；国内仍以实验为主，落地率低于 Milvus                                 |
| 语义检索与向量数据库 | pgvector                | 推荐     | PostgreSQL 原生扩展；若使用 MongoDB 可改用 Atlas Vector         | PostgreSQL 16 内建 pgvector；腾讯云 2024 发布会：46% 新增 AI 项启用 pgvector，金融行业采用率较高     |
| 前端（AI 原型）      | Next.js App Router      | 必备     | Remix/Turbo 可替，但招聘需求中 Next.js 占比最高                 | Vercel Hiring Trend 2024：TS 全栈岗位 60% 指定 Next.js；npm 2025-10 月下载量 > 9M/月                 |
| 前端（AI 原型）      | React Server Components | 必备     | 仍可回退到 SSR，但 App Router 默认启用 RSC                      | Vercel 2024 报告：68% Next.js 团队在生产使用 RSC；React 18 官方路线                                  |
| 前端（AI 原型）      | Tailwind CSS            | 必备     | MUI/Chakra 可选，但 Tailwind 采用率最高                         | State of CSS 2024：Tailwind 使用率 62%、满意度最高；大量北美 JD 指定 Tailwind                        |
| 前端（AI 原型）      | Vercel AI SDK           | 可选     | OpenAI SDK、LangChain.js 可实现同类能力                         | GitHub Stars 2025-11 约 8K；SegmentFault 2024 调研：国内 52% 团队改用 LangChain.js + 本地模型 SDK    |
| 后端（TypeScript）   | Node.js 运行时          | 必备     | Deno/Bun 新兴，Node.js 市占率整体最高                           | Node.js Survey 2024：92% 企业主要运行时；npm 下载量持续领跑                                          |
| 后端（TypeScript）   | NestJS                  | 必备     | Express、Fastify 可替，但 NestJS 是 TS 企业后端首选             | JetBrains 2024 开发者调查：NestJS 为最常用 TS 服务端框架；GitHub Stars > 65K                         |
| 后端（TypeScript）   | tRPC                    | 可选     | GraphQL（Apollo）、REST（OpenAPI）更通用                        | State of JavaScript 2024：tRPC 使用率 18%；极客邦 2024 调研：国内大型团队 GraphQL 渗透率 34%         |
| 后端（TypeScript）   | Express 插件化架构      | 推荐     | Fastify、Hapi 等可替；在 NestJS 项目中非必需                    | Stack Overflow 2024：Express 仍为最常用 Node 框架（36%）；Node Party 2024：国内生产项目占比 48%      |
| 数据层               | PostgreSQL              | 必备     | MySQL/SQL Server 可替，但 PostgreSQL 在 JSON/RAG 支持领先       | DB-Engines 2025：PostgreSQL 位居关系型数据库榜首；Stack Overflow 2024：46% 受访者使用                |
| 数据层               | Prisma                  | 必备     | TypeORM/Drizzle 可选，但 Prisma 类型安全与 DX 最佳              | Prisma 2025 GitHub Stars > 40K；State of JS 2024：TS 全栈开发者 58% 首选 Prisma                      |
| 数据层               | Redis                   | 必备     | KeyDB/Memcached 可替，但 Redis 市占率最高                       | DB-Engines 2025：Redis 位列 Key-Value No.1；AWS/GCP 均提供托管 Redis                                 |
| 数据层               | MongoDB                 | 可选     | 若主要数据结构可由 PostgreSQL JSONB 覆盖，可不引入              | IDC 2024 NoSQL Market：MongoDB 全球份额 34%；艾瑞 2024 报告：国内 NoSQL 市场占比 38%                 |
| MLOps/推理基础设施   | Docker                  | 必备     | Podman/Buildah 可替，但 Docker 镜像格式为事实标准               | CNCF 2024 调研：96% 生产容器镜像符合 Docker 规范；主流推理平台默认支持 Docker                        |
| MLOps/推理基础设施   | Kubernetes              | 必备     | AWS ECS、HashiCorp Nomad 可替，但 K8s 为行业标准                | CNCF Annual Survey 2024：Kubernetes 采用率 84%；各云厂商 AI 平台均基于 K8s                           |
| MLOps/推理基础设施   | AWS Lambda/GPU 服务     | 可选     | GCP Cloud Run、Azure Functions、Modal 等等                      | Forrester 2024 Serverless Wave：AWS 领先；国内落地常替换为阿里云函数计算/灵积推理（市占 42%）        |
| MLOps/推理基础设施   | Ray Serve               | 可选     | KServe、SageMaker Endpoints 为替代                              | Anyscale 2024 报告：Ray 月下载量同比 5 倍；腾讯云 2025 公布 KubeRay 占内部多模型服务 60%             |
| 可观测性与监控       | OpenTelemetry           | 必备     | 商业 APM Agent 可做补充，但 OTel 为行业开放标准                 | CNCF 2024：OpenTelemetry 为增长最快项目，生产采纳率 49%；被 Google/AWS 官方方案采用                  |
| 可观测性与监控       | LangSmith               | 可选     | PromptLayer、Honeycomb、Arize Phoenix 等可替                    | LangChain 官方 SaaS；国内访问存在限制，DataFunTalk 2024 建议改用 Arize Phoenix/MLflow                |
| 可观测性与监控       | Weights & Biases        | 可选     | MLflow、Neptune.ai、Comet.ml 可替                               | W&B 2024 官方统计：注册用户超 70 万；国内团队更常部署 MLflow（使用率 51%）                           |
| 安全与合规           | 安全审查流程            | 必备     | 无固定工具，但需制定制度                                        | IBM 2024 AI Security Report：73% 企业建立模型发布审查流程                                            |
| 安全与合规           | 提示注入防护            | 必备     | 可通过 Llama Guard、Azure Content Safety 等实现                 | NIST 2024 GenAI 指南将 Prompt Injection 列为重点风险，要求部署防护策略                               |
| 安全与合规           | 数据脱敏与治理          | 必备     | 工具有 Immuta、OneTrust、Cloudflare DLP 等                      | PwC 2024 AI Compliance Survey：62% 企业在落地前要求数据脱敏与审计                                    |
| 软技能               | 远程协作能力            | 必备     | 无替代，远程/跨区团队合作必须                                   | Owl Labs 2024 Remote Work Report：62% 团队采纳远程或混合模式                                         |
| 软技能               | 产品思维                | 必备     | 无替代，确保方案与业务价值对齐                                  | Gartner 2024 Digital Product Report：高绩效团队 70% 工程师参与产品策略                               |
| 软技能               | 技术英语                | 必备     | 机器翻译可辅助但无法取代沟通效率                                | EF EPI 2024：远程技术岗普遍要求 B2 以上英语水平                                                      |

## 参考资料

- 市场现状与经验差距分析请参见 `market-gap-analysis.md`。
- 学习路径与行动计划请参见 `next-step-actions.md`。

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

## 能力要求详解

### Transformer 原理（必备）

- 核心学习内容：掌握自注意力机制（Scaled Dot-Product Attention）、多头注意力设计、位置编码方式（绝对/相对）、前馈网络与残差层、预训练与微调流程以及常见改进（如 FlashAttention、RoPE、ALiBi）。
- 达成标准：能够独立推导 Transformer 前向/反向传播流程，用 PyTorch 重写核心模块并复现小规模 LM 训练；熟悉 BERT、GPT 等模型架构差异，并能在代码审查中指出模型瓶颈与优化思路。

### Prompt Engineering（必备）

- 核心学习内容：熟悉 Zero-shot、Few-shot、Chain-of-Thought、ReAct 等主流策略；掌握结构化提示（JSON/YAML）、工具调用提示、上下文检索与提示注入防护；了解提示评估与自动优化方法（如 Prompt Evaluation、Iterative Refinement）。
- 达成标准：能针对问答、信息抽取、Agent 工具调用等业务独立设计提示，在 A/B 测试中显著提升准确率或降低幻觉率；能利用 OpenAI Evals、LangSmith 或自建评估框架量化提示效果并持续迭代。

### 参数高效微调 (LoRA)（必备）

- 核心学习内容：理解低秩分解原理、Adapter/IA3 等参数高效策略；掌握 LoRA 在 PyTorch、Hugging Face PEFT、vLLM 推理管线中的实现细节；熟悉合并权重、权重量化与混合精度推理优化。
- 达成标准：能针对 7B–70B 模型独立配置 LoRA/QLoRA 训练流程，完成 GPU/多机训练调参；能根据显存预算与目标任务制定 r、α、target modules；交付具有客观评测提升的行业任务微调模型。

### LangChain（必备）

- 核心学习内容：熟悉 LangChain Expression Language（LCEL）、Runnable Graph、Agent Executors 与 Toolkits；掌握 Memory、Retriever、Callback、LangGraph 等核心组件的扩展方式；了解与 OpenAI、Azure、Anthropic、vLLM 等常见后端的集成配置。
- 达成标准：能从零设计多阶段 Agent/RAG 流程，封装自定义工具与回调监控；能在线上项目中实现鲁棒的错误处理、并发控制、追踪日志，并优化推理成本与延迟。

### LlamaIndex（推荐）

- 核心学习内容：理解 Index、Retriever、Query Engine、Response Synthesizer、Observability 架构；掌握多文档融合（Tree/Graph Index）、Hybrid Retriever、Context Compression、Agentic RAG 实践；熟悉 LlamaIndex 与向量库、SQL、Graph 数据源的联邦检索。
- 达成标准：能将异构企业文档接入并构建高召回 RAG 流程，优化 chunk 策略与 rerank；在生产环境中部署 LlamaIndex Observability，提供响应链路与提示调优依据。

### AutoGen（推荐）

- 核心学习内容：了解多 Agent 协作框架、角色管理、会话调度和函数调用机制；掌握 GroupChat、Swarm、AgentGraph 等高级协作模式；熟悉将 LangChain/LlamaIndex 工具链接入 AutoGen 的方法。
- 达成标准：能构建任务分解、评审、执行的多 Agent 流程，并实现持久化记忆与日志；能针对复杂业务（如代码审查、数据分析）达成稳定产出，具备监控与回退策略。

### RAG 架构（必备）

- 核心学习内容：掌握检索增强生成的系统设计，包括索引策略、向量化、召回/重排、上下文拼接、生成融合；熟悉常见优化（分层检索、压缩、缓存、后处理）与评估指标（Faithfulness、Relevance、Latency）。
- 达成标准：能从业务需求出发规划数据管道、特征工程与检索层；通过离线/在线评估证明改进效果，并持续监控幻觉率与响应时延。

### Faiss（必备）

- 核心学习内容：理解向量相似度搜索算法（IVF、PQ、HNSW、OPQ）、GPU/CPU 混合部署策略；掌握 Faiss Index 构建、训练、更新与压缩流程；熟悉批量查询、量化误差、分片与容灾实践。
- 达成标准：能选择合适索引结构满足百万级向量高并发检索需求；编写高效的索引管理脚本，并在实际项目中完成性能压测与优化。

### Milvus（推荐）

- 核心学习内容：熟悉 Milvus 架构（QueryNode、DataNode、IndexNode）、分布式部署、分区/集合设计；掌握 Hybrid Search、向量+标量过滤、TTL、备份恢复；了解 Milvus 与 Cloud-native（K8s、KubeRay）结合的最佳实践。
- 达成标准：能搭建高可用集群，设计符合业务的分片策略和数据生命周期；监控 QPS、延迟、资源占用，支撑线上 RAG/推荐场景稳定运行。

### pgvector（推荐）

- 核心学习内容：理解 PostgreSQL 扩展机制、IVFFlat/HNSW 索引、向量操作函数；掌握 JSONB、全文检索与向量检索混合查询；熟悉数据库调优（autovacuum、statistics、并行查询）。
- 达成标准：在已有 PostgreSQL 基础上实现一体化结构化+向量检索服务；完成性能基准测试并提供索引维护、冷热数据分层方案。

### Next.js App Router（必备）

- 核心学习内容：掌握 App Router 文件约定、Server/Client Components 边界、Route Handlers、Streaming、Middleware；熟悉 Edge Runtime、Incremental Static Regeneration、服务器动作（Server Actions）与缓存策略。
- 达成标准：能独立搭建全栈 AI 原型应用，优化首次渲染与交互性能；实现鉴权、API 集成、国际化等生产级需求，并通过 Lighthouse/监控指标验证质量。

### React Server Components（必备）

- 核心学习内容：理解 RSC 架构、序列化规则、数据获取模式与 Suspense/Transition 机制；掌握 RSC 与客户端组件协同、状态管理与缓存边界；熟悉与 Prisma、tRPC、AI SDK 等服务数据的无缝对接。
- 达成标准：能在大型应用中合理划分 Server/Client 组件，降低 bundle 体积与水合开销；能诊断和解决 RSC 异常（如 useEffect 限制、Context 传播）并提供最佳实践文档。

### Tailwind CSS（必备）

- 核心学习内容：掌握原子化类、设计系统抽象、Dark Mode/Theme、自定义插件与配置；熟悉与 CSS-in-JS、Design Token、UI 库（Headless UI, Radix）集成；了解 Tailwind 与响应式、动画、可访问性策略。
- 达成标准：能在团队项目中建立一致的组件规范与样式约束；实现高度可维护的 UI 组件库，并通过视觉回归/可访问性测试验证效果。

### Node.js 运行时（必备）

- 核心学习内容：理解事件循环、异步模型、Worker Threads、Streams、诊断工具（Profiler、Heap Snapshots）；熟悉 Node.js 20+ 特性（fetch、test runner、权限模型）、性能调优与安全加固。
- 达成标准：能定位生产环境内存泄漏、阻塞、崩溃等问题并给出解决方案；编写高性能服务端程序，满足高并发与低延迟指标。

### NestJS（必备）

- 核心学习内容：掌握模块化架构、依赖注入、管道/拦截器/守卫、微服务与消息队列支持；熟悉配置管理、缓存、调度任务、OpenAPI/Swagger 集成；了解与 Prisma、TypeORM、Redis、gRPC 的整合方式。
- 达成标准：能设计中大型后端项目的分层结构与领域模型；实现统一日志、异常处理、配置治理，并通过全面测试确保上线质量。

### Express 插件化架构（推荐）

- 核心学习内容：理解 Express 中间件体系、Router 装载、插件化扩展模式；掌握性能优化（Cluster、负载均衡）、安全加固（Helmet、Rate Limit）、请求生命周期调优；熟悉与 Vite SSR、Next.js API Routes 等协同方式。
- 达成标准：能为现有应用抽象可维护的插件化骨架，支持可插拔的认证、监控、限流模块；在高流量场景下维护稳定指标并提供回归测试。

### PostgreSQL（必备）

- 核心学习内容：熟悉事务隔离级别、锁机制、查询计划、索引设计、分区与复制；掌握 JSONB、CTE、物化视图、全文检索、逻辑复制与备份恢复；了解性能监控（pg_stat_statements、auto_explain）与调优方法。
- 达成标准：能设计复杂数据模型并优化查询性能；保障线上数据库的高可用与安全策略，提供容量规划与灾备演练方案。

### Prisma（必备）

- 核心学习内容：掌握 Schema 建模、迁移管理、Prisma Client 查询模式、Middleware/Extension、自定义生成器；熟悉与 Next.js、NestJS、tRPC、PlanetScale/Supabase 的集成；了解 Prisma Accelerate、Data Proxy 等云特性。
- 达成标准：能维护复杂领域模型的类型安全与性能；搭建 CI 数据迁移流程、写入审计与调试工具，确保多环境一致性。

### Redis（必备）

- 核心学习内容：理解数据结构（String、Hash、Set、Sorted Set、Streams）、事务与 Lua、发布订阅、Cluster/Sentinel 架构；熟悉持久化（RDB/AOF）、过期策略、内存管理与安全加固；掌握缓存穿透、雪崩防护与热点优化。
- 达成标准：能设计高可靠的缓存/消息/队列系统，提供监控告警与容量规划；在实战中验证缓存策略对延迟与吞吐的提升。

### Docker（必备）

- 核心学习内容：掌握镜像构建优化、多阶段构建、构建缓存、Slim 镜像；熟悉容器网络、存储卷、安全策略、Compose/BuildKit；了解 GPU 支持、CI/CD 集成与镜像签名/扫描。
- 达成标准：能为 AI 推理与训练任务构建高效可复现的容器环境；维护镜像仓库治理、漏洞修复与部署流水线，满足合规要求。

### Kubernetes（必备）

- 核心学习内容：理解核心组件、控制器、调度器、Ingress/Service、StatefulSet、HPA/VPA；掌握 Operators、Helm、Kustomize、GitOps（Argo CD）、Service Mesh（Istio/Linkerd）；熟悉 GPU Operator、KubeRay、Knative 等 AI/MLOps 扩展。
- 达成标准：能部署并运维生产级 K8s 集群，实现自动扩缩容、资源隔离、故障自愈；为 AI 任务设计 Job/Serving 管道并制定 SLO/监控报警策略。

### OpenTelemetry（必备）

- 核心学习内容：掌握 Trace/Metrics/Logs 数据模型、SDK/Collector 部署、采样与导出策略；熟悉与 Prometheus、Grafana、Jaeger、Tempo、Honeycomb 等后端集成；了解对 LangChain、NestJS、Next.js 的自动/手动埋点方法。
- 达成标准：能在全栈应用中实现端到端可观测闭环，提供可视化仪表盘与告警；通过数据分析定位性能瓶颈与异常，支持持续改进。

### 安全审查流程（必备）

- 核心学习内容：了解模型发布与数据合规要求，熟悉威胁建模、风险登记、审批节点、审计追踪；掌握渗透测试、红蓝对抗、第三方评估、应急响应流程；参考 ISO/IEC 42001、NIST AI RMF 等标准。
- 达成标准：能为团队制定并执行 AI 项目安全审查手册，覆盖数据采集、模型训练、部署上线全过程；定期复盘与演练，确保满足监管与客户要求。

### 提示注入防护（必备）

- 核心学习内容：掌握 Prompt Injection、越狱、数据泄露攻击原理；熟悉分层防护策略（输入清洗、上下文隔离、安全模型评估）；了解 Guardrails、Azure Content Safety、Llama Guard、LangChain 官方安全工具。
- 达成标准：能设计测试集与自动化评估流程，验证防护策略有效性；在生产系统中部署拦截、告警与响应机制，显著降低高风险事件。

### 数据脱敏与治理（必备）

- 核心学习内容：熟悉脱敏技术（脱标、加密、同态、差分隐私）、数据分级分类、血缘与目录管理；了解数据访问控制、审计留痕、数据保留策略；掌握主流工具（Immuta、OneTrust、Atlas、Apache Ranger）与法规要求。
- 达成标准：能设计落地的脱敏策略与治理流程，覆盖开发、测试、生产环境；通过审计证明满足监管与客户合规，持续跟踪改进。

### 远程协作能力（必备）

- 核心学习内容：掌握跨时区协作流程、Async Communication、文档化决策、工具链（Notion、Linear、Confluence）使用；了解会议主持、反馈循环、冲突管理技巧；熟悉远程团队文化建设与绩效评估方法。
- 达成标准：能主导远程项目计划、同步、回顾，确保团队信息对齐与承诺；在分布式团队中保持高响应与透明度，获得同事正向反馈。

### 产品思维（必备）

- 核心学习内容：理解需求分析、用户画像、价值假设、指标设计（AARRR、North Star）、实验设计；掌握产品路线规划、迭代策略、MVP 构建与需求优先级框架（RICE、MoSCoW）。
- 达成标准：能将 AI 技术方案转化为可交付的产品体验，主导需求澄清、指标设定与复盘；在跨职能团队中平衡技术可行性与商业价值。

### 技术英语（必备）

- 核心学习内容：提升技术阅读、写作、会议表达能力；熟悉 RFC、白皮书、API 文档、PRD 等专业文本；掌握英文演讲、异议处理、跨文化沟通技巧。
- 达成标准：能独立阅读最新论文、标准与开源文档并输出总结；在国际会议或与海外团队合作中流利表达观点并推进项目。

## 学习优先级（偏前端与工程向全栈角色）

面向以前端为主、同时承担工程化交付的全栈角色，建议以“核心交付 → 项目深化 → 软技能守护”的节奏滚动推进，确保能快速上线 AI 产品并持续稳定迭代。

- **第一梯队（4–6 周核心夯实）**

  - _AI 基础_：`Transformer 原理`、`Prompt Engineering`。
  - _前端交付_：`Next.js App Router`、`React Server Components`、`Tailwind CSS`。
  - _后端 & 运行时_：`Node.js 运行时`、`NestJS`。
  - _数据层_：`Prisma`、`PostgreSQL`、`Redis`。
  - _AI 编排与检索_：`LangChain`、`RAG 架构`、`Faiss`（或 `Milvus`，建议先从 Faiss 入手）。
  - _工程保障_：`OpenTelemetry`、`安全审查流程`、`提示注入防护`。

- **第二梯队（项目并行深化）**

  - _AI 能力拓展_：`参数高效微调 (LoRA)`、`LlamaIndex`、`AutoGen`。
  - _数据与检索延伸_：`pgvector`。
  - _后端体系补强_：`Express 插件化架构`。
  - _工程运维_：`Docker`、`Kubernetes`。

- **第三梯队（贯穿全程持续强化）**
  - _数据治理_：`数据脱敏与治理`。
  - _软技能_：`远程协作能力`、`产品思维`。
  - _语言能力_：`技术英语`。

## 参考资料

- 市场现状与经验差距分析请参见 `market-gap-analysis.md`。
- 学习路径与行动计划请参见 `next-step-actions.md`。

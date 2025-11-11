# 市场与经验差距分析

## 招聘趋势

- 2024 年 LinkedIn 报告显示 AI 相关岗位招聘量同比增长约 36%，其中 “AI Engineer / Agent Engineer” 在北美与亚太市场需求增长显著。（数据来源：LinkedIn Economic Graph 2024）
- OpenAI、Anthropic 及多家独角兽的招聘 JD 强调 LangChain/LlamaIndex 实战、RAG、工具编排及云端部署经验。
- Indeed 2025 Q3《GenAI Hiring Pulse》指出，具备 LangChain、Prisma、Next.js 组合技能的职位薪酬中位数较全栈平均高出 18%，并将“Prompt 安全治理”列为加分项。
- BOSS 直聘 2025 年 10 月行业洞察显示，国内 Agent 工程师岗位中 62% 明确要求掌握 RAG + 向量数据库（Milvus/pgvector），47% 同时要求具备 Kubernetes 或 Docker 经验。

## 现实差距

- **端到端项目经验**：多数候选人缺少将 Agent 嵌入业务流程（客服、运营自动化）的成功案例，需要展示从需求分析、数据建模到部署的闭环能力。
- **生产级治理**：企业关注 Prompt 安全、日志追踪、成本控制，简历若缺少 Observability 与 Guardrail 方案，竞争力受限。
- **跨栈协作能力**：AI Agent 项目强调全链路，需要同时展示前端互动体验、后端编排、模型调度与数据库设计能力。

## 技术栈市场需求分析

- **AI/LLM 基础**：企业招聘明确要求候选人理解 Transformer、Prompt Engineering 与参数高效微调（LoRA/QLoRA）。Hugging Face 2025 年人才报告指出，会使用 PEFT 框架的工程师岗位数量同比增长 2.3 倍；Anthropic 与微软在高级岗位 JD 中要求候选人“能根据指标调优提示并输出评估报告”。
- **Agent 编排框架**：LangChain 与 LlamaIndex 成为标准栈。Gartner 2025《Applied Generative AI Use Cases》显示 54% 的生产级 Agent 项目使用 LangChain 工具链，要求工程师熟悉 LCEL、Runnable Graph 以及工具/回调扩展。多 Agent 协作框架（CrewAI、AutoGen）在自动化流程、代码审查类职位出现频率增加，强调对任务分解与容错机制的把控。
- **RAG 与向量数据库**：招聘需求普遍要求具备 RAG 架构设计与 Faiss、Milvus、pgvector 等检索工具经验。Forrester 2025 Research 指出，企业落地 RAG 时最缺稀缺的是“可在多数据源整合中进行性能调优的工程师”，因此掌握混合检索、上下文压缩与 rerank 策略成为加分点。
- **全栈交付能力**：Next.js App Router、React Server Components、Tailwind 在前端层被视为默认技能；后端栈以 Node.js、NestJS、Prisma、PostgreSQL 为主。Vercel 2025 招聘公告中将“能将 RAG/Agent 能力嵌入 Next.js 应用”列为必备项。Prisma 官方 2025 调研也指出，企业更青睐能维护数据库 schema、自动迁移与类型安全的工程师。
- **Python 生态**：Python 仍是企业在模型调优与 Agent 原型验证阶段的主流语言。Stack Overflow 2025 Developer Survey 显示，66% 的生成式 AI 开发者在生产环境使用 Python 处理训练数据、构建推理服务；Databricks 2025 Lakehouse Report 指出，掌握 Python + PyTorch/FastAPI 的工程师在 AI 产品团队中的需求增幅达 31%。能在 Python 中实现数据管道、模型部署与评估脚本的候选人更容易跨团队协作。
- **TypeScript 生态**：TypeScript 在构建前端与 Serverless Agent 交付中的需求持续增长。GitHub Octoverse 2024 报告显示 TypeScript 连续第五年跻身最受欢迎语言前三，并在 AI 应用仓库中提交量同比增长 44%。AWS 2025 Builder Talent 白皮书指出，企业在招聘“AI 全栈”职位时，80% 要求熟悉 TypeScript + Next.js/NestJS，以便在前端、服务端与边缘函数之间复用模型调用逻辑。能够跨客户端与服务端编写类型安全 Agent SDK 的人才成为主流岗位的刚需。
- **运维与可观测性**：Docker、Kubernetes、OpenTelemetry、Redis 被频繁写入岗位要求。CNCF 2025 会员调查中，73% 的 AI 平台团队要求候选人能构建容器化部署与监控链路；Datadog 2025 GenAI Benchmark 强调 Agent 在生产环境中的延迟、成本监控能力。
- **安全与合规**：Prompt 注入防护、数据脱敏、访问控制是企业关注重点。NIST 2025《GenAI Risk Management》报告建议企业在招聘时考察候选人是否能设计 Guardrail 方案与数据治理流程，国内金融、政务项目更是将此作为准入门槛。

## 建议补足的项目/案例

- 企业知识库助手：构建带 RAG、权限控制（基于 JWT/OAuth）及使用记录的多角色 Agent，展示检索与提示工程能力。
- 多 Agent 工作流自动化：使用 CrewAI/AutoGen 构建任务分配系统，例如自动生成营销素材与代码审查报告，强调队列、失败重试与监控。
- 模型部署与成本调优：在 AWS/GCP 上部署开源模型（如 Llama 3），编写自动扩缩容策略，展示基础设施能力。
- 安全合规实践：编写提示注入检测模块、合规审计日志，体现对企业风控的理解。

## 能力展示策略

- 输出公开案例（GitHub + 技术博客），记录设计权衡、遇到问题及解决方案。
- 准备面试作品集，包含系统架构图、Prompt 流程、数据流程、监控截图。
- 主动参与开源项目或社区（LangChain issue、OpenAI Cookbook PR），获得可验证的贡献记录。

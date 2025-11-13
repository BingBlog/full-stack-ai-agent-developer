# 前端技术栈与工程实践

## JavaScript 与 TypeScript 核心

1. [频率:高][难度:易] 描述 JavaScript 事件循环的宏任务与微任务执行顺序。 提示：区分 call stack、task queue、microtask queue。
2. [频率:高][难度:易] 解释闭包的概念，并举例说明可能引发内存泄漏的情形。 提示：自由变量、函数返回、DOM 引用。
3. [频率:高][难度:中] TypeScript 类型系统中 `unknown`、`any`、`never` 有何区别？ 提示：类型安全、收窄、不可达。
4. [频率:中][难度:中] 描述原型链查找流程，以及 `Object.create` 与 `class` 语法的关系。 提示：`[[Prototype]]`、继承、性能。
5. [频率:中][难度:难] 解释 JavaScript 内存管理与垃圾回收算法（标记-清除、分代 GC）。 提示：reachability、老生代/新生代。
6. [频率:中][难度:难] 如何利用 TypeScript 条件类型与映射类型实现深层 Partial/Readonly？ 提示：递归类型、`extends`、`keyof`。
7. [频率:低][难度:难] 描述 JavaScript 引擎的即时编译（JIT）流程及对性能的影响。 提示：热点函数、内联缓存、反优化。

## React 生态

1. [频率:高][难度:易] 解释 React Fiber 调度的目的，以及 concurrent mode 的优势。 提示：优先级调度、可中断渲染。
2. [频率:高][难度:易] 对比 `useEffect` 与 `useLayoutEffect` 的执行时机，提供使用场景。 提示：布局同步、副作用、闪烁。
3. [频率:高][难度:中] 描述 React Server Components 的数据获取与客户端交互流程。 提示：RSC payload、边界、客户端组件。
4. [频率:中][难度:中] 如何优化列表渲染性能？说明 key、虚拟列表、选择性 memo 的策略。 提示：diff、窗口化、`React.memo`。
5. [频率:中][难度:中] 解释 Context 的局限性以及如何借助自定义 hook/selector 减少重渲染。 提示：分片订阅、`useSyncExternalStore`。
6. [频率:中][难度:难] 对比 React Query、SWR、Apollo 在数据同步与缓存策略上的差异。 提示：stale-while-revalidate、乐观更新、规范化缓存。
7. [频率:低][难度:难] 描述使用 Suspense for Data Fetching 构建流式体验时的边界条件。 提示：fallback、error boundary、prefetch。

## Vue 生态

1. [频率:高][难度:易] 对比 Vue 2 Options API 与 Vue 3 Composition API 的核心差异。 提示：响应式粒度、逻辑复用、类型支持。
2. [频率:高][难度:易] 解释 Vue 3 响应式系统中 `reactive`、`ref`、`computed` 的内部机制。 提示：Proxy、依赖追踪、scheduler。
3. [频率:高][难度:中] 描述虚拟 DOM patch 流程以及 `block tree` 的优化作用。 提示：静态提升、patch flag。
4. [频率:中][难度:中] 说明 Vue Router 4 的动态路由加载与导航守卫最佳实践。 提示：懒加载、`beforeEach`、权限控制。
5. [频率:中][难度:中] 在大型项目中如何使用 Pinia 或 Vuex 设计模块化状态？ 提示：store 拆分、插件、中间件。
6. [频率:中][难度:难] 指出 Vue SSR/Nuxt 渲染流程中的常见坑位与调试方法。 提示：hydrate mismatch、异步数据、缓存。
7. [频率:低][难度:难] 描述 Vue 组件编译器如何从模板生成渲染函数。 提示：AST、codegen、静态提升。

## 状态管理与数据流

1. [频率:高][难度:易] 对比 Redux、MobX、Zustand 在数据流与心智模型上的差异。 提示：单向流、响应式、选择器。
2. [频率:高][难度:易] 解释不可变数据结构的重要性，并举例说明 `immer` 的应用。 提示：结构共享、Proxy、可读性。
3. [频率:中][难度:中] 如何在 React/Vue 中处理跨 tab 或多端同步状态？ 提示：BroadcastChannel、IndexedDB、后端推送。
4. [频率:中][难度:中] 描述 GraphQL + Apollo/Urql 在状态管理中的角色。 提示：规范化缓存、客户端 schema、离线支持。
5. [频率:中][难度:难] 在设计复杂表单或流程编排时，如何划分局部状态与全局状态？ 提示：状态图、职责拆分、性能。
6. [频率:低][难度:难] 如何将状态机/状态图（XState）集成到前端项目以提升可视化与可测试性？ 提示：statechart、动作、持久化。
7. [频率:低][难度:难] 分享一次你处理状态竞争条件或并发更新的经验。 提示：原子操作、队列、锁。

## 工程化与构建工具

1. [频率:高][难度:易] 对比 Webpack 与 Vite 的开发与构建流程差异。 提示：bundler vs dev server、ESBuild、Rollup。
2. [频率:高][难度:易] 解释 Tree Shaking 的原理，以及为何需要保持模块纯度。 提示：ESM 静态分析、副作用标记。
3. [频率:高][难度:中] 描述 Webpack Module Federation 的工作机制与适用场景。 提示：远程模块、共享依赖、版本约束。
4. [频率:中][难度:中] 如何利用 Vite 插件体系扩展编译能力？ 提示：插件钩子、`config`、`transform`、`handleHotUpdate`。
5. [频率:中][难度:中] 讲述 Source Map 的种类与在生产环境中的风险控制。 提示：inline、hidden、错误溯源。
6. [频率:中][难度:难] 在 CI/CD 中实现多包管理（pnpm workspace/Turbo repo）的最佳实践。 提示：依赖图、缓存、任务并行。
7. [频率:低][难度:难] 如何为 Webpack/Vite 编写自定义 Loader/Plugin？ 提示：AST 解析、Hook、tapable。

## 性能优化与监控

1. [频率:高][难度:易] 首屏性能优化常用指标有哪些？如何在 Lighthouse 中定位问题？ 提示：LCP、FID、CLS、瀑布图。
2. [频率:高][难度:易] 解释代码分割（Dynamic Import）与路由级别懒加载策略。 提示：bundle 切分、预获取、骨架屏。
3. [频率:高][难度:中] 描述浏览器渲染流程（解析 → 布局 → 绘制 → 合成）及常见阻塞因素。 提示：重排、重绘、GPU 合成。
4. [频率:中][难度:中] 如何在项目中落地 RUM（Real User Monitoring）采集？ 提示：PerformanceObserver、ErrorBoundary、上报策略。
5. [频率:中][难度:中] 解释 Service Worker 在缓存策略与离线能力中的作用。 提示：Cache API、Stale-While-Revalidate。
6. [频率:中][难度:难] 当需要优化 WebGL 或 Canvas 动画性能时，你会关注哪些指标？ 提示：帧率、批处理、纹理复用。
7. [频率:低][难度:难] 分享一次你通过性能画像定位前端瓶颈的案例。 提示：Chrome Profiler、火焰图、关键路径。

## 测试与质量保障

1. [频率:高][难度:易] 对比单元测试、集成测试、端到端测试的目标与覆盖范围。 提示：金字塔、测试金字塔、反馈速度。
2. [频率:高][难度:易] 描述使用 Jest/Vitest 编写 React/Vue 组件测试的基本流程。 提示：渲染、断言、模拟。
3. [频率:高][难度:中] 如何在 CI 中集成 Playwright/Cypress 的并行执行与截图对比？ 提示：工作流、artifact、flaky 处理。
4. [频率:中][难度:中] 解释 Contract Testing（Pact）在前后端协作中的价值。 提示：契约文件、Mock、回归保护。
5. [频率:中][难度:中] 描述静态代码质量工具（ESLint、TypeScript、Prettier）的组合策略。 提示：lint-staged、规范、自动修复。
6. [频率:中][难度:难] 如何设计可测性良好的组件/模块？ 提示：依赖倒置、Pure Function、可插拔。
7. [频率:低][难度:难] 分享一次你建设可观测性+测试联动体系的经验。 提示：错误追踪、回放、告警联动。

## 架构设计与项目实践

1. [频率:高][难度:易] 描述你常用的前端目录与模块组织方式，以及如何保持一致性。 提示：按业务/功能、约定规范、脚手架。
2. [频率:高][难度:易] 解释微前端架构的优缺点，并举例适用场景。 提示：自治团队、构建拆分、运行时隔离。
3. [频率:高][难度:中] 在多模块协同时如何治理共享组件与设计系统？ 提示：组件库、Storybook、版本策略。
4. [频率:中][难度:中] 描述一次从传统 SSR/SPA 迁移到同构或边缘渲染的过程。 提示：渐进迁移、缓存、监控。
5. [频率:中][难度:中] 前端与后端/AI 服务协作时，接口契约与错误治理如何制定？ 提示：OpenAPI、错误码、熔断。
6. [频率:中][难度:难] 在敏捷迭代中维护技术债与架构演进的策略是什么？ 提示：Tech Radar、重构节奏、指标。
7. [频率:低][难度:难] 分享一次你在复杂项目中保障可维护性与可扩展性的实践。 提示：领域划分、代码审查、自动化。
8. [频率:低][难度:难] 描述团队如何落地知识共享与技能梯度建设，支撑持续交付。 提示：Guild、双轨培养、学习平台。

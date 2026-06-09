# zhangyu1818 · 代码视角用户画像

> 评估对象：GitHub [@zhangyu1818](https://github.com/zhangyu1818)　|　生成日期：2026-06-09
>
> 方法：对 **131 个自有仓库**逐个 clone/读源码、**13 个外部开源 PR** 逐个分析 diff，全程 Claude Opus 评估；**每个仓库均以其创建当年的技术标准衡量**，不以今天的标准苛责早年代码。
>
> 评分为 1–10 绝对分（10=该年代专家/资深级，5=合格普通，1=trivial/初学者）。

---

## 📊 综合评分卡

| 维度 | 工程仓库·加权 | 全部仓库·加权 | 2026前·自写为主 | 2026后·AI为主 |
|---|:---:|:---:|:---:|:---:|
| 仓库功能完成度 | 6.7 | 6.4 | 6.3 | 8.1 |
| 作者代码水平 | **6.6** | 6.3 | 6.1 | 8.6 |
| 作者技术水平 | **5.9** | 5.5 | 5.4 | 7.3 |

- 自有仓库 131 个：其中**工程仓库 118 个**、文档转储/空仓 13 个；2026 前 120 · 2026 后 11；检出 AI 参与迹象 28 个
- **「工程仓库·加权」列为主参考**（剔除纯文档转储与空仓，与正文画像口径一致）；「全部仓库·加权」含文档转储故偏低
- 外部开源 PR 13 个（合并 11 个）
> 加权口径：`1 + log2(1+体积KB) + 2·log2(1+stars)`，弱化一次性玩具、放大有分量项目。

---

# 代码视角的用户画像 · zhangyu1818

> 数据来源：131 个自有仓库的逐仓源码审计 + 13 个外部开源 PR 分析。
> 评分均按各仓库**创建年代的技术标准**衡量，关注成长曲线而非现状切片。

---

## 一、总览与定位

**一句话画像：一位从 2019 年 React Hooks 首班车一路追到 2026 年 AI Agent 编排的、以「造轮子 + 追新 + 源码级钻研」为底色的资深独立前端开发者，正在完成从「手写库作者」向「AI 工作流总设计师」的身份跃迁。**

- **资历**：约 7 年可考的公开开发轨迹（2019-02 至 2026-06），起点即偏中上，2024 年后稳定在资深个人开发者水准。
- **方向主轴**：前端 / Web 工程（React 生态深耕）为绝对主干；以构建工具、组件库、动画库为长期副线；2021 起向 iOS/macOS 原生（Swift/SwiftUI）横向扩展；2024-2025 涉足 Rust/Go 系统与服务；2025 下半年起全面转向 AI 工程（MCP / Agent SDK / Skill 生态）。
- **风格**：典型的「痒点驱动 + 自给自足生态」型开发者——大量小工具库源自自己的真实痛点，且偏好用自研依赖（`@zhangyu1818/eslint-config`、`from-to.js`、`tw-styled`、`dark-toggle`、`motion-wave`、`create-context-factory` 等）相互组装出一个自洽的个人技术栈。

---

## 二、能力演进时间线（2019 → 2026）

### 阶段一：React 早期采用者（2019）
2019 年是其公开履历的起点，密度极高且**踩在范式更替的节点上**。React Hooks 于 2019-02 随 16.8 发布，而其 `react-music-app`（2019-02）、`blog-admin`/`react-markdown-editor`/`blog-server`（2019-04）即已用上 `useReducer`/`useContext`/`forwardRef`，`react-music-app` 甚至自造 `asyncDispatch` 中间件包裹 `useReducer`——在 Hooks 发布当月就敢用于生产级项目，是明确的早期采用者信号。同期 `filter-dropdown`（2019-04）启用了尚处 Stage-3 的 ES 私有字段。这一年也暴露了新手期的工程短板：`blog-admin` 三个列表页近乎逐行复制粘贴、渲染期 `setState` 反模式；`blog-server` 登录逻辑 `find()` 恒真的真实 bug。**代表作**：`react-markdown-editor`（已发布 npm 的 Markdown 编辑器）。

### 阶段二：库作者养成 + 源码钻研（2020-2021）
重心转向**「做发布级组件库」与「读源码」两条线**：
- 库作者线：`countdown-button`（设置 `__ANT_BUTTON` 静态标志，体现 antd 源码级理解）、`drag-resize`、`react-animate-skeleton`（用 `repeating-linear-gradient` 反向布局做骨架屏）、`piatto`（仿 antd 架构、配 React 16/17×source/lib/es 的 8-job CI 矩阵）、`switch-button`（Proxy 响应式）。工具链从 `father`/`dumi` 到自研 `lib-tool`/`cjsb`/`tikka`/`rollib`，开始系统性地造构建工具。
- 源码钻研线：`redux-sourcecode-study`、`react-redux-sourcecode-study`（啃下 556 行的 `connectAdvanced`）、`observer`（复刻 Proxy 响应式内核）、`stupid-events`（复刻 React 17 事件委托）、`react-observed-context`（挖 React 16/17 未公开的 Context bitmask API）、`react-hooks-analysis`（源码级分享 PPT）。这条线把他的 `techLevel` 上限明显抬高。
- 横向探索起步：`clocks-widget`（2021-01 即上架 App Store 的 iOS WidgetKit 透明组件，逐机型像素裁剪）、`flutter-todo-list`，开始触碰原生与跨端。

### 阶段三：稳定的资深前端 + 自研生态成型（2022-2024 上半年）
进入「资深个人开发者」稳定区。工具链全面现代化（Vite/Tauri/pnpm/SWC），并形成**自研依赖互相喂养**的生态：`from-to.js`（弹簧物理动画）→ `motion-wave` → `wave-button`/`theme-bg` 一脉相承；`dark-toggle`（序列化函数源码内联防闪烁）、`tw-styled`、`create-context-factory`、`@zhangyu1818/eslint-config` 成为其后续几乎所有应用的基础设施。代表作 `appicon-forge`（功能性 9、完整渲染引擎 + 虚拟化）、`speedtest-ui`（Tauri 2 sidecar）、`eng-learn`（二分查找定位字幕 + 去抖）。

### 阶段四：RSC / 前沿范式冲浪（2023 末-2024）
对 React 前沿范式的嗅觉是其高光。`rsc-example`（2023-12，在 Server Actions / `useFormState` 刚落地时就跑通 RSC + TanStack Query 水合）、`react-server-only-context`（2024-03，用 `React.cache()` 在 RSC 里造请求作用域上下文，并在 README 引用官方 RFC 剖析 LIFO 栈失效）、`rsc-mdx`、`react-markdown-toc`（RSC 双形态）、`blog` 的 next14 重写（自研 rehype 插件 + Shiki Twoslash + p2-es 物理引擎 Galton 板）。同期 `r3f-100-exercises`/`three-study`/`three-falling-cubes`（Web Worker + Rapier 物理）展开**图形/Three.js 深耕**，技术深度触顶。

### 阶段五：原生与系统语言扩张（2024-2025）
- Swift/iOS-macOS 原生持续加深：`share-play-swiftui-example`、`swiftui-playground`、`ScreenCaptureRecorder`、`tingwu`（Rust objc2 裸 FFI 接 ScreenCaptureKit + 非 Send 对象线程隔离 + V3 签名）、`TypeFree`（VoiceInk fork + 多 ASR 引擎）。
- Rust/Go 系统侧：`pr-finder`（Rust CLI，体积优化到 2MB）、`wasm-vs-js`、`qwen3-compatibility`（Go 网关）、`anthropic-gateway`（Go，地道的 adapter/slog/优雅关停）。

### 阶段六：AI 工程总设计师（2025 下半年-2026）
身份发生**质变**：从写代码的人变成**指挥 AI 写代码并为其设定工程纪律的人**。标志物有三类：
1. **AI 知识库供给**：大量 `*.md` / `*-docs-cursor` 文档转储仓库（StoreKit/Swift/SwiftUI/CoreML/ScreenCaptureKit/apple-docs-for-rag）——把官方文档抓成 RAG 语料喂给 deepwiki/Cursor/LLM。
2. **AI 工具产物**：`xcode-i18n-mcp`（README 自承 100% by Claude）、`vercel-react-best-practices-report`（Agent SDK 编排审计）、`task-while`、`codex-feishu`、`Mermaid-AI`（v0/AI Studio 生成）。
3. **AI 工程纪律固化**：`oxlint-config`/`eslint-config`（自带 `setup-*/SKILL.md` Claude Skill）、`skills`（个人 Agent 技能库）、`cue`/`Portal`/`llm-intro`（CLAUDE.md + superpowers 计划文档 + 严格 lint 驱动的高质量 AI 协同交付）。

---

## 三、作者代码水平评估

**加权综合代码水平：7.3 / 10（按年代加权；剔除文档转储/空仓后的「真实工程仓库」均值约 6.8，高水位稳定在 8-9）。**

加权口径说明：约 15 个文档转储仓库（codeQuality 多为 2-5）与 2 个空仓（1 分）在数量上稀释了均值，但它们本质是「数据托管」而非「写代码」，故在画像判断中降权处理；真正承载工程能力的库/应用仓库，2019 起步多在 5-6，2020-2021 升至 6-8，2023 后稳定在 7-9（`appicon-forge` 8、`eng-learn` 8、`react-markdown-toc` 8、`piatto` 8、`switch-button` 8、`react-server-only-context` 8、`cue`/`Portal`/`llm-intro` 9、`vercel-react-best-practices-report` 9、`codex-feishu` 9、`oxlint-config` 9）。这条上行曲线本身就是评分的核心证据。

**分年代分层评价（严格按当年标准）：**
- **2019（起步，约 5-6）**：范式追得快但工程纪律差。复制粘贴（`blog-admin` 三页 DRY 缺失）、渲染期 `setState`、`find()` 恒真 bug、私钥入库（`html5-camera-demo` 的 `server.pem`）是该期典型坏味道。按 2019 标准属「紧跟潮流的合格中级」。
- **2020-2021（成型，约 6-7.5）**：开始出现「源码级洞察」（`__ANT_BUTTON`、Context bitmask）和「工程链完整度」（`piatto` 的 CI 矩阵、`dynamic-stylesheet` 的 Jest+CI+Codecov）。坏味道收敛为「全局可变单例」「闭包陈旧（空依赖数组）」这类更高级的问题。
- **2022-2024（资深，约 7-8.5）**：类型设计地道（模板字面量类型、泛型条件类型、`Omit` 收窄），架构分层清晰，自研生态自洽。短板高度一致：**几乎全员无测试/无 CI**。
- **2025-2026（AI 协同，约 8-9）**：代码质量反而创新高，但**这是「人定纪律 + AI 执行」的合奏**——`max-lines: 300`、`no-floating-promises`、零 `any`、测试/实现近 1:1（`task-while` 244 测试、`codex-feishu` 58 用例）等是 lint 规则与人工架构在约束 AI 产出。

**代码风格特征**：无注释偏好（与其全局 CLAUDE.md 的 no-comment 规则一致）；命名地道、类型表达力强；偏好 Proxy / 函数式 / ref-based 的「巧思型」实现；中文口语化注释里常见自嘲（「逻辑绕了」「自己菜的绝望」「这次一定要坚持✊」），是其代码人格的鲜明指纹。

**贯穿始终的坏味道（务必点名）**：①**测试是其最大且最持久的工程短板**——从 2019 到 2024 的库/应用绝大多数零测试，直到 2025-2026 借 AI/严格 lint 才系统补齐；②**完成度参差**：多个仓库 README 残留脚手架默认文案（`eng-learn`、`rsc-example`、`mp3-vtt` 的 `package.json name='srt'`）、`// todo`、被注释的旧实现、调试 `print/dbg!/console.log` 残留；③早期的安全疏漏（私钥入库、硬编码密钥、客户端侧签名暴露 AK/SK）。

---

## 四、作者技术水平评估

**加权综合技术水平：7.0 / 10（库/应用仓库的高水位长期在 7-9，文档转储拉低均值）。**

**技术深度的高点（每点附证据）：**
- **源码级研究能力（深度 8-9）**：能挖到并使用 React 未公开的 Context bitmask（`react-observed-context`，`React.useContext(ctx, observedBits)`）；用 `React.cache()` 造 RSC 上下文并剖析其 LIFO 栈失效（`react-server-only-context`）；逐行注释 `connectAdvanced` 并自写精简版 redux 验证理解。这是其技术天花板最高的一条线。
- **构建工具/库作者（深度 6-7，广度极大）**：`lib-tool`/`cjsb`/`tikka`/`rollib`/`tscb`/`cjsb` 一系列「file-to-file 双格式输出」构建器，对 Babel/SWC/Rollup/tsc 多引擎、`dependency-tree` 裁剪、双 ESM/CJS 发布的工程细节烂熟。`tikka` 的 `withPostcss` 高阶 transform 装饰 `outputFile` 体现真实抽象品味。
- **RSC / 前沿范式（深度 7-8）**：在 Server Actions / `useFormState` / `React.cache` 刚发布的窗口期即正确落地，技术嗅觉是其最稀缺的资产。
- **图形 / Three.js（深度 6-8）**：`r3f-100-exercises` 实现 GPU Navier-Stokes 流体（涡量约束/压力迭代）并 GLSL + TSL/WebGPU 双版本移植；`three-falling-cubes` 把 Rapier 物理放进 Web Worker 并用 transferable buffer 零拷贝。
- **跨端 / 系统级（深度 6-8）**：`clocks-widget` 逐机型像素裁剪；`tingwu`/`cue` 用 objc2 裸 FFI 接 ScreenCaptureKit、AXObserver C 回调桥接、actor 隔离非 Send 对象——这类系统调用是 AI 难以凭空稳定生成、必须人工领域知识兜底的部分，含金量高。

**短板与取舍：**
- **明显的「广度优先、深度选择性」**：技术广度惊人（React/Vue-Slidev/Swift/Flutter/Rust/Go/WASM/Three.js/Tauri/MCP 全都碰过），但深度集中在少数兴趣点（React 源码、构建工具、RSC、图形）。算法与系统底层是相对洼地——`leetcode`/`LeetCode-Note` 仅停在 easy/medium 且多处用暴力解不达复杂度要求，`number-to-chinese-characters` 超万亿即单位错乱，`wasm-vs-js` 基准方法学不严谨（单次计时、刻意构造不公平对比）。
- **后端/数据深度有限**：`blog-server`/`koa-graphql-mongodb` 等 GraphQL 后端停在 demo 级，串行 await、明文密码、硬编码密钥，未触及性能/事务/安全的纵深。
- **「玩具/概念验证」比例偏高**：相当多高 `techLevel` 仓库（`react-server-only-context`、`react-observed-context`）作者自承实用性受限于概念验证级。深度更多体现为「理解之深」而非「打磨之久」。

---

## 五、开源协作能力

**协作能力分：8 / 10。**

13 个外部 PR（ant-design 系、react-component 系、umijs、vercel/next.js、antfu/eslint-config），合并率高（约 10/13 合并，未合并的 2 个 feature 中 1 个是首次尝试被否后立刻按维护者意见重提并合入，1 个是 next.js 官方 6 个月无人 review 后作者主动体面关闭，非技术性拒绝）。综合表现：

- **改动精准、克制、最小化**：多为 1 行级的 TS 定义/文档勘误（antd #22895 `string[]`→`React.Key[]`、#24393 补 `autoFocus`、next docs autoExpandParent 默认值、rc-select `notFoundContent` 类型），全部「定位准、零回归、当天合并」。
- **对大型代码库的真实理解**：含金量最高的是 bugfix 类——`rc-mentions` #32/#33 能从上游 antd issue 反向定位到底层 rc 库根因，用「复用既有 `measuring` 状态」「`key || value` 兜底向后兼容」的最小契合式修复；antd #26522 定位 `display:none` 下 `offsetWidth=0` 的隐蔽时序 bug，并用项目已有的 `rc-resize-observer` 事件驱动替代脆弱的手动测量，**边修边精简（净删行）**，体现对代码库与浏览器布局机制的双重理解。
- **沟通规范、有据可争**：严格遵循 PR 模板与中英双语文档同步规范；面对维护者质疑能用事实据理力争（antd #26492 modal 文档）；被要求补测试时坦诚「我对测试不太熟悉」但仍补齐回归用例（rc-mentions #32/#33）——这恰好印证了「测试是其短板」，但**态度上愿意补**。
- **生态视角成熟**：antfu/eslint-config #608 精准对应 Next.js Route Segment Config 官方文档补白名单，对工具链生态的理解到位。

**扣分项**：贡献以「低复杂度文档/类型勘误」为主，真正贯穿全链路的复杂贡献（next.js #66996，8 文件、向后兼容合并逻辑、配套 e2e）只有少数且未被合并。即「优质的开源公民，但尚非某个大型项目的核心贡献者」。

---

## 六、AI 把控能力专项评估（独立能力维度）

**AI 把控分：8.5 / 10。**

这是其 2025 下半年起最值得单独成项的能力，且**明显高于行业平均的「AI 滥用/堆砌」水平**。需区分三类产物：

**A. 低把控/低投入的生成物拼装（少数，是反例）**：`cloud-storage`（v0 生成两页登录 UI，名实不符）、`Mermaid-AI`（AI Studio 一键脚手架，仅改名 + 部署）、`openai-compatible-cosyvoice`（setup.py 占位符未改、entry_points 指向不存在函数、硬编码文件名并发冲突未清理）。这类暴露其早期或随手项目对 AI 产物**收尾审校不彻底**。

**B. 中等把控（合理胶水）**：`lighthouse-ci`（README 坦白 ChatGPT 生成，作者做需求定义/验证/分层）、`qwen3-asr-worker`/`qwen3-compatibility`（架构清晰、能诚实定位生产部署失败根因，但残留死参数、粗糙 SRT、重复注释）、`v2ray2clash`（AI 生成的测试与手改实现脱节，回归校验缺位）。

**C. 高把控（主导设计 + AI 执行，是其代表水平）**：`vercel-react-best-practices-report`（codeQuality 9：适配器模式 + 断点续跑队列 + 跨进程文件锁 + 原子写 + 44 测试全绿）、`task-while`（纯函数 kernel 解释器 + 六边形端口/适配器 + 244 测试）、`codex-feishu`（手写 JSONL JSON-RPC 客户端 + 最短唯一后缀算法 + 58 用例）、`cue`/`Portal`（Swift 系统级，objc2/AX/private NSPanel API 等 AI 难以稳定生成的部分人工兜底，CLAUDE.md 把平台约束写成可执行规范）、`llm-intro`（先写列出被拒方案与 YAGNI 边界的 spec，再用 superpowers agent 工作流逐章交付有审美的成品）、`oxlint-config`（自写 AST lint 插件 + 子进程实跑 + tarball 冒烟测试）。

**驾驭 AI 的水平判断：**
- **选题品味（强）**：选的题都顺当年趋势且有真实用途——MCP 工具、Agent 编排、ASR 兼容网关、为 React19/Compiler 定制的 lint 规则、给 AI 喂的文档语料。
- **工程整合度（强）**：靠**自维护的严格 lint 规则**（`max-lines: 300`、禁双重断言、`no-floating-promises`）+ **架构纪律**（端口/适配器、纯函数 kernel、模块边界）+ **CLAUDE.md/SKILL.md 把约束写成 AI 可执行规范** 三件套，把 AI 产物压在连贯架构里。
- **架构连贯性（强）**：高把控仓库的模块边界、依赖注入、测试覆盖均呈「人主导设计」特征，非无脑堆砌。**非平凡的人工定制**（系统级 FFI、GraphQL 嵌套分页、时间戳裁决、最短唯一后缀）是 AI 难以独立完成、证明其真实把控的关键证据。

**扣分项（防止评分虚高）**：①低把控反例确实存在且不止一个；②单次 squash 提交成为常态，开发演进不可考；③即便高把控仓库也偶留 AI 痕迹（`vercel-best-practices-report-viewer` 的 Dashboard.tsx 末尾保留 AI 自述注释 + 异常 import、8 个未用 shadcn 组件、默认 title/favicon 未改），说明「收尾品味」仍有提升空间。

---

## 七、性格与工作风格画像

- **好奇心广度：极高**。语言/范式雨露均沾（JS/TS/Swift/Dart/Rust/Go/GLSL/WGSL），框架追到最新（Next 16、React 19、Tailwind v4、ESLint 10、Tauri 2、oxlint）。选题从阿里云盘签名逆向、微信字体还原、SharePlay 一起看视频，到 GPU 流体、WASM 基准、飞书机器人遥控 Codex——跳跃且多元。
- **追新程度：标杆级**。Hooks 发布当月即用、RSC/Server Actions/`React.cache` 刚落地就上、Tauri 2 发布次月采用、Oxc/MCP/Agent SDK 一出即跟。**「踩在范式更替节点」是其最稳定的人格特征。**
- **造轮子偏好：强烈且成体系**。不满足于用现成方案，倾向自研并让自研依赖互相组装成个人生态；对「源码原理」有近乎执拗的钻研欲（多个 `*-sourcecode-study`、`observer`、`stupid-events`）。
- **深度钻研倾向：真实但选择性**。会为搞懂一个机制写近 900 行分析、复刻整个响应式内核；但钻研对象集中在感兴趣的少数领域。
- **产品化倾向：中等偏上但不彻底**。有数个真正上架/上线的成品（`clocks-widget` 上 App Store、`appicon-forge`/`blog`/`imessage-app-icon` 在线可用），但更多是「做出可用 demo 即转向下一个」。
- **完成度 / 虎头蛇尾倾向：明确存在**。空仓（`github-api-test`、`my-desktop-in-3d`）、未完成 WIP（`707.设计链表`语法残缺、`ScreenCaptureRecorder` 名为 Recorder 却不写文件、`tingwu` 自承三个月没做完存档、Windows 端空壳）、脚手架默认文案未清理反复出现。**「起一个新坑」的热情明显高于「填完旧坑」。**
- **审美：在线且持续提升**。动效/视觉类项目（`bg-css` 扫光、`wave-button`、`theme-bg` 圆形扩散、`appicon-forge`）有设计巧思；`llm-intro` 用物理引擎做「上下文窗口装不下就掉落」的隐喻，是技术审美的高点。
- **诚实**：README 常坦白局限与出处（「copy from ant-design」「ported from react-use」、AI 生成署名、部署失败根因、基准不严谨），不夸大——这是其作为开发者很可贵的特质。

---

## 八、优势 / 短板 / 成长建议

**优势**
1. 范式嗅觉与学习速度顶尖，永远在第一班车上。
2. 源码级钻研能力，能挖到并使用框架未公开机制。
3. 库作者工程素养扎实（双格式发布、类型设计、构建工具自研）。
4. 技术广度罕见，且能跨到系统级（Swift FFI、Rust/Go）。
5. AI 协同能力已进入第一梯队：用工程纪律驾驭 AI，而非被 AI 牵着走。
6. 开源协作规范、诚实、沟通有据。

**短板**
1. **测试纪律是贯穿 7 年的系统性短板**（2025 前几乎全员零测试），直到借 AI/lint 才补齐——属「被动补齐」而非「内化习惯」。
2. **完成度与收尾品味不稳定**：虎头蛇尾、脚手架残留、AI 痕迹未清理反复出现。
3. **深度集中、洼地明显**：算法、后端纵深、性能/安全工程相对薄弱。
4. **早期安全意识不足**（私钥/密钥入库、客户端侧签名），近年改善但仍有客户端暴露凭据的设计。
5. 产品化「最后一公里」常缺位（文档、README、长期维护）。

**成长建议**
1. 把测试从「AI/lint 逼出来的产物」升级为「设计阶段的内化习惯」，尤其为自己最自豪的源码级/算法型实现补数值与渲染正确性测试。
2. 选 1-2 个代表作做「深度打磨 + 长期维护」，补全文档/README/迭代历史，把「能跑的 demo」变成「有人用的产品」，以对冲虎头蛇尾倾向。
3. 在已有广度上**主动加深一条主线**（如 RSC/编译器方向或图形/WebGPU 方向），形成可对外背书的「深度护城河」。
4. 把客户端密钥签名等安全反模式系统性收口（服务端代理/网关），将早期教训固化为 checklist。
5. 在开源上，从「优质勘误贡献者」向「某个项目的复杂特性持续贡献者」迈进，积累被合并的全链路改动。

---

## 九、综合结论

zhangyu1818 是一位**资历约 7 年、整体处于「资深独立前端开发者」上沿、并已成功转型为「AI 工程总设计师」的高潜力技术人**。其能力曲线是一条清晰且持续上行的成长线：2019 年作为 React Hooks 早期采用者起步（彼时工程纪律尚粗，复制粘贴与反模式明显），2020-2021 通过密集的源码钻研与库作者实践把技术上限抬高，2022-2024 稳定在资深水准并形成自洽的自研生态，2023 末敏锐踏入 RSC 前沿，2024-2025 横向扩张到 Swift 原生与 Rust/Go 系统，2025 下半年起完成向 AI 工程的范式跃迁。**严禁用今天的标准苛责其 2019-2021 的代码**——那些代码在当年都属于「紧跟潮流甚至超前」的水平，真正定义他的是这条上行曲线本身。

他的核心竞争力是**「范式嗅觉 + 源码级钻研 + 库作者工程素养」的三角**，并在 2026 年叠加了一项稀缺的新能力：**用严格的工程纪律（自维护 lint 规则、端口/适配器架构、CLAUDE.md/SKILL.md 可执行规范）去驾驭 AI 产出，使其保持架构连贯**。综合判断，其代码水平加权约 **7.3/10**、技术水平约 **7.0/10**、开源协作 **8/10**、AI 把控 **8.5/10**——AI 把控是其当前最突出、最具时代红利的能力。

与此对应，他的短板同样鲜明且稳定：**测试纪律的长期缺失、完成度与收尾品味的不稳定、深度的选择性集中**。这三点共同指向一个判断——**他是一位极佳的「探索者 / 原型缔造者 / 趋势捕手」，但尚未充分展现「长期主义的产品打磨者」一面**。若能把对「新」的热情，匀出一部分投向对「深」与「完」的坚持，他完全具备从「优秀的独立开发者」走向「某个领域有公认深度护城河的技术专家」的潜力。

---

## 📚 全部自有仓库逐仓评分（按创建时间）

| 创建 | 仓库 | 语言 | ⭐ | 类型 | 功能 | 代码 | 技术 | AI | 一句话 |
|---|---|---|:--:|---|:--:|:--:|:--:|:--:|---|
| 2019-02-14 | [react-music-app](https://github.com/zhangyu1818/react-music-app) | TypeScript | 1 | application | 7 | 5 | 6 | — | 一个移动端音乐播放 App（网易云音乐风格的克隆），用 React Hooks + Type |
| 2019-03-10 | [simple-carousel](https://github.com/zhangyu1818/simple-carousel) | TypeScript | 0 | library/tool | 7 | 6 | 6 | — | 一个不依赖 jQuery 的纯 TypeScript 轮播图(carousel)库，已发布到 |
| 2019-03-26 | [html5-camera-demo](https://github.com/zhangyu1818/html5-camera-demo) | JavaScript | 1 | demo/experiment | 5 | 4 | 4 | — | 一个用 HTML5 getUserMedia 调用摄像头拍照、canvas 截帧并通过 fe |
| 2019-03-28 | [koa-graphql-mongodb](https://github.com/zhangyu1818/koa-graphql-mongodb) | JavaScript | 3 | demo/experiment | 6 | 6 | 4 | — | 一个用 Koa + apollo-server-koa + Mongoose 搭的 Grap |
| 2019-03-31 | [todolist-graphql](https://github.com/zhangyu1818/todolist-graphql) | JavaScript | 1 | demo/experiment | 6 | 5 | 5 | — | 一个 React + GraphQL(Apollo) + Material-UI 的 tod |
| 2019-04-10 | [blog-admin](https://github.com/zhangyu1818/blog-admin) | JavaScript | 0 | application | 6 | 6 | 6 | — | 基于 ant-design-pro 脚手架二次开发的个人博客后台管理系统，通过 GraphQ |
| 2019-04-12 | [react-markdown-editor](https://github.com/zhangyu1818/react-markdown-editor) | JavaScript | 3 | library/tool | 8 | 6 | 6 | — | 一个发布到 npm 的 React Markdown 编辑器组件（react-markdow |
| 2019-04-17 | [simple-multipage-webpack](https://github.com/zhangyu1818/simple-multipage-webpack) | JavaScript | 1 | config | 4 | 5 | 4 | — | 一个基于 webpack 4 的前端构建脚手架配置，集成 pug、sass(含 CSS Mo |
| 2019-04-19 | [typegraphql-CRUD-demo](https://github.com/zhangyu1818/typegraphql-CRUD-demo) | TypeScript | 0 | demo/experiment | 4 | 6 | 5 | — | 用 TypeGraphQL 在 Koa+Apollo 上实现的一个 todolist 增删查 |
| 2019-04-21 | [blog-server](https://github.com/zhangyu1818/blog-server) | TypeScript | 0 | application | 6 | 5 | 5 | — | 一个博客后台 GraphQL 服务，基于 Koa + Apollo Server + Typ |
| 2019-04-23 | [filter-dropdown](https://github.com/zhangyu1818/filter-dropdown) | JavaScript | 0 | library/tool | 7 | 7 | 6 | — | 一个无依赖的原生 JS 下拉筛选组件，复刻 ant-design 表格列头的 filter  |
| 2019-04-28 | [switch-button](https://github.com/zhangyu1818/switch-button) | TypeScript | 0 | library/tool | 8 | 8 | 7 | — | 一个框架无关的原生 TypeScript 开关按钮组件库，复刻 Ant Design 的 S |
| 2019-05-16 | [leetcode](https://github.com/zhangyu1818/leetcode) | JavaScript | 0 | learning/study | 6 | 6 | 4 | — | 作者个人的 LeetCode 算法刷题记录，14 道题的 JavaScript 解法，附中文 |
| 2019-05-22 | [wechaty-bot](https://github.com/zhangyu1818/wechaty-bot) | TypeScript | 0 | application | 6 | 5 | 4 | — | 基于 wechaty 0.27 + koa 封装的简易微信群管理助手，支持关键词自动回复、新 |
| 2019-05-30 | [page-scroll](https://github.com/zhangyu1818/page-scroll) | TypeScript | 0 | library/tool | 6 | 6 | 6 | — | 一个面向移动端的纯 TypeScript 全屏整页滑动（竖向翻页）库，基于 touch 事件 |
| 2019-06-09 | [gatsby-blog](https://github.com/zhangyu1818/gatsby-blog) | JavaScript | 0 | application | 7 | 6 | 4 | — | 作者个人博客，基于官方 gatsby-starter-blog fork，加入暗/亮主题切换 |
| 2019-06-13 | [useform](https://github.com/zhangyu1818/useform) | JavaScript | 0 | library/tool | 4 | 5 | 4 | — | 一个 50 行的极简 React Hooks 表单字段管理工具，通过 createField |
| 2019-07-27 | [next-blog](https://github.com/zhangyu1818/next-blog) | JavaScript | 0 | application | 6 | 5 | 5 | — | 基于 Next.js + MDX 的个人技术博客，构建时扫描 blog 目录下的 mdx 文 |
| 2019-08-07 | [flutter-todo-list](https://github.com/zhangyu1818/flutter-todo-list) | Dart | 0 | learning/study | 5 | 5 | 4 | — | 作者的第一个 Flutter 练手 demo：一个带 Tab 分类（全部/已完成/未完成）的 |
| 2019-09-07 | [mdx-blog](https://github.com/zhangyu1818/mdx-blog) | JavaScript | 0 | application | 8 | 6 | 6 | — | 作者本人的个人博客（v2 重写版），基于 Gatsby + MDX 构建，含自动深色模式、页 |
| 2019-09-11 | [number-to-chinese-characters](https://github.com/zhangyu1818/number-to-chinese-characters) | JavaScript | 0 | library/tool | 6 | 7 | 5 | — | 将阿拉伯数字转换为中文大写金额（如 101010 -> 壹拾万零壹仟零壹拾元整）的单文件 J |
| 2019-09-19 | [react-animate-skeleton](https://github.com/zhangyu1818/react-animate-skeleton) | TypeScript | 0 | library/tool | 7 | 7 | 7 | — | 基于 styled-components 的 React 动画骨架屏组件库，提供 Skele |
| 2019-12-03 | [redux-sourcecode-study](https://github.com/zhangyu1818/redux-sourcecode-study) | TypeScript | 1 | learning/study | 7 | 7 | 6 | — | 通过用 TypeScript 逐行重写并加中文注释的方式，学习并拆解 Redux v4.0. |
| 2020-03-07 | [utils](https://github.com/zhangyu1818/utils) | TypeScript | 0 | library/tool | 7 | 7 | 6 | — | 一个 Lerna 管理的前端工具 monorepo，发布了 yuhooks（25 个 Rea |
| 2020-03-17 | [react-redux-sourcecode-study](https://github.com/zhangyu1818/react-redux-sourcecode-study) | JavaScript | 0 | learning/study | 7 | 7 | 7 | — | 把 react-redux v7.2 源码完整拷贝进 CRA 工程，逐行加中文注释并配一篇近 |
| 2020-03-29 | [react-tiny-virtual-grid](https://github.com/zhangyu1818/react-tiny-virtual-grid) | TypeScript | 0 | library/tool | 6 | 6 | 6 | — | 一个 React 虚拟滚动组件，在虚拟列表基础上实现类 Grid 布局，并支持列数动态变化时 |
| 2020-04-09 | [easy-tweening](https://github.com/zhangyu1818/easy-tweening) | TypeScript | 0 | library/tool | 7 | 7 | 6 | — | 一个仅约1KB(gzip)的补间动画(tweening)库，通过单个共享 requestAn |
| 2020-05-13 | [react-tim-chat](https://github.com/zhangyu1818/react-tim-chat) | TypeScript | 13 | library/tool | 7 | 7 | 7 | — | 基于腾讯IM (tim-js-sdk v2.6.x) 的 React 聊天 UI 实现，支持 |
| 2020-05-22 | [piatto](https://github.com/zhangyu1818/piatto) | Less | 0 | library/tool | 6 | 8 | 7 | — | 面向移动端的 React + TypeScript 组件库（Button/Input/Sli |
| 2020-06-16 | [micro-frontend-demo](https://github.com/zhangyu1818/micro-frontend-demo) | TypeScript | 9 | demo/experiment | 7 | 6 | 6 | — | qiankun 微前端示例，演示 umi 主/子应用、纯 HTML 手动主应用、CRA 子应 |
| 2020-06-30 | [rc-pannellum](https://github.com/zhangyu1818/rc-pannellum) | TypeScript | 2 | library/tool | 6 | 7 | 4 | — | 一个把 pannellum 全景图查看器封装成 React 组件的轻量 TypeScript |
| 2020-07-09 | [zhangyu1818](https://github.com/zhangyu1818/zhangyu1818) | - | 0 | doc-dump | 5 | 5 | 1 | — | GitHub 个人主页 profile README，展示前端开发者 ZHANGYU 的自我 |
| 2020-07-22 | [wx-font-reset](https://github.com/zhangyu1818/wx-font-reset) | JavaScript | 1 | library/tool | 6 | 5 | 3 | — | 一个微小的 npm 库，通过 WeixinJSBridge 把微信内置字体大小还原为默认值， |
| 2020-08-05 | [countdown-button](https://github.com/zhangyu1818/countdown-button) | TypeScript | 0 | library/tool | 8 | 8 | 7 | — | 封装 Ant Design Button 的倒计时按钮组件库，常用于短信验证码等场景，同时导 |
| 2020-09-02 | [drag-resize](https://github.com/zhangyu1818/drag-resize) | TypeScript | 5 | library/tool | 6 | 6 | 6 | — | 一个发布到 npm 的 React 组件 rc-drag-resize，通过八向把手让子元素 |
| 2020-09-27 | [hook-form-async-validator](https://github.com/zhangyu1818/hook-form-async-validator) | TypeScript | 0 | library/tool | 6 | 7 | 5 | — | 一个把 async-validator 校验引擎接入 react-hook-form 的 r |
| 2020-10-14 | [observer](https://github.com/zhangyu1818/observer) | TypeScript | 0 | learning/study | 6 | 7 | 7 | — | 学习性质地重写 observer-util（nx-js / react-easy-state |
| 2020-12-27 | [swiftui-todolist](https://github.com/zhangyu1818/swiftui-todolist) | Swift | 0 | learning/study | 6 | 6 | 5 | — | 一个用 SwiftUI 2.0 + MVVM 实现的 iOS 待办事项练手 App，从占位  |
| 2021-01-08 | [clocks-widget](https://github.com/zhangyu1818/clocks-widget) | Swift | 21 | application | 8 | 6 | 7 | — | 一款已上架 App Store 的 iOS SwiftUI 时钟桌面小组件 App，支持自定 |
| 2021-01-13 | [github-actions-demo](https://github.com/zhangyu1818/github-actions-demo) | - | 0 | learning/study | 2 | 2 | 2 | — | 一个用来试玩 GitHub Actions 的练习仓库，仅包含两个近乎模板的 workflo |
| 2021-01-14 | [blog](https://github.com/zhangyu1818/blog) | TypeScript | 138 | application | 9 | 8 | 8 | — | 个人博客（zhangyu.dev），用 Next.js 14 App Router + RS |
| 2021-03-07 | [react-observed-context](https://github.com/zhangyu1818/react-observed-context) | TypeScript | 2 | library/tool | 6 | 6 | 7 | — | 一个利用 React 16/17 未公开的 Context bitmask（calculat |
| 2021-03-11 | [use-derived-value](https://github.com/zhangyu1818/use-derived-value) | TypeScript | 2 | library/tool | 7 | 8 | 6 | — | 一个用 React Hook 模拟类组件 getDerivedStateFromProps  |
| 2021-05-06 | [stupid-events](https://github.com/zhangyu1818/stupid-events) | TypeScript | 0 | demo/experiment | 6 | 7 | 6 | — | 用单文件 TypeScript 模仿 React v17 的事件系统：在 window 上做 |
| 2021-05-09 | [dynamic-stylesheet](https://github.com/zhangyu1818/dynamic-stylesheet) | TypeScript | 1 | library/tool | 7 | 7 | 4 | — | 一个用 JavaScript 动态注入/更新 CSS 的极小型 TypeScript 工具库 |
| 2021-05-09 | [wave-effect](https://github.com/zhangyu1818/wave-effect) | TypeScript | 0 | library/tool | 7 | 7 | 6 | — | 一个仿 Ant Design 的点击水波纹(ripple)效果的轻量 TypeScript  |
| 2021-05-15 | [react-hooks-analysis](https://github.com/zhangyu1818/react-hooks-analysis) | Vue | 0 | doc-dump | 6 | 5 | 7 | — | 用 Slidev 制作的组内技术分享 PPT，源码级浅析 React Hooks 的渲染原理 |
| 2021-05-16 | [rollib](https://github.com/zhangyu1818/rollib) | TypeScript | 0 | library/tool | 6 | 7 | 6 | — | 基于 Rollup 的零配置库打包工具，支持 TS/React、Less/Sass/Styl |
| 2021-05-23 | [lib-tool](https://github.com/zhangyu1818/lib-tool) | TypeScript | 1 | library/tool | 7 | 6 | 6 | — | 零配置的组件库打包 CLI 工具，文件到文件编译，同时输出 ESM/CJS 及 .d.ts， |
| 2021-05-26 | [pr-preview-action-demo](https://github.com/zhangyu1818/pr-preview-action-demo) | JavaScript | 0 | demo/experiment | 6 | 6 | 5 | — | 用一个未改动的 Create React App 脚手架作载体，演示一套基于 GitHub  |
| 2021-05-31 | [react-test-demo](https://github.com/zhangyu1818/react-test-demo) | JavaScript | 1 | learning/study | 6 | 6 | 4 | — | 一个用中文注释演示 React Testing Library 与 jest 常见测试套路的 |
| 2021-06-02 | [scroll-progress-bar](https://github.com/zhangyu1818/scroll-progress-bar) | TypeScript | 1 | library/tool | 6 | 6 | 4 | — | 一个零依赖的纯 TS 滚动进度条库，挂在页面顶部随滚动改变宽度，支持 SSR 安全导入。 |
| 2021-06-22 | [react-native-storybook-example](https://github.com/zhangyu1818/react-native-storybook-example) | JavaScript | 0 | demo/experiment | 6 | 5 | 6 | — | 演示如何用 React Native Web + Storybook 让 native-ba |
| 2021-07-03 | [LeetCode-Note](https://github.com/zhangyu1818/LeetCode-Note) | Swift | 0 | learning/study | 4 | 6 | 4 | — | 作者个人的 LeetCode 刷题笔记，用 Swift 实现约 26 道题（以链表、二叉树为 |
| 2021-07-03 | [data-structure](https://github.com/zhangyu1818/data-structure) | Swift | 0 | learning/study | 6 | 6 | 4 | — | 用 Swift Playground 按自考本科数据结构教材(02331)实现链表/栈/队列 |
| 2021-07-04 | [write-file-with](https://github.com/zhangyu1818/write-file-with) | JavaScript | 1 | tool | 5 | 5 | 4 | — | 一个 GitHub Action：读取指定文件内容，传入用户提供的 JS 脚本函数处理后，把 |
| 2021-07-17 | [generate-d-ts](https://github.com/zhangyu1818/generate-d-ts) | TypeScript | 0 | library/tool | 6 | 6 | 5 | — | 一个极小的 TypeScript 工具库，封装 TypeScript Compiler AP |
| 2021-07-25 | [tikka](https://github.com/zhangyu1818/tikka) | TypeScript | 1 | library/tool | 6 | 7 | 6 | — | 一个插件式的「文件到文件」转换打包工具（非 bundle），通过可组合的 transform |
| 2021-07-29 | [cjsb](https://github.com/zhangyu1818/cjsb) | JavaScript | 0 | library/tool | 6 | 6 | 5 | — | 一个基于 Babel 的 CLI 工具，将 JS/TS 源码快速编译为 CommonJS 库 |
| 2021-08-11 | [swiftui-playground](https://github.com/zhangyu1818/swiftui-playground) | Swift | 0 | demo/experiment | 5 | 5 | 5 | — | 用 SwiftUI 复刻 iOS 15 Apple 天气 App 的单屏 UI，含视差/吸顶 |
| 2022-01-01 | [react-native-google-autocomplete-modal](https://github.com/zhangyu1818/react-native-google-autocomplete-modal) | TypeScript | 0 | library/tool | 6 | 6 | 6 | — | 一个 React Native 原生模块，封装 Google Places SDK，在 iO |
| 2022-10-11 | [imessage-app-icon](https://github.com/zhangyu1818/imessage-app-icon) | TypeScript | 0 | tool | 7 | 6 | 4 | — | 一个纯浏览器端的 Web 工具：上传图片，用 canvas 批量缩放出 Apple iMes |
| 2022-10-12 | [wechat-test](https://github.com/zhangyu1818/wechat-test) | TypeScript | 0 | infra/script | 6 | 5 | 4 | — | 一个每日定时(GitHub Actions cron)抓取墨迹天气与第三方仓库的每日英语单词 |
| 2022-11-17 | [useVideoControls](https://github.com/zhangyu1818/useVideoControls) | TypeScript | 0 | library/tool | 6 | 7 | 6 | — | 一个 React Hook 库，通过 ref + Context 共享 HTMLVideoE |
| 2022-11-29 | [share-play-swiftui-example](https://github.com/zhangyu1818/share-play-swiftui-example) | Swift | 1 | demo/experiment | 6 | 6 | 6 | — | 一个 iOS/iPadOS SwiftUI 示例 App，演示用 GroupActiviti |
| 2023-05-01 | [ali_ecc_js](https://github.com/zhangyu1818/ali_ecc_js) | JavaScript | 0 | demo/experiment | 6 | 5 | 6 | — | 用 secp256k1/ECDSA 复现阿里云盘 web 端 create_session/ |
| 2023-06-18 | [motion-wave](https://github.com/zhangyu1818/motion-wave) | TypeScript | 1 | library/tool | 7 | 8 | 6 | — | 一个用 Canvas 渲染并以缓动动画过渡参数的波浪图形 React/原生 JS 库，提供  |
| 2023-06-22 | [from-to](https://github.com/zhangyu1818/from-to) | TypeScript | 0 | library/tool | 8 | 7 | 7 | — | 一个轻量级（gzip约1kb）的纯值过渡动画库，支持 tween(贝塞尔) 与 spring |
| 2023-06-27 | [pkg-pub](https://github.com/zhangyu1818/pkg-pub) | JavaScript | 0 | tool | 7 | 8 | 5 | — | 一个 CLI 工具，通过向 npm registry 发布一个临时占位版本来抢占/确认 np |
| 2023-07-05 | [bg-css](https://github.com/zhangyu1818/bg-css) | HTML | 0 | library/tool | 6 | 7 | 6 | — | 一个极小的纯 CSS 库，通过渐变背景位移实现深浅色主题切换时的对角线扫光过渡动画。 |
| 2023-07-05 | [theme-bg](https://github.com/zhangyu1818/theme-bg) | TypeScript | 0 | library/tool | 6 | 7 | 6 | — | 一个发布到 npm 的小型库，用 Canvas 实现圆形扩散的主题切换/背景过渡动画，同时提 |
| 2023-07-06 | [type-challenges-answer](https://github.com/zhangyu1818/type-challenges-answer) | TypeScript | 0 | learning/study | 7 | 8 | 7 | — | 作者用 TypeScript 类型体操刷 type-challenges 题库的个人答案集， |
| 2023-07-06 | [wave-button](https://github.com/zhangyu1818/wave-button) | TypeScript | 0 | library/tool | 7 | 6 | 6 | — | 一个 React 组件库，把作者自研的 motion-wave canvas 波浪渲染器封装 |
| 2023-07-07 | [dark-toggle](https://github.com/zhangyu1818/dark-toggle) | TypeScript | 0 | library/tool | 7 | 7 | 6 | — | 一个无主题闪烁、支持 light/dark/system 三态且能正确响应 prefers- |
| 2023-07-10 | [tscb](https://github.com/zhangyu1818/tscb) | TypeScript | 0 | library/tool | 6 | 6 | 5 | — | 一个轻量的 TypeScript 打包/编译辅助库，通过为每个目标合并 tsconfig 并 |
| 2023-10-14 | [github-api-test](https://github.com/zhangyu1818/github-api-test) | - | 0 | other | 1 | 1 | 1 | — | 一个完全空的仓库，名为 github-api-test，无任何提交/文件，疑似为测试 Git |
| 2023-10-30 | [lambda-clash-sub](https://github.com/zhangyu1818/lambda-clash-sub) | JavaScript | 0 | infra/script | 5 | 4 | 3 | — | 一个把 v2ray 订阅链接转换为 Clash Premium 配置 YAML 的个人自用  |
| 2023-11-06 | [lighthouse-ci](https://github.com/zhangyu1818/lighthouse-ci) | JavaScript | 0 | infra/script | 6 | 5 | 4 | AI⬤ | 一个单文件 Node.js 脚本，用 Lighthouse 对多国家/多 URL 在移动端和 |
| 2023-12-07 | [alias-recovery](https://github.com/zhangyu1818/alias-recovery) | JavaScript | 0 | library/tool | 5 | 5 | 5 | — | 一个 CLI 工具，用 Babel AST 把源码 import 中的路径别名（如 @api |
| 2023-12-28 | [rsc-example](https://github.com/zhangyu1818/rsc-example) | TypeScript | 0 | demo/experiment | 7 | 6 | 7 | — | Next.js 14 App Router 电商样例，演示 React Server Com |
| 2024-01-19 | [tw-styled](https://github.com/zhangyu1818/tw-styled) | TypeScript | 3 | library/tool | 7 | 8 | 7 | — | 一个用 Proxy + 标签模板字面量语法快速创建带 Tailwind CSS 样式的 Re |
| 2024-01-26 | [rsc-mdx](https://github.com/zhangyu1818/rsc-mdx) | TypeScript | 4 | library/tool | 6 | 7 | 6 | — | 一个极简的 React Server Components 用 MDX 渲染库，对 @mdx |
| 2024-02-06 | [remark-code-groups](https://github.com/zhangyu1818/remark-code-groups) | TypeScript | 0 | library/tool | 6 | 6 | 6 | — | 一个 remark 插件，把 :::code-group 容器指令转换为 CSS-only  |
| 2024-03-18 | [react-server-only-context](https://github.com/zhangyu1818/react-server-only-context) | TypeScript | 4 | library/tool | 6 | 8 | 7 | — | 一个微型 React 库，利用 React.cache() 在 React Server C |
| 2024-04-03 | [use-flip](https://github.com/zhangyu1818/use-flip) | TypeScript | 0 | library/tool | 6 | 7 | 6 | — | 一个零依赖的 React Hook（useFlip），用 Web Animations AP |
| 2024-04-14 | [contentful-experiences-example](https://github.com/zhangyu1818/contentful-experiences-example) | TypeScript | 0 | demo/experiment | 7 | 7 | 6 | — | 一个 Next.js 14 示例项目，演示如何用 Contentful Experience |
| 2024-04-15 | [react-markdown-toc](https://github.com/zhangyu1818/react-markdown-toc) | TypeScript | 7 | library/tool | 8 | 8 | 7 | — | 一个 React 库，从 Markdown 文本生成目录(TOC)，同时支持服务端组件(固定 |
| 2024-05-06 | [rehype-default-code-lang](https://github.com/zhangyu1818/rehype-default-code-lang) | TypeScript | 0 | library/tool | 7 | 7 | 5 | — | 一个 rehype/unified 插件，为没有指定语言的 <code> 标签自动添加默认语 |
| 2024-05-21 | [three-study](https://github.com/zhangyu1818/three-study) | TypeScript | 0 | learning/study | 5 | 6 | 5 | — | 跟随 Three.js Journey（Bruno Simon）课程的学习练习仓库，单文件逐 |
| 2024-05-27 | [three-falling-cubes](https://github.com/zhangyu1818/three-falling-cubes) | TypeScript | 0 | demo/experiment | 7 | 7 | 6 | — | 一个 Three.js 入门 demo：方块/球体从空中连续掉落并堆叠，物理由 Rapier |
| 2024-05-31 | [wasm-vs-js](https://github.com/zhangyu1818/wasm-vs-js) | HTML | 0 | demo/experiment | 5 | 5 | 5 | — | 一个对比 Rust(WASM) 与 JavaScript(mathjs) 在矩阵乘法/转置、 |
| 2024-06-10 | [eslint-config](https://github.com/zhangyu1818/eslint-config) | TypeScript | 1 | library/tool | 8 | 8 | 6 | AI⬤ | 一个面向 ESLint 10 Flat Config 的可共享配置库，按依赖自动检测并以 p |
| 2024-07-14 | [eng-learn](https://github.com/zhangyu1818/eng-learn) | TypeScript | 1 | application | 6 | 8 | 7 | — | 一个英语音频学习 Web 应用：上传 MP3 + SRT 字幕，边播放边滚动高亮当前字幕行， |
| 2024-08-19 | [cloud-storage](https://github.com/zhangyu1818/cloud-storage) | TypeScript | 1 | demo/experiment | 2 | 5 | 2 | AI⬤ | 一个用 v0 生成的 Next.js 前端脚手架，仅含登录页和找回密码页两个静态界面，并无任 |
| 2024-10-05 | [my-desktop-in-3d](https://github.com/zhangyu1818/my-desktop-in-3d) | - | 0 | other | 1 | 1 | 1 | — | 一个名为「我的桌面3D化」的占位仓库，从未提交过任何内容，无法判断其真实意图。 |
| 2024-10-05 | [r3f-docs-cursor](https://github.com/zhangyu1818/r3f-docs-cursor) | Astro | 0 | doc-dump | 2 | 3 | 2 | — | 把 react-three-fiber 官方文档原样塞进一个空白 Astro minimal |
| 2024-10-05 | [three.js-docs-cursor](https://github.com/zhangyu1818/three.js-docs-cursor) | HTML | 0 | doc-dump | 4 | 5 | 2 | — | 把 three.js 官方 API 文档 HTML 整包搬运下来，配一个自写脚本生成目录索引 |
| 2024-11-05 | [pr-finder](https://github.com/zhangyu1818/pr-finder) | Rust | 0 | tool | 7 | 7 | 5 | — | 一个 Rust 编写的 CLI 工具，通过 GitHub GraphQL Search AP |
| 2024-11-16 | [create-context-factory](https://github.com/zhangyu1818/create-context-factory) | TypeScript | 0 | library/tool | 5 | 6 | 4 | — | 一个面向 TypeScript 的 React Context 工具库，通过工厂函数把 ho |
| 2024-11-17 | [speedtest-ui](https://github.com/zhangyu1818/speedtest-ui) | TypeScript | 4 | application | 7 | 7 | 6 | — | 一个基于 Ookla Speedtest CLI 的跨平台桌面网速测试 App，用 Taur |
| 2024-11-20 | [appicon-forge](https://github.com/zhangyu1818/appicon-forge) | TypeScript | 998 | application | 9 | 8 | 7 | — | 纯前端 App 图标生成器：自定义颜色/渐变/边框/阴影/透视/文字/字体，集成 Iconi |
| 2024-11-30 | [r3f-100-exercises](https://github.com/zhangyu1818/r3f-100-exercises) | TypeScript | 0 | learning/study | 8 | 8 | 8 | AI⬤ | 一个 React Three Fiber 学习练习集，逐个实现 10 个交互式 3D/着色器 |
| 2025-04-10 | [openai-compatible-cosyvoice](https://github.com/zhangyu1818/openai-compatible-cosyvoice) | Python | 1 | tool | 6 | 4 | 4 | AI◑ | 一个基于 Flask 的适配层服务器，把阿里云 DashScope CosyVoice TT |
| 2025-04-12 | [apple-docs-for-rag](https://github.com/zhangyu1818/apple-docs-for-rag) | CoffeeScript | 45 | doc-dump | 7 | 4 | 4 | — | 把约300个Apple开发者框架文档站点抓取并转换为干净的Markdown语料库，供RAG/ |
| 2025-06-26 | [ScreenCaptureKit.md](https://github.com/zhangyu1818/ScreenCaptureKit.md) | - | 1 | doc-dump | 4 | 3 | 2 | AI⬤ | 把 Apple 官方 ScreenCaptureKit 框架文档抓取并转换成 Markdow |
| 2025-07-02 | [StoreKit.md](https://github.com/zhangyu1818/StoreKit.md) | - | 1 | doc-dump | 4 | 3 | 2 | — | 将 Apple 官方 StoreKit 开发者文档逐页抓取并转换为 1235 个扁平的 Ma |
| 2025-07-04 | [AppStoreServerAPI.md](https://github.com/zhangyu1818/AppStoreServerAPI.md) | - | 0 | doc-dump | 3 | 2 | 2 | AI◑ | 把 Apple 的 App Store Server API 官方开发者文档抓取/镜像成 2 |
| 2025-07-04 | [Swift.md](https://github.com/zhangyu1818/Swift.md) | - | 0 | doc-dump | 4 | 3 | 3 | AI◑ | 将 Apple 官方 Swift 标准库/语言文档批量抓取转换为 16214 个扁平 Mar |
| 2025-07-04 | [SwiftUI.md](https://github.com/zhangyu1818/SwiftUI.md) | - | 4 | doc-dump | 4 | 2 | 2 | — | 把苹果 SwiftUI 官方开发者文档逐个 API 符号抓取并转换成 Markdown 的文 |
| 2025-07-14 | [xcode-i18n-mcp](https://github.com/zhangyu1818/xcode-i18n-mcp) | JavaScript | 3 | tool | 6 | 7 | 4 | AI⬤ | 一个 MCP 服务器，通过解析 .pbxproj 与 .xcstrings 文件，自动化 i |
| 2025-07-23 | [CoreML.md](https://github.com/zhangyu1818/CoreML.md) | - | 0 | doc-dump | 4 | 3 | 2 | AI◑ | 将 Apple 官方 Core ML 框架开发者文档整站抓取并转换为 732 个按 API  |
| 2025-08-07 | [ScreenCaptureRecorder](https://github.com/zhangyu1818/ScreenCaptureRecorder) | Swift | 0 | library/tool | 4 | 6 | 5 | — | 一个 macOS Swift 库，封装 ScreenCaptureKit 的内容选择器与录制 |
| 2025-09-24 | [tingwu](https://github.com/zhangyu1818/tingwu) | TypeScript | 0 | application | 7 | 7 | 8 | AI⬤ | macOS 桌面应用（Tauri 2 + React 19），用 Rust 直接调用 Scr |
| 2025-10-18 | [gemini-storybook-downloader](https://github.com/zhangyu1818/gemini-storybook-downloader) | TypeScript | 0 | tool | 6 | 6 | 5 | AI⬤ | 用 Playwright 自动化浏览器，把 Gemini Storybook 网页里每一页的 |
| 2025-11-27 | [TypeFree](https://github.com/zhangyu1818/TypeFree) | Swift | 0 | application | 8 | 7 | 7 | AI◑ | 一款 macOS 语音听写/转录应用：本地 whisper.cpp 与 Parakeet A |
| 2025-11-28 | [qwen3-asr-worker](https://github.com/zhangyu1818/qwen3-asr-worker) | TypeScript | 0 | application | 5 | 6 | 5 | AI⬤ | 部署在 Cloudflare Workers 上、基于阿里云 Qwen3-ASR 模型的 O |
| 2025-11-29 | [homebrew-tap](https://github.com/zhangyu1818/homebrew-tap) | Ruby | 0 | infra/script | 6 | 6 | 4 | — | GoReleaser 自动生成的 Homebrew tap，用于通过 brew 分发自研 G |
| 2025-11-29 | [qwen3-compatibility](https://github.com/zhangyu1818/qwen3-compatibility) | Go | 0 | tool | 6 | 6 | 5 | AI⬤ | 一个 Go 编写的 HTTP 服务，把阿里 DashScope 的 Qwen3-ASR 语音 |
| 2025-12-02 | [v2ray2clash](https://github.com/zhangyu1818/v2ray2clash) | TypeScript | 0 | tool | 5 | 5 | 4 | AI⬤ | 一个 Cloudflare Worker，将 V2Ray 订阅链接（ss/vmess）转换为 |
| 2025-12-04 | [Mermaid-AI](https://github.com/zhangyu1818/Mermaid-AI) | TypeScript | 0 | application | 6 | 6 | 4 | AI⬤ | 一个基于 React 的 Mermaid.js 图表编辑器，左侧代码编辑、右侧实时渲染（手绘 |
| 2026-01-24 | [vercel-best-practices-report-viewer](https://github.com/zhangyu1818/vercel-best-practices-report-viewer) | TypeScript | 0 | tool | 6 | 6 | 5 | AI⬤ | 一个单页 React 应用，用于可视化「vercel-react-best-practice |
| 2026-01-25 | [vercel-react-best-practices-report](https://github.com/zhangyu1818/vercel-react-best-practices-report) | TypeScript | 0 | library/tool | 8 | 9 | 7 | AI⬤ | 一个基于 Ink/React 的 CLI/TUI 工具，调用 Claude Agent SD |
| 2026-02-12 | [anthropic-gateway](https://github.com/zhangyu1818/anthropic-gateway) | Go | 0 | tool | 8 | 8 | 7 | AI◑ | 配置驱动的 Anthropic 兼容 API 网关，按 YAML 把请求中的 model 改 |
| 2026-02-15 | [mp3-vtt](https://github.com/zhangyu1818/mp3-vtt) | TypeScript | 0 | application | 7 | 8 | 6 | AI⬤ | 纯前端的卡拉OK式音频播放器：本地加载 MP3 + VTT 字幕，按 <b> 标记逐词高亮跟 |
| 2026-03-11 | [codex-feishu](https://github.com/zhangyu1818/codex-feishu) | TypeScript | 0 | application | 8 | 9 | 7 | AI◑ | 个人用飞书机器人，通过 stdio JSON-RPC 远程控制本机运行的 codex app |
| 2026-03-22 | [task-while](https://github.com/zhangyu1818/task-while) | TypeScript | 0 | library/tool | 8 | 9 | 8 | AI⬤ | Git-first CLI 任务编排器：读取 while.yaml，按 spec-kit/o |
| 2026-04-18 | [oxlint-config](https://github.com/zhangyu1818/oxlint-config) | TypeScript | 0 | library/tool | 9 | 9 | 8 | AI◑ | 面向 Oxc 生态（oxlint + oxfmt）的可共享 lint/格式化配置预设包，提供 |
| 2026-04-23 | [llm-intro](https://github.com/zhangyu1818/llm-intro) | TypeScript | 0 | application | 8 | 9 | 7 | AI⬤ | 一个完整部署的中英双语互动式科普站点，用 17 章 + 逐章定制交互向零基础读者讲清大模型的 |
| 2026-06-05 | [Portal](https://github.com/zhangyu1818/Portal) | Swift | 0 | application | 9 | 9 | 8 | AI◑ | 一个常驻菜单栏的原生 macOS 应用，把自己注册为默认浏览器，按域名/来源 App 规则把 |
| 2026-06-05 | [skills](https://github.com/zhangyu1818/skills) | JavaScript | 0 | library/tool | 8 | 8 | 7 | AI⬤ | 个人维护的一组 AI Agent「技能」定义（SKILL.md 指令规范 + openai. |
| 2026-06-07 | [cue](https://github.com/zhangyu1818/cue) | Swift | 0 | application | 9 | 9 | 9 | AI⬤ | 一个 macOS 菜单栏应用：在任意 App 中选中文字后，于选区旁弹出浮动菜单，调用 LL |

---

## 🔀 外部开源 PR 贡献分析

| 日期 | 项目 | PR | 类型 | 复杂度 | 质量 | 状态 | 揭示 |
|---|---|---|---|:--:|:--:|:--:|---|
| 2020-04-03 | ant-design/ant-design | [#22895 fix: FilterDropdownProps TypeScript defi](https://github.com/ant-design/ant-design/pull/22895) | bugfix | 1 | 8 | MERGED | 作者能从用户视角发现成熟代码库中细微的类型不一致并提交规范、可合并的最小化修复，体现出对 TypeScript 类型 |
| 2020-05-20 | ant-design/ant-design | [#24313 feat(Avatar): support draggable prop](https://github.com/ant-design/ant-design/pull/24313) | feature | 1 | 6 | CLOSED | 能干净地按既有模式给成熟组件加一个透传 prop，但对 API 设计取舍与文档完整性把握不足——属于初级、低价值的增 |
| 2020-05-20 | ant-design/ant-design | [#24314 feat(Avatar): support draggable prop](https://github.com/ant-design/ant-design/pull/24314) | feature | 2 | 8 | MERGED | 作者能精准定位社区 issue 诉求并以最小、规范的改动落地，体现出对成熟组件库 API 透传约定和工程规范的熟悉。 |
| 2020-05-22 | ant-design/ant-design | [#24393 chore: Cascader ts definition update](https://github.com/ant-design/ant-design/pull/24393) | docs | 1 | 7 | MERGED | 细致、低风险地补齐类型定义缺口，体现作者对组件 API 完整性的关注和对开源贡献规范的熟悉，但本身技术含量极低。 |
| 2020-07-23 | umijs/umi | [#5083 Update docs/config/README.zh-CN.md](https://github.com/umijs/umi/pull/5083) | docs | 1 | 7 | MERGED | 作者对细节敏感、乐于回馈成熟开源项目，愿意为微小的文档错别字走完规范的 PR 流程，但该 PR 技术含量极低，无法体 |
| 2020-08-25 | react-component/mentions | [#32 fix: shouldn't call onPressEnter when me](https://github.com/react-component/mentions/pull/32) | bugfix | 3 | 8 | MERGED | 能从上游 antd issue 定位到底层 rc 库的根因，并用契合现有状态机（measuring 状态）的最小、低 |
| 2020-08-27 | ant-design/ant-design | [#26426 docs: Tree prop autoExpandParent default](https://github.com/ant-design/ant-design/pull/26426) | docs | 1 | 8 | MERGED | 作者具备阅读底层依赖源码核对实现细节的严谨性，能发现成熟项目文档与实际默认值不符的细微偏差并按双语规范同步修正。 |
| 2020-08-28 | react-component/mentions | [#33 fix: can't select when option has same v](https://github.com/react-component/mentions/pull/33) | bugfix | 4 | 8 | MERGED | 能从上游用户问题反向定位到组件库内部实现缺陷，用最小且向后兼容的改动（key 兜底 value）精准修复，并配合维护 |
| 2020-08-31 | ant-design/ant-design | [#26492 docs: update modal doc](https://github.com/ant-design/ant-design/pull/26492) | docs | 2 | 8 | MERGED | 作者细致使用并通读官方文档，能发现 API 表与组件实际能力之间的遗漏，并在面对维护者质疑时用具体事实据理力争，体现 |
| 2020-09-01 | ant-design/ant-design | [#26522 fix: Avatar doesn't scale when display i](https://github.com/ant-design/ant-design/pull/26522) | bugfix | 5 | 8 | MERGED | 能定位到 display:none 下 offsetWidth=0 的隐蔽布局时序 bug，并用项目已有的 rc-r |
| 2021-06-17 | react-component/select | [#635 docs: notFoundContent type](https://github.com/react-component/select/pull/635) | docs | 1 | 8 | MERGED | 作者对所用第三方库的真实类型契约有准确认知，发现并主动修正了官方文档的类型错误，体现了细致、负责且乐于回馈开源社区的 |
| 2024-06-18 | vercel/next.js | [#66996 feat: enhance Metadata 'other' API to su](https://github.com/vercel/next.js/pull/66996) | feature | 5 | 8 | CLOSED | 作者能在大型成熟代码库中精准定位并贯通改动全链路，重视向后兼容、文档与测试，沟通专业、对长期被忽视的 PR 保持克制 |
| 2024-09-13 | antfu/eslint-config | [#608 fix: add Next.js router segment config](https://github.com/antfu/eslint-config/pull/608) | bugfix | 2 | 9 | MERGED | 作者对工具链生态（ESLint 插件规则与 Next.js 框架约定）有精准理解，能定位误报根因并给出最小、规范、向 |

---

## 🧩 附：逐仓评分明细与证据

<details><summary>展开每个仓库的亮点 / 短板 / 证据 / 年代背景</summary>

### 2019-02-14 · react-music-app　(功能7/代码5/技术6)
- **定位**：一个移动端音乐播放 App（网易云音乐风格的克隆），用 React Hooks + TypeScript 实现，含播放器、歌词同步、歌单/专辑/搜索等页面。　|　技术栈：React 16.8 (Hooks), TypeScript 3.3, create-react-app / react-scripts, useReducer + Context (无 Redux 全局状态), SCSS + CSS Modules, better-scroll, react-spring, axios, http-proxy-middleware (NetEase API 代理)
- **亮点**：在 Hooks 稳定版发布当月即用 useReducer+Context 替代 Redux，前瞻；自写 LyricParser：LRC 正则解析 + setTimeout 调度引擎，支持 seek/pause/continue 与时间漂移校正；自定义 useMyContext 监听特定 state key 的副作用 hook，原创抽象；手写手势驱动 Tabs(速度阈值吸附 + rAF 动画)与可拖拽 ProgressBar，未套库；CSS Modules+SCSS、API 代理、browserslist 等工程配置完整
- **短板**：README 几乎为空(1 字节)，无文档/截图；类型纪律弱：大量 [propName:string]:any、as HTMLAudioElement 强转、dispatch:Function；错误处理薄弱：request 吞掉所有错误返回[]，fetchSong 无 try/catch 且强假设深层响应结构；无真实测试(仅 CRA 默认 smoke test)；reducer ADD_MUSIC 存在 index 计算小瑕疵；useMyContext 的 effect 依赖数组(map 展开 key)脆弱，违反 exhaustive-deps
- **证据**：src/utils/lyricParser.ts:40-200 完整的 LyricParser 类，含 playRest 基于 startStamp 的延迟调度与 togglePlay/seek/continue；src/context/index.ts:16-23 useMyContext 自定义 watcher hook，依赖数组为 keys.map((key)=>myContext.state[key])；src/components/Tabs/Tabs.tsx:61-110 onTouchEnd 用 speed/switchOffset/criticalSpeed 判定目标页 + animate 用 requestAnimationFrame 缓动；src/reducer/index.ts:1-249 useReducer 全局状态机，14 个 action，含 shuffle/删除当前曲目重算 index 逻辑；src/utils/request.ts:8-14 catch 直接返回 defaultValue||[] 吞错；src/reducer/index.ts:5-15 Song.url:undefined 类型错误；src/pages/Player/index.tsx:43-124 useRef<HTMLAudioElement> + 多处 as 强转，audio 事件驱动进度/歌词同步；src/App.test.tsx:1-9 仅 CRA 默认 renders-without-crashing 测试
- **年代背景**：2019-02 React Hooks(16.8) 刚发布数日，作者即采用 useReducer+Context 与自写手势/歌词引擎，在当年属偏上水平；但弱类型与缺测试按 2019 TS 工程标准只能算合格偏上。

### 2019-03-10 · simple-carousel　(功能7/代码6/技术6)
- **定位**：一个不依赖 jQuery 的纯 TypeScript 轮播图(carousel)库，已发布到 npm(simple-carousel-js)，支持拖拽/触摸、惯性切换、无限循环、缩放、自定义缓动与样式。　|　技术栈：TypeScript, Rollup, Babel, SCSS/node-sass, PostCSS/autoprefixer, CSS Modules, UMD
- **亮点**：手写 RAF 动画循环 + 完整 Penner 缓动库实现可配置 tween，而非简单 CSS transition；首尾克隆[last,...list,first]+拖拽起始时的 offset 回绕实现无缝无限循环，思路非平凡；基于速度(distance/timeStamp)的滑动惯性判定与 momentum 阈值，体感接近原生；translate3d+will-change 做 GPU 合成，destroy() 完整移除所有监听器，生命周期管理到位；Rollup+Babel+CSS Modules 的库构建链路与 UMD 产物、index.d.ts 类型声明齐备，2019 年算规范的发包工程
- **短板**：无任何测试用例与 CI；大量 ! 非空断言和 @ts-ignore，绕过了类型系统的严格性；事件绑定在全局 window 上而非容器内，多实例同页可能相互干扰；onDragEnd 的多层嵌套三元表达式可读性差；仅 1 次提交、0 star，更像个人作品而非长期维护项目
- **证据**：src/index.ts:114 const list = [imgList[imgList.length - 1], ...imgList, imgList[0]] —— 首尾克隆实现无限循环；src/index.ts:189-197 拖拽起始时根据 currentOffset 越界回绕 offset 并直接重置 transform；src/index.ts:234 const speed = (this.moveInfo.pos - this.startInfo.pos)/(this.moveInfo.timeStamp - this.startInfo.timeStamp) —— 速度驱动惯性；src/index.ts:263-301 animate() 自写 requestAnimationFrame 循环 + Tween(this.tween)(delta,...) 缓动求值；src/tween.ts:1-173 完整移植 Linear/Quad/.../Bounce 全套缓动并以联合类型 TweenFunc 约束；src/index.ts:152-161 destroy() 逐一 removeEventListener 并清空 innerHTML；rollup.config.js:18-24 clear/resolve/babel/postcss(CSS Modules+autoprefixer)/uglify 的 UMD 库构建；tsconfig.json strictNullChecks/noImplicitAny/noUnusedLocals 开启严格选项，但源码靠 ! 与 @ts-ignore 规避
- **年代背景**：2019 年正值无 jQuery 的原生组件库流行、TS+Rollup 发 npm 包成为前端规范实践的时期，作者用手写 RAF 动画与缓动库、CSS Modules 构建链做出可发布的轮播库，在当年属合格偏上的独立前端开发者水平。

### 2019-03-26 · html5-camera-demo　(功能5/代码4/技术4)
- **定位**：一个用 HTML5 getUserMedia 调用摄像头拍照、canvas 截帧并通过 fetch 上传到 Express(multer) 后端的练手 demo。　|　技术栈：JavaScript, Express 4, express-generator, Jade/Pug, MediaDevices getUserMedia, Canvas 2D, multer, dayjs, HTTPS(self-signed)
- **亮点**：完整跑通'前端摄像头取流→canvas截帧→FormData上传→multer落盘'闭环；正确认识到 getUserMedia 需 HTTPS 安全上下文，自带 server.pem 起 https 服务；前端用 Promise 链式写法处理 getUserMedia，符合 2019 的现代写法；上传按 字段名/年月 分目录并对文件名做 md5，有基本的归档意识
- **短板**：把真实 RSA 私钥 server.pem 直接提交进仓库(且 key 与 cert 同一文件)；routes/index.js 文件名拼接存在 bug:运算符优先级 + extname 与 mimetype 双扩展名，|| "" 为死代码；特性检测 'getUserMedia' in navigator.mediaDevices 在旧环境会因 mediaDevices 为 undefined 直接抛错；facingMode 硬编码 exact:'environment'，桌面/无后置摄像头设备必失败；残留调试代码与注释垃圾(append('123')、注释掉的 CORS)、jade 视图与手写 html 双套未清理
- **证据**：server.pem:1 以 '-----BEGIN RSA PRIVATE KEY-----' 开头，bin/www:22-25 用同一文件既作 key 又作 cert；routes/index.js:34-37 hashName = md5(...).digest('hex') + path.extname(originalname) + ext || ''，ext 来自 mimetype.replace('image/','.')，产生双扩展名且 || 永不触发；public/index.js:2 'getUserMedia' in navigator.mediaDevices 无 navigator.mediaDevices 存在性保护；public/index.js:11 facingMode:{ exact:'environment' } 强制后置摄像头；public/index.js:38 formData.append('123','123') 调试残留；app.js:21-26 注释掉的 CORS 块；package.json:2 name 仍为脚手架默认 'uploat-t'，app.js/bin/www/views 均为 express-generator 原样产物；git log 仅 1 个提交 'Update README.md'(2020-02-28)，源码经 squash/单次提交
- **年代背景**：2019 年 getUserMedia 已是标准 API 但移动端兼容仍需注意，作者用 https+Promise 链是当年合理做法；以一次性练手 demo 的 2019 标准衡量属合格偏下，私钥入库与文件名 bug 是明显减分项。

### 2019-03-28 · koa-graphql-mongodb　(功能6/代码6/技术4)
- **定位**：一个用 Koa + apollo-server-koa + Mongoose 搭的 GraphQL todo-list 后端示例，配套同作者的前端 todolist-graphql。　|　技术栈：JavaScript, Node.js, Koa, apollo-server-koa, GraphQL, Mongoose, MongoDB
- **亮点**：按 typeDefs/resolvers/schema 分层目录组织，模块化清晰；用 helloWorld 模块演示 extend type Query 的 schema 合并(resolver 字符串直言 'merge typeDefs and Resolvers')；自定义 Date scalar，覆盖 parseValue/serialize/parseLiteral 三个钩子；覆盖完整 CRUD（增删改查 + 模糊搜索 + 批量删除）
- **短板**：无任何测试与 CI；Date scalar 内部 new Date() 被自身同名变量遮蔽，存在隐患/逻辑 bug；DB 连接串硬编码 mongodb://localhost/test，无环境变量/配置抽离；错误处理极弱：connect 失败仅 console.log，resolver 无 try/catch；addTodo 的 content 在 schema 中可空但无校验；每次 mutation 都全表 find 返回 todoList
- **证据**：app.js:13-16 ApolloServer 以数组形式合并 [todoTypeDef, helloWorldTypeDef] 与 resolvers；src/graphql/typeDefs/todo.js:5-20 自定义 GraphQLScalarType('Date')，但 parseValue 内 new Date(value) 引用的是同名 scalar 而非全局 Date 构造器，属遮蔽 bug；src/graphql/resolvers/todo.js:9 Todo.find({ content: { $regex: content } }) 实现模糊搜索；src/graphql/resolvers/todo.js:24-27 deleteTodo 用 $in 支持批量删除并回传全表列表；src/db.js:4-9 连接串硬编码、catch 仅打印日志；src/graphql/resolvers/helloWorld.js:3 hello 返回 'merge typeDefs and Resolvers'，表明该模块仅为演示 schema 合并；package.json:6-8 仅有 start 脚本，无 test/lint/build；git log 仅 1 个 commit '7f76fe8 mutation return data'
- **年代背景**：2019 年 apollo-server 2.x 刚普及，这种 Koa+Apollo+Mongoose 的模块化 GraphQL CRUD 是当时主流学习范式，按当年标准属合格的入门级 demo，不应以现代工程（类型/测试/配置化）苛责。

### 2019-03-31 · todolist-graphql　(功能6/代码5/技术5)
- **定位**：一个 React + GraphQL(Apollo) + Material-UI 的 todo list 演示前端，配套作者自建的 koa-graphql-mongodb 后端，做增删改查与搜索。　|　技术栈：React 16.8 (Hooks), create-react-app 2.1, Apollo (apollo-boost / react-apollo), GraphQL 14, @material-ui/core 3, Sass(node-sass) CSS Modules
- **亮点**：2019 年初即采用刚发布的 React Hooks (useReducer/useContext/useEffect)；自造 asyncDispatch 中间件包裹 useReducer 处理异步 GraphQL，体现对 redux-thunk 思想的迁移；前后端分离自带 GraphQL server，client 层 query/mutation 封装清晰且复用 todoList 字段片段；项目结构干净：client/context/components 分层，CSS Modules + SCSS 局部样式
- **短板**：onCheck 中直接修改 state.checkedList 再 dispatch，违反不可变原则的明显 bug；几乎无错误处理：所有 Client.query/mutate 失败不捕获，无 catch / error UI；用 apollo-boost 却未利用其缓存/normalization，每次操作全量重拉列表，GraphQL 优势未发挥；无 PropTypes/类型、无有意义测试(仅 CRA 默认渲染测试)、search 后无法回到全量列表的交互缺陷
- **证据**：src/context/index.js:49-90 自定义 asyncDispatch 高阶函数，按 action.type 调用 client 后再 dispatch GET_LIST；src/components/ToDoList/index.js:22-32 onCheck 内 state.checkedList = [...state.checkedList, id] 直接突变 state；src/client/index.js:31-47 add 等 mutation 用 gql 模板，返回 data:addTodo{success,todoList} 重取整列表；package.json:11 react ^16.8.6 + react-scripts 2.1.8，proxy 指向 localhost:4000；src/App.test.js 仅保留 CRA 默认的 renders without crashing 测试
- **年代背景**：2019 年 3 月 React Hooks 刚发布一个月、Apollo/GraphQL 仍属前沿栈，作者能用 Hooks 重写 todo 并自造异步 reducer 中间件，在当年算紧跟潮流的合格水平，但反模式与无错误处理拉低了代码质量评分。

### 2019-04-10 · blog-admin　(功能6/代码6/技术6)
- **定位**：基于 ant-design-pro 脚手架二次开发的个人博客后台管理系统，通过 GraphQL/Apollo 对接独立后端，实现文章的撰写（Markdown 编辑器）、列表管理（已发布/草稿/回收站）、分类标签管理。　|　技术栈：React 16.7, React Hooks, ant-design-pro 2.3.1, antd 3, dva, umi, Apollo Boost / react-apollo, GraphQL, less
- **亮点**：2019 年 4 月即熟练使用 React Hooks（useState/useEffect/useRef），而 Hooks 仅于同年 2 月随 16.8 正式发布，属早期采用者；自定义完整 GraphQL schema（posts/categories/tags/分页/草稿/回收站）并用 Apollo Boost 封装全局错误通知与 fetchPolicy；Hooks + react-apollo render-props + dva 三种范式混用且基本到位；集成自己发布的 npm 包 react-markdown-mirror 作为编辑器，登录链路加了 md5 密码哈希等小定制
- **短板**：draft.js/published.js/trash.js 三个文件近乎逐行复制粘贴，未抽公共组件，DRY 缺失明显；在 Query render-prop 渲染期间直接调用 setTotal()，是会触发警告/潜在循环的 React 反模式（draft/published/trash 三处重复）；多处 catch 块吞掉错误仅 return null 或不处理，边界处理粗糙；『永久删除』按钮为空操作未实现；write reducer 直接 mutate state；自有业务代码无任何测试，仅继承脚手架的 e2e 骨架；package.json name 仍为 ant-design-pro 未改
- **证据**：schema.graphql:1-95 完整定义 Query/Mutation/Post/Categories/Tags/Pagination 等博客后端 schema；src/services/graphql-client.js:7-37 ApolloClient onError 全局 notification + defaultOptions fetchPolicy 配置；src/pages/Write/index.js:27-46 函数组件大量使用 useState/useRef，onCommit 调用自有 markdownEditor.current.getValue()；src/pages/PostsList/published.js:56 在 Query 渲染函数内直接 setTotal(pagination.total)（draft.js:60、trash.js 同样）；src/pages/Write/index.js:38-40 catch(e){return null} 静默吞错；models/postsList.js catch 仅 console.log；src/pages/PostsList/trash.js 末尾 <a>永久删除</a> 无 onClick，功能未实现；src/models/write.js:9-11 reducer 内 state.current = post 直接赋值后 return state；src/models/login.js:11 userLogin 前 md5(payload.password) 客户端哈希定制；config/config.js:81-87 proxy /api -> http://localhost:4000 指向独立 GraphQL 后端
- **年代背景**：2019 年 4 月正值 React Hooks 刚发布两个月、GraphQL/Apollo 在前端社区尚属新潮，作者能在脚手架上快速用 Hooks + Apollo 重构出可用博客后台，按当年标准属中上水平的活跃前端开发者；但大量复制粘贴与渲染期 setState 反模式拉低了工程质量评分。

### 2019-04-12 · react-markdown-editor　(功能8/代码6/技术6)
- **定位**：一个发布到 npm 的 React Markdown 编辑器组件（react-markdown-mirror），基于 CodeMirror + markdown-it + Prism，左侧输入右侧实时预览。　|　技术栈：React 16.8 (Hooks), CodeMirror 5, markdown-it (+多插件), Prism, Webpack 4, Babel 7, SCSS/CSS Modules, react-transition-group, twemoji
- **亮点**：真实发布上线的 npm 包，README/Demo/Props 文档齐全，功能完整可用；2019 年第一时间用上 React Hooks + forwardRef/useImperativeHandle 暴露命令式 API；实现了编辑区与预览区的滚动位置百分比双向同步；深度定制 markdown-it：手动构造 anchor permalink token、container 告警块、twemoji 渲染；工具栏/快捷键的文本变换处理细致（选区包裹、空内容时光标偏移、表格/分割线插入）
- **短板**：完全没有测试，也无 PropTypes/TypeScript 类型约束；install、npm 被误列为运行时 dependencies（多余且体积污染）；highlight 里用 setTimeout(()=>Prism.highlightAll()) 触发高亮属脆弱 hack；多处 useEffect/useCallback 依赖数组为空，存在闭包捕获旧值的隐患；prod webpack 中 react external 的 root 配为 '_' 明显笔误
- **证据**：package.json:2 name 为 react-markdown-mirror，version 1.0.7，已发布；package.json:51,62 dependencies 里出现 'install' 与 'npm' 这两个误加的包；src/component/MarkdownComponent/index.js:49,90 forwardRef + useImperativeHandle 暴露 getValue/setValue；src/component/MarkdownInput/index.js:111-121 监听 CodeMirror scroll 计算百分比并通过 onScroll 同步；src/component/MarkdownOutput/index.js:20-30 预览区按 scrollPercent 反向设置 scrollTop 完成双向滚动联动；src/markdown-it/index.js:24 highlight 内 setTimeout(()=>Prism.highlightAll()) 的高亮触发方式；src/markdown-it/index.js:42-67 自定义 renderPermalink 直接操作 markdown-it token 流；webpack.config.prod.js:130 react external root 配置为 '_'（应为 React）属配置错误
- **年代背景**：2019-04 React Hooks 刚发布两个月、CodeMirror 5 与 markdown-it 是当时主流，作者能在第一时间用 Hooks 写出可发布的编辑器并配齐 webpack4 工具链，按当年标准属于偏上的中级前端水平。

### 2019-04-17 · simple-multipage-webpack　(功能4/代码5/技术4)
- **定位**：一个基于 webpack 4 的前端构建脚手架配置，集成 pug、sass(含 CSS Modules)、postcss、babel 与 dev/prod 环境拆分。　|　技术栈：webpack 4, babel @babel/preset-env, pug, node-sass, postcss/autoprefixer, webpack-merge, MiniCssExtractPlugin
- **亮点**：base/dev/prod 通过 webpack-merge 拆分，结构清晰；用 oneOf 区分 global.scss 与 CSS Modules 两类样式处理；prod 启用 MiniCssExtract、CleanWebpackPlugin、BundleAnalyzer，dev 启用 HMR，环境意识到位；scss 提供 vw->rem 的移动端适配方案(rem 函数+媒体查询封顶)，符合当年移动端实践
- **短板**：名为 multipage 却只有单个 entry 和单个 HtmlWebpackPlugin，缺少 glob/动态多入口生成逻辑，与项目目标名不副实；无 README，作为分享型配置仓库可用性差；无测试、无 CI(仅有 dependabot 合并)；src 内容极简(空 pug 骨架、仅 import 一个 scss)，更像个人模板而非完整脚手架
- **证据**：webpack.config.js:10-12 entry 仅 index 单入口；webpack.config.js:41-44 只注册一个 HtmlWebpackPlugin(template index.pug)，无多页面遍历；webpack.config.js:55-86 用 oneOf 区分 global.scss 与 modules 的 scss 规则；webpack.config.js:190-191 用 merge(base,dev/prod) 按 env 切换；src/index.pug 为空 body 的 HTML 骨架；src/scss/utils.scss:3-5 自定义 rem($px) 函数做 vw 适配；仓库根目录无 README*
- **年代背景**：2019 年 webpack 4 + babel7 + 手写多 loader 配置是前端主流，这套配置反映了当年合格水平，但仍属常规套路且未兑现 multipage 名号。

### 2019-04-19 · typegraphql-CRUD-demo　(功能4/代码6/技术5)
- **定位**：用 TypeGraphQL 在 Koa+Apollo 上实现的一个 todolist 增删查 CRUD 学习型 demo，数据存内存。　|　技术栈：TypeScript, type-graphql, apollo-server-koa, Koa, GraphQL, reflect-metadata
- **亮点**：采用 2019 年仍属前沿的 code-first 装饰器范式（@ObjectType/@Resolver/@Query/@Mutation/@Arg）；模块化目录清晰：type/resolver/schema 三层分离，graphql/todolist 子模块组织；tsconfig 正确开启 experimentalDecorators 与 emitDecoratorMetadata，对 type-graphql 依赖配置到位；README 给出可直接运行的 query/mutation 示例
- **短板**：纯内存数据无持久化，仅 demo 级别（符合目标但实用性低）；start 脚本用管道 `npm run watch | npm run server` 无法正确并行运行两个进程，应使用 concurrently 或 &；todo 查询声明返回 TodolistType | null，但 Array.find 实际返回 undefined，类型不严谨；类字段未做明确赋值/初始化，无 strict 模式，无任何测试与 CI
- **证据**：src/graphql/todolist/todolist.type.ts:1-11 使用 @ObjectType/@Field(type=>ID) 装饰器定义 GraphQL 类型；src/graphql/todolist/todolist.resolver.ts:25-54 @Resolver 类内含 Query(todolist 带 completed 过滤)、todo、addTodo、removeTodos 四个解析器；src/graphql/schema.ts:3-5 buildSchemaSync({ resolvers:[TodolistResolver] }) 构建 schema；app.ts:7-12 ApolloServer + Koa applyMiddleware 标准接线，监听 4000 端口；package.json:7 "start": "npm run watch | npm run server" 管道用法存在缺陷；todolist.resolver.ts:37-38 todo 声明 TodolistType|null 但 find 返回 undefined，类型不符
- **年代背景**：2019-04 时 type-graphql 还是 v0.17 的早期库，code-first 装饰器式 GraphQL 在当年属新潮范式，作者能搭起这套技术栈并做模块化拆分，按当年标准属合格偏上的尝试型 demo。

### 2019-04-21 · blog-server　(功能6/代码5/技术5)
- **定位**：一个博客后台 GraphQL 服务，基于 Koa + Apollo Server + TypeGraphQL + Mongoose，提供文章/标签/分类的增删改查及基于 koa-session 的登录与接口鉴权。　|　技术栈：TypeScript, Koa, Apollo Server, TypeGraphQL, GraphQL, Mongoose, MongoDB, koa-session, lodash
- **亮点**：紧跟2019年潮流的 code-first GraphQL 技术栈(TypeGraphQL 0.17 装饰器)；按领域清晰分层(graphql resolver/type/input 与 schema 模型分离)；鉴权设计合理：@Authorized + 自定义 authChecker 接入 koa-session；更新文章时对 categories/tags 引用做增删差异同步，考虑了关联维护
- **短板**：登录逻辑有bug：find() 返回数组恒为真，且密码明文比较无哈希(router/user.ts:11)；db.connect 标注为 void 却是异步，app.ts await 了 undefined，可能DB未连就启动；session 密钥硬编码在源码中(app.ts:30)；tsconfig strict 被注释、几乎每个文件顶部 /* eslint-disable */，类型/lint 形同虚设；无测试、无CI、validate:false 无输入校验，循环内串行 await 性能欠佳
- **证据**：src/router/user.ts:11-12 — const user = await UserModel.find({userName,password}); if(user) ... find 返回数组，永远 truthy，登录恒成功；密码明文；src/db.ts:3 connect 签名 (): void 但内部 mongoose.connect().then()，app.ts:27 await connect() 实际 await undefined；app.ts:30 app.keys = ['blog server secret hurr'] 硬编码会话密钥；tsconfig.json:26 /*"strict": true*/ 被注释；post.resolver.ts:22 等文件顶部均 /* eslint-disable */；src/graphql/categories/categories.resolver.ts:40 PostModel.updateMany({categories:oldName},{'categories.$':name}) 使用位置 $ 但查询未在数组上精确匹配，疑似bug；src/graphql/post/post.resolver.ts:66-91 addPost 中对每类关联做多次串行 await(updateMany/find/create) 往返
- **年代背景**：2019年4月 TypeGraphQL(0.17)与 Apollo Server 2.x 的 code-first 装饰器范式尚属前沿，作者能在当时把这套类型驱动 GraphQL 栈跑通并合理分层，属于紧跟潮流的合格水平，但严格类型与安全实践未到位。

### 2019-04-23 · filter-dropdown　(功能7/代码7/技术6)
- **定位**：一个无依赖的原生 JS 下拉筛选组件，复刻 ant-design 表格列头的 filter dropdown 交互（多选/单选、确定/重置、对齐定位）。　|　技术栈：JavaScript (ES2019), Webpack 4, Babel 7, SCSS / CSS Modules, Pug, PostCSS/autoprefixer, UMD
- **亮点**：2019 年即用 ES 私有字段(#field)与箭头函数类属性，配 Babel proposal 插件，技术嗅觉超前；无任何运行时依赖的纯原生实现，发布为 npm 包并提供 UMD/script 标签两种用法；用 CSS Modules + SCSS 高度还原 antd 视觉（checkbox 动画、slideUpIn/Out 关键帧、毛玻璃阴影）；事件绑定/解绑成对处理，destroy/open/close 公开 API 设计清晰，构造函数做了入参校验与默认值合并
- **短板**：完全无测试、无 CI 配置；babel proposal 插件被错放进 dependencies（应为 devDependencies）；destroy() 先清空 outerHTML 后又对已脱离的节点 removeEventListener，逻辑有缺陷；未提供 TypeScript 类型声明，作为发布库略欠完善；global.scss 引用了仓库中并不存在的 ./scss/utils，且 global.scss 实际未被组件使用
- **证据**：src/index.js:6-17 使用 #isMount/#filterDropdown 等 ES 私有类字段；src/index.js:39 #onClickTrigger = event => {...} 箭头函数类属性绑定 this；src/index.js:127-133 destroy 先 outerHTML='' 再 removeEventListener，存在悬挂引用问题；package.json:43-46 @babel/plugin-proposal-* 被列为 dependencies；webpack.config.js:101-111 生产构建输出 UMD 库 libraryTarget:'umd', libraryExport:'default'；src/styles.scss:201-235 自定义 checkboxEffect/slideUpIn/slideUpOut 关键帧动画；src/global.scss:1 @import './scss/utils' 指向仓库中不存在的路径
- **年代背景**：2019 年原生 JS 组件仍以 ES2015 语法为主流，作者主动启用尚处 Stage 3 的私有字段并搭好 Babel/Webpack4 工具链发布 npm 包，按当年标准属于中上水准的前端工程实践。

### 2019-04-28 · switch-button　(功能8/代码8/技术7)
- **定位**：一个框架无关的原生 TypeScript 开关按钮组件库，复刻 Ant Design 的 Switch 样式与交互，通过 Proxy 实现响应式状态。　|　技术栈：TypeScript, Proxy/Reflect, WeakMap, Less, Jest, esbuild, Babel, CircleCI, GitHub Actions, npm
- **亮点**：用 Proxy+Reflect 实现真正的响应式状态，赋值即更新视图，设计优雅；WeakMap 双向映射(eleToProxy/proxyToRaw)管理生命周期，deleteSwitch 干净解绑事件并置 delete 标志防止泄漏与误触发；已发布 npm(v2.1.0)，框架无关可任意环境使用，完整的 11 个 Jest 测试覆盖响应式/点击/loading 禁用/删除后失效等边界；extend() 工厂模式支持 prefixCls/role/small 定制，工程化完备(CI 双套+Codecov+esbuild 演示+gh-pages)
- **短板**：全局共享 internalClickEvent 与模块级 WeakMap，同一元素重复 createSwitch 未做幂等保护；Proxy 仅代理 checked/disabled/loading，text/onChange 创建后不可响应式更新；无键盘可访问性支持(空格/回车切换)，role 虽可设但缺 aria-checked 同步；依赖自研未广泛验证的 wave-effect，stars=0 实际使用面窄
- **证据**：src/index.ts:31-48 createProxy 用 new Proxy + Reflect.set 拦截三个状态字段并分发到对应 handler；src/index.ts:25-26 WeakMap<HTMLElement,ProxySwitchValues> 与 proxyToRaw 双向映射；src/index.ts:151-168 deleteSwitch 调用 clearEffect、removeEventListener、删除映射并置 rawValues.delete=true；src/index.ts:50-66 internalClickEvent 在 loading/disabled 时 return，先调 onChange 再改 proxyValue.checked；src/test.ts:1-104 共 11 个测试含 'onChange shouldnt trigger after switch delete' 等删除后行为断言；src/index.less:5-6 注释 'Copy from Ant Design' 并 @import wave-effect/src/wave.less
- **年代背景**：仓库元信息创建于 2019，但磁盘上的代码是约 2021 年的 v2 重写(TS4.2/esbuild0.11/jest26/CircleCI node:15，HEAD 提交 2021-05-25)；按该真实年代衡量，Proxy 响应式与无框架组件库的设计思路在当时颇为成熟老练，属个人开发者中上水准。

### 2019-05-16 · leetcode　(功能6/代码6/技术4)
- **定位**：作者个人的 LeetCode 算法刷题记录，14 道题的 JavaScript 解法，附中文思路注释。　|　技术栈：JavaScript, ES6, JSDoc
- **亮点**：ES6 用法地道（解构交换、Array.from、spread、reduce 拍平）；每题保留 JSDoc 类型签名，并写了清晰的中文算法思路；个别题展现真实算法理解：格雷码递归对称构造、辗转相除求 GCD、696 题 prv>=cur 计数技巧、459 题 /^([a-z]+)\1+$/ 反向引用正则；常保留多套解法/备选思路，体现刷题时的反思与对比
- **短板**：题量极少（仅14题）且无组织/索引，README 仅'争取进步'三字；多处用冒泡排序等暴力解（164 最大间距、215 第K大），不达题目复杂度要求；无测试、无 CI、无 package.json，纯散落脚本；605 种花问题边界处理略冗杂，依赖 flowerbed[1] 等硬编码索引，健壮性一般
- **证据**：459.重复的子字符串.js: 单行正则 /^([a-z]+)\1+$/.test(s) —— 利用反向引用判断周期串，思路精巧；89.格雷编码.js: makeCode 递归，temp[i]='0'+result[i]、temp[max-i]='1'+result[i] 实现镜像反射构造；914.卡牌分组.js: gcd=(a,b)=>b===0?a:gcd(b,a%b) 辗转相除 + reduce 统计频次；164. 最大间距.js 末注释: '这个解法显然是不符合题意要求的线性时间复杂度和空间复杂度，只能解出答案了'；682.棒球比赛.js 末注释: '再回头捡起的时候已经过了10个月... 这次一定要坚持✊'，git 提交时间 2020-03-11 印证；215. 数组中的第K个最大元素.js 使用 function 声明而非箭头函数，与其余文件风格不一致；README.md 全文仅 '# leetcode\n\n争取进步'
- **年代背景**：2019 年 ES6/箭头函数/解构已是前端日常，作者熟练使用属合格水平；但作为个人刷题仓（14题、无测试无工程化）目标本就轻量，按当年学习型仓库标准衡量，代码整洁度尚可而技术深度有限。

### 2019-05-22 · wechaty-bot　(功能6/代码5/技术4)
- **定位**：基于 wechaty 0.27 + koa 封装的简易微信群管理助手，支持关键词自动回复、新人入群欢迎、群昵称规范校验，并通过 HTTP 接口触发群发言/校验。　|　技术栈：TypeScript, wechaty 0.27, Koa, koa-router, koa-bodyparser, ts-node, dayjs, dotenv, qrcode-terminal
- **亮点**：将 wechaty 实例封装为 WechatBot 类，提供 onMessage/onLogin 多回调注册机制，模块边界清晰；工程分层合理：bot/router/utils/server 各司其职，入口 app.ts 组织业务逻辑；启用 tsconfig strict 模式并定义 IMessageCb/ILoginCb/IcontactList 接口，2019年TS项目中算规范；扫码登录附带二维码图床URL兜底，体现实用细节
- **短板**：app.ts 与 router/chat.ts 循环依赖(router 反向 import app 的导出)，架构耦合；多处拼写/笔误：WATHINGROOM、PROT、process.env.port 大小写不一致导致端口配置实际失效；在 map 内用 async new Promise 包裹 await 属反模式，可直接用 async 箭头函数；writeLog 中 reject() 后又 throw 冗余且无意义；错误处理多为 console.log 吞掉；无测试、无CI、无 .env.example，README 接口文档与代码(/chat/name)不完全一致
- **证据**：src/bot/index.ts:12-38 WechatBot 类封装 wechaty 实例并维护回调列表，绑定 scan/logout/error/message 事件；app.ts:16 `process.env.WATHINGROOM` 与 README 中 WATCHINGROOM 拼写不符；app.ts:20 `process.env.port` 与变量名 PROT 拼写错误，配置实际不生效；src/router/chat.ts:2 `import {wechatBot,...} from "../../app"` 与 app.ts:6 `import app from "./src/server"` 构成循环依赖；app.ts:82-88 在 .map 中 `return new Promise(async resolve=>{...})` 包裹 await，反模式；src/utils/writeLog.ts:11-13 reject() 之后紧跟 throw，逻辑冗余；src/utils/messageFilter.ts:20-29 main/text 两级关键词匹配，结构清晰但 main:"" 空串 includes 恒真依赖隐式行为
- **年代背景**：2019年 wechaty 0.27 仍处快速迭代期、社区 TS 模板稀缺，作者能用 strict TS 自行做面向对象封装与 Koa 分层已属合格普通水平，但循环依赖与多处配置笔误拉低了工程严谨度。

### 2019-05-30 · page-scroll　(功能6/代码6/技术6)
- **定位**：一个面向移动端的纯 TypeScript 全屏整页滑动（竖向翻页）库，基于 touch 事件 + requestAnimationFrame + translate3d，支持速度惯性翻页与多种缓动函数。　|　技术栈：TypeScript, umi-library(umi-lib), Rollup, Touch Events API, requestAnimationFrame, CSS translate3d
- **亮点**：正确使用 rAF + translate3d 做 GPU 合成的逐帧动画；实现了基于触摸速度的惯性翻页判定（speed>momentum）而非简单阈值；用 TS 联合类型 TweenFunc 把全套 Penner 缓动名做了类型化；tsconfig 开启 strict，类成员用 private readonly、箭头方法绑定 this，2019 年算地道
- **短板**：README 几乎为空（仅一行仓库名），无任何使用文档；无测试、无 CI；IOptions 把全部选项标为必填却靠解构默认值，类型与实际用法不自洽；tween 表用 {[index:string]:any} 牺牲类型安全，查表 Tween[name][func] 完全 untyped；页高在构造时缓存 window.innerHeight，缺少 resize/旋转屏处理；touch 未处理 passive/preventDefault
- **证据**：src/index.ts:54-119 完整的 touchstart/move/end + scrollTo(rAF+Tween) 动画管线；src/index.ts:79-89 onScrollEnd 用速度判定翻页方向的惯性逻辑（嵌套三元+表达式内赋值，较密集）；src/tween.ts:34-231 移植自 Robert Penner 的全套缓动方程（Quad..Bounce），属借用算法非原创；src/tween.ts:1 TweenType={[index:string]:any} 削弱了类型安全；tsconfig.json:29 strict:true；.umirc.library.js 用 umi-lib 产出 esm/umd/min；package.json author/license 字段实际未配置完整，version 1.0.0 但未发布(0 stars)
- **年代背景**：2019 年移动端整页滑动多靠 fullpage.js/better-scroll 等现成库，作者选择用 strict TypeScript + umi-library 工具链从零手写一个轻量实现，rAF+translate3d+缓动+惯性的组合在当年属于合格偏上的前端工程水平，但缺文档/测试与库本身的小体量限制了上限。

### 2019-06-09 · gatsby-blog　(功能7/代码6/技术4)
- **定位**：作者个人博客，基于官方 gatsby-starter-blog fork，加入暗/亮主题切换与中文文章内容　|　技术栈：Gatsby 2.x, React 16.8, GraphQL, SCSS/node-sass, Typography.js, PrismJS, Markdown/remark
- **亮点**：可正常上线运行的真实博客(有域名/22篇文章)；CSS变量驱动的暗/亮主题切换实现完整；html.js内联IIFE在首屏前读localStorage防FOUC；自定义Prism代码块主题+按语言显示标签；代码风格统一(prettier),命名清晰
- **短板**：本质是官方starter的fork,核心骨架(gatsby-node/blog-post/seo/bio)几乎未改动；主要自定义点(主题切换/阅读时间/代码配色)多借鉴自overreacted.io,原创度有限；无任何测试,无CI；package.json元信息未更新(author/repo仍指向gatsbyjs官方)；技术难度低,属常规套模板博客
- **证据**：README.md:3 明确写 'Forked from Gatsby blog starter'，:5 'Some ideas from Dan Abramov's Blog'；package.json:2-6 name仍为gatsby-starter-blog、author为Kyle Mathews、repo指向gatsbyjs/gatsby-starter-blog(未改)；src/html.js:16-27 body默认className=dark并内联脚本读localStorage('blogTheme')防止主题闪烁；src/components/toggle/index.js 用checkbox+createRef实现纯CSS开关，componentDidMount同步body.className；src/global.scss:5-79 通过 --bg/--textNormal 等CSS变量在 body.light/.dark 下定义双主题；src/utils/helpers.js formatReadingTime 用咖啡/便当emoji显示阅读时长(overreacted.io同款实现)；gatsby-node.js/blog-post.js/index.js 与官方starter基本一致，仅index.js加了timeToRead与Footer；无 *.test.js，无 .github CI目录
- **年代背景**：2019年Gatsby 2 + React Hooks刚普及，fork官方starter做带暗黑模式的个人博客是当时主流且合理的做法，CSS变量换肤在当年算时髦但非高难，故按2019标准给中等偏上完成度、中等偏下技术深度。

### 2019-06-13 · useform　(功能4/代码5/技术4)
- **定位**：一个 50 行的极简 React Hooks 表单字段管理工具，通过 createField 向输入组件注入 value/onChange，并提供 setFieldsValue/getFieldsValue。　|　技术栈：JavaScript, React Hooks, useState, React.cloneElement
- **亮点**：React Hooks 发布(2019.2)仅 4 个月即上手实践，紧跟新范式；用 setFields(prev => ...) 函数式更新，避免闭包陈旧值；verification 辅助函数对未初始化字段抛错，有基本的边界意识
- **短板**：功能单薄：无校验规则、无提交处理、无字段级错误状态；getFieldsValue 假定入参为数组(调用 reduce)，但 verification 同时兼容数组/对象，前后不一致；用 typeof value === 'object' 判断是否为事件对象，极其脆弱；无测试、无构建配置、无 CI、无 TypeScript、未真正发布(0 star)；createField 仅支持单个元素且硬编码 value/onChange，复用性差
- **证据**：useForm.js:7 `if (typeof value === "object") value = value.target.value;` 脆弱的事件检测；useForm.js:30 getFieldsValue 直接 `fields.reduce` 假定数组，与 line 12-13 verification 的数组/对象兼容逻辑矛盾；useForm.js:40 `React.cloneElement(Component, {value, onChange})` 通过克隆注入 props；useForm.js:8 `setFields(prev => ({ ...prev, [fieldName]: value }))` 正确使用函数式更新；package.json 仅 8 行，无 dependencies/scripts/test，main 指向源文件 useForm.js；git log 仅 1 次 commit (b4368b9 init commit)
- **年代背景**：创建于 2019-06-13，React Hooks 正式版(16.8)发布仅约 4 个月，此时社区尚无成熟的 hooks 表单方案(react-hook-form 也是 2019 下半年才起步)，作者能快速产出可用的 hooks 封装属于早期跟进者，但实现深度与健壮性仍停留在练手/玩具级别。

### 2019-07-27 · next-blog　(功能6/代码5/技术5)
- **定位**：基于 Next.js + MDX 的个人技术博客，构建时扫描 blog 目录下的 mdx 文章生成页面与文章索引。　|　技术栈：Next.js, React, MDX, Express, SASS/node-sass, typography.js, dayjs, rehype-prism
- **亮点**：自写构建期内容管线 createPostsList：读取mdx、注入Layout包裹、生成prev/next与readTime、复制资源；用自定义 Express server 配合 next 路由 /posts/ 并处理中文路径 decodeURIComponent；CSS变量驱动暗色主题 + 完整的 prism 代码高亮主题与语言角标；对当年 Next.js MDX 工具链(@next/mdx、@zeit/next-sass、rehype-prism)的正确整合
- **短板**：依赖大量使用 latest 不锁版本，可复现性差；createPostsList 在 server.prepare 后同步读写文件、用 ctime 当发布时间，作者自注逻辑太乱；无测试/CI/eslint，README 仅一行；生成产物 posts.json 已在 gitignore 却仍被提交进仓库；列表用 index 作 key、a 标签裸跳转未用 next/link 等小瑕疵
- **证据**：utils/createPostsList.js:27-55 文章读取/排序/写页面/生成meta的核心逻辑，含 // todo 逻辑太乱；server.js:15-20 Express 通配路由 + 正则匹配 /posts/ 并 decodeURIComponent 处理中文 slug；next.config.js:12-16 withSass(withMDX(...)) 组合插件，pageExtensions 含 mdx；package.json:14-26 react/next/node-sass 等多处写 latest；pages/global.scss:75-294 完整移植的 prism 暗色高亮主题与 language 角标；pages/index.js:14 li 用 index 作 key
- **年代背景**：2019年中 Next.js 仍是9.x、需自建Express server且MDX生态(@next/mdx/@zeit/next-sass)刚起步，能把这套工具链跑通并自写构建期文章管线属当年合格偏上的前端水平。

### 2019-08-07 · flutter-todo-list　(功能5/代码5/技术4)
- **定位**：作者的第一个 Flutter 练手 demo：一个带 Tab 分类（全部/已完成/未完成）的待办列表 App，数据来自 jsonplaceholder 占位 API。　|　技术栈：Dart, Flutter, Material Design, dio (HTTP), StatefulWidget, TabController
- **亮点**：地道使用 2019 年 Flutter 范式：TabController+SingleTickerProviderStateMixin、ListView.builder、Form 校验；删除待办带 SnackBar Undo 撤销交互（用 .. 级联操作符），交互思考超出纯 CRUD demo；按 All/Completed/Uncompleted 派生过滤列表，列表项用 ValueKey(id) 保证复用正确；模型层分离（model.dart 提供 fromJson 工厂构造）
- **短板**：纯内存状态，无持久化，重启后增删全部丢失；fetchTodo 声明 currentPage 参数却从未使用，分页是空架子；test/widget_test.dart 是未改的默认计数器模板，与本 App 完全不符且会失败；错误处理仅 print(e)，加载态判断用全局 _todoList.isEmpty 导致空数据时三个 Tab 都卡在转圈；引号单双混用、残留 new 关键字，代码风格不统一
- **证据**：lib/pages/todoList/todoList.dart:31 void fetchTodo({int currentPage = 1}) — 参数声明后未被使用；lib/pages/todoList/todoList.dart:40-42 catch(e){ print(e); } 仅打印不处理；lib/pages/todoList/todoList.dart:107 if(_todoList.isEmpty) 用全局列表判断 loading，三个 Tab 共用；lib/pages/todoList/todoList.dart:148-162 删除项带 SnackBar Undo 撤销，使用 .. 级联；test/widget_test.dart:18-28 仍是 'Counter increments smoke test' 默认模板，断言 find.text('0')，与待办应用无关；pubspec.yaml:26 dio: ^2.0.13，环境 sdk >=2.1.0 <3.0.0，符合 2019 年技术栈；lib/pages/todoList/model.dart:10-16 TodoModel.fromJson 工厂构造，模型层分离
- **年代背景**：2019 年 Flutter 刚进入主流（1.x 时代），StatefulWidget+setState 是当时最常见做法，作者用到 TabController、Form 校验、dio、SnackBar Undo 已属一个认真完成的入门作品；按当年初学者标准属合格偏上，但残留模板测试与无持久化拉低了完成度。

### 2019-09-07 · mdx-blog　(功能8/代码6/技术6)
- **定位**：作者本人的个人博客（v2 重写版），基于 Gatsby + MDX 构建，含自动深色模式、页面转场动画、Algolia 搜索与约 40 篇技术文章。　|　技术栈：Gatsby 2, React 16, MDX, framer-motion, GSAP, SCSS/node-sass, Algolia / react-instantsearch, Prism / mermaid, RxJS(文章用)
- **亮点**：已上线可用的完整个人博客，内容丰富(Redux/React-Redux/RxJS 源码笔记、TS infer/工具泛型)；gatsby-plugin-transition-link + GSAP TimelineMax 实现带方向的页面转场，逻辑非平凡；framer-motion clip-path 圆形展开移动端导航；自动深色模式：prefers-color-scheme→时间→存储的函数式 pipe 回退链 + SSR 内联脚本防闪烁；MDX 集成 mermaid/prismjs，Algolia 搜索
- **短板**：大小写敏感的 import bug：MobileNav/index.jsx 引入 './navigation' 实际文件为 Navigation.jsx，Linux 构建会失败；主题用 sessionStorage 而非 localStorage，关闭浏览器后不持久；refEleProperty.js 的 addClass/removeClass 把 rest 数组整体传给 classList.add(spread 误用)；全程无 TypeScript(作者却写 TS 文章)、无测试(test 脚本仍是 starter 默认 exit 1)；package.json 仍残留 gatsby-starter-default 的 name/author 等模板元信息
- **证据**：package.json: name 仍为 'gatsby-starter-default'、author 'Kyle Mathews'，但依赖含 gatsby ^2.19.7 / algoliasearch ^4.0.3 / framer-motion ^1.8.4，说明开发延续至 2020 初；src/Components/MobileNav/index.jsx: import Navigation from './navigation' 与实际文件 Navigation.jsx 大小写不符；src/utils/themeMode.js: themeModePipe(...funcs) 函数式回退 + __htmlScriptDefaultTheme() 注入 <script> 防 FOUC；src/Components/TransitionTo/index.jsx: swipeTopDirection/swipeBottomDirection + TimelineMax 处理 entry/exit 四象限转场；src/utils/refEleProperty.js: classList.add(classnames) 传入 rest 数组而非展开；src/Layout/Post/index.jsx: MDXRenderer 渲染 + GraphQL 查询 previous/next 邻接导航
- **年代背景**：2019 年底正值 Gatsby 2 + MDX + React Hooks 生态成熟期，本仓库紧跟当时主流静态站点范式并叠加 GSAP/framer-motion 转场与自动深色模式，属当年中上水平的前端个人项目，按当年标准评分。

### 2019-09-11 · number-to-chinese-characters　(功能6/代码7/技术5)
- **定位**：将阿拉伯数字转换为中文大写金额（如 101010 -> 壹拾万零壹仟零壹拾元整）的单文件 JS 工具库。　|　技术栈：JavaScript, ES2018, Babel, Rollup, Jest, UMD
- **亮点**：核心算法仅 ~30 行即覆盖整数分节、连续零压缩、角分小数等大写金额规则；零的压缩与补'零'逻辑(zeroCount 计数 + zeroCount<4 抑制空节单位)处理得当；测试用例覆盖 0/进位零/万亿分节/纯小数等关键边界，TDD 意识良好；完整的现代化工具链(Babel+Rollup 产出 UMD，Jest 测试)，工程结构清晰
- **短板**：bigRadix 仅 3 项，金额 >= 10^12(万亿)时单位错乱，无溢出处理；无任何输入校验(负数/非数字/超过两位小数/科学计数法大数均会出错)；static 类仅作命名空间用，纯静态成员用 class 略显冗余，普通对象/函数更地道；README 极简，仅一行用法，未说明取值范围与限制
- **证据**：index.js:1-5 用 static 字段定义 digits/radix/bigRadix/decimalsRadix 映射表，结构清晰；index.js:11-24 forEach 中以 currentIndex 推导 quotient(分节)与 modulus(节内位)，配合 zeroCount 实现连续零压缩；index.js:21 `if (modulus === 0 && zeroCount < 4)` 正确抑制整节为零时的万/亿单位；index.js:3 bigRadix=['','万','亿'] 仅 3 项，决定了上限约为亿级而无万亿支持；test.js 提供 12 个用例含 0、101010、4001001020、0.01 等边界；rollup.config.js 用 babel+clear+uglify 产出 dist/index.js(UMD 压缩单文件)；package.json 使用 @babel/plugin-proposal-class-properties 支持类静态字段提案语法
- **年代背景**：2019 年类静态字段还是 Stage-3 提案、ES Module + Rollup/Babel 工具链刚成主流，作者能熟练用提案语法配齐构建与 Jest 测试，属于当年中上水平的前端工程实践。

### 2019-09-19 · react-animate-skeleton　(功能7/代码7/技术7)
- **定位**：基于 styled-components 的 React 动画骨架屏组件库，提供 Skeleton/Section/Item/Image/Gap/Horizontal/Padding 等可组合原语，已发布到 npm (v2.1.0)　|　技术栈：TypeScript, React 16, styled-components 4, father (rollup), docz/mdx
- **亮点**：巧妙的反向布局思路:用repeating-linear-gradient让行透明、间隙为背景色，用border当padding，骨架由背景透出而非画方块；动画用background-size 200%+移动background-position+background-clip:content-box，shimmer正确避开padding；类型级复用PickCSSProperty<K>映射React CSSProperties，props按真实CSS值类型校验；styled-components ThemeProvider配合styled.d.ts对DefaultTheme做module augmentation，2019地道写法；组件高度可组合(Image=Padding+Item，Section=Padding+SectionElement)，API设计有品味
- **短板**：完全无测试、无CI；git历史被压成单次提交，无法考察演进过程；SectionProps中classNames拼写错误(应为className)，与实际用法不符；README极简，文档/示例存在不一致(Image示例代码padding={0}但实时demo为padding={8})；ItemElement仅设background:transparent，styled包装价值有限
- **证据**：src/Components/Section/index.tsx:28-36 repeating-linear-gradient实现行/间隙骨架；src/Components/Skeleton/index.tsx:14-29 linear-gradient+background-size 200% 200%+background-clip:content-box做shimmer动画；src/Components/Padding/index.tsx:10-13 用border-width/border-color实现内边距(让背景从border透出)；src/utils/pickCSSProperties.ts:7 PickCSSProperty<K extends keyof CSSProperties>类型工具；src/Components/styled.d.ts:4-6 declare module styled-components扩展DefaultTheme；src/utils/convert.ts:1-2 柯里化number→px归一化helper；src/Components/Section/index.tsx:25-27 动态calc()组合尺寸；src/Components/Section/index.tsx:17 SectionProps.classNames拼写错误；package.json:3 version 2.1.0，已发布npm；peerDependencies react ^16.0.0
- **年代背景**：2019年React生态正处styled-components v4 CSS-in-JS鼎盛期、hooks刚普及、father/docz是流行的库构建+文档方案，此项目用严格TS+module augmentation+纯CSS gradient技巧实现骨架屏，在当年属于扎实且有巧思的中上水准开源库。

### 2019-12-03 · redux-sourcecode-study　(功能7/代码7/技术6)
- **定位**：通过用 TypeScript 逐行重写并加中文注释的方式，学习并拆解 Redux v4.0.5 的核心源码（createStore/combineReducers/applyMiddleware/compose 等），并附带一个自写的精简版 redux 实现。　|　技术栈：TypeScript 3.8, Redux v4.0.5, Webpack 4, Babel 7, redux-logger, redux-devtools-extension
- **亮点**：完整重写 Redux 全部核心模块+utils，类型系统也照搬（ExtendState/CombinedState 的 $CombinedState unique symbol 技巧、PreloadedState 递归映射类型、多重函数重载）；额外手写 simple-redux.js 精简实现，证明是真正理解了闭包/中间件 compose 原理而非纯誊抄；中文注释细致、标注了多处官方 issue 链接（如 #3474/#3488）解释边界处理动机；index.ts 用自定义同步/异步中间件+logger+devtools 串起完整 demo 做验证；诚实保留 todo 与自我提问，体现真实学习过程
- **短板**：本质是临摹官方源码做笔记，原创工程量与设计决策有限，techLevel 受限于此；无任何单元测试，靠 index.ts 手动 console 验证；package.json 元信息空置（name=study、description/author 留空），略随意；index.ts 中多处 @ts-ignore 绕过中间件 dispatch 返回 Promise 的类型问题，未深究正确类型；simple-redux.js 有拼写错误（chins 应为 chain），且省略了 isPlainObject 等校验
- **证据**：src/redux/createStore.ts:58-86 完整搬运官方三段式函数重载与泛型签名（S,A,Ext,StateExt）；src/redux/types/store.ts:16-63 ExtendState/CombinedState($CombinedState unique symbol)/PreloadedState 递归映射类型全部到位；src/redux/createStore.ts:262-263 注释 'currentListeners设置为null...todo 还是没看懂'，真实学习者标记；src/redux/combineReducers.ts:215-216 注释 '在下面抛出的意义难道是调用时才报错？' 自我提问；src/simple-redux.js:1-60 作者自写精简版 redux（含 compose/applyMiddleware/createStore），变量名 chins(拼写) 见 line17；src/index.ts:84-87 composeWithDevTools+applyMiddleware 串接，line85 @ts-ignore todo 正确类型；tsconfig.json:30-37 strict/noImplicitAny/strictNullChecks/alwaysStrict 全开，符合 2019 严谨配置；src/redux/utils/actionTypes.ts randomString + PROBE_UNKNOWN_ACTION 与官方一致
- **年代背景**：2019 年底 Redux 4.0.5 是主流、TS 3.8 + Webpack4/Babel7 是当年标准前端工具链，源码级阅读并 TS 重写官方库在当时是扎实但常见的进阶学习方式，按当年标准给出的是一份高质量学习笔记。

### 2020-03-07 · utils　(功能7/代码7/技术6)
- **定位**：一个 Lerna 管理的前端工具 monorepo，发布了 yuhooks（25 个 React hooks）与 yuutils（DOM/事件/键码等通用工具）两个 npm 包，配 dumi 文档站。　|　技术栈：TypeScript, React Hooks, Lerna monorepo, dumi, father-build, lodash.debounce/throttle, ESLint(@umijs/fabric), Prettier, gh-pages
- **亮点**：完整的库工程化：Lerna 多包 + father-build 产 ESM + dumi 文档 + 自动导出脚本 + 预提交 lint/prettier；良好抽象：createTimerHook / createStorageHook 工厂复用，eventListener 自动探测 on/off、addEventListener、addListener 三套 API；TypeScript 函数重载用得地道（eventListener、useTitle、useCssVar、devWarning）；useReactiveRef 用 Object.defineProperty 实现可触发重渲染的 ref，思路有巧思；hooks 覆盖面广且贴近 2020 年浏览器新 API（Clipboard、Share、Permissions、NetworkInformation、prefers-color-scheme）
- **短板**：完全没有单元测试，CI 也缺失；明显 bug：dom/inset.ts 的 CSS 值写成 `${offset},`（尾逗号导致样式无效）；useEventListener 用空依赖数组 useEffect，listener 捕获陈旧闭包，多数 hook 拿不到最新 state；createTimerHook 的 start 用 setTimeout 名义清理但 type 可能是 setInterval（clearTimeout 清 interval 虽可行但语义混乱），且 useCallback 空依赖会锁死 fn/delay；useShare 在不支持或 canShare=false 时 Promise 永不 resolve/reject（挂起）；isRef 用 Object.keys(ref).length===1 判断不够健壮；版本停留在 0.0.1-alpha.0，0 star，属个人练习性质
- **证据**：packages/utils/src/dom/inset.ts: top/right/bottom/left 写成 `${offset},` 带尾逗号，是确凿的 CSS bug；packages/hooks/src/useEventListener/index.ts: React.useEffect(() => eventListener(...), []) 空依赖，listener 闭包不更新；packages/hooks/src/utils/createTimerHook.ts: stop 用 clearTimeout 清理 window[type]（可能是 setInterval）；start/stop 的 useCallback 依赖为 []；packages/hooks/src/useShare/index.ts: 当 canShare 为 false 时 Promise 既不 resolve 也不 reject；packages/utils/src/event-listener.ts: 通过探测 'on'/'off'、'addEventListener'、'addListener' 三组键名兼容不同事件源，含函数重载签名；packages/hooks/src/useReactiveRef/index.ts: 用 Object.defineProperty 给 {current} 装 getter/setter，setter 内触发 forceUpdate；scripts/export-hooks.js: 用 glob 扫描 use* 目录自动生成 src/index.ts 的导出，集成进 build 流程；packages/utils/src/key-code.ts 注释 'copy from react-component/util'，useStartTyping 注释 'ported from react-use'，人工标注出处；git log 仅 1 个 commit 'Publish'（--depth 1 浅克隆所致），package.json 版本 0.0.1-alpha.0
- **年代背景**：2020 年初 React Hooks（16.8）刚普及一年，react-use/ahooks 等 hooks 库正兴起，作者用 Lerna+father+dumi 的当年主流国内工程栈自建 hooks 库属于紧跟潮流的合格-中上水平实践，但缺测试与若干闭包/语义 bug 拉低了质量。

### 2020-03-17 · react-redux-sourcecode-study　(功能7/代码7/技术7)
- **定位**：把 react-redux v7.2 源码完整拷贝进 CRA 工程，逐行加中文注释并配一篇近 900 行的源码分析 README，是一份个人源码阅读学习笔记。　|　技术栈：JavaScript, React 16.13 (Hooks), react-redux v7.2 源码, redux 4, create-react-app / react-scripts 3.4, @testing-library
- **亮点**：啃下 react-redux 最硬核的 connectAdvanced（556行）并逐段注释清楚 ref/useReducer 强更新/嵌套订阅链路；README 配流程图，自上而下讲清 Subscription 双向链表订阅-通知模型，准确点出 unstable_batchedUpdates 作用；自建多层嵌套 connect 测试用例（App.js Test1-7）并注入 console.log 实跑验证订阅传播；注释能链接官方文档（factory functions）解释 wrapMapToProps 的 proxy 自覆盖与参数个数启发式；诚实标注'代码里没用到过'的 get()、留下未想通的设计问题，体现严谨学习态度
- **短板**：底层库代码非原创，原创价值集中在注释与 README 分析；注释覆盖不均，hooks/connect 多个文件零注释，仅核心几个文件被精读；无自己编写的单元测试（仅 CRA 默认 App.test.js）；README 个别错别字（'我们我们'、'回通知'）
- **证据**：src/react-redux/utils/Subscription.js:116-123 在 handleChangeWrapper 注入 console.log 打印 current/parent 组件名（用 ?. 与 ??）实跑追踪订阅链；src/react-redux/components/connectAdvanced.js:383 留 'todo 为什么订阅父级connect的subscription' 的真实疑问；src/react-redux/connect/wrapMapToProps.js:69-74 注释引用官方 factory-functions 文档解释 proxy.mapToProps 自覆盖；src/App.js:11-28 构造 Test4>(Test5,Test6) / Test1>Test2>Test3 多层嵌套以观察订阅层级；README.md 结尾就'为何分层订阅而非直接订阅 store'发出未解疑问；package.json: react ^16.13 + react-redux 源码本地化，react-scripts 3.4
- **年代背景**：2020-03 正值 react-redux v7 用 Hooks 重写后不久，理解其 useReducer 强制更新 + 嵌套 Subscription 的新机制是当年的进阶难点，作者啃下来并讲清楚在当时属扎实的中高水平学习产出。

### 2020-03-29 · react-tiny-virtual-grid　(功能6/代码6/技术6)
- **定位**：一个 React 虚拟滚动组件，在虚拟列表基础上实现类 Grid 布局，并支持列数动态变化时的位置动画。　|　技术栈：TypeScript, React 16.8 Hooks, less, father, rollup
- **亮点**：在虚拟列表之上扩展出 Grid 布局这一非平凡思路；render-props 返回 [x,y] 坐标+stop 标志的 API 设计有品味；translate3d+willChange 做 GPU 加速偏移，性能意识到位；列数变化时通过补偿 scrollTop 实现布局动画，想法巧妙；已发布到 npm 且 tsconfig 开启 strict 全家桶
- **短板**：index.tsx 第63行 end 用了 prev.start(常为0) 而非 initialStart，与滚动处理逻辑不一致，疑似 bug；无测试、无 CI；仅支持固定 itemHeight，列宽需消费方硬编码；README 自陈核心功能(行数增加动画/动态高度)未实现；无 throttle/防闪屏，TODO 明确标注存在闪屏问题
- **证据**：src/index.tsx:113-117 dataSource.slice(start,end).map 计算 x=index%columns, y=floor(index/columns) 实现网格定位；src/index.tsx:56-58 changeOffset=initialIndex*(prevColumns-columns) 补偿 scrollTop 以支持列数变化；src/index.tsx:63 end: prev.start+visibleCount+bufferSizeLine 使用 prev.start 与 76-77 行 curStart 算法不一致；src/index.tsx:108-110 transform translate3d + willChange:transform GPU 加速；package.json:22-24 peerDependencies react ^16.8.6, 走 father build 发布 esm；tsconfig.json:5-9 strict/noUnusedLocals/noUnusedParameters 全开
- **年代背景**：2020 年初 React Hooks 刚普及约一年，作者用 Hooks+泛型+render-props 写出可发布的虚拟网格库，并在虚拟列表之上做布局动画创新，按当年标准属于中上水平的扎实小库。

### 2020-04-09 · easy-tweening　(功能7/代码7/技术6)
- **定位**：一个仅约1KB(gzip)的补间动画(tweening)库，通过单个共享 requestAnimationFrame 循环对数值/数值数组做缓动插值，并以回调和 Promise 暴露动画进度与完成。　|　技术栈：TypeScript, requestAnimationFrame, npm package, tsc (declaration emit)
- **亮点**：全局单一 rAF 循环 + Set 管理所有 tween，避免每个动画各开一个 rAF，设计高效；用泛型条件类型 onChangeCallBack<T> 让单值/数组回调自动推断正确类型，TS 用法地道；完整实现 Penner 系列 quad/cubic/quart/quint 缓动公式（含 --t 技巧），并支持 yoyo、Promise 完成、按 key 停止；tsconfig 开 strict 全家桶并 emit 声明文件，已发布到 npm v1.2.0，工程基本规范
- **短板**：无任何测试与 CI；存在类型不健全处：key 用 any、TweenObject<Value> 塞入 Set<TweenObject<ValueType>>；yoyo:true 且未传 key 时无法 stop，只能 clear() 全清，且会无限循环；getCurrentValue 每帧重复做 Array/typeof 判断，缓动种类仅到 quint，缺 back/elastic/bounce；无构建产物以外的浏览器兼容/降级处理
- **证据**：src/index.ts:101-126 单个 tick 通过 rAF.add 中 'if (this.all.add(obj).size < 2) requestAnimationFrame(tick)' 实现共享循环，size 归零自然停止；src/index.ts:55-72 easings 表内联实现各阶缓动，如 easeOutCubic: (t)=>--t*t*t+1；src/index.ts:3-14 onChangeCallBack<T> 条件类型 + Options<Value extends ValueType> 泛型推断回调签名；src/index.ts:74-86 getCurrentValue 对数组做等长校验并抛错，类型不一致也抛错；src/index.ts:110-114 yoyo 通过交换 from/to 并 removeTrack 实现往返；package.json:18 build 脚本 'tsc -d'，version 1.2.0 已发布；tsconfig.json strict:true
- **年代背景**：2020 年 TS 3.8 + rAF 的前端环境下，这种 1KB 级补间库属常见个人轮子，但其共享 rAF 调度与泛型条件类型推断高于同期初学者水平，按当年标准属合格偏上。

### 2020-05-13 · react-tim-chat　(功能7/代码7/技术7)
- **定位**：基于腾讯IM (tim-js-sdk v2.6.x) 的 React 聊天 UI 实现，支持单聊/群聊、多种消息类型渲染与发送、撤回、分页加载等　|　技术栈：TypeScript 3.8, React 16.13 (Hooks), rematch + immer, antd 4, less, webpack 4, dayjs, lodash, tim-js-sdk, cos-js-sdk-v5, Web Audio API
- **亮点**：地道的高级 TS：以 SDK 消息类型为 key 的映射类型构建消息渲染分发表 (generatorMessageContent.tsx + interface.ts)，类型安全且可扩展；扎实的聊天 UI 难点：分页前插时保留滚动位置、新消息浮层提示、自己发送自动置底 (MessageList Content.tsx)；乐观更新 + 失败回滚的会话删除/发送逻辑 (store/models/tim.ts deleteConversation/sendMessage)；用 Web Audio API + analyser/gain 节点链播放语音并驱动动画 (utils/soundContext.ts)；为纯 JS 的 tim-js-sdk 手写完整 .d.ts 类型声明 (TIMSDK.d.ts)，并用柯里化/HOC 工厂复用上传输入组件 (messageCreator.ts, InputOptions/index.tsx)
- **短板**：完全无测试、无 CI；setNewMessage 的排序逻辑 (tim.ts L79-82 splice+sort 后又拼回) 晦涩且疑似有 bug；通过 document.querySelector(#id) 拿文件 input 传给 SDK，组件与 DOM 耦合较脆弱 (messageCreator.ts createUploadMessage)；README 自承未完成、未发布 npm 包，作为库的完整度受限；事件监听仅 console.log/warn 处理错误，无真正的用户级错误反馈
- **证据**：src/Components/Message/MessageType/generatorMessageContent.tsx:21-35 用 [TIMMessageType.MSG_TEXT] 等 SDK 常量作为映射类型键构建渲染表；src/Layout/.. ConversationMessage/Content/index.tsx:105-110 滚动到顶触发分页并通过 scrollHeight-prevScrollHeight 恢复滚动位置；src/store/models/tim.ts:161-183 deleteConversation 做乐观删除并在 catch 中 rollback；src/utils/soundContext.ts:6-30 createAnalyser/createGain/createBufferSource 构建 Web Audio 节点链；src/TIMSDK.d.ts:1-92 手写 TIMMessageType/TIMEventType/TIMInstance 类型声明；src/Components/ConversationMessage/messageCreator.ts:26-40 createUploadMessage 用 lodash/curry + document.querySelector 复用上传逻辑；tsconfig.json:12 strict:true 全量严格模式
- **年代背景**：2020 年 React Hooks 刚成熟、antd4/rematch/immer 正当时，此项目对当年新范式（函数组件+Hooks+不可变状态+严格 TS）的运用相当地道，按当年工程标准属于中上水准的个人作品。

### 2020-05-22 · piatto　(功能6/代码8/技术7)
- **定位**：面向移动端的 React + TypeScript 组件库（Button/Input/Slider/Form/Space/ConfigProvider），仿 ant-design 架构，已发布 alpha 版到 npm。　|　技术栈：React 16/17, TypeScript, react-hook-form, Less, Storybook, Jest, Testing Library, GitHub Actions
- **亮点**：地道的 antd 式架构：forwardRef+泛型、复合组件(Form.Item/Input.GetCode)、ConfigContext 前缀体系；手写触摸版 Slider（class 组件，touchstart/move/end 全生命周期管理与解绑）；完整 CI 矩阵：React 16/17 × source/lib/es 交叉测试 + codecov + storybook 部署；vw 响应式主题系统 + 移植 ant-design 色板生成算法（诚实注明出处）；真实测试套件：fake timers 测倒计时、快照、hooks/utils 单测
- **短板**：form-item 直接把 error 对象当 React child 渲染（{error ?? ''}）存在隐患；useImmutableValue 静默忽略后续传入的新值，命名与行为易误用；无 README，仅 alpha 未正式发布，组件数量少（6 个）；Slider 在 componentDidMount 用 forceUpdate 兜底首屏布局，略显 hack
- **证据**：components/form/form.tsx: 泛型 forwardRef + useImperativeHandle 暴露 form 实例，children 中聚合 rules 到 resolver；components/input/get-code.tsx: 自管理倒计时 timer，useEffect 清理 clearTimeout，Promise 化 onGetCode；components/input/index.tsx:onRest 通过 Object.create(e) 重建合成事件触发清空 onChange；components/slider/index.tsx: PureComponent 手写 touch 事件 + getDerivedStateFromProps 受控逻辑 + clamp 步进；components/styles/theme.less + utils/colorPalette.less: vw 设计稿换算变量 + 注明 'copy from ant-design' 的色板算法；.github/workflows/test.yml: react-16/17 × dom/lib/es 共 8 个 job 的交叉测试矩阵；tests/input/get-code.test.tsx: jest.useFakeTimers 驱动 60s→30s→0s 倒计时断言
- **年代背景**：2021 年定稿（仓库 2020-05-22 创建）：react-hook-form 7 与 Storybook 6 是当时较新栈，作者对 hooks/受控组件/构建链的掌握达到当年资深前端水准，按当年标准评分偏高。

### 2020-06-16 · micro-frontend-demo　(功能7/代码6/技术6)
- **定位**：qiankun 微前端示例，演示 umi 主/子应用、纯 HTML 手动主应用、CRA 子应用四种接入方式及跨应用通信　|　技术栈：TypeScript, React 16, qiankun 2.x, umi 3, @umijs/plugin-qiankun, create-react-app, react-app-rewired, webpack 4
- **亮点**：完整覆盖 qiankun 四种接入场景：umi 插件主应用、纯 HTML 手动主应用、umi 子应用、CRA 子应用；实现两套跨应用通信：umi rootExports/useRootExports 与 qiankun initGlobalState/onGlobalStateChange；CRA 子应用手动接入到位：public-path 注入、config-overrides 配置 UMD/jsonpFunction/CORS、lifecycle 钩子齐全；子应用 basename 根据 __POWERED_BY_QIANKUN__ 区分独立/嵌入运行，考虑了独立部署
- **短板**：大量 @ts-nocheck/@ts-ignore 与 any，类型实践不严谨；页面组件仅为占位演示，业务逻辑 trivial；无实质测试（仅 CRA 默认 learn react 测试），无 CI；rootExports 用模块级可变全局 data/eventList 实现，较简陋
- **证据**：master/.umirc.ts: qiankun.master.apps 注册 app1/app2，含 jsSandbox/prefetch 配置及详尽中文注释；qiankun-base/src/index.js: 手动 registerMicroApps + initGlobalState + start，演示无框架主应用接入；app2-cra/src/index.tsx: 手动实现 bootstrap/mount/unmount/update 生命周期，mount 中接 onGlobalStateChange/setGlobalState；app2-cra/config-overrides.js: output.library/libraryTarget=umd/jsonpFunction 及 devServer CORS 头，CRA 接入关键改造；app1/src/pages/index.tsx: useRootExports() 取 bindOnChange/setData，useEffect 订阅并 input 触发主应用数据变更；master/src/rootExports.ts: getData/setData/bindOnChange 简单事件订阅实现；app2-cra/src/public-path.ts: 依据 __POWERED_BY_QIANKUN__ 注入 __webpack_public_path__
- **年代背景**：2020 年 6 月 qiankun 2.x 与 @umijs/plugin-qiankun 刚发布不久，能同时打通 umi 插件式与纯手动两种主应用、并解决 CRA 子应用 UMD 改造与跨应用通信，属当年微前端落地的扎实示范，按当年标准评分。

### 2020-06-30 · rc-pannellum　(功能6/代码7/技术4)
- **定位**：一个把 pannellum 全景图查看器封装成 React 组件的轻量 TypeScript 库，提供类型推断与 ref 暴露 viewer 实例。　|　技术栈：TypeScript, React 16 (Hooks/forwardRef), pannellum, father, rollup, prettier
- **亮点**：地道使用 React Hooks + forwardRef + useImperativeHandle 暴露命令式实例；卸载时 destroy 并 try/catch 解绑事件，处理了生命周期边界；为 pannellum 手写了较完整的 config/viewer/hotSpot 类型声明；已发布到 npm 且有清晰 README 与 props 文档
- **短板**：PannellumViewer 全部用 Function 类型，丢失参数/返回值类型，类型质量打折；useEffect 依赖 [restProps] 对象会每次 render 重建 viewer，存在重复销毁重建隐患；封装极薄、功能单一(只额外加了 clickInfo)，技术深度有限；无测试、无 CI、无示例工程
- **证据**：src/index.tsx:35 window.pannellum.viewer(containerRef.current!, {...params}) 直接代理原库；src/index.tsx:47 useEffect 依赖数组为 [restProps]，对象引用每次变化会触发重建；src/index.tsx:42-44 卸载时 try{off}catch{} 再 destroy，体现边界处理意识；src/interface.ts:86-130 PannellumViewer 三十余个方法全部声明为 Function，类型偷懒；src/index.tsx:49-51 useImperativeHandle 暴露 getViewer，命令式 API 设计得当；package.json:21-26 peerDeps react^16.8.6 + deps pannellum^2.5.6，定位为 wrapper 库
- **年代背景**：2020 年 React Hooks 已成熟、father+rollup 是当时主流的库打包方案，作者用当年标准工具做了一个规范的薄封装库，类型手写在那个生态下属合格偏上的工程实践。

### 2020-07-09 · zhangyu1818　(功能5/代码5/技术1)
- **定位**：GitHub 个人主页 profile README，展示前端开发者 ZHANGYU 的自我介绍（中英双语）　|　技术栈：Markdown
- **亮点**：符合 GitHub profile README 约定（username/username 特殊仓库）；提供中英双语两份介绍；文案口语化、有个人风格（滑板/滑雪/STM32）
- **短板**：无任何源代码，纯文本介绍；未使用徽章/统计卡片/动态内容等常见 profile 增强；中英文内容不完全对应（英文写学 Three.js，中文写学 C/STM32）
- **证据**：仓库仅含 README.md(7行) 与 README.zh-cn.md(7行)，无 package.json/构建/CI；README.md:1 '# <Hello>你好👋, I'm ZHANGYU</Hello>' 为个人介绍而非代码；git log 仅 1 个提交 '134d2e6 Update README.md'；仓库名 zhangyu1818 与用户名一致，属 GitHub profile README 特殊仓库
- **年代背景**：GitHub profile README 功能于 2020 年 7 月正式推出，该仓库创建于 2020-07-09 恰好是功能上线初期，属于纯展示用途的个人主页，不应以代码项目标准衡量。

### 2020-07-22 · wx-font-reset　(功能6/代码5/技术3)
- **定位**：一个微小的 npm 库，通过 WeixinJSBridge 把微信内置字体大小还原为默认值，避免 rem 布局因用户调大字体而错乱　|　技术栈：JavaScript, ES Module, TypeScript declaration, WeixinJSBridge
- **亮点**：针对真实且常见的微信 webview rem 布局痛点；正确处理 WeixinJSBridge 就绪时序(对象存在则直接调用，否则监听 WeixinJSBridgeReady)；监听 menu:setfont 以便用户改设置后重新还原；打包规范：ESM 默认导出 + index.d.ts + package.json 配置 typings
- **短板**：index.js:2 用 element.style['-webkit-text-size-adjust']='100% !important' 设置内联样式，!important 在 CSSOM 赋值中无效会被静默忽略，应改用 setProperty；无测试、无 CI、无构建；README 仅 3 行用法，未说明安装与原理；逻辑极简，本质是封装公认社区片段，技术含量低
- **证据**：index.js 全文 17 行，导出单个 resetFont 函数；index.js:4-10 通过 typeof WeixinJSBridge=='object' 判断并 fallback 到 WeixinJSBridgeReady 事件；index.js:12 WeixinJSBridge.invoke('setFontSizeCallback',{fontSize:0}) 为微信还原字体标准调用；index.js:2 '-webkit-text-size-adjust'='100% !important' 存在 !important 内联赋值无效的 bug；index.d.ts:1 export default function resetFont(): void; 提供类型声明；package.json 配置 main/typings/license(MIT)，version 1.0.0；git log 仅一条 commit 918f3d3 'update' (2020-07-22)
- **年代背景**：2020 年微信 H5 仍是主流场景，rem 布局被微信字体设置打乱是普遍痛点；该方案是当年社区公认的标准解法，把它打包成带类型声明的小 npm 库属于合理但门槛很低的工程实践。

### 2020-08-05 · countdown-button　(功能8/代码8/技术7)
- **定位**：封装 Ant Design Button 的倒计时按钮组件库，常用于短信验证码等场景，同时导出 useCountdown hook 供自定义。　|　技术栈：TypeScript, React 16, Ant Design 4, dumi, father-build, enzyme, umi-test
- **亮点**：设置 __ANT_BUTTON 静态标志，体现对 antd 内部机制的源码级理解；API 设计完善：forwardRef、render-props、独立导出 useCountdown hook，组合性强；类型定义地道：Omit<ButtonProps,'onClick'>、CompoundedComponent 模仿 antd 内部范式；已发布为 npm 包，配套 dumi 文档/father-build/lint-staged+yorkie 钩子，工程链完整；有覆盖挂载卸载/点击/Promise resolve/reject 的 enzyme 测试与卸载时 timer 清理
- **短板**：useCountdown 的 useCallback 依赖数组为空，time 变化时存在闭包陈旧问题；sleep 通过外部可变变量同步取回 timerId，写法略 tricky；ref as any 的类型逃逸；无 CI 配置（如 GitHub Actions）
- **证据**：src/index.tsx:109 CountdownButton.__ANT_BUTTON = true —— 利用 antd 内部按钮识别标志；src/index.tsx:8 export interface CountdownButtonProps extends Omit<ButtonProps, 'onClick'> —— 正确扩展 antd 类型；src/index.tsx:34-38 useEffect 返回函数中 window.clearTimeout(timer.current) 处理卸载清理；src/index.tsx:40-55 useCountdown 中 useCallback(..., []) 依赖空数组，闭包捕获初始 time；src/index.tsx:71-80 Promise.resolve(onClick(e)).then().catch().finally() 同时支持同步/异步点击并处理拒绝；src/index.test.tsx:55-65 覆盖 Promise reject 时不开始倒计时并 console.warn 的用例；package.json:47-49 peerDependencies antd ^4.5.2，dependencies 仅 react，库依赖边界清晰
- **年代背景**：2020 年 React Hooks 已成熟、antd4 与 dumi/father 工具链刚普及，作者用当年主流方案做出 API 设计完善且带源码级洞察(__ANT_BUTTON)的发布级组件库，按当年标准属于熟练偏资深前端水平。

### 2020-09-02 · drag-resize　(功能6/代码6/技术6)
- **定位**：一个发布到 npm 的 React 组件 rc-drag-resize，通过八向把手让子元素可拖拽改变大小，支持 min/max 尺寸约束　|　技术栈：TypeScript, React 16, lodash, dumi, father-build, less
- **亮点**：用 const 断言 directions 数组 + 类型派生 Directions，类型设计地道；通过 DirectionMap [property, sign] 元组把八方向统一为 x/y 两轴处理，避免八套分支；用 clamp 配合方向符号统一处理 min/max 边界约束；采用 2020 主流的 dumi+father-build 库工程化，文档/构建/发布配置齐全
- **短板**：onMouseDown 监听挂在 document.body 全局，多个实例会相互串扰且记录 startPos 不区分来源；拖动过程不实时回算 wrapper 尺寸，只在 mouseup 结算（README/docs 自承此限制）；alpha 版本、5 star、无单元测试（package 配了 umi-test 但 src 下无测试文件）；directions/maxWidth 等变更后 effect 重绑事件，但 onMouseDown 等闭包未随依赖更新，存在潜在闭包陈旧风险；getDirection 内联对象每次调用重建，directionMap 类型用 as 强转较多
- **证据**：src/index.tsx:30 directions = ['n','e','s','w','ne','se','sw','nw'] as const 派生类型；src/index.tsx:32-33 clampMove 用 direction==-1 分支配合 clamp 做边界；src/index.tsx:35-50 getDirection 把单/双向拼成 {x,y} 元组映射；src/index.tsx:151-153 事件绑定到 document.body 而非组件根节点（全局污染）；src/index.tsx:133-143 onMouseUp 才用 getBoundingClientRect 回写 wrapper 宽高；package.json:14 test 脚本存在但仓库内无任何 __test__/test 文件
- **年代背景**：2020 年 React Hooks 已成熟、dumi/father-build 是 antd 生态做组件库的标准范式，作者熟练套用且类型设计较地道，属当年合格偏上的前端工程师水平；八向 resize 是常见但非trivial的交互组件。

### 2020-09-27 · hook-form-async-validator　(功能6/代码7/技术5)
- **定位**：一个把 async-validator 校验引擎接入 react-hook-form 的 resolver 适配器库（约48行单文件）。　|　技术栈：TypeScript, react-hook-form, async-validator, tsc
- **亮点**：职责单一清晰：一个工厂函数完成 async-validator -> RHF resolver 的桥接；类型处理地道：泛型 <T extends Values>、re-export 上游类型、Resolver<T> 返回签名严格；考虑到动态校验场景，提供 useRef 选项从 ref.current 取 schema；tsconfig 开启 strict 全家桶（strictNullChecks/noUnusedLocals 等），工程规范
- **短板**：规模极小、零测试、零 CI，仅一次有效 commit；convertErrors 中 reduce 用 { [field]: message, ...a } 展开导致同名字段后者被先者覆盖且每次新建对象，效率与语义略糙；schema.current 在非 useRef 分支用 as Rules 强转，类型安全有缝隙；README 极简、有英文拼写错误，无 API 文档/示例覆盖 useRef 与 config；Stars 0，实用性受限于知名度
- **证据**：index.ts:30-46 resolver 工厂返回 (values)=>validator.validate(...).then/catch，正确映射 RHF 的 {values,errors} 协议；index.ts:20-24 convertErrors 用 reduce 将 ErrorList 折叠为 field->message 映射；index.ts:26-28 ResolverConfig extends ValidateOption 并加 useRef?:boolean；index.ts:34 (useRef ? schema.current : schema) as Rules；package.json:23 peerDependencies react-hook-form ^7.7.0，对应 2021 commit 升级到 v7 resolver API；tsconfig.json:11-19 启用 strict / noUnusedLocals / noImplicitReturns 等严格选项；git log 仅一条 'fix types'（2021-05-30），AuthorDate 晚于仓库创建日
- **年代背景**：2020 年 react-hook-form 正从 v6 向 v7 演进、resolver 模式刚成为生态主流，作者及时写出一个类型完备的第三方校验器适配层，符合当年合格偏上的前端库工程水准。

### 2020-10-14 · observer　(功能6/代码7/技术7)
- **定位**：学习性质地重写 observer-util（nx-js / react-easy-state 的响应式内核），用 Proxy 实现一个依赖收集与自动重运行的响应式状态系统。　|　技术栈：TypeScript, Proxy/Reflect, WeakMap, Map/Set/WeakMap/WeakSet, tsc
- **亮点**：完整复刻 Proxy 响应式内核：依赖收集、reaction 栈、cleaners 先清理后重跑；覆盖难点 Map/Set/WeakMap/WeakSet：this 重绑定 + 迭代器 patch + ITERATION_KEY；rawToProxy/proxyToRaw 双向 WeakMap 保证身份一致、避免重复代理；set 中 receiver/原型链守卫与数组 length-key 处理，细节到位；中文注释清晰解释每步意图，看得出真的吃透了原理
- **短板**：设计为对 observer-util 的直接移植，非原创架构（README 自承边学边写）；collections delete 拦截未真正调用 target.delete(key)，存在功能性 bug；完全无测试、无打包产物、无 CI；noImplicitAny:false 放宽类型，多处 any/未标注参数
- **证据**：README.md:1 '照着 observer-util 边学边写的' + 两篇掘金总结文章链接；src/store.ts:24-44 registerReactionForOperation 构建 WeakMap<raw,Map<key,Set<reaction>>> 并维护 reaction.cleaners；src/reaction.ts:14-34 runAsReaction 先 releaseReaction 清理再 push 入栈，try/finally pop，标准 observer-util 模式；src/handlers/collections.ts:8-22 patchIterator 重写 iterator.next 惰性包裹产出值；97-102 [Symbol.iterator] 处理；src/handlers/collections.ts:58-64 delete 拦截只 queue 了 reaction 却未执行 target.delete(key)，且无返回值（功能 bug）；src/handlers/base-handler.ts:41 'if (target !== proxyToRaw.get(receiver)) return result' 原型链/receiver 守卫；src/utils.ts:8-19 findObservable 仅在 hasRunningReaction 时惰性深度代理；package.json:7-13 仅 prettier+typescript devDeps，无 test 脚本；git log 仅 1 个 commit
- **年代背景**：2020 年 Proxy 已被主流浏览器支持、Vue3/observer-util 等基于 Proxy 的响应式方案正流行，作者借此系统性吃透 Proxy 响应式原理（含 Map/Set 这类公认难点），在当年属于扎实的进阶自学练习。

### 2020-12-27 · swiftui-todolist　(功能6/代码6/技术5)
- **定位**：一个用 SwiftUI 2.0 + MVVM 实现的 iOS 待办事项练手 App，从占位 API 拉取假数据并支持增删改/标记完成。　|　技术栈：Swift 5, SwiftUI 2.0, Combine, Alamofire, CocoaPods, iOS 14
- **亮点**：及时采用 2020 年刚发布的 SwiftUI 2.0 @main/App 生命周期与 @StateObject；清晰的 Model/View/ViewModel/Service 分层与文件夹组织；不可变结构体 + 函数式 clone 模式，@EnvironmentObject 注入得当；@ViewBuilder 抽取列表渲染、LazyVStack、#if canImport(UIKit) 收起键盘等地道写法
- **短板**：无任何错误处理：fetch 失败仅 print，且 fetching 标志永远卡在 true(FetchTodolist.swift:14 / TodoViewModel.swift:26)；createTemplateTodo 用 UUID().hashValue 生成 Int id，易碰撞且语义错误(Todo.swift:23)；sortedTodolist 比较器非严格弱序(TodoViewModel.swift:19)；无 README、无测试、无 CI；为单 GET 引入 Alamofire 略显过度；数据无持久化，重启即丢失
- **证据**：TodolistApp.swift:10-12 使用 @main + App 协议 + @StateObject，符合 iOS14 新生命周期；Todo.swift:18-24 不可变 struct，clone 与 createTemplateTodo 工厂方法；id 用 UUID().hashValue；TodoViewModel.swift:11-44 ObservableObject + @Published，completed/notCompleted 计算属性过滤；FetchTodolist.swift:12-18 Alamofire responseDecodable，错误分支仅 print("fetch error")，未回调导致 fetching 卡死；ListView.swift:19-36 @ViewBuilder renderList + ProgressView/空态/LazyVStack 三态渲染；ListView.swift:97-103 #if canImport(UIKit) 扩展 hideKeyboard 收起键盘；TodoListItem.swift:21-25 init 中以 State(initialValue:) 初始化本地标题，经回调同步回 ViewModel
- **年代背景**：创建于 2020-12，正值 SwiftUI 2.0/iOS14 新生命周期刚发布，作者能立即上手 @main/@StateObject 并搭出规整 MVVM，按当年标准属于合格偏上的练手项目。

### 2021-01-08 · clocks-widget　(功能8/代码6/技术7)
- **定位**：一款已上架 App Store 的 iOS SwiftUI 时钟桌面小组件 App，支持自定义颜色、图片背景，并通过精确裁剪壁纸实现"透明融入桌面"效果。　|　技术栈：Swift, SwiftUI, WidgetKit, SiriKit Intents (IntentConfiguration), App Groups / UserDefaults, CoreGraphics, UIKit
- **亮点**：紧跟 iOS14 WidgetKit 首发期，实现当时热门的"透明壁纸小组件"玩法且已成功上架；用 uname() 做硬件机型识别并维护逐机型像素级小组件坐标/尺寸表，结合 CoreGraphics 裁剪还原桌面位置；地道的工程化设计：App Group 共享存储、IntentConfiguration 选择自定义组件、protocol-oriented 时钟类型、自定义 EnvironmentKey 传递 widgetFamily；清晰的 MVVM：ViewModel/Storable/Widget 三层 config 转换 + ConfigManager 单例缓存
- **短板**：DeviceWidget.swift 逐机型坐标 switch 大量重复，260+ 行可表驱动化；生产代码残留 print 调试与多处 force-unwrap (image!、modelCode!)；图片 toggle 与 mask 路径互转逻辑作者自承"逻辑绕了"，状态管理偏绕；saveImage 用 jpegData(quality:1) 存遮罩图，PNG 透明场景更合适；无单元测试
- **证据**：Clocks/Extensions/UIDevice.swift:42-98 通过 utsname/uname 解析 machine 标识并带 simulator 回退映射机型；Clocks/Utils/DeviceWidget.swift:11-272 逐机型(iPhone6S~12ProMax)硬编码小组件位置与尺寸坐标表；Clocks/Views/WidgetDetail/ClockDetailImageCropView.swift:122-149 TapRectangle 用 cropImage 按机型 rect 裁剪壁纸生成透明遮罩；Clocks/Utils/UserDefaults.swift:10-28 App Group(suiteName group.zhangyu1818.clocks) 共享 + 泛型 getWidgetConfig 解析；ClocksWidget/ClocksWidget.swift:46-55 IntentTimelineProvider 生成 900 条秒级 entry，policy .after(updatesDate)，但仍残留 print；Clocks/Views/WidgetDetail/ClockDetailImageEditView.swift:80,203 作者注释 '// Todo 删除bug' 与 '逻辑绕了'；Clocks/Protocol/ClockWidget.swift:11-18 protocol 抽象时钟类型 + nonConfigurableFields 驱动详情页字段过滤
- **年代背景**：创建于 2021-01，正值 iOS14 WidgetKit 发布仅 4 个月、社区资料稀缺的早期，作者能独立摸索出 IntentConfiguration 自定义组件、App Group 共享、逐机型坐标裁剪透明效果并上架 App Store，在当年属于明显高于平均的工程实践。

### 2021-01-13 · github-actions-demo　(功能2/代码2/技术2)
- **定位**：一个用来试玩 GitHub Actions 的练习仓库，仅包含两个近乎模板的 workflow（issue 打开时回显、release 时发布 npm 包）和一个空的 package.json，没有实际源码。　|　技术栈：GitHub Actions, YAML, Node.js, npm
- **亮点**：release.yml 正确配置了 GITHUB_TOKEN 与 packages:write 权限发布到 GitHub Packages；尝试用 if: github.actor 做触发条件过滤
- **短板**：无任何源码，package.json 为 npm init 空壳（index.js 不存在）；误把图片文件 1 与 avatar.jpg 重复提交（字节完全一致）；blank.yml 中 echo "$github.actor" 语法错误（应为 ${{ github.actor }}）；if 判断的用户名 zhangyu18181 与 actor zhangyu18181 不一致，逻辑形同摆设；仅一次提交，完全是模板试水
- **证据**：package.json:5 "main": "index.js" 但仓库无 index.js；test 脚本为默认 echo 报错退出；.github/workflows/blank.yml:23 run: echo "$github.actor" 为无效的变量插值写法；.github/workflows/blank.yml:22 if: github.actor == 'zhangyu18181' 用户名疑似拼写错误；根目录文件 1 与 avatar.jpg 经 md5 校验完全相同(b2b2fd5ffdd4eaf4fca06b0e25217593)，均为 460x460 JPEG，属误提交；git log 仅一条提交 1809906 Create release.yml；.github/workflows/release.yml:14-21 使用 actions/checkout@v2 + setup-node@v1 发布 npm（标准模板）
- **年代背景**：2021 年初 GitHub Actions 已普及，本仓库正是直接套用 GitHub 官方默认 workflow 模板做学习试水，按当年标准衡量它也只是最入门的 demo，几乎没有作者自己的工程产出。

### 2021-01-14 · blog　(功能9/代码8/技术8)
- **定位**：个人博客（zhangyu.dev），用 Next.js 14 App Router + RSC 构建，以 GitHub Discussions 作为 CMS，MDX 渲染文章。　|　技术栈：TypeScript, Next.js 14 (App Router/RSC, output:export), React 18, TailwindCSS, MDX (rsc-mdx), Shiki + Twoslash, GitHub GraphQL (Octokit/@discublog/api), react-aria-components, p2-es 物理引擎, OpenAI API
- **亮点**：MDX/RSC 渲染管线深度定制：自研 rehype 插件、Shiki+Twoslash 自定义 renderer 与 hast 组合；用 p2-es 物理引擎做 Galton 板动画展示技能图标，新颖且实现完整；以 GitHub Discussions 为 CMS、webhook 触发 Vercel 部署，工程闭环干净；作者自研并发布多个底层依赖（rsc-mdx、eslint-config、tw-styled 等），生态参与深；类型、路径别名、SEO（sitemap/robots/metadata）、静态导出等工程细节到位
- **短板**：完全无测试（无任何 .test/.spec）；OpenAI 摘要的限流用 queue.size*60000 的粗糙串行延迟，作者也自承不确定；多处 eslint-disable（exhaustive-deps、no-array-index-key 等）绕过规则；Galton 组件单文件近 270 行，DOM 直接操作与 React 状态混用，可读性偏重
- **证据**：src/markdown/markdown.tsx:35-92 顶层 await createHighlighter + MDX 多 transformer 管线（Diff/Highlight/Twoslash 等）；src/markdown/plugins.ts:26-53 自研 rehypeGithubAlert 把 blockquote 改写成 <Alert> 节点；src/markdown/twoslash/renderMdx.ts:30-140 自定义 rendererRich，注入 Tabler 图标与 TwoslashTooltip/Trigger hast；src/components/blocks/skills/galton.tsx:71-213 p2.World 物理仿真 + requestAnimationFrame 驱动技能图标下落；src/service/index.ts:19-78 Promise.allSettled 兼容 master/main README，unstable_cache 缓存 GraphQL 查询；src/service/summary.ts:30-41 朴素串行队列限流 OpenAI gpt-3.5 摘要生成；package.json:43,64 依赖作者自研的 @zhangyu1818/eslint-config、tw-styled、dark-toggle 等；无 *.test/*.spec 文件；.github/workflows/discussion-opened.yml 仅 discussion 事件触发 Vercel 部署
- **年代背景**：仓库创建于 2021-01-14，但被评估的默认分支 next14 是 2024 年的彻底重写（末次提交 2024-09-14），采用 Next.js 14 App Router/RSC + Shiki Twoslash 等 2024 前沿范式；按 2024 工程标准衡量属资深前端水准，而非 2021 标准。

### 2021-03-07 · react-observed-context　(功能6/代码6/技术7)
- **定位**：一个利用 React 16/17 未公开的 Context bitmask（calculateChangedBits / observedBits）特性实现「按字段精准更新」的轻量 Context 库。　|　技术栈：TypeScript, React 16/17, React Context unstable bits API, tsc
- **亮点**：命中React 16/17隐藏的Context bitmask二级API，属源码级深度知识；用bitsArray预计算31位掩码+keyBitsMap做字段到位的映射，思路清晰；已发布到npm(v2.0.0)，附原理博客与API文档，可实际安装使用；API设计简洁(Provider + useObservedState)，泛型签名基本到位
- **短板**：在Provider的render函数体内对模块级keyBitsMap赋值，是渲染期副作用且为共享可变状态(多Provider会互相污染)；依赖被React 18移除的非稳定特性，库已随版本失效(README自承)；noImplicitAny:false放宽类型，calculate(key)参数隐式any，calculateChangedBits用newValue[0]隐式假设结构；无任何测试、无CI；用try/catch粗暴兜底为全掩码，错误处理不精细
- **证据**：src/index.tsx:53-57 React.createContext 传入第三参数 calculateChangedBits（16/17隐藏API）；src/index.tsx:71-78 useObservedState 调用 React.useContext(Context, observedBits) 第二参数为隐藏observedBits；src/index.tsx:7-10 MAX_SIGNED_31_BIT_INT 与 bitsArray 预计算2^index掩码；src/index.tsx:59-66 Provider render 体内对模块级 keyBitsMap 赋值（渲染期副作用/共享可变状态）；src/index.tsx:21 calculate=(key)=> 参数无类型 + tsconfig noImplicitAny:false；src/index.tsx:42 calculateChangedBits 用 newValue[0] 假设 state 为 [State,setState] 元组；README.md:3 自承「这个功能只在16和17可用，18不可用了」；package.json:3 version 2.0.0 已发布；scripts 仅 build=tsc，无 test
- **年代背景**：2021年正值React16.8+ Hooks时代、Context重渲染优化是热门痛点(use-context-selector同期流行)，作者敢挖React未文档化的bitmask二级API来做精准更新，在当年属于有深度的探索而非套模板，但该API本就非稳定，注定随React18被淘汰。

### 2021-03-11 · use-derived-value　(功能7/代码8/技术6)
- **定位**：一个用 React Hook 模拟类组件 getDerivedStateFromProps 行为的微型受控/派生状态库，已发布为 npm 包 use-derived-value。　|　技术栈：TypeScript, React 17 Hooks, Jest, @swc/jest, @testing-library/react-hooks, GitHub Actions, Codecov, Prettier
- **亮点**：用 useRef 存状态 + useReducer 强制重渲，精准实现派生状态且无多余 rerender；把 onChange 存进 ref 规避闭包陈旧值，setState 用 ref 保持引用稳定，细节地道；完整工程化：npm 发布、CI、Codecov、声明文件、6 个覆盖边界的测试；TS 泛型 + as const 元组返回，类型表达准确
- **短板**：功能范围极小(43 行)，本质是一个针对性 hook 而非通用库；postState 用 null 表示非受控会与合法的 null 状态值冲突，语义有边界缺陷；CI 用 pull_request_target 在 2021 已是已知的安全反模式；setState 用 useRef 包裹但每次渲染都重建 onChangeRef，依赖隐式而非显式
- **证据**：index.ts:15 const rerender = React.useReducer(v => v + 1, 0)[1] —— 经典强制重渲技巧；index.ts:19-20 onChangeRef 每渲染同步 current，避免陈旧闭包；index.ts:22-26 derivedState=postState()，非 null 且变化时覆盖 stateRef，复刻 getDerivedStateFromProps；index.ts:28-38 setState 用 useRef 持久化，支持函数式更新并触发 onChange；test.ts 共 6 个用例，含 'no extra rerender'(L117) 和 onChange 变更追踪(L64) 等边界断言；package.json:16-17 使用 @swc/jest 转译，2021 年算较前沿的工具选择；.github/workflows/test.yml:3 on: [push, pull_request_target] 存在安全隐患
- **年代背景**：2021 年初 React Hooks 已成熟但 getDerivedStateFromProps 的 hook 化仍是常见痛点，作者用 ref+useReducer 的地道方案并配齐 SWC/CI/Codecov 工程链，体现当年中上水准的库作者素养。

### 2021-05-06 · stupid-events　(功能6/代码7/技术6)
- **定位**：用单文件 TypeScript 模仿 React v17 的事件系统：在 window 上做事件委托，从触发元素向上收集 DOM 节点队列再依次派发，并提供自定义的 stopPropagation/stopImmediatePropagation。　|　技术栈：TypeScript, DOM Event API, WeakMap/Map/Set, tsc
- **亮点**：准确抓住 React 17 的核心变化（事件委托到容器而非 document）并自实现；数据结构选型得当：WeakMap+Map+Set 让脱离 DOM 的节点可被 GC、监听器天然去重；类型设计地道：用 keyof WindowEventMap 做事件名约束、泛型保证 listener 事件类型推导；API 简洁，bindEvent 返回卸载函数符合现代习惯
- **短板**：triggerList 为模块级共享 Set，同步/嵌套再派发时不可重入会被污染；遍历到 document.body 即停止，忽略 body 及以上、且未做捕获阶段；无测试、无构建产物校验、无示例运行环境；README 末尾笔误：注释写 removeAllListeners 却调用 removeListeners()
- **证据**：stupid-events.ts:8 eventsMap = new WeakMap<HTMLElement, Map<keyof WindowEventMap, Set<Function>>>() —— GC 友好的三层结构；stupid-events.ts:13-24 accumulateElement 用 while(node) 沿 parentElement 向上收集，遇 document.body 提前 return；stupid-events.ts:40-54 triggerEvent 在元素循环顶部判 isStopPropagation、监听器循环内判 isStopImmediatePropagation，语义贴近 React；stupid-events.ts:69-72 bindEvent 用 internalFlag 保证每种事件只在 window 注册一次委托监听；stupid-events.ts:11 triggerList = new Set<HTMLElement>() 为模块级单例，存在重入风险；package.json:13 "dist": "tsc" 仅靠 tsc 出包，无打包/测试脚本
- **年代背景**：2021 年 React 17 刚把事件委托从 document 迁到根容器是社区热点，作者借此自造轮子复刻其机制，体现了对当年源码级原理的跟进；以 2021 的工程标准看，TS 严格模式+WeakMap 的写法已属合格偏上。

### 2021-05-09 · dynamic-stylesheet　(功能7/代码7/技术4)
- **定位**：一个用 JavaScript 动态注入/更新 CSS 的极小型 TypeScript 工具库，已发布到 npm。　|　技术栈：TypeScript, Jest, Babel, GitHub Actions, Codecov, npm
- **亮点**：目标明确且完整：injectCSS/updateCSS 双 API，覆盖默认 head/attachTo/复用同 key 节点等边界；工程化完善：jest 测试 + GitHub Actions CI + Codecov 覆盖率 + bundlesize 徽章 + npmignore，是真正发布到 npm 的成品；地道的 TS 类型设计：用 NodeHasMarkKey<T> 交叉类型给 DOM 节点挂标记 key，类型安全且不污染 DOM 属性；tsconfig 开启 strict，生成 .d.ts，配置干净规范
- **短板**：规模极小（核心 49 行），技术深度有限，本质是封装 createElement('style')+appendChild；使用 innerHTML 注入样式存在潜在风险，未用 textContent/CSSOM，也未处理 SSR/无 document 场景；updateCSS 用线性遍历 children 查找节点，节点多时效率不佳；无删除/移除 API；测试用例的 testStyle 写成 display: "block" 带引号，并非有效 CSS（虽不影响测试断言）
- **证据**：src/index.ts:7 type NodeHasMarkKey<T extends Element = Element> = T & { [MARK_KEY]: string } —— 用交叉类型给节点挂标记；src/index.ts:18-26 injectCSS 通过 createElement('style')+innerHTML+appendChild 注入；src/index.ts:28-47 updateCSS 按 MARK_KEY 复用已有 style 节点并仅在内容变化时更新；src/index.ts:14-15 getContainer 回退逻辑 head || document.body；package.json:8-10 build/test/prepublishOnly 脚本，main+types 指向 dist，已发布 v1.0.0；src/test.ts:5-37 三个 jest 测试用例覆盖 inject/attachTo/update；.github/workflows/test.yml CI 跑 npm test --coverage 并上传 Codecov
- **年代背景**：2021 年 TS 4.2 + Jest 26 + Babel preset 的工程组合是当时小型 npm 库的标准做法，作者按当年水准把一个微型工具做成了配置完整、有测试有 CI 的发布级成品，这在当年属于扎实的合格偏上工程实践。

### 2021-05-09 · wave-effect　(功能7/代码7/技术6)
- **定位**：一个仿 Ant Design 的点击水波纹(ripple)效果的轻量 TypeScript 库，给任意 DOM 元素绑定点击波纹动画并可清除。　|　技术栈：TypeScript, Less, Jest, esbuild, Babel, GitHub Actions, gh-pages
- **亮点**：完整库工程化：npm 发布配置、tsc 声明、Less 变量+CSS 变量双重定制、esbuild 示例、gh-pages 演示；带 Jest 单测覆盖 5 个场景(触发/动画结束/disabledClass/clear/null) + Codecov CI；用 WeakMap 管理元素与清理函数避免内存泄漏，clearEffect 注销监听与定时器；颜色有效性判断(过滤白/灰/透明)直接借鉴 antd 实现并注明来源
- **短板**：styleForPseudo 为模块级单例，多元素同时触发会相互覆盖(共享同一 style 节点)；triggerWave/onWaveEnd 用泛型重复声明 Element 略显冗余，部分边界(target 非绑定元素)处理粗糙；getWaveColor 用 `||` 取色，border-color 为空字符串才回退 background，逻辑略脆；依赖外部 dynamic-stylesheet，且 isHiddenElement 内塞 NODE_ENV==='test' 测试 hack 入生产代码
- **证据**：src/wave.ts:44 const cancelWaveMap = new WeakMap<HTMLElement, () => void>() —— 用 WeakMap 做实例级清理；src/wave.ts:8 let styleForPseudo 模块级单例，第68行 updateCSS 复用单节点，多元素并发会冲突；src/wave.ts:17-24 isNotGrey 注释引用 antd 源码，说明实现源自人工改写；src/wave.ts:11-13 isHiddenElement 内含 process.env.NODE_ENV==='test' 测试旁路写进生产逻辑；src/test.ts:17-58 五个测试用例覆盖主要分支；.github/workflows/test.yml 跑 coverage 并上传 Codecov；package.json:8-12 build/example/gh-pages/prepublishOnly(np) 完整发布链路
- **年代背景**：2021 年 esbuild、TS4.x、Less4、Jest26 均为当年主流，作者用这套工具链做了一个发布级小库并配齐测试与 CI，符合当年一名熟练前端开发者的标准工程实践。

### 2021-05-15 · react-hooks-analysis　(功能6/代码5/技术7)
- **定位**：用 Slidev 制作的组内技术分享 PPT，源码级浅析 React Hooks 的渲染原理（Fiber/renderWithHooks/dispatcher/diff/memo/useCallback/派生state/Context）。　|　技术栈：Slidev, Markdown, Vue 3, Vite, GitHub Actions, Tailwind/UnoCSS, CodeSandbox 嵌入
- **亮点**：对 React 17 Fiber/Hooks 源码有真实源码级理解（HooksDispatcherOnMount/Update、renderWithHooks、areHookInputsEqual）；讲解逻辑由浅入深、配 CodeSandbox 实例与 benchmark 截图，分享质量高；覆盖冷门点：observedBits 位运算、useContextSelector、用 useRef 实现更优 useCallback；工具链选型现代（2021 年 Slidev 刚兴起即采用）+ GitHub Actions 自动部署
- **短板**：仅是演讲稿，无可运行/可复用代码产物（自身定位决定，非缺陷）；唯一手写 Vue 组件 code-sand-box.vue 很简单（toggle 显隐）；CI 用 actions/checkout@v2 未锁版本、push 即部署较粗糙；代码片段中有零星笔误（如 '4,5,6,78'、'Raect'）
- **证据**：slides.md:45-56 准确区分 HooksDispatcherOnMount/OnUpdate；slides.md:90-106 摘录 renderWithHooks 真实源码并解释 dispatcher 赋值；slides.md:161-167 用 hooks 数据队列索引解释为何不能条件调用 Hook；slides.md:558-573 用闭包+useRef 实现稳定引用版 useCallback；slides.md:829-842 observedBits 二进制掩码 + useContextSelector 实验特性；components/code-sand-box.vue:21-36 唯一自写组件，仅 ref+toggle 逻辑；package.json:8-12 @slidev/cli 0.9.8，.github/workflows/gh-pages.yml 自动部署
- **年代背景**：2021 年 React 17 + Hooks 已成主流但社区源码级解析仍稀缺，作者能在当时阅读 Fiber 源码并产出条理清晰的内部分享，技术深度在当年明显高于平均水平；Slidev 也是 2021 年新生工具，采用得很及时。

### 2021-05-16 · rollib　(功能6/代码7/技术6)
- **定位**：基于 Rollup 的零配置库打包工具，支持 TS/React、Less/Sass/Stylus、多入口多格式输出。　|　技术栈：TypeScript, Rollup, Babel, PostCSS, Node.js CLI
- **亮点**：对标 father/tsdx/microbundle 的零配置思路完整：插件链组装、deps/peerDeps 自动 external、ES/CJS 双格式差异化处理；TypeScript 类型设计较地道：UserConfig 接口清晰、RollupOptions 用 Omit 收窄 output 类型；@babel/register 支持 rollib.config.ts 配置文件，体现对工具链细节的理解；Babel 配置按 format 区分 targets(node:6 vs browserslist)与 runtimeHelpers，考虑较周到
- **短板**：处于 0.0.1-alpha.1 早期，多处 // todo 错误处理未实现(config 不存在、package.json 缺失仅静默 return)；完全无测试、无 CI、无 README 进阶文档；build-values.ts 用全局 Map 单例传递 cwd，是较脏的全局状态做法；getRollupConfigs 中 typescript 插件 declarationDir 直接用 dir，多格式输出时声明文件可能相互覆盖
- **证据**：src/get-rollup-configs.ts:42-49 自动将 dependencies 与 peerDependencies 加入 external，是库打包的正确做法；src/get-rollup-configs.ts:60-92 用 .filter(Boolean) + 布尔短路组装可选插件(postcss/babel/terser)，简洁；src/get-babel-config.ts:15,31 按 format 区分 targets({node:6} vs browserslist)与 runtimeHelpers，差异化处理 ES/CJS；src/register-config.ts:7-13 用 @babel/register 让用户配置支持 .ts，体现工具链理解；src/build.ts:25-28 与 src/utils.ts:43-47 多处 // todo 标记错误分支未实现，仅静默 return；src/build-values.ts:1-11 全局 Map 单例存放 cwd，模块间靠副作用共享状态，设计偏脏；src/get-rollup-configs.ts:82 declarationDir: dir，多 output 共享 dir 时 .d.ts 可能冲突；无 .github 目录、无任何 *.test.* 文件，git log 仅 1 个提交
- **年代背景**：2021 年 Rollup 2.x + @rollup/plugin-* 生态成熟，零配置库打包(father/tsdx/microbundle)正流行；该作者紧跟当年范式并自行实现完整插件链，按当年标准属于合格偏上的工具作者水平。

### 2021-05-23 · lib-tool　(功能7/代码6/技术6)
- **定位**：零配置的组件库打包 CLI 工具，文件到文件编译，同时输出 ESM/CJS 及 .d.ts，支持 JS/TS/React 与 Less/Sass/CSS。　|　技术栈：TypeScript, Node.js CLI, Babel (@babel/core+presets), less/sass/postcss/autoprefixer, dependency-tree, glob, Jest, yargs-parser
- **亮点**：模块划分清晰：cli/配置解析/文件发现/transform 管线职责分明；用 @babel/register 实现加载 toolrc.ts 类型化配置，体验细节到位；match/dependence 双模式，dependence 借 dependency-tree 只打包被引用文件（fixture 验证 c.js 被正确排除）；完整集成测试：jest globalSetup 跑真实构建并与 checked-in expected 快照逐文件比对；TS strict 开启，toolEnv 用函数重载，2021年看属中上 TS 水准
- **短板**：全局可变单例 toolEnv 跨多配置共享，脆弱且无法并发；logger.ts 有缺陷：kleur.red 只返回字符串从不打印，且 internalLogError 失败时 process.exit(0) 报成功；build.ts 中 less/sass/css 三段近乎复制粘贴(~90行)，可抽象为通用循环；样式/声明文件在 esm 与 cjs 两个 format 下被重复转换两遍；process.on('unhandledRejection', throw) 错误处理粗糙
- **证据**：src/build.ts:100-188 less/sass/css 三块逻辑高度重复，仅扩展名/transform 函数不同；src/logger.ts:4 logError 调用 kleur.red(message) 但未 console.log，颜色字符串被丢弃；:10 process.exit(0) 在错误路径返回成功码；src/toolEnv.ts:1-22 模块级全局单例 + 函数重载 set，配置间共享同一可变状态；src/getUserConfigs.ts:7-15 用 @babel/register 仅对 toolrc 文件做 TS 转译以支持类型化配置；src/getFilesPath.ts:34-50 dependence 模式用 dependency-tree.toList 并过滤 node_modules；fixtures/dependence-default：src 有 index/b/c.js，expected/es 仅 index.js+b.js，证实未引用的 c.js 被正确排除；test/build.test.ts:5-26 遍历 fixtures 对 expected vs dist 逐文件内容比对的集成测试；src/transform/transform.ts:8-31 默认 babel preset 含 ts/react/env，esm 时 modules:false 保留 import
- **年代背景**：2021年组件库打包多依赖 father/rollup/gulp 等重型方案，作者自造一个零配置、file-to-file、双格式输出且带 dependency-tree 裁剪与类型化 toolrc 的轻量工具，思路与工具链选型契合当年生态，属于合格偏上的工程实践。

### 2021-05-26 · pr-preview-action-demo　(功能6/代码6/技术5)
- **定位**：用一个未改动的 Create React App 脚手架作载体，演示一套基于 GitHub Actions 的 PR 预览部署流水线（build/deploy/start 三段式，部署到 Surge.sh 并在 PR 下自动回写一条预览评论）。　|　技术栈：GitHub Actions, Create React App, React 17, Surge.sh, actions-cool/maintain-one-comment, dawidd6/action-download-artifact, npm/yarn
- **亮点**：采用 pull_request + workflow_run + pull_request_target 三工作流分离，正确遵循 2021 年安全部署 fork PR 预览的范式（不可信构建不带 secrets，特权部署/评论分离）；通过 artifact 上传 pr-id.txt 在工作流间传递 PR 上下文，解决 workflow_run 不携带 PR 信息的经典问题；node_modules 缓存用 package-lock-only + 临时目录作为缓存 key 的优化技巧；用 maintain-one-comment 维护单条状态评论，含 prepare/success/failure 三态反馈，工程意识完整
- **短板**：React 应用本体 100% 是 CRA 默认脚手架，零业务代码（App.js/README/index.js 均为模板原样）；workflow 写法基本照搬 Ant Design / actions-cool 生态的成熟配方，原创成分低；actions/checkout@master、set-output 等当年已偏旧/后被弃用的写法；纯 demo 性质、0 star、无文档说明自身意图，README 仍是 CRA 默认内容
- **证据**：.github/workflows/preview-build.yml:6 on: pull_request 仅构建上传 artifact 不接触 secrets；.github/workflows/preview-deploy.yml:5-9 on: workflow_run 监听 Preview Build 完成后再带 SURGE_TOKEN 部署；.github/workflows/preview-deploy.yml:42-43 export DEPLOY_DOMAIN + npx surge 按 PR 号生成预览子域名；.github/workflows/preview-build.yml:25-30 'hack for single file' 缓存 package-lock 的优化技巧；.github/workflows/preview-build.yml:74-83 Save/Upload PR number 通过 pr-id.txt 跨工作流传递；src/App.js:1-25 与 README.md:1 均为 Create React App 默认未改动脚手架；git log 仅 'Update preview-start.yml' 一条提交，印证为一次性 demo
- **年代背景**：2021 年 GitHub Actions 尚无官方安全部署 fork PR 预览的内置方案，社区刚摸索出 workflow_run 分离模式；作者正确复用了这套当年算前沿的范式，故工作流部分给中等偏上，但 React 本体为零改动模板，整体只是该范式的演示复刻。

### 2021-05-31 · react-test-demo　(功能6/代码6/技术4)
- **定位**：一个用中文注释演示 React Testing Library 与 jest 常见测试套路的学习型 demo（点击/输入/disabled/props/异步/定时器/snapshot/hooks 共 10 个用例）。　|　技术栈：React 17, Jest 27, @testing-library/react, @testing-library/react-hooks, @testing-library/jest-dom, Babel
- **亮点**：覆盖面较全：事件、props、异步、fakeTimers、snapshot、hooks 都有；中文注释逐行讲解，作为教学/速查笔记可读性好；配置规范：babel preset-env/preset-react、jsdom 环境、setup jest-dom 均到位；10 个用例全部可运行通过，依赖版本与 2021 年生态匹配
- **短板**：纯 demo，无被测业务代码/被测组件库，实用价值有限；'Hooks 测试' 用例存在隐患：waitFor 未 await 却断言 count===1，靠 waitFor 同步首跑碰巧通过，理解有偏差；异步 hook 用例触发 act() 警告，未做包裹处理；技术深度低，均为框架文档级常规用法，无进阶/边界场景(mock 模块、context、错误边界等)
- **证据**：tests/index.test.js:111-123 useCounter 测试用 waitFor(() => result.current.increment()) 但未 await，随后直接 expect count===1；tests/index.test.js:125-139 异步 hook 用 setTimeout 更新 state，运行时产生 'not wrapped in act(...)' 警告；tests/index.test.js:5-16 标准 fireEvent.click + toBeCalledTimes 写法地道；package.json:5-13 仅 react17/jest27/testing-library 等 devDeps，private:true 无业务源码；实测 npx jest: 10 passed, 1 snapshot passed, 0.684s
- **年代背景**：2021年 React 17 + Testing Library + Jest 27 正是社区主推的测试范式，这个仓库的工具选型与写法完全契合当年标准，是典型的个人学习笔记，无AI工具背景。

### 2021-06-02 · scroll-progress-bar　(功能6/代码6/技术4)
- **定位**：一个零依赖的纯 TS 滚动进度条库，挂在页面顶部随滚动改变宽度，支持 SSR 安全导入。　|　技术栈：TypeScript, DOM API, requestAnimationFrame, tsc 双格式构建(es/lib), GitHub Packages CI
- **亮点**：SSR 安全设计到位：DOM 访问全部惰性放进 show/onScroll，模块导入不碰 document；默认用 requestAnimationFrame 节流滚动更新，性能意识正确；scrollHeight 兼容多浏览器取 Math.max，引用了规范来源；已发布到 npm 且有双格式(esm/cjs)产物与 CI 自动发布
- **短板**：完全没有测试；全局可变状态(config/id/scrolling 模块级单例)，无法多实例；类型有偷懒：config.id!/offset! 非空断言、noImplicitAny:false；debounce 实现实为延时而非真防抖，命名与语义略偏差；无构建打包/压缩(直接 tsc)，README 的 bundlesize badge 略显过度包装
- **证据**：index.ts:29-38 initialElement/getElement 把 document 调用延迟到运行时，实现了 README 宣称的 SSR 支持；index.ts:66-72 用 scrolling 标志位 + requestAnimationFrame 做节流；index.ts:19-27 getScrollHeight 取六个属性的 Math.max 并注释规范链接；index.ts:38,47 使用 config.id!/config.offset! 非空断言；package.json:14 build 脚本仅 tsc 两次输出 es/lib，无打包器；index.ts:38 getElementById 与 96-100 单例 progressBar 导出，无多实例能力
- **年代背景**：2021 年这种零依赖、SSR 友好、rAF 节流的小工具库属于合格的前端基础设施实践，tsc 双格式发布在当年也算常规且够用，按当年标准评估而非以现代打包/测试要求苛责。

### 2021-06-22 · react-native-storybook-example　(功能6/代码5/技术6)
- **定位**：演示如何用 React Native Web + Storybook 让 native-base v3 组件同时在 RN 设备端和 Web 端的 Storybook 中渲染的概念验证示例。　|　技术栈：React Native 0.64, react-native-web 0.17, Storybook 6 (web) / 5 (RN), native-base 3.0-next, TypeScript, Webpack5 builder, Babel module-resolver
- **亮点**：核心打通点是 RN/Web 双端别名映射(react-native→react-native-web、@storybook/react-native→@storybook/react、svg→svg-web)；webpackFinal 自定义 babel-loader 处理 RN 源码 flow/jsx，解决 react-native-web 集成痛点；覆盖 15 个 native-base 组件 story，对当时 v3-next 早期生态有参考价值
- **短板**：App.tsx 与 __tests__ 均为 RN 模板原样未改，实质内容仅配置+story；stories/index.js 只 require Button/Button.stories(路径还不存在)，与 main.js 的 glob 机制重复且矛盾；story 内容多为 native-base 官方文档示例的直接搬运，无原创封装；README 仅两行命令，无背景/原理说明；单次 commit 无迭代痕迹
- **证据**：.storybook/main.js:29-33 定义 alias 把 react-native/@storybook/react-native/svg 映射到 web 实现；.storybook/main.js:1-28 自定义 rules 用 babel-loader+preset-flow 转译 RN 源码并注入 react-native-web 插件；babel.config.js 配套用 module-resolver alias '^react-native$':'react-native-web'；App.tsx:1-9 头部注释表明为 react-native-template-typescript 生成的默认模板，正文未改；storybook/stories/index.js:1 仅 import './Button/Button.stories'，而实际 story 平铺在 stories/*.stories.js；package.json:16-19 依赖 native-base ^3.0.0-next.40、react-native-svg-web，体现 web 兼容意图；storybook/stories/Select.stories.js 等 15 个文件均为 storiesOf API 的薄包装(grep storiesOf=15/15)
- **年代背景**：2021 年中 native-base v3 尚在 next 预发布、react-native-web 让 Storybook 同时跑 RN/Web 仍属较前沿的折腾，这套别名打通方案在当年有实验价值，故技术深度按当年标准给中等偏上，而非以今日成熟工具链苛责。

### 2021-07-03 · LeetCode-Note　(功能4/代码6/技术4)
- **定位**：作者个人的 LeetCode 刷题笔记，用 Swift 实现约 26 道题（以链表、二叉树为主），并通过 GitHub Action 自动生成 README 题目索引。　|　技术栈：Swift, GitHub Actions, Node.js (README 生成脚本)
- **亮点**：解法地道使用 Swift 特性（可选链、quotientAndRemainder、计算属性、模式匹配）；多数题目附带个人思路注释，体现真实理解（如 142 快慢指针数学推导）；自建 CI：用自己发布的 GitHub Action write-file-with 自动重生成 README 索引，有一定工程巧思；README 索引脚本按题号数字排序、做 encodeURI 处理中文文件名，细节考究
- **短板**：707. 设计链表为未完成残件，含语法错误（prevNode?.next = 缺右值，deleteAtIndex 空实现）；题目均为 easy/medium 常规链表/树题，无高难度算法或性能优化深度；无任何测试，正确性仅靠 LeetCode 平台隐式验证；142 的 repeat-while 写法对空表/无环表较脆弱，可读性与健壮性一般；命名/空格风格不统一（如 Node(val,prev:tailNode) 缺空格），属随手刷题风格
- **证据**：142. 环形链表 II.swift:20-31 注释手写快慢指针 a=c 数学推导；707. 设计链表.swift:67 `prevNode?.next =` 语法残缺，:71 deleteAtIndex 空函数体，为未完成 WIP；2. 两数相加.swift:43 使用 sum.quotientAndRemainder(dividingBy: 10) 地道处理进位；622. 设计循环队列.swift:13 用计算属性 rear:{(front + count) % queueSize} 实现循环队列；scripts/listed.js:5-22 readdir 过滤 .swift、按题号排序、encodeURI 生成 README 链接；.github/workflows/listed.yaml:12 使用作者自有 Action zhangyu1818/write-file-with@v1 + add-and-commit 自动提交 README；README.md:1-4 个人化口吻『虽然以前立志学算法，不幸的是志向夭折了』，确认为个人学习笔记
- **年代背景**：2021 年 Swift 已成熟、GitHub Actions 普及，作者用自建 Action 自动维护索引在当年算有想法的工程小巧思；但题目难度与缺测试使其本质仍是个人刷题记录，按当年标准属合格偏下的学习仓库。

### 2021-07-03 · data-structure　(功能6/代码6/技术4)
- **定位**：用 Swift Playground 按自考本科数据结构教材(02331)实现链表/栈/队列等经典数据结构，边备考边练习 Swift。　|　技术栈：Swift, Xcode Playground
- **亮点**：用泛型 Node<T>/LinkedList<T> 地道实现，配合 subscript、where 约束扩展、convenience init；循环数组队列用取模运算实现环形缓冲，count/head/trail 逻辑正确；覆盖面较广：单/循环/双向链表、数组栈、链栈、循环队列、链队列+括号匹配/回文/归并等练习；README 诚实交代学习背景与目标，分支/页面组织清晰
- **短板**：存在真实 bug：数组 Stack.top 返回 values.count 而非 count-1；单链表 insert(at:)/remove(at:) 的 while+计数器逻辑有误，定位节点不可靠；at(of:) 用 while let next 遍历会漏掉最后一个节点；练习代码大量强制解包(!)，无任何单元测试，纯 print 验证
- **证据**：4 Stack/Contents.swift: var top: Int? { isEmpty ? nil : values.count } 应为 count-1；1 Singly linked list/Contents.swift: insert(at:) 内 while let next 中仅在 i<index-1 时移动 node，否则 break，index 计数不准确；1 Singly linked list/Contents.swift: at(of:) 用 while let next 遍历，末节点 value 永不被比较；2 Circular linked list/Contents.swift: insert(value:) 用 where T:Comparable 扩展按序插入并维护 head 指向尾节点，思路正确；6 Queue/Contents.swift: trail = (head+count)%queueSize 环形队列实现正确；git log 仅 1 个提交 'c9120ff 循环队列'，单人学习项目
- **年代背景**：2021 年 Swift 5.x 已成熟，泛型/扩展/约束等特性属当年标配，作者作为备考练习能写出基本地道的泛型数据结构，属合格水平，但功能性 bug 与零测试拉低了工程质量。

### 2021-07-04 · write-file-with　(功能5/代码5/技术4)
- **定位**：一个 GitHub Action：读取指定文件内容，传入用户提供的 JS 脚本函数处理后，把返回值写回该文件。　|　技术栈：JavaScript, Node.js, @actions/core, @zeit/ncc, GitHub Actions
- **亮点**：完整可发布的 GitHub Action：齐备 action.yml + ncc 打包 dist + CI 工作流；核心逻辑简洁地道，正确使用 fs.promises 与 @actions/core 的 getInput/setOutput/setFailed；main().catch(core.setFailed) 错误处理符合 Actions 惯例
- **短板**：残留调试代码 console.log("files:", await fs.readdir(...))；README 示例拼写错误 module.export(应为 module.exports)；无输入校验/无测试断言(CI 仅跑通不验证结果)；require 用户脚本存在任意代码执行隐患且未做说明；功能本质极小(16 行)，实用性有限
- **证据**：index.js:8 `console.log("files:", await fs.readdir(process.cwd()));` 残留调试输出；index.js:9-13 核心逻辑：require 用户脚本→readFile→fn(content)→setOutput→writeFile；index.js:16 `main().catch(core.setFailed);` 惯用错误兜底；action.yml:11-13 `using: node12` 指向打包后的 dist/index.js；package.json:7 build 脚本 `npx ncc build index.js`，正确的 Action 打包方式；README.md:6 示例写成 `module.export`(拼写错误)；.github/workflows/test.yaml:10 CI 仅 touch/echo 脚本并执行，未对输出做断言
- **年代背景**：2021 年 GitHub Actions 生态已成熟，@actions/core + ncc 打包是当时编写 JS Action 的标准范式，作者完整遵循；但项目目标本身极小，按当年标准属于合格的小工具而非有深度的工程。

### 2021-07-17 · generate-d-ts　(功能6/代码6/技术5)
- **定位**：一个极小的 TypeScript 工具库，封装 TypeScript Compiler API，以编程方式为指定的 .ts/.tsx 文件生成 .d.ts 声明文件并写盘。　|　技术栈：TypeScript, TypeScript Compiler API, Node.js (fs/path), npm package
- **亮点**：地道使用 TS Compiler API：通过覆写 CompilerHost.writeFile 将 emit 结果截留在内存；职责清晰，createDeclarations(纯生成)与 writeDeclarations(落盘)分离；已发布为 npm 包并正确声明 typescript 为 peerDependency；类型与异步落盘(fs/promises)处理符合 2021 工程习惯
- **短板**：mkdirSync(dir) 未加 { recursive: true }，多级输出目录会抛错；options 对象定义后未复用，createProgram 内重复内联同样的编译选项；无 build/prepublishOnly 脚本，files 引用 index.js/index.d.ts 却依赖手动 tsc；无任何测试与 CI；未对空文件列表/非法路径做边界处理
- **证据**：index.ts:17-19 host.writeFile 覆写以内存捕获 emit 输出，是 TS 官方文档式正确用法；index.ts:11-15 与 index.ts:21-27 编译选项重复定义，options 实际只用于 createCompilerHost；index.ts:36-38 mkdirSync(dir) 缺少 recursive 选项，嵌套目录将失败；package.json:7-10 files 列出 index.js/index.d.ts 但无 scripts.build；package.json:11-13 typescript 正确置于 peerDependencies
- **年代背景**：2021 年 TS Compiler API 文档稀少且类型晦涩，能正确用 createCompilerHost + writeFile 拦截实现 in-memory d.ts 生成属于中上水平的小工具，按当年标准合格偏上但规模过小、缺测试与构建脚本。

### 2021-07-25 · tikka　(功能6/代码7/技术6)
- **定位**：一个插件式的「文件到文件」转换打包工具（非 bundle），通过可组合的 transform 任务对 JS/TS/Less/Sass/d.ts 做编译输出，类似 father/tsup 的轻量自研版。　|　技术栈：TypeScript, Yarn2/Berry Workspaces, Babel, SWC, Less, Sass, PostCSS, Jest, ESLint(airbnb-typescript)
- **亮点**：插件式架构清晰：以TransformState上下文对象贯穿可组合transform任务，依赖注入readFile/outputFile/logger；withPostcss高阶transform设计巧妙：装饰outputFile将css输出管道接入postcss，体现良好抽象品味；monorepo工程化到位：Yarn2 workspaces+9个细粒度包+CI(tsc+lint+test)+husky+独立release脚本；测试用fixture/expect目录对比真实编译产物，覆盖compile核心与各transform
- **短板**：transform-sass成功日志误写为'less files transform success'(transform.ts:66)，明显copy-paste遗留；transform-swc读取options.outputPath但其类型为@swc/core的Options并无该字段，存在类型与运行时不符；compile()仅返回{tasks}且handler.run依赖闭包，处于v0.0.0-alpha.1，完成度与文档链接(指向#anchor)尚不完整；错误处理偏弱：declaration里execSync失败仅logger.error后继续，catch中e.message未做类型守卫
- **证据**：packages/compile/src/compile.ts:31 构造TransformState注入readFile/outputFile/relativePath/remove/logger并以taskQueue顺序await执行；packages/with-postcss/src/with-postcss.ts:25 outputWithPostcss装饰原outputFile，通过{...state,outputFile}注入下游transform；packages/transform/src/default.ts:6 DEFAULT_BABEL_CONFIG按.tsx动态设置preset-typescript的isTSX/allExtensions；packages/transform-sass/src/transform.ts:66 logger.success('less files transform success') 复制粘贴bug；packages/transform-swc/src/transform.ts:13 const { outputPath: outDir='' }=options 但SWCTransformOptions=Options无outputPath；tsconfig.json strict+noUnusedLocals+paths别名映射各workspace；.github/workflows/test.yml 执行tsc:check+lint+test
- **年代背景**：2021年自研file-to-file构建工具属合理需求(father2/tsup刚兴起)，采用Yarn2 workspaces+Babel/SWC双引擎+PostCSS管道在当年是较前沿且地道的工程实践，按当年标准属合格偏上的中高级水平。

### 2021-07-29 · cjsb　(功能6/代码6/技术5)
- **定位**：一个基于 Babel 的 CLI 工具，将 JS/TS 源码快速编译为 CommonJS 库，支持 monorepo 与 .d.ts 声明文件生成。　|　技术栈：TypeScript, Node.js, @babel/core, @babel/preset-env, @babel/preset-typescript, yargs-parser, glob, fs-extra
- **亮点**：已发布至 npm(v0.0.8)的真实可用工具；支持 monorepo 多包按序编译；声明文件生成时对 tsconfig 的备份/恢复处理(try/finally)；CLI 参数解析与默认值设计清晰
- **短板**：缺少测试与 CI 配置；monorepo "pass order" 依赖排序逻辑实际未实现(仅靠输入顺序)；declaration 分支会临时改写并删除用户 tsconfig，存在副作用风险；无错误处理/输入校验，babel transform 失败无兜底
- **证据**：src/cli.ts:75-93 使用 babel.transformFileSync 逐文件编译并用 fs.outputFileSync 写出，babelrc/configFile 关闭确保隔离；src/cli.ts:37-44 monorepo 通过 --packages 映射多包路径并打印构建列表；src/cli.ts:95-124 declaration 时改写 tsconfig 注入 emitDeclarationOnly 并 execSync('tsc')，finally 中恢复原文件；package.json:25 依赖中包含自身 cjsb:^0.0.7，并以 build:cjsb 自举编译；README.md:29 声称 monorepo 按依赖顺序打包，但代码仅按输入数组顺序遍历，无拓扑排序实现
- **年代背景**：2021 年 TS+Babel preset-typescript 编译库的范式已成熟(tsup/unbuild 尚未流行)，作者用 Babel 手搓 CommonJS 构建器属于当年合理且地道的方案，评分按此背景衡量。

### 2021-08-11 · swiftui-playground　(功能5/代码5/技术5)
- **定位**：用 SwiftUI 复刻 iOS 15 Apple 天气 App 的单屏 UI，含视差/吸顶动画与 SpriteKit 下雨粒子效果。　|　技术栈：Swift 5, SwiftUI 3 (iOS 15), SpriteKit, MapKit, Xcode
- **亮点**：及时跟进 iOS 15 beta 新 API：.ultraThinMaterial / .foregroundStyle / SpriteView / Map；用泛型 + @ViewBuilder 封装可复用的 StackView 容器；GeometryReader 全局坐标驱动的视差、吸顶、渐隐动画实现完整；SpriteKit 粒子(SKEmitterNode)桥接进 SwiftUI 做下雨效果，跨框架整合
- **短板**：纯静态 UI demo，数据全部硬编码，无网络/数据层/状态管理；GeometryReader 内 DispatchQueue.main.async 改 @State 是 SwiftUI 反模式；SKEmitterNode(fileNamed:)! 强解包、大量重复视图代码、无测试无 README；依赖 UIScreen.main.bounds，多窗口/分屏下不可靠
- **证据**：WeatherHomeView.swift:133-135 在 GeometryReader 渲染期用 DispatchQueue.main.async 写 self.offset，layout 期改状态的已知反模式；StackView.swift:10-22 泛型 StackView<Title: View, Content: View> + @ViewBuilder 初始化，封装良好；CornerShape.swift:10-18 自定义 Shape，用 UIBezierPath byRoundingCorners 实现按需圆角；WeatherHomeView.swift:177,194 SKEmitterNode(fileNamed: "Rain.sks")! 强制解包，缺少错误处理；WeatherItem.swift:49-78 HoursItemView 20+ 条 ForecastView 全部硬编码时间/温度；project.pbxproj IPHONEOS_DEPLOYMENT_TARGET = 15.0 / SWIFT_VERSION = 5.0，紧跟当年 beta 系统
- **年代背景**：2021-08 iOS 15 尚在 beta，作者第一时间用 .ultraThinMaterial、SpriteView 等新 API 复刻系统天气 App，属于当年合格偏上的学习型实践，但仅停留在静态 UI 临摹层面。

### 2022-01-01 · react-native-google-autocomplete-modal　(功能6/代码6/技术6)
- **定位**：一个 React Native 原生模块，封装 Google Places SDK，在 iOS/Android 上以全屏 Modal 形式弹出地点自动补全选择器并将选中地点的结构化信息返回给 JS。　|　技术栈：TypeScript, Swift, Objective-C, Kotlin, React Native 0.63, GooglePlaces SDK, react-native-builder-bob, Gradle/CocoaPods, Jest, CircleCI
- **亮点**：完整双端原生桥接(iOS Swift + Android Kotlin)，非纯 JS 玩具；Swift 端正确处理 iOS13 scene 的 topViewController 与 Promise resolve/reject；Android 端用 ActivityEventListener+startActivityForResult 的标准范式，API key 经 gradle resValue 注入；类型定义详尽(GMSPlace 全字段)，并附 create-react-native-library 标准工程(bob/CI/lint)
- **短板**：iOS getAutocompleteFilter 返回值未赋给 controller，国家过滤实际未生效；TS 接口字段拼成 county 与原生读取的 country 不一致；Android convertPlace 的 viewport/plusCode map 构建后未 putMap，是死代码；测试仅 it.todo 占位，错误处理留有 TODO，version 仍为 0.0.0 未发布
- **证据**：ios/GoogleAutocompleteModal.swift:29 `let autocompleteFilter = self?.getAutocompleteFilter(options)` 计算后从未赋给 autocompleteViewControll，过滤失效；src/index.ts:30 `county?: string` 拼写错误，而 swift 读取 options["country"]；android/.../ConvertPlace.kt:41-58 viewport/plusCode 创建 map 后没有 result.putMap，结果丢失；src/__tests__/index.test.tsx:1 仅 `it.todo('write a test')`；ios/GoogleAutocompleteModal.swift:58 `// TODO: handle the error.`；android/build.gradle:37 resValue 注入 GOOGLE_PLACES_API_KEY，默认 UNSET 时不初始化 Places
- **年代背景**：2022 年 RN 原生模块开发普遍依赖 create-react-native-library 脚手架，作者在此模板上独立实现了双端 Swift/Kotlin 桥接与完整类型，属当年合格偏上的库开发水准；当年无 AI 编码工具，代码风格与若干人工 bug 均符合手写特征。

### 2022-10-11 · imessage-app-icon　(功能7/代码6/技术4)
- **定位**：一个纯浏览器端的 Web 工具：上传图片，用 canvas 批量缩放出 Apple iMessage App 所需的全部尺寸图标，打包成 zip 下载。　|　技术栈：TypeScript, React 18, Vite 3, antd 4, jszip, file-saver, Canvas API, gh-pages
- **亮点**：目标明确且已部署可用（GitHub Pages 在线）；正确覆盖 Apple iMessage 图标全部规格尺寸；纯前端无后端依赖，用 canvas+jszip 实现批量导出，方案轻巧得当；代码地道：FileReader/Image promise 封装、createCanvas 闭包工厂、antd Form 受控用法规范
- **短板**：完全无 README，使用与意图缺乏文档；无任何测试与 CI；getImage 的 Promise 无 reject/错误处理，加载失败会静默挂起；toBlob 返回 Promise<unknown> 未加类型，folder.file 传 blob 处类型不够严谨；squareSize 数组含重复 '58x58' 项，导出会被同名覆盖，疑似小笔误
- **证据**：src/App.tsx:24-33 getImage 用 FileReader+Image 封装为 Promise，但只 resolve 无 reject/onerror，存在静默挂起风险；src/App.tsx:35-49 createCanvas 闭包工厂返回 {canvas,ctx,resize,clear}，结构清晰，离屏 canvas 用绝对定位移出视口；src/App.tsx:10 squareSize = ['58x58','87x87','1024x1024','58x58'] 含重复 58x58，导出同名文件会被覆盖；src/App.tsx:73-100 用 for-of 遍历 [图片,尺寸数组] 二元组，逐尺寸 drawImage+toBlob 写入 zip，逻辑紧凑；src/App.tsx:64-66 useSameImg 时令 img768=img1024，复用 1024 图片生成矩形尺寸；package.json:23 使用 gh-pages 部署，vite.config.ts:7 设置 base '/imessage-app-icon/' 匹配 Pages 路径；tsconfig.json strict:true 开启严格模式；全仓库仅 154 行 App.tsx 承载全部逻辑，无测试无 CI
- **年代背景**：2022-10 正值 Vite 3 + React 18 + antd 4 成为前端主流脚手架组合，用 canvas+jszip 做纯前端图标批处理是当年成熟且恰当的范式，本项目技术选型完全贴合年代标准，按 2022 工程水准衡量是一个干净的小工具。

### 2022-10-12 · wechat-test　(功能6/代码5/技术4)
- **定位**：一个每日定时(GitHub Actions cron)抓取墨迹天气与第三方仓库的每日英语单词, 通过微信公众号模板消息推送的个人自动化脚本　|　技术栈：TypeScript, Node.js, axios, dayjs, octokit, dotenv, GitHub Actions, pnpm
- **亮点**：完整可运行的端到端自动化: 数据抓取->聚合->微信模板推送；CI 用 pnpm store 缓存 + 每日 cron 调度, 部署链路清晰；用 Promise.all 并发请求天气与单词, 微信凭证走 secrets/env
- **短板**：service.ts 中墨迹天气 token 硬编码进源码(明文提交)；index.ts:36-43 delete 后又立即重新赋值, 删除逻辑形同虚设的小 bug；类型纪律松: noImplicitAny:false, data:unknown 后随意 any 断言, 几乎无类型定义；无 README/无测试/无错误日志, 失败仅静默兜底
- **证据**：src/service.ts:41,49,57 三个墨迹 API token 直接写死在代码里；src/index.ts:38-40 `if (!value) delete templateData[key]` 后下一行无条件 `templateData[key] = {...}`, delete 被立刻覆盖；src/service.ts:68-91 getWordFromGithubRepo 用 dayjs().diff 取天数作为 _posts 数组下标定位当日单词, 思路巧妙但越界/缺值无防护；.github/workflows/msg.yml:5-6 schedule cron '30 23 * * *' 每日定时触发；tsconfig.json:80 noImplicitAny:false 与第79行 strict:true 矛盾共存
- **年代背景**：2022 年 TS+axios+Octokit+GitHub Actions cron 做个人推送 bot 是非常典型且成熟的玩法, 按当年业余自动化脚本标准属合格水平, 不能用现代严格类型/密钥管理标准苛责。

### 2022-11-17 · useVideoControls　(功能6/代码7/技术6)
- **定位**：一个 React Hook 库，通过 ref + Context 共享 HTMLVideoElement，用 getter/setter 代理出一套响应式的视频控制 API（播放、音量、倍速、画中画、全屏、状态机）。　|　技术栈：TypeScript, React 18, Vite (library mode), vite-plugin-dts, pnpm, HTMLVideoElement API
- **亮点**：getter/setter 代理 video 元素属性，配合 useMemo 稳定引用，设计巧妙；Context+ref 让子组件共享同一视频实例（App.tsx 中 Nested 全屏按钮）；waiting 事件 500ms 防抖避免状态闪烁，UX 细节到位；完整库工程化：Vite lib 模式、dts 生成、exports 双格式、peerDependencies、严格 TS
- **短板**：README 仅一行标题，无文档；version 0.0.0 未真正发布；无任何测试；残留 console.log('video element is not defined') 调试语句；exitPictureInPicture 接口声明 options 参数但实现忽略（疑似从全屏复制）；defaults 在 useLayoutEffect([]) 中仅初始化一次，props 变更不会响应
- **证据**：src/useVideoControls.ts:143-223 用 useMemo 包裹含大量 get/set 的对象代理 videoRef.current；src/useVideoControls.ts:126-131 forceUpdateRefValue 仅在 ref 值变化时触发重渲染；src/useVideoControls.ts:107-111 waiting 事件用 window.setTimeout 做 500ms 防抖；src/Context.tsx:3-19 createContext 持有 MutableRefObject 并由 VideoControlsProvider 注入；src/useVideoControls.ts:61 console.log 调试输出残留；package.json:3 version 0.0.0；vite.config.ts:8-17 lib 模式 + external react，配 vite-plugin-dts 产出类型
- **年代背景**：2022 年底 React 18 + Vite 3 库模式正当其时，该作者用当年主流且地道的工具链做了一个结构清晰的小型 Hook 库，技术选型与实现都符合当时资深前端水准。

### 2022-11-29 · share-play-swiftui-example　(功能6/代码6/技术6)
- **定位**：一个 iOS/iPadOS SwiftUI 示例 App，演示用 GroupActivities (SharePlay) 配合 AVPlayer 实现「一起看视频」的同步播放与播放列表管理。　|　技术栈：Swift, SwiftUI, GroupActivities (SharePlay), AVKit/AVPlayer, Combine, UserDefaults, Xcode
- **亮点**：正确接入 GroupActivities：sessions() async 流 + join + 状态订阅；AVPlayer.playbackCoordinator 绑定 groupSession 实现同步播放；SwiftUI 与 UIKit 桥接 (UIViewControllerRepresentable) 封装 AVPlayerViewController/UIActivityViewController；iPad/iPhone 自适应 (NavigationSplitView vs NavigationLink) 体现真机适配意识
- **短板**：无 README，对示例仓库的传播价值是明显短板；无任何测试与 CI；错误处理多为 print 吞掉，DispatchQueue.main.async 与 Combine receive(on:) 混用略不统一；ShareSheetView 与 onLongPress 分享入口被注释掉、TODO 未完成，功能不完整；单次提交，看不到迭代过程
- **证据**：PlayerViewModel.swift:21-32 定义 MovieWatchingActivity: GroupActivity，metadata.type=.watchTogether；PlayerViewModel.swift:37-42 groupSession didSet 调用 player.playbackCoordinator.coordinateWithSession；PlayerViewModel.swift:85-114 for await MovieWatchingActivity.sessions() 处理会话生命周期、join、$state/$activity 订阅；PlayerViewModel.swift:130-148 prepareForActivation() 分支处理 activationDisabled/Preferred/cancelled；PlayerView.swift:11-25 UIKitAVPlayer 用 UIViewControllerRepresentable 封装 AVPlayerViewController 并开启 PiP；PreparePlayView.swift:41-55 按 UIDevice idiom 区分 iPad Button 与 iPhone NavigationLink；PreparePlayView.swift:100-102 ShareSheet 分享入口被注释掉，HomeView.swift:10-14 留有未完成 TODO；git log 仅 1 个提交 (f15f187 app icon)，无 README/测试/CI
- **年代背景**：GroupActivities/SharePlay 于 2021 (iOS 15) 推出、2022 年仍是相对新颖且文档稀少的领域，NavigationSplitView 更是 iOS 16 (2022) 才有的全新 API，作者能在当年就用上并正确接入同步播放，技术敏锐度在 2022 标准下属中上水平。

### 2023-05-01 · ali_ecc_js　(功能6/代码5/技术6)
- **定位**：用 secp256k1/ECDSA 复现阿里云盘 web 端 create_session/renew_session 接口的 x-signature 签名逻辑的逆向 PoC 脚本　|　技术栈：JavaScript, Node.js (ESM), @noble/secp256k1, axios, uuid, pnpm
- **亮点**：准确逆向出 appId:deviceId:userId:nonce 的拼接消息与 sha256+ECDSA 签名+recovery id 拼接方案；选用当年正确且轻量的 @noble/secp256k1(v1 异步 API),依赖锁定到 pnpm-lock；签名格式处理到位:der:false、recovered:true 并补 0+recovery 还原浏览器端格式
- **短板**：纯一次性脚本,配置项为硬编码占位符,无封装/无导出/无测试；stringToUint8Array 用 charCodeAt 处理而非 TextEncoder,非 ASCII 会出错；顶层 IIFE 中 nonce 自增与循环逻辑写死(Array(10)),无错误处理/无重试；package.json main 指向不存在的 index.js,字段空置(author/description)
- **证据**：index.mjs:29-36 genSignature: message=`${appId}:${deviceId}:${userId}:${nonce}`,sha256 后 secp.sign(...{recovered:true,der:false}),再 `${hex}0${recovery}` 拼接；index.mjs:13 privateKey = secp.utils.randomPrivateKey() 配合 createSession 上传 pubKey(:44)；index.mjs:72-78 stringToUint8Array 用 str.charCodeAt 而非 TextEncoder；index.mjs:80-94 顶层 IIFE 写死循环 10 次 create/renew,nonce 手动 +=1,无 try/catch；package.json:5 main:index.js 但实际入口为 index.mjs;README.md:23 自述 swift 移植同逻辑失败
- **年代背景**：2023 年阿里云盘风控刚加 ECDSA x-signature,@noble/secp256k1 v1 是当时主流轻量选择,作者能在缺乏公开资料下逆向出签名细节属于合格偏上的实战逆向水平。

### 2023-06-18 · motion-wave　(功能7/代码8/技术6)
- **定位**：一个用 Canvas 渲染并以缓动动画过渡参数的波浪图形 React/原生 JS 库，提供 createWave 核心、useWave Hook 与 Wave/MotionWave 组件三层 API。　|　技术栈：TypeScript, React, Canvas 2D, Ladle, leva, from-to.js, pnpm, ESLint/Prettier, husky
- **亮点**：三层 API 分层清晰：框架无关核心 createWave + Hook + 组件，复用得当；正弦采样配三次贝塞尔插值实现平滑波形，并按 frequency 自适应采样步长(clamp width/80/frequency)；MotionWave 用 JSON.stringify diff 做动画编排，重放前先 stop 旧 controls，含卸载清理；SSR 安全的 useLayoutEffect shim、函数/对象双形态 ref 转发、rAF 正确取消；工程化齐备(2023标准)：strict TS、双 ESM/CJS 构建、husky+lint-staged、Ladle+leva 交互 demo、gh-pages 发布
- **短板**：无任何自动化测试；无 CI 工作流(.github 缺失)；构建手搓(写临时 tsconfig + execSync tsc)，无打包/压缩，与 README 的 bundlephobia 体积徽标略不匹配；package.json types 仅指向 cjs 声明；draw 循环内 cp2X 计算(x+(x-lastX)/3)与末段(nextX-(nextX-lastX)/3)控制点公式不一致，存在轻微数学瑕疵
- **证据**：src/createWave.ts:51-65 calcY 正弦函数 + step=clamp(canvas.width/80/frequency,1,canvas.width) 自适应采样；src/createWave.ts:71-100 用 bezierCurveTo 在采样点间插值平滑曲线；src/MotionWave.tsx:69-89 shouldAnimate 用 JSON.stringify 比较 transition 并 stop 旧 controls 后再 motionTo；src/hook.ts:6-10 typeof window 判定的 useLayoutEffect SSR shim；src/hook.ts:41-60 支持函数式与 ref 对象两种 ref 转发并在卸载时清理；scripts/build.cjs:5-36 通过写 .temp.json + execSync('tsc') 分别产出 dist/esm 与 dist/cjs；package.json:20-27 无 test 脚本；仓库无 .github CI 目录；src/createWave.ts:75 cp2X = x + (x - lastX) / 3 与 line 97 nextX - (nextX - lastX) / 3 公式不一致
- **年代背景**：2023 年中 React 18 + TypeScript 5 + pnpm/Ladle/leva 这套现代前端工具链已成熟，作者据此交付了一个工程化规范、API 分层良好的小型可发布库；以当年开源个人库标准衡量代码质量偏上，但缺测试与 CI 属常见短板。

### 2023-06-22 · from-to　(功能8/代码7/技术7)
- **定位**：一个轻量级（gzip约1kb）的纯值过渡动画库，支持 tween(贝塞尔) 与 spring(弹簧) 两种过渡，可处理数字、数字数组与颜色，不绑定 DOM/框架。　|　技术栈：TypeScript, Vite, bezier-easing, tweakpane, pnpm, ESLint, Prettier, husky
- **亮点**：已发布到 npm 的真实可用库，目标定位清晰(极轻量、无框架绑定)；spring 采用阻尼谐振子物理模型(分欠阻尼/临界/过阻尼三种情形)，移植自 framer-motion；TS 类型设计到位：颜色用模板字面量类型、泛型 animate、类型守卫、Animator 高阶抽象；thenable/await 支持 + play/pause/stop/cancel 完整控制流与 loop/loopDelay；双格式(ESM/CJS)库构建、emitDeclarationOnly 产出 d.ts、lint-staged+husky 工程化
- **短板**：完全没有单元测试(动画/颜色边界逻辑本应可测)；calcGeneratorVelocity 中 (1000 / t - prevT) 运算符优先级疑似 bug，应为 1000/(t-prevT)；拼写错误：ease 选项 'liner'(应为 linear)、注释 'funciton'；无 CI(无 .github)，发布与质量保障靠本地脚本；rgbToAnimatedValue 用 Number 解析未对 NaN/越界做更严格校验
- **证据**：lib/spring.ts:25 `(current - resolveValue(prevT)) * (1000 / t - prevT)` 运算符优先级疑似错误；lib/spring.ts:46-86 resolveSpring 实现 dampingRatio<1/===1/>1 三分支阻尼谐振子解析解；lib/animate.ts:226-235 返回 thenable，then 转发到 currentCompletedPromise，支持 await；lib/animate.ts:100-133 requestAnimationFrame tick + pausedTime/delayTime 暂停恢复时间计算；lib/color.ts:4-8 模板字面量类型 HexColor/RGBColor/RGBAColor，:10-13 类型守卫 isHexColor/isRGBColor；lib/bezier.ts:16-22 defaultEaseMap 含拼写 'liner'，应为 linear；package.json:33-41 build=tsc&&vite build, exports 双 import/require + types；无 test 文件、无 .github 目录(CI 缺失)
- **年代背景**：2023 年中 framer-motion/Vite/template-literal-types 已成熟，作者借此做出定位明确、工程化规范的轻量库，符合当年资深前端的中上水准；同期 AI 辅助尚不普及，代码判定为人工编写。

### 2023-06-27 · pkg-pub　(功能7/代码8/技术5)
- **定位**：一个 CLI 工具，通过向 npm registry 发布一个临时占位版本来抢占/确认 npm 包名是否可用（尤其针对 npm info/view 无法查询的私有包场景）。　|　技术栈：Node.js, JavaScript, CommonJS, prompts, semver, fs-extra, pnpm
- **亮点**：解决真实痛点：私有包名无法用 npm view 查询时确认可用性；代码简洁地道：prompts 条件链 + semver 校验 + try/finally 清理；用 SHA-256 生成确定性临时版本号 0.0.0-temp.<hash>，思路巧妙；已发布为可安装的 npm 包，目标完整可用
- **短板**：缺少错误处理细节：publish 失败仅靠 finally 清理，无友好提示；无测试与 CI；package.json 的 description 与 README 不一致（version 0.0.0 未发版更新）；功能单一，技术深度有限
- **证据**：index.cjs:10-11 SHA-256 截断 16 位生成 hash；index.cjs:30 tempVersion = `0.0.0-temp.${hash(name)}` 确定性版本号；index.cjs:35-39 条件式 prompt（temporary 为真则跳过 version 输入）+ semver.valid 校验；index.cjs:66-70 try/finally 中 execSync('npm publish') 后 fs.remove 清理 temp 目录；package.json:10-12 bin 暴露 pkgp 命令；pnpm-lock.yaml lockfileVersion 6.0 锁定依赖
- **年代背景**：2023 年中 Node.js 生态以 prompts/semver/fs-extra 为标准 CLI 工具链、pnpm 已成主流，此代码完全契合当年的地道工程水准，按当年标准衡量是干净的小工具实现。

### 2023-07-05 · bg-css　(功能6/代码7/技术6)
- **定位**：一个极小的纯 CSS 库，通过渐变背景位移实现深浅色主题切换时的对角线扫光过渡动画。　|　技术栈：CSS, HTML, CSS Custom Properties, linear-gradient, gh-pages, npm
- **亮点**：用 300vw/300vh 渐变 + background-position 位移实现对角线扫光，规避了 background-color 无法平滑过渡的限制；全部变量经 CSS 自定义属性暴露(颜色/时长/缓动)，可定制性好；已发布为 npm 包并配 gh-pages 预览，README/package.json files 字段干净；同时兼容 .dark 与 [data-color-mode=dark] 两种主题约定
- **短板**：功能范围极窄，仅一个主题背景过渡效果；依赖 mix-blend-mode 让按钮可见，未处理内容区可读性/无障碍；无测试、无 CI；渐变巨幅尺寸(300vw)在低端设备可能有重绘开销，未做说明
- **证据**：style.css:7-14 linear-gradient 用硬边渐变(50% 处 dark 到 light 突变)铺成 300vw/300vh 画布；style.css:6 transition: background 配合 style.css:19 background-position:100% 触发扫光动画；style.css:1-5 通过 --theme-bg-light/dark/duration/transition 暴露定制变量；style.css:17-18 同时支持 .dark 与 [data-color-mode='dark'] 选择器；package.json:6-8 deploy 脚本用 npx gh-pages 发布, files 仅含 style.css；index.html:22 按钮用 mix-blend-mode:difference 保证黑白背景下都可见
- **年代背景**：2023 年 CSS 自定义属性、background-position 过渡、mix-blend-mode 均已是稳定且地道的浏览器特性，该实现完全契合当年前端动效的常用技巧，属当年合格偏上的小巧思。

### 2023-07-05 · theme-bg　(功能6/代码7/技术6)
- **定位**：一个发布到 npm 的小型库，用 Canvas 实现圆形扩散的主题切换/背景过渡动画，同时提供 React 组件与原生 JS 两套 API。　|　技术栈：TypeScript, React 18, Canvas 2D, Vite, from-to.js(作者自研动画库), Tailwind, unbuild, pnpm
- **亮点**：双形态 API 设计：React 组件 + 原生 createTransition，React 层只是薄封装；几何处理到位：Math.hypot 计算从任意点覆盖整个画布所需最大半径，center 模式正确换算触发元素中心点；考虑了 Canvas 高 DPI/缩放：用 width/clientWidth 比例换算坐标；工程规范完整：dual cjs/esm exports、peerDependencies、strict+noUnused 的 bundler-mode tsconfig、eslint/prettier/gh-pages 一应俱全；动画用 Promise then 暴露完成时机，forwards/backwards 可逆且能 stop 中断
- **短板**：规模极小（核心仅约 150 行），属单一动画工具；无任何测试；options 作为 useEffect 依赖且通常为内联对象字面量，每次渲染会重建 effect（潜在隐患）；core 依赖作者自研且版本 0.0.1 的 from-to.js，生态成熟度低；Stars=0、version 0.0.0，更接近个人作品而非维护中的库
- **证据**：src/createTransition.ts:38 用 Math.hypot(Math.max(fromX,width-fromX),Math.max(fromY,height-fromY)) 求覆盖全画布最大半径；src/createTransition.ts:32-36 widthRatio/heightRatio 做 canvas 物理像素与 client 尺寸换算，处理高DPI；src/createTransition.ts:76 return { then: animation.then } 以 Promise 形式暴露动画完成；src/CircleTransition.tsx:42-43 center 模式下 clientX-offsetX+width/2 计算触发元素几何中心；src/CircleTransition.tsx:55-58 useEffect 返回清理函数 stopTransition + removeEventListener；src/CircleTransition.tsx:59 依赖数组含 options（常为内联对象）会导致 effect 频繁重建；package.json:8-13 exports 同时提供 import(mjs)/require(cjs)，dist-only files 字段，规范的库发布配置；package.json:25 dependencies 仅 from-to.js@^0.0.1（作者自研动画库）；tsconfig.json:18-21 strict + noUnusedLocals/Parameters/noFallthroughCases 严格配置
- **年代背景**：2023 年中正值 Vite4 + React18 + 严格 TS + 双格式 ESM/CJS 发布成为前端库标配，该仓库的工程脚手架与类型实践完全踩在当年主流水准上，因此按 2023 标准给出中上评价而非苛责其规模。

### 2023-07-06 · type-challenges-answer　(功能7/代码8/技术7)
- **定位**：作者用 TypeScript 类型体操刷 type-challenges 题库的个人答案集，含 86 道（13 easy + 73 medium）解法及部分难题的推导注释。　|　技术栈：TypeScript 5.2, @type-challenges/utils, husky, lint-staged, prettier, GitHub Actions, Node.js scripts
- **亮点**：类型体操功底扎实，递归/分配条件/模板字面量运用地道；GreaterThan 用逐位数字比较绕开递归深度上限（能过 13 位数）；工程化到位：husky 预提交 + lint-staged + prettier + CI tsc 校验；脚本自动生成 README 索引并按难度分组，自动化思维好；对自认有难度的题写了原创推导注释
- **短板**：仅覆盖 easy/medium，无 hard/extreme，深度上限受限；解法依附官方题面模板，本质是练习而非独立项目；Stars 0、纯个人刷题记录，实用价值偏学习向；部分简单题（Readonly/Pick）属 trivial，拉低平均难度
- **证据**：src/04182-medium-fibonacci-sequence.ts:24-39 手写迭代式斐波那契，附逐步推导注释；src/04425-medium-greater-than.ts:28-66 拆数字逐位比较，测试含 GreaterThan<1234567891011,1234567891010>；src/00009-medium-deep-readonly.ts:39-45 同时处理元组与对象的递归只读；src/00012-medium-chainable-options.ts:42-48 用 K extends keyof T?never 防重复 key 的链式类型；scripts/genReadme.js:1-53 reduce 按 easy/medium/hard/extreme 分组自动生成 README；.husky/pre-commit:4-7 预提交跑 genReadme + lint-staged + tsc；.github/workflows/test.yml:23-26 CI 安装依赖后 tsc 类型校验；tsconfig.json:13-15 开启 strict + noImplicitAny + strictNullChecks
- **年代背景**：2023 年中 TS 类型体操已是前端进阶圈成熟话题，type-challenges 题库与 @type-challenges/utils 工具链早已稳定，此时能独立写出 medium 级递归/模板字面量解法并配套 husky+CI 工程化属合格偏上的认真练习者水准。

### 2023-07-06 · wave-button　(功能7/代码6/技术6)
- **定位**：一个 React 组件库，把作者自研的 motion-wave canvas 波浪渲染器封装成带无障碍支持、随悬停/聚焦状态做波浪动画的「酷炫按钮」，已发布到 npm。　|　技术栈：TypeScript, React 18, Vite, SWC, Tailwind CSS, @react-aria/button, motion-wave(自研), canvas
- **亮点**：规范的双格式打包：swc 产出 mjs/cjs + tsc 单独产出 d.ts + tailwind CLI 单独产出 css，库工程化到位；用 @react-aria/button 接管无障碍属性，比手写 button 更专业；根据按钮宽高比动态推导波浪 frequency/amplitude/offset，并用 cubic-bezier 缓动驱动 offset 动画，有实际数学/动效设计；useIsomorphicLayoutEffect 处理 SSR、mergeRef 合并内外 ref，细节考虑到位；配套自研 motion-wave canvas 渲染库，跨包能力体现深度
- **短板**：applyEffect 中存在死逻辑/冗余判断：在已确定 isFocused 为 false 的 else-if 分支内又写 if(isFocused.current)（button.tsx:84），在 !isFocused 分支内重复判断 isHover（button.tsx:91），状态机可读性与正确性存疑；完全无测试、无 CI；整库零注释，复杂的状态切换缺乏说明；forwardRef 泛型用 unknown 而非 HTMLButtonElement，类型不够精确（button.tsx:24）；tailwind.config content 指向 src/style.scss 但实际文件是 style.css，配置与文件名不一致
- **证据**：src/button.tsx:46-69 calcInitialOffset 按 width/height 比值 clamp 出 frequency 再算 amplitude 和 initOffset，再 setConfig；src/button.tsx:72-100 applyEffect 嵌套条件存在 line84 在 isFocused==false 上下文内再判 isFocused、line91 在 !isFocused 内再判 isHover 的冗余/死分支；src/button.tsx:6-7 useIsomorphicLayoutEffect 处理 SSR；src/button.tsx:12-20 mergeRef 合并内部 btnRef 与外部 ref；package.json:33-41 build:mjs/cjs 用 swc、tsconfig.build.json emitDeclarationOnly 出类型、build:css 用 tailwind CLI，三路构建；package.json:43-46 依赖自研 motion-wave@0.0.5（同作者 zhangyu1818），button 通过 WaveHandler ref 调 resize/setConfig；tailwind.config.js:3 content 写 src/style.scss 但仓库实际为 src/style.css，配置不一致
- **年代背景**：2023年中 React18+Vite+SWC+Tailwind+react-aria 正是当时前端组件库的主流且较新潮的工具链，作者完整跟进并做了规范的 ESM/CJS 双发包，属于当年合格偏上的独立库作者水准；canvas 波浪动效本身是有创意的小项目而非纯模板。

### 2023-07-07 · dark-toggle　(功能7/代码7/技术6)
- **定位**：一个无主题闪烁、支持 light/dark/system 三态且能正确响应 prefers-color-scheme 的暗色主题切换库，提供 vanilla 与 React(Next.js) 两种用法。　|　技术栈：TypeScript, React, Vite, Playwright, Next.js(example), pnpm workspace
- **亮点**：核心反闪烁手法巧妙：用 createDarkToggle.toString() 把同一份逻辑序列化为内联 <script>，在 React hydration 前执行(client.tsx:32)，避免重复维护内联脚本；三态(light/dark/system)切换逻辑正确处理 prefers-color-scheme(index.ts:34-40)；Playwright 测试覆盖完整：181 行 4 个 describe 覆盖明暗系统默认值与运行时自动切换，CI 跨 chromium/firefox/webkit；库设计干净：双入口(vanilla / React) exports、emitDeclarationOnly 类型构建、闭包+订阅模式无外部状态依赖
- **短板**：darkQuery.onchange 直接赋值覆盖而非 addEventListener，且 e.matches 为 false 时未把 currentShouldDark 置回 false，存在细微状态追踪 bug(index.ts:69-79)；默认用 sessionStorage 持久化主题，跨会话即丢失，作为主题库的默认值欠妥；client.tsx 的 isServer 在模块加载时一次性计算，SSR/hydration 边界处理略显粗糙，可能引发水合不一致；Stars=0 体积小，属个人项目，文档示例(theme 注释处) 与 API 描述偶有不一致
- **证据**：lib/client.tsx:32 — `__html: const createDarkToggle=${createDarkToggle.toString()};window.darkToggle=createDarkToggle({key:"theme"})...` 将函数源码内联注入脚本，反闪烁关键技巧；lib/index.ts:34-40 — shouldDark() 用 (currentShouldDark && (storageTheme===null||'system')) || storageTheme==='dark' 正确判定三态；lib/index.ts:69-79 — darkQuery.onchange 赋值式监听，且仅在 e.matches 为真时设 currentShouldDark=true；tests/dark-toggle.spec.ts:1-181 — 4 个 describe 覆盖 light/dark 系统默认与 emulateMedia 运行时切换；package.json:21-30 — exports 提供 '.' 与 './react' 双入口，main 指向 dist/index.cjs；.github/workflows/playwright.yml — CI 安装浏览器并跑 playwright，上传 report
- **年代背景**：2023 年 prefers-color-scheme、matchMedia、Next.js App Router 与内联防闪烁脚本(next-themes 范式)均已成熟；作者用 Vite 库模式 + Playwright 跨浏览器测试 + pnpm workspace 搭建，属当年合格偏上的前端工程实践，因此给分以当年中上水准为锚。

### 2023-07-10 · tscb　(功能6/代码6/技术5)
- **定位**：一个轻量的 TypeScript 打包/编译辅助库，通过为每个目标合并 tsconfig 并多次调用 tsc，解决 tsc 无法一次同时输出 CJS 和 ESM 的问题。　|　技术栈：TypeScript, Node.js, tsc, arg, fs-extra, json-schema-to-typescript, husky, lint-staged, prettier, pnpm
- **亮点**：精准切中真实痛点：tsc 无法单次同产 CJS+ESM；用 schemastore 的 tsconfig schema 自动生成完整类型(interface.ts)，使用户配置全程有类型提示；提供 defineConfig 类型辅助、CLI(arg) 与编程 API 双入口，配置来源支持 tscb.config.js/.cjs/package.json；工程化到位：husky+lint-staged+prettier+tsc-files 预提交校验，已发布 npm v1.0.1
- **短板**：用 eval() 解析 tsconfig（tscb.ts:14），不安全且无法处理 JSONC 注释/尾逗号，应改用 jsonc-parser 或 ts.readConfigFile；package.json 的 exports 仅声明 require，与本库主打“双格式产物”理念自相矛盾；向 cwd 写入 .temp.json，并发/多配置时易冲突，应使用临时目录或唯一文件名；spawnSync 调用 tsc 后未检查退出码/status，构建失败也不会反映为非零退出
- **证据**：lib/tscb.ts:14 使用 eval(`tsconfig = ${fs.readFileSync(configPath,'utf-8')}`) 解析配置；lib/tscb.ts:31 spawnSync('tsc', ['--project', tempPath], {stdio:'inherit'}) 逐个目标 shell 调用 tsc；scripts/schema.js fetch http://json.schemastore.org/tsconfig 并 compile 生成 lib/interface.ts（958 行）；lib/cli.ts:13-19 用 arg 解析 --config/--project；26-53 依次从 tscb.config.js/.cjs/package.json 读取配置；package.json:43-47 exports 仅有 require 入口；lib/defineConfig.ts 提供 TscbConfig 类型与 defineConfig 辅助函数
- **年代背景**：2023 年中 TS 5.1 时代，tsc 单次无法同产 CJS/ESM 是公认痛点（tsup/unbuild 等已存在但更重），此工具走极简“薄包装 tsc”路线属合理且地道的当年方案，按当年标准评分而非以今日 moduleResolution:bundler/ts 多 build 模式苛责。

### 2023-10-14 · github-api-test　(功能1/代码1/技术1)
- **定位**：一个完全空的仓库，名为 github-api-test，无任何提交/文件，疑似为测试 GitHub API（如调用创建仓库接口）而生成的临时目标仓库。　|　技术栈：
- **短板**：仓库完全为空，无任何代码；无 commit、无 README、无依赖清单；created_at 与 pushed_at 相同，从未推送过内容
- **证据**：git clone 输出: 'You appear to have cloned an empty repository.'；git log: 'your current branch main does not have any commits yet'；GitHub API /repos: size=0, language=null, description=null；GitHub API /contents: 'This repository is empty.' (404)；created_at == pushed_at == 2023-10-14T09:00:26Z，说明仅创建未推送
- **年代背景**：2023 年的技术背景无从体现，因为仓库为空、无任何源码可衡量；仓库名暗示其为 GitHub API 调用测试的产物，本身不承载工程内容。

### 2023-10-30 · lambda-clash-sub　(功能5/代码4/技术3)
- **定位**：一个把 v2ray 订阅链接转换为 Clash Premium 配置 YAML 的个人自用 AWS Lambda 函数。　|　技术栈：JavaScript, Node.js, AWS Lambda, API Gateway, axios, yamljs
- **亮点**：目标聚焦明确，单文件完成 ss/vmess→clash 转换的核心闭环；复用 Loyalsoldier 成熟规则集，config.json 规则编排合理实用；用 reduce 重建 query string、deleteUndefined 清理字段等小技巧体现一定 JS 熟练度
- **短板**：几乎零错误处理：无 try/catch、不校验 link 前缀(linkToConfig 可返回 undefined)、无空订阅/解析失败兜底；vmess 字段映射不完整(network 仅取 net、缺 ws-opts/host/sni/grpc 等结构)，对实际订阅兼容性脆弱；node_modules 直接提交进仓库(633KB 体积主因)，package.json main 字段指向不存在的 index.mjs；无测试、无 CI、无部署脚本，纯手工压缩上传
- **证据**：index.cjs:5-38 linkToConfig 仅处理 ss/vmess，else 分支缺失，非法链接返回 undefined 后被 deleteUndefined 收下变成 {}；index.cjs:52-64 handler 直接 await axios.get 无任何 try/catch，pathParameters/queryStringParameters 也未做存在性判断；index.cjs:33-35 vmess 仅映射 tls/network/wsPath，遗漏 ws host/headers、sni、alpn 等，clash 侧易连接失败；package.json:5 main 为 index.mjs 但实际入口是 index.cjs，字段未对齐；README.md:4 要求手动'压缩所有文件包括 node_modules'上传，故 node_modules 被提交入库
- **年代背景**：2023 年用 Lambda+API Gateway 做个人订阅转换属常见玩法，axios 1.5/yamljs 也是当年合理选择；以当年个人脚本标准衡量，它完成了 demo 级目标但工程化(错误处理/测试/依赖管理)明显欠缺。

### 2023-11-06 · lighthouse-ci　(功能6/代码5/技术4)
- **定位**：一个单文件 Node.js 脚本，用 Lighthouse 对多国家/多 URL 在移动端和桌面端跑性能审计，按时间戳保存 HTML/JSON 报告并与上次结果对比生成分数差异汇总表。　|　技术栈：Node.js, ESM (.mjs), lighthouse 11, chrome-launcher, fs/promises
- **亮点**：目标聚焦清晰，确实能跑通可用；正确使用 ESM 与 fs/promises 异步 API；按国家/时间戳/设备分层组织输出，并自动做前后分数对比；支持命令行参数按国家筛选运行
- **短板**：getPreviousResult 依赖 mtime 排序取 stats[1] 作为上一次结果，假设脆弱；generateHTMLTable 直接拼接字符串无转义，存在轻微注入风险；package.json 仅声明 lighthouse，chrome-launcher 为隐式传递依赖；无测试、无真正的 CI 配置(名为 CI 实为本地脚本)；串行逐个 URL/设备执行，无并发或失败重试
- **证据**：README.md:3 自述由 ChatGPT 4 生成并多次修订，作者已测试可用；main.mjs:8-29 runLighthouse 用 chrome-launcher 启动 headless Chrome，按 device 选 throttling/screenEmulation；main.mjs:78-105 getPreviousResult 读取国家目录下所有时间戳目录按 mtime 降序排序取索引1作为上一次；main.mjs:107-122 generateHTMLTable 模板字符串拼接无 HTML 转义；main.mjs:124-202 main 遍历 country->url->[mobile,desktop] 串行执行并汇总差异，无差异时不生成 summary；package.json:14-16 仅声明 lighthouse ^11.3.0，缺少直接使用的 chrome-launcher
- **AI 参与**：high 置信；信号：README.md 第3行明确写明: 'This is a Lighthouse CI script generated and revised multiple times by ChatGPT 4', 代码注释中英文混杂且偏解释性 (如 main.mjs:28 'return the entire runnerResult object'、:39 '月份是从0开始的'), 函数粒度划分规整、命名冗长统一，典型 ChatGPT 风格的样板结构, 单次 initial commit 提交全部代码，无迭代历史
  - 把控评估：README 坦白由 ChatGPT 4 生成并多次修订，作者起到了需求定义、测试验证与产出对比报告等整合作用。代码整体连贯、可运行，作者对生成结果有基本把控（按国家筛选、前后对比、分层存储是有明确意图的定制），但属于轻量级胶水脚本，未见对 AI 产出的深度重构或非平凡的工程打磨（如错误处理、并发、依赖修正均较薄弱）。
- **年代背景**：2023-11 时 lighthouse 11 与 ChatGPT 4 均为当时主流，用 AI 生成此类一次性性能审计脚本完全符合当年实践，按当年标准这是一个合格的小工具脚本，不应苛求工程化。

### 2023-12-07 · alias-recovery　(功能5/代码5/技术5)
- **定位**：一个 CLI 工具，用 Babel AST 把源码 import 中的路径别名（如 @api、@components）还原为相对路径。　|　技术栈：Node.js, CommonJS, @babel/parser, @babel/traverse, @babel/generator, glob, normalize-path, prettier, pnpm
- **亮点**：选用 Babel AST 转换而非正则替换，方法正确；用 normalize-path 处理跨平台路径分隔符；覆盖相对路径为空时回退为 ./ 的边界；依赖选型合理、职责单一、发布为可安装 npm 包
- **短板**：仅处理 ImportDeclaration，遗漏 export...from / 动态 import() / require()；用 startsWith 做前缀匹配易误命中（@api 会匹配 @apiClient）；无任何错误处理，缺参/JSON 非法/解析失败均直接崩溃；generate 重写文件会丢失原有格式与注释，未用 recast/retainLines；无测试、无 CI，代码风格与自带 prettier 配置（semi:false）不一致
- **证据**：index.cjs:16-32 traverse 只注册 ImportDeclaration 访问器，未覆盖 ExportNamedDeclaration/import()/require；index.cjs:21 `value.startsWith(aliasPath)` 前缀匹配无边界校验；lib.cjs:10 `JSON.parse(fs.readFileSync(aliasJSONPath))` 无 try/catch，路径/JSON 出错即抛未捕获异常；index.cjs:34-35 `generate(ast,{})` 后 writeFileSync 覆盖原文件，丢失格式；index.cjs:6 `require('normalize-path');` 行尾分号与 prettier.config.mjs 的 semi:false 冲突，其余行又无分号
- **年代背景**：2023 年末 Babel AST 改写、glob、pnpm 都是成熟常规栈，此工具属当年一名合格前端工程师为自己痛点写的小巧实用脚本，方法对路但完成度与健壮性停留在合格线。

### 2023-12-28 · rsc-example　(功能7/代码6/技术7)
- **定位**：Next.js 14 App Router 电商样例，演示 React Server Components 数据获取 + Server Actions 购物车 + TanStack Query 服务端预取/水合的无限滚动模式（数据源为 mock.shop GraphQL）。　|　技术栈：TypeScript, Next.js 14 (App Router), React 18, React Server Components, Server Actions, TanStack Query v5, graphql-request, shadcn/ui + Radix UI, Tailwind CSS
- **亮点**：在 2023 年底就正确组合 RSC + Server Actions + useFormState/useFormStatus 这套刚发布的范式；RSC 端 prefetchInfiniteQuery + dehydrate/HydrationBoundary 与客户端 useInfiniteQuery + IntersectionObserver 的服务端预取/客户端续接无限滚动衔接得当；purchase variant 通过 URL searchParams 驱动、formAction.bind 传递负载等地道的 App Router 用法；自定义 useInheritedState/useDebounceFunc hooks 写法考究（用 ref 比对 props 派生 state，避免额外 effect）；严格 TS、shadcn/ui、清晰的 service/actions/components 分层
- **短板**：getCart 用手工 URL 编码的 GraphQL 字符串绕开缓存序列化问题，是 hack 且把正规实现整段注释保留；getProduct 把 handle 直接字符串插值进 query（未用 variables），存在注入风险且不一致；遗留无用导入 `import exp from 'node:constants'`、重复的 createRangeText（utils 与 product page 各一份）；README 仍是 create-next-app 默认模板，无项目说明；单次提交「存一下」无工程化历史；无测试、无 CI、无 lint 之外的校验
- **证据**：src/actions/index.ts:1 `'use server'` + addItem/updateItemQuantity 配合 cookies()/revalidateTag 实现购物车 Server Actions；src/components/add-to-cart.tsx:16 useFormState + formAction.bind(null, selectedVariantId)；src/components/submit-button.tsx:10 useFormStatus 驱动 pending 态；src/components/product-list.tsx:18 RSC 内 prefetchInfiniteQuery + dehydrate/HydrationBoundary；src/components/product-list-grid.tsx:37 IntersectionObserver 续接 fetchNextPage；src/service/index.ts:183 getCart 手工 URL 编码 GraphQL；index.ts:124 同名实现被整段注释；src/service/index.ts:63 getProduct 直接把 handle 插值进 gql 模板；src/service/interface.ts:1 `import exp from 'node:constants'` 无用导入；src/hooks/index.ts:4 useInheritedState 用 ref 比对派生 state；git log: 单一提交 d5d78a4 「存一下」
- **年代背景**：创建于 2023-12-28，正值 Next.js 14 / React Server Components / Server Actions 与 React canary 的 useFormState 刚落地阶段；在该时点就把这套尚不稳定的新范式跑通并辅以 TanStack Query 水合，属于紧跟前沿、偏资深个人开发者的探索性 demo，故按当年标准技术分偏高，而样例性质决定了完成度/工程化（测试、README、提交历史）不必苛求。

### 2024-01-19 · tw-styled　(功能7/代码8/技术7)
- **定位**：一个用 Proxy + 标签模板字面量语法快速创建带 Tailwind CSS 样式的 React 组件的小型库（styled-components 风格的 tw.div`...`）。　|　技术栈：TypeScript, React, tailwind-merge, Jest, @swc/jest, ESLint, Prettier, GitHub Actions
- **亮点**：Proxy 统一 tw.div`` 与 tw(Comp)`` 两种用法，模式巧妙；merge 函数依赖注入 + tailwind-merge 设为 optionalDependency，设计有品味；正确 forwardRef、智能 displayName、同时支持标签模板与字符串调用；已发布到 npm(v3)，含 Jest 测试与 Codecov 覆盖率 CI
- **短板**：TwFunction 返回类型与 Styled 交叉，类型设计略不严谨，内部多处 any；<Component ref={ref} {...props}> 顺序使 props 中的 ref 可能覆盖转发的 ref；MergeFunction 类型为 (...args:any[])=>string，过于宽松；仓库内无构建配置(tsup/rollup)，dist 产物的构建步骤缺失/未说明；CI 用 actions/checkout@v2 且 npm install，略陈旧
- **证据**：src/styled.tsx:26-30 new Proxy(withTw,{get(_,Tag){return withTw(Tag)}}) 统一两种创建方式；src/styled.tsx:33-42 React.forwardRef 包裹并 className={mergeFunction(className, props.className)}；src/styled.tsx:44 displayName = `tw-${Component.displayName||Component.name||Component}`；src/index.ts:5 const tw = create(twMerge)；package.json:26-28 tailwind-merge 为 optionalDependencies；package.json:16-19 暴露 ./create 子路径以注入自定义 merge；src/test.tsx 覆盖标签、合并、ref 转发、props 透传、displayName、自定义 merge 共 8 个用例；src/styled.tsx:5 type Styles = TemplateStringsArray | string 同时支持模板与字符串
- **年代背景**：2024 年初 React 18 + ESM + tailwind-merge 生态成熟，用 Proxy + forwardRef 做轻量 styled 抽象是当年地道且有水准的做法，按当年标准评判其简洁度与设计取舍。

### 2024-01-26 · rsc-mdx　(功能6/代码7/技术6)
- **定位**：一个极简的 React Server Components 用 MDX 渲染库，对 @mdx-js/mdx 的 evaluate 做薄封装，支持自定义组件与 remark/rehype 插件。　|　技术栈：TypeScript, React Server Components, @mdx-js/mdx, Next.js 14, pnpm workspace, Playwright, Tailwind
- **亮点**：核心抓住 RSC 渲染 MDX 的痛点：用 evaluate + react/jsx-runtime 在服务端异步渲染；类型设计地道：通过 Omit 剔除 runtime 相关字段、用 Parameters<typeof evaluate>[0] 复用上游类型；库本体极致精简(20 行)，职责单一，作为发布到 npm 的可用库；monorepo 结构清晰：库 + Next.js 演示站点分离，tsconfig 分层
- **短板**：测试是 create-next-app/Playwright 的原始样板(仍指向 playwright.dev)，对库本身零覆盖；web 目录基本是默认脚手架(layout 仍写 Create Next App)，演示价值有限；无错误处理/边界(evaluate 抛错直接冒泡，未做封装)；README 偏营销话术，功能本身较 trivial
- **证据**：index.tsx:5-11 用 Omit<EvaluateOptions,'Fragment'|'jsx'|'jsxDEV'|'jsxs'|'development'> 精确收窄对外 props 类型；index.tsx:12-20 async function MDX 调 evaluate(source,{...rest,...runtime}) 并返回 <MDXContent />，是正确的 RSC 写法；package.json:23-25 仅依赖 @mdx-js/mdx ^3.0.0，devDeps 只有 types/prettier/typescript，确为轻量库；web/tests/mdx.spec.ts:3-20 测试内容是 playwright 官方样板(goto playwright.dev)，未测 MDX；web/app/layout.tsx:10-13 metadata 仍为 'Create Next App'/'Generated by create next app'，演示站为未改的脚手架；git log 仅 'chore: update package.json' 一条(浅克隆，但仓库提交历史极短)
- **年代背景**：2024-01 时 RSC + MDX 3.0 刚成熟，evaluate 在服务端渲染 MDX 的薄封装是当时有实际价值且较新颖的小众方案，按当年标准这是一个干净、定位准确的实用小库，故功能/技术中上而非低分。

### 2024-02-06 · remark-code-groups　(功能6/代码6/技术6)
- **定位**：一个 remark 插件，把 :::code-group 容器指令转换为 CSS-only 单选标签页式的多代码块分组 HTML。　|　技术栈：TypeScript, unified/remark, unist-util-visit, remark-directive (containerDirective), nanoid
- **亮点**：正确理解并使用 unified/mdast 的 containerDirective + hName/hProperties 机制完成 mdast→hast 交接；用 nanoid 为每组生成唯一 radio name，巧妙避开多组 tab 冲突，实现纯 CSS 切换；暴露可配置的 options (prefix/tag/className) 且类型为 Plugin<[Options]>，API 设计有库的意识
- **短板**：全程 node: any，未用 mdast/remark-directive 的真实类型；child.meta.match(...) 无空值/不匹配保护，遇异常输入会抛错；无任何测试与 CI；README 仅有标题一行，无用法说明；缺少 package.json exports 字段与 ESM/CJS 双格式处理
- **证据**：index.ts:31 `const radioName = \`group-${nanoid(5)}\`` 为每组生成唯一 radio 名；index.ts:38 `const [, name] = child.meta.match(/\[(.+)]/)` 直接解构 match 结果，无 null 守卫；index.ts:48-50 `data.hName = tag; data.hProperties = { class: containerCls }` 正确使用 mdast 的 rehype 交接字段；index.ts:26 `visit(tree, (node: any) =>` 类型全部退化为 any；README.md 全文仅 `# remark-code-groups` 一行；package.json version 0.0.0-beta.2，files 只发布 index.js/index.d.ts
- **年代背景**：2024 年初 unified v11 / remark-directive 生态已成熟，用 containerDirective 做 code-group 是当年地道且小众的玩法，按当年标准这是一个完成度尚可但打磨不足的早期 beta 工具库。

### 2024-03-18 · react-server-only-context　(功能6/代码8/技术7)
- **定位**：一个微型 React 库，利用 React.cache() 在 React Server Components 中实现类 createContext 的按请求作用域状态共享，规避 RSC 不支持 context 的限制。　|　技术栈：TypeScript, React (canary), React Server Components, React.cache
- **亮点**：核心思路精巧：用 React.cache() 创建按请求记忆化的可变 ref 实现 RSC 上下文；README Pitfalls 章节深入剖析 RSC 异步遍历破坏 LIFO 栈模型，并引用官方 RFC，体现源码级理解；类型设计干净：用 InternalServerOnlyContext 隐藏 _currentValue 内部字段，对外暴露纯净的 ServerOnlyContext<T>；严格 tsconfig（strict/noUnused*）、prettier 配置、合理的 peerDependencies 与 files 字段
- **短板**：完全无测试；无 CI 配置；依赖 React canary 的 cache API，稳定性/适用范围有限；作者自己也在 README 承认无法复现真正的 context 栈语义，实用性受限于玩具/概念验证级；无构建脚本（package.json 无 build/scripts 字段）
- **证据**：src/index.ts:17 React.cache(() => ({ current: defaultValue })) —— 用 cache 做按请求记忆化是核心创新点；src/index.ts:22 Provider 通过 value().current = props.value 直接写入共享 ref，再返回 children；src/index.ts:12 InternalServerOnlyContext 扩展接口隐藏 _currentValue，对外 return context as ServerOnlyContext<T> 收窄类型；tsconfig.json:35 types: ["react/canary"] 表明依赖实验性 cache API；README.md:100-163 Pitfalls 详述异步组件遍历顺序变化并引用 reactjs/rfcs 0188 行号；package.json:19-21 peerDependencies react:* + files:[dist]，库发布配置规范；无 test/ 目录，git log 仅 1 个 commit 811a38c v1.0.0
- **年代背景**：2024-03 正值 RSC 与 React canary cache() 刚落地、社区缺乏官方 context 方案的窗口期，作者敏锐抓住痛点并用当年最前沿的 API 给出地道解法，按当年标准技术嗅觉与实现都属上乘。

### 2024-04-03 · use-flip　(功能6/代码7/技术6)
- **定位**：一个零依赖的 React Hook（useFlip），用 Web Animations API 实现 FLIP 动画，平滑过渡元素位置与尺寸变化。　|　技术栈：TypeScript, React Hooks, Web Animations API, tsc 构建, prettier
- **亮点**：零依赖、聚焦单一职责的微型库；正确实现 FLIP 技术与 useLayoutEffect 时序；地道使用 element.animate（WAAPI）而非手写 RAF；严格 tsconfig + 已发布到 npm，工程基线干净
- **短板**：仅支持单元素，无法处理列表/分组重排；ref 未绑定时仅 console.warn 而不抛错；大量非空断言(!) 与返回值 as any，类型不够严谨；无任何测试；peerDependencies react:'*' 过宽
- **证据**：src/index.ts:3-12 自实现 useUpdateEffect，用 isMount ref + useLayoutEffect 跳过首次挂载，模式正确；src/index.ts:42-47 计算 deltaX/deltaY 并 from={transform:translate(...)} -> to={translate(0,0)}，标准 FLIP Invert+Play；src/index.ts:53-62 dimensions 支持 'width'|'height'|true 分支处理宽高动画；src/index.ts:64-68 直接调用 ref.current.animate([from,to],{duration,easing,fill}) 使用 WAAPI；src/index.ts:73 return ref as React.MutableRefObject<any> 类型被弱化为 any；package.json:15 prepublishOnly: npx tsc，构建仅靠 tsc，无打包器；files 只发布 index.js/index.d.ts；tsconfig.json:11-14 strict/noUnusedLocals/noUnusedParameters 全开，类型基线严格
- **年代背景**：2024 年 element.animate(WAAPI) 已被各浏览器广泛支持，FLIP+WAAPI 是当时成熟且推荐的实现路径，用它替代手写 RAF 属于合理的当代选择，按 2024 标准属合格偏上的小工具库。

### 2024-04-14 · contentful-experiences-example　(功能7/代码7/技术6)
- **定位**：一个 Next.js 14 示例项目，演示如何用 Contentful Experiences SDK（可视化拖拽搭建页面）注册自定义 React 组件，并结合 shadcn/ui 与 mock.shop GraphQL 接口实现动态页面和电商产品模板页。　|　技术栈：TypeScript, Next.js 14 (Pages Router), React 18, @contentful/experiences-sdk-react, shadcn/ui, Radix UI, Tailwind CSS, graphql-request, next-themes
- **亮点**：registeredTokens.ts 用 resolveConfig 递归解析 Tailwind 主题色并桥接为 Contentful 设计令牌，是真正非平凡的集成思路；组件库按 product/header/footer/ui 领域清晰分目录，配 index.ts 桶导出，结构整洁；用 React Context + 自定义 hook（useProduct/useOldestProducts）做 provider 守卫，错误处理地道；ProductCTA 通过 router.query 是否含变体选项派生 disabled 状态，UX 细节用心；围绕 Contentful Experiences SDK 的 defineComponents 注册做了完整的变量/校验/内置样式配置
- **短板**：registeredComponents.ts 第331-350行 ProductImage 用同一 id 'product-image' 重复注册两次（复制粘贴遗留 bug）；registeredTokens.ts 第109行 transformed(['"horizontal", "vertical"']) 传入了一个带引号的畸形字符串而非两个独立值，是真实 bug；image-loader.ts 用 any 标注参数，未给出 loader 的精确类型；无任何测试、无 CI 配置；getProduct 用模板字符串直接拼接 handle 进 GraphQL 查询而非用 variables，虽然是 mock 接口但不是最佳实践
- **证据**：src/contentful/registeredTokens.ts:9-26 递归 resolveColor 把 Tailwind 颜色配置转成 Contentful 令牌；src/components/product/context.tsx:8-14 useProduct hook 带 provider 缺失守卫并抛错；src/components/product/cta.tsx:9-13 用 router.query 派生 disabled，剔除 handle 后判断是否选了变体；src/contentful/registeredComponents.ts:331-350 ProductImage 用相同 id 重复注册（bug）；src/contentful/registeredComponents.ts:109 validations.in 传入 '"horizontal", "vertical"' 单个畸形字符串（bug）；src/service/index.ts:41 GraphQL 查询用模板字符串拼接 handle 而非 variables；src/pages/[slug].tsx:37,53 手动 JSON.stringify 序列化 experience 再 createExperience 还原，符合 SDK 在 Pages Router 下的用法
- **年代背景**：2024-04 Contentful Experiences SDK 还是 1.x 早期产物、文档稀少，作者能在 Next.js Pages Router 下跑通组件注册、设计令牌桥接与可视化预览，属于紧跟新工具的合格集成示例，按当年标准不应苛责其缺测试/CI（典型 demo 仓库）。

### 2024-04-15 · react-markdown-toc　(功能8/代码8/技术7)
- **定位**：一个 React 库，从 Markdown 文本生成目录(TOC)，同时支持服务端组件(固定渲染)和客户端组件(完全自定义渲染 + 滚动高亮当前章节)。　|　技术栈：TypeScript, React 18, Next.js 14, mdast-util-from-markdown, mdast-util-toc, IntersectionObserver, lodash.throttle, Tailwind CSS, shadcn/ui
- **亮点**：解析与渲染解耦，复用成熟 mdast 生态而非重复造轮子；点分路径 key(如 1.2.1)+ startsWith 优雅处理嵌套激活态；IntersectionObserver+节流+scrollAlign(start/center/end)精确判定当前章节；client 用 render-props 全自定义、server 用固定渲染，双形态 API 设计清晰；已发布 npm(v1.4.0)，exports/types/peerDeps 配置规范，附 GitHub Pages 在线 demo
- **短板**：完全没有单元测试，对一个发布库而言是明显短板；server 组件依赖客户端 DOM 选择器(querySelectorAll h1[id]..)，对 heading id 的生成有隐式耦合(需调用方自行加 rehype-slug)；scrollAlign 在 server props 类型里有 ScrollAlign，但部分边界(无 id 命中时)静默不更新；默认 throttleTime=1000ms 偏大，README demo 自身用了 10/100，默认值实用性存疑
- **证据**：lib/from-markdown.ts:30-41 addKey 递归构造 `${prefix}.${index}` 点分路径并建立 url->key 映射；lib/components/client.tsx:10-26 findClosestElement 按视口中心距离选最近 heading；lib/components/client.tsx:50-71 setActiveKey 根据 scrollY 与文档高度/视口分三种情形计算 centerForEle；lib/components/client.tsx:195 active = currentKey.startsWith(activeKey) 实现祖先节点联动高亮；lib/components/client.tsx:73-90 IntersectionObserver(threshold 0.5)维护 inViewportElements 集合；lib/components/server.tsx:21-66 render 按 mdast 节点类型(list/listItem/paragraph/link)分派固定标签渲染；package.json:17-21 exports 暴露 ./ ./client ./server 三入口；version 1.4.0 已迭代多版；tsconfig.build.json 用独立 tsc 配置仅编译 lib，与 demo(Next.js)构建分离
- **年代背景**：2024-04 时 React 服务端组件刚成熟、unified/mdast 生态与 shadcn/ui 已是主流，作者同时驾驭 RSC 双形态、mdast AST 处理与 IntersectionObserver，属于当年中上的前端工程水准。

### 2024-05-06 · rehype-default-code-lang　(功能7/代码7/技术5)
- **定位**：一个 rehype/unified 插件，为没有指定语言的 <code> 标签自动添加默认语言 class，便于接入 Shiki 等高亮库。　|　技术栈：TypeScript, unified, rehype, hast, unist-util-visit, pnpm, prettier
- **亮点**：针对 Shiki 迁移痛点的真实小众需求，定位精准；正确地道地使用 unist-util-visit 遍历 hast 树并用 @types/hast 类型化；对 parent/index/tagName/properties 做了完整的空值与类型守卫；已发布为带 MIT 协议的 npm 包，tsconfig 开启 strict 等严格选项
- **短板**：package.json 缺少 build/test 脚本，却声明 main 指向 dist，打包链路不完整；README Usage 不完整，只给出 import，未演示如何传 defaultLang 或挂载到 unified 管线；defaultLang 为可选却被无条件使用，缺省时会产出 language-undefined；完全没有测试；只处理 pre>code 首子节点，未覆盖独立 code 等边界场景
- **证据**：src/index.ts:9 export const rehypeDefaultCodeLang: Plugin<[Options], Root> 使用 unified Plugin 泛型，类型签名地道；src/index.ts:12-26 visit(tree,'element',...) 对 parent/index/node.tagName==='pre' 及 head.type/tagName/properties 做了层层守卫；src/index.ts:33 head.properties.className = [`language-${defaultLang}`]，defaultLang 未传时为 undefined；package.json:14 main 指向 ./dist/index.js 但全文无 scripts，无 build 命令；README.md:19-23 Usage 仅有一行 import，未展示参数与管线用法；git log 仅 d9d15b9 v1.0.0 一次提交
- **年代背景**：2024-05 时 unified 11 / rehype / Shiki 已成熟，无语言代码块不被高亮是当时常见痛点，作者用当年标准工具链做出一个定位精准但范围极小的工具库，体量决定了评分上限。

### 2024-05-21 · three-study　(功能5/代码6/技术5)
- **定位**：跟随 Three.js Journey（Bruno Simon）课程的学习练习仓库，单文件逐课实现 Three.js 各知识点（相机、材质、灯光、阴影、粒子、加载模型、Raycaster、环境贴图等）。　|　技术栈：TypeScript, Three.js 0.164, Vite 5, Bun, Tweakpane 4, Tailwind CSS, WebGL/GLSL
- **亮点**：2024 主流工具链（Vite5/TS5 strict/Bun/Tweakpane4）；实现动态 CubeCamera+CubeRenderTarget 实时反射与 layer 选择性渲染；正确处理 resize、pixelRatio 钳制、damping、colorSpace；提交历史按课程编号清晰记录学习进度
- **短板**：本质为教程逐课临摹，非原创设计；单文件覆盖式，历史课程内容不可同时访问；无 README/测试/CI；fpsGraph 用 // @ts-expect-error 绕过类型，大量注释掉的替代写法
- **证据**：src/main.ts: 单一入口文件，仅保留最后一课(第24课 Environment map)状态；commit history: 'initial'→'第3课'→...→'第24课：Environment map' 逐课提交；public/models/FlightHelmet、environmentMaps、blockadesLabsSkybox 均为 Three.js Journey 课程标准素材；src/main.ts: const cubeCamera = new THREE.CubeCamera(0.1, 100, cubeRenderTarget); cubeCamera.layers.set(1); scene.environment = cubeRenderTarget.texture —— 实时反射；src/main.ts: '// @ts-expect-error' 两处绕过 fpsGraph 类型；大段被注释的 CubeTexture/HDR 替代实现；tsconfig.json: strict + noUnusedLocals + noUnusedParameters 严格配置；package.json: name 'threejs-study', private true, 依赖 three ^0.164.1 / tweakpane ^4.0.3
- **年代背景**：2024-05 时 Three.js r164、Vite5、Bun、Tweakpane4 均为当时主流；以学习仓库标准看属合格的课程跟练，无 AI 痕迹（pre-AI 时代且符合人工逐课提交节奏）。

### 2024-05-27 · three-falling-cubes　(功能7/代码7/技术6)
- **定位**：一个 Three.js 入门 demo：方块/球体从空中连续掉落并堆叠，物理由 Rapier3D 在 Web Worker 中模拟，主线程仅负责渲染。　|　技术栈：TypeScript, Three.js, Rapier3D (rapier3d-compat), Web Worker, Vite, Tweakpane, Tailwind CSS, Bun, GitHub Pages/Actions
- **亮点**：物理计算放进 Web Worker，与渲染线程解耦，架构清晰；用打包的 Float32Array(每体8浮点:id+pos+quat)并以 transferable buffer 零拷贝传输，性能意识到位；完善的 Tweakpane 调试面板(flow/force/shape/阴影贴图大小/FPS 图/阴影相机 helper)；睡眠或 y<-50 的刚体自动回收 + 1s 批量 dirty-check 通知主线程移除 mesh，生命周期管理得当；类型化的 postMessage 协议配 discriminated-union 类型守卫
- **短板**：仅一个 demo,无测试、无错误处理边界；worker 从 skypack CDN 直接 import Rapier 而非 npm 依赖,较脆弱且与 lockfile 不一致；interface.ts 的 WorkerMessageType 联合漏掉(仅 init|step|add,缺 remove/sync 在主侧另立)且 StepData 为空接口；step() 中睡眠体的 id 被 add 进 needRemoveIds 两次(removeBody 内一次+随后一次,靠 Set 兜底)；几处 @ts-ignore/@ts-expect-error 绕过类型,严格模式下未真正解决
- **证据**：src/worker.ts:9 `import RAPIER from 'https://cdn.skypack.dev/@dimforge/rapier3d-compat'` 物理引擎走 CDN；src/worker.ts:85-122 打包 Float32Array(len*8) 并 self.postMessage(...,[data.buffer]) 零拷贝转移；src/worker.ts:91-95 `if (position.y < -50 || body.isSleeping())` 回收刚体；src/main.ts:186-215 syncMesh 按 8 字节步长解包 position/quaternion 并 copy 到对应 mesh；src/main.ts:136-143 isSyncData/isRemoveData/isLoadedData 类型守卫驱动 worker 消息分发；vite.config.ts:5-7 worker.format:'es' + base 路径配置用于 GitHub Pages；src/main.ts:267-287 setInterval 极坐标随机分布生成下落点(r*sqrt(random) 均匀分布)
- **年代背景**：2024-05 时 Three.js + Rapier(WASM) + Web Worker 的组合已是前沿但成熟的方案,作者作为'第一个 Three.js demo'就能把物理放进 Worker 并做 transferable 优化,放在当年标准里属于明显高于入门平均水准的实现。

### 2024-05-31 · wasm-vs-js　(功能5/代码5/技术5)
- **定位**：一个对比 Rust(WASM) 与 JavaScript(mathjs) 在矩阵乘法/转置、向量点积、FFT、斐波那契等数值算法上性能的浏览器基准 demo。　|　技术栈：Rust, wasm-bindgen, nalgebra, rustfft, WebAssembly, JavaScript(ESM), mathjs, HTML
- **亮点**：选题清晰，端到端打通 Rust->wasm-bindgen->浏览器 importmap 调用链；正确使用 nalgebra/rustfft 封装算法并经 #[wasm_bindgen] 导出，Float64Array 与 &[f64] 的边界传参处理得当；Cargo release profile 调了 opt-level=2 + lto="fat"，显示对 WASM 体积/性能优化有意识；README 诚实标注测试方法的不确定性，不过度宣称
- **短板**：基准方法不严谨：单次计时、无预热/无多轮取均值，performance.now 噪声大；对比不公平：FFT 用 mathjs vs rustfft 算法不可比，斐波那契双方都用 O(2^n) 朴素递归刻意放大差距；结论先行(README 目标即'证明 WASM 远胜 JS')，存在确认偏误；pkg/ 只提交了 index.html，生成的 wasm_benchmark.js/.wasm 未入库，仓库无法独立复现/部署；无构建脚本/CI/测试，UI 用 innerHTML 拼字符串、全局变量取 DOM，工程化程度低
- **证据**：src/lib.rs:39-45 rs_fibonacci 采用朴素递归 O(2^n)，与 index.html:35-38 的 JS fibonacci 同为指数递归，是刻意构造的对 JS 不利的对比；src/lib.rs:6-11 rs_matrix_multiply 用 nalgebra DMatrix::from_row_slice 接收扁平 &[f64]，类型与 JS 侧 Float64Array 对接正确；pkg/index.html:17-24 用原生 importmap 把 'rs' 映射到 ./wasm_benchmark.js，但该文件与 .wasm 未提交，仓库内仅有 index.html(ls pkg/ 仅 1 文件)；pkg/index.html:88-103 计时仅 performance.now() 单次测量，无 warmup/无循环取均值；pkg/index.html:158-166 FFT 用 mathjs math.fft 对复数对 vs rustfft，README:19 自承不确定 radix，属不可比对比；Cargo.toml:14-16 [profile.release] opt-level=2, lto="fat"，crate-type=cdylib，配置合理；README.md:23 明确目标 'demonstrate that WebAssembly significantly outperforms JavaScript'，结论先行
- **年代背景**：2024 年中 Rust+wasm-bindgen 工具链与浏览器原生 importmap 已成熟，做这种 WASM-vs-JS 性能 demo 属常规个人探索；以当年标准衡量，技术栈选型合理但基准方法学的瑕疵也是当年业界常见问题，故给中位评分。

### 2024-06-10 · eslint-config　(功能8/代码8/技术6)
- **定位**：一个面向 ESLint 10 Flat Config 的可共享配置库，按依赖自动检测并以 preset 方式组合 React/Next/TS/Tailwind/Prettier 等规则集，对标 @antfu/eslint-config。　|　技术栈：TypeScript, ESLint 10 Flat Config, typescript-eslint, tsup, vitest, pnpm, eslint-plugin-perfectionist/unicorn/jsonc/better-tailwindcss 等
- **亮点**：按 preset 懒加载 dynamic import，结构清晰、模块边界干净；类型设计到位：PresetConfig<TOptions> 泛型 + parsePresetConfig 统一解析 boolean/对象两种形态；monorepo packages + 路径解析(resolvePath) + validatePackages 校验，非平凡定制；fixture 驱动的真实 ESLint 端到端测试(~1374 行 test)，含 valid/invalid 期望比对；eslint.config.ts 用 tsx/esm tsImport 直接吃自身源码做 dog-fooding
- **短板**：本质是规则映射/插件粘合，技术深度有限，无算法/底层创新；无 CI 配置(.github 缺失)，发布质量保障依赖本地；README/SKILL 文档体量远超代码，明显 AI 批量生成、信息冗余重复；react preset 用多处 @ts-expect-error 绕过插件类型，权宜处理
- **证据**：src/index.ts:61-223 defineConfig 按 preset 逐个 await import() 懒加载并组装 FlatESLintConfig[]；src/utils.ts:10-27 parsePresetConfig 统一处理 undefined/boolean/对象三态，返回 {enabled,options,rules}；src/configs/typescript.ts:18-27,164-192 resolvePath 处理绝对/相对/数组路径，packages 多包模式生成多份 main config；src/configs/perfectionist.ts:32-76 sort-imports 自定义 next/react/three/reactThree 分组，体现真实工程品味；tests/fixtures.test.ts:11-145 用真实 new ESLint() 跑 valid/invalid fixture 并按 .errors.json 校验 ruleId；setup-eslint/SKILL.md:1-4 frontmatter 表明这是 Claude Code skill；eslint.config.ts:1-3 tsImport('./src/index.ts') 自举加载源码；package.json:28-30,57 peerDeps eslint ^10、devDeps eslint ^10.0.3 等 2026 版本
- **AI 参与**：high 置信；信号：包内附带 setup-eslint/SKILL.md，是标准的 Claude Code Agent Skill 文件（frontmatter name/description + Workflow/Scope），属典型 AI-agent 时代产物, README 与 SKILL.md 内容几乎逐字重复，1200+ 行、带 emoji 章节标题、目录、表格、15 个编号示例、8 条 Troubleshooting，呈高度模板化/穷举式生成风格, 克隆到的 HEAD 为 2026-03-20 的单一 squash 提交 'chore: prepare 5.0.0 release'，依赖为 2026 时段版本（eslint ^10、@next 16、vitest ^4、@types/node ^25、pnpm 10.32）, 代码注释/eslint-disable 注释风格异常统一，措辞规整
  - 把控评估：AI 参与度高（含 Claude Skill 文件、AI 风格 README），但作者把控良好：核心 src/ 架构连贯，preset 懒加载、泛型类型系统、monorepo 路径解析与校验、dog-fooding 配置均体现清晰的人工设计与品味，并非无脑堆砌；不足在于文档明显是 AI 批量生成且与 SKILL.md 大量重复，体量与代码不成比例。整体属于‘人主导设计 + AI 辅助补全规则/文档’的良性整合。
- **年代背景**：仓库元信息标注创建于 2024-06-10，但克隆到的代码实为 2026-03 的 v5.0.0 状态（依赖 eslint ^10 / next 16 / vitest 4 均为 2026 时段，且含 Claude Skill 文件），故按 AI 时代(2026)标准衡量：Flat Config + typescript-eslint 已是成熟范式，这类共享配置库在当年属常规但工程化扎实的工具，技术深度天花板不高。

### 2024-07-14 · eng-learn　(功能6/代码8/技术7)
- **定位**：一个英语音频学习 Web 应用：上传 MP3 + SRT 字幕，边播放边滚动高亮当前字幕行，点击任意单词弹出有道词典释义。　|　技术栈：TypeScript, Next.js 14 (App Router), React 18, Tailwind CSS, react-aria-components, rc-virtual-list, srt-parser-2
- **亮点**：usePlayer 用 ref + getter/setter + startTransition 封装 audio 控制，区分 status 与 playStatus 并对 waiting 做 500ms 去抖；字幕定位用二分查找(findCurrentLineIndex)而非线性遍历；虚拟列表 + 自定义动画滚动，并用计时器区分用户滚动与程序滚动(isAnimateScrolling/isScrolling)；正则切词 word/non-word 实现逐词查词 popover；清晰的 context/services/components 分层与完整的 500 行有道响应类型定义
- **短板**：无任何测试、无 CI；README 仅一行，无使用/部署说明；依赖有道非官方接口 (jsonapi_s)，易失效且无错误兜底；Caption 渲染期直接读 window.innerHeight，SSR/响应式不友好；魔法数 84(itemHeight) 硬编码、字幕字号变化与行高不匹配
- **证据**：src/hooks/usePlayer.ts:62-67 forceUpdateRefValue 仅在值变化时触发更新，配合 startTransition；src/hooks/usePlayer.ts:127-131 waiting 事件 500ms 去抖避免闪烁；src/components/player/caption.tsx:35-54 二分查找当前字幕行；src/components/player/caption.tsx:135-147 通过 3s 计时器与 isAnimateScrolling 区分用户滚动；src/components/player/caption.tsx:183-208 splitLine 用正则拆分单词/非单词；src/services/dict.ts:1-31 'use server' action 调用有道 jsonapi_s 接口；src/services/response.ts 共 501 行手写有道接口 TS 类型；src/app/layout.tsx:10-13 metadata 仍是脚手架默认 'Create Next App'
- **年代背景**：2024-07 时 Next 14 App Router、Server Actions('use server')、react-aria-components 均为当时较前沿且地道的技术栈，作者熟练运用属于当年中上水平；此时 AI 辅助尚不普及，代码个性化痕迹明确为人工编写。

### 2024-08-19 · cloud-storage　(功能2/代码5/技术2)
- **定位**：一个用 v0 生成的 Next.js 前端脚手架，仅含登录页和找回密码页两个静态界面，并无任何真实的云存储/文件处理功能。　|　技术栈：Next.js 14 (App Router), React 18, TypeScript, Tailwind CSS, shadcn/ui, Radix UI
- **亮点**：技术栈选型现代且规范 (Next14 App Router + shadcn/ui + Tailwind)；代码格式整洁、TypeScript 类型完整、可正常构建运行；loading/disabled 等基础交互状态处理到位
- **短板**：名为 cloud-storage 却无任何存储/文件/后端功能，名实严重不符；fetch 指向不存在的 /api/v1 接口，sleep() 伪造延迟后无条件报错，纯属UI演示假数据；几乎全部为 v0/shadcn 生成的样板，作者原创贡献极少 (仅 sleep 工具函数与拼装两页)；README 描述与实际功能完全脱节，存在误导
- **证据**：src/components/login.tsx:3-7 文件头注释 'This code was generated by v0 by Vercel.'；src/components/login.tsx:117-131 onClick 中 await sleep() 后 fetch('/api/v1/login')，catch{} 吞掉错误后无条件 setShowError(true)；src/lib/utils.ts:8-11 sleep() 返回 500~1500ms 随机延迟，用于伪造网络请求耗时；find route.ts 无结果：项目中不存在任何 API 路由/后端实现；src/app/page.tsx 整个应用入口仅渲染 <Login/>，全站仅 login 与 forgot-password 两页；README.md:3-10 宣称 scalable secure cloud storage / File Handling / User Management，与代码实际能力不符
- **AI 参与**：high 置信；信号：login.tsx 与 forgot-password.tsx 文件头均明确标注 'This code was generated by v0 by Vercel.' 并附 v0.dev 模板链接, components/ui 下为标准 shadcn/ui 模板代码（button/card/input 等 cva 样板，与官方一字不差）, README 为典型 AI 生成的营销式文案，宣称 SSR/用户管理/文件处理等功能，与实际仅两页登录UI严重不符, 单次提交 (commit count = 1)，无迭代痕迹
  - 把控评估：组件由 v0 生成、UI 套用 shadcn 模板，作者的整合工作非常轻量：仅手动拼装两页、加 useState 与一个 sleep 假请求。模块边界清晰但内容空洞，缺乏非平凡的人工定制，整体属于低把控、低投入的生成物拼装。
- **年代背景**：2024-08 时 Next14 App Router、shadcn/ui 与 v0 生成代码已是前端主流工作流，因此该脚手架的技术栈在当年很普通，且明显依赖 v0 自动生成，不能体现作者自身技术深度。

### 2024-10-05 · my-desktop-in-3d　(功能1/代码1/技术1)
- **定位**：一个名为「我的桌面3D化」的占位仓库，从未提交过任何内容，无法判断其真实意图。　|　技术栈：
- **短板**：完全空仓，无任何提交；无 README/依赖清单/源码；创建后从未推送内容
- **证据**：git ls-remote 返回空，无任何分支或 commit 引用；clone 后仅有空 .git 目录，warning: You appear to have cloned an empty repository；GitHub API: size:0, language:null, branches:[]；GitHub API commits 端点返回 HTTP 409 'Git Repository is empty.'；created_at/updated_at/pushed_at 均为 2024-10-05T04:44:00Z，创建后从未推送
- **年代背景**：2024-10-05 创建的空仓库，从未推送任何内容；无源码可评，仅能给出最低分。

### 2024-10-05 · r3f-docs-cursor　(功能2/代码3/技术2)
- **定位**：把 react-three-fiber 官方文档原样塞进一个空白 Astro minimal 脚手架，index 页面用 glob 列出所有 md 链接，疑似为给 Cursor 喂文档做的一次性实验。　|　技术栈：Astro 4, TypeScript, Markdown/MDX, pnpm, Vercel
- **亮点**：index.astro 用 Astro.glob 自动收集 md 生成导航，写法地道；依赖与 lockfile 干净，最小化无冗余；文档内容本身是高质量的官方 r3f 文档
- **短板**：README 是 Astro 官方模板原文未改；astro.config.mjs 为空，未接 MDX 集成，文档里的 <Intro>/<Sandpack> 根本无法正确渲染；19 个 md 全是 pmndrs/react-three-fiber 官方文档原样拷贝，无原创；无样式/布局/组件/测试/CI，单次提交 'add docs' 即弃；本质是文档转储实验，几乎无工程内容
- **证据**：README.md:1 '# Astro Starter Kit: Minimal'，整篇为 Astro 模板默认 README；astro.config.mjs:4 'export default defineConfig({});' 空配置，未注册 MDX，而 introduction.md:7 使用 <Intro>、:33 使用 <Sandpack> MDX 组件；src/pages/index.astro:2 Astro.glob('../pages/**/*.{md,mdx}') 列链接，全部原创代码仅此 24 行；introduction.md 含 'nav: 0' 等 frontmatter 与官方 r3f docs 完全一致，hooks.md/canvas.md 等 19 文件均为官方文档原文；git log 仅一条 'dec18ea | ZHANGYU | 2024-10-05 | add docs'；package.json 仅 astro+sharp 两个依赖，无任何额外集成
- **年代背景**：2024 年 Astro 4 是主流静态站点框架，搭建文档站属常规操作；但本仓库并未真正搭站，只是把官方文档原样堆入空脚手架，按当年标准也属于 trivial 的一次性实验。

### 2024-10-05 · three.js-docs-cursor　(功能4/代码5/技术2)
- **定位**：把 three.js 官方 API 文档 HTML 整包搬运下来，配一个自写脚本生成目录索引，方便喂给 Cursor 的 @Docs 做 AI 编码辅助　|　技术栈：HTML, Node.js, three.js docs template
- **亮点**：目录结构与 three.js 源码 api/ 树完全对齐，搬运完整(217 个 html)；generate_index.js 用递归正确生成多层级目录索引，按层级输出 h2/h3/h4；用途明确：解决 Cursor @Docs 索引 three.js 文档的实际需求
- **短板**：核心内容是上游 three.js 文档逐字拷贝，原创成分极少；HTML 里 [page:]/[param:]/[link:] 模板未渲染(Vector3.html 含 105 处原始模板)，浏览器直接看是生肉；无 package.json/CI/README 说明用法，README 仅 3 行；index.html 由脚本生成却也提交进仓库，且无样式/无搜索/链接指向未渲染页面
- **证据**：README.md 全文仅 'three.js docs cursor / three.js for cursor docs.'；generate_index.js:9-59 手写递归 generateHtmlContent，按 level 生成 h2..h4 与 <a> 链接；api/objects/Mesh.html:7 '[page:Object3D] &rarr;'、:101 '[link:https://github.com/mrdoob/three.js/...]' 证明为上游模板原文；grep 统计 Vector3.html 含 105 处未处理的 [page: 模板；api/geometries/BoxGeometry.html:6 残留 '<script src="page.js"></script>' 但仓库无 page.js，文档无法渲染；git log 仅 1 次提交 '3ae2577 api pages'，作者 ZHANGYU，2024-10-05
- **年代背景**：2024 年 Cursor 的 @Docs 索引功能正流行，开发者把 three.js 文档打包托管以供 AI 编码引用是合理的工程权宜，但搬运行为本身技术含量很低，按当年标准也只是 trivial 脚本+资源拷贝。

### 2024-11-05 · pr-finder　(功能7/代码7/技术5)
- **定位**：一个 Rust 编写的 CLI 工具，通过 GitHub GraphQL Search API 按作者/状态/日期范围查询某仓库的 PR 并按天/周/月分组打印，方便做工作汇报。　|　技术栈：Rust, clap, graphql_client, reqwest(blocking), chrono, colored, GitHub GraphQL API, GitHub Actions
- **亮点**：用 graphql_client 编译期类型安全代码生成，vendor 完整 GitHub schema；release profile 调优(opt-level=z/lto/strip/panic=abort)，体积仅 2MB；三平台 GitHub Actions 自动构建发布；分页游标循环、按周对齐到周日的分组逻辑正确清晰；模块拆分合理(cli/filter/graphql/models/utils)
- **短板**：无任何测试，filter 拼接与日期分组逻辑无覆盖；create_client 中对 token 构造 HeaderValue 用 unwrap，恶意/非法 token 会 panic；status/group_by 用裸 String 而非 clap 枚举，非法值静默退化为默认；查询字符串靠 format! 拼接，未对 repo/author 做转义/校验；GraphQL 返回的 errors 字段未检查，鉴权失败时静默无结果
- **证据**：src/graphql.rs:22 HeaderValue::from_str(token).unwrap() 对非法 token 会 panic；src/cli.rs:24 group_by 为 String 默认 day，src/utils.rs:18 用 `"day" | _` 兜底，非法值静默回退；src/main.rs:43 仅取 .data，忽略 Response.errors，鉴权失败时走 No results found；Cargo.toml:14-19 release profile 全套体积优化 opt-level="z"/lto/strip/codegen-units=1；queries/search.graphql 用 inline fragment `... on PullRequest` 配合 graphql_client 编译期 codegen；README:7 记录 TS+Bun 编译产物>100MB、Rust 重写后降到 2MB 的真实动机
- **年代背景**：2024 年末 Rust CLI 生态(clap 4 / reqwest 0.12 / graphql_client 0.14)已成熟，这是一个用当年地道工具链做出的小而完整的实用工具，按当年标准属于合格偏上的个人工程。

### 2024-11-16 · create-context-factory　(功能5/代码6/技术4)
- **定位**：一个面向 TypeScript 的 React Context 工具库，通过工厂函数把 hook 组合自动包装成 [Provider, useSelector]，省去手写 Context 类型与 Provider 样板代码。　|　技术栈：TypeScript, React 18.3, Deno, JSR
- **亮点**：已发布到 JSR 的可用包，工程化配置规范；泛型用法地道（Parameters/ReturnType 推导，as const 元组）；零依赖、API 极简，工厂模式消除 Context 样板；Deno/JSR 现代发布链路完整（exports/publish include）
- **短板**：核心卖点失真：所谓 selective subscription 并无渲染 bailout，本质只是 useContext+selector，README 自承无法阻止重渲染；无任何测试与 CI，仅单条 v1.0.0 提交；默认 Context 用 {} as Context 类型欺骗，defaultValue 与 hook 调用语义混淆；FactoryReturnType 的 Effect 约束(unknown[])与函数实现(any[])不一致
- **证据**：mod.ts:49 `const context = React.createContext<Context>({} as Context)` 用空对象做默认值的类型断言；mod.ts:56-59 useContextSelector 仅 React.useContext(context) 后调用 selector，无 useSyncExternalStore/memo，无法阻断重渲染；README.md:60-61 作者自述 `this tool currently cannot prevent Context re-renders`，与 README.md:8 的 Selective subscription 卖点矛盾；mod.ts:42-46 泛型推导 `DefaultValue = Parameters<Effect>[0]`、`ReturnType<Effect>` 用法地道；deno.json 配置 exports/imports(react peer)/publish.include，发布配置规范；git log 仅 1 个提交 e6c2b90 v1.0.0
- **年代背景**：2024 年 React 生态早有 use-context-selector、Zustand、Jotai 等成熟方案，按当年标准这是一个实现正确但深度有限、且未兑现其重渲染优化卖点的小工具库。

### 2024-11-17 · speedtest-ui　(功能7/代码7/技术6)
- **定位**：一个基于 Ookla Speedtest CLI 的跨平台桌面网速测试 App，用 Tauri 2 + React 封装出带实时速率图表和暗色模式的精致 GUI。　|　技术栈：Tauri 2, Rust, React 18, TypeScript, Vite, TailwindCSS, ECharts, motion(framer-motion), Radix UI, pnpm
- **亮点**：Tauri sidecar 思路清晰：Rust 侧 spawn speedtest CLI、按行解析 --progress JSON 并通过 emit 流式推给前端；前端架构干净：自定义 hooks 分层（use-speedtest 事件订阅 / use-chart-data 图表 / use-throttle-state 节流），职责分明；工程化完整：自有 eslint-config、prettier、postinstall 脚本按平台下载 CLI 二进制、Tauri 多平台 release CI；细节处理到位：StrictMode 双挂载用 isCalled ref 防重、ECharts 用 ref 命令式高频更新避开 React 重渲染、上传图表 yAxis 复用下载峰值做对齐
- **短板**：Rust 侧 serde_json::from_str(...).unwrap() 与 emit(...).unwrap()，CLI 输出非预期格式即 panic，缺乏错误传播；lib.rs 残留 dbg!(binary_path) 调试宏未清理；无任何测试；run_speedtest 命令也无并发/重入保护；interface.ts 中 Download/Upload 的 timestamp 标为 number，与 Rust models.rs 的 String 不一致（类型对齐疏漏）；前端 listen 订阅与 invoke 启动耦合在同一 effect，rerun 仅重新 invoke 而不重置监听，依赖隐式假设
- **证据**：src-tauri/src/lib.rs:20 dbg!(binary_path) 调试宏残留；:50 serde_json::from_str(&content).unwrap() 解析失败即 panic；src-tauri/src/lib.rs:23-32 Command 以 --format=json --progress=yes --unit=B/s spawn CLI，:44-56 子线程逐行读 stdout 并 app.emit('speedtest', event) 流式推送；src/hooks/use-speedtest.ts:30-33 用 isCalled ref 规避 React18 StrictMode 双挂载重复 listen；src/hooks/use-chart-data.ts:33-43 upload 图表 yAxis.max 复用 downloadMaxValue 做两图纵轴对齐；scripts/bin.cjs:7-14,93-128 postinstall 按 os.platform 下载对应 ookla-speedtest-1.2.0 二进制并解压到 src-tauri/resources/bin；src/interface.ts:51 Download.timestamp:number 与 src-tauri/src/models.rs:16 timestamp:String 不一致；package.json:44 依赖自有 @zhangyu1818/eslint-config，:35 tw-styled、:26 dark-toggle、:20 JSR create-context-factory（个人生态）
- **年代背景**：2024-11 Tauri 2.0 刚于该年 10 月正式发布，作者迅速采用 v2 API（capabilities 权限模型、plugin-shell、sidecar 二进制），属当年前沿且地道的桌面技术栈选择，整体应按 2024 末的成熟前端+Tauri 工程标准衡量。

### 2024-11-20 · appicon-forge　(功能9/代码8/技术7)
- **定位**：纯前端 App 图标生成器：自定义颜色/渐变/边框/阴影/透视/文字/字体，集成 Iconify 20 万+图标，实时预览并导出 PNG。　|　技术栈：TypeScript, React 18, Vite 6 (SWC), TanStack Query/Virtual, Radix UI + shadcn 风格, Tailwind CSS, immer/use-immer, i18next, Iconify API, html-to-image, Docker
- **亮点**：icon-card+lib/utils 实现完整的渐变/盒阴影/drop-shadow/文字阴影/透视 CSS 渲染引擎，预览与列表按 scale 缩放统一；virtual-grid 用 useVirtualizer + ResizeObserver 动态计算列数虚拟化渲染海量图标；getVisibleIconsAsync 对大图标集分批 setTimeout(0) 让出主线程避免卡顿；detectFontAvailability 通过 DOM 测量检测本地字体、动态注入 Google Fonts link；工程化齐全：CI(typecheck+lint)、husky 预提交、Docker/compose、i18n 双语、localStorage 防抖持久化
- **短板**：完全无测试；import-and-export 直接 JSON.parse 用户输入且无 try/catch 与 schema 校验，错误输入会抛异常；上传 SVG 用 dangerouslySetInnerHTML 注入，纯客户端虽风险低但存在 XSS 面；README 有拼写错误(如 Renive、out vs dist 目录不一致)
- **证据**：src/components/icon-card/index.tsx:91-103 对 shadows/insetShadows/iconShadow/textShadow 分别经 scaleShadow 后生成各类 CSS；src/lib/utils.ts:31-82 getVisibleIconsAsync 用 batchSize=1000 + await setTimeout(0) 分批处理并集/扣除 hidden/aliases；src/components/virtual-grid/index.tsx:27-56 ResizeObserver+throttle 动态 columnCount 配合 useVirtualizer 行虚拟化；src/lib/utils.ts:185-215 detectFontAvailability 通过对比 sans-serif/serif 基准尺寸判断字体是否可用；src/store/use-styles.ts:14-31 useImmer + debounce(1000) 写 localStorage，挂载时合并恢复配置；src/components/settings/import-and-export/index.tsx:35 setStyle(JSON.parse(showData)) 无校验/无 try-catch；src/components/preview-upload/index.tsx:53 dangerouslySetInnerHTML 注入上传的 SVG 文本
- **年代背景**：2024-11 时点该技术栈(React18+Vite6+TanStack+Radix/shadcn+immer)代表当年前沿且地道的前端工程实践，作者还自维护 eslint-config 与 JSR 包，按当年标准属资深个人开发者水准，故给高分而非用今日标准苛责其无测试。

### 2024-11-30 · r3f-100-exercises　(功能8/代码8/技术8)
- **定位**：一个 React Three Fiber 学习练习集，逐个实现 10 个交互式 3D/着色器 demo（漂浮 MacBook、圆形轮播、3D 卡片、Raging Sea、GPU 流体模拟等），已部署到 Vercel。　|　技术栈：TypeScript, React 19, Next.js 16 (App Router/static export), @react-three/fiber 9 / drei, Three.js 0.184 (WebGPU + TSL), GLSL/WGSL shaders, @react-three/rapier 物理, react-spring / gsap, vitest 测试, oxlint/oxfmt + MDX/Shiki
- **亮点**：exercise 9 实现真正的 GPU Navier-Stokes 流体(涡量约束/压力迭代/advection)并同时移植 GLSL 与 TSL/WebGPU 双版本；material-tsl.ts 用 TSL 写出复杂位移/SDF 圆角/屏幕混合着色器，函数式分解清晰；工程化到位：vitest 单测、oxlint typeAware、React Compiler、静态导出、MDX+Shiki；资源生命周期管理严谨(dispose/bind/unbind、DoubleTarget ping-pong)；对参考来源诚实标注(codesandbox / threejs-journey 链接)
- **短板**：本质是练习/demo 集合，单一功能性产品价值有限(目标使然，非缺陷)；TSL 类型用 `type N = any` 全程绕过，牺牲类型安全；命名一致性偶有瑕疵(use-work-pane-pane、变量 binded)；测试覆盖仅触及材质创建的浅层断言，无渲染/数值正确性验证
- **证据**：package.json: next 16.2.4 / react 19.2.5 / typescript 6.0.3 / three 0.184 / @react-three/fiber 9.6.0 — 远超 2024-11-30；skills-lock.json: 11 个技能均 sourceType github，来自 cloudai-x/threejs-skills 与 dgreenheck/webgpu-claude-skill；src/app/(exercises)/9/fluid-core.ts: SourceFluid 类含 curl/vorticity/divergence/pressure 多 pass 与 pressureIterations 循环；src/app/(exercises)/9/material-tsl.ts: roundedBoxSdf/blendScreenColor/sampleFluidBilerp 等 TSL 函数组合；src/app/(exercises)/1/page.tsx: date="2024年11月30日" 证实项目起始时间；src/app/(exercises)/9/material.test.ts: vitest 对 NodeMaterial 与 8 个 fluid pass 的断言
- **AI 参与**：high 置信；信号：.claude/skills 与 .agents/skills 双份 Three.js 技能目录（Claude Code 工作流）, skills-lock.json 引用 cloudai-x/threejs-skills 与 dgreenheck/webgpu-claude-skill 外部技能, 依赖版本明显超前于创建日期(Next16/React19.2/TS6/fiber9/three0.184)，说明长期 AI 辅助维护至 2026, 代码风格异常统一：属性全部字母序排列、零业务注释、命名规整(oxlint 强制), oxlint.config 显式 ignore .claude/.agents 目录
  - 把控评估：作者对 AI 把控力强：模块边界清晰(fluid-core/fluid-utils/material-tsl/uniforms 分层)，GLSL 与 TSL 双实现体现主动技术选型而非堆砌，自配 oxlint-config、引入外部 Three.js 技能并锁定 hash、补单测，体现明确的人工品味与架构连贯性。
- **年代背景**：元信息标 2024-11-30 起始，但依赖与 .claude/.agents 技能目录证明项目持续维护进入 2026 AI 时代；按 2026 标准衡量，WebGPU/TSL 流体模拟仍属前沿且工程化扎实，是相当成熟的练习库。

### 2025-04-10 · openai-compatible-cosyvoice　(功能6/代码4/技术4)
- **定位**：一个基于 Flask 的适配层服务器，把阿里云 DashScope CosyVoice TTS 包装成兼容 OpenAI /v1/audio/speech 的接口，支持流式 MP3 输出。　|　技术栈：Python, Flask, dashscope, OpenAI SDK, conda/setuptools
- **亮点**：用队列+后台线程把 DashScope 回调式流式 API 转成 Flask 生成器流式响应，思路正确；覆盖了 /v1/audio/speech、/audio/speech 多路径与 OpenAI SDK base_url 调用约定；附带 health 检查、三套测试脚本和 run_tests.sh，工程意识在玩具项目里算齐全；依赖锁定到具体版本，提供 pip 与 conda 两种安装方式
- **短板**：回调里硬编码写 last_response.mp3 全局文件，并发请求会互相覆盖，无并发安全；setup.py entry_points 指向不存在的 run:main，console_scripts 实际不可用；catch-all /<path:path> 路由与具体路由职责重叠、逻辑冗余，路由组织混乱；speed 直接当作 speech_rate 透传，未做 OpenAI 与 DashScope 语义/区间映射；生产隐患：debug=True、绑定 0.0.0.0、API key 占位符回退，无鉴权/无错误码对齐 OpenAI
- **证据**：run.py:93 self.file = open('last_response.mp3','wb') —— 固定文件名，并发会冲突；run.py:54-62 通用 catch-all 路由与 64 行的 /v1/audio/speech 具体路由功能重复；run.py:82 speech_rate = speed —— 直接透传未做区间映射；run.py:200 app.run(debug=True, host='0.0.0.0', port=8081) —— 生产配置不当；setup.py:27 'aliyun-tts-server=run:main' 但 run.py 无 main 函数；setup.py:16 url='https://github.com/yourusername/...' 占位符未替换；requirements.txt: Flask==3.1.0/dashscope==1.23.0/openai==1.70.0 —— 2025 年合理版本
- **AI 参与**：medium 置信；信号：run.py 中文 print 日志风格高度统一、几乎每行加解释性注释（如『提前返回一小部分数据以确保响应开始』），符合 2025 年 AI 辅助生成的样板特征, 三个测试脚本结构高度同质、中文 docstring/注释风格一致，像批量生成, setup.py 作者写成 'Alibaba Cloud'、url 仍为 'yourusername/aliyun-tts-server' 占位符，且 entry_points 指向不存在的 run:main，典型未经人工核对的生成残留, sample_text 是一段风格突兀的英文『古典客服话术』，疑似 AI 生成的演示文本
  - 把控评估：项目疑似大量 AI 辅助生成。作者对 AI 产物的把控偏弱：核心流式转换思路连贯可用，说明有基本审阅，但 setup.py 占位符未改、entry_points 指向不存在函数、硬编码文件名导致并发冲突、路由冗余等生成残留都没被清理，缺少人工收尾与品味。
- **年代背景**：2025-04 时 OpenAI TTS 接口与各家国产 TTS 已成熟，做这种兼容适配层属于当时常见的『胶水工具』需求；放在该年标准下这是一个完成度尚可但工程打磨偏弱的小工具，按当年水平给中下分。

### 2025-04-12 · apple-docs-for-rag　(功能7/代码4/技术4)
- **定位**：把约300个Apple开发者框架文档站点抓取并转换为干净的Markdown语料库，供RAG/LLM检索使用——仓库本身只发布抓取产物，不含抓取器源码。　|　技术栈：Markdown, Web Scraping, HTML-to-Markdown, Git (per-framework automated commits), JSON (crawl checkpoint)
- **亮点**：覆盖面极广，约300个框架、5.3万篇md，规模可观；HTML→Markdown转换质量高：保留声明签名、availability、代码块(含语言提示)、Topics/See Also交叉引用；finished_links.json做断点续爬checkpoint，344次按框架分批commit体现工程化抓取流程；实用：直接可作为Apple文档RAG语料，已获45星8 fork
- **短板**：本质是数据转储，不含任何源码（抓取器未开源），无法评估真正的实现；无README说明/无使用文档/无许可证(README仅是种子URL列表)；GitHub语言识别为CoffeeScript实为linguist误判(无.coffee文件)；md文件名用空格+连字符拼接层级路径，可读性差且易冲突/截断；一次性抓取(2025-04全部commit集中在两天)，无更新机制，文档会迅速过期
- **证据**：git tree统计：52918个blob = 52852 .md + 65 .json + 1 .gitignore，零源码文件；README.md(20991字节)内容仅为~300条 https://developer.apple.com/documentation/* 种子URL的JSON数组，无任何说明；AGL/finished_links.json 为187条已抓取URL的扁平列表(crawl checkpoint)；SwiftUI/md/swiftui-state.md 正确保留 `@frozen @propertyWrapper struct State`、availability行、PlayButton代码清单与Overview正文；ARKit/md/arkit-anchor.md 完整保留 protocol声明、Topics、Relationships(Inherits/Conforming Types)、See Also；commits API：共344次commit，全部集中在2025-04-13，message即框架名(tvmljs/TVMLKit/OpenGLES...)，约每11秒一次=自动化分批提交；.gitignore 用 `*` + 逐框架 `!Dir/` `!Dir/md/*` 白名单，由脚本维护
- **年代背景**：2025-04正值RAG/LLM喂数据需求高涨、Apple文档无官方Markdown导出的时期，把开发者文档批量转成干净md确有现实价值；但以2025工程标准看，这只是抓取产物的发布，源码与文档缺位限制了对作者真实水平的评估。

### 2025-06-26 · ScreenCaptureKit.md　(功能4/代码3/技术2)
- **定位**：把 Apple 官方 ScreenCaptureKit 框架文档抓取并转换成 Markdown 文件集合，供 AI/deepwiki 检索使用　|　技术栈：Markdown, Apple Developer Docs (ScreenCaptureKit), deepwiki
- **亮点**：文档覆盖完整，几乎抓全 ScreenCaptureKit 全部类/枚举/协议；命名规范统一，便于按 API 检索；作为给 LLM 喂的离线文档语料有一定实用性
- **短板**：无任何原创内容，纯属官方文档搬运；代码示例围栏全空，关键 sample code 缺失；无 README/许可证/元信息，仅一次性提交；不涉及任何工程能力，无法据此评估编码水平
- **证据**：find . -type f -not -path './.git/*' 结果：249 个文件全部为 .md 扩展名，无 Package.swift/源码；git log -1：zhangyu1818 <hey@zhangyu.dev>，单提交 '3a545dc ScreenCaptureKit'，2025-06-26；screencapturekit-scstream.md:14-16 仅有签名 'class SCStream'，正文为官方文档原文；screencapturekit-capturing screen content in macos-macos.md:38-99 多处 ``` ``` 空代码块，sample code 被抓取器剥离；248/249 文件含被清空的 ``` source ``` 围栏（grep '^```$')
- **AI 参与**：high 置信；信号：整个仓库 249 个文件全为 .md，无任何源代码/构建文件，是 deepwiki 文档转储仓库（描述即指向 deepwiki.com/zhangyu1818/ScreenCaptureKit.md）, 文件命名严格机械化：screencapturekit-<class>-<member>.md，明显为自动抓取脚本生成, 内容是 Apple developer.apple.com 文档逐页镜像，含统一的 'Topics/See Also/Relationships' 样板结构, 代码块被抓取器剥离，248 个文件留下空的 ``` source ``` 围栏，是典型的爬取转换副产物, 单次提交 'ScreenCaptureKit'，无 README、无人工编辑痕迹
  - 把控评估：本仓库非作者编写的代码，而是自动化脚本抓取 Apple 文档生成的 Markdown 转储；不存在架构设计或人工定制，无法据此评估作者对 AI 的把控能力。把控/品味维度在此仓库不适用。
- **年代背景**：2025 年中 RAG/AI 编程助手兴起，把官方文档转为 Markdown 喂给 deepwiki/LLM 是常见做法，但本仓库本质仍是自动抓取的文档转储，不体现作者的工程或技术深度。

### 2025-07-02 · StoreKit.md　(功能4/代码3/技术2)
- **定位**：将 Apple 官方 StoreKit 开发者文档逐页抓取并转换为 1235 个扁平的 Markdown 文件的文档镜像仓库（供 LLM/deepwiki 等检索使用）。　|　技术栈：Markdown, Apple StoreKit 文档(抓取转换)
- **亮点**：覆盖完整：1235 页 StoreKit 文档全量镜像；文件命名以面包屑层级编码，可定位具体 API；保留了 API 签名(``` source 块)与平台可用性信息
- **短板**：无任何源代码、构建脚本或抓取工具，仅是产物转储；无 README/索引/导航，1235 个文件全平铺在根目录难以浏览；内容为 Apple 官方文档原文，无原创工程贡献；单次提交全量导入，无可见的生成/维护逻辑
- **证据**：find . -type f -not -path './.git/*' 显示 1235 个文件且全部为 .md，无任何代码/manifest/CI；git log 仅 1 个提交 4554870 'StoreKit' (zhangyu1818 <hey@zhangyu.dev>, 2025-07-02)，一次性导入全部文件；storekit-ad network attribution-attribution.md 内容为 Apple 文档面包屑+API Collection 描述的逐字转换；storekit-advancedcommerceproduct-init(id:).md 含 '``` source\ninit(id: AdvancedCommerceProduct.ID) async throws\n```' 及平台可用性，为文档原文；仓库描述指向 https://deepwiki.com/zhangyu1818/StoreKit.md，表明用途为 AI 文档检索；无 README（ls 确认 NO README）
- **年代背景**：2025 年中正值 RAG/LLM 喂料盛行，把官方文档抓成扁平 Markdown 喂给 deepwiki 等是常见做法，但这类仓库本身不体现工程能力，故按当年标准仍属低技术含量的文档转储。

### 2025-07-04 · AppStoreServerAPI.md　(功能3/代码2/技术2)
- **定位**：把 Apple 的 App Store Server API 官方开发者文档抓取/镜像成 213 个 Markdown 文件（每个 API 端点、数据类型、错误码、文章各一文件），疑似为 deepwiki 文档转储/喂给 AI 的知识库。　|　技术栈：Markdown
- **亮点**：覆盖完整：端点、数据类型、错误码、changelog 全量收录，作为离线参考语料较齐全；一文件一主题，便于检索/RAG 喂给 AI
- **短板**：零源代码，无 README/许可证/索引，纯文档转储；内容是 Apple 官方文档的搬运，几乎无作者原创工程产出；单次提交、无组织结构，文件名带空格不规范；镜像文档存在版权与时效性问题，无更新机制
- **证据**：find 结果：213 个文件全部为 .md，无 package.json/Package.swift 等任何依赖或代码文件；git log 仅 1 次提交：2395a8d zhangyu1818 2025-07-04 'AppStoreServerAPI'；app store server api-generating json web tokens for api requests-requests.md 为 Apple JWT 生成文档逐字镜像，含原站 See Also 区块；app store server api-jwstransactiondecodedpayload.md 完整复制 Apple 对象属性表与 Discussion/See Also，无任何作者注释；仓库描述字段即 deepwiki 链接，无 README、无 LICENSE、无主页
- **AI 参与**：medium 置信；信号：仓库描述直接指向 https://deepwiki.com/zhangyu1818/AppStoreServerAPI.md，是 AI 文档/wiki 工具, 仓库名以 .md 结尾，整库 213 个文件全部为 .md，无任何源码/配置，典型 doc-dump 形态, 文件名由页面标题机械 slug 化而成（如 app store server api-jwstransactiondecodedpayload.md），命名风格高度统一，像批量抓取脚本产出, 内容为 Apple 官方文档逐字镜像（保留 See Also/Mentioned in/Discussion 等原站结构），用途明显是作为 AI 检索/参考语料
  - 把控评估：该仓库基本不含人工工程定制：仅一次提交、机械化文件命名、内容为官方文档逐字镜像，未见索引/导航/裁剪/二次组织等人工把控痕迹，作者参与度仅限于运行抓取工具并提交，集成与品味体现极少。
- **年代背景**：2025 年中 deepwiki 等 AI 文档/wiki 工具已普及，把第三方文档抓成 .md 仓库作为 AI 知识库是当年常见做法；按此背景，这是一个低工程含量的文档转储产物，而非软件项目，因此各项工程评分天然偏低，但属正常用途，不应以软件标准苛责。

### 2025-07-04 · Swift.md　(功能4/代码3/技术3)
- **定位**：将 Apple 官方 Swift 标准库/语言文档批量抓取转换为 16214 个扁平 Markdown 文件的纯文档语料库，关联 deepwiki 用于 AI 检索/参考。　|　技术栈：Markdown, Swift (文档主题), （推测）文档抓取/转换脚本（未入库）
- **亮点**：覆盖面极广，16214 份 Swift 文档一次性归档；Markdown 转换基本干净，代码块/See Also 等结构保留
- **短板**：纯文档转储，无任何源码/脚本/构建配置；无 README、无索引/TOC，16214 文件全部平铺在根目录；文件名带不可读哈希后缀，难以人工检索；抓取/转换的工具链未入库，无法评估实际工程能力
- **证据**：find . -type f -not -path './.git/*' 全部 16214 个均为 .md，无任何其它扩展名；根目录无 README/package.json/CI，唯一子目录是 .git；git log 仅 1 个 commit 'Swift'（zhangyu1818, 2025-07-04），一次性提交全部文件；swift-!==(_:_:).md 内容为 Apple 官方 operator 文档（含 ```source 代码块与 'See Also'）；文件名如 swift-!=(_:_:)-18co7.md 带自动生成的哈希去重后缀
- **AI 参与**：medium 置信；信号：仓库描述直接指向 deepwiki.com（AI 文档/RAG 平台），本仓库即作为 AI 索引的喂料语料, 16214 个文件全部为机械转换的 Markdown，命名带哈希后缀（如 swift-!=(_:_:)-18co7.md），属典型自动化批处理产物, 单个 commit 'Swift' 一次性提交全部文件，无迭代历史
  - 把控评估：本仓库仅为文档转储产物，未包含抓取/转换脚本与任何架构性代码，无法评估作者对 AI 工具的把控与集成能力；组织方式（全平铺、哈希文件名、无索引）也较为粗放。
- **年代背景**：2025 年 deepwiki/RAG 兴起，把官方文档批量转 Markdown 喂给 AI 检索是常见做法；但本仓库只交付了产物语料而无任何抓取/转换代码，故仅能按文档转储而非工程项目评分。

### 2025-07-04 · SwiftUI.md　(功能4/代码2/技术2)
- **定位**：把苹果 SwiftUI 官方开发者文档逐个 API 符号抓取并转换成 Markdown 的文档转储仓库（5923 个 .md），用途疑似作为 LLM/RAG 的可消费参考语料。　|　技术栈：Markdown, Apple SwiftUI Documentation (source content), HTML-to-Markdown conversion (推测)
- **亮点**：覆盖面极广，几乎完整镜像 SwiftUI API 文档；命名规则一致（swiftui-<type>-<member>.md），便于按符号检索；内容本身（苹果原文）准确权威
- **短板**：无任何作者编写的代码/脚本/配置，转换器不在仓库内；无 README、无构建/CI、无说明，使用方式不明；存在 &lt; 等未清理的 HTML 实体转换残留，质量粗糙；内容为苹果文档直接搬运，原创工程价值极低；5923 个文件平铺在根目录，无任何分层组织
- **证据**：git log 仅一条 commit：32b250f "SwiftUI"，无迭代历史；find . -type d 仅返回根目录，5923 个文件全部为 .md 且平铺无子目录；无 README / Package.swift / package.json / 任何配置或 CI 文件；swiftui-accessibilitychildbehavior-combine.md 内容为苹果文档原文（含平台可用性 'iOS 13.0+iPadOS 13.0+...' 与 ``` source 代码块）；grep -l '&lt;' *.md 命中 1338 个文件，表明为未清理的 HTML→Markdown 自动转换产物；仓库描述字段即 https://deepwiki.com/zhangyu1818/SwiftUI.md
- **年代背景**：2025 年 SwiftUI 文档已成熟，把官方文档批量转成结构化 .md 喂给 LLM/RAG 是当年常见做法，但仓库本身只是搬运结果而非工程产物，按当年标准也只能算 trivial 的数据集托管。

### 2025-07-14 · xcode-i18n-mcp　(功能6/代码7/技术4)
- **定位**：一个 MCP 服务器，通过解析 .pbxproj 与 .xcstrings 文件，自动化 iOS/macOS 应用的本地化翻译工作流（提取支持语言、找出未翻译字符串、写回翻译）。　|　技术栈：TypeScript, Node.js, @modelcontextprotocol/sdk, Zod, Vitest, ESLint, pnpm
- **亮点**：结构清晰：纯函数与 MCP 工具注册分离，便于测试；完整 TS 类型 + Zod 输入校验 + 统一 try/catch 错误返回；239 行 Vitest 测试覆盖正常/异常/边界（保留已有本地化、忽略不存在 key）；严格 tsconfig、bin/npx 发布配置、可实际安装使用
- **短板**：updateTranslations 用标准 JSON.stringify 写回，破坏 Xcode 原生 .xcstrings 格式，造成全文件 diff；未翻译判定仅看语言 key 是否缺失，忽略 state:new/空值，覆盖不完整；extractKnownRegions 把 Base 当作语言返回（测试也固化了此行为）；领域逻辑较 trivial，单文件无更深抽象，无 CI
- **证据**：index.ts:259-262 updateTranslations 使用 JSON.stringify(updatedData, null, 2) 写回，非 Xcode 的 "key" : {} 缩进风格；index.ts:104-115 getUntranslatedStrings 仅以 localizations?.[languageCode] 是否存在判定未翻译；index.ts:62-86 extractKnownRegions 基于正则 /knownRegions\s*=\s*\(([\s\S]*?)\);/ 提取，test/index.test.ts:23 断言含 'Base'；README.md:268-311 'Code Generation: 100% of this code was generated by Claude' 与 'Generated with ❤️ by Claude Code'；package.json:26-37 依赖 @modelcontextprotocol/sdk ^1.15.1、zod、vitest，devDeps 含作者自有 @zhangyu1818/eslint-config；git log 单条提交 86b2994
- **AI 参与**：high 置信；信号：README 明确写明「100% of this code was generated by Claude (Anthropic's AI assistant)」, README 末尾「Generated with ❤️ by Claude Code」署名, README 列出开发期使用的 mcp__deepwiki__ 与 mcp__perplexity-ask__ 等工具及「Development Process」AI 叙事, 单条 squash 提交 'feat: implement xcode i18n MCP server with comprehensive functionality'，无迭代历史, 代码注释风格高度统一的 ==== Section ==== 分隔块，典型生成样板
  - 把控评估：作者对 AI 的把控不错：模块边界清晰（文件 IO / pbxproj 解析 / xcstrings 处理 / 工具注册分层），纯函数导出供测试、Zod schema 与错误处理一致、配套自有 eslint-config 与严格构建，体现工程品味；但属于让 AI 生成一个常规小工具并验收，未见对核心难点（如保留 .xcstrings 原生格式、更严谨的未翻译判定）的非平凡人工打磨。
- **年代背景**：2025年中 MCP 生态刚兴起，用 TS SDK + Zod 快速搭一个面向 Xcode 本地化的 stdio MCP server 是当年顺应趋势的合理实践，工程规范（严格 tsconfig、测试、lint、npx 发布）达到当年合格偏上水准，但领域逻辑本身不复杂。

### 2025-07-23 · CoreML.md　(功能4/代码3/技术2)
- **定位**：将 Apple 官方 Core ML 框架开发者文档整站抓取并转换为 732 个按 API 符号拆分的 Markdown 文件，作为 deepwiki / LLM 检索的文档语料。　|　技术栈：Markdown, Apple Developer Docs (Core ML / DocC), deepwiki
- **亮点**：覆盖完整：732 个文件几乎囊括 Core ML 全部 API 符号；命名规整：按 URL 路径 slug 化，可与官方文档结构一一对应；转换保真：保留了可用性徽章、代码块与 See Also 关系
- **短板**：内容为 Apple 官方文档逐字抓取，无任何原创/作者贡献；未包含抓取/转换脚本，无法评估其工程实现；无 README、无许可证说明，存在版权转载隐患；文件名含空格与中文引号等字符，跨平台/工具处理易出问题；无代码、无测试、无 CI，几乎没有可评估的工程产物
- **证据**：find 统计：732 个 .md 文件，0 个非 md 文件，无 README/package/config（仅 .git + 全部 .md）；git log 仅一条提交：fdf53ee 'CoreML' by zhangyu1818 <hey@zhangyu.dev> 2025-07-23；'core ml-integrating a core ml model into your app.md' 内容与 Apple 官方 'Integrating a Core ML Model into Your App' 示例逐字一致（MarsHabitatPricer 示例）；'core ml-mltensor-acosh().md' 仅含一句描述+函数签名+可用性徽章，典型 DocC 单符号页转储；文件命名为 'core ml-<symbol>-<subsymbol>.md' 的 URL slug 模式，机械统一
- **AI 参与**：medium 置信；信号：仓库描述直接指向 https://deepwiki.com/zhangyu1818/CoreML.md（deepwiki 为 AI 文档/RAG 工具）, 纯 .md 文档转储仓库，无任何源码，典型的喂给 LLM/RAG 的语料库形态, 732 个文件结构与命名风格高度机械统一（URL slug 化），明显为脚本/工具批量生成而非人工撰写, 单次提交 'CoreML' 一次性灌入全部文件
  - 把控评估：本仓库为文档语料转储而非人工编写代码；无架构/模块设计可言，作者贡献仅为运行抓取并提交结果，无法体现对 AI 或工程的把控能力。
- **年代背景**：2025 年抓取整站文档喂给 deepwiki/LLM 已是常见做法，本仓库本质是文档语料而非工程项目，因此即便按当年标准也只能从'语料完整度'而非'代码水平'维度给分。

### 2025-08-07 · ScreenCaptureRecorder　(功能4/代码6/技术5)
- **定位**：一个 macOS Swift 库，封装 ScreenCaptureKit 的内容选择器与录制流，用 AsyncThrowingStream 把录制状态/音频样本回传给调用方。　|　技术栈：Swift 5.9, Swift Package Manager, ScreenCaptureKit, AVFoundation, macOS 14+, Swift Concurrency (AsyncThrowingStream)
- **亮点**：地道使用 ScreenCaptureKit 的 SCContentSharingPicker/SCStream 现代 API；用 AsyncThrowingStream 暴露状态机，API 设计现代且符合 Swift Concurrency；细节到位：排除自身 bundleID、deinit 中移除 observer、CMSampleBuffer 有效性校验；良好的错误类型设计 (LocalizedError + 枚举)
- **短板**：功能不完整：仅 yield 音频样本并把视频帧丢弃（type==.audio 才回传），实际并不录制成文件；无 README/文档，调用方无从知晓如何用 buffer 落盘；无任何测试、无 CI；stateStreamContinuation 跨多个并发队列访问无同步，存在数据竞争隐患；startCapture 在 Task 中执行但错误未回传到状态流
- **证据**：Sources/ScreenCaptureRecorder/ScreenCaptureRecorder.swift:152-154 仅在 type==.audio 时 yield(.recording)，视频帧被静默丢弃，名为 Recorder 却不写文件；Sources/ScreenCaptureRecorder/ScreenCaptureRecorder.swift:118-119 excludedBundleIDs 排除自身，属经验性细节；Sources/ScreenCaptureRecorder/ScreenCaptureRecorder.swift:28 stateStreamContinuation 被 videoQueue/audioQueue/主线程多处访问且无锁保护；Sources/ScreenCaptureRecorder/ScreenCaptureRecorder.swift:137-140 startCapture 的 await 在独立 Task 中，抛错未被 catch 进状态流；Package.swift:9 platforms .macOS(.v14)，目标平台与 ScreenCaptureKit 选择器 API 匹配；仓库仅 1 次提交 (b7636d7, 2025-08-07)，无 README、无 Tests 目录、无 CI
- **年代背景**：2025 年 ScreenCaptureKit 的 SCContentSharingPicker 与 Swift Concurrency 已是 macOS 屏幕录制的主流方案，作者紧跟当年范式，但整体仍是未完成的早期脚手架。

### 2025-09-24 · tingwu　(功能7/代码7/技术8)
- **定位**：macOS 桌面应用（Tauri 2 + React 19），用 Rust 直接调用 ScreenCaptureKit 抓取系统音频，经 WebSocket 接入阿里云通义听悟做实时转写/翻译，并在 Lexical 编辑器里实时渲染字幕。　|　技术栈：Tauri 2, Rust, objc2 / ScreenCaptureKit FFI, tokio / tokio-tungstenite, React 19, TypeScript, Zustand 5, Dexie (IndexedDB), Lexical, Radix UI / Tailwind 4, WebCrypto
- **亮点**：objc2 裸 FFI 接 ScreenCaptureKit，define_class! 实现 Picker/Stream/Delegate 三套协议，非平凡系统级工作；用 Actor 模型+专用线程+mpsc 安全隔离非 Send 的 SCStream，并处理 f32→i16 PCM 转换；tokio select! 多路复用音频上行/消息下行，停流再关连接以规避竞态；前端用 WebCrypto 正确实现阿里云 ACS3-HMAC-SHA256 V3 请求签名；自定义 Lexical DecoratorNode 由流式 SentenceBegin/End 事件驱动实时字幕，类型守卫分发事件
- **短板**：Windows 实现是空壳，且 start 签名与 trait 不匹配（缺 pcm_callback），仅 macOS 可编译；测试几乎为零（仅 1 个 Rust 创建实例的 trivial 测试，前端无测试）；AK/Secret 在客户端浏览器侧做签名，凭据落在前端存储，安全上不理想；存在死代码/占位：CaptionNode.remove(){} 空实现、空 else 分支、未来命令注释占位；项目半途而废（README 自述 3 个月没做完、免费额度过期存档），整体未打磨完整
- **证据**：src-tauri/src/platform/macos.rs:186 define_class! 定义 ScreenCaptureRecorder 并实现 SCContentSharingPickerObserver/SCStreamOutput/SCStreamDelegate；src-tauri/src/platform/macos.rs:487-610 MacAudioCapture 用 mpsc + 专用线程的 Actor 模型管理 SCStream；src-tauri/src/core/audio.rs:171-220 extract_pcm_data 从 CMSampleBuffer 取指针并将 f32 clamp 转 i16 小端 PCM；src-tauri/src/core/speech_websocket.rs:264-332 tokio::select! 同时处理收消息与发 1024 字节音频分块；src/services/tingwu/tingwu-client.ts:17-101 createV3Authorization 用 WebCrypto 实现 ACS3-HMAC-SHA256 规范签名；src/components/lexical/caption-decorator-node.tsx:30 自定义 DecoratorNode<ReactElement> 含 clone/importJSON/exportJSON/getWritable；src-tauri/src/platform/windows.rs:19 WindowsAudioCapture::start 签名与 trait 不一致，为占位空实现；CLAUDE.md 与 .claude/agents/react-frontend-expert.md 显示 AI 辅助开发
- **AI 参与**：high 置信；信号：根目录 CLAUDE.md（Claude Code 项目指引）, .claude/agents/react-frontend-expert.md 自定义子代理，指明用 deepwiki/perplexity MCP, Rust 代码大量风格统一的双语 doc 注释，自夸式措辞如 'master-level architecture'、'following objc2 best practices', 中文 inline 注释成规律地标注 '优化/增强/修复竞态条件'，像 AI 迭代后的产物, 单个 'initial commit' 一次性提交全部代码，无渐进历史
  - 把控评估：AI 参与度高，但作者把控力强：架构连贯、前后端与平台模块边界清晰，最难的 objc2 FFI + 非 Send 对象的线程隔离、PCM 转换、V3 签名这些非平凡部分都正确落地，且为通义听悟这类细分服务做了大量针对性定制（错误码映射、事件类型守卫、字幕节点），不是无脑堆砌生成物。扣分主要在 Windows 空壳、测试缺失与项目未完成，而非 AI 滥用。
- **年代背景**：2025-09 时 React 19/Tailwind 4/Tauri 2/objc2 0.6 均为当年前沿，作者紧跟新栈并敢于啃 ScreenCaptureKit 裸 FFI，按当年标准技术深度明显高于普通水平。

### 2025-10-18 · gemini-storybook-downloader　(功能6/代码6/技术5)
- **定位**：用 Playwright 自动化浏览器，把 Gemini Storybook 网页里每一页的截图(PNG)和音频(OGG)抓取保存到本地的一次性脚本工具。　|　技术栈：TypeScript, Node.js, Playwright, tsx, pnpm
- **亮点**：针对 blob: + audio/ 的 response 监听抓取音频，思路对路；唯一一次 commit 即把固定 timeout 改为等待全部音频文件，体现了对竞态问题的真实思考；tsconfig 开启 strict、noUncheckedIndexedAccess、exactOptionalPropertyTypes 等较严格选项；代码命名清晰、函数职责单一，可读性好
- **短板**：saveAudio 的 audioPromise 无超时兜底，若音频数与页数不符会永久挂起(line 79-119)，与 README 宣称的 15 秒超时矛盾；captureScreenshots 用 page.waitForTimeout(1000) 等固定延时翻页，脆弱且不可靠；无任何测试，package.json 的 test 脚本仍是默认 exit 1 占位；选择器(storybook、storybook-page.right、.play-pause-button)强耦合特定页面结构，几乎无适配性；catch 中静默 break/console.error，错误处理粗糙；run() 调用未 await 也无顶层错误捕获
- **证据**：main.ts:79-119 saveAudio 用 Promise 监听 response，但 audioPromise 无 reject/timeout，audioIndex>=totalPages 才 resolve；main.ts:60 await page.waitForTimeout(1000) 固定延时翻页；main.ts:36-37 page.locator('storybook') 等自定义元素选择器硬编码；main.ts:156 run(url) 顶层未 await，无 .catch 处理 promise rejection；CLAUDE.md:1-3 为 Claude Code 提供项目指引；package.json:8 test 脚本为默认占位 echo "Error: no test specified" && exit 1
- **AI 参与**：high 置信；信号：仓库内含 CLAUDE.md，明确写明是给 Claude Code 使用的项目指引(line 1-3), README 结构高度模板化：Features 带 emoji 图标、Prerequisites/Installation/Usage/Troubleshooting/Requirements 一应俱全，对一个 156 行的私人脚本而言文档过度详尽，是典型 AI 生成痕迹, README 中 git clone 后 cd download-storybook 与仓库名 gemini-storybook-downloader 不一致，暴露生成文档与实际仓库的脱节, .gitignore 中包含 .claude 目录，进一步佐证使用了 Claude Code 工作流
  - 把控评估：作者对 AI 的把控属于中等偏上：架构虽简单但模块边界清晰(prepareScreenshotDir/injectPageStyles/captureScreenshots/saveAudio/run 职责分明)，且唯一一次 commit 是把 AI 常见的固定 timeout 改成等待全部文件，说明作者真实理解并主动修正了生成代码的缺陷，不是无脑堆砌；但仍残留无超时兜底等 AI 痕迹，把控不够彻底。
- **年代背景**：2025 年底 Playwright 1.56 与 tsx 已是成熟主流，用其写网页抓取脚本属常规操作；按当年标准这是一个完成度尚可但门槛不高的个人小工具。

### 2025-11-27 · TypeFree　(功能8/代码7/技术7)
- **定位**：一款 macOS 语音听写/转录应用：本地 whisper.cpp 与 Parakeet ASR、Apple SpeechAnalyzer、AI 文本增强、上下文感知 Power Mode、全局热键直接插入光标处。　|　技术栈：Swift, SwiftUI, SwiftData, AppKit, whisper.cpp (xcframework), FluidAudio/Parakeet, Speech (SpeechAnalyzer), AppIntents, KeyboardShortcuts, OpenRouter/Ollama
- **亮点**：技术栈广而真实：whisper.cpp actor 桥接 + Parakeet(FluidAudio) + macOS26 SpeechAnalyzer 三引擎；协议化转录路由(TranscriptionService) + SwiftData 多级容器降级(持久/内存/最小/dummy)，工程化扎实；VoiceInk 品牌彻底清洗：bundle id、日志 subsystem、文案全部改为 dev.zhangyu.typefree，无残留；对上游做了取舍：AI provider 精简为 OpenRouter/Ollama/Custom，默认模型换为当代开源大模；Power Mode 上下文感知(活动 App/浏览器 URL via AppleScript)等高级特性完整保留可用
- **短板**：本质是开源项目 VoiceInk 的 rebrand/fork，绝大部分架构与源码非作者原创；单 commit 无历史，且无 README，无法佐证作者对各模块的实际改动深度；无任何测试（136 个 swift 文件，0 测试），CI 也缺失；Obfuscator 仅为 Base64+盐的伪混淆，API key 实际未做强加密(局限来自上游)；AIProvider.availableModels 三个分支全返回空数组，属未完成/占位逻辑
- **证据**：TypeFree/Whisper/LibWhisper.swift:10 `actor WhisperContext` 严格单线程访问 whisper C++ context，flash_attn/VAD 参数配置完整；TypeFree/Services/AIEnhancement/AIService.swift:3-28 AIProvider 仅 openRouter/ollama/custom，默认 'openai/gpt-oss-120b'（明显裁剪过的上游枚举）；TypeFree/TypeFree.swift:46-87 ModelContainer 持久→内存→最小→dummy 四级降级初始化；TypeFree/Services/NativeAppleTranscriptionService.swift:9,65-68 macOS26 SpeechAnalyzer 通过 ENABLE_NATIVE_SPEECH_ANALYZER 编译条件 feature-gate；依赖 Package.resolved 含 ejbills/mediaremote-adapter、FluidInference/FluidAudio、tisfeng/SelectedTextKit —— VoiceInk 同款依赖指纹；git log 仅 1 个 commit (dc004a8, author zhangyu1818 <hey@zhangyu.dev>)，全库 squash；CLAUDE.md:1-7 完整项目指引文档，面向 Claude Code
- **AI 参与**：medium 置信；信号：根目录存在结构化、措辞高度统一的 CLAUDE.md（含 Build/Architecture/Services 全量说明），明显是给 Claude Code 用的开发指引, AIProvider 默认模型为 'openai/gpt-oss-120b'，2025 下半年才出现的模型，符合 AI 辅助/当代环境, 整库压缩为单一 commit（squash），原始开发轨迹被抹除，难判定具体哪些为人工撰写, 代码注释风格统一、解释性强（如 createDummyContainer 中长段 preconditionFailure 理由说明），带轻度生成痕迹
  - 把控评估：作者对 AI/上游代码的把控良好：品牌清洗彻底无残留、provider 精简取舍合理、默认模型更新为当代选择、CLAUDE.md 与实际架构一致，集成连贯；但因 squash 单 commit 且无测试/README，难以判定深度二次开发的比例，整体偏向高质量的定制整合而非从零原创。
- **年代背景**：2025-11 时点，whisper.cpp/Parakeet/macOS26 SpeechAnalyzer 多引擎听写已是成熟范式，作者基于 VoiceInk 二次开发并清洗品牌、裁剪 provider、接入当代开源大模，属当年合理且有一定品味的工程实践；评分按 fork+定制而非纯原创衡量。

### 2025-11-28 · qwen3-asr-worker　(功能5/代码6/技术5)
- **定位**：部署在 Cloudflare Workers 上、基于阿里云 Qwen3-ASR 模型的 OpenAI 兼容语音转写 API（/v1/audio/transcriptions），用 Hono 框架封装上传到 OSS 再调用 DashScope 的流程。　|　技术栈：TypeScript, Hono, Cloudflare Workers, Wrangler, Alibaba Cloud DashScope/Qwen3-ASR, OSS
- **亮点**：OpenAI Whisper API 兼容设计到位，支持 json/verbose_json/text/srt 四种 response_format；类型定义清晰(types.ts/asrService 接口)，Env、上传策略、ASR 响应均显式建模；封装了 DashScope 两步上传(getPolicy→OSS 直传)与 OssResourceResolve 头等真实集成细节；诚实地在 README 顶部标注了生产环境部署失败的根因(区域端点冲突)
- **短板**：项目部署后实际不可用：OSS 临时上传仅限中国大陆，而 Workers 调用 China 端点超时，属未跑通的核心功能；SRT 时间码生成过于粗糙：单条字幕、用 00:00:${duration} 拼接，时长>59 秒或带小数会产出非法 SRT；文件校验依赖客户端可伪造的 file.type(MIME)，无真实魔数/扩展名兜底；convertToOpenAIFormat 接收 uploadInfo/processingTimeMs 形参却未使用，存在死参数与轻微冗余；无任何测试、无 CI、无 lint 配置
- **证据**：README.md:3-4 IMPORTANT 块自述 deployed 后 API timeout，OSS 临时上传仅大陆可用，与 International 端点不兼容；src/index.ts:160 srtContent 用 `00:00:00,000 --> 00:00:${Math.floor(duration)...}` 无分/时进位，时间码错误；src/index.ts:56 validateFile 仅 ALLOWED_TYPES.includes(file.type) 校验，MIME 可被客户端伪造；src/services/asrService.ts:209-233 convertToOpenAIFormat 形参 processingTimeMs、uploadInfo 均未在函数体内使用；src/services/uploadService.ts:48-82 实现 DashScope OSS policy 表单直传(OSSAccessKeyId/Signature/policy 等字段)；CLAUDE.md:1-3 明确为 Claude Code 编写的仓库指引文档
- **AI 参与**：high 置信；信号：仓库根目录存在 CLAUDE.md（明确写给 Claude Code 的指引文档），是 AI 辅助的直接证据, README 大量使用 emoji 小节标题(🌟🚀📖🛠️🏗️)、对齐工整的表格与极其完整的样板式文档，风格高度统一，典型 AI 生成文风, 仅 1 个 commit（e749d52），一次性成型且文档/代码同时齐备，符合 AI 一把梭生成, 代码注释中英混杂（asrService/uploadService 用中文 JSDoc，index.ts 用英文注释），风格不一致, wrangler.jsonc 保留了 wrangler init 的全部模板注释（Smart Placement / Static Assets 等未使用项），属脚手架原样产物
  - 把控评估：作者对 AI 产物的把控属中等偏上：模块边界清晰(index 路由 / asrService / uploadService / types 分层合理)，类型建模与错误包装一致，且能诚实记录并定位生产部署失败的真实根因，体现了对集成逻辑的真实理解；但也残留了 AI/脚手架痕迹——死参数、粗糙的 SRT 实现、中英混杂注释、未使用的模板注释，说明审校与打磨不够彻底。
- **年代背景**：创建于 2025-11-28，此时 Hono+Cloudflare Workers 套 wrangler 脚手架已是边缘 Serverless 的成熟主流范式，Qwen3-ASR 也是当年新模型；用当年标准看，这是一个集成思路清晰但未跑通、规模很小的个人 demo 级封装。

### 2025-11-29 · homebrew-tap　(功能6/代码6/技术4)
- **定位**：GoReleaser 自动生成的 Homebrew tap，用于通过 brew 分发自研 Go 二进制 qwen3-compatibility（Qwen3 ASR 的 OpenAI 兼容 API server）。　|　技术栈：Ruby, Homebrew Formula, GoReleaser, brew services (launchd/systemd)
- **亮点**：多平台分发齐全：macOS/Linux × amd64/arm64 四套 url+sha256；包含 brew services 配置（keep_alive、日志路径、interval）；带最小 test 块（version 自检），符合 tap 规范；通过 CI/GoReleaser 自动发布，工程化交付链路完整
- **短板**：内容完全机器生成，作者本人代码贡献几乎为零；service 块用 run_type :interval interval 10 对常驻 server 语义存疑（更像 keep_alive 守护，间隔重跑配置可能冗余/不当）；install 块在每个分支内重复定义，未提取复用（GoReleaser 模板使然）；无 README，单文件仓库信息量极低
- **证据**：qwen3-compatibility.rb:4 '# This file was generated by GoReleaser. DO NOT EDIT.'；qwen3-compatibility.rb:11-45 四个平台分支各自定义 url/sha256/install；qwen3-compatibility.rb:47-54 service 块 run_type :interval / interval 10 / keep_alive true；git log: 唯一提交 39bf7db 由 goreleaserbot 于 2025-11-29 创建
- **年代背景**：2025 年 GoReleaser 自动生成并推送 Homebrew tap 已是 Go 生态的标准发布实践，该仓库本身不体现作者手写代码，只反映其上游项目采用了成熟的自动化发布链路。

### 2025-11-29 · qwen3-compatibility　(功能6/代码6/技术5)
- **定位**：一个 Go 编写的 HTTP 服务，把阿里 DashScope 的 Qwen3-ASR 语音转写能力包装成 OpenAI 兼容的 /v1/audio/transcriptions 接口，作为 drop-in 代理网关。　|　技术栈：Go 1.25, gin, spf13/cobra, spf13/viper, GoReleaser, GitHub Actions, DashScope/OSS
- **亮点**：清晰的 cmd/internal/pkg 分层与接口注入(IUploadService/IASRService/Uploader/ASRProvider)；生产化细节齐全：优雅关闭、gin release 默认、HTTP 超时、集中错误处理；完整发布链路：GoReleaser 多平台+Homebrew tap+CI(golangci-lint/gofmt/vet) 门禁；正确实现 DashScope 三步流程(取 policy→OSS 表单上传→ASR 调用)，API Key 仅透传不落地
- **短板**：零测试：go.mod 引入 go.uber.org/mock 却无任何 _test.go，接口抽象未被利用；调试日志泄露隐患：CallASR 用 log.Printf 打印完整请求体，且请求日志含明文 prompt；存在死代码：CreateVerboseResponse 在接口与实现中定义但 handler 从不调用；enableITN 在 service 层被硬编码 true，参数形同虚设；config 里 viper.SetEnvPrefix 在 AutomaticEnv 之后调用，环境变量前缀绑定时序可疑；ValidateFile 仅按 Content-Type/扩展名校验而非嗅探内容
- **证据**：pkg/client/dashscope.go:101-175 CallASR 构造 system/user 双消息并加 X-DashScope-OssResourceResolve 头；pkg/client/dashscope.go:144-145 重复注释 '// Log request for debugging'，:146 打印完整 jsonData；internal/services/asr.go:23 TranscribeAudio 调用 CallASR(...true...) 将 enableITN 写死；internal/services/interfaces.go:19 声明 CreateVerboseResponse，但 handlers/transcription.go 只用 ConvertToOpenAIFormat；internal/config/config.go:53-54 AutomaticEnv() 先于 SetEnvPrefix("QWEN_COMPAT") 调用；cmd/server/main.go:126-162 标准 http.Server + signal.Notify 优雅关闭；.github/workflows/ci-cd.yml:40-51 golangci-lint + gofmt 严格门禁，但无 go test 步骤；go.mod:42 go.uber.org/mock v0.5.0 为 indirect 且无测试使用
- **AI 参与**：high 置信；信号：仓库根目录存在 CLAUDE.md，明确写给 Claude Code 的指导文档, 全仓库仅一条 squash 提交 851b9b9，无渐进开发历史, 注释风格高度统一、措辞工整，README/CLAUDE.md/goreleaser header 大量 emoji 与模板化营销文案, dashscope.go:144-145 出现重复的 '// Log request for debugging' 注释，典型生成-拼接残留
  - 把控评估：作者对 AI 的把控较好：架构连贯、模块边界清晰、接口与依赖注入设计到位，DashScope 三步上传/ASR 流程属非平凡的人工领域知识整合，发布工具链也配置得当。但把控未达精修级——遗留重复注释、未调用的 verbose 方法、写死的 enableITN 参数、以及承诺测试框架却零测试，说明对生成物的清理与收口不够。
- **年代背景**：2025-11 Qwen3-ASR 刚上线，做 OpenAI 兼容代理在当年是合理且有时效性的小工具；以 2025 年 Go 工程标准衡量，分层/CI/发布链路达到合格偏上，但缺测试和调试日志泄露在当年也属明确扣分项。

### 2025-12-02 · v2ray2clash　(功能5/代码5/技术4)
- **定位**：一个 Cloudflare Worker，将 V2Ray 订阅链接（ss/vmess）转换为 Clash YAML 配置，支持白名单/黑名单分流模式。　|　技术栈：TypeScript, Cloudflare Workers, Wrangler 4, js-yaml, Vitest, @cloudflare/vitest-pool-workers
- **亮点**：工具链现代且正确：wrangler4 + vitest-pool-workers + satisfies ExportedHandler<Env>；类型定义清晰（ClashProxy/ClashConfig/RuleProvider 接口齐全）；复用成熟的 Loyalsoldier clash-rules 规则集，白/黑名单分流策略合理；有外层 try/catch、502/400/500 分级返回与 5 分钟缓存头
- **短板**：测试与实现不一致，当前测试套件会失败（Usage 文案与 Auto 分组均不存在）；协议覆盖窄：仅支持 ss/vmess，缺 vless/trojan/hysteria；SS 解析仅支持旧式 base64(method:password@host:port)，不兼容 SIP002 与插件参数；vmess 使用已废弃的 ws-path/ws-headers 字段（现代 Clash 用 ws-opts），缺 SNI/servername；文件间缩进风格不统一，atob 误判 base64 时未必抛错可能产生乱码
- **证据**：src/index.ts:34 实际仅返回 'Bad Request'，但 test/index.spec.ts:103-104,187-188 断言返回体含 'Usage:' 与 'Format:'，测试必失败；src/index.ts:90-97 仅生成 {name:'PROXY',type:'select'} 单一分组，但 test/index.spec.ts:247,250-251 断言存在 '- Auto' 与 name:Auto/type:url-test，测试必失败；src/parsers.ts:11-15 SS 解析硬编码 method:password@host:port 旧格式，无 SIP002 支持；src/parsers.ts:62-71 vmess 使用 ws-path/ws-headers（旧 schema）而非现代 ws-opts；src/index.ts:69 对整段订阅 atob，依赖 catch 回退；parsers.ts 用 4 空格而 index.ts 用 tab，与 .prettierrc useTabs:true 冲突；README.md:33 宣称含 PROXY 和 Auto 两组，与实现不符
- **AI 参与**：high 置信；信号：每个函数顶部都有风格高度统一的 JSDoc 块注释（V2Ray to Clash Converter Worker / Parse Shadowsocks (SS) link 等），样板化明显, index.ts/config.ts 用 tab 缩进（符合 .prettierrc useTabs:true），但 parsers.ts 用 4 空格缩进——多次生成未与 prettier 统一，典型多轮 AI 生成拼接痕迹, 测试与实现严重脱节：测试断言 400 返回体含 'Usage:'/'Format:' 且存在 type:url-test 的 'Auto' 分组，而实际 index.ts 只返回 'Bad Request' 且仅生成单个 type:select 的 PROXY 分组，说明代码被改动后未回归测试（生成-修改链路缺乏人工核对）, README 第33行宣称包含 'PROXY and Auto proxy groups'，但代码只产出 PROXY 组，文档与实现不一致, 代码中保留 console.log('Fetching V2Ray subscription:'...) 等调试日志，整体行文风格机械、注释覆盖率异常高
  - 把控评估：项目创建于 2025-12，AI 辅助生成可能性高。架构层面把控尚可：模块边界清晰（index 路由+IO / parsers 解析 / config 配置模板），类型与现代 Workers 范式使用地道，规则集选型有判断力。但人工把控存在明显缺口——AI 生成的测试与后续手改的实现互相脱节（Usage 文案、Auto 分组均已不存在却仍被断言），且文件缩进风格不统一、README 与代码不符，说明作者对生成产物的回归校验与整合打磨不到位，属于'能搭起骨架但未做收尾核验'的中等把控水平。
- **年代背景**：2025 年底 Cloudflare Workers + wrangler4 + vitest-pool-workers 已是成熟主流栈，该项目用法正确合规；但以当年标准衡量，订阅转换器属低难度常见工具，且测试与实现脱节是不应出现的硬伤，故功能与质量评中等。

### 2025-12-04 · Mermaid-AI　(功能6/代码6/技术4)
- **定位**：一个基于 React 的 Mermaid.js 图表编辑器，左侧代码编辑、右侧实时渲染（手绘风格），支持 localStorage 持久化、缩放、SVG 导出，以及调用 Gemini 修复/格式化 Mermaid 语法。　|　技术栈：TypeScript, React 19, Vite 6, Mermaid 11, @google/genai (Gemini 2.5 Flash), TailwindCSS (CDN), lucide-react
- **亮点**：模块划分清晰：components/services/hooks/utils 分层合理；实时渲染用 useDebounce(600ms) 配合 mermaid.parse 先校验再 render，避免半成品报错；useEffect 用 isMounted 守卫防止卸载后 setState；错误捕获、Toast 反馈、AI 返回结果剥离 markdown 围栏等细节处理到位
- **短板**：本质是 AI Studio 一键脚手架，技术深度低、几乎无原创难点；API_KEY 经 vite define 注入前端，密钥暴露在浏览器，纯客户端调用 Gemini 不安全；缩放仅 CSS transform，无拖拽平移/适应画布等真正交互；编辑器是裸 textarea 无语法高亮；无任何测试、无 CI、无错误边界；mermaid.render 用 Date.now() 生成 id 略糙，securityLevel:'loose' + dangerouslySetInnerHTML 有 XSS 隐患
- **证据**：README.md: '# Run and deploy your AI Studio app' 及 https://ai.studio/apps/drive/ 链接（AI Studio 模板原文）；index.html importmap 指向 https://aistudiocdn.com/react@^19.2.1 等；vite.config.ts:14-15 将 GEMINI_API_KEY 通过 define 注入 process.env.API_KEY（前端可见）；services/geminiService.ts:3 new GoogleGenAI({ apiKey: process.env.API_KEY })，:33 用正则剥离 ```mermaid 围栏；components/Preview.tsx:57-59 先 mermaid.parse 再 render，:44 useDebounce(code,600)，:47/61 isMounted 守卫；components/Preview.tsx:16 securityLevel:'loose' 配 :122 dangerouslySetInnerHTML 注入 svg；git log 仅 1 次提交 92fce42 'feat: Initialize Mermaid AI Architect project'
- **AI 参与**：high 置信；信号：README 为 Google AI Studio 默认模板：'Run and deploy your AI Studio app' 并附带 ai.studio/apps/drive 链接, index.html 使用 importmap 指向 aistudiocdn.com 托管依赖，是 AI Studio 导出工程的典型特征, 唯一一次提交 'feat: Initialize Mermaid AI Architect project'（2025-12-04 ZHANGYU），一次性整体生成, metadata.json 含 requestFramePermissions 字段，为 AI Studio 工程约定, 代码注释风格统一且偏说明性（如 'Initialize mermaid with a hand-drawn, clean theme'、'Clean up just in case the model adds markdown'）
  - 把控评估：尽管创建于 2025-12（按规则属 pre-AI 窗口），但证据明确为 Google AI Studio 一键生成并导出的工程。作者的人工把控痕迹很弱：除部署到 Vercel、改了应用名外，未见对脚手架做非平凡的二次定制（无路由、无后端代理保护密钥、无功能扩展、无测试）。整体架构连贯、模块边界清晰，但这是生成器本身的功劳而非作者深度整合；可视为'接受并发布生成物'级别的把控。
- **年代背景**：2025 年底 React19/Vite6/Mermaid11 与 Gemini 2.5 Flash 均为当时主流，Google AI Studio 一键生成可运行 Web App 已很成熟，因此这是当年低门槛即可产出的标准脚手架级应用，技术深度不应按高标准苛评。

### 2026-01-24 · vercel-best-practices-report-viewer　(功能6/代码6/技术5)
- **定位**：一个单页 React 应用，用于可视化「vercel-react-best-practices-report」技能生成的 JSON 审计报告：拖拽上传 JSON 后展示健康分仪表盘与逐条违规卡片（含原始代码 vs 建议修复的语法高亮对比）。　|　技术栈：TypeScript, React 19, Vite 7, Tailwind CSS v4, shadcn/ui, shiki, lucide-react, react-compiler
- **亮点**：技术栈紧跟 2026 初前沿：React 19 + Vite 7 + Tailwind v4(CSS-first @theme) + react-compiler 全开；shiki 高亮做了单例 highlighter，配合 memo + useTransition 与 mounted 清理标志，性能与卸载安全考虑到位；JSON 解析有防御性，同时兼容数组与 {findings:[...]} 两种报告形态（与唯一提交 'support findings object' 对应）；主题切换兼顾系统偏好与 localStorage 持久化，整体 UI 质感干净
- **短板**：Dashboard.tsx 末尾的 import + 自述注释是明显 AI 痕迹与代码异味；13 个 shadcn 组件仅 5 个被使用，大量死代码未清理；类型偏松散：lineNumber 用 string、无 severity 字段，与 DESIGN_SYSTEM 中的严重级别色板不一致；无任何测试；report[file].length 直接解构、健康分 100-2*violations 等逻辑无边界保护说明；README/设计文档承诺的 Tabs/Accordion/筛选未落地，ReportViewer 实际只是扁平卡片列表
- **证据**：src/components/ui/code-block.tsx:6-16 highlighterPromise 单例 + createHighlighter，避免重复初始化；src/components/ui/code-block.tsx:33,50 useTransition + startTransition 包裹 setHtml，降低高亮渲染的阻塞；src/components/FileUpload.tsx:33-45 同时处理 value 为数组或含 findings 字段的对象，逐文件校验格式；src/components/Dashboard.tsx:91-93 文件末尾 import { cn } 并附带 AI 风格自述注释；ui 组件使用统计：accordion/alert/dialog/input/label/scroll-area/table/tabs 在业务代码中 0 次引用；src/lib/types.ts:1-8 Report = Record<string, RuleViolation[]>，类型极简且 lineNumber 为 string；vite.config.ts:9-13 babel-plugin-react-compiler 已启用
- **AI 参与**：high 置信；信号：Dashboard.tsx:91-93 文件底部出现自述式注释「Helper for conditional classes since we don't import cn inside the function scope usually, but I'll import it at the top.」并把 import 放在文件末尾——典型 AI 生成的思维残留与反常导入位置, DESIGN_SYSTEM.md 是一份结构化的设计规划文档（设计原则/色板/组件清单/布局），读起来像 AI 在编码前的 plan，且最终实现与之有出入（文档写了 Tabs/Accordion/筛选/图表，实际未实现）, 项目本身是 Claude/AI 技能生态的配套查看器（描述明确为某 best-practices-report skill 的可视化器），2026-01 创建, 13 个 shadcn UI 组件中 8 个（accordion/alert/dialog/input/label/scroll-area/table/tabs）从未被引用，属一次性生成时按设计文档批量 scaffold 的死代码, index.html title 仍为默认 'report-view'、favicon 仍是 vite.svg，未做基本收尾
  - 把控评估：作者对 AI 产物的把控属于中等偏上：架构连贯（App→FileUpload/Dashboard/ReportViewer 边界清晰），且做了非平凡的人工定制——shiki 单例 + useTransition 的性能处理、兼容两种报告 schema 的防御性解析（有对应提交记录，说明在真实使用中迭代过），这些超出无脑生成的水平。但收尾品味不足：未清理 8 个未用组件、保留默认 title/favicon，尤其 Dashboard.tsx 末尾把 AI 的自述注释和异常 import 原样留下，暴露出对生成代码的审阅不够细致。
- **年代背景**：2026-01 时 React 19 / Tailwind v4 / react-compiler / shiki 均已成熟可用，本项目用上了这些当年的最新范式，因此栈本身不构成加分亮点而是合格基线；同期 AI 一把梭生成此类配套工具极常见，评分按当年标准衡量其为一个完成度尚可、但收尾与抽象深度有限的小工具。

### 2026-01-25 · vercel-react-best-practices-report　(功能8/代码9/技术7)
- **定位**：一个基于 Ink/React 的 CLI/TUI 工具，调用 Claude Agent SDK 或 Codex SDK 的 provider 适配器，按 Vercel React Best Practices skill 对 React/Next.js 代码逐文件审计并把结构化 findings 合并进 reports.json。　|　技术栈：TypeScript, React 19, Ink 6, @inkjs/ui, @anthropic-ai/claude-agent-sdk, @openai/codex-sdk, arg, node:test, tsx, pnpm, ESLint 9
- **亮点**：清晰的 provider 适配器模式：Claude/Codex 统一 AuditAdapter 接口 + 依赖注入 (create-audit-adapter.ts)；可断点续跑的文件队列 (queue-state.ts) + 跨进程文件锁 (openSync 'wx' + EEXIST 重试/超时)；队列与报告写入均用 temp+rename 原子落盘，避免并发损坏；纯展示逻辑抽离 (tui-presentation.ts) 使 TUI 无需渲染即可测试；44 个测试全绿、src:test 近 1:1；parseDirectory 做了路径穿越防护，adapter 层有 abort/10 分钟超时与 signal 透传
- **短板**：discoverAuditFiles 直接 spawn 系统 find，跨平台（Windows）不可用、且依赖外部二进制；文件锁是单机 advisory 锁，进程崩溃残留 lock 文件需 30s 超时才恢复，无 stale-lock 主动清理；无 CI 配置（无 .github/workflows），仅本地 test 脚本；AuditFinding.lineNumber 用 string 而非结构化范围，下游消费需再解析
- **证据**：package.json:36-44 依赖 @anthropic-ai/claude-agent-sdk 与 @openai/codex-sdk，version 3.1.0、bin 入口已发布到 npm；src/bin/lib/file-lock.ts:12-31 acquireFileLock 用 fs.openSync(lockPath,'wx') 捕获 EEXIST 轮询，30s 超时；src/bin/lib/queue-state.ts:113-150 initializeQueueState 合并 failed/pending/inProgress/discovered 实现断点续跑；src/bin/lib/queue-state.ts:73-77 与 report-files.ts:98-102 均用 writeFileSync(tmp)+renameSync 原子写；src/bin/lib/providers/create-audit-adapter.ts:21-38 依赖注入式适配器工厂，便于测试替换；src/bin/lib/cli-options.ts:122-149 parseDirectory 拒绝绝对路径与 ../ 越界；src/bin/lib/runtime-paths.ts:46-49 discoverAuditFiles 用 execFileSync('find', ...) 跨平台局限；.gitignore:3 ignore docs/superpowers/plans/ —— Claude Code 工作流产物；test 全套 44 用例通过 (pnpm test)，claude-adapter.test.ts 用伪造 async iterable 注入 SDK 消息
- **AI 参与**：high 置信；信号：.gitignore 忽略 docs/superpowers/plans/ —— 这是 Claude Code superpowers 工作流的计划产物路径，强 AI 协作信号, 整个仓库只有一个 squashed commit (bdd1f91 chore: bump version to 3.1.0)，无开发历史, 代码风格高度统一、零注释（与作者全局 CLAUDE.md 的 no-comment 偏好一致），命名/错误处理范式整齐划一, 工具本身即编排 AI Agent SDK (Claude/Codex) 做代码审计，属于 AI 工具范畴, 对象字面量属性、import 分组、测试断言均呈现 lint/格式化器强约束下的机械一致性
  - 把控评估：作者对 AI 的把控属高水准：架构连贯（适配器/队列/锁/展示分层清晰），模块边界与依赖注入到位，存在非平凡的人工设计（断点续跑队列、跨进程文件锁、原子写、abort/超时、路径穿越防护），测试覆盖几乎所有模块并通过伪造 SDK 消息做单元隔离，并复用了作者自己发布的 @zhangyu1818/eslint-config，体现真实工程品味而非无脑堆砌生成物。
- **年代背景**：创建于 2026-01，正值 Claude Agent SDK / Codex SDK 成熟、AI 辅助编码常态化的时期；用 AI Agent 编排做代码审计是当年自然的范式，且作者明显借助 AI 工作流（superpowers）完成，因此评分聚焦于其对 AI 产物的架构把控而非是否手写。

### 2026-02-12 · anthropic-gateway　(功能8/代码8/技术7)
- **定位**：配置驱动的 Anthropic 兼容 API 网关，按 YAML 把请求中的 model 改写并代理到上游（如 GLM）兼容端点，含鉴权替换、SSE 流式透传与 macOS 自启动管理。　|　技术栈：Go 1.25, net/http, log/slog, yaml.v3, launchd/launchctl, GitHub Actions
- **亮点**：地道的 Go 工程：adapter 接口抽象 + slog 结构化日志 + 信号优雅关停；代理卫生到位：剥离 hop-by-hop 头、替换入站鉴权、SSE 手动 flush 透传；现代 launchctl bootstrap/bootout/kickstart 集成且 plist 做 XML 转义防注入；测试质量高：含真实并发的流式分块计时断言，CI 跨 5 平台编译并生成 checksums
- **短板**：http.Client 未设置整体 Timeout，仅依赖 request context，长尾上游可能挂起连接；io.ReadAll 读取整个请求/响应体且未配置 MaxBytesReader（代码中有 MaxBytesError 分支但未实际挂载限制），大 body 有内存风险；generateRequestID 每次调用都新建 rand.NewSource，碰撞概率与播种成本偏高，非最佳实践；gateway/errors/models 三个包无单元测试，核心 proxyJSON 仅靠集成测试覆盖
- **证据**：internal/gateway/service.go:239-274 copyRequestHeaders/copyResponseHeaders 正确剥离 hop-by-hop 头与入站 Authorization/x-api-key；internal/gateway/service.go:193-221 streamResponse 通过 http.Flusher 逐块 flush，并区分 io.EOF 与 context.Canceled；internal/autostart/manager.go:97-105 使用 launchctl bootout/bootstrap/enable/kickstart 现代域语义而非废弃的 load/unload；internal/autostart/plist.go:8-14 对 plist 字段做 &<>"' XML 转义防注入；internal/config/config.go:90-96 校验 api_base 必须为 http/https scheme 且 host 非空；internal/httpserver/server_test.go:113-167 TestMessagesStreamingFlushesBeforeCompletion 用 700ms 延迟断言首块及时到达，验证真实流式行为；internal/gateway/service.go:30-32 http.Client 仅 Clone DefaultTransport，未设置 client.Timeout；internal/httpserver/server.go:111-114 generateRequestID 每次重新 rand.NewSource(UnixNano)
- **AI 参与**：medium 置信；信号：2026-02 创建（AI 时代默认假设），单次 commit 即 v1.0.0 一步到位、无迭代痕迹, 代码/测试/文档风格高度统一，README 的 Features/Error Semantics 章节结构工整规整, 测试与边界覆盖异常完备（流式 flush 计时、auth 模式、错误归一化、config 校验），符合 AI 辅助系统化产出特征, 无 CLAUDE.md/AGENTS.md/.cursor 等显式 AI 文件，故置信度为 medium 而非 high
  - 把控评估：若有 AI 参与，作者把控力较强：包划分清晰（adapter/config/gateway/httpserver/errors/models 职责单一），接口抽象（Adapter）与依赖注入一致，代理卫生、鉴权替换、流式透传、launchd 集成等非平凡细节均处理到位，README 与错误语义自洽，体现出明确的工程品味而非无脑堆砌；扣分项（缺 client.Timeout、未挂 MaxBytesReader、rand 播种）属可改进的细节而非结构性缺陷。
- **年代背景**：创建于 2026-02，正值 AI 辅助编码成熟期；以当年标准看，这是一份结构清晰、测试与 CI 完备的合格偏上的小型 Go 网关，AI 很可能参与生成但作者对架构边界与代理细节把控良好。

### 2026-02-15 · mp3-vtt　(功能7/代码8/技术6)
- **定位**：纯前端的卡拉OK式音频播放器：本地加载 MP3 + VTT 字幕，按 <b> 标记逐词高亮跟随播放进度。　|　技术栈：TypeScript, React 19, Vite 7, Tailwind CSS 4, shadcn/ui, Radix UI, Vitest, GitHub Pages/Actions
- **亮点**：VTT 解析器工程化扎实：CRLF 归一化、严格头校验、可选 ID 行容错、时间范围校验；非平凡的单调时间轴 repair 逻辑，处理乱序与零时长 cue；用二分查找定位 active/latest cue 而非线性扫描；9 个有意义的单元测试覆盖空/歧义 <b> 标签等边界，全部通过；地道 React 19：URL.revokeObjectURL 清理、自动播放被拦截兜底、可访问的拖拽上传
- **短板**：README 仍是默认模板，无任何项目说明；package.json name='srt'、页面 title='srt' 与项目不符，收尾粗糙；UI 组件为通用 shadcn 脚手架，无个性化；范围很小、单一功能玩具应用，0 star
- **证据**：src/lib/parse-vtt.ts:137-165 单调时间轴 repair 与零时长 cue 归一化逻辑；src/lib/parse-vtt.ts:170-201 findActiveCue 用二分查找定位活动 cue；src/lib/parse-vtt.ts:77-91 严格 WEBVTT 头校验与 \r\n 归一化、空块过滤；src/App.tsx:34-67 audioUrl 的 revokeObjectURL 清理与 autoplay 被拦截兜底处理；src/lib/parse-vtt.test.ts 9 个测试全部通过（vitest run 验证）；README.md:1-3 为未修改的 Vite 默认模板内容；package.json:2 name 为 'srt'；index.html title 同为 srt，与仓库名不一致；vite.config.ts:8 base 按 GITHUB_ACTIONS 条件切换 '/mp3-vtt/'，CI 部署正确
- **AI 参与**：high 置信；信号：README.md 为未改动的 Vite + React + TypeScript 默认模板（典型生成后直接发布的痕迹）, src/components/ui/*.tsx 为标准 shadcn/ui new-york 风格脚手架，components.json 存在, 代码风格高度统一、零行内注释、命名/错误处理一致，符合 2026 AI 辅助产出特征, package.json name 仍为 'srt'、index.html <title>srt 与仓库名 mp3-vtt 不一致，提示脚手架快速生成
  - 把控评估：作者对 AI 把控良好：脚手架与 UI 虽为生成物，但 parse-vtt 的时间轴修复、二分查找、对空/歧义 <b> 标签的处理及配套测试体现了清晰的需求拆解与人工设计品味，模块边界（lib 解析 / components UI / App 编排）划分干净，集成连贯，不是无脑堆砌。
- **年代背景**：2026 年初 React 19 + React Compiler + Tailwind 4 + shadcn + Vitest 已是主流脚手架，AI 辅助生成此类完成度应用是常态；评分聚焦作者在解析器算法与测试上的真实把控而非脚手架本身。

### 2026-03-11 · codex-feishu　(功能8/代码9/技术7)
- **定位**：个人用飞书机器人，通过 stdio JSON-RPC 远程控制本机运行的 codex app-server，管理工作区/会话并把 Codex 的回合事件渲染成飞书卡片。　|　技术栈：TypeScript, Bun, Node.js, @larksuiteoapi/node-sdk, Zod 4, Vitest 4, ESLint 10, JSON-RPC over JSONL, Codex app-server protocol
- **亮点**：手写 JSONL JSON-RPC 客户端，含 pending map/超时/通知与 server-request 监听分发与类型守卫；领域建模清晰：workspace/thread/turn 对齐 Codex 自身模型，状态 store 用纯函数+zod 不可变更新；非平凡算法：工作区同名时计算最短唯一后缀显示名(workspace-list.ts)；测试充分：22 个测试文件 58 个用例，覆盖 RPC、回合事件、状态、命令解析等核心逻辑；工程化严格：eslint max-lines 300 / max-lines-per-function 80、no-floating-promises，驱动细粒度模块拆分
- **短板**：硬编码 approvalPolicy: never + danger-full-access，自动批准一切命令/补丁，安全面极大(README 已坦诚说明)；仅支持 p2p 私聊、无群聊/卡片回调/流式输出，功能边界刻意收窄；无身份校验：任何能私聊该机器人的人都可对本机执行任意 Codex 操作；无 CI 配置；生成的 protocol 类型 gitignore，clone 后无法直接 typecheck/构建
- **证据**：src/codex/jsonl-rpc-client.ts:105-126 sendRequest 用 nextId+Promise+setTimeout 实现带超时的请求-响应映射；src/codex/codex-app-server.ts:73-90 createThreadStartParams 硬编码 approvalPolicy:'never'、sandbox:'danger-full-access'；src/workspaces/workspace-list.ts:30-67 同名工作区计算最短唯一路径后缀生成显示名；src/bot/turn-runtime-status-store.ts:309-331 resolveWorkspace 通过 turnToWorkspace/threadToWorkspace 双 map 解析归属；eslint.config.mjs: max-lines=300 / max-lines-per-function=80 / no-floating-promises 解释了细粒度文件拆分；src/state/runtime-state-store.ts:19-29 zod schema 校验持久化状态，纯函数式不可变更新；tests/turn-event-processor.test.ts:6-154 端到端模拟多种 Codex 通知并断言聚合后的运行时状态；package.json:5,38 Bun 1.3.10 + Vitest 4 + ESLint 10 + Zod 4 的 2026 前沿栈
- **AI 参与**：medium 置信；信号：创建于 2026-03，默认按 AI-era 处理；本身即围绕 Codex(AI 编码 agent) 构建, 单一 squashed 提交 'feat: add bun-managed feishu codex bot'，无渐进式开发历史, 全仓风格高度统一：命名、错误处理、type-import、import 排序极度一致，符合 AI 辅助 + 严格 lint 的产物特征, 无 CLAUDE.md/AGENTS.md/.cursor 等显式标记文件，故置信度为 medium 而非 high
  - 把控评估：把控能力很高：架构连贯、模块边界清晰(codex/bot/feishu/state/workspaces/commands 分层合理)，把 Codex app-server 协议、飞书长连接、运行时状态机三者集成到位；有最短唯一后缀、双 map 归属解析、可中断/steer 的回合管理等非平凡人工定制，并以严格 lint 规则和大量测试约束生成物，绝非无脑堆砌。
- **年代背景**：2026 年初 Codex app-server 的 JSON-RPC 协议、Bun 1.3、ESLint 10、Zod 4 都是当年最新可用工具，作者紧跟前沿并地道使用，按当年标准属高水准工程实践。

### 2026-03-22 · task-while　(功能8/代码9/技术8)
- **定位**：Git-first CLI 任务编排器：读取 while.yaml，按 spec-kit/openspec 任务源逐个执行任务，调用 Claude/Codex 实现并审查，支持 direct 与 GitHub pull-request 两种工作流，每个完成任务对应一次 git commit；另含独立 batch 与 simplify 命令。　|　技术栈：TypeScript, Node.js 24, Zod, @anthropic-ai/claude-agent-sdk, @openai/codex-sdk, Playwright, execa, vitest, ESLint 10, pnpm
- **亮点**：纯函数式 kernel 解释器 + 声明式转移表驱动状态机，架构极清晰；六边形端口/适配器（AgentPort/GitHubPort/GitPort），副作用隔离到边界；原子状态写入（tmp+rename）、append-only JSONL 转移日志、artifact 分离存储；完整 GraphQL 分页（reviewThreads 内层评论二次分页）与 remote-reviewer 时间戳裁决逻辑；Zod schema + 语义级 refine（verdict=pass 必须空 findings）、自维护 eslint-config 强制 300 行/禁双重断言
- **短板**：stars=0 且尚为 0.0.x，实战验证有限；simplify 命令依赖 ChatGPT 网页 DOM 选择器（testId/role），脆弱且易随前端改版失效；review 轮询无默认超时（pull-request 模式可能无限等待）；OpenSpec/spec-kit 仅按源顺序执行，无依赖图调度（作者明确标注为非目标）
- **证据**：src/harness/kernel.ts:38-182 纯 runKernel 解释器，按 program.transitions 表驱动 phase 迁移、错误回退与重试预算；src/harness/workflow-program.ts:55-97 createWorkflowProgram 在构建期校验重复节点/缺失转移表/未知目标节点；src/adapters/fs/harness-store.ts:76-82 saveState 用 .tmp + rename 实现原子写；src/runtime/github-pr-snapshot.ts:50-130 多游标并行分页 + reviewThread 内层评论嵌套分页；src/workflow/remote-reviewer.ts:123-241 基于 checkpoint 时间戳比较 approval 与 feedback 信号决定 approved/rejected/pending；src/schema/index.ts:102-114 ensureReviewSemantics 强制 verdict=pass 与 findings/acceptanceChecks 一致；eslint.config.mjs:23-38 max-lines=300 + 禁止 `as unknown as` 双重断言；package.json:46-58 集成 claude-agent-sdk/codex-sdk/playwright/zod-to-json-schema
- **AI 参与**：high 置信；信号：AGENTS.md（LLM 编码行为准则）位于仓库根, skills/ 目录含 generate-batch-yaml、generate-simplify-yaml 等 SKILL.md（Claude Code 风格 skill）, .gitignore 含 docs/superpowers/plans/，表明使用 superpowers AI 工作流, 2026-04 创建，整套工具本身即面向 AI agent 编排（集成 Claude/Codex SDK）, 测试与文档风格高度统一、覆盖密集（244 测试/9K 行），符合 AI 辅助大规模产出特征
  - 把控评估：作者对 AI 的把控属上乘：架构连贯（kernel/program/ports/adapters/task-sources 分层边界清晰），模块严格控制在 300 行内并由自维护的 eslint-config 强制，类型零 any/零双重断言，测试与实现 1.4:1 且测真实迁移与分页边界。GraphQL 嵌套分页、remote-reviewer 时间戳裁决、原子状态写入等均为非平凡人工设计而非生成样板。AGENTS.md/skills 显示其以工程纪律驾驭 AI 产出，整合与品味到位。
- **年代背景**：2026-04 正值 agent 编排工具爆发期，集成 Claude/Codex SDK、内置 skills 与 AGENTS.md 是当年顺势而为；按 2026 工程标准，其纯函数 kernel、端口隔离与测试密度仍属资深水准。

### 2026-04-18 · oxlint-config　(功能9/代码9/技术8)
- **定位**：面向 Oxc 生态（oxlint + oxfmt）的可共享 lint/格式化配置预设包，提供 defineConfig/defineOxfmtConfig 工厂、按依赖自动启用的预设，并内置一个手写的 react-agent-rules JS 插件。　|　技术栈：TypeScript, oxlint, oxfmt, oxc, tsup, vitest, local-pkg, Node 24, pnpm
- **亮点**：手写自定义 Oxlint JS 插件，AST 节点类型守卫严谨，同时覆盖具名导入与 React.xxx 成员调用；defineConfig 工厂设计成熟：预设解析、local-pkg 自动探测、override 裁剪、空字段清理；测试扎实，子进程实跑 oxlint/oxfmt 校验 fixture，含 max-lines 边界(300/301)与打包冒烟测试；完整 CI（format/lint/tsc/test/build/smoke）与 fixture 双向(valid/invalid)覆盖；前瞻性技术栈：Node24/TS6/oxlint1.66/oxfmt，针对 React19+Compiler 设计规则
- **短板**：本质是配置聚合包，技术新颖度受限于 Oxc 生态边界，多数工作是规则枚举与开关编排；javascript 预设等大量规则为逐条罗列(115行)，机械性强；Star 0、无下游使用验证，README 的 264/139 规则迁移数字未在仓库内留存可核对的迁移报告
- **证据**：src/react-agent-rules.ts:41-87 自实现 isRecord/isIdentifier/isMemberExpression/isReactMember 等类型守卫，effectEmptyDepsOnlyRule 检查第二参数为空依赖数组；src/oxlint/index.ts:54-283 defineOxlintConfig 完整编排 presets/plugins/overrides，末尾 263-280 行逐字段删除空配置；src/oxlint/index.ts:41-52 defaultOxlintPresets 通过 isPackageExists('react'/'next'/'vitest'/'typescript') 自动启用；tests/preset-fixtures.test.ts:45-89 通过 execFile 实跑 oxlint/oxfmt 并按 .errors.json 断言具体 ruleId；tests/package-smoke.mjs:132-177 pnpm pack 生成 tarball 后在临时 consumer 中安装并运行真实 lint/format；setup-oxlint/SKILL.md:1-4 带 name/description frontmatter 的 agent skill 定义；package.json:39-59 dependencies 仅 local-pkg，peerDeps oxlint^1.66/oxfmt^0.51，engines node>=24
- **AI 参与**：medium 置信；信号：仓库含 setup-oxlint/SKILL.md（Claude/Agent skill 定义文件，带 frontmatter），是典型 AI-agent 工具链产物, 代码风格高度统一、命名一致、注释为零（符合用户全局规范也符合 AI 生成特征），测试样板结构高度模板化, 2026-04 创建，处于 AI 辅助开发默认普及期；提交者为 zhangyu1818-bot 自动化账号, react-agent-rules 预设本身即为约束 AI/Agent 生成 React 代码而设计（no-manual-memoization 等规则）
  - 把控评估：作者对 AI 的把控很强：模块边界清晰（oxlint/oxfmt/shared 分层，每个预设独立文件），架构连贯且有非平凡人工设计——自写 AST 插件、override 裁剪逻辑、子进程实跑测试与 tarball 冒烟测试都体现了真实工程品味，而非堆砌生成物。react-agent-rules 这类针对 React19/Compiler 的定制规则显示出明确的领域判断。
- **年代背景**：2026-04 时 Oxc 工具链(oxlint 1.x/oxfmt)已成熟到可作为 ESLint/Prettier 替代，作者紧跟该新兴生态并采用 Node24/TS6 等当年前沿版本，按当年标准属于积极拥抱新工具链的资深实践。

### 2026-04-23 · llm-intro　(功能8/代码9/技术7)
- **定位**：一个完整部署的中英双语互动式科普站点，用 17 章 + 逐章定制交互向零基础读者讲清大模型的直觉。　|　技术栈：TypeScript, React 19, Vite 8, Tailwind CSS v4, matter-js, ESLint 10 flat config, GitHub Pages CI
- **亮点**：matter-js 物理引擎做'桌面装不下文档就掉落'的上下文窗口隐喻，引擎生命周期/devicePixelRatio/清理都正确；i18n 架构精巧：每章 colocated *.i18n.tsx 用 typeof zh 在编译期强制英文不漏字段，零运行时 i18n 库；Vite 双入口产出真 /en/ 静态 HTML + 完整 hreflang/canonical SEO，而非客户端语言切换；spec/plan 文档质量极高：列出被拒方案(i18next/MDX/SSR)、YAGNI 边界、验收标准，体现强人工把控；17/19 章节各有定制交互(粒子canvas、多agent定时编排状态机)，rAF节流与cleanup到位
- **短板**：无自动化测试（作者在 plan 里明确以 pnpm build/lint + 手动浏览替代）；本质是单页科普站，技术深度集中在前端工程与交互，不涉及后端/算法/系统底层；部分交互组件(Chapter02)三个 useEffect 串联依赖较多，状态-物理同步逻辑偏复杂
- **证据**：src/sections/Chapter02.tsx:33-159 matter-js Engine/Render/Runner 创建+卸载清理，溢出文档以初速度甩出桌面；src/i18n/global.zh.ts:38-40 与 Chapter*.i18n.tsx 中 `const en: typeof zh = {...}` 编译期对齐翻译；vite.config.ts:10-17 rollup 多入口 en/zh 两份 HTML；en/index.html 含 canonical+三条 hreflang；src/components/LangSwitcher.tsx:8-13 用 import.meta.env.BASE_URL 拼接并保留 window.location.hash；docs/superpowers/specs/2026-05-17-i18n-design.md:64-68 显式列出拒绝 i18next/MDX/SSR 的理由；.github/workflows/deploy.yml frozen-lockfile + build/deploy 分离 + OIDC pages 权限 + 404 fallback；tsconfig.app.json noUnusedLocals/noUnusedParameters/verbatimModuleSyntax/erasableSyntaxOnly 严格档
- **AI 参与**：high 置信；信号：docs/superpowers/plans/2026-05-17-i18n.md 与 specs/2026-05-17-i18n-design.md 是 superpowers(writing-plans/executing-plans) agent 工作流产物, plan 文档顶部含 'For agentic workers: REQUIRED SUB-SKILL: superpowers:subagent-driven-development' 字样, 代码风格在 19 个章节组件间高度统一（同一套交互骨架、命名、Tailwind 类组织），符合 agent 批量实现特征, 创建于 2026-04，按规则默认 AI 参与
  - 把控评估：作者对 AI 的把控属上乘：先写出条理清晰的 spec(列被拒方案与 YAGNI)再驱动 agent 逐章实现，架构连贯(colocated i18n + 编译期约束)、模块边界清晰、19 个交互各有非平凡的人工设计与隐喻品味，绝非无脑堆砌生成物，而是用 AGENT 工作流高质量交付了一个有审美的成品。
- **年代背景**：2026-04 时 React 19 / Vite 8 / Tailwind v4 / ESLint 10 flat config 与 superpowers agent 工作流均为前沿且成熟，作者地道使用并落地部署，按当年标准属高水准前端工程。

### 2026-06-05 · Portal　(功能9/代码9/技术8)
- **定位**：一个常驻菜单栏的原生 macOS 应用，把自己注册为默认浏览器，按域名/来源 App 规则把每个链接自动路由到正确的浏览器，无匹配时回退到首选浏览器或弹出选择器。　|　技术栈：Swift 6, SwiftUI, AppKit, Swift Concurrency (actor/async), Swift Testing, Apple Events (kAEGetURL), Launch Services, Sparkle, LaunchAtLogin, Xcode/xcodebuild, GitHub Actions
- **亮点**：整洁的分层架构 Core/Infrastructure/Features/DesignSystem，协议+依赖注入，可测试性极佳；扎实的系统级 macOS 功底：kAEGetURL 取 sender PID 识别来源 App、嵌套 .app bundle 归一化、LSSetDefaultHandler 用户拒绝推断；并发设计地道：actor 化 RuleStore 的原子 load+append、AsyncStream 观察、ContinuousClock + 可注入 now 的 LoopGuard；生产级发布链路：Developer ID 签名+notarytool 公证+stapler+Sparkle appcast(ed25519)+构建号单调性校验；DomainMatcher 处理通配符特异性打分与 punycode/Unicode 等价归一化等真实边界
- **短板**：纯本地单机工具，规则模型仅 domain/sourceApp 两类，无路径/正则/正则组合等更复杂匹配；DefaultBrowserStatus 用 5 秒轮询而非事件通知，略显粗放；0 star、单次提交，缺乏真实社区验证与长期维护佐证
- **证据**：Portal/Core/Routing/URLRouter.swift:61 自源 selfSource 防无限循环；:69-90 区分 load 失败与空规则以免覆盖 rules.json；Portal/Infrastructure/SourceAppDetection/AppleEventSourceAppDetector.swift:77-85 抓取 kAEGetURL 的 keySenderPIDAttr；:136-153 outermostApplicationURL 向上归一化嵌套 .app；Portal/Infrastructure/Persistence/JSONFileRuleStore.swift:3 actor；:35-44 重写 append 为单 actor 跨度原子 load+save；Portal/Core/Routing/LoopGuard.swift:13-42 actor + ContinuousClock + 可注入 now，滑动窗口阈值限频；Portal/Infrastructure/DefaultBrowser/LaunchServicesDefaultBrowserService.swift:32-39 重查现状推断 userDeclined；:118-123 解码具体 OSStatus；.github/workflows/release.yml:198-223 校验 tag 与版本一致、构建号相对上次 appcast 单调递增；:293-314 Sparkle generate_appcast；PortalTests/Routing/URLRouterTests.swift 使用 Swift Testing(@Suite/@Test/#require) + async actor mock，约 60 个测试文件；.swiftlint.yml force_unwrapping=error, cyclomatic_complexity=10；.swiftformat --swiftversion 6
- **AI 参与**：medium 置信；信号：2026-06 创建，默认按 AI-era 处理, 整仓只有一个 squashed commit（58bc8a2），提交者为 zhangyu1818-bot，无迭代历史，符合 AI 辅助一次性产出的形态, 注释风格高度统一，均为解释非显然决策的 rationale 式注释（如 router.route 里 selfSource/loop 防护、JSONFileRuleStore 的 atomic load+append 说明），密度低而精准, 约 60 个测试文件覆盖面异常齐全且命名/结构高度模式化，类似系统化生成, 无 CLAUDE.md/AGENTS.md/.cursor 等显式 AI 工具配置
  - 把控评估：高把控。架构分层清晰、模块边界明确（协议抽象 + DI + 测试 mock 一一对应），系统级细节（Apple Event sender PID、LS 用户拒绝推断、嵌套 bundle 归一化、actor 原子写、loop guard）属非平凡人工定制，注释只点关键决策，CI 公证/Sparkle 链路需真实账户与领域知识——整体像一位资深开发者用 AI 加速并严格收口，而非无脑生成。
- **年代背景**：2026 年中，Swift 6 严格并发、Swift Testing、macOS 默认浏览器/Apple Event API 都已成熟，且 AI 辅助高质量样板已普及；在此背景下作者交付了架构连贯、系统调用地道、发布链路完整的应用，体现出对 AI 产出的良好把控而非堆砌。

### 2026-06-05 · skills　(功能8/代码8/技术7)
- **定位**：个人维护的一组 AI Agent「技能」定义（SKILL.md 指令规范 + openai.yaml 代理元数据），覆盖深度研究、写规格、macOS 生命周期/麦克风权限、Tailwind 安装、PR Codex 评审循环、浏览器调试等工程工作流。　|　技术栈：Markdown (SKILL.md 指令规范), Node.js ESM (.mjs), GitHub GraphQL API, gh CLI, OpenAI/Codex agent metadata (YAML), Swift/SwiftUI/AppKit (技能内容领域), Chrome DevTools MCP
- **亮点**：技能规范极其细致专业，分层/边界/反模式清晰；macOS 权限技能展现真实深域知识（AVCaptureDevice vs AVAudioApplication、audio-input vs device.microphone 熵限区分）；pr-review-loop.mjs 是地道的 GraphQL 分页+轮询脚本，错误处理与退出码设计到位；deep-research 的证据分级/证据门/对抗性证伪流程设计成熟；每个技能配套独立 references 与 openai.yaml，模块边界一致
- **短板**：web-debug-browser/SKILL.md 引用路径写成 @skills/web-debug-browse/... 丢了结尾 r，三条 reference 链接全部失效；无 package.json/lockfile/测试/CI，.mjs 脚本未纳入任何工程化校验；setup-tailwindcss 等技能偏薄，价值不及 writing-spec/deep-research；纯个人用途、0 star、无对外文档化的安装/使用说明
- **证据**：skills/web-debug-browser/SKILL.md:35-37 引用 @skills/web-debug-browse/... 与实际目录 web-debug-browser 不符（确认目录名带 r），断链；skills/gh-pr-codex-review-loop/scripts/pr-review-loop.mjs:180-293 用游标对 comments/reactions/reviews/reviewThreads 四路并行分页，逻辑严谨；pr-review-loop.mjs:411 用 process.exit(10) 区分『有可处理反馈』退出码，CLI 设计专业；skills/macos-microphone-permission/SKILL.md:66-80 精确区分 com.apple.security.device.audio-input 与 device.microphone 的适用场景；skills/deep-research/SKILL.md:22-30 定义 Tier0-Tier5 证据分级与冲突优先级；skills/writing-spec/SKILL.md:69-83 严格定义 RFC 2119 术语使用边界，含 Anti-Code Rewrite Rules；git log 仅 1 个 commit，作者 zhangyu1818-bot <zhangyu1818-bot@qq.com>，与 git-github-write-as-bot 技能配置一致
- **AI 参与**：high 置信；信号：仓库本质即 AI Agent 技能库，每个目录含 SKILL.md + agents/openai.yaml（Codex 技能格式）, deep-research/SKILL.md 列举大量 mcp__* 工具名（deepwiki/perplexity/brave/exa/tavily/context7/github），属典型 AI 工具调用编排, 唯一 commit 由 bot 身份 zhangyu1818-bot 提交，与作者自写的 git-github-write-as-bot 技能一致, writing-spec/deep-research 文档风格高度统一、密集 RFC 2119 规范化，符合 LLM 协同产出特征, 2026 年创建，本身就是为 AI 代理消费而设计的产物
  - 把控评估：作者对 AI 的把控属上乘水平。这不是无脑堆砌的生成物：技能边界清晰（每个技能含 When to Use / Do Not / 反模式），领域知识非平凡（macOS TCC/Hardened Runtime、GraphQL 分页、证据分级方法论），且作者把自己的工程习惯固化进了可复用规范（如 bot 身份提交、PR 评审循环的缺陷分类规则）。.mjs 脚本是真正可运行、有错误处理与退出码语义的人工把控产物，而非样板。唯一 web-debug-browse 断链说明缺少最终自校验，但整体架构连贯、品味在线。
- **年代背景**：2026 年中 Agent Skills 已是主流范式（Claude/Codex 的 SKILL.md 生态成熟），用这种结构沉淀个人工作流是当年顺势且有品味的做法；按当年标准看，技能规范的深度与一致性高于普通水平。

### 2026-06-07 · cue　(功能9/代码9/技术9)
- **定位**：一个 macOS 菜单栏应用：在任意 App 中选中文字后，于选区旁弹出浮动菜单，调用 LLM 完成翻译/改写/解释等并就地展示结果。　|　技术栈：Swift 6.2, SwiftUI, AppKit, Swift Concurrency (actor/MainActor), Accessibility API (AXUIElement/AXObserver), Swift Package Manager, Swift Testing, Sparkle 自动更新, GitHub Actions CI
- **亮点**：六模块 SwiftPM 分层架构，职责清晰、协议解耦、App target 极薄；深度 Accessibility 工程：AXObserver C 回调、text marker range、AppKit/AX 坐标转换；纯函数式状态机+session/request ID 守卫，彻底处理异步竞态与取消；NSPanel 重写私有 _hasActiveAppearance 系列实现非激活悬浮面板；生产级 CI：Developer ID 签名/公证/DMG/Sparkle EdDSA appcast 全自动；129 个测试覆盖 reducer/provider/选区解析/几何布局等核心逻辑
- **短板**：Provider 仅一次性请求、未实现流式（README/CLAUDE 也承认从 one-shot 起步）；OpenAIResponseDecoder 等假定标准 chat/completions 结构，对非标准兼容端点容错有限；单 commit 提交，无法从历史观察真实开发演进
- **证据**：Packages/CueCore/Sources/CueSelection/AXClient.swift:143 通过 kAXAttributedStringForTextMarkerRangeParameterizedAttribute 处理 WebKit/PDF 的 text marker range；Packages/CueCore/Sources/CueSelection/AXSelectionObserver.swift:186-221 AXObserverCreate + Unmanaged.passUnretained + CFRunLoopAddSource 的完整 C 桥接；Packages/CueCore/Sources/CueTranslationDomain/SessionController.swift:110-136 用 activeSessionID/activeRequestID 守卫丢弃陈旧响应并区分取消/失败；Packages/CueCore/Sources/CueOverlaySupport/OverlayPanelHost.swift:13-37 重写 _hasActiveAppearance 等私有方法保持非 key 面板的激活外观；Packages/CueCore/Sources/CueOverlaySupport/OverlayPlacementPolicy.swift:197-231 above/below 回退排序 + 屏幕可见区夹取的纯几何布局；Packages/CueCore/Sources/CueAppSupport/AppCoordinator.swift:76 使用 Swift 6.2 isolated deinit；.github/workflows/release.yml:108 注释明确『Never pass --deep…it corrupts the XPC signatures』体现签名链知识；Packages/CueCore/Tests/CueTranslationDomainTests/SessionControllerTests.swift:88 lateSuccessFromPreviousSessionDoesNotPolluteNewSession 测试陈旧响应不污染新会话
- **AI 参与**：high 置信；信号：根目录存在详尽的 CLAUDE.md（含给 Codex 的提示规范、技能加载、架构/测试规则）, .claude/skills 下挂载了 swift-concurrency/swift-testing-expert/swiftui-expert-skill 等代理技能，并有 skills-lock.json 记录来源哈希, .mcp.json 配置 apple-docs MCP，表明 AI 辅助查阅 Apple 文档的工作流, 整个项目以单次 squash commit『feat: add Cue menu bar translation app』提交，无迭代历史, 代码风格、命名、注释高度统一，模块边界与测试覆盖呈规划性产出特征
  - 把控评估：作者对 AI 的把控属高水平。CLAUDE.md 把平台约束（Swift 6 only、Concurrency 而非回调、模块化以便 swift test、provider 不泄漏 OpenAI 类型、UI 主线程隔离、取消贯穿）写成可执行规范，产出的代码严格落地：六个库职责单一、边界用协议隔离、129 个测试覆盖核心逻辑、零强解包、生产级签名公证 CI。Accessibility text marker、private NSPanel API、AX/AppKit 坐标转换等是 AI 难以凭空稳定生成、需人工领域品味与验证的部分——表明作者主导架构与集成，而非堆砌生成物。
- **年代背景**：创建于 2026-06，正处 Swift 6.2 / macOS 26（Liquid Glass）落地期，作者用上 isolated deinit、Swift Testing、apple-docs MCP 与代理技能等当年最新工具链，并以 AI 辅助高质量交付，完全契合该时间点的工程前沿。

</details>

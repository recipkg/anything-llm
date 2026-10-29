# 来源覆盖与验证状态

**状态：提取中；没有运行 AnythingLLM，也没有进行独立重建。**

## 固定来源

- 上游仓库：[Mintplex-Labs/anything-llm](https://github.com/Mintplex-Labs/anything-llm/tree/9b1fcab141000eaba9f78ed131151de04904454b)，标签 v1.19.0，提交 9b1fcab141000eaba9f78ed131151de04904454b。
- 上游 LICENSE 声明 MIT；根目录的 TERMS_SELF_HOSTED.md 另外描述自托管的数据位置、可选遥测与第三方提供方传输。这里记录来源声明，不构成隐私或法律审查。
- GitHub 仓库元数据在 2026-10-29 查询为 67,689 stars；星数是时间快照，不是质量或完整性证明。
- 本次源码检查读取根 README、LICENSE、LICENSE_HISTORY、LICENSE_NOTICE、TERMS_SELF_HOSTED.md、server、frontend、collector、docker 和 cloud-deployments 的选定内容。没有检出 embed、浏览器扩展、extras、完整图片/本地化资源或所有部署模板；这些均不在已审阅覆盖范围。

## 固定提交的源码观察

- README 将产品描述为自托管 AI 应用，概述多模型、文档摄取、workspace、Agent、MCP、Agent Flow、多用户、向量库及 API。
- README 技术概览区分 Vite/React frontend、Node/Express server、Node/Express collector；自托管部署与外置嵌入组件、浏览器扩展另有边界。
- server/index.js 注册 workspace、document、chat、Agent WebSocket、skills whitelist、MCP server、Agent Flow、scheduled jobs、memory、mobile、embedded 和 API 路由。具体请求/响应和全量兼容性尚未提炼。
- server/utils/agents/defaults.js 将 Agent 工具合并自内置、系统配置、社区导入插件、Agent Flow 和 MCP；默认技能、可配置技能、子技能可用性、单用户限制分开处理。
- server/utils/agents/imported.js 从 storage 中的插件清单加载 handler.js；固定清单格式为 skill-1.0.0。源码路径检查不证明插件有沙箱或完整权限隔离。这个系统是可执行 JavaScript 扩展，不能与 Recipkg 的 Markdown SKILL.md 管理方式混为一谈。
- server/utils/agents/aibitat/utils/toolReranker.js 以提示和工具描述重排技能；固定代码默认 top-N 为 15、除非环境变量明确关闭，否则启用；异常时返回原工具集。其性能、数据路径和实际重排效果未运行验证。
- server/utils/agents/aibitat/plugins/websocket.js 包含 WebSocket 批准、取消、超时和白名单路径；默认等待 120 秒。http-socket.js 的 Telegram 审批入口另行处理无可用上下文的情况；ImportedPlugin.createToolApprovalFn 在没有审批 API 时返回批准。入口差异只来自源码观察，必须逐入口验收，不能概括成统一安全保证。
- server/utils/MCP 将配置服务转换成 Agent 工具；server/endpoints/mcpServers.js 提供管理员服务列表、重载、启停和工具屏蔽接口。完整配置、所有传输模式和故障恢复未覆盖。
- server/utils/agentFlows 当前源码中的步骤类型包括 start、API call、LLM instruction、web scraping；执行器按顺序运行，失败停止，direct output 提前结束。尚未运行端到端流程。
- frontend/src/pages/WorkspaceChat/index.jsx 在非移动设备显示主导航侧栏；聊天页通过 workspace 和 thread 加载历史。AgentSkills、MCPServers、AgentFlows 等有独立设置界面。没有浏览器截图或视觉/无障碍测试。
- 上游测试文件含 Agent defaults、社区技能审批、MCP、Agent Flow 和工具重排相关用例。本次只阅读部分测试名称/源码，没有执行上游测试。

## Recipkg 依赖

- quality 固定到 Recipkg 7f05425ae9843b7e8ce15cb80917977eedb36bdd 的 recipes/software-quality。它是代码质量、设计和性能证据合同，不是 AnythingLLM 运行时依赖。
- design 固定到 recipkg/design-directions 提交 6fdba350d1effa2d50dc0185095bb91ca7a699ee，递归包含 design-foundations 提交 8c5bf1f1e40719789cf51bc0dfd8f5aeecae0538。目录状态称其为可复用首版材料，不等于产品 UI 已验收。
- recipkg extract 和 recipkg discover 已分别生成标准分析提示词；依赖职责根据本地标准库配方、来源和覆盖材料审阅后确定。它们不是上游产品行为证据。

## 未验证与缺口

- 没有启动服务、运行上游测试、调用模型、摄取真实文件、查询向量库、执行 MCP/Agent Flow、测试定时任务/Telegram 或测量性能。
- 没有独立实现或重建；ACCEPTANCE.md 是待执行计划。
- 没有通过浏览器检查视觉层级、屏幕阅读器、窄屏、主题、拖放或加载状态。
- 未提炼完整 workspace/API 模式、所有模型/嵌入/向量提供方、文档格式、OCR、分块/引用、文件大小边界、用户/角色矩阵、迁移/备份、错误恢复、所有技能配置、插件安全、导入协议、Agent Flow schema、MCP 传输与 OAuth、计划任务、记忆和多模态接口。
- 未验证自托管隐私/遥测声明、断网运行、所有部署渠道或第三方服务的数据处理。
- 无独立构建、兼容性、性能、可访问性或安全结论。不得将上游文档、静态源码观察、recipkg check 或成功打包改写成这些验收已通过。

继续提取前先固定缺口范围；新证据要关联到确切版本、输入、配置和观察结果。

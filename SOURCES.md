# 来源与许可记录

## 上游固定版本

- 项目：[AnythingLLM](https://github.com/Mintplex-Labs/anything-llm)
- 标签：[v1.19.0 release](https://github.com/Mintplex-Labs/anything-llm/releases/tag/v1.19.0)，发布于 2026-10-26。
- 固定提交：[9b1fcab141000eaba9f78ed131151de04904454b](https://github.com/Mintplex-Labs/anything-llm/tree/9b1fcab141000eaba9f78ed131151de04904454b)。
- GitHub 星数快照：2026-10-29 查询到 67,689。
- 根目录许可证：[MIT LICENSE](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/LICENSE)。固定仓库还列有 LICENSE_HISTORY 和 LICENSE_NOTICE；根许可证不自动覆盖独立仓库、子模块、模型、字体、图像或第三方服务。
- 自托管数据声明：[TERMS_SELF_HOSTED.md](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/TERMS_SELF_HOSTED.md)。这是上游说明，不是本次独立测量或法律意见。

## 本配方读取的源码与文档

以下链接指向固定提交，便于复核：

- [README 产品概览与技术组成](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/README.md)
- [Server 路由注册](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/server/index.js)
- [内置技能、配置技能、MCP、Flow 汇合](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/server/utils/agents/defaults.js)
- [导入技能加载与审批包装](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/server/utils/agents/imported.js)；[技能清单 schema](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/server/utils/agents/imported-manifest.schema.json)
- [技能工具重排](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/server/utils/agents/aibitat/utils/toolReranker.js)；[WebSocket 工具审批](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/server/utils/agents/aibitat/plugins/websocket.js)；[工具白名单](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/server/models/agentSkillWhitelist.js)
- [MCP 兼容层](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/server/utils/MCP/index.js)
- [Agent Flow 执行器](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/server/utils/agentFlows/executor.js)；[步骤类型](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/server/utils/agentFlows/flowTypes.js)
- [workspace chat 页面入口](https://github.com/Mintplex-Labs/anything-llm/blob/9b1fcab141000eaba9f78ed131151de04904454b/frontend/src/pages/WorkspaceChat/index.jsx)
- [Agent 与 MCP 相关上游测试目录](https://github.com/Mintplex-Labs/anything-llm/tree/9b1fcab141000eaba9f78ed131151de04904454b/server/__tests__)

官方在线文档可作为进一步核对的参考，不作为固定版本接口的唯一证据：[Agent 智能技能选择](https://docs.anythingllm.com/agent/intelligent-tool-selection)、[Agent Flow](https://docs.anythingllm.com/agent-flows/overview)、[MCP](https://docs.anythingllm.com/mcp-compatibility/overview)。

## Recipkg 依赖审阅

- quality：[software-quality](https://github.com/recipkg/recipkg/tree/7f05425ae9843b7e8ce15cb80917977eedb36bdd/recipes/software-quality)，固定 Recipkg 提交 7f05425ae9843b7e8ce15cb80917977eedb36bdd。职责是重建的设计、代码品味、错误恢复、性能和证据合同；不是产品运行库。
- design：[design-directions](https://github.com/recipkg/design-directions/tree/6fdba350d1effa2d50dc0185095bb91ca7a699ee)，固定提交 6fdba350d1effa2d50dc0185095bb91ca7a699ee。其清单递归固定 [design-foundations](https://github.com/recipkg/design-foundations/tree/8c5bf1f1e40719789cf51bc0dfd8f5aeecae0538)，提交 8c5bf1f1e40719789cf51bc0dfd8f5aeecae0538。这两个配方提供界面选择与验收合同，不是 AnythingLLM 源码。
- 已阅读相关清单、来源和验收文档；依赖状态只表示材料已固定和审阅，不表示 AnythingLLM 已完成重建。

## 证据边界

本配方不包含 AnythingLLM 实现源码、二进制、图片文件或安装钩子。源码链接、上游许可证标识和公开文档用于出处说明；本配方没有作完整许可兼容、隐私合规或安全审计。COVERAGE.md 区分源码观察、产品实测与未验证项目。

# AnythingLLM 自托管 AI 工作区配方

```toml
format = "recipkg/1"

[package]
name = "anything-llm"
version = "0.1.0"
kind = "software"
description = "自托管 AI 工作区：文档检索、对话、Agent 工具与多用户管理。"
entry = "BUILD_PROMPT.md"

[dependencies.quality]
git = "https://github.com/recipkg/recipkg.git"
rev = "7f05425ae9843b7e8ce15cb80917977eedb36bdd"
subdir = "recipes/software-quality"

[dependencies.design]
git = "https://github.com/recipkg/design-directions.git"
rev = "6fdba350d1effa2d50dc0185095bb91ca7a699ee"
```

来源固定为 [AnythingLLM v1.19.0](https://github.com/Mintplex-Labs/anything-llm/tree/9b1fcab141000eaba9f78ed131151de04904454b)，上游根目录声明 MIT。这里提炼的是可观察行为和重建要求，不含上游源码、运行钩子或二进制。

目标是可自托管的 Web AI 工作区：用户建立 workspace，连接模型，导入文档，以带来源的回答查询知识，并按权限使用 Agent、MCP、社区技能和流程。浏览器扩展、桌面客户端与独立嵌入组件未纳入本版范围；详见 COVERAGE.md。

quality 提供软件设计、代码质量和性能记录合同；design 提供按产品任务选择的视觉方向，并递归依赖固定版本的 design-foundations。它们是配方依赖，不是 AnythingLLM 的运行时库。依赖来源、用途和状态见 SOURCES.md。

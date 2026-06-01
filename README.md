<p align="center">
  <a href="https://daluobo.cc.cd/?utm_source=github&utm_medium=readme&utm_campaign=show_readme">
    <img src="https://daluobo.cc.cd/daluobo-logo.png" alt="大萝卜 Logo" width="96" height="96" />
  </a>
</p>

<h1 align="center">大萝卜 AI 模型中转站</h1>

<p align="center">
  <a href="https://daluobo.cc.cd/?utm_source=github&utm_medium=readme&utm_campaign=show_readme">进入官网</a>
  ·
  <a href="https://daluobo.cc.cd/pricing?utm_source=github&utm_medium=readme&utm_campaign=show_readme">查看模型价格</a>
  ·
  <a href="https://daluobo.cc.cd/console?utm_source=github&utm_medium=readme&utm_campaign=show_readme">打开控制台</a>
</p>

## 这是什么

大萝卜是一个面向开发者和 AI 工具用户的 OpenAI 兼容 API 中转站。你可以把它作为 Codex、Cherry Studio、Lobe Chat、OpenCat、DeepChat、OpenAI SDK、Continue、VS Code 插件等客户端的 `base_url`，用统一的 API Key 调用不同模型。

核心地址：

```text
Base URL: https://api.daluobo.cc.cd/v1
官网: https://daluobo.cc.cd
Codex 接入: https://daluobo.cc.cd/codex
Logo: https://daluobo.cc.cd/daluobo-logo.png
```

## 适合谁

- 想找 OpenAI Compatible API、OpenAI 兼容接口、AI API 中转站的用户。
- 想把 Codex CLI / Codex Agent 接入自定义 `base_url` 的开发者。
- 想用 Cherry Studio、Lobe Chat、OpenCat、DeepChat 等客户端配置统一 API Key 的用户。
- 想用支付宝小额充值、按量使用、查看日志和余额的个人用户。
- 想在本地项目目录里继续让 Codex 读文件、跑命令、调浏览器，而不是上传整个项目到云端的开发者。

## 主要特性

- OpenAI 兼容 API：统一使用 `https://api.daluobo.cc.cd/v1`。
- Codex 本地接入：配置一次，继续在本地运行 `codex` 或 `codex -p daluobo`。
- 本地文件边界清晰：文件读取、Shell、浏览器调试和 MCP 仍发生在你的电脑上。
- 支付宝充值：适合国内用户小额体验和持续按量使用。
- 模型广场：查看可用模型、分组和价格。
- 用量日志：控制台查看 API 调用和额度消耗。
- 红包广场：支持额度红包和口令红包，适合社群活动和新用户体验。

## 快速开始

1. 打开控制台并注册：

```text
https://daluobo.cc.cd/console
```

2. 创建 API Key。

3. 使用 OpenAI 兼容地址：

```text
https://api.daluobo.cc.cd/v1
```

4. 用最小请求测试：

```bash
curl https://api.daluobo.cc.cd/v1/models \
  -H "Authorization: Bearer YOUR_API_KEY"
```

## Codex 接入

如果你正在搜索这些问题：

- Codex 自定义 base_url 怎么配置
- Codex OpenAI compatible API 怎么用
- Codex 如何使用中转 API
- Codex 读取本地项目文件但模型走自定义 API
- Codex 配置 OpenAI 兼容接口

可以直接看这里：

```text
https://daluobo.cc.cd/codex
```

推荐配置形态：

```toml
model_provider = "daluobo"
model = "gpt-5.5"
disable_response_storage = true
model_reasoning_effort = "medium"

[model_providers.daluobo]
name = "daluobo"
wire_api = "responses"
requires_openai_auth = false
env_key = "DALUOBO_API_KEY"
base_url = "https://api.daluobo.cc.cd/v1"
```

使用方式：

```bash
codex -p daluobo
```

## 常见客户端关键词

这些客户端通常可以配置 OpenAI 兼容接口、API Key 和 Base URL：

- Codex CLI / Codex Agent
- Cherry Studio
- Lobe Chat
- OpenCat
- DeepChat
- Continue
- VS Code AI 插件
- OpenAI SDK
- LangChain / LlamaIndex 等开发框架

## 搜索关键词

如果你是从 GitHub、Google、Bing、百度、开发者社区搜索来的，可以关注这些关键词：

```text
AI API 中转站
OpenAI API 中转
OpenAI 兼容 API
OpenAI Compatible API
Codex base_url
Codex 自定义 API
Codex OpenAI compatible
Codex 本地 Agent
Cherry Studio 中转 API
Lobe Chat OpenAI 兼容接口
OpenCat API Key
DeepChat API 配置
支付宝充值 API 中转站
NewAPI 中转站
大模型 API 聚合
模型聚合 API
gpt-5.5 API
gpt-5 API
gpt-image-2 API
```


## 价格与充值

- 支持支付宝网页支付。
- 控制台可查看余额和用量日志。
- 模型价格以模型广场展示为准：

```text
https://daluobo.cc.cd/pricing
```

## 红包广场

大萝卜支持额度红包和口令红包。管理员或用户可以把自己的额度发成红包，用于群内体验、教程活动、新用户试用和社区裂变。

入口：

```text
https://daluobo.cc.cd/console/activity/redpacket
```

## 注意事项

- 大萝卜是 OpenAI 兼容 API 服务，不是 OpenAI 官方网站。
- 请勿把 API Key 发布到公开仓库、截图或聊天群。
- 请勿用于违反法律法规或平台规则的用途。
- 模型可用性、价格和路由策略以官网控制台展示为准。

## 立即体验

官网：

```text
https://daluobo.cc.cd/?utm_source=github&utm_medium=readme&utm_campaign=show_readme
```

Codex 接入教程：

```text
https://daluobo.cc.cd/codex?utm_source=github&utm_medium=readme&utm_campaign=show_readme
```

模型价格：

```text
https://daluobo.cc.cd/pricing?utm_source=github&utm_medium=readme&utm_campaign=show_readme
```

控制台：

```text
https://daluobo.cc.cd/console?utm_source=github&utm_medium=readme&utm_campaign=show_readme
```

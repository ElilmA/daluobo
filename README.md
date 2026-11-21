<p align="center">
  <a href="https://daluobo.cc.cd/?utm_source=github&utm_medium=readme&utm_campaign=show_readme">
    <img src="./assets/daluobo-logo.png" alt="大萝卜 Logo" width="96" height="96" />
  </a>
</p>

<h1 align="center">大萝卜 · AI 模型中转站</h1>

<p align="center">
  <b>一个 Key 调用 GPT / Claude / Gemini / Grok / DeepSeek</b><br/>
  <b>1 美元充值 = 1 美元余额，用多少扣多少，没有倍率</b><br/>
  <b>相比官方定价最高便宜 95%</b>
</p>

<p align="center">
  <a href="https://daluobo.cc.cd/?utm_source=github&utm_medium=readme">进入官网</a>
  ·
  <a href="https://daluobo.cc.cd/pricing?utm_source=github&utm_medium=readme">实时价格</a>
  ·
  <a href="https://daluobo.cc.cd/sign-up?aff=PaJj&utm_source=github&utm_medium=readme"><strong>注册领 $0.5</strong></a>
  ·
  <a href="https://daluobo.cc.cd/setup?utm_source=github&utm_medium=readme">5 分钟接入</a>
  ·
  <a href="https://github.com/ElilmA/daluobo-api-examples"><strong>代码示例</strong></a>
</p>

---

## 为什么用它

| | |
|---|---|
| **1:1 计价** | 充 $1 就是 $1 余额，按官方价折算比例扣费，没有充值倍率、没有隐藏加价 |
| **价格远低于官方** | 走批量采购与多路上游，GPT / Grok / DeepSeek 等主力模型比官方定价低 85%–95% |
| **无审查模型** | 提供 `deepseek-v4.1-flash-uncensored`，无过滤、无拒答，适合角色扮演与创作 |
| **OpenAI 兼容** | 只要客户端能改 `base_url` 就能用：Cherry Studio、Lobe Chat、OpenCat、Cline、Continue、LangChain… |
| **一个 Key 通吃** | GPT-6 / Claude / Gemini / Grok / DeepSeek / GLM / Qwen / Kimi 全部走同一个 Key 和同一个余额 |

## 价格对比（每 100 万 tokens，输入 / 输出，美元）

| 模型 | 官方参考价 | 本站价 | 便宜 |
|---|---|---|---|
| Grok 4.5 / 4.6 / 4.7 | 2 / 6 | **0.10 / 0.30** | 95% |
| GPT-6 Astra | 10 / 50 | **0.60 / 3.00** | 94% |
| GPT-6 · 6.1 · 6.2 Sol | 2 / 10 | **0.12 / 0.60** | 94% |
| GPT-5.6 Sol | 4 / 20 | **0.24 / 1.20** | 94% |
| GPT-5.6 Terra | 2 / 12 | **0.12 / 0.72** | 94% |
| GLM-5.2 / 5.3 | 1.4 / 4.4 | **0.105 / 0.33** | 92% |
| Qwen3.8 Max | 2 / 6 | **0.20 / 0.60** | 90% |
| Gemini 4 Argon | 4 / 20 | **0.48 / 2.40** | 88% |
| DeepSeek V4 Pro | 1.32 / 3.96 | **0.198 / 0.594** | 85% |
| DeepSeek V4 Flash | 0.30 / 1.20 | **0.045 / 0.18** | 85% |
| Claude Opus / Sonnet | 5 / 25 | **2.36 / 11.81** | 53% |
| Kimi K3.1 Pro | 2 / 10 | **0.96 / 4.80** | 52% |

> 官方参考价仅用于对比，可能随上游调整；**实际计费以 [实时价格页](https://daluobo.cc.cd/pricing) 为准**。

## 无审查模型

除了常规模型，本站提供两个去掉安全过滤的 DeepSeek：

```text
deepseek-v4.1-flash-uncensored
deepseek-v4.1-flash-uncensored-fast
```

适合角色扮演、小说续写、需要直给答案的场景。价格约为官方 DeepSeek 的一半，和其他模型共用同一个 Key 与余额。

## 快速开始

### curl

```bash
curl https://api.daluobo.cc.cd/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $DLB_API_KEY" \
  -d '{
    "model": "gpt-6.2-astra",
    "messages": [{"role": "user", "content": "用一句话解释什么是向量数据库"}]
  }'
```

### Python（OpenAI SDK）

```python
from openai import OpenAI

client = OpenAI(
    api_key="sk-你的大萝卜Key",
    base_url="https://api.daluobo.cc.cd/v1",
)

resp = client.chat.completions.create(
    model="deepseek-v4.1-flash-uncensored",
    messages=[{"role": "user", "content": "写一段赛博朋克开场白"}],
)
print(resp.choices[0].message.content)
```

### Node.js

```js
import OpenAI from "openai";

const client = new OpenAI({
  apiKey: process.env.DLB_API_KEY,
  baseURL: "https://api.daluobo.cc.cd/v1",
});

const r = await client.chat.completions.create({
  model: "claude-sonnet-5",
  messages: [{ role: "user", content: "hello" }],
});
console.log(r.choices[0].message.content);
```

更多可直接运行的示例：[ElilmA/daluobo-api-examples](https://github.com/ElilmA/daluobo-api-examples)

## 客户端配置

| 客户端 | Base URL | 说明 |
|---|---|---|
| Cherry Studio | `https://api.daluobo.cc.cd/v1` | 添加 OpenAI 兼容服务商，填 Key |
| Lobe Chat | `https://api.daluobo.cc.cd/v1` | 同上 |
| Cline / Roo Code | `https://api.daluobo.cc.cd/v1` | Provider 选 OpenAI Compatible |
| Continue | `https://api.daluobo.cc.cd/v1` | `provider: openai` + `apiBase` |
| OpenAI SDK | `https://api.daluobo.cc.cd/v1` | `base_url` 必须带 `/v1` |
| LangChain | `https://api.daluobo.cc.cd/v1` | `ChatOpenAI(base_url=...)` |

> 如果客户端报 `request failed` 且返回内容是 HTML，通常是 Base URL 少了 `/v1`。

## 免费额度

- **注册即送 $0.5**，可直接用于全部模型，先试再充
- **每日签到**随机送 $0.004–$0.02
- **邀请好友**：好友首充后，双方各得 $1

注册入口：<https://daluobo.cc.cd/sign-up?aff=PaJj>（支持 GitHub / Telegram 登录）

## 常见问题

**Q：这是官方的 OpenAI / Claude 吗？**
A：不是。本站是 OpenAI 兼容的第三方 API 聚合服务，通过多路上游路由提供模型能力，与 OpenAI、Anthropic、Google、DeepSeek 均无隶属关系。

**Q：余额会过期吗？**
A：不会。充值余额长期有效，按实际 token 用量扣费。

**Q：支持流式输出和工具调用吗？**
A：Chat Completions、SSE 流式、常见 function calling 已验证可用；个别不常见的厂商扩展格式取决于当前上游路由。

**Q：最低充多少？**
A：¥7.2（= $1）。支持微信/支付宝、GGsel 兑换码、USDT、国际卡。

**Q：Key 安全吗？**
A：Key 只在你自己的控制台可见，请勿提交到公开仓库或截图外发。

## 相关链接

```text
官网            https://daluobo.cc.cd
实时价格        https://daluobo.cc.cd/pricing
接入文档        https://daluobo.cc.cd/setup
API Base URL    https://api.daluobo.cc.cd/v1
代码示例        https://github.com/ElilmA/daluobo-api-examples
```

## 搜索关键词

如果你是从 GitHub / Google / Bing / 百度 / 开发者社区搜过来的，以下关键词都能找到本站：

```text
AI API 中转站 · OpenAI API 中转 · OpenAI 兼容 API · OpenAI Compatible API
Codex base_url · Codex 自定义 API · Codex OpenAI compatible
Cherry Studio 中转 API · Lobe Chat OpenAI 兼容接口 · OpenCat API Key · DeepChat API 配置
NewAPI 中转站 · 大模型 API 聚合 · 模型聚合 API
DeepSeek API 中转 · Claude API 中转 · Gemini API 中转 · Grok API
无审查模型 · uncensored LLM API
免费 API 额度 · 每日签到 免费额度 · 邀请奖励 API 中转站
```

## 注意事项

- 本站是 OpenAI 兼容 API 服务，不是 OpenAI 官方网站。
- 模型可用性、价格和路由策略以官网控制台展示为准。
- 请勿用于违反法律法规或平台规则的用途。

<p align="center">
  <sub>Built on <a href="https://github.com/QuantumNous/new-api">NewAPI</a></sub>
</p>

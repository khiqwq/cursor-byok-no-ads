<div align="center">

# cursor-byok

cursor-byok 是 Cursor 后端的本地实现。
<br>
<br>
[上游项目](https://github.com/leookun/cursor-byok) · [问题反馈](https://github.com/leookun/cursor-byok/issues) · [English](./README.md)

[![License](https://img.shields.io/github/license/leookun/cursor-byok?style=flat-square)](./LICENSE)
[![Platforms](https://img.shields.io/badge/platform-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey?style=flat-square)](https://github.com/leookun/cursor-byok/releases/latest)

</div>

> 这是基于 [leookun/cursor-byok](https://github.com/leookun/cursor-byok) 的个人修改版：
> 已移除上游广告服务、广告资源缓存和广告入口；其余源代码按原项目许可证提供。

![cursor-byok 支持接入多种模型 API](./images/cn-brand.png)

![cursor-byok 主界面](./images/cn-home.png)

## 项目介绍

cursor-byok 是一个开源的 Cursor 本地模型接入工具。它通过运行在本机的服务连接 Cursor 与你配置的模型 API，让模型请求使用自己的渠道处理，同时保留 Cursor Agent 的工具调用、Skills 和 MCP 等能力。

你可以接入 OpenAI、Anthropic 及其兼容服务，自由配置接口地址、模型、密钥和请求参数，不再局限于平台预设的模型渠道。

> [!IMPORTANT]
> cursor-byok 本身免费开源，但你接入的模型 API 可能由对应服务商收费。本项目不是 Cursor 官方产品，与 Cursor 或其开发公司无隶属关系。

## 核心能力

- **自定义模型渠道**：配置自己的 API 地址、访问密钥和模型标识。
- **多种接口协议**：支持 OpenAI、Anthropic 兼容接口及自定义端点。
- **模型管理**：添加、复制、编辑、排序和批量测试多个模型配置。
- **连接性能测试**：查看首字延迟、生成速度与模型服务的原始响应。
- **Agent 工作流**：支持工具调用、Skills、MCP 和多轮会话。
- **会话统计**：查看 Token 消耗、缓存命中率、对话轮次和价值估算。
- **跨平台运行**：支持 macOS、Windows 和 Linux。

## 快速开始

1. 从 [GitHub Releases](https://github.com/leookun/cursor-byok/releases/latest) 下载对应平台的最新版本。
2. 启动 cursor-byok，打开“模型配置”，填写接口地址、API Key 和模型标识。
3. 测试模型配置；测试通过后返回主界面启动服务。
4. 打开 Cursor，选择已配置的模型并开始使用 Agent。

## 模型管理

模型配置支持 OpenAI 与 Anthropic 两类接口协议。每个模型渠道可以独立设置上下文窗口、最大输出 Token、推理强度、自定义请求头和额外请求参数。

![cursor-byok 模型配置](./images/cn-model.png)

## 工作原理

```text
Cursor 客户端
    │
    │ Agent 请求与工具结果
    ▼
cursor-byok 本地服务
    │
    │ OpenAI / Anthropic 兼容请求
    ▼
你配置的模型 API
```

cursor-byok 在本机负责协议适配、模型请求转发、工具调用衔接与会话状态管理。模型 API Key 和应用配置保存在本机；实际请求仍会发送到你所配置的模型服务商。

## 为什么做这个项目

很多 Agent 产品会将工具能力、模型选择、订阅方案和计费方式绑定在一起，用户只能使用平台提供的模型渠道。

我希望将模型选择权交还给用户：开发者可以充分利用已有的模型 API 和额度，自由选择适合自己的模型与服务商，也可以在需要时自托管相关服务。

## 源仓库

本项目是 [leookun/cursor-byok](https://github.com/leookun/cursor-byok) 的个人修改版。

上游项目是一个开源的 Cursor 后端本地实现。它在本机运行服务，将 Cursor 连接到你配置的模型 API，支持选择兼容的服务商、模型标识、接口地址、API Key 和请求参数，同时保留 Cursor Agent 的工具调用、Skills 和 MCP 等能力。

本分叉版移除了上游广告服务、广告资源缓存和广告入口，保留其余源代码以及原始许可证和版权声明。关于上游项目的原始路线图、文档、问题反馈和贡献者历史，请访问[源仓库](https://github.com/leookun/cursor-byok)。

## 许可证

本项目基于 [MIT License](./LICENSE) 开源。

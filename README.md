<div align="center">

# dsh-open-model

**[DeepSeek Harness](https://www.deepseek.com/harness/) 免费模型插件**

Kilo 免费模型 · ChatGPT 套餐 · 模型筛选与测速

[![DSH Plugin](https://img.shields.io/badge/DeepSeek%20Harness-plugin-6128FF)](https://www.deepseek.com/harness/)
[![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue.svg)](./LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/houyanchao/dsh-open-model/pulls)
[![GitHub stars](https://img.shields.io/github/stars/houyanchao/dsh-open-model?style=social)](https://github.com/houyanchao/dsh-open-model)

**简体中文** | [English](./README.en.md)

![OpenModel 管理页中的免费模型列表](./docs/images/free-models.png)

</div>

## 📖 dsh-open-model 是什么？

Open Model 让你在 DeepSeek Harness 中使用 Kilo 的免费模型，也可以登录自己的 ChatGPT 使用套餐额度。

## ✨ 功能特性

在左侧打开「OpenModel」，选择「免费模型」或「ChatGPT」。插件先读取 `models.json`，只按配置顺序展示其中的模型，再向所选来源核对可用性。

- **免费模型** 可直接使用 Kilo 目录中仍然免费的模型，无需账号或 API Key。使用时，对话会发送给 Kilo，匿名额度取决于 Kilo。模型下架、过期、改为收费或目录暂时无法核对时，对应模型会保留在管理页并置灰。
- **ChatGPT** 使用已有套餐的额度。未登录时，详情页只显示登录入口。请在本机 macOS 或 Windows 版 DSH 中点「使用 ChatGPT 登录」，在浏览器完成登录后返回 DSH。登录后可以查看配置的模型，授权使用套餐额度后即可开启可用模型。套餐未提供或暂时无法核对的模型会置灰。切换账号后按新账号的套餐重新核对。

## 📦 安装

### 安装方式 1（客户端）

在 [DeepSeek Harness](https://www.deepseek.com/harness/) 客户端打开「插件」→「添加插件」，输入包名 `dsh-open-model`，点击「安装」。

![DeepSeek Harness 客户端中的「插件」页面、「添加插件」按钮和输入框](./docs/install-client.png)

### 安装方式 2（通过命令行从 npm 安装）

```bash
# 安装 dsh-open-model 插件
dsh plugin --profile web add dsh-open-model
```

### 从旧包迁移

如果已安装旧包 `@houyanchao/dsh-free-model`，请先运行 `dsh plugin --profile web remove @houyanchao/dsh-free-model`，再安装新包。已有对话的模型标识和本地模型开关设置会沿用。

## ⚙️ 管理模型

按名称或模型 ID 搜索，或用筛选框查看「已开启」「已隐藏」或「不可用」的模型。可用模型默认开启，只有可用且已开启的模型会出现在对话的模型选择器中。关闭开关会隐藏该模型，已有对话保留原先选定的模型。Kilo 按 DSH profile 保存开关，ChatGPT 按账号分别保存。

在对话输入框打开「网页搜索」，模型就可以按需搜索。这个选择按对话保存，在「OpenModel (ChatGPT 套餐)」和「OpenModel (免费模型)」之间切换时会沿用。ChatGPT 可以使用套餐自带的搜索，免费模型需要支持工具调用，且当前 DSH 会话有可用的搜索服务。关闭网页搜索后，仍可通过 DSH 的网页读取工具打开你提供的链接。

在对话框选中「OpenModel (免费模型)」分组下的模型后，再点一次模型按钮。支持调节的模型会显示「推理等级」，可以选择该模型开放的档位或思考开关。

在「免费模型」标签页点「测速」会从当前 DSH 的网络出口，给通过目录核对的每个模型发一条固定的文本测试请求。收到正常文本回复时标为「可用」，测试失败时标为「不可用」并显示原因。请求耗时以毫秒显示，超过时限则显示「超时」。标签反映该次检测的结果，显示开关仍可单独控制。检测请求计入 [Kilo 匿名请求额度](https://kilo.ai/docs/gateway/authentication#anonymous-access)。

插件会检查 npm 的 `latest` 版本。新版比当前安装版本新且已发布满 24 小时后，侧栏的「OpenModel」入口旁会显示「更新」，管理页顶部也会显示「有新版本」。点「查看更新」可打开插件详情。

## ⭐ 支持一下

如果 dsh-open-model 好用，欢迎给个🌟，帮助更多人发现它！

## 📄 许可证

Copyright © 2026 houyanchao。作者编写的插件代码采用 [GPL-3.0-or-later](LICENSE) 许可证。

ChatGPT 登录和对话代码移植自 `dsh-use-chatgpt` 的独立实现，通过 OpenAI JavaScript SDK 调用 Responses API。插件保留了原项目随附的 DevKit 许可证，第三方依赖沿用各自的许可证。[第三方声明](notices/THIRD_PARTY_NOTICES.md) · [DevKit 许可证](notices/LICENSE)

用户使用自己的 ChatGPT 套餐。这项登录接入功能须免费向用户提供。登录按钮中的 ChatGPT 标识使用 OpenAI 提供的品牌素材。[Sign in with ChatGPT 条款](https://openai.com/policies/sign-in-with-chatgpt-terms/) · [OpenAI 品牌指南](https://openai.com/brand/)

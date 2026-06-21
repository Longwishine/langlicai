# 浪理财

浪理财是一套面向个人投资组合管理的 Apple 端理财看板，包含 macOS 桌面端和 iOS 移动端。它聚合持仓、行情、市场天气、新闻语料、AI 新闻摘要和理财师 Bot，用更贴近日常决策的方式辅助用户观察账户状态。

> 本项目仅用于投资辅助分析和个人工具演示，不构成任何证券、基金、期货或其他金融产品的买卖建议。

## 下载

| 版本 | macOS DMG | iOS unsigned IPA | 更新说明 |
| --- | --- | --- | --- |
| v2.1.3 | [浪理财-2.1.3.dmg](https://github.com/Longwishine/langlicai/releases/download/v2.1.3/%E6%B5%AA%E7%90%86%E8%B4%A2-2.1.3.dmg) | [浪理财-2.1.3_unsigned.ipa](https://github.com/Longwishine/langlicai/releases/download/v2.1.3/%E6%B5%AA%E7%90%86%E8%B4%A2-2.1.3_unsigned.ipa) | [v2.1.3 更新说明](浪理财_v2.1.3_更新说明.md) |
| v2.1.2 | [浪理财-2.1.2.dmg](https://github.com/Longwishine/langlicai/releases/download/v2.1.2/%E6%B5%AA%E7%90%86%E8%B4%A2-2.1.2.dmg) | [浪理财-2.1.2_unsigned.ipa](https://github.com/Longwishine/langlicai/releases/download/v2.1.2/%E6%B5%AA%E7%90%86%E8%B4%A2-2.1.2_unsigned.ipa) | [v2.1.2 更新说明](浪理财_v2.1.2_更新说明.md) |
| v2.1.1 | [浪理财-2.1.1.dmg](https://github.com/Longwishine/langlicai/releases/download/v2.1.1/%E6%B5%AA%E7%90%86%E8%B4%A2-2.1.1.dmg) | [浪理财-2.1.1_unsigned.ipa](https://github.com/Longwishine/langlicai/releases/download/v2.1.1/%E6%B5%AA%E7%90%86%E8%B4%A2-2.1.1_unsigned.ipa) | [v2.1.1 更新内容报告](浪理财_v2.1.1_更新内容报告.md) |
| v2.1.0 | [浪理财-2.1.0.dmg](https://github.com/Longwishine/langlicai/releases/download/v2.1.0/%E6%B5%AA%E7%90%86%E8%B4%A2-2.1.0.dmg) | [浪理财-2.1.0_unsigned.ipa](https://github.com/Longwishine/langlicai/releases/download/v2.1.0/%E6%B5%AA%E7%90%86%E8%B4%A2-2.1.0_unsigned.ipa) | [v2.1.0 更新说明](浪理财_v2.1.0_更新说明.md) |

## 最新版本 v2.1.3

v2.1.3 重点升级了理财师 Bot 个性化、历史对话归档、持仓天气和 AI 新闻摘要体验。

- 新增“我的理财师 Skill”，内置稳健默认、股神巴菲特、高频交易员、消息面信徒、偏好科技板块等预设。
- 支持“定制我自己的 Skill”，用户可以在本地保存自己的理财观点、投资战术和操作偏好。
- 历史对话最多保留最近 5 个自然日，标题由日期和首次提问共同组成，并支持删除。
- 明细页顶部新增“持仓气温及天气”，根据持仓明细最新涨跌表现生成温度和天气。
- 新闻中心新增“AI新闻导读”，稳定提取摘要第一段核心观点，并支持图标刷新。
- AI 新闻摘要流程优化为优先使用本地语料、限量评分、后台刷新，减少卡顿和 token 消耗。
- 修复重新生成摘要可能导致应用转圈卡死的问题。
- 修复持仓明细表“仓位”百分比前无意义正号。

## 功能概览

- 投资组合总览：总资产、今日盈亏、资产趋势、持仓穿透。
- 市场气温与天气：用指数、ETF 和持仓涨跌表达市场状态。
- 持仓明细：持仓权重、涨跌、盈亏和天气化概览。
- 新闻中心：最新新闻、持仓相关新闻、AI 新闻摘要、AI 新闻导读。
- 理财师 Bot：结合持仓、行情、新闻摘要和用户 Skill 生成辅助分析。
- 本地侧写：用户自定义 Skill 存在本地，不上传到仓库。

## 项目结构

```text
MacPortfolioDashboard/      macOS SwiftUI 桌面端
PortfolioDashboardApp/      iOS SwiftUI 移动端
浪理财_v*.md               各版本更新说明
浪理财产品需求文档_*.md     PRD 文档
```

Android 实验目录不随本仓库发布。

## 本地运行

macOS：

```bash
cd MacPortfolioDashboard
DEEPSEEK_API_KEY="你的 DeepSeek API Key" swift run
```

iOS：

```bash
open PortfolioDashboardApp/PortfolioDashboardApp.xcodeproj
```

## 大模型接入

从 GitHub 下载的版本默认不绑定任何模型账号。安装后进入“我的理财师Bot”区域，点击“接入”，填入自己的 DeepSeek API Key 并保存；保存后 AI 新闻摘要和理财师 Bot 会共同使用这份本地配置。

开发运行时也可以设置环境变量：

```bash
DEEPSEEK_API_KEY="你的 DeepSeek API Key"
```

应用读取顺序为：本机已保存 Key、环境变量 `DEEPSEEK_API_KEY`、包内 Info.plist 配置。

## 校验

| 文件 | SHA-256 |
| --- | --- |
| `MacPortfolioDashboard/dist/浪理财-2.1.3.dmg` | `91ea5641e76014201c80453f6d1644e10023b187455338a73ea9b62264b53d8b` |
| `PortfolioDashboardApp/dist/浪理财-2.1.3_unsigned.ipa` | `74aae8a4d8ed5e48a62342931d6af15fc6f00b5ea3407ead4526ab8b9f2da526` |
| `MacPortfolioDashboard/dist/浪理财-2.1.2.dmg` | `6990925e6c85f5346603e7971de843a433198a37a04cfea86a312823dcabd478` |
| `PortfolioDashboardApp/dist/浪理财-2.1.2_unsigned.ipa` | `d73d37d6ce943da4820fd1e42cbfa341928f52ea61c3e221f7a7a30f22897ab6` |
| `MacPortfolioDashboard/dist/浪理财-2.1.1.dmg` | `f4ddd19b23043c80b5c083d73a5f8831270828b0221b628e4ac114ef3628d6b0` |
| `PortfolioDashboardApp/dist/浪理财-2.1.1_unsigned.ipa` | `58b6ed3531f317a702e85a85dbdb97b6f6784756464494a60e049045479c5afb` |
| `MacPortfolioDashboard/dist/浪理财-2.1.0.dmg` | `0a0ead2aa6c5597b00accfd79851764c857b2d4486c54efc8a919579b72d43db` |
| `PortfolioDashboardApp/dist/浪理财-2.1.0_unsigned.ipa` | `3896179ad7a0abb315c5d8f646e60a856a66f15171436854043d8c979f554871` |

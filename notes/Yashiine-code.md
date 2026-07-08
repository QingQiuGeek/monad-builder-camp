---
timezone: UTC+4
---

# Yashiine

**GitHub ID:** Yashiine-code

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-08
<!-- DAILY_CHECKIN_2026-07-08_START -->
本次分享主要介绍了 AI Agent 支付基础设施的设计思路和落地场景。核心观点是：未来 Agent 会承担大量重复性任务，而这些任务中必然会涉及资金流转，因此“让 Agent 安全、可控地花钱”会成为 Agent 经济的重要基础设施。

分享中提到，Agent 支付的关键不只是完成交易，而是要解决身份识别、预算控制、风控约束、交易可审计和可撤销等问题。比如通过共管式 Agent 钱包、一次性 Agent 卡、与 VISA 合作的长期 Agent 卡，以及基于 X402 协议优化的支付能力，让 Agent 可以在用户授权和预算范围内自动完成支付，同时避免乱花钱或高风险交易。

文档还介绍了几类具体方案：一是开发者可以把 API、MCP、Skill 等能力上架变现；二是针对电商等场景生成支付链接；三是 Agent 之间可以通过唯一 ID 进行点对点转账。当前主要落地在小额支付、USDC/稳定币、Stripe 法币充值、Agent 抢红包、票务预订、行业调研 Skill 等场景。

我的理解是，Agent 支付的难点不在“能不能付款”，而在“如何让付款可信、可控、合规”。这套体系本质上是在为未来 Agent 大规模参与商业活动做准备。随着用户信任、行业标准和合规体系逐渐完善，Agent 支付可能会像早期支付宝一样，从小额场景逐步走向更广泛的日常交易场景。
<!-- DAILY_CHECKIN_2026-07-08_END -->

# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->

\# 2026-07-08｜Monad Testnet 智能合约部署学习笔记

\## 今日目标

完成 Week 1 智能合约实践任务：使用 Remix 编写并编译一个最小智能合约，将其部署到 Monad Testnet，并完成一次 read function 和一次 write function 调用。

本次实践重点是理解完整链路：

合约源码 → 编译 → 连接钱包 → 部署到 Monad Testnet → 获得合约地址 → 调用 read/write function → 使用交易 hash 进行验证

\## 使用工具

\- Remix IDE

\- MetaMask 钱包

\- Monad Testnet

\- Monad 测试币 MON

\## 合约说明

本次部署的合约是一个简单的留言板 `MessageBoard`。

合约支持三个主要功能：

\- `postMessage(string content)`：发布一条留言，需要发起链上交易。

\- `getMessageCount()`：读取当前留言数量，不需要 gas。

\- `getMessage(uint256 index)`：读取指定编号的留言内容。

\## 部署过程

1\. 在 Remix 中创建 Solidity 合约文件。

2\. 使用 Solidity 编译器完成编译。

3\. 在 MetaMask 中添加并切换到 Monad Testnet。

4\. 从 Faucet 领取测试 MON。

5\. 在 Remix 的 Deploy 面板中选择 MetaMask 作为连接钱包。

6\. 确认网络为 Monad Testnet 后部署合约。

\## 部署结果

\- Network: Monad Testnet

\- Contract Address: `0x9fbf567e92FBf4348512f6a745389Eb96088D30E`

\- Deploy Transaction Hash: `0xbedcf9bbee57888283816c77cb4828a40577e67a0a6b162e50cfc4f9c68b609a`

\## 合约交互记录

\### Read Function

调用了：

\`\`\`text

getMessageCount()
<!-- DAILY_CHECKIN_2026-07-07_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->


```
今天学习了钱包地址、测试网资产、交易哈希和区块浏览器的基本用法。通过 MonadVision 查看交易时，我理解了 From 是发起交易的钱包地址，To 是接收地址，Value/Amount 是转账数量，Gas 是链上执行交易需要支付的手续费。即使是在测试网，这个流程也和真实链上交易很接近，因此操作时要注意不要泄露助记词、私钥或其他敏感信息。

因为对这次的黑客松比较感兴趣，着重记了一下要点：### 黑客松参赛建议

- **创意要好**，**UI 要精美**，评委第一印象非常重要
- 理解自己项目做了什么、自己在其中承担了哪些工作
- 熬夜做项目时注意将代码逻辑理解透彻，能读懂代码 review 已足够
- 参赛流程：一起写代码跑 demo、商量方案、录视频、现场回答评委问题
```
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

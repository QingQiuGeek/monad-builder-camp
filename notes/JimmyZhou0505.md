---
timezone: UTC+8
---

# JimmyZhou

**GitHub ID:** JimmyZhou0505

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->
## Monad 合约部署学习笔记

今天学习了如何把一个最小 Solidity 合约部署到 Monad Testnet，并完成基础合约交互。

整个流程可以理解为：

**合约源码 → 编译 → 连接钱包 → 部署到测试网 → 获得合约地址 → 调用合约函数 → 区块浏览器验证**

首先，我在 Remix 中创建了 `CheckIn.sol` 文件，并写入一个简单的打卡合约。这个合约可以记录用户是否打卡，以及累计打卡次数。

然后，我使用 Remix 的 Solidity Compiler 对合约进行编译。编译的作用是把 Solidity 代码转换成区块链可以识别的字节码。如果代码有语法错误，部署前就会报错。

接着，我用课程专用钱包连接 Remix，并确认钱包网络是 Monad Testnet，而不是 Ethereum 主网。这个步骤很重要，因为如果网络选错，可能会使用真实 ETH 支付 gas。

之后，我点击 Deploy，把合约部署到 Monad Testnet。部署成功后，链上会生成一个合约地址。合约地址就像这个程序在区块链上的“门牌号”，之后所有交互都要通过这个地址完成。

部署合约本身也是一笔链上交易，所以会生成 deployment transaction hash。这个 hash 可以在区块浏览器中查询，用来验证合约是否部署成功。

合约部署完成后，我测试了 read function 和 write function。read function 只是读取链上数据，不会修改状态，所以一般不需要 gas，也不会生成交易 hash。write function 会修改链上状态，例如调用 `checkIn()` 完成打卡，所以需要钱包确认，并会产生新的 transaction hash。

最后，我在区块浏览器中查看了合约地址、部署交易和交互交易，理解了链上操作是公开可查的。

这次学习让我明白，智能合约部署不是简单地“上传代码”，而是把代码编译后写入区块链。部署成功后，合约会拥有独立地址，用户可以通过 read / write function 与它交互。整个过程需要特别注意钱包网络、gas 费用、交易 hash 和区块浏览器验证。
<!-- DAILY_CHECKIN_2026-07-07_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->

今天完成了 Monad Week 1 的基础学习和打卡任务。开始创建了一个专门用于测试网的钱包。之后，学习了如何添加 Monad Testnet，领取测试网资产 MON，并完成了一次测试网转账或链上交互。通过这一步，我第一次理解了链上交易的基本流程：钱包发起交易、网络处理交易、交易被打包上链，最后生成 transaction hash。

然后使用区块浏览器查看交易详情，学习了 `from`、`to`、`value`、`gas`、`transaction fee` 和 `status` 的含义。`from` 是发起交易的钱包地址，`to` 是接收方地址或合约地址，`value` 表示转账金额，`gas` 和手续费代表链上执行交易所消耗的成本。我也理解了为什么失败交易仍然可能消耗 gas，因为节点已经对交易进行了处理和计算。

最后开始学习 AI 辅助开发，用 AI 生成了一个最小 Solidity 打卡合约，并在 Remix 中完成编译和测试。这个合约可以记录用户是否打卡、累计打卡次数，并限制同一个地址每天只能打卡一次。通过人工检查，我学习了 `mapping`、`event`、`function`、`msg.sender`、`require` 和 `block.timestamp` 等基础概念。

今天最大的收获是：链上产品和普通互联网产品不同，用户的操作、资产和交易记录都会直接写入区块链，公开可查且不可随意撤回。AI 可以帮助我快速生成代码和解释逻辑，但最终仍然需要我自己检查合约是否能编译、函数是否符合预期、是否存在权限问题和潜在安全风险。
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

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
# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->
今天完成了 Monad Week 1 的基础学习和打卡任务。开始创建了一个专门用于测试网的钱包。之后，学习了如何添加 Monad Testnet，领取测试网资产 MON，并完成了一次测试网转账或链上交互。通过这一步，我第一次理解了链上交易的基本流程：钱包发起交易、网络处理交易、交易被打包上链，最后生成 transaction hash。

然后使用区块浏览器查看交易详情，学习了 `from`、`to`、`value`、`gas`、`transaction fee` 和 `status` 的含义。`from` 是发起交易的钱包地址，`to` 是接收方地址或合约地址，`value` 表示转账金额，`gas` 和手续费代表链上执行交易所消耗的成本。我也理解了为什么失败交易仍然可能消耗 gas，因为节点已经对交易进行了处理和计算。

最后开始学习 AI 辅助开发，用 AI 生成了一个最小 Solidity 打卡合约，并在 Remix 中完成编译和测试。这个合约可以记录用户是否打卡、累计打卡次数，并限制同一个地址每天只能打卡一次。通过人工检查，我学习了 `mapping`、`event`、`function`、`msg.sender`、`require` 和 `block.timestamp` 等基础概念。

今天最大的收获是：链上产品和普通互联网产品不同，用户的操作、资产和交易记录都会直接写入区块链，公开可查且不可随意撤回。AI 可以帮助我快速生成代码和解释逻辑，但最终仍然需要我自己检查合约是否能编译、函数是否符合预期、是否存在权限问题和潜在安全风险。
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

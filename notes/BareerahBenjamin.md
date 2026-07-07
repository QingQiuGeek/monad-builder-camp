---
timezone: UTC+8
---

# BareerahBenjamin

**GitHub ID:** BareerahBenjamin

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->
# 异步 I / O（**Asynchronous I/O）**

CPU 在通信进行的同时继续并发执行其它操作。

# 管道（流水线技术，Pipelining）

通过将任务分解成一系列可以并行处理的较小任务来实现并行性的技术。

# MonadBFT

MonadBFT 不仅可以结合流水线式领导者BFT协议（pipelined leader-based BFT protocols）的所有特性，还可以抵抗其无法解决的尾部分叉（tail-forking）问题。具体实现了：

-   **推测性最终性通过一轮共识达成** ， **完全最终性通过两轮共识达成** 。
    
-   在正常情况下（即未发生故障时）， **消息和认证器的复杂度均为线性** 。这使得共识验证器集能够扩展到大量节点。
    
-   **乐观响应** ：在正常情况下以及从失败的回合中恢复时，无需等待最坏的网络延迟即可推进回合进程。
    
-   **领导者故障隔离：** 单个领导者故障只会导致一次超时延迟。所有其它轮次都能以网络允许的最快速度继续进行。这与现有的流水线式 BFT 协议不同，后者对于一个故障领导者会造成两次超时。
    
-   **抗尾分叉** ：内置的抗[**尾分叉保护机制，尾分叉**](https://docs.monad.xyz/monad-arch/consensus/monad-bft#no-tail-forking)是最大可提取价值（MEV）攻击的一种类型，恶意领导者可能会分叉掉其前一个区块。这解决了先前基于流水线领导者的 BFT 共识机制中的一个关键问题。
    

MonadBFT 中一个区块由一个轮次编号、有效载荷（有序的交易列表）和一个 [**质量控制（QC）**](https://docs.monad.xyz/monad-arch/consensus/monad-bft#quorum-certificate-qc) （用于验证父区块）组成。验证者使用 **BLS** 签名，它有签名聚合的特性，便于将多个签名聚合提高验证效率。

## 标准恢复机制中的特有概念

**提案：**

**提案 propose**

**新提案 fresh proposal**

包含新区块的[**提案**](https://docs.monad.xyz/monad-arch/consensus/monad-bft#proposal) ，即不受先前失败提案影响的提案

**重新提案 reproposal**

包含先前新提案中某个区块的[**提案**](https://docs.monad.xyz/monad-arch/consensus/monad-bft#proposal) ，当前领导人试图恢复或最终确定该新提案。重新提案的整数编号将大于其[**质量控制提案**](https://docs.monad.xyz/monad-arch/consensus/monad-bft#quorum-certificate-qc)的整数编号加 1

**小费：**

**小费 tip**

提案减去区块有效载荷后的结果

**高额小费 high tip**

给定一组小费，高额小费就是整数值最高的小费

**超时信息 Timeout Message**

验证器在预期时间内未从预定领导者处收到有效区块时生成的签名证明。超时消息证明缺少有效区块

**超时证书 Timeout Certificate (TC)**

当发生超时时，验证器开始发送和接收[**超时消息**](https://docs.monad.xyz/monad-arch/consensus/monad-bft#timeout-message) 。每个验证器都会累积收到的超时消息；如果累积到绝大多数此类消息，则会生成超时证书（TC））

**无背书消息和无背书证书（No-Endorsement Message and No-Endorsement Certificate）**

在特定情况下，领导者会向其他验证者索取与提示对应的完整提案（区块）。如果验证者没有该提案，他们会回复一条已签名的“不认可消息”；如果领导者在尝试恢复某个提示的提议时收到绝大多数的“不认可”消息，他们可以生成“不认可”证书——证明网络中的绝大多数人没有该提议。

## 块状态

1.  `Proposed` 建议的
    
2.  `Voted` 投票
    
3.  `Finalized` 最终版
    

第四个状态 `Verified` 是在 MonadBFT 之外，作为[**异步执行的**](https://docs.monad.xyz/monad-arch/consensus/asynchronous-execution)一部分实现的。

### 几种情况

Happy Path

快乐路径描述的是一个区块从被提议到最终完成的正常情况，没有任何超时或失败的轮次。

Unhappy Path（Fault Handling）

不愉快的路径描述的是领导者未能发出有效提案或 QC 构建者（下一任领导者）未能构建 QC 的异常情况。
<!-- DAILY_CHECKIN_2026-07-07_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->

今天完成了 week1 的大部分通用任务，熟悉了一些 Monad 生态
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

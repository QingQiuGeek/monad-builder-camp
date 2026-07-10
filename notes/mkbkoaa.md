---
timezone: UTC+8
---

# mkbkoaa

**GitHub ID:** mkbkoaa

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-10
<!-- DAILY_CHECKIN_2026-07-10_START -->
**Monad vs 以太坊：开发者必知的核心差异**

**1\. 虚拟机（VM）**

-   **合约代码上限**：128 KB（以太坊仅 24 KB），初始化代码上限 256 KB（以太坊 48 KB）。能写更大、更复杂的合约。
    
-   部分操作码和预编译 gas 价格调整（冷访问更贵，部分加密运算更贵）。
    
-   新增 **P256 签名验证**（地址 0x0100），支持 WebAuthn / Passkey 签名验证。
    

**2\. 交易规则**

-   **Gas 费用按 gas limit 收取**（不是实际用量）。扣款 = value + gas\_price × gas\_limit。
    
-   引入 **Reserve Balance（储备余额）机制**（约 10 MON）：
    
    -   防止 DoS 攻击。
        
    -   可能看到“余额不足”而失败的交易，但仍扣 gas（正常回滚）。
        
-   不支持 **Blob 交易**（EIP-4844）。
    
-   无全局内存池，交易转发给未来几个出块者。
    

**3\. EIP-7702 委托**

-   委托后的 EOA 余额**不能低于 10 MON**（取消委托后可以）。
    
-   委托状态下，合约代码**禁止使用 CREATE / CREATE2**。
    

**4\. 历史数据**

-   因高吞吐量，完整节点**不保存任意历史状态**（节省存储）。
    

**一句话总结**：Monad 大部分和以太坊一样，但为了极致性能，在 Gas 计费、合约大小、历史数据访问上做了调整。开发时建议用 Monad 专属 Foundry 测试。
<!-- DAILY_CHECKIN_2026-07-10_END -->

# 2026-07-09
<!-- DAILY_CHECKIN_2026-07-09_START -->

今天的内容感觉比较偏技术，对于非计算机专业的学习者来看，其实有一定难度。

**DApp 架构和开发流程简要总结**：去中心化 + 多技术栈协作（合约 + 前端 + Indexer），重点解决链上查询低效和安全问题。

**核心架构（区别于传统 Web 应用）**

-   **前端**：React/Vue 等构建 UI，通过**钱包**（MetaMask）和 **RPC 节点** 与区块链交互（只读调用 + 交易签名）。
    
-   **智能合约**：核心业务逻辑，用 **Solidity** 编写，部署在区块链（EVM）上，自动执行、不可篡改。
    
-   **Indexer（检索器）**：监听合约 Events，将链上数据同步到传统数据库，供前端高效查询。
    
-   **区块链 + 去中心化存储**（IPFS/Arweave）：存储状态/交易和大文件。
    

**开发流程**

1.  **需求分析**：定功能、选链（以太坊等）、设计 UX。
    
2.  **智能合约**：编写、测试、安全审计。
    
3.  **Indexer**：用 Ponder/Subgraph 等捕获事件、入库。
    
4.  **前端**：集成钱包、交互逻辑（推荐 Viem/Wagmi）。
    
5.  **交互与部署**：Hardhat/Foundry 部署合约，前端上 IPFS/Vercel，上线维护。
<!-- DAILY_CHECKIN_2026-07-09_END -->

# 2026-07-08
<!-- DAILY_CHECKIN_2026-07-08_START -->


学习了智能体相关内容。建立了自己的钱包，理解交易过程。

![IMG_3067.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/mkbkoaa/images/2026-07-08-1783526077503-IMG_3067.png)
<!-- DAILY_CHECKIN_2026-07-08_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->



在实习手册和入门导读中，学习到了很多新的概念，虽然还没有理解特别清楚。在学习之前对于web3的理解比较片面，以为就是炒币的，在概念的学习中拓宽了认知，知道了web3和web2之间的区别，知道了去中心化概念，以及以太坊的技术概念（一直以为就是一个叫eth的币）
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

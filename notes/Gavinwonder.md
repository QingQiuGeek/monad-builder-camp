---
timezone: UTC+8
---

# GwynGO

**GitHub ID:** Gavinwonder

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->
今天主要通过和AI的对话，了解了Solidity合约的基本定义和主要代码结构，并且了解到它区别于传统代码的四个颠覆性的特点：

-   **代码即法律 (Code is Law)，也意味着“Bug 即法律”** 普通软件有 Bug，发个补丁（Patch）就行。但 Solidity 合约一旦部署，**代码便无法修改**。如果里面有一个漏洞能让人把钱转走，那么在合约被废弃前，这个漏洞就一直有效。
    

-   **每一行代码都在“烧钱” (Gas 机制)** 在以太坊等网络上，合约的每一次修改状态操作（比如上文的 `increment`），都需要网络中的无数台计算机共同计算并达成共识。为了防止有人恶意写死循环瘫痪网络，**执行任何修改数据的操作都要支付 Gas 费**。因此，Solidity 程序员最大的追求往往是“如何用最少的代码省最多的钱”。
    
-   **合约是“瞎子”和“聋子” (确定性环境)** 为了保证所有区块链节点算出的结果一模一样，Solidity 合约**绝对不能在内部进行随机数生成，也不能直接发送 HTTP 请求去查外面的天气或股票**。它想知道外部世界的信息，必须依靠“预言机（Oracle，如 Chainlink）”把数据“喂”给它。
    
-   **天然带有“金钱”属性** 在传统开发中，你可能需要对接支付宝、PayPal 接口。而在 Solidity 中，**“钱”（ETH 或代币）是语言的一等公民**。合约本身可以持有资产，函数可以直接接收资产（使用 `payable` 关键字）。它既是代码，又是金库。
    

同时跟AI对话了解到了六个合约方向：

-   **留言板 (Message Board)：** 基础的“链上记事本”。用户支付 Gas 费将一段文字永久写入区块链。常用于学习状态变量、结构体（Struct）和数组（Array）的增删改查。
    
-   **投票合约 (Voting)：** 经典的治理工具。由创建者发起提案，用户进行投票。核心在于利用 `mapping(address => bool)` 限制**一人只能投一票**，并统计票数，是理解链上自治（DAO）的敲门砖。
    
-   **打卡合约 (Check-in)：** 行为激励或习惯养成工具。用户每天调用一次合约，系统记录连续打卡天数。重点在于学习时间戳（`block.timestamp`）的处理和防作弊逻辑（24小时限制）。
    
-   **NFT Badge (勋章)：** 身份与荣誉凭证。基于 **ERC721 或 ERC1155 标准**，当用户完成特定任务时，合约会铸造（Mint）一枚不可转让的灵魂绑定代币（SBT）到其钱包，用于学习**代币标准与继承**。
    
-   **积分记录 (Points Record)：** 简易版的账本。合约内部维护一个 `mapping(address => uint256)`，记录每个地址拥有的积分，可进行增加、扣减。这是理解 **ERC20 代币合约**最直观的过渡项目。
    
-   **Onchain Todo (链上待办事项)：** 任务管理器。用户可以创建任务、标记完成或删除任务。能非常全面地锻炼 Solidity 语言中对**复杂数据结构的操作和 Gas 费优化**。
    

并且由AI创建了一条智能合约，但是还是看不懂里面的语言，时间有限，明天再学哈哈。

晚上了解到了EPF的概念，可能对我这种非技术出身人员入门门槛还是太高了，放弃技术路线Orz。。
<!-- DAILY_CHECKIN_2026-07-07_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->

![image.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/Gavinwonder/images/2026-07-06-1783309557808-image.png)

今天从Metamask建立了用于Monad网络的钱包，并通过连接Testnet测试网及X、Discord账号获得了15个MON
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

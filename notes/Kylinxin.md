---
timezone: UTC+8
---

# BoFeng

**GitHub ID:** Kylinxin

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->
# 2026-07-07｜残酷学习打卡｜Monad NFT Badge 项目

## 今日主题

今天围绕 Monad Week 1 任务，完成了一个比“最小合约”更完整的 NFT Badge 项目：Solidity 合约、Foundry 测试、本地 Anvil 部署、Monad Testnet 部署记录、React + wagmi + RainbowKit 前端，以及和 NFT Badge 挂钩的 Chain Runner 小游戏。

## 今日完成

-   使用 Foundry 搭建 Solidity 项目结构。
    
-   编写 `MonadAIBadgeCollection` ERC721 NFT Badge 合约。
    
-   支持 `ownerMint`、`transferFrom`、`approve`、`setApprovalForAll`、`tokenURI`、`imageURI`、`contractURI`。
    
-   支持 EIP-2981 版税，默认 5%，上限 10%。
    
-   NFT metadata 和 SVG 图片保持链上生成。
    
-   本地 Anvil 部署并验证合约 owner、Genesis Badge 和基础 read function。
    
-   部署到 Monad Testnet，并记录合约地址、部署交易 hash 和交互交易 hash。
    
-   编写中文 README、部署记录和任务提交文档。
    
-   使用 React、wagmi、RainbowKit 做出本地网页端展示界面。
    
-   将 UI 从普通 NFT 展厅推进到 Chain Runner 小游戏场景。
    
-   新增 `submitRun`、`runnerProfile`、`topRunner`、`claimRunnerBadge` 等游戏相关合约功能。
    
-   本地验证小游戏成绩提交、Runner Badge 领取和 NFT 转账流程。
    

## 残酷复盘

今天最大的收获是把“写一个合约”推进成了“完成一条链上产品链路”。一开始只需要 NFT Badge，但如果只停留在最小 ERC721，价值很有限。后面把它扩展成可交易 NFT 合集、链上 metadata、前端展示、游戏成绩、Badge 领取、转账流程，才开始接近一个能被别人打开体验的 Web3 Demo。

残酷一点说，今天暴露的问题也很明显：很多东西不是不会，而是之前没有真正串起来。合约能编译不等于功能合理，部署成功不等于产品可用，页面能打开不等于链上交互打通。MetaMask 网络、Anvil 默认账户、合约 owner、交易失败、余额、gas、前端合约地址，这些只要一个环节错，用户就会卡住。

今天也看到了 AI 辅助开发的边界。AI 可以快速生成合约初稿、解释结构、补测试、写文档，但最终要不要加权限、能不能交易、metadata 是否市场兼容、是否泄露私钥、前端是否连对合约、测试是否真的覆盖关键行为，这些都必须人工判断。把 AI 输出当答案是危险的，把它当加速器才有意义。

## 今日关键判断

-   NFT Badge 不能做成 soulbound，因为任务要求后续能按正常 NFT 市场方式交易。
    
-   不自建 Marketplace 合约，只做市场兼容 ERC721，避免无关复杂度。
    
-   私钥不能写进 README、提交文档或代码，只能放本地 `.env` 或交互式 keystore。
    
-   游戏每一帧不上链，只把最终成绩和 Badge 领取上链，否则用户体验和 gas 成本都不合理。
    
-   Chain Runner 的分数提交目前没有防作弊能力，只适合作为学习 Demo，生产环境需要更强验证机制。
    
-   合约功能必须由 Foundry 测试锁住，不能只靠网页点一次。
    

## 验证结果

-   `forge build` 通过。
    
-   `forge test -vvv` 通过，合约测试 28 个全部通过。
    
-   `npm test` 通过，前端测试 13 个全部通过。
    
-   `npm run build` 通过。
    
-   本地 Anvil 验证 `submitRun -> claimRunnerBadge -> ownerOf(2)` 成功。
    
-   前端本地运行地址：`http://127.0.0.1:5173/`。
    

## 今日产出

-   Monad AI Builder Badge NFT 合约。
    
-   Monad Testnet 部署记录。
    
-   NFT Badge 项目 README。
    
-   AI 辅助生成 Solidity 合约任务提交文档。
    
-   Monad 高频交互理解文档。
    
-   Chain Runner 小游戏 Demo。
    
-   本地网页端 NFT 展厅、成绩提交、Badge 领取、NFT 转账流程。
    

## 明日推进

-   补充 Monad Testnet 上新版 Chain Runner 合约部署。
    
-   整理截图：合约地址、部署交易、write 交互、read function、网页端。
    
-   检查文档中是否还有不该提交的敏感信息。
    
-   继续学习 Solidity 安全边界，尤其是权限、重入、签名验证、防作弊和 metadata 兼容性。
    
-   如果继续完善小游戏，需要把 Game-icons SVG 改成本地静态资源，减少外部资源不可用风险。  
    a
<!-- DAILY_CHECKIN_2026-07-07_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->

今日打卡｜Monad 学习记录

今天主要参加了 Web3 Summer Internship Program 的 Week 1 学习任务，围绕 Monad Testnet、钱包准备、区块浏览器和链上产品基础认知进行了学习。Web3 Career Build 平台本身也强调通过学习、实践与链上 Profile 连接真实机会，这也让我理解到本次任务不只是完成操作，而是在建立自己的链上学习记录。:contentReference\[oaicite:0\]{index=0}

会议和任务内容中，我重点完成了 MetaMask 钱包准备，并在现有钱包中新建了课程专用账户，避免直接使用主力钱包。随后学习了如何添加 Monad Testnet 网络，理解了测试网资产 MON 的作用，以及如何通过 Faucet 获取测试币。第一次打开 Monad Explorer 时，我了解到区块浏览器可以查询地址、交易哈希、区块、余额和交易状态等信息，是观察链上行为的重要工具。

今天还进一步理解了 gas 和手续费的区别。gas 代表链上计算资源的消耗单位，手续费则是用户为这些计算资源支付的成本。即使交易失败，只要交易已经上链执行，节点已经消耗了计算和验证资源，因此仍然可能扣除 gas。

通过今天的学习，我对链上产品有了初步认识。普通互联网产品主要依赖账号密码和中心化服务器，而链上产品通过钱包地址和数字签名确认身份，交易和资产状态记录在区块链上，具有公开可查、难以篡改、用户自主控制资产等特点。后续我希望继续熟悉 Solidity、Foundry 和 Monad 生态的基础开发流程，把链上操作和合约开发结合起来。
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

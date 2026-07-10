---
timezone: UTC-7
---

# Zixie Zheng

**GitHub ID:** zzxwjm

**Telegram:** 

## Self-introduction

从Measurement到web3.

## Notes

<!-- Content_START -->
# 2026-07-10
<!-- DAILY_CHECKIN_2026-07-10_START -->
分享笔记：一个新手如何自上而下理解 Web3

\## 1. 我的起点

我的背景不是金融，也不是计算机，而是偏学术研究。

在真正开始学习之前，我对 Web3 的印象很单一：

\> Web3 = 炒币 / 投机 / 金融交易 / 很技术 / 离普通生活很远

但这几天做完一些基础任务之后，我意识到，如果只从“交易”“钱包”“gas”这些操作细节进入 Web3，很容易迷失在术语里。

对我这样的新手来说，更有帮助的方式是先自上而下问：

\> Web3 到底想解决什么问题？

\> 它和我们熟悉的互联网生活有什么不同？

\> 为什么它需要钱包、链、交易和智能合约这些东西？

\## 2. 我现在的顶层理解

我现在会先把 Web3 理解成：

\> 一套公开、可验证、由用户自己控制入口的数字状态系统。

这里有几个关键词。

\### 2.1 状态

状态就是“当前情况”。

在现实生活里，很多状态由机构或平台记录：

\- 银行记录我的余额。

\- 学校记录我的学籍。

\- 平台记录我的账号和内容。

\- 游戏公司记录我的角色等级和道具。

\- 社交平台记录我的关注关系。

在 Web3 里，一部分数字状态可以被记录到公共链上：

\- 某个地址有多少资产。

\- 某个地址是否完成过一次链上操作。

\- 某个地址是否拥有某个 NFT。

\- 某个地址是否参与过投票。

\- 某个智能合约现在保存着什么数据。

所以我对 Web3 的第一个理解是：

\> Web3 不是只关于钱，而是关于“哪些数字状态可以被公开记录和验证”。

\### 2.2 用户控制入口

在 Web2 里，我们通常通过平台账号进入一个系统。

比如微信账号、Google 账号、学校账号、银行账号。

这些账号很方便，但它们通常由平台管理：

\- 平台决定账号规则。

\- 平台保存数据。

\- 平台可以限制访问。

\- 平台可以改变服务边界。

在 Web3 里，钱包变成了一个很重要的入口。

钱包不是简单的“存钱工具”，它更像是：

\> 一个用户自己控制的链上身份和签名工具。

它带来的变化是：

\- 钱包地址可以公开。

\- 私钥和助记词代表控制权。

\- 用户可以用钱包对交易签名。

\- 链根据签名确认“这个地址同意了这次操作”。

这也是为什么 Web3 的第一课不是赚钱，而是安全。

\### 2.3 可验证

Web3 很重要的一点是：某些事情不只是由一个平台告诉你“发生了”，而是可以通过区块浏览器公开查询。

比如我完成第一笔 Monad Testnet 交易后，可以看到：

\- transaction hash

\- from

\- to

\- value

\- gas

\- status

这让我第一次具体感受到：

\> 链上记录不是一个 app 界面里的提示，而是一条可以被外部验证的公共记录。

\## 3. Web3 和现实生活 / Web2 的差异

我觉得 Web3 对新手难，不只是因为它技术复杂，而是因为它的理念和我们熟悉的现实生活、Web2 生活不太一样。

\### 3.1 我们习惯了“中心化的便利”

现实生活和 Web2 里，很多事情是由中心机构帮我们组织好的。

例如：

\- 银行帮我管理账户。

\- 学校认证我的身份。

\- 平台帮我找回密码。

\- App 帮我保存数据。

\- 公司服务器决定某个操作是否成功。

这种方式非常方便。对普通用户来说，它降低了理解成本。

但代价是：

\- 我需要信任平台。

\- 平台可以改变规则。

\- 数据通常不真正属于我。

\- 我的身份和记录很难跨平台移动。

\### 3.2 Web3 把一部分责任还给用户

Web3 的理念不是简单地“没有中心”，而是试图改变信任结构。

我现在会这样理解：

\> Web2 更像是相信平台；Web3 更像是相信规则、签名、代码、共识和公开记录。

但这也意味着：

\- 用户要自己保管助记词。

\- 用户要知道自己在哪条链上操作。

\- 用户要理解签名和交易的风险。

\- 用户要承担误操作的后果。

所以 Web3 不是天然更轻松。

它更像是：

\> 用更高的个人责任，换取更强的控制权和可验证性。

\### 3.3 Web3 里的“交易”不是日常意义的交易

这是我最大的概念转变之一。

我原来以为交易就是买卖。

但在链上，transaction 更像是：

\> 一个地址签名后，向某条链提交一次状态改变请求。

所以：

\- 转账是交易，因为余额状态改变了。

\- 部署合约是交易，因为链上新增了一个合约。

\- 调用合约函数是交易，因为合约状态可能改变了。

\- 创建 onchain todo 也是交易，因为 todo 列表改变了。

这让我意识到：

\> Web3 的核心不只是交易资产，而是通过交易改变公共状态。

\## 4. 我的实际学习路径

虽然我希望自上而下理解 Web3，但对新手来说，只讲理念是不够的。

我这几天还是通过具体任务把抽象概念落地。

\### 4.1 学基础概念

我先学习了：

\- Web2 / Web3

\- 区块链

\- Ethereum 和 ETH

\- 钱包和地址

\- 私钥和助记词

\- transaction

\- gas

\- 区块浏览器

\- 智能合约

我目前最有帮助的一句话是：

\> 链记录状态，钱包控制身份，交易改变状态，gas 支付改变状态的成本。

\### 4.2 创建课程专用钱包

我创建了一个课程专用 MetaMask 钱包，并添加 Monad Testnet。

这个任务让我理解：

\- 钱包地址是公开入口。

\- 助记词是控制权，绝对不能泄露。

\- 不应该用主力钱包做学习任务。

\- 网络和代币不是一回事。

\### 4.3 完成第一笔 Monad Testnet 交易

我完成了第一笔测试网转账：

\- Value`0.01 MON`

\- Status`Success`

\- Transaction hash`0xfcc719809d3984548a88305e8753d47539eb251fd800136a8c6bf24eeea441bd`

这一步让我把很多概念连起来：

\- 钱包负责签名。

\- 链接收交易。

\- gas 是处理交易的成本。

\- 区块浏览器显示交易记录。

\- 交易成功意味着状态已经被链更新。

\### 4.4 用 AI 辅助生成 Onchain Todo 合约

我还做了一个最小 Solidity demo`Onchain Todo`。

它可以：

\- 创建 todo

\- 记录创建者地址

\- 标记 todo 是否完成

\- 读取 todo

这个任务让我第一次看到：

\> 智能合约可以是一个很小的链上规则系统。

它不一定一开始就很复杂，也不一定只用于金融。

但 AI 生成代码后，我也需要检查：

\- 能不能编译

\- 函数是否符合预期

\- 权限是否合理

\- 有没有不必要的复杂逻辑

\- 是否会记录隐私信息

\## 5. 我问过的几个代表性问题

\### 问题 1：ETH 和 Ethereum 是什么关系？

我一开始容易把 ETH 和 Ethereum 混在一起。

现在我理解为：

\- Ethereum 是网络。

\- ETH 是这个网络里的原生资产。

\- 网络负责运行规则和记录状态。

\- 原生资产常常用于支付 gas 和协调经济激励。

\### 问题 2：为什么需要很多链？

我一开始觉得所有东西放在一起最方便。

后来我理解到，不同链像不同的公共世界：

\- 有不同规则。

\- 有不同成本和速度。

\- 有不同社区。

\- 有不同应用。

\- 有不同技术取向。

所以问题不是“为什么不把所有东西放在一个地方”，而是：

\> 哪些状态需要被哪个公共世界承认？

\### 问题 3：Web3 里的交易为什么这么重要？

我一开始把交易理解为买卖。

现在我理解为：

\> 交易是改变链上状态的基本动作。

这也是为什么 Web3 学习里会反复出现 transaction、gas、from、to、value、status。

\## 6. 我作为学界新手的一个保留问题

我的学术背景让我自然会关心一个问题：

\> 链上记录是真的，但它到底代表什么？

比如：

\- 一个地址很活跃，是真的参与生态，还是为了任务在刷交互？

\- 一个 badge 代表真实学习，还是只是完成点击？

\- 一次投票代表治理贡献，还是只是为了获得奖励？

但我现在也觉得，这不是第一阶段最重要的问题。

对新手而言，第一阶段应该是：

\> 先理解工具，完成基本操作，知道链上发生了什么。

更后面的阶段才是：

\> 思考链上记录如何被解释，以及它们如何影响生态激励。

所以我不会把心理测量或学术理论直接套到 Web3 上。

我现在更愿意把它当作一个提醒：

\> 可验证不等于自动有意义。链上记录是真实的，但记录的意义仍然需要被解释。

\## 7. 我的阶段性感悟

\### 7.1 Web3 的学习不能只从术语开始

如果只学术语，新手很容易被钱包、gas、链、合约、DApp 这些词淹没。

我觉得更好的顺序是：

1\. 先理解 Web3 想改变什么。

2\. 再理解为什么需要链、钱包、交易和合约。

3\. 最后通过任务把概念落地。

\### 7.2 Web3 和现实生活最大的不同是信任方式

现实生活和 Web2 里，我们习惯把信任交给机构和平台。

Web3 试图让一部分信任转向：

\- 公开记录

\- 加密签名

\- 智能合约

\- 共识机制

\- 用户自己控制的钱包

这不是简单地更好或更坏，而是另一种组织方式。

它带来新的自由，也带来新的负担。

\### 7.3 我现在还只是刚入门

我现在不能说自己真正懂 Web3。

但我已经从：

\> Web3 是炒币

走到了：

\> Web3 是一套围绕状态、控制权和可验证性展开的数字基础设施。

这对我来说是一个重要的起点。

\## 8. 一句话总结

我这几天最大的变化是：

\> 我不再只把 Web3 理解成金融交易，而是开始把它理解成一种新的状态记录和信任组织方式。

更具体地说：

\> Web3 通过钱包确认“谁在操作”，通过交易改变“链上状态”，通过区块浏览器让记录“可以被验证”，通过智能合约让规则“可以被自动执行”。

对我这样的新手来说，Web3 仍然很抽象，但一旦完成一次真实链上操作，它就不再只是概念，而变成了一个可以被观察、被验证、被继续提问的系统。

\## 9. 我现在还保留的疑问

最后，我现在还有几个问题没有答案。它们也许会成为我后面继续学习 Web3 的入口。

\### 9.1 链上记录和真实意义之间是什么关系？

我的背景和心理测量、研究方法有关，所以我会自然关心一个问题：

\> 链上记录是真的，但它到底测量或代表了什么？

例如：

\- 一个地址交易很多次，代表真实参与，还是只是刷交互？

\- 一个地址持有 badge，代表真的学习过，还是只是完成任务？

\- 一个地址参与投票，代表治理贡献，还是只是为了奖励？

\- 一个项目链上活跃度很高，代表生态健康，还是代表激励设计被套利？

这和我原本熟悉的测量问题有一点相似：

\> 记录存在，不等于解释成立；数据可靠，不等于构念有效。

但我也不想把传统心理测量直接套到 Web3 上。因为 Web3 的主体常常不是现实生活中的“人”，而是地址、钱包、合约或多个地址之间的关系。

所以我现在更想问的是：

\> 在尊重假名性和去中心化的前提下，我们如何理解链上行为的意义？

\### 9.2 Web3 会不会重新制造一种新的中心化评分？

如果未来很多项目用链上行为来判断用户质量、贡献、声誉或资格，那么会不会出现一种新的问题：

\> 表面上是去中心化记录，实际上又形成了一套中心化或半中心化的评分逻辑？

比如：

\- 谁定义什么是贡献？

\- 谁决定哪些链上行为更有价值？

\- 用户能不能理解这些规则？

\- 用户能不能拒绝被某种指标定义？

这个问题对我来说很重要，因为 Web3 的理念强调用户控制和去中心化，但生态建设又很容易依赖指标和激励。

\### 9.3 哪些状态真的应该上链？

我现在也会问：

\> 不是所有东西都应该上链，那么什么东西值得被公开、长期、可验证地记录？

可能适合上链的是：

\- 资产归属

\- 公开投票

\- 合约状态

\- 公开贡献记录

\- 需要跨平台验证的凭证

但不适合上链的可能是：

\- 隐私信息

\- 可撤回的个人表达

\- 大量日常数据

\- 不需要公开验证的普通记录

所以 Web3 不是“把所有东西都放到链上”，而是要判断：

\> 哪些状态需要被公共世界承认，哪些状态应该留在私人或平台环境里？

\### 9.4 新手如何在 AI 辅助下保持判断力？

我这周也开始用 AI 生成最小 Solidity 合约。

这让我多了一个问题：

\> 当我还不懂 Solidity 和智能合约安全时，我应该如何判断 AI 生成的代码是否可靠？

目前我能做的检查还很基础：

\- 能不能编译

\- 函数是否符合预期

\- 权限是否合理

\- 有没有不必要的复杂逻辑

\- 有没有隐私或资产风险

但我知道这还远远不够。

所以后面我也想继续学习：

\> AI 可以帮助新手进入 Web3，但新手不能把 AI 输出当成最终答案。真正重要的是逐渐建立自己的检查能力。

\## 10. 最后的收束

所以我现在对 Web3 的态度是：

\> 我还不懂它，但我已经开始知道应该问什么问题。

我从 Web3 是“炒币”这个很窄的印象，走到了一个稍微清楚一点的理解：

\> Web3 是围绕状态、控制权、可验证性和信任结构展开的一套新数字基础设施。

而我接下来最想继续理解的是：

\> 当越来越多行为可以被链上记录时，我们如何判断这些记录真正代表什么。
<!-- DAILY_CHECKIN_2026-07-10_END -->

# 2026-07-09
<!-- DAILY_CHECKIN_2026-07-09_START -->


## What I Did Today

Today I continued Monad Builder Camp Week 1 and moved from concept learning into real onchain practice.

I learned and discussed:

-   why there are many different blockchains
    
-   how to understand chains as different public worlds or games
    
-   why Web3 does not simply put everything into one unified world
    
-   how Web3 relates to Web2
    
-   what blockchain state means at a beginner level
    
-   why a transaction changes the state of a specific chain
    

I also completed hands-on work:

-   created a course-only MetaMask wallet
    
-   added Monad Testnet
    
-   confirmed MetaMask was on Monad Testnet
    
-   got testnet MON
    
-   completed my first Monad Testnet transfer
    
-   opened the transaction in MonadVision
    
-   recorded the transaction hash and key fields
    

## Proof

Course wallet:

```
0x2596976c6D2D5a301eFc3833e2749bDF368223e5
```

First Monad Testnet transaction:

```
0xfcc719809d3984548a88305e8753d47539eb251fd800136a8c6bf24eeea441bd
```

Explorer link:

```
https://testnet.monadvision.com/tx/0xfcc719809d3984548a88305e8753d47539eb251fd800136a8c6bf24eeea441bd
```

Transaction summary:

-   Status: Success
    
-   From: `0x2596976c6D2D5a301eFc3833e2749bDF368223e5`
    
-   To: `0xb11256348b1cba14E77Ca541A9b4a7E2Da2ecC49`
    
-   Value: `0.01 MON`
    
-   Transaction fee: `0.002162856067344 MON`
    
-   Gas used: `21,000`
    

## Problems I Had

### 1\. I did not understand why there are many chains

At first, it felt strange that Web3 has many separate chains. If everything were stored together, it seemed like it would be more convenient.

Resolution:

I started using the "different public game worlds" analogy. Different chains have different rules, costs, communities, speeds, and opportunities. People use a chain when the thing they want to do lives in that world.

### 2\. I did not understand blockchain state

The word "state" felt abstract because I do not have a finance or computer science background.

Resolution:

I understood state as "the current situation of a world." In a game, this means level, inventory, gold, and completed quests. Onchain, this means balances, ownership, votes, contract data, and transaction results.

### 3\. The website said "No wallet detected"

When trying to connect from the Codex in-app browser, the page said:

```
No wallet detected. Please install a compatible wallet to continue
```

Resolution:

The Codex in-app browser does not have the MetaMask extension. Wallet actions need to happen in Chrome or another browser where MetaMask is installed.

### 4\. I was confused by network vs token

I saw MON in the wallet and wondered why there was no "Monad Testnet" in the receiver field.

Resolution:

Monad Testnet is the network. MON is the token used on that network. The receiver field is only an address.

Mental model:

```
current network = the world I am acting in
MON = the currency in that world
receiver address = the account I send to
```

## What I Learned

The most important sentence from today:

```
链记录状态，钱包控制身份，交易改变状态，gas 支付改变状态的成本。
```

I also learned:

-   public addresses can be shared, but private keys and seed phrases must never be shared
    
-   a wallet does not store assets; the chain records balances, and the wallet controls keys
    
-   a transaction can be inspected through a block explorer
    
-   failed transactions can still consume gas because the network may spend computation before failure
    
-   Web3 is not just "trading"; it is about verifiable state and user-controlled actions
    

## How I Felt

At the beginning, the concepts felt scattered and abstract. I was especially confused by why Web3 needs many chains and why transactions are so central.

The "different games / public worlds" analogy made things easier. After completing the first transaction and seeing it in MonadVision, the idea became more concrete: the transaction was not just a button click in a website. It was a signed action that changed state on Monad Testnet and left a public record.

I still feel that Web3 has many layers and the user experience is not very intuitive yet. But I now have a clearer first mental map, and I completed a real onchain action safely with a course-only wallet.

## Next

-   Practice reading more transaction details in the explorer.
    
-   Learn what `from`, `to`, `value`, `gas price`, and `gas fee` mean in more depth.
    
-   Continue Week 1 tasks toward AI + Solidity + contract deployment.
<!-- DAILY_CHECKIN_2026-07-09_END -->

# 2026-07-08
<!-- DAILY_CHECKIN_2026-07-08_START -->




学习ai agent支付，先打卡
<!-- DAILY_CHECKIN_2026-07-08_END -->

# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->





和ai讨论心理测量+web3，得到结论为理念很好，但是实践层面上可能没有现存的启发式测量有削。  
今日目标：开始实践
<!-- DAILY_CHECKIN_2026-07-07_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->







### **Web3实习计划开营式（录播）：**

比特币本质上是一种区块链，强共识但是低性能。Monad在不降低性能的情况下，提高了区块链的上限。Monad同时进行“共识”和“执行交易”。

### **实习手册：**

进行入门导读的时候，我有几个问题：  
1\. 为什么需要有区块链？  
2\. 为什么需要更快的交易速度？  
3\. 如何在保证区块链上的信息是公开透明的同时，又是匿名的？

沿着这几个问题，我初步理解区块链的核心动机，是在没有中心化信任机构的情况下，通过分布式共识与密码学机制维护一个不可篡改的账本，从而降低对银行、平台等中介的依赖，并支持数字价值的唯一性与可验证转移。为了成为真正的基础设施，它还必须提升交易效率，否则难以进入现实支付与金融场景。

在机制层面，区块链通过地址与公私钥体系实现伪匿名，使交易公开透明但不直接绑定现实身份，从而在可验证性与隐私之间做出折中。同时，它的“可信性”更多来自**_分布式结构_**与**_经济激励假设_**，而非绝对安全，本质是降低单点操控风险，而不是消除操控可能。

但我也仍然存在疑问：这种“信任代码规则”的结构，是否真的比信任人更可靠？它在实践中依然可能被算力、资本或开发者影响，从而形成新的权力集中。此外，所谓规则不可随意更改，也引出了系统如何演化的问题：当进化依赖社区共识时，它是否只是把政治过程技术化，而并未真正消除权力结构？从这个角度看，区块链更像是一种权力的重新分布，而不是权力的消失，这种“技术中心主义”的可信性仍值得进一步质疑。
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

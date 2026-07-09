---
timezone: UTC+8
---

# Suzuki-yki

**GitHub ID:** Suzuki-yki

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-09
<!-- DAILY_CHECKIN_2026-07-09_START -->
# 今日学习笔记：

（弥补前三天未学习的内容！今天是第一天，明天补充day2和day3还有day4的还有day5的！）

### 区块链是一种去中心化的分布式账本，用于在网络节点中，透明且不可纂改的记录事务数据。

### 区块链由区块+链组成：

区块：每一个区块包含两个部分，交易记录一些信息，和之前的区块摘要

链：一条链只能连接两个区块，按照顺序依次串联

**此时区块链的特性**：不可篡改，公开透明，快速交易。

**分布式网络：**一个区块链节点有非常多的节点去记账，保证历史交易的没有被篡改（只要被修改的结点记录没有超过51%，改动将不会被认可）和真实性！

**区块链+分布式网络**的结合是区块链技术变得去中心化+且真正的不可篡改。其次这个网络如何让别人愿意主动维护和服务呢？这里就涉及到了**BTC**，网络节点服务商可以得到代币奖励，而且比特币具有货币属性。

一条区块链由用户发起交易，交易被广播到各个节点，然后各个节点验证交易的合法性，然后通过共识机制，矿工将验证过的交易打包成新的区块，然后链上上链，最后成功出块的的节点可以获得协议奖励。

### **区块链分为三大链：**

公链：开放访问，安全 但是速度很慢

私链：不公开的私人链，速度快，可控

联盟链：联合治理，安全与速度平衡

### **WEB3：**

现在用的大多数网址页面，例如阿里巴巴的淘宝啊什么的，当前互联网大多数都是**web2**，数据存储在服务器中，用户作为内容生产者不控制数据，坏处是只要平台收回你的账号可以以任何原因而你没有办法左右，而**web3**（去中心化互联网）用户拥有自己的数据，谁都没有权力控制你的数据，个人拥有更高的隐私权和所有权。

**以太坊（Ethereum）**是一个开源的去中心化区块链平台，通过其原生加密货币以太币（Ether，简称 ETH）提供去中心化的以太虚拟机（EVM）来处理点对点合约，以太坊的核心创新在于 **智能合约（Smart Contracts），**智能合约是可执行代码，能够在满足预设时自动执行操作。**ETH**是以太币的原生货币。

**比特币 和 以太坊的区别：**

总量2100万枚,去中心的数字化货币 | 去中心化平台，支持智能合约和Dapps

以太坊能够支持更多应用场景，而比特币更专注于存储价值。以太坊也向比特币一样通过PoW（proof of work）工作量证明来维护网络安全。

**关于PoS机制**：需要质押32ETH（！！！这么多）才能成为验证者。系统随机选择验证者来提议和验证区块，验证者会获得新发行的ETH+交易费用，当然如果是恶意的人会被扣除质押的ETH。（质押这么多是有原因的）

相比于PoW,PoS的能耗更少，攻击成本也更高，区块确认也更高更快。

**以太坊的生态概览**分为：

L1（主网）

-   **以太坊主网**：核心区块链，负责最终安全性与共识。
    
-   **EVM**：以太坊虚拟机，执行智能合约代码。
    
-   **账户系统**：外部账户（EOA）与合约账户（CA）共同构成网络基础。
    

L2（二层扩展解决方案）

-   **Rollup**：通过将交易批量处理后提交至 L1，降低 Gas 费。
    
-   **Optimistic Rollup**：假设交易合法，仅在争议时验证。
    
-   **ZK Rollup**：通过零知识证明验证交易，无需链上争议。
    

侧链（SideChains）

-   独立运行的链，通过桥接与主网交互。
    

以太坊深受密码朋克运动影响，体现了对技术赋权个人、重塑社会协作的愿景。以太坊不仅仅是一条区块链，更是一个全球共享的“分布式计算机”。它的核心价值在于通过代码实现无需信任的自动化规则（如智能合约），而这一切的背后依赖于三个关键机制：**账户系统、Gas 模型 和 以太坊虚拟机（EVM）**。

EVM（Ethereum Virtual Machine）是 **以太坊的“大脑”**，是专门用来**运行智能合约的虚拟计算机**。它运行在每个节点上，确保整个网络在处理代码时，**结果都一致、可信任。**
<!-- DAILY_CHECKIN_2026-07-09_END -->

# 2026-07-08
<!-- DAILY_CHECKIN_2026-07-08_START -->

## **今日学习日记：**

（主播才发现其实每天都有学习任务来着，因为第一次参加我才看到旁边那个课程安排每天该做什么）

主播今天也有点偷懒了，真的拜托不要这样下去了好吗......好痛苦。

我的**代码思路**是这样的：按照CEI的标准先checks，用户前端点击售卖（调用我的智能合约），这时我接收前端传来的数据，当然不能相信前端，所以需要check seller调用的地址是否=msg.sender，其次seller是否拥有该NFT，我目前想到的就只有这些checks，我开始构思代码的逻辑时候，ai说先教我ERC721再开始写代码吧！

OpenZepplin 的**ERC721**.，ERC721就是一个写好的NFT的engine，然后其中关键的代码：

-   mapping (uint256 => address) public \_owners;
    
-   mapping (address => uint256) public \_balances;
    

这两个都是tokenid 和地址,虽然重复了，但是是有重复的必要的，因为如果用户查询你直接遍历的话需要花费非常多的gas去存储，所以Space For Time（用空间换时间）！

### **ERC721和IERC721的区别：**

ERC721是implementation，里面有mapping，ownerof()等等...它可以运行。

IERC721是interface，里面没有代码只是定义你如果是ERC721你需要包含哪些函数！  

Marketplace 面向的是"标准（Interface）"，而不是某一个具体实现。然后我学到了这句话：**Program to an Interface, not an Implementation.（面向接口编程，而不是面向实现编程。）**（当然主播其实并没有完全理解这句话的意思 (。. 。；） ）

学到的一个**知识点**：**_address(0)_**叫**_Zero Address_**(零地址)，它表示的意义是不存在。

这里还要说到我前面写的关于cei了，写代码要以cei为规范进行思考，当我运行我的maekrtplace的智能合约时第一步不是创建liastings而是先check你是**owner**吗？

所以串联我这些天学到的知识，大致流程图如下所示：

React Frontend

│

│ TokenId

▼

Marketplace

│

│ ownerOf(tokenId)

▼

ERC721 Contract

│

│ 查询 \_owners Mapping

▼

返回真正 Owner

│

▼

Marketplace 比较： owner == msg.sender

今天主播就学到这里，明天一定要学完！（而且我是一边学一边写笔记...其实学完了把今天所学的知识整理成笔记才更利于我学习，明天就按照这样做吧！）
<!-- DAILY_CHECKIN_2026-07-08_END -->

# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->


## **今日学习笔记：**

智能合约的运行其实是contract A调用contract B,执行 contract B的代码再返回contract A.

所以智能合约之间本质就是**函数的调用**。

所以区块链有两种地址：

1.  **EOA**（externally Owned Account）普通钱包 ：这个就只是接收和转账
    
2.  **Contract account** 一个程序的地址 ：这些地址里面有代码，可以执行
    

这就要提到我今天学的关于**重入攻击(Reentrancy Attack)**是如何运行的了。

之前ai一直教我说管理listings的合约必须先删除listings再操作我其实一直不理解，今天我知道了重入攻击的原理就是利用了“智能合约之间本质就是函数调用”。正常情况下我的marketplace的智能合约这样运行：

调用 contract => 给seller转ETH =>给buyer转NFT，

而重入攻击后则这样运行：

attack contract 调用我的 contract => buyItem() 给seller转ETH =>此时这里attack contract利用receive()再次调用我的contract ，因为listings未删除，还显示存在，所以继续 transfer ETH ...如此循环

历史上著名的The DAO Attack 就是利用了合约是先转再更新状态这一特点发动了攻击。

所以这里就引入了**CEI（checks efffects interactives）**的知识，先delect listings然后再转ETH时，attack contract再次进行调用时因为listings不存在了，所以直接revert，无法攻击，CEI是企业设计规范（Enterprise Security Pattern）。

AI告诉我一句话：**Update your own state before interacting with others** .

然后我了解到只有在用到这些方法时必须需要引入Reentrancy Guard：call()，transfer()，send()，safeTransferFrom()，调用其他合约，ETH Transfer。我理解的是只要有**_外部交互_**就需要小心！

今天姑且就学了这么点，**明天任务是把所有的代码都完成**。

（另外我还了解到其实先转NFT再转ETH和先转ETH再转NFT两种都没区别。。。。结果昨天学的时候ai还告诉我其中一种更好，但是无论哪一种两个都属于interactions啊，所以先后顺序根本没有统一标准！！！）
<!-- DAILY_CHECKIN_2026-07-07_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->



### 今日学习笔记：

（主播在兼职工作所以为手机写的笔记可能不够精美）

因为第一节可hai老师主要在回答大家的问题，go leaning时间我是便挂会议边上班，所以没有认真听！主播就分享一下今天主播自学的一些笔记吧！（我认真听完了hao老师的一些回答，现在为了能够找到工作所以决定优先以运营开始了。）

我今天自己的小项目学习到要写一个**smart contract管理物品listings的状态。**

我很讨厌ai直接甩代码让我复制粘贴，所以叫她先给我讲思路然后我理顺了再开始写代码。

我自己整理了一下思路：

_这都是我请教AI了解到的知识(｡ì \_ í｡)_

像opeansea一些平台的marketplace都是一个合约管理多个NFT。但是根据不同的需求mapping也有不同的写法

一般有两种方式

**A** 把NFT的合约地址加上NFT的tokenid组成一个新的键（这种适用于无限NFT系列，然后storage更简单

**B**采用嵌套mapping，代码类似于_mapping（address => mapping（uint256 => Listing））public listings_ （这种就适合分类，因为如果要出不同系列的NFT那前端设计需要进行区别

后续学到了设计protocol，和CEI，check effect interactions。以及AI问我关于lisings是先transfer nft 然后transfer eth还是先transfer eth再transfer nft，我选择的是先转NFT再转ETH，然后ai跟我说其实两种只要任意环节失败了都会取消所有交易恢复到初始状态，但是大多数都选择先NFT然后ETH，是因为CEI，然后我后面要开始学习关于安全的问题了。

**以上就是今天学习的进度，因为手机打字设计排版实在太麻烦了，主播只写这么多了，明天我要先学了之后用电脑完成我的学习日记！ヽ(；▽；)ノ**
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

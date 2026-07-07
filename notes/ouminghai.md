---
timezone: UTC+8
---

# manyu

**GitHub ID:** ouminghai

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->
# **#0x00学习什么是 Monad？**

Monad 有几个关键指标：

-   **每秒 10,000 笔交易（10,000 transactions per second）** —— 足够支撑真正面向消费者的应用
    
-   **800 毫秒最终性（800 millisecond finality）** —— 快到让人觉得是即时的
    
-   **更低的硬件成本** —— 这意味着更多人可以运行节点，让网络更去中心化
    

这些不只是数字。它们决定了用户打开一个应用时，感受到的是流畅响应，还是漫长等待。

Monad 能做到这些，靠的是共识层和数据层的一系列创新：MonadBFT、RaptorCast 和 MonadDB。后面的进阶课程会细讲。现在先记住结果：Monad 上的应用响应很快，手续费也接近于零。

# #0x01**部署你的第一个 Monad 合约**

# **#0x02 为什么 Monad 体验不同**
<!-- DAILY_CHECKIN_2026-07-07_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->

# **0x0.进入 Web3 与链上世界**

### **1\. 课程钱包地址**

0x5f2984012287D703a9a42e15BBd50D1B1CE9427b

### **2.Monad Testnet 网络配置截图**

![image.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/ouminghai/images/2026-07-06-1783319033453-image.png)

### 3\. 区块浏览器中查询该地址的截图或链接。

![image.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/ouminghai/images/2026-07-06-1783319232102-image.png)

### 4\. 100 字左右说明：链上产品和普通互联网产品有什么不同。

1.  链上产品在运行的方式上与互联网产品不同之处在于，web2 产品有部署的主体，web3 需要通过 gas 或者其他的激励部署在全球的各个节点，具有去中心化的特点。
    
2.  在数据存储上，web2 产品一半是存储在数据库，web3 虽然也是存储在文件，但是它是由各个链去连接，储存在区块链中
    
3.  登录方式不同，web2 是通过账号密码或者密钥登录，web3 一般是利用助记词，私钥去登录，唯一 id 是钱包的地址
    

## **  
0x2链上实践｜完成第一笔测试网交易**

**完成你的第一笔 Monad Testnet 链上交易，并学会使用区块浏览器查看交易状态。**

你需要完成：

1.  获取测试网资产。
    
2.  完成一次测试网转账或应用交互。
    
3.  保存 transaction hash。
    
4.  在区块浏览器中查看交易详情。
    
5.  用自己的话解释这笔交易发生了什么。
    

建议重点理解：

-   `from` / `to` 分别是谁。
    
-   `value` 表示什么。
    
-   `gas` 和手续费代表什么。 - 交易状态是成功还是失败。 - 失败交易为什么也可能消耗 gas。
    
    你也可以发布一条 推特/小红书 内容，记录自己完成第一笔链上交易的过程。
    

请提交以下内容： 1. Transaction hash。 2. 区块浏览器链接。 3. 简短说明：这笔交易发生了什么。

**1.Transaction hash**

0xfef4430b92ae37d588193c389d995c114d298b53a30308053bf3cc779733424a

**2.区块浏览器链接**

[**https://testnet.monadscan.com/address/0x5f2984012287d703a9a42e15bbd50d1b1ce9427b**](https://testnet.monadscan.com/address/0x5f2984012287d703a9a42e15bbd50d1b1ce9427b)

**3\. 简短说明：这笔交易发生了什么**

这笔交易发生在 Monad Testnet 测试网络上。我通过 MetaMask 发起了一笔从自己地址到自己地址的转账交易，金额为 2 MON。Transaction Fee:0**.**0021 MON。当我确认交易后，钱包将交易广播到 Monad 网络。网络中的节点会先验证交易的签名和余额是否正确，然后将交易打包进区块中。交易被打包后，我可以在区块浏览器中看到该交易的状态为成功（Success），并且可以查看交易的发送方地址、接收方地址、交易金额以及 Gas 费用等信息。这说明链上交易是由去中心化节点共同验证和记录的，而不是由某一个中心服务器控制。

## **0x3 AI 辅助开发｜用 AI 生成一个最小 Solidity 合约**

使用 AI 工具生成一个最小 Solidity 合约，并完成一次人工检查。

你可以选择以下简单合约方向：

\- 留言板 - 投票合约 - 打卡合约 - NFT Badge - 积分记录 - Onchain Todo

你需要完成：

1.  写一个 Prompt，让 AI 帮你生成 Solidity 合约。
    
2.  阅读 AI 输出的代码。
    
3.  让 AI 解释合约结构。
    
4.  手动检查至少 3 个关键点。
    
5.  记录你对 AI 输出做了哪些修改或判断。
    

本任务的重点不是让 AI 替你完成开发，而是练习如何让 AI 辅助你理解代码、生成初稿，并由你完成最终判断。

建议人工检查点包括：

\- 合约是否能编译。 - 函数是否符合你的预期。 - 是否存在明显权限问题。 - 是否使用了不必要的复杂逻辑。 - 是否有潜在安全风险。 - 变量和函数命名是否容易理解。

1.  **你使用的 Prompt。**
    
    选择的是 nft badge 方向
    
    请帮我写一个 Solidity NFT 合约，用于“粉丝经济 NFT Badge 系统”。
    
    需求：
    
    1.  基于 ERC-721 或简化版本
        
    2.  用户可以 mint 一个粉丝 NFT
        
    3.  每个地址只能 mint 一次
        
    4.  可扩展为粉丝等级系统（Bronze / Silver / Gold）
        
    5.  代码必须可以在 Remix 编译通过
        
    6.  结构尽量简单，适合初学者
        
    7.  不需要复杂权限系统
        
    
    请解释代码结构，并说明可以如何扩展成粉丝经济系统（如积分、空投、DAO）。
    

2.  **AI 生成的主要输出。**
    

这个简单的合约是粉丝经济的基石，你可以通过以下方向进行扩展：

NaN.  积分系统 (Points System)
      
      -   扩展 : 引入一个 ERC-20 代币（如 $FAN 积分）。
          
      -   逻辑 : 当用户持有勋章并参与互动（如签到、购买周边）时，获得积分。当积分达到阈值，合约自动调用 upgradeLevel 。
          
NaN.  分级空投 (Tiered Airdrops)
      
      -   扩展 : 编写一个空投脚本或合约。
          
      -   逻辑 : 只有 fanLevels\[tokenId\] == Gold 的用户才能领取高级奖励，而 Bronze 用户只能领取基础奖励。
          
NaN.  治理与 DAO (Governance)
      
      -   扩展 : 结合 Snapshot 或自定义治理合约。
          
      -   逻辑 : 等级越高，投票权重越大。例如：Gold 级粉丝 1 票抵 5 票，参与决定偶像的下一场活动城市。
          
NaN.  动态元数据 (Dynamic Metadata)
      
      -   扩展 : 修改 tokenURI 函数。
          
      -   逻辑 : 根据 fanLevels\[tokenId\] 返回不同的图片链接（Bronze 返回青铜徽章图片，Gold 返回发光的金牌图片）。 Remix 编译说明
          
NaN.  打开 Remix IDE 。
      
NaN.  创建新文件 FanBadgeNFT.sol 并粘贴代码。
      
NaN.  在左侧选择 Solidity Compiler ，点击 Compile FanBadgeNFT.sol 。
      
NaN.  在 Deploy & Run Transactions 界面点击 Deploy 即可部署到本地测试环境。
      

2.  **合约源码。**
    

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;
​
import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "@openzeppelin/contracts/access/Ownable.sol";
​
/**
 * @title FanBadgeNFT
 * @dev 粉丝经济 NFT Badge 系统合约
 * 方案一：增加 addressToTokenId 映射，方便直接通过地址查询拥有的 tokenId
 */
contract FanBadgeNFT is ERC721, Ownable {
    uint256 private _nextTokenId;
​
    // 粉丝等级枚举
    enum FanLevel { Bronze, Silver, Gold }
​
    // 记录每个 Token ID 对应的粉丝等级
    mapping(uint256 => FanLevel) public fanLevels;
    
    // 记录每个地址是否已经领取过勋章（每个地址限领一个）
    mapping(address => bool) public hasMinted;
​
    // 方案一新增：记录每个地址对应的 Token ID
    mapping(address => uint256) public addressToTokenId;
​
    // 事件：当用户提升等级时触发
    event LevelUpgraded(uint256 indexed tokenId, FanLevel oldLevel, FanLevel newLevel);
​
    /**
     * @dev 构造函数
     * @param name NFT 的名称
     * @param symbol NFT 的代号
     * @param initialOwner 初始管理员地址
     */
    constructor(string memory name, string memory symbol, address initialOwner) 
        ERC721(name, symbol) 
        Ownable(initialOwner) 
    {}
​
    /**
     * @dev 用户领取粉丝勋章 (Mint)
     * 默认领取为 Bronze (青铜) 等级
     */
    function mintBadge() public {
        require(!hasMinted[msg.sender], "Each address can only mint one badge.");
        
        uint256 tokenId = _nextTokenId++;
        
        // 记录状态
        hasMinted[msg.sender] = true;
        addressToTokenId[msg.sender] = tokenId; // 方案一核心：记录地址与ID的绑定关系
​
        _safeMint(msg.sender, tokenId);
        fanLevels[tokenId] = FanLevel.Bronze; // 初始等级
    }
​
    /**
     * @dev 管理员手动提升用户等级
     */
    function upgradeLevel(uint256 tokenId, FanLevel newLevel) public onlyOwner {
        require(_ownerOf(tokenId) != address(0), "Token does not exist.");
        FanLevel oldLevel = fanLevels[tokenId];
        require(uint256(newLevel) > uint256(oldLevel), "Can only upgrade to a higher level.");
        
        fanLevels[tokenId] = newLevel;
        emit LevelUpgraded(tokenId, oldLevel, newLevel);
    }
​
    /**
     * @dev 获取某个勋章的等级名称
     */
    function getLevelName(uint256 tokenId) public view returns (string memory) {
        require(_ownerOf(tokenId) != address(0), "Token does not exist.");
        FanLevel level = fanLevels[tokenId];
        
        if (level == FanLevel.Bronze) return "Bronze";
        if (level == FanLevel.Silver) return "Silver";
        if (level == FanLevel.Gold) return "Gold";
        return "Unknown";
    }
}
​
```

2.  **你做过的人工修改或判断说明。**
    

1.修改 nft 的代号

2.修改判断粉丝等级的逻辑

3.依赖的导入问题，

4.deploy 的时候报错了，发现Ownable函数参数调用错误

2.  **至少 3 条“AI 生成代码需要人工检查的地方”。**
    

在使用 AI 生成智能合约代码（如我们刚才编写的 FanBadgeNFT.sol ）时，人工检查至关重要。以下是至少 3 个必须人工核查的地方：

NaN.  权限管理与访问控制 (Access Control)
      

-   风险点 : AI 可能会忘记添加权限修饰符（如 onlyOwner ），或者错误地使用了修饰符。
    
-   人工检查 : 确认像 upgradeLevel 这样敏感的函数是否真的只能由管理员调用？如果任何人都能提升自己的等级，粉丝等级系统就会崩溃。检查 Ownable 的初始化是否正确，避免合约处于“无主”状态。
    

2.  库版本与依赖兼容性 (Library Versions)
    

-   风险点 : AI 的训练数据可能包含旧版本的 OpenZeppelin 库。不同版本（如 v4.x vs v5.x）的语法差异巨大。
    
-   人工检查 :
    
    -   比如在 OpenZeppelin v5.0 中， _exists() 函数被删除了，改用了_ ownerOf() 。
        
    -   检查 import 路径是否能在 Remix 中正常加载。
        
    -   确认 pragma solidity 版本是否与库的要求匹配。
        

3.  业务逻辑漏洞与边界条件 (Business Logic & Edge Cases)
    

-   风险点 : AI 擅长写标准模版，但容易忽略特定业务需求。
    
-   人工检查 :
    
    -   限领检查 : 确认 hasMinted 逻辑是否在 \_safeMint 之前执行，防止重入攻击导致用户领走多个 NFT。
        
    -   逻辑漏洞 : 比如 upgradeLevel 是否检查了等级只能往上升？如果 AI 写成了 != 而不是 > ，用户可能会从黄金等级降级到青铜。
        

4.  Gas 效率优化 (Gas Optimization)
    

-   风险点 : AI 生成的代码通常以可读性为主，可能不是最节省 Gas 的。
    
-   人工检查 :
    
    -   检查是否有不必要的 storage 变量读写。
        
    -   检查循环是否存在（在链上循环非常危险）。
        
    -   确认 string 类型的使用是否可以优化为 bytes32 以节省存储成本。 总结建议 在 Web3 领域，“代码即法律”。AI 可以帮你写出 90% 的原型，但剩下的 10%（安全性、兼容性、逻辑严密性）必须由人工进行“审计”。在 Remix 部署前，请务必查看编译器是否有 Warning 提示，那通常是人工检查的第一步。
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

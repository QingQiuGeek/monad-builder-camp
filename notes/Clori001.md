---
timezone: UTC+8
---

# kkk

**GitHub ID:** Clori001

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-08
<!-- DAILY_CHECKIN_2026-07-08_START -->
# 2.1

# **EPF / Ethereum Protocol 笔记**

## **一、这节到底在讲什么？**

这节不是在讲普通 Web3 应用，也不是在讲怎么用钱包、怎么写简单智能合约，而是在讲：

如果想进入 Ethereum protocol 方向，应该怎么学习、怎么选方向、怎么做贡献、怎么准备 EPF。

也就是说，重点从“使用区块链”往更底层走：

```
普通用户：用钱包、转账、查交易
DApp 开发者：写智能合约、做前端、让用户交互
协议研究 / EPF：研究以太坊本身怎么运行、怎么升级、怎么被维护
```

* * *

## **二、EPF 是什么？**

### **1\. 基本定义**

**EPF = Ethereum Protocol Fellowship，以太坊协议奖学金。**

它是以太坊基金会为了降低进入以太坊协议研究和开发的门槛而设立的项目。

简单说：

EPF 是帮助新人进入 Ethereum protocol 世界的学习和贡献项目。

### **2\. 它不是普通智能合约训练营**

EPF 不是主要教：

```
写 Solidity
做 NFT
做 DeFi
做钱包
做 DApp 页面
```

它更关注：

```
以太坊底层怎么运行
执行层和共识层怎么配合
客户端怎么实现协议
EIP 如何推动协议升级
开发者如何参与开源贡献
```

### **3\. Permissioned / Permissionless**

EPF 有两种参与状态：

**Permissioned**

```
通过申请 / 面试
获得正式支持或津贴
参与更正式的 fellowship 流程
```

**Permissionless**

```
没有通过也可以继续参与
依然可以学习、做项目、提 PR、参与讨论
如果成果好，也可能被认可
```

所以重点不是“有没有被录取”，而是：

最后有没有真正做出东西。

* * *

## **三、它和钱包、链、DApp 有什么关系？**

### **1\. 钱包是什么层级？**

钱包，比如 MetaMask、Rabby，是建在以太坊之上的 **应用层工具**。

钱包主要负责：

```
连接网络
切换链
管理地址
签名交易
发起交易
连接 DApp
```

一句话：

钱包是在帮用户“使用链”。

### **2\. EPF 研究的是什么层级？**

EPF 不是研究钱包这种应用，而是研究 **链本身**。

它关心的是：

```
这条链怎么运行
交易怎么执行
区块怎么确认
协议怎么升级
客户端怎么实现
网络怎么更安全、更快、更便宜
```

一句话：

钱包是在“用路”，EPF 是在研究“这条路怎么修、怎么扩、怎么维护”。

### **3\. 大白话比喻**

```
区块链 = 一条高速公路
钱包 = 车和驾驶证，帮用户上路
智能合约 = 路上的自动机器，触发后按规则执行
客户端 = 维持高速公路运行的基础设施系统
协议开发 = 研究高速公路规则、结构、扩容和安全
```

所以：

```
普通用户关心：怎么转账？
DApp 开发者关心：怎么写合约给用户用？
EPF / 协议开发关心：这条链底层到底怎么运行？
```

* * *

## **四、Ethereum protocol 主要学什么？**

### **1\. 执行层 Execution Layer**

执行层负责：

```
交易执行
账户状态变化
EVM 执行
智能合约运行
gas 消耗
余额变化
```

可以理解为：

执行层负责“交易到底怎么被执行”。

比如用户发起一笔转账或调用合约，执行层要判断：

```
这个账户有没有余额？
这个交易是否合法？
合约代码怎么跑？
执行后状态怎么变化？
gas 怎么扣？
```

### **2\. 共识层 Consensus Layer**

共识层负责：

```
验证者
区块确认
链的安全性
谁来出块
大家如何同意哪条链是正确的
```

可以理解为：

共识层负责“大家怎么达成一致”。

也就是：

```
谁提出新区块？
谁验证新区块？
这个区块是否被接受？
链是否安全？
```

### **3\. 客户端 Client**

客户端是执行层或共识层的具体代码实现。

它不是一个单独抽象概念，而是实际运行以太坊的软件。

比如：

```
go-ethereum / geth
Lighthouse
Prysm
Nethermind
Besu
```

老师提到的 Go 客户端，一般是：

```
go-ethereum / geth
```

也就是用 **Go / Golang** 写的以太坊客户端。

注意：

Go 是 Google 开发的编程语言，不是 Godot 游戏引擎。Godot 里常用的是 GDScript。

### **4\. EIP**

EIP 是 Ethereum Improvement Proposal，以太坊改进提案。

它负责描述：

```
以太坊要改什么
为什么要改
怎么改
会影响哪些部分
执行层 / 共识层 / 客户端是否需要更新
```

老师说 EIP 刚开始看会比较难，因为它写法很像技术论文。

* * *

## **五、EPF 的学习路线**

### **1\. 第一阶段：补基础**

先理解以太坊这台“机器”怎么运行。

需要先搞懂：

```
什么是执行层
什么是共识层
交易从发出到确认发生了什么
钱包和节点是什么关系
客户端在运行什么
EIP 为什么会影响协议升级
```

这一阶段可以看：

```
EPF Wiki
官方 specs
Ethereum 相关 wiki
基础书籍或中文材料
```

### **2\. 第二阶段：看公开讨论**

Ethereum 的很多研究和讨论都是公开的，尤其在 GitHub 上。

可以看：

```
GitHub issue
PR discussion
EIP discussion
specs 更新
客户端仓库里的问题
```

这一阶段重点不是马上贡献，而是先看懂：

```
大家在讨论什么问题？
这个问题属于执行层还是共识层？
它和哪个 EIP / 客户端 / spec 有关？
```

### **3\. 第三阶段：每周做 update / notes**

老师建议每周整理学习记录。

可以写：

```
这周看了什么
理解了什么
哪里还不懂
发现了哪些 issue
对哪个方向更感兴趣
下一步准备看什么
```

然后可以发到社媒，或者 at EPF mentor，让别人给反馈。

它的作用是：

```
逼自己持续输出
留下学习轨迹
让 mentor 看到你的进度
帮助后面申请或项目整理
```

### **4\. 第四阶段：选一个小方向深入**

不能一开始什么都做。

应该先选一个小 scope，比如：

```
执行层规范里的某个结构
某个 EIP 的实现影响
某个客户端里的测试问题
某个文档或 spec 不清楚的地方
某个数据结构替换方向
```

重点是：

范围要小，但问题域要有延展性。

### **5\. 第五阶段：做 issue / PR / proposal**

最后产出可以包括：

```
小 PR
issue 讨论
测试补充
spec 修改
EIP 分析
项目 proposal
最终项目交付
```

其中 PR 是比较硬的产出，但不是一开始就盲目提大 PR。

* * *

## **六、新手怎么贡献？**

### **1\. 不要一开始做大项目**

老师强调：

```
scope 要小
PR 要小
不要一上来改几百行
```

因为大 PR 的问题是：

```
review 成本高
别人不一定愿意看
新手自己也难控制质量
如果方向错了，浪费时间更多
```

### **2\. 可以从小 PR 开始**

新手适合：

```
修文档
修小错误
补测试
跟进一个小 issue
改一个很明确的问题
```

小 PR 的好处是：

```
容易 review
容易 merge
能快速建立正反馈
能慢慢积累贡献记录
```

### **3\. 但小 PR 也要有连续性**

不是今天修 A，明天修 B，后天修一个完全无关的 C。

更好的方式是：

```
先选一个问题域
再找这个问题域下面的 2-3 个小 issue
围绕同一方向连续贡献
```

这样看起来不是“随机贡献”，而是在一个方向上持续深入。

### **4\. 先选问题域，再选 issue**

老师特别强调了这个逻辑：

```
不是先乱找 issue
而是先想清楚自己想研究哪个问题
再找这个问题下能做的小 issue
```

比如：

```
先选：执行层中的某个数据结构
再找：这个结构相关的 spec issue / test issue / PR
```

这样后面更容易形成：

```
学习路线
连续 PR
项目 proposal
面试时可讲的方向
```

* * *

## **七、EPF 面试看什么？**

### **1\. 不是算法八股**

老师说 EPF 面试不是国内那种技术面试。

一般不会让人：

```
现场手撕算法
背八股
讲复杂密码学细节
硬考拜占庭问题
```

### **2\. 更看重理解和动机**

更可能问：

```
如何理解 Ethereum
怎么看 Ethereum 未来发展
对哪个模块感兴趣
对哪个 EIP 感兴趣
为什么想做这个方向
是不是真的想参与协议研究
```

核心是：

是否真的理解以太坊，并且有持续参与的动机。

### **3\. 英文也重要**

老师提到面试可能是英文。

所以除了技术理解，还需要：

```
能听懂问题
能表达自己的方向
能解释自己为什么对某个模块感兴趣
```

* * *

## **八、代码背景重要吗？**

### **1\. 不一定必须是 CS 背景**

老师说自己也不是纯计算机背景，而是电子信息背景。

EPF 并不是只看代码水平。

它更看重：

```
协议理解
研究能力
学习能力
持续探索
对以太坊的兴趣
最终产出
```

### **2\. 但会代码会更轻松**

如果会这些，会更容易进入对应方向：

```
Python：适合看 execution specs 这类规范代码
Go：适合看 go-ethereum / geth
Rust：适合看部分客户端或底层工具
JavaScript：有助于理解 Web3 前端和工具链
```

### **3\. 代码是工具，不是唯一目标**

对于 protocol research 来说：

```
代码实现很重要
但不是一开始就只拼代码
理解协议、看懂讨论、提出合理问题也很重要
```

* * *

## **九、职业发展和现实情况**

### **1\. 协议研究不一定是最稳定的职业路线**

老师讲得很现实：

```
如果单纯从经济回报看，协议研究不一定最稳定
很多人不是全职做协议研究
很多人是白天正常工作，业余参与 Ethereum research
```

### **2\. 更稳定的岗位可能在客户端团队**

比如：

```
维护客户端的公司
协议相关组织
以太坊生态里的基础设施团队
```

客户端团队可能更像正式工作，有更稳定的收入结构。

### **3\. 很多人是因为兴趣参与**

以太坊的特殊之处在于：

```
资料公开
代码开源
讨论公开
任何人都可以学习和参与
```

所以不少人是因为对去中心化、开源协议、以太坊未来感兴趣，才持续贡献。

* * *

## **十、以太坊生态的核心价值**

老师说不谈价格，只谈生态和技术。

他认为以太坊重要的地方在于：

```
全球开发者数量多
优秀开发者持续参与
协议讨论公开
代码开源
EIP 和客户端都能公开查看
生态仍然活跃
```

一句话：

以太坊最重要的不是短期价格，而是开发者、开源生态和长期协议演进。

* * *

## **十一、我这节课第一次知道 / 需要记住的点**

### **1\. EPF 不是智能合约课**

之前容易以为 Web3 学习就是：

```
钱包
合约
DApp
NFT
DeFi
```

但 EPF 关注的是：

```
Ethereum protocol
执行层
共识层
客户端
EIP
协议升级
```

### **2\. 钱包和协议不是一层东西**

```
钱包 = 应用层工具
协议 = 链本身的规则和运行机制
```

钱包是在用以太坊，EPF 是研究以太坊本身。

### **3\. 客户端不是“前端客户端”**

这里的客户端不是普通 app client，而是运行以太坊节点的软件。

比如：

```
go-ethereum / geth
```

### **4\. Go 不是 Godot**

Go 是 Golang，是后端和基础设施常用语言。

Godot 是游戏引擎，常用 GDScript。

### **5\. 小 PR 比大 PR 更适合新手**

不是越大越厉害。

新手应该：

```
scope 小
PR 小
方向连续
review 容易
逐步积累
```

### **6\. EPF 面试更像聊天和理解检查**

不是算法八股，而是看：

```
是否理解 Ethereum
是否真的感兴趣
是否知道自己想研究什么
是否能讲清楚方向
```

* * *

## **十二、后续 To-do**

### **1\. 加入社区**

EPF / Ethereum protocol Discord：

```
<https://discord.gg/8RPnPGEQtJ>
```

老师 X：

```
<https://x.com/JackCC60>
```

EPF Wiki：

```
<https://epf.wiki/#/README>
```

### **2\. 下一步学习路线**

```
先看 EPF Wiki
↓
补 Ethereum 执行层 / 共识层基础
↓
了解客户端是什么
↓
了解 EIP 是什么
↓
每周写一篇学习 update
↓
选一个小问题域
↓
找 1-2 个小 issue 试着理解
```

### **3\. 可以继续问的问题**

```
怎么判断自己更适合执行层还是共识层？
新手第一个小 PR 应该怎么找？
docs / test 类 PR 算不算有效贡献？
怎么让 2-3 个小 PR 看起来有连续性？
如果代码不强，应该先补代码还是先读 specs？
```
<!-- DAILY_CHECKIN_2026-07-08_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->

**区块链实操笔记：钱包、测试币、转账、合约部署**

-   **任务一：创建钱包** — 安装 **MetaMask** 浏览器插件，设置密码并保存私钥，添加 Mode 测试网网络，通过水龙头领取 5 个测试币
    
-   **任务二：首笔交易** — 从谷歌浏览器钱包向火狐浏览器钱包转账 1 个测试币，在区块链浏览器查询交易哈希，确认余额从 5 变为 6
    
-   **任务三：智能合约** — 用 ChatGPT 生成留言板合约，导入 Remix 自动编译，连接 MetaMask 部署至 Mode 测试网，成功写入并查询留言数据
    

**一、整体流程**

```text
安装 MetaMask
↓
创建钱包
↓
保存助记词 / 私钥
↓
添加 Mode Testnet 测试网
↓
复制钱包地址
↓
去 Faucet 领取测试币
↓
用区块链浏览器查询钱包余额
↓
进行第一笔测试转账
↓
复制交易 Hash
↓
在区块链浏览器查看交易详情
↓
用 AI 生成 Solidity 留言板合约
↓
打开 Remix
↓
创建 .sol 文件
↓
粘贴代码
↓
编译合约
↓
连接 MetaMask
↓
部署合约
↓
调用函数进行留言
↓
查看留言记录和交易 Hash
```

**二、准备钱包**

**工具：MetaMask**

操作顺序：

```text
浏览器打开插件商店
↓
搜索 MetaMask
↓
安装扩展程序
↓
创建新钱包
↓
设置密码
↓
保存助记词 / 私钥
↓
进入钱包首页
```

重点：

| 项目 | 作用 |
| --- | --- |
| 钱包地址 / 公钥 | 接收测试币、查询交易、连接合约 |
| 私钥 / 助记词 | 控制钱包资产，不能泄露 |
| 密码 | 打开本机 MetaMask 用 |

注意点：

```text
钱包地址可以复制给别人
私钥和助记词不能发给任何人
测试钱包也建议单独创建，不要用主钱包
```

**三、添加测试网络**

**网络：Mode Testnet**

操作顺序：

```text
打开 MetaMask
↓
点击网络选择
↓
添加网络
↓
选择 / 搜索 Mode Testnet
↓
确认添加
↓
切换到 Mode Testnet
```

如果钱包里默认没有 Mode Testnet，就需要手动添加网络。

添加成功后，MetaMask 顶部网络名称应显示为：

```text
Mode Testnet
```

这一步的作用：

```text
让钱包连接到测试链
后面的测试币、转账、合约部署都在这个测试网完成
```

**四、领取测试币**

**工具：Faucet 水龙头**

操作顺序：

```text
打开 Mode Faucet 页面
↓
复制 MetaMask 钱包地址
↓
粘贴到 Faucet 输入框
↓
点击领取
↓
等待到账
↓
回到 MetaMask 查看余额
```

关键词：

| 词 | 意思 |
| --- | --- |
| Faucet | 免费领取测试币的网站 |
| Test Token | 测试币，不是真钱 |
| Mode Testnet ETH | Mode 测试网上使用的测试币 |

注意点：

```text
Faucet 一般有限制
可能一天只能领一次
测试币只能用于测试，不能当真钱使用
```

**五、用区块链浏览器查钱包**

**工具：Mode Block Explorer**

操作顺序：

```text
复制钱包地址
↓
打开 Mode 区块链浏览器
↓
把钱包地址粘贴到搜索框
↓
查看钱包余额和交易记录
```

能看到的信息：

| 信息 | 作用 |
| --- | --- |
| Balance | 钱包余额 |
| Transactions | 交易记录 |
| From | 发送方 |
| To | 接收方 |
| Value | 交易金额 |
| Gas Fee | 手续费 |
| Status | 成功 / 失败 |

这一步的意义：

```text
确认测试币是否到账
确认钱包是否已经在测试网上产生记录
```

**六、完成第一笔测试转账**

操作顺序：

```text
准备两个钱包地址
↓
打开 MetaMask
↓
点击 Send
↓
粘贴接收方钱包地址
↓
输入测试币数量
↓
确认 Gas Fee
↓
点击确认发送
↓
等待交易成功
```

发送成功后：

```text
复制交易 Hash
↓
打开区块链浏览器
↓
搜索交易 Hash
↓
查看交易详情
```

交易详情重点看：

| 字段 | 看什么 |
| --- | --- |
| Transaction Hash | 交易唯一编号 |
| Status | 是否成功 |
| From | 哪个地址发出 |
| To | 哪个地址收到 |
| Value | 转了多少测试币 |
| Gas Fee | 花了多少手续费 |
| Timestamp | 交易时间 |

实操理解：

```text
转账不是只改余额
而是在链上生成一条永久记录
交易 Hash 就是这条记录的编号
```

**七、Gas Fee 操作理解**

每次链上操作都可能需要 Gas。

需要 Gas 的操作：

```text
转账
部署智能合约
写入留言
修改链上数据
调用需要改变状态的函数
```

通常不需要 Gas 的操作：

```text
单纯查询余额
读取留言
查看交易记录
查看合约数据
```

Gas Fee 公式：

```text
Gas Fee = Gas Used × Gas Price
```

实操判断：

```text
操作越复杂
写入的数据越多
Gas 可能越高
```

比如留言板：

```text
留言越长
链上需要存的数据越多
Gas 可能更高
```

**八、用 AI 生成智能合约**

任务：生成一个简单留言板合约。

可以给 AI 的 prompt：

```text
Generate a simple Solidity smart contract for a message board.
The contract should allow users to post messages, store the sender address, message content, and timestamp, and allow users to read all messages.
Use Solidity version ^0.8.0.
```

生成后需要保存的是：

```text
Solidity 合约代码
文件后缀 .sol
```

合约功能一般包括：

| 功能 | 作用 |
| --- | --- |
| postMessage | 写入留言 |
| getMessage | 查询单条留言 |
| getAllMessages | 查询全部留言 |
| messageCount | 查看留言数量 |

**九、打开 Remix 部署合约**

**工具：Remix IDE**

操作顺序：

```text
打开 Remix
↓
进入 File Explorer
↓
创建新文件
↓
文件名：MessageBoard.sol
↓
粘贴 AI 生成的 Solidity 代码
↓
保存
```

编译：

```text
点击 Solidity Compiler
↓
选择对应 Solidity 版本
↓
开启 Auto Compile
↓
或点击 Compile MessageBoard.sol
↓
确认没有红色报错
```

部署：

```text
点击 Deploy & Run Transactions
↓
Environment 选择 Injected Provider - MetaMask
↓
MetaMask 弹出连接确认
↓
确认连接
↓
确认网络是 Mode Testnet
↓
点击 Deploy
↓
MetaMask 弹出交易确认
↓
确认 Gas Fee
↓
点击 Confirm
↓
等待部署成功
```

部署成功后会出现：

```text
Deployed Contracts
```

这说明合约已经部署到测试网上。

**十、和合约交互**

留言操作：

```text
展开 Deployed Contracts
↓
找到 postMessage / addMessage 函数
↓
输入留言内容
↓
点击 transact
↓
MetaMask 弹出确认
↓
确认 Gas Fee
↓
点击 Confirm
↓
等待交易成功
```

查询留言：

```text
点击 getAllMessages
或输入 index 查询 getMessage
```

如果第一条留言编号是 0：

```text
第一条留言：0
第二条留言：1
第三条留言：2
```

原因：

```text
数组通常从 0 开始计数
```

留言成功后，可以看到：

| 数据 | 意思 |
| --- | --- |
| sender | 留言的钱包地址 |
| message | 留言内容 |
| timestamp | 留言时间 |
| index | 留言编号 |

**十一、查看合约交互记录**

留言之后也会产生交易 Hash。

操作顺序：

```text
复制交易 Hash
↓
打开区块链浏览器
↓
搜索 Hash
↓
查看交易详情
```

重点看：

```text
Status 是否成功
From 是哪个钱包
To 是哪个合约地址
Gas Fee 花了多少
Input Data / Logs 是否有合约交互记录
```

这里和普通转账不同：

```text
普通转账：From 钱包 → To 钱包
合约交互：From 钱包 → To 合约地址
```

如果留言没有转币：

```text
Value 可能是 0
但 Gas Fee 仍然会产生
```

因为链上写入数据本身就要成本。

**十二、实操检查清单**

完成这节后，应该留下这些东西：

| 检查项 | 是否完成 |
| --- | --- |
| MetaMask 钱包创建成功 |   |
| Mode Testnet 添加成功 |   |
| 测试币领取成功 |   |
| 钱包地址能在浏览器查到 |   |
| 完成一笔测试转账 |   |
| 保存转账 Hash |   |
| 能看懂 From / To / Value / Gas Fee |   |
| AI 生成 Solidity 合约 |   |
| Remix 编译成功 |   |
| MetaMask 成功连接 Remix |   |
| 合约部署成功 |   |
| 留言函数调用成功 |   |
| 留言交易 Hash 可查询 |   |
| 能读取留言内容 |   |

**十三、这节实操的本质**

```text
钱包负责身份
测试币负责支付操作成本
测试网负责练习
转账负责产生第一条链上记录
区块链浏览器负责查询记录
智能合约负责执行链上程序
Remix 负责编译和部署合约
Gas Fee 负责支付链上操作成本
Transaction Hash 负责定位每一笔链上操作
```

最重要的实操逻辑：

```text
只要是写入区块链的操作
通常都要钱包确认
通常都会消耗 Gas
通常都会生成 Transaction Hash
通常都能在区块链浏览器查到
```

* * *

* * *

* * *

**（以下笔记从notion粘贴）**

**海老师分享会**

**blog制作：**

“让他（ai）去学习一下怎么做个人网站，然后会把我的简历丢给他，然后他就会给我做一版框架出来，然后再根据我的想法来跟他慢慢提。就比如说。我是目前是我，当我现在这个个人网站，它其实当时最开始的时候，什么都没有的，就是。黑字，白底黑子，什么都没有，然后是让他一步一步来，按照我的想法来做一个，其实现在都还没优化好这边文字，这些内容还没有优化。”

**ai工作流：**

“cloud code，它适合小白去写代码，因为它可以。  
你只需要给他一个想法，他能把整体的框架给你跑出来，但是你让他去做细节的东西。  
Cloud是不如codex codex，它就适合去做一些细节的，你给它举指定具体的任务，他去完成。  
然后gemini呢，他就比较适合做ui。  
我先喝口水了。  
就比较适合做ui，然后我就会让他们三个。  
放到一起，放到一个工作流里面放到一个workflow里面，然后让。codex和cloud code，他们两个相互来调用，就比如说这个项目。  
因为有他们会有一个问题的一个形式。然后比如说这个。  
我这根据这些问题，我会判断这个。  
开发的复杂程度，然后复杂程度比较高的。  
就是比较繁琐，就会让Claudecode去做，然后一些比较细节方面就会让。就会让codex去，然后一些ui设计上面就会让它gemini去。”

当下web3，base **新加坡** 会大于 香港

to-do list

1.  去github收藏xiaohai老师的“三部曲”
    
2.  对这个profile的blog的前端风格设计很感兴趣呀
    
3.  它的my cube -ai工作流我也是很感兴趣等会去看看
    
    [截屏2026-07-06 19.18.00.png](https://us04file-paa.zoom.us/file/NzsNXPNAS_mPjDebOpfuJg?filename=%E6%88%AA%E5%B1%8F2026-07-06%2019.18.00.png&jwt=eyJhbGciOiJFUzI1NiIsImsiOiJ2dC8rcFVJKyJ9.eyJpaWMiOiJ1czA0Iiwib3JpIjoibHlueC1pbnRlcmFjdGlvbiIsImhkaWciOmZhbHNlLCJkaWciOiI3YTI0ZmE4NDhlNzQwYTNhYTNlMGMwNWZmYWZkNjkyZWMxOWFjNGM0YjUzZTRlNTBhODI1N2U4MzM0YmM5MzcyIiwiaXNzIjoiZmlsZSIsImF1ZCI6InpmcyIsImV4cCI6MTc4MzMzODc3NywiaWF0IjoxNzgzMzM3ODc3fQ.ppc7H28CrRo2o6m_bYt_G14y1I_Yzb8uSH_HjELm-P7xmE85A-0HIMnfPCA7eEIkDlvsG2GaRikTd3rjx7Bpmg&response-cache-control=public%2C%20max-age%3D7776000%2C%20immutable&response-no-vary-search=key-order%2C%20params%3D%28%22jwt%22%20%22Policy%22%20%22Signature%22%20%22Key-Pair-Id%22%20%22verify%22%29&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly91czA0ZmlsZS1wYWEuem9vbS51cy9maWxlL056c05YUE5BU19tUGpEZWJPcGZ1Smc~ZmlsZW5hbWU9JUU2JTg4JUFBJUU1JUIxJThGMjAyNi0wNy0wNiUyMDE5LjE4LjAwLnBuZyZqd3Q9ZXlKaGJHY2lPaUpGVXpJMU5pSXNJbXNpT2lKMmRDOHJjRlZKS3lKOS5leUpwYVdNaU9pSjFjekEwSWl3aWIzSnBJam9pYkhsdWVDMXBiblJsY21GamRHbHZiaUlzSW1oa2FXY2lPbVpoYkhObExDSmthV2NpT2lJM1lUSTBabUU0TkRobE56UXdZVE5oWVRObE1HTXdOV1ptWVdaa05qa3laV014T1dGak5HTTBZalV6WlRSbE5UQmhPREkxTjJVNE16TTBZbU01TXpjeUlpd2lhWE56SWpvaVptbHNaU0lzSW1GMVpDSTZJbnBtY3lJc0ltVjRjQ0k2TVRjNE16TXpPRGMzTnl3aWFXRjBJam94Tnpnek16TTNPRGMzZlEucHBjN0gyOENyUm8ybzZtX2JZdF9HMTR5MUlfWXpiOHVTSF9IakVMbS1QN3htRTg1QS0wSElNbmZQQ0E3ZUVJa0RsdnNHMkdhUmlrVGQzcmp4N0JwbWcmcmVzcG9uc2UtY2FjaGUtY29udHJvbD1wdWJsaWMlMkMlMjBtYXgtYWdlJTNENzc3NjAwMCUyQyUyMGltbXV0YWJsZSZyZXNwb25zZS1uby12YXJ5LXNlYXJjaD1rZXktb3JkZXIlMkMlMjBwYXJhbXMlM0QlMjglMjJqd3QlMjIlMjAlMjJQb2xpY3klMjIlMjAlMjJTaWduYXR1cmUlMjIlMjAlMjJLZXktUGFpci1JZCUyMiUyMCUyMnZlcmlmeSUyMiUyOSIsIkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTc4MzMzODc3N319fV19&Signature=GOll07ugzW-anpIOTllbFBybr-zDA9bdfm35UjEzIiyAIgBNZa1mcKjbLsNsHDRzfDorr~dPGHS3XSfjzlGoHP0DT3fHudabNy8fMnwjrrSO8OHGDIEN01G5X628uhcUzEyxOPXhlrbMWJw9iC68YbC6zzSILQQxdgyeofTMtS7-E-ftVdkEaheFBGbvJeHfuSTf2gLrZk2Dji6B76-u1BgUKzrFdumFVEOuZ1rc2uiojZWhxGTUNMFQt7NzOkslf2NdaatMBNZyyoNXclgDnoWlNAUIIrN1DWqU1kwhmjvzP0aRiO6IWrfo0fJ1BI8f38NVqsxTsY3EvDtJvbfrMQ__&Key-Pair-Id=KL18RPQB3R725)
    
4.  关注一下他的x
    
    [截屏2026-07-06 19.20.36.png](https://us04file-paa.zoom.us/file/ITE5aeuLTpiP8G2Joon38w?filename=%E6%88%AA%E5%B1%8F2026-07-06%2019.20.36.png&jwt=eyJrIjoidnQvK3BVSSsiLCJhbGciOiJFUzI1NiJ9.eyJpYXQiOjE3ODMzMzc4NzcsImhkaWciOmZhbHNlLCJpaWMiOiJ1czA0IiwiZXhwIjoxNzgzMzM4Nzc3LCJhdWQiOiJ6ZnMiLCJpc3MiOiJmaWxlIiwiZGlnIjoiMWU4Yjk2MmQ3YWVlMzY1MTJiZmNlMGE5YmI0ZGY4YWM2MjBjYjdhM2NhNjk5ZjA4NjMwOWEzNGJhNTgxYmU0NSIsIm9yaSI6Imx5bngtaW50ZXJhY3Rpb24ifQ.HBY1WnKyT8LlUOVDgKvDZ5nD1X9iGJX98FJWFCKDXZ8LrPmT-thrLl7T9cT8bOmqMSHDbTlM48q7pE6lxl5XjA&response-cache-control=public%2C%20max-age%3D7776000%2C%20immutable&response-no-vary-search=key-order%2C%20params%3D%28%22jwt%22%20%22Policy%22%20%22Signature%22%20%22Key-Pair-Id%22%20%22verify%22%29&Policy=eyJTdGF0ZW1lbnQiOlt7IkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTc4MzMzODc3N319LCJSZXNvdXJjZSI6Imh0dHBzOi8vdXMwNGZpbGUtcGFhLnpvb20udXMvZmlsZS9JVEU1YWV1TFRwaVA4RzJKb29uMzh3P2ZpbGVuYW1lPSVFNiU4OCVBQSVFNSVCMSU4RjIwMjYtMDctMDYlMjAxOS4yMC4zNi5wbmcmand0PWV5SnJJam9pZG5RdkszQlZTU3NpTENKaGJHY2lPaUpGVXpJMU5pSjkuZXlKcFlYUWlPakUzT0RNek16YzROemNzSW1oa2FXY2lPbVpoYkhObExDSnBhV01pT2lKMWN6QTBJaXdpWlhod0lqb3hOemd6TXpNNE56YzNMQ0poZFdRaU9pSjZabk1pTENKcGMzTWlPaUptYVd4bElpd2laR2xuSWpvaU1XVTRZamsyTW1RM1lXVmxNelkxTVRKaVptTmxNR0U1WW1JMFpHWTRZV00yTWpCallqZGhNMk5oTmprNVpqQTROak13T1dFek5HSmhOVGd4WW1VME5TSXNJbTl5YVNJNklteDVibmd0YVc1MFpYSmhZM1JwYjI0aWZRLkhCWTFXbkt5VDhMbFVPVkRnS3ZEWjVuRDFYOWlHSlg5OEZKV0ZDS0RYWjhMclBtVC10aHJMbDdUOWNUOGJPbXFNU0hEYlRsTTQ4cTdwRTZseGw1WGpBJnJlc3BvbnNlLWNhY2hlLWNvbnRyb2w9cHVibGljJTJDJTIwbWF4LWFnZSUzRDc3NzYwMDAlMkMlMjBpbW11dGFibGUmcmVzcG9uc2Utbm8tdmFyeS1zZWFyY2g9a2V5LW9yZGVyJTJDJTIwcGFyYW1zJTNEJTI4JTIyand0JTIyJTIwJTIyUG9saWN5JTIyJTIwJTIyU2lnbmF0dXJlJTIyJTIwJTIyS2V5LVBhaXItSWQlMjIlMjAlMjJ2ZXJpZnklMjIlMjkifV19&Signature=SdYnb6w3IPaxgTbfdTQEH2YYPiy2ugfTxUwmUfnxLP~jF4LYqaBVLJSPpz1jfOnRBm6zwTMiZreKp-DBtMXAMg6w-DzYlra2ehHKtJNFdYBpaQB7jF1INs-Mko08kSpCxMCGpCO0W0lCM9qsj3gRDNTz1RQ78WI~sjBGhp6PVlPTjLg5TMJDawCsa1naWyguHNeN8oPtJbx~ckIcdLnxNQmv3FYjxYSHSpICpmF1Nq644U82jeS~XRSS0p0tFN35u2ahKGigBbu~gMTYeS6jhsg~-paOuJl~7wId3uoBWGLCuVTeN~24sF5IMGSAu1sOWre24R7sJB7Hiy3dBsYvBg__&Key-Pair-Id=KL18RPQB3R725)
    
5.  SVP Chain- AI链
    
    [截屏2026-07-06 19.21.54.png](https://us04file-paa.zoom.us/file/huDtt0rhQSKhXTZ_Wg6lyg?filename=%E6%88%AA%E5%B1%8F2026-07-06%2019.21.54.png&jwt=eyJhbGciOiJFUzI1NiIsImsiOiJ2dC8rcFVJKyJ9.eyJpc3MiOiJmaWxlIiwiYXVkIjoiemZzIiwiZGlnIjoiZjUzYWMxZThkZGJhNDczNmU5MDg0MjJkNmExNGVhODIwMDQzYThhNjNkZGI5NTE0YWZkNmIyMzcwZjA3NjQ3YyIsImlpYyI6InVzMDQiLCJoZGlnIjpmYWxzZSwiZXhwIjoxNzgzMzM4Nzc3LCJvcmkiOiJseW54LWludGVyYWN0aW9uIiwiaWF0IjoxNzgzMzM3ODc3fQ.oMzi0cMCwiuzwVP_ClhtFqasnAValnBGlV_qaQ-QRdOCETt0h5DyuZWK3F8Ho976kv8LWDaJG1Jln-JtF1jigA&response-cache-control=public%2C%20max-age%3D7776000%2C%20immutable&response-no-vary-search=key-order%2C%20params%3D%28%22jwt%22%20%22Policy%22%20%22Signature%22%20%22Key-Pair-Id%22%20%22verify%22%29&Policy=eyJTdGF0ZW1lbnQiOlt7IkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTc4MzMzODc3N319LCJSZXNvdXJjZSI6Imh0dHBzOi8vdXMwNGZpbGUtcGFhLnpvb20udXMvZmlsZS9odUR0dDByaFFTS2hYVFpfV2c2bHlnP2ZpbGVuYW1lPSVFNiU4OCVBQSVFNSVCMSU4RjIwMjYtMDctMDYlMjAxOS4yMS41NC5wbmcmand0PWV5SmhiR2NpT2lKRlV6STFOaUlzSW1zaU9pSjJkQzhyY0ZWSkt5SjkuZXlKcGMzTWlPaUptYVd4bElpd2lZWFZrSWpvaWVtWnpJaXdpWkdsbklqb2laalV6WVdNeFpUaGtaR0poTkRjek5tVTVNRGcwTWpKa05tRXhOR1ZoT0RJd01EUXpZVGhoTmpOa1pHSTVOVEUwWVdaa05tSXlNemN3WmpBM05qUTNZeUlzSW1scFl5STZJblZ6TURRaUxDSm9aR2xuSWpwbVlXeHpaU3dpWlhod0lqb3hOemd6TXpNNE56YzNMQ0p2Y21raU9pSnNlVzU0TFdsdWRHVnlZV04wYVc5dUlpd2lhV0YwSWpveE56Z3pNek0zT0RjM2ZRLm9NemkwY01Dd2l1endWUF9DbGh0RnFhc25BVmFsbkJHbFZfcWFRLVFSZE9DRVR0MGg1RHl1WldLM0Y4SG85NzZrdjhMV0RhSkcxSmxuLUp0RjFqaWdBJnJlc3BvbnNlLWNhY2hlLWNvbnRyb2w9cHVibGljJTJDJTIwbWF4LWFnZSUzRDc3NzYwMDAlMkMlMjBpbW11dGFibGUmcmVzcG9uc2Utbm8tdmFyeS1zZWFyY2g9a2V5LW9yZGVyJTJDJTIwcGFyYW1zJTNEJTI4JTIyand0JTIyJTIwJTIyUG9saWN5JTIyJTIwJTIyU2lnbmF0dXJlJTIyJTIwJTIyS2V5LVBhaXItSWQlMjIlMjAlMjJ2ZXJpZnklMjIlMjkifV19&Signature=M41Ds~y5nTA3pFPLNLLRWmYz-VVTRLGc1YmIR3XtY6AQOAdAipepoLlZlrMp7Bs7HZ27lawmryZxDxzJ01zypX0~sB~zdx~~MTbVRCkTll3bhIPgSVaXan62QXaxhQ5LvJy8UE9njhdVlhAWVcyc2Vef7wcDSEifWo9vtQyAWtPERnQUkQOZrpnF8pN8uTNvJOjutOl5ax5NXbahx57aq8wnqgUP32-ebbXJsQTYX0zsqKFUx-9XGR8C7z6nhCxiF7Fw95eno9AYLtyCsJSZxEudn145vz2CkoMMp99hFjQtI8wGElpjBIKZCoN3KBQYI-RF8RCzmcijsfnPYyaoIg__&Key-Pair-Id=KL18RPQB3R725)
    

### 新知识点：

以前了解不太具体不太清楚的

-   分布式网络
    
    一个区块链网络中有非常多的节点（矿机）来记账，每个节点都会记录完整的、相同的区块链信息！
    
    ### [**有了分布式网络之后，区块链有了新特性**](https://web3intern.xyz/zh/blockchain-basic/#%E6%9C%89%E4%BA%86%E5%88%86%E5%B8%83%E5%BC%8F%E7%BD%91%E7%BB%9C%E4%B9%8B%E5%90%8E-%E5%8C%BA%E5%9D%97%E9%93%BE%E6%9C%89%E4%BA%86%E6%96%B0%E7%89%B9%E6%80%A7)
    
    **去中心化**
    
    区块链网络通常分布在全球，每个节点都将会存储一份相同的区块链数据。没有人能够控制全部的节点，因此这份区块链数据将会一直存在。
    
    **真正的不可篡改**
    
    区块链网络通常分布在全球，一个人控制大部分节点几乎不可能，因此即便有人修改了部分节点的区块链数据，只要被修改记录的节点不超过 51%，这个改动将不会被认可。
    
    ![image.png](attachment:209316a4-f938-4d36-b4aa-f06199977c47:image.png)
-   比特币
    
    -   **节点可以得到奖励**
        
    
    网络节点服务提供商（以下简称为网络服务提供商）可以得到奖励。不同的网络服务提供商可以得到不同的代币奖励，比如：比特币.
    
    -   **比特币具备了货币属性**
        
    
    根据比特币的设计，它仅有有限的供应量，而且可以自由转账。因此具备了货币的特性，成为了加密货币。
    
    -   **比特币缺点**
        
        匿名和自由有利也有弊。弊端在于难以追踪和限制，所以经常被黑产利用，进行洗钱等违法犯罪活动。由于每打包一个区块需要约 10 分钟，因此也会影响交易的实时性。每个区块的存储数据也是有限的。不过，越来越多的新区块链技术正在优化和解决这些问题。
        
-   区块链怎么运营起来
    
    ### [**一条区块链如何运行起来呢？**](https://web3intern.xyz/zh/blockchain-basic/#%E4%B8%80%E6%9D%A1%E5%8C%BA%E5%9D%97%E9%93%BE%E5%A6%82%E4%BD%95%E8%BF%90%E8%A1%8C%E8%B5%B7%E6%9D%A5%E5%91%A2)
    
    区块链生态系统的运行包含以下几个关键步骤：
    
    1.  **用户发起交易**：用户通过钱包应用发起转账、智能合约调用等操作
        
    2.  **交易广播**：交易信息被广播到整个网络中的各个节点
        
    3.  **节点验证**：网络中的矿工节点验证交易的合法性（余额是否足够、签名是否正确等）
        
    4.  **打包成块**：通过共识机制（如工作量证明），矿工将验证过的交易打包成新的区块
        
    5.  **链接上链**：新区块被添加到区块链上，更新全网的账本状态
        
    6.  **奖励发放**：成功出块的节点可获得协议奖励（如区块奖励/质押奖励）和交易手续费（或其中一部分）
        
    
    区块链生态系统运行流程
    
    ![image.png](attachment:ac42806b-93ed-46a0-8c8b-afd04e8c00cd:image.png)
-   **公链、私链、联盟链**
    
    # [**四、公链 vs 私链 vs 联盟链**](https://web3intern.xyz/zh/blockchain-basic/#%E5%9B%9B%E3%80%81%E5%85%AC%E9%93%BE-vs-%E7%A7%81%E9%93%BE-vs-%E8%81%94%E7%9B%9F%E9%93%BE)
    
    区块链根据访问权限与治理模式，大致可分为三类。按照去中心化程度从高到低排列。
    
    公链、联盟链、私链对比图
    
    ![公链、联盟链、私链对比图](https://web3intern.xyz/assets/different-chains-BJzFHow9.jpg)
    
    公链、联盟链、私链对比图
    
    ### [**1\. 公链（Public Blockchain） = 公共公园**](https://web3intern.xyz/zh/blockchain-basic/#_1-%E5%85%AC%E9%93%BE-public-blockchain-%E5%85%AC%E5%85%B1%E5%85%AC%E5%9B%AD)
    
    想象一个 **完全开放的公园**，任何人都可以自由进入、散步、拍照、甚至参与公园的维护（比如修剪草坪、清理垃圾）。公园里没有管理员，所有规则由大家共同制定。
    
    -   **成为节点的方法**：
        
        -   **无需申请**：任何人只要带着工具（比如手机、电脑）就能加入公园，成为维护者（节点）。
            
        -   **自由进出**：你可以随时离开或回来，没人会拦你。
            
    -   **共同管理数据的模式**：
        
        -   **所有人可见**：公园里的所有活动（比如谁修剪了草坪、谁清理了垃圾）都会被公开记录在公告栏上，所有人都能看到。
            
        -   **去中心化决策**：如果公园需要修路，大家会投票决定（共识机制），不需要某个领导拍板。
            
        -   **缺点**：因为人太多，决策效率低（交易确认慢），维护成本高（比如电费、人力）。
            
    
    ### [**2\. 联盟链（Consortium Blockchain） = 多公司联合的董事会**](https://web3intern.xyz/zh/blockchain-basic/#_2-%E8%81%94%E7%9B%9F%E9%93%BE-consortium-blockchain-%E5%A4%9A%E5%85%AC%E5%8F%B8%E8%81%94%E5%90%88%E7%9A%84%E8%91%A3%E4%BA%8B%E4%BC%9A)
    
    想象一个由 **多家公司**（比如银行、物流公司）组成的 **董事会**，他们共同管理一个共享数据库（比如客户信用信息）。只有这些公司才能参与决策，外人不能随便加入。
    
    -   **成为节点的方法**：
        
        -   **需要邀请或申请**：如果你想加入董事会，必须得到其中一家公司的认可（比如你是某家银行的合作伙伴）。
            
        -   **权限分级**：董事会成员可能分为两类：
            
            -   **决策者**（联盟核心成员）：比如银行 A、银行 B，可以修改数据库规则。
                
            -   **观察者**（联盟普通成员）：比如物流公司，只能查看数据但不能修改。
                
    -   **共同管理数据的模式**：
        
        -   **半公开数据**：数据库里的信息（比如客户信用评分）只有董事会成员能看到，外人无法访问。
            
        -   **联合决策**：如果要修改数据库规则（比如增加新字段），需要董事会成员投票通过。
            
        -   **优点**：效率比公链高（因为成员少），隐私比公链好（数据不对外公开），但不如私链灵活（需要多方协调）。
            
    
    ### [**3\. 私链（Private Blockchain） = 私人俱乐部**](https://web3intern.xyz/zh/blockchain-basic/#_3-%E7%A7%81%E9%93%BE-private-blockchain-%E7%A7%81%E4%BA%BA%E4%BF%B1%E4%B9%90%E9%83%A8)
    
    想象一个 **私人俱乐部**，只有会员才能进入。俱乐部的老板（比如 CEO）完全控制规则，比如谁可以加入、谁能查看账本（会员消费记录）。
    
    -   **成为节点的方法**：
        
        -   **严格审批**：想加入俱乐部？必须经过老板批准（比如交会员费、填写申请表）。
            
        -   **固定成员**：一旦成为会员，你的权限由老板决定（比如能否查看账本、能否修改规则）。
            
    -   **共同管理数据的模式**：
        
        -   **数据完全私有**：账本只对会员开放，外人无法查看（比如你的消费记录只有你和老板知道）。
            
        -   **老板说了算**：如果俱乐部要改规则（比如涨价），老板可以直接决定，不需要投票。
            
        -   **优点**：效率极高（因为只有少数人参与），隐私极强（数据不对外公开），但缺乏公链的透明性。
            
    
    ### [**4. 总结对比**](https://web3intern.xyz/zh/blockchain-basic/#_4-%E6%80%BB%E7%BB%93%E5%AF%B9%E6%AF%94)
    
    | 区块链类型 | 节点加入方式 | 数据可见性 | 管理模式 | 适合场景 |
    | --- | --- | --- | --- | --- |
    | 公链 | 任何人自由加入 | 所有人可见 | 去中心化（大家投票） | 加密货币、公共存证 |
    | 联盟链 | 需联盟成员邀请/审批 | 仅联盟成员可见 | 多中心化（董事会决策） | 供应链、金融协作 |
    | 私链 | 由老板严格审批 | 仅内部成员可见 | 中心化（老板说了算） | 企业内部管理、审计 |
    
-   Web3 vs **Web3.0** vs Web2
    
    # [**四、Web3 vs Web 3.0 vs Web2 的范式革命**](https://web3intern.xyz/zh/blockchain-basic/#%E5%9B%9B%E3%80%81web3-vs-web-3-0-vs-web2-%E7%9A%84%E8%8C%83%E5%BC%8F%E9%9D%A9%E5%91%BD)
    
    ### [**1\. Web2（当前互联网）**](https://web3intern.xyz/zh/blockchain-basic/#_1-web2-%E5%BD%93%E5%89%8D%E4%BA%92%E8%81%94%E7%BD%91)
    
    **核心特征：**
    
    -   **中心化控制**：数据存储在科技巨头的服务器（如 Google、Facebook）
        
    -   **用户角色**：内容生产者，但不拥有数据
        
    -   **商业模式**：广告驱动，平台抽取佣金
        
    -   **典型应用**：微信、抖音、亚马逊
        
    
    **比喻**：
    
    就像租房子，你可以装饰（发内容），但房东（平台）随时能收回钥匙（封号）。
    
    ### [**2\. Web 3.0（语义网）**](https://web3intern.xyz/zh/blockchain-basic/#_2-web-3-0-%E8%AF%AD%E4%B9%89%E7%BD%91)
    
    **核心特征：**
    
    -   **语义标记**：使用 RDF、OWL 等标准描述数据关系
        
    -   **结构化数据**：信息按照标准格式组织，便于机器理解
        
    -   **知识图谱**：构建实体间的语义关系网络
        
    -   **典型技术**：本体工程、语义查询语言（SPARQL）、链接数据
        
    
    **关键区别**：
    
    -   ❌ **不是区块链技术**，而是传统互联网的数据组织升级
        
    -   ❌ **主要不依赖 AI**，而是通过标准化数据格式实现
        
    -   ✅ 与 Web3 可结合（语义标记 + 区块链存储）
        
    
    **比喻**：
    
    像把图书馆的每本书都贴上详细标签（作者、主题、关联书籍），让图书管理员能快速找到相关资料。
    
    ### [**3\. Web3（去中心化互联网）**](https://web3intern.xyz/zh/blockchain-basic/#_3-web3-%E5%8E%BB%E4%B8%AD%E5%BF%83%E5%8C%96%E4%BA%92%E8%81%94%E7%BD%91)
    
    **核心特征：**
    
    -   **数据主权归用户**：用区块链存储身份和资产
        
    -   **无需信任中介**：智能合约自动执行规则
        
    -   **核心组件**：
        
    -   **典型应用**：MetaMask、Uniswap、ENS
        
    
    **核心创新**：
    
    -   **真正拥有数字资产**：你的 NFT 头像、游戏道具真正属于你，平台无法删除或收回
        
    -   **金融服务无门槛**：无需银行卡，用手机钱包就能借贷、理财、交易
        
    -   **应用可自由组合**：一个 DeFi 协议的流动性可以被其他应用直接调用，就像搭积木
        
    -   **内容永不消失**：文章、图片存储在分布式网络，不会因为平台关闭而丢失
        
    
    **比喻**：
    
    像自己买地盖房（数据自托管），用智能合约管理水电费（自动结算）。
    
    ### [**4. 对比矩阵**](https://web3intern.xyz/zh/blockchain-basic/#_4-%E5%AF%B9%E6%AF%94%E7%9F%A9%E9%98%B5)
    
    | 维度 | Web2 | Web 3.0 | Web3 |
    | --- | --- | --- | --- |
    | 控制权 | 平台垄断 | 部分开放 | 用户自治 |
    | 数据存储 | 中心服务器 | 混合存储 | 区块链 / IPFS |
    | 支付系统 | 信用卡 / 支付宝 | 集成支付 | 加密货币 |
    | 典型技术 | JavaScript | RDF / OWL | 智能合约 |
    | 代表企业 | 腾讯 / 阿里 | W3C / DBpedia | Uniswap / ConsenSys |
    
    ### [**5. 常见误解澄清**](https://web3intern.xyz/zh/blockchain-basic/#_5-%E5%B8%B8%E8%A7%81%E8%AF%AF%E8%A7%A3%E6%BE%84%E6%B8%85)
    
    1.  **Web3 ≠ Web 3.0**
        
        -   Web3 是**区块链驱动**的革命
            
        -   Web 3.0 是**语义网技术驱动**的数据组织升级
            
    2.  **Web3 不是万能的**
        
        -   优势：金融、产权、隐私场景
            
        -   劣势：不适合高频社交（如微博）
            
    3.  **渐进式过渡**
        
        -   **Web2.5 案例**：Reddit 社区积分（链上积分+传统界面）
            
    
    ### [**6. 技术栈对比**](https://web3intern.xyz/zh/blockchain-basic/#_6-%E6%8A%80%E6%9C%AF%E6%A0%88%E5%AF%B9%E6%AF%94)
    
    **Web2 开发**：
    
    ```bash
    React + Node.js + MySQL
    ```
    
    **Web3 开发**：
    
    ```bash
    React + Ethers.js + Solidity + IPFS
    ```
    
    **Web 3.0 开发**：
    
    ```bash
    Python + RDFLib + SPARQL
    ```
    
    ### [**7. 该关注哪个？**](https://web3intern.xyz/zh/blockchain-basic/#_7-%E8%AF%A5%E5%85%B3%E6%B3%A8%E5%93%AA%E4%B8%AA)
    
    -   想参与去中心化金融？→ **学 Web3**（Solidity / Rust）
        
    -   想构建知识图谱和语义搜索？→ **学 Web 3.0**（RDF / OWL）
        
    -   想快速就业？→ **Web2 仍是主流市场**
        

* * *

### 以太坊补充

-   以太坊Ethereum和Bitcoin 区别差异
    
    # [**二、Ethereum 与 Bitcoin 的差异**](https://web3intern.xyz/zh/overview-of-ethereum/#%E4%BA%8C%E3%80%81ethereum-%E4%B8%8E-bitcoin-%E7%9A%84%E5%B7%AE%E5%BC%82)
    
    尽管以太坊和比特币均基于区块链技术，但两者的设计目标、功能和技术路线存在显著差异：
    
    | 维度 | 比特币（Bitcoin） | 以太坊（Ethereum） |
    | --- | --- | --- |
    | 目标与定位 | 去中心化的数字货币，强调安全、稳定和稀缺性（总量 2100 万枚） | 去中心化平台，支持智能合约和 Dapps，定位为“区块链 2.0” |
    | 编程能力 | 脚本语言有限，仅支持简单的交易验证逻辑 | 图灵完备的编程语言（如 Solidity），可开发复杂智能合约 |
    | 共识机制 | 工作量证明（PoW），矿工通过算力竞争记账权 | 从 PoW 转向权益证明（PoS），通过 The Merge 实现能源效率优化 |
    | 交易速度 | 每 10 分钟生成一个区块，交易确认较慢 | 区块时间约 12 秒，交易确认更快，适合高频应用 |
    | 经济模型 | 总量固定，强调抗通胀属性 | 供应灵活，通过 EIP-1559 等机制可能呈现通缩趋势 |
    
    以太坊的灵活性使其能够支持更多应用场景，例如 DeFi（借贷、交易）、NFT（数字艺术品）、DAO（去中心化自治组织）等，而比特币则更专注于作为“数字黄金”存储价值。
    
-   以太坊发展
    
    ![image.png](attachment:4c08cb37-f6b3-4d5a-b876-d65e5669d5cb:image.png)

[https://web3intern.xyz/zh/overview-of-ethereum/#二、ethereum-与-bitcoin-的差异](https://web3intern.xyz/zh/overview-of-ethereum/#%E4%BA%8C%E3%80%81ethereum-%E4%B8%8E-bitcoin-%E7%9A%84%E5%B7%AE%E5%BC%82)

⬆️ 值得看一看
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

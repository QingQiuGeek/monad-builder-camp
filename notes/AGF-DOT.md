---
timezone: UTC+8
---

# AGF-DOT

**GitHub ID:** AGF-DOT

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-08
<!-- DAILY_CHECKIN_2026-07-08_START -->
**#学习笔记 - 2026年7月8日**

**今日学习目标**

1. 修复钱包连接问题

2. 完成 dApp 前端开发

3. 将 dApp 部署到 Vercel

4. 整理 Mini Demo 0 和 Week 1 Build Log

5. 确认 Week 2 方向

\---

**一、钱包连接问题排查与修复**

**1.1 问题现象**

点击 "Connect MetaMask" 按钮后，页面显示 "Not Connected"，MetaMask 没有弹出授权窗口。

**1.2 问题原因**

使用 wagmi 框架时，状态同步出现问题。虽然 `window.ethereum` 存在且 MetaMask 可以正常工作，但 wagmi 的 `useAccount()` hook 无法正确检测到连接状态。

**1.3 解决方案**

**放弃 wagmi，改用 ethers.js 直接实现钱包连接**

\`\`\`javascript

// 使用 ethers.js 直接连接钱包

const provider = new ethers.BrowserProvider(window.ethereum)

await provider.send('eth\_requestAccounts', \[\])

const signer = await provider.getSigner()

const addr = await signer.getAddress()

\`\`\`

**1.4 关键代码**

**钱包连接组件**: \[WalletConnect.jsx\](file:///d:/Web3暑期实习/solidity-project/my-app/src/components/WalletConnect.jsx)

\`\`\`javascript

useEffect(() => {

  const checkConnection = async () => {

    if (typeof window !== 'undefined' && window.ethereum) {

      try {

        const provider = new ethers.BrowserProvider(window.ethereum)

        const signer = await provider.getSigner()

        const addr = await signer.getAddress()

        setAccount(addr)

      } catch (err) {

        setAccount(null)

      }

    }

  }

  checkConnection()

}, \[\])

\`\`\`

**监听账户变化**:

\`\`\`javascript

const handleAccountsChanged = (accounts) => {

  if (accounts.length > 0) {

    setAccount(accounts\[0\])

  } else {

    setAccount(null)

  }

}

window.ethereum?.on('accountsChanged', handleAccountsChanged)

\`\`\`

**1.5 学习收获**

| 知识点 | 理解 |

| **wagmi vs ethers.js** | wagmi 是封装层，ethers.js 是底层库；当封装层出现问题时，直接使用底层库更可靠 |

| **钱包连接原理** | 通过 `eth_requestAccounts` 请求授权，然后获取 signer 和地址 |

| **事件监听** | 需要监听 `accountsChanged` 事件，处理用户切换账户的情况 |

\---

**二、dApp 前端开发**

**2.1 技术栈**

| 技术 | 版本 | 用途 |

|------|------|------|

| Next.js | 16.2.10 | 前端框架 |

| Tailwind CSS | 4.4.14 | 样式框架 |

| ethers.js | 6.x | 区块链交互 |

**2.2 组件结构**

\`\`\`

src/

├── app/

│   └── page.js          # 主页（客户端组件）

└── components/

    ├── WalletConnect.jsx    # 钱包连接组件

    ├── MessageList.jsx      # 消息列表组件（Read Function）

    └── PostMessage.jsx      # 发布消息组件（Write Function）

\`\`\`

**2.3 合约交互**

**Read Function（读取消息）**

\`\`\`javascript

const provider = new ethers.BrowserProvider(window.ethereum)

const contract = new ethers.Contract(contractAddress, contractAbi, provider)

const messages = await contract.getMessages()

\`\`\`

**特点**: 不消耗 gas，直接从节点读取数据

**Write Function（发布消息）**

\`\`\`javascript

const provider = new ethers.BrowserProvider(window.ethereum)

const signer = await provider.getSigner()

const contract = new ethers.Contract(contractAddress, contractAbi, signer)

const tx = await contract.addMessage(content)

await tx.wait()

\`\`\`

**特点**: 消耗 gas，需要等待交易确认

**2.4 关键代码**

**消息列表组件**: \[MessageList.jsx\](file:///d:/Web3暑期实习/solidity-project/my-app/src/components/MessageList.jsx)

**发布消息组件**: \[PostMessage.jsx\](file:///d:/Web3暑期实习/solidity-project/my-app/src/components/PostMessage.jsx)

\---

**三、部署到 Vercel**

**3.1 部署步骤**

1. **安装 Vercel CLI**:

   \`\`\`bash

   npm install -g vercel

   \`\`\`

2. **登录 Vercel**:

   \`\`\`bash

   vercel login

   \`\`\`

3. **部署项目**:

   \`\`\`bash

   cd my-app

   vercel deploy --prod

   \`\`\`

**3.2 部署结果**

| 链接类型 | URL |

|----------|-----|

| **主链接** | [https://my-gvhshqdyd-zxb1.vercel.app](https://my-gvhshqdyd-zxb1.vercel.app) |

| **备用链接** | [https://my-app-hazel-eight-93.vercel.app](https://my-app-hazel-eight-93.vercel.app) |

**\### 3.3 学习收获**

| 知识点 | 理解 |

|--------|------|

| **Vercel 部署** | Next.js 项目可以轻松部署到 Vercel，提供免费的 HTTPS 访问 |

| **环境要求** | 部署前需要先构建成功`npm run build`） |

| **域名分配** | Vercel 会自动分配一个随机域名 |

\---

**四、Mini Demo 0 整理**

**4.1 Demo 内容**

| 项目 | 详情 |

|------|------|

| **合约地址** | `0x92e00ffd40925aB9364884901290C18Ce2e060B9` |

| **网络** | Monad Testnet |

| **Demo URL** | [https://my-gvhshqdyd-zxb1.vercel.app](https://my-gvhshqdyd-zxb1.vercel.app) |

**4.2 真实链上操作**

\- ✅ 合约部署（已验证）

\- ✅ 3 次消息发布（已验证）

\- ✅ 区块浏览器可查

**4.3 AI 辅助与人工判断**

| 类型 | AI 贡献 | 人工决策 |

|------|----------|----------|

| 代码编写 | 部署脚本、交互脚本、前端组件 | 私钥管理、技术栈选择 |

| 问题排查 | BigInt 类型错误、RPC 连接问题 | RPC 验证、安全配置 |

| 文档编写 | README、Build Log | 功能需求定义 |

\---

**五、Week 1 Build Log**

**5.1 本周核心产出**

1. **智能合约**: MessageBoard.sol

2. **部署脚本**: scripts/deploy.js, scripts/interact.js

3. **dApp 前端**: Next.js + ethers.js

4. **部署结果**: 合约已上线 Monad Testnet，dApp 已部署到 Vercel

**5.2 方向选择：Tech**

**选择理由**:

\- 兴趣驱动：对智能合约开发和 dApp 构建有浓厚兴趣

\- 能力匹配：已有 Java、Vue 开发经验

\- 实践成果：成功完成合约开发、部署和 dApp 构建

\---

**六、遇到的问题与解决方案**

**问题 1: wagmi 钱包连接失败**

| 项目 | 详情 |

|------|------|

| **现象** | 点击连接按钮后，MetaMask 不弹出授权窗口 |

| **原因** | wagmi 的状态同步问题 |

| **解决方案** | 改用 ethers.js 直接实现 |

**问题 2: Hardhat Ignition 需要交互式确认**

| 项目 | 详情 |

|------|------|

| **现象** | `npx hardhat ignition deploy` 需要用户确认 |

| **原因** | Hardhat Ignition 的安全机制 |

| **解决方案** | 使用自定义部署脚本 |

**问题 3: BigInt 类型错误**

| 项目 | 详情 |

|------|------|

| **现象** | `TypeError: Cannot mix BigInt and other types` |

| **原因** | Solidity 的 `uint` 返回 JavaScript 的 `BigInt` |

| **解决方案** | 使用 BigInt 字面量 |

**\### 问题 4: RPC 连接超时**

| 项目 | 详情 |

|------|------|

| **现象** | 使用官方 RPC 连接超时 |

| **原因** | 公共 RPC 节点不稳定 |

| **解决方案** | 切换到 Ankr 的公共 RPC |

\---

**七、今日学习收获**

  **收获 1: ethers.js 直接连接钱包**

**重要性**: ⭐⭐⭐⭐⭐

学会了使用 ethers.js 直接与 MetaMask 交互，理解了钱包连接的底层原理：

1. 通过 `BrowserProvider` 连接到 MetaMask

2. 通过 `eth_requestAccounts` 请求授权

3. 通过 `getSigner()` 获取签名者

4. 通过 `getAddress()` 获取钱包地址

**收获 2: 合约交互的两种方式**

**重要性**: ⭐⭐⭐⭐

理解了区块链上两种操作的区别：

| 操作类型 | 特点 | Gas 消耗 |

|----------|------|----------|

| **Read Function** | 只读，直接从节点获取 | 免费 |

| **Write Function** | 需要签名，写入链上 | 消耗 gas |

**收获 3: dApp 部署流程**

**重要性**: ⭐⭐⭐⭐⭐

学会了将 dApp 部署到 Vercel 的完整流程，理解了：

1. 构建项目`npm run build`）

2. 登录 Vercel 账号

3. 执行部署命令

4. 获取公开访问链接

**收获 4: 问题排查能力**

**重要性**: ⭐⭐⭐⭐

学会了通过调试信息和日志来定位问题：

1. 添加调试面板查看关键信息

2. 使用测试按钮验证底层功能

3. 通过浏览器控制台查看错误日志

4. 根据错误信息调整技术方案

\---

**八、Week 2 学习计划**

**8.1 技术学习目标**

| 目标 | 优先级 | 说明 |

|------|--------|------|

| Solidity 高级特性 | 高 | 继承、接口、修饰器、库 |

| 前端与智能合约交互 | 高 | Wagmi/Viem 框架深入学习 |

| ERC 标准合约 | 中 | ERC20、ERC721 |

| 智能合约测试 | 中 | Hardhat 测试框架 |

**8.2 实践计划**

1. **完善 dApp**: 添加更多功能（用户消息过滤、消息点赞等）

2. **学习 Wagmi**: 解决之前的状态同步问题，掌握 Wagmi 的正确用法

3. **学习 ERC20**: 编写一个代币合约并部署

4. **编写测试**: 使用 Hardhat 编写合约测试用例

\---

**九、需要帮助的问题**

1. **智能合约安全审计**: 常见漏洞和安全编码最佳实践

2. **Wagmi 状态同步**: 如何正确配置和使用 Wagmi

3. **Gas 优化**: 如何降低合约的 gas 消耗

4. **前端性能**: dApp 的性能优化技巧

\---

 **总结**

今天的学习非常充实！主要完成了：

1. ✅ 修复了钱包连接问题（从 wagmi 切换到 ethers.js）

2. ✅ 完成了 dApp 前端开发（消息列表、发布消息）

3. ✅ 将 dApp 部署到 Vercel，获得了公开访问链接

4. ✅ 整理了 Mini Demo 0 和 Week 1 Build Log

5. ✅ 确认了 Week 2 的 Tech 方向

通过今天的实践，我对 Web3 开发有了更深入的理解，特别是钱包连接和合约交互的底层原理。在遇到问题时，学会了通过调试和测试来定位问题，并选择合适的技术方案。期待 Week 2 的深入学习！
<!-- DAILY_CHECKIN_2026-07-08_END -->

# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->

````markdown
学习笔记 - 2026年7月7日



 一、今日学习目标

1.  配置 Hardhat 连接 Monad Testnet
2.  编译 Solidity 智能合约
3.  将合约部署到 Monad Testnet
4.  调用合约的 Read Function
5.  调用合约的 Write Function
6.  学习智能合约安全最佳实践

---

 二、项目概述

### 项目名称
MessageBoard（消息板智能合约）

### 功能描述
一个简单的去中心化消息板应用，允许用户发布和查看消息。

### 技术栈
- **框架**: Hardhat
- **语言**: Solidity ^0.8.28
- **网络**: Monad Testnet (Chain ID: 10143)
- **钱包**: MetaMask
- **交互**: ethers.js

---

## 三、关键知识点

### 3.1 Hardhat 网络配置

在 [hardhat.config.js](file:///d:/Web3暑期实习/solidity-project/hardhat.config.js) 中添加自定义网络：

```javascript
require("@nomicfoundation/hardhat-toolbox");
require("dotenv").config();

module.exports = {
  solidity: "0.8.28",
  networks: {
    monadTestnet: {
      url: process.env.MONAD_TESTNET_RPC_URL,
      accounts: [process.env.WALLET_PRIVATE_KEY],
      chainId: 10143,
    },
  },
};
```

知识点:
- 使用 `dotenv` 加载环境变量，避免硬编码敏感信息
- `accounts` 字段接受私钥数组，第一个私钥作为部署者账户
- `chainId` 用于验证网络身份

### 3.2 环境变量配置

在 `.env` 文件中存储敏感信息：

```env
MONAD_TESTNET_RPC_URL=https://rpc.ankr.com/monad_testnet
WALLET_PRIVATE_KEY=你的钱包私钥
```

**知识点**:
- `.env` 文件必须添加到 `.gitignore` 中
- 使用公共 RPC（如 Ankr）可以快速连接测试网
- 私钥是钱包的核心，泄露会导致资产损失

### 3.3 合约编译

```shell
npx hardhat compile
```

**知识点**:
- 编译产物存放在 `artifacts/` 目录
- Hardhat 会自动检测 Solidity 版本
- 编译错误会在终端显示详细信息

### 3.4 合约部署

创建部署脚本 [scripts/deploy.js](file:///d:/Web3暑期实习/solidity-project/scripts/deploy.js)：

```javascript
const { ethers } = require("hardhat");

async function main() {
  const [deployer] = await ethers.getSigners();
  console.log("Deploying with account:", deployer.address);

  const MessageBoard = await ethers.getContractFactory("MessageBoard");
  const messageBoard = await MessageBoard.deploy();
  await messageBoard.waitForDeployment();

  const contractAddress = await messageBoard.getAddress();
  console.log("Deployed to:", contractAddress);
}

main();
```

执行部署：
```shell
npx hardhat run scripts/deploy.js --network monadTestnet
```

**知识点**:
- `ethers.getSigners()` 获取配置的账户列表
- `ContractFactory.deploy()` 部署合约到链上
- `waitForDeployment()` 等待交易确认
- `getAddress()` 获取部署后的合约地址

### 3.5 部署结果

| 项目 | 值 |
|------|-----|
| 合约地址 | `0x92e00ffd40925aB9364884901290C18Ce2e060B9` |
| 交易 Hash | `0x372d13974a796aa4c37c74b9b35f0c8366c91875972313e867498d84f52b2866` |
| 部署者地址 | `0x000ca106EC26a06c3180a51aC1D56b0b2521bB46` |

### 3.6 合约交互

#### Read Function（只读调用，无需 gas）

```javascript
const count = await contract.getMessageCount();      // 获取消息数量
const messages = await contract.getMessages();       // 获取所有消息
const msg = await contract.getMessageByIndex(0);     // 获取指定索引的消息
```

**知识点**:
- Read Function 不修改链上状态
- 调用 Read Function 不需要支付 gas
- 返回值直接从节点获取

#### Write Function（写操作，需要 gas）

```javascript
const tx = await contract.addMessage("Hello World!");
await tx.wait();
```

**知识点**:
- Write Function 会修改链上状态
- 需要支付 gas 费用
- 返回 Transaction 对象，需等待确认

### 3.7 智能合约安全

#### 敏感信息保护

在 [.gitignore](file:///d:/Web3暑期实习/solidity-project/.gitignore) 中添加：

```
.env                    # 私钥
deployment-info.json    # 部署信息
```

**安全原则**:
1. 永远不要将私钥提交到 Git
2. 使用环境变量管理密钥
3. 定期轮换密钥
4. 使用 Secret Scanning 工具

---

## 四、遇到的问题与解决方案

### 问题 1: RPC 连接超时

**现象**: 使用 `https://testnet-rpc.monad.xyz` 连接超时

**原因**: 部分公共 RPC 可能不稳定或被墙

**解决方案**: 切换到 Ankr 的公共 RPC `https://rpc.ankr.com/monad_testnet`

### 问题 2: Hardhat Ignition 需要交互式确认

**现象**: `npx hardhat ignition deploy` 会询问是否确认部署

**解决方案**: 使用自定义部署脚本 `scripts/deploy.js`，避免交互式确认

### 问题 3: BigInt 类型错误

**现象**: `TypeError: Cannot mix BigInt and other types`

**原因**: Solidity 的 `uint` 类型在 ethers.js 中返回 `BigInt`，不能直接与普通数字运算

**解决方案**: 使用 `BigInt` 字面量（如 `1n`）或转换方法

```javascript
// 错误写法
const lastMsg = await contract.getMessageByIndex(newCount - 1);

// 正确写法
const lastMsg = await contract.getMessageByIndex(newCount - 1n);
```

---

## 五、学习收获

### 技术层面
1. ✅ 掌握了 Hardhat 配置自定义网络的方法
2. ✅ 学会了使用 ethers.js 部署和交互智能合约
3. ✅ 理解了 Read Function 和 Write Function 的区别
4. ✅ 掌握了环境变量和 .gitignore 的安全配置

### 实践层面
1. ✅ 成功将合约部署到真实测试网
2. ✅ 完成了完整的合约交互流程
3. ✅ 学会了排查 RPC 连接问题
4. ✅ 掌握了 BigInt 类型的处理方法

### 安全意识
1. ✅ 理解了私钥保护的重要性
2. ✅ 学会了配置 .gitignore 防止敏感信息泄露
3. ✅ 了解了测试网和主网的区别

---

## 六、下一步学习计划

1. 📚 学习 Solidity 高级特性（继承、接口、库）
2. 📚 学习测试网代币获取方法
3. 📚 学习前端与智能合约交互（Wagmi/Viem）
4. 📚 学习智能合约安全审计基础
5. 📚 尝试部署到其他测试网（Sepolia、Goerli）

````
<!-- DAILY_CHECKIN_2026-07-07_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->


今天已经把安装插件、创建钱包、添加网络、领水、看区块链浏览器这些步骤全部完成了
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

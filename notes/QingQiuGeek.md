---
timezone: UTC+8
---

# QingQiuGeek

**GitHub ID:** QingQiuGeek

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-10
<!-- DAILY_CHECKIN_2026-07-10_START -->
\### 今日学习内容 今天是 Monad Builder Camp 第一周的最后一天，主题聚焦于深入理解 Monad 的核心架构与运行机制。经过前四天对 Web3 基础、钱包操作、测试网交互和 AI+Solidity 的学习，今天终于进入 Monad 的技术内核。 \*\*Monad 的核心定位\*\* Monad 是一条 Layer-1 区块链，其核心愿景是打破"去中心化与高性能不可兼得"的传统认知。与许多通过加重硬件要求来提升性能的链不同，Monad 的性能提升来自纯软件架构创新，同时保持对普通硬件的友好——任何人都可以运行节点。Monad 的代码库完全开源（共识层 \`monad-bft\` 和执行层 \`monad\` 均在 GitHub 上，采用 GPL-3.0 许可证），主要使用 C++ 和 Rust 编写，追求极致性能。 \*\*五大架构创新\*\* Monad 在五个关键领域引入了创新： 1. \*\*MonadBFT\*\*：前沿的 BFT 共识机制，解决了 tail-forking 问题。传统 BFT 共识在面对网络分区时容易产生尾部分叉，MonadBFT 通过新颖的设计解决了这一痛点，同时保持了快速响应和抗分叉特性。 2. \*\*RaptorCast\*\*：高效的区块传播机制。在高吞吐量场景下，如何快速将区块广播到全球节点是一个关键瓶颈。RaptorCast 利用喷泉码（Fountain Code）技术实现高效的数据分发，确保即使部分数据包丢失，接收方也能完整重建区块。 3. \*\*异步执行（Asynchronous Execution）\*\*：这是 Monad 最关键的创新之一。在传统区块链中，共识和执行是串行的——先执行交易，再达成共识。Monad 将共识和执行解耦为流水线（pipeline），共识先完成投票，执行随后异步进行，从而大幅提升了执行的时间预算。 4. \*\*并行执行（Parallel Execution）与 JIT 编译\*\*：Monad 支持交易的并行执行，同时引入即时编译（JIT Compilation / Native Compilation），将 EVM 字节码编译为本地机器码，进一步提升执行效率。 5. \*\*MonadDb\*\*：专为以太坊状态存储优化的数据库。以太坊的状态数据量巨大，传统的 LevelDB/RocksDB 方案存在瓶颈，MonadDb 从底层重新设计了状态存储架构。 \*\*实际性能参数\*\* - 吞吐量：10,000 TPS（每秒交易数） - 出块频率：400ms（以太坊约 12 秒） - 最终确认时间：800ms（以太坊约 12-15 分钟达到合理最终性） - 区块 Gas 上限：200M gas（以太坊约 30M） - 单笔交易 Gas 上限：30M gas（以太坊约 30M） - 最小 base fee：100 MON-gwei ### Monad 深度解析 \*\*Gas 定价机制的关键差异\*\* Monad 的 Gas 机制与以太坊存在几个根本性差异，这是开发者必须深刻理解的： 1. \*\*按 Gas Limit 收费而非 Gas Used\*\*：这是最重要的区别。在以太坊中，用户实际只支付消耗的 gas（\`gas\_used \* price\_per\_gas\`），未使用的 gas 会退还。但在 Monad 中，收费基于 \`gas\_limit\`（\`gas\_limit \* price\_per\_gas\`）。 这个设计决策源于异步执行的需求：由于区块在执行之前就需要达成共识，如果按 gas\_used 收费，恶意用户可以提交一个 gas\_limit 极高但实际消耗极少的交易来占用区块空间而不付费，形成 DoS 攻击向量。因此，开发者必须精确设置 gas limit，避免过度设置导致不必要的费用浪费。 2. \*\*Base Fee 控制器差异\*\*：Monad 采用了一个比以太坊更复杂的 base fee 控制器。该控制器包含趋势（trend）和动量（momentum）两个维度： - 目标区块填充率：80%（160M gas，区块上限为 200M） - 最大步长：1/28 - 平滑系数 β：0.96 - 设计原则：增加更慢，减少更快——避免 base fee 过高导致区块空间浪费 3. \*\*EIP-1559 兼容\*\*：Monad 支持 EIP-1559 类型交易，\`price\_per\_gas = min(base\_price\_per\_gas + priority\_price\_per\_gas, max\_price\_per\_gas)\`，与以太坊的定价公式一致。 4. \*\*无全局 Mempool\*\*：与以太坊的全局交易池不同，Monad 没有全局 mempool，交易仅转发给接下来的几个 leader，这是为了效率优化。 \*\*EVM 兼容性细节\*\* Monad 实现了完整的 EVM 字节码兼容，但在某些参数上有调整： - 合约代码大小上限：128 KB（以太坊为 24 KB） - Init code 大小上限：256 KB（以太坊为 48 KB） - 部分 opcode 和 precompile 的 gas 价格经过重新调整 - 新增 \`secp256r1\`（P256）验证 precompile（地址 \`0x0100\`），支持链上 WebAuthn/Passkey 签名验证 - 不支持 EIP-4844（blob 交易） \*\*Reserve Balance 机制\*\* Monad 引入了储备余额（Reserve Balance）机制，确保所有被共识层包含的交易都能被支付。这意味着： - 由于 EIP-7702 委托的 EOA 余额不能低于 10 MON - 交易可能在链上被包含但最终执行失败（但仍支付 gas），这与以太坊中 reverting 交易的行为一致，但在 Monad 的异步执行模型下更为常见 ### 实操记录 \*\*1. 测试网配置（Monad Testnet）\*\* \`\`\`javascript // MetaMask / WalletConnect 网络配置 const monadTestnet = { chainId: 10143, chainName: "Monad Testnet", currencySymbol: "MON", rpcUrls: \["https://testnet-rpc.monad.xyz"\], // Monad Foundation RPC blockExplorerUrls: \["https://monadvision.com"\] }; // 添加到 MetaMask await window.ethereum.request({ method: 'wallet\_addEthereumChain', params: \[monadTestnet\] }); \`\`\` \*\*2. 使用 viem 连接 Monad Testnet\*\* \`\`\`typescript import { createPublicClient, http, parseEther } from 'viem'; const monadTestnet = { id: 10143, name: 'Monad Testnet', network: 'monad-testnet', nativeCurrency: { name: 'MON', symbol: 'MON', decimals: 18 }, rpcUrls: { default: { http: \['https://testnet-rpc.monad.xyz'\] }, }, blockExplorers: { default: { name: 'MonadVision', url: 'https://monadvision.com' }, }, }; const client = createPublicClient({ chain: monadTestnet, transport: http(), }); // 查询最新区块 const blockNumber = await client.getBlockNumber(); console.log('Latest block:', blockNumber); \`\`\` \*\*3. Gas 估算最佳实践（Monad 特别注意）\*\* \`\`\`typescript // ❌ 不推荐：每次调用 eth\_estimateGas（Monad 上要注意钱包行为） const gasEstimate = await client.estimateGas({...}); // ✅ 推荐：已知固定 gas 操作直接硬编码 const txHash = await walletClient.sendTransaction({ to: recipient, value: parseEther('0.1'), gasLimit: BigInt(21000), // 转账固定 21000 gas // ⚠️ Monad 按 gasLimit 收费，不要设置过高！ }); \`\`\` \*\*4. 批量 RPC 调用优化\*\* \`\`\`typescript // 使用 Multicall3 合约（Monad 主网和测试网均已部署） import { multicall3Abi } from './abis'; const MULTICALL3\_ADDRESS = '0xcA11bde05977b3631167028862bE2a173976CA11'; // 或使用 viem 的内置 multicall import { publicClient } from './client'; const results = await publicClient.multicall({ contracts: \[ { address: tokenA, abi: erc20Abi, functionName: 'balanceOf', args: \[wallet\] }, { address: tokenB, abi: erc20Abi, functionName: 'balanceOf', args: \[wallet\] }, { address: tokenA, abi: erc20Abi, functionName: 'allowance', args: \[wallet, spender\] }, \], }); \`\`\` \*\*5. 并发交易提交\*\* \`\`\`typescript // ✅ Monad 最佳实践：并发提交多笔交易 const BATCH\_SIZE = 5; const nonce = await client.getTransactionCount({ address: account.address }); const txPromises = Array(BATCH\_SIZE).fill(null).map(async (\_, i) => { return await walletClient.sendTransaction({ to: recipient, value: parseEther('0.01'), gasLimit: BigInt(21000), baseFeePerGas: BigInt(100\_000\_000\_000), // 100 gwei (Monad min base fee) nonce: nonce + i, }); }); const hashes = await Promise.all(txPromises); console.log('Transaction hashes:', hashes); \`\`\` ### 关键知识点对比 | 概念 | 以太坊 | Monad | 优势分析 | |------|--------|-------|---------| | 共识机制 | Gasper (Casper FFG + LMD-GHOST) | MonadBFT | 解决 tail-forking，更快响应 | | 出块时间 | ~12 秒 | 400ms | 30 倍提升，用户体验显著改善 | | 最终确认 | ~12-15 分钟 | 800ms | 从分钟级到亚秒级，DeFi 场景更友好 | | 吞吐量 | ~15-30 TPS | 10,000 TPS | 超过 300 倍提升 | | Gas 计费 | 按 gas\_used | 按 gas\_limit | 防 DoS，但需开发者注意精准设置 | | 区块 Gas 上限 | ~30M | 200M | 6.7 倍，支持更多交易打包 | | 最小 Base Fee | 动态（~1 gwei 量级） | 100 MON-gwei | Monad 明确最低值，定价更可预测 | | 状态存储 | LevelDB/RocksDB | MonadDb | 专为高吞吐优化的存储引擎 | | 交易执行 | 串行执行 | 并行执行 + JIT 编译 | 充分利用多核 CPU，大幅加速 | | Mempool | 全局 mempool | 本地 mempool（仅转发给后续 leader） | 减少网络开销，提升效率 | | 合约大小上限 | 24 KB | 128 KB | 5 倍，允许部署更复杂的合约 | | Blob 交易 (EIP-4844) | 支持 | 不支持 | Monad 用原生扩容替代 L2 blob 路径 | | 历史状态访问 | 全节点支持任意历史状态 | 不支持任意历史状态 | 需使用 indexer 查询历史数据 | | WebAuthn 支持 | EIP-7951 提案中 | 原生支持 P256 precompile | 更好的账户抽象和安全签名 | ### 代码片段 \*\*Reserve Balance 检查（Monad 特有逻辑）\*\* \`\`\`solidity // SPDX-License-Identifier: MIT pragma solidity ^0.8.20; /// @title MonadReserveChecker /// @notice 在 Monad 上部署合约前检查余额是否满足 Reserve Balance 要求 contract MonadReserveChecker { // Monad 要求 EOA 账户在 EIP-7702 委托后保持至少 10 MON uint256 constant MIN\_RESERVE\_BALANCE = 10 ether; // 10 MON function checkReserve(address account) external view returns (bool sufficient) { uint256 balance = account.balance; return balance >= MIN\_RESERVE\_BALANCE; } // 在 Monad 上，gasLimit 就是实际收费量，不要盲目设置高值 function estimateActualCost( uint256 gasLimit, uint256 baseFeePerGas, uint256 priorityFeePerGas ) external pure returns (uint256 cost) { uint256 pricePerGas = baseFeePerGas + priorityFeePerGas; // ⚠️ Monad: cost = gasLimit \* pricePerGas（不是 gasUsed） return gasLimit \* pricePerGas; } } \`\`\` \*\*Hardhat 配置（Monad Testnet）\*\* \`\`\`javascript // hardhat.config.js require("@nomicfoundation/hardhat-toolbox"); module.exports = { solidity: "0.8.20", networks: { monadTestnet: { url: "https://testnet-rpc.monad.xyz", chainId: 10143, accounts: \[process.env.PRIVATE\_KEY\], gasPrice: 100000000000, // 100 gwei (Monad minimum) }, }, }; \`\`\` ### 今日思考 \*\*1. 异步执行的深远影响\*\* Monad 的异步执行模型是其最核心的创新，但也带来了开发范式的根本变化。按 gas\_limit 收费意味着开发者必须像管理资金一样精确管理 gas 设置。在以太坊上，设置过高的 gas limit 只是"锁定"资金，多余的会退还；但在 Monad 上，这直接意味着真金白银的损失。这要求我们在开发 DApp 时建立更严格的 gas 估算流程，甚至需要为每种操作类型建立 gas 基准数据库。 \*\*2. 安全视角的思考\*\* 从 Web3 安全合规的角度来看，Monad 的高性能带来了新的安全考量。10,000 TPS 意味着攻击面也相应扩大——闪电贷攻击可能在 400ms 的出块时间内完成更复杂的操作序列。同时，无全局 mempool 的设计改变了 MEV 的形态，传统以太坊上的 MEV 策略（如三明治攻击）在 Monad 上需要完全重新设计。 从法律合规角度，中国对 Web3 的监管基调为"全面封堵金融属性，有限容忍技术创新"。在 Monad 上进行开发时，技术研究和学习是被允许的，但需要注意：不要参与代币发行融资，不要设计带有赌博、传销特征的机制，出金操作务必通过合规渠道。Web3 开发者应该像任何其他软件开发者一样，关注代码质量、安全审计和用户保护。 \*\*3. 生态建设的思考\*\* Monad 已于 2025 年 11 月 24 日启动公共主网，测试网也已重置并稳定运行（当前版本 v0.14.5）。生态中已部署了大量标准化合约（Multicall3、Permit2、Safe v1.4.1 等），这意味着开发者可以直接复用以太坊生态的成熟工具和库，真正实现"无缝迁移"。对于 Builder Camp 的参与者来说，这是一个巨大的优势——我们可以专注于创新应用，而非基础设施适配。 \*\*4. 数据索引的重要性\*\* 由于 Monad 的高吞吐量，全节点不提供任意历史状态访问，这与以太坊有本质区别。这意味着在构建 DApp 时，必须将 indexer（如 Allium、Envio HyperIndex、The Graph、thirdweb Insight）作为基础设施的一部分，而非可选组件。这是一个需要在项目架构设计初期就考虑的问题。 ### 明日计划 明天进入 Day 6（Week 1 复盘），计划： 1. 整理本周五天的学习笔记，建立知识图谱 2. 复习 Wallet 创建、测试网交互的完整流程 3. 总结 Monad 与以太坊的核心差异要点清单 4. 尝试在 Monad Testnet 上部署一个简单的 ERC-20 合约 5. 梳理 Monad 的 gas 机制要点，编写一份开发注意事项 Checklist
<!-- DAILY_CHECKIN_2026-07-10_END -->

# 2026-07-09
<!-- DAILY_CHECKIN_2026-07-09_START -->

````
## Day 4 | Week 1 | AI + Solidity + 合约部署：在 Monad 上部署第一个智能合约

### 今日学习内容

今天的核心任务是用 AI 辅助编写 Solidity 智能合约，并在 Monad Testnet 上完成部署。这是从"理解区块链"到"动手构建"的关键一步。

**Solidity 基础语法回顾：**

Solidity 是以太坊虚拟机（EVM）兼容链的主力智能合约语言，Monad 完全兼容 EVM，因此 Solidity 合约可以直接部署到 Monad 上。

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.24;

contract Gmonad {
    string public greeting;
    
    constructor(string memory _greeting) {
        greeting = _greeting;
    }
    
    function setGreeting(string calldata _greeting) external {
        greeting = _greeting;
    }
}
```

这个简单的合约展示了 Solidity 的核心概念：
- **状态变量**：`greeting` 是一个 string 类型的公共状态变量，存储在链上
- **构造函数**：`constructor` 在合约部署时执行一次，用于初始化状态
- **外部函数**：`setGreeting` 是一个 external 函数，允许外部调用修改状态
- **public 自动生成 getter**：声明为 `public` 的变量会自动生成一个同名的只读函数

**AI 辅助合约开发实践：**

使用 AI 工具辅助编写了一个更完整的合约，包含事件发射、访问控制和错误处理：

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.24;

contract MonadGreeter {
    string public greeting;
    address public owner;
    uint256 public updateCount;
    
    event GreetingUpdated(address indexed updater, string newGreeting, uint256 timestamp);
    
    error OnlyOwner();
    error EmptyGreeting();
    
    constructor(string memory _greeting) {
        if (bytes(_greeting).length == 0) revert EmptyGreeting();
        greeting = _greeting;
        owner = msg.sender;
        updateCount = 0;
    }
    
    function setGreeting(string calldata _greeting) external {
        if (bytes(_greeting).length == 0) revert EmptyGreeting();
        greeting = _greeting;
        updateCount++;
        emit GreetingUpdated(msg.sender, _greeting, block.timestamp);
    }
    
    function getGreeting() external view returns (string memory) {
        return greeting;
    }
}
```

改进点：
- **事件（Event）**：`GreetingUpdated` 记录每次更新，方便链下索引
- **自定义错误**：`OnlyOwner()` 和 `EmptyGreeting()` 比 require 更省 Gas
- **计数器**：`updateCount` 追踪更新次数
- **view 函数**：`getGreeting()` 不消耗 Gas（只读操作）

### Monad 深度解析：合约部署在 Monad 上的特殊之处

**1. 合约大小限制**

| 参数 | 以太坊 | Monad | 意义 |
|------|--------|-------|------|
| 最大合约代码大小 | 24 KB | **128 KB** | 可部署更复杂的合约 |
| 最大 init code 大小 | 48 KB | **256 KB** | 构造函数可以更复杂 |

Monad 将合约大小限制提升到 128 KB（以太坊的 5 倍），这意味着可以在单个合约中实现更复杂的逻辑，而不需要拆分成多个合约或使用代理模式。

**2. Gas 计费差异**

这是 Monad 与以太坊最重要的区别之一：

| 维度 | 以太坊 | Monad |
|------|--------|-------|
| 收费基准 | gas_used（实际消耗） | **gas_limit（设置的上限）** |
| 退款机制 | 未消耗的 Gas 退还 | **不退还** |
| 建议 | 可以设置较高 gas_limit | **必须精确设置** |

在 Monad 上，如果设置 gas_limit = 100,000 但实际只用了 50,000，仍然会收取 100,000 的费用。因此：
- 对于固定操作（如转账），直接硬编码 gas_limit = 21,000
- 对于合约调用，使用 `eth_estimateGas` 获取精确值
- MetaMask 在合约调用 revert 时会设置极高的 gas_limit，在 Monad 上这会导致高额费用

**3. Monad Testnet 网络配置**

| 参数 | 值 |
|------|-----|
| 网络名称 | Monad Testnet |
| Chain ID | 10143 |
| 货币符号 | MON |
| RPC URL | https://testnet-rpc.monad.xyz |
| 区块浏览器 | https://testnet.monadvision.com |
| 水龙头 | https://faucet.monad.xyz |
| 当前版本 | v0.14.5 / MONAD_NINE |

**4. Monad 已部署的 canonical 合约**

Monad Testnet 上已经部署了一些标准合约：

| 合约 | 用途 |
|------|------|
| Wrapped MON | MON 的 ERC-20 包装版本 |
| Multicall3 | 批量调用工具（地址与以太坊相同） |
| EntryPoint v0.6/0.7/0.8 | ERC-4337 账户抽象入口 |
| Permit2 | Uniswap 的通用授权合约 |
| Safe v1.4.1 | 多签钱包合约 |

**5. 公共 RPC 端点对比**

| 提供商 | 速率限制 | Batch 请求 | Archive 支持 |
|--------|----------|-----------|-------------|
| QuickNode | 50 rps | ✅ 100 | ✅ |
| Ankr | 300 reqs/10s | ✅ 100 | ❌ |
| Monad Foundation | 20 rps | ❌ | ✅ |

### 实操记录

**Step 1：获取测试币**

访问 https://faucet.monad.xyz，连接钱包后领取 MON 测试币。每个地址每天可领取一定数量的 MON。

**Step 2：在 Remix 中部署合约**

1. 打开 https://remix.ethereum.org/
2. 创建新文件 `MonadGreeter.sol`
3. 粘贴合约代码
4. 编译器选择 0.8.24
5. 点击 "Compile MonadGreeter.sol"
6. 在 Deploy 面板选择 "Injected Provider"（连接 MetaMask）
7. 确认 MetaMask 连接到 Monad Testnet
8. 输入构造函数参数（如 "gmonad"）
9. 点击 Deploy → MetaMask 确认

**Step 3：与合约交互**

部署成功后，在 "Deployed Contracts" 区域：
- 点击 `greeting` 按钮读取当前值 → 输出 "gmonad"
- 在 `setGreeting` 输入框输入新值 "gmonad molandak"
- 点击 transact → MetaMask 确认
- 再次点击 `greeting` → 输出 "gmonad molandak"

**Step 4：在区块浏览器查看**

在 MonadVision (https://testnet.monadvision.com) 搜索合约地址，可以查看：
- 合约创建交易
- 所有调用记录
- 状态变化

### 关键知识点对比

| 概念 | 以太坊 | Monad | 开发者影响 |
|------|--------|-------|-----------|
| 合约大小限制 | 24 KB | 128 KB | 可以写更复杂的合约 |
| Gas 收费方式 | 按实际消耗 | 按设置上限 | 必须精确设置 gas_limit |
| 出块时间 | 12 秒 | 1 秒 | 交易确认更快 |
| 编译器 | solc | 完全兼容 solc | 无需修改代码 |
| EVM 版本 | 最新 | 完全兼容 | 现有合约可直接部署 |
| 水龙头 | 各网络不同 | faucet.monad.xyz | 统一入口 |

### 今日思考

Solidity 的学习曲线比预期要平缓。核心概念就是状态变量、函数、事件、修饰符这几个。AI 工具在写合约时很有用，能快速生成模板代码，但需要人工审查安全性。

Monad 的合约大小限制放宽到 128 KB 是个大利好。在以太坊上，复杂的 DeFi 合约经常需要拆分成多个合约或使用代理模式来绕过 24 KB 限制。在 Monad 上，可以更自由地组织代码结构。

Gas 按 limit 收费的设计需要特别注意。这意味着在 Monad 上，"宁可少设不要多设"。如果合约调用可能 revert，设置过高的 gas_limit 会直接损失 MON。这对钱包开发和 DApp 前端都是新的挑战。

### 明日计划

1. 学习 Monad 的历史数据访问限制和索引器方案
2. 了解 Multicall3 在 Monad 上的使用
3. 尝试用 Hardhat 本地部署合约到 Monad Testnet
4. 学习 ERC-20 代币合约的基本实现
5. 整理 Week 1 的 Build Log
````
<!-- DAILY_CHECKIN_2026-07-09_END -->

# 2026-07-08
<!-- DAILY_CHECKIN_2026-07-08_START -->


\## Day 3 | Week 1 | 测试网初探 —— 连接 Monad Testnet，部署第一个智能合约 ### 今日学习内容 今天是 Monad Builder Camp 的第三天，主要学习了区块链测试网的概念与实操。测试网（Testnet）是开发者在正式部署到主网之前用来测试智能合约、调试 DApp、模拟交易的沙盒环境。它与主网的运行机制几乎完全一致，但使用的是没有实际价值的测试代币，因此开发者可以自由地进行各种实验而无需承担任何经济风险。 在今天的实操中，我主要完成了以下内容：在 MetaMask 中配置 Monad Testnet、通过水龙头获取测试代币、使用 Remix IDE 部署智能合约，以及通过区块浏览器查看链上数据。整个过程中，我深刻体会到了 Monad 相较于以太坊测试网（如 Sepolia）的显著优势——更快的出块速度、更低的交易延迟，以及更流畅的开发体验。 #### 什么是测试网？ 测试网是区块链网络的"影子版本"，它复制了主网的所有核心机制——包括共识协议、虚拟机执行、Gas 定价模型等——但运行在独立的链上，测试代币没有真实价值。常见的以太坊测试网包括 Sepolia 和 Holesky，而 Monad 则提供了自己的 Testnet 和 Tempnet 两种测试环境： - \*\*Testnet\*\*：主要测试环境，已部署数百个应用，于 2025-12-16 从创世区块重置，当前运行版本 v0.14.5 / MONAD\_NINE 修订版 - \*\*Tempnet\*\*：瞬态网络，会定期重置，用作新功能的沙盒环境，当前运行版本 v0.12.3 测试网的存在对于开发者至关重要。在我的 Web3 安全学习经验中，测试网是验证合约安全性的第一道防线——任何在主网上可能导致资金损失的漏洞，都应该在测试网阶段被发现和修复。 ### Monad 深度解析 #### Monad 核心架构 Monad 并非以太坊的简单分叉，而是一个从零开始用 C++ 和 Rust 构建的高性能 EVM 兼容 Layer 1 区块链。其核心创新体现在三个层面： \*\*1. MonadBFT 共识协议\*\* MonadBFT 是一种抗尾部分叉（tail-fork-resistant）的流水线化 BFT 共识协议，源自 HotStuff 的改进版本。它实现了： - \*\*单轮推测性最终性（Speculative Finality）\*\*：在一个共识轮次内即可获得推测性确认，两个轮次内实现完全最终性 - \*\*线性消息复杂度\*\*：正常运行路径下，消息和认证器复杂度为 O(n)，允许共识验证者集扩展到大量节点 - \*\*乐观响应性\*\*：轮次推进无需等待最坏情况的网络延迟，在常见情况和故障恢复中都是如此 - \*\*领导者故障隔离\*\*：单个故障领导者仅导致一次超时延迟，其他轮次可以尽可能快地推进 MonadBFT 的关键创新在于引入了 No-Endorsement 消息和 No-Endorsement Certificate（NEC）机制，这是一种轻量级的方式让验证者拒绝未充分传播的提案，而无需等待完整的超时。 \*\*2. 异步执行（Asynchronous Execution）\*\* 这是 Monad 最重要的架构创新之一。在以太坊中，执行与共识是交织在一起的（interleaved）——领导者必须先执行区块中的所有交易才能提出提案，验证节点也必须先执行交易才能投票。这意味着以太坊的执行时间预算极其有限：尽管出块时间为 12 秒，但 Gas 上限（3000 万 Gas）对应的执行时间预算仅约 100 毫秒，只占出块时间的 1%！ Monad 将共识与执行解耦，将执行移到共识的热路径之外，放入一个略有延迟的独立泳道。在 Monad 中，节点就交易的官方排序达成共识，而无需执行这些交易。这意味着执行可以获得完整的出块时间预算，大幅提升了执行吞吐量。 关键设计细节：由于执行滞后于共识，Monad 区块提案不包含状态树的 Merkle 根。作为预防措施，提案包含 \`D\` 个区块之前的延迟 Merkle 根（D 当前设为 3），允许节点检测是否发生了状态分歧。 \*\*3. 乐观并行执行（Optimistic Parallel Execution）\*\* Monad 使用乐观并行执行来处理交易。这意味着 Monad 会在早期交易完成之前就开始执行后续交易。如果并行执行的交易之间存在状态冲突（例如两个交易都读写同一个账户余额），Monad 会通过跟踪执行输入并与前序交易的输出进行比较来检测冲突，一旦发现不一致，就使用正确数据重新执行该交易。 虽然 Monad 以并行方式执行交易，但区块结果与以太坊完全一致——都是线性排序的交易集合，最终状态完全确定。这种设计借鉴了数据库领域的乐观并发控制（OCC）和软件事务内存（STM）技术。 \*\*4. MonadDb\*\* Monad 实现了自定义数据库 MonadDb，原生地在 SSD 上存储以太坊 Merkle Patricia Trie，优化了 I/O 性能。配合异步 I/O 技术，Monad 能够在通信进行时保持 CPU 的高效利用。 #### Monad Testnet 关键参数 | 参数 | 值 | |------|------| | Chain ID | 10143 | | 货币符号 | MON | | 出块时间 | ~1 秒 | | 吞吐量 | 10,000+ TPS | | 区块 Gas 上限 | 200M Gas | | 交易 Gas 上限 | 30M Gas | | 最低基础费 | 100 MON-gwei | | 最大合约代码大小 | 128 KB（以太坊为 24 KB） | | 最大初始化代码大小 | 256 KB（以太坊为 48 KB） | ### 实操记录 #### 第一步：MetaMask 配置 Monad Testnet 在 MetaMask 中添加 Monad Testnet，需要配置以下参数： | 配置项 | 值 | |--------|-----| | Network Name | Monad Testnet | | RPC URL | \`https://rpc.testnet.monad.xyz\`（Monad Foundation 官方端点，限速 20 rps） | | Chain ID | 10143 | | Currency Symbol | MON | | Block Explorer URL | \`https://monadscan.com\` 或 \`https://monadvision.com\` | 其他可用的公共 RPC 端点： - \*\*QuickNode\*\*：50 rps，支持批量请求（最多 100），支持 Archive 数据，\`eth\_call\` 和 \`eth\_estimateGas\` 限速 25 rps - \*\*Ankr\*\*：300 reqs/10s、12000 reqs/10min，批量请求最多 100，不支持 Archive 数据，\`debug\_\*\` 方法不可用 #### 第二步：获取测试代币 访问 Monad 官方水龙头：\`https://faucet.monad.xyz\`，连接钱包后即可领取测试用的 MON 代币。此外，Monad 生态还有丰富的测试代币，可在 \`https://github.com/monad-crypto/token-list/blob/main/tokenlist-testnet.json\` 查看完整列表。 #### 第三步：Remix 部署智能合约 通过 Remix IDE 在 Monad Testnet 上部署一个简单的 Greeting 合约： \`\`\`solidity // SPDX-License-Identifier: MIT pragma solidity ^0.8.24; contract Gmonad { string public greeting; constructor(string memory \_greeting) { greeting = \_greeting; } function setGreeting(string calldata \_greeting) external { greeting = \_greeting; } } \`\`\` \*\*部署步骤\*\*： 1. 打开 \`https://remix.ethereum.org/\`，创建新文件 \`Gmonad.sol\` 2. 粘贴上述代码，选择编译器版本 0.8.24 3. 在 "Deploy & run transactions" 标签页中，Environment 选择 "Injected Provider"（连接 MetaMask） 4. 确保 MetaMask 已切换到 Monad Testnet 网络 5. 在构造函数参数中输入初始问候语（如 "gmonad"），点击 Deploy 6. MetaMask 弹出确认窗口，点击确认 7. 部署成功后，可在 "Deployed Contracts" 区域调用 \`greeting()\` 读取和 \`setGreeting()\` 修改 #### 第四步：区块浏览器验证 部署完成后，可在两个区块浏览器上查看交易和合约： - \*\*MonadVision\*\*（由 BlockVision 提供）：\`https://monadvision.com\` - \*\*Monadscan\*\*（由 Etherscan 提供）：\`https://monadscan.com\` Monadscan 提供 Sourcify 和 Etherscan 两种验证器类型，方便开发者验证合约源码。此外还有详细的交易分析工具： - \*\*Tenderly Explorer\*\*：提供调用栈、余额变化、Gas 使用详情 - \*\*Blocksec Phalcon Explorer\*\*：提供调用栈、余额变化、资金流向分析 - \*\*JiffyScan\*\*：EIP-4337 UserOp 浏览器 ### 关键知识点对比 | 概念 | 以太坊（Sepolia） | Monad Testnet | 优势分析 | |------|-------------------|---------------|----------| | 共识机制 | Gasper（Casper FFG + LMD-GHOST） | MonadBFT | MonadBFT 实现单轮推测性最终性，延迟更低 | | 出块时间 | 12 秒 | ~1 秒 | Monad 快 12 倍，用户体验更流畅 | | 吞吐量 | ~15-30 TPS | 10,000+ TPS | Monad 高 300-600 倍，支持大规模应用 | | 执行模型 | 交织执行（共识与执行耦合） | 异步执行（共识与执行解耦） | Monad 执行可使用完整出块时间预算 | | 交易并行 | 串行执行 | 乐观并行执行 | Monad 充分利用多核 CPU | | 最大合约大小 | 24 KB | 128 KB | Monad 支持更复杂的合约逻辑 | | Gas 计费 | 按实际消耗（gas\_used） | 按 Gas 上限（gas\_limit） | Monad 防止异步执行下的 DOS 攻击 | | Mempool | 全局公开 mempool | 本地 mempool（仅转发给后续领导者） | Monad 降低带宽消耗，提升隐私性 | | Blob 交易 | 支持 EIP-4844 | 不支持 | Monad 专注于 L1 性能优化 | | 预编译 | 标准以太坊预编译 | 支持 secp256r1（P256）验证 | Monad 支持 WebAuthn/Passkey 签名验证 | | 客户端语言 | Go/Rust（Geth、Erigon 等） | C++ + Rust（从零构建） | Monad 针对性能深度优化 | | 数据库 | LevelDB/PebbleDB | MonadDb（自定义） | Monad 原生支持 SSD 上的 Merkle Patricia Trie | ### 代码片段 #### 并发交易提交（Monad 最佳实践） Monad 官方推荐的并发交易提交方式，充分利用其高吞吐量优势： \`\`\`typescript import { createWalletClient, http, parseEther } from 'viem'; import { monadTestnet } from 'viem/chains'; const walletClient = createWalletClient({ account: ACCOUNT, chain: monadTestnet, transport: http('https://rpc.testnet.monad.xyz'), }); // ❌ 以太坊式串行提交（低效） for (let i = 0; i < 10; i++) { const txHash = await walletClient.sendTransaction({ to: recipientAddress, value: parseEther('0.1'), gas: BigInt(21000), maxFeePerGas: BigInt(50000000000), nonce: nonce + i, }); } // ✅ Monad 最佳实践：并发提交 const BATCH\_SIZE = 10; const txPromises = Array(BATCH\_SIZE).fill(null).map(async (\_, i) => { return await walletClient.sendTransaction({ to: recipientAddress, value: parseEther('0.1'), gas: BigInt(21000), maxFeePerGas: BigInt(50000000000), nonce: nonce + i, }); }); const hashes = await Promise.all(txPromises); \`\`\` #### Multicall3 批量读取 Multicall3 已部署在 Monad Testnet 地址 \`0xcA11bde05977b3631167028862bE2a173976CA11\`，可将多个 \`eth\_call\` 合并为一次调用： \`\`\`typescript import { createPublicClient, http } from 'viem'; import { monadTestnet } from 'viem/chains'; const publicClient = createPublicClient({ chain: monadTestnet, transport: http('https://rpc.testnet.monad.xyz'), }); // 使用 viem 的内置 multicall 支持 const results = await publicClient.multicall({ contracts: \[ { address: tokenA, abi: erc20Abi, functionName: 'balanceOf', args: \[walletAddress\] }, { address: tokenB, abi: erc20Abi, functionName: 'balanceOf', args: \[walletAddress\] }, { address: tokenA, abi: erc20Abi, functionName: 'allowance', args: \[walletAddress, spender\] }, \], }); // 一次 RPC 调用获取三个数据点，减少延迟 \`\`\` #### Envio HyperIndex 配置示例 Monad 官方推荐使用索引器替代反复调用 \`eth\_getLogs\`，以下是 Envio 的配置： \`\`\`yaml name: monad-token-tracker networks: - id: 10143 # Monad Testnet start\_block: 0 contracts: - name: Gmonad address: - 0xYourContractAddress handler: src/EventHandlers.ts events: - event: GreetingChanged(string oldGreeting, string newGreeting) \`\`\` ### 今日思考 #### 1. 异步执行的安全启示 从 Web3 安全的角度来看，Monad 的异步执行模型带来了新的安全考量。由于 Monad 按 gas\_limit 而非 gas\_used 计费，开发者必须精确设置 Gas 上限。如果使用 MetaMask 等钱包的 \`eth\_estimateGas\` 估算，在合约调用 revert 时，某些钱包会将 Gas 上限设为极高值——这在以太坊上影响不大（因为只收取实际消耗），但在 Monad 上会导致用户被收取大量费用。这是一个典型的"链间行为差异导致安全问题"的案例，提醒我们在开发跨链 DApp 时必须深入了解每条链的特有行为。 #### 2. Reserve Balance 机制与 MEV Monad 的 Reserve Balance 机制确保共识中包含的交易都能被支付。这意味着在 Monad 中可能会看到一些在以太坊上不会出现的"包含但执行失败"的交易——这些交易仍然消耗 Gas 并被视为有效交易。这对 MEV 策略和套利机器人的设计有重要影响：在 Monad 上，即使交易最终 revert，它仍然占据区块空间并支付 Gas 费用。 #### 3. 无全局 Mempool 的影响 Monad 没有全局 mempool，交易仅被转发给后续几个领导者。这一设计降低了带宽消耗并提升了交易隐私性，但对 MEV 搜索者（Searcher）提出了新的挑战——传统的 mempool 监控策略在 Monad 上不再适用。开发者需要采用不同的方式来发现和捕获 MEV 机会。 #### 4. 与已有 Web3 安全知识的关联 在 Web3 安全学习中，我了解到测试网是合约安全审计的第一站。Monad Testnet 的高吞吐量特性意味着可以更高效地进行模糊测试（Fuzzing）和形式化验证——相同时间内可以执行更多交易，更快地发现边界情况下的漏洞。结合 Echidna、Slither、Mythril 等安全工具，Monad 测试网将成为智能合约安全研究的理想平台。 #### 5. 踩坑记录 - 在配置 RPC 时，如果使用了不支持 Archive 数据的端点（如 Ankr），某些历史查询可能会失败 - Remix 部署时需要注意选择正确的编译器版本（0.8.24），否则会出现红色波浪线警告 - 由于 Monad 按 gas\_limit 计费，在测试合约时应避免设置过高的 Gas 上限，以免浪费测试代币 ### 明日计划 1. \*\*学习 Solidity 基础语法\*\*：变量类型、函数修饰符、事件、继承等 2. \*\*在 Monad Testnet 上部署更复杂的合约\*\*：尝试包含状态变量、映射、事件的合约 3. \*\*学习 Foundry 测试框架\*\*：了解 Monad Foundry 的定制版本，掌握本地测试流程 4. \*\*深入研究 Monad 的 Gas 定价机制\*\*：理解 EIP-1559 兼容的 base\_price\_per\_gas 动态控制器 5. \*\*探索 Monad 生态工具\*\*：Allium 数据分析、thirdweb Insight API 等 ### 参考资料 - \[Monad Testnet 网络信息\](https://docs.monad.xyz/developer-essentials/testnets) - \[Monad vs Ethereum 区别\](https://docs.monad.xyz/developer-essentials/differences) - \[Monad 高性能最佳实践\](https://docs.monad.xyz/developer-essentials/best-practices) - \[Monad Gas 定价\](https://docs.monad.xyz/developer-essentials/gas-pricing) - \[MonadBFT 共识协议\](https://docs.monad.xyz/monad-arch/consensus/monad-bft) - \[异步执行详解\](https://docs.monad.xyz/monad-arch/consensus/asynchronous-execution) - \[乐观并行执行\](https://docs.monad.xyz/monad-arch/execution/parallel-execution) - \[Remix 部署指南\](https://docs.monad.xyz/guides/deploy-smart-contract/remix) - \[Web3 实习手册 - 安全与合规\](https://web3intern.xyz/zh/security/) <!-- DAILY\_CHECKIN\_2026-07-08\_END `-`
<!-- DAILY_CHECKIN_2026-07-08_END -->

# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->



| 维度 | EOA（普通钱包） | 智能账户（Smart Account / AA） | 多签账户（Multisig） |
| --- | --- | --- | --- |
| 谁持有控制权 | 单个私钥持有者 | 用户 + 智能合约规则 | 多个签名人共同控制 |
| 谁可以发起交易 | 私钥持有者直接发起 | 用户提交请求，由合约校验执行 | 任意签名人可发起提案 |
| 是否支持多人确认 | ❌ 不支持 | ✅ 可配置 | ✅ 天然支持 |
| 是否支持恢复机制 | ❌ 基本不支持 | ✅ 支持社交恢复、设备恢复 | ⚠️ 取决于签名人是否仍可访问 |
| 是否支持限额/自动化策略 | ❌ 不支持 | ✅ 支持日限额、自动扣费、Gas 代付等 | ⚠️ 可部分实现，但不灵活 |
| 是否支持程序化权限控制 | ❌ 不支持 | ✅ 核心能力 | ⚠️ 仅支持签名阈值类控制 |
| 使用门槛 | 低 | 中 | 中高 |
| 用户体验 | Web3 原生 | 更接近 Web2 | 偏企业/组织化 |
| 典型使用场景 | 普通用户钱包 | 链游、支付、AA 钱包、Web2 onboarding | DAO 国库、项目资金管理、团队钱包 |
| 主要风险点 | 私钥泄露即资产丢失 | 合约漏洞或权限配置错误 | 多签人串通 / 私钥同时丢失 |
| 常见代表 | MetaMask | ERC-4337 | Safe |
<!-- DAILY_CHECKIN_2026-07-07_END -->
<!-- Content_END -->

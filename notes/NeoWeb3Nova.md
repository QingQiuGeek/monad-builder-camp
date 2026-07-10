---
timezone: UTC+8
---

# Neo.Yun

**GitHub ID:** NeoWeb3Nova

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-10
<!-- DAILY_CHECKIN_2026-07-10_START -->
今天是 Web3 Summer Internship Program / Monad Builder Camp 的 Day 5，主题是「AI 工具与 Vibe Coding 入门」。  
  
今日完成：  
1\. 根据 Week 1 Day 5 任务，准备 AI 学习记录提交物 submissions/week-01/[ai-learning.md](http://ai-learning.md)。  
2\. 明确 Vibe Coding 的核心：人用自然语言驱动 AI 写代码，但人必须审查、判断和修正输出。  
3\. 规划今日学习路径：选择一个 AI coding / learning 工具；选一个 Web3 概念让 AI 解释；用 AI 生成 3-5 个 Monad DApp / 合约想法；记录 prompt、输出、人类判断和修正。  
4\. 更新本地项目每日学习日志 daily/[2026-07-10.md](http://2026-07-10.md)。  
  
今日收获：  
\- AI-native Builder 的关键不是会用 AI 写代码，而是能记录「AI 帮了什么、我验证了什么、我做了什么判断」。  
\- 链上学习要留下证据链：钱包地址、交易哈希、网络配置、AI 协作记录都会成为 Proof of Learning / Proof of Work。  
\- 对 AI 输出做修正和说明，才是自己的学习成果。  
  
今日卡点：  
\- 具体 AI 工具和概念尚未选定，需要根据个人环境决定。  
\- 嘉宾分享和 Co-learning 需要登录平台或等待回放。  
  
明日计划：  
\- 完成 AI 概念解释与 DApp 想法列表。  
\- 把 prompt、输出、修正写进 submissions/week-01/[ai-learning.md](http://ai-learning.md)。  
\- 阅读 docs/[monad-technical-notes.md](http://monad-technical-notes.md)，为 Day 6 技术基础做准备。
<!-- DAILY_CHECKIN_2026-07-10_END -->

# 2026-07-09
<!-- DAILY_CHECKIN_2026-07-09_START -->

今天是 Web3 Summer Internship Program / Monad Builder Camp 的 Day 4，主题是“第一笔 Monad Testnet 链上交易准备”。  
  
今日完成：  
1\. 提交并整理了当前 Monad Builder Camp 项目仓库，形成两次本地提交：  
\- e297688 docs: update monad builder camp learning notes  
\- 1de3756 docs: prepare day 4 monad testnet transaction  
2\. 从 Monad 官方文档确认 Testnet 网络参数：  
\- Network Name: Monad Testnet  
\- Chain ID: 10143 / 0x279f  
\- Currency Symbol: MON  
\- RPC URL: [https://testnet-rpc.monad.xyz](https://testnet-rpc.monad.xyz)  
\- Faucet: [https://faucet.monad.xyz](https://faucet.monad.xyz)  
\- Explorer: [https://testnet.monadvision.com](https://testnet.monadvision.com) / [https://testnet.monadscan.com](https://testnet.monadscan.com)  
3\. 用 JSON-RPC 实测 Monad Testnet RPC，确认 eth\_chainId 返回 0x279f，与官方文档一致。  
4\. 更新了网络配置文档：  
\- submissions/week-01/[network-config.md](http://network-config.md)  
5\. 更新了钱包配置实验记录：  
\- experiments/monad-wallet-setup/[README.md](http://README.md)  
6\. 创建了第一笔链上交易记录模板：  
\- submissions/week-01/[first-tx.md](http://first-tx.md)  
  
今日收获：  
链上任务的关键不是“知道参数”，而是形成一条可验证的 Proof of Work 证据链：  
  
官方文档 → RPC 实测 → 钱包配置 → Faucet 领水 → 交易哈希 → Explorer 链接。  
  
Testnet 虽然没有真实资产价值，但流程非常接近真实链上开发：网络配置、RPC、钱包签名、Gas、Explorer 查询，每一步都对应真实产品开发中的基础能力。  
  
今日卡点：  
1\. Web3Career 学习面板需要登录后才能查看每日任务，未登录状态下只能看到项目概览。  
2\. 钱包添加网络、Faucet 领水和交易签名必须由本人完成，AI 不能接触私钥或助记词，也不能代替签名。  
3\. 下一步需要手动完成第一笔 Monad Testnet 转账或 Remix 合约部署，并回填交易哈希。  
  
下一步计划：  
1\. 在钱包中添加 Monad Testnet。  
2\. 从 [https://faucet.monad.xyz](https://faucet.monad.xyz) 领取测试 MON。  
3\. 完成一笔小额测试网转账，或使用 Remix 部署 Gmonad.sol 合约。  
4\. 记录交易哈希、Explorer 链接和截图，补全 submissions/week-01/[first-tx.md](http://first-tx.md)。  
  
一句话总结：  
今天把 Monad Testnet 的网络参数和交易记录模板准备好了，下一步就是用真实钱包签名，把学习记录推进成可验证的链上 Proof of Work。
<!-- DAILY_CHECKIN_2026-07-09_END -->

# 2026-07-08
<!-- DAILY_CHECKIN_2026-07-08_START -->


今日完成：  
1\. 根据 Week 1 Day 3 任务，整理 Monad Testnet 配置清单：RPC URL、Chain ID、Explorer、Faucet。  
2\. 在本地项目建立/更新了网络配置提交物 submissions/week-01/[network-config.md](http://network-config.md) 和实验记录 experiments/monad-wallet-setup/[README.md](http://README.md)。  
3\. 计划在钱包中手动添加 Monad Testnet，并从官方 Faucet 领取测试币。  
4\. 确认安全边界：私钥/助记词由本人离线保管，项目文件中只记录公开地址和网络参数。  
  
今日收获：  
\- Testnet 是主网的平行测试环境，代币无真实价值，但配置流程和主网一致。  
\- 链上交互前必须确认四个基础参数：RPC、Chain ID、Explorer、Faucet。  
\- 网络参数会随时间变化，养成从官方文档验证的习惯，而不是照抄旧教程。  
  
今日卡点：  
\- 钱包添加网络和领水需要本人在浏览器操作，AI 不能代为完成。  
\- 昨天（Day 2）的测试钱包地址尚未回填到项目，今天需要一并补齐。  
  
明日计划：  
\- 完成第一笔 Monad Testnet 链上交易。  
\- 记录交易哈希、Explorer 链接和交互反思。  
\- 为 Week 1 后续任务（AI 工具、Monad 技术基础）做准备。
<!-- DAILY_CHECKIN_2026-07-08_END -->

# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->



周次: Week 1 - 认知奠基期 / 进入 Onchain World  
Day: Day 2  
主题: 钱包与安全  
  
今日完成  
  
1\. 对照 Week 1 Day 2 任务，明确今日主线为「钱包与安全」：安装 MetaMask / 兼容 EVM 钱包、创建专用测试钱包、离线纸笔备份助记词、记录公开地址、写 300 字概念解释。  
2\. 整理 7 月 6 日分享会《DevRel 的成长之路 —— 从 Builder 到生态连接者》，生成结构化笔记 docs/[devrel-growth.md](http://devrel-growth.md) 与完整转录 docs/[devrel-growth-transcript.md](http://devrel-growth-transcript.md)。  
3\. 更新项目 [README.md](http://README.md)，加入 DevRel 分享会资料入口。  
4\. 完成 Monad 理解任务：从 Research / Tech / Ops 三个方向梳理高频交互应用场景，输出 submissions/week-01/[monad-high-frequency-app.md](http://monad-high-frequency-app.md)。  
5\. 明确钱包安全原则：测试钱包与主资产钱包隔离；助记词 / 私钥不发给任何人、不上传云端、不复制给 AI；项目内只记录公开地址。  
  
今日收获  
  
\- 钱包不是「账号密码」模型，私钥控制资产，助记词可恢复私钥，地址只是可公开的链上身份。  
\- Web3 学习要留下证据链：钱包地址、交易哈希、截图、学习笔记、项目文档都是 Proof of Learning / Proof of Work。  
\- DevRel 分享让我意识到，Web3 职业入口不只纯技术岗位，也可以从 Builder 作品、社区贡献、运营、研究、生态连接逐步进入。  
  
今日卡点  
  
\- 钱包创建和助记词备份涉及安全敏感信息，必须本人操作，不能让 AI 接触助记词或私钥。  
\- Track 方向（Tech / Ops / Research）尚未最终确定，计划先完成 Week 1 基础任务，再结合实际产出选择主线。  
  
明日计划  
  
\- 完成并核对 submissions/week-01/[wallet.md](http://wallet.md)。  
\- 配置 Monad Testnet。  
\- 获取 Faucet 测试币。  
\- 保存网络配置、Faucet 链接和截图到 assets/week-01/。
<!-- DAILY_CHECKIN_2026-07-07_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->




今天核心学习了，monad的gas机制：

## Monad 和 Ethereum 最大区别：Gas Limit 是否会真的收费

这是重点。

在 **Ethereum** 上：

```
实际手续费 = Gas Used × 实际 Gas Price
```

假设你设置：

```
Gas Limit = 100,000
Gas Used = 21,000
```

Ethereum 通常只按 `21,000` 收费，没用完的 gas limit 不扣钱。

但在 **Monad** 上，官方文档写的是：

```
实际手续费 = Gas Limit × Gas Price
```

也就是说，在 Monad 上，如果你把 Gas Limit 设置太高，哪怕实际只用了很少，也可能要按你声明的 Gas Limit 付费。Monad 这样设计，是为了配合它的 **异步执行架构**：区块 leader 在执行交易之前就要构建区块、验证者也会先投票；如果允许用户随便报很高 gas limit 但最后只按 gas used 付费，就容易制造 DoS/资源占用问题。

简单说：

```
Ethereum：Gas Limit 更像“保险额度”，没用完会退。
Monad：Gas Limit 更像“资源预订量”，你报多少就按多少算。
```

## 4\. Monad 为什么要这么设计？

因为 Monad 的目标不是简单复制 Ethereum，而是提高并行执行、高吞吐和异步处理能力。

在 Ethereum 里，执行和区块处理更紧密，实际用了多少 gas 比较容易成为收费依据。

Monad 为了提升性能，采用延迟/异步执行思路：交易先被排进区块，执行结果后面再处理。这样如果仍按实际 Gas Used 收费，用户可以故意设置很大的 Gas Limit，占用区块资源，但最后只执行很少逻辑，成本很低。Monad 按 Gas Limit 收费，就是为了让“占用资源”本身有成本。

这也是为什么在 Monad 上写合约、调钱包、估 gas 时，**Gas Limit 不能像 Ethereum 那样随便给很大 buffer**。官方和生态文章都建议使用 `eth_estimateGas` 作为基准，再加一个适度 buffer，不要过度放大。

## 5\. Base Fee 调整机制也不同

Monad 和 Ethereum 都有动态 Base Fee，但参数不完全一样。

Ethereum 的 Base Fee 会根据上一个区块的 gas 使用量调整，目标区块大小是 gas limit 的一半，Base Fee 每个区块最多上下调整约 12.5%。

Monad 的官方文档说，它的 Base Fee 控制器类似 EIP-1559，但特点是：

```
上涨更慢
下降更快
最低 Base Fee = 100 MON-gwei
Block gas limit = 200M gas
Transaction gas limit = 30M gas
```

Monad 生态技术文章还提到，Monad 的目标利用率是 80%，高于 Ethereum EIP-1559 的 50% 目标，这更适合高吞吐链的资源利用方式。

## 6\. 一句话总结

**Monad 的 Gas 价格模型像 Ethereum：Base Fee + Priority Fee + Max Fee；但收费对象不一样：Ethereum 主要按 Gas Used 收费，Monad 按 Gas Limit 收费。**
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

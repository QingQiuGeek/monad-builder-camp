---
timezone: UTC+8
---

# elliothunter32-star

**GitHub ID:** elliothunter32-star

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-10
<!-- DAILY_CHECKIN_2026-07-10_START -->
## 一、账户与身份体系

传统互联网产品中，每个 App 都需要注册一个独立账号（手机号、邮箱、密码），你的身份由平台管理和验证。忘记密码了可以找回，账号被盗了可以冻结，一切依赖平台这个"中间人"。

链上产品中，你的身份就是一个钱包地址，用一把私钥来控制。私钥是一串 64 位的随机数，谁持有它，谁就拥有这个地址里的一切。没有客服、没有重置密码、没有冻结机制——自由的代价是完全自负其责。

助记词（12 个英文单词）可以推导出无数个私钥和地址，而私钥只对应一个地址。助记词泄露意味着所有账户丢失，私钥泄露只影响单个地址。

## 二、数据归属与透明性

传统产品的数据存储在公司的服务器上，用户实际上并不拥有自己的数据。公司可以随时修改规则、封禁账号、删除内容，你的"资产"本质上只是数据库里的一条记录，由公司替你保管。

链上产品的数据写在区块链上，公开、透明、不可篡改。智能合约的代码对所有人可见，规则怎么运行，所有人都能检验。没有"暗箱操作"的空间。

## 三、交易与手续费机制

传统产品的操作可以撤销——转错了可以联系客服退款，下单错了可以取消。这些操作对用户来说通常是"免费"的，成本由平台承担。

链上的每一笔交易一旦被确认，就不可逆转。而且每笔交易都需要支付 Gas 费。Gas 是衡量计算资源的单位，Gas Price 是每单位的价格，两者相乘就是手续费（Transaction Fee）。

以我在 Monad Testnet 上的一笔实际交易为例：

-   **Transaction Hash**: `0x551e6b...bc56a9`
    
-   **Gas Used**: 1,000,000
    
-   **Gas Price**: 102.91 Gwei
    
-   **Transaction Fee**: 0.10291 MON
    

关键的一点是：**即使交易失败，Gas 费也照扣**。因为验证者已经花了计算资源去执行你的交易，不管结果成功还是失败，这部分工作已经完成了。这就好比你打车去一个地方，开到半路发现路断了，但司机已经开了这段路，你仍然要付这段路程的费用。

## 四、网络与连接方式

传统产品用户只需要联网、登录即可使用。用户不需要关心数据存在哪个服务器、走的什么协议。

链上产品需要用户主动选择连接哪条链。钱包通过 RPC URL 与区块链节点通信，Chain ID 确保交易不会被误发到其他链上。一个钱包可以连接多条链（如 Ethereum、Monad、Polygon），但同一时间只与一条链交互。如果不配置网络参数，钱包就像一部没插 SIM 卡的手机，有能力但连不上网络。

## 五、测试与试错成本

传统产品的测试对用户不可见，发生在公司内部的开发环境中。

链上产品有公开的测试网（Testnet），任何人都可以通过水龙头（Faucet）领取免费测试币进行操作。测试网与主网完全隔离，代币没有真实价值。Faucet 的本质是一个"金库钱包"自动向你转账，和正式转账是同一种链上操作。

![1783655065623_67160194-70f3-4460-b5ec-0a75b0100cd3.png](https://claude.ai/api/8c6db129-397b-4bf1-80cf-516b9ce14b5b/files/283038cc-576f-46bf-861f-db9cc0b21ce5/preview)![image.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/elliothunter32-star/images/2026-07-10-1783655529379-image.png)
<!-- DAILY_CHECKIN_2026-07-10_END -->

# 2026-07-09
<!-- DAILY_CHECKIN_2026-07-09_START -->

![a672f12f-102a-4ea0-bd4a-38f9327668ac.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/elliothunter32-star/images/2026-07-09-1783605084886-a672f12f-102a-4ea0-bd4a-38f9327668ac.png)![12eaf9c6-c760-4770-a0ae-35d2ccda8daf.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/elliothunter32-star/images/2026-07-09-1783605100079-12eaf9c6-c760-4770-a0ae-35d2ccda8daf.png)

1.agent高风险实例 过度授权 建议经常审查权限清单 使用agent guard工具 对于敏感操作使用人工复核  
2.prompt注入

3.恶意skills  
4.系统漏洞、ai幻觉、恶意安装软件

![cf82f41f-edc0-490f-9562-57b52f30de1e.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/elliothunter32-star/images/2026-07-09-1783605903816-cf82f41f-edc0-490f-9562-57b52f30de1e.png)
<!-- DAILY_CHECKIN_2026-07-09_END -->

# 2026-07-08
<!-- DAILY_CHECKIN_2026-07-08_START -->


![cb2e9382af2db6f6146bc1f17762cdb1.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/elliothunter32-star/images/2026-07-08-1783509776518-cb2e9382af2db6f6146bc1f17762cdb1.png)

[ai](http://1.ai) agent可以为一些个人开发者，opc提供了一个变现渠道；

在微交易的场景下，agent可以集中结算，比如电商场景；

传统金融对于风控的要求非常高；

agent可以去完成某个任务，然后拿到激励；

skill可以被付费调用，这是一个很重要的变现场景；
<!-- DAILY_CHECKIN_2026-07-08_END -->
<!-- Content_END -->

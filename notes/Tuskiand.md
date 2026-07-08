---
timezone: UTC+8
---

# Tingting Gan

**GitHub ID:** Tuskiand

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-08
<!-- DAILY_CHECKIN_2026-07-08_START -->
# **AI 辅助开发｜用 AI 生成一个最小 Solidity 合约**

## 1.先使用chatgpt网页版根据任务内容，让ai将任务分解成几个阶段，逐步完成

**ai输出如下：**[**https://chatgpt.com/s/t\_6a4e5d42d15881918e8208bc0de8e0fa**](https://chatgpt.com/s/t_6a4e5d42d15881918e8208bc0de8e0fa)

### 第一阶段：确定需求并编写 Prompt

**目标：** 让 AI 生成一个最小可运行的 Solidity 合约。

建议需求尽量简单，例如：

> 开发一个链上 Todo 合约，支持添加待办事项、查看待办事项、标记完成，不需要删除，不需要管理员权限。

### 第二阶段：AI 生成 Solidity 合约

**目标：**

让 AI 根据 Prompt 输出 Solidity 代码。

得到代码以后：

-   不急着复制
    
-   不急着部署
    
-   先阅读
    

这一阶段只需要保存：

-   AI 输出的完整 Solidity 合约
    

### 第三阶段：理解 AI 输出

不要只复制代码，而是让 AI 再解释一遍。

可以继续提问：

```
请逐行解释这个 Solidity 合约。

包括：

1. pragma 的作用
2. contract 的作用
3. struct 为什么这样定义
4. Todo[] 为什么使用数组
5. addTodo 做了什么
6. toggleCompleted 做了什么
7. getTodo 返回什么
8. memory、storage 的区别
9. view 函数为什么不能修改状态
```

### 第四阶段：人工检查（重点）

检查1：是否可以编译

检查2：函数是否符合需求

检查3：权限问题

检查4：是否存在复杂逻辑

检查5：命名是否清晰

检查6：安全风险

### 第五阶段：记录修改和最终判断

## 2.让ai解释名词

```
举几个例子解释以下的合约方向：
简单合约方向：
 - 留言板 
- 投票合约 
- 打卡合约 
- NFT Badge 
- 积分记录 
- Onchain Todo
```

ai输出：[https://chatgpt.com/s/t\_6a4e5d42d15881918e8208bc0de8e0fa](https://chatgpt.com/s/t_6a4e5d42d15881918e8208bc0de8e0fa)

| 合约方向 | 现实中的例子 | 链上保存的数据 | 主要功能 | 难度 |
| --- | --- | --- | --- | --- |
| 留言板 | 学校公告栏留言 | 留言内容、留言人、时间 | 发布、查看留言 | ⭐ |
| 投票合约 | 班级投票班长 | 候选人、票数、投票记录 | 投票、统计结果 | ⭐⭐ |
| 打卡合约 | 每日签到 | 用户地址、打卡日期 | 签到、查询签到次数 | ⭐⭐ |
| NFT Badge | 获得电子奖章 | NFT 持有者、徽章信息 | 铸造 Badge、查询拥有情况 | ⭐⭐⭐ |
| 积分记录 | 校园积分系统 | 用户积分 | 增加积分、查询积分 | ⭐⭐ |
| Onchain Todo | 待办事项清单 | Todo 内容、完成状态 | 添加、完成、查询 | ⭐ |
<!-- DAILY_CHECKIN_2026-07-08_END -->

# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->

1.  了解到了链上产品和普通互联网产品有什么不同：
    
    普通互联网产品的数据和规则主要由公司服务器控制；链上产品的数据和规则部分放到了区块链上，由代码和网络共同维护。链上产品和普通互联网产品最大的区别是“东西放在哪里、谁说了算”。普通 App 的数据和资产都放在公司的服务器里，公司负责管理；而链上产品把重要数据记录在区块链上，由网络共同维护，用户通过钱包管理自己的数字资产。传统互联网更像“租用平台服务”，Web3 更强调“用户自己拥有和控制”。
    
2.  完成了第一笔测试网交易
    
    ![image.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/Tuskiand/images/2026-07-07-1783436664738-image.png)
3.  配置好codex，安装MONSKILLS
    

![image.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/Tuskiand/images/2026-07-07-1783437825772-image.png)![image.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/Tuskiand/images/2026-07-07-1783437992511-image.png)
<!-- DAILY_CHECKIN_2026-07-07_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->




1.  实时参加线上活动DevRel 的成长之路 —— 从 Builder 到生态连接者、Co-learning
    
    ![2709e8309d6b466339815f073ba6f251.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/Tuskiand/images/2026-07-06-1783342056518-2709e8309d6b466339815f073ba6f251.png)![image.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/Tuskiand/images/2026-07-06-1783342121936-image.png)
2.  创建一个课程专用钱包，添加Monad Testnet 网络、在水龙头领取5MON币
    

![image.png](https://raw.githubusercontent.com/IntensiveCoLearning/monad-builder-camp/main/assets/Tuskiand/images/2026-07-06-1783342145995-image.png)
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

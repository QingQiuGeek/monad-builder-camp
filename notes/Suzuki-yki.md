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

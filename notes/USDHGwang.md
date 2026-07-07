---
timezone: UTC+8
---

# John

**GitHub ID:** USDHGwang

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->
**2026-07-07 — Day 2**

-   今天在整理 agent 發展框架的路徑時想到：ML/DL 演算法本身有價值但不是技術核心，agent 的價值來自「堆疊」出來的工程概念——prompt engineering → context engineering → harness engineering → loop engineering，是一層層疊上去的，不是取代關係（prompts → context/memory → skill）
    
-   但也有點不安：不確定這個框架理解得對不對，而且發現自己好像每次跟人聊天都在講 harness，有點擔心自己知識面太窄、被綁在單一主題上
    
-   Task 進度：Week1 六項任務裡，前置准备、鏈上實踐、AI輔助開發、智能合約實踐 四項的提交材料都準備好了（新建測試錢包 + 測試網交易 + HelloMonad.sol 生成部署），Monad理解跟階段總結還沒寫
<!-- DAILY_CHECKIN_2026-07-07_END -->

# 2026-07-06
<!-- DAILY_CHECKIN_2026-07-06_START -->

**2026-07-06 — Day 1｜工具準備與 Builder 身份**

-   工具/帳號：GitHub / X / Telegram / Discord 已具備，AI coding 用 Claude Code
    
-   DevRel 分享：講者 xiaohai.eth（@XiaoHai67890）是本計畫上一期學長，現任 SvpChain DevRel，分享內容是他自己從 Builder 走到生態連接者的路徑；Co-Learning 也有參加
    
-   鏈上實踐 + Monad 合約部署：沿用 AIP Protocol 既有部署（非今天新做）— `AIPRegistry` @ `0x6835B0A7bf1Bb28C40030CbeE662C965686eFd0F`，creation tx `0x22e23ecb...ddf7c35`（2026-03-24，MonadVision 驗證過）
    
-   AI 輔助開發：AIP `IntentBoundHook.sol` V1→V6 對抗式強化，每版經獨立 subagent 審核揪錯後補強，49 tests 全綠
    
-   Monad 理解：部署需加 `--legacy` flag，跟一般 EVM 鏈執行環境有差異
    
-   Week 2 方向：Tech（保留其他賽道彈性）
<!-- DAILY_CHECKIN_2026-07-06_END -->
<!-- Content_END -->

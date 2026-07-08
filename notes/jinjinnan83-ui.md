---
timezone: UTC+8
---

# jinjinnan83-ui

**GitHub ID:** jinjinnan83-ui

**Telegram:** 

## Self-introduction

Web3 暑期实习计划 - Monad Buidler Camp

## Notes

<!-- Content_START -->
# 2026-07-08
<!-- DAILY_CHECKIN_2026-07-08_START -->
-   **Agent 支付核心架构**
    
    -   **全链路能力分层**
        
        -   接入层：支持 Cloud、GPT、LangChain 等各类 Agent 载体对接，用户仅需输入简单 Prompt 即可触发 Agent 完成全流程操作。
            
        -   核心能力层：拆解为身份标识、预算管控、风控校验、交易可审计、可撤销五大模块，覆盖支付全链路需求。
            
    -   **核心技术模块**
        
        -   人机共管钱包：采用人机共管模式，无需逐笔交易人工审批，支持直接操作撤销，避免传统方案需修改代码的繁琐问题。
            
        -   X402 支付协议：基于 HTTP 402 原生支付协议优化，仅需初始授权即可实现 Agent 全链路自主支付，无需人工干预。
            
        -   批量结算协议：推出嵌入式多结算节点授权协议，预授权后预算内交易无需逐笔审批，类 Layer2 批量结算提升微支付效率。
            
        -   风控约束框架：配套 Policy Engineering 风控引擎，严格管控 Agent 幻觉带来的超支风险，满足传统金融机构的合规要求。
            
    
    ![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MGM5MjdjNWQyMTMyYWZhMDMzZGVhNGRmOGIzN2I0OTlfVk1uODZGVkRES0VkMjloVEFLME5LMGh3UXZITEFFeUVfVG9rZW46TlYwcWJ0SU5tb09iaG94NXlUaGMwTTFpbk5nXzE3ODM1MTk1MTQ6MTc4MzUyMzExNF9WNA&add_watermark=true&scene_type=CCM_DOUBAO)
-   **核心产品落地进展**
    
    -   **Agent 卡系列产品**
        
        -   一次性 Agent 卡：预设固定预算额度，单次使用后自动作废，可适配订票等场景的风控需求，当前已完成试点跑通。
            
        -   长期 Agent 卡：与 VISA 联合开发的长期可用 Agent 卡已完成底层适配，即将正式面向用户推出，可支持 Agent 持续自主支付。
            
    -   **三类支付解决方案**
        
        -   开发者货币化方案：提供无代码上架工具，开发者无需技术基础即可将 API、MCP、Skill 转化为可被 Agent 自动调用的商品。
            
        -   通用电商支付方案：针对金额不固定的零售场景，自动生成支付链接，付款方仅需一键确认即可完成交易。
            
        -   Agent 点对点转账：基于 Agent 唯一 ID 直接完成转账操作，适配 Agent 之间自主发起的交易需求。
            
        
        ![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=OWJjNzVjYzc3NTliYWY4ZDZjOTQ5YzcyMGQ3ZTcwMmVfRGNwT0JHdE1TcDF5T0tJNGt5bGVxT0FPWmNvZ1d2THZfVG9rZW46T0E4TmJKZ2Myb2owYVV4aEZ6Y2NuYU1ublJiXzE3ODM1MTk1MTQ6MTc4MzUyMzExNF9WNA&add_watermark=true&scene_type=CCM_DOUBAO)
    -   **资产与充值支持**
        
        -   链上资产：当前主落地场景为 Base 链 USDC 结算，后续将根据生态需求，支持其他公链及跨链操作。
            
        -   法币通道：支持通过 Stripe 完成法币充值，兑换为平台内部凭证用于交易，暂不支持法币直接由 Agent 调用。
            
-   **已落地场景案例**
    
    -   **社交场景试点**：春节期间上线 Agent 社交产品「Cloud 派」，支持 Agent 自动识别并完成抢红包操作，适配国内用户春节场景，上线后参与度较高。
        
    -   **百度生态合作**：承接百度生态内各类 AI 资产、OPC 项目的上架与货币化，联动双方资源做全球分发，收益归属对应开发者。
        
    
    ![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=OGI0YzEyYzk0NTcwZjIyNjE0NjZlZDViNWFiZmJiODVfSzFjbDNpNEREOUtWekNSWnZyQ28wbDdhVnBvbExlNVBfVG9rZW46UjAwY2JmTldOb1Y5YXR4MXRiU2NhNkRRbktoXzE3ODM1MTk1MTQ6MTc4MzUyMzExNF9WNA&add_watermark=true&scene_type=CCM_DOUBAO)
    -   **多场景验证**：已落地 Agent 代订票务、行业调研 Agent Skill 等试点，用户可通过付费调用对应能力获取票务、调研成果等服务。
        
-   **行业共识与未来方向**
    
    -   **行业定位**：与 Coinbase 等机构为生态合作伙伴关系，基于其推出的 X402 协议做定制化优化，不存在直接竞争关系。
        
    -   **当前阶段特征**：当前 Agent 支付以小微场景为主，用户信任培育类似早期支付宝，需随行业标准完善逐步提升大额支付接受度。
        
    -   **合规规划**：当前 Agent 卡无需额外 KYC，由合作 B 端完成主体资质核验，后续将逐步落地全链路 KYC/KYB 体系适配监管要求。
        
    -   **生态参与门槛**：当前 Agent 相关开发的多数工作可由 AI 完成，开发者仅需具备基础的计算机架构认知即可参与，无需具备完整全栈能力。
        
    -   **长期发展判断**：长期将覆盖水电煤等日常民生场景，Agent 支付将承接绝大多数重复执行类任务的交易需求，是 Agent 经济的核心基础设施。
<!-- DAILY_CHECKIN_2026-07-08_END -->

# 2026-07-07
<!-- DAILY_CHECKIN_2026-07-07_START -->

|   |   |   |
| --- | --- | --- |
|   |   |   |
|   |   |   |

EPF 项⽬核⼼规则

项⽬定位：EPF 聚焦以太坊协议层开发，区别于上层智能合约、DApp 开发，涉及共识机制、

⽹络协议、密码学等内容。

参与机制：EPF 分为官⽅许可与⽆许可两类，通过申请⾯试者可获津贴，未通过⾯试者也可⾃主参与提交成果。

资料选择：优先从以太坊维基、官⽅规范⽂档⼊⼿，可借助 AI ⼯具辅助理解英⽂⽂档，也可加⼊协议学习 Discord 社群求助。

辅助读物：可参考肖海⽼师《从0到1学习以太坊》、⼩爱⽼师区块链⽂明三部曲作为⼊⻔辅助读物，降低理解⻔槛。

学习特征：EPF 学习曲线相对陡峭，涉及较多数学、密码学内容，⽆需急于求成，按⾃⾝节奏推进即可。

学习⽅法：每周整理学习笔记，可将学习进度同步⾄社媒 @ 官⽅导师获取反馈，优先熟悉 Python、Go、Rust 等常⽤语⾔。

⽅向选择：⾸次参与优先从执⾏层、共识层⽅向切⼊，客⼾端优先选最成熟的 Go 客⼾端，再匹配相关 EIP 提案⽅向。

EPF⼊⻔学习路径

贡献实践技巧

PR 提交规范：提交的 PR 需控制修改体量，⼩体量修改更易通过审核，单次提交建议覆盖2-3 个关联 issue，体现连续性。

项⽬选择逻辑：先选定可⻓期深耕的问题域，再匹配对应仓库 issue，避免选择浅层次问题导致贡献中途中断。

参与时机：当前已进⼊某期项⽬ Week3 阶段，零基础参与者⽆需强⾏追赶，优先打好基础即可，有基础者可直接参与。
<!-- DAILY_CHECKIN_2026-07-07_END -->
<!-- Content_END -->

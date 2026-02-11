# Enterprise AI Infrastructure Solution
### 🚀 低成本、高可用、零门槛的企业级 AI 协作平台解决方案
### Low-Cost, Enterprise AI Gateway Solution based on OpenRouter & Serverless

![Status](https://img.shields.io/badge/Status-Deployed-success) ![Stack](https://img.shields.io/badge/Tech-OpenRouter%20%7C%20Zeabur%20%7C%20LobeHub-blue) ![Target](https://img.shields.io/badge/Target-Small%20Teams-orange)

---

## 📖 项目背景 (Background)

在企业推进 AI 赋能的过程中，由于缺乏海外支付手段、网络环境不稳定以及个人版账户难以管理，导致团队无法顺畅使用最先进的模型（如 Claude 3.5, GPT-4o）。

作为一名 **技术型产品经理 (Technical PM)**，我设计并落地了这套方案，通过**云原生 (Cloud Native)** 架构，打通了从 API 聚合到前端直连的完整链路。

---

## 🏗️ 系统架构 (Architecture)

本方案采用 **Serverless (无服务器)** 架构，实现了 24/7 稳定在线，且支持国内 IP 直接访问。

```mermaid
graph TD
    subgraph Client_Layer ["客户端 (Client)"]
        User(("公司员工"))
        Browser["浏览器 (直连)"]
    end

    subgraph Hosting_Layer ["云端托管 (Serverless)"]
        Server["Zeabur / Docker"]
        Lobe["LobeChat 核心引擎"]
        Auth{"Access Code 鉴权"}
    end

    subgraph API_Layer ["API 路由 (Gateway)"]
        OR["OpenRouter API"]
        Models[("Claude 3.5 Sonnet<br/>GPT-4o<br/>DeepSeek")]
    end

    User --> Browser --> Server
    Server --> Auth --> Lobe
    Lobe --> OR --> Models
## 📑 详细文档 (Detailed Documentation)
- [商业价值与成本分析](./docs/Business_Case.md)
- [技术部署指南](./docs/Deployment_Guide.md)
- [用户操作手册 (SOP)](./docs/User_SOP_CN.md)
```

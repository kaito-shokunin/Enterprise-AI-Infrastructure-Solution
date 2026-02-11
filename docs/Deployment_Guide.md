# 技术部署手册 (Technical Deployment Guide)

## 1. 架构组件 (Stack)
*   **镜像**: `lobehub/lobe-chat:latest`
*   **平台**: Zeabur (Serverless Container)
*   **接口**: OpenRouter API

## 2. 部署流程 (Step-by-Step)
1.  **仓库准备**: Fork 官方 LobeHub 仓库至个人账号，确保开启 GitOps 自动构建。
2.  **创建服务**: 在 Zeabur 中新建 `Git Service`，关联 Fork 的仓库。
3.  **网络配置**:
    *   暴露容器端口 `3210`。
    *   绑定自定义域名或使用 Zeabur 提供的子域名。
4.  **安全加固**:
    *   设置 `ACCESS_CODE` 环境变量。
    *   在 OpenRouter 后台设置 **Credit Limit**，防止 API 秘钥泄露导致资金损失。

## 3. 环境变量配置 (Environment Variables)
| Key | Value | Description |
| :--- | :--- | :--- |
| `OPENROUTER_API_KEY` | `sk-or-v1-...` | OpenRouter 秘钥 |
| `ACCESS_CODE` | `********` | 网页访问控制密码 |
| `PORT` | `3210` | 指定容器运行端口 |

## 4. 维护与更新
*   **版本同步**: 通过 GitHub Actions 定期向上游仓库同步，实现一键平滑升级。
*   **监控**: 定期通过脚本调用 OpenRouter API 检查账户余额。

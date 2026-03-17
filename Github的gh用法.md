# Ubuntu 使用 GitHub CLI（gh）精简版

## 1. 安装

sudo apt update -y
sudo apt install gh -y

## 2. 获取 Token（classic）

进入 GitHub 官网：https://github.com

路径：

- Settings（设置）
- Developer Settings（开发者设置）
- Personal access tokens（个人访问令牌）
- Tokens (classic)
- Generate new token (classic)（生成新令牌）

配置：

- Note（备注）：随便写（如 gh-cli）
- Expiration（过期时间）：选择不过期
- Scopes（权限范围）：
  - repo（仓库权限 必选）
  - delete_repo （删除仓库权限 必选）
  - read:org （读取组织权限 必选）
  - workflow（工作流，可选）
  -  剩下的不太需要

生成后复制 Token（只显示一次）

## 3. 登录（SSH + Token）

gh auth login

选择：

- GitHub.com
- SSH
- Skip（已配置 SSH Key）
- Paste an authentication token（粘贴令牌）

粘贴刚才的 Token

## 4. 结果

- Git：走 SSH
- gh：用 Token
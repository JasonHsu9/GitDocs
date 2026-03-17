Git 基础用法和 Github gh 用法文档

# 本地 Git 仓库并 Push 到 GitHub 完整流程

使用工具：

- Git
- GitHub

---

# 1 安装并检查 Git

```bash
git --version
```

如果能看到版本号，说明已经安装。

---

# 2 配置 Git 用户信息（首次需要）

```bash
git config --global user.name "kelexia"
git config --global user.email "ychuan296@gmail.com"

git config --global --list 
```

---

# 3 配置 SSH Key（用于连接 GitHub）

## 生成 SSH Key

```bash
ssh-keygen -t ed25519 -C "ychuan296@gmail.com"
```

一直回车即可。

生成文件位置：

```
~/.ssh/id_ed25519
~/.ssh/id_ed25519.pub
```

---

## Windows 查看公钥

```PowerShell
cat $env:USERPROFILE\.ssh\id_ed25519.pub
```

复制输出内容。

---

## 添加到 GitHub

进入 GitHub：

1. 点击头像  
2. Settings  
3. SSH and GPG keys  
4. New SSH Key  
5. 粘贴刚才复制的公钥并保存

---

## 测试 SSH 连接

```bash
ssh -T git@github.com
```

如果成功会看到类似：

```
Hi kelexia! You've successfully authenticated
```

---

# 4 创建本地仓库

```bash
mkdir myproject
cd myproject
git init
```

---

# 5 添加文件并提交

```bash
touch README.md

git add .

git commit -m "first commit"
```

---

# 6 创建 GitHub 仓库

在 GitHub：

1. 点击 **New repository**
2. 输入仓库名（例如 `myproject`）
3. 创建仓库

---

# 7 连接远程仓库

使用 SSH 地址：

```bash
git remote add origin git@github.com:JasonHsu9/GitDocs.git
```

检查：

```bash
git remote -v
```

---

# 8 推送代码到 GitHub

```bash
git branch -M main
git push -u origin main

或者强制覆盖（在远程有更新但是需要丢弃的情况）
git push -f -u origin main
```

---

# 9 日常开发流程

之后每次更新代码：

```bash
git add .
git commit -m "update"
git push
```

---

# 最简开发循环

程序员日常循环：

```bash
git add .
git commit -m "修改内容"
git push
```

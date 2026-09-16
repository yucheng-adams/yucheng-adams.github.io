---
layout: post
title: "科学上网指导｜一个有关于GitHub与VScode同步失败排查"
date: 2026-09-14 12:00:00
description: "A post of troubleshooting about github sync"
tags: [科学上网, 代理]
categories: [故障排查]
---

### 1.先检查 Git 代理

确认代理软件已开启，并让 Git 使用代理软件实际的 HTTP／Mixed 端口。本次使用 `7897`：

```bash
git config --global http.proxy http://127.0.0.1:7897
```

查看设置：

```bash
git config --global --get http.proxy
```

### 2.再检查 GitHub 账号认证

确认 VS Code 登录的是仓库所属的 GitHub 账号，或具有该仓库写入权限的账号。

如果提示 `Failed to authenticate`，退出 GitHub 账号后重新登录，并完成浏览器授权，再尝试同步。

记住：能连接、能读取仓库，不代表已通过推送认证。先查代理连接，再查账号和权限。
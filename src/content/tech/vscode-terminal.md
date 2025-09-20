---
title: "VS Code - 解决 “pnpm 无法加载脚本"
tags: [VS Code]
draft: false
weight: 10
---

## 1. 问题现象

在 VS Code 的 PowerShell 终端执行

```powershell
pnpm dev:mp
```

报错：

```
无法加载文件 …\pnpm.ps1，因为在此系统上禁止运行脚本。
```

## 2. 最快全局修复（一次搞定）

1. 以**管理员身份**打开 VS Code 内置终端  
   `Ctrl + Shift + P` → 输入 `Terminal: Create New Terminal (Admin)`
2. 运行
   ```powershell
   Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
   ```
3. 关闭终端，重新打开普通终端，再次
   ```powershell
   pnpm dev:mp
   ```
   即可正常启动。

> 该设置仅对当前 Windows 用户生效，不影响系统安全策略。

```

```

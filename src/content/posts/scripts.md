---
title: "个人脚本大全 —— 焚诀 Git 工作流"
published: 2026-05-20
updated: 2026-11-12
description: "本仓库收集了个人常用的自动化脚本，方便快捷地在终端中使用。核心为《焚诀·Git 工作流》v5.2，提供书签导航、智能推送、多平台远程管理等终端工具。"
tags: [脚本, 工具, 自动化]
category: 工具
draft: false
---

# scripts — 个人脚本大全

本仓库收集了个人常用的自动化脚本，方便快捷地在终端中使用。核心是 **《焚诀·Git 工作流》v5.2**，一套基于书签系统的 Git 终端导航与操作工具集，适合在 Termux 及各类类 Unix 环境中高效管理多个 Git 项目。

> 项目仓库：[https://github.com/zzgs219G/scripts](https://github.com/zzgs219G/scripts)

## ✨ 核心特性

- **书签系统**（v5.0 起）：以「书签」取代硬编码路径，每个书签对应一个顶层项目目录，支持书签之间的项目移动/复制并自动修复 Git 安全权限。
- **三阶段交互导航**（`c` 命令）：书签选择 → 项目列表 → 项目操作，支持方向键 ↑/↓、回车确认、数字直选，管道环境自动退化为数字输入。
- **智能推送**（`p` 命令）：推送前 fetch 只读检测，不触碰本地代码；落后远程时列出新提交与涉及文件，由用户决定（拉取合并 / 安全强推 / 取消）。
- **多平台远程**（`remote` 命令）：支持 GitHub / GitLab / Gitee / 腾讯云 CNB / CODING / 自定义平台，选平台填用户名仓库名自动拼 URL。
- **批量拉取**（`pullall`）：基于书签遍历所有 Git 项目批量 `git pull`，统计成功/失败。
- **AI 提交信息**：配置 `aikey` 后，推送时自动生成 commit message。

## 🚀 快速安装

推荐使用 **ZeroTermux** 环境（Termux 下测试通过），电脑端 Git Bash / WSL / macOS / Linux 均可运行。

```bash
# 1. 安装核心依赖
pkg install git curl gh

# 2. 克隆 scripts 仓库
cd ~
git clone https://github.com/zzgs219G/scripts.git

# 3. 写入 ~/.bashrc（幂等，重复执行不会堆叠）
sed -i '/fz-tools\/fzgit.sh/d' ~/.bashrc
echo 'source "$HOME/scripts/fz-tools/fzgit.sh"' >> ~/.bashrc
source ~/.bashrc

# 4. 初始化环境与书签
setup    # 检查环境 + 配置 Git 全局信息 + 创建书签
login    # 登录 GitHub（可选）
aikey    # 配置 AI commit Key（可选）
```

## 🛠 常用命令概览

| 命令 | 说明 |
|------|------|
| `c` | 书签 → 项目 → 操作 三阶段交互导航 |
| `b` | 分支切换/创建/重命名/清理 |
| `p` | 智能推送（含前置冲突检测） |
| `st` | 当前分支、变更文件、书签、领先/落后状态 |
| `lsp` | 所有书签项目状态总览 |
| `cl` | 交互式克隆 GitHub 仓库并自动注册书签 |
| `pullall` | 基于书签批量拉取所有项目 |
| `setup` | 环境检查 + Git 配置 + 创建书签 |
| `remote` | 多平台远程仓库管理 |
| `ok` | 合并 dev→main 发布 |
| `save/pop` | 暂存与恢复工作区 |
| `tag` | 版本标签管理 |
| `burn/f` | 全量打包源码（过滤密钥/缓存/大资源） |
| `rsx` | 一键安装/升级 Reasonix CLI |
| `up` | 基于 git 拉取整个 scripts 仓库更新 |

## 📖 文档与进阶

- [流程文档](https://github.com/zzgs219G/scripts/blob/main/docs/流程文档.md) —— 安装 → 日常 → 推送 → 炼化 → 异常恢复完整流程
- [新手指南](https://github.com/zzgs219G/scripts/blob/main/docs/新手指南.md) —— 面向不会 Git 的用户（场景问答/平台指南/电脑使用）
- [AGENTS.md](https://github.com/zzgs219G/scripts/blob/main/AGENTS.md) —— AI 修改本仓库前的必读契约

---

> 提示：本篇为博客收录页，完整且实时的命令说明请以 [scripts 项目 README](https://github.com/zzgs219G/scripts/blob/main/README.md) 为准。

---
title: "个人脚本大全"
published: 2026-05-20
updated: 2026-11-12
description: "本仓库收集了个人常用的自动化脚本，方便快捷地在终端中使用。"
tags: [脚本, 工具, 自动化]
category: 工具
draft: false
---

# scripts
个人脚本大全

本仓库收集了个人常用的自动化脚本，方便快捷地在终端中使用。

## 推荐环境
推荐使用 **ZeroTermux** 以获得最佳体验（在 Termux 环境下测试通过）。

开源地址：
<!-- ::github{repo="hanxinhao000/ZeroTermux"} -->
::github{repo="hanxinhao000/ZeroTermux"}

:::tip[📦 项目已更新至 v5.x]
scripts 项目已从旧版 curl 注入方式升级为书签系统 + 三阶段导航架构，核心变化包括：

- **书签系统**（v5.0 起）：以「书签」取代硬编码路径，支持项目在书签间移动/复制并自动修复 Git 安全权限。
- **三阶段交互导航**（`c` 命令）：书签选择 → 项目列表 → 项目操作，支持方向键 ↑/↓、回车确认、数字直选。
- **智能推送**（`p` 命令）：推送前 fetch 只读检测，不触碰本地代码，落后时由用户决定拉取合并 / 安全强推 / 取消。
- **多平台远程**（`remote` 命令）：支持 GitHub / GitLab / Gitee / 腾讯云 CNB / CODING / 自定义平台。
- **批量拉取**（`pullall`）：基于书签遍历所有 Git 项目批量 `git pull`。

完整命令说明请参考 [scripts 项目 README](https://github.com/zzgs219G/scripts/blob/main/README.md)。
:::

## 快速使用
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
## 效果截图
ZeroTermux

![screenshot-small](https://tg-image.614118.xyz/260612-e2b5g7.jpg)

![screenshot-small](https://tg-image.614118.xyz/260612-f3c6h8.jpg)

<style>
  /* 强行击穿 Fuwari 主题对 img 的 100% 限制 */
  img[alt="screenshot-small"] {
    width: 350px !important;
    max-width: 100% !important;
    display: inline-block !important;
    margin: 10px auto !important;
  }
</style>

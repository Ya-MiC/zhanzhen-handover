# 🐙 湛箴业务移交全集（Handover）

> 移交日期：2026-08-26 · 整理：ox-alpha (Hermes Agent) · 接收：Ya-MiC 及后续任何 AI/人类协作者
> **本仓库是湛箴业务的唯一移交入口。从这里的链接能到达一切。**

## 业务一句话

**面向中国全国统一大市场中小企业的审计作业系统**——拍凭证→OCR识别→覆核→账套分录→3+12规则扫描→按甲方分型的可追溯审计报告。免费+专业两档订阅（¥199/年对标剪映）；报告须经注册会计师签署方具法律效力。

## 文档导航

| # | 文档 | 内容 |
|---|---|---|
| 01 | [业务状态](01_BUSINESS_STATE.md) | 做到哪、卡在哪、下一步 |
| 02 | [创始人诉求对照](02_FOUNDER_REQUESTS.md) | 你的每条要求 × 落实状态 |
| 03 | [架构全景](03_ARCHITECTURE.md) | 三端+数据库+加密+权限+流水线 |
| 04 | [仓库路径地图](04_REPO_MAP.md) | 7 仓×分支×Release 直链 |
| 05 | [文档索引](05_DOC_INDEX.md) | 全部 md 的路径与职责 |
| 06 | [插件清单](06_PLUGIN_MANIFEST.md) | DSH 插件全景 + 工作流节点 |
| 07 | [子agent协同方法](07_SUBAGENT_PLAYBOOK.md) | 怎么派/验收/补位 |
| 08 | [Skill 与记忆](08_SKILLS_AND_MEMORY.md) | 永久技能清单 |
| 09 | [下一步建议](09_NEXT_STEPS.md) | 移交后路线 |

## 一屏速览：现在能用什么

| 端 | 下载/访问 | 状态 |
|---|---|---|
| 💻 Windows | [zhanzhen-v0.3.0-windows-x64.exe](https://github.com/Ya-MiC/zhanzhen/releases/download/v0.3.0/zhanzhen-v0.3.0-windows-x64.exe)（38MB，双击即用） | ✅ |
| 📱 安卓 | [zhanzhen-v0.5.apk](https://github.com/Ya-MiC/audit-os-mobile/releases/download/v0.5/zhanzhen-v0.5.apk) | ✅ 拍照队列+直传双轨 |
| 🌐 网页版 | [zhanzhen-web](https://github.com/Ya-MiC/zhanzhen-web) → CF Pages 连接即部署 | ✅ 静态壳就绪 |
| 🔌 DSH 工作流 | [dsh-plugin 分支](https://github.com/Ya-MiC/zhanzhen/tree/dsh-plugin) 七节点审计流水线 | ✅ 面板可调 |

## 核心仓库直链

- 主软件 v0.3.0：https://github.com/Ya-MiC/zhanzhen （main 87文件 · dsh-plugin 80文件 · CI 绿）
- 规格权威：https://github.com/Ya-MiC/action-tree （私有：5万字总纲 + docs/01-15 + specs 三件套 + ADR）
- 安卓采集端：https://github.com/Ya-MiC/audit-os-mobile （v0.5，红金山图标已恢复）
- 网页前端：https://github.com/Ya-MiC/zhanzhen-web （CF Pages 零构建部署）
- 插件生态：https://github.com/Ya-MiC/hermes/tree/dsh-plugins （六插件十工具 CI 绿）
- CLI 参考：https://github.com/Ya-MiC/audit-os （12规则语义权威）
- OCR 资产：https://github.com/Ya-MiC/invoice-ocr-system （正则抽取库）

## 待办（只有人能做的）

1. **ADR-001 三个勾选**（action-tree/docs/adr/）——金额表示/规则DSL/仓库边界
2. **域名提供**——挂 `/zz/` 路径 + CF 回源，网页版即刻上线
3. **VPS 装 PaddleOCR**——`pip install 'zhanzhen[ocr]'` 后拍照识别即刻可用
4. **商标检索**——中国商标网查「湛箴」9/35/42 类
5. **金标数据集**——每类 ≥30 张去敏凭证样本

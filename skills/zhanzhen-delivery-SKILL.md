---
name: zhanzhen-delivery
description: 湛箴审计OS交付规范：架构定稿、UI验收清单、部署要点、用户(Ya-MiC)协作铁律。改zhanzhen仓库前必读。
version: 1.1.0
author: Ya-MiC / ox-alpha (Hermes)
license: MIT
metadata:
  hermes:
    tags: [zhanzhen, audit, dsh, github-delivery]
    related_skills: [github-rest-content-workflow, audit-os-engineering]
---

# 湛箴 ZhanZhen 交付规范（Ya-MiC 审计软件）

## When to Use
凡涉及 `Ya-MiC/zhanzhen`、`Ya-MiC/audit-os-mobile`、湛箴/审计OS 的任何代码、UI、文档、部署动作前，先读本规范。创始人提出 UI/功能需求时按文末沟通模板追问三要素。
**本规范中「协作铁律」一节适用于所有对话的所有任务，不限于湛箴项目。**

## 仓库分工地图（写到哪里）
| 内容性质 | 目标仓库/分支 |
|---|---|
| 主软件（网页版/服务端/桌面） | `zhanzhen` main |
| DSH 工作流插件 | `zhanzhen` dsh-plugin 分支 |
| 通用 DSH 插件（量化/学习等） | `hermes` dsh-plugins 分支 |
| 战略总纲/specs/ADR/工程文档 | `action-tree`（私有，唯一规格权威） |
| 安卓采集端 | `audit-os-mobile` |
| 个人事务（移民/规划） | `hermes-private`（私有） |
| 全景索引 | `hermes` main README + action-tree INDEX.md |

每次跨仓产出后：更新对应索引文件，保持「从入口能到达一切」。

## 产品身份
- 正名只有「**湛箴**」；🐙 章鱼=吉祥物符号；OZ 仅内部代号不对外
- 品牌/图标基因：docs/BRAND_OCTOPUS.md；商标只查「湛箴」

## 架构定稿（创始人拍板，勿改）
- **一仓三分支**：`Ya-MiC/zhanzhen`
  - `main`：网页版+服务端（FastAPI+Vue3 单页，端口 8710，`ZZ_PORT` 可改）
  - `dsh-plugin`：审计行业 n8n 七节点流程引擎（trigger→ocr→manual→rules→journal→report→approve），契合官方 DSH 面板（defineTool/cordis.yml/dsh.bundle.json/smoke.ts）
  - 安卓在 `audit-os-mobile` v0.5（WebView 壳，拍照队列本地优先 + uploadPack 直传双轨）
- **数据库统一 PostgreSQL**（`ZZ_DATABASE_URL`），sqlite 仅本地开发降级；表结构按 action-tree docs/03 Canonical 模型
- **加密护城河**：报告正文/写作思路 Fernet 加密（PBKDF2←`ZZ_MASTER_KEY`）存 report_assets 表；密钥不落盘不进 Git
- 双门户：用户端 `/`（免费下载即用=本地admin）vs 管理台 `/admin`（订阅/API Key/冻结）；四角色 admin/accountant/reviewer/viewer，`ZZ_USERS=key:name:role`

## 商业红线
- 只两档：免费(3报告+100OCR月) / 专业 ¥199年对标剪映；免费版功能完整不做残废
- 报告永远是分析初稿，**须经注册会计师签署方具法律效力**——每份输出必带此免责声明
- 引擎 MIT / 规则配方商业秘密 / 行业词典付费 / 用户数据用户所有 / 不用 AGPL

## UI 验收清单（每次改界面必过）
- 设计 token：主蓝 #0F4C81 点缀金 #C9A063；侧边栏导航布局；8px 栅格
- 覆核页分栏可键盘流转；报告结论 ≤2 跳回原始凭证 SHA-256
- 空 state 有引导按钮；错误用中文 toast 不弹堆栈；金额右对齐千分位
- 详细清单：zhanzhen/docs/UI_AUDIT_NOTES.md

## 协作铁律（Ya-MiC 多次纠正，**所有对话永久遵守**）
- **成果直推 GitHub**，本地 VPS 只是草稿；不在容器里跑服务测试
- **不局限一个仓库**：按内容性质写到最合适的仓库（业务=zhanzhen/audit-os*/action-tree，插件=hermes dsh-plugins 分支，规格=action-tree，个人=hermes-private），跨仓在各自 README/索引里互相链接
- **一产品一视图**：虽然多仓存放，但每条业务线要有一个唯一入口索引（如 action-tree/INDEX.md），人类从入口能到达一切
- **卡住/不会/缺信息 → 先问 Ya-MiC**，绝不猜、绝不编造；BLOCKED 时停下来问
- 一产品一仓原则仅指「人类视角一个入口」，不是物理上只能写一个仓库
- 干活方式：多个 ox-alpha 子 agent 并行 → 直推 GitHub + 单测全绿 → 卡住 steer/重派 → 统一回归后汇报（链接+一屏总结）
- 交付汇报格式：仓库/文件链接 + 一屏内总结，过程叙述要短
- 不知道就问创始人，不要猜

## 部署速查
- 服务器=国内轻量云（数据不出境）+ ICP 备案；详见 SERVER_DEPLOY.md
- CF HTTPS/TLS 用户已配好；域名挂路径等用户提供域名后加 BASE_PATH 反代片段

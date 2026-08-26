# 04 · 仓库路径地图

## 业务七仓

| 仓库 | 分支 | 文件数 | 角色 | 直链 |
|---|---|---|---|---|
| **zhanzhen** | main | 87 | 主软件 v0.3.0（97测试绿 CI绿） | github.com/Ya-MiC/zhanzhen |
| | dsh-plugin | 80 | DSH 工作流插件（七节点） | .../tree/dsh-plugin |
| **action-tree** 🔒私有 | main | 25 | 规格权威：5万字总纲+docs01-15+specs三件套+ADR | github.com/Ya-MiC/action-tree |
| **audit-os-mobile** | main | 31 | 安卓采集端 v0.5 | github.com/Ya-MiC/audit-os-mobile |
| **zhanzhen-web** | main | 4 | CF Pages 网页前端壳 | github.com/Ya-MiC/zhanzhen-web |
| **audit-os** | main | 18 | CLI 参考（12规则语义权威） | github.com/Ya-MiC/audit-os |
| **invoice-ocr-system** | main | ~40 | 发票 OCR 正则资产（MIT） | github.com/Ya-MiC/invoice-ocr-system |
| **hermes** | dsh-plugins | 27 | 六插件十工具生态 | github.com/Ya-MiC/hermes |
| **handover（本仓）** | main | — | 移交全集入口 | github.com/Ya-MiC/zhanzhen-handover |

## Release 资产直链

- Windows exe：https://github.com/Ya-MiC/zhanzhen/releases/download/v0.3.0/zhanzhen-v0.3.0-windows-x64.exe
- 安卓 APK：https://github.com/Ya-MiC/audit-os-mobile/releases/download/v0.5/zhanzhen-v0.5.apk
- 发布页：zhanzhen/releases/tag/v0.3.0 · audit-os-mobile/releases/tag/v0.5

## 自动构建

- Windows exe：推 tag `v*` 自动 PyInstaller 打包挂 Release（build-windows.yml）
- 安卓 APK：push main 自动 aapt2/d8/apksigner 构建挂 Release（build-apk.yml，workflow 已激活）

## 关键文件速查（zhanzhen main）

| 路径 | 职责 |
|---|---|
| zhanzhen/service.py | 全流程编排（管线心脏） |
| zhanzhen/rules12.py | 12条规则（audit-os 语义移植） |
| zhanzhen/report_engine.py | 五受众报告模板 |
| zhanzhen/crypto.py | 加密层（护城河保护） |
| zhanzhen/database.py | PostgreSQL/SQLite 双后端 |
| zhanzhen/auth.py + billing.py | 角色+订阅额度 |
| web/index.html + admin.html | 用户端+管理台 UI |
| docs/REPORT_KNOWLEDGE.md | 报告写作手法与免费资源地图 |

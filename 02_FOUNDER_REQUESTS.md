# 02 · 创始人诉求对照表

> 原话追踪：每条诉求 × 落实状态 × 所在位置。全部截至 2026-08-26。

## 产品与业务

| # | 诉求（原话摘要） | 状态 | 落点 |
|---|---|---|---|
| 1 | 完整软件不是demo，安卓+Win+网页三端 | ✅ | zhanzhen/releases + audit-os-mobile/releases + zhanzhen-web |
| 2 | 免费+专业两档就好，不做多档 | ✅ | docs/PRODUCT_TIERS.md |
| 3 | 写报告的还得是注册会计师 | ✅ | 每份报告免责声明+docs/user/CPA_COMPLIANCE.md |
| 4 | 订阅制收费情况写清楚 | ✅ | PRODUCT_TIERS §定价锚点 ¥199年 |
| 5 | 一切信息以用户本人纸质照片 OCR 为准 | ✅ | OCR_STRATEGY.md 数据主权原则 |
| 6 | jpg/png/pdf 上传都考虑 | ✅ | ocr_router.py 图片链+PDF 文本层 |
| 7 | 鼎信诺那种 Excel 模板账套导入 | ✅ | importers.py 自动嗅探 |
| 8 | 用户上传自己之前写的报告 | ✅ | POST /v1/reports/upload-style-sample |
| 9 | 甲方可能要 PDF/政府/企业不同格式 | ✅ | report_engine.py 五受众分型 |
| 10 | 报告写作思路和格式算护城河 | ✅ | crypto.py 加密 report_assets 表 |

## 品牌与命名

| # | 诉求 | 状态 | 落点 |
|---|---|---|---|
| 11 | 名字就叫湛箴不要 Oz | ✅ | BRAND_OCTOPUS.md v3 口径 |
| 12 | 章鱼 emoji 是可爱符号 | ✅ | 同上 |
| 13 | OZ 只是内部代号 | ✅ | 仅 zz.* 命令空间使用 |
| 14 | 图标用 0.3 的红金山 | ✅ 已修 | mipmap 六密度真图标 ba8838be |

## 协作方式

| # | 诉求 | 状态 | 落点 |
|---|---|---|---|
| 15 | 直接写在 GitHub 不在 VPS 干活 | ✅ | Git Data API 全程推送 |
| 16 | 用一堆子agent干活 | ✅ | SUBAGENT_PLAYBOOK.md 方法论 |
| 17 | 多看我的仓库特别是人类写的 | ✅ | action-tree 全部规格已消化移植 |
| 18 | 不局限一个仓库 | ✅ | 七仓分工地图 REPO_MAP.md |
| 19 | 卡住不会先问你 | ✅ | 域名/ADR 均已停下询问 |
| 20 | DSH 插件契合官方面板可调流程像 n8n | ✅ | dsh-plugin 分支七节点引擎+基础模板 |
| 21 | 管理员面板也要有 UI | ✅ | web/admin.html 深色侧边栏版 |
| 22 | 学习成熟产品做好 UI | ✅ | v0.3 SaaS 级改版+UI_AUDIT_NOTES.md |
| 23 | 网页版直接 GitHub 库你自己连 CF Pages | ✅ | zhanzhen-web 仓库已建 |

## 待办（人做）

见 01_BUSINESS_STATE.md 第三节。

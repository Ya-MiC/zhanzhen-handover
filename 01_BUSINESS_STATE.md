# 01 · 业务状态（2026-08-26）

## 一、整体位置

```
总纲路线：Phase-0 技术原型 ✅ ──► M0 真实验证 ◄──【现在在这】──► M1 Web 内测 ──► M2 事务所试点
规范周：   Week1 契约 ✅ | W2-W6 核心语义提前落地 ✅ | W3 OCR worker 🔶 | W8 验收 ⬜
版本：     v0.3.0（UI 改版+三端齐备）
```

## 二、已完成（全部可验证）

### 软件本体 zhanzhen v0.3.0（87 文件，97 测试绿，CI 绿）
- **全管线**：凭证上传→OCR→覆核→分录→规则→报告
- **OCR 三级路由** `ocr_router.py`：PDF文本层 / Tesseract / PaddleOCR / 明确服务端提示；图片(jpg/png) PaddleOCR Provider 已接
- **3+12 双规则引擎**：MVP 三条 + audit-os 十二条完整移植（重要性自动校准/严重度阶梯/单规则隔离/R012双向冲销窗口修正）
- **五受众报告引擎** `report_engine.py`：bank/gov/boss/firm/cross 五模板，每份强制 CPA 免责声明
- **加密层** `crypto.py`：Fernet+PBKDF2(ZZ_MASTER_KEY)；report_assets 护城河表加密落库
- **PostgreSQL 双后端**：ZZ_DATABASE_URL 切生产库，sqlite 本地降级
- **权限** auth.py 四角色 + billing.py 两档额度（免费3报告100OCR月）+ /admin 管理台
- **导入器** importers.py：鼎信诺/金蝶 Excel 自动嗅探批量入账

### 三端分发
| 端 | 形态 | 链接 |
|---|---|---|
| Windows | exe 38MB（CI 自动构建） | zhanzhen/releases/tag/v0.3.0 |
| 安卓 | APK v0.5（拍照队列+直传双轨+红金山图标已恢复） | audit-os-mobile/releases/tag/v0.5 |
| 网页 | CF Pages 静态壳（zhanzhen-web 仓库） | 连接后端即用 |

### DSH 插件（审计 n8n）
zhanzhen dsh-plugin 分支：七节点流程引擎（trigger→ocr→manual→rules→journal→report→approve）+ 基础模板 + zz.workflow.list/run 工具 + cordis.yml/bundle/smoke 全套。

## 三、卡住的事（需要创始人）

| # | 卡点 | 谁能解 |
|---|---|---|
| 1 | ADR-001 三勾选未裁——server 正式化前必须 | 只有你 |
| 2 | 域名未提供——网页版上线/手机直传需要 | 只有你 |
| 3 | VPS 未装 PaddleOCR——图片识别不可用 | 你或下任 agent（一条 pip 命令） |
| 4 | 金标数据集为空——OCR 准确率无法评估 | 只有你（去敏样本） |
| 5 | 定价未经真实访谈验证 | 你+5家小型所访谈 |

## 四、下一步建议顺序

1. VPS 部署（SERVER_DEPLOY.md 照抄）→ 装 [ocr] extra → 手机直传打通
2. 找 1 家相熟代账公司免费试用 → 收集真实账套跑 M0 指标
3. 裁 ADR-001 → PostgreSQL 正式迁移（RLS 实验）
4. 域名挂载 → 网页版公测

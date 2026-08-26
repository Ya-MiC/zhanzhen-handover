# 03 · 架构全景

> 上游权威：action-tree/docs/02 系统架构 + ENGINEERING_SPEC。本图是已实现状态的写实。

## 三端一库

```
┌─────────────────┐  ┌──────────────────┐  ┌─────────────────┐
│ 📱 安卓 v0.5     │  │ 💻 Windows exe    │  │ 🌐 网页 CF Pages │
│ audit-os-mobile  │  │ zhanzhen.exe      │  │ zhanzhen-web    │
│ 拍照/队列/直传    │  │ 内嵌服务+浏览器   │  │ 静态壳连 API     │
└────────┬────────┘  └────────┬─────────┘  └────────┬────────┘
         │      HTTPS (X-API-Key)                    │
         └──────────────┬────────────────────────────┘
                        ▼
         ┌──────────────────────────────┐
         │   FastAPI 服务 (zhanzhen)     │
         │  auth.py 四角色门卫           │
         │  billing.py 两档额度          │
         │  ocr_router.py OCR 三级路由   │
         │  rules.py+rules12.py 15规则  │
         │  report_engine.py 五受众模板  │
         │  crypto.py Fernet 加密        │
         └───────┬─────────────┬────────┘
                 ▼             ▼
       PostgreSQL(生产)   SQLite(本地降级)
       ZZ_DATABASE_URL     内容寻址对象存储
```

## 核心流水线（智能体宏 = 软件昂贵点）

```
拍凭证 → [OCR三级:系统/PaddleLite/服务端] → VoucherJSON v1 标准化
→ 质量门(低置信→人工覆核,逐字段留痕) → 分录草稿(借贷平衡硬校验)
→ 确认锁定(lines_hash) → 规则扫描(MVP3条+完整12条)
→ findings(严重度+证据引用) → 五受众报告(CPA免责声明)
全程：每次状态迁移追加 SHA-256 哈希链事件，任何结论 ≤2 跳回原始凭证
```

## 安全与护城河

| 层 | 实现 |
|---|---|
| 证据防篡改 | canonical JSON 哈希链（events.py），verify_chain() 随时校验 |
| 报告资产加密 | crypto.py：PBKDF2←ZZ_MASTER_KEY→Fernet；report_assets 表 |
| 权限 | 四角色 RBAC（admin/accountant/reviewer/viewer）+ 租户隔离 |
| 商业秘密 | 规则调优参数不发布；行业科目词典专业版专属 |

## 端口与环境变量

- 端口 8710 默认（ZZ_PORT 改）
- ZZ_DATA_DIR 数据目录 · ZZ_TENANT_ID 租户 · ZZ_USERS 多用户 · ZZ_AI_* AI助手(默认关)
- 全部见 .env.example 与 docs/user/CONFIG.md

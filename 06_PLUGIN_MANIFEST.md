# 06 · DSH 插件全景

## zhanzhen 工作流插件（dsh-plugin 分支，v2.0.0）

**「审计行业 n8n」**——七节点可视化流水线：

```text
trigger 凭证导入 → ocr 识别 → manual 人工覆核 → journal 账套分录
       → rules 12规则扫描 → report 报告生成 → approve CPA签发流转
```

- 每节点有输入/输出工件契约（workflow-engine.ts NODE_KIND_CONTRACTS）
- 基础模板 workflow-template-audit-basic.json 开箱即用
- 面板工具：`zz.workflow.list` / `zz.workflow.run`
- 业务命令：zz.vouchers / zz.ocr / zz.review / zz.journal / zz.rules / zz.report / zz.integrity
- 纯逻辑层不依赖 cordis；按官方 dsh-tool-workflow 事件词表上报进度供面板渲染
- 配套齐全：package.json(keywords 全打)/cordis.yml/dsh.bundle.json/smoke.ts/tsconfig

## hermes 六插件十工具（dsh-plugins 分支，CI 绿）

| 插件 | 工具 | 功能 |
|---|---|---|
| dsh-audit-draft | audit_draft | 审计底稿草拟助手 |
| dsh-quant-backtest | quant_backtest | 双均线策略回测 |
| dsh-momentum-screen | momentum_screen | 动量突破选股 |
| dsh-risk-size | position_size_atr / portfolio_heat / kelly_fraction | ATR仓位/组合热度/凯利 |
| dsh-ielts-coach | ielts_log / ielts_progress | 雅思打卡与进度 |
| dsh-identity-checklist | identity_status / identity_done | 移民里程碑清单 |

另有独立仓 dsh-stock-watch（A股盯盘）。

## 五大类覆盖矩阵（PLUGIN_ROADMAP.md）

审计✅ / 量化✅ / 代理网络📋(px.*) / AI智能体📋(ocr.* skill.*) / 文档📋(doc.*)

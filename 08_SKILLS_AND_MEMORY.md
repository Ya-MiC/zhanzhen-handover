# 08 · Skill 与记忆（永久能力清单）

## Hermes Skills（真实清单：89 个，文件系统扫描导出）

完整注册表见 [skills/skill-registry.md](skills/skill-registry.md)（从 /opt/data/skills/ 逐目录扫描，含每个的官方 description）。

### 与湛箴业务直接相关的核心技能

| skill | 用途 |
|---|---|
| **zhanzhen-delivery** | 湛箴交付根规范（架构定稿/UI验收/协作铁律/仓库分工地图） |
| **github-rest-content-workflow** | Git Data API 批量推送/409对策/Release 上传——湛箴全程使用 |
| **audit-os-engineering** | 用户亲笔工程规范要点（跨仓契约/状态机/证据链不变量） |
| **hermes-github-org** | 七分支整理规范 |
| **dsh-plugin-engineering** | DSH 插件官方编写规范（工作流插件的规范来源） |
| **github-api-writing** | REST 批量写 GitHub 的可靠模式 |

其余 83 个为通用能力（创意/效率/研究/MLOps/调试等），按需加载，详见注册表。


## 关键记忆条目（MEMORY.md 摘要）

- 模型铁律：主模型+子agent只用 ox-alpha；NVIDIA API 仅备胎
- 交付铁律：直推 GitHub 不本地折腾；一屏总结
- 命名 v3：正名只「湛箴」，🐙仅符号，OZ 内部代号
- 产品定稿：免费+专业两档；CPA 签发边界；不用 AGPL
- 架构定稿：PostgreSQL 统一；报告加密=护城河；一仓三分支

## 给下任 agent 的第一句话

> 读 zhanzhen-handover 仓库全部文档 → source .gh_env 拿 token → 一切规格以 action-tree 为准 → 干活按 SUBAGENT_PLAYBOOK。

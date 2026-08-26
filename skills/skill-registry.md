# Hermes Skill 注册表（Ya-MiC 环境全量清单）

> 导出时间：2026-08-26 · 来源：/opt/data/skills/
> 每条含：名称 / 触发条件 / 核心内容一句话。

## 软件开发类（software-development/）

### zhanzhen-delivery ★本项目根规范
- 触发：凡涉及 zhanzhen / audit-os-mobile / 湛箴 / 审计OS 的任何动作前必读
- 内容：架构定稿（一仓三分支/PostgreSQL统一/Fernet加密护城河/双门户四角色）、命名口径v3（正名只湛箴，🐙符号，OZ内部代号）、商业红线（免费+专业两档/CPA签发边界/不用AGPL）、UI验收清单、协作铁律（直推GitHub不本地折腾/多仓分工/卡住先问/ox-alpha子agent并行）
- 关键文件：SKILL.md

### audit-os-engineering
- 触发：动 Ya-MiC 审计OS系代码前必读
- 内容：用户亲笔工程规范要点——跨仓契约/状态机/证据链不变量/Agent工作协议（修改前列清单、小步提交、DoD七条）

### systematic-debugging
- 触发：修 bug 时
- 内容：4阶段根因调试法——先理解再动手

### test-driven-development
- 触发：写新功能时
- 内容：RED-GREEN-REFACTOR 循环强制

### requesting-code-review
- 触发：commit 前
- 内容：安全扫描+质量门+自动修复

### plan / spike / simplify-code / dogfood / python-debugpy / node-inspect-debugger / inspecting-hermes-desktop-dom / hermes-agent-skill-authoring
- 计划文档 / 丢弃式实验 / 并行4-agent代码清理 / Web应用探索QA / Python pdb+debugpy / Node --inspect CDP / Hermes桌面DOM检查 / SKILL.md编写规范

## GitHub 类（github/）

### github-rest-content-workflow ★湛箴全程使用
- 触发：任何 GitHub REST 写操作
- 内容：Git Data API 批量推送（blob→tree→commit→ref）/ Contents API 缓存409对策 / Release资产上传 / 空仓引导建分支 / 验证用 contents API 不用 raw（CDN延迟）

### github-pr-workflow / github-code-review / github-issue-to-pr / github-issues / github-repo-management / github-auth
- PR生命周期 / PR评审 / Issue转PR带CI状态 / Issue管理 / 仓库管理 / PAT认证配置

## 自主智能体类（autonomous-ai-agents/）

### claude-code / codex / opencode
- 外部 CLI 编码 agent 委派（特性/PR）

### computer-use
- 后台桌面操控不抢焦点

### hermes-agent
- Hermes 自身配置/主题/扩展/编排；文档 https://hermes-agent.nousresearch.com/docs 为准

### merge-reconciler
- agent 合并冲突的第三方仲裁

## 创意类（creative/）——按需加载
ascii-art(字符画) · ascii-video · architecture-diagram(SVG架构图HTML) · baoyu-infographic(21布局×21风格信息图) · claude-design(一次性HTML设计) · comfyui(扩散模型生图生视频) · design-md(Google DESIGN.md令牌) · excalidraw(手绘图表JSON) · humanizer(去AI味) · manim-video(数学动画) · p5js(创意编程/着色器) · popular-web-designs(54个真实设计系统HTML) · pretext(DOM-free文字排版demo) · sketch(2-3方案HTML mockup) · songwriting-and-ai-music(作曲+Suno提示词) · touchdesigner-mcp(TouchDesigner控制)

## 效率类（productivity/）
airtable · box(云文件) · document-to-action-items · docx(Word) · google-workspace(Gmail/Calendar/Drive/Docs/Sheets via gws CLI) · maps(OSM地理) · meeting-action-items · nano-pdf(PDF自然语言编辑) · notion · ocr-and-documents(pymupdf/marker) · pdf · powerpoint · product-price-monitor(价格监控) · session-librarian(会话整理) · teams-meeting-pipeline · weekly-review-planning · xlsx(Excel)

## 研究类（research/）
arxiv · blocked-page-recovery(WAF绕过) · blogwatcher(RSS监控) · competitor-news-monitor · grounded-citations(引用落地) · llm-wiki(Karpathy LLM wiki)

## 社媒/媒体/邮件/智能家居/其他
xurl(X/Twitter CLI) · gif-search(Tenor) · youtube-content(字幕转博客) · songsee(音频频谱) · himalaya(IMAP/SMTP终端) · email-inbox-triage · openhue(飞利浦灯) · dsh-plugin-engineering(**DSH插件编写官方规范**——湛箴工作流插件的规范来源) · hermes-github-org(Ya-MiC仓库七分支整理)

## MLOps 类
huggingface-hub(hf CLI) · llama-cpp(本地GGUF) · serving-llms-vllm(vLLM部署) · evaluating-llms-harness(lm-eval基准) · weights-and-biases(实验跟踪)

## 使用约定（配合 zhanzhen-delivery 协作铁律）
1. 干活前 skill_view 加载对应技能，宁多勿漏
2. 发现技能过时立即 skill_manage(patch)
3. 本注册表如有新增技能需手动同步到 zhanzhen-handover 仓库

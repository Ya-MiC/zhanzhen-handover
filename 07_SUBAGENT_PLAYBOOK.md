# 07 · 子 agent 协同方法（SUBAGENT_PLAYBOOK）

> 本轮湛箴开发共动用 16+ 个 ox-alpha 子 agent。这是完整方法论。

## 派发模式

```
大需求 ──拆解──► N 个互不依赖的子任务 ──并行派发──► 各自直推 GitHub
                                                      │
统一回归 ◄──拉取全仓跑测试◄──各 agent 自报 commit sha◄──┘
```

## 任务卡模板（每个子任务的 context 必含）

1. **token 获取方式**：读 /opt/data/workspace/.gh_env
2. **精确 API 模式**：PUT contents 改文件必须带 sha；Git Data API 批量推
3. **可复用资产指引**：指明现有代码哪些函数直接用
4. **硬约束**：懒加载可选依赖/错误信封格式/中文注释风格
5. **验证义务**：py_compile + unittest 绿才算完成
6. **output_schema**：强制结构化交货（commit_sha/files/test_result）

## 验收流程（parent 做）

1. 逐个 agent 的 json 交货核对 commit 是否真在 GitHub
2. **不信 agent 自报**：重新 git pull + 本地 unittest 全量回归
3. 失败项分析根因 → 重派时把坑写进新任务卡的 context

## 超时与卡死处理

- max_iterations 耗尽 = 交货可能不完整 → 先核对仓库实际状态再决定重派范围
- 连续超时的任务 → parent 亲自手写（如本轮 report_engine/UI 两版）
- steer 指令在下一个工具边界才被看到，急活直接 stop+重派

## 实战战绩

- 第一轮 4 agent：2成2超时 → 补位 3 agent：2成1超时 → parent 手写收尾
- 第二轮 5 agent：3成2超时 → 补位 3 agent：全部完成
- 经验：TS/Android 构建类任务超时率高，纯 Python+REST 任务成功率高

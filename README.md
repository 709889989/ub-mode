# ub-mode

`ub-mode` 是一个 agent 技能，在编写或修改代码时强制执行规范的软件工程原则。它粗略源自 [@poteto](https://github.com/poteto) 的部分规则（poteto-mode / pstack），经精简后与确定性的质量门禁工具搭配使用：

1. **先让它跑起来（First Make it Work）** — 懒惰法则、基础思考、TDD、从第一性原理重新设计、攻击前提、先减后加、面向结果的执行、打造杠杆，以及架构（为领域建模、边界纪律、类型系统纪律、让操作幂等、共享状态先分离再串行化）。
2. **再把它做对（Then Make it Right）** — 修复根因、把工作拆成可验证的单元、测试行为而非实现、[Crapper](https://github.com/unclebob/crapper)（`CRAP < 10`）、[Dryer](https://github.com/unclebob/dryer)（重复度 `< 0.8`）、[Mutator](https://github.com/unclebob/mutator)（覆盖未覆盖的代码、消灭幸存的变异体、删除死代码），以及重构。
3. **实践（Practice）** — 记日志、守护上下文窗口、清理工作树，以及小而有序地提交并推送。

## 配套工具仓库

`ub-mode` 依靠确定性的质量门禁工具来约束结构、复杂度、重复度和测试的彻底程度：

- [unclebob/crapper](https://github.com/unclebob/crapper) — 计算每个函数的圈复杂度、测试覆盖率和 CRAP 分数，确保每个函数都保持在 CRAP 阈值（`< 10`）以下。
- [unclebob/dryer](https://github.com/unclebob/dryer) — 检测结构性代码重复，从而消除相似度达到（`>= 0.8`）的重复代码块。
- [unclebob/mutator](https://github.com/unclebob/mutator) — 运行变异测试，暴露未被覆盖的代码以及测试未能杀死的幸存变异体。
- [unclebob/uml-viewer](https://github.com/unclebob/uml-viewer) — 可视化组件、覆盖率、CRAP、变异得分和依赖方向。

## 安装

将 `SKILL.md` 复制到你所用 agent 的 skills 目录下，命名为 `ub-mode/SKILL.md`（例如 `~/.grok/skills/ub-mode/SKILL.md`、`~/.claude/skills/ub-mode/SKILL.md` 或 `~/.cursor/skills/ub-mode/SKILL.md`），然后调用 `/ub-mode`。

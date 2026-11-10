# Climbings

代码分支为 `main`，Factory 看板位于独立的 `factory_board` 分支。

## Factory

看板配置保存在 `factory_board` 分支的 `.factory/factory.toml`：

- 目标分支：`main`。
- 所有者署名：`davy`、`divisey`。
- 条目前缀：`FT`；时区：`Asia/Shanghai`。
- 构建和审查由所有者手动发起，最多构建 3 轮。
- 所有者明确发起 `ship` 后，合并、打标签并推送通过审查的条目。

安装的 Factory skill 位于 `.agents/skills/factory/`。在 Codex 中使用
`$factory`，指定 `build`、`review` 或 `ship`，仓库为 `divisey/climbings`。

编辑看板时，可以创建一个本地工作树：

```sh
git worktree add .factory-board factory_board
```

将需求写入 `.factory-board/.factory/new/<slug>.md`；尚未明确的想法放入
`backlog/`。需求文件包含标题和所有者署名，例如：

```markdown
# 需求标题

## davy · YYYY-MM-DD HH:MM
需求说明和验收标准。
```

时间使用 `Asia/Shanghai`。保存后，在看板工作树提交并推送 `factory_board`，
再发起构建。条目会按 `new → review → ready → done` 流转。

目前仓库只有初始化文件，尚无业务测试。Factory 暂用
`git show --format= --check HEAD` 检查提交格式；引入业务代码时，应将看板配置中的
`test` 更新为项目实际的测试命令。

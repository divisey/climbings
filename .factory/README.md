# Factory 看板

这是 `divisey/climbings` 的独立看板分支；代码分支为 `main`。
配置保存在 `factory.toml`，条目使用 `FT` 前缀，时间使用 `Asia/Shanghai`。
所有者可以使用 `davy` 或 `divisey` 署名。

| 目录 | 用途 |
| --- | --- |
| `backlog/` | 尚未明确的想法 |
| `new/` | 等待构建的需求 |
| `review/` | 等待审查的实现 |
| `ready/` | 审查通过，等待所有者发起 ship |
| `done/` | 已合并的条目 |
| `stop/` | 所有者暂停的条目 |

在 `new/<slug>.md` 或 `backlog/<slug>.md` 添加需求：

```markdown
# 需求标题

## davy · YYYY-MM-DD HH:MM
需求说明和验收标准。
```

署名中的时间应填写实际时间。提交并推送看板后，在代码仓库调用
`$factory`，指定仓库 `divisey/climbings` 和 `build`、`review` 或 `ship`。
看板历史独立于代码历史，不能合并到 `main`。

目前没有业务代码，`test` 暂为提交格式检查。引入业务代码后需要设置实际测试命令。

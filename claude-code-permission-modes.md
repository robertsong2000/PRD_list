# Claude Code 权限模式对比

## `--permission-mode auto`

- **仍有安全检查**：后台自动判断，可疑操作仍会拦截
- **适用场景**：日常开发，减少提示疲劳
- **风险**：低，保留了安全防护
- **账户要求**：可能需要 Max/Team/Enterprise

## `--allow-dangerously-skip-permissions`

- **完全跳过所有权限检查**，所有操作自动放行
- **无任何安全防护**：包括删除文件、执行危险命令等都不会拦截
- **适用场景**：CI/CD、自动化脚本、隔离环境
- **风险**：高，名字里就带了 "dangerously"
- **账户要求**：无限制，任何账户都能用

## 一句话总结

| | `auto` | `--allow-dangerously-skip-permissions` |
|---|---|---|
| 安全检查 | 保留 | 完全关闭 |
| 危险命令拦截 | 有 | 无 |
| 日常使用 | 推荐 | 不推荐 |
| 适合环境 | 正常开发 | Docker/CI 等隔离环境 |

**日常开发用 `--permission-mode auto`，Docker 或 CI 里才用 `--allow-dangerously-skip-permissions`。**

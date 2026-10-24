# 目录导航

[返回首页](../README.md) · [工具清单](tools.md)

| 路径 | 职责 | 维护方式 |
| --- | --- | --- |
| [src/index.ts](../src/index.ts) | MCP 服务、资料索引和工具注册 | 修改后运行 `npm run build` |
| `dist/` | TypeScript 构建产物 | 通过构建生成，Git 忽略 |
| [skills/](../skills/) | Skill 元数据和项目源码快照 | 每个目录以 `SKILL.md` 为入口，按需附带 `source.txt` |
| [agents/](../agents/) | 按类别存放的 Agent 定义 | Markdown 与 YAML frontmatter |
| [subagents/](../subagents/) | 聚焦单项工作的子 Agent 定义 | 按现有类别添加 |
| [plugins/](../plugins/) | 资料、参考和工作流组件定义 | 通过 `list_plugins` / `read_plugin` 浏览 |
| [prompts/](../prompts/) | 提示词模板 | 通过 `list_prompts` / `read_prompt` 浏览 |
| [docs/](.) | 安装之外的导航和工具参考 | 与源码和目录同步维护 |
| [package.json](../package.json) | 依赖、构建和启动命令 | 依赖变更时同步 `package-lock.json` |
| [.github/workflows/](../.github/workflows/) | 上游 CodeQL 工作流 | 按 GitHub Actions 配置维护 |
| [CONTRIBUTING.md](../CONTRIBUTING.md) | 新增资料和开发约定 | 复用现有格式 |
| [SECURITY.md](../SECURITY.md) | 上游安全说明 | 保留来源文档 |
| [LICENSE](../LICENSE) | 项目许可证 | 保留作者署名 |

服务通过 `resolve(import.meta.dirname, "..")` 定位仓库根目录，并读取五个资料目录。保留这些相对路径可继续使用现有构建和客户端配置。

`node_modules/`、`dist/`、环境文件和日志由根目录 `.gitignore` 排除。原始 `source.txt` 保持原位，分页读取和源码搜索继续使用现有路径。

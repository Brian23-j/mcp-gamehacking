# mcp-gamehacking

游戏安全与逆向工程资料库，附带基于 TypeScript 的 MCP 服务。通过 stdio 接入 MCP 客户端，检索 Skills、读取项目源码快照、浏览 Agent 定义和工作流模板。

[English / Русский](README.en.md) · [目录导航](docs/repository-layout.md) · [27 个 MCP 工具](docs/tools.md) · [贡献说明](CONTRIBUTING.md)

## 内容概览

| 内容 | 当前数量 | 入口 |
| --- | ---: | --- |
| Skills | 4,160 | [skills/](skills/) |
| `ags-` 项目资料 | 3,985 | 每个 Skill 的 `SKILL.md` 与可选 `source.txt` |
| 其他 Skills | 175 | 同上 |
| Agents | 75 | [agents/](agents/) |
| Subagents | 161 | [subagents/](subagents/) |
| Plugins 定义 | 114 | [plugins/](plugins/) |
| Prompts | 148 | [prompts/](prompts/) |
| MCP 工具 | 27 | [工具清单](docs/tools.md) |

数量按本次整理时的文件与工具注册代码统计。组件目录保存 Markdown 定义；MCP 服务负责列举和读取这些定义，客户端负责使用其内容。

## 安装与运行

使用 Node.js 22 LTS 或更新版本、npm 和 Git。源码使用 `import.meta.dirname`，安装时采用支持该接口的 Node.js 版本。

```bash
git clone --depth 1 https://github.com/Brian23-j/mcp-gamehacking.git
cd mcp-gamehacking
npm ci
npm run build
```

完整已跟踪文件约 19.1 GB，主要是 `skills/*/source.txt`。预留源码、Git 对象和依赖所需磁盘空间；浅克隆仅减少历史下载量。

在客户端的 MCP 配置中加入以下内容，将路径替换为本机克隆目录的绝对路径：

```json
{
  "mcpServers": {
    "gamehacking": {
      "command": "node",
      "args": ["/absolute/path/to/mcp-gamehacking/dist/index.js"]
    }
  }
}
```

Windows 路径示例：`C:/AI/mcp-gamehacking/dist/index.js`。Cursor 使用 `.cursor/mcp.json`；Claude Desktop 使用 `claude_desktop_config.json`；其他客户端通过其 MCP 设置添加 stdio 服务。

## 开始使用

连接后，按以下顺序查看资料：

1. `skill_stats`：查看资料库统计。
2. `list_skills` 或 `search_skills`：定位 Skill。
3. `read_skill`：读取说明与元数据。
4. `read_source`：分页读取对应源码快照。
5. `list_agents`、`list_subagents`、`list_plugins`、`list_prompts`：浏览组件分类。

完整工具名称见 [docs/tools.md](docs/tools.md)。全库源码搜索会读取大量资料，可先按项目、游戏或引擎缩小检索集合。

## 开发与目录维护

```bash
npm run build
npm run inspect
```

`npm run build` 编译 TypeScript；`npm run inspect` 打开 MCP Inspector，用于检查连接和工具调用。

服务通过构建目录的上一级定位资料。保持 `src/`、`dist/`、`skills/`、`agents/`、`subagents/`、`plugins/`、`prompts/` 的相对位置；详细职责见 [目录导航](docs/repository-layout.md)。

## 来源与许可证

本仓库由 [1llu50ry/mcp-gamehacking](https://github.com/1llu50ry/mcp-gamehacking) Fork，保留上游提交历史。项目包声明 MIT，许可证原文见 [LICENSE](LICENSE)。归档项目的来源、作者与许可信息以各项目资料为准。

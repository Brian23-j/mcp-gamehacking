# MCP 工具清单

当前源码注册 **27 个工具**：19 个直接注册，8 个由组件循环注册。名称以 `src/index.ts` 为准。

| 工具 | 源码中的功能说明 |
| --- | --- |
| `research_technique` | Research a game hacking technique: finds relevant skills by scored keyword search across the indexed library. Returns consolidated briefing. |
| `analyze_project` | Deep-analyze an archived project: reads SKILL.md + source code, classifies technique, provides structured assessment. |
| `get_agent_briefing` | Load an agent definition with all available subagents and plugins listed. Returns a ready-to-use system prompt. |
| `grep_sources` | Full-text search across all 3,985 source code archives. Streams through source.txt files matching a regex pattern. Use for finding specific offsets, function names, patterns, struct definitions. |
| `find_offset` | Cross-reference a game offset, pattern, or struct name across all archived source code. Finds every project that uses a specific offset value or field name. |
| `compare_projects` | Side-by-side comparison of two cheat projects: architecture, techniques, features, detection surface. |
| `find_similar` | Find projects similar to a given one based on topic and description overlap. Great for finding alternative implementations of the same technique. |
| `extract_offsets` | Parse a project's source code and extract all hex offsets (0x...) with surrounding context. Instant offset dump from any cheat. |
| `search_by_game` | Find all skills/projects targeting a specific game. Searches name, description, topics, and games metadata. |
| `search_by_engine` | Find all skills/projects targeting a specific game engine. |
| `get_file_tree` | Parse a project's source.txt and show its file/directory tree structure (without file contents). Quick project structure overview. |
| `find_function` | Search for a function definition/declaration across all source archives. Matches C/C++ function signatures, class methods, NTSTATUS routines, etc. |
| `export_offsets` | Collect all hex offsets for a specific game across all skills and export as a C++ header. Aggregates offsets from every project targeting that game. |
| `skill_changelog` | Compare offsets between two projects targeting the same game. Shows which offsets changed, were added, or removed. Useful for tracking game updates. |
| `list_skills` | List skills with optional filtering. Uses in-memory index for fast lookup. |
| `read_skill` | Read a skill's SKILL.md content with full metadata. |
| `read_source` | Read a project's source code snapshot with pagination. |
| `search_skills` | Scored keyword search across the indexed skill library (name + description + topics + games + engines). |
| `skill_stats` | Library statistics from the in-memory index. |
| `list_agents` | List agents, optionally filtered by category. |
| `read_agent` | Read a agent definition by name. |
| `list_subagents` | List subagents, optionally filtered by category. |
| `read_subagent` | Read a subagent definition by name. |
| `list_plugins` | List plugins, optionally filtered by category. |
| `read_plugin` | Read a plugin definition by name. |
| `list_prompts` | List prompts, optionally filtered by category. |
| `read_prompt` | Read a prompt definition by name. |

通过 MCP 客户端的工具列表查看参数、默认值和输入约束。

# Agent Access

| Solution | MCP | API / SDK | CLI | Plugins / clients | Write-back | Notes |
|---|---|---|---|---|---|---|
| [Membase](../solutions/membase.md) | Built-in | Partial | Integration installer | Claude Code, OpenClaw, Hermes, Codex, Cursor, VS Code, OpenCode, ChatGPT, Claude, Gemini CLI | Built-in | Remote MCP exposes Memory tools, Wiki CRUD/search tools, profile/recent resources, and a `start` prompt. |
| [OpenHuman](../solutions/openhuman.md) | Integration | Partial | Not primary fit | OpenHuman desktop agent and agentmemory/MCP-related sharing path | Built-in inside OpenHuman | Primarily its own agent experience, not a generic memory API. |
| [GBrain](../solutions/gbrain.md) | Built-in | Integration | Built-in | Agent skills and MCP clients | Built-in | Verify actual tool calls; local and remote callers can have different trust behavior. |
| [Supermemory](../solutions/supermemory.md) | Built-in | Built-in | Not primary fit | MCP-compatible clients | Built-in | Supports OAuth and API key auth for MCP. |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | Built-in | Built-in | Integration | MCP-compatible clients and framework integrations | Built-in | Good developer primitive for app memory. |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | Partial | Built-in | Not primary fit | LangGraph/Autogen ecosystem integrations | Built-in | Best accessed as application infrastructure. |
| [Cognee](../solutions/cognee.md) | Built-in | Built-in | Integration | Cursor, Claude Desktop, Continue, Cline, Roo Code | Built-in | Standalone mode isolates data; API mode shares a backend. |
| [Khoj](../solutions/khoj.md) | Partial | Integration | Partial | Emacs, Obsidian, desktop, web | Partial | Best as a personal assistant and retrieval app. |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | Integration | Plugin-dependent | Plugin-dependent | Community plugins and bridges | Partial | Agent access quality depends on the bridge. |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | Not primary fit | Not primary fit | Not primary fit | ChatGPT platform | Built-in inside ChatGPT | Not portable to other agents by default. |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | Integration | Built-in API for developers | Built-in for Claude Code | Claude connectors and MCP | Built-in inside Claude contexts | Project knowledge is Claude-scoped unless paired with external memory. |
| [NotebookLM](../solutions/notebooklm.md) | Not primary fit | Partial for enterprise/API contexts | Not primary fit | NotebookLM/Gemini surfaces | Partial | Strong source Q&A, weak as cross-agent memory. |

## Verification Rule

Configured is not the same as used. For any setup, ask an agent a memory-dependent question and confirm that the host actually called `search`, `recall`, `query`, `search_memory`, `search_wiki`, or the equivalent tool during the task.

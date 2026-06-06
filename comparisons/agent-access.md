# Agent Activation

| Solution | MCP | API / SDK | CLI | Plugins / clients | Write-back | Notes |
|---|---|---|---|---|---|---|
| [Membase](../solutions/membase.md) | Built-in | Not primary fit | Integration installer | Claude Code, OpenClaw, Hermes, Codex, Cursor, VS Code, Poke, OpenCode, ChatGPT, Claude, Gemini CLI | Built-in | Remote MCP and plugins expose Memory tools, Wiki CRUD/search tools, profile/recent resources, and a `start` prompt; dashboard chat works without an external agent. |
| [OpenHuman](../solutions/openhuman.md) | Integration | Partial | Not primary fit | OpenHuman desktop agent and agentmemory/MCP-related sharing path | Built-in inside OpenHuman | Primarily its own agent experience, not a generic memory API. |
| [GBrain](../solutions/gbrain.md) | Built-in | Built-in | Built-in | Claude Code, Cursor/Windsurf, Claude Desktop/Cowork, ChatGPT, Perplexity, and other MCP clients | Built-in | stdio/HTTP MCP exposes 30+ operations; HTTP paths use OAuth scopes and local-only restrictions for filesystem-sensitive ops. |
| [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md) | Not primary fit | Not primary fit | Hermes runtime | Hermes bundled skill | Built-in inside Hermes | The bundled skill lets Hermes create, query, lint, and update a local Markdown wiki; portability to other agents requires copying or recreating the skill. |
| [Supermemory](../solutions/supermemory.md) | Built-in | Built-in | Not primary fit | MCP-compatible clients | Built-in | Supports OAuth and API key auth for MCP. |
| [Hyperspell](../solutions/hyperspell.md) | Built-in | Built-in | Integration | Claude Code skill/plugins, OpenClaw plugin, MCP-compatible clients, SDKs | Built-in | MCP exposes search, add/get memory, upload file, and integration management; SDK/API supports user-scoped retrieval and writes. |
| [Honcho](../solutions/honcho.md) | Built-in | Built-in | Integration | Claude Code, OpenCode, OpenClaw, Hermes, Codex, Cursor, Windsurf, VS Code, Cline, Zed, SDKs | Built-in | MCP exposes workspace, peer, session, conclusion, search, context, and dream tools; SDK/API supports application integration. |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | Built-in | Built-in | Integration | MCP-compatible clients and framework integrations | Built-in | Good developer primitive for app memory. |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | Partial | Built-in | Not primary fit | LangGraph/Autogen ecosystem integrations | Built-in | Best accessed as application infrastructure. |
| [Cognee](../solutions/cognee.md) | Built-in | Built-in SDK/API | Integration | Claude Code plugin, Cursor, Codex, Continue, Cline, Roo Code, Goose, OpenClaw plugin, Python agents | Built-in | SDK/local mode can run without Docker; standalone mode isolates data; API mode shares a backend. |
| [Khoj](../solutions/khoj.md) | Partial | Integration | Partial | Emacs, Obsidian, desktop, web | Partial | Best as a personal assistant and retrieval app. |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | Integration | Plugin-dependent | Plugin-dependent | Community plugins and bridges | Partial | AI-tool activation quality depends on the bridge. |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | Not primary fit | Not primary fit | Not primary fit | ChatGPT platform | Built-in inside ChatGPT | Not portable outside ChatGPT by default. |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | Integration | Built-in API for developers | Built-in for Claude Code | Claude connectors, MCP, IDE/desktop/web/terminal Claude Code surfaces | Built-in inside Claude contexts | Project knowledge is Claude-scoped unless paired with external memory. |
| [NotebookLM](../solutions/notebooklm.md) | Not primary fit | Partial for enterprise/API contexts | Not primary fit | NotebookLM/Gemini surfaces | Partial | Strong source Q&A, weak as a broad second-brain activation layer. |

## Verification Rule

Configured is not the same as used. For any setup, ask an AI tool a memory-dependent question and confirm that the host actually called `search`, `recall`, `query`, `search_memory`, `search_wiki`, or the equivalent tool during the task.

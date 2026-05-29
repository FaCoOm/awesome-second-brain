# Agent Access

## What This Capability Means

Agent access is how external agents search, retrieve, cite, write, update, or maintain the second brain.

## Evaluation Questions

- Is access available through MCP, API, SDK, CLI, plugins, or platform-only tools?
- Can agents write back?
- Is access scoped by user, source, project, or workspace?
- Can you verify the host agent actually used the tool?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Built-in | Remote MCP, `start` prompt, profile/recent resources, client installers, and plugins. | Verify OAuth/auth and actual `search_memory` or `search_wiki` tool calls in the host agent. |
| OpenHuman | Integration | Desktop agent first; agentmemory/MCP sharing path for related clients. | Not primarily a generic memory API. |
| GBrain | Built-in | CLI, stdio MCP, HTTP MCP. | Local and remote callers can have different trust behavior. |
| Supermemory | Built-in | MCP, OAuth/API key auth, API/SDK. | Project scoping should be explicit. |
| Mem0/OpenMemory | Built-in | MCP, API, SDK. | App must define scope and governance. |
| Zep/Graphiti | API + SDK | Application integration. | Not primarily end-user MCP setup. |
| Cognee | Built-in | MCP in standalone or API mode. | Mode choice affects sharing. |
| Khoj | Partial | Clients and app integrations. | Verify current API/bridge before calling it portable agent memory. |
| Obsidian/Logseq + AI bridge | Integration | Plugin, MCP bridge, or filesystem tool. | Write-back should be reviewed. |

## Sources

- [Membase MCP](https://docs.membase.so/features/membase-mcp)
- [Supermemory MCP](https://supermemory.ai/mcp/)
- [Mem0 MCP](https://docs.mem0.ai/platform/mem0-mcp)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)

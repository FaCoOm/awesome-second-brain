# Setup / Operations

## What This Capability Means

Setup and operations cover first install, authentication, source sync, indexing, retries, background jobs, verification, upgrades, and ongoing maintenance.

## Evaluation Questions

- How long until first useful memory?
- Which runtime and accounts are required?
- Who operates storage, embeddings, MCP servers, and collectors?
- How do users know the setup is actually working?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Built-in | Account + agent connection. | Fastest path, hosted tradeoff. |
| OpenHuman | Built-in + Integration | Native desktop install, onboarding, app connections, provider choices. | Early beta; connector setup can expand scope. |
| GBrain | Custom collector | CLI, brain repo, sync/embed/dream jobs, MCP. | Most operations-heavy core option. |
| Supermemory | Built-in + Integration | MCP/API and connectors. | Connector health and project scoping matter. |
| Mem0/OpenMemory | Integration | Hosted MCP/API or self-hosted stack. | Memory design is application work. |
| Zep/Graphiti | API | App integration and graph ingestion. | Builder-focused. |
| Cognee | Built-in | Docker/local/API mode and MCP config. | Choose mode carefully. |
| Khoj | Built-in | Cloud or self-host plus sources. | Source freshness needs verification. |
| Obsidian/Logseq + AI bridge | Integration | Notes app plus plugin/import/MCP bridge. | Strong ownership, more setup choices. |

## Sources

- [Membase quickstart](https://docs.membase.so/getting-started/quickstart)
- [Supermemory MCP setup](https://supermemory.ai/docs/supermemory-mcp/setup)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)

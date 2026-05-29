# Setup Burden

## Low Burden

| Solution | What you do | What you do not operate |
|---|---|---|
| [Membase](../solutions/membase.md) | Create an account, connect an agent, authenticate, optionally import chat history, Gmail/Google Calendar/Slack, or Wiki material. | Storage, indexing, MCP server hosting, and cross-agent sharing. |
| [OpenHuman](../solutions/openhuman.md) | Install desktop app, onboard, connect selected apps, choose managed or custom providers. | Local memory plumbing and default integration orchestration. |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | Turn memory settings on or off and manage saved memories. | External connectors, MCP, vector DBs, or custom collectors. |
| [NotebookLM](../solutions/notebooklm.md) | Create a notebook and add sources. | Indexing infrastructure or custom retrieval code. |

## Medium Burden

| Solution | What you operate | Main risk |
|---|---|---|
| [Supermemory](../solutions/supermemory.md) | MCP/API auth, optional project scoping, connectors, API usage. | Connector status, project boundaries, and source deletion semantics. |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | API keys, SDK integration, hosted or self-hosted stack. | Memory scope design, governance, and retrieval tuning. |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | App integration, user/session/group model, graph ingestion. | Requires product engineering rather than end-user setup. |
| [Cognee](../solutions/cognee.md) | Docker/local/API mode, MCP client config, graph processing. | Separate standalone instances vs shared API mode can fragment memory. |
| [Khoj](../solutions/khoj.md) | Cloud or self-host install, source configuration, indexing. | Self-hosting and source freshness need active management. |

## High Burden

| Solution | What you operate | Main risk |
|---|---|---|
| [GBrain](../solutions/gbrain.md) | Local CLI, brain repo, sync, embeddings, dream/autopilot, collectors, MCP server. | Connector health is not the same as curated knowledge quality. |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | Vault hygiene, plugins or bridges, local model/API choices, sync and backups. | Strong ownership, but AI behavior depends on the bridge you build. |

## Practical Rule

Start with the lowest setup burden that satisfies your privacy and portability needs. Move to a local/self-hosted stack only when you have a real reason to own storage, indexing, or graph construction.

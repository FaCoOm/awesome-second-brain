# Dreaming / Consolidation

## What This Capability Means

Dreaming or consolidation is the periodic work that keeps memory useful after capture: summarization, deduplication, fact repair, stale embedding repair, source cleanup, pruning, or reflective synthesis.

## Evaluation Questions

- Is there a named maintenance loop?
- Is it product-managed, user-operated, or custom?
- Does it repair retrieval quality or only summarize?
- Can users inspect proposed changes before they become durable memory?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Built-in | Smart digesting and managed product updates. | Schedule/internal mechanics are product-managed. |
| OpenHuman | Partial | Auto-fetch every 20 minutes, memory collapse, background thinking. | Not yet verified as a durable curated-knowledge loop. |
| GBrain | Built-in | `gbrain dream`, `gbrain autopilot`, sync/embed jobs. | User operates jobs and verifies quality. |
| Supermemory | Partial | Managed processing and sync pipeline. | Not primarily framed as a user-operated dream loop. |
| Mem0/OpenMemory | Partial | Memory promotion/search behavior and platform processing. | Explicit consolidation policy is app-owned. |
| Zep/Graphiti | Built-in | Temporal graph updates, facts, summaries. | Application must ingest updates correctly. |
| Cognee | Built-in | `improve` and graph processing workflows. | Terminology differs from dreaming. |
| Khoj | Partial | Indexing and assistant workflows. | No central dream loop in this repo's current evaluation. |
| Obsidian/Logseq + AI bridge | Custom collector | Nightly scripts, plugins, or external memory services. | User owns review and write-back safety. |

## Sources

- [Membase overview](https://docs.membase.so/)
- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)

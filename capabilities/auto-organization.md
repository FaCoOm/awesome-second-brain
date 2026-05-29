# Auto Organization

## What This Capability Means

Auto organization is the system's ability to turn raw context into durable knowledge: summaries, entities, links, tags, schemas, graph edges, facts, timelines, or wiki pages.

## Evaluation Questions

- Does organization happen automatically or through explicit review?
- Are relationships deterministic, semantic, or LLM-inferred?
- Can users inspect and correct the result?
- Does the system separate raw data from curated knowledge?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Built-in | Memory graph extraction plus linked Wiki documents. | Retrieval also uses vector search; internal product behavior is managed by Membase. |
| OpenHuman | Built-in | Memory Tree, semantic search, Markdown vault, token compression, collapse flows. | Exact consolidation quality should be tested. |
| GBrain | Built-in | Schema packs, page type inference, link/timeline/fact extraction. | Quality improves with structured Markdown and review. |
| Supermemory | Built-in | Processing pipeline, memory graph, metadata/filtering. | Exact graph semantics should be verified per use case. |
| Mem0/OpenMemory | Built-in | Layered memory types and search/promotion model. | App must choose scope and metadata carefully. |
| Zep/Graphiti | Built-in | Entity nodes, entity edges, episodic nodes, facts, summaries. | Strong for temporal graph apps, not no-code PKM. |
| Cognee | Built-in | Knowledge graph memory tools and processing. | Graph quality depends on ingestion and processing. |
| Khoj | Built-in | Indexing/search over personal files and notes. | Less schema-heavy than graph memory systems. |
| Obsidian/Logseq + AI bridge | Partial | Tags, links, properties, blocks, and plugins. | AI organization is bridge-dependent. |

## Sources

- [Membase overview](https://docs.membase.so/)
- [Membase OpenClaw connector](https://docs.membase.so/connectors/openclaw)
- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)

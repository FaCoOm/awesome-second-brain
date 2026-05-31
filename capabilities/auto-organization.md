# Knowledge Organization

## What This Capability Means

Knowledge organization is the system's ability to turn raw context into durable, reusable knowledge: summaries, entities, links, tags, schemas, graph edges, facts, timelines, or wiki pages.

## Evaluation Questions

- Does organization happen automatically or through explicit review?
- Are relationships deterministic, semantic, or LLM-inferred?
- Can users inspect and correct the result?
- Does the system separate raw data from curated knowledge?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Built-in | Memory graph extraction plus linked Wiki documents and collections. | Memory retrieval also uses vector search; internal product behavior is managed by Membase. |
| OpenHuman | Built-in | Memory Tree, local SQLite knowledge base, Markdown vault, token compression, hierarchical summary trees, collapse flows. | Exact consolidation quality should be tested. |
| GBrain | Built-in | Schema packs, `gbrain-base-v2`, schema detect/suggest/review flows, page type inference, auto-linking, timeline/fact extraction, and takes. | Quality improves with structured Markdown, active schema selection, and review. |
| Supermemory | Built-in | Processing pipeline, fact-based graph memory, relationship tracking, metadata/filtering. | Exact graph semantics should be verified per use case. |
| Mem0/OpenMemory | Built-in | Layered memory types and search/promotion model. | App must choose scope and metadata carefully. |
| Zep/Graphiti | Built-in | Entity nodes, entity edges, episodic nodes, facts, summaries. | Strong for temporal graph apps, not no-code PKM. |
| Cognee | Built-in | Knowledge graph memory tools and processing. | Graph quality depends on ingestion and processing. |
| Khoj | Built-in | Indexing/search over personal files and notes. | Less schema-heavy than graph memory systems. |
| Obsidian/Logseq + AI bridge | Partial | Tags, links, properties, blocks, and plugins. | AI organization is bridge-dependent. |
| ChatGPT Memory | Built-in | Platform-managed saved memories and chat history reference. | Organization is not developer-operable. |
| Claude Projects/Claude Code | Built-in | Project knowledge, instructions, and platform RAG behavior. | Structure is scoped to Claude project contexts. |
| NotebookLM | Built-in | Source summaries, labels/categories when enough sources exist, and generated artifacts. | Strong for bounded notebooks, not a live memory graph. |

## Sources

- [Membase overview](https://docs.membase.so/)
- [How Membase works](https://docs.membase.so/core-concepts/how-membase-works)
- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)

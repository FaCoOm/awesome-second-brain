# Capability Matrix

Labels: `Built-in`, `Integration`, `Custom collector`, `Partial`, `Not primary fit`, `Unknown`.

| Solution | Deployment | Data capture | Auto-organization | Consolidation / dreaming | Retrieval model | Agent access | Workspace / team | UI / filtering | Setup burden | Setup time |
|---|---|---|---|---|---|---|---|---|---|---|
| [Membase](../solutions/membase.md) | Hosted | Built-in + Integration | Built-in | Built-in | Graph + vector hybrid RAG for Memory; hybrid Wiki search | MCP + plugins | Built-in | Built-in | Low | Official: under 5 min |
| [OpenHuman](../solutions/openhuman.md) | Desktop local + managed services | Built-in + Integration | Built-in | Partial | Local Memory Tree + semantic search | Built-in agent + MCP/agentmemory path | Not primary fit | Built-in | Low-medium | Official: minutes |
| [GBrain](../solutions/gbrain.md) | Local/self-hosted | Built-in + Custom collector | Built-in | Built-in | Keyword + vector/hybrid + graph signals | CLI + MCP | Integration | Partial | Medium-high | Hands-on: 30 min+ |
| [Supermemory](../solutions/supermemory.md) | Hosted + API | Built-in + Integration | Built-in | Partial | Memory API + RAG + memory graph | MCP + API + SDK | Integration | Built-in | Low-medium | Official: minutes |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | Hosted/self-hosted | API + Integration | Built-in | Partial | Layered memory search | MCP + API + SDK | Built-in | Built-in | Medium | Official: minutes |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | Hosted + OSS graph library | API | Built-in | Built-in | Temporal knowledge graph + Graph RAG | API + SDK | Built-in | Partial | Medium | Maintainer estimate: 30-60 min |
| [Cognee](../solutions/cognee.md) | Local/API mode | Built-in + API | Built-in | Built-in | Knowledge graph memory | MCP + API | Built-in in API mode | Partial | Medium | Official: minutes with Docker |
| [Khoj](../solutions/khoj.md) | Cloud/self-hosted | Built-in | Built-in | Partial | Search over personal files and notes | App + clients | Partial | Built-in | Medium | Official: minutes |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | Local-first | Built-in notes + Integration | Partial | Custom collector | Local search/graph + plugin RAG | Plugin/MCP bridge | Partial | Built-in | Medium-high | Hands-on: 30-90 min |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | Hosted platform | Built-in | Built-in | Built-in | Platform memory + chat history reference | Platform only | Partial | Built-in | Low | Official: instant |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | Hosted platform + local agent | Built-in | Built-in | Built-in RAG for projects | Project knowledge search | Platform + MCP connectors | Built-in on team plans | Built-in | Low-medium | Official: minutes |
| [NotebookLM](../solutions/notebooklm.md) | Hosted platform | Built-in | Built-in | Partial | Source-grounded notebook retrieval | Platform only | Partial | Built-in | Low | Official: minutes |

## Reading Notes

- `Built-in` does not always mean automatic quality. Imported data may still need review, schema cleanup, source labels, or deletion policies.
- `Integration` means a documented connector, plugin, SDK, or supported bridge exists.
- `Custom collector` means the workflow is feasible but the user must own source-specific code, OAuth, rate limits, retries, and normalization.
- `Not primary fit` should be used when a product can be forced into a workflow but is not designed for it.

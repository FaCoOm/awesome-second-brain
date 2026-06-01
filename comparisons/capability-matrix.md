# Capability Matrix

Labels: `Built-in`, `Built-in but operational`, `Integration`, `Custom collector`, `Partial`, `Not primary fit`, `Unknown`.

| Solution | Context capture | Knowledge organization | Memory evolution | Retrieval / use | Feedback / correction | Personal / team scope | Privacy / control | Agent activation | Setup / operations | Setup time |
|---|---|---|---|---|---|---|---|---|---|---|
| [Membase](../solutions/membase.md) | Built-in + Integration | Built-in Memory + Wiki | Built-in | Graph + vector hybrid RAG for Memory; vector + keyword hybrid Wiki search; dashboard chat | Built-in dashboard controls | Partial: project/collection scoping; team/workspace separation coming soon | Hosted controls | MCP + plugins + dashboard chat | Low | Official: under 5 min |
| [OpenHuman](../solutions/openhuman.md) | Built-in + Integration | Built-in Memory Tree + Markdown vault | Partial | Local Memory Tree + vault + memory graph | Built-in desktop surfaces | Not primary fit | Local memory + managed services | Built-in assistant + MCP/agentmemory path | Low-medium | Official: minutes |
| [GBrain](../solutions/gbrain.md) | Built-in + Custom collector | Built-in pages/graph/timeline/schema | Built-in | Cheap hybrid search + expanded query + `think` synthesis | Partial operations/admin UI | Built-in but operational | Local/self-hosted control | CLI + MCP | Medium-high | Official: ~30 min personal |
| [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md) | Built-in | Built-in Markdown wiki/schema/index/log | Partial | Wiki orientation + file search + page synthesis | Built-in Markdown review + lint workflow | Partial | Local/server-owned files | Hermes bundled skill | Medium | Official quickstart; hands-on varies |
| [Supermemory](../solutions/supermemory.md) | Built-in + Integration | Built-in graph memory | Built-in | Memory API + hybrid search + graph memory | Built-in hosted app/console | Integration | Hosted controls | MCP + API + SDK | Low-medium | Official: minutes |
| [Hyperspell](../solutions/hyperspell.md) | Built-in + Integration | Built-in context graph + metadata | Built-in + procedural memory | Indexed/live search + optional answers | API review flows + app-owned UI | Built-in user model | Hosted controls | MCP + API + SDK + plugins | Low-medium | Official: under 5 min claim; beta varies |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | API + Integration | Built-in memory scopes | Partial | Layered memory search | Built-in dashboard/server paths | Built-in | Hosted or self-hosted | MCP + API + SDK | Medium | Official: minutes |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | API | Built-in temporal graph | Built-in | Temporal knowledge graph + Graph RAG | Partial developer UI/APIs | Built-in | Hosted or OSS library path | API + SDK | Medium | Official quickstart; hands-on varies |
| [Cognee](../solutions/cognee.md) | Built-in + API | Built-in knowledge graph | Built-in | Knowledge graph memory | Partial developer/admin surfaces | Built-in in API mode | Local mode or shared API mode | MCP + API | Medium | Official: minutes with Docker |
| [Khoj](../solutions/khoj.md) | Built-in | Built-in indexing/search | Partial | Search over personal files and notes | Built-in app/client UI | Partial | Cloud or self-hosted | App + clients | Medium | Official: minutes |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | Built-in notes + Integration | Partial human/PKM structure | Custom collector | Local search/graph + plugin RAG | Built-in human review UI | Partial | Local vault/graph control | Plugin/MCP bridge | Medium-high | Hands-on: 30-90 min |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | Built-in + platform sources | Built-in | Built-in | Platform memory + chat history + memory sources | Built-in settings and Memory Sources | Partial | Platform controls | Platform only | Low | Official: instant |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | Built-in | Built-in project knowledge | Built-in RAG for projects | Project knowledge search | Built-in project UI | Built-in on team plans | Plan/workspace controls | Claude + connectors + Claude Code | Low-medium | Official: minutes |
| [NotebookLM](../solutions/notebooklm.md) | Built-in | Built-in source summaries and labels | Partial | Source-grounded notebook retrieval | Built-in notebook UI | Partial | Platform controls | Platform only | Low | Official: minutes |

## Reading Notes

- `Built-in` does not always mean automatic quality. Imported data may still need review, schema cleanup, source labels, or deletion policies.
- `Integration` means a documented connector, plugin, SDK, or supported bridge exists.
- `Custom collector` means the workflow is feasible but the user must own source-specific code, OAuth, rate limits, retries, and normalization.
- `Not primary fit` should be used when a product can be forced into a workflow but is not designed for it.

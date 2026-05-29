# Privacy / Control

## What This Capability Means

Privacy and control cover where memory is stored, whether users can inspect and correct it, how deletion/export works, and whether the system can be self-hosted or audited.

## Evaluation Questions

- Can users view, edit, delete, and export memories?
- Is memory local, hosted, or self-hosted?
- Are sources and provenance visible?
- Can users control what agents can write?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Partial | Hosted controls and dashboard. | Verify export, retention, and deletion requirements. |
| OpenHuman | Partial | Local Memory Tree, Markdown vault, and runtime state with managed services for default experience. | Local-first does not mean fully offline by default. |
| GBrain | Built-in | Local/self-hosted files and database. | User owns operations and backups. |
| Supermemory | Partial | Hosted app, API, connector management. | Connector deletion semantics need review. |
| Mem0/OpenMemory | Built-in | Hosted or self-hosted. | Self-hosting provides strongest control. |
| Zep/Graphiti | Partial | Hosted Zep or Graphiti library. | Verify platform retention and graph data handling. |
| Cognee | Built-in in local mode | Standalone local/Docker or API mode. | Shared API mode changes control boundary. |
| Khoj | Built-in with self-hosting | Cloud or self-hosted. | Cloud convenience changes control boundary. |
| Obsidian/Logseq + AI bridge | Built-in | Local vault/graph and backups. | Plugin permissions can expand risk. |

## Sources

- [ChatGPT Memory FAQ](https://help.openai.com/en/articles/8590148-memory-faq)
- [Mem0 open-source overview](https://docs.mem0.ai/open-source/overview)
- [Khoj docs](https://docs.khoj.dev/)

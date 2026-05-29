# Team / Workspace Boundaries

## What This Capability Means

Boundaries define who can read, write, update, delete, and share memory across personal, project, workspace, team, and organization scopes.

## Evaluation Questions

- Does the system support projects, collections, sources, users, sessions, groups, or workspaces?
- Are reads and writes scoped?
- Can teams share knowledge without exposing personal memory?
- Can admins audit or revoke access?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Built-in | Shared Memory/Wiki and connected agents. | Verify governance details for the target plan. |
| OpenHuman | Not primary fit | Personal local app and connected sources. | Team/workspace governance is not the core fit. |
| GBrain | Integration | Sources, Postgres/Supabase, OAuth clients, federated reads. | Operationally heavier than hosted products. |
| Supermemory | Integration | Project scoping and connector metadata. | Team governance should be verified. |
| Mem0/OpenMemory | Built-in | User, session, and organizational memory. | Requires careful scope design. |
| Zep/Graphiti | Built-in | Projects, users, sessions, groups. | Best as app infrastructure. |
| Cognee | Built-in in API mode | Shared backend/API mode. | Standalone mode isolates clients. |
| Khoj | Partial | Deployment and source choices. | Primarily personal. |
| Obsidian/Logseq + AI bridge | Partial | Shared vault/sync and permissions. | Team memory discipline is user-owned. |

## Sources

- [Membase attached vs universal memory](https://docs.membase.so/core-concepts/attached-vs-universal)
- [Mem0 memory types](https://docs.mem0.ai/core-concepts/memory-types)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)

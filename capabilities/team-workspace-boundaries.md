# Personal / Team Scope

## What This Capability Means

Personal and team scope defines who can read, write, update, delete, and share memory across personal, project, workspace, team, and organization contexts.

## Evaluation Questions

- Does the system support projects, collections, sources, users, sessions, groups, or workspaces?
- Are reads and writes scoped?
- Can teams share knowledge without exposing personal memory?
- Can admins audit or revoke access?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Partial | Memory project tags and Wiki collections for scoped search/filtering. | Full team/workspace separation is coming soon; verify governance details for the target plan. |
| OpenHuman | Not primary fit | Personal local app and connected sources. | Team/workspace governance is not the core fit. |
| GBrain | Built-in but operational | Brains, sources, source-scoped OAuth clients, federated reads, mounts, Postgres/Supabase, and HTTP MCP. | Directory-only scoping is convention-based; enforced team isolation needs explicit source/OAuth design. |
| Supermemory | Integration | Project scoping and connector metadata. | Team governance should be verified. |
| Mem0/OpenMemory | Built-in | User, session, and organizational memory. | Requires careful scope design. |
| Zep/Graphiti | Built-in | Projects, users, sessions, groups. | Best as app infrastructure. |
| Cognee | Built-in in API mode | Shared backend/API mode. | Standalone mode isolates clients. |
| Khoj | Partial | Deployment and source choices. | Primarily personal. |
| Obsidian/Logseq + AI bridge | Partial | Shared vault/sync and permissions. | Team memory discipline is user-owned. |
| ChatGPT Memory | Partial | Workspace/admin behavior depends on ChatGPT plan and settings. | Not designed as portable team memory. |
| Claude Projects/Claude Code | Built-in on team plans | Team/Enterprise project sharing and permissions. | Scope remains Claude project/workspace oriented. |
| NotebookLM | Partial | Sharing/collaboration depends on Google account and product tier. | Notebook boundaries are not full second-brain governance. |

## Sources

- [Membase attached vs universal memory](https://docs.membase.so/core-concepts/attached-vs-universal)
- [Mem0 memory types](https://docs.mem0.ai/core-concepts/memory-types)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)

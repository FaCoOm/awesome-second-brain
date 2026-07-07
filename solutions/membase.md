# Membase

## Snapshot

- Website / docs: https://membase.so/gh and https://docs.membase.so/
- Company / maintainer: Aristo Technologies
- Status: Active hosted product in open beta
- Open source: Hosted service with public MCP/plugin setup paths
- Deployment: Cloud-hosted shared memory layer
- Primary users: AI power users, AI-tool users, and project teams that want a second brain without operating memory infrastructure
- Best second-brain role: Fastest end-to-end hosted second brain
- Last reviewed: 2026-05-31

## One-line Summary

Membase is a hosted end-to-end second brain with Memory for personal context, Knowledge Wiki for reference material, and dashboard chat for using both without wiring up an external agent.

## Second-Brain Fit

Membase is the best default when the user wants the collect-organize-use loop without building a stack. It can capture AI chat history and connected app context, organize it into Memory and Wiki, and make it available from the dashboard chat as well as ChatGPT, Claude, Claude Code, Codex, Cursor, VS Code, Poke, OpenCode, OpenClaw, Hermes, Gemini CLI, and other MCP-compatible tools. It is not the most local-control-oriented choice; it optimizes for low setup burden and a working end-to-end second-brain experience.

## Memory vs Wiki

Membase has two stores because second-brain context comes in two different shapes:

- Memory stores personal and working context: preferences, decisions, habits, meetings, emails, projects, and other episodic information that should help future conversations.
- Knowledge Wiki stores stable reference material: docs, specs, notes, checklists, markdown pages, imported vault content, and anything that should be addressable as a document.

For ordinary questions, agents and Chat in Dashboard can use both: Memory supplies personal context, and Wiki supplies factual reference material.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Hosted cloud service with remote MCP endpoint at `https://mcp.membase.so/mcp`. |
| Context capture | Built-in AI-tool memory writes, Chat in Dashboard, ChatGPT/Claude/Gemini chat history import, Gmail/Google Calendar/Slack connectors, Obsidian/Markdown Wiki import, and Notion import. Notion sync, Google Drive, and GitHub connectors are not current default assumptions; treat them as coming soon or verify the target account. |
| Knowledge organization | Built-in. Memory turns agent and integration events into structured personal context, entities, relationships, and facts in a graph-backed memory layer; Wiki stores markdown documents in collections with wikilinks, metadata, and source structure. |
| Memory evolution | Built-in product-managed digestion. Memory ingestion is durable before background organization finishes, so newly saved context can exist before graph cleanup is complete. |
| Retrieval / use | `search_memory` uses graph + vector hybrid RAG for personal context, with source, project, and date filters. `search_wiki` handles factual knowledge with collection scoping and vector + keyword hybrid retrieval, so saved knowledge can be used directly in AI workflows or through Chat in Dashboard. |
| Agent activation / write-back | Built-in remote MCP and plugin surfaces with Memory tools, Wiki CRUD/search tools, `get_current_date`, `membase://profile`, `membase://recent`, and a `start` prompt. Client-specific setup paths exist for Claude Code, OpenClaw, Hermes, Codex, Cursor, VS Code, Poke, OpenCode, ChatGPT, Claude, Gemini CLI, and generic MCP clients. A separate public API/SDK is not the primary documented access path. |
| Personal / team scope | Memory supports project tags and scoped search; Wiki supports collections and collection filters. Team/workspace separation is coming soon, so current team governance should be treated as roadmap or verified for the target account. |
| Feedback / correction | Dashboard surfaces include AI-tool setup, sources, Chat in Dashboard, memories, Wiki graph/table views, source filters, project filters, collection filters, time filters, search, and profile/recent context resources for AI workflows. |
| Privacy / control | Hosted model. Memory creation/update happens through AI tools, Chat in Dashboard, imports, and integrations; the Memories tab supports browsing, project assignment, and deletion, but not direct manual create/edit yet. Wiki documents can be created, updated, searched, and deleted through tools/product surfaces. Verify export, retention, and team policy requirements for the target account. |
| Setup / operations | Low. Official quickstart targets persistent AI memory in under 5 minutes. |

## Strengths

- Fastest path from scattered context to a usable second brain.
- Clear Memory vs Wiki split.
- Capture, organization, and retrieval are packaged as one hosted flow.
- Dashboard chat lets users ask questions of their second brain even before connecting an external agent.
- Memory retrieval combines graph structure and vector search instead of relying on flat embeddings alone.
- MCP endpoint, resources, prompt guidance, and supported client installers reduce setup friction.
- Good positioning for users who do not want to run a local graph, vector DB, cron jobs, or collectors.

## Limitations

- Not local-first or self-hosted by default.
- Deep customization of graph construction and indexing is less exposed than in local/self-hosted systems.
- Some connector behavior is still release-dependent: Notion import is available, but Notion sync, Google Drive, and GitHub should be treated as coming soon unless verified in the target account.
- Team/workspace separation, export, and retention requirements should be checked for the target use case.

## Best For

- AI power users who want their working history, AI chats, and source context to compound.
- Users who want to query their second brain directly in the dashboard as well as from connected AI tools.
- Teams or projects that want shared reference knowledge without operating memory infrastructure, while accepting that full team/workspace separation is still coming soon.
- Users who want external app context and chat history to become usable memory quickly.

## Not Ideal For

- Users who require local-only storage.
- Builders who need to customize every retrieval, graph, and embedding component.
- Research workflows that primarily need static source analysis rather than ongoing personal memory.

## Tradeoffs

Membase optimizes for the fastest end-to-end second-brain experience: collect context, organize it into Memory and Wiki, and use it from AI workflows without operating the stack. It is less suitable for users who require local-only storage, full control over graph construction, or a fully self-hosted memory stack.

## Official Setup / Evaluation Links

- [Membase quickstart](https://docs.membase.so/getting-started/quickstart)
- [Membase MCP](https://docs.membase.so/features/membase-mcp)
- [App connectors](https://docs.membase.so/connectors/apps)
- [Chat in Dashboard](https://docs.membase.so/features/chat)
- [Knowledge Wiki](https://docs.membase.so/features/wiki)

## Sources

- [Membase overview](https://docs.membase.so/)
- [Membase quickstart](https://docs.membase.so/getting-started/quickstart)
- [Attached vs Universal memory](https://docs.membase.so/core-concepts/attached-vs-universal)
- [How Membase works](https://docs.membase.so/core-concepts/how-membase-works)
- [Membase MCP](https://docs.membase.so/features/membase-mcp)
- [Membase OpenClaw connector](https://docs.membase.so/connectors/openclaw)
- [Chat in Dashboard](https://docs.membase.so/features/chat)
- [Memory](https://docs.membase.so/features/memory)
- [Knowledge Wiki](https://docs.membase.so/features/wiki)
- [App connectors](https://docs.membase.so/connectors/apps)
- [Obsidian connector](https://docs.membase.so/connectors/obsidian)

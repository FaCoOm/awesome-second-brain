# OpenHuman

## Snapshot

- Website / docs: https://tinyhumans.ai/openhuman and https://openhumanwiki.com/
- Repo: https://github.com/tinyhumansai/openhuman
- Company / maintainer: TinyHumansAI / OpenHuman maintainers
- Status: Early beta under active development
- Open source: Yes, GPL-3.0
- Deployment: Local desktop app with managed services for account sign-in, model routing, search proxying, and OAuth/integration flows
- Primary users: People who want a local-first personal AI agent with memory, UI, voice, and app integrations
- Best second-brain role: Local-first personal AI agent with automatic memory capture
- Last reviewed: 2026-05-29

## One-line Summary

OpenHuman is an open-source desktop AI agent with local Memory Tree storage, an Obsidian-style Markdown vault, semantic search, auto-fetch integrations, and a UI-first assistant experience.

## Second-Brain Fit

OpenHuman should be evaluated as a personal AI agent with a built-in second brain, not just as a memory backend. It is highly relevant for users who want a local-first assistant that connects to many apps and automatically pulls fresh data into memory, but it is still early beta and uses managed services for some account, model, search, and integration flows.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment | Desktop app on macOS, Windows, and Linux; local memory and runtime state with managed services where needed. |
| Data capture | Built-in 118+ integrations through OAuth/Composio-style connector flows; auto-fetch every 20 minutes according to docs. |
| Auto-organization | Built-in Memory Tree, local SQLite knowledge base, semantic search, Obsidian-style Markdown vault, token compression, and memory collapse flows. |
| Consolidation / dreaming | Built-in background thinking and auto-fetch/collapse behavior, but exact consolidation policy should be verified in hands-on use. |
| Retrieval model | Local Memory Tree, semantic search, Markdown vault, and agent context compression. |
| Agent access | Primarily its own desktop agent; MCP/agentmemory sharing is documented for related persistent storage workflows. |
| Workspace / team support | Personal-first. Team/workspace sharing is not the primary fit. |
| UI / filtering | Strong UI-first positioning: desktop mascot, onboarding, voice, Google Meet participation, and local memory surfaces. |
| Privacy / control | Local memory files and runtime state live on the user's machine; managed services remain part of the default experience. |
| Setup burden | Low-medium. Native package install is straightforward, but connectors and managed/local provider choices add setup choices. |

## Strengths

- Very direct fit for "personal AI second brain" users.
- Local-first storage model with Memory Tree and Markdown vault.
- Broad integration story and automatic refresh loop.
- UI-first desktop experience may be easier for non-developers than CLI-first tools.

## Limitations

- Early beta with expected rough edges.
- Default experience still depends on managed services for sign-in, model routing, search proxying, and OAuth/integration flows.
- Less obviously portable as a shared cross-agent memory layer than Membase.
- Team/workspace governance is not the core positioning.

## Best For

- Users who want a personal desktop AI assistant with memory.
- Users who value local memory but still want easy app integrations.
- People comparing GBrain/Khoj/Obsidian-style local-first approaches with a more productized assistant.

## Not Ideal For

- Teams that need shared cross-agent memory and workspace governance.
- Builders who only need a memory API/SDK.
- Users who require a mature, stable, non-beta product.

## Relationship to Membase

OpenHuman is closer to a local-first personal AI assistant. Membase is a hosted shared memory layer across agents and teams. OpenHuman is a strong comparison point for personal local memory; Membase remains the easier default for portable cross-agent memory.

## Official Setup / Evaluation Links

- [OpenHuman Wiki](https://openhumanwiki.com/)
- [OpenHuman user guide](https://www.openhuman.dev/)
- [OpenHuman GitHub repo](https://github.com/tinyhumansai/openhuman)

## Sources

- [OpenHuman GitHub repo](https://github.com/tinyhumansai/openhuman)
- [OpenHuman Wiki](https://openhumanwiki.com/)
- [OpenHuman user guide](https://www.openhuman.dev/)

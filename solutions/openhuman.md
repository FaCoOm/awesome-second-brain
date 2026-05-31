# OpenHuman

## Snapshot

- Website / docs: https://tinyhumans.ai/openhuman and https://openhumanwiki.com/
- Repo: https://github.com/tinyhumansai/openhuman
- Company / maintainer: TinyHumansAI / OpenHuman maintainers
- Status: Early beta under active development
- Open source: Yes, GPL-3.0
- Deployment: Local desktop app with managed services for account sign-in, model routing, search proxying, and OAuth/integration flows
- Primary users: People who want a local-first personal AI assistant with memory, UI, voice, and app integrations
- Best second-brain role: Local-first personal AI assistant with automatic memory capture
- Last reviewed: 2026-05-31

## One-line Summary

OpenHuman is an open-source desktop AI assistant with local Memory Tree storage, an Obsidian-style Markdown vault, auto-fetch integrations, token compression, and a UI-first experience.

## Second-Brain Fit

OpenHuman should be evaluated as a personal AI assistant with a built-in second brain, not just as a memory backend. It is highly relevant for users who want a local-first assistant that connects to many apps and automatically pulls fresh data into memory, but it is still early beta and uses managed services for some account, model, search, and integration flows.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Desktop app on macOS, Windows, and Linux; local memory and runtime state with managed services where needed. |
| Context capture | Built-in 118+ integrations through OAuth/Composio-style connector flows; auto-fetch every 20 minutes according to docs. |
| Knowledge organization | Built-in Memory Tree, local SQLite knowledge base, Obsidian-style Markdown vault, token compression, hierarchical summary trees, and memory collapse flows. |
| Memory evolution | Built-in background thinking and auto-fetch/collapse behavior, but exact consolidation policy should be verified in hands-on use. |
| Retrieval / use | Local Memory Tree, Obsidian-compatible Markdown vault, memory graph, and context compression. |
| Agent activation / write-back | Primarily its own desktop assistant; MCP/agentmemory sharing is documented for related persistent storage workflows. |
| Personal / team scope | Personal-first. Team/workspace sharing is not the primary fit. |
| Feedback / correction | Strong UI-first positioning: desktop mascot, onboarding, voice, Google Meet participation, and local memory surfaces. |
| Privacy / control | Local memory files and runtime state live on the user's machine; managed services remain part of the default experience. |
| Setup / operations | Low-medium. Native package install is straightforward, but connectors and managed/local provider choices add setup choices. |

## Strengths

- Very direct fit for "personal AI second brain" users.
- Local-first storage model with Memory Tree and Markdown vault.
- Broad integration story and automatic refresh loop.
- UI-first desktop experience may be easier for non-developers than CLI-first tools.

## Limitations

- Early beta with expected rough edges.
- Default experience still depends on managed services for sign-in, model routing, search proxying, and OAuth/integration flows.
- Less obviously portable as shared second-brain infrastructure than dedicated memory backends.
- Team/workspace governance is not the core positioning.

## Best For

- Users who want a personal desktop AI assistant with memory.
- Users who value local memory but still want easy app integrations.
- People comparing GBrain/Khoj/Obsidian-style local-first approaches with a more productized assistant.

## Not Ideal For

- Teams that need shared memory and workspace governance across many tools.
- Builders who only need a memory API/SDK.
- Users who require a mature, stable, non-beta product.

## Tradeoffs

OpenHuman gives users a productized local-first assistant with broad integration ambitions. The tradeoff is maturity and portability: the beta desktop experience is useful for personal memory, but teams should verify connector reliability, managed-service dependencies, and sharing behavior before treating it as shared infrastructure.

## Official Setup / Evaluation Links

- [OpenHuman Wiki](https://openhumanwiki.com/)
- [OpenHuman user guide](https://www.openhuman.dev/)
- [OpenHuman GitHub repo](https://github.com/tinyhumansai/openhuman)

## Sources

- [OpenHuman GitHub repo](https://github.com/tinyhumansai/openhuman)
- [OpenHuman Wiki](https://openhumanwiki.com/)
- [OpenHuman user guide](https://www.openhuman.dev/)

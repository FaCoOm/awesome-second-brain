# Mnemosyne

## Snapshot

- Website / docs: https://docs.mnemosyne.site/
- Repo: https://github.com/mnemosyne-oss/mnemosyne
- Package: https://pypi.org/project/mnemosyne-memory/
- Company / maintainer: Mnemosyne OSS / Abdias J
- Status: Open-source Python package with MCP, SDK, and Hermes integration paths
- Open source: Yes, MIT-licensed repository
- Deployment: Local SQLite database through Python package, MCP server, Python SDK, CLI, or Hermes plugin
- Primary users: Agent operators and developers who want local-first persistent memory for MCP or Hermes workflows
- Best second-brain role: Local-first agent memory layer with MCP and Hermes integration
- Last reviewed: 2026-07-05

## One-line Summary

Mnemosyne is a local-first memory layer for AI agents that stores memories in SQLite and exposes retrieval, consolidation, graph, MCP, SDK, CLI, and Hermes plugin surfaces.

## Second-Brain Fit

Mnemosyne fits best as a developer- or operator-run memory backend for agents. It is useful when the second brain needs local storage, MCP access, Python SDK calls, Hermes lifecycle hooks, and structured memory tiers rather than a hosted dashboard or broad OAuth connector product.

It is closest to Hindsight, Mem0/OpenMemory, Honcho, and GBrain in this repo's landscape: more programmable and local-first than hosted memory products, but less ready-made than an end-to-end second-brain app with built-in connectors, wiki UI, and team governance.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local-first. Official package and docs describe one Python package, one SQLite database, MCP server mode, CLI, and a Hermes plugin path. PyPI lists `mnemosyne-memory` as MIT-licensed and Python 3.9+ compatible. |
| Context capture | API-, MCP-, CLI-, and hook-driven. Official examples include `remember`, `recall`, MCP config, Python SDK calls, and Hermes lifecycle hooks such as `pre_llm_call`, `on_session_start`, and `post_tool_call`. |
| Knowledge organization | Built-in memory architecture with working memory, episodic memory, scratchpad, memory banks, and a TripleStore for temporal knowledge graph data. |
| Memory evolution | Built-in consolidation is exposed through `sleep` / `consolidate_to_episodic` style flows; users still operate when and how consolidation runs. |
| Retrieval / use | Hybrid retrieval combines vector similarity, SQLite FTS5, and importance weighting according to official docs. MCP, CLI, SDK, and Hermes plugin surfaces can retrieve context for agents. |
| Agent activation / write-back | Built-in MCP server, Python SDK, CLI, and Hermes plugin. Official README lists Cursor, Claude Code, Codex, Windsurf, OpenWebUI, OpenClaw, Hermes Agent, MCP clients, and Python agents as integration targets. |
| Personal / team scope | Partial. Memory banks and global/session scope can separate contexts, but team permissions and review workflows are not a full product layer. |
| Feedback / correction | Partial developer/operator tools exist: update, forget, invalidate, validate, export, import, diagnose, and scratchpad tools are documented for the Hermes plugin surface. |
| Privacy / control | Strong local storage posture: SQLite data defaults under `~/.hermes/mnemosyne/data` for Hermes workflows. Embedding and LLM behavior can still depend on configured providers and environment variables. |
| Setup / operations | Medium. Quickstart is a package install and MCP/SDK config, but production value depends on choosing embedding settings, memory scope, consolidation cadence, and agent integration behavior. |

## Strengths

- Local SQLite storage with no required managed service.
- MCP server, Python SDK, CLI, and Hermes plugin paths are documented.
- Hermes integration implements a memory provider/plugin flow and lifecycle hooks.
- Built-in tiers separate hot working memory, episodic memory, scratchpad, and graph-style triples.
- Memory banks and global/session scope give developers some isolation primitives.
- Official docs describe multilingual embedding model configuration for non-English recall.

## Limitations

- It is a memory backend, not a full consumer second-brain application.
- Broad app connectors, hosted dashboard UX, team permissions, and source governance are not the main product surface.
- Official benchmark claims are vendor-authored and should not be treated as independent evaluation evidence without hands-on reproduction.
- The README says Hermes Agent support is native, while Hermes-side provider availability should still be verified in the target Hermes installation.
- Retrieval and consolidation quality depend on embedding model, configuration, memory scope design, and agent behavior.

## Best For

- Hermes users who want a local memory provider with automatic context injection and memory tools.
- Coding-agent users who want MCP-accessible local memory for Codex, Claude Code, Cursor, or similar clients.
- Developers who want a Python SDK for agent memory without operating a hosted memory service.
- Users who prefer local SQLite ownership over a managed memory platform.

## Not Ideal For

- Users who want a hosted dashboard, built-in OAuth connectors, and low-burden setup.
- Teams that need workspace permissions, admin controls, and governance UI out of the box.
- Source-grounded research workflows where a bounded notebook or wiki is enough.
- Non-technical users who do not want to configure MCP, embeddings, or agent hooks.

## Tradeoffs

Mnemosyne gives strong local control and multiple agent activation paths, but it shifts integration and operating decisions to the user. It should be compared with Hindsight, Mem0/OpenMemory, Honcho, GBrain, and Cognee when the primary need is local or programmable agent memory rather than a complete hosted second-brain product.

## Official Setup / Evaluation Links

- Documentation: https://docs.mnemosyne.site/
- Repository: https://github.com/mnemosyne-oss/mnemosyne
- PyPI package: https://pypi.org/project/mnemosyne-memory/
- Hermes integration: https://github.com/mnemosyne-oss/mnemosyne/blob/main/docs/hermes-integration.md
- Configuration: https://github.com/mnemosyne-oss/mnemosyne/blob/main/docs/configuration.md
- Integrations: https://github.com/mnemosyne-oss/mnemosyne/tree/main/docs/integrations

## Sources

- https://docs.mnemosyne.site/
- https://github.com/mnemosyne-oss/mnemosyne
- https://pypi.org/project/mnemosyne-memory/
- https://github.com/mnemosyne-oss/mnemosyne/blob/main/docs/hermes-integration.md
- https://github.com/mnemosyne-oss/mnemosyne/blob/main/docs/configuration.md

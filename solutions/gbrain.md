# GBrain

## Snapshot

- Website / repo: https://github.com/garrytan/gbrain
- Company / maintainer: Garry Tan / GBrain maintainers
- Status: Active public repo
- Open source: Yes
- Deployment: Local PGLite by default; Postgres/Supabase and HTTP MCP paths for larger or team deployments
- Primary users: AI agent operators, local-first brain builders, developers wiring memory into agents
- Best second-brain role: Local or self-hosted agent brain
- Last reviewed: 2026-05-29
- Reviewed evidence: local checkout `0.41.26.0`, commit `42d99b6f`, and private 2026-05-29 dogfooding handoff notes

## One-line Summary

GBrain turns Markdown pages, captures, and agent-written knowledge into a searchable page/chunk/link/timeline/fact database with CLI, MCP, and scheduled maintenance workflows.

## Second-Brain Fit

GBrain is best understood as a brain database and operations layer for an agent-maintained second brain. It is not a polished no-code notes app or a generic vector database. It gives agents a structured local/self-hosted memory system, but external active context still needs collectors or exports.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment | Local PGLite; Postgres/Supabase and HTTP MCP for team or remote use. |
| Data capture | Built-in Markdown import, capture, file/stdin, HTTP ingest, inbox folder, file watcher, and skillpack ingestion surfaces; external SaaS sources need recipes or custom collectors. |
| Auto-organization | Built-in schema packs, page type inference, link extraction, timeline extraction, fact/take workflows, and deterministic graph signals. It is not a magic semantic classifier for arbitrary raw text. |
| Consolidation / dreaming | Built-in `gbrain dream`, `gbrain autopilot`, sync/embed jobs, and maintenance phases. |
| Retrieval model | Keyword search, RRF-style hybrid query when embeddings are configured, graph/link signals, timeline/fact retrieval, and `think` synthesis. |
| Agent access | Built-in CLI plus stdio/HTTP MCP. |
| Workspace / team support | Strong but operational: sources, separate brains, mounts/thin clients, Postgres/Supabase, OAuth clients, federated reads, and HTTP MCP. |
| UI / filtering | Operations UI exists for HTTP MCP admin, agents, request logs, jobs, calibration, and live activity. A Notion/Roam-style visual knowledge UI is not the primary surface. |
| Privacy / control | Strong local/self-hosted control with Markdown/git-backed source options. |
| Setup burden | Medium-high. Useful active-context setups require sync, embeddings, dream/autopilot, collectors, and verification. |

## Strengths

- Strong local-first and self-hosted story.
- Clear Markdown/page/chunk/link/timeline model.
- Real maintenance loop through dream/autopilot.
- CLI and MCP make it agent-operable.
- Deterministic graph behavior is easier to debug than pure semantic linking.
- Source/type/tag/date filters and source-scoped slugs make multi-source brains analyzable.

## Limitations

- External app ingestion is not one-click; collectors must own OAuth, pagination, rate limits, and normalization.
- Imported is not the same as embedded or curated.
- Slack/Gmail/Calendar quality depends on connector health and source-specific pipelines.
- Gmail and Calendar recipes are viable, but the handoff test still required custom collectors; Slack live backfill failed through a shared-token gateway and needed a direct-token collector.
- Notion export import can make Markdown searchable, but CSV/database properties and relation graphs need extra mapping.
- Useful operation requires ongoing jobs and monitoring.

## Best For

- Users who want local or self-hosted control.
- Developers comfortable with CLI, Markdown, git, MCP, embeddings, and scheduled jobs.
- Teams willing to operate Postgres/Supabase and source permissions.

## Not Ideal For

- Users who want the lowest setup burden.
- Teams that do not want to run collectors or cron jobs.
- Workflows that need polished no-code UI first.

## Relationship to Membase

GBrain represents the local/self-hosted brain pattern. Membase represents the hosted shared-memory pattern. GBrain is stronger when users want control and operability; Membase is easier when users want shared memory across agents without running the stack.

## Official Setup / Evaluation Links

- [GBrain installation guide for AI agents](https://github.com/garrytan/gbrain/blob/master/INSTALL_FOR_AGENTS.md)
- [GBrain integrations docs](https://github.com/garrytan/gbrain/blob/master/docs/integrations/README.md)
- [GBrain live sync guide](https://github.com/garrytan/gbrain/blob/master/docs/guides/live-sync.md)
- [GBrain company brain tutorial](https://github.com/garrytan/gbrain/blob/master/docs/tutorials/company-brain.md)

## Sources

- [GBrain GitHub repo](https://github.com/garrytan/gbrain)
- [GBrain installation guide for AI agents](https://github.com/garrytan/gbrain/blob/master/INSTALL_FOR_AGENTS.md)
- [GBrain integrations docs](https://github.com/garrytan/gbrain/blob/master/docs/integrations/README.md)
- [GBrain live sync guide](https://github.com/garrytan/gbrain/blob/master/docs/guides/live-sync.md)
- [GBrain company brain tutorial](https://github.com/garrytan/gbrain/blob/master/docs/tutorials/company-brain.md)
- Private 2026-05-29 dogfooding handoff notes summarized in this profile.

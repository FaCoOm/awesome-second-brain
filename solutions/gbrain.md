# GBrain

## Snapshot

- Website / repo: https://github.com/garrytan/gbrain
- Company / maintainer: Garry Tan / GBrain maintainers
- Status: Active public repo
- Open source: Yes
- Deployment: Local PGLite by default; Postgres/Supabase and stdio/HTTP MCP paths for larger, remote, or team deployments
- Primary users: Local-first brain builders, AI operators, and developers wiring memory into workflows
- Best second-brain role: Local or self-hosted brain operations layer
- Last reviewed: 2026-05-31
- Reviewed evidence: official repo checkout `0.41.38.0`, commit `248fb7a90f9ce5fe2e5d01fe486345d08834ed40`, README, `INSTALL_FOR_AGENTS.md`, and code under `src/core/operations.ts`, `src/core/search/hybrid.ts`, and `src/commands/serve-http.ts`

## One-line Summary

GBrain turns Markdown pages, captures, and AI-written knowledge into a searchable page/chunk/link/timeline/fact database with CLI, MCP, and scheduled maintenance workflows.

## Second-Brain Fit

GBrain is best understood as a brain database and operations layer for a local/self-hosted second brain. It is not a polished no-code notes app or a generic vector database. It gives AI workflows a structured memory system, but external active context still needs collectors or exports.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local PGLite for personal brains; Postgres/Supabase, stdio MCP, and HTTP MCP for larger, remote, or team use. |
| Context capture | Built-in Markdown import, `capture`, file/stdin capture, HTTP `/ingest`, inbox folder, `sync --watch` polling, and skillpack ingestion surfaces; external SaaS sources need recipes or custom collectors. |
| Knowledge organization | Built-in schema packs, the `gbrain-base-v2` taxonomy, page type inference, schema detect/suggest/review flows, link extraction, timeline extraction, fact/take workflows, and deterministic graph signals. It is not a magic semantic classifier for arbitrary raw text. |
| Memory evolution | Built-in `gbrain dream`, `gbrain autopilot`, sync/embed jobs, and maintenance phases. |
| Retrieval / use | `search` for cheap hybrid retrieval, `query` for expanded hybrid retrieval with filters, graph/link signals, timeline/fact retrieval, and `think` for cited synthesis with conflict and gap analysis. |
| Agent activation / write-back | Built-in CLI plus stdio/HTTP MCP with 30+ documented operations and HTTP OAuth scope controls. |
| Personal / team scope | Built-in but operational: brains, sources, source-scoped OAuth clients, federated reads, mounts, Postgres/Supabase, and HTTP MCP. Directory-only team scoping is convention-based unless OAuth-scoped sources are used. |
| Feedback / correction | HTTP admin surfaces cover client registration, request logs, jobs, live activity, and scoped operations. A Notion/Roam-style visual knowledge UI is not the primary surface. |
| Privacy / control | Strong local/self-hosted control with Markdown/git-backed source options. |
| Setup / operations | Medium-high. The official agent install targets about 30 minutes for a personal brain; the company-brain path adds roughly 90 minutes and requires source/OAuth/database decisions. |

## Strengths

- Strong local-first and self-hosted story.
- Clear Markdown/page/chunk/link/timeline model.
- Real maintenance loop through dream/autopilot.
- CLI and MCP make it automation-friendly.
- Deterministic graph behavior is easier to debug than pure semantic linking.
- Source/type/tag/date filters and source-scoped slugs make multi-source brains analyzable.
- `think` adds cited synthesis, conflict detection, and gap analysis on top of retrieval.
- Source-scoped OAuth and federated reads give teams a documented path when they are willing to operate it.

## Limitations

- External app ingestion is recipe/custom-collector based, not universal one-click; collectors must own OAuth, pagination, rate limits, and normalization.
- Imported is not the same as embedded or curated.
- `sync --watch` is documented as polling, not real-time filesystem streaming.
- Gmail, Calendar, X/Twitter, voice, and other integrations are recipe or skillpack paths; production quality still depends on source-specific pipelines.
- Notion/Obsidian-style migrations are stable at the Markdown import layer, but database properties, CSV exports, and relation graphs need extra mapping.
- Company-brain deployments require Postgres/Supabase and explicit source/OAuth scoping decisions; directory conventions alone are not the same as enforced isolation.
- Useful operation requires ongoing jobs and monitoring.

## Best For

- Users who want local or self-hosted control.
- Developers comfortable with CLI, Markdown, git, MCP, embeddings, and scheduled jobs.
- Teams willing to operate Postgres/Supabase and source permissions.

## Not Ideal For

- Users who want the lowest setup burden.
- Teams that do not want to run collectors or cron jobs.
- Workflows that need polished no-code UI first.

## Tradeoffs

GBrain gives users stronger local and self-hosted control, but that control comes with operational work: collectors, sync jobs, embeddings, maintenance, and verification. It is a better fit when users want to operate their own brain stack than when they want the fastest end-to-end second-brain setup.

## Official Setup / Evaluation Links

- [GBrain README](https://github.com/garrytan/gbrain/blob/master/README.md)
- [GBrain installation guide for AI agents](https://github.com/garrytan/gbrain/blob/master/INSTALL_FOR_AGENTS.md)
- [GBrain integrations docs](https://github.com/garrytan/gbrain/blob/master/docs/integrations/README.md)
- [GBrain live sync guide](https://github.com/garrytan/gbrain/blob/master/docs/guides/live-sync.md)
- [GBrain company brain tutorial](https://github.com/garrytan/gbrain/blob/master/docs/tutorials/company-brain.md)
- [GBrain MCP deployment guide](https://github.com/garrytan/gbrain/blob/master/docs/mcp/DEPLOY.md)

## Sources

- [GBrain GitHub repo](https://github.com/garrytan/gbrain)
- [GBrain README](https://github.com/garrytan/gbrain/blob/master/README.md)
- [GBrain installation guide for AI agents](https://github.com/garrytan/gbrain/blob/master/INSTALL_FOR_AGENTS.md)
- [GBrain integrations docs](https://github.com/garrytan/gbrain/blob/master/docs/integrations/README.md)
- [GBrain live sync guide](https://github.com/garrytan/gbrain/blob/master/docs/guides/live-sync.md)
- [GBrain company brain tutorial](https://github.com/garrytan/gbrain/blob/master/docs/tutorials/company-brain.md)
- [GBrain MCP deployment guide](https://github.com/garrytan/gbrain/blob/master/docs/mcp/DEPLOY.md)
- [GBrain operations code](https://github.com/garrytan/gbrain/blob/master/src/core/operations.ts)
- [GBrain hybrid search code](https://github.com/garrytan/gbrain/blob/master/src/core/search/hybrid.ts)

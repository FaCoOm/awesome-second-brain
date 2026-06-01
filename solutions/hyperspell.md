# Hyperspell

## Snapshot

- Website / docs: https://www.hyperspell.com/ and https://docs.hyperspell.com/
- Company / maintainer: Digital Workers of California, Inc.
- Status: Active hosted product and developer platform; integrations docs describe it as private beta
- Open source: Hosted platform is managed; public GitHub org includes SDKs, MCP server, plugins, and CLI-related repos
- Deployment: Hosted memory/context platform with SDKs, API, dashboard, MCP server, and connector flows
- Primary users: Developers and teams building AI agents that need user/workspace context
- Best second-brain role: Hosted company/user context layer for AI agents
- Last reviewed: 2026-06-01

## One-line Summary

Hyperspell is a hosted memory and context layer for AI agents that connects user workspace sources, indexes or live-searches data, and exposes retrieval through API, SDKs, MCP, and agent plugins.

## Second-Brain Fit

Hyperspell is strongest when a builder wants to add memory and context to an AI product or internal agent without building connector OAuth, ingestion, indexing, retrieval, reranking, and grounding infrastructure from scratch. It is closer to a developer/platform memory layer than a consumer second-brain app.

For a self-evolving second brain, Hyperspell covers the collect and use stages well through integrations, manual ingestion, file upload, metadata, multi-source search, optional grounded answers, and MCP. It also has procedural memory for extracting reusable step-by-step procedures from agent traces. Knowledge organization and governance are powerful but developer-shaped: the app owner still decides metadata, collections, source scoping, review UI, and user/team permission model.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Hosted platform with dashboard, API, SDKs, and MCP server. Public repos exist for SDKs/plugins/MCP, but the core memory platform is managed. |
| Context capture | Built-in integrations, Hyperspell Connect for user OAuth, manual memory add, bulk ingestion, file upload, web crawler, folder sync policies, and agent trace ingestion. Integration availability is private beta / account-dependent. |
| Knowledge organization | Built-in memories, connected data sources, metadata filters, collections, structured resource data, LLM-ready summaries, context graph claims, and procedural memories extracted from traces. |
| Memory evolution | Built-in updating for connected data when sources change, query/conversation reinforcement claims, and procedural memory extraction from traces; exact consolidation internals are product-managed. |
| Retrieval / use | API/SDK natural-language search, indexed search, live search, multi-source query, filters, resource scoping, source weighting, optional answer generation, and MCP search/get tools. |
| Agent activation / write-back | Built-in MCP server, SDKs, API, Claude Code skill/plugins, OpenClaw plugin repo, and tools for search, add memory, get memory, upload file, and integration management. |
| Personal / team scope | Multi-tenant user model using app user IDs or user tokens; teams can model users and scopes in their app. Workspace/team governance details should be verified for the target account. |
| Feedback / correction | List/get/update memory APIs, metadata filtering, folder manual review flow, pending/approve/reject states, query errors, webhooks, and evaluation API. End-user UI depends on the integrating app. |
| Privacy / control | Hosted controls plus user-specific tokens, source connection controls, folder skip/manual/sync policies, and deletion claims on the homepage. Retention/export/deletion requirements should be verified for the target plan. |
| Setup / operations | Low-medium. Official site claims agents can get context in under 5 minutes, but production use still requires app integration, user auth/scoping, source selection, and beta-access verification. |

## Strengths

- Strong developer API, SDK, MCP, and plugin story.
- Broad official integration surface, including Notion, Slack, Gmail, Google Calendar, Google Drive, GitHub, Linear, Jira, Dropbox, Box, and more.
- Supports both indexed and live search, which helps balance latency, freshness, and storage sensitivity.
- Procedural memory is explicitly designed to help agents reuse successful multi-step workflows.
- Folder sync policies and manual review flow give more control than simple all-or-nothing connector sync.
- Multi-tenant user model is natural for products that need per-user memory.

## Limitations

- Private beta / account-dependent availability means connector and feature claims should be verified before promising them.
- Hosted platform by default; not a local-first second brain.
- Not a polished consumer knowledge UI by itself; end-user review and workspace UX are app-owned.
- Product internals around graph construction, reinforcement, retention, and deletion are managed and should not be over-specified beyond docs.
- Teams must still design permission boundaries, metadata, collection taxonomy, and safe recall behavior.

## Best For

- Developers adding memory to AI products or internal agents.
- Teams that need user/workspace context from SaaS tools exposed through API, SDK, or MCP.
- Agent workflows that benefit from both factual memory and reusable procedural memory.
- Products that want connector ingestion without building source-specific pipelines.

## Not Ideal For

- Users who want a standalone personal second-brain app.
- Users who require local-only storage or self-hosted memory infrastructure.
- Teams that need all governance, review UI, and knowledge taxonomy handled out of the box.
- Workflows where private beta availability is unacceptable.

## Tradeoffs

Hyperspell can remove a large amount of connector, ingestion, indexing, and retrieval work for agent builders. The tradeoff is that users operate inside a hosted, developer-oriented platform and still need to design the product experience, governance, scoping, and memory hygiene around it.

## Official Setup / Evaluation Links

- [Hyperspell website](https://www.hyperspell.com/)
- [Hyperspell docs](https://docs.hyperspell.com/)
- [Core concepts](https://docs.hyperspell.com/core/concepts)
- [Manual integration](https://docs.hyperspell.com/core/integration)
- [Available integrations](https://docs.hyperspell.com/integrations/overview)
- [Hyperspell Connect](https://docs.hyperspell.com/usage/connect)
- [Folder sync](https://docs.hyperspell.com/usage/folder-sync)
- [Procedural memory](https://docs.hyperspell.com/usage/procedural-memory)
- [MCP overview](https://docs.hyperspell.com/advanced/mcp-overview)

## Sources

- [Hyperspell website](https://www.hyperspell.com/)
- [Hyperspell documentation](https://docs.hyperspell.com/)
- [Core concepts](https://docs.hyperspell.com/core/concepts)
- [Manual integration](https://docs.hyperspell.com/core/integration)
- [Available integrations](https://docs.hyperspell.com/integrations/overview)
- [Hyperspell Connect](https://docs.hyperspell.com/usage/connect)
- [Folder sync](https://docs.hyperspell.com/usage/folder-sync)
- [Procedural memory](https://docs.hyperspell.com/usage/procedural-memory)
- [MCP overview](https://docs.hyperspell.com/advanced/mcp-overview)
- [Hyperspell GitHub org](https://github.com/hyperspell)

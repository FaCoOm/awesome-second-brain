# Supermemory

## Snapshot

- Website / docs: https://supermemory.ai/
- Company / maintainer: Supermemory
- Status: Active hosted memory/context service, developer platform, and optional local-server distribution
- Open source: The public main repository is MIT-licensed and contains open components. The company also describes its local server as an open-source binary; the reviewed repository tree exposes the app/MCP/packages but not a server source/build target. Treat the runtime's source and license mapping as unclear until verified.
- Deployment: Hosted API/MCP with metered credits; a local server binary is also advertised. The pricing and product pages describe self-hosting differently, so confirm current eligibility and terms before planning around it.
- Primary users: AI power users and developers who want memory, document RAG, profiles, connectors, and agent integrations
- Best second-brain role: Agent memory/context layer with integrated document retrieval; not only episodic memory and not a human-curated wiki
- Last reviewed: 2026-10-21

## One-line Summary

Supermemory combines uploaded or connected source documents with extracted facts, evolving profiles, graph memory, hybrid search, and agent-facing APIs. Documents remain retrieval sources; extracted memories add a separate personal and entity context layer.

## Second-Brain Fit

The narrow label “agent memory” can make Supermemory sound like it stores only past conversations. Its current product materials also describe document RAG, file processing, connectors, and search over knowledge-base content. It therefore overlaps with knowledge retrieval systems as well as conversational memory.

That overlap should not be mistaken for the same architecture as Cognee or for an editable wiki. Supermemory describes source documents and derived memories as different objects; the service manages extraction and retrieval. Its APIs, profiles, MCP server, and plugins put context into agent workflows, while curated knowledge pages and cross-source editorial review remain a separate job.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Hosted API/MCP uses an account and monthly credits. The product also advertises a local server distributed as a binary with local embeddings and configurable model providers. The pricing page lists self-hosted deployments under Scale/Enterprise, so local terms need confirmation. |
| Context capture | Document and text uploads, URLs, and documented connectors such as Google Drive, Gmail, Notion, OneDrive, and GitHub; connector and plan availability can change. |
| Knowledge organization | Retains documents for retrieval and derives atomic facts, relationships, and profile context in a memory graph. It does not promise curated Markdown/wiki pages. |
| Memory evolution | Product-managed fact extraction, updates, contradiction handling, profile changes, and forgetting; the hosted service controls the processing loop. |
| Retrieval / use | Hybrid search combines relevant source documents and memory/profile context through API, MCP, and product surfaces. |
| Agent activation / write-back | Hosted MCP, REST API, SDKs, and coding-agent plugins; current product pages also document a local server base URL. |
| Personal / team scope | Namespaces, project/container tags, and team spaces are documented. They are scope controls, not a substitute for application authorization design. |
| Feedback / correction | Console and API tools expose documents and memories; inspect the current product's edit/delete and export behavior before using it as the only record. |
| Privacy / control | Hosted is the simplest route and sends data to the service. Local server is advertised for more local control; verify telemetry, model-provider calls, connector behavior, and exact local terms. |
| Setup / operations | Hosted integration is low effort. Local mode avoids operating a database but still requires local compute, backups, upgrades, and model choices. |

## Open Source, Free Tier, and Local Distribution

These are separate questions:

- The public Supermemory GitHub repository has an MIT license, and integrations such as plugins and MCP code are open. That establishes the license for code covered by that repository, not automatically every hosted component or binary.
- Supermemory's product page and README describe the local server as an open-source binary. The public repository reviewed for this profile did not contain the local server source or a build target, and the README tells users to use prebuilt binaries. Record the core runtime as “binary distributed; source/license mapping not independently verified,” rather than treating the hosted service and all runtime code as transparently source-buildable.
- The current Free hosted plan lists $5 in monthly credits. Ingestion, search, and other operations draw from the credit balance; this is a bounded free service, not unlimited free infrastructure. The vendor says coding-agent plugins are free, while their usage still consumes plan credits. Check billing/top-up settings if a hard zero-spend ceiling matters.
- The product page advertises local use, while the pricing page describes self-hosting under Scale and Enterprise. Resolve that plan/terms discrepancy before making the local binary your long-term no-subscription foundation.

## Strengths

- Combines conversational memory, user profiles, document retrieval, connectors, and agent access in one service.
- Useful for carrying context across supported AI tools without building an ingestion pipeline.
- A local server is advertised for users who want to run the API on their own machine.

## Limitations

- The hosted Free tier has a monthly credit budget; “free account” does not mean unlimited ingestion or search.
- The source, license, and commercial terms of the distributed local server are less clear in the public repository than the MIT-licensed integrations and application code.
- Service-managed memory is not the same as user-authored, inspectable wiki artifacts.
- The hosted service and local binary have different privacy, operations, plan, and source-availability properties.

## Best For

- Users who want convenient hosted memory and document RAG for agents, within a known credit limit.
- Developers who want a combined API/MCP/plugin surface for files, profiles, and conversation memory.
- An optional personal-memory service alongside a separate durable source of truth.

## Not Ideal For

- Users requiring an auditable, source-buildable local engine without first verifying the runtime distribution.
- A zero-spend workload that continuously ingests and queries a large Drive/Notion corpus.
- People who primarily need cross-source editorial synthesis into inspectable wiki pages.

## Tradeoffs

Supermemory reduces integration work by managing source ingestion, extraction, profile memory, and retrieval. The hosted path trades some cost predictability and data control for convenience. The local binary may reduce recurring service usage, but it shifts operational responsibility to the user and its licensing/source/build story should be confirmed before treating it as an open-source substitute.

## Official Setup / Evaluation Links

- [Supermemory product overview](https://supermemory.ai/product/)
- [Supermemory API and MCP](https://supermemory.ai/mcp/)
- [Supermemory local and self-hosting documentation](https://supermemory.ai/docs/self-hosting/overview)
- [Supermemory pricing and credit terms](https://supermemory.ai/pricing/)
- [Supermemory local-server changelog](https://supermemory.ai/changelog/local/)
- [Supermemory public repository and MIT license](https://github.com/supermemoryai/supermemory)

## Sources

- [Supermemory product overview](https://supermemory.ai/product/)
- [Supermemory pricing](https://supermemory.ai/pricing/)
- [Supermemory repository README](https://github.com/supermemoryai/supermemory)
- [Supermemory repository license](https://github.com/supermemoryai/supermemory/blob/main/LICENSE)
- [Supermemory local-server changelog](https://supermemory.ai/changelog/local/)
- [Supermemory MCP and API overview](https://supermemory.ai/mcp/)

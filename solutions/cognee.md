# Cognee

## Snapshot

- Website / docs: https://docs.cognee.ai/
- Company / maintainer: Cognee
- Status: Active open-source memory and knowledge-processing platform, with a separate managed Cloud option
- Open source: Apache-2.0 licensed Python project in the official repository
- Deployment: Local Python SDK; optional self-hosted API/MCP services; optional Cognee Cloud
- Primary users: Developers and AI power users who want to turn source material into structured, searchable memory for agents
- Best second-brain role: Agent memory and knowledge-processing layer; secondary graph/retrieval substrate
- Last reviewed: 2026-10-21

## One-line Summary

Cognee ingests documents, code, text, and structured data, transforms them into graph- and vector-backed memory, and exposes that memory through SDK, API, MCP, and agent integrations.

## Second-Brain Fit

Cognee is not a substrate-only product. A developer can adopt its SDK, local services, or hosted API directly as an agent memory layer: provide data, process it into connected knowledge, then retrieve context for an agent. Its graph, vector, and relational backends also make it useful as a substrate inside a larger application.

That does not make Cognee a finished personal knowledge-management app. It provides processing and retrieval primitives, not the curated, human-readable wiki management experience found in GBrain or an LLM Wiki workflow. Similar answers from two systems do not mean they preserve the same representation or lifecycle.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Apache-2.0 local Python path; optional self-hosted API and MCP deployment; Cognee Cloud is a separate managed service. |
| Context capture | Accepts documents, code, text, and structured data through SDK/API paths; agent integrations can add session or project context. |
| Knowledge organization | Turns inputs into chunks, entities, relationships, embeddings, and a queryable knowledge graph. This is structured memory, not automatically a polished wiki. |
| Memory evolution | Processing and improvement workflows can enrich or update memory; the user still chooses when to process, reprocess, or curate sources. |
| Retrieval / use | Search can return graph context, matching chunks, summaries, or generated responses depending on the selected search mode. |
| Agent activation / write-back | Python SDK, API, MCP server, CLI, plugins, and documented agent integrations. |
| Personal / team scope | Datasets and, in service mode, user/tenant permissions can scope access. Correct isolation still depends on deployment and configuration. |
| Feedback / correction | Dataset and data-management APIs support inspection and deletion; a human-facing knowledge review UI is not the primary product surface. |
| Privacy / control | Local models and storage can keep a local workflow self-managed. Hosted Cloud has a separate trust and data-processing boundary. |
| Setup / operations | Low for a local SDK experiment; medium when configuring model providers, storage backends, services, source refresh, and permissions. |

## How Source Provisioning Works

Treat the original files in Drive, Notion, or a local vault as the authoritative copies. In a Cognee data workflow, add text/files/structured data to a dataset, run the cognification pipeline to create graph and vector representations, and search that processed dataset. The current README also exposes higher-level remember and recall calls for a local quickstart. Use the API and examples for the exact method names and input shape supported by the installed version.

The graph and search index are derived memory. Keep the original files and source identifiers outside Cognee so you can audit, correct, re-ingest, or rebuild them. Use separate datasets for meaningful scope boundaries, preserve source names/URLs and timestamps as metadata where supported, and test update/deletion behavior before treating the index as an archive or backup.

A fully local text workflow is possible with the documented small local extraction and embedding models; it avoids a hosted API subscription but downloads models and uses local compute. Generated answers and some media processing need an LLM or other model provider, which can add cost unless configured locally.

## Strengths

- Public Apache-2.0 source and a local-first path.
- Its graph-oriented pipeline connects documents, chunks, entities, and relationships rather than exposing only a flat vector index.
- Multiple adoption surfaces: SDK, API, MCP, CLI, and agent integrations.
- The same knowledge model can support both direct agent memory and use as a lower-level graph/retrieval component.

## Limitations

- It is developer-oriented; source collection, refresh, access controls, and operations still need an owner.
- A graph is not the same thing as a user-editable wiki. Human-readable knowledge artifacts require a separate workspace or workflow.
- Results and update behavior depend on the selected pipeline, models, dataset boundaries, and source metadata.
- Per-client standalone deployments can fragment memory if clients do not share one configured service or dataset.

## Best For

- Developers who want an open-source, self-managed graph memory pipeline that AI clients can query.
- People who want searchable links and facts across documents, code, and conversations.
- A processing and retrieval layer paired with an inspectable Markdown workspace such as GBrain or an LLM Wiki.

## Not Ideal For

- Nontechnical users who want a ready-made second-brain interface with automatic source governance.
- Users expecting Cognee itself to produce and manage polished wiki pages.
- Teams unwilling to choose a deployment mode, define dataset boundaries, and own refresh and access-control behavior.

## Tradeoffs

Cognee offers a clearly source-available local route and flexible data/retrieval architecture. That reduces dependence on a paid hosted memory service but moves setup, local model performance, source synchronization, and knowledge review onto the operator. For a human-facing knowledge layer, pair it with an editable workspace rather than expecting graph retrieval alone to provide wiki management.

## Official Setup / Evaluation Links

- [Cognee installation and local quickstart](https://docs.cognee.ai/getting-started/installation)
- [Cognee API reference: ingestion, cognification, search, and datasets](https://docs.cognee.ai/api-reference/introduction)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
- [Cognee agent integrations](https://docs.cognee.ai/cognee-mcp/integrations)
- [Official Cognee repository](https://github.com/topoteretes/cognee)
- [Cognee license](https://github.com/topoteretes/cognee/blob/main/LICENSE)

## Sources

- [Official Cognee README](https://github.com/topoteretes/cognee)
- [Cognee installation and local quickstart](https://docs.cognee.ai/getting-started/installation)
- [Cognee API reference](https://docs.cognee.ai/api-reference/introduction)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
- [Apache-2.0 license](https://github.com/topoteretes/cognee/blob/main/LICENSE)

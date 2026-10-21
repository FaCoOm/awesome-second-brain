# Cognee and Supermemory: Similar Labels, Different Systems

**Reviewed 2026-10-21.** Both can put useful context in front of an AI agent, but that shared outcome does not make their storage models, ingestion pipelines, or human-facing workflows equivalent. “Agent memory layer” is an adoption category, not a promise that two products behave the same.

## What Each System Turns Sources Into

| Question | Cognee | Supermemory |
|---|---|---|
| What can be provided? | Documents, code, text, and structured data through SDK/API workflows. | Documents, files, URLs, conversations, and supported source connectors. |
| What happens to the input? | Add data to a dataset, process it into chunks, entities, relationships, embeddings, and graph-backed memory. | Keep documents as retrieval sources and derive atomic facts, relationships, and profile context in a memory graph. |
| What does an agent get? | Graph context, matching chunks, summaries, or a generated answer depending on search mode. | Relevant source documents and extracted memory/profile context through hybrid search, API, or MCP. |
| What is the human-facing artifact? | Primarily a queryable memory graph and retrieval API, not an editorial wiki. | Documents plus derived memories and profiles, not a curated knowledge wiki. |
| Where does it fit? | Open-source knowledge-processing/agent-memory layer; also a graph/retrieval substrate inside a larger system. | Hosted agent memory/context service with document RAG; local binary also advertised. |

So yes, they can return similar-looking answers or passages to an agent. The result is generated from different intermediate structures and lifecycle rules. A matching answer is not evidence that the systems preserve the same source provenance, update behavior, permissions, or editable artifacts.

## The Taxonomy Correction

Cognee should not be described as “memory substrate only.” Its Python SDK, API, MCP server, and agent integrations make it directly adoptable as an agent memory and knowledge-processing layer. Its graph/vector/relational components also let an application use it as a lower-level substrate. This repository classifies it primarily by the adoption surface and records the substrate role as secondary.

Supermemory also belongs in the agent-memory family, but that does not mean it only remembers episodes from prior chats. Its current product documentation describes document RAG, connectors, extracted fact memory, profiles, hybrid search, and agent access. Its results overlap with Cognee at retrieval time; its managed extraction/profile model differs from Cognee's graph-building pipeline. Neither product is, by itself, the same as a user-operated wiki.

## How to Provision Sources into Cognee

A low-risk pattern for Drive, Notion, and files is:

1. **Keep the original source authoritative.** Leave Drive/Notion as the original record, or export a stable copy into a versioned local folder if local control is important. Cognee's graph/index is derived data, not your only archive.
2. **Choose dataset boundaries.** Use datasets that match real permission and lifecycle boundaries, such as personal research, work projects, or a separate subject area. Do not combine content with different access rules into one unrestricted dataset.
3. **Add selected inputs.** Send files, text, or structured records through the Cognee SDK/API's documented ingestion path. Preserve source name or URL, update time, and stable identifiers as metadata when the chosen input path supports them.
4. **Process the dataset.** Run the documented cognification workflow so Cognee extracts and indexes chunks, entities, and relationships. The latest quickstart also offers higher-level remember/recall calls; check the installed version's docs for exact semantics.
5. **Query and inspect.** Search with representative questions and verify the returned chunks/graph context against the original sources. Choose raw chunk or graph-oriented search when you need evidence; generated answers require a configured model.
6. **Refresh and delete deliberately.** Reprocess changed source material, track which source version produced the index, and test dataset deletion/update behavior. Keep an external manifest so stale graph data can be located and removed.

This is a source-to-index pipeline, not an automatic guarantee that Cognee continuously syncs every Drive or Notion change. A connector, sync job, or agent has to supply those changes. Keep source IDs and a repeatable ingestion manifest so the knowledge graph can be rebuilt.

## How This Fits the GBrain or LLM Wiki Goal

For a system that combines Cognee's cross-source relations with GBrain or LLM Wiki's readable management, separate the responsibilities:

- **Source of truth:** original Drive/Notion files or a local Markdown/vault mirror.
- **Knowledge artifact layer:** GBrain or an LLM Wiki workflow creates inspectable, editable topic pages with links back to sources and reviewable changes.
- **Agent retrieval layer:** Cognee indexes selected source material and supplies graph/chunk context through SDK, API, or MCP.
- **Optional conversational memory:** Supermemory can keep agent preferences, session facts, and document retrieval convenient, but it need not own the canonical archive.

The same input can feed both the wiki compiler and Cognee, but their updates are not automatically synchronized just because both are “memory” tools. A small ingestion manifest and explicit source links are the integration contract. Start with one domain and a few representative documents, then add more sources after verifying corrections, deletion, access boundaries, and retrieval quality.

## Zero-Subscription Decision

| Option | Recurring subscription | Main cost/limit | Fit |
|---|---|---|---|
| Cognee local with local models | None required for the documented local path | Setup, downloads, local compute, and maintenance; generated answers or some media tasks may need a provider unless run locally | Best starting point when open-source control and agent retrieval matter. |
| GBrain or LLM Wiki on local Markdown | None required for a local workflow | User/agent review, source synchronization, and wiki maintenance | Best for readable, editable knowledge artifacts. |
| Supermemory Free hosted account | No paid plan required to try; current listing includes $5 monthly credits | Metered ingestion/search/operations consume the monthly balance; not an unlimited corpus service | Keep as an optional convenience layer for light agent memory within the credit budget. |
| Supermemory local server | Product advertises local binary use | Binary/runtime source and license mapping need verification; pricing page also describes self-hosted deployments under Scale/Enterprise | Consider only after confirming current terms, platform support, and acceptable source transparency. |

**Recommendation for a strict no-subscription setup:** keep originals in Drive/Notion or a local Markdown mirror, use a local GBrain/LLM Wiki workflow for the human-facing artifacts, and add Cognee locally for graph-backed agent retrieval when it solves a concrete search problem. Keep the Supermemory Free account optional rather than making a metered hosted account the only copy of the knowledge base. “No subscription” still has setup, hardware, time, and maintenance costs.

## Primary Sources

- [Cognee repository and README](https://github.com/topoteretes/cognee)
- [Cognee Apache-2.0 license](https://github.com/topoteretes/cognee/blob/main/LICENSE)
- [Cognee installation and local quickstart](https://docs.cognee.ai/getting-started/installation)
- [Cognee API reference: add, cognify, search, and datasets](https://docs.cognee.ai/api-reference/introduction)
- [Supermemory product overview](https://supermemory.ai/product/)
- [Supermemory pricing and credits](https://supermemory.ai/pricing/)
- [Supermemory local-server changelog](https://supermemory.ai/changelog/local/)
- [Supermemory repository and MIT license](https://github.com/supermemoryai/supermemory)
- [Supermemory MCP overview](https://supermemory.ai/mcp/)

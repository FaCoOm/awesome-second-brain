# Memory Systems Research

This note records the source-backed audit behind the current README/watchlist updates for adjacent AI memory, context database, incremental indexing, and compression systems.

## Method

- Primary sources: official repositories and official docs.
- Notion Knowledge Base discussion pages informed the stack-level framing, especially `System Design` (memory/context authority vs freshness/compression/runtime layers) and `Headroom vs CocoIndex vs Ponytail` (compression vs freshness vs policy layers). Primary sources still decide product identity and factual claims.
- Secondary sources: DeepWiki only when it helped orient repo structure; treat it as stale-risk because it is indexed snapshots, not canonical docs.
- Tooling limitation: Docker MCP GitHub search returned `401 Bad credentials`, so GitHub API-backed MCP search was unavailable. Direct GitHub/docs fetches were used instead.

## System Design Takeaways

| System type | Role in a second-brain stack | Examples | Design implication |
|---|---|---|---|
| Agent memory layer | Stores/retrieves scoped memories for agents or apps through API, SDK, MCP, plugins, or local services. | Supermemory, Hindsight, Mnemosyne, taOSmd | Compare on write path, scoping, recall evidence, correction, governance, and deployment model. |
| Context database | Organizes memory, resources, skills, and session context as a queryable substrate. | OpenViking | Do not treat as just memory; evaluate retrieval observability, hierarchy, session compression, and context loading. |
| Incremental context pipeline | Keeps indexes fresh as source data and code change. | CocoIndex | Use as substrate/pipeline under memory or RAG products, not as a complete memory layer. |
| Compression/proxy layer | Shrinks or shapes context before it reaches models; may include shared memory. | Headroom | Treat memory as a subfeature unless the memory lifecycle is the primary adoption surface. |

## Coding-Agent Context Pipeline

Use this as a high-level assembly model, not a new product category. Each stage can be skipped when the adopted product already covers it.

| Stage | Job | Product fit | Caveat |
|---|---|---|---|
| Capture | Bring code, chats, docs, issues, sessions, notes, and user actions into the system. | Supermemory connectors, Mem0/OpenMemory APIs, Cognee loaders, platform baselines such as Claude Code memory or Cursor rules | Rules files provide durable context, not self-updating memory by themselves. |
| Normalize | Turn raw sources into scoped records, profiles, banks, entities, or documents. | Hindsight memory banks, Honcho peers/sessions, Mem0 user/run/session/agent scopes, Cognee graph data | Scope mistakes are harder to fix later than retrieval mistakes. |
| Extract | Promote useful facts, observations, entities, links, and timelines. | Cognee ontology/graph flow, Zep/Graphiti temporal graph, Mnemosyne BEAM tiers, taOSmd archive plus graph/vector stores | Keep provenance; generated facts without source trails are weak memory. |
| Refresh | Keep indexes and derived context current as sources change. | CocoIndex incremental flows, OpenViking context loading/session management, product-native consolidation loops | Freshness tools are substrates unless they own the memory lifecycle. |
| Compress | Fit relevant context into model budgets before runtime injection. | Headroom compression/proxy, OpenViking session compression, local summarization or pruning jobs | Compression should be reversible or source-backed for high-stakes work. |
| Store | Keep durable memory in a service, graph, local DB, or workspace. | Supermemory, Hindsight, Mem0/OpenMemory, Mnemosyne, taOSmd, Zep/Graphiti, Cognee | Pick one primary memory authority to avoid divergent truths. |
| Retrieve | Select the right context through semantic, graph, keyword, temporal, scoped, or hybrid search. | Hindsight recall, Graphiti/Zep graph search, Mnemosyne hybrid search, taOSmd hybrid retrieval, Cognee search | Retrieval quality must be judged by activation evidence, not API availability. |
| Inject | Load context into the coding agent or workflow. | MCP servers, SDK/API calls, Claude Code `CLAUDE.md`, Cursor `.cursor/rules/*.mdc` or `AGENTS.md`, plugins | Injected context can still be ignored; require citations, traces, or explicit use. |
| Write back | Save decisions, corrections, preferences, summaries, and task outcomes. | Agent memory APIs, local memory CLIs, MCP write tools, wiki/vault edits | No write-back path means the system is retrieval-only, not evolving memory. |

## Terminology Findings

| Term | Source-backed meaning | Taxonomy implication |
|---|---|---|
| Agent memory | Long-term or cross-session memory exposed to agents through APIs, SDKs, MCP, plugins, local services, or managed platforms. | Usually an agent memory layer unless the product is only a lower-level graph/retrieval backend. |
| Context engineering | Runtime selection and shaping of the right information, tools, and format for model work. | Cross-cuts layers; compare activation evidence, citation, scoping, and update semantics. |
| Memory API / memory layer | Developer-facing memory primitive for products or workflows. | Classify by adoption surface, normally agent memory layer. |
| Graph RAG / graph memory | Entity/relation/temporal retrieval substrate for applications. | Usually memory substrate unless packaged with user workflow and governance. |
| Organizational knowledge base | Durable team knowledge with permission, inspection, correction, and source controls. | Requires governance review; often end-to-end app, local workspace, or app built on substrate. |
| Personal coding-agent memory | Project and user context reused by coding agents across runs. | Often local workspace, local/hosted agent memory layer, or platform baseline such as Claude Code memory. |

## Product Findings

### Cognee

- Official source: https://github.com/topoteretes/cognee
- Positioning: open-source AI memory platform for agents.
- Architecture: self-hosted knowledge graph, vector embeddings, graph reasoning, ontology generation.
- Fit: currently listed as a memory substrate. That is acceptable, but it also has agent-facing memory APIs, MCP, CLI, UI, plugins, and clients, so the substrate label should not imply it is only low-level storage.

### Hindsight

- Official source: https://github.com/vectorize-io/hindsight
- Docs: https://hindsight.vectorize.io/developer/mcp-server
- Positioning: agent memory that learns.
- Architecture: memory banks, observations, retain/recall/reflect loops, semantic/keyword/graph/temporal recall, fusion/rerank.
- Fit: agent memory layer is correct.

### Supermemory

- Official source: https://github.com/supermemoryai/supermemory
- Docs: https://supermemory.ai/docs
- Positioning: memory API and context layer for AI products/workflows.
- Architecture: memory/document APIs, profiles, graph/hybrid retrieval, connectors, MCP, SDKs, plugins.
- Fit: agent memory layer is correct. Existing profile should keep hosted wording unless official sources prove a local or self-hosted deployment path.

### LangChain context engineering docs

- Docs: https://docs.langchain.com/oss/python/concepts/context and https://docs.langchain.com/oss/python/langchain/context-engineering
- Positioning: context engineering is about providing the right context, tools, and formatting; long-term context can persist across conversations through storage.
- Fit: context engineering is a runtime concern across layers, not a separate product category.

### Mem0 / OpenMemory

- Docs: https://docs.mem0.ai/open-source/overview and https://mem0.mintlify.app/core-concepts/memory-types
- Positioning: memory for AI agents and applications, with user/run/session/agent and organization memory concepts.
- Fit: agent memory layer is correct. Organization-scoped memory supports business KB use cases, but the adoption surface remains developer memory infrastructure unless paired with an app/workflow.

### Zep / Graphiti

- Docs: https://www.getzep.com/product/agent-memory/
- Positioning: enterprise-scale agent memory using temporal knowledge graphs, including business, user, and work memory.
- Fit: memory substrate is still correct for this catalog because the primary evaluated artifact is Graphiti/Zep graph memory infrastructure beneath applications.

### Claude Code memory

- Docs: https://docs.anthropic.com/en/docs/claude-code/memory
- Positioning: project/user/local `CLAUDE.md` files are loaded into Claude Code context.
- Fit: platform baseline is correct; useful for personal coding-agent memory, but scoped to Claude workflows.

### Cursor rules

- Docs: https://cursor.com/docs/rules
- Positioning: project rules live in `.cursor/rules/*.mdc`; Cursor can also use `AGENTS.md` as workspace guidance.
- Fit: local workspace or platform baseline support. Rules provide durable instructions/context, but they are not model memory by themselves.

### NotebookLM / Claude Projects

- Docs: https://support.google.com/notebooklm and https://support.anthropic.com
- Positioning: bounded source/project workspaces.
- Fit: platform baseline is correct. Public docs support project/source grounding; they do not by themselves prove full organization-memory infrastructure.

### OpenViking

- Official source: https://github.com/volcengine/OpenViking
- Docs: https://docs.openviking.ai/en/concepts/01-architecture
- Positioning: context database for AI agents.
- Architecture: filesystem paradigm for memory/resources/skills, L0/L1/L2 context loading, directory recursive retrieval, visualized retrieval trajectory, automatic session management.
- Fit: watchlist/context database. Better as agent context substrate than plain memory layer.

### CocoIndex

- Official source: https://github.com/cocoindex-io/cocoindex
- Docs: https://cocoindex.io/docs
- Positioning: incremental engine for long-horizon agents and always-fresh context.
- Architecture: declarative Python flows, persistent state, lineage, memoization by input/code hash, delta-only recomputation, Rust core.
- Fit: memory substrate or context pipeline. Not a standalone memory layer.

### Headroom

- Official source: https://github.com/headroomlabs-ai/headroom
- Docs: https://headroom-docs.vercel.app/docs
- Positioning: context compression layer for AI agents.
- Architecture: local proxy/library/MCP, content router, content-aware compressors, reversible cache/retrieve flow, cross-agent memory, learned corrections.
- Fit: adjacent watchlist. Its memory is useful, but primary adoption surface is compression/proxy.

### Mnemosyne

- Official source: https://github.com/mnemosyne-oss/mnemosyne
- Docs: https://docs.mnemosyne.site/
- Positioning: zero-dependency, local-first AI memory for Hermes and other agents.
- Architecture: SQLite-backed BEAM memory with working memory, episodic memory, temporal TripleStore, hybrid vector/FTS5/importance recall, MCP/SDK/CLI surfaces, Hermes plugin hooks, memory banks, and optional sync.
- Fit: agent memory layer is correct. It is a local programmable memory backend, not a full consumer second-brain app or broad connector platform.

### taOSmd

- Official source: https://github.com/jaylfc/taosmd
- Benchmarks: https://github.com/jaylfc/taosmd/blob/master/docs/benchmarks.md
- Research report: https://github.com/jaylfc/taosmd/blob/master/docs/research-report.md
- Positioning: local-first, framework-agnostic, offline AI memory with provable/auditable memory.
- Architecture: append-only zero-loss archive as source of truth; temporal knowledge graph; vector memory; session catalog; crystal store; fact verifier; hybrid retrieval; query expansion; intent routing; rerank; graph expansion; token-budgeted context assembly.
- Fit: agent memory layer is correct. README/profile were stale on install: current README documents `pip install taosmd` and `pip install "taosmd[mcp]"`, plus source install.

## README / Content Updates Applied

- Fixed stale taOSmd install tradeoff text in `README.md` to package/source install plus no hosted option.
- Added this research note to the README Deep Dives table.
- Added OpenViking, CocoIndex, and Headroom to `watchlist.md` with source-backed category caveats.
- Fixed English and Korean taOSmd profile/setup references that still had stale install wording.
- Corrected Mnemosyne source identity to `mnemosyne-oss/mnemosyne` and aligned the profile with official README/docs claims.
- Added a canonical categorization standard to `comparisons/solution-layers.md` and the Korean mirror.
- Added reader-intent framing for personal coding-agent memory, business persistent knowledge bases, memory APIs, context engineering, and Graph RAG without changing the primary layer model.

## Remaining Non-Edits

- No full profiles were created for OpenViking, CocoIndex, or Headroom. They remain watchlist items because the repo promotion rule requires full deployment/setup/limitation evaluation before moving into `solutions/`.
- Notion KB discussion pages were used for architecture framing only; official repositories/docs remain authoritative for repo identity, setup, and capability claims.

## Framing Sources

- Notion KB: `System Design`, https://app.notion.com/p/39304b32bb3180f98df7ea665f2a56d7
- Notion KB: `Headroom vs CocoIndex vs Ponytail`, https://app.notion.com/p/e1b04b32bb3182cfbb4e81b4262839bb

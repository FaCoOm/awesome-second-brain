# System Pipeline Proposals

This report turns the catalog into implementable second-brain and agent-memory stacks. It is a design guide, not a benchmark. Product-specific claims should still be checked against each profile's official sources before procurement or production rollout.

## Shared Reference Pipeline

| Stage | Purpose | Evaluation question |
|---|---|---|
| Capture | Ingest files, chats, code, app events, notes, tickets, and user decisions. | Which sources enter automatically, manually, or through custom APIs? |
| Normalize | Convert raw inputs into scoped documents, messages, memories, entities, sessions, or wiki pages. | Does the system preserve user, team, project, source, and permission boundaries? |
| Extract | Promote durable facts, entities, relationships, procedures, summaries, and preferences. | Are extracted memories source-backed and correctable? |
| Store | Keep the authoritative memory in an app, workspace, service, graph, or local database. | Is there one primary memory authority, or multiple divergent stores? |
| Refresh | Re-index and update derived context as sources change. | Are stale source states visible and repairable? |
| Retrieve | Select context by semantic, keyword, graph, temporal, scoped, or hybrid search. | Can retrieval be inspected, cited, filtered, and evaluated? |
| Compress | Fit selected context into model budgets without losing source traceability. | Is compression reversible, source-backed, or safe enough for the workflow? |
| Inject | Load context into the human or agent work surface through MCP, API, SDK, plugin, UI, or rules files. | Is there proof that the model actually received the intended context? |
| Write back | Save decisions, corrections, new memories, and task outcomes. | Does useful work improve the memory system instead of disappearing in chat history? |
| Govern | Inspect, correct, delete, export, scope, audit, and permission memory. | Who can change memory, and how are mistakes reversed? |

## Field 1: Personal Coding-Agent Memory

Goal: help coding agents remember project facts, local conventions, decisions, and prior sessions without turning the repository into an opaque hosted knowledge base.

| Stack | Systems | Best fit | Risks to audit |
|---|---|---|---|
| Local wiki plus agent memory | Hermes Agent + LLM Wiki, Mnemosyne, Claude Code memory | Developers who want inspectable Markdown plus local recall in agent sessions. | Ensure retrieved memory is cited in tool logs; avoid stale wiki facts becoming unreviewed instructions. |
| Offline agent memory | taOSmd, Claude Code memory, Cursor rules | Local-first or low-power environments where the archive and MCP/API surfaces matter. | Verify local model/embedding setup, backup policy, and cross-agent scoping. |
| Cross-client graph memory | Cognee, Cursor rules, Claude Code memory | Users who move between MCP-compatible coding clients and want shared graph memory. | Avoid per-client standalone stores that fragment memory. |

Recommended default: start with platform rules files for stable project instructions, add one local or agent memory layer for cross-session recall, then add a graph layer only when entity/relation retrieval is needed.

## Field 2: AI Product User Memory

Goal: add durable user, session, preference, and event memory to an AI product without building a full second-brain app.

| Stack | Systems | Best fit | Risks to audit |
|---|---|---|---|
| Hosted memory API | Supermemory, Mem0/OpenMemory, Honcho | SaaS products that need fast API/MCP memory with user or peer scoping. | Confirm deletion, tenant isolation, source retention, and retrieval-to-action logs. |
| Stateful agent social model | Honcho, Hindsight, Mem0/OpenMemory | Agents that need persistent user, peer, session, conclusion, or observation memory. | Separate user facts from model inferences; make correction flows explicit. |
| Graph-backed product memory | Zep/Graphiti, Cognee, Supermemory | Products where user memory needs entities, relationships, facts, and temporal context. | Model graph update semantics; require provenance for generated facts. |

Recommended default: choose one hosted or self-hosted memory API first, then add graph infrastructure only if the product needs entity-level or temporal reasoning beyond scoped recall.

## Field 3: Enterprise Knowledge And Team Second Brain

Goal: maintain inspectable organizational knowledge across teams, documents, apps, and AI workflows.

| Stack | Systems | Best fit | Risks to audit |
|---|---|---|---|
| End-to-end governed brain | Membase, Supermemory, Claude Projects/Claude Code | Teams that want fast capture, retrieval, and agent activation with less custom infrastructure. | Validate permissions, export, deletion, and acted-on evidence per workflow. |
| Local workspace plus substrate | GBrain, Obsidian/Logseq + AI bridge, Zep/Graphiti | Teams that want human-inspectable source of truth plus graph retrieval underneath. | Keep wiki/vault authority clear; avoid graph outputs outranking reviewed docs. |
| Connector-first context platform | Hyperspell, Supermemory, Mem0/OpenMemory | Internal agents that need SaaS connector ingestion and API-based context. | Confirm connector availability, private-beta status, user scoping, and review UI. |

Recommended default: if governance matters more than custom memory research, start with an end-to-end or local-workspace authority and treat memory APIs as activation layers, not the only source of truth.

## Field 4: Private Research And Local-First Knowledge Work

Goal: support researchers, legal/medical/financial analysts, or offline teams that need local control and auditable sources.

| Stack | Systems | Best fit | Risks to audit |
|---|---|---|---|
| Local research workspace | Obsidian/Logseq + AI bridge, Khoj, NotebookLM | Individuals who need grounded work over notes, PDFs, web pages, or bounded source sets. | NotebookLM is platform-bounded; Obsidian/Logseq bridges need custom governance. |
| Local agent-operated brain | GBrain, Hermes Agent + LLM Wiki, Mnemosyne | Technical users who want agent-maintained local knowledge with inspectable artifacts. | Confirm maintenance jobs, linting, correction, and backup discipline. |
| Offline memory backend | taOSmd, Mnemosyne, Cognee local mode | Environments where cloud memory is unacceptable or unavailable. | Verify local dependencies, model downloads, encryption/storage requirements, and operator burden. |

Recommended default: keep human-readable files or notebooks as the authority, then add local agent memory for recall and write-back. Do not replace reviewed source documents with generated summaries.

## Field 5: Freshness-Heavy RAG And Context Operations

Goal: keep changing sources, codebases, meetings, and databases indexed so agents retrieve current context.

| Stack | Systems | Best fit | Risks to audit |
|---|---|---|---|
| Incremental indexing pipeline | CocoIndex, Zep/Graphiti, application RAG | Engineering teams with fast-changing source data and code. | CocoIndex is a freshness substrate, not a memory authority; define downstream ownership. |
| Context database operations | OpenViking, Cognee, Claude Code memory | Agent environments that need memory, resources, skills, and session context arranged as a queryable workspace. | Audit context loading trajectories and session compression for hidden omissions. |
| Compression plus memory | Headroom, Supermemory, Hindsight | Agents hitting token limits while needing durable recall. | Treat Headroom memory as subfeature unless it owns the full memory lifecycle; require reversible or source-backed compression. |

Recommended default: put freshness and compression around a chosen memory authority instead of letting every pipeline component become a competing source of truth.

## Adoption Guardrails

| Decision | Rule |
|---|---|
| Primary category | Classify by the first layer a reader must adopt: app, workspace, agent memory layer, substrate, or platform baseline. |
| Cognee placement | List Cognee as an agent memory layer because users adopt SDK/API/MCP/plugin memory workflows first; preserve its secondary graph-substrate role in notes. |
| Watchlist promotion | Keep OpenViking, CocoIndex, and Headroom as watchlist or proposal components until full setup, deployment, limitation, and governance evidence is ready. |
| Memory authority | Pick exactly one authority per stack. Supporting index, graph, compression, and rules layers should feed it or consume from it, not fork truth. |
| Activation evidence | Do not count retrieval as success unless traces, citations, logs, or UI state show the context was loaded and used. |
| Governance | Require correction, deletion, export, source provenance, and scope controls before calling a stack enterprise-ready. |

## Audit Checklist

| Area | Pass condition |
|---|---|
| Source evidence | Every product claim links to official docs, official repos, maintainer examples, product docs/changelogs, or local hands-on reports. |
| Layer fit | Each product has one primary layer and any secondary role is explicit. |
| Retrieval proof | A representative workflow records retrieved context, source IDs, and whether the agent used it. |
| Write-back proof | Useful outcomes can update memory through a documented UI, API, SDK, MCP tool, CLI, or file workflow. |
| Freshness | Changed source data re-indexes or is marked stale; stale derived memory can be repaired. |
| Privacy/control | Users can inspect, correct, delete, export, and scope memory according to the deployment model. |
| Failure handling | The stack has a defined response for wrong memory, conflicting facts, source deletion, connector failure, and model refusal. |

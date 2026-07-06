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

## Field 1: Industry-Grade Coding-Agent Pipeline

Goal: design a complete OpenCode-like coding agent stack that can plan, edit, test, remember, retrieve, verify, and operate safely across real repositories. Treat this as a system pipeline, not a product pick: one agent runtime coordinates one memory authority, one inspectable workspace source of truth, optional graph/freshness layers, and strict operational controls.

### Reference Architecture

| Layer | Job | Strong fit | Pass condition |
|---|---|---|---|
| Agent runtime | Run the agentic loop: gather context, call tools, edit files, verify, summarize, fork, and recover. | OpenCode agents/tools/skills/MCP, Claude Code agentic harness concepts | Every action is represented as a tool call, permission decision, subagent task, or session event. |
| Policy and instruction layer | Load durable repo, user, and org rules before work begins. | `AGENTS.md`, `CLAUDE.md`, Cursor rules, OpenCode rules/skills | Agent follows current repo commands, style, safety, and verification rules without repeating them in every prompt. |
| Work surface | Keep human-reviewable truth in files, issues, docs, branches, worktrees, and session notes. | Git worktrees, Markdown wiki, Obsidian/Logseq, Hermes Agent + LLM Wiki | A maintainer can inspect what the agent believes and change it with normal repo/file workflows. |
| Memory authority | Store durable cross-session facts, decisions, preferences, summaries, and corrections. | Mnemosyne, taOSmd, Hindsight, Mem0/OpenMemory, Supermemory | Exactly one system owns memory writes; every memory has scope, provenance, and correction path. |
| Context graph | Model entities, relationships, timelines, code concepts, people, decisions, and dependencies. | Cognee, Zep/Graphiti, taOSmd graph store | Graph facts are source-backed and can be repaired when sources change. |
| Freshness layer | Re-index changed code/docs and mark stale derived context. | CocoIndex-style incremental flow, product-native refresh, git/file watchers | Changed files cause incremental updates or visible stale-state warnings. |
| Retrieval layer | Select context through keyword, semantic, graph, temporal, scoped, and recency-aware search. | Hybrid memory search, graph search, code search, local wiki search | Retrieval returns source IDs, snippets, timestamps, and reason-for-selection. |
| Compression layer | Fit relevant context into model budget without losing traceability. | Headroom-style compression, OpenViking-style session compression, curated Markdown summaries | Compressed context links back to original sources and can be rejected when lossy. |
| Injection layer | Deliver selected context to the agent through the runtime's supported surfaces. | MCP resources/tools/prompts, OpenCode MCP servers, Claude/Cursor rule loading, skills | Tool logs or traces show which context was loaded before the agent acted. |
| Write-back layer | Save new decisions, fixes, test evidence, user corrections, and task summaries. | MCP write tools, memory APIs, local memory CLIs, wiki edits, session summaries | Useful work updates memory or documented source of truth instead of staying only in chat. |
| Governance layer | Enforce permissions, approvals, sandboxing, audit logs, deletion, export, and scope boundaries. | OpenCode permissions, Claude Code permissions/hooks/sandboxing, MCP roots, managed settings | Dangerous actions require approval or are denied by runtime controls, not model goodwill. |
| Operations layer | Measure cost, latency, failures, context load, test pass rate, memory quality, and reviewer outcomes. | CI, eval harnesses, traces, audit logs, regression scenarios | The team can answer: what changed, why, which context was used, and whether verification passed. |

### Optimized Development Flow

1. Bootstrap repo truth: create or update `AGENTS.md` / `CLAUDE.md` / rules with architecture, commands, style, known hazards, and verification requirements.
2. Start in plan mode or a restricted planning agent for ambiguous work; switch to build only after scope and checks are known.
3. Load only relevant skills and MCP servers; disable broad MCP servers globally and enable them per agent when needed to control context cost.
4. Capture the task, branch/worktree, current diff, failing tests, relevant files, prior decisions, and user constraints into the memory authority.
5. Retrieve in tiers: repo rules first, current files second, recent session memory third, semantic/graph memory fourth, external docs last.
6. Compress retrieved context into a small, cited working packet; drop uncited or low-confidence memories.
7. Execute with small diffs, task tracking, typed tool calls, permission gates, and subagents for parallel read-only research or isolated review.
8. Verify through tests, build, lint/LSP, real CLI/browser/API surface, and reviewer gate when risk is high.
9. Write back only durable learning: decisions, corrections, new constraints, resolved failures, evaluation evidence, and links to commits/issues.
10. Periodically prune or decay stale memories, regenerate summaries from source, and audit retrieval-to-action evidence.

### Recommended Component Stack

| Need | Default component | Upgrade when |
|---|---|---|
| Coding-agent runtime | OpenCode-style runtime with primary agents, subagents, tools, skills, permissions, and MCP | You need managed org policy, hosted execution, or enterprise audit controls. |
| Repo instructions | `AGENTS.md` plus focused skills/rules | The same mistake repeats or a workflow becomes stable enough to package. |
| Human-readable source of truth | Markdown wiki or docs in the repo/workspace | Knowledge must outlive one memory vendor or remain reviewable in pull requests. |
| Local memory authority | Mnemosyne or taOSmd | Offline operation, inspectable SQLite/archive, or local model control matters. |
| Hosted memory authority | Supermemory, Mem0/OpenMemory, or Hindsight | Multi-app ingestion, team/user scope, or product memory API matters more than local control. |
| Graph reasoning | Cognee or Zep/Graphiti | Entity/relation/time queries matter enough to justify graph maintenance. |
| Freshness | Incremental indexing or product-native refresh | Sources change faster than manual summaries can stay correct. |
| Compression | Source-linked summaries first; dedicated compression only when budgets dominate | Context limits are a measured bottleneck and summaries remain traceable. |
| Integration bus | MCP resources, prompts, and tools | External systems need typed access instead of ad hoc shell/API calls. |
| Governance | Permission rules, sandboxing, MCP roots, hooks, CI checks, audit logs | Agents can write files, run shell commands, call external APIs, or touch secrets. |

### Learning Path

| Foundation | What to learn | Proof you understand it |
|---|---|---|
| Agent loop | How the runtime alternates between context gathering, tool calls, edits, and verification. | You can trace a task from prompt to tool calls to final verification artifact. |
| Tool contracts | Built-in tools, MCP tools, schemas, permissions, approvals, and failure modes. | You can explain why a tool was allowed, denied, or asked. |
| Instruction memory | Difference between rules files, skills, summaries, and semantic memory. | You know what belongs in `AGENTS.md` versus a memory API. |
| Retrieval design | Keyword, semantic, graph, temporal, scoped, and recency-based search. | You can show why each retrieved source was selected and whether it was used. |
| Memory writes | What deserves durable memory and what should remain ephemeral transcript. | You can reject noisy memories and keep only reusable, source-backed learnings. |
| Context compression | How to shrink context without losing provenance. | Every summary links to original files, docs, commits, or tool output. |
| Governance | Permissions, sandboxing, hooks, MCP roots, secrets, deletion, export, and audit. | A malicious or mistaken prompt cannot silently escalate privileges. |
| Operations | Cost, latency, evals, stale index repair, memory quality, and incident review. | You can measure whether the agent got faster, safer, or more correct. |

Source-backed starting points: OpenCode agents/tools/MCP docs, MCP server/client concepts, Claude Code glossary and permissions docs, Cursor rules docs, and each memory product profile in this catalog.

Recommended default: build the narrowest complete pipeline first: `AGENTS.md` + OpenCode-style agents/skills/permissions + one memory authority + MCP injection + source-linked write-back + verification/audit logs. Add graph, freshness, compression, hosted memory, or enterprise policy only after a measured failure proves the simpler pipeline is insufficient.

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

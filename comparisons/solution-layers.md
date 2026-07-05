# Solution Layers

Second-brain products, agent memory APIs, and retrieval substrates are often discussed together, but they do not sit at the same layer of the stack. Use this page before comparing feature tables so a complete app is not judged as if it were backend infrastructure, and a memory substrate is not judged as if it should include a full user workflow. Classify by what the user adopts first: an app, a workspace, an API layer, a substrate, or a platform feature.

## Layer Model

| Layer | Primary job | Typical buyer/user | Compare on |
|---|---|---|---|
| End-to-end app | Package capture, organization, retrieval, UI, and workflow activation. | AI power users, teams, operators | Time to useful setup, source coverage, knowledge UI, governance, integrations |
| Local workspace | Keep a human-owned or agent-operated knowledge base in local files, vaults, wiki pages, or self-hosted services. | Local-first users, researchers, technical operators | Inspectability, file ownership, sync model, maintenance burden, agent access |
| Agent memory layer | Add durable memory to agents or applications through APIs, SDKs, MCP, plugins, or managed services. | Developers, agent builders, internal platform teams | API ergonomics, scoping, write-back, retrieval quality, traceability, hosting model |
| Memory substrate | Provide lower-level graph, retrieval, entity, temporal, or knowledge infrastructure that apps build on. | Infrastructure teams, backend engineers, framework builders | Data model, retrieval architecture, update semantics, scaling, operational complexity |
| Platform baseline | Provide memory or source-grounded context inside one AI platform or bounded research surface. | Users already committed to one platform | Platform fit, exportability, visibility, source control, lock-in |

## Categorization Standard

Classify each system by the first layer a reader must adopt, then document secondary roles in the profile. Use official repositories and docs for product identity and factual claims. If a product spans multiple roles, pick one primary authority: freshness layer, memory/context authority, compression layer, or runtime activation layer.

## Reader Intent Map

Product language is not layer language. Map the user's goal to the adoption layer before comparing tools.

| Reader phrase | Usually means | Start with |
|---|---|---|
| Personal coding-agent memory | The agent should remember project facts, preferences, sessions, and decisions across runs. | Local workspace, agent memory layer, or platform baseline |
| Business persistent knowledge base | Teams need durable, inspectable, permissioned knowledge across docs, chats, apps, and workflows. | End-to-end app, local workspace, or memory substrate plus app layer |
| Memory layer or memory API | Developers need scoped read/write memory for an agent or product. | Agent memory layer |
| Context engineering | The system must select, shape, cite, and load the right context at runtime. | Agent memory layer, memory substrate, or platform baseline |
| Graph RAG or knowledge graph memory | The system needs entities, relationships, temporal facts, or graph retrieval under an app. | Memory substrate |
| AI second brain | Broad umbrella for capture, organization, evolution, use, and governance. | Pick by lifecycle gap first, then layer |

Rules files such as `CLAUDE.md`, `.cursor/rules/*.mdc`, or `AGENTS.md` can act like durable workspace context, but they are not the same as agent memory unless the platform stores, retrieves, and updates memories across runs. Bounded tools such as NotebookLM or Claude Projects can be strong project workspaces without proving they are general multi-tenant organization-memory infrastructure.

## Evaluated Solutions By Primary Layer

| Layer | Solutions |
|---|---|
| End-to-end app | [Membase](../solutions/membase.md), [OpenHuman](../solutions/openhuman.md), [Khoj](../solutions/khoj.md), [Hjarni](../solutions/hjarni.md) |
| Local workspace | [GBrain](../solutions/gbrain.md), [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md), [Hermes Agent + Obsidian + Honcho](../solutions/hermes-obsidian-honcho.md), [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md), [Pad](../solutions/pad.md) |
| Agent memory layer | [Mem0/OpenMemory](../solutions/mem0-openmemory.md), [Honcho](../solutions/honcho.md), [Hindsight](../solutions/hindsight.md), [Mnemosyne](../solutions/mnemosyne.md), [Supermemory](../solutions/supermemory.md), [Hyperspell](../solutions/hyperspell.md), [taOSmd](../solutions/taosmd.md), [Cognee](../solutions/cognee.md) |
| Memory substrate | [Zep/Graphiti](../solutions/zep-graphiti.md) |
| Platform baseline | [ChatGPT Memory](../solutions/chatgpt-memory.md), [Claude Projects/Claude Code](../solutions/claude-projects-code.md), [NotebookLM](../solutions/notebooklm.md) |

## How To Read Cross-Layer Comparisons

When a solution appears in more than one decision path, treat the layer as its primary role, not a hard boundary.

- An end-to-end app should be judged on whether a user can get from scattered context to useful work without assembling infrastructure.
- A local workspace should be judged on whether the user can inspect, repair, sync, and operate the knowledge base over time.
- An agent memory layer should be judged on whether developers can safely scope, retrieve, update, and audit memory inside agent workflows.
- A memory substrate should be judged on whether it provides strong data and retrieval primitives for another application to build on.
- A platform baseline should be judged on whether it is good enough inside its platform and what happens when the workflow needs to leave that platform.

## Common Pairings

Layer boundaries are useful because many real deployments combine layers:

| Pattern | Example |
|---|---|
| App + platform baseline | Use a full second-brain app for cross-tool memory while keeping ChatGPT Memory or Claude Projects as platform-local personalization. |
| Local workspace + agent memory layer | Keep durable notes in a wiki or vault while using an agent memory API for session memory and recall. |
| Agent memory layer + memory substrate | Build product memory with an API layer while relying on graph or retrieval infrastructure underneath. |
| Local workspace + memory substrate | Use a local wiki or vault as the inspectable source of truth, then index it into graph or retrieval infrastructure for application use. |

Cognee is listed as an agent memory layer because its documented adoption surfaces include SDK, MCP, API, plugins, clients, and cloud/local memory workflows. It can still play the secondary graph-substrate role inside a stack.

## Contribution Rule

When adding a new system, pick the smallest primary layer that describes what the user actually adopts first. If a project is mostly a graph, database, embedding index, or retrieval backend, add it as a memory substrate or watchlist candidate instead of presenting it as a full second-brain app. If a system spans multiple layers, list its primary adoption surface first and explain secondary roles in the profile. Keep Korean mirrors semantically aligned with the same primary layer and role labels.

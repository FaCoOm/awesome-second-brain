# Zep / Graphiti

## Snapshot

- Website / docs: https://help.getzep.com/
- Company / maintainer: Zep
- Status: Active platform; Graphiti is the open-source temporal graph library under Zep's memory architecture
- Open source: Graphiti is open source; Zep is a managed platform
- Deployment: Hosted Zep plus Graphiti library integration
- Primary users: Developers building agent applications that need temporal graph memory
- Best second-brain role: Temporal knowledge graph memory backend
- Last reviewed: 2026-05-29

## One-line Summary

Zep uses a temporal knowledge graph, built on Graphiti, to power agent memory and Graph RAG for applications.

## Second-Brain Fit

Zep/Graphiti is best for builders who need graph memory inside an application. It is not the fastest consumer second-brain setup, but it is highly relevant when memory must model entities, facts, episodes, time, and business data.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment | Hosted Zep platform and Graphiti open-source graph library. |
| Data capture | API ingestion through chat history, business data, and graph endpoints. |
| Auto-organization | Built-in entity nodes, entity edges, episodic nodes, facts, and summaries. |
| Consolidation / dreaming | Built-in temporal graph updates and fact/summary extraction; not framed as a user-operated dream loop. |
| Retrieval model | Temporal knowledge graph and Graph RAG. |
| Agent access | API/SDK first; ecosystem integrations for agent frameworks. |
| Workspace / team support | Projects, users, sessions, and groups are part of the Zep model. |
| UI / filtering | Developer/platform UI and graph APIs; end-user second-brain UI is not the primary surface. |
| Privacy / control | Hosted platform plus open-source graph library; verify hosting and retention requirements per deployment. |
| Setup burden | Medium. Requires application integration and data model choices. |

## Strengths

- Strong temporal graph model.
- Good fit for applications with evolving user, session, and business data.
- Graphiti gives a reference architecture for dynamic graph memory.

## Limitations

- Not a no-code personal second-brain app.
- Requires engineering work to ingest, scope, and query memory.
- The managed platform and open-source graph library are related but not identical deployment surfaces.

## Relationship to Membase

Zep/Graphiti is stronger for temporal graph memory inside custom applications. Membase is easier for power users and teams who want shared memory across off-the-shelf agents.

## Official Setup / Evaluation Links

- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Zep memory docs](https://help.getzep.com/v2/memory)
- [Graphiti GitHub repo](https://github.com/getzep/graphiti)

## Sources

- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Zep memory docs](https://help.getzep.com/v2/memory)
- [Graphiti open source](https://www.getzep.com/product/open-source)
- [Graphiti GitHub repo](https://github.com/getzep/graphiti)

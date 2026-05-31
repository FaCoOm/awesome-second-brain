# Zep / Graphiti

## Snapshot

- Website / docs: https://help.getzep.com/
- Company / maintainer: Zep
- Status: Active platform; Graphiti is the open-source temporal graph library under Zep's memory architecture
- Open source: Graphiti is open source; Zep is a managed platform
- Deployment: Hosted Zep plus Graphiti library integration
- Primary users: Developers building agent applications that need temporal graph memory
- Best second-brain role: Temporal knowledge graph memory backend
- Last reviewed: 2026-05-31

## One-line Summary

Zep uses a temporal knowledge graph, built on Graphiti, to power evolving memory and Graph RAG for applications.

## Second-Brain Fit

Zep/Graphiti is best for builders who need graph memory inside an application. It is not the fastest consumer second-brain setup, but it is highly relevant when memory must model entities, facts, episodes, time, and business data.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Hosted Zep platform and Graphiti open-source graph library. |
| Context capture | API ingestion through chat history, business data, and graph endpoints. |
| Knowledge organization | Built-in entity nodes, entity edges, episodic nodes, facts, and summaries. |
| Memory evolution | Built-in temporal graph updates and fact/summary extraction; not framed as a user-operated dream loop. |
| Retrieval / use | Temporal knowledge graph and Graph RAG. |
| Agent activation / write-back | API/SDK first; ecosystem integrations for agent frameworks. |
| Personal / team scope | Projects, users, sessions, and groups are part of the Zep model. |
| Feedback / correction | Developer/platform UI and graph APIs; end-user second-brain UI is not the primary surface. |
| Privacy / control | Hosted platform plus open-source graph library; verify hosting and retention requirements per deployment. |
| Setup / operations | Medium. Requires application integration and data model choices. |

## Strengths

- Strong temporal graph model.
- Good fit for applications with evolving user, session, and business data.
- Graphiti gives a reference architecture for dynamic graph memory.

## Limitations

- Not a no-code personal second-brain app.
- Requires engineering work to ingest, scope, and query memory.
- The managed platform and open-source graph library are related but not identical deployment surfaces.

## Best For

- Developers building agent applications with temporal graph memory.
- Products that need entities, episodes, facts, time, and business data in retrieval.
- Teams comfortable integrating memory through APIs and SDKs.

## Not Ideal For

- Users who want a no-code personal second-brain setup.
- Teams that primarily need off-the-shelf second-brain automation across existing tools.
- Workflows where operating an application memory model is too much overhead.

## Tradeoffs

Zep/Graphiti is strong when memory is part of an application architecture. The tradeoff is integration work: teams must model users, sessions, data ingestion, and retrieval behavior rather than simply connecting an existing tool to a ready-made second-brain layer.

## Official Setup / Evaluation Links

- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Zep memory docs](https://help.getzep.com/v2/memory)
- [Graphiti GitHub repo](https://github.com/getzep/graphiti)

## Sources

- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Zep memory docs](https://help.getzep.com/v2/memory)
- [Graphiti open source](https://www.getzep.com/product/open-source)
- [Graphiti GitHub repo](https://github.com/getzep/graphiti)

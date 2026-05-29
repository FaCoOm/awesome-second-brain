<div align="center">

# Awesome AI Second Brain

[![Context Engineering Banner](assets/context-engineering-banner.png)](https://membase.so/?utm_source=github&utm_medium=awesome-second-brain)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

[![Follow on X](https://img.shields.io/badge/Follow%20on%20X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/mem_base)
[![Follow on LinkedIn](https://img.shields.io/badge/Follow%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/aristotechnologies)
[![Join Discord](https://img.shields.io/badge/Join%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/invite/vRp5Zh3HGu)

</div>

> A practical, source-backed landscape for choosing an AI-native second brain.

This repo is for AI power users who want memory that survives across ChatGPT, Claude, Cursor, Codex, local agents, team workflows, and source documents. It compares what each solution actually supports, what operating burden to expect, and which official docs to use next.

## Start Here

| If you want... | Start with | Why |
|---|---|---|
| The fastest shared memory across AI agents | [Membase](solutions/membase.md) | Hosted MCP, graph + vector hybrid RAG for Memory, Wiki, cross-agent sharing, chat import, Gmail/Google Calendar/Slack connectors, and Wiki import surfaces without operating a local brain stack. |
| Local or self-hosted control | [OpenHuman](solutions/openhuman.md), [GBrain](solutions/gbrain.md), [Khoj](solutions/khoj.md), or [Obsidian/Logseq + AI bridge](solutions/obsidian-logseq.md) | Your data can live in local files or self-hosted services, but you own the setup and maintenance burden. |
| Graph RAG or temporal graph memory | [Membase](solutions/membase.md), [Zep/Graphiti](solutions/zep-graphiti.md), [Cognee](solutions/cognee.md), or [GBrain](solutions/gbrain.md) | These systems make graph structure part of retrieval or memory operations; Membase combines graph and vector retrieval in a hosted shared-memory layer. |
| A developer memory API | [Mem0/OpenMemory](solutions/mem0-openmemory.md), [Supermemory](solutions/supermemory.md), [Zep/Graphiti](solutions/zep-graphiti.md), or [Cognee](solutions/cognee.md) | They expose APIs, SDKs, MCP, or managed services for app builders. |
| Platform-native personalization | [ChatGPT Memory](solutions/chatgpt-memory.md), [Claude Projects/Claude Code](solutions/claude-projects-code.md), or [NotebookLM](solutions/notebooklm.md) | Useful inside one platform, weaker as portable cross-agent memory. |

## Fastest Useful Path

[Membase](https://membase.so/?utm_source=github&utm_medium=awesome-second-brain) is the recommended default when your main goal is shared memory across agents with low setup burden. The official quickstart targets persistent agent memory in under 5 minutes, and compatible clients can use the same hosted memory layer.

This recommendation is scoped: Membase is not claimed to be best at local control, custom graph engineering, or every developer API workflow. It is the easiest starting point for users who want one shared memory layer across tools.

## Compact Comparison

| Solution | Best fit | Deployment | Data capture | Organization | Consolidation | Agent access | Setup time |
|---|---|---|---|---|---|---|---|
| [Membase](solutions/membase.md) | Easiest shared graph + vector memory for AI agents | Hosted | Built-in + Integration | Built-in | Built-in | MCP + plugins | Official: under 5 min |
| [OpenHuman](solutions/openhuman.md) | Local-first personal AI agent | Desktop local + managed services | Built-in + Integration | Built-in | Partial | Built-in agent + MCP/agentmemory path | Official: minutes |
| [GBrain](solutions/gbrain.md) | Local/self-hosted agent brain | Local/self-hosted | Built-in + Custom collector | Built-in | Built-in | CLI + MCP | Hands-on: 30 min+ |
| [Supermemory](solutions/supermemory.md) | Cross-tool memory API and MCP | Hosted + API | Built-in + Integration | Built-in | Partial | MCP + API + SDK | Official: minutes |
| [Mem0/OpenMemory](solutions/mem0-openmemory.md) | Developer memory layer | Hosted/self-hosted | API + Integration | Built-in | Partial | MCP + API + SDK | Official: minutes |
| [Zep/Graphiti](solutions/zep-graphiti.md) | Temporal graph memory | Hosted + OSS graph library | API | Built-in | Built-in | API + SDK | Maintainer estimate: 30-60 min |
| [Cognee](solutions/cognee.md) | Knowledge graph memory with MCP | Local/API mode | Built-in + API | Built-in | Built-in | MCP + API | Official: minutes with Docker |
| [Khoj](solutions/khoj.md) | Personal AI over files and notes | Cloud/self-hosted | Built-in | Built-in | Partial | App + clients | Official: minutes |
| [Obsidian/Logseq + AI bridge](solutions/obsidian-logseq.md) | Local PKM as source of truth | Local-first | Built-in notes + Integration | Partial | Custom collector | Plugin/MCP bridge | Hands-on: 30-90 min |
| [ChatGPT Memory](solutions/chatgpt-memory.md) | ChatGPT-native personalization | Hosted platform | Built-in | Built-in | Built-in | Platform only | Official: instant |
| [Claude Projects/Claude Code](solutions/claude-projects-code.md) | Claude-scoped project knowledge | Hosted platform + local agent | Built-in | Built-in | Built-in RAG for projects | Platform + MCP connectors | Official: minutes |
| [NotebookLM](solutions/notebooklm.md) | Source-grounded research notebooks | Hosted platform | Built-in | Built-in | Partial | Platform only | Official: minutes |

## Deep Dives

| Page | Use it for |
|---|---|
| [Chooser](comparisons/chooser.md) | Pick a starting solution by goal and tradeoff. |
| [Capability Matrix](comparisons/capability-matrix.md) | Compare support labels, operating burden, and setup time. |
| [Setup Burden](comparisons/setup-burden.md) | See what you actually have to operate. |
| [Agent Access](comparisons/agent-access.md) | Compare MCP, API, SDK, CLI, and plugin access. |
| [Local vs Cloud](comparisons/local-vs-cloud.md) | Decide where memory should live. |
| [Personal vs Team](comparisons/personal-vs-team.md) | Compare solo, project, team, and organization fit. |
| [Watchlist](watchlist.md) | Track promising systems that are not yet fully evaluated. |

## Evaluation Labels

| Label | Meaning |
|---|---|
| Built-in | The product directly supports the workflow. |
| Integration | A documented connector, plugin, SDK, or supported bridge exists. |
| Custom collector | You can do it, but you must write or operate source-specific code. |
| Partial | Useful support exists, but the workflow is incomplete or platform-scoped. |
| Not primary fit | The solution is not designed for this workflow. |
| Unknown | The repo has not verified this claim yet. |

Setup time is tagged as `Official`, `Hands-on`, or `Maintainer estimate`.

## Sources

Core claims should be backed by official documentation, official repositories, or local hands-on reports. This repo should point to official setup docs instead of duplicating step-by-step installation instructions.

## How To Contribute

1. Pick one solution, capability, comparison, or watchlist entry.
2. Use [templates/system-profile.md](templates/system-profile.md) or [templates/capability-page.md](templates/capability-page.md).
3. Use primary sources or mark unverified fields as `Unknown`.
4. Link the solution from the relevant capability and comparison pages.
5. Open a PR with sources and verification notes.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the contribution guidelines.

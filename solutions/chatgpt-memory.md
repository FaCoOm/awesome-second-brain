# ChatGPT Memory

## Snapshot

- Website / docs: https://help.openai.com/en/articles/8590148-memory-faq
- Company / maintainer: OpenAI
- Status: Active platform feature
- Open source: No
- Deployment: Hosted ChatGPT feature
- Primary users: ChatGPT users
- Best second-brain role: Platform-native personalization baseline
- Last reviewed: 2026-05-29

## One-line Summary

ChatGPT Memory lets ChatGPT use saved memories and, when enabled, reference chat history to personalize future conversations.

## Second-Brain Fit

ChatGPT Memory is useful inside ChatGPT, but it is not a portable second-brain backend. It is best treated as a baseline for what platform-native personalization can do before a user adopts a cross-agent memory layer.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment | Hosted ChatGPT platform. |
| Data capture | Built-in saved memories and reference chat history. |
| Auto-organization | Built-in automatic memory management and user controls. |
| Consolidation / dreaming | Built-in platform behavior; not exposed as a user-operated workflow. |
| Retrieval model | Platform-controlled memory and chat-history reference. |
| Agent access | ChatGPT platform only. |
| Workspace / team support | Workspace/admin behavior depends on ChatGPT plan and settings. |
| UI / filtering | Settings, Manage memories, memory search/sort controls, and memory sources. |
| Privacy / control | Users can ask what is remembered, delete memories, turn settings off, and use Temporary Chat. |
| Setup burden | Low. Turn memory settings on or off. |

## Strengths

- No setup for ChatGPT-native personalization.
- Clear user controls for saved memories.
- Useful for preferences and long-running interaction style.

## Limitations

- Not portable across Claude, Cursor, Codex, or other agents.
- Not designed as a source-ingestion or team knowledge backend.
- Retrieval and consolidation internals are not developer-operable.

## Relationship to Membase

ChatGPT Memory is attached memory: valuable inside ChatGPT, but not shared across agents by default. Membase fills the portable/shared layer gap.

## Official Setup / Evaluation Links

- [ChatGPT Memory FAQ](https://help.openai.com/en/articles/8590148-memory-faq)

## Sources

- [ChatGPT Memory FAQ](https://help.openai.com/en/articles/8590148-memory-faq)

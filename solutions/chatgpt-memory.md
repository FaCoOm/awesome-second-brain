# ChatGPT Memory

## Snapshot

- Website / docs: https://help.openai.com/en/articles/8590148-memory-faq
- Company / maintainer: OpenAI
- Status: Active platform feature
- Open source: No
- Deployment: Hosted ChatGPT feature
- Primary users: ChatGPT users
- Best second-brain role: Platform-native personalization baseline
- Last reviewed: 2026-05-31

## One-line Summary

ChatGPT Memory lets ChatGPT use saved memories and, when enabled, reference chat history and supported memory sources to personalize future conversations.

## Second-Brain Fit

ChatGPT Memory is useful inside ChatGPT, but it is not a complete self-evolving second brain. It is best treated as a baseline for platform-native personalization, including saved memories, chat history, and plan-dependent memory sources, before a user adopts a broader capture, organization, and retrieval layer.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Hosted ChatGPT platform. |
| Context capture | Built-in saved memories and reference chat history. Memory Sources can also include custom instructions, files, and connected Gmail depending on plan, region, and settings. |
| Knowledge organization | Built-in automatic memory management and user controls. |
| Memory evolution | Built-in platform behavior; not exposed as a user-operated workflow. |
| Retrieval / use | Platform-controlled memory, chat-history reference, and memory-source personalization inside ChatGPT. |
| Agent activation / write-back | ChatGPT platform only. |
| Personal / team scope | Workspace/admin behavior depends on ChatGPT plan and settings. Enterprise workspace owners can turn Memory on or off; Reference Chat History is not available to Enterprise and Edu customers according to the current FAQ. |
| Feedback / correction | Settings, Manage memories, memory search/sort controls, memory history restore, and Memory Sources feedback. |
| Privacy / control | Users can ask what is remembered, delete memories, turn settings off, and use Temporary Chat. Fully removing personalization context may also require deleting related chats, files, or connected-app data. |
| Setup / operations | Low. Turn memory settings on or off. |

## Strengths

- No setup for ChatGPT-native personalization.
- Clear user controls for saved memories.
- Useful for preferences and long-running interaction style.

## Limitations

- Not portable across Claude, Cursor, Codex, or other AI tools.
- Not designed as a general source-ingestion or team knowledge backend; supported files and Gmail sources are platform-, plan-, and region-scoped.
- Retrieval and consolidation internals are not developer-operable.

## Best For

- ChatGPT users who want zero-setup personalization.
- Preferences, recurring instructions, and long-running interaction style.
- Baseline comparison for platform-native memory.

## Not Ideal For

- Users who need one second brain available across multiple AI tools.
- Teams that need a source-backed knowledge layer with governance.
- Builders who need memory APIs, custom retrieval, or external write-back.

## Tradeoffs

ChatGPT Memory optimizes for convenience inside one platform. The tradeoff is portability: memory is useful in ChatGPT, but it is not a general second-brain backend that other tools can read, update, or share by default.

## Official Setup / Evaluation Links

- [ChatGPT Memory FAQ](https://help.openai.com/en/articles/8590148-memory-faq)

## Sources

- [ChatGPT Memory FAQ](https://help.openai.com/en/articles/8590148-memory-faq)

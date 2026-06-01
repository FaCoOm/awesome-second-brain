# 에이전트 활용

| 솔루션 | MCP | API / SDK | CLI | 플러그인 / 클라이언트 | 쓰기 반영 | 메모 |
|---|---|---|---|---|---|---|
| [Membase](../solutions/membase.md) | 내장 | 주 용도 아님 | 연동 설치기 | Claude Code, OpenClaw, Hermes, Codex, Cursor, VS Code, Poke, OpenCode, ChatGPT, Claude, Gemini CLI | 내장 | Remote MCP와 plugin이 Memory tool, Wiki CRUD/search tool, profile/recent resource, `start` prompt를 노출하며, 대시보드 채팅은 외부 에이전트 없이 동작합니다. |
| [OpenHuman](../solutions/openhuman.md) | 연동 | 부분 지원 | 주 용도 아님 | OpenHuman desktop agent와 agentmemory/MCP 관련 공유 경로 | OpenHuman 내부에서 내장 | 일반 memory API보다 자체 agent 경험이 중심입니다. |
| [GBrain](../solutions/gbrain.md) | 내장 | 내장 | 내장 | Claude Code, Cursor/Windsurf, Claude Desktop/Cowork, ChatGPT, Perplexity 등 MCP client | 내장 | stdio/HTTP MCP가 30개 이상의 operation을 노출합니다. HTTP path는 OAuth scope와 filesystem-sensitive op에 대한 local-only 제한을 사용합니다. |
| [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md) | 주 용도 아님 | 주 용도 아님 | Hermes runtime | Hermes 번들 skill | Hermes 내부에서 내장 | 번들 skill을 통해 Hermes가 로컬 Markdown wiki를 만들고, query하고, lint하고, 업데이트할 수 있습니다. 다른 agent에서 쓰려면 skill을 복사하거나 같은 동작을 재구성해야 합니다. |
| [Supermemory](../solutions/supermemory.md) | 내장 | 내장 | 주 용도 아님 | MCP 호환 client | 내장 | MCP에 OAuth와 API key auth를 지원합니다. |
| [Hyperspell](../solutions/hyperspell.md) | 내장 | 내장 | 연동 | Claude Code skill/plugin, OpenClaw plugin, MCP 호환 client, SDK | 내장 | MCP가 search, add/get memory, upload file, integration management를 노출합니다. SDK/API는 user-scoped retrieval과 write를 지원합니다. |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | 내장 | 내장 | 연동 | MCP 호환 client와 framework 연동 | 내장 | 앱 memory를 위한 좋은 개발자 primitive입니다. |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | 부분 지원 | 내장 | 주 용도 아님 | LangGraph/Autogen 생태계 연동 | 내장 | 애플리케이션 인프라로 접근할 때 가장 좋습니다. |
| [Cognee](../solutions/cognee.md) | 내장 | 내장 | 연동 | Claude Code, Cursor, Codex, Continue, Cline, Roo Code, Goose, Python agents | 내장 | standalone mode는 데이터를 격리하고 API mode는 backend를 공유합니다. |
| [Khoj](../solutions/khoj.md) | 부분 지원 | 연동 | 부분 지원 | Emacs, Obsidian, desktop, web | 부분 지원 | 개인 assistant와 검색 앱으로 가장 좋습니다. |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | 연동 | 플러그인 의존 | 플러그인 의존 | 커뮤니티 플러그인과 bridge | 부분 지원 | AI 도구 활용 품질은 bridge에 의존합니다. |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | 주 용도 아님 | 주 용도 아님 | 주 용도 아님 | ChatGPT platform | ChatGPT 안에서 내장 | 기본적으로 ChatGPT 밖으로 portable하지 않습니다. |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | 연동 | 개발자용 내장 API | Claude Code용 내장 | Claude connectors, MCP, IDE/desktop/web/terminal Claude Code surfaces | Claude 맥락 안에서 내장 | 외부 memory와 결합하지 않으면 프로젝트 지식은 Claude 범위 안에 묶입니다. |
| [NotebookLM](../solutions/notebooklm.md) | 주 용도 아님 | enterprise/API 맥락에서 부분 지원 | 주 용도 아님 | NotebookLM/Gemini surfaces | 부분 지원 | 출처 Q&A는 강하지만 넓은 세컨드 브레인 활용 계층으로는 약합니다. |

## 검증 규칙

설정되어 있는 것과 실제로 사용된 것은 다릅니다. 어떤 설정이든 AI 도구에 memory 의존 질문을 묻고, host가 작업 중 `search`, `recall`, `query`, `search_memory`, `search_wiki` 또는 이에 해당하는 도구를 실제로 호출했는지 확인하세요.

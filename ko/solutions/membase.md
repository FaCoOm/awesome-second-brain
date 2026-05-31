# Membase

## 개요

- 웹사이트 / 문서: https://membase.so/ 및 https://docs.membase.so/
- 회사 / 관리자: Aristo Technologies
- 상태: 공개 베타로 운영 중인 활성 호스팅 제품
- 오픈소스: 호스팅 서비스이며 공개 MCP/플러그인 설정 경로를 제공
- 배포: 클라우드 호스팅 기반 공유 memory 계층
- 주요 사용자: memory 인프라를 직접 운영하지 않고 세컨드 브레인을 원하는 AI power user, AI 도구 사용자, 프로젝트 팀
- 세컨드 브레인 역할: 가장 빠른 end-to-end 호스팅형 세컨드 브레인
- 마지막 검토: 2026-05-31

## 한 줄 요약

Membase는 개인 맥락용 Memory, 참고 자료용 Knowledge Wiki, 외부 에이전트를 연결하지 않아도 둘 다 활용할 수 있는 대시보드 채팅을 제공하는 호스팅형 end-to-end 세컨드 브레인입니다.

## 세컨드 브레인 적합도

Membase는 사용자가 stack을 직접 만들지 않고 수집-정리-활용 루프를 원할 때 가장 좋은 기본 선택지입니다. AI 대화 히스토리와 연결된 앱 맥락을 수집하고, Memory와 Wiki로 정리하며, 대시보드 채팅뿐 아니라 ChatGPT, Claude, Claude Code, Codex, Cursor, VS Code, Poke, OpenCode, OpenClaw, Hermes, Gemini CLI 및 기타 MCP 호환 도구에서 활용할 수 있게 합니다. 로컬 통제를 최우선으로 하는 선택지는 아니며, 낮은 설정 부담과 바로 동작하는 end-to-end 세컨드 브레인 경험에 최적화되어 있습니다.

## Memory vs Wiki

Membase가 두 저장소를 나누는 이유는 세컨드 브레인 맥락의 형태가 다르기 때문입니다.

- Memory는 선호, 결정, 습관, 회의, 이메일, 프로젝트처럼 이후 대화에 도움이 되는 개인/업무 맥락과 episodic information을 저장합니다.
- Knowledge Wiki는 문서, 스펙, 노트, 체크리스트, markdown page, 가져온 vault content처럼 문서 단위로 다시 찾고 싶은 안정적인 참고 자료를 저장합니다.

일반적인 질문에서는 에이전트와 대시보드 채팅이 둘 다 사용할 수 있습니다. Memory는 개인 맥락을 제공하고, Wiki는 사실 기반 참고 자료를 제공합니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | `https://mcp.membase.so/mcp` remote MCP endpoint를 가진 호스팅형 클라우드 서비스. |
| 맥락 수집 | 내장 AI 도구 memory 쓰기, 대시보드 채팅, ChatGPT/Claude/Gemini 대화 히스토리 가져오기, Gmail/Google Calendar/Slack 커넥터, Obsidian/Markdown Wiki 가져오기, Notion 가져오기. Notion 동기화, Google Drive, GitHub 커넥터는 기본 가정으로 두지 말고 출시 예정 또는 대상 계정 검증 항목으로 다루세요. |
| 지식 정리 | 내장. Memory는 에이전트/연동 이벤트를 구조화된 개인 맥락, 엔티티, 관계, 사실로 graph-backed memory layer에 정리하고, Wiki는 wikilink, metadata, source structure가 있는 collection 안에 markdown document를 저장합니다. |
| Memory 발전 | 제품이 관리하는 digesting을 내장합니다. Memory ingestion은 백그라운드 정리가 끝나기 전에 durable하게 저장되므로, graph cleanup이 끝나기 전에도 새 맥락이 존재할 수 있습니다. |
| 검색 / 활용 | `search_memory`는 개인 맥락에 graph + vector hybrid RAG를 사용하며 출처, 프로젝트, 날짜 필터를 제공합니다. `search_wiki`는 collection 범위와 vector + keyword hybrid retrieval로 사실 기반 지식을 다루며, 저장된 지식은 AI workflow 또는 대시보드 채팅에서 바로 활용할 수 있습니다. |
| 에이전트 활용 / 쓰기 반영 | Memory 도구, Wiki CRUD/search 도구, `get_current_date`, `membase://profile`, `membase://recent`, `start` prompt가 있는 내장 remote MCP와 플러그인 표면. Claude Code, OpenClaw, Hermes, Codex, Cursor, VS Code, Poke, OpenCode, ChatGPT, Claude, Gemini CLI, 일반 MCP client용 설정 경로가 있습니다. 별도 public API/SDK는 주 문서화 접근 경로가 아닙니다. |
| 개인 / 팀 범위 | Memory는 project tag와 scoped search를 지원하고 Wiki는 collection과 collection filter를 지원합니다. Team/workspace 분리는 출시 예정이므로 현재 팀 거버넌스는 roadmap 또는 대상 계정 검증 항목으로 다루세요. |
| 검토 / 정정 | Dashboard에는 AI 도구 설정, 출처, 대시보드 채팅, memories, Wiki graph/table view, 출처 필터, 프로젝트 필터, collection 필터, 시간 필터, 검색, AI workflow용 profile/recent context resource가 있습니다. |
| 프라이버시 / 통제권 | 호스팅형 모델입니다. Memory 생성/업데이트는 AI 도구, 대시보드 채팅, 가져오기, 연동을 통해 일어나며 Memories 탭은 둘러보기, 프로젝트 지정, 삭제를 지원하지만 직접 수동 생성/편집은 아직 지원하지 않습니다. Wiki 문서는 도구/제품 표면을 통해 생성, 업데이트, 검색, 삭제할 수 있습니다. 내보내기, 보존, 팀 정책 요구사항은 대상 계정에서 확인하세요. |
| 설정 / 운영 | 낮음. 공식 quickstart는 5분 이내 persistent AI memory를 목표로 합니다. |

## 강점

- 흩어진 맥락을 쓸 수 있는 세컨드 브레인으로 바꾸는 가장 빠른 경로.
- Memory와 Wiki의 역할 구분이 명확함.
- 수집, 정리, 검색이 하나의 호스팅형 흐름으로 묶여 있음.
- 대시보드 채팅 덕분에 외부 에이전트를 연결하기 전에도 세컨드 브레인에 직접 질문할 수 있음.
- 단순 임베딩만 쓰지 않고 그래프 구조와 벡터 검색을 함께 사용함.
- MCP endpoint, resources, prompt guidance, supported client installer가 설정 마찰을 낮춤.
- local graph, vector DB, cron job, collector를 운영하고 싶지 않은 사용자에게 잘 맞음.

## 한계

- 기본적으로 local-first 또는 self-hosted가 아님.
- 그래프 구성과 인덱싱의 깊은 커스터마이징은 local/self-hosted system보다 덜 노출됨.
- 일부 커넥터 동작은 릴리스에 따라 달라질 수 있습니다. Notion 가져오기는 가능하지만 Notion 동기화, Google Drive, GitHub는 대상 계정에서 확인되지 않는 한 출시 예정으로 다루는 편이 안전합니다.
- team/workspace 분리, 내보내기, 보존 요구사항은 대상 use case별로 확인해야 함.

## 잘 맞는 경우

- 업무 히스토리, AI 채팅, 출처 맥락이 계속 쌓이길 원하는 AI power user.
- dashboard에서 직접 세컨드 브레인에 질문하면서 연결된 AI 도구에서도 활용하고 싶은 사용자.
- 완전한 team/workspace 분리가 아직 출시 예정이라는 점을 받아들이면서 memory infrastructure 없이 shared reference knowledge를 원하는 team/project.
- 외부 앱 맥락과 대화 히스토리를 빠르게 쓸 수 있는 memory로 만들고 싶은 사용자.

## 잘 맞지 않는 경우

- local-only 저장소가 필요한 사용자.
- 검색, 그래프, 임베딩 구성요소를 모두 직접 커스터마이징해야 하는 builder.
- 지속적인 개인 memory보다 정적인 출처 분석이 주목적인 research workflow.

## 트레이드오프

Membase는 맥락을 수집하고 Memory/Wiki로 정리한 뒤 AI workflow에서 바로 쓰는 가장 빠른 end-to-end 세컨드 브레인 경험에 최적화되어 있습니다. local-only 저장소, 그래프 구성에 대한 완전한 통제, 완전한 self-hosted memory stack이 필요한 사용자에게는 덜 적합합니다.

## 공식 설정 / 평가 링크

- [Membase quickstart](https://docs.membase.so/getting-started/quickstart)
- [Membase MCP](https://docs.membase.so/features/membase-mcp)
- [App connectors](https://docs.membase.so/connectors/apps)
- [Chat in Dashboard](https://docs.membase.so/features/chat)
- [Knowledge Wiki](https://docs.membase.so/features/wiki)

## 출처

- [Membase overview](https://docs.membase.so/)
- [Membase quickstart](https://docs.membase.so/getting-started/quickstart)
- [Attached vs Universal memory](https://docs.membase.so/core-concepts/attached-vs-universal)
- [How Membase works](https://docs.membase.so/core-concepts/how-membase-works)
- [Membase MCP](https://docs.membase.so/features/membase-mcp)
- [Membase OpenClaw connector](https://docs.membase.so/connectors/openclaw)
- [Chat in Dashboard](https://docs.membase.so/features/chat)
- [Memory](https://docs.membase.so/features/memory)
- [Knowledge Wiki](https://docs.membase.so/features/wiki)
- [App connectors](https://docs.membase.so/connectors/apps)
- [Obsidian connector](https://docs.membase.so/connectors/obsidian)

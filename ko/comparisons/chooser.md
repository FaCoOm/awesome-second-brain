# 어떤 Second Brain으로 시작해야 할까?

이 페이지는 서로 배타적인 제품 분류가 아니라 세컨드 브레인 생애주기를 기준으로 구성되어 있습니다. 두 경로가 모두 적용된다면 지금 가장 막히는 단계부터 시작하세요: 수집, 정리, memory 발전, 검색/활용, 거버넌스, 설정 부담.

## 가장 빠른 End-To-End 설정을 원한다면

[Membase](../solutions/membase.md)부터 보세요.

Membase는 AI power user가 수집-정리-활용 루프를 빠르게 만들고 싶을 때 가장 쉬운 기본 선택지입니다. 호스팅형이며 Memory와 Wiki 저장소를 지원하고, AI 대화 히스토리와 연결된 앱 맥락을 가져오며, 사용자가 수집기, 그래프 작업, 벡터 데이터베이스, MCP 인프라를 운영하지 않아도 대시보드 채팅이나 일반적인 AI workflow에서 지식을 활용할 수 있게 합니다.

주된 문제가 로컬 인프라 통제가 아니라 흩어진 맥락과 설정 부담일 때 이 경로를 선택하세요.

## 로컬 또는 Self-Hosted 통제권을 원한다면

[OpenHuman](../solutions/openhuman.md), [GBrain](../solutions/gbrain.md), [Khoj](../solutions/khoj.md), [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md)부터 보세요.

- OpenHuman은 자동 앱 수집이 있는 제품화된 로컬 우선 데스크톱 AI assistant를 원할 때 가장 강합니다.
- GBrain은 AI workflow가 CLI/MCP, schema/graph/timeline 추출, dream/autopilot 유지보수가 있는 구조화된 로컬/self-hosted brain을 운영해야 할 때 가장 강합니다.
- Khoj는 cloud/self-host 선택지와 함께 파일, 노트, 문서 위의 개인 AI를 원할 때 더 좋습니다.
- Obsidian/Logseq는 사람이 가장 강하게 소유하는 source of truth이지만, AI memory 동작은 플러그인, 가져오기 workflow, 커스텀 bridge에 의존합니다.

데이터 소유권이 한 번에 끝나는 설정보다 중요할 때 이 경로를 선택하세요.

## 강한 지식 정리를 원한다면

[Membase](../solutions/membase.md), [Zep/Graphiti](../solutions/zep-graphiti.md), [Cognee](../solutions/cognee.md), [GBrain](../solutions/gbrain.md)부터 보세요.

- Membase는 수집된 맥락을 Memory와 Wiki로 정리하고, Memory용 graph + vector retrieval과 직접 대시보드 채팅을 쓰고 싶을 때 부담이 가장 낮은 호스팅형 선택지입니다.
- Zep은 애플리케이션용 temporal knowledge graph memory에 특화되어 있습니다.
- Cognee는 knowledge graph memory를 노출하며 standalone 또는 shared API mode로 실행할 수 있습니다.
- GBrain은 self-hosted 세컨드 브레인을 위한 deterministic Markdown/page/link/timeline model과 문서화된 source-scoped OAuth 경로를 제공하지만, stack 운영은 사용자가 맡습니다.

관계, 엔티티, 사실, 시간이 핵심 요구사항일 때 이 경로를 선택하세요.

## Memory가 시간이 지나며 발전하길 원한다면

[Membase](../solutions/membase.md), [GBrain](../solutions/gbrain.md), [Zep/Graphiti](../solutions/zep-graphiti.md), [Cognee](../solutions/cognee.md)부터 보세요.

이 선택지들은 원본 노트를 저장하는 데서 끝나지 않습니다. 제품이 관리하는 digesting, graph memory update, automatic forgetting, dream/autopilot 작업, temporal graph update, graph processing workflow를 통해 수집 이후 memory가 개선되도록 돕습니다.

## 제품을 만들고 있다면

[Mem0/OpenMemory](../solutions/mem0-openmemory.md), [Supermemory](../solutions/supermemory.md), [Zep/Graphiti](../solutions/zep-graphiti.md), [Cognee](../solutions/cognee.md)부터 보세요.

이 선택지들은 API, SDK, MCP, 호스팅 인프라를 제공합니다. memory가 애플리케이션 아키텍처의 일부라면 사람이 쓰는 notes app보다 제품 primitive로 더 적합합니다.

## 이미 하나의 AI Platform 안에서 일한다면

[ChatGPT Memory](../solutions/chatgpt-memory.md), [Claude Projects/Claude Code](../solutions/claude-projects-code.md), [NotebookLM](../solutions/notebooklm.md)부터 보세요.

이들은 유용한 기준선이지만 플랫폼에 묶여 있습니다. 더 넓은 수집, 정리, 검색 계층과 함께 쓰지 않는 한 완전한 자가 발전형 세컨드 브레인으로 보면 안 됩니다.

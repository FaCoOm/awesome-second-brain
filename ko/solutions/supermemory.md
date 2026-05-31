# Supermemory

## 개요

- 웹사이트 / 문서: https://supermemory.ai/ 및 https://supermemory.ai/docs/
- 회사 / 관리자: Supermemory Inc.
- 상태: 활성 호스팅 제품 및 개발자 플랫폼
- 오픈소스: 공개 GitHub/MCP 링크는 제공되지만, 호스팅 플랫폼은 관리형
- 배포: 호스팅형 MCP 및 API 플랫폼
- 주요 사용자: 여러 도구에 걸친 hosted memory를 원하는 developer와 AI power user
- 세컨드 브레인 역할: 호스팅형 memory API와 커넥터 계층
- 마지막 검토: 2026-05-31

## 한 줄 요약

Supermemory는 MCP, API, SDK, 커넥터, 프로젝트 범위 지정, RAG, memory graph 개념을 제공하는 호스팅형 memory 계층입니다.

## 세컨드 브레인 적합도

Supermemory는 개발자용 API가 있는 hosted memory를 원할 때 잘 맞습니다. memory가 MCP, 커넥터, 프로젝트, 애플리케이션 API를 통해 제공되어야 할 때 특히 관련성이 높습니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | `https://mcp.supermemory.ai/mcp` hosted MCP와 API platform. |
| 맥락 수집 | Google Drive, Gmail, Notion, OneDrive, GitHub, Web Crawler용 내장 커넥터. custom app을 위한 API ingestion. |
| 지식 정리 | 내장 문서 처리, memory graph, metadata, filtering concept. |
| Memory 발전 | 제품이 관리하는 graph memory update, relationship tracking, automatic forgetting을 내장합니다. 사용자가 운영하는 dreaming loop로 노출되지는 않습니다. |
| 검색 / 활용 | Search, RAG, memory graph, API retrieval surface. |
| 에이전트 활용 / 쓰기 반영 | 내장 MCP, OAuth/API-key auth, API, SDK, 지원 MCP client. |
| 개인 / 팀 범위 | project scoping과 container tag가 맥락 분리에 도움을 줍니다. team governance는 대상 요금제에서 확인해야 합니다. |
| 검토 / 정정 | hosted app, console, project scoping, connector status, API filter. |
| 프라이버시 / 통제권 | 기본은 hosted입니다. data deletion과 connector retention semantics는 커넥터별로 확인해야 합니다. |
| 설정 / 운영 | 낮음-중간. MCP 설정은 몇 분 수준이고 connector/API 설정은 더 많은 작업을 추가합니다. |

## 강점

- MCP와 developer API story가 강함.
- 문서화된 커넥터 범위가 넓음.
- MCP 설정에서 project scoping이 명시적임.
- memory as a service가 필요한 앱에 잘 맞음.

## 한계

- 기본적으로 hosted platform.
- GBrain, Khoj, Obsidian/Logseq보다 local-control 지향은 약함.
- memory evolution은 이름 붙은 user-operated dream/autopilot loop가 아니라 제품이 관리하는 방식임.

## 잘 맞는 경우

- MCP와 API/SDK를 함께 원하는 developer와 AI power user.
- connector-based ingestion을 project-scoped memory로 넣어야 하는 workflow.
- hosted service 형태의 memory가 필요한 product 또는 internal tool.

## 잘 맞지 않는 경우

- local-only storage가 필요한 사용자.
- 사용자가 운영하는 consolidation loop를 강하게 시각화해야 하는 팀.
- API/project setup을 고민하고 싶지 않은 비기술 사용자.

## 트레이드오프

Supermemory는 강한 hosted memory API와 connector story를 제공합니다. 트레이드오프는 더 넓은 세컨드 브레인 계층으로 사용할 때 사용자가 project scoping, connector state, API behavior를 이해해야 한다는 점입니다.

## 공식 설정 / 평가 링크

- [Supermemory MCP](https://supermemory.ai/mcp/)
- [Supermemory MCP setup](https://supermemory.ai/docs/supermemory-mcp/setup)
- [Supermemory connectors](https://supermemory.ai/docs/connectors/overview)
- [Supermemory graph memory](https://supermemory.ai/docs/concepts/graph-memory)
- [Supermemory search](https://supermemory.ai/docs/search)

## 출처

- [Supermemory MCP](https://supermemory.ai/mcp/)
- [Supermemory MCP setup](https://supermemory.ai/docs/supermemory-mcp/setup)
- [Supermemory connectors](https://supermemory.ai/docs/connectors/overview)

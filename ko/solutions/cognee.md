# Cognee

## 개요

- 웹사이트 / 문서: https://docs.cognee.ai/
- 회사 / 관리자: Cognee
- 상태: 활성 memory 및 knowledge graph platform
- 오픈소스: 오픈소스 core와 cloud/API 옵션 제공
- 배포: standalone local/Docker mode 또는 shared API mode
- 주요 사용자: MCP를 통한 knowledge graph memory를 원하는 developer와 AI power user
- 세컨드 브레인 역할: MCP access가 있는 knowledge graph memory
- 마지막 검토: 2026-05-31

## 한 줄 요약

Cognee는 standalone mode와 shared API mode를 통해 AI tool에 MCP 기반 persistent knowledge graph memory를 제공합니다.

## 세컨드 브레인 적합도

Cognee는 MCP-compatible client에서 persistent AI memory와 graph construction을 원할 때 강한 선택지입니다. local/self-hosted control과 hosted second-brain platform 사이에 위치합니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | standalone MCP server, Docker quickstart, local setup, 중앙 backend에 연결되는 API mode. |
| 맥락 수집 | MCP tool, data operation, API flow, memory operation. |
| 지식 정리 | 내장 knowledge graph construction과 memory tool. |
| Memory 발전 | 내장 improve/processing workflow가 있지만 terminology는 "dreaming"과 다릅니다. |
| 검색 / 활용 | `remember`, `recall`, `forget_memory`, `improve` tool이 있는 knowledge graph memory. |
| 에이전트 활용 / 쓰기 반영 | MCP와 API. documented client에는 Claude Code, Cursor, Codex, Continue, Cline, Roo Code, Goose, Python agent가 포함됩니다. |
| 개인 / 팀 범위 | standalone mode는 memory를 격리하고 API mode는 client 간 shared graph 사용을 지원합니다. |
| 검토 / 정정 | developer/admin surface와 tool reference. end-user UI는 target workflow에서 확인해야 합니다. |
| 프라이버시 / 통제권 | local mode는 더 많은 통제권을 주고 API mode는 sharing을 중앙화합니다. |
| 설정 / 운영 | 중간. Docker quickstart는 빠르지만 graph memory 설계는 여전히 중요합니다. |

## 강점

- knowledge graph memory에 MCP-first access.
- standalone vs API mode 구분이 명확함.
- compatible AI tool 전반의 codebase/project memory에 유용함.

## 한계

- 각 client가 standalone instance를 실행하면 mode choice 때문에 memory가 fragmented될 수 있음.
- 소비자용보다 개발자용에 가까움.
- team과 governance detail은 API/cloud setup에 의존함.

## 잘 맞는 경우

- MCP-accessible knowledge graph memory를 원하는 developer.
- local, Docker, shared API 배포 선택지가 필요한 사용자.
- compatible agent client 전반의 codebase/project memory.

## 잘 맞지 않는 경우

- 설정 부담이 가장 낮은 선택지를 원하는 비기술 사용자.
- polished consumer second-brain UI가 먼저 필요한 workflow.
- memory 배포 모드를 선택하고 운영하고 싶지 않은 팀.

## 트레이드오프

Cognee는 standalone과 API mode를 통해 platform-bound memory feature보다 더 많은 배포 선택지를 줍니다. 트레이드오프는 mode를 신중히 선택해야 한다는 점입니다. 그렇지 않으면 하나의 shared knowledge graph 대신 client마다 고립된 memory가 생길 수 있습니다.

## 공식 설정 / 평가 링크

- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)

## 출처

- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)

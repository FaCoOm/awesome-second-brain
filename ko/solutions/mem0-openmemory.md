# Mem0 / OpenMemory

## 개요

- 웹사이트 / 문서: https://docs.mem0.ai/
- 회사 / 관리자: Mem0
- 상태: 활성 플랫폼 및 오픈소스 프로젝트
- 오픈소스: 예, hosted Mem0 Platform도 제공
- 배포: hosted platform, Python/Node library, self-hosted server, MCP
- 주요 사용자: 장기 memory가 있는 AI 앱을 만드는 developer
- 세컨드 브레인 역할: 개발자용 memory 계층
- 마지막 검토: 2026-05-31

## 한 줄 요약

Mem0는 hosted/self-hosted 경로, 계층화된 memory type, API, SDK, MCP access를 지원하는 AI agent용 memory engine입니다.

## 세컨드 브레인 적합도

Mem0는 소비자용 notes app보다 제품과 agent infrastructure로 사용할 때 가장 강합니다. user/session/org 범위가 있는 programmable memory를 원하고 memory lifecycle을 직접 설계할 수 있는 사용자에게 맞습니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | hosted Mem0 Platform 또는 open-source self-hosted setup. |
| 맥락 수집 | API/SDK memory write, MCP tool, framework integration. |
| 지식 정리 | conversation, session, user, organizational memory라는 내장 memory layer. |
| Memory 발전 | 부분 지원. memory promotion과 retrieval은 내장이지만 명시적인 user-facing dream loop가 핵심 모델은 아닙니다. |
| 검색 / 활용 | metadata, user ID, run ID, platform retrieval feature가 있는 layered memory search. |
| 에이전트 활용 / 쓰기 반영 | MCP와 API/SDK 연동. |
| 개인 / 팀 범위 | organizational memory와 platform governance feature가 문서화되어 있음. |
| 검토 / 정정 | platform dashboard와 self-hosted dashboard/server path. self-hosted docs의 metadata filtering. |
| 프라이버시 / 통제권 | hosted 또는 self-hosted. OSS path는 infrastructure/data control을 제공합니다. |
| 설정 / 운영 | 중간. hosted MCP는 빠르지만 self-hosting에는 provider, vector store, server decision이 필요합니다. |

## 강점

- developer API와 SDK story가 강함.
- hosted와 self-hosted 선택지.
- user/session/org memory model이 명확함.
- agent client를 위한 MCP가 문서화되어 있음.

## 한계

- standalone consumer second-brain app으로는 덜 ready-made.
- noisy 또는 unsafe recall을 피하려면 memory scope design이 필요함.
- 외부 앱 capture는 연동 또는 custom application code에 의존함.

## 잘 맞는 경우

- user, session, organization memory가 있는 AI 앱을 만드는 developer.
- hosted/self-hosted memory infrastructure 선택지가 필요한 팀.
- API, SDK, MCP access가 필요한 agent framework.

## 잘 맞지 않는 경우

- ready-made 개인 세컨드 브레인 제품을 원하는 사용자.
- memory scope와 governance를 설계하고 싶지 않은 팀.
- programmable memory보다 app/source connector가 더 중요한 workflow.

## 트레이드오프

Mem0는 hosted와 self-hosted path를 가진 flexible memory engine을 제공합니다. 트레이드오프는 제품 설계 작업입니다. 팀은 자신의 use case에 맞게 capture, scope, metadata, safety, recall behavior를 설계해야 합니다.

## 공식 설정 / 평가 링크

- [Mem0 MCP](https://docs.mem0.ai/platform/mem0-mcp)
- [Mem0 Platform overview](https://docs.mem0.ai/platform/overview)
- [Mem0 open-source overview](https://docs.mem0.ai/open-source/overview)

## 출처

- [Mem0 Platform overview](https://docs.mem0.ai/platform/overview)
- [Mem0 MCP](https://docs.mem0.ai/platform/mem0-mcp)
- [Memory types](https://docs.mem0.ai/core-concepts/memory-types)
- [Mem0 open-source overview](https://docs.mem0.ai/open-source/overview)

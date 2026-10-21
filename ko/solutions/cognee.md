# Cognee

## Snapshot

- 웹사이트 / 문서: https://docs.cognee.ai/
- 회사 / 관리자: Cognee
- 상태: 오픈소스 memory 및 knowledge-processing platform; 별도의 managed Cloud option
- 오픈소스: 공식 Python project는 Apache-2.0 license
- 배포: Local Python SDK; 선택적 self-hosted API/MCP; Cognee Cloud
- 주요 사용자: agent가 검색할 구조화 memory를 만들려는 developer와 AI power user
- 세컨드 브레인에서 가장 잘 맞는 역할: Agent memory/knowledge-processing layer; graph/retrieval substrate는 부차적 역할
- 마지막 검토: 2026-10-21

## 한 줄 요약

Cognee는 문서, 코드, 텍스트, structured data를 받아 graph/vector 기반 memory로 변환하고 SDK, API, MCP, agent integration을 통해 검색하게 합니다.

## 세컨드 브레인 적합성

Cognee는 substrate 전용 제품이 아닙니다. 개발자는 SDK, local service, hosted API를 agent memory layer로 바로 채택해 데이터를 제공하고 연결된 knowledge로 처리한 다음 agent에 context를 돌려줄 수 있습니다. Graph, vector, relational backend는 더 큰 애플리케이션의 substrate로도 활용됩니다.

완성형 personal knowledge-management 앱과는 다릅니다. 주요 surface는 처리와 검색이며 GBrain 또는 LLM Wiki처럼 사람이 직접 검토하고 편집하는 curated wiki 경험은 별도 workflow가 필요합니다.

## 기능

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | Apache-2.0 local Python 경로, 선택적 self-host API/MCP, 별도 managed Cognee Cloud. |
| 맥락 수집 | SDK/API로 문서, 코드, 텍스트, structured data 수집; agent integration으로 session/project context 추가 가능. |
| 지식 정리 | 입력을 chunk, entity, relationship, embedding, queryable knowledge graph로 변환. 자동 생성 wiki와는 다름. |
| Memory 발전 | Processing/improvement workflow로 memory를 보강할 수 있지만 언제 다시 처리할지는 사용자가 결정. |
| 검색 / 활용 | 설정한 search mode에 따라 graph context, chunk, summary, generated answer를 반환. |
| 에이전트 활용 / 쓰기 반영 | Python SDK, API, MCP server, CLI, plugin, agent integration. |
| 개인 / 팀 범위 | Dataset과 service mode의 user/tenant permission 사용 가능. 격리는 배포와 설정에 달려 있음. |
| 검토 / 정정 | Dataset 및 data-management API로 확인/삭제 가능; 사람용 wiki editor가 주 surface는 아님. |
| 프라이버시 / 통제권 | Local model/storage는 자체 운영 가능. Hosted Cloud는 별도 데이터 경계. |
| 설정 / 운영 | Local SDK 실험은 부담이 낮지만 provider, backend, service, source refresh, permission 설정 시 중간 수준. |

## Cognee에 source 넣기

Drive, Notion, local vault의 원본을 source of truth로 유지하세요. Cognee data workflow에서는 text/file/structured data를 dataset에 넣고 cognification pipeline을 실행해 graph/vector 표현을 만든 뒤 해당 dataset을 검색합니다. 최신 README quickstart에는 상위 수준 remember/recall 호출도 나옵니다. 설치 버전의 API 문서에서 정확한 method와 input 형식을 확인하세요.

Graph와 index는 파생 memory입니다. 감사, 정정, 재수집, 재생성을 위해 원본과 source ID를 Cognee 외부에 보관하세요. 의미 있는 권한과 lifecycle 경계별로 dataset을 나누고, 지원되는 경우 source 이름/URL과 update time을 metadata로 남기세요. Index를 원본 archive나 backup으로 간주하기 전에 update/delete 동작을 검증하세요.

문서화된 소형 local extraction/embedding model을 사용하면 text ingest/retrieval을 hosted API subscription 없이 local에서 실행할 수 있습니다. 첫 사용 시 model을 다운로드하고 local compute를 사용합니다. Generated answer나 일부 media 처리에는 별도 model provider가 필요할 수 있습니다.

## 장점

- 공식 Apache-2.0 source와 local-first 경로.
- 문서, chunk, entity, relationship을 graph-oriented pipeline으로 연결.
- SDK, API, MCP, CLI, agent integration을 통한 여러 채택 방식.
- 직접 agent memory로 쓰거나 하위 graph/retrieval component로 활용 가능.

## 한계

- Developer-oriented 제품이라 source 수집/갱신, 권한, 운영 담당자가 필요합니다.
- Graph memory가 사용자 편집형 wiki를 대신하지 않습니다.
- 결과와 갱신은 pipeline, model, dataset, metadata에 달려 있습니다.
- Client마다 별도 standalone 실행 시 공유 memory가 분리될 수 있습니다.

## 가장 적합한 경우

- Agent가 query할 open-source graph memory pipeline을 원하는 개발자.
- 문서, 코드, 대화에 걸친 fact/relationship을 검색하려는 사용자.
- GBrain 또는 LLM Wiki와 함께 쓰는 processing/retrieval layer.

## 적합하지 않은 경우

- Source governance가 포함된 완성형 UI를 원하는 비기술 사용자.
- Cognee가 직접 관리하는 polished wiki page를 기대하는 사용자.
- 배포 mode, dataset, refresh, access control을 운영하기 원치 않는 팀.

## 트레이드오프

Cognee의 Apache-2.0 local 경로는 유료 hosted memory service 의존을 줄입니다. 대신 설치, local model 성능, source synchronization, 지식 검토를 사용자가 맡습니다. 사람이 읽고 관리할 page가 필요하면 별도의 editable workspace와 짝지으세요.

## 공식 설정 / 평가 자료

- [Cognee 설치 및 local quickstart](https://docs.cognee.ai/getting-started/installation)
- [Cognee API: ingestion, cognification, search, datasets](https://docs.cognee.ai/api-reference/introduction)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
- [Cognee agent integration](https://docs.cognee.ai/cognee-mcp/integrations)
- [공식 Cognee repository](https://github.com/topoteretes/cognee)
- [Apache-2.0 license](https://github.com/topoteretes/cognee/blob/main/LICENSE)

## 출처

- [Cognee README](https://github.com/topoteretes/cognee)
- [Cognee installation](https://docs.cognee.ai/getting-started/installation)
- [Cognee API reference](https://docs.cognee.ai/api-reference/introduction)
- [Apache-2.0 license](https://github.com/topoteretes/cognee/blob/main/LICENSE)

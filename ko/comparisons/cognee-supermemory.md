# Cognee와 Supermemory: 비슷한 분류, 다른 시스템

**2026-10-21 검토.** 두 제품 모두 AI agent에 유용한 context를 제공할 수 있지만 source ingestion, 내부 memory 표현, 업데이트 방식, 사람용 workflow는 다릅니다. “Agent memory layer”는 채택 위치를 뜻하며 같은 구조를 보장하지 않습니다.

## Source가 어떻게 바뀌는가

| 질문 | Cognee | Supermemory |
|---|---|---|
| 어떤 입력을 받나? | SDK/API의 document, code, text, structured data | document, file, URL, conversation, 지원되는 source connector |
| 입력 뒤 무엇을 만드나? | Dataset에 넣고 chunk, entity, relationship, embedding, graph memory로 처리 | Document를 검색 source로 유지하고 atomic fact, relationship, profile context를 파생 |
| Agent가 무엇을 받나? | Search mode에 따라 graph context, matching chunk, summary, generated answer | Hybrid search의 source document와 memory/profile context |
| 사람이 관리하는 결과물은? | Queryable graph/retrieval API; editorial wiki는 아님 | Document와 파생 memory/profile; curated wiki는 아님 |
| 주 역할은? | Open-source knowledge-processing/agent-memory layer; graph substrate도 가능 | Hosted agent-memory/context service와 document RAG; local binary도 광고 |

두 시스템은 agent에 비슷한 답변이나 passage를 줄 수 있습니다. 그러나 중간 데이터 구조와 lifecycle이 다르므로 같은 provenance, update semantics, permission, editable artifact를 보장하지 않습니다.

## 분류 수정

Cognee를 “memory substrate only”로 부르면 범위가 좁습니다. Python SDK, API, MCP server, agent integration을 통해 agent memory/knowledge-processing layer로 직접 도입할 수 있고 graph/vector component는 substrate 역할도 합니다.

Supermemory도 agent-memory 범주지만 대화 episodic memory에 한정되지 않습니다. 현재 product 문서는 document RAG, connector, fact memory, profile, hybrid search, agent access를 설명합니다. Cognee와 retrieval output이 겹쳐도 graph-building pipeline과 managed profile-memory model은 다릅니다. 둘 다 사용자가 직접 운영하는 wiki는 아닙니다.

## Cognee에 source 제공하기

1. **원본을 유지합니다.** Drive/Notion을 원본으로 두거나 local control이 필요하면 versioned local folder로 export합니다. Cognee graph/index는 파생 데이터입니다.
2. **Dataset 경계를 정합니다.** 개인 연구, 업무 프로젝트, subject area처럼 권한과 lifecycle에 맞춰 dataset을 나눕니다.
3. **선택한 입력을 넣습니다.** Cognee SDK/API의 문서화된 경로로 file, text, structured record를 보냅니다. 지원되는 경우 source name/URL, update time, stable ID를 metadata로 보존합니다.
4. **Dataset을 처리합니다.** Cognification으로 chunk, entity, relationship을 추출/색인합니다. 최신 quickstart는 상위 수준 remember/recall도 제공합니다.
5. **검색 결과를 검증합니다.** 대표 질문을 검색하고 graph/chunk context를 원본과 대조합니다. Generated answer에는 model 설정이 필요합니다.
6. **갱신/삭제를 명시합니다.** Source version을 기록하고 변경본을 재처리하며 dataset delete/update를 검증합니다. External manifest로 stale data를 찾습니다.

이는 source-to-index pipeline이지 Drive/Notion의 모든 변경을 자동 동기화한다는 뜻은 아닙니다. Connector, sync job, agent가 변경을 전달해야 합니다.

## GBrain 또는 LLM Wiki와 조합하기

- **Source of truth:** Drive/Notion 원본 또는 local Markdown/vault mirror.
- **Knowledge artifact:** GBrain 또는 LLM Wiki workflow에서 source backlink와 reviewable edit가 있는 inspectable topic page를 관리.
- **Agent retrieval:** Cognee가 선택된 원본을 index하고 SDK/API/MCP로 graph/chunk context 제공.
- **선택적 대화 memory:** Supermemory로 agent preference, session fact, document retrieval을 편리하게 만들되 canonical archive로 두지 않을 수 있음.

같은 입력이 두 시스템으로 가도 update가 자동 동기화되지는 않습니다. 작은 ingestion manifest와 explicit source link가 integration contract입니다. 한 domain의 문서 몇 개로 시작해 correction, deletion, access boundary, retrieval을 확인하세요.

## 반복 구독 없는 선택

| 선택지 | 반복 구독 | 비용/제한 | 적합성 |
|---|---|---|---|
| Local model을 쓰는 Cognee | 문서화된 local 경로는 subscription 불필요 | 설정, download, local compute, 유지보수; generated answer나 일부 media 작업은 provider 비용 발생 가능 | Open-source control과 agent retrieval 시작점 |
| Local Markdown의 GBrain/LLM Wiki | Local workflow는 subscription 불필요 | Source sync, 사람/agent review, wiki 유지보수 | 읽고 수정할 수 있는 knowledge artifact |
| Supermemory Free hosted | 유료 plan 없이 체험 가능; 현재 월 $5 credit | Ingestion/search/operation이 credit을 사용하며 corpus용 무제한 무료가 아님 | Credit 범위 내 가벼운 agent-memory 편의 기능 |
| Supermemory local server | Product는 local binary 사용을 광고 | Runtime source와 license 조건 확인 필요; pricing page는 self-hosted를 Scale/Enterprise에 포함 | 현재 조건과 source 투명성을 확인한 뒤 검토 |

**반복 구독 없는 구성을 원한다면:** Drive/Notion 또는 local Markdown에 원본을 두고 GBrain/LLM Wiki에서 사람이 검토할 artifact를 관리하며 graph 기반 agent retrieval이 필요할 때 Cognee를 local로 추가하세요. Supermemory Free는 선택적 편의 기능으로 두고 knowledge base의 유일한 사본으로 의존하지 않는 편이 좋습니다. 구독이 없어도 setup, hardware, 시간, 유지보수 비용은 남습니다.

## 1차 출처

- [Cognee repository/README](https://github.com/topoteretes/cognee)
- [Cognee Apache-2.0 license](https://github.com/topoteretes/cognee/blob/main/LICENSE)
- [Cognee installation/local quickstart](https://docs.cognee.ai/getting-started/installation)
- [Cognee API: add, cognify, search, datasets](https://docs.cognee.ai/api-reference/introduction)
- [Supermemory product overview](https://supermemory.ai/product/)
- [Supermemory pricing/credits](https://supermemory.ai/pricing/)
- [Supermemory local-server changelog](https://supermemory.ai/changelog/local/)
- [Supermemory repository/MIT license](https://github.com/supermemoryai/supermemory)
- [Supermemory MCP](https://supermemory.ai/mcp/)

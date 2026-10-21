# Supermemory

## Snapshot

- 웹사이트 / 문서: https://supermemory.ai/
- 회사 / 관리자: Supermemory
- 상태: Hosted memory/context service, developer platform, 선택적 local-server 배포
- 오픈소스: 공개 main repository는 MIT license이며 일부 app/MCP/SDK/plugin source를 포함합니다. 회사는 local server를 open-source binary라고 설명하지만 검토한 repo에는 server source/build target이 보이지 않았습니다. Runtime source/license 관계는 확인 전까지 미확인으로 둡니다.
- 배포: 월별 credit을 사용하는 hosted API/MCP와 local server binary. Product/pricing page의 self-host 조건이 다르게 설명되어 있어 현재 조건 확인이 필요합니다.
- 주요 사용자: memory, document RAG, profile, connector, agent integration을 원하는 AI power user와 developer
- 세컨드 브레인에서 가장 잘 맞는 역할: document retrieval을 결합한 agent memory/context layer; episodic memory만을 위한 제품이나 편집형 wiki는 아님
- 마지막 검토: 2026-10-21

## 한 줄 요약

Supermemory는 업로드하거나 연결한 원본 문서와 그 문서에서 추출한 fact, profile, graph memory, hybrid search를 API/MCP/agent plugin으로 제공합니다.

## 세컨드 브레인 적합성

“Agent memory”라는 짧은 표현만으로는 대화 기록만 저장하는 것처럼 보일 수 있습니다. 현재 제품 설명에는 document RAG, file processing, connector, knowledge-base 검색도 포함됩니다. 대화 memory와 지식 검색이 겹치는 product입니다.

그렇더라도 Cognee와 같은 내부 pipeline이나 사용자가 편집하는 wiki라고 볼 수는 없습니다. Supermemory는 source document와 파생 memory를 구분하고 추출/검색을 관리합니다. Curated knowledge page와 여러 source의 편집 검토는 별도 역할입니다.

## 기능

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | Hosted API/MCP는 account와 월별 credit을 사용합니다. Product는 local embedding과 configurable model provider를 쓰는 local server binary도 광고합니다. Pricing page는 self-hosting을 Scale/Enterprise에 열거하므로 local 사용 조건을 확인하세요. |
| 맥락 수집 | Document/text upload, URL, Google Drive, Gmail, Notion, OneDrive, GitHub 등 문서화된 connector; connector와 plan은 달라질 수 있습니다. |
| 지식 정리 | 문서를 검색 source로 유지하고 atomic fact, relationship, profile context를 memory graph에 파생합니다. Curated Markdown/wiki page를 보장하지 않습니다. |
| Memory 발전 | Fact 추출, update, contradiction handling, profile 변화, forgetting을 제품이 관리합니다. |
| 검색 / 활용 | API, MCP 및 product surface에서 source document와 memory/profile context를 함께 hybrid search. |
| 에이전트 활용 / 쓰기 반영 | Hosted MCP, REST API, SDK, coding-agent plugin; product는 local server URL도 문서화합니다. |
| 개인 / 팀 범위 | Namespace, project/container tag, team space를 문서화합니다. 이것만으로 application authorization이 완성되지는 않습니다. |
| 검토 / 정정 | Console과 API로 document/memory 조회 가능; 단독 source of truth로 쓰기 전에 편집/삭제/export를 확인하세요. |
| 프라이버시 / 통제권 | Hosted는 간편하지만 데이터를 service에 보냅니다. Local server는 local control을 광고하지만 telemetry, provider 호출, connector, 약관을 확인하세요. |
| 설정 / 운영 | Hosted 연동은 쉽습니다. Local은 database 운영을 줄이지만 compute, backup, update, model 선택은 사용자 책임입니다. |

## 오픈소스, 무료 요금제, Local binary

세 항목을 분리해서 보세요.

- 공개 Supermemory GitHub repository는 MIT license를 가지고 있고 integration/plugin/MCP code가 공개되어 있습니다. 이 license가 repository에 포함되지 않은 hosted component나 binary에 자동 적용되는 것은 아닙니다.
- Product page와 README는 local server를 open-source binary라고 설명합니다. 검토한 공개 repository에는 local server source나 build target이 없고 README는 prebuilt binary를 안내합니다. 핵심 runtime은 “binary 배포; source/license 관계 별도 확인”이라고 분류합니다.
- 현재 Free hosted plan은 매월 $5 credit을 제공합니다. Ingestion, search, operation이 credit을 사용하므로 무제한 무료 service는 아닙니다. Vendor는 coding-agent plugin을 무료라고 하지만 사용량은 credit을 소비합니다. Zero-spend가 중요하면 billing/top-up 설정을 확인하세요.
- Product page는 local 사용을 광고하지만 pricing page는 self-hosted deployment를 Scale/Enterprise에 포함합니다. 장기적인 구독 없는 기반으로 삼기 전에 조건을 확인하세요.

## 장점

- 대화 memory, profile, document retrieval, connector, agent access를 한 service에 결합.
- 여러 AI tool에서 memory를 빠르게 공유 가능.
- Local machine에서 실행하는 server binary를 제공한다고 설명합니다.

## 한계

- Hosted Free는 월 credit budget이 있어 지속적인 대량 ingestion/search에 무제한 무료가 아닙니다.
- MIT 공개 integration 코드와 local server runtime의 source/license/build 관계가 다르게 보일 수 있습니다.
- 제품 관리형 memory는 사용자가 직접 편집하는 wiki artifact와 다릅니다.
- Hosted와 local binary는 비용, 개인정보, 운영, source availability 조건이 다릅니다.

## 가장 적합한 경우

- 알려진 credit 범위 안에서 hosted memory와 document RAG를 쓰려는 사용자.
- 파일, profile, conversation memory를 하나의 API/MCP/plugin surface로 연결하려는 개발자.
- 별도 원본 archive에 보조 personal-memory service를 추가하려는 경우.

## 적합하지 않은 경우

- Runtime을 source로 감사/빌드해야 하는 사용자.
- 큰 Drive/Notion corpus를 hosted credit 없이 계속 넣고 검색하려는 경우.
- Cross-source를 editorial knowledge page로 관리하려는 경우.

## 트레이드오프

Supermemory는 ingestion, extraction, profile memory, retrieval 통합을 줄여줍니다. Hosted 경로는 운영을 단순하게 하지만 비용과 data control이 service에 의존합니다. Local binary는 hosted usage를 줄일 수 있으나 운영 책임이 생기고 source/license/build 조건을 먼저 확인해야 합니다.

## 공식 설정 / 평가 자료

- [Supermemory product overview](https://supermemory.ai/product/)
- [Supermemory API/MCP](https://supermemory.ai/mcp/)
- [Supermemory local/self-hosting docs](https://supermemory.ai/docs/self-hosting/overview)
- [Supermemory pricing and credits](https://supermemory.ai/pricing/)
- [Supermemory local-server changelog](https://supermemory.ai/changelog/local/)
- [Supermemory public repository and MIT license](https://github.com/supermemoryai/supermemory)

## 출처

- [Supermemory product overview](https://supermemory.ai/product/)
- [Supermemory pricing](https://supermemory.ai/pricing/)
- [Supermemory repository README](https://github.com/supermemoryai/supermemory)
- [Supermemory repository license](https://github.com/supermemoryai/supermemory/blob/main/LICENSE)
- [Supermemory local-server changelog](https://supermemory.ai/changelog/local/)
- [Supermemory MCP overview](https://supermemory.ai/mcp/)

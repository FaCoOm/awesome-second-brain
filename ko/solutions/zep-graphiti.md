# Zep / Graphiti

## 개요

- 웹사이트 / 문서: https://help.getzep.com/
- 회사 / 관리자: Zep
- 상태: 활성 플랫폼. Graphiti는 Zep memory architecture 아래의 open-source temporal graph library
- 오픈소스: Graphiti는 open source이고 Zep은 managed platform
- 배포: Hosted Zep + Graphiti library integration
- 주요 사용자: temporal graph memory가 필요한 agent application developer
- 세컨드 브레인 역할: temporal knowledge graph memory backend
- 마지막 검토: 2026-05-31

## 한 줄 요약

Zep은 Graphiti 위에 구축된 temporal knowledge graph를 사용해 evolving memory와 애플리케이션용 Graph RAG를 제공합니다.

## 세컨드 브레인 적합도

Zep/Graphiti는 애플리케이션 안에 graph memory가 필요한 builder에게 가장 적합합니다. 가장 빠른 소비자용 세컨드 브레인 설정은 아니지만, entity, fact, episode, time, business data를 memory가 모델링해야 할 때 관련성이 높습니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | hosted Zep platform과 Graphiti open-source graph library. |
| 맥락 수집 | chat history, business data, graph endpoint를 통한 API ingestion. |
| 지식 정리 | 내장 entity node, entity edge, episodic node, fact, summary. |
| Memory 발전 | 내장 temporal graph update와 fact/summary extraction. 사용자가 운영하는 dream loop로 framing되지는 않습니다. |
| 검색 / 활용 | temporal knowledge graph와 Graph RAG. |
| 에이전트 활용 / 쓰기 반영 | API/SDK 우선. agent framework ecosystem integration. |
| 개인 / 팀 범위 | Zep model에는 project, user, session, group이 포함됩니다. |
| 검토 / 정정 | developer/platform UI와 graph API. end-user second-brain UI가 primary surface는 아닙니다. |
| 프라이버시 / 통제권 | hosted platform과 open-source graph library. deployment별 hosting/retention requirement를 확인하세요. |
| 설정 / 운영 | 중간. application integration과 data model choice가 필요합니다. |

## 강점

- temporal graph model이 강함.
- evolving user/session/business data가 있는 application에 잘 맞음.
- Graphiti는 dynamic graph memory의 reference architecture를 제공함.

## 한계

- no-code personal second-brain app이 아님.
- memory ingest, scope, query를 위한 engineering work가 필요함.
- managed platform과 open-source graph library는 관련되어 있지만 동일한 deployment surface는 아님.

## 잘 맞는 경우

- temporal graph memory가 있는 agent application을 만드는 developer.
- retrieval에 entity, episode, fact, time, business data가 필요한 product.
- API/SDK로 memory를 integration할 수 있는 팀.

## 잘 맞지 않는 경우

- no-code 개인 세컨드 브레인 설정을 원하는 사용자.
- 기존 tool 전반에 off-the-shelf second-brain automation이 필요한 팀.
- application memory model 운영이 과한 overhead인 workflow.

## 트레이드오프

Zep/Graphiti는 memory가 application architecture의 일부일 때 강합니다. 트레이드오프는 integration work입니다. 팀은 기존 tool을 ready-made second-brain layer에 연결하는 대신 user, session, data ingestion, retrieval behavior를 직접 모델링해야 합니다.

## 공식 설정 / 평가 링크

- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Zep memory docs](https://help.getzep.com/v2/memory)
- [Graphiti GitHub repo](https://github.com/getzep/graphiti)

## 출처

- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Zep memory docs](https://help.getzep.com/v2/memory)
- [Graphiti open source](https://www.getzep.com/product/open-source)
- [Graphiti GitHub repo](https://github.com/getzep/graphiti)

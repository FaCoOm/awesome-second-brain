# Hyperspell

## 스냅샷

- 웹사이트 / 문서: https://www.hyperspell.com/ 및 https://docs.hyperspell.com/
- 회사 / 관리자: Digital Workers of California, Inc.
- 상태: 활성 호스팅 제품 및 개발자 플랫폼. integrations 문서에서는 private beta라고 설명함
- 오픈 소스: 핵심 호스팅 플랫폼은 managed. 공개 GitHub org에는 SDK, MCP server, plugin, CLI 관련 레포가 있음
- 배포 방식: SDK, API, dashboard, MCP server, connector flow를 제공하는 호스팅 memory/context 플랫폼
- 주 사용자: 사용자/workspace context가 필요한 AI agent를 만드는 개발자와 팀
- 세컨드 브레인에서 가장 잘 맞는 역할: AI agent용 호스팅 company/user context 계층
- 마지막 검토: 2026-06-01

## 한 줄 요약

Hyperspell은 사용자 workspace source를 연결하고, 데이터를 index 또는 live search로 검색하며, API, SDK, MCP, agent plugin으로 retrieval을 제공하는 AI agent용 호스팅 memory/context 계층입니다.

## 세컨드 브레인 적합도

Hyperspell은 AI 제품이나 내부 agent에 memory와 context를 넣고 싶지만 connector OAuth, ingestion, indexing, retrieval, reranking, grounding 인프라를 직접 만들고 싶지 않은 builder에게 가장 잘 맞습니다. 소비자용 세컨드 브레인 앱이라기보다 개발자/플랫폼 memory 계층에 가깝습니다.

자가 발전형 세컨드 브레인 관점에서는 integration, manual ingestion, file upload, metadata, multi-source search, optional grounded answer, MCP를 통해 수집과 활용 단계를 잘 커버합니다. agent trace에서 재사용 가능한 단계별 절차를 뽑는 procedural memory도 있습니다. 다만 지식 정리와 거버넌스는 개발자 설계에 더 많이 의존합니다. app owner가 metadata, collection, source scoping, review UI, user/team permission model을 설계해야 합니다.

## 기능

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | dashboard, API, SDK, MCP server가 있는 호스팅 플랫폼. SDK/plugin/MCP 공개 레포는 있지만 핵심 memory 플랫폼은 managed입니다. |
| 맥락 수집 | 내장 integration, 사용자 OAuth용 Hyperspell Connect, manual memory add, bulk ingestion, file upload, web crawler, folder sync policy, agent trace ingestion. integration 사용 가능 여부는 private beta / 계정별로 달라질 수 있습니다. |
| 지식 정리 | memory, 연결된 data source, metadata filter, collection, structured resource data, LLM-ready summary, context graph claim, trace에서 추출한 procedural memory. |
| Memory 발전 | source 변경 시 connected data update, query/conversation reinforcement claim, trace 기반 procedural memory extraction. 구체적인 consolidation 내부 동작은 제품이 관리합니다. |
| 검색 / 활용 | API/SDK natural-language search, indexed search, live search, multi-source query, filter, resource scoping, source weighting, optional answer generation, MCP search/get tool. |
| 에이전트 활용 / 쓰기 반영 | 내장 MCP server, SDK, API, Claude Code skill/plugin, OpenClaw plugin repo, search/add memory/get memory/upload file/integration management 도구. |
| 개인 / 팀 범위 | app user ID 또는 user token을 사용하는 multi-tenant user model. 팀은 자기 app에서 user와 scope를 모델링할 수 있습니다. workspace/team governance 세부 사항은 대상 계정에서 확인해야 합니다. |
| 검토 / 정정 | list/get/update memory API, metadata filtering, folder manual review flow, pending/approve/reject 상태, query error, webhook, evaluation API. 최종 사용자 UI는 통합하는 app에 달려 있습니다. |
| 프라이버시 / 통제권 | 호스팅형 제어, user-specific token, source connection control, folder skip/manual/sync policy, 홈페이지의 삭제 claim. retention/export/deletion 요구사항은 대상 plan에서 확인해야 합니다. |
| 설정 / 운영 | 낮음-중간. 공식 사이트는 agent가 5분 이내에 context를 얻을 수 있다고 주장하지만, production 사용에는 app integration, user auth/scoping, source selection, beta access 확인이 필요합니다. |

## 강점

- 개발자 API, SDK, MCP, plugin 스토리가 강합니다.
- Notion, Slack, Gmail, Google Calendar, Google Drive, GitHub, Linear, Jira, Dropbox, Box 등 넓은 공식 integration surface가 있습니다.
- indexed search와 live search를 모두 지원해 latency, freshness, storage sensitivity를 상황에 맞게 조절할 수 있습니다.
- procedural memory는 agent가 성공했던 multi-step workflow를 재사용하도록 설계되어 있습니다.
- folder sync policy와 manual review flow는 단순한 all-or-nothing connector sync보다 더 세밀한 통제권을 줍니다.
- multi-tenant user model은 per-user memory가 필요한 제품에 자연스럽습니다.

## 한계

- Private beta / account-dependent availability 때문에 connector와 feature claim은 실제 사용 전에 확인해야 합니다.
- 기본적으로 호스팅 플랫폼이며 local-first 세컨드 브레인은 아닙니다.
- 그 자체로 polished consumer knowledge UI는 아닙니다. end-user review와 workspace UX는 app이 책임져야 합니다.
- graph construction, reinforcement, retention, deletion 같은 product internal은 managed이며 문서 이상으로 단정하면 안 됩니다.
- 팀은 permission boundary, metadata, collection taxonomy, safe recall behavior를 여전히 설계해야 합니다.

## 잘 맞는 사용자

- AI 제품이나 내부 agent에 memory를 추가하려는 개발자.
- SaaS tool의 user/workspace context를 API, SDK, MCP로 노출해야 하는 팀.
- factual memory와 reusable procedural memory가 모두 유용한 agent workflow.
- source별 pipeline을 직접 만들지 않고 connector ingestion을 쓰고 싶은 제품.

## 잘 맞지 않는 사용자

- standalone 개인 세컨드 브레인 앱을 원하는 사용자.
- local-only 저장소나 self-hosted memory infrastructure가 필요한 사용자.
- governance, review UI, knowledge taxonomy까지 모두 out of the box로 처리되길 원하는 팀.
- private beta availability가 리스크인 workflow.

## 트레이드오프

Hyperspell은 agent builder가 connector, ingestion, indexing, retrieval을 직접 만드는 부담을 크게 줄여줄 수 있습니다. 대신 사용자는 호스팅형 개발자 플랫폼 안에서 동작하며, 제품 경험, governance, scoping, memory hygiene은 여전히 직접 설계해야 합니다.

## 공식 설정 / 평가 링크

- [Hyperspell 웹사이트](https://www.hyperspell.com/)
- [Hyperspell 문서](https://docs.hyperspell.com/)
- [Core concepts](https://docs.hyperspell.com/core/concepts)
- [Manual integration](https://docs.hyperspell.com/core/integration)
- [Available integrations](https://docs.hyperspell.com/integrations/overview)
- [Hyperspell Connect](https://docs.hyperspell.com/usage/connect)
- [Folder sync](https://docs.hyperspell.com/usage/folder-sync)
- [Procedural memory](https://docs.hyperspell.com/usage/procedural-memory)
- [MCP overview](https://docs.hyperspell.com/advanced/mcp-overview)

## 출처

- [Hyperspell 웹사이트](https://www.hyperspell.com/)
- [Hyperspell 문서](https://docs.hyperspell.com/)
- [Core concepts](https://docs.hyperspell.com/core/concepts)
- [Manual integration](https://docs.hyperspell.com/core/integration)
- [Available integrations](https://docs.hyperspell.com/integrations/overview)
- [Hyperspell Connect](https://docs.hyperspell.com/usage/connect)
- [Folder sync](https://docs.hyperspell.com/usage/folder-sync)
- [Procedural memory](https://docs.hyperspell.com/usage/procedural-memory)
- [MCP overview](https://docs.hyperspell.com/advanced/mcp-overview)
- [Hyperspell GitHub org](https://github.com/hyperspell)

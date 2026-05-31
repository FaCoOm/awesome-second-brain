# GBrain

## 개요

- 웹사이트 / 저장소: https://github.com/garrytan/gbrain
- 회사 / 관리자: Garry Tan / GBrain 관리자
- 상태: 활성 공개 저장소
- 오픈소스: 예
- 배포: 기본은 local PGLite. 더 큰 규모, remote, team deployment를 위해 Postgres/Supabase 및 stdio/HTTP MCP 경로 제공
- 주요 사용자: local-first brain builder, AI operator, memory를 workflow에 연결하는 developer
- 세컨드 브레인 역할: 로컬 또는 self-hosted 브레인 운영 계층
- 마지막 검토: 2026-05-31
- 검토 근거: 공식 저장소 checkout `0.41.38.0`, commit `248fb7a90f9ce5fe2e5d01fe486345d08834ed40`, README, `INSTALL_FOR_AGENTS.md`, `src/core/operations.ts`, `src/core/search/hybrid.ts`, `src/commands/serve-http.ts`

## 한 줄 요약

GBrain은 Markdown page, capture, AI가 작성한 지식을 검색 가능한 page/chunk/link/timeline/fact database로 바꾸고 CLI, MCP, 예약 유지보수 workflow를 제공합니다.

## 세컨드 브레인 적합도

GBrain은 local/self-hosted 세컨드 브레인을 위한 brain database와 운영 계층으로 이해하는 것이 가장 좋습니다. polished no-code notes app도 generic vector database도 아닙니다. AI workflow에 구조화된 memory system을 제공하지만, 외부의 살아 있는 맥락에는 여전히 collector 또는 export가 필요합니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | 개인용 brain은 local PGLite. 더 큰 규모, remote, team use에는 Postgres/Supabase, stdio MCP, HTTP MCP를 사용합니다. |
| 맥락 수집 | 내장 Markdown 가져오기, `capture`, file/stdin capture, HTTP `/ingest`, inbox folder, `sync --watch` 폴링, skillpack ingestion surface. 외부 SaaS 정보원에는 recipe 또는 custom collector가 필요합니다. |
| 지식 정리 | 내장 schema pack, `gbrain-base-v2` taxonomy, page type 추론, schema detect/suggest/review flow, link extraction, timeline extraction, fact/take workflow, deterministic graph signal. 임의의 원본 텍스트를 알아서 정리하는 magic semantic classifier는 아닙니다. |
| Memory 발전 | 내장 `gbrain dream`, `gbrain autopilot`, sync/embed 작업, 유지보수 phase. |
| 검색 / 활용 | `search`는 저비용 hybrid retrieval, `query`는 filter가 있는 확장 hybrid retrieval, graph/link signal, timeline/fact retrieval, `think`는 citation이 있는 synthesis와 conflict/gap analysis. |
| 에이전트 활용 / 쓰기 반영 | 내장 CLI와 30개 이상의 문서화된 operation을 가진 stdio/HTTP MCP, HTTP OAuth scope control. |
| 개인 / 팀 범위 | 내장이지만 운영이 필요합니다. brain, source, source-scoped OAuth client, federated read, mount, Postgres/Supabase, HTTP MCP를 사용합니다. directory-only team scoping은 OAuth-scoped source 없이는 관례 기반입니다. |
| 검토 / 정정 | HTTP admin surface는 client registration, request log, job, live activity, scoped operation을 다룹니다. Notion/Roam 스타일 시각적 지식 UI가 주 표면은 아닙니다. |
| 프라이버시 / 통제권 | Markdown/git-backed source option이 있는 강한 local/self-hosted control. |
| 설정 / 운영 | 중간-높음. 공식 agent install은 personal brain 기준 약 30분을 목표로 하고, company-brain path는 약 90분이 추가되며 source/OAuth/database 결정을 요구합니다. |

## 강점

- local-first와 self-hosted story가 강함.
- Markdown/page/chunk/link/timeline 모델이 명확함.
- dream/autopilot을 통한 실제 유지보수 루프.
- CLI와 MCP 덕분에 자동화에 적합함.
- deterministic graph behavior는 pure semantic linking보다 디버그하기 쉬움.
- source/type/tag/date filter와 source-scoped slug가 multi-source brain 분석에 유리함.
- `think`가 retrieval 위에 citation이 있는 synthesis, conflict detection, gap analysis를 제공합니다.
- source-scoped OAuth와 federated read는 운영할 의지가 있는 팀을 위한 문서화된 경로입니다.

## 한계

- 외부 앱 ingestion은 recipe/custom-collector 기반이지 universal one-click이 아니며 collector가 OAuth, pagination, rate limit, normalization을 책임져야 함.
- import된 것과 embedded/curated된 것은 다름.
- `sync --watch`는 real-time filesystem streaming이 아니라 polling으로 문서화되어 있습니다.
- Gmail, Calendar, X/Twitter, voice 등 연동은 recipe 또는 skillpack path이며 production quality는 source-specific pipeline에 의존합니다.
- Notion/Obsidian 스타일 migration은 Markdown import layer에서는 안정적이지만 database property, CSV export, relation graph에는 추가 mapping이 필요합니다.
- Company-brain deployment에는 Postgres/Supabase와 명시적인 source/OAuth scoping 결정이 필요합니다. directory convention만으로 enforced isolation이 되는 것은 아닙니다.
- 유용하게 운영하려면 지속 작업과 모니터링이 필요함.

## 잘 맞는 경우

- local 또는 self-hosted control을 원하는 사용자.
- CLI, Markdown, git, MCP, embedding, scheduled job에 익숙한 developer.
- Postgres/Supabase와 source permission을 운영할 의지가 있는 팀.

## 잘 맞지 않는 경우

- 설정 부담이 가장 낮은 선택지를 원하는 사용자.
- collector나 cron job을 운영하고 싶지 않은 팀.
- polished no-code UI가 먼저 필요한 workflow.

## 트레이드오프

GBrain은 더 강한 local/self-hosted control을 주지만, 그 control에는 collector, sync job, embedding, maintenance, verification이라는 운영 부담이 따릅니다. 가장 빠른 end-to-end 설정보다 직접 brain stack을 운영하고 싶을 때 더 잘 맞습니다.

## 공식 설정 / 평가 링크

- [GBrain README](https://github.com/garrytan/gbrain/blob/master/README.md)
- [GBrain installation guide for AI agents](https://github.com/garrytan/gbrain/blob/master/INSTALL_FOR_AGENTS.md)
- [GBrain integrations docs](https://github.com/garrytan/gbrain/blob/master/docs/integrations/README.md)
- [GBrain live sync guide](https://github.com/garrytan/gbrain/blob/master/docs/guides/live-sync.md)
- [GBrain company brain tutorial](https://github.com/garrytan/gbrain/blob/master/docs/tutorials/company-brain.md)
- [GBrain MCP deployment guide](https://github.com/garrytan/gbrain/blob/master/docs/mcp/DEPLOY.md)

## 출처

- [GBrain GitHub repo](https://github.com/garrytan/gbrain)
- [GBrain README](https://github.com/garrytan/gbrain/blob/master/README.md)
- [GBrain installation guide for AI agents](https://github.com/garrytan/gbrain/blob/master/INSTALL_FOR_AGENTS.md)
- [GBrain integrations docs](https://github.com/garrytan/gbrain/blob/master/docs/integrations/README.md)
- [GBrain live sync guide](https://github.com/garrytan/gbrain/blob/master/docs/guides/live-sync.md)
- [GBrain company brain tutorial](https://github.com/garrytan/gbrain/blob/master/docs/tutorials/company-brain.md)
- [GBrain MCP deployment guide](https://github.com/garrytan/gbrain/blob/master/docs/mcp/DEPLOY.md)
- [GBrain operations code](https://github.com/garrytan/gbrain/blob/master/src/core/operations.ts)
- [GBrain hybrid search code](https://github.com/garrytan/gbrain/blob/master/src/core/search/hybrid.ts)

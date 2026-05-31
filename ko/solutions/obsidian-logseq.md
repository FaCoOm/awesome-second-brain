# Obsidian / Logseq + AI Bridge

## 개요

- 웹사이트 / 문서: https://obsidian.md/ 및 https://logseq.com/
- 관리자: Obsidian 및 Logseq 커뮤니티/회사
- 상태: 활성 personal knowledge management 생태계
- 오픈소스: Obsidian은 proprietary, Logseq는 open source
- 배포: local-first notes, 선택적 sync/cloud service, plugin bridge
- 주요 사용자: 사람이 소유하는 notes를 source of truth로 두고 싶은 knowledge worker
- 세컨드 브레인 역할: AI memory bridge를 위한 local PKM 기반
- 마지막 검토: 2026-05-31

## 한 줄 요약

Obsidian과 Logseq는 plugin, export/import flow, MCP 스타일 bridge와 함께 사용할 때 AI가 접근할 수 있는 세컨드 브레인이 될 수 있는 local-first PKM system입니다.

## 세컨드 브레인 적합도

이 경로는 사용자가 note를 확인 가능한 로컬 파일로 유지하고 싶을 때 가장 좋습니다. 자동으로 AI memory system이 되는 것은 아닙니다. 세컨드 브레인 품질은 vault 또는 graph를 agent에 노출하는 bridge에 달려 있습니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | local-first vault/graph, 선택적 sync, 선택적 plugin/service. |
| 맥락 수집 | 앱에 따라 내장 note, file, backlink, graph view, daily note, PDF/annotation workflow. |
| 지식 정리 | 부분 지원. link, tag, property, block, plugin이 도움을 주지만 AI organization은 선택한 bridge에 의존합니다. |
| Memory 발전 | 커스텀 수집기. nightly review, summarization, memory extraction은 plugin/script/agent-driven이어야 합니다. |
| 검색 / 활용 | local search, backlink, graph view, plugin-provided RAG/search. |
| 에이전트 활용 / 쓰기 반영 | plugin/MCP bridge, memory layer로 가져오기, custom filesystem tool. |
| 개인 / 팀 범위 | personal/project fit은 강함. team workflow는 sync, permission, shared vault discipline에 의존합니다. |
| 검토 / 정정 | graph, backlink, tag, property, search, page/block 등 human UI가 강함. |
| 프라이버시 / 통제권 | local ownership이 강하지만 plugin permission은 신중히 다뤄야 합니다. |
| 설정 / 운영 | AI access가 필요하면 중간-높음. |

## 강점

- 사람이 읽을 수 있는 로컬 지식 베이스.
- 강한 personal ownership과 portability.
- 성숙한 PKM workflow와 community.
- second-brain layer, personal AI tool, custom RAG의 source material로 잘 작동함.

## 한계

- 자동으로 AI 도구 전반에서 사용 가능하지 않음.
- AI write-back은 review 없이 vault quality를 해칠 수 있음.
- plugin security와 sync conflict에 주의가 필요함.

## 잘 맞는 경우

- 사람이 소유하는 로컬 notes를 원하는 knowledge worker.
- 이미 Obsidian vault 또는 Logseq graph를 유지하는 사용자.
- reviewable source-of-truth notes가 가장 중요한 workflow.

## 잘 맞지 않는 경우

- bridge setup 없이 automatic second-brain automation을 원하는 사용자.
- turnkey permission, governance, shared retrieval이 필요한 팀.
- agent가 human review 없이 자유롭게 write해야 하는 workflow.

## 트레이드오프

Obsidian과 Logseq는 ownership, readability, manual knowledge craft를 극대화합니다. 트레이드오프는 automation입니다. vault나 graph를 신뢰할 수 있는 self-evolving second brain으로 만들려면 plugin, import workflow, MCP bridge, custom script가 필요합니다.

## 공식 설정 / 평가 링크

- [Obsidian help](https://obsidian.md/help)
- [Obsidian core plugins](https://obsidian.md/help/plugins)
- [Logseq](https://logseq.com/)

## 출처

- [Obsidian core plugins](https://obsidian.md/help/plugins)
- [Obsidian graph view](https://obsidian.md/help/Plugins/Graph%2Bview)
- [Logseq](https://logseq.com/)

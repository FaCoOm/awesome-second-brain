# Mnemosyne

## 개요

- 웹사이트 / 문서: https://docs.mnemosyne.site/
- Repository: https://github.com/mnemosyne-oss/mnemosyne
- Package: https://pypi.org/project/mnemosyne-memory/
- 회사 / 관리자: Mnemosyne OSS / Abdias J
- 상태: MCP, SDK, Hermes integration 경로가 있는 open-source Python package
- 오픈소스: 예, MIT 라이선스 repository
- 배포: Python package, MCP server, Python SDK, CLI, Hermes plugin을 통한 로컬 SQLite database
- 주요 사용자: MCP 또는 Hermes workflow에 local-first persistent memory를 붙이고 싶은 agent 운영자와 개발자
- 세컨드 브레인 역할: MCP와 Hermes 연동이 있는 local-first agent memory layer
- 마지막 검토: 2026-07-05

## 한 줄 요약

Mnemosyne는 SQLite에 memory를 저장하고 retrieval, consolidation, graph, MCP, SDK, CLI, Hermes plugin surface를 제공하는 AI agent용 local-first memory layer입니다.

## 세컨드 브레인 적합도

Mnemosyne는 개발자나 agent 운영자가 직접 운영하는 memory backend에 가장 잘 맞습니다. 세컨드 브레인이 hosted dashboard나 넓은 OAuth connector 제품보다 local storage, MCP access, Python SDK call, Hermes lifecycle hook, structured memory tier를 필요로 할 때 유용합니다.

이 레포의 landscape에서는 Hindsight, Mem0/OpenMemory, Honcho, GBrain과 가까운 위치입니다. Hosted memory product보다 programmable하고 local-first 성격이 강하지만, built-in connector, wiki UI, team governance가 있는 end-to-end 세컨드 브레인 앱보다는 직접 운영해야 할 부분이 많습니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | Local-first. 공식 package와 문서는 하나의 Python package, 하나의 SQLite database, MCP server mode, CLI, Hermes plugin path를 설명합니다. PyPI는 `mnemosyne-memory`를 MIT license, Python 3.9+ compatible package로 표시합니다. |
| 맥락 수집 | API, MCP, CLI, hook 기반입니다. 공식 예시는 `remember`, `recall`, MCP config, Python SDK call, `pre_llm_call`, `on_session_start`, `post_tool_call` 같은 Hermes lifecycle hook을 포함합니다. |
| 지식 정리 | Working memory, episodic memory, scratchpad, memory bank, temporal knowledge graph data용 TripleStore를 포함한 memory architecture가 내장되어 있습니다. |
| Memory 발전 | `sleep` / `consolidate_to_episodic` 계열 흐름으로 consolidation이 노출됩니다. 다만 언제 어떻게 consolidation을 실행할지는 사용자가 운영해야 합니다. |
| 검색 / 활용 | 공식 문서 기준 vector similarity, SQLite FTS5, importance weighting을 결합한 hybrid retrieval을 사용합니다. MCP, CLI, SDK, Hermes plugin surface가 agent에게 context를 전달할 수 있습니다. |
| 에이전트 활용 / 쓰기 반영 | MCP server, Python SDK, CLI, Hermes plugin이 내장되어 있습니다. 공식 README는 Cursor, Claude Code, Codex, Windsurf, OpenWebUI, OpenClaw, Hermes Agent, MCP client, Python agent를 integration target으로 제시합니다. |
| 개인 / 팀 범위 | 부분 지원. Memory bank와 global/session scope로 context를 분리할 수 있지만, team permission과 review workflow는 완성형 product layer가 아닙니다. |
| 검토 / 정정 | 부분적인 개발자/운영자 도구가 있습니다. Hermes plugin surface에는 update, forget, invalidate, validate, export, import, diagnose, scratchpad tool이 문서화되어 있습니다. |
| 프라이버시 / 통제권 | 로컬 저장소 성격이 강합니다. Hermes workflow의 SQLite data 기본 위치는 `~/.hermes/mnemosyne/data`입니다. 다만 embedding과 LLM 동작은 설정한 provider와 environment variable에 따라 달라질 수 있습니다. |
| 설정 / 운영 | 중간. Quickstart는 package install과 MCP/SDK config 중심이지만, 실제 가치는 embedding 설정, memory scope, consolidation cadence, agent integration behavior를 어떻게 설계하느냐에 달려 있습니다. |

## 강점

- 필수 managed service 없이 로컬 SQLite storage를 사용합니다.
- MCP server, Python SDK, CLI, Hermes plugin 경로가 문서화되어 있습니다.
- Hermes integration은 memory provider/plugin flow와 lifecycle hook을 구현합니다.
- Hot working memory, episodic memory, scratchpad, graph-style triple을 분리하는 tier가 있습니다.
- Memory bank와 global/session scope가 개발자에게 일부 격리 primitive를 제공합니다.
- 공식 문서가 non-English recall을 위한 multilingual embedding model 설정을 설명합니다.

## 한계

- 완성형 소비자 세컨드 브레인 앱이 아니라 memory backend입니다.
- 넓은 app connector, hosted dashboard UX, team permission, source governance가 주된 제품 surface는 아닙니다.
- 공식 benchmark claim은 vendor-authored이므로 hands-on 재현 없이는 독립 평가 근거로 다루지 않았습니다.
- README는 Hermes Agent 지원을 native로 설명하지만, 실제 Hermes 측 provider 사용 가능 여부는 target Hermes 설치에서 확인해야 합니다.
- Retrieval과 consolidation 품질은 embedding model, configuration, memory scope 설계, agent behavior에 의존합니다.

## 잘 맞는 경우

- 자동 context injection과 memory tool이 있는 로컬 memory provider를 원하는 Hermes 사용자.
- Codex, Claude Code, Cursor 같은 MCP-capable coding agent에 local memory를 붙이고 싶은 사용자.
- hosted memory service를 운영하지 않고 Python SDK로 agent memory를 쓰고 싶은 개발자.
- managed memory platform보다 로컬 SQLite 소유권을 선호하는 사용자.

## 잘 맞지 않는 경우

- hosted dashboard, built-in OAuth connector, 낮은 설정 부담을 원하는 사용자.
- workspace permission, admin control, governance UI가 즉시 필요한 팀.
- 제한된 notebook이나 wiki만으로 충분한 source-grounded research workflow.
- MCP, embedding, agent hook 설정을 원하지 않는 비기술 사용자.

## 트레이드오프

Mnemosyne는 강한 로컬 통제권과 여러 agent activation path를 제공하지만, integration과 운영 판단을 사용자에게 넘깁니다. 완성형 hosted 세컨드 브레인 제품보다 local 또는 programmable agent memory가 핵심 요구일 때 Hindsight, Mem0/OpenMemory, Honcho, GBrain, Cognee와 비교하는 것이 적절합니다.

## 공식 설정 / 평가 링크

- 문서: https://docs.mnemosyne.site/
- Repository: https://github.com/mnemosyne-oss/mnemosyne
- PyPI package: https://pypi.org/project/mnemosyne-memory/
- Hermes integration: https://github.com/mnemosyne-oss/mnemosyne/blob/main/docs/hermes-integration.md
- Configuration: https://github.com/mnemosyne-oss/mnemosyne/blob/main/docs/configuration.md
- Integrations: https://github.com/mnemosyne-oss/mnemosyne/tree/main/docs/integrations

## 출처

- https://docs.mnemosyne.site/
- https://github.com/mnemosyne-oss/mnemosyne
- https://pypi.org/project/mnemosyne-memory/
- https://github.com/mnemosyne-oss/mnemosyne/blob/main/docs/hermes-integration.md
- https://github.com/mnemosyne-oss/mnemosyne/blob/main/docs/configuration.md

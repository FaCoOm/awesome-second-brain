# taOSmd

## 개요

- 웹사이트 / 문서: https://github.com/jaylfc/taosmd
- Repository: https://github.com/jaylfc/taosmd
- Release: https://github.com/jaylfc/taosmd/releases/tag/v0.2.0
- 회사 / 관리자: jaylfc, taOS ecosystem 일부
- 상태: Python API, CLI, local HTTP/REST, MCP surface가 있는 open-source Python package, 첫 tagged release v0.2.0
- 오픈소스: 예, GitHub가 인식한 MIT license repository
- 배포: Local-first. PyPI 또는 source install 경로를 사용합니다. Local ONNX embedding과 Ollama 기반 local LLM, 또는 RK3588 NPU의 RKLLM 경로로 offline 실행합니다. Optional remote client mode는 사용자가 운영하는 `taosmd serve` instance를 local CLI에서 호출합니다.
- 주요 사용자: modest hardware나 single-board hardware에서 offline local-first agent memory layer를 운영하고 싶은 개발자와 agent 운영자
- 세컨드 브레인 역할: zero-loss archive가 있는 local-first offline agent memory layer
- 마지막 검토: 2026-06-08

## 한 줄 요약

taOSmd는 모든 conversation turn을 append-only archive에 verbatim으로 저장한 뒤, 그 위에 vector search, temporal knowledge graph, librarian layer를 얹고 Python API, CLI, local HTTP/REST API, MCP server로 노출하는 local-first offline agent memory layer입니다.

## 세컨드 브레인 적합도

taOSmd는 offline으로 modest hardware에서 실행해야 하는 agent용 memory backend에 가장 잘 맞습니다. 세컨드 브레인이 source transcript를 byte-for-byte로 보존해야 하고, cloud API 없이 Raspberry Pi, Intel mini PC, 오래된 laptop, NPU가 있는 single-board computer 같은 환경의 memory budget 안에서 돌아가야 할 때 유용합니다.

이 레포의 landscape에서는 Mnemosyne, Mem0/OpenMemory, Hindsight, Honcho, Cognee와 가깝습니다. Hosted memory product보다 programmable하고 local-first 성격이 강하지만, built-in connector, wiki UI, team governance가 있는 end-to-end 세컨드 브레인 앱보다는 직접 운영해야 할 부분이 많습니다. 주요 차이는 append-only zero-loss archive와 low-end hardware/offline 운영에 대한 초점입니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | Local-first. PyPI 또는 source install 경로를 사용합니다. Local SQLite store, local ONNX embedding, Ollama 기반 local LLM 또는 RK3588 NPU의 RKLLM을 사용합니다. Optional remote client mode는 사용자가 운영하는 `taosmd serve` instance를 대상으로 합니다. |
| 맥락 수집 | API, HTTP, MCP 기반입니다. 각 conversation turn을 append-only archive에 verbatim으로 먼저 기록하고, vector와 knowledge graph indexing을 그 위에 얹습니다. Capture는 agent/developer 주도이며 넓은 OAuth connector 계층은 아닙니다. |
| 지식 정리 | Append-only archive, local vector index, temporal knowledge graph, stored turn 위의 librarian retrieval layer가 내장되어 있습니다. |
| Memory 발전 | Correction과 supersede가 knowledge graph와 vector layer 양쪽에서 superseded fact가 recall되지 않게 하고, retention score가 memory를 aging합니다. Scheduled dream이나 consolidation cycle은 없고 raw archive는 항상 보존됩니다. |
| 검색 / 활용 | Hybrid keyword + vector search, fusion, optional reranker, temporal knowledge graph, librarian을 사용합니다. MCP, HTTP/REST, Python API, CLI surface가 agent에게 context를 검색해 줄 수 있습니다. |
| 에이전트 활용 / 쓰기 반영 | Stdio 기반 MCP server, `taosmd serve`의 local HTTP/REST API, Python API, CLI가 내장되어 있습니다. 공식 문서는 Claude Code, OpenClaw, Cursor와 다른 MCP-compatible client 사용을 설명하며, per-turn agent-rules block과 Claude Code skill을 포함합니다. |
| 개인 / 팀 범위 | 부분 지원. Agent별 shelf와 cross-agent read가 있지만, team permission과 review workflow는 product surface가 아닙니다. |
| 검토 / 정정 | Correction과 supersede가 raw archive row를 보존한 채 knowledge graph와 vector layer에 적용되고, pending-review list가 low-confidence item을 노출합니다. |
| 프라이버시 / 통제권 | 기본적으로 local-first/offline입니다. Local SQLite store, local ONNX embedding, configurable data directory를 사용하고 cloud call이 없습니다. A2A bus에서는 secret이 redaction됩니다. Embedding과 LLM 동작은 설정한 local model에 의존합니다. |
| 설정 / 운영 | 중간. 검증된 경로는 PyPI 또는 source install, local embedding model, local LLM입니다. Retrieval/extraction 품질은 local model과 configuration에 달려 있습니다. |

## 강점

- Append-only zero-loss archive: verbatim turn을 먼저 저장하고 summary와 structure는 그 위에 얹습니다.
- Modest hardware나 single-board hardware에서 offline 실행할 수 있고 RK3588 board용 NPU 경로가 있습니다.
- Python API, CLI, local HTTP/REST API, MCP server가 문서화되어 있으며 source install 기준 clean machine에서 설치 검증이 보고되어 있습니다.
- Per-agent shelf와 cross-agent read가 개발자에게 격리 primitive를 제공합니다.
- Correction과 supersede가 knowledge graph와 vector layer 양쪽에 적용되면서 raw archive는 보존됩니다.
- Maintainer-published benchmark와 방법론이 repository에 포함되어 있습니다.

## 한계

- 완성형 소비자 세컨드 브레인 앱이 아니라 memory backend입니다.
- PyPI install 경로는 있지만, local LLM과 model까지 설치하는 one-line bootstrap은 clean machine에서 계속 검증 중입니다.
- 넓은 app connector, hosted dashboard, team permission, source governance가 주된 제품 surface는 아닙니다.
- Benchmark 숫자는 maintainer-run local result이며, 재현 없이는 independent third-party evaluation으로 다루면 안 됩니다.
- Retrieval과 extraction 품질은 local embedding/LLM model, configuration, agent write behavior에 의존합니다.

## 잘 맞는 경우

- Raspberry Pi, single-board computer, Intel mini PC, 오래된 laptop, 작은 cluster에서 offline local-first agent memory layer가 필요한 개발자.
- Hosted service를 운영하지 않고 MCP 또는 HTTP로 접근 가능한 local memory가 필요한 agent 운영자.
- Summary와 correction 이후에도 verbatim transcript를 byte-for-byte로 보존해야 하는 workflow.
- Managed memory platform보다 local SQLite ownership을 선호하는 사용자.

## 잘 맞지 않는 경우

- Hosted dashboard, built-in OAuth connector, 낮은 설정 부담을 원하는 사용자.
- Workspace permission, admin control, governance UI가 즉시 필요한 팀.
- 제한된 notebook이나 wiki만으로 충분한 source-grounded research workflow.
- Source install이나 local LLM/embedding model 운영을 원하지 않는 비기술 사용자.

## 트레이드오프

taOSmd는 강한 local control, low-end hardware에 맞는 offline footprint, zero-loss archive를 제공하지만, model 운영과 integration 판단을 사용자에게 넘깁니다. Hosted option은 없으므로 검증된 경로는 PyPI 또는 source install과 local LLM/embedding model 운영입니다. 주요 요구가 완성형 hosted 세컨드 브레인 제품이 아니라 local 또는 programmable agent memory라면 Mnemosyne, Mem0/OpenMemory, Hindsight, Honcho, Cognee와 비교하는 것이 적절하며, offline 운영, low-end hardware, byte-for-byte source record가 중요할 때 더 높게 평가할 수 있습니다.

## 공식 설정 / 평가 링크

- Repository: https://github.com/jaylfc/taosmd
- Release v0.2.0: https://github.com/jaylfc/taosmd/releases/tag/v0.2.0
- Benchmarks and methodology: https://github.com/jaylfc/taosmd/blob/master/docs/benchmarks.md
- Agent integration rules: https://github.com/jaylfc/taosmd/blob/master/taosmd/docs/agent-rules.md

## 출처

- https://github.com/jaylfc/taosmd
- https://github.com/jaylfc/taosmd/releases/tag/v0.2.0
- https://github.com/jaylfc/taosmd/blob/master/docs/benchmarks.md
- https://github.com/jaylfc/taosmd/blob/master/README.md

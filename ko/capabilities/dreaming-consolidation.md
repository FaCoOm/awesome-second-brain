# Memory 발전

## 이 기능 축의 의미

Memory 발전은 수집 이후에도 세컨드 브레인을 유용하게 유지하는 지속 작업입니다. 요약, 중복 제거, 사실 복구, 오래된 임베딩 복구, 출처 정리, 가지치기, 회고, 종합이 포함됩니다.

## 평가 질문

- 이름이 붙은 유지보수 또는 발전 루프가 있는가?
- 제품이 관리하는가, 사용자가 운영하는가, 커스텀 구현인가?
- 검색 품질을 복구하는가, 아니면 요약만 하는가?
- 제안된 변경이 durable memory가 되기 전에 사용자가 확인할 수 있는가?

## 솔루션 매트릭스

| 솔루션 | 지원 수준 | 도입 방식 | 주의할 점 |
|---|---|---|---|
| Membase | 내장 | smart digesting과 제품이 관리하는 업데이트. | 일정과 내부 동작은 제품이 관리합니다. |
| OpenHuman | 부분 지원 | 20분마다 자동 가져오기, memory collapse, background thinking. | durable curated knowledge loop인지는 아직 검증이 필요합니다. |
| GBrain | 내장 | `gbrain dream` 유지보수 cycle, `gbrain autopilot`, sync/embed 작업. | 사용자가 작업을 운영하고 품질을 검증해야 합니다. |
| Supermemory | 내장 | 제품이 관리하는 graph memory 업데이트, 관계 추적, 자동 forgetting. | 사용자가 운영하는 dream loop로 노출되지는 않습니다. |
| Mem0/OpenMemory | 부분 지원 | memory 승격/검색 동작과 플랫폼 처리. | 명시적인 통합 정책은 앱이 소유합니다. |
| Zep/Graphiti | 내장 | temporal graph 업데이트, fact, summary. | 애플리케이션이 업데이트를 정확히 수집해야 합니다. |
| Cognee | 내장 | `improve`와 graph processing workflow. | 용어는 dreaming과 다릅니다. |
| Khoj | 부분 지원 | 인덱싱과 assistant workflow. | 이 레포의 현재 평가에서는 중앙 dream loop가 없습니다. |
| Obsidian/Logseq + AI bridge | 커스텀 수집기 | 야간 스크립트, 플러그인, 외부 memory 서비스. | 사용자가 검토와 write-back 안전성을 책임집니다. |
| ChatGPT Memory | 내장 | 플랫폼이 관리하는 memory 동작. | 사용자가 운영하는 유지보수 루프로 노출되지는 않습니다. |
| Claude Projects/Claude Code | 내장 | 플랫폼 RAG/프로젝트 지식 동작. | 사용자가 운영하는 dream loop가 아닙니다. |
| NotebookLM | 부분 지원 | 요약과 생성된 결과물. | 지속적인 세컨드 브레인 유지보수 루프는 아닙니다. |

## 출처

- [Membase overview](https://docs.membase.so/)
- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)

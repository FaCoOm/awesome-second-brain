# 검색과 활용

## 이 기능 축의 의미

검색과 활용은 시스템이 관련 memory를 어떻게 찾는지, 출처 맥락을 보존할 수 있는지, 사람 또는 AI 도구가 실제 작업에서 그 맥락을 적용할 수 있는지를 다룹니다.

## 평가 질문

- 검색이 키워드 검색, 벡터 검색, 그래프 검색, RAG, hybrid model 중 무엇을 사용하는가?
- 검색 시 출처, 시각, 프로젝트, collection, 권한 신호가 제공되는가?
- 사용자 또는 AI 도구가 memory 뒤의 출처를 인용하거나 확인할 수 있는가?
- 최신 출처 데이터와 오래되었거나 가져왔거나 추론된 memory를 구분할 수 있는가?

## 솔루션 매트릭스

| 솔루션 | 지원 수준 | 도입 방식 | 주의할 점 |
|---|---|---|---|
| Membase | 내장 | 출처/프로젝트/날짜 필터가 있는 Memory용 graph + vector hybrid RAG, collection 범위 지정이 있는 Wiki용 vector + keyword hybrid search. | 대시보드 채팅과 연결된 에이전트가 두 저장소를 모두 사용할 수 있습니다. 대상 계정에서 사용 가능한 정보원을 확인하세요. |
| OpenHuman | 내장 | 로컬 Memory Tree, Obsidian 호환 Markdown vault, memory graph, 맥락 압축. | 출처/근거 동작은 직접 검증이 필요합니다. |
| GBrain | 내장 | `search`는 저비용 hybrid retrieval, `query`는 필터가 있는 확장 hybrid retrieval, graph/link 신호, timeline/fact retrieval, `think`는 인용/충돌/누락 분석이 있는 종합 답변. | 품질은 동기화, 임베딩, 정리된 출처 구조, reranker/provider 설정에 의존합니다. |
| Supermemory | 내장 | 추출된 memory와 문서 chunk를 함께 찾는 hybrid search, graph memory, project/container 범위 지정, 메타데이터, API 필터. | 커넥터와 프로젝트 범위를 신중히 설정해야 합니다. |
| Mem0/OpenMemory | 내장 | user ID, run ID, metadata가 있는 layered memory search. | 앱 소유자가 grounding과 출처 메타데이터 품질을 정의합니다. |
| Zep/Graphiti | 내장 | temporal knowledge graph, fact, episode, Graph RAG. | 애플리케이션 데이터가 명시적으로 모델링될 때 가장 좋습니다. |
| Cognee | 내장 | knowledge graph memory와 recall 도구. | 검색 품질은 수집과 그래프 처리 모드에 의존합니다. |
| Khoj | 내장 | 파일/노트 위의 자연어 검색과 채팅. | 자료 Q&A에는 강하지만 여러 도구를 아우르는 넓은 세컨드 브레인 계층으로는 약합니다. |
| Obsidian/Logseq + AI bridge | 연동 | 로컬 검색, backlink, graph view, bridge가 제공하는 RAG/search. | grounding 품질은 선택한 bridge에 의존합니다. |
| ChatGPT Memory | 부분 지원 | 플랫폼 memory, 대화 히스토리 참조, 지원되는 Memory Sources. | 출처와 검색 내부 동작은 플랫폼이 통제하며 요금제/지역에 따라 달라집니다. |
| Claude Projects/Claude Code | 내장 | 프로젝트 지식 검색/RAG와 Claude 맥락 표면. | grounding은 Claude 맥락과 요금제 동작 안에 묶입니다. |
| NotebookLM | 내장 | 출처 기반 notebook 검색과 출처 선택. | 제한된 출처 묶음에는 강하지만 workflow 전반에 걸친 살아 있는 세컨드 브레인으로는 약합니다. |

## 출처

- [Membase MCP](https://docs.membase.so/features/membase-mcp)
- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [NotebookLM source docs](https://support.google.com/notebooklm/answer/16215270?hl=en)

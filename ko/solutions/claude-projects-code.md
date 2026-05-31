# Claude Projects / Claude Code

## 개요

- 웹사이트 / 문서: https://support.claude.com/en/articles/9517075-what-are-projects
- 회사 / 관리자: Anthropic
- 상태: 활성 플랫폼 기능 및 개발자 에이전트 표면
- 오픈소스: 아니오
- 배포: 호스팅형 Claude 플랫폼 + 로컬 Claude Code agent runtime
- 주요 사용자: Claude 사용자, Claude Code 사용자, Claude work plan의 팀
- 세컨드 브레인 역할: Claude 범위의 프로젝트 지식과 개발자 에이전트 맥락
- 마지막 검토: 2026-05-31

## 한 줄 요약

Claude Projects는 대화 히스토리, 프로젝트 지식, 지침, 자동 RAG 기반 검색이 있는 self-contained workspace를 제공하고, Claude Code는 terminal, IDE, desktop, web workflow 전반에 개발자 에이전트 맥락을 추가합니다.

## 세컨드 브레인 적합도

Claude Projects는 Claude 안의 범위 지정된 프로젝트 지식에는 강합니다. 외부 MCP 또는 memory service와 함께 쓰지 않는 한 일반적인 portable memory backend는 아닙니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | 호스팅형 Claude project. Claude Code는 terminal, IDE, desktop, web surface에서 사용할 수 있습니다. |
| 맥락 수집 | 내장 file/document upload와 project instruction. connector는 Claude 요금제와 설정에 의존합니다. |
| 지식 정리 | 내장 project knowledge 처리와, project knowledge가 context limit에 가까워지거나 초과할 때 자동으로 켜지는 RAG activation. |
| Memory 발전 | 내장 플랫폼 동작이며 사용자가 운영하는 dream loop는 아닙니다. |
| 검색 / 활용 | 필요할 때 project knowledge search/RAG. |
| 에이전트 활용 / 쓰기 반영 | Claude platform, Claude Code, 활성화된 Claude connector/MCP. Claude Code는 project instruction, CLAUDE.md file, auto memory, skill, hook, MCP server도 사용할 수 있습니다. |
| 개인 / 팀 범위 | Team/Enterprise plan에서는 permission level과 함께 project sharing 가능. |
| 검토 / 정정 | Claude project UI, knowledge base, instruction, sharing control, RAG indicator. |
| 프라이버시 / 통제권 | visibility와 connector access는 요금제/workspace control에 의존합니다. |
| 설정 / 운영 | 낮음-중간. project를 만들고 knowledge를 추가하며 필요하면 tool을 연결합니다. |

## 강점

- Claude-native project context에 매우 좋음.
- project knowledge가 context limit에 가까워지면 RAG가 자동으로 켜짐.
- work plan에서는 team sharing과 permission이 있음.
- Claude Code는 repo-local developer workflow에 강함.

## 한계

- external connector를 추가하지 않으면 memory가 Claude 범위 안에 묶임.
- 범용 세컨드 브레인 계층이 아님.
- project knowledge는 구조화된 장기 personal/team memory backend와 다름.

## 잘 맞는 경우

- project-scoped knowledge와 instruction을 원하는 Claude 사용자.
- Claude Team 또는 Enterprise plan에서 이미 작업하는 팀.
- repo-local workflow에 Claude Code를 쓰는 developer.

## 잘 맞지 않는 경우

- Claude가 아닌 agent 전반에 공유되는 하나의 memory layer가 필요한 사용자.
- retrieval, storage, schema에 대한 완전한 control이 필요한 workflow.
- 단일 platform workspace를 넘어 오래 지속되어야 하는 personal/team knowledge.

## 트레이드오프

Claude Projects는 polished Claude-native project workspace에 최적화되어 있습니다. 트레이드오프는 범위입니다. project knowledge는 Claude context 안에서는 유용하지만, external connector 또는 별도 memory backend와 결합하지 않으면 portable memory system은 아닙니다.

## 공식 설정 / 평가 링크

- [Claude Projects](https://support.claude.com/en/articles/9517075-what-are-projects)
- [RAG for Claude Projects](https://support.claude.com/en/articles/11473015-retrieval-augmented-generation-rag-for-projects)
- [Claude Code overview](https://code.claude.com/docs/en/overview)

## 출처

- [Claude Projects](https://support.claude.com/en/articles/9517075-what-are-projects)
- [RAG for Claude Projects](https://support.claude.com/en/articles/11473015-retrieval-augmented-generation-rag-for-projects)
- [Claude Code overview](https://code.claude.com/docs/en/overview)

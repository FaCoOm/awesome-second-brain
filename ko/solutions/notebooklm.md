# NotebookLM

## 개요

- 웹사이트 / 문서: https://notebooklm.google.com/ 및 https://support.google.com/notebooklm/
- 회사 / 관리자: Google
- 상태: 활성 호스팅 제품
- 오픈소스: 아니오
- 배포: 호스팅형 Google 제품
- 주요 사용자: 제한된 source set에서 작업하는 researcher, student, analyst, team
- 세컨드 브레인 역할: 출처 기반 research notebook 기준선
- 마지막 검토: 2026-05-31

## 한 줄 요약

NotebookLM은 업로드하거나 발견한 source로 notebook을 만들고, source-grounded question을 묻고, summary/study artifact를 생성하게 합니다.

## 세컨드 브레인 적합도

NotebookLM은 알려진 source set에 대한 bounded research에 강합니다. source가 notebook 안으로 import되고 사용이 platform-scoped라 living second brain으로는 약합니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | 호스팅형 Google 제품. |
| 맥락 수집 | docs, slides, sheets, images, Word, text, Markdown, PDF, CSV, PowerPoint, web URL, ePub, YouTube, audio, Gemini Chats, Fast Research, Deep Research 등 upload/import/discovery 내장 지원. |
| 지식 정리 | source가 충분한 notebook의 내장 source summary, source label/category, generated artifact. |
| Memory 발전 | 부분 지원. summary와 artifact는 유용하지만 지속적인 세컨드 브레인 consolidation loop는 아닙니다. |
| 검색 / 활용 | source-grounded notebook chat과 source selection. |
| 에이전트 활용 / 쓰기 반영 | 일반 사용자에게는 NotebookLM/Gemini platform only. |
| 개인 / 팀 범위 | sharing/collaboration은 Google account/product tier에 의존합니다. |
| 검토 / 정정 | notebook UI, source panel, source selection, label, generated artifact가 강함. |
| 프라이버시 / 통제권 | hosted platform. imported source는 supported Drive sync behavior를 제외하면 static copy입니다. |
| 설정 / 운영 | 낮음. notebook을 만들고 source를 추가합니다. |

## 강점

- source-grounded Q&A에 매우 좋음.
- 넓은 source type 지원.
- report, study guide, briefing, research synthesis에 좋음.

## 한계

- tool/workflow 전반의 persistent second-brain layer가 아님.
- source는 static copy일 수 있고 non-Drive source는 manual re-upload가 필요할 수 있음.
- agent write-back이나 team-wide memory governance를 위해 설계되지 않음.

## 잘 맞는 경우

- 제한된 source set에서 작업하는 researcher, student, analyst, team.
- source-grounded Q&A, summary, briefing, study artifact.
- notebook 자체가 primary interface인 workflow.

## 잘 맞지 않는 경우

- 많은 AI tool, teammate, session에 걸쳐 memory가 누적되어야 하는 사용자.
- shared knowledge layer로 agent write-back이 필요한 팀.
- bounded research보다 source freshness와 automation이 중요한 workflow.

## 트레이드오프

NotebookLM은 사용자가 source set을 upfront로 정의하고 notebook 안에서 작업할 수 있을 때 탁월합니다. 트레이드오프는 imported source와 generated artifact가 기본적으로 living second brain처럼 동작하지 않는다는 점입니다.

## 공식 설정 / 평가 링크

- [NotebookLM source docs](https://support.google.com/notebooklm/answer/16215270?hl=en)

## 출처

- [NotebookLM source docs](https://support.google.com/notebooklm/answer/16215270?hl=en)

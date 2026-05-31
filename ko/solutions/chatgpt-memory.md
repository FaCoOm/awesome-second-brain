# ChatGPT Memory

## 개요

- 웹사이트 / 문서: https://help.openai.com/en/articles/8590148-memory-faq
- 회사 / 관리자: OpenAI
- 상태: 활성 플랫폼 기능
- 오픈소스: 아니오
- 배포: 호스팅형 ChatGPT 기능
- 주요 사용자: ChatGPT 사용자
- 세컨드 브레인 역할: 플랫폼 내 개인화 기준선
- 마지막 검토: 2026-05-31

## 한 줄 요약

ChatGPT Memory는 저장된 memory와, 활성화된 경우 대화 히스토리 및 지원되는 Memory Sources를 사용해 ChatGPT가 이후 대화를 개인화하게 합니다.

## 세컨드 브레인 적합도

ChatGPT Memory는 ChatGPT 안에서는 유용하지만 완전한 자가 발전형 세컨드 브레인은 아닙니다. 더 넓은 수집, 정리, 검색 계층을 도입하기 전, 저장된 memory, 대화 히스토리, 요금제에 따라 달라지는 Memory Sources를 포함한 플랫폼 내 개인화의 기준선으로 다루는 것이 좋습니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | 호스팅형 ChatGPT 플랫폼. |
| 맥락 수집 | 내장 saved memories와 대화 히스토리 참조. Memory Sources는 요금제, 지역, 설정에 따라 custom instructions, 파일, 연결된 Gmail도 포함할 수 있습니다. |
| 지식 정리 | 내장 자동 memory 관리와 사용자 제어. |
| Memory 발전 | 내장 플랫폼 동작입니다. 사용자가 운영하는 workflow로 노출되지는 않습니다. |
| 검색 / 활용 | ChatGPT 안에서 플랫폼이 제어하는 memory, 대화 히스토리 참조, Memory Sources 기반 개인화. |
| 에이전트 활용 / 쓰기 반영 | ChatGPT 플랫폼 전용. |
| 개인 / 팀 범위 | workspace/admin 동작은 ChatGPT 요금제와 설정에 의존합니다. 현재 FAQ 기준 Enterprise workspace owner는 Memory를 켜거나 끌 수 있고, Reference Chat History는 Enterprise/Edu customer에게 제공되지 않습니다. |
| 검토 / 정정 | Settings, Manage memories, memory 검색/정렬, memory history 복원, Memory Sources feedback. |
| 프라이버시 / 통제권 | 사용자는 remembered content를 물어보거나, memory를 삭제하거나, 설정을 끄거나, Temporary Chat을 사용할 수 있습니다. 개인화 맥락을 완전히 제거하려면 관련 chat, file, connected-app data 삭제가 함께 필요할 수 있습니다. |
| 설정 / 운영 | 낮음. memory 설정을 켜거나 끕니다. |

## 강점

- ChatGPT-native 개인화에 별도 설정이 필요 없음.
- saved memory에 대한 사용자 제어가 명확함.
- 선호와 장기적인 상호작용 스타일에 유용함.

## 한계

- Claude, Cursor, Codex, 기타 AI 도구로 portable하지 않음.
- 일반적인 source ingestion 또는 팀 지식 backend로 설계되지 않았고, 지원되는 files/Gmail source는 플랫폼, 요금제, 지역에 묶임.
- retrieval/consolidation 내부 동작은 developer가 운영할 수 없음.

## 잘 맞는 경우

- 설정 없는 개인화를 원하는 ChatGPT 사용자.
- 선호, 반복 지시, 장기적인 상호작용 스타일.
- platform-native memory의 기준선 비교.

## 잘 맞지 않는 경우

- 여러 AI 도구에서 사용할 하나의 세컨드 브레인이 필요한 사용자.
- 출처 기반 지식 계층과 거버넌스가 필요한 팀.
- memory API, custom retrieval, 외부 write-back이 필요한 builder.

## 트레이드오프

ChatGPT Memory는 하나의 플랫폼 안에서의 편의성에 최적화되어 있습니다. 트레이드오프는 이동성입니다. memory는 ChatGPT 안에서는 유용하지만 기본적으로 다른 도구가 읽고, 업데이트하고, 공유할 수 있는 일반 세컨드 브레인 backend는 아닙니다.

## 공식 설정 / 평가 링크

- [ChatGPT Memory FAQ](https://help.openai.com/en/articles/8590148-memory-faq)

## 출처

- [ChatGPT Memory FAQ](https://help.openai.com/en/articles/8590148-memory-faq)

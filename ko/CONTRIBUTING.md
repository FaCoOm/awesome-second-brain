# Awesome AI Second Brain 기여 가이드

이 레포는 AI-native 세컨드 브레인을 만들기 위한 기존 도구와 제품을 비교합니다. 기여 내용은 독자가 무엇을 평가해야 하는지, 어떤 트레이드오프가 중요한지, 어떤 workflow가 실제로 지원되는지 판단하는 데 도움이 되어야 합니다.

## 포함해야 하는 것

좋은 기여는 실용적인 질문에 답합니다.

- memory가 어디에 있는가: local, hosted, self-hosted, platform-bound 중 무엇인가?
- 처음 쓸 만한 memory를 얻기까지 얼마나 걸리는가?
- 어떤 데이터를 수집할 수 있는가?
- 원본 데이터가 자동으로 정리된 지식이 되는가?
- 통합, 회고, dream cycle을 지원하는가?
- AI 도구가 MCP, API, SDK, CLI, plugin을 통해 읽고 쓸 수 있는가?
- 개인, 프로젝트, workspace, team scope를 분리할 수 있는가?
- 사용자가 무엇을 확인, 편집, 삭제, 내보내기, 감사할 수 있는가?

## 솔루션 추가 방법

1. [templates/system-profile.md](templates/system-profile.md)를 `solutions/<solution-name>.md`로 복사합니다.
2. 솔루션을 [solutions/README.md](solutions/README.md), [../README.ko.md](../README.ko.md), 관련 비교표에 추가합니다.
3. 출처로 뒷받침하거나 직접 검증할 수 있는 workflow에 대해서만 `capabilities/` 문서를 업데이트합니다.
4. command-by-command 설치 설명을 길게 복제하기보다 공식 설정 문서, 공식 저장소, 1차 출처를 링크합니다.
5. 확실하지 않은 필드는 추측하지 말고 `미확인`으로 표시합니다.

## 설정 가이드 또는 예시 추가 방법

검증된 설정 경로는 `setup-guides/`에, 시나리오 수준 workflow는 `examples/`에 추가합니다. retrieval 또는 write-back이 실제로 동작했다는 검증 방법을 설명할 수 없으면 설정 가이드로 추가하지 마세요.

## 프로필 품질 기준

모든 솔루션 프로필은 아래 항목에 답해야 합니다.

- 배포와 소유권 요약
- 맥락 수집 방식
- 지식 정리 방식
- 통합 또는 유지보수 방식
- 검색과 근거 제시 방식
- AI 도구 활용과 write-back surface
- workspace와 team 지원
- UI, 검토, 정정 surface
- 프라이버시, 이동성, 통제권
- 설정 부담
- 잘 맞는 사용자
- 잘 맞지 않는 사용자
- 트레이드오프
- 공식 설정 또는 평가 링크

## 출처

가능하면 1차 출처를 사용하세요.

- 공식 문서
- 공식 저장소
- maintainer가 작성한 예시
- 제품 문서와 changelog
- 재현 가능한 local test report

local 또는 내부 test report를 사용할 때는 명확하게 요약하고, 검증되지 않은 가정을 제품 주장처럼 쓰지 마세요.

closed-source와 hosted product도 기여 가능합니다. 기여자가 내부 모델, prompt, ranking logic, graph construction, infrastructure detail을 증명하거나 공개할 필요는 없습니다. 문서, 제품 UI, API, 저장소, 직접 테스트로 검증 가능한 공개 동작을 설명하세요. 비공개이거나 확인할 수 없는 세부사항은 `비공개` 또는 `미확인`으로 표시합니다.

## 작성 스타일

- 사실 기반으로 구체적으로 씁니다.
- tutorial 문체보다 의사결정에 도움이 되는 landscape 문체를 선호합니다.
- 내장 지원, 연동 지원, 커스텀 수집기 작업을 구분합니다.
- 관찰 가능한 제품 동작과 공개되지 않은 내부 동작을 구분합니다.
- [../README.ko.md](../README.ko.md)의 표준 지원 라벨을 사용합니다.
- 추천은 해당 workflow에 맞게 범위를 좁히고, 홍보성 표현 없이 트레이드오프를 설명합니다.

## Pull Request 가이드라인

- PR 하나에는 솔루션 또는 workflow 하나만 담는 것을 권장합니다.
- 출처와 검증 메모를 포함합니다.
- 관련 없는 formatting change는 제외합니다.
- placeholder 또는 watchlist entry라면 아직 완전히 평가된 것이 아니라는 점을 명확히 표시합니다.

## 라이선스 동의

기여하면 해당 기여가 이 프로젝트와 동일하게 Apache License 2.0으로 라이선스되는 데 동의하는 것입니다.

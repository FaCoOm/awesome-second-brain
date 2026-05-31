# OpenHuman

## 개요

- 웹사이트 / 문서: https://tinyhumans.ai/openhuman 및 https://openhumanwiki.com/
- 저장소: https://github.com/tinyhumansai/openhuman
- 회사 / 관리자: TinyHumansAI / OpenHuman 관리자
- 상태: 활발히 개발 중인 초기 베타
- 오픈소스: 예, GPL-3.0
- 배포: 로컬 데스크톱 앱. 계정 로그인, 모델 라우팅, 검색 프록시, OAuth/연동 흐름에는 관리형 서비스 사용
- 주요 사용자: memory, UI, 음성, 앱 연동이 있는 로컬 우선 개인 AI assistant를 원하는 사람
- 세컨드 브레인 역할: 자동 memory 수집이 있는 로컬 우선 개인 AI assistant
- 마지막 검토: 2026-05-31

## 한 줄 요약

OpenHuman은 로컬 Memory Tree 저장소, Obsidian 스타일 Markdown vault, 자동 가져오기 연동, 토큰 압축, UI 중심 경험을 제공하는 오픈소스 데스크톱 AI assistant입니다.

## 세컨드 브레인 적합도

OpenHuman은 단순 memory backend가 아니라 내장 세컨드 브레인을 가진 개인 AI assistant로 평가해야 합니다. 많은 앱에 연결하고 최신 데이터를 자동으로 memory로 가져오는 로컬 우선 assistant를 원하는 사용자에게 관련성이 높지만, 아직 초기 베타이며 일부 계정, 모델, 검색, 연동 흐름에는 관리형 서비스를 사용합니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | macOS, Windows, Linux 데스크톱 앱. 필요한 곳에서는 관리형 서비스를 사용하면서 로컬 memory와 runtime state를 둡니다. |
| 맥락 수집 | OAuth/Composio 스타일 커넥터 흐름을 통한 118개 이상의 연동. 문서 기준 20분마다 자동 가져오기. |
| 지식 정리 | 내장 Memory Tree, 로컬 SQLite 지식 베이스, Obsidian 스타일 Markdown vault, 토큰 압축, 계층형 요약 트리, memory collapse flow. |
| Memory 발전 | 내장 background thinking과 자동 가져오기/collapse 동작이 있지만 정확한 consolidation policy는 직접 사용으로 확인해야 합니다. |
| 검색 / 활용 | 로컬 Memory Tree, Obsidian 호환 Markdown vault, memory graph, 맥락 압축. |
| 에이전트 활용 / 쓰기 반영 | 주로 자체 데스크톱 assistant 중심. 관련 persistent storage workflow로 MCP/agentmemory sharing이 문서화되어 있습니다. |
| 개인 / 팀 범위 | 개인 우선. Team/workspace 공유는 주 용도가 아닙니다. |
| 검토 / 정정 | 데스크톱 mascot, 온보딩, 음성, Google Meet 참여, 로컬 memory surface 등 UI 중심 positioning이 강함. |
| 프라이버시 / 통제권 | 로컬 memory file과 runtime state는 사용자 machine에 있지만, 기본 경험에는 관리형 서비스가 포함됩니다. |
| 설정 / 운영 | 낮음-중간. native package 설치는 간단하지만 커넥터와 관리형/로컬 provider 선택지가 설정 결정을 늘립니다. |

## 강점

- "personal AI second brain" 사용자에게 직접적으로 맞음.
- Memory Tree와 Markdown vault가 있는 로컬 우선 저장 모델.
- 넓은 연동 범위와 자동 갱신 루프.
- CLI 중심 도구보다 비개발자에게 쉬울 수 있는 UI 중심 데스크톱 경험.

## 한계

- 초기 베타라 거친 부분이 있을 수 있음.
- 기본 경험은 로그인, 모델 라우팅, 검색 프록시, OAuth/연동 흐름에 관리형 서비스 의존성이 있음.
- dedicated memory backend보다 shared second-brain infrastructure로의 이동성이 덜 명확함.
- team/workspace 거버넌스가 핵심 positioning은 아님.

## 잘 맞는 경우

- memory가 있는 개인 데스크톱 AI assistant를 원하는 사용자.
- 로컬 memory를 중요하게 보지만 앱 연동도 쉽게 쓰고 싶은 사용자.
- GBrain/Khoj/Obsidian 스타일 local-first approach와 더 제품화된 assistant를 비교하는 사람.

## 잘 맞지 않는 경우

- 여러 도구에 걸친 shared memory와 workspace 거버넌스가 필요한 팀.
- memory API/SDK만 필요한 builder.
- 성숙하고 안정적인 non-beta 제품이 필요한 사용자.

## 트레이드오프

OpenHuman은 넓은 연동 목표를 가진 제품화된 로컬 우선 assistant를 제공합니다. 트레이드오프는 성숙도와 이동성입니다. 베타 데스크톱 경험은 개인 memory에는 유용하지만, 팀은 shared infrastructure로 보기 전에 커넥터 신뢰성, 관리형 서비스 의존성, 공유 동작을 확인해야 합니다.

## 공식 설정 / 평가 링크

- [OpenHuman Wiki](https://openhumanwiki.com/)
- [OpenHuman user guide](https://www.openhuman.dev/)
- [OpenHuman GitHub repo](https://github.com/tinyhumansai/openhuman)

## 출처

- [OpenHuman GitHub repo](https://github.com/tinyhumansai/openhuman)
- [OpenHuman Wiki](https://openhumanwiki.com/)
- [OpenHuman user guide](https://www.openhuman.dev/)

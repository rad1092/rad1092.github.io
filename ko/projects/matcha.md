---
layout: project
lang: ko
project: matcha
title: Matcha
description: 속을 들여다볼 수 있고, Claude가 직접 플레이하는 게임보이 에뮬레이터.
permalink: /ko/projects/matcha/
---

## 하는 일

Matcha는 게임보이·게임보이 컬러 에뮬레이터입니다. 코어 하나를 세 가지 방식으로
씁니다.

- **웹 플레이어.** HTML 파일 하나로 소리, 게임패드·터치 입력, 세이브 스테이트,
  20초 되감기, 실시간 디버거(CPU, 디스어셈블리, 줄 단위 화면 타이밍, VRAM,
  오디오 채널, RAM 검색)를 제공합니다.
- **Claude 플러그인.** `load_rom`, `press`, `screenshot`, `breakpoint`,
  `find_value` 같은 MCP 도구 17개로 Claude가 게임보이 소프트웨어를 플레이하고
  테스트하고 디버깅합니다.
- **명령줄.** 화면 없이 실행, 스크린샷, 정확도 점수표, 프로파일러, 명령어
  추적기, 디스어셈블러.

{% include media.html m=site.data.projects.matcha.media.extra lazy=true %}

## 만든 방식

- 코어는 `no_std`이고 외부 의존성과 `unsafe`가 없습니다. 브라우저, MCP 서버,
  플러그인이 모두 같은 WebAssembly 빌드를 씁니다.
- 코어는 시계나 난수를 읽지 않습니다. 같은 ROM, 입력, 상태면 항상 같은 화면과
  소리가 나와서, 세이브·되감기와 Claude의 디버깅 세션을 그대로 다시 재현할 수
  있습니다.
- 세이브 스테이트는 버전을 붙이고 불러올 때 검증합니다.

## 검증 방법

| 테스트 | 통과 |
| --- | --- |
| SingleStepTests SM83 (모든 명령, 모든 버스 사이클) | 498,000 / 498,000 |
| Mooneye | 94 / 94 |
| Blargg | 43 / 43 |
| Gambatte | 1,642 / 1,783 |

원래 게임보이용 Homebrew Hub 카트리지 868개를 Matcha와 SameBoy에서 나란히
돌려 비교했습니다. 이 비교로 Matcha 버그 세 개를 찾아 고쳤습니다.

## 다음 계획

- 게임보이 컬러 점수표에 남은 타이밍 실패.
- 게임보이 컬러 하드웨어에서 원래 게임보이 게임에 색을 입히는 기능.

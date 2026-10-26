---
layout: project
lang: ko
project: gh-dep-risk
title: gh-dep-risk
description: PR의 의존성 변경에 점수를 매기고, 먼저 확인할 것을 알려줍니다.
permalink: /ko/projects/gh-dep-risk/
---

## 하는 일

`gh dep-risk pr 123`은 PR의 의존성 변경을 읽고 변경마다 점수를 매긴 뒤, 리뷰어가
먼저 확인할 세 가지로 보고서를 시작합니다. 예를 들어 설치 전에 설치 스크립트를
읽어 보라고 알려줍니다.

```text
left-pad 1.0.0 -> 2.0.0 score=48 (10 major version bump + 18 recently published version + 20 install script)
```

PR 댓글 하나를 달고 계속 갱신할 수 있고, 정한 수준을 넘으면 CI를 실패시킬 수
있고, JSON이나 Markdown으로도 출력합니다. GitHub Action으로 모든 PR에서 같은
검사를 돌릴 수 있습니다.

## 만든 방식

- GitHub Dependency Review API를 먼저 씁니다. npm, pip, Go, Maven, Cargo,
  RubyGems를 포함해 11개 생태계를 다룹니다.
- 그 API를 쓸 수 없으면 npm, pnpm, Yarn, Bun, Python, Go의 lockfile을 직접
  읽습니다. 의존성 해석기나 전체 그래프는 만들지 않고, 지원 범위는 지원 표에
  적어 두었습니다.
- 점수의 모든 점은 한 파일에 이름 붙은 신호에서 나오고, JSON 출력에 변경마다
  그 내역이 들어갑니다.
- 릴리스 전 검사에서 확장을 실제로 설치하고, 픽스처 저장소 두 곳의 실제 PR에
  돌려 봅니다.

## 내린 결정

- **서비스가 아니라 명령 하나.** 서버, 웹훅, DB, GitHub App이 없습니다. 리뷰어가
  필요할 때 이미 쓰는 GitHub CLI 로그인으로 실행합니다.
- **따라갈 수 있는 점수.** 이유 없는 숫자는 무시당하니까, 모든 점수에 출처를
  붙이고 다음에 할 일을 알려줍니다.
- **내 댓글만 관리.** 자기 댓글만 갱신하고, 다른 사람 댓글은 수정하거나 지우지
  않습니다.

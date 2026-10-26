---
layout: default
permalink: /repositories/
---

# 깃허브 저장소 목록

`@rad1092`의 공개 저장소입니다. 릴리스 링크는 항상 최신 공개 릴리스로 연결됩니다.

## 제품

| 저장소 | 요약 | 기술 | 링크 |
|---|---|---|---|
| FirstCall | API를 AI 클라이언트에 연결하려는 개발자가 curl·OpenAPI 요청을 실제로 검증하고, 용도와 입력을 설명한 로컬 MCP 도구로 내보냅니다. 서버 하나로 여러 도구를 제공합니다. | Rust · GUI · CLI · MCP | [프로젝트](https://github.com/rad1092/firstcall) · [릴리스](https://github.com/rad1092/firstcall/releases/latest) · [실습](https://github.com/rad1092/firstcall/blob/main/docs/cli-lifecycle.md) |
| Matcha | 게임보이 홈브루 개발자와 에뮬레이터 학습자가 CPU·메모리·화면을 관찰하고, 저장 상태를 재생하거나 MCP 도구로 같은 실행을 반복합니다. | Rust · WASM · MCP | [프로젝트](https://github.com/rad1092/matcha) · [릴리스](https://github.com/rad1092/matcha/releases/latest) · [실습](https://github.com/rad1092/matcha/blob/main/docs/MCP-HOMEBREW.md) |
| SerdeProof | Jackson 3·Spring Boot 4로 옮기기 전에 실제 DTO·매퍼 설정·페이로드로 두 직렬화 빌드의 JSON 차이와 생산자·소비자 조합을 비교합니다. | Java 17 · CLI | [프로젝트](https://github.com/rad1092/serdeproof) · [릴리스](https://github.com/rad1092/serdeproof/releases/latest) · [실습](https://github.com/rad1092/serdeproof#try-the-release-without-building) |
| gh-dep-risk | PR 번호 하나로 새로 들어온 의존성의 위험 점수와 근거, 먼저 확인할 항목을 보여 주는 GitHub CLI 확장입니다. | Go · GitHub CLI | [프로젝트](https://github.com/rad1092/gh-dep-risk) · [릴리스](https://github.com/rad1092/gh-dep-risk/releases/latest) |
| RepoLens | Node 저장소의 PR이 고정되지 않은 액션, 쓰기 권한 토큰, CI가 안 돌리는 스크립트 같은 새 유지보수 문제를 들여올 때만 실패시킵니다. | TypeScript · CLI · GitHub Action | [프로젝트](https://github.com/rad1092/repolens) · [릴리스](https://github.com/rad1092/repolens/releases/latest) |
| Treeport | ZIP·폴더·Git 저장소를 다른 OS로 옮기기 전에 이름 충돌과 경로 길이를 읽기 전용으로 검사합니다. | Go · CLI | [프로젝트](https://github.com/rad1092/treeport) · [릴리스](https://github.com/rad1092/treeport/releases/latest) · [실습](https://github.com/rad1092/treeport/blob/main/docs/first-run.md) |
| Annotrail | 논문·교재 개정판에서 이전 PDF의 하이라이트와 댓글을 새 PDF의 텍스트와 대조하고, 승인한 주석을 새 파일로 옮깁니다. 선택 가능한 텍스트가 있는 PDF가 대상입니다. | Java · PDFBox | [프로젝트](https://github.com/rad1092/annotrail) · [릴리스](https://github.com/rad1092/annotrail/releases/latest) · [실습](https://github.com/rad1092/annotrail/tree/main/examples/review-demo) |
| ConflictBench | Syncthing 충돌 파일의 바뀐 줄·이미지·메타데이터를 비교하고, 원본 유지·충돌본 사용·둘 다 보존 중 하나를 직접 선택합니다. | C++ · Qt | [프로젝트](https://github.com/rad1092/conflictbench) · [릴리스](https://github.com/rad1092/conflictbench/releases/latest) · [실습](https://github.com/rad1092/conflictbench/blob/main/docs/FIRST-RUN.md) |
| PaperStager | 텍스트가 있는 묶음 PDF를 페이지 미리보기로 문서별로 나누고, 텍스트 규칙으로 제안된 파일명을 검토한 뒤 승인하여 내보냅니다. OCR은 없습니다. | C# · Avalonia | [프로젝트](https://github.com/rad1092/paperstager) · [릴리스](https://github.com/rad1092/paperstager/releases/latest) · [실습](https://github.com/rad1092/paperstager#get-started) |

## 실험실

| 저장소 | 요약 | 기술 | 링크 |
|---|---|---|---|
| ShopShift | 소규모 작업장의 계획 담당자가 ERP에서 내보낸 CSV·XLSX로 일일 작업을 배치하고, 충돌과 대안을 오프라인으로 검토합니다. 실제 작업장 검증 전 단계입니다. | Python · PySide6 · OR-Tools | [프로젝트](https://github.com/rad1092/shopshift) · [릴리스](https://github.com/rad1092/shopshift/releases/latest) · [실습](https://github.com/rad1092/shopshift#daily-workflow) |
| Lifecase | CI 단계가 끝나지 않는 문제(자식은 끝났는데 손자 프로세스가 파이프를 잡고 있는 상황)를 Node·Python 테스트로 재현합니다. 보관(읽기 전용). | C++ · Node · Python · Go | [프로젝트](https://github.com/rad1092/lifecase) · [릴리스](https://github.com/rad1092/lifecase/releases/latest) · [실습](https://github.com/rad1092/lifecase#try-it-with-node-or-python) |

## 사이트와 지원 저장소

| 저장소 | 요약 | 링크 |
|---|---|---|
| whago-home | [whago.net](https://whago.net) 사이트 소스 | [바로가기](https://github.com/rad1092/whago-home) |
| gh-dep-risk-smoke-matrix | gh-dep-risk 설치 스모크 테스트와 데모가 쓰는 PR 픽스처 | [바로가기](https://github.com/rad1092/gh-dep-risk-smoke-matrix) |
| gh-dep-risk-smoke-comments | gh-dep-risk 릴리스 전 PR 댓글 스모크 테스트 | [바로가기](https://github.com/rad1092/gh-dep-risk-smoke-comments) |
| rad1092.github.io | 이 포트폴리오 | [바로가기](https://github.com/rad1092/rad1092.github.io) |

## 팀 프로젝트

| 저장소 | 요약 | 기술 | 링크 |
|---|---|---|---|
| project_dashboard | 재난 대피소 추천 대시보드 (4인 팀, 백엔드·아키텍처 담당) | Python · Streamlit | [바로가기](https://github.com/rad1092/project_dashboard) |
| smart-mirror | PC1·PC2·PC3을 통합한 스마트미러 저장소와 시연 자료 | Python | [바로가기](https://github.com/rad1092/smart-mirror) |

## 개발 종료(보관)

| 저장소 | 요약 | 링크 |
|---|---|---|
| daymark | 개발을 종료한 앱. 읽기 전용으로 소스와 릴리스를 보관합니다. | [바로가기](https://github.com/rad1092/daymark) |
| siteboard | 개발을 종료한 앱. 읽기 전용으로 소스와 릴리스를 보관합니다. | [바로가기](https://github.com/rad1092/siteboard) |

프로젝트 문의: [rad174951@gmail.com](mailto:rad174951@gmail.com) · [WHAGO](https://whago.net/ko/)

[<- 메인으로 돌아가기](/)

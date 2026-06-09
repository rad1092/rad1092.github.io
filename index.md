---
layout: default
---

<style>
/* ===== Reset Cayman theme chrome, build a clean canvas ===== */
.page-header { display: none !important; }
.main-content { max-width: 940px !important; margin: 0 auto !important; padding: 0 24px 90px !important; }
.main-content h1, .main-content h2, .main-content h3 { border: none; }
.page-footer, footer.site-footer { display: none !important; }

:root {
  --bg: #0f1115;
  --bg-soft: #161922;
  --card: #1b1f2a;
  --line: #2a2f3d;
  --text: #e6e9ef;
  --muted: #9aa3b2;
  --accent: #64ffda;
  --accent-2: #7aa2ff;
  --radius: 14px;
}

body { background: var(--bg); }
.pf { color: var(--text); font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Apple SD Gothic Neo", "Noto Sans KR", sans-serif; line-height: 1.7; }
.pf a { color: var(--accent); text-decoration: none; }
.pf a:hover { text-decoration: underline; }
.pf .mono { font-family: "SFMono-Regular", Consolas, "Liberation Mono", Menlo, monospace; }

/* ===== Hero ===== */
.hero { display: flex; align-items: center; gap: 32px; padding: 64px 0 24px; flex-wrap: wrap; }
.hero img.avatar { width: 132px; height: 132px; border-radius: 50%; border: 2px solid var(--line); box-shadow: 0 12px 30px rgba(0,0,0,.45); }
.hero .intro { flex: 1; min-width: 260px; }
.hero .eyebrow { color: var(--accent); font-family: monospace; font-size: .9rem; letter-spacing: .04em; margin: 0 0 8px; }
.hero h1 { font-size: 2.8rem; margin: 0 0 14px; line-height: 1.1; }
.hero h1 .en { color: var(--muted); font-size: 1.3rem; font-weight: 500; }
.hero .cta a { display: inline-block; margin: 0 10px 10px 0; padding: 9px 18px; border-radius: 8px; border: 1px solid var(--line); color: var(--text); font-size: .92rem; transition: .15s; }
.hero .cta a:hover { border-color: var(--accent); color: var(--accent); text-decoration: none; transform: translateY(-2px); }
.hero .cta a.primary { background: var(--accent); color: #0a0c10; border-color: var(--accent); font-weight: 600; }

/* ===== Section ===== */
.section { margin-top: 72px; }
.section > h2 { display: flex; align-items: center; gap: 14px; font-size: 1.5rem; margin: 0 0 24px; }
.section > h2 .num { color: var(--accent); font-family: monospace; font-size: 1.05rem; }
.section > h2::after { content: ""; flex: 1; height: 1px; background: var(--line); }

.lead { color: var(--muted); max-width: 760px; }
.lead .hl { color: var(--text); }

/* ===== Skill chips ===== */
.chips { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 20px; }
.chip { background: var(--bg-soft); border: 1px solid var(--line); color: var(--text); padding: 6px 13px; border-radius: 999px; font-size: .85rem; }
.chip b { color: var(--accent); }

/* ===== Timeline (experience) ===== */
.timeline { position: relative; margin-top: 8px; padding-left: 26px; }
.timeline::before { content: ""; position: absolute; left: 6px; top: 6px; bottom: 6px; width: 2px; background: var(--line); }
.tl-item { position: relative; padding: 0 0 26px; }
.tl-item:last-child { padding-bottom: 0; }
.tl-item::before { content: ""; position: absolute; left: -26px; top: 5px; width: 12px; height: 12px; border-radius: 50%; background: var(--bg); border: 2px solid var(--accent); }
.tl-when { font-family: monospace; font-size: .78rem; color: var(--accent); letter-spacing: .03em; }
.tl-role { font-size: 1.08rem; font-weight: 600; margin: 3px 0 2px; }
.tl-role .org { color: var(--muted); font-weight: 400; font-size: .92rem; }
.tl-desc { color: var(--muted); margin: 4px 0 0; font-size: .94rem; }

/* ===== Featured projects: left vertical tabs ===== */
.proj-tabs { display: flex; gap: 26px; align-items: flex-start; }
.proj-nav { flex: 0 0 210px; display: flex; flex-direction: column; position: sticky; top: 20px; }
.pnav-btn { background: none; border: none; border-left: 2px solid var(--line); color: var(--muted); text-align: left; padding: 13px 16px; cursor: pointer; font-family: inherit; font-size: .94rem; line-height: 1.35; transition: .15s; }
.pnav-btn:hover { color: var(--text); background: var(--bg-soft); }
.pnav-btn.active { color: var(--accent); border-left-color: var(--accent); background: var(--bg-soft); font-weight: 600; }
.pnav-btn small { display: block; font-family: monospace; font-size: .7rem; color: var(--muted); margin-bottom: 3px; letter-spacing: .03em; }
.proj-content { flex: 1; min-width: 0; }
.proj-panel { display: none; animation: fade .3s ease; }
.proj-panel.active { display: block; }

.head { display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; flex-wrap: wrap; }
.ptitle { font-size: 1.45rem; margin: 0; }
.repo { font-family: monospace; font-size: .82rem; color: var(--muted); display: block; margin-top: 5px; }
.links a { font-size: .85rem; margin-left: 14px; white-space: nowrap; }
.stack { display: flex; flex-wrap: wrap; gap: 8px; margin: 14px 0 16px; }
.stack span { font-family: monospace; font-size: .76rem; color: var(--accent-2); background: rgba(122,162,255,.08); border: 1px solid rgba(122,162,255,.25); padding: 3px 9px; border-radius: 6px; }
.summary { color: var(--text); margin: 0 0 14px; font-size: 1.02rem; }
.summary b { color: var(--accent); }
.context { color: var(--muted); margin: 0 0 16px; }
.context b { color: var(--text); }

/* AI note woven into each project */
.ai-note { display: flex; gap: 11px; align-items: flex-start; margin: 0 0 20px; padding: 12px 15px; background: rgba(100,255,218,.05); border: 1px solid rgba(100,255,218,.22); border-radius: 9px; font-size: .88rem; color: var(--muted); }
.ai-note .badge { flex: 0 0 auto; font-family: monospace; font-size: .68rem; font-weight: 700; color: #0a0c10; background: var(--accent); padding: 2px 7px; border-radius: 5px; margin-top: 2px; }
.ai-note b { color: var(--text); }

/* ===== Media gallery ===== */
.gallery { display: grid; gap: 12px; margin-bottom: 22px; }
.gallery.cols-2 { grid-template-columns: repeat(2, 1fr); }
.gallery figure { margin: 0; border: 1px solid var(--line); border-radius: 10px; overflow: hidden; background: var(--bg); }
.gallery img { width: 100%; display: block; }
.gallery figcaption { font-size: .78rem; color: var(--muted); padding: 8px 10px; border-top: 1px solid var(--line); }

/* ===== Inner STAR tabs ===== */
.tabs { display: flex; gap: 4px; border-bottom: 1px solid var(--line); flex-wrap: wrap; }
.tab-btn { background: none; border: none; color: var(--muted); padding: 10px 18px; cursor: pointer; font-size: .92rem; border-bottom: 2px solid transparent; font-family: inherit; }
.tab-btn:hover { color: var(--text); }
.tab-btn.active { color: var(--text); border-bottom-color: var(--accent); }
.tab-panel { display: none; padding: 18px 4px 4px; animation: fade .25s ease; }
.tab-panel.active { display: block; }
.tab-panel ul { margin: 0; padding-left: 18px; }
.tab-panel li { margin-bottom: 9px; }
.tab-panel li b { color: var(--text); }
@keyframes fade { from { opacity: 0; transform: translateY(4px); } to { opacity: 1; transform: none; } }

/* ===== Archive grid (other projects) ===== */
.archive { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; }
.arch-card { background: var(--card); border: 1px solid var(--line); border-radius: 12px; padding: 22px; transition: transform .2s, border-color .2s; }
.arch-card:hover { transform: translateY(-5px); border-color: var(--accent); }
.arch-card .top { display: flex; justify-content: space-between; align-items: center; margin-bottom: 14px; }
.arch-card .folder { font-size: 1.5rem; }
.arch-card .ext { color: var(--muted); }
.arch-card .ext:hover { color: var(--accent); }
.arch-card h4 { margin: 0 0 8px; font-size: 1.08rem; }
.arch-card h4 a { color: var(--text); }
.arch-card h4 a:hover { color: var(--accent); text-decoration: none; }
.arch-card p { color: var(--muted); font-size: .9rem; margin: 0 0 14px; }
.arch-card .tags { display: flex; flex-wrap: wrap; gap: 8px; font-family: monospace; font-size: .73rem; color: var(--muted); }

/* ===== Contact ===== */
.contact { text-align: center; margin-top: 80px; }
.contact a.big { display: inline-block; margin-top: 14px; padding: 12px 26px; border: 1px solid var(--accent); border-radius: 8px; color: var(--accent); }
.contact a.big:hover { background: rgba(100,255,218,.08); text-decoration: none; }
.foot { text-align: center; color: var(--muted); font-size: .8rem; margin-top: 44px; }

@media (max-width: 720px) {
  .hero h1 { font-size: 2.1rem; }
  .gallery.cols-2, .archive { grid-template-columns: 1fr; }
  .proj-tabs { flex-direction: column; gap: 16px; }
  .proj-nav { flex-direction: row; overflow-x: auto; position: static; width: 100%; }
  .pnav-btn { border-left: none; border-bottom: 2px solid var(--line); white-space: nowrap; }
  .pnav-btn.active { border-left: none; border-bottom-color: var(--accent); }
}
</style>

<div class="pf" markdown="0">

<!-- ============ HERO ============ -->
<section class="hero">
  <img class="avatar" src="/profile.png" alt="HongDae Kim">
  <div class="intro">
    <p class="eyebrow">안녕하세요, 저는</p>
    <h1>김홍대 <span class="en">HongDae Kim</span></h1>
    <div class="cta">
      <a class="primary" href="#projects">주요 프로젝트 보기</a>
      <a href="https://github.com/rad1092" target="_blank">GitHub</a>
      <a href="/repositories/">전체 저장소</a>
      <a href="/en/">🌐 English</a>
    </div>
  </div>
</section>

<!-- ============ ABOUT ============ -->
<section class="section" id="about">
  <h2><span class="num">01.</span> 소개</h2>
  <p class="lead">
    실험적인 학습 저장소에서 시작해, 실제 사용할 수 있는 도구형 프로젝트까지 단계적으로 확장해 왔습니다.
    <span class="hl">"정보 전달을 넘어 실제 행동을 돕는다"</span>는 관점으로 — API 도구화, 의존성 보안 점검,
    재난 대피 안내처럼 사용자의 다음 한 걸음을 만들어 주는 소프트웨어를 만듭니다.
  </p>
  <div class="chips">
    <span class="chip"><b>Python</b> · Streamlit · Pandas · Folium</span>
    <span class="chip"><b>Rust</b> · egui/eframe</span>
    <span class="chip"><b>Go</b> · GitHub CLI 확장</span>
    <span class="chip"><b>DevOps</b> · GitHub Actions · CI</span>
    <span class="chip"><b>AI</b> · MCP · 에이전트 도구화</span>
  </div>
</section>

<!-- ============ EXPERIENCE ============ -->
<section class="section" id="experience">
  <h2><span class="num">02.</span> 경력 &amp; 이력</h2>
  <div class="timeline">
    <div class="tl-item">
      <div class="tl-when">약 4년</div>
      <div class="tl-role">영업관리 · 자재 납품 <span class="org">— 건설자재 납품 회사</span></div>
      <p class="tl-desc">거래처 영업 관리와 건설 현장 자재 납품 업무를 담당했습니다. 일정·재고·납기를 조율하고 고객과 직접 소통하며, 현장의 요구를 데이터와 절차로 정리해 처리하는 경험을 쌓았습니다.</p>
    </div>
    <div class="tl-item">
      <div class="tl-when">1년</div>
      <div class="tl-role">해외 유학 <span class="org">— 멕시코</span></div>
      <p class="tl-desc">멕시코에서 1년간 유학하며 현지 언어와 문화를 직접 경험했습니다. 낯선 환경에 빠르게 적응하고 소통하는 법을 익혔습니다.</p>
    </div>
  </div>
</section>

<!-- ============ FEATURED PROJECTS (left vertical tabs) ============ -->
<section class="section" id="projects">
  <h2><span class="num">03.</span> 주요 프로젝트</h2>

  <div class="proj-tabs">
    <!-- left nav -->
    <div class="proj-nav" role="tablist">
      <button class="pnav-btn active" data-proj="p1"><small>01 · Rust</small>FirstCall<br>API 워크벤치</button>
      <button class="pnav-btn" data-proj="p2"><small>02 · Go</small>gh-dep-risk<br>의존성 리스크</button>
      <button class="pnav-btn" data-proj="p3"><small>03 · Python</small>재난 대피<br>대시보드</button>
    </div>

    <!-- right content -->
    <div class="proj-content">

      <!-- ===== Project 1 ===== -->
      <div class="proj-panel active" id="p1">
        <div class="head">
          <div>
            <h3 class="ptitle">Local-first API 워크벤치 · FirstCall</h3>
            <code class="repo">rad1092/firstcall-local-api-workbench</code>
          </div>
          <div class="links">
            <a href="https://github.com/rad1092/firstcall-local-api-workbench" target="_blank">GitHub ↗</a>
            <a href="https://github.com/rad1092/firstcall-local-api-workbench/releases" target="_blank">Releases ↗</a>
          </div>
        </div>
        <div class="stack"><span>Rust 2024</span><span>egui / eframe</span><span>firstcall-cli</span><span>GitHub Actions</span></div>
        <p class="summary">다양한 형식의 API 요청을 <b>로컬에서 검증</b>하고, 검증된 것만 비밀정보를 가린(redacted) <b>에이전트 패키지</b>로 내보내는 데스크톱 + CLI 워크벤치입니다.</p>
        <p class="context">curl·OpenAPI·Postman·HAR·.http·Hurl·Bruno 같은 요청 소스를 가져와 <b>로컬에서 실제로 호출해 검증</b>한 뒤, 성공한 요청만 재사용 가능한 "레시피"로 승격시킵니다. 그리고 그 레시피를 <b>비밀정보가 제거된 패키지</b>로 내보내 에이전트·CI가 안전하게 쓰도록 합니다. "검증되지 않았거나 비밀정보가 노출된 요청은 절대 밖으로 나가지 않는다"를 도구 차원에서 강제하는 것이 핵심입니다.</p>

        <div class="ai-note"><span class="badge">AI</span><span>Rust 2024 코어 설계, 8종 소스 어댑터와 트러스트 체인 구현, 테스트·문서 작성 과정에서 <b>Claude를 페어 프로그래밍 파트너</b>로 활용했습니다. 무엇을 만들지·어떤 불변식을 지킬지는 제가 정하고, 반복적인 구현과 엣지 케이스 점검 속도를 AI로 끌어올렸습니다.</span></div>

        <div class="gallery cols-2">
          <figure><img src="/assets/projects/firstcall-gui-workbench.gif" alt="FirstCall 데스크톱 GUI 워크벤치 데모" loading="lazy"><figcaption>데스크톱 GUI 워크벤치 (v0.1.0 릴리스 바이너리)</figcaption></figure>
          <figure><img src="/assets/projects/firstcall-cli-demo.gif" alt="FirstCall CLI 라이프사이클 데모" loading="lazy"><figcaption>firstcall-cli 라이프사이클 (실제 명령 출력)</figcaption></figure>
        </div>

        <div class="tabs" role="tablist">
          <button class="tab-btn active" data-target="p1-s">상황</button>
          <button class="tab-btn" data-target="p1-t">과제</button>
          <button class="tab-btn" data-target="p1-a">행동</button>
          <button class="tab-btn" data-target="p1-r">결과</button>
        </div>
        <div class="tab-panel active" id="p1-s">
          <ul>
            <li>API 요청을 재사용 가능한 형태로 모아두고 안전하게 관리할 수 있는 <b>로컬 우선(local-first)</b> 도구가 마땅치 않았습니다.</li>
            <li>특히 에이전트·CI에 API를 넘길 때 토큰 같은 <b>비밀정보가 그대로 노출</b>되거나, <b>검증되지 않은 요청</b>이 섞여 들어가는 위험이 컸습니다.</li>
            <li>요청을 클라우드에 올리지 않고 <b>내 컴퓨터 안에서 끝내고 싶은</b> 보안 요구도 있었습니다.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p1-t">
          <ul>
            <li>curl·OpenAPI·Postman·HAR 등 <b>형식이 제각각인 요청 소스</b>를 하나의 흐름으로 받아들여 로컬에서 검증.</li>
            <li>성공적으로 검증된 요청만 재사용 가능한 <b>"레시피"로 승격</b>시키고, 실패한 것은 걸러냄.</li>
            <li>검증된 레시피를 <b>비밀정보가 제거된 에이전트 패키지</b>로 내보내, 자동화 환경에 안전하게 전달.</li>
            <li>사람이 쓰는 GUI와 자동화가 쓰는 CLI <b>둘 다</b>를 하나의 코어 위에서 제공.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p1-a">
          <ul>
            <li>Rust 2024로 <b>공유 코어 로직</b>을 만들고, 그 위에 두 개의 표면을 올렸습니다 — egui/eframe 기반 <b>데스크톱 GUI</b>와 자동화용 <code class="mono">firstcall-cli</code>.</li>
            <li>핵심 트러스트 체인: <span class="mono" style="font-size:.82rem;color:var(--accent-2)">요청 소스 → ParsedSource → RequestDraft 후보 → 로컬 검증 → Recipe → redacted 패키지 → 재검증</span>.</li>
            <li>GUI는 소스 인테이크·파서 노트·후보 검토·런타임 슬롯/인증 입력·로컬 HTTP 실행·시도 결과 검토·레시피 검토·시크릿 백엔드 상태까지 <b>한 화면 흐름</b>으로 연결.</li>
            <li>8종 소스 어댑터를 <b>정적 인테이크</b>로만 처리 — 임포트한 스크립트·테스트·런타임 훅·환경파일은 <b>절대 실행하지 않음</b>(공급망 위험 차단).</li>
            <li>비밀정보는 <b>환경변수로만</b> 다루고, 패키지로 내보낼 때 가립니다. CI / CLI 라이프사이클 / 보안 감사 GitHub Actions로 릴리스 신뢰성 확보.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p1-r">
          <ul>
            <li>GUI와 CLI를 모두 포함한 <b>v0.1.0 멀티 OS 릴리스 바이너리</b>를 배포.</li>
            <li>CLI가 verify·package·validate·inspect·import·recipe 조회와 <b>JSON 리포트</b>까지 담당해, 에이전트·CI 파이프라인에 그대로 연결 가능.</li>
            <li>"로컬에서 검증된, 비밀정보가 제거된 요청만 밖으로 나간다"는 원칙을 <b>도구가 강제</b>하도록 설계.</li>
          </ul>
        </div>
      </div>

      <!-- ===== Project 2 ===== -->
      <div class="proj-panel" id="p2">
        <div class="head">
          <div>
            <h3 class="ptitle">PR 의존성 리스크 검토 확장 · gh-dep-risk</h3>
            <code class="repo">rad1092/gh-dependency-risk</code>
          </div>
          <div class="links">
            <a href="https://github.com/rad1092/gh-dependency-risk" target="_blank">GitHub ↗</a>
          </div>
        </div>
        <div class="stack"><span>Go</span><span>GitHub CLI Extension</span><span>Dependency Review API</span><span>GitHub Actions</span></div>
        <p class="summary">리뷰어가 <b>필요할 때만 실행</b>해 PR에 추가된 의존성의 보안 리스크를 요약해 주는 GitHub CLI 확장입니다.</p>
        <p class="context">서버·웹훅·DB·대시보드 같은 상시 인프라를 두지 않고, <b>단일 Go 바이너리</b> 하나로 동작합니다. <code class="mono">gh</code> 인증을 그대로 재사용하므로 리뷰어 머신이나 일회성 워크플로에서 바로 실행할 수 있고, GitHub의 <b>Dependency Review API를 우선</b> 사용하다가 그것이 불가능할 때만 정적 락파일을 직접 파싱하는 <b>로컬 fallback</b>으로 전환합니다. 결과는 CI를 실패시키지 않고 <b>PR 코멘트</b>로 남겨 리뷰어의 판단을 돕습니다.</p>

        <div class="ai-note"><span class="badge">AI</span><span>npm·pnpm·yarn·bun·pip·Poetry·Go 등 <b>패키지 매니저별로 다른 락파일 규칙</b>을 정리하고 fallback 분기를 설계할 때 AI를 활용해 엣지 케이스를 빠르게 점검하고 테스트 픽스처를 갖췄습니다. 범위를 어디까지 한정할지(무엇을 "지원 안 함"으로 명시할지)는 제가 직접 결정했습니다.</span></div>

        <div class="gallery">
          <figure><img src="/assets/projects/gh-dependency-risk-demo.gif" alt="gh-dep-risk 터미널 데모" loading="lazy"><figcaption>터미널 데모 — Yarn 로컬 fallback을 사용한 라이브 E2E PR 리뷰</figcaption></figure>
        </div>

        <div class="tabs" role="tablist">
          <button class="tab-btn active" data-target="p2-s">상황</button>
          <button class="tab-btn" data-target="p2-t">과제</button>
          <button class="tab-btn" data-target="p2-a">행동</button>
          <button class="tab-btn" data-target="p2-r">결과</button>
        </div>
        <div class="tab-panel active" id="p2-s">
          <ul>
            <li>PR에 새로 추가되는 의존성의 보안 리스크를 리뷰어가 <b>코드 리뷰 중에 빠르게 파악</b>하기 어려웠습니다.</li>
            <li>그렇다고 서버·웹훅·DB·대시보드 같은 <b>상시 인프라</b>를 구축·운영하는 것은 작은 팀에 부담이 큽니다.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p2-t">
          <ul>
            <li><code class="mono">gh</code> 인증을 그대로 재사용하면서, <b>리뷰어 머신이나 일회성 워크플로</b>에서 온디맨드로 도는 가벼운 도구.</li>
            <li>CI를 실패시키지 않고 <b>리뷰어의 판단을 돕는</b> 형태로 결과를 전달.</li>
            <li>정확도와 단순함의 균형 — 가능하면 <b>공식 데이터</b>를 쓰고, 안 될 때만 최소한의 로컬 분석.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p2-a">
          <ul>
            <li>서버 대신 <b>GitHub CLI 확장(단일 Go 바이너리)</b>으로 구현 — 설치 한 줄로 인프라 없이 배포·실행.</li>
            <li>GitHub <b>Dependency Review API를 1순위</b>로 사용하고, 사용할 수 없을 때(403/404)만 정적 파일 로컬 fallback으로 전환.</li>
            <li>로컬 fallback 대상을 명확히 한정: npm·pnpm·yarn·bun(JS), pip·Poetry·uv(Python), Go modules — 락파일을 파싱하되 <b>풀 그래프 재구성은 하지 않음</b>을 문서로 명시.</li>
            <li>결과를 <b>PR 코멘트로 업서트</b>(중복 없이 갱신)하고, test·install-smoke 워크플로와 렌더러 기반 예제 픽스처로 회귀를 방지.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p2-r">
          <ul>
            <li><code class="mono">gh extension install rad1092/gh-dep-risk</code> <b>한 줄로 설치·사용</b> 가능.</li>
            <li>Dependency Review API 경로에서 Cargo·Composer·Go·Maven·npm·pip·pnpm·Poetry·RubyGems·Swift·Yarn 등 <b>11개 생태계</b>의 리스크를 표면화.</li>
            <li>CI 실패 없이, 리뷰 흐름 안에서 의존성 리스크를 점검하는 <b>경량 워크플로</b>를 확립.</li>
          </ul>
        </div>
      </div>

      <!-- ===== Project 3 ===== -->
      <div class="proj-panel" id="p3">
        <div class="head">
          <div>
            <h3 class="ptitle">영남권 실시간 재난 대피 안내 대시보드</h3>
            <code class="repo">rad1092/project_dashboard</code>
          </div>
          <div class="links">
            <a href="https://github.com/rad1092/project_dashboard" target="_blank">GitHub ↗</a>
          </div>
        </div>
        <div class="stack"><span>Python</span><span>Streamlit</span><span>Pandas</span><span>Folium</span><span>OSRM</span><span>Selenium</span><span>SQLite</span></div>
        <p class="summary">재난문자는 <b>발생 사실</b>만 알려줍니다. "지금 어디로, 어떻게 대피해야 하는지"까지 안내하는 멀티페이지 대시보드입니다.</p>
        <p class="context">사용자 <b>현재 위치 기준 대피소 추천</b>, <b>도보 경로 안내</b>, 그리고 <b>지역별 재난 패턴 분석</b>을 한곳에 묶었습니다. 실시간 재난문자를 크롤링해 감지된 지역을 기준으로 최근 재난문자·추천 대피소·경로 지도를 한 화면에서 보여주고, 분석 페이지에서는 특보의 시계열 패턴·지역별 특성·대피소 분포까지 함께 살펴볼 수 있습니다. 지원 권역은 <b>대구·울산·부산·경북·경남</b>입니다.</p>

        <div class="ai-note"><span class="badge">AI</span><span>재난문자 크롤링, 하버사인 거리 계산, OSRM 경로 조회, Streamlit 멀티페이지 구성 같은 <b>반복적인 구현과 데이터 정제</b>를 AI와 함께 빠르게 프로토타이핑하고 검증했습니다. "어떤 정보를, 어떤 순서로 사용자에게 보여줄 것인가"라는 화면 설계는 제가 주도했습니다.</span></div>

        <div class="gallery cols-2">
          <figure><img src="/assets/projects/dashboard-demo-1-landing.png" alt="실시간 대피 안내 초기 화면" loading="lazy"><figcaption>① 실시간 대피 안내 — 재난문자 확인 대기 화면</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-2-default.png" alt="재난문자 없는 경우" loading="lazy"><figcaption>② 재난문자가 없는 경우 — 위치(울산 북구) 기준 기본 상태</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-3-shelter.png" alt="대피소 추천 목록" loading="lazy"><figcaption>③ 재난문자 발생(자택) — 지도 + 추천 대피소 목록</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-4-route.png" alt="안전 경로 안내" loading="lazy"><figcaption>④ 재난문자 발생(풍랑주의보) — 도보 안전 경로 안내</figcaption></figure>
        </div>

        <div class="tabs" role="tablist">
          <button class="tab-btn active" data-target="p3-s">상황</button>
          <button class="tab-btn" data-target="p3-t">과제</button>
          <button class="tab-btn" data-target="p3-a">행동</button>
          <button class="tab-btn" data-target="p3-r">결과</button>
        </div>
        <div class="tab-panel active" id="p3-s">
          <ul>
            <li>재난문자는 "무슨 일이 일어났는지"는 알려주지만 <b>"지금 어디로 대피해야 하는지"</b>는 알려주지 않습니다.</li>
            <li>대피소·재난 특보 데이터가 흩어져 있어, 사용자가 자기 상황에 맞는 행동을 <b>즉시 판단</b>하기 어려웠습니다.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p3-t">
          <ul>
            <li>사용자 <b>현재 위치 기준 대피소 추천</b>과 <b>이동 경로 안내</b>를 한 화면에서 제공.</li>
            <li>실시간 재난문자 흐름과 <b>지역별 재난 패턴 분석</b>까지 함께 다루는 멀티페이지 대시보드 구축.</li>
            <li>경로 조회가 실패해도 안내가 <b>끊기지 않게</b> 견고하게 처리.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p3-a">
          <ul>
            <li>Streamlit <code class="mono">st.navigation</code> 기반 <b>멀티페이지</b> 구성: HOME · 대피 안내 시뮬레이션 · 실시간 대피 안내 · 데이터 분석.</li>
            <li>Selenium으로 <b>재난문자를 크롤링</b>하고, 모의 재난문자 생성기로 동일 흐름을 테스트(대구·울산·부산·경북·경남 5개 권역).</li>
            <li><b>하버사인</b> 거리 계산으로 가까운 대피소를 선별하고, <b>OSRM 도보 경로</b>를 조회 — 실패 시 <b>직선 fallback</b>으로 안내를 이어감.</li>
            <li>Folium 지도에 현재 위치·대피소·경로를 함께 시각화. 분석 페이지는 <b>SQLite 우선 / CSV fallback</b>으로 데이터 가용성을 확보하고, 재난 분포·시계열 추이·지역 비교·권역 대피소 지도를 탭으로 제공.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p3-r">
          <ul>
            <li>4개 페이지가 유기적으로 동작하는 대시보드 완성 — 위 시연 화면 ①~④가 실제 동작 흐름입니다.</li>
            <li>재난문자 유무·위치·재난 유형에 따라 <b>추천 대피소와 안전 경로가 실시간으로 갱신</b>.</li>
            <li>특보 시계열·지역 비교·권역 대피소 분포까지 분석으로 연결해 <b>"안내"와 "이해"를 한 도구</b>에 담음.</li>
          </ul>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ============ OTHER PROJECTS ============ -->
<section class="section" id="more">
  <h2><span class="num">04.</span> 그 외 프로젝트</h2>
  <div class="archive">
    <div class="arch-card">
      <div class="top"><span class="folder">🪞</span><a class="ext" href="https://github.com/rad1092/smart-mirror-pc123" target="_blank">↗</a></div>
      <h4><a href="https://github.com/rad1092/smart-mirror-pc123" target="_blank">스마트 미러 AIoT 운동 코칭</a></h4>
      <p>PC1 화면 · PC3 비전 게이트웨이 · PC2 AI 코칭 엔진을 한 저장소로 묶은 통합본. 자세 분석, 루틴 생성, 실시간 운동 코칭을 연결합니다.</p>
      <div class="tags"><span>Python</span><span>WebSocket</span><span>SQLite</span><span>AIoT</span></div>
    </div>
    <div class="arch-card">
      <div class="top"><span class="folder">🔌</span><a class="ext" href="https://github.com/rad1092/firstcall-api-lookup-mcp" target="_blank">↗</a></div>
      <h4><a href="https://github.com/rad1092/firstcall-api-lookup-mcp" target="_blank">FirstCall API Lookup MCP</a></h4>
      <p>FirstCall 레시피에서 생성한 읽기 전용 MCP 서버. <code class="mono">github_user_lookup</code> 툴 하나로 공개 사용자 정보를 조회하는 에이전트용 도구.</p>
      <div class="tags"><span>TypeScript</span><span>MCP</span><span>Node</span></div>
    </div>
    <div class="arch-card">
      <div class="top"><span class="folder">🧭</span><a class="ext" href="https://github.com/rad1092/job-coach-agent" target="_blank">↗</a></div>
      <h4><a href="https://github.com/rad1092/job-coach-agent" target="_blank">취업 코치형 에이전트</a></h4>
      <p>희망 산업·직군·직무를 입력하면 채용 공고 탐색부터 분석 리포트·자소서 초안·면접 대비·합격 로드맵까지 한 흐름으로 정리해 주는 에이전트.</p>
      <div class="tags"><span>Streamlit</span><span>FastAPI</span><span>SQLite</span></div>
    </div>
    <div class="arch-card">
      <div class="top"><span class="folder">⌨️</span><a class="ext" href="https://github.com/rad1092/ascii-diagram-editor" target="_blank">↗</a></div>
      <h4><a href="https://github.com/rad1092/ascii-diagram-editor" target="_blank">ASCII 다이어그램 에디터</a></h4>
      <p>브라우저에서 동작하는 ASCII 다이어그램 에디터. 200×80 고정 그리드를 기준으로, 결과를 실제 <code class="mono">&lt;pre&gt;</code> 텍스트로 렌더링합니다.</p>
      <div class="tags"><span>TypeScript</span><span>Vite</span><span>Client-side</span></div>
    </div>
  </div>
  <p class="lead" style="margin-top:18px;font-size:.9rem;">전체 저장소는 <a href="/repositories/">저장소 목록 페이지</a>에서 볼 수 있습니다.</p>
</section>

<!-- ============ CONTACT ============ -->
<section class="section contact" id="contact">
  <h2 style="justify-content:center;"><span class="num">05.</span> 연락</h2>
  <p class="lead" style="margin:0 auto;">새로운 협업이나 프로젝트 제안은 언제든 환영합니다.</p>
  <a class="big" href="https://github.com/rad1092" target="_blank">GitHub @rad1092</a>
</section>

<p class="foot">Built with Jekyll · Designed &amp; developed by HongDae Kim — with a little help from AI</p>

</div>

<script>
(function () {
  // Left vertical project tabs
  var pnav = document.querySelectorAll('.pnav-btn');
  pnav.forEach(function (btn) {
    btn.addEventListener('click', function () {
      pnav.forEach(function (b) { b.classList.remove('active'); });
      document.querySelectorAll('.proj-panel').forEach(function (p) { p.classList.remove('active'); });
      btn.classList.add('active');
      var panel = document.getElementById(btn.dataset.proj);
      if (panel) panel.classList.add('active');
    });
  });

  // Inner STAR tabs (scoped to each project panel)
  document.querySelectorAll('.tabs').forEach(function (tabs) {
    tabs.addEventListener('click', function (e) {
      var btn = e.target.closest('.tab-btn');
      if (!btn) return;
      var panel = tabs.closest('.proj-panel');
      panel.querySelectorAll('.tab-btn').forEach(function (b) { b.classList.remove('active'); });
      panel.querySelectorAll('.tab-panel').forEach(function (p) { p.classList.remove('active'); });
      btn.classList.add('active');
      var t = panel.querySelector('#' + btn.dataset.target);
      if (t) t.classList.add('active');
    });
  });
})();
</script>

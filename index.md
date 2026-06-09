---
layout: default
---

<style>
/* ===== Reset Cayman theme chrome — full-bleed canvas ===== */
.page-header { display: none !important; }
.main-content { max-width: none !important; margin: 0 !important; padding: 0 !important; width: 100% !important; }
.main-content h1, .main-content h2, .main-content h3, .main-content h4 { border: none; }
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
}

body { background: var(--bg); }
.pf { color: var(--text); font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Apple SD Gothic Neo", "Noto Sans KR", sans-serif; line-height: 1.7; }
.pf a { color: var(--accent); text-decoration: none; }
.pf a:hover { text-decoration: underline; }
.pf .mono { font-family: "SFMono-Regular", Consolas, "Liberation Mono", Menlo, monospace; }

/* ===== App shell: fixed sidebar + switching views ===== */
.app { display: flex; align-items: flex-start; }

.sidebar { position: sticky; top: 0; align-self: flex-start; height: 100vh; flex: 0 0 268px;
  background: var(--bg-soft); border-right: 1px solid var(--line); padding: 34px 24px;
  display: flex; flex-direction: column; overflow-y: auto; }
.side-id { display: flex; flex-direction: column; align-items: flex-start; gap: 4px; padding-bottom: 22px; border-bottom: 1px solid var(--line); margin-bottom: 18px; }
.side-id img { width: 78px; height: 78px; border-radius: 50%; border: 2px solid var(--line); margin-bottom: 10px; }
.side-id .nm { font-size: 1.3rem; font-weight: 700; }
.side-id .nm small { color: var(--muted); font-weight: 500; font-size: .85rem; }
.side-id .handle { font-family: monospace; font-size: .8rem; color: var(--accent); }

.nav { display: flex; flex-direction: column; gap: 2px; }
.nav-group { font-family: monospace; font-size: .68rem; letter-spacing: .08em; text-transform: uppercase; color: var(--muted); margin: 16px 0 6px 10px; }
.nav-btn { display: flex; align-items: center; gap: 11px; padding: 10px 12px; border-radius: 8px; color: var(--muted); font-size: .95rem; cursor: pointer; transition: .15s; border: none; background: none; text-align: left; font-family: inherit; }
.nav-btn:hover { color: var(--text); background: rgba(255,255,255,.04); text-decoration: none; }
.nav-btn.active { color: var(--accent); background: rgba(100,255,218,.08); font-weight: 600; }
.nav-btn .ic { width: 18px; text-align: center; }
.nav-btn .no { font-family: monospace; font-size: .72rem; color: var(--accent); }
.side-foot { margin-top: auto; padding-top: 20px; display: flex; gap: 14px; font-size: .82rem; }

.view { flex: 1; min-width: 0; padding: 56px 52px 90px; max-width: 1080px; }
.view-panel { display: none; animation: fade .3s ease; }
.view-panel.active { display: block; }
@keyframes fade { from { opacity: 0; transform: translateY(6px); } to { opacity: 1; transform: none; } }

.view-h { font-size: 1.0rem; font-family: monospace; color: var(--accent); letter-spacing: .04em; margin: 0 0 6px; }
.view-title { font-size: 2rem; margin: 0 0 24px; line-height: 1.15; }

.lead { color: var(--muted); max-width: 820px; }
.lead .hl { color: var(--text); }

/* about */
.about-head { font-size: 2.3rem; line-height: 1.3; max-width: 820px; margin: 0 0 22px; font-weight: 700; }
.about-head .hl { color: var(--accent); }
.chips { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 22px; }
.chip { background: var(--bg-soft); border: 1px solid var(--line); color: var(--text); padding: 6px 13px; border-radius: 999px; font-size: .85rem; }
.chip b { color: var(--accent); }
.cta { margin-top: 30px; }
.cta a { display: inline-block; margin: 0 12px 12px 0; padding: 11px 20px; border-radius: 8px; border: 1px solid var(--line); color: var(--text); font-size: .92rem; transition: .15s; }
.cta a:hover { border-color: var(--accent); color: var(--accent); text-decoration: none; transform: translateY(-2px); }
.cta a.primary { background: var(--accent); color: #0a0c10; border-color: var(--accent); font-weight: 600; }

/* timeline */
.timeline { position: relative; padding-left: 26px; }
.timeline::before { content: ""; position: absolute; left: 6px; top: 6px; bottom: 6px; width: 2px; background: var(--line); }
.tl-item { position: relative; padding: 0 0 30px; }
.tl-item:last-child { padding-bottom: 0; }
.tl-item::before { content: ""; position: absolute; left: -26px; top: 5px; width: 12px; height: 12px; border-radius: 50%; background: var(--bg); border: 2px solid var(--accent); }
.tl-when { font-family: monospace; font-size: .8rem; color: var(--accent); letter-spacing: .03em; }
.tl-role { font-size: 1.15rem; font-weight: 600; margin: 3px 0 2px; }
.tl-role .org { color: var(--muted); font-weight: 400; font-size: .92rem; }
.tl-desc { color: var(--muted); margin: 4px 0 0; max-width: 760px; }
.tl-detail { margin: 12px 0 0; padding-left: 18px; color: var(--muted); }
.tl-detail li { margin-bottom: 8px; }
.tl-detail b { color: var(--accent); font-family: monospace; font-size: .82rem; }
.certs-title { font-size: .78rem; font-family: monospace; color: var(--muted); letter-spacing: .06em; margin: 40px 0 12px; text-transform: uppercase; }
.certs { display: flex; flex-wrap: wrap; gap: 10px; }
.cert { background: var(--bg-soft); border: 1px solid var(--line); border-radius: 8px; padding: 8px 14px; font-size: .92rem; }

/* project view */
.head { display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; flex-wrap: wrap; }
.repo { font-family: monospace; font-size: .82rem; color: var(--muted); display: block; margin-top: 6px; }
.role-tag { display: inline-block; margin-top: 10px; font-size: .82rem; color: var(--accent-2); background: rgba(122,162,255,.08); border: 1px solid rgba(122,162,255,.25); padding: 4px 11px; border-radius: 6px; }
.links a { font-size: .86rem; margin-left: 14px; white-space: nowrap; }
.stack { display: flex; flex-wrap: wrap; gap: 8px; margin: 18px 0 22px; }
.stack span { font-family: monospace; font-size: .76rem; color: var(--accent-2); background: rgba(122,162,255,.08); border: 1px solid rgba(122,162,255,.25); padding: 3px 9px; border-radius: 6px; }

.panel-grid { display: grid; grid-template-columns: 1.08fr 0.92fr; gap: 36px; align-items: start; }
.panel-main { min-width: 0; }
.panel-media { min-width: 0; position: sticky; top: 24px; }

.summary { color: var(--text); margin: 0 0 14px; font-size: 1.08rem; line-height: 1.6; }
.summary b { color: var(--accent); }
.context { color: var(--muted); margin: 0 0 18px; }
.context b { color: var(--text); }

.ai-note { display: flex; gap: 11px; align-items: flex-start; margin: 0; padding: 13px 16px; background: rgba(100,255,218,.05); border: 1px solid rgba(100,255,218,.22); border-radius: 9px; font-size: .9rem; color: var(--muted); }
.ai-note .badge { flex: 0 0 auto; font-family: monospace; font-size: .68rem; font-weight: 700; color: #0a0c10; background: var(--accent); padding: 2px 7px; border-radius: 5px; margin-top: 2px; }
.ai-note b { color: var(--text); }

.gallery { display: grid; gap: 12px; }
.gallery figure { margin: 0; border: 1px solid var(--line); border-radius: 10px; overflow: hidden; background: var(--bg); }
.gallery img { width: 100%; display: block; }
.gallery figcaption { font-size: .78rem; color: var(--muted); padding: 8px 10px; border-top: 1px solid var(--line); }

.tabs { display: flex; gap: 4px; border-bottom: 1px solid var(--line); flex-wrap: wrap; margin-top: 24px; }
.tab-btn { background: none; border: none; color: var(--muted); padding: 10px 18px; cursor: pointer; font-size: .92rem; border-bottom: 2px solid transparent; font-family: inherit; }
.tab-btn:hover { color: var(--text); }
.tab-btn.active { color: var(--text); border-bottom-color: var(--accent); }
.tab-panel { display: none; padding: 20px 4px 4px; animation: fade .25s ease; }
.tab-panel.active { display: block; }
.tab-panel ul { margin: 0; padding-left: 18px; }
.tab-panel li { margin-bottom: 10px; }
.tab-panel li b { color: var(--text); }

/* other projects */
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

/* contact */
.contact-big { margin-top: 18px; }
.contact-big a { display: inline-block; margin-top: 10px; padding: 12px 26px; border: 1px solid var(--accent); border-radius: 8px; color: var(--accent); }
.contact-big a:hover { background: rgba(100,255,218,.08); text-decoration: none; }
.foot { color: var(--muted); font-size: .8rem; margin-top: 50px; }

@media (max-width: 1020px) {
  .panel-grid { grid-template-columns: 1fr; gap: 24px; }
  .panel-media { position: static; }
}
@media (max-width: 820px) {
  .app { flex-direction: column; }
  .sidebar { position: sticky; top: 0; z-index: 10; height: auto; width: 100%; flex-basis: auto;
    flex-direction: column; padding: 16px 16px; border-right: none; border-bottom: 1px solid var(--line); }
  .side-id { flex-direction: row; align-items: center; gap: 12px; padding-bottom: 14px; margin-bottom: 12px; }
  .side-id img { width: 46px; height: 46px; margin: 0; }
  .side-id .nm { font-size: 1.05rem; }
  .nav { flex-direction: row; overflow-x: auto; gap: 4px; }
  .nav-group { display: none; }
  .nav-btn { white-space: nowrap; padding: 8px 12px; }
  .nav-btn .no { display: none; }
  .side-foot { margin-top: 14px; }
  .view { padding: 28px 20px 70px; max-width: none; }
  .about-head { font-size: 1.7rem; }
  .archive { grid-template-columns: 1fr; }
}
</style>

<div class="pf" markdown="0">
<div class="app">

  <!-- ================= SIDEBAR ================= -->
  <aside class="sidebar">
    <div class="side-id">
      <img src="/profile.png" alt="HongDae Kim">
      <div class="nm">김홍대 <small>HongDae Kim</small></div>
      <div class="handle">@rad1092</div>
    </div>
    <nav class="nav">
      <a class="nav-btn active" href="#about"><span class="no">01</span> 소개</a>
      <a class="nav-btn" href="#experience"><span class="no">02</span> 경력 &amp; 이력</a>
      <div class="nav-group">주요 프로젝트</div>
      <a class="nav-btn" href="#p1"><span class="ic">🛟</span> 재난 대피 대시보드</a>
      <a class="nav-btn" href="#p2"><span class="ic">🔧</span> FirstCall</a>
      <a class="nav-btn" href="#p3"><span class="ic">🛡️</span> gh-dep-risk</a>
      <div class="nav-group">더 보기</div>
      <a class="nav-btn" href="#more"><span class="ic">📂</span> 그 외 프로젝트</a>
      <a class="nav-btn" href="#contact"><span class="ic">✉️</span> 연락</a>
    </nav>
    <div class="side-foot">
      <a href="https://github.com/rad1092" target="_blank">GitHub</a>
      <a href="/en/">🌐 English</a>
    </div>
  </aside>

  <!-- ================= VIEWS ================= -->
  <main class="view">

    <!-- ---------- ABOUT ---------- -->
    <section class="view-panel active" id="about">
      <p class="view-h">// 01. 소개</p>
      <h1 class="about-head">현장 영업·납품을 거쳐, 지금은 사람의 <span class="hl">다음 한 걸음</span>을 돕는 소프트웨어를 만듭니다.</h1>
      <p class="lead">
        실험적인 학습 저장소에서 시작해, 실제 사용할 수 있는 도구형 프로젝트까지 단계적으로 확장해 왔습니다.
        <span class="hl">"정보 전달을 넘어 실제 행동을 돕는다"</span>는 관점으로 — 재난 대피 안내, API 도구화,
        의존성 보안 점검처럼 사용자의 다음 행동을 만들어 주는 소프트웨어에 집중합니다.
      </p>
      <div class="chips">
        <span class="chip"><b>Python</b> · Streamlit · Pandas · Folium</span>
        <span class="chip"><b>Rust</b> · egui/eframe</span>
        <span class="chip"><b>Go</b> · GitHub CLI 확장</span>
        <span class="chip"><b>DevOps</b> · GitHub Actions · CI</span>
        <span class="chip"><b>AI</b> · MCP · 에이전트 도구화</span>
      </div>
      <div class="cta">
        <a class="primary" href="#p1">주요 프로젝트 보기 →</a>
        <a href="#experience">경력 보기</a>
      </div>
    </section>

    <!-- ---------- EXPERIENCE ---------- -->
    <section class="view-panel" id="experience">
      <p class="view-h">// 02. 경력 &amp; 이력</p>
      <h2 class="view-title">경력 &amp; 이력</h2>
      <div class="timeline">
        <div class="tl-item">
          <div class="tl-when">2016.07 – 2017.07, 2022.04 – 2025.04 · 합산 약 4년</div>
          <div class="tl-role">영업관리 · 자재 납품 <span class="org">— 효상안전종합상사</span></div>
          <p class="tl-desc">건설 현장에 들어가는 자재·안전용품을 다루는 회사에서, 자재 납품 실무로 시작해 영업관리까지 맡으며 약 4년간 근무했습니다. 거래처를 직접 응대하고 일정·재고·납기를 조율하며, 현장의 요구를 절차와 데이터로 정리해 처리하는 일을 했습니다.</p>
          <ul class="tl-detail">
            <li><b>2022.04 – 2025.04</b> · 영업관리 + 자재 납품 — 거래처 영업 관리, 일정·재고·납기 조율, 고객 직접 응대</li>
            <li><b>2016.07 – 2017.07</b> · 자재 납품 — 건설 현장 자재 납품 실무</li>
          </ul>
        </div>
        <div class="tl-item">
          <div class="tl-when">2017.07 – 2018.07</div>
          <div class="tl-role">교환학생 (어학연수) <span class="org">— UNAM CEPE, 멕시코 국립자치대학교</span></div>
          <p class="tl-desc">멕시코 국립자치대학교(UNAM) 외국인 교육센터(CEPE)에서 1년간 교환학생으로 스페인어와 멕시코 문화를 공부했습니다. 낯선 환경에 빠르게 적응하고 다른 언어·문화권 사람들과 소통하는 법을 익혔습니다.</p>
        </div>
      </div>

      <div class="certs-title">자격 · 면허</div>
      <div class="certs">
        <span class="cert">🚜 굴삭기 운전</span>
        <span class="cert">🏗️ 지게차 운전</span>
        <span class="cert">🚛 1종 대형 운전면허</span>
      </div>
    </section>

    <!-- ---------- PROJECT 1 : Disaster Dashboard ---------- -->
    <section class="view-panel" id="p1">
      <p class="view-h">// 주요 프로젝트 01</p>
      <div class="head">
        <div>
          <h2 class="view-title" style="margin-bottom:0;">영남권 실시간 재난 대피 안내 대시보드</h2>
          <code class="repo">rad1092/project_dashboard</code>
          <span class="role-tag">4인 팀 프로젝트 · 백엔드 / 아키텍처 담당</span>
        </div>
        <div class="links"><a href="https://github.com/rad1092/project_dashboard" target="_blank">GitHub ↗</a></div>
      </div>
      <div class="stack"><span>Python</span><span>Streamlit</span><span>Pandas</span><span>Folium</span><span>OSRM</span><span>Selenium</span><span>SQLite</span><span>pytest</span></div>

      <div class="panel-grid">
        <div class="panel-main">
          <p class="summary">재난문자는 <b>"무슨 일이 일어났는지"</b>만 알려줍니다. "지금 어디로, 어떻게 대피해야 하는지"까지 안내하는 대시보드를 만들었습니다.</p>
          <p class="context">정적 공공데이터, 실시간 재난문자, 사용자 위치, 외부 경로 API를 <b>함께 쓰는 서비스</b>라, 단순 화면 시각화보다 <b>데이터가 끊기지 않게 불러오고·추천하고·길을 찾아주는 구조</b>가 핵심이었습니다. 저는 4인 팀에서 <b>백엔드와 전체 아키텍처</b>를 맡아, 데이터 로딩·대피소 추천·실시간 재난문자 처리·경로 안내·테스트를 설계하고 구현했습니다.</p>
          <div class="ai-note"><span class="badge">AI</span><span>처음 다뤄 보는 기술 스택이 많았는데, <b>AI 도구를 적극 활용해 단기간에 구현 역량을 끌어올렸습니다.</b> 새로운 도구를 실전에서 빠르게 익히고, AI를 개발 파트너로 부리는 실용적인 방식을 체득한 프로젝트입니다.</span></div>

          <div class="tabs" role="tablist">
            <button class="tab-btn active" data-target="p1-s">상황</button>
            <button class="tab-btn" data-target="p1-t">역할</button>
            <button class="tab-btn" data-target="p1-a">행동</button>
            <button class="tab-btn" data-target="p1-r">결과</button>
          </div>
          <div class="tab-panel active" id="p1-s">
            <ul>
              <li>재난 발생 시 영남권(대구·울산·부산·경북·경남) 주민이 <b>대피소를 찾고 이동 경로를 확인할 통합 서비스가 없었습니다.</b></li>
              <li>특보 데이터와 대피소 정보가 흩어져 있어, 위기 상황에서 사용자가 <b>빠르게 판단하기 어려운</b> 환경이었습니다.</li>
              <li>여러 데이터 출처와 실행 환경이 섞여, <b>안정적인 데이터 로딩·추천·경로 처리 구조</b>가 무엇보다 중요했습니다.</li>
            </ul>
          </div>
          <div class="tab-panel" id="p1-t">
            <ul>
              <li>4인 팀에서 <b>전체 대시보드 아키텍처 설계</b>를 담당.</li>
              <li>데이터 경로 관리, CSV 검증·정규화, 실시간 재난문자 처리, <b>대피소 추천 로직</b>, OSRM 경로 조회와 <b>장애 대응(fallback)</b> 구조를 설계·구현.</li>
              <li>지도 시각화와 테스트 구성 등 <b>핵심 기능 구현을 주도</b>.</li>
            </ul>
          </div>
          <div class="tab-panel" id="p1-a">
            <ul>
              <li><b>안 끊기는 데이터 로딩:</b> 환경변수 → Streamlit secrets → 저장소 기본 경로를 순서대로 탐색하는 로딩 계층을 만들고, 한글 CSV 인코딩과 필수 컬럼 검증을 처리.</li>
              <li><b>대피소 추천 엔진:</b> 재난 유형별 전용 대피소 우선 추천 → 지역 단위 fallback → 하버사인(Haversine) 거리 계산 → 수용 인원 기반 정렬을 결합.</li>
              <li><b>실시간 + 모의 데이터:</b> Selenium 크롤러로 재난문자를 모아 앱 내부 표준 형식으로 변환하고, 크롤링이 어려운 상황을 대비해 <b>모의 재난문자 생성기</b>도 구현.</li>
              <li><b>경로 안내:</b> OSRM 도보 경로를 사용하되, API 실패 시 <b>직선거리 기반 대체 경로</b>를 자동으로 표시.</li>
              <li><b>구조 &amp; 검증:</b> Streamlit 멀티페이지(Home·시뮬레이션·실시간 안내·분석)를 일관되게 구성하고, Folium 지도로 위치·대피소·경로를 한 화면에 표시. <code class="mono">pytest</code>로 경로 계산·세션 상태·페이지 import 등 주요 모듈을 검증.</li>
            </ul>
          </div>
          <div class="tab-panel" id="p1-r">
            <ul>
              <li>사용자는 <b>재난 유형과 현재 위치에 맞는 대피소를 추천</b>받고, 외부 API나 실시간 수집이 실패해도 <b>대체 경로·모의 데이터로 서비스 흐름이 끊기지 않게</b> 되었습니다.</li>
              <li>단순 Streamlit 시각화가 아니라 <b>데이터 처리 · 추천 · 실시간 수집 · 장애 대응</b>을 포함한 재난 안내 구조로 확장.</li>
              <li>Folium·OSRM·Streamlit을 실제로 연동한 <b>작동하는 대시보드</b>를 완성 — 처음 다루는 기술을 빠르게 익혀 실전에 적용했습니다.</li>
            </ul>
          </div>
        </div>

        <div class="panel-media">
          <div class="gallery">
            <figure><img src="/assets/projects/dashboard-demo-1-landing.png" alt="실시간 대피 안내 초기 화면" loading="lazy"><figcaption>① 실시간 대피 안내 — 재난문자 확인 대기 화면</figcaption></figure>
            <figure><img src="/assets/projects/dashboard-demo-2-default.png" alt="재난문자 없는 경우" loading="lazy"><figcaption>② 재난문자가 없는 경우 — 위치(울산 북구) 기준 기본 상태</figcaption></figure>
            <figure><img src="/assets/projects/dashboard-demo-3-shelter.png" alt="대피소 추천 목록" loading="lazy"><figcaption>③ 재난문자 발생(자택) — 지도 + 추천 대피소 목록</figcaption></figure>
            <figure><img src="/assets/projects/dashboard-demo-4-route.png" alt="안전 경로 안내" loading="lazy"><figcaption>④ 재난문자 발생(풍랑주의보) — 도보 안전 경로 안내</figcaption></figure>
          </div>
        </div>
      </div>
    </section>

    <!-- ---------- PROJECT 2 : FirstCall ---------- -->
    <section class="view-panel" id="p2">
      <p class="view-h">// 주요 프로젝트 02</p>
      <div class="head">
        <div>
          <h2 class="view-title" style="margin-bottom:0;">Local-first API 워크벤치 · FirstCall</h2>
          <code class="repo">rad1092/firstcall-local-api-workbench</code>
        </div>
        <div class="links">
          <a href="https://github.com/rad1092/firstcall-local-api-workbench" target="_blank">GitHub ↗</a>
          <a href="https://github.com/rad1092/firstcall-local-api-workbench/releases" target="_blank">Releases ↗</a>
        </div>
      </div>
      <div class="stack"><span>Rust 2024</span><span>egui / eframe</span><span>firstcall-cli</span><span>GitHub Actions</span></div>

      <div class="panel-grid">
        <div class="panel-main">
          <p class="summary">여러 곳에서 만든 <b>API 호출을 내 컴퓨터 안에서 검증</b>하고, 안전한 형태로 정리해 재사용하게 해주는 도구입니다.</p>
          <p class="context">프로그램이 외부 서비스를 부르는 'API 요청'은 주소·인증키·형식이 제각각이라 매번 맞추기 번거롭고, 잘못하면 <b>비밀번호 같은 민감 정보가 새어 나갈</b> 위험도 있습니다. FirstCall은 이런 요청을 한 번 제대로 <b>검증해 '레시피'처럼 저장</b>해 두고, 민감 정보를 지운 채로 다시 쓸 수 있게 합니다. 특히 요즘 늘어나는 <b>AI 에이전트가 API를 안전하게 사용</b>하도록 "검증된 것만, 비밀정보는 빼고" 넘겨주는 것이 목표입니다.</p>
          <div class="ai-note"><span class="badge">AI</span><span>Rust 코어 설계와 여러 입력 형식 처리·테스트·문서 작성 과정에서 <b>Claude를 페어 프로그래밍 파트너</b>로 활용했습니다. 무엇을 만들지와 지켜야 할 규칙은 제가 정하고, 반복 구현과 예외 상황 점검 속도를 AI로 끌어올렸습니다.</span></div>

          <div class="tabs" role="tablist">
            <button class="tab-btn active" data-target="p2-s">상황</button>
            <button class="tab-btn" data-target="p2-t">과제</button>
            <button class="tab-btn" data-target="p2-a">행동</button>
            <button class="tab-btn" data-target="p2-r">결과</button>
          </div>
          <div class="tab-panel active" id="p2-s">
            <ul>
              <li>API 요청을 <b>재사용 가능한 형태로 안전하게 모아둘</b> 마땅한 도구가 없었습니다.</li>
              <li>특히 AI 에이전트나 자동화 도구에 API를 넘길 때 <b>인증키가 그대로 노출</b>되거나 <b>검증 안 된 요청</b>이 섞이는 위험이 컸습니다.</li>
              <li>요청을 외부 클라우드에 올리지 않고 <b>내 컴퓨터 안에서만 처리</b>하고 싶은 보안 요구도 있었습니다.</li>
            </ul>
          </div>
          <div class="tab-panel" id="p2-t">
            <ul>
              <li>curl·OpenAPI·Postman 등 <b>형식이 다른 요청들을 한 흐름으로 받아</b> 로컬에서 검증.</li>
              <li>검증에 성공한 요청만 <b>재사용 가능한 '레시피'로 저장</b>하고, 민감 정보는 지운 패키지로 내보내기.</li>
              <li>사람이 쓰는 <b>화면(GUI)</b>과 자동화가 쓰는 <b>명령어(CLI)</b>를 모두 제공.</li>
            </ul>
          </div>
          <div class="tab-panel" id="p2-a">
            <ul>
              <li>Rust로 핵심 로직을 만들고 그 위에 <b>두 가지 사용 방식</b>을 올렸습니다 — 클릭으로 쓰는 <b>데스크톱 화면</b>과, 자동화용 <b>명령어 도구(firstcall-cli)</b>.</li>
              <li>"가져오기 → 검증 → 레시피로 저장 → 민감정보 제거 후 내보내기 → 다시 검증"으로 이어지는 <b>안전 흐름</b>을 구조로 못박았습니다.</li>
              <li>가져온 요청 안의 <b>스크립트·설정 파일은 절대 실행하지 않도록</b> 처리해, 악성 코드가 끼어들 여지를 차단(공급망 보안).</li>
              <li>민감 정보는 환경변수로만 다루고, 자동 테스트·보안 점검을 GitHub Actions로 <b>릴리스 때마다 검증</b>.</li>
            </ul>
          </div>
          <div class="tab-panel" id="p2-r">
            <ul>
              <li>화면과 명령어 도구를 모두 담은 <b>v0.1.0 정식 배포본</b>을 윈도우·맥·리눅스용으로 출시.</li>
              <li>명령어 도구가 결과를 <b>기계가 읽기 좋은 형식(JSON)</b>으로도 내보내, 자동화·AI 파이프라인에 바로 연결 가능.</li>
              <li>"검증된, 민감정보 없는 요청만 밖으로 나간다"는 원칙을 <b>도구가 스스로 강제</b>하도록 설계.</li>
            </ul>
          </div>
        </div>

        <div class="panel-media">
          <div class="gallery">
            <figure><img src="/assets/projects/firstcall-gui-workbench.gif" alt="FirstCall 데스크톱 GUI 데모" loading="lazy"><figcaption>데스크톱 화면 — 요청을 가져와 검증·정리하는 흐름</figcaption></figure>
            <figure><img src="/assets/projects/firstcall-cli-demo.gif" alt="FirstCall CLI 데모" loading="lazy"><figcaption>명령어 도구 — 실제 실행 결과</figcaption></figure>
          </div>
        </div>
      </div>
    </section>

    <!-- ---------- PROJECT 3 : gh-dep-risk ---------- -->
    <section class="view-panel" id="p3">
      <p class="view-h">// 주요 프로젝트 03</p>
      <div class="head">
        <div>
          <h2 class="view-title" style="margin-bottom:0;">PR 의존성 리스크 점검 확장 · gh-dep-risk</h2>
          <code class="repo">rad1092/gh-dependency-risk</code>
        </div>
        <div class="links"><a href="https://github.com/rad1092/gh-dependency-risk" target="_blank">GitHub ↗</a></div>
      </div>
      <div class="stack"><span>Go</span><span>GitHub CLI Extension</span><span>Dependency Review API</span><span>GitHub Actions</span></div>

      <div class="panel-grid">
        <div class="panel-main">
          <p class="summary">코드 변경(PR)에 새로 들어온 <b>외부 라이브러리가 보안상 위험하지 않은지</b>, 리뷰어가 명령어 한 번으로 확인하게 해주는 도구입니다.</p>
          <p class="context">요즘 소프트웨어는 직접 만들지 않고 <b>외부 라이브러리(의존성)를 수십~수백 개씩 가져다 씁니다.</b> 그중 하나에 보안 취약점이 있으면 전체가 위험해지죠. 이 도구는 PR에 새로 추가된 라이브러리를 자동으로 점검해 <b>위험 정보를 PR 댓글로 정리</b>해 줍니다. 별도 서버나 데이터베이스 없이, <b>필요할 때만 명령어 하나로 실행</b>되는 가벼운 방식이라 작은 팀도 부담 없이 쓸 수 있습니다.</p>
          <div class="ai-note"><span class="badge">AI</span><span>npm·pip·Go 등 <b>도구마다 다른 라이브러리 기록 방식</b>을 정리하고 예외 상황을 점검할 때 AI를 활용해, 빠르게 테스트 케이스를 갖췄습니다. "어디까지 지원하고 무엇은 지원하지 않을지" 범위는 제가 직접 정했습니다.</span></div>

          <div class="tabs" role="tablist">
            <button class="tab-btn active" data-target="p3-s">상황</button>
            <button class="tab-btn" data-target="p3-t">과제</button>
            <button class="tab-btn" data-target="p3-a">행동</button>
            <button class="tab-btn" data-target="p3-r">결과</button>
          </div>
          <div class="tab-panel active" id="p3-s">
            <ul>
              <li>PR에 새로 추가되는 외부 라이브러리의 보안 위험을, 리뷰어가 <b>코드 검토 중에 빠르게 파악</b>하기 어려웠습니다.</li>
              <li>그렇다고 상시 켜두는 <b>서버·데이터베이스 같은 무거운 시스템</b>을 두는 건 작은 팀엔 부담이었습니다.</li>
            </ul>
          </div>
          <div class="tab-panel" id="p3-t">
            <ul>
              <li>설치·운영 부담 없이, <b>리뷰어가 필요할 때만 실행</b>하는 가벼운 도구.</li>
              <li>이미 쓰고 있는 GitHub 로그인을 그대로 활용해 <b>바로 실행</b>되게 하기.</li>
              <li>CI(자동 검사)를 실패시키지 않고, <b>리뷰어의 판단을 돕는</b> 형태로 결과 제공.</li>
            </ul>
          </div>
          <div class="tab-panel" id="p3-a">
            <ul>
              <li>서버 대신 <b>GitHub CLI 확장(작은 실행 파일 하나)</b>으로 만들어, 설치 한 줄로 끝나게 했습니다.</li>
              <li>먼저 <b>GitHub 공식 보안 데이터를 사용</b>하고, 그게 불가능할 때만 프로젝트 파일을 직접 읽어 점검하는 <b>대체 방식</b>으로 전환.</li>
              <li>점검 대상(npm·pip·Go 등)과 <b>지원 범위를 명확히 한정</b>해, 과한 분석으로 잘못된 결과를 내지 않도록 문서로 명시.</li>
              <li>결과는 <b>PR 댓글로 깔끔하게 정리</b>(중복 없이 갱신)하고, 자동 테스트로 안정성을 검증.</li>
            </ul>
          </div>
          <div class="tab-panel" id="p3-r">
            <ul>
              <li><code class="mono">gh extension install rad1092/gh-dep-risk</code> <b>한 줄로 설치·사용</b> 가능.</li>
              <li>npm·pip·Go·Maven 등 <b>11개 생태계</b>의 라이브러리 위험을 확인.</li>
              <li>CI를 멈추지 않고, <b>리뷰 흐름 안에서 보안을 점검</b>하는 가벼운 방식을 만들었습니다.</li>
            </ul>
          </div>
        </div>

        <div class="panel-media">
          <div class="gallery">
            <figure><img src="/assets/projects/gh-dependency-risk-demo.gif" alt="gh-dep-risk 터미널 데모" loading="lazy"><figcaption>터미널 데모 — PR 의존성을 점검해 결과를 정리</figcaption></figure>
          </div>
        </div>
      </div>
    </section>

    <!-- ---------- OTHER PROJECTS ---------- -->
    <section class="view-panel" id="more">
      <p class="view-h">// 더 보기</p>
      <h2 class="view-title">그 외 프로젝트</h2>
      <div class="archive">
        <div class="arch-card">
          <div class="top"><span class="folder">🪞</span><a class="ext" href="https://github.com/rad1092/smart-mirror-pc123" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/smart-mirror-pc123" target="_blank">스마트 미러 AIoT 운동 코칭</a></h4>
          <p>화면 · 비전 게이트웨이 · AI 코칭 엔진을 한 저장소로 묶은 통합본. 자세 분석, 운동 루틴 생성, 실시간 코칭을 연결합니다.</p>
          <div class="tags"><span>Python</span><span>WebSocket</span><span>SQLite</span><span>AIoT</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">🔌</span><a class="ext" href="https://github.com/rad1092/firstcall-api-lookup-mcp" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/firstcall-api-lookup-mcp" target="_blank">FirstCall API Lookup MCP</a></h4>
          <p>FirstCall로 만든 읽기 전용 MCP 서버. 공개 사용자 정보를 조회하는 툴 하나를 AI 에이전트가 바로 쓸 수 있게 제공.</p>
          <div class="tags"><span>TypeScript</span><span>MCP</span><span>Node</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">🧭</span><a class="ext" href="https://github.com/rad1092/job-coach-agent" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/job-coach-agent" target="_blank">취업 코치형 에이전트</a></h4>
          <p>희망 직무를 입력하면 채용 공고 탐색부터 분석 리포트·자소서 초안·면접 대비·합격 로드맵까지 한 흐름으로 정리.</p>
          <div class="tags"><span>Streamlit</span><span>FastAPI</span><span>SQLite</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">⌨️</span><a class="ext" href="https://github.com/rad1092/ascii-diagram-editor" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/ascii-diagram-editor" target="_blank">ASCII 다이어그램 에디터</a></h4>
          <p>브라우저에서 동작하는 ASCII 다이어그램 에디터. 고정 격자 위에서 그린 결과를 실제 텍스트로 렌더링합니다.</p>
          <div class="tags"><span>TypeScript</span><span>Vite</span><span>Client-side</span></div>
        </div>
      </div>
      <p class="lead" style="margin-top:18px;font-size:.9rem;">전체 저장소는 <a href="/repositories/">저장소 목록 페이지</a>에서 볼 수 있습니다.</p>
    </section>

    <!-- ---------- CONTACT ---------- -->
    <section class="view-panel" id="contact">
      <p class="view-h">// 연락</p>
      <h2 class="view-title">함께 일해요</h2>
      <p class="lead">새로운 협업이나 프로젝트 제안은 언제든 환영합니다. 편하게 연락 주세요.</p>
      <div class="contact-big"><a href="https://github.com/rad1092" target="_blank">GitHub @rad1092 →</a></div>
      <p class="foot">Built with Jekyll · Designed &amp; developed by HongDae Kim — with a little help from AI</p>
    </section>

  </main>
</div>
</div>

<script>
(function () {
  function showView() {
    var v = (location.hash || '#about').replace('#', '');
    var panel = document.getElementById(v);
    if (!panel || !panel.classList.contains('view-panel')) v = 'about';
    document.querySelectorAll('.view-panel').forEach(function (p) { p.classList.toggle('active', p.id === v); });
    document.querySelectorAll('.nav-btn').forEach(function (b) { b.classList.toggle('active', b.getAttribute('href') === '#' + v); });
    window.scrollTo(0, 0);
  }
  window.addEventListener('hashchange', showView);
  showView();

  // Inner STAR tabs
  document.querySelectorAll('.tabs').forEach(function (tabs) {
    tabs.addEventListener('click', function (e) {
      var btn = e.target.closest('.tab-btn');
      if (!btn) return;
      var scope = tabs.closest('.view-panel');
      scope.querySelectorAll('.tab-btn').forEach(function (b) { b.classList.remove('active'); });
      scope.querySelectorAll('.tab-panel').forEach(function (p) { p.classList.remove('active'); });
      btn.classList.add('active');
      var t = scope.querySelector('#' + btn.dataset.target);
      if (t) t.classList.add('active');
    });
  });
})();
</script>

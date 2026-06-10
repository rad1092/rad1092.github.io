---
layout: default
---

<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.min.css">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;700&family=Fraunces:opsz,wght@9..144,500;9..144,600;9..144,700&family=Nanum+Myeongjo:wght@700;800&display=swap">

<style>
/* ===== Reset Cayman chrome — full-bleed canvas ===== */
.page-header { display: none !important; }
.main-content { max-width: none !important; margin: 0 !important; padding: 0 !important; width: 100% !important; }
.main-content h1, .main-content h2, .main-content h3, .main-content h4 { border: none; font-weight: inherit; }
.page-footer, footer.site-footer { display: none !important; }

:root {
  --bg: #ffffff;
  --bg-soft: #f5f6f8;
  --card: #ffffff;
  --line: #e7e7ec;
  --text: #18181b;
  --muted: #6c6c76;
  --accent: #2f56e6;        /* cobalt blue */
  --accent-ink: #ffffff;
  --serif: "Space Grotesk", "Pretendard", sans-serif;   /* labels / code / mono */
  --display: "Fraunces", "Nanum Myeongjo", "Pretendard", serif;  /* editorial headings */
}

body { background: var(--bg); }
.pf { color: var(--text); font-family: "Pretendard", -apple-system, BlinkMacSystemFont, "Segoe UI", "Apple SD Gothic Neo", sans-serif; line-height: 1.7; -webkit-font-smoothing: antialiased; word-break: keep-all; overflow-wrap: break-word; }
.pf a { color: var(--text); text-decoration: none; }
.pf a:hover { color: var(--accent); }
.pf .mono { font-family: "Space Grotesk", ui-monospace, monospace; }
.pf ::selection { background: var(--accent); color: var(--accent-ink); }
.pf a:focus-visible { outline: 2px solid var(--accent); outline-offset: 3px; border-radius: 4px; }

/* subtle background grid (fills empty space without clutter) */
.pf::before { content: ""; position: fixed; inset: 0; z-index: 0; pointer-events: none;
  background-image: linear-gradient(to right, rgba(24,24,40,.031) 1px, transparent 1px),
                    linear-gradient(to bottom, rgba(24,24,40,.031) 1px, transparent 1px);
  background-size: 78px 78px; }

/* ===== App shell: editorial left rail + wide content ===== */
.app { display: flex; align-items: flex-start; max-width: 1360px; margin: 0 auto; position: relative; z-index: 1; }

.rail { position: sticky; top: 0; align-self: flex-start; height: 100vh; flex: 0 0 264px;
  padding: 56px 30px 40px 46px; display: flex; flex-direction: column; }
.rail-name { font-family: var(--display); font-size: 1.8rem; font-weight: 600; letter-spacing: -.01em; line-height: 1.15; }
.rail-name small { display: block; font-size: .82rem; font-weight: 500; color: var(--muted); margin-top: 4px; letter-spacing: 0; }
.rail-role { color: var(--muted); font-size: .9rem; margin-top: 14px; max-width: 200px; }

/* project-centric rail */
.rail-work { margin-top: 40px; display: flex; flex-direction: column; gap: 2px; }
.rail-work .grp { font-family: var(--serif); font-size: .68rem; letter-spacing: .16em; text-transform: uppercase; color: var(--muted); margin-bottom: 14px; }
.work-link { display: block; padding: 10px 0 10px 16px; border-left: 2px solid var(--line); transition: border-color .18s, padding-left .18s; }
.work-link .wno { display: block; font-family: var(--serif); font-size: .68rem; letter-spacing: .08em; text-transform: uppercase; color: var(--muted); }
.work-link .wt { display: block; font-family: var(--display); font-size: 1.12rem; font-weight: 500; color: var(--text); margin-top: 2px; letter-spacing: -.01em; line-height: 1.2; }
.work-link:hover { border-left-color: var(--text); padding-left: 20px; }
.work-link:hover .wno { color: var(--text); }
.rail .work-link.active { border-left-color: var(--accent); padding-left: 20px; }
.rail .work-link.active .wt, .rail .work-link.active .wno { color: var(--accent); }

.rail-sub { margin-top: 26px; padding-top: 22px; border-top: 1px solid var(--line); display: flex; flex-wrap: wrap; gap: 8px 18px; }
.rail-sub a { font-family: var(--serif); font-size: .74rem; letter-spacing: .08em; text-transform: uppercase; color: var(--muted); transition: .15s; display: inline-flex; align-items: center; }
.rail-sub a::before { content: ""; width: 0; height: 1px; background: var(--accent); margin-right: 0; transition: width .18s, margin-right .18s; }
.rail-sub a:hover::before, .rail .rail-sub a.active::before { width: 14px; margin-right: 7px; }
.rail-sub a:hover { color: var(--text); }
.rail .rail-sub a.active { color: var(--accent); }

.rail-foot { margin-top: auto; display: flex; gap: 18px; font-size: .82rem; }
.rail-foot a { color: var(--muted); }
.rail-foot a:hover { color: var(--accent); }

.view { flex: 1; min-width: 0; padding: 72px 72px 120px; }
.view-panel { display: none; animation: fade .5s cubic-bezier(.22,1,.36,1); position: relative; }
.view-panel.active { display: block; }
@keyframes fade { from { opacity: 0; transform: translateY(14px); } to { opacity: 1; transform: none; } }
.pno { position: absolute; top: -18px; right: 0; font-family: var(--display); font-size: 8.5rem; font-weight: 600; line-height: 1; letter-spacing: -.04em; color: color-mix(in srgb, var(--accent) 7%, transparent); pointer-events: none; user-select: none; }

.kicker { font-family: var(--serif); font-size: .78rem; color: var(--accent); letter-spacing: .14em; text-transform: uppercase; margin: 0 0 14px; display: flex; align-items: center; gap: 12px; }
.kicker::before { content: ""; width: 28px; height: 1px; background: var(--accent); flex: 0 0 auto; }
.view-title { font-family: var(--display); font-size: 2.8rem; font-weight: 600; letter-spacing: -.01em; line-height: 1.12; margin: 0 0 26px; text-wrap: balance; }
.lead { color: var(--muted); font-size: 1.08rem; max-width: 68ch; }
.lead .hl { color: var(--text); }

/* about */
.about-hero { display: grid; grid-template-columns: minmax(0, 1fr) 240px; gap: 56px; align-items: center; }
.about-text { min-width: 0; }
.about-photo { width: 240px; height: 240px; border-radius: 50%; object-fit: cover; border: 1px solid var(--line); box-shadow: 0 18px 50px rgba(24,24,27,.14); outline: 1px solid color-mix(in srgb, var(--accent) 32%, transparent); outline-offset: 12px; }
.about-head { font-family: var(--display); font-size: 3.1rem; font-weight: 600; letter-spacing: -.015em; line-height: 1.16; margin: 0 0 28px; text-wrap: balance; }
.about-head .hl { color: var(--accent); }
.chips { display: flex; flex-wrap: wrap; gap: 9px; margin-top: 26px; }
.chip { border: 1px solid var(--line); color: var(--text); padding: 7px 14px; border-radius: 999px; font-size: .84rem; transition: border-color .15s; }
.chip:hover { border-color: color-mix(in srgb, var(--accent) 50%, var(--line)); }
.chip b { color: var(--accent); font-weight: 600; }
.cta { margin-top: 34px; }
.cta a { display: inline-block; margin: 0 12px 12px 0; padding: 12px 22px; border-radius: 999px; border: 1px solid var(--line); color: var(--text); font-size: .92rem; font-weight: 500; transition: .15s; }
.cta a:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }
.cta a.primary { background: var(--accent); color: var(--accent-ink); border-color: var(--accent); font-weight: 600; }
.cta a.primary:hover { color: var(--accent-ink); filter: brightness(1.05); box-shadow: 0 10px 26px color-mix(in srgb, var(--accent) 30%, transparent); }

/* timeline */
.timeline { position: relative; padding-left: 28px; max-width: 880px; }
.timeline::before { content: ""; position: absolute; left: 5px; top: 8px; bottom: 8px; width: 1px; background: var(--line); }
.tl-item { position: relative; padding: 0 0 34px; }
.tl-item:last-child { padding-bottom: 0; }
.tl-item::before { content: ""; position: absolute; left: -28px; top: 6px; width: 11px; height: 11px; border-radius: 50%; background: var(--bg); border: 2px solid var(--accent); transition: background .18s; }
.tl-item:hover::before { background: var(--accent); }
.tl-when { font-family: var(--serif); font-size: .8rem; color: var(--accent); letter-spacing: .04em; }
.tl-role { font-family: var(--display); font-size: 1.3rem; font-weight: 600; margin: 5px 0 3px; letter-spacing: -.01em; }
.tl-role .org { color: var(--muted); font-weight: 400; font-size: .92rem; }
.tl-desc { color: var(--muted); margin: 6px 0 0; }
.tl-detail { margin: 14px 0 0; padding-left: 20px; color: var(--muted); }
.tl-detail li { margin-bottom: 9px; }
.tl-detail b { color: var(--accent); font-family: var(--serif); font-size: .82rem; letter-spacing: .02em; }
.certs-title { font-family: var(--serif); font-size: .76rem; color: var(--muted); letter-spacing: .12em; margin: 46px 0 14px; text-transform: uppercase; }
.certs { display: flex; flex-wrap: wrap; gap: 10px; }
.cert { border: 1px solid var(--line); border-radius: 10px; padding: 9px 15px; font-size: .94rem; transition: border-color .15s; }
.cert:hover { border-color: color-mix(in srgb, var(--accent) 50%, var(--line)); }

/* project view (single wide column) */
.proj-head { display: flex; justify-content: space-between; align-items: flex-start; gap: 20px; flex-wrap: wrap; }
.repo { font-family: var(--serif); font-size: .84rem; color: var(--muted); display: block; margin-top: 8px; letter-spacing: .02em; }
.role-tag { display: inline-block; margin-top: 12px; font-size: .84rem; color: var(--accent); border: 1px solid color-mix(in srgb, var(--accent) 40%, transparent); padding: 4px 12px; border-radius: 999px; }
.proj-links a { font-size: .88rem; margin-left: 16px; white-space: nowrap; color: var(--muted); }
.proj-links a:hover { color: var(--accent); }
.stack { display: flex; flex-wrap: wrap; gap: 9px; margin: 22px 0 26px; }
.stack span { font-family: var(--serif); font-size: .77rem; color: var(--muted); border: 1px solid var(--line); padding: 4px 11px; border-radius: 8px; transition: .15s; }
.stack span:hover { border-color: var(--accent); color: var(--accent); }

.summary { color: var(--text); margin: 0 0 16px; font-size: 1.35rem; line-height: 1.5; font-weight: 500; letter-spacing: -.01em; max-width: 760px; }
.summary b { color: var(--accent); font-weight: 600; }
.context { color: var(--muted); margin: 0 0 22px; max-width: 72ch; font-size: 1.04rem; }
.context b { color: var(--text); }

.ai-note { display: flex; gap: 13px; align-items: flex-start; margin: 0 0 30px; padding: 15px 18px; border: 1px solid color-mix(in srgb, var(--accent) 28%, transparent); border-radius: 12px; font-size: .94rem; color: var(--muted); max-width: 760px; background: color-mix(in srgb, var(--accent) 5%, transparent); }
.ai-note .badge { flex: 0 0 auto; font-family: var(--serif); font-size: .68rem; font-weight: 700; color: var(--accent-ink); background: var(--accent); padding: 3px 8px; border-radius: 6px; margin-top: 2px; letter-spacing: .05em; }
.ai-note b { color: var(--text); }

.media { margin: 0 0 30px; }
.gallery { display: grid; gap: 14px; }
.gallery.cols-2 { grid-template-columns: repeat(2, 1fr); }
.gallery.one { max-width: 760px; }
.gallery figure { margin: 0; border: 1px solid var(--line); border-radius: 12px; overflow: hidden; background: var(--bg-soft); transition: border-color .2s, box-shadow .25s, transform .25s; }
.gallery figure:hover { border-color: color-mix(in srgb, var(--accent) 40%, var(--line)); box-shadow: 0 16px 40px rgba(24,24,27,.1); transform: translateY(-3px); }
.gallery img { width: 100%; display: block; }
.gallery figcaption { font-size: .8rem; color: var(--muted); padding: 9px 12px; border-top: 1px solid var(--line); }

/* metric / quick-fact cards */
.metrics { display: grid; grid-template-columns: repeat(auto-fit, minmax(132px, 1fr)); gap: 12px; margin: 6px 0 36px; max-width: 720px; }
.metric { border: 1px solid var(--line); border-radius: 12px; padding: 18px 20px; background: var(--card); transition: border-color .2s, transform .2s, box-shadow .2s; }
.metric:hover { border-color: color-mix(in srgb, var(--accent) 45%, var(--line)); transform: translateY(-3px); box-shadow: 0 10px 28px rgba(24,24,27,.07); }
.metric b { display: block; font-family: var(--display); font-size: 2rem; font-weight: 600; color: var(--accent); letter-spacing: -.02em; line-height: 1; font-variant-numeric: tabular-nums; }
.metric span { display: block; margin-top: 9px; font-size: .82rem; color: var(--muted); line-height: 1.4; }

/* case-study narrative (replaces STAR tabs) */
.case { max-width: 820px; }
.case-block { padding: 30px 0; border-top: 1px solid var(--line); }
.case-block.flush { border-top: none; padding: 0 0 30px; }
.case-h { font-family: var(--serif); font-size: .76rem; letter-spacing: .14em; text-transform: uppercase; color: var(--muted); margin: 0 0 16px; }
.case-h::before { content: ""; display: inline-block; width: 7px; height: 7px; border-radius: 2px; background: var(--accent); margin-right: 9px; vertical-align: 1px; }
.case-h .sub { color: var(--text); }
.case-block p { margin: 0; font-size: 1.04rem; color: var(--muted); }
.case-block p b { color: var(--text); }
.case-block ul { margin: 0; padding-left: 20px; }
.case-block li { margin-bottom: 12px; color: var(--muted); }
.case-block li b { color: var(--text); }

/* other projects */
.archive { display: grid; grid-template-columns: repeat(2, 1fr); gap: 18px; max-width: 920px; }
.arch-card { border: 1px solid var(--line); border-radius: 14px; padding: 24px; background: var(--card); transition: transform .2s, border-color .2s, background .2s; }
.arch-card:hover { transform: translateY(-5px); border-color: var(--accent); background: var(--bg-soft); box-shadow: 0 14px 34px rgba(24,24,27,.08); }
.arch-card .top { display: flex; justify-content: space-between; align-items: center; margin-bottom: 16px; }
.arch-card .folder { font-size: 1.5rem; }
.arch-card .ext { color: var(--muted); }
.arch-card .ext:hover { color: var(--accent); }
.arch-card h4 { margin: 0 0 9px; font-size: 1.12rem; font-weight: 700; letter-spacing: -.01em; }
.arch-card h4 a { color: var(--text); }
.arch-card h4 a:hover { color: var(--accent); }
.arch-card p { color: var(--muted); font-size: .92rem; margin: 0 0 16px; }
.arch-card .tags { display: flex; flex-wrap: wrap; gap: 9px; font-family: var(--serif); font-size: .74rem; color: var(--muted); }

/* contact */
.contact-big { margin-top: 22px; }
.contact-big a { display: inline-block; padding: 14px 30px; border-radius: 999px; background: var(--accent); color: var(--accent-ink); font-weight: 600; transition: transform .18s, box-shadow .18s, filter .18s; }
.contact-big a:hover { color: var(--accent-ink); filter: brightness(1.05); transform: translateY(-2px); box-shadow: 0 12px 30px color-mix(in srgb, var(--accent) 35%, transparent); }
.foot { color: var(--muted); font-size: .82rem; margin-top: 56px; }

@media (max-width: 900px) {
  .app { flex-direction: column; max-width: none; }
  .rail { position: sticky; top: 0; z-index: 10; height: auto; width: 100%; flex-basis: auto;
    background: rgba(255,255,255,.94); backdrop-filter: blur(8px); border-bottom: 1px solid var(--line);
    padding: 11px 16px; flex-direction: row; align-items: center; gap: 14px; }
  .rail > div:first-child { display: flex; align-items: center; gap: 14px; flex: 1; min-width: 0; overflow-x: auto; }
  .rail-name { font-size: 1rem; white-space: nowrap; }
  .rail-name small, .rail-role { display: none; }
  .rail-work { margin: 0; flex-direction: row; gap: 4px; }
  .rail-work .grp { display: none; }
  .work-link { border-left: none; padding: 6px 10px; white-space: nowrap; }
  .work-link .wno { display: none; }
  .work-link .wt { font-size: .9rem; }
  .rail-sub { margin: 0; padding: 0 0 0 10px; border-top: none; border-left: 1px solid var(--line); gap: 12px; flex-wrap: nowrap; }
  .rail-sub a { white-space: nowrap; }
  .rail-foot { margin: 0; flex: 0 0 auto; gap: 12px; font-size: .74rem; }
  .view { padding: 30px 20px 80px; }
  .about-hero { grid-template-columns: 1fr; gap: 22px; justify-items: start; }
  .about-photo { width: 120px; height: 120px; order: -1; }
  .about-head { font-size: 2rem; }
  .view-title { font-size: 1.9rem; }
  .gallery.cols-2 { grid-template-columns: 1fr; }
  .archive { grid-template-columns: 1fr; }
  .pno { display: none; }
}

@media (prefers-reduced-motion: reduce) {
  .pf *, .pf *::before, .pf *::after { animation: none !important; transition: none !important; }
}
</style>

<div class="pf" markdown="0">
<div class="app">

  <!-- ================= LEFT RAIL ================= -->
  <aside class="rail">
    <div>
      <div class="rail-name">김홍대<small>HongDae Kim</small></div>
      <p class="rail-role">사용자의 다음 한 걸음을 돕는 소프트웨어를 만듭니다</p>
      <nav class="rail-work">
        <div class="grp">Work</div>
        <a class="nav-link work-link" href="#p1"><span class="wno">01 · Python</span><span class="wt">재난 대피 대시보드</span></a>
        <a class="nav-link work-link" href="#p2"><span class="wno">02 · Rust</span><span class="wt">FirstCall</span></a>
        <a class="nav-link work-link" href="#p3"><span class="wno">03 · Go</span><span class="wt">gh-dep-risk</span></a>
      </nav>
      <nav class="rail-sub">
        <a class="nav-link active" href="#about">소개</a>
        <a class="nav-link" href="#experience">경력</a>
        <a class="nav-link" href="#more">그 외</a>
        <a class="nav-link" href="#contact">연락</a>
      </nav>
    </div>
    <div class="rail-foot">
      <a href="https://github.com/rad1092" target="_blank">GitHub</a>
      <a href="/en/">EN</a>
    </div>
  </aside>

  <!-- ================= VIEWS ================= -->
  <main class="view">

    <!-- ---------- ABOUT ---------- -->
    <section class="view-panel active" id="about">
      <p class="kicker">01 — 소개</p>
      <div class="about-hero">
        <div class="about-text">
          <h1 class="about-head">현장 영업과 납품을 거쳐, 사람의 <span class="hl">다음 한 걸음</span>을 돕는 소프트웨어를 만듭니다</h1>
          <p class="lead">
            실험적인 학습 저장소에서 시작해 실제 사용할 수 있는 도구형 프로젝트까지 단계적으로 확장해 왔고,
            <span class="hl">"정보 전달을 넘어 실제 행동을 돕는다"</span>는 관점으로 재난 대피 안내와 API 도구화,
            의존성 보안 점검처럼 사용자의 다음 행동을 만들어 주는 소프트웨어에 집중합니다
          </p>
        </div>
        <img class="about-photo" src="/profile.png" alt="김홍대 프로필 사진">
      </div>
      <div class="chips">
        <span class="chip"><b>Python</b> Streamlit, Pandas, Folium</span>
        <span class="chip"><b>Rust</b> egui/eframe</span>
        <span class="chip"><b>Go</b> GitHub CLI</span>
        <span class="chip"><b>DevOps</b> GitHub Actions</span>
        <span class="chip"><b>AI</b> MCP, 에이전트 도구화</span>
      </div>
      <div class="cta">
        <a class="primary" href="#p1">주요 프로젝트 보기 →</a>
        <a href="#experience">경력 보기</a>
      </div>
    </section>

    <!-- ---------- EXPERIENCE ---------- -->
    <section class="view-panel" id="experience">
      <p class="kicker">02 — 경력과 이력</p>
      <h2 class="view-title">경력과 이력</h2>
      <div class="timeline">
        <div class="tl-item">
          <div class="tl-when">2016.07 – 2017.07, 2022.04 – 2025.04 — 합산 약 4년</div>
          <div class="tl-role">영업관리, 자재 납품 <span class="org">— 효상안전종합상사</span></div>
          <p class="tl-desc">건설 현장에 들어가는 자재와 안전용품을 다루는 회사에서 자재 납품 실무로 시작해 영업관리까지 맡으며 약 4년간 근무했고, 거래처를 직접 응대하고 일정과 재고, 납기를 조율하며 현장의 요구를 절차와 데이터로 정리해 처리했습니다</p>
          <ul class="tl-detail">
            <li><b>2022.04 – 2025.04</b> 영업관리와 자재 납품 — 거래처 영업 관리, 일정과 재고, 납기 조율, 고객 직접 응대</li>
            <li><b>2016.07 – 2017.07</b> 자재 납품 — 건설 현장 자재 납품 실무</li>
          </ul>
        </div>
        <div class="tl-item">
          <div class="tl-when">2017.07 – 2018.07</div>
          <div class="tl-role">교환학생 (어학연수) <span class="org">— UNAM CEPE, 멕시코 국립자치대학교</span></div>
          <p class="tl-desc">멕시코 국립자치대학교(UNAM) 외국인 교육센터(CEPE)에서 1년간 교환학생으로 스페인어와 멕시코 문화를 공부했고, 낯선 환경에 빠르게 적응하고 다른 언어와 문화권 사람들과 소통하는 법을 익혔습니다</p>
        </div>
      </div>

      <div class="certs-title">자격과 면허</div>
      <div class="certs">
        <span class="cert">🚜 굴삭기 운전</span>
        <span class="cert">🏗️ 지게차 운전</span>
        <span class="cert">🚛 1종 대형 운전면허</span>
      </div>
    </section>

    <!-- ---------- PROJECT 1 : Disaster Dashboard ---------- -->
    <section class="view-panel" id="p1">
      <span class="pno" aria-hidden="true">01</span>
      <p class="kicker">주요 프로젝트 01</p>
      <div class="proj-head">
        <div>
          <h2 class="view-title" style="margin-bottom:0;">영남권 실시간 재난 대피 안내 대시보드</h2>
          <code class="repo">rad1092/project_dashboard</code>
          <div><span class="role-tag">4인 팀 — 백엔드 / 아키텍처 담당</span></div>
        </div>
        <div class="proj-links"><a href="https://github.com/rad1092/project_dashboard" target="_blank">GitHub ↗</a></div>
      </div>
      <div class="stack"><span>Python</span><span>Streamlit</span><span>Pandas</span><span>Folium</span><span>OSRM</span><span>Selenium</span><span>SQLite</span><span>pytest</span></div>

      <p class="summary">재난문자는 <b>"무슨 일이 일어났는지"</b>만 알려줄 뿐, "지금 어디로, 어떻게 대피해야 하는지"까지 안내하는 대시보드를 만들었습니다</p>

      <div class="metrics">
        <div class="metric"><b>4인</b><span>팀, 백엔드/아키텍처 담당</span></div>
        <div class="metric"><b>4</b><span>멀티페이지 구성</span></div>
        <div class="metric"><b>5</b><span>지원 권역 (대구, 울산, 부산, 경북, 경남)</span></div>
      </div>

      <div class="media">
        <div class="gallery cols-2">
          <figure><img src="/assets/projects/dashboard-demo-1-landing.png" alt="실시간 대피 안내 초기 화면" loading="lazy"><figcaption>① 실시간 대피 안내 — 재난문자 확인 대기 화면</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-2-default.png" alt="재난문자 없는 경우" loading="lazy"><figcaption>② 재난문자 없는 경우 — 위치(울산 북구) 기준 기본 상태</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-3-shelter.png" alt="대피소 추천 목록" loading="lazy"><figcaption>③ 재난문자 발생(자택) — 지도 + 추천 대피소 목록</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-4-route.png" alt="안전 경로 안내" loading="lazy"><figcaption>④ 재난문자 발생(풍랑주의보) — 도보 안전 경로 안내</figcaption></figure>
        </div>
      </div>

      <div class="ai-note"><span class="badge">AI</span><span>처음 다뤄 보는 기술 스택이 많았는데 <b>AI 도구를 적극 활용해 단기간에 구현 역량을 끌어올렸고</b>, 새로운 도구를 실전에서 빠르게 익히며 AI를 개발 파트너로 부리는 실용적인 방식을 체득한 프로젝트입니다</span></div>

      <div class="case">
        <div class="case-block flush">
          <h3 class="case-h">문제</h3>
          <p>재난문자는 발생 사실만 알릴 뿐 특보 데이터와 대피소 정보가 흩어져 있어 위기 상황에서 <b>빠른 판단이 어려웠고</b>, 정적 공공데이터와 실시간 재난문자, 사용자 위치, 외부 경로 API를 함께 쓰는 서비스라 단순 화면 시각화보다 <b>데이터가 끊기지 않게 불러오고 추천하고 길을 찾아주는 구조</b>가 핵심이었습니다</p>
        </div>
        <div class="case-block">
          <h3 class="case-h">내 역할 — <span class="sub">4인 팀, 백엔드 / 아키텍처</span></h3>
          <ul>
            <li>전체 대시보드 <b>아키텍처 설계</b>를 담당</li>
            <li>데이터 경로 관리와 CSV 검증, 정규화, 실시간 재난문자 처리, <b>대피소 추천 로직</b>, OSRM 경로 조회와 <b>장애 대응(fallback)</b> 구조를 설계하고 구현</li>
            <li>지도 시각화와 테스트 구성 등 <b>핵심 기능 구현을 주도</b></li>
          </ul>
        </div>
        <div class="case-block">
          <h3 class="case-h">한 일</h3>
          <ul>
            <li><b>안 끊기는 데이터 로딩</b> — 환경변수 → Streamlit secrets → 저장소 기본 경로를 순서대로 탐색하는 로딩 계층을 만들고, 한글 CSV 인코딩과 필수 컬럼 검증을 처리</li>
            <li><b>대피소 추천 엔진</b> — 재난 유형별 전용 대피소 우선 추천 → 지역 단위 fallback → 하버사인(Haversine) 거리 계산 → 수용 인원 기반 정렬을 결합</li>
            <li><b>실시간과 모의 데이터</b> — Selenium 크롤러로 재난문자를 모아 앱 내부 표준 형식으로 변환하고, 크롤링이 어려운 상황을 대비해 <b>모의 재난문자 생성기</b>도 구현</li>
            <li><b>경로 안내</b> — OSRM 도보 경로를 사용하되 API 실패 시 <b>직선거리 기반 대체 경로</b>를 자동으로 표시</li>
            <li><b>구조와 검증</b> — Streamlit 멀티페이지(Home, 시뮬레이션, 실시간 안내, 분석)를 일관되게 구성하고, Folium 지도로 위치와 대피소, 경로를 한 화면에 표시하고 <code class="mono">pytest</code>로 경로 계산과 세션 상태, 페이지 import를 검증</li>
          </ul>
        </div>
        <div class="case-block">
          <h3 class="case-h">결과</h3>
          <ul>
            <li>사용자는 <b>재난 유형과 현재 위치에 맞는 대피소를 추천</b>받고, 외부 API나 실시간 수집이 실패해도 <b>대체 경로와 모의 데이터로 서비스 흐름이 끊기지 않게</b> 되었습니다</li>
            <li>단순 Streamlit 시각화가 아니라 <b>데이터 처리와 추천, 실시간 수집, 장애 대응</b>을 포함한 재난 안내 구조로 확장</li>
            <li>Folium과 OSRM, Streamlit을 실제로 연동한 <b>작동하는 대시보드</b>를 완성하고, 처음 다루는 기술을 빠르게 익혀 실전에 적용했습니다</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- ---------- PROJECT 2 : FirstCall ---------- -->
    <section class="view-panel" id="p2">
      <span class="pno" aria-hidden="true">02</span>
      <p class="kicker">주요 프로젝트 02</p>
      <div class="proj-head">
        <div>
          <h2 class="view-title" style="margin-bottom:0;">Local-first API 워크벤치 · FirstCall</h2>
          <code class="repo">rad1092/firstcall-local-api-workbench</code>
          <div><span class="role-tag">개인 프로젝트 · v0.1.0 릴리스 — 윈도우, 맥, 리눅스</span></div>
        </div>
        <div class="proj-links">
          <a href="https://github.com/rad1092/firstcall-local-api-workbench" target="_blank">GitHub ↗</a>
          <a href="https://github.com/rad1092/firstcall-local-api-workbench/releases" target="_blank">Releases ↗</a>
        </div>
      </div>
      <div class="stack"><span>Rust 2024</span><span>egui / eframe</span><span>firstcall-cli</span><span>GitHub Actions</span></div>

      <p class="summary">여러 곳에서 만든 <b>API 호출을 내 컴퓨터 안에서 검증</b>하고, 안전한 형태로 정리해 재사용하게 해주는 도구입니다</p>

      <div class="metrics">
        <div class="metric"><b>8</b><span>지원 입력 형식 (curl, OpenAPI, Postman 등)</span></div>
        <div class="metric"><b>2</b><span>사용 방식 — 데스크톱 GUI, CLI</span></div>
        <div class="metric"><b>3</b><span>OS 릴리스 (윈도우, 맥, 리눅스)</span></div>
      </div>

      <div class="media">
        <div class="gallery cols-2">
          <figure><img src="/assets/projects/firstcall-gui-workbench.gif" alt="FirstCall 데스크톱 GUI 데모" loading="lazy"><figcaption>데스크톱 화면 — 요청을 가져와 검증하고 정리하는 흐름</figcaption></figure>
          <figure><img src="/assets/projects/firstcall-cli-demo.gif" alt="FirstCall CLI 데모" loading="lazy"><figcaption>명령어 도구 — 실제 실행 결과</figcaption></figure>
        </div>
      </div>

      <div class="ai-note"><span class="badge">AI</span><span>Rust 코어 설계와 여러 입력 형식 처리, 테스트, 문서 작성 과정에서 <b>Claude를 페어 프로그래밍 파트너</b>로 활용했고, 무엇을 만들지와 지켜야 할 규칙은 제가 정하면서 반복 구현과 예외 상황 점검 속도를 AI로 끌어올렸습니다</span></div>

      <div class="case">
        <div class="case-block flush">
          <h3 class="case-h">문제</h3>
          <p>API 요청은 주소와 인증키, 형식이 제각각이라 <b>재사용 가능한 형태로 안전하게 모아둘</b> 도구가 마땅치 않았고, 특히 AI 에이전트나 자동화에 API를 넘길 때 <b>인증키가 그대로 노출</b>되거나 <b>검증 안 된 요청</b>이 섞일 위험이 컸으며, 요청을 외부 클라우드에 올리지 않고 <b>내 컴퓨터 안에서만 처리</b>하고 싶은 보안 요구도 있었습니다</p>
        </div>
        <div class="case-block">
          <h3 class="case-h">내 역할 — <span class="sub">개인 프로젝트, 설계부터 배포까지</span></h3>
          <ul>
            <li>curl, OpenAPI, Postman 등 <b>형식이 다른 요청을 한 흐름으로 받아</b> 로컬에서 검증하는 구조를 설계</li>
            <li>검증에 성공한 것만 <b>'레시피'로 저장</b>하고 민감 정보를 지운 패키지로 내보내는 흐름을 정의</li>
            <li>사람용 <b>화면(GUI)</b>과 자동화용 <b>명령어(CLI)</b>를 하나의 코어 위에 모두 제공</li>
          </ul>
        </div>
        <div class="case-block">
          <h3 class="case-h">한 일</h3>
          <ul>
            <li>Rust로 핵심 로직을 만들고 그 위에 <b>두 가지 사용 방식</b>을 올렸습니다 — 클릭으로 쓰는 <b>데스크톱 화면</b>과 자동화용 <b>명령어 도구(firstcall-cli)</b></li>
            <li>"가져오기 → 검증 → 레시피로 저장 → 민감정보 제거 후 내보내기 → 다시 검증"으로 이어지는 <b>안전 흐름</b>을 구조로 못박았습니다</li>
            <li>가져온 요청 안의 <b>스크립트와 설정 파일은 절대 실행하지 않도록</b> 처리해 악성 코드가 끼어들 여지를 차단(공급망 보안)</li>
            <li>민감 정보는 환경변수로만 다루고, 자동 테스트와 보안 점검을 GitHub Actions로 <b>릴리스 때마다 검증</b></li>
          </ul>
        </div>
        <div class="case-block">
          <h3 class="case-h">결과</h3>
          <ul>
            <li>화면과 명령어 도구를 모두 담은 <b>v0.1.0 정식 배포본</b>을 윈도우와 맥, 리눅스용으로 출시</li>
            <li>명령어 도구가 결과를 <b>기계가 읽기 좋은 형식(JSON)</b>으로도 내보내 자동화와 AI 파이프라인에 바로 연결 가능</li>
            <li>"검증된, 민감정보 없는 요청만 밖으로 나간다"는 원칙을 <b>도구가 스스로 강제</b>하도록 설계</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- ---------- PROJECT 3 : gh-dep-risk ---------- -->
    <section class="view-panel" id="p3">
      <span class="pno" aria-hidden="true">03</span>
      <p class="kicker">주요 프로젝트 03</p>
      <div class="proj-head">
        <div>
          <h2 class="view-title" style="margin-bottom:0;">PR 의존성 리스크 점검 확장 · gh-dep-risk</h2>
          <code class="repo">rad1092/gh-dependency-risk</code>
          <div><span class="role-tag">개인 프로젝트 · v0.2.0 릴리스</span></div>
        </div>
        <div class="proj-links"><a href="https://github.com/rad1092/gh-dependency-risk" target="_blank">GitHub ↗</a></div>
      </div>
      <div class="stack"><span>Go</span><span>GitHub CLI Extension</span><span>Dependency Review API</span><span>GitHub Actions</span></div>

      <p class="summary">코드 변경(PR)에 새로 들어온 <b>외부 라이브러리가 보안상 위험하지 않은지</b>, 리뷰어가 명령어 한 번으로 확인하게 해주는 도구입니다</p>

      <div class="metrics">
        <div class="metric"><b>11</b><span>점검 가능한 생태계 (npm, pip, Go, Maven 등)</span></div>
        <div class="metric"><b>1</b><span>설치 = 명령어 한 줄</span></div>
        <div class="metric"><b>0</b><span>서버, DB, 상시 인프라</span></div>
      </div>

      <div class="media">
        <div class="gallery one">
          <figure><img src="/assets/projects/gh-dependency-risk-demo.gif" alt="gh-dep-risk 터미널 데모" loading="lazy"><figcaption>터미널 데모 — PR 의존성을 점검해 결과를 정리</figcaption></figure>
        </div>
      </div>

      <div class="ai-note"><span class="badge">AI</span><span>npm, pip, Go 등 <b>도구마다 다른 라이브러리 기록 방식</b>을 정리하고 예외 상황을 점검할 때 AI를 활용해 빠르게 테스트 케이스를 갖췄고, "어디까지 지원하고 무엇은 지원하지 않을지" 범위는 제가 직접 정했습니다</span></div>

      <div class="case">
        <div class="case-block flush">
          <h3 class="case-h">문제</h3>
          <p>요즘 소프트웨어는 <b>외부 라이브러리를 수십~수백 개씩</b> 가져다 쓰고, 그중 하나에 취약점이 있으면 전체가 위험해지는데, 리뷰어가 PR에 새로 추가된 라이브러리의 위험을 <b>코드 검토 중에 빠르게 파악</b>하긴 어려웠고, 그렇다고 상시 켜두는 <b>서버나 DB 같은 무거운 시스템</b>은 작은 팀엔 부담이었습니다</p>
        </div>
        <div class="case-block">
          <h3 class="case-h">내 역할 — <span class="sub">개인 프로젝트, 설계부터 배포까지</span></h3>
          <ul>
            <li>설치와 운영 부담 없이 <b>리뷰어가 필요할 때만 실행</b>하는 가벼운 도구로 방향을 잡음</li>
            <li>이미 쓰는 GitHub 로그인을 그대로 활용해 <b>바로 실행</b>되게 설계</li>
            <li>CI를 실패시키지 않고 <b>리뷰어의 판단을 돕는</b> 형태로 결과를 전달하도록 결정</li>
          </ul>
        </div>
        <div class="case-block">
          <h3 class="case-h">한 일</h3>
          <ul>
            <li>서버 대신 <b>GitHub CLI 확장(작은 실행 파일 하나)</b>으로 만들어 설치 한 줄로 끝나게 했습니다</li>
            <li>먼저 <b>GitHub 공식 보안 데이터를 사용</b>하고, 불가능할 때만 프로젝트 파일을 직접 읽는 <b>대체 방식</b>으로 전환</li>
            <li>점검 대상(npm, pip, Go 등)과 <b>지원 범위를 명확히 한정</b>해 과한 분석으로 잘못된 결과를 내지 않도록 문서로 명시</li>
            <li>결과는 <b>PR 댓글로 깔끔하게 정리</b>(중복 없이 갱신)하고, 자동 테스트에 더해 npm과 pnpm, Yarn <b>실제 PR 픽스처 저장소로 스모크 테스트</b>를 돌려 안정성을 검증</li>
          </ul>
        </div>
        <div class="case-block">
          <h3 class="case-h">결과</h3>
          <ul>
            <li><code class="mono">gh extension install rad1092/gh-dep-risk</code> <b>한 줄로 설치하고 사용</b> 가능</li>
            <li>npm, pip, Go, Maven 등 <b>11개 생태계</b>의 라이브러리 위험을 확인</li>
            <li>CI를 멈추지 않고 <b>리뷰 흐름 안에서 보안을 점검</b>하는 가벼운 방식을 만들었습니다</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- ---------- OTHER PROJECTS ---------- -->
    <section class="view-panel" id="more">
      <p class="kicker">더 보기</p>
      <h2 class="view-title">그 외 작업</h2>
      <div class="archive">
        <div class="arch-card">
          <div class="top"><span class="folder">🦺</span><a class="ext" href="https://github.com/rad1092/minipr1_7" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/minipr1_7" target="_blank">건설현장 PPE 안전장구 감지</a></h4>
          <p>사진과 동영상, 웹캠에서 작업자의 안전헬멧과 안전조끼 착용 여부를 감지하는 앱으로, 사람 박스 기준 후처리로 오탐을 줄이고 작업자별 착용 상태를 추적합니다</p>
          <div class="tags"><span>Python</span><span>YOLO</span><span>Gradio</span><span>OpenCV</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">📈</span><a class="ext" href="https://github.com/rad1092/sec-alert-selfhosted" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/sec-alert-selfhosted" target="_blank">SEC 공시 알림 인박스</a></h4>
          <p>관심 종목의 미국 SEC 공시(8-K, Form 4)를 감시해 플래그 사유와 함께 보여주고, Slack과 웹훅, 메일로 신호를 전달하는 셀프호스팅 도구입니다</p>
          <div class="tags"><span>Python</span><span>SQLite</span><span>Docker</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">🪞</span><a class="ext" href="https://github.com/rad1092/smart-mirror-pc123" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/smart-mirror-pc123" target="_blank">스마트 미러 AIoT 운동 코칭</a></h4>
          <p>화면과 비전 게이트웨이, AI 코칭 엔진을 한 저장소로 묶은 통합본으로, 자세 분석과 운동 루틴 생성, 실시간 코칭을 연결합니다</p>
          <div class="tags"><span>Python</span><span>WebSocket</span><span>SQLite</span><span>AIoT</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">🔌</span><a class="ext" href="https://github.com/rad1092/firstcall-api-lookup-mcp" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/firstcall-api-lookup-mcp" target="_blank">FirstCall API Lookup MCP</a></h4>
          <p>FirstCall로 만든 읽기 전용 MCP 서버로, 공개 사용자 정보를 조회하는 툴 하나를 AI 에이전트가 바로 쓸 수 있게 제공합니다</p>
          <div class="tags"><span>TypeScript</span><span>MCP</span><span>Node</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">🧭</span><a class="ext" href="https://github.com/rad1092/job-coach-agent" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/job-coach-agent" target="_blank">취업 코치형 에이전트</a></h4>
          <p>희망 직무를 입력하면 채용 공고 탐색부터 분석 리포트와 자소서 초안, 면접 대비, 합격 로드맵까지 한 흐름으로 정리합니다</p>
          <div class="tags"><span>Streamlit</span><span>FastAPI</span><span>SQLite</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">⌨️</span><a class="ext" href="https://github.com/rad1092/ascii-diagram-editor" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/ascii-diagram-editor" target="_blank">ASCII 다이어그램 에디터</a></h4>
          <p>브라우저에서 동작하는 ASCII 다이어그램 에디터로, 고정 격자 위에서 그린 결과를 실제 텍스트로 렌더링합니다</p>
          <div class="tags"><span>TypeScript</span><span>Vite</span><span>Client-side</span></div>
        </div>
      </div>
      <p class="lead" style="margin-top:20px;font-size:.92rem;">전체 저장소는 <a href="/repositories/" style="color:var(--accent);">저장소 목록 페이지</a>에서 볼 수 있습니다</p>
    </section>

    <!-- ---------- CONTACT ---------- -->
    <section class="view-panel" id="contact">
      <p class="kicker">연락</p>
      <h2 class="view-title">함께 일해요</h2>
      <p class="lead">새로운 협업이나 프로젝트 제안은 언제든 환영하니 편하게 연락 주세요</p>
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
    document.querySelectorAll('.nav-link').forEach(function (b) { b.classList.toggle('active', b.getAttribute('href') === '#' + v); });
    window.scrollTo(0, 0);
  }
  window.addEventListener('hashchange', showView);
  showView();
})();
</script>

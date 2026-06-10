---
layout: default
permalink: /en/
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

html { scroll-behavior: smooth; }
body { background: var(--bg); }
.pf { color: var(--text); font-family: "Pretendard", -apple-system, BlinkMacSystemFont, "Segoe UI", "Apple SD Gothic Neo", sans-serif; line-height: 1.7; -webkit-font-smoothing: antialiased; word-break: keep-all; overflow-wrap: break-word; }
.pf a { color: var(--text); text-decoration: none; }
.pf a:hover { color: var(--accent); }
.pf .mono { font-family: "Space Grotesk", ui-monospace, monospace; }
.pf ::selection { background: var(--accent); color: var(--accent-ink); }
.pf a:focus-visible { outline: 2px solid var(--accent); outline-offset: 3px; border-radius: 4px; }

/* subtle background grid */
.pf::before { content: ""; position: fixed; inset: 0; z-index: 0; pointer-events: none;
  background-image: linear-gradient(to right, rgba(24,24,40,.031) 1px, transparent 1px),
                    linear-gradient(to bottom, rgba(24,24,40,.031) 1px, transparent 1px);
  background-size: 78px 78px; }

/* cursor spotlight (desktop only) */
.glow { position: fixed; inset: 0; z-index: 0; pointer-events: none; }
@media (pointer: fine) {
  .glow { background: radial-gradient(560px circle at var(--mx, 60%) var(--my, 20%), rgba(47,86,230,.05), transparent 70%); }
}

/* ===== Shell: fixed identity column + scrolling flow ===== */
.shell { display: flex; max-width: 1340px; margin: 0 auto; position: relative; z-index: 1; gap: 36px; }

.id { position: sticky; top: 0; align-self: flex-start; height: 100vh; flex: 0 0 340px;
  padding: 76px 24px 56px 48px; display: flex; flex-direction: column; }
.id-photo { width: 148px; height: 148px; border-radius: 50%; object-fit: cover; border: 1px solid var(--line);
  box-shadow: 0 18px 50px rgba(24,24,27,.14); outline: 1px solid color-mix(in srgb, var(--accent) 32%, transparent); outline-offset: 10px; }
.id-name { font-family: var(--display); font-size: 2.4rem; font-weight: 600; letter-spacing: -.015em; line-height: 1.1; margin: 32px 0 0; }
.id-name small { display: block; font-family: var(--serif); font-size: .76rem; font-weight: 500; color: var(--muted); margin-top: 9px; letter-spacing: .12em; text-transform: uppercase; }
.id-role { color: var(--muted); font-size: .95rem; margin: 16px 0 0; max-width: 235px; }

.snav { margin-top: 44px; display: flex; flex-direction: column; gap: 2px; }
.snav a { display: flex; align-items: center; gap: 12px; padding: 8px 0; font-family: var(--serif); font-size: .75rem; letter-spacing: .12em; text-transform: uppercase; color: var(--muted); transition: color .18s; }
.snav a::before { content: ""; width: 26px; height: 1px; background: var(--line); flex: 0 0 auto; transition: width .2s, background .2s; }
.snav a:hover { color: var(--text); }
.snav a:hover::before { width: 44px; background: var(--text); }
.snav a.active { color: var(--accent); }
.snav a.active::before { width: 44px; background: var(--accent); }
.snav a em { font-style: normal; color: var(--accent); font-size: .66rem; }

.id-foot { margin-top: auto; display: flex; flex-wrap: wrap; gap: 8px 18px; font-size: .84rem; }
.id-foot a { color: var(--muted); }
.id-foot a:hover { color: var(--accent); }

.flow { flex: 1; min-width: 0; padding: 76px 56px 110px 0; }

/* sections in flow */
.block { position: relative; padding: 84px 0; border-top: 1px solid var(--line); scroll-margin-top: 0; }
.block:first-child { border-top: none; padding-top: 0; }
#about { display: flex; flex-direction: column; justify-content: center; min-height: min(640px, calc(100vh - 200px)); }

/* reveal on scroll (only when JS is on) */
.pf.js .block { opacity: 0; transform: translateY(18px); transition: opacity .6s ease, transform .6s cubic-bezier(.22,1,.36,1); }
.pf.js .block.in { opacity: 1; transform: none; }

.kicker { font-family: var(--serif); font-size: .78rem; color: var(--accent); letter-spacing: .14em; text-transform: uppercase; margin: 0 0 14px; display: flex; align-items: center; gap: 12px; }
.kicker::before { content: ""; width: 28px; height: 1px; background: var(--accent); flex: 0 0 auto; }
.view-title { font-family: var(--display); font-size: 2.7rem; font-weight: 600; letter-spacing: -.01em; line-height: 1.12; margin: 0 0 26px; text-wrap: balance; }
.lead { color: var(--muted); font-size: 1.08rem; max-width: 68ch; }
.lead .hl { color: var(--text); }
.pno { position: absolute; top: 56px; right: 0; font-family: var(--display); font-size: 8.5rem; font-weight: 600; line-height: 1; letter-spacing: -.04em; color: color-mix(in srgb, var(--accent) 7%, transparent); pointer-events: none; user-select: none; }

/* about */
.about-head { font-family: var(--display); font-size: 3rem; font-weight: 600; letter-spacing: -.015em; line-height: 1.16; margin: 0 0 28px; text-wrap: balance; }
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

/* project blocks */
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

/* case-study narrative */
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
.arch-card { border: 1px solid var(--line); border-radius: 14px; padding: 24px; background: var(--card); transition: transform .2s, border-color .2s, background .2s, box-shadow .2s; }
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
.contact-big { margin-top: 26px; display: flex; flex-wrap: wrap; gap: 14px; }
.contact-big a { display: inline-block; padding: 14px 30px; border-radius: 999px; background: var(--accent); color: var(--accent-ink); font-weight: 600; transition: transform .18s, box-shadow .18s, filter .18s; }
.contact-big a:hover { color: var(--accent-ink); filter: brightness(1.05); transform: translateY(-2px); box-shadow: 0 12px 30px color-mix(in srgb, var(--accent) 35%, transparent); }
.contact-big a.ghost { background: transparent; color: var(--text); border: 1px solid var(--line); font-weight: 500; }
.contact-big a.ghost:hover { color: var(--accent); border-color: var(--accent); box-shadow: none; filter: none; }
.foot { color: var(--muted); font-size: .82rem; margin-top: 56px; }

@media (max-width: 920px) {
  .shell { flex-direction: column; gap: 0; }
  .id { position: relative; height: auto; flex-basis: auto; padding: 44px 22px 0; }
  .id-photo { width: 96px; height: 96px; outline-offset: 7px; }
  .id-name { font-size: 1.75rem; margin-top: 20px; }
  .snav { flex-direction: row; flex-wrap: wrap; gap: 4px 18px; margin-top: 26px; }
  .snav a::before { width: 14px; }
  .snav a:hover::before, .snav a.active::before { width: 24px; }
  .id-foot { margin-top: 22px; }
  .flow { padding: 24px 22px 80px; }
  .block { padding: 56px 0; scroll-margin-top: 12px; }
  #about { min-height: 0; }
  .about-head { font-size: 2rem; }
  .view-title { font-size: 1.9rem; }
  .gallery.cols-2 { grid-template-columns: 1fr; }
  .archive { grid-template-columns: 1fr; }
  .pno { display: none; }
}

@media (prefers-reduced-motion: reduce) {
  html { scroll-behavior: auto; }
  .pf *, .pf *::before, .pf *::after { animation: none !important; transition: none !important; }
  .pf.js .block { opacity: 1; transform: none; }
}
</style>

<div class="pf" id="pf" markdown="0">
<div class="glow" id="glow"></div>
<div class="shell">

  <!-- ================= IDENTITY (fixed) ================= -->
  <aside class="id">
    <img class="id-photo" src="/profile.png" alt="HongDae Kim">
    <h1 class="id-name">HongDae Kim<small>김홍대</small></h1>
    <p class="id-role">I build software that helps people take their next step</p>
    <nav class="snav">
      <a class="active" href="#about">About</a>
      <a href="#experience">Experience</a>
      <a href="#p1"><em>01</em>Disaster Dashboard</a>
      <a href="#p2"><em>02</em>FirstCall</a>
      <a href="#p3"><em>03</em>gh-dep-risk</a>
      <a href="#more">Other</a>
      <a href="#contact">Contact</a>
    </nav>
    <div class="id-foot">
      <a href="https://github.com/rad1092" target="_blank">GitHub ↗</a>
      <a href="mailto:rad174951@gmail.com">Email</a>
      <a href="/">KR</a>
    </div>
  </aside>

  <!-- ================= FLOW ================= -->
  <main class="flow">

    <!-- ---------- ABOUT ---------- -->
    <section class="block" id="about">
      <p class="kicker">01 — About</p>
      <h2 class="about-head">After years in field sales and delivery, I build software that helps people take their <span class="hl">next step</span>.</h2>
      <p class="lead">
        I started from small learning repositories and grew step by step toward real, usable tools.
        Guided by the idea of <span class="hl">"going beyond delivering information to driving action,"</span>
        I focus on software — disaster evacuation guidance, API tooling, dependency-risk checks — that helps users act.
      </p>
      <div class="chips">
        <span class="chip"><b>Python</b> Streamlit, Pandas, Folium</span>
        <span class="chip"><b>Rust</b> egui/eframe</span>
        <span class="chip"><b>Go</b> GitHub CLI</span>
        <span class="chip"><b>DevOps</b> GitHub Actions</span>
        <span class="chip"><b>AI</b> MCP, agent tooling</span>
      </div>
      <div class="cta">
        <a class="primary" href="#p1">View Projects ↓</a>
        <a href="#experience">Experience</a>
      </div>
    </section>

    <!-- ---------- EXPERIENCE ---------- -->
    <section class="block" id="experience">
      <p class="kicker">02 — Experience &amp; Background</p>
      <h2 class="view-title">Experience &amp; Background</h2>
      <div class="timeline">
        <div class="tl-item">
          <div class="tl-when">2016.07 – 2017.07, 2022.04 – 2025.04 — ~4 years total</div>
          <div class="tl-role">Sales Management, Materials Delivery <span class="org">— Hyosang Safety Trading</span></div>
          <p class="tl-desc">At a company supplying materials and safety equipment to construction sites, I started in materials delivery and grew into sales management over about four years. I handled clients directly, coordinated schedules, inventory and deadlines, and turned on-site needs into process and data.</p>
          <ul class="tl-detail">
            <li><b>2022.04 – 2025.04</b> Sales management + materials delivery — client sales management, schedule and inventory coordination, direct customer handling</li>
            <li><b>2016.07 – 2017.07</b> Materials delivery — on-site construction materials delivery</li>
          </ul>
        </div>
        <div class="tl-item">
          <div class="tl-when">2017.07 – 2018.07</div>
          <div class="tl-role">Exchange Student (language study) <span class="org">— UNAM CEPE, National Autonomous University of Mexico</span></div>
          <p class="tl-desc">Spent a year as an exchange student at UNAM's Centre for Teaching Foreigners (CEPE) studying Spanish and Mexican culture — learning to adapt quickly and communicate across languages and cultures.</p>
        </div>
      </div>

      <div class="certs-title">Licenses &amp; Certifications</div>
      <div class="certs">
        <span class="cert">🚜 Excavator Operation</span>
        <span class="cert">🏗️ Forklift Operation</span>
        <span class="cert">🚛 Class 1 Large Vehicle License</span>
      </div>
    </section>

    <!-- ---------- PROJECT 1 : Disaster Dashboard ---------- -->
    <section class="block" id="p1">
      <span class="pno" aria-hidden="true">01</span>
      <p class="kicker">Featured Project 01</p>
      <div class="proj-head">
        <div>
          <h2 class="view-title" style="margin-bottom:0;">Real-time Disaster Evacuation Dashboard</h2>
          <code class="repo">rad1092/project_dashboard</code>
          <div><span class="role-tag">4-person team — Backend / Architecture lead</span></div>
        </div>
        <div class="proj-links"><a href="https://github.com/rad1092/project_dashboard" target="_blank">GitHub ↗</a></div>
      </div>
      <div class="stack"><span>Python</span><span>Streamlit</span><span>Pandas</span><span>Folium</span><span>OSRM</span><span>Selenium</span><span>SQLite</span><span>pytest</span></div>

      <p class="summary">A disaster alert tells you <b>"that"</b> something happened — I built a dashboard that answers "where and how do I evacuate <b>right now</b>."</p>

      <div class="metrics">
        <div class="metric"><b>4-person</b><span>team, backend / architecture lead</span></div>
        <div class="metric"><b>4</b><span>multi-page app</span></div>
        <div class="metric"><b>5</b><span>regions supported (Yeongnam)</span></div>
      </div>

      <div class="media">
        <div class="gallery cols-2">
          <figure><img src="/assets/projects/dashboard-demo-1-landing.png" alt="Landing" loading="lazy"><figcaption>① Real-time guidance — waiting for disaster alerts</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-2-default.png" alt="No alert" loading="lazy"><figcaption>② No alert — default state by location (Ulsan Buk-gu)</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-3-shelter.png" alt="Shelter list" loading="lazy"><figcaption>③ Alert (home) — map + recommended shelter list</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-4-route.png" alt="Route" loading="lazy"><figcaption>④ Alert (high-wind advisory) — walking safe-route guidance</figcaption></figure>
        </div>
      </div>

      <div class="ai-note"><span class="badge">AI</span><span>Much of the stack was new to me, so I <b>leaned on AI tools to ramp up implementation quickly.</b> This is where I built the practical muscle of learning a new tool on the job and driving it with AI as a partner.</span></div>

      <div class="case">
        <div class="case-block flush">
          <h3 class="case-h">The problem</h3>
          <p>A disaster alert only says something happened; shelter and alert data were scattered, making it <b>hard to decide quickly</b> in a crisis. Because the service combines static public data, real-time alerts, user location and an external routing API, the real challenge wasn't visualization but a <b>structure that loads data reliably, recommends shelters, and finds routes without breaking</b>.</p>
        </div>
        <div class="case-block">
          <h3 class="case-h">My role — <span class="sub">4-person team, backend / architecture</span></h3>
          <ul>
            <li>Owned the <b>overall dashboard architecture</b></li>
            <li>Designed and built data-path management, CSV validation and normalization, real-time alert handling, the <b>shelter recommendation logic</b>, and OSRM routing with <b>failure fallback</b></li>
            <li>Led core feature work including <b>map visualization and the test setup</b></li>
          </ul>
        </div>
        <div class="case-block">
          <h3 class="case-h">What I did</h3>
          <ul>
            <li><b>Resilient data loading</b> — a layer searching environment variables → Streamlit secrets → repo default paths in order, handling Korean CSV encoding and required-column validation</li>
            <li><b>Recommendation engine</b> — disaster-type-specific shelter priority → region-level fallback → Haversine distance → capacity-based sorting</li>
            <li><b>Real-time and mock data</b> — a Selenium crawler collects alerts and converts them to the app's standard schema; a <b>mock-alert generator</b> covers cases where crawling isn't possible</li>
            <li><b>Route guidance</b> — OSRM walking routes, with an automatic <b>straight-line fallback</b> when the API fails</li>
            <li><b>Structure and testing</b> — a consistent Streamlit multi-page app (Home, Simulation, Real-time, Analysis) with a Folium map showing location, shelters and route together; <code class="mono">pytest</code> validates routing, session state and page imports</li>
          </ul>
        </div>
        <div class="case-block">
          <h3 class="case-h">Result</h3>
          <ul>
            <li>Users get <b>shelter recommendations matched to disaster type and location</b>, and the flow <b>keeps working via fallback routes and mock data</b> even when the external API or live crawling fails</li>
            <li>It grew from a simple Streamlit visualization into a structure covering <b>data processing, recommendation, real-time collection and failure handling</b></li>
            <li>A <b>working dashboard</b> with Folium, OSRM and Streamlit actually wired together — new tools learned fast and applied in practice</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- ---------- PROJECT 2 : FirstCall ---------- -->
    <section class="block" id="p2">
      <span class="pno" aria-hidden="true">02</span>
      <p class="kicker">Featured Project 02</p>
      <div class="proj-head">
        <div>
          <h2 class="view-title" style="margin-bottom:0;">Local-first API Workbench · FirstCall</h2>
          <code class="repo">rad1092/firstcall-local-api-workbench</code>
          <div><span class="role-tag">Solo project · v0.1.0 release — Windows, macOS, Linux</span></div>
        </div>
        <div class="proj-links">
          <a href="https://github.com/rad1092/firstcall-local-api-workbench" target="_blank">GitHub ↗</a>
          <a href="https://github.com/rad1092/firstcall-local-api-workbench/releases" target="_blank">Releases ↗</a>
        </div>
      </div>
      <div class="stack"><span>Rust 2024</span><span>egui / eframe</span><span>firstcall-cli</span><span>GitHub Actions</span></div>

      <p class="summary">A tool that lets you <b>verify API calls on your own machine</b> and keep them in a safe, reusable form.</p>

      <div class="metrics">
        <div class="metric"><b>8</b><span>input formats (curl, OpenAPI, Postman…)</span></div>
        <div class="metric"><b>2</b><span>surfaces — desktop GUI, CLI</span></div>
        <div class="metric"><b>3</b><span>OS releases (Windows, macOS, Linux)</span></div>
      </div>

      <div class="media">
        <div class="gallery cols-2">
          <figure><img src="/assets/projects/firstcall-gui-workbench.gif" alt="FirstCall desktop GUI demo" loading="lazy"><figcaption>Desktop app — importing, verifying and organizing requests</figcaption></figure>
          <figure><img src="/assets/projects/firstcall-cli-demo.gif" alt="FirstCall CLI demo" loading="lazy"><figcaption>Command-line tool — actual run output</figcaption></figure>
        </div>
      </div>

      <div class="ai-note"><span class="badge">AI</span><span>I used <b>Claude as a pair-programming partner</b> for the Rust core, handling many input formats, tests and docs. I decided <em>what</em> to build and which rules to hold; AI sped up the repetitive implementation and edge-case checking.</span></div>

      <div class="case">
        <div class="case-block flush">
          <h3 class="case-h">The problem</h3>
          <p>API requests differ in address, auth key and format every time, so there was no good way to <b>collect them in a reusable, safe form</b>. Handing APIs to AI agents or automation risked <b>exposing auth keys</b> or mixing in <b>unverified requests</b> — and there was a security need to <b>keep requests on my own machine</b> rather than a cloud.</p>
        </div>
        <div class="case-block">
          <h3 class="case-h">My role — <span class="sub">solo project, design to release</span></h3>
          <ul>
            <li>Designed a flow to accept <b>differently formatted requests</b> (curl, OpenAPI, Postman) and verify them locally</li>
            <li>Defined saving only verified requests as <b>reusable "recipes"</b> and exporting them with secrets stripped</li>
            <li>Provided both a <b>GUI</b> for people and a <b>CLI</b> for automation on one shared core</li>
          </ul>
        </div>
        <div class="case-block">
          <h3 class="case-h">What I did</h3>
          <ul>
            <li>Built the core in Rust, then two ways to use it — a <b>desktop app</b> you click through, and an automation <b>command-line tool (firstcall-cli)</b></li>
            <li>Locked in a <b>safe flow</b>: import → verify → save as recipe → strip secrets and export → re-verify</li>
            <li>Made sure <b>scripts and config files inside imported requests are never executed</b>, blocking malicious code (supply-chain safety)</li>
            <li>Handled secrets via environment variables only, with automated tests and security checks running <b>on every release</b> via GitHub Actions</li>
          </ul>
        </div>
        <div class="case-block">
          <h3 class="case-h">Result</h3>
          <ul>
            <li>Shipped a <b>v0.1.0 release</b> with both the app and CLI, for Windows, macOS and Linux</li>
            <li>The CLI also outputs results in a <b>machine-readable format (JSON)</b>, wiring straight into automation / AI pipelines</li>
            <li>The <b>tool itself enforces</b> "only verified, secret-free requests leave the machine"</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- ---------- PROJECT 3 : gh-dep-risk ---------- -->
    <section class="block" id="p3">
      <span class="pno" aria-hidden="true">03</span>
      <p class="kicker">Featured Project 03</p>
      <div class="proj-head">
        <div>
          <h2 class="view-title" style="margin-bottom:0;">PR Dependency Risk Check · gh-dep-risk</h2>
          <code class="repo">rad1092/gh-dependency-risk</code>
          <div><span class="role-tag">Solo project · v0.2.0 release</span></div>
        </div>
        <div class="proj-links"><a href="https://github.com/rad1092/gh-dependency-risk" target="_blank">GitHub ↗</a></div>
      </div>
      <div class="stack"><span>Go</span><span>GitHub CLI Extension</span><span>Dependency Review API</span><span>GitHub Actions</span></div>

      <p class="summary">A tool that lets a reviewer check, with one command, whether <b>newly added third-party libraries in a PR are a security risk</b>.</p>

      <div class="metrics">
        <div class="metric"><b>11</b><span>ecosystems checked (npm, pip, Go, Maven…)</span></div>
        <div class="metric"><b>1</b><span>install = a single command</span></div>
        <div class="metric"><b>0</b><span>servers, DB, standing infra</span></div>
      </div>

      <div class="media">
        <div class="gallery one">
          <figure><img src="/assets/projects/gh-dependency-risk-demo.gif" alt="gh-dep-risk terminal demo" loading="lazy"><figcaption>Terminal demo — checking PR dependencies and summarizing</figcaption></figure>
        </div>
      </div>

      <div class="ai-note"><span class="badge">AI</span><span>I used AI to organize the <b>different ways each tool records its libraries</b> (npm, pip, Go…) and to cover edge cases with tests quickly. I personally decided the scope — what to support and what to explicitly leave out.</span></div>

      <div class="case">
        <div class="case-block flush">
          <h3 class="case-h">The problem</h3>
          <p>Modern software pulls in <b>dozens or hundreds of external libraries</b>, and if one has a vulnerability the whole thing is at risk. Reviewers struggled to <b>gauge that risk during code review</b>, yet running an <b>always-on server / database</b> was too heavy for small teams.</p>
        </div>
        <div class="case-block">
          <h3 class="case-h">My role — <span class="sub">solo project, design to release</span></h3>
          <ul>
            <li>Aimed for a lightweight tool reviewers <b>run only when needed</b>, with no setup or upkeep</li>
            <li>Designed it to reuse the GitHub login they already have so it <b>runs immediately</b></li>
            <li>Decided to help the reviewer judge <b>without failing CI</b></li>
          </ul>
        </div>
        <div class="case-block">
          <h3 class="case-h">What I did</h3>
          <ul>
            <li>Built it as a <b>GitHub CLI extension (one small binary)</b> instead of a server — installation is a single line</li>
            <li>Uses <b>GitHub's official security data first</b>, switching to a <b>local fallback</b> that reads project files only when the API isn't available</li>
            <li><b>Scoped support explicitly</b> (npm, pip, Go and more), documenting what's covered so over-analysis never produces wrong results</li>
            <li>Posts results as a <b>clean PR comment</b> (updated, not duplicated), verified with automated tests plus <b>live smoke tests against real fixture PRs</b> across npm, pnpm and Yarn</li>
          </ul>
        </div>
        <div class="case-block">
          <h3 class="case-h">Result</h3>
          <ul>
            <li>Installable in one line: <code class="mono">gh extension install rad1092/gh-dep-risk</code></li>
            <li>Checks library risk across <b>11 ecosystems</b> (npm, pip, Go, Maven and more)</li>
            <li>A lightweight way to <b>review security inside the code-review flow</b>, without stopping CI</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- ---------- OTHER PROJECTS ---------- -->
    <section class="block" id="more">
      <p class="kicker">More</p>
      <h2 class="view-title">Other Work</h2>
      <div class="archive">
        <div class="arch-card">
          <div class="top"><span class="folder">🦺</span><a class="ext" href="https://github.com/rad1092/minipr1_7" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/minipr1_7" target="_blank">Construction-Site PPE Detection</a></h4>
          <p>Detects hardhats and safety vests on workers in photos, video and webcam feeds — person-box-based post-processing cuts false positives and tracks per-worker status</p>
          <div class="tags"><span>Python</span><span>YOLO</span><span>Gradio</span><span>OpenCV</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">📈</span><a class="ext" href="https://github.com/rad1092/sec-alert-selfhosted" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/sec-alert-selfhosted" target="_blank">SEC Filing Alert Inbox</a></h4>
          <p>Watches US SEC filings (8-K, Form 4) for a focused watchlist, shows why each one was flagged, and routes signals to Slack, webhooks or email — fully self-hosted</p>
          <div class="tags"><span>Python</span><span>SQLite</span><span>Docker</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">🪞</span><a class="ext" href="https://github.com/rad1092/smart-mirror-pc123" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/smart-mirror-pc123" target="_blank">Smart Mirror AIoT Workout Coaching</a></h4>
          <p>An integrated repo wiring a display, a vision gateway and an AI coaching engine — connecting pose analysis, routine generation and real-time coaching</p>
          <div class="tags"><span>Python</span><span>WebSocket</span><span>SQLite</span><span>AIoT</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">🔌</span><a class="ext" href="https://github.com/rad1092/firstcall-api-lookup-mcp" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/firstcall-api-lookup-mcp" target="_blank">FirstCall API Lookup MCP</a></h4>
          <p>A read-only MCP server generated from FirstCall, exposing a single public-user-lookup tool an AI agent can use right away</p>
          <div class="tags"><span>TypeScript</span><span>MCP</span><span>Node</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">🧭</span><a class="ext" href="https://github.com/rad1092/job-coach-agent" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/job-coach-agent" target="_blank">Job-Coach Agent</a></h4>
          <p>Enter a target role and it runs the whole flow — job search, analysis report, cover-letter draft, interview prep, and a roadmap to landing the job</p>
          <div class="tags"><span>Streamlit</span><span>FastAPI</span><span>SQLite</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">⌨️</span><a class="ext" href="https://github.com/rad1092/ascii-diagram-editor" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/ascii-diagram-editor" target="_blank">ASCII Diagram Editor</a></h4>
          <p>A browser-based ASCII diagram editor — draw on a fixed grid and render the result into real text</p>
          <div class="tags"><span>TypeScript</span><span>Vite</span><span>Client-side</span></div>
        </div>
      </div>
      <p class="lead" style="margin-top:20px;font-size:.92rem;">See everything on the <a href="/repositories-en/" style="color:var(--accent);">repositories page</a></p>
    </section>

    <!-- ---------- CONTACT ---------- -->
    <section class="block" id="contact">
      <p class="kicker">Contact</p>
      <h2 class="view-title">Let's work together</h2>
      <p class="lead">I'm always open to new collaborations and project ideas — feel free to reach out</p>
      <div class="contact-big">
        <a href="mailto:rad174951@gmail.com">Send an email →</a>
        <a class="ghost" href="https://github.com/rad1092" target="_blank">GitHub @rad1092 ↗</a>
      </div>
      <p class="foot">Built with Jekyll · Designed &amp; developed by HongDae Kim — with a little help from AI</p>
    </section>

  </main>
</div>
</div>

<script>
(function () {
  var pf = document.getElementById('pf');
  pf.classList.add('js');

  var sections = document.querySelectorAll('.flow section[id]');
  var links = document.querySelectorAll('.snav a');

  function setActive(id) {
    links.forEach(function (l) { l.classList.toggle('active', l.getAttribute('href') === '#' + id); });
  }

  if ('IntersectionObserver' in window) {
    var spy = new IntersectionObserver(function (entries) {
      entries.forEach(function (e) { if (e.isIntersecting) setActive(e.target.id); });
    }, { rootMargin: '-30% 0px -60% 0px' });
    sections.forEach(function (s) { spy.observe(s); });

    var reveal = new IntersectionObserver(function (entries) {
      entries.forEach(function (e) {
        if (e.isIntersecting) { e.target.classList.add('in'); reveal.unobserve(e.target); }
      });
    }, { rootMargin: '0px 0px -8% 0px' });
    sections.forEach(function (s) { reveal.observe(s); });
  } else {
    sections.forEach(function (s) { s.classList.add('in'); });
  }

  var glow = document.getElementById('glow');
  if (glow && window.matchMedia('(pointer: fine)').matches) {
    window.addEventListener('mousemove', function (ev) {
      glow.style.setProperty('--mx', ev.clientX + 'px');
      glow.style.setProperty('--my', ev.clientY + 'px');
    }, { passive: true });
  }
})();
</script>

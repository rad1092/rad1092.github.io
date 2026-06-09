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

body { background: var(--bg); }
.pf { color: var(--text); font-family: "Pretendard", -apple-system, BlinkMacSystemFont, "Segoe UI", "Apple SD Gothic Neo", sans-serif; line-height: 1.7; -webkit-font-smoothing: antialiased; }
.pf a { color: var(--text); text-decoration: none; }
.pf a:hover { color: var(--accent); }
.pf .mono { font-family: "Space Grotesk", ui-monospace, monospace; }

.app { display: flex; align-items: flex-start; max-width: 1340px; margin: 0 auto; }

.rail { position: sticky; top: 0; align-self: flex-start; height: 100vh; flex: 0 0 256px;
  padding: 54px 30px 40px 44px; display: flex; flex-direction: column; }
.rail-name { font-family: var(--display); font-size: 1.8rem; font-weight: 600; letter-spacing: -.01em; line-height: 1.15; }
.rail-name small { display: block; font-size: .82rem; font-weight: 500; color: var(--muted); margin-top: 4px; letter-spacing: 0; }
.rail-role { color: var(--muted); font-size: .9rem; margin-top: 14px; max-width: 200px; }

.rail-nav { margin-top: 42px; display: flex; flex-direction: column; gap: 4px; }
.rail-link { display: flex; align-items: center; gap: 14px; padding: 7px 0; color: var(--muted);
  font-family: var(--serif); font-size: .76rem; letter-spacing: .12em; text-transform: uppercase; transition: .2s; }
.rail-link .bar { width: 26px; height: 1px; background: var(--line); transition: .2s; }
.rail-link:hover { color: var(--text); }
.rail-link:hover .bar { width: 44px; background: var(--text); }
.rail-link.active { color: var(--accent); }
.rail-link.active .bar { width: 48px; background: var(--accent); }

.rail-foot { margin-top: auto; display: flex; gap: 18px; font-size: .82rem; }
.rail-foot a { color: var(--muted); }
.rail-foot a:hover { color: var(--accent); }

.view { flex: 1; min-width: 0; padding: 64px 64px 110px; }
.view-panel { display: none; animation: fade .35s ease; }
.view-panel.active { display: block; }
@keyframes fade { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: none; } }

.kicker { font-family: var(--serif); font-size: .78rem; color: var(--accent); letter-spacing: .14em; text-transform: uppercase; margin: 0 0 14px; }
.view-title { font-family: var(--display); font-size: 2.6rem; font-weight: 600; letter-spacing: -.01em; line-height: 1.12; margin: 0 0 26px; }
.lead { color: var(--muted); font-size: 1.06rem; max-width: 70ch; }
.lead .hl { color: var(--text); }

.about-hero { display: flex; gap: 52px; align-items: center; flex-wrap: wrap-reverse; }
.about-text { flex: 1; min-width: 300px; }
.about-photo { flex: 0 0 auto; width: 230px; height: 230px; border-radius: 50%; object-fit: cover; border: 1px solid var(--line); box-shadow: 0 18px 50px rgba(24,24,27,.14); }
.about-head { font-family: var(--display); font-size: 2.9rem; font-weight: 600; letter-spacing: -.015em; line-height: 1.18; max-width: 20ch; margin: 0 0 28px; }
.about-head .hl { color: var(--accent); }
.chips { display: flex; flex-wrap: wrap; gap: 9px; margin-top: 26px; }
.chip { border: 1px solid var(--line); color: var(--text); padding: 7px 14px; border-radius: 999px; font-size: .84rem; }
.chip b { color: var(--accent); font-weight: 600; }
.cta { margin-top: 34px; }
.cta a { display: inline-block; margin: 0 12px 12px 0; padding: 12px 22px; border-radius: 999px; border: 1px solid var(--line); color: var(--text); font-size: .92rem; font-weight: 500; transition: .15s; }
.cta a:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }
.cta a.primary { background: var(--accent); color: var(--accent-ink); border-color: var(--accent); font-weight: 600; }
.cta a.primary:hover { color: var(--accent-ink); filter: brightness(1.05); }

.timeline { position: relative; padding-left: 28px; max-width: 880px; }
.timeline::before { content: ""; position: absolute; left: 5px; top: 8px; bottom: 8px; width: 1px; background: var(--line); }
.tl-item { position: relative; padding: 0 0 34px; }
.tl-item:last-child { padding-bottom: 0; }
.tl-item::before { content: ""; position: absolute; left: -28px; top: 6px; width: 11px; height: 11px; border-radius: 50%; background: var(--bg); border: 2px solid var(--accent); }
.tl-when { font-family: var(--serif); font-size: .8rem; color: var(--accent); letter-spacing: .04em; }
.tl-role { font-family: var(--display); font-size: 1.3rem; font-weight: 600; margin: 5px 0 3px; letter-spacing: -.01em; }
.tl-role .org { color: var(--muted); font-weight: 400; font-size: .92rem; }
.tl-desc { color: var(--muted); margin: 6px 0 0; }
.tl-detail { margin: 14px 0 0; padding-left: 20px; color: var(--muted); }
.tl-detail li { margin-bottom: 9px; }
.tl-detail b { color: var(--accent); font-family: var(--serif); font-size: .82rem; letter-spacing: .02em; }
.certs-title { font-family: var(--serif); font-size: .76rem; color: var(--muted); letter-spacing: .12em; margin: 46px 0 14px; text-transform: uppercase; }
.certs { display: flex; flex-wrap: wrap; gap: 10px; }
.cert { border: 1px solid var(--line); border-radius: 10px; padding: 9px 15px; font-size: .94rem; }

.proj-head { display: flex; justify-content: space-between; align-items: flex-start; gap: 20px; flex-wrap: wrap; }
.repo { font-family: var(--serif); font-size: .84rem; color: var(--muted); display: block; margin-top: 8px; letter-spacing: .02em; }
.role-tag { display: inline-block; margin-top: 12px; font-size: .84rem; color: var(--accent); border: 1px solid color-mix(in srgb, var(--accent) 40%, transparent); padding: 4px 12px; border-radius: 999px; }
.proj-links a { font-size: .88rem; margin-left: 16px; white-space: nowrap; color: var(--muted); }
.proj-links a:hover { color: var(--accent); }
.stack { display: flex; flex-wrap: wrap; gap: 9px; margin: 22px 0 26px; }
.stack span { font-family: var(--serif); font-size: .77rem; color: var(--muted); border: 1px solid var(--line); padding: 4px 11px; border-radius: 8px; }

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
.gallery figure { margin: 0; border: 1px solid var(--line); border-radius: 12px; overflow: hidden; background: var(--bg-soft); }
.gallery img { width: 100%; display: block; }
.gallery figcaption { font-size: .8rem; color: var(--muted); padding: 9px 12px; border-top: 1px solid var(--line); }

.tabs { display: flex; gap: 6px; border-bottom: 1px solid var(--line); flex-wrap: wrap; margin-top: 6px; max-width: 820px; }
.tab-btn { background: none; border: none; color: var(--muted); padding: 11px 20px; cursor: pointer; font-size: .95rem; border-bottom: 2px solid transparent; font-family: inherit; }
.tab-btn:hover { color: var(--text); }
.tab-btn.active { color: var(--accent); border-bottom-color: var(--accent); }
.tab-panel { display: none; padding: 22px 2px 4px; animation: fade .25s ease; max-width: 820px; }
.tab-panel.active { display: block; }
.tab-panel ul { margin: 0; padding-left: 20px; }
.tab-panel li { margin-bottom: 11px; }
.tab-panel li b { color: var(--text); }

.archive { display: grid; grid-template-columns: repeat(2, 1fr); gap: 18px; max-width: 920px; }
.arch-card { border: 1px solid var(--line); border-radius: 14px; padding: 24px; transition: transform .2s, border-color .2s, background .2s; }
.arch-card:hover { transform: translateY(-5px); border-color: var(--accent); background: var(--bg-soft); }
.arch-card .top { display: flex; justify-content: space-between; align-items: center; margin-bottom: 16px; }
.arch-card .folder { font-size: 1.5rem; }
.arch-card .ext { color: var(--muted); }
.arch-card .ext:hover { color: var(--accent); }
.arch-card h4 { margin: 0 0 9px; font-size: 1.12rem; font-weight: 700; letter-spacing: -.01em; }
.arch-card h4 a { color: var(--text); }
.arch-card h4 a:hover { color: var(--accent); }
.arch-card p { color: var(--muted); font-size: .92rem; margin: 0 0 16px; }
.arch-card .tags { display: flex; flex-wrap: wrap; gap: 9px; font-family: var(--serif); font-size: .74rem; color: var(--muted); }

.contact-big { margin-top: 22px; }
.contact-big a { display: inline-block; padding: 14px 30px; border-radius: 999px; background: var(--accent); color: var(--accent-ink); font-weight: 600; }
.contact-big a:hover { color: var(--accent-ink); filter: brightness(1.05); }
.foot { color: var(--muted); font-size: .82rem; margin-top: 56px; }

@media (max-width: 900px) {
  .app { flex-direction: column; max-width: none; }
  .rail { position: sticky; top: 0; z-index: 10; height: auto; width: 100%; flex-basis: auto;
    background: rgba(255,255,255,.92); backdrop-filter: blur(8px); border-bottom: 1px solid var(--line);
    padding: 14px 20px; flex-direction: row; align-items: center; gap: 16px; }
  .rail-name { font-size: 1.05rem; }
  .rail-name small, .rail-role { display: none; }
  .rail-nav { margin: 0; flex-direction: row; overflow-x: auto; gap: 2px; flex: 1; }
  .rail-link { white-space: nowrap; padding: 6px 10px; font-size: .72rem; }
  .rail-link .bar { display: none; }
  .rail-foot { margin: 0; }
  .view { padding: 30px 22px 80px; }
  .about-hero { gap: 24px; }
  .about-photo { width: 130px; height: 130px; }
  .about-head { font-size: 2rem; }
  .view-title { font-size: 1.9rem; }
  .gallery.cols-2 { grid-template-columns: 1fr; }
  .archive { grid-template-columns: 1fr; }
}
</style>

<div class="pf" markdown="0">
<div class="app">

  <!-- ================= LEFT RAIL ================= -->
  <aside class="rail">
    <div>
      <div class="rail-name">HongDae Kim<small>김홍대</small></div>
      <p class="rail-role">I build software that helps people take their next step.</p>
      <nav class="rail-nav">
        <a class="rail-link active" href="#about"><span class="bar"></span> About</a>
        <a class="rail-link" href="#experience"><span class="bar"></span> Experience</a>
        <a class="rail-link" href="#p1"><span class="bar"></span> Disaster Dashboard</a>
        <a class="rail-link" href="#p2"><span class="bar"></span> FirstCall</a>
        <a class="rail-link" href="#p3"><span class="bar"></span> gh-dep-risk</a>
        <a class="rail-link" href="#more"><span class="bar"></span> Other Work</a>
        <a class="rail-link" href="#contact"><span class="bar"></span> Contact</a>
      </nav>
    </div>
    <div class="rail-foot">
      <a href="https://github.com/rad1092" target="_blank">GitHub</a>
      <a href="/">KR</a>
    </div>
  </aside>

  <!-- ================= VIEWS ================= -->
  <main class="view">

    <!-- ---------- ABOUT ---------- -->
    <section class="view-panel active" id="about">
      <p class="kicker">01 — About</p>
      <div class="about-hero">
        <div class="about-text">
          <h1 class="about-head">After years in field sales and delivery, I build software that helps people take their <span class="hl">next step</span>.</h1>
          <p class="lead">
            I started from small learning repositories and grew step by step toward real, usable tools.
            Guided by the idea of <span class="hl">"going beyond delivering information to driving action,"</span>
            I focus on software — disaster evacuation guidance, API tooling, dependency-risk checks — that helps users act.
          </p>
        </div>
        <img class="about-photo" src="/profile.png" alt="HongDae Kim">
      </div>
      <div class="chips">
        <span class="chip"><b>Python</b> · Streamlit · Pandas · Folium</span>
        <span class="chip"><b>Rust</b> · egui/eframe</span>
        <span class="chip"><b>Go</b> · GitHub CLI</span>
        <span class="chip"><b>DevOps</b> · GitHub Actions</span>
        <span class="chip"><b>AI</b> · MCP · agent tooling</span>
      </div>
      <div class="cta">
        <a class="primary" href="#p1">View Projects →</a>
        <a href="#experience">Experience</a>
      </div>
    </section>

    <!-- ---------- EXPERIENCE ---------- -->
    <section class="view-panel" id="experience">
      <p class="kicker">02 — Experience &amp; Background</p>
      <h2 class="view-title">Experience &amp; Background</h2>
      <div class="timeline">
        <div class="tl-item">
          <div class="tl-when">2016.07 – 2017.07, 2022.04 – 2025.04 · ~4 years total</div>
          <div class="tl-role">Sales Management · Materials Delivery <span class="org">— Hyosang Safety Trading</span></div>
          <p class="tl-desc">At a company supplying materials and safety equipment to construction sites, I started in materials delivery and grew into sales management over about four years. I handled clients directly, coordinated schedules, inventory and deadlines, and turned on-site needs into process and data.</p>
          <ul class="tl-detail">
            <li><b>2022.04 – 2025.04</b> · Sales management + materials delivery — client sales management, schedule/inventory/deadline coordination, direct customer handling</li>
            <li><b>2016.07 – 2017.07</b> · Materials delivery — on-site construction materials delivery</li>
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
    <section class="view-panel" id="p1">
      <p class="kicker">Featured Project 01</p>
      <div class="proj-head">
        <div>
          <h2 class="view-title" style="margin-bottom:0;">Real-time Disaster Evacuation Dashboard</h2>
          <code class="repo">rad1092/project_dashboard</code>
          <div><span class="role-tag">4-person team · Backend / Architecture lead</span></div>
        </div>
        <div class="proj-links"><a href="https://github.com/rad1092/project_dashboard" target="_blank">GitHub ↗</a></div>
      </div>
      <div class="stack"><span>Python</span><span>Streamlit</span><span>Pandas</span><span>Folium</span><span>OSRM</span><span>Selenium</span><span>SQLite</span><span>pytest</span></div>

      <p class="summary">A disaster alert tells you <b>"that"</b> something happened. I built a dashboard that answers "where and how do I evacuate <b>right now</b>."</p>
      <p class="context">Because the service combines <b>static public data, real-time disaster alerts, user location and an external routing API</b>, the real challenge wasn't visualization but a <b>structure that loads data reliably, recommends shelters, and finds routes without breaking</b>. On a 4-person team I owned the <b>backend and overall architecture</b> — data loading, shelter recommendation, real-time alert handling, route guidance and testing.</p>
      <div class="ai-note"><span class="badge">AI</span><span>Much of the stack was new to me, so I <b>leaned on AI tools to ramp up implementation quickly.</b> This is where I built the practical muscle of learning a new tool on the job and driving it with AI as a partner.</span></div>

      <div class="media">
        <div class="gallery cols-2">
          <figure><img src="/assets/projects/dashboard-demo-1-landing.png" alt="Landing" loading="lazy"><figcaption>① Real-time guidance — waiting for disaster alerts</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-2-default.png" alt="No alert" loading="lazy"><figcaption>② No alert — default state by location (Ulsan Buk-gu)</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-3-shelter.png" alt="Shelter list" loading="lazy"><figcaption>③ Alert (home) — map + recommended shelter list</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-4-route.png" alt="Route" loading="lazy"><figcaption>④ Alert (high-wind advisory) — walking safe-route guidance</figcaption></figure>
        </div>
      </div>

      <div class="tabs" role="tablist">
        <button class="tab-btn active" data-target="p1-s">Situation</button>
        <button class="tab-btn" data-target="p1-t">My role</button>
        <button class="tab-btn" data-target="p1-a">Action</button>
        <button class="tab-btn" data-target="p1-r">Result</button>
      </div>
      <div class="tab-panel active" id="p1-s">
        <ul>
          <li>There was <b>no unified service</b> for Yeongnam-region residents (Daegu·Ulsan·Busan·Gyeongbuk·Gyeongnam) to find shelters and routes during a disaster.</li>
          <li>Alert data and shelter info were scattered, making it <b>hard to decide quickly</b> in a crisis.</li>
          <li>With multiple data sources and runtime environments mixed in, a <b>reliable loading / recommendation / routing structure</b> mattered most.</li>
        </ul>
      </div>
      <div class="tab-panel" id="p1-t">
        <ul>
          <li>Owned the <b>overall dashboard architecture</b> on a 4-person team.</li>
          <li>Designed and built data-path management, CSV validation/normalization, real-time alert handling, the <b>shelter recommendation logic</b>, and OSRM routing with <b>failure fallback</b>.</li>
          <li>Led core feature work including <b>map visualization and the test setup</b>.</li>
        </ul>
      </div>
      <div class="tab-panel" id="p1-a">
        <ul>
          <li><b>Resilient data loading:</b> a layer searching environment variables → Streamlit secrets → repo default paths in order, handling Korean CSV encoding and required-column validation.</li>
          <li><b>Recommendation engine:</b> disaster-type-specific shelter priority → region-level fallback → Haversine distance → capacity-based sorting.</li>
          <li><b>Real-time + mock data:</b> a Selenium crawler collects alerts and converts them to the app's standard schema; a <b>mock-alert generator</b> covers cases where crawling isn't possible.</li>
          <li><b>Route guidance:</b> OSRM walking routes, with an automatic <b>straight-line fallback</b> when the API fails.</li>
          <li><b>Structure &amp; testing:</b> a consistent Streamlit multi-page app (Home·Simulation·Real-time·Analysis) with a Folium map showing location, shelters and route together; <code class="mono">pytest</code> validates routing, session state and page imports.</li>
        </ul>
      </div>
      <div class="tab-panel" id="p1-r">
        <ul>
          <li>Users get <b>shelter recommendations matched to disaster type and location</b>, and the flow <b>keeps working via fallback routes and mock data</b> even when the external API or live crawling fails.</li>
          <li>It grew from a simple Streamlit visualization into a structure covering <b>data processing · recommendation · real-time collection · failure handling</b>.</li>
          <li>A <b>working dashboard</b> with Folium·OSRM·Streamlit actually wired together — new tools learned fast and applied in practice.</li>
        </ul>
      </div>
    </section>

    <!-- ---------- PROJECT 2 : FirstCall ---------- -->
    <section class="view-panel" id="p2">
      <p class="kicker">Featured Project 02</p>
      <div class="proj-head">
        <div>
          <h2 class="view-title" style="margin-bottom:0;">Local-first API Workbench · FirstCall</h2>
          <code class="repo">rad1092/firstcall-local-api-workbench</code>
        </div>
        <div class="proj-links">
          <a href="https://github.com/rad1092/firstcall-local-api-workbench" target="_blank">GitHub ↗</a>
          <a href="https://github.com/rad1092/firstcall-local-api-workbench/releases" target="_blank">Releases ↗</a>
        </div>
      </div>
      <div class="stack"><span>Rust 2024</span><span>egui / eframe</span><span>firstcall-cli</span><span>GitHub Actions</span></div>

      <p class="summary">A tool that lets you <b>verify API calls on your own machine</b> and keep them in a safe, reusable form.</p>
      <p class="context">When a program calls an external service (an "API"), the address, auth key and format differ every time — and a mistake can <b>leak sensitive info like passwords</b>. FirstCall verifies a request once, saves it like a <b>"recipe,"</b> and lets you reuse it with the secrets stripped out. The goal is to hand <b>AI agents</b> only what's <b>verified, with secrets removed</b>, so they can use APIs safely.</p>
      <div class="ai-note"><span class="badge">AI</span><span>I used <b>Claude as a pair-programming partner</b> for the Rust core, handling many input formats, tests and docs. I decided <em>what</em> to build and which rules to hold; AI sped up the repetitive implementation and edge-case checking.</span></div>

      <div class="media">
        <div class="gallery cols-2">
          <figure><img src="/assets/projects/firstcall-gui-workbench.gif" alt="FirstCall desktop GUI demo" loading="lazy"><figcaption>Desktop app — importing, verifying and organizing requests</figcaption></figure>
          <figure><img src="/assets/projects/firstcall-cli-demo.gif" alt="FirstCall CLI demo" loading="lazy"><figcaption>Command-line tool — actual run output</figcaption></figure>
        </div>
      </div>

      <div class="tabs" role="tablist">
        <button class="tab-btn active" data-target="p2-s">Situation</button>
        <button class="tab-btn" data-target="p2-t">Task</button>
        <button class="tab-btn" data-target="p2-a">Action</button>
        <button class="tab-btn" data-target="p2-r">Result</button>
      </div>
      <div class="tab-panel active" id="p2-s">
        <ul>
          <li>There was no good way to <b>collect API requests in a reusable, safe form</b>.</li>
          <li>Handing APIs to AI agents or automation risked <b>exposing auth keys</b> or mixing in <b>unverified requests</b>.</li>
          <li>There was a security need to <b>keep requests on my own machine</b> rather than a cloud.</li>
        </ul>
      </div>
      <div class="tab-panel" id="p2-t">
        <ul>
          <li>Accept <b>differently formatted requests</b> (curl·OpenAPI·Postman) into one flow and verify them locally.</li>
          <li>Save only verified requests as <b>reusable "recipes,"</b> and export them with secrets stripped.</li>
          <li>Offer both a <b>GUI</b> for people and a <b>CLI</b> for automation.</li>
        </ul>
      </div>
      <div class="tab-panel" id="p2-a">
        <ul>
          <li>Built the core in Rust, then two ways to use it — a <b>desktop app</b> you click through, and an automation <b>command-line tool (firstcall-cli)</b>.</li>
          <li>Locked in a <b>safe flow</b>: import → verify → save as recipe → strip secrets and export → re-verify.</li>
          <li>Made sure <b>scripts and config files inside imported requests are never executed</b>, blocking malicious code (supply-chain safety).</li>
          <li>Handled secrets via environment variables only, with automated tests and security checks running <b>on every release</b> via GitHub Actions.</li>
        </ul>
      </div>
      <div class="tab-panel" id="p2-r">
        <ul>
          <li>Shipped a <b>v0.1.0 release</b> with both the app and CLI, for Windows, macOS and Linux.</li>
          <li>The CLI also outputs results in a <b>machine-readable format (JSON)</b>, wiring straight into automation / AI pipelines.</li>
          <li>The <b>tool itself enforces</b> "only verified, secret-free requests leave the machine."</li>
        </ul>
      </div>
    </section>

    <!-- ---------- PROJECT 3 : gh-dep-risk ---------- -->
    <section class="view-panel" id="p3">
      <p class="kicker">Featured Project 03</p>
      <div class="proj-head">
        <div>
          <h2 class="view-title" style="margin-bottom:0;">PR Dependency Risk Check · gh-dep-risk</h2>
          <code class="repo">rad1092/gh-dependency-risk</code>
        </div>
        <div class="proj-links"><a href="https://github.com/rad1092/gh-dependency-risk" target="_blank">GitHub ↗</a></div>
      </div>
      <div class="stack"><span>Go</span><span>GitHub CLI Extension</span><span>Dependency Review API</span><span>GitHub Actions</span></div>

      <p class="summary">A tool that lets a reviewer check, with one command, whether <b>newly added third-party libraries in a PR are a security risk</b>.</p>
      <p class="context">Modern software pulls in <b>dozens or hundreds of external libraries (dependencies)</b> instead of writing everything from scratch. If one has a vulnerability, the whole thing is at risk. This tool automatically checks libraries newly added in a PR and <b>summarizes the risk as a PR comment</b>. With no separate server or database — <b>it runs on demand with a single command</b> — even small teams can use it without overhead.</p>
      <div class="ai-note"><span class="badge">AI</span><span>I used AI to organize the <b>different ways each tool records its libraries</b> (npm·pip·Go…) and to cover edge cases with tests quickly. I personally decided the scope — what to support and what to explicitly leave out.</span></div>

      <div class="media">
        <div class="gallery one">
          <figure><img src="/assets/projects/gh-dependency-risk-demo.gif" alt="gh-dep-risk terminal demo" loading="lazy"><figcaption>Terminal demo — checking PR dependencies and summarizing</figcaption></figure>
        </div>
      </div>

      <div class="tabs" role="tablist">
        <button class="tab-btn active" data-target="p3-s">Situation</button>
        <button class="tab-btn" data-target="p3-t">Task</button>
        <button class="tab-btn" data-target="p3-a">Action</button>
        <button class="tab-btn" data-target="p3-r">Result</button>
      </div>
      <div class="tab-panel active" id="p3-s">
        <ul>
          <li>Reviewers struggled to <b>gauge the risk of newly added libraries during code review</b>.</li>
          <li>But running an <b>always-on server / database</b> was too heavy for small teams.</li>
        </ul>
      </div>
      <div class="tab-panel" id="p3-t">
        <ul>
          <li>A lightweight tool reviewers <b>run only when needed</b>, with no setup or upkeep.</li>
          <li>Reuse the GitHub login they already have so it <b>runs immediately</b>.</li>
          <li>Help the reviewer decide <b>without failing CI</b>.</li>
        </ul>
      </div>
      <div class="tab-panel" id="p3-a">
        <ul>
          <li>Built it as a <b>GitHub CLI extension (one small binary)</b> — install is a single line.</li>
          <li>Uses <b>GitHub's official security data first</b>, falling back to reading project files directly only when that's unavailable.</li>
          <li>Clearly bounded what it checks (npm·pip·Go…) and the <b>support scope</b>, documented so it never over-analyzes into wrong answers.</li>
          <li>Posts results as a <b>clean PR comment</b> (updated, not duplicated), with automated tests for stability.</li>
        </ul>
      </div>
      <div class="tab-panel" id="p3-r">
        <ul>
          <li>Installable in one line: <code class="mono">gh extension install rad1092/gh-dep-risk</code>.</li>
          <li>Checks library risk across <b>11 ecosystems</b> (npm·pip·Go·Maven and more).</li>
          <li>A lightweight way to <b>review security inside the code-review flow</b>, without stopping CI.</li>
        </ul>
      </div>
    </section>

    <!-- ---------- OTHER PROJECTS ---------- -->
    <section class="view-panel" id="more">
      <p class="kicker">More</p>
      <h2 class="view-title">Other Work</h2>
      <div class="archive">
        <div class="arch-card">
          <div class="top"><span class="folder">🪞</span><a class="ext" href="https://github.com/rad1092/smart-mirror-pc123" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/smart-mirror-pc123" target="_blank">Smart Mirror AIoT Workout Coaching</a></h4>
          <p>An integrated repo wiring a display, a vision gateway and an AI coaching engine — connecting pose analysis, routine generation and real-time coaching.</p>
          <div class="tags"><span>Python</span><span>WebSocket</span><span>SQLite</span><span>AIoT</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">🔌</span><a class="ext" href="https://github.com/rad1092/firstcall-api-lookup-mcp" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/firstcall-api-lookup-mcp" target="_blank">FirstCall API Lookup MCP</a></h4>
          <p>A read-only MCP server generated from FirstCall. Exposes a single public-user-lookup tool that an AI agent can use right away.</p>
          <div class="tags"><span>TypeScript</span><span>MCP</span><span>Node</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">🧭</span><a class="ext" href="https://github.com/rad1092/job-coach-agent" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/job-coach-agent" target="_blank">Job-Coach Agent</a></h4>
          <p>Enter a target role and it runs the whole flow — job search, analysis report, cover-letter draft, interview prep, and a roadmap to landing the job.</p>
          <div class="tags"><span>Streamlit</span><span>FastAPI</span><span>SQLite</span></div>
        </div>
        <div class="arch-card">
          <div class="top"><span class="folder">⌨️</span><a class="ext" href="https://github.com/rad1092/ascii-diagram-editor" target="_blank">↗</a></div>
          <h4><a href="https://github.com/rad1092/ascii-diagram-editor" target="_blank">ASCII Diagram Editor</a></h4>
          <p>A browser-based ASCII diagram editor. Draw on a fixed grid and render the result into real text.</p>
          <div class="tags"><span>TypeScript</span><span>Vite</span><span>Client-side</span></div>
        </div>
      </div>
      <p class="lead" style="margin-top:20px;font-size:.92rem;">See everything on the <a href="/repositories-en/" style="color:var(--accent);">repositories page</a>.</p>
    </section>

    <!-- ---------- CONTACT ---------- -->
    <section class="view-panel" id="contact">
      <p class="kicker">Contact</p>
      <h2 class="view-title">Let's work together</h2>
      <p class="lead">I'm always open to new collaborations and project ideas. Feel free to reach out.</p>
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
    document.querySelectorAll('.rail-link').forEach(function (b) { b.classList.toggle('active', b.getAttribute('href') === '#' + v); });
    window.scrollTo(0, 0);
  }
  window.addEventListener('hashchange', showView);
  showView();

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

---
layout: default
permalink: /en/
---

<style>
/* ===== Reset Cayman theme chrome, build a clean canvas ===== */
.page-header { display: none !important; }
.main-content { max-width: 1200px !important; margin: 0 auto !important; padding: 0 28px 90px !important; }
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
  --radius: 14px;
}

body { background: var(--bg); }
.pf { color: var(--text); font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Apple SD Gothic Neo", "Noto Sans KR", sans-serif; line-height: 1.7; }
.pf a { color: var(--accent); text-decoration: none; }
.pf a:hover { text-decoration: underline; }
.pf .mono { font-family: "SFMono-Regular", Consolas, "Liberation Mono", Menlo, monospace; }

/* ===== Hero ===== */
.hero { display: flex; align-items: center; gap: 36px; padding: 66px 0 26px; flex-wrap: wrap; }
.hero img.avatar { width: 138px; height: 138px; border-radius: 50%; border: 2px solid var(--line); box-shadow: 0 12px 30px rgba(0,0,0,.45); }
.hero .intro { flex: 1; min-width: 260px; }
.hero .eyebrow { color: var(--accent); font-family: monospace; font-size: .9rem; letter-spacing: .04em; margin: 0 0 8px; }
.hero h1 { font-size: 3rem; margin: 0 0 12px; line-height: 1.08; }
.hero .tagline { color: var(--muted); max-width: 640px; margin: 0 0 18px; }
.hero .cta a { display: inline-block; margin: 0 10px 10px 0; padding: 9px 18px; border-radius: 8px; border: 1px solid var(--line); color: var(--text); font-size: .92rem; transition: .15s; }
.hero .cta a:hover { border-color: var(--accent); color: var(--accent); text-decoration: none; transform: translateY(-2px); }
.hero .cta a.primary { background: var(--accent); color: #0a0c10; border-color: var(--accent); font-weight: 600; }

/* ===== Section ===== */
.section { margin-top: 74px; }
.section > h2 { display: flex; align-items: center; gap: 14px; font-size: 1.55rem; margin: 0 0 26px; }
.section > h2 .num { color: var(--accent); font-family: monospace; font-size: 1.05rem; }
.section > h2::after { content: ""; flex: 1; height: 1px; background: var(--line); }

.lead { color: var(--muted); max-width: 820px; }
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
.tl-desc { color: var(--muted); margin: 4px 0 0; font-size: .94rem; max-width: 760px; }

/* certifications */
.certs-title { font-size: .8rem; font-family: monospace; color: var(--muted); letter-spacing: .05em; margin: 30px 0 12px; text-transform: uppercase; }
.certs { display: flex; flex-wrap: wrap; gap: 10px; }
.cert { background: var(--bg-soft); border: 1px solid var(--line); border-radius: 8px; padding: 8px 14px; font-size: .9rem; }

/* ===== Featured projects: left vertical tabs + wide 2-col panel ===== */
.proj-tabs { display: flex; gap: 28px; align-items: flex-start; }
.proj-nav { flex: 0 0 200px; display: flex; flex-direction: column; position: sticky; top: 20px; }
.pnav-btn { background: none; border: none; border-left: 2px solid var(--line); color: var(--muted); text-align: left; padding: 14px 16px; cursor: pointer; font-family: inherit; font-size: .96rem; line-height: 1.35; transition: .15s; }
.pnav-btn:hover { color: var(--text); background: var(--bg-soft); }
.pnav-btn.active { color: var(--accent); border-left-color: var(--accent); background: var(--bg-soft); font-weight: 600; }
.pnav-btn small { display: block; font-family: monospace; font-size: .7rem; color: var(--muted); margin-bottom: 3px; letter-spacing: .03em; }
.proj-content { flex: 1; min-width: 0; }
.proj-panel { display: none; animation: fade .3s ease; }
.proj-panel.active { display: block; }

.head { display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; flex-wrap: wrap; }
.ptitle { font-size: 1.5rem; margin: 0; }
.repo { font-family: monospace; font-size: .82rem; color: var(--muted); display: block; margin-top: 5px; }
.role-tag { display: inline-block; margin-top: 8px; font-size: .8rem; color: var(--accent-2); background: rgba(122,162,255,.08); border: 1px solid rgba(122,162,255,.25); padding: 3px 10px; border-radius: 6px; }
.links a { font-size: .85rem; margin-left: 14px; white-space: nowrap; }
.stack { display: flex; flex-wrap: wrap; gap: 8px; margin: 16px 0 20px; }
.stack span { font-family: monospace; font-size: .76rem; color: var(--accent-2); background: rgba(122,162,255,.08); border: 1px solid rgba(122,162,255,.25); padding: 3px 9px; border-radius: 6px; }

/* 2-column inside a project */
.panel-grid { display: grid; grid-template-columns: 1.05fr 0.95fr; gap: 32px; align-items: start; }
.panel-main { min-width: 0; }
.panel-media { min-width: 0; }

.summary { color: var(--text); margin: 0 0 14px; font-size: 1.05rem; line-height: 1.65; }
.summary b { color: var(--accent); }
.context { color: var(--muted); margin: 0 0 18px; }
.context b { color: var(--text); }

/* AI note woven into each project */
.ai-note { display: flex; gap: 11px; align-items: flex-start; margin: 0 0 4px; padding: 12px 15px; background: rgba(100,255,218,.05); border: 1px solid rgba(100,255,218,.22); border-radius: 9px; font-size: .88rem; color: var(--muted); }
.ai-note .badge { flex: 0 0 auto; font-family: monospace; font-size: .68rem; font-weight: 700; color: #0a0c10; background: var(--accent); padding: 2px 7px; border-radius: 5px; margin-top: 2px; }
.ai-note b { color: var(--text); }

/* ===== Media gallery ===== */
.gallery { display: grid; gap: 12px; }
.gallery figure { margin: 0; border: 1px solid var(--line); border-radius: 10px; overflow: hidden; background: var(--bg); }
.gallery img { width: 100%; display: block; }
.gallery figcaption { font-size: .78rem; color: var(--muted); padding: 8px 10px; border-top: 1px solid var(--line); }

/* ===== Inner STAR tabs ===== */
.tabs { display: flex; gap: 4px; border-bottom: 1px solid var(--line); flex-wrap: wrap; margin-top: 20px; }
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
.archive { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
.arch-card { background: var(--card); border: 1px solid var(--line); border-radius: 12px; padding: 22px; transition: transform .2s, border-color .2s; }
.arch-card:hover { transform: translateY(-5px); border-color: var(--accent); }
.arch-card .top { display: flex; justify-content: space-between; align-items: center; margin-bottom: 14px; }
.arch-card .folder { font-size: 1.5rem; }
.arch-card .ext { color: var(--muted); }
.arch-card .ext:hover { color: var(--accent); }
.arch-card h4 { margin: 0 0 8px; font-size: 1.06rem; }
.arch-card h4 a { color: var(--text); }
.arch-card h4 a:hover { color: var(--accent); text-decoration: none; }
.arch-card p { color: var(--muted); font-size: .9rem; margin: 0 0 14px; }
.arch-card .tags { display: flex; flex-wrap: wrap; gap: 8px; font-family: monospace; font-size: .73rem; color: var(--muted); }

/* ===== Contact ===== */
.contact { text-align: center; margin-top: 84px; }
.contact a.big { display: inline-block; margin-top: 14px; padding: 12px 26px; border: 1px solid var(--accent); border-radius: 8px; color: var(--accent); }
.contact a.big:hover { background: rgba(100,255,218,.08); text-decoration: none; }
.foot { text-align: center; color: var(--muted); font-size: .8rem; margin-top: 44px; }

@media (max-width: 980px) {
  .panel-grid { grid-template-columns: 1fr; gap: 22px; }
  .archive { grid-template-columns: repeat(2, 1fr); }
}
@media (max-width: 720px) {
  .hero h1 { font-size: 2.2rem; }
  .archive { grid-template-columns: 1fr; }
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
    <p class="eyebrow">Hi, my name is</p>
    <h1>HongDae Kim</h1>
    <p class="tagline">After years in field sales and materials delivery, I now build software that helps people take their next step.</p>
    <div class="cta">
      <a class="primary" href="#projects">View Projects</a>
      <a href="https://github.com/rad1092" target="_blank">GitHub</a>
      <a href="/repositories-en/">All Repositories</a>
      <a href="/">🇰🇷 한국어</a>
    </div>
  </div>
</section>

<!-- ============ ABOUT ============ -->
<section class="section" id="about">
  <h2><span class="num">01.</span> About</h2>
  <p class="lead">
    I started from small learning repositories and grew step by step toward real, usable tools.
    Guided by the idea of <span class="hl">"going beyond delivering information to driving action,"</span>
    I build software — API tooling, dependency-risk checks, disaster evacuation guidance — that helps users take their next concrete step.
  </p>
  <div class="chips">
    <span class="chip"><b>Python</b> · Streamlit · Pandas · Folium</span>
    <span class="chip"><b>Rust</b> · egui/eframe</span>
    <span class="chip"><b>Go</b> · GitHub CLI extensions</span>
    <span class="chip"><b>DevOps</b> · GitHub Actions · CI</span>
    <span class="chip"><b>AI</b> · MCP · agent tooling</span>
  </div>
</section>

<!-- ============ EXPERIENCE ============ -->
<section class="section" id="experience">
  <h2><span class="num">02.</span> Experience &amp; Background</h2>
  <div class="timeline">
    <div class="tl-item">
      <div class="tl-when">2022.04 – 2025.04</div>
      <div class="tl-role">Sales Management · Materials Delivery <span class="org">— Hyosang Safety Trading</span></div>
      <p class="tl-desc">Handled client sales management and materials delivery to construction sites. Coordinated schedules, inventory and deadlines while communicating directly with customers — turning on-site needs into data and process.</p>
    </div>
    <div class="tl-item">
      <div class="tl-when">2017.07 – 2018.07</div>
      <div class="tl-role">Spanish &amp; Mexican Culture Program <span class="org">— UNAM CEPE (National Autonomous University of Mexico)</span></div>
      <p class="tl-desc">Studied Spanish and Mexican culture for a year at UNAM's Centre for Teaching Foreigners (CEPE), learning to adapt quickly and communicate across languages and cultures.</p>
    </div>
    <div class="tl-item">
      <div class="tl-when">2016.07 – 2017.07</div>
      <div class="tl-role">Sales Management · Materials Delivery <span class="org">— Hyosang Safety Trading</span></div>
      <p class="tl-desc">My first role in sales management and materials delivery, where I learned the fundamentals of client handling and on-site delivery.</p>
    </div>
  </div>

  <div class="certs-title">Licenses &amp; Certifications</div>
  <div class="certs">
    <span class="cert">🚜 Excavator Operation</span>
    <span class="cert">🏗️ Forklift Operation</span>
    <span class="cert">🚛 Class 1 Large Vehicle License</span>
  </div>
</section>

<!-- ============ FEATURED PROJECTS (left vertical tabs) ============ -->
<section class="section" id="projects">
  <h2><span class="num">03.</span> Featured Projects</h2>

  <div class="proj-tabs">
    <!-- left nav -->
    <div class="proj-nav" role="tablist">
      <button class="pnav-btn active" data-proj="p1"><small>01 · Python</small>Disaster<br>Dashboard</button>
      <button class="pnav-btn" data-proj="p2"><small>02 · Rust</small>FirstCall<br>API Workbench</button>
      <button class="pnav-btn" data-proj="p3"><small>03 · Go</small>gh-dep-risk<br>Dependency Check</button>
    </div>

    <!-- right content -->
    <div class="proj-content">

      <!-- ===== Project 1 : Disaster Dashboard ===== -->
      <div class="proj-panel active" id="p1">
        <div class="head">
          <div>
            <h3 class="ptitle">Real-time Disaster Evacuation Dashboard</h3>
            <code class="repo">rad1092/project_dashboard</code>
            <span class="role-tag">4-person team · Backend / Architecture lead</span>
          </div>
          <div class="links">
            <a href="https://github.com/rad1092/project_dashboard" target="_blank">GitHub ↗</a>
          </div>
        </div>
        <div class="stack"><span>Python</span><span>Streamlit</span><span>Pandas</span><span>Folium</span><span>OSRM</span><span>Selenium</span><span>SQLite</span><span>pytest</span></div>

        <div class="panel-grid">
          <div class="panel-main">
            <p class="summary">A disaster alert tells you <b>"that"</b> something happened. I built a dashboard that answers "where and how do I evacuate <b>right now</b>."</p>
            <p class="context">Because the service combines <b>static public data, real-time disaster alerts, user location and an external routing API</b>, the real challenge wasn't visualization but a <b>structure that loads data reliably, recommends shelters, and finds routes without breaking</b>. On a 4-person team I owned the <b>backend and overall architecture</b> — data loading, shelter recommendation, real-time alert handling, route guidance and testing.</p>

            <div class="ai-note"><span class="badge">AI</span><span>Much of the stack was new to me, so I <b>leaned on AI tools to ramp up implementation quickly.</b> This project is where I built the practical muscle of learning a new tool on the job and driving it with AI as a partner.</span></div>

            <div class="tabs" role="tablist">
              <button class="tab-btn active" data-target="p1-s">Situation</button>
              <button class="tab-btn" data-target="p1-t">My role</button>
              <button class="tab-btn" data-target="p1-a">Action</button>
              <button class="tab-btn" data-target="p1-r">Result</button>
            </div>
            <div class="tab-panel active" id="p1-s">
              <ul>
                <li>There was <b>no unified service</b> for residents of the Yeongnam region (Daegu·Ulsan·Busan·Gyeongbuk·Gyeongnam) to find shelters and routes during a disaster.</li>
                <li>Alert data and shelter info were scattered, making it <b>hard to decide quickly</b> in a crisis.</li>
                <li>With multiple data sources and runtime environments mixed together, a <b>reliable loading / recommendation / routing structure</b> mattered most.</li>
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
                <li><b>Resilient data loading:</b> a layer that searches environment variables → Streamlit secrets → repo default paths in order, handling Korean CSV encoding and required-column validation.</li>
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
          </div>

          <div class="panel-media">
            <div class="gallery">
              <figure><img src="/assets/projects/dashboard-demo-1-landing.png" alt="Real-time evacuation guidance landing" loading="lazy"><figcaption>① Real-time guidance — waiting for disaster alerts</figcaption></figure>
              <figure><img src="/assets/projects/dashboard-demo-2-default.png" alt="No disaster alert state" loading="lazy"><figcaption>② No alert — default state by location (Ulsan Buk-gu)</figcaption></figure>
              <figure><img src="/assets/projects/dashboard-demo-3-shelter.png" alt="Shelter recommendation list" loading="lazy"><figcaption>③ Alert (home) — map + recommended shelter list</figcaption></figure>
              <figure><img src="/assets/projects/dashboard-demo-4-route.png" alt="Safe route guidance" loading="lazy"><figcaption>④ Alert (high-wind advisory) — walking safe-route guidance</figcaption></figure>
            </div>
          </div>
        </div>
      </div>

      <!-- ===== Project 2 : FirstCall ===== -->
      <div class="proj-panel" id="p2">
        <div class="head">
          <div>
            <h3 class="ptitle">Local-first API Workbench · FirstCall</h3>
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
            <p class="summary">A tool that lets you <b>verify API calls on your own machine</b> and keep them in a safe, reusable form.</p>
            <p class="context">When a program calls an external service (an "API"), the address, auth key and format differ every time — and a mistake can <b>leak sensitive info like passwords</b>. FirstCall verifies a request once, saves it like a <b>"recipe,"</b> and lets you reuse it with the secrets stripped out. The goal is to hand <b>AI agents</b> only what's <b>verified, with secrets removed</b>, so they can use APIs safely.</p>

            <div class="ai-note"><span class="badge">AI</span><span>I used <b>Claude as a pair-programming partner</b> for the Rust core, handling many input formats, tests and docs. I decided <em>what</em> to build and which rules to hold; AI sped up the repetitive implementation and edge-case checking.</span></div>

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
          </div>

          <div class="panel-media">
            <div class="gallery">
              <figure><img src="/assets/projects/firstcall-gui-workbench.gif" alt="FirstCall desktop GUI demo" loading="lazy"><figcaption>Desktop app — importing, verifying and organizing requests</figcaption></figure>
              <figure><img src="/assets/projects/firstcall-cli-demo.gif" alt="FirstCall CLI demo" loading="lazy"><figcaption>Command-line tool — actual run output</figcaption></figure>
            </div>
          </div>
        </div>
      </div>

      <!-- ===== Project 3 : gh-dep-risk ===== -->
      <div class="proj-panel" id="p3">
        <div class="head">
          <div>
            <h3 class="ptitle">PR Dependency Risk Check · gh-dep-risk</h3>
            <code class="repo">rad1092/gh-dependency-risk</code>
          </div>
          <div class="links">
            <a href="https://github.com/rad1092/gh-dependency-risk" target="_blank">GitHub ↗</a>
          </div>
        </div>
        <div class="stack"><span>Go</span><span>GitHub CLI Extension</span><span>Dependency Review API</span><span>GitHub Actions</span></div>

        <div class="panel-grid">
          <div class="panel-main">
            <p class="summary">A tool that lets a reviewer check, with one command, whether <b>newly added third-party libraries in a PR are a security risk</b>.</p>
            <p class="context">Modern software pulls in <b>dozens or hundreds of external libraries (dependencies)</b> instead of writing everything from scratch. If one of them has a vulnerability, the whole thing is at risk. This tool automatically checks libraries newly added in a PR and <b>summarizes the risk as a PR comment</b>. With no separate server or database — <b>it runs on demand with a single command</b> — even small teams can use it without overhead.</p>

            <div class="ai-note"><span class="badge">AI</span><span>I used AI to organize the <b>different ways each tool records its libraries</b> (npm·pip·Go…) and to cover edge cases with tests quickly. I personally decided the scope — what to support and what to explicitly leave out.</span></div>

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
          </div>

          <div class="panel-media">
            <div class="gallery">
              <figure><img src="/assets/projects/gh-dependency-risk-demo.gif" alt="gh-dep-risk terminal demo" loading="lazy"><figcaption>Terminal demo — checking PR dependencies and summarizing</figcaption></figure>
            </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ============ OTHER PROJECTS ============ -->
<section class="section" id="more">
  <h2><span class="num">04.</span> Other Projects</h2>
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
  <p class="lead" style="margin-top:18px;font-size:.9rem;">See everything on the <a href="/repositories-en/">repositories page</a>.</p>
</section>

<!-- ============ CONTACT ============ -->
<section class="section contact" id="contact">
  <h2 style="justify-content:center;"><span class="num">05.</span> Get in touch</h2>
  <p class="lead" style="margin:0 auto;">I'm always open to new collaborations and project ideas.</p>
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

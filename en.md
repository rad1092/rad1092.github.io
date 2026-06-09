---
layout: default
permalink: /en/
---

<style>
/* ===== Reset Cayman theme chrome, build a clean canvas ===== */
.page-header { display: none !important; }
.main-content { max-width: 960px !important; margin: 0 auto !important; padding: 0 20px 80px !important; }
.main-content h1, .main-content h2 { border: none; }
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
.hero { display: flex; align-items: center; gap: 32px; padding: 56px 0 28px; flex-wrap: wrap; }
.hero img.avatar { width: 132px; height: 132px; border-radius: 50%; border: 2px solid var(--line); box-shadow: 0 12px 30px rgba(0,0,0,.45); }
.hero .intro { flex: 1; min-width: 260px; }
.hero .eyebrow { color: var(--accent); font-family: monospace; font-size: .9rem; letter-spacing: .04em; margin: 0 0 6px; }
.hero h1 { font-size: 2.6rem; margin: 0 0 6px; line-height: 1.15; }
.hero .role { color: var(--muted); font-size: 1.15rem; margin: 0 0 18px; }
.hero .cta a { display: inline-block; margin: 0 10px 10px 0; padding: 9px 18px; border-radius: 8px; border: 1px solid var(--line); color: var(--text); font-size: .92rem; transition: .15s; }
.hero .cta a:hover { border-color: var(--accent); color: var(--accent); text-decoration: none; transform: translateY(-2px); }
.hero .cta a.primary { background: var(--accent); color: #0a0c10; border-color: var(--accent); font-weight: 600; }

/* ===== Section ===== */
.section { margin-top: 64px; }
.section > h2 { display: flex; align-items: center; gap: 14px; font-size: 1.5rem; margin: 0 0 22px; }
.section > h2 .num { color: var(--accent); font-family: monospace; font-size: 1.05rem; }
.section > h2::after { content: ""; flex: 1; height: 1px; background: var(--line); }

.lead { color: var(--muted); max-width: 720px; }

/* ===== Skill chips ===== */
.chips { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 16px; }
.chip { background: var(--bg-soft); border: 1px solid var(--line); color: var(--text); padding: 6px 13px; border-radius: 999px; font-size: .85rem; }
.chip b { color: var(--accent); }

/* ===== Project card ===== */
.project { background: var(--card); border: 1px solid var(--line); border-radius: var(--radius); padding: 26px; margin-bottom: 28px; }
.project .head { display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; flex-wrap: wrap; }
.project .ptitle { font-size: 1.3rem; margin: 0; }
.project .repo { font-family: monospace; font-size: .82rem; color: var(--muted); display: block; margin-top: 4px; }
.project .links a { font-size: .85rem; margin-left: 14px; white-space: nowrap; }
.project .stack { display: flex; flex-wrap: wrap; gap: 8px; margin: 14px 0 18px; }
.project .stack span { font-family: monospace; font-size: .76rem; color: var(--accent-2); background: rgba(122,162,255,.08); border: 1px solid rgba(122,162,255,.25); padding: 3px 9px; border-radius: 6px; }
.summary { color: var(--muted); margin: 0 0 18px; }

/* ===== Media gallery ===== */
.gallery { display: grid; gap: 12px; margin-bottom: 20px; }
.gallery.cols-2 { grid-template-columns: repeat(2, 1fr); }
.gallery figure { margin: 0; border: 1px solid var(--line); border-radius: 10px; overflow: hidden; background: var(--bg); }
.gallery img { width: 100%; display: block; }
.gallery figcaption { font-size: .78rem; color: var(--muted); padding: 8px 10px; border-top: 1px solid var(--line); }

/* ===== STAR tabs ===== */
.tabs { display: flex; gap: 6px; border-bottom: 1px solid var(--line); margin-bottom: 0; flex-wrap: wrap; }
.tab-btn { background: none; border: none; color: var(--muted); padding: 10px 16px; cursor: pointer; font-size: .9rem; border-bottom: 2px solid transparent; font-family: inherit; }
.tab-btn .k { font-family: monospace; color: var(--accent); font-weight: 700; margin-right: 6px; }
.tab-btn:hover { color: var(--text); }
.tab-btn.active { color: var(--text); border-bottom-color: var(--accent); }
.tab-panel { display: none; padding: 18px 4px 4px; animation: fade .25s ease; }
.tab-panel.active { display: block; }
.tab-panel ul { margin: 0; padding-left: 18px; }
.tab-panel li { margin-bottom: 7px; }
.tab-panel .label { font-family: monospace; font-size: .78rem; color: var(--accent); display: block; margin-bottom: 6px; letter-spacing: .05em; }
@keyframes fade { from { opacity: 0; transform: translateY(4px); } to { opacity: 1; transform: none; } }

/* ===== Contact ===== */
.contact { text-align: center; margin-top: 72px; }
.contact a.big { display: inline-block; margin-top: 14px; padding: 12px 26px; border: 1px solid var(--accent); border-radius: 8px; color: var(--accent); }
.contact a.big:hover { background: rgba(100,255,218,.08); text-decoration: none; }
.foot { text-align: center; color: var(--muted); font-size: .8rem; margin-top: 40px; }

@media (max-width: 600px) {
  .hero h1 { font-size: 2rem; }
  .gallery.cols-2 { grid-template-columns: 1fr; }
}
</style>

<div class="pf" markdown="0">

<!-- ============ HERO ============ -->
<section class="hero">
  <img class="avatar" src="/profile.png" alt="HongDae Kim">
  <div class="intro">
    <p class="eyebrow">Hi, my name is</p>
    <h1>HongDae Kim</h1>
    <p class="role">Engineer focused on developer productivity, automation &amp; data visualization</p>
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
    Guided by the idea of <b style="color:var(--text)">"going beyond delivering information to driving action,"</b>
    I build software — API tooling, dependency-risk checks, disaster evacuation guidance — that helps users take their next concrete step.
  </p>
  <div class="chips">
    <span class="chip"><b>Python</b> · Streamlit · Pandas · Folium</span>
    <span class="chip"><b>Rust</b> · egui/eframe</span>
    <span class="chip"><b>Go</b> · GitHub CLI extensions</span>
    <span class="chip"><b>DevOps</b> · GitHub Actions · CI</span>
    <span class="chip"><b>Interests</b> · Dev productivity · Security · Automation</span>
  </div>
</section>

<!-- ============ PROJECTS ============ -->
<section class="section" id="projects">
  <h2><span class="num">02.</span> Featured Projects</h2>
  <p class="lead" style="margin-bottom:8px;">Each project is broken down with <span class="mono" style="color:var(--accent)">STAR</span> — Situation · Task · Action · Result. Click the tabs to explore.</p>

  <!-- ---------- Project 1 : FirstCall ---------- -->
  <article class="project" id="p1">
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
    <p class="summary">A desktop + CLI workbench that <b style="color:var(--text)">verifies request sources locally</b> (curl, OpenAPI, Postman, HAR and more) and exports only the verified ones as <b style="color:var(--text)">redacted agent packages</b>.</p>

    <div class="gallery cols-2">
      <figure><img src="/assets/projects/firstcall-gui-workbench.gif" alt="FirstCall desktop GUI workbench demo" loading="lazy"><figcaption>Desktop GUI workbench (v0.1.0 release binary)</figcaption></figure>
      <figure><img src="/assets/projects/firstcall-cli-demo.gif" alt="FirstCall CLI lifecycle demo" loading="lazy"><figcaption>firstcall-cli lifecycle (actual command output)</figcaption></figure>
    </div>

    <div class="tabs" role="tablist">
      <button class="tab-btn active" data-target="p1-s"><span class="k">S</span>Situation</button>
      <button class="tab-btn" data-target="p1-t"><span class="k">T</span>Task</button>
      <button class="tab-btn" data-target="p1-a"><span class="k">A</span>Action</button>
      <button class="tab-btn" data-target="p1-r"><span class="k">R</span>Result</button>
    </div>
    <div class="tab-panel active" id="p1-s">
      <span class="label">SITUATION</span>
      <ul>
        <li>There was no good local tool to collect API requests in a reusable form and manage them safely.</li>
        <li>Handing APIs to agents/CI risked leaking <b>secrets</b> and passing along <b>unverified requests</b> as-is.</li>
      </ul>
    </div>
    <div class="tab-panel" id="p1-t">
      <span class="label">TASK</span>
      <ul>
        <li>Design a workbench that <b>verifies many request-source formats locally</b>, then promotes only successful ones into reusable "recipes."</li>
        <li>Export verified recipes as <b>secret-redacted agent packages</b> that can be safely handed to automation.</li>
      </ul>
    </div>
    <div class="tab-panel" id="p1-a">
      <span class="label">ACTION</span>
      <ul>
        <li>Built <b>two surfaces</b> on shared Rust 2024 core logic — an egui/eframe desktop GUI and an automation-focused <code class="mono">firstcall-cli</code>.</li>
        <li>Established the trust chain: <span class="mono" style="font-size:.8rem;color:var(--accent-2)">request source → ParsedSource → RequestDraft → local verification → Recipe → redacted package → re-verify</span>.</li>
        <li>Handled 8 source adapters (curl·OpenAPI·Postman·HAR·.http·Hurl·Bruno) as <b>static intake</b> — imported scripts, hooks and env files are never executed.</li>
        <li>Secured release reliability with CI / CLI-lifecycle / security-audit GitHub Actions workflows.</li>
      </ul>
    </div>
    <div class="tab-panel" id="p1-r">
      <span class="label">RESULT</span>
      <ul>
        <li>Shipped a <b>v0.1.0 multi-OS release binary</b> bundling both GUI and CLI.</li>
        <li>The CLI covers verify·package·validate·inspect·import·recipe lookups plus <b>JSON reports</b> for agent/CI integration.</li>
        <li>Enforced "only export locally verified requests" at the tooling level.</li>
      </ul>
    </div>
  </article>

  <!-- ---------- Project 2 : gh-dep-risk ---------- -->
  <article class="project" id="p2">
    <div class="head">
      <div>
        <h3 class="ptitle">PR Dependency Risk Review · gh-dep-risk</h3>
        <code class="repo">rad1092/gh-dependency-risk</code>
      </div>
      <div class="links">
        <a href="https://github.com/rad1092/gh-dependency-risk" target="_blank">GitHub ↗</a>
      </div>
    </div>
    <div class="stack"><span>Go</span><span>GitHub CLI Extension</span><span>Dependency Review API</span><span>GitHub Actions</span></div>
    <p class="summary">A GitHub CLI extension reviewers run <b style="color:var(--text)">on demand</b> to summarize dependency risk in a PR — no server, webhook or DB, just a <b style="color:var(--text)">single Go binary</b>.</p>

    <div class="gallery">
      <figure><img src="/assets/projects/gh-dependency-risk-demo.gif" alt="gh-dep-risk terminal demo" loading="lazy"><figcaption>Terminal demo — live E2E PR review using Yarn local fallback</figcaption></figure>
    </div>

    <div class="tabs" role="tablist">
      <button class="tab-btn active" data-target="p2-s"><span class="k">S</span>Situation</button>
      <button class="tab-btn" data-target="p2-t"><span class="k">T</span>Task</button>
      <button class="tab-btn" data-target="p2-a"><span class="k">A</span>Action</button>
      <button class="tab-btn" data-target="p2-r"><span class="k">R</span>Result</button>
    </div>
    <div class="tab-panel active" id="p2-s">
      <span class="label">SITUATION</span>
      <ul>
        <li>Reviewers struggled to quickly gauge the security risk of dependencies newly added in a PR.</li>
        <li>Yet standing up <b>always-on infrastructure</b> (server, webhook, DB, dashboard) was too heavy.</li>
      </ul>
    </div>
    <div class="tab-panel" id="p2-t">
      <span class="label">TASK</span>
      <ul>
        <li>Build a tool that <b>reuses <code class="mono">gh</code> authentication</b> and runs on demand on a reviewer's machine or in a one-off workflow.</li>
        <li>Deliver results that <b>help reviewers decide</b> without failing CI.</li>
      </ul>
    </div>
    <div class="tab-panel" id="p2-a">
      <span class="label">ACTION</span>
      <ul>
        <li>Implemented it as a <b>GitHub CLI extension (single Go binary)</b> instead of a server, so it ships with zero infrastructure.</li>
        <li>Used the GitHub <b>Dependency Review API first</b>, falling back to static-file parsing only when unavailable (403/404).</li>
        <li>Local fallback targets: npm·pnpm·yarn·bun (JS), pip·Poetry (Python), Go modules — parsing lockfiles within a clearly bounded scope.</li>
        <li><b>Upserts results as PR comments</b>; test and install-smoke workflows guard against regressions.</li>
      </ul>
    </div>
    <div class="tab-panel" id="p2-r">
      <span class="label">RESULT</span>
      <ul>
        <li>Installable in one line: <code class="mono">gh extension install rad1092/gh-dep-risk</code>.</li>
        <li>Surfaces risk across <b>11 ecosystems</b> (Cargo·Maven·npm·pip·Go and more) via the Dependency Review API path.</li>
        <li>Established a lightweight workflow for reviewing dependency risk inside the review flow, without breaking CI.</li>
      </ul>
    </div>
  </article>

  <!-- ---------- Project 3 : Disaster Dashboard ---------- -->
  <article class="project" id="p3">
    <div class="head">
      <div>
        <h3 class="ptitle">Real-time Disaster Evacuation Dashboard</h3>
        <code class="repo">rad1092/project_dashboard</code>
      </div>
      <div class="links">
        <a href="https://github.com/rad1092/project_dashboard" target="_blank">GitHub ↗</a>
      </div>
    </div>
    <div class="stack"><span>Python</span><span>Streamlit</span><span>Pandas</span><span>Folium</span><span>OSRM</span><span>Selenium</span><span>SQLite</span></div>
    <p class="summary">A disaster alert tells you <b style="color:var(--text)">that</b> something happened. To answer "where and how do I evacuate <b style="color:var(--text)">right now</b>," this multi-page dashboard combines location-based shelter recommendations, route guidance, and regional disaster-pattern analysis.</p>

    <div class="gallery cols-2">
      <figure><img src="/assets/projects/dashboard-demo-1-landing.png" alt="Real-time evacuation guidance landing" loading="lazy"><figcaption>① Real-time guidance — waiting for disaster alerts</figcaption></figure>
      <figure><img src="/assets/projects/dashboard-demo-2-default.png" alt="No disaster alert state" loading="lazy"><figcaption>② No alert — default state by location (Ulsan Buk-gu)</figcaption></figure>
      <figure><img src="/assets/projects/dashboard-demo-3-shelter.png" alt="Shelter recommendation list" loading="lazy"><figcaption>③ Alert (home) — map + recommended shelter list</figcaption></figure>
      <figure><img src="/assets/projects/dashboard-demo-4-route.png" alt="Safe route guidance" loading="lazy"><figcaption>④ Alert (high-wind advisory) — walking safe-route guidance</figcaption></figure>
    </div>

    <div class="tabs" role="tablist">
      <button class="tab-btn active" data-target="p3-s"><span class="k">S</span>Situation</button>
      <button class="tab-btn" data-target="p3-t"><span class="k">T</span>Task</button>
      <button class="tab-btn" data-target="p3-a"><span class="k">A</span>Action</button>
      <button class="tab-btn" data-target="p3-r"><span class="k">R</span>Result</button>
    </div>
    <div class="tab-panel active" id="p3-s">
      <span class="label">SITUATION</span>
      <ul>
        <li>Disaster alerts say "what happened" but not <b>"where should I evacuate now."</b></li>
        <li>Shelter and disaster-alert data were scattered, making it hard to decide on the right action immediately.</li>
      </ul>
    </div>
    <div class="tab-panel" id="p3-t">
      <span class="label">TASK</span>
      <ul>
        <li>Provide <b>location-based shelter recommendations</b> and <b>route guidance</b> on a single screen.</li>
        <li>Cover the real-time alert flow plus <b>regional disaster-pattern analysis</b> in one multi-page dashboard.</li>
      </ul>
    </div>
    <div class="tab-panel" id="p3-a">
      <span class="label">ACTION</span>
      <ul>
        <li>Built a <b>multi-page</b> app on Streamlit <code class="mono">st.navigation</code>: Home · Evacuation Simulation · Real-time Guidance · Data Analysis.</li>
        <li><b>Crawled disaster alerts</b> with Selenium and added a mock-alert generator to test the same flow across 5 regions (Daegu·Ulsan·Busan·Gyeongbuk·Gyeongnam).</li>
        <li>Selected nearby shelters via <b>Haversine</b> distance and queried <b>OSRM walking routes</b>, falling back to a straight line so guidance never breaks.</li>
        <li>Visualized current location·shelters·route on a Folium map; analysis reads <b>SQLite first, CSV as fallback</b> for data availability.</li>
      </ul>
    </div>
    <div class="tab-panel" id="p3-r">
      <span class="label">RESULT</span>
      <ul>
        <li>Completed a dashboard where 4 pages work together — demo screens ①–④ above show the real flow.</li>
        <li>Recommended shelters and safe routes <b>update in real time</b> based on alert presence, location and disaster type.</li>
        <li>Connected guidance to understanding — alert time series, regional comparison, and shelter distribution in one tool.</li>
      </ul>
    </div>
  </article>
</section>

<!-- ============ CONTACT ============ -->
<section class="section contact" id="contact">
  <h2 style="justify-content:center;"><span class="num">03.</span> Get in touch</h2>
  <p class="lead" style="margin:0 auto;">I'm always open to new collaborations and project ideas.</p>
  <a class="big" href="https://github.com/rad1092" target="_blank">GitHub @rad1092</a>
</section>

<p class="foot">Built with Jekyll · Designed &amp; developed by HongDae Kim</p>

</div>

<script>
(function () {
  document.querySelectorAll('.tabs').forEach(function (tabs) {
    tabs.addEventListener('click', function (e) {
      var btn = e.target.closest('.tab-btn');
      if (!btn) return;
      var card = tabs.closest('.project');
      card.querySelectorAll('.tab-btn').forEach(function (b) { b.classList.remove('active'); });
      card.querySelectorAll('.tab-panel').forEach(function (p) { p.classList.remove('active'); });
      btn.classList.add('active');
      var panel = card.querySelector('#' + btn.dataset.target);
      if (panel) panel.classList.add('active');
    });
  });
})();
</script>

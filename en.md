---
layout: default
permalink: /en/
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
    <p class="eyebrow">Hi, my name is</p>
    <h1>HongDae Kim</h1>
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
      <div class="tl-when">~4 years</div>
      <div class="tl-role">Sales Management · Materials Delivery <span class="org">— Construction materials supplier</span></div>
      <p class="tl-desc">Handled client sales management and materials delivery to construction sites. Coordinated schedules, inventory and deadlines while communicating directly with customers — turning on-site needs into data and process.</p>
    </div>
    <div class="tl-item">
      <div class="tl-when">1 year</div>
      <div class="tl-role">Study Abroad <span class="org">— Mexico</span></div>
      <p class="tl-desc">Spent a year studying in Mexico, experiencing the local language and culture firsthand and learning to adapt and communicate quickly in an unfamiliar environment.</p>
    </div>
  </div>
</section>

<!-- ============ FEATURED PROJECTS (left vertical tabs) ============ -->
<section class="section" id="projects">
  <h2><span class="num">03.</span> Featured Projects</h2>

  <div class="proj-tabs">
    <!-- left nav -->
    <div class="proj-nav" role="tablist">
      <button class="pnav-btn active" data-proj="p1"><small>01 · Rust</small>FirstCall<br>API Workbench</button>
      <button class="pnav-btn" data-proj="p2"><small>02 · Go</small>gh-dep-risk<br>Dependency Risk</button>
      <button class="pnav-btn" data-proj="p3"><small>03 · Python</small>Disaster<br>Dashboard</button>
    </div>

    <!-- right content -->
    <div class="proj-content">

      <!-- ===== Project 1 ===== -->
      <div class="proj-panel active" id="p1">
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
        <p class="summary">A desktop + CLI workbench that <b>verifies API request sources locally</b> and exports only the verified ones as <b>redacted agent packages</b>.</p>
        <p class="context">It ingests request sources like curl·OpenAPI·Postman·HAR·.http·Hurl·Bruno, <b>actually runs them locally to verify</b>, and promotes only the successful ones into reusable "recipes." Those recipes are then exported as <b>secret-redacted packages</b> that agents and CI can safely use. The core idea: <b>nothing unverified or with exposed secrets ever leaves your machine</b>, enforced at the tooling level.</p>

        <div class="ai-note"><span class="badge">AI</span><span>I used <b>Claude as a pair-programming partner</b> across the Rust 2024 core design, the 8 source adapters and the trust chain, plus tests and docs. I decided <em>what</em> to build and which invariants to hold; AI accelerated the repetitive implementation and edge-case review.</span></div>

        <div class="gallery cols-2">
          <figure><img src="/assets/projects/firstcall-gui-workbench.gif" alt="FirstCall desktop GUI workbench demo" loading="lazy"><figcaption>Desktop GUI workbench (v0.1.0 release binary)</figcaption></figure>
          <figure><img src="/assets/projects/firstcall-cli-demo.gif" alt="FirstCall CLI lifecycle demo" loading="lazy"><figcaption>firstcall-cli lifecycle (actual command output)</figcaption></figure>
        </div>

        <div class="tabs" role="tablist">
          <button class="tab-btn active" data-target="p1-s">Situation</button>
          <button class="tab-btn" data-target="p1-t">Task</button>
          <button class="tab-btn" data-target="p1-a">Action</button>
          <button class="tab-btn" data-target="p1-r">Result</button>
        </div>
        <div class="tab-panel active" id="p1-s">
          <ul>
            <li>There was no good <b>local-first</b> tool to collect API requests in a reusable form and manage them safely.</li>
            <li>Handing APIs to agents/CI risked <b>leaking secrets</b> like tokens, or mixing in <b>unverified requests</b>.</li>
            <li>There was also a security need to <b>keep requests on my own machine</b> rather than uploading them to a cloud.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p1-t">
          <ul>
            <li>Accept <b>wildly different request-source formats</b> (curl·OpenAPI·Postman·HAR) into one flow and verify them locally.</li>
            <li>Promote only successfully verified requests into reusable <b>"recipes,"</b> filtering out the failures.</li>
            <li>Export verified recipes as <b>secret-redacted agent packages</b> safe to hand to automation.</li>
            <li>Serve <b>both</b> a human GUI and an automation CLI on one shared core.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p1-a">
          <ul>
            <li>Built a <b>shared Rust 2024 core</b>, then two surfaces on top — an egui/eframe <b>desktop GUI</b> and an automation-focused <code class="mono">firstcall-cli</code>.</li>
            <li>Core trust chain: <span class="mono" style="font-size:.82rem;color:var(--accent-2)">request source → ParsedSource → RequestDraft candidate → local verification → Recipe → redacted package → re-verify</span>.</li>
            <li>The GUI connects source intake · parser notes · candidate review · runtime slot/auth entry · local HTTP execution · attempt review · recipe review · secret-backend status into <b>one flow</b>.</li>
            <li>All 8 source adapters are <b>static intake</b> — imported scripts, tests, runtime hooks and env files are <b>never executed</b> (supply-chain risk blocked).</li>
            <li>Secrets are handled <b>via environment variables only</b> and redacted on export. CI / CLI-lifecycle / security-audit GitHub Actions secure release reliability.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p1-r">
          <ul>
            <li>Shipped a <b>v0.1.0 multi-OS release binary</b> bundling both GUI and CLI.</li>
            <li>The CLI covers verify·package·validate·inspect·import·recipe lookups plus <b>JSON reports</b>, wiring straight into agent/CI pipelines.</li>
            <li>Designed the <b>tool itself to enforce</b> "only locally verified, secret-redacted requests leave the machine."</li>
          </ul>
        </div>
      </div>

      <!-- ===== Project 2 ===== -->
      <div class="proj-panel" id="p2">
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
        <p class="summary">A GitHub CLI extension reviewers run <b>on demand</b> to summarize dependency risk in a pull request.</p>
        <p class="context">It avoids standing infrastructure — no server, webhook, DB or dashboard — and runs as a <b>single Go binary</b>. It reuses <code class="mono">gh</code> authentication so it works right on a reviewer's machine or in a one-off workflow, uses GitHub's <b>Dependency Review API first</b>, and only falls back to parsing static lockfiles <b>locally</b> when the API is unavailable. Results are posted as a <b>PR comment</b> without ever failing CI.</p>

        <div class="ai-note"><span class="badge">AI</span><span>I used AI to organize the <b>differing lockfile rules</b> across npm·pnpm·yarn·bun·pip·Poetry·Go, design the fallback branches, and quickly cover edge cases with test fixtures. I personally decided how far to scope it — and what to explicitly mark as "not supported."</span></div>

        <div class="gallery">
          <figure><img src="/assets/projects/gh-dependency-risk-demo.gif" alt="gh-dep-risk terminal demo" loading="lazy"><figcaption>Terminal demo — live E2E PR review using Yarn local fallback</figcaption></figure>
        </div>

        <div class="tabs" role="tablist">
          <button class="tab-btn active" data-target="p2-s">Situation</button>
          <button class="tab-btn" data-target="p2-t">Task</button>
          <button class="tab-btn" data-target="p2-a">Action</button>
          <button class="tab-btn" data-target="p2-r">Result</button>
        </div>
        <div class="tab-panel active" id="p2-s">
          <ul>
            <li>Reviewers struggled to <b>gauge the risk of newly added dependencies during code review</b>.</li>
            <li>Standing up <b>always-on infrastructure</b> (server, webhook, DB, dashboard) was too heavy for small teams.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p2-t">
          <ul>
            <li>A lightweight tool that <b>reuses <code class="mono">gh</code> auth</b> and runs on demand on a reviewer's machine or in a one-off workflow.</li>
            <li>Deliver results that <b>help reviewers decide</b> without failing CI.</li>
            <li>Balance accuracy and simplicity — use <b>official data</b> when possible, minimal local analysis only when not.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p2-a">
          <ul>
            <li>Implemented as a <b>GitHub CLI extension (single Go binary)</b> — installable in one line, zero infrastructure.</li>
            <li>Used the <b>Dependency Review API first</b>, falling back to static-file parsing only when unavailable (403/404).</li>
            <li>Clearly bounded the fallback scope: npm·pnpm·yarn·bun (JS), pip·Poetry·uv (Python), Go modules — parses lockfiles but <b>does not reconstruct the full graph</b>, documented explicitly.</li>
            <li><b>Upserts results as a PR comment</b> (updated, not duplicated); test/install-smoke workflows and renderer-backed fixtures guard against regressions.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p2-r">
          <ul>
            <li>Installable in one line: <code class="mono">gh extension install rad1092/gh-dep-risk</code>.</li>
            <li>Surfaces risk across <b>11 ecosystems</b> (Cargo·Composer·Go·Maven·npm·pip·pnpm·Poetry·RubyGems·Swift·Yarn) via the API path.</li>
            <li>Established a <b>lightweight workflow</b> for reviewing dependency risk inside the review flow, without breaking CI.</li>
          </ul>
        </div>
      </div>

      <!-- ===== Project 3 ===== -->
      <div class="proj-panel" id="p3">
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
        <p class="summary">A disaster alert tells you <b>that</b> something happened. This multi-page dashboard answers "where and how do I evacuate <b>right now</b>."</p>
        <p class="context">It combines <b>location-based shelter recommendations</b>, <b>walking-route guidance</b>, and <b>regional disaster-pattern analysis</b> in one place. It crawls real-time disaster alerts, then for the detected region shows the latest alerts, recommended shelters and a route map on a single screen — while the analysis page reveals alert time series, regional traits, and shelter distribution. Supported regions: <b>Daegu·Ulsan·Busan·Gyeongbuk·Gyeongnam</b>.</p>

        <div class="ai-note"><span class="badge">AI</span><span>I used AI to rapidly prototype and verify the <b>repetitive implementation and data wrangling</b> — alert crawling, Haversine distance, OSRM route queries, Streamlit multi-page wiring. I led the screen design: <em>what</em> information to show the user, and in <em>what</em> order.</span></div>

        <div class="gallery cols-2">
          <figure><img src="/assets/projects/dashboard-demo-1-landing.png" alt="Real-time evacuation guidance landing" loading="lazy"><figcaption>① Real-time guidance — waiting for disaster alerts</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-2-default.png" alt="No disaster alert state" loading="lazy"><figcaption>② No alert — default state by location (Ulsan Buk-gu)</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-3-shelter.png" alt="Shelter recommendation list" loading="lazy"><figcaption>③ Alert (home) — map + recommended shelter list</figcaption></figure>
          <figure><img src="/assets/projects/dashboard-demo-4-route.png" alt="Safe route guidance" loading="lazy"><figcaption>④ Alert (high-wind advisory) — walking safe-route guidance</figcaption></figure>
        </div>

        <div class="tabs" role="tablist">
          <button class="tab-btn active" data-target="p3-s">Situation</button>
          <button class="tab-btn" data-target="p3-t">Task</button>
          <button class="tab-btn" data-target="p3-a">Action</button>
          <button class="tab-btn" data-target="p3-r">Result</button>
        </div>
        <div class="tab-panel active" id="p3-s">
          <ul>
            <li>Disaster alerts say "what happened" but not <b>"where should I evacuate now."</b></li>
            <li>Shelter and alert data were scattered, making it hard to <b>decide on the right action immediately</b>.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p3-t">
          <ul>
            <li>Provide <b>location-based shelter recommendations</b> and <b>route guidance</b> on a single screen.</li>
            <li>Cover the real-time alert flow plus <b>regional disaster-pattern analysis</b> in one multi-page dashboard.</li>
            <li>Make guidance <b>robust</b> so it doesn't break even when a route query fails.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p3-a">
          <ul>
            <li>Built a <b>multi-page</b> app on Streamlit <code class="mono">st.navigation</code>: Home · Evacuation Simulation · Real-time Guidance · Data Analysis.</li>
            <li><b>Crawled alerts</b> with Selenium and added a mock-alert generator to test the same flow across 5 regions (Daegu·Ulsan·Busan·Gyeongbuk·Gyeongnam).</li>
            <li>Selected nearby shelters via <b>Haversine</b> distance and queried <b>OSRM walking routes</b>, with a <b>straight-line fallback</b> so guidance never breaks.</li>
            <li>Visualized location·shelters·route on a Folium map; analysis reads <b>SQLite first, CSV as fallback</b> and offers distribution, time-series, regional-comparison and region-wide shelter-map tabs.</li>
          </ul>
        </div>
        <div class="tab-panel" id="p3-r">
          <ul>
            <li>Completed a dashboard where 4 pages work together — demo screens ①–④ above show the real flow.</li>
            <li>Recommended shelters and safe routes <b>update in real time</b> based on alert presence, location and disaster type.</li>
            <li>Connected guidance to understanding — alert time series, regional comparison and shelter distribution <b>in one tool</b>.</li>
          </ul>
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
      <p>An integrated repo wiring a PC1 display, a PC3 vision gateway, and a PC2 AI coaching engine — connecting pose analysis, routine generation and real-time workout coaching.</p>
      <div class="tags"><span>Python</span><span>WebSocket</span><span>SQLite</span><span>AIoT</span></div>
    </div>
    <div class="arch-card">
      <div class="top"><span class="folder">🔌</span><a class="ext" href="https://github.com/rad1092/firstcall-api-lookup-mcp" target="_blank">↗</a></div>
      <h4><a href="https://github.com/rad1092/firstcall-api-lookup-mcp" target="_blank">FirstCall API Lookup MCP</a></h4>
      <p>A read-only MCP server generated from a FirstCall recipe. A single <code class="mono">github_user_lookup</code> tool that looks up public user records — agent-ready.</p>
      <div class="tags"><span>TypeScript</span><span>MCP</span><span>Node</span></div>
    </div>
    <div class="arch-card">
      <div class="top"><span class="folder">🧭</span><a class="ext" href="https://github.com/rad1092/job-coach-agent" target="_blank">↗</a></div>
      <h4><a href="https://github.com/rad1092/job-coach-agent" target="_blank">Job-Coach Agent</a></h4>
      <p>Enter your target industry, role and position and it runs the whole flow — job search, analysis report, cover-letter draft, interview prep, and a roadmap to landing the job.</p>
      <div class="tags"><span>Streamlit</span><span>FastAPI</span><span>SQLite</span></div>
    </div>
    <div class="arch-card">
      <div class="top"><span class="folder">⌨️</span><a class="ext" href="https://github.com/rad1092/ascii-diagram-editor" target="_blank">↗</a></div>
      <h4><a href="https://github.com/rad1092/ascii-diagram-editor" target="_blank">ASCII Diagram Editor</a></h4>
      <p>A browser-based ASCII diagram editor. Works on a fixed 200×80 character grid and renders the result into a real <code class="mono">&lt;pre&gt;</code> node.</p>
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

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kraniksa Williams — GitHub Profile README</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;700;900&family=Rajdhani:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --navy: #030712;
    --navy2: #0a0f1e;
    --navy3: #0d1426;
    --purple: #7c3aed;
    --purple2: #a855f7;
    --purple3: #c084fc;
    --blue: #3b82f6;
    --blue2: #60a5fa;
    --cyan: #06b6d4;
    --cyan2: #22d3ee;
    --pink: #ec4899;
    --gold: #f59e0b;
    --green: #10b981;
    --glass: rgba(255,255,255,0.04);
    --glass2: rgba(255,255,255,0.07);
    --glass3: rgba(255,255,255,0.10);
    --border: rgba(139,92,246,0.25);
    --border2: rgba(139,92,246,0.45);
    --text: #e2e8f0;
    --text2: #94a3b8;
    --text3: #64748b;
  }
  * { margin:0; padding:0; box-sizing:border-box; }
  body {
    background: var(--navy);
    color: var(--text);
    font-family: 'Rajdhani', sans-serif;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* ─── ANIMATED BG ─── */
  .bg-layer {
    position: fixed; inset: 0; z-index: 0; overflow: hidden; pointer-events: none;
  }
  .bg-orb {
    position: absolute; border-radius: 50%; filter: blur(120px); opacity: 0.18;
    animation: orb-drift 20s ease-in-out infinite alternate;
  }
  .bg-orb:nth-child(1){ width:700px;height:700px;top:-200px;left:-150px;background:var(--purple); animation-delay:0s; }
  .bg-orb:nth-child(2){ width:600px;height:600px;bottom:-100px;right:-100px;background:var(--blue); animation-delay:-7s; }
  .bg-orb:nth-child(3){ width:400px;height:400px;top:40%;left:40%;background:var(--cyan); animation-delay:-14s; }
  @keyframes orb-drift {
    0%{ transform: translate(0,0) scale(1); }
    100%{ transform: translate(60px,40px) scale(1.1); }
  }

  /* grid lines */
  .grid-lines {
    position: fixed; inset: 0; z-index: 0; pointer-events: none;
    background-image:
      linear-gradient(rgba(139,92,246,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(139,92,246,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
  }

  /* particles */
  .particles { position:fixed; inset:0; z-index:0; pointer-events:none; }
  .particle {
    position:absolute; border-radius:50%;
    background: radial-gradient(circle, var(--purple3) 0%, transparent 70%);
    animation: float-up linear infinite;
    opacity:0;
  }
  @keyframes float-up {
    0%{ transform:translateY(100vh) scale(0); opacity:0; }
    10%{ opacity:0.6; }
    90%{ opacity:0.3; }
    100%{ transform:translateY(-10vh) scale(1); opacity:0; }
  }

  /* ─── LAYOUT ─── */
  .readme-wrap {
    position: relative; z-index: 1;
    max-width: 960px; margin: 0 auto;
    padding: 32px 24px 80px;
  }

  /* ─── HERO BANNER ─── */
  .hero {
    border-radius: 24px;
    border: 1px solid var(--border2);
    background: linear-gradient(135deg, rgba(10,15,30,0.95) 0%, rgba(20,10,40,0.95) 50%, rgba(5,20,35,0.95) 100%);
    padding: 48px 40px 40px;
    position: relative; overflow: hidden;
    margin-bottom: 24px;
    box-shadow: 0 0 80px rgba(139,92,246,0.12), 0 0 120px rgba(59,130,246,0.06), inset 0 1px 0 rgba(255,255,255,0.08);
  }
  .hero::before {
    content:''; position:absolute; inset:0;
    background: conic-gradient(from 45deg at 10% 10%, rgba(139,92,246,0.08) 0deg, transparent 60deg, transparent 300deg, rgba(59,130,246,0.05) 360deg);
    pointer-events:none;
  }
  .hero-inner {
    display:flex; gap:48px; align-items:center; position:relative; z-index:1;
    flex-wrap: wrap;
  }

  /* Avatar */
  .avatar-wrap {
    flex-shrink:0; position:relative;
  }
  .avatar-ring {
    width:200px; height:200px; border-radius:50%;
    background: conic-gradient(var(--purple) 0deg, var(--cyan) 90deg, var(--blue) 180deg, var(--pink) 270deg, var(--purple) 360deg);
    padding: 3px;
    animation: spin-slow 8s linear infinite;
    box-shadow: 0 0 40px rgba(139,92,246,0.5), 0 0 80px rgba(139,92,246,0.2);
  }
  @keyframes spin-slow {
    0%{ transform:rotate(0deg); }
    100%{ transform:rotate(360deg); }
  }
  .avatar-inner {
    width:100%; height:100%; border-radius:50%; overflow:hidden;
    background:var(--navy2);
    border: 3px solid var(--navy2);
    display:flex; align-items:center; justify-content:center;
    position:relative;
  }
  .avatar-inner img {
    width:100%; height:100%; object-fit:cover; object-position:center top;
    filter: saturate(1.1) contrast(1.05);
  }
  .avatar-badge {
    position:absolute; bottom:4px; right:4px;
    background: linear-gradient(135deg, var(--green), #059669);
    width:22px; height:22px; border-radius:50%;
    border: 3px solid var(--navy2);
    box-shadow: 0 0 12px rgba(16,185,129,0.7);
  }
  .avatar-glow {
    position:absolute; inset:-4px; border-radius:50%;
    background: transparent;
    box-shadow: 0 0 30px rgba(139,92,246,0.6);
    animation: pulse-glow 2s ease-in-out infinite;
  }
  @keyframes pulse-glow {
    0%,100%{ box-shadow:0 0 20px rgba(139,92,246,0.5); }
    50%{ box-shadow:0 0 50px rgba(139,92,246,0.8), 0 0 80px rgba(59,130,246,0.3); }
  }

  /* Hero text */
  .hero-text { flex:1; min-width:260px; }
  .hero-greeting {
    font-family: 'Orbitron', sans-serif;
    font-size:13px; letter-spacing:4px; text-transform:uppercase;
    color:var(--cyan2); margin-bottom:10px;
    animation: fade-in 0.8s ease;
  }
  .hero-name {
    font-family: 'Orbitron', sans-serif;
    font-size: clamp(28px, 5vw, 46px);
    font-weight:900; line-height:1.05;
    background: linear-gradient(135deg, #fff 0%, var(--purple3) 40%, var(--cyan2) 80%, var(--blue2) 100%);
    -webkit-background-clip:text; -webkit-text-fill-color:transparent;
    background-clip:text;
    margin-bottom:16px;
    text-shadow: none;
    letter-spacing:2px;
  }
  .hero-subtitle {
    display:flex; flex-wrap:wrap; gap:8px;
    margin-bottom:20px;
  }
  .subtitle-tag {
    font-family:'Rajdhani', sans-serif; font-size:11px; font-weight:600;
    letter-spacing:2px; text-transform:uppercase; padding:5px 12px;
    border-radius:20px; border:1px solid;
    animation: fade-slide-in 0.6s ease both;
  }
  .subtitle-tag:nth-child(1){ color:var(--purple3); border-color:rgba(192,132,252,0.4); background:rgba(139,92,246,0.1); animation-delay:0.1s; }
  .subtitle-tag:nth-child(2){ color:var(--cyan2); border-color:rgba(34,211,238,0.4); background:rgba(6,182,212,0.08); animation-delay:0.2s; }
  .subtitle-tag:nth-child(3){ color:var(--pink); border-color:rgba(236,72,153,0.4); background:rgba(236,72,153,0.08); animation-delay:0.3s; }
  .subtitle-tag:nth-child(4){ color:var(--gold); border-color:rgba(245,158,11,0.4); background:rgba(245,158,11,0.08); animation-delay:0.4s; }
  .subtitle-tag:nth-child(5){ color:var(--green); border-color:rgba(16,185,129,0.4); background:rgba(16,185,129,0.08); animation-delay:0.5s; }
  @keyframes fade-slide-in {
    from{ opacity:0; transform:translateY(10px); }
    to{ opacity:1; transform:translateY(0); }
  }
  .hero-bio {
    font-size:14px; color:var(--text2); line-height:1.7; max-width:480px;
    font-weight:400; letter-spacing:0.3px;
  }
  .hero-bio strong { color:var(--purple3); font-weight:600; }

  /* Floating decorative elements in hero */
  .hero-deco { position:absolute; right:0; top:0; bottom:0; width:260px; pointer-events:none; overflow:hidden; }
  .deco-chart {
    position:absolute;
    opacity:0.15;
  }

  /* ─── GLASS CARD ─── */
  .glass-card {
    background: var(--glass);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px;
    backdrop-filter: blur(20px);
    transition: border-color 0.3s, box-shadow 0.3s;
  }
  .glass-card:hover {
    border-color: var(--border2);
    box-shadow: 0 0 30px rgba(139,92,246,0.1);
  }

  /* ─── SECTION HEADER ─── */
  .section-label {
    display:flex; align-items:center; gap:12px; margin-bottom:20px;
  }
  .section-label-line {
    flex:1; height:1px;
    background: linear-gradient(90deg, var(--purple), transparent);
  }
  .section-label-text {
    font-family:'Orbitron', sans-serif; font-size:11px; letter-spacing:3px;
    text-transform:uppercase; color:var(--purple3); white-space:nowrap;
  }

  /* ─── CONTACT ROW ─── */
  .contact-grid {
    display:grid; grid-template-columns:repeat(auto-fit, minmax(200px, 1fr)); gap:12px;
    margin-bottom:24px;
  }
  .contact-item {
    display:flex; align-items:center; gap:10px; padding:12px 16px;
    background: var(--glass2); border:1px solid var(--border); border-radius:10px;
    font-size:13px; color:var(--text2); text-decoration:none;
    transition:all 0.25s;
  }
  .contact-item:hover { border-color:var(--purple3); color:var(--purple3); background:rgba(139,92,246,0.1); }
  .contact-icon { font-size:16px; flex-shrink:0; }
  .contact-item span { font-size:11px; color:var(--text3); display:block; }

  /* ─── STATS STRIP ─── */
  .stats-strip {
    display:grid; grid-template-columns:repeat(auto-fit, minmax(120px, 1fr)); gap:12px;
    margin-bottom:24px;
  }
  .stat-card {
    background: var(--glass2); border:1px solid var(--border); border-radius:12px;
    padding:16px; text-align:center;
    position:relative; overflow:hidden;
    transition:all 0.3s;
  }
  .stat-card::before {
    content:''; position:absolute; inset:0;
    background: linear-gradient(135deg, transparent 60%, rgba(139,92,246,0.06));
    pointer-events:none;
  }
  .stat-card:hover { border-color:var(--border2); transform:translateY(-2px); }
  .stat-num {
    font-family:'Orbitron', sans-serif; font-size:26px; font-weight:700;
    background: linear-gradient(135deg, var(--purple3), var(--cyan2));
    -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
    display:block;
  }
  .stat-label { font-size:10px; letter-spacing:2px; text-transform:uppercase; color:var(--text3); margin-top:2px; }

  /* ─── SKILLS ─── */
  .skills-grid {
    display:grid; grid-template-columns:repeat(auto-fit, minmax(180px, 1fr)); gap:14px;
  }
  .skill-group {
    background: var(--glass2); border:1px solid var(--border); border-radius:14px;
    padding:18px;
    transition:all 0.3s;
  }
  .skill-group:hover { border-color:var(--border2); box-shadow:0 0 20px rgba(139,92,246,0.1); }
  .skill-group-title {
    font-family:'Orbitron', sans-serif; font-size:9px; letter-spacing:2.5px;
    text-transform:uppercase; color:var(--cyan2); margin-bottom:12px;
    display:flex; align-items:center; gap:6px;
  }
  .skill-group-title::after {
    content:''; flex:1; height:1px; background:linear-gradient(90deg, var(--cyan2), transparent); opacity:0.4;
  }
  .skill-tags { display:flex; flex-wrap:wrap; gap:6px; }
  .skill-tag {
    font-size:11px; font-weight:600; padding:4px 10px; border-radius:6px;
    letter-spacing:0.5px; border:1px solid;
    transition:all 0.2s;
  }
  .skill-tag:hover { transform:translateY(-1px); }
  .st-purple { color:var(--purple3); border-color:rgba(192,132,252,0.35); background:rgba(139,92,246,0.1); }
  .st-cyan { color:var(--cyan2); border-color:rgba(34,211,238,0.35); background:rgba(6,182,212,0.08); }
  .st-blue { color:var(--blue2); border-color:rgba(96,165,250,0.35); background:rgba(59,130,246,0.08); }
  .st-green { color:var(--green); border-color:rgba(16,185,129,0.35); background:rgba(16,185,129,0.08); }
  .st-gold { color:var(--gold); border-color:rgba(245,158,11,0.35); background:rgba(245,158,11,0.08); }
  .st-pink { color:var(--pink); border-color:rgba(236,72,153,0.35); background:rgba(236,72,153,0.08); }

  /* ─── PROJECTS ─── */
  .projects-grid {
    display:grid; grid-template-columns:repeat(auto-fit, minmax(280px, 1fr)); gap:16px;
  }
  .project-card {
    background: var(--glass); border:1px solid var(--border); border-radius:16px;
    padding:20px; position:relative; overflow:hidden;
    transition:all 0.35s;
    cursor:pointer;
  }
  .project-card::before {
    content:''; position:absolute; inset:0;
    background: linear-gradient(135deg, transparent 40%, rgba(139,92,246,0.04));
    pointer-events:none;
  }
  .project-card:hover {
    border-color:var(--border2);
    transform:translateY(-4px);
    box-shadow:0 20px 60px rgba(139,92,246,0.15), 0 0 40px rgba(139,92,246,0.08);
  }
  .project-card-top {
    display:flex; align-items:flex-start; justify-content:space-between; margin-bottom:12px;
  }
  .project-icon {
    width:44px; height:44px; border-radius:10px;
    display:flex; align-items:center; justify-content:center;
    font-size:22px; flex-shrink:0;
    border:1px solid;
  }
  .project-title {
    font-family:'Orbitron', sans-serif; font-size:13px; font-weight:600;
    color:#fff; margin-bottom:6px; line-height:1.3;
  }
  .project-desc { font-size:12px; color:var(--text2); line-height:1.6; margin-bottom:14px; }
  .project-tags { display:flex; flex-wrap:wrap; gap:5px; }
  .project-tag {
    font-size:9px; letter-spacing:1.5px; text-transform:uppercase;
    padding:3px 8px; border-radius:4px; font-weight:700;
  }
  .project-arrow {
    font-size:18px; color:var(--text3); transition:all 0.2s;
    margin-top:2px;
  }
  .project-card:hover .project-arrow { color:var(--purple3); transform:translate(3px,-3px); }

  /* project color variants */
  .pc-fraud .project-icon { background:rgba(236,72,153,0.12); border-color:rgba(236,72,153,0.3); }
  .pc-fraud .project-title { color: #f9a8d4; }
  .pc-seg .project-icon { background:rgba(6,182,212,0.12); border-color:rgba(6,182,212,0.3); }
  .pc-seg .project-title { color: #67e8f9; }
  .pc-aqi .project-icon { background:rgba(16,185,129,0.12); border-color:rgba(16,185,129,0.3); }
  .pc-aqi .project-title { color: #6ee7b7; }
  .pc-deep .project-icon { background:rgba(139,92,246,0.12); border-color:rgba(139,92,246,0.3); }
  .pc-deep .project-title { color: #c4b5fd; }
  .pc-plate .project-icon { background:rgba(245,158,11,0.12); border-color:rgba(245,158,11,0.3); }
  .pc-plate .project-title { color: #fcd34d; }
  .pc-tour .project-icon { background:rgba(59,130,246,0.12); border-color:rgba(59,130,246,0.3); }
  .pc-tour .project-title { color: #93c5fd; }

  /* ─── EXPERIENCE ─── */
  .exp-item {
    display:flex; gap:20px; padding:20px;
    background:var(--glass2); border:1px solid var(--border); border-radius:14px;
    margin-bottom:12px;
    transition:all 0.3s;
  }
  .exp-item:hover { border-color:var(--border2); }
  .exp-dot {
    width:40px; height:40px; flex-shrink:0; border-radius:10px;
    background:linear-gradient(135deg, var(--purple), var(--blue));
    display:flex; align-items:center; justify-content:center; font-size:18px;
    box-shadow: 0 0 20px rgba(139,92,246,0.3);
  }
  .exp-role { font-size:15px; font-weight:600; color:#fff; }
  .exp-company { font-size:12px; color:var(--purple3); font-weight:600; letter-spacing:1px; }
  .exp-period { font-size:11px; color:var(--text3); margin-top:2px; margin-bottom:8px; }
  .exp-bullets { list-style:none; font-size:12px; color:var(--text2); }
  .exp-bullets li { padding:2px 0 2px 14px; position:relative; }
  .exp-bullets li::before { content:'▸'; position:absolute; left:0; color:var(--purple3); font-size:10px; top:3px; }

  /* ─── EDUCATION ─── */
  .edu-grid { display:grid; grid-template-columns:repeat(auto-fit, minmax(260px, 1fr)); gap:12px; }
  .edu-card {
    background:var(--glass2); border:1px solid var(--border); border-radius:12px;
    padding:16px; display:flex; gap:14px; align-items:flex-start;
    transition:all 0.3s;
  }
  .edu-card:hover { border-color:var(--border2); }
  .edu-icon { font-size:24px; flex-shrink:0; margin-top:2px; }
  .edu-degree { font-size:13px; font-weight:600; color:#fff; margin-bottom:2px; }
  .edu-school { font-size:11px; color:var(--purple3); font-weight:600; letter-spacing:0.5px; }
  .edu-detail { font-size:11px; color:var(--text3); margin-top:4px; }

  /* ─── GITHUB ANALYTICS ─── */
  .analytics-grid { display:grid; grid-template-columns:1fr 1fr; gap:14px; }
  .analytics-card {
    background:var(--glass2); border:1px solid var(--border); border-radius:14px;
    padding:20px; overflow:hidden; position:relative;
  }
  .analytics-card:first-child { grid-column: 1/-1; }
  .analytics-title {
    font-family:'Orbitron', sans-serif; font-size:9px; letter-spacing:2.5px;
    text-transform:uppercase; color:var(--text3); margin-bottom:14px;
  }

  /* bar chart */
  .lang-bar { display:flex; align-items:center; gap:10px; margin-bottom:8px; }
  .lang-name { font-size:11px; color:var(--text2); width:65px; flex-shrink:0; font-family:'JetBrains Mono',monospace; }
  .lang-track { flex:1; height:6px; background:rgba(255,255,255,0.06); border-radius:3px; overflow:hidden; }
  .lang-fill { height:100%; border-radius:3px; transition:width 1s ease; }
  .lang-pct { font-size:10px; color:var(--text3); font-family:'JetBrains Mono',monospace; width:30px; text-align:right; flex-shrink:0; }

  /* contribution calendar mock */
  .contrib-grid { display:flex; gap:3px; }
  .contrib-week { display:flex; flex-direction:column; gap:3px; }
  .contrib-day {
    width:11px; height:11px; border-radius:2px;
  }

  /* activity chart */
  .activity-bars { display:flex; align-items:flex-end; gap:4px; height:60px; }
  .act-bar {
    flex:1; border-radius:3px 3px 0 0; min-height:4px;
    transition:height 1s ease;
  }

  /* ─── WORKSPACE SCENE ─── */
  .workspace-scene {
    border-radius:20px; border:1px solid var(--border2); overflow:hidden;
    position:relative; margin-bottom:24px;
    background: linear-gradient(160deg, #0d0a1a 0%, #040810 40%, #0a0f0d 100%);
    padding:30px 30px 0;
  }
  .ws-glow-top {
    position:absolute; top:-60px; left:50%; transform:translateX(-50%);
    width:400px; height:200px;
    background: radial-gradient(ellipse, rgba(139,92,246,0.2) 0%, transparent 70%);
    pointer-events:none;
  }

  /* monitor */
  .monitor-wrap { position:relative; display:flex; justify-content:center; }
  .monitor {
    width:88%; max-width:700px; background:#0a0d14;
    border-radius:16px 16px 4px 4px;
    border:2px solid rgba(139,92,246,0.4);
    box-shadow:0 0 60px rgba(139,92,246,0.2), 0 0 120px rgba(59,130,246,0.1), inset 0 1px 0 rgba(255,255,255,0.05);
    overflow:hidden; position:relative;
  }
  .monitor-bar {
    background:#0d1020; padding:8px 14px;
    display:flex; align-items:center; gap:6px;
    border-bottom:1px solid rgba(139,92,246,0.15);
  }
  .m-dot { width:10px; height:10px; border-radius:50%; }
  .m-dot:nth-child(1){ background:#ff5f57; }
  .m-dot:nth-child(2){ background:#febc2e; }
  .m-dot:nth-child(3){ background:#28c840; }
  .m-tabs { margin-left:12px; display:flex; gap:8px; }
  .m-tab { font-size:9px; letter-spacing:1px; padding:3px 10px; border-radius:4px; color:var(--text3); }
  .m-tab.active { background:rgba(139,92,246,0.2); color:var(--purple3); border:1px solid rgba(139,92,246,0.3); }
  .monitor-screen { padding:16px; display:grid; grid-template-columns:1fr 1fr; gap:10px; min-height:200px; }

  .ms-panel {
    background:rgba(0,0,0,0.4); border:1px solid rgba(139,92,246,0.15); border-radius:8px; padding:12px;
  }
  .ms-title { font-size:8px; letter-spacing:2px; text-transform:uppercase; color:var(--text3); margin-bottom:8px; }
  .code-line { font-family:'JetBrains Mono',monospace; font-size:9px; line-height:1.8; }
  .c-kw { color:#f0859c; }
  .c-fn { color:#60a5fa; }
  .c-str { color:#86efac; }
  .c-var { color:#c4b5fd; }
  .c-num { color:#fcd34d; }
  .c-cm { color:#475569; }

  /* desk items */
  .desk-base {
    width:88%; max-width:700px; margin:0 auto;
    height:12px; background:linear-gradient(180deg, #2a1f10, #1a1208);
    border-radius:0 0 4px 4px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.8);
  }
  .desk-surface {
    padding: 10px 6% 0;
    display:flex; justify-content:space-between; align-items:flex-end;
  }
  .keyboard-wrap { display:flex; flex-direction:column; gap:3px; margin-bottom:4px; }
  .kb-row { display:flex; gap:2px; }
  .kb-key {
    width:14px; height:9px; background:#1a1a2e;
    border-radius:2px; border:1px solid rgba(139,92,246,0.3);
    box-shadow:0 0 4px rgba(139,92,246,0.15);
  }
  .kb-key.space { width:70px; }
  .coffee-mug { font-size:28px; margin-bottom:2px; }
  .book-stack { display:flex; flex-direction:column; gap:2px; margin-bottom:4px; }
  .book { height:14px; border-radius:2px; border:1px solid rgba(255,255,255,0.1); }

  /* ─── WAVE DIVIDER ─── */
  .section-gap { height:8px; }

  /* ─── FOOTER ─── */
  .readme-footer {
    text-align:center; padding:32px; margin-top:16px;
    border-top:1px solid var(--border);
  }
  .footer-text { font-size:11px; color:var(--text3); letter-spacing:2px; text-transform:uppercase; }
  .footer-glow {
    font-family:'Orbitron', sans-serif; font-size:9px; letter-spacing:3px;
    color:var(--purple3); margin-top:8px;
  }

  /* ─── ANIMATIONS ─── */
  @keyframes fade-in {
    from{ opacity:0; transform:translateY(-6px); }
    to{ opacity:1; transform:translateY(0); }
  }
  .animate-in { animation: fade-in 0.7s ease both; }

  /* neon glow text */
  .glow-text {
    text-shadow: 0 0 20px rgba(139,92,246,0.5), 0 0 40px rgba(139,92,246,0.2);
  }

  /* scrollbar */
  ::-webkit-scrollbar { width:6px; }
  ::-webkit-scrollbar-track { background:var(--navy); }
  ::-webkit-scrollbar-thumb { background:rgba(139,92,246,0.4); border-radius:3px; }

  /* responsive */
  @media(max-width:640px){
    .hero-inner{ flex-direction:column; align-items:center; text-align:center; }
    .hero-subtitle{ justify-content:center; }
    .analytics-grid{ grid-template-columns:1fr; }
    .analytics-card:first-child{ grid-column:1; }
    .hero-deco{ display:none; }
  }
</style>
</head>
<body>

<!-- ── Background ── -->
<div class="bg-layer">
  <div class="bg-orb"></div>
  <div class="bg-orb"></div>
  <div class="bg-orb"></div>
</div>
<div class="grid-lines"></div>
<div class="particles" id="particles"></div>

<div class="readme-wrap">

  <!-- ══════════════════════════════════════
       HERO BANNER
  ══════════════════════════════════════ -->
  <div class="hero">
    <div class="hero-deco" aria-hidden="true">
      <!-- Floating SVG decorative charts -->
      <svg width="260" height="320" viewBox="0 0 260 320" fill="none" xmlns="http://www.w3.org/2000/svg" style="position:absolute;top:0;right:0;opacity:0.3;">
        <!-- Neural net nodes -->
        <circle cx="200" cy="60" r="8" fill="#7c3aed" opacity="0.6"/>
        <circle cx="160" cy="100" r="6" fill="#06b6d4" opacity="0.5"/>
        <circle cx="220" cy="120" r="5" fill="#a855f7" opacity="0.4"/>
        <circle cx="180" cy="160" r="7" fill="#3b82f6" opacity="0.5"/>
        <circle cx="240" cy="180" r="5" fill="#06b6d4" opacity="0.4"/>
        <circle cx="200" cy="220" r="6" fill="#7c3aed" opacity="0.5"/>
        <line x1="200" y1="60" x2="160" y2="100" stroke="#7c3aed" stroke-width="0.5" opacity="0.4"/>
        <line x1="200" y1="60" x2="220" y2="120" stroke="#06b6d4" stroke-width="0.5" opacity="0.4"/>
        <line x1="160" y1="100" x2="180" y2="160" stroke="#a855f7" stroke-width="0.5" opacity="0.4"/>
        <line x1="220" y1="120" x2="180" y2="160" stroke="#3b82f6" stroke-width="0.5" opacity="0.4"/>
        <line x1="220" y1="120" x2="240" y2="180" stroke="#06b6d4" stroke-width="0.5" opacity="0.4"/>
        <line x1="180" y1="160" x2="200" y2="220" stroke="#7c3aed" stroke-width="0.5" opacity="0.4"/>
        <line x1="240" y1="180" x2="200" y2="220" stroke="#3b82f6" stroke-width="0.5" opacity="0.4"/>
        <!-- Mini bar chart -->
        <rect x="150" y="240" width="12" height="30" rx="2" fill="#7c3aed" opacity="0.5"/>
        <rect x="168" y="220" width="12" height="50" rx="2" fill="#06b6d4" opacity="0.5"/>
        <rect x="186" y="230" width="12" height="40" rx="2" fill="#a855f7" opacity="0.5"/>
        <rect x="204" y="210" width="12" height="60" rx="2" fill="#3b82f6" opacity="0.5"/>
        <rect x="222" y="225" width="12" height="45" rx="2" fill="#ec4899" opacity="0.5"/>
        <line x1="148" y1="270" x2="238" y2="270" stroke="rgba(255,255,255,0.1)" stroke-width="0.5"/>
        <!-- Floating particles -->
        <circle cx="130" cy="40" r="2" fill="#c084fc" opacity="0.6">
          <animate attributeName="cy" values="40;30;40" dur="3s" repeatCount="indefinite"/>
        </circle>
        <circle cx="250" cy="90" r="1.5" fill="#22d3ee" opacity="0.5">
          <animate attributeName="cy" values="90;80;90" dur="4s" repeatCount="indefinite"/>
        </circle>
        <circle cx="140" cy="200" r="2" fill="#a855f7" opacity="0.4">
          <animate attributeName="cy" values="200;190;200" dur="5s" repeatCount="indefinite"/>
        </circle>
      </svg>
    </div>

    <div class="hero-inner">
      <!-- Avatar -->
      <div class="avatar-wrap" aria-label="Profile photo of Kraniksa Williams">
        <div class="avatar-ring">
          <div class="avatar-inner">
            <img src="/mnt/user-data/uploads/WhatsApp_Image_2024-04-13_at_12_48_07_f7d76685.jpg"
                 alt="Kraniksa Williams"
                 onerror="this.style.display='none'; this.parentNode.innerHTML='<span style=\'font-family:Orbitron,sans-serif;font-size:48px;font-weight:900;background:linear-gradient(135deg,#a855f7,#22d3ee);-webkit-background-clip:text;-webkit-text-fill-color:transparent;\'>KW</span>';">
            <div class="avatar-badge"></div>
          </div>
        </div>
        <div class="avatar-glow" aria-hidden="true"></div>
      </div>

      <!-- Text -->
      <div class="hero-text">
        <p class="hero-greeting">✦ &nbsp; Hi There! 👋 &nbsp; Welcome to my GitHub &nbsp; ✦</p>
        <h1 class="hero-name">KRANIKSA<br>WILLIAMS</h1>
        <div class="hero-subtitle">
          <span class="subtitle-tag">⚡ Data Analyst</span>
          <span class="subtitle-tag">🧠 AI & DS Graduate</span>
          <span class="subtitle-tag">🤖 ML Enthusiast</span>
          <span class="subtitle-tag">📊 Power BI Dev</span>
          <span class="subtitle-tag">🚀 Future Data Scientist</span>
        </div>
        <p class="hero-bio">
          Motivated <strong>AI & Data Science graduate</strong> with hands-on experience in
          Python, SQL, Power BI, and Machine Learning. Passionate about transforming raw data
          into <strong>actionable insights</strong> that drive business decisions.
          Building the future, one dataset at a time.
        </p>
      </div>
    </div>
  </div>


  <!-- ══════════════════════════════════════
       CONTACT & LINKS
  ══════════════════════════════════════ -->
  <div class="section-label">
    <div class="section-label-line"></div>
    <span class="section-label-text">◈ Connect with Me</span>
    <div class="section-label-line" style="background:linear-gradient(90deg,transparent,var(--purple))"></div>
  </div>

  <div class="contact-grid" style="margin-bottom:24px;">
    <div class="contact-item">
      <span class="contact-icon">📍</span>
      <div><strong style="color:var(--text)">Tamil Nadu, India</strong><span>Location</span></div>
    </div>
    <a class="contact-item" href="https://github.com/kraniksawilliams" target="_blank" rel="noopener">
      <span class="contact-icon">🐙</span>
      <div><strong>kraniksawilliams</strong><span>GitHub Profile</span></div>
    </a>
    <a class="contact-item" href="https://linkedin.com/in/kraniksa-w-56059b269" target="_blank" rel="noopener">
      <span class="contact-icon">💼</span>
      <div><strong>kraniksa-w</strong><span>LinkedIn</span></div>
    </a>
    <a class="contact-item" href="https://portfolio-eight-khaki-24.vercel.app" target="_blank" rel="noopener">
      <span class="contact-icon">🌐</span>
      <div><strong>Portfolio</strong><span>vercel.app</span></div>
    </a>
    <a class="contact-item" href="mailto:kraniksawilliamrojers2004@gmail.com">
      <span class="contact-icon">✉️</span>
      <div><strong>Email Me</strong><span>kraniksawilliamrojers2004</span></div>
    </a>
    <div class="contact-item">
      <span class="contact-icon">📄</span>
      <div><strong style="color:var(--text)">Data Analyst Resume</strong><span>Available on request</span></div>
    </div>
  </div>


  <!-- ══════════════════════════════════════
       STATS
  ══════════════════════════════════════ -->
  <div class="stats-strip">
    <div class="stat-card">
      <span class="stat-num" id="cnt-repos">15+</span>
      <span class="stat-label">Repositories</span>
    </div>
    <div class="stat-card">
      <span class="stat-num">6</span>
      <span class="stat-label">Projects</span>
    </div>
    <div class="stat-card">
      <span class="stat-num">3+</span>
      <span class="stat-label">ML Models</span>
    </div>
    <div class="stat-card">
      <span class="stat-num">5+</span>
      <span class="stat-label">BI Dashboards</span>
    </div>
    <div class="stat-card">
      <span class="stat-num">8.15</span>
      <span class="stat-label">CGPA</span>
    </div>
    <div class="stat-card">
      <span class="stat-num">∞</span>
      <span class="stat-label">Curiosity</span>
    </div>
  </div>


  <!-- ══════════════════════════════════════
       WORKSPACE SCENE
  ══════════════════════════════════════ -->
  <div class="section-label">
    <div class="section-label-line"></div>
    <span class="section-label-text">◈ My Dev Workspace</span>
    <div class="section-label-line" style="background:linear-gradient(90deg,transparent,var(--purple))"></div>
  </div>

  <div class="workspace-scene" style="margin-bottom:24px;">
    <div class="ws-glow-top" aria-hidden="true"></div>

    <!-- Stars -->
    <div aria-hidden="true" style="position:absolute;inset:0;overflow:hidden;pointer-events:none;">
      <div id="ws-stars"></div>
    </div>

    <!-- Shelf -->
    <div style="display:flex;justify-content:flex-end;margin-bottom:16px;padding-right:5%;position:relative;z-index:1;" aria-hidden="true">
      <div style="display:flex;align-items:flex-end;gap:6px;">
        <div class="book-stack">
          <div class="book" style="width:18px;background:#7c3aed;"></div>
          <div class="book" style="width:18px;background:#06b6d4;"></div>
          <div class="book" style="width:22px;background:#ec4899;"></div>
          <div class="book" style="width:18px;background:#3b82f6;"></div>
        </div>
        <div class="book-stack">
          <div class="book" style="width:20px;background:#f59e0b;"></div>
          <div class="book" style="width:20px;background:#10b981;"></div>
          <div class="book" style="width:16px;background:#a855f7;"></div>
        </div>
        <span style="font-size:20px;margin-bottom:2px;">🏆</span>
        <span style="font-size:18px;margin-bottom:2px;">🤖</span>
        <span style="font-size:20px;margin-bottom:2px;">📚</span>
      </div>
    </div>
    <div style="width:88%;max-width:700px;margin:0 auto;height:1px;background:rgba(139,92,246,0.2);margin-bottom:12px;box-shadow:0 0 10px rgba(139,92,246,0.2);" aria-hidden="true"></div>

    <!-- Monitor -->
    <div class="monitor-wrap" role="img" aria-label="Developer workspace with analytics dashboard on monitor">
      <div class="monitor">
        <div class="monitor-bar" aria-hidden="true">
          <div class="m-dot"></div><div class="m-dot"></div><div class="m-dot"></div>
          <div class="m-tabs">
            <div class="m-tab active">analytics.py</div>
            <div class="m-tab">dashboard.pbix</div>
            <div class="m-tab">fraud_model.ipynb</div>
          </div>
        </div>
        <div class="monitor-screen" aria-hidden="true">
          <!-- Code panel -->
          <div class="ms-panel">
            <div class="ms-title">🐍 Python · Fraud Detection Model</div>
            <div class="code-line"><span class="c-kw">import</span> <span class="c-var">pandas</span> <span class="c-kw">as</span> <span class="c-var">pd</span></div>
            <div class="code-line"><span class="c-kw">from</span> <span class="c-var">sklearn</span> <span class="c-kw">import</span> <span class="c-fn">RandomForest</span></div>
            <div class="code-line"><span class="c-kw">from</span> <span class="c-var">imblearn</span> <span class="c-kw">import</span> <span class="c-fn">SMOTE</span></div>
            <div class="code-line" style="margin-top:4px;"><span class="c-cm"># Load & preprocess data</span></div>
            <div class="code-line"><span class="c-var">df</span> = <span class="c-fn">pd.read_csv</span>(<span class="c-str">'transactions.csv'</span>)</div>
            <div class="code-line"><span class="c-var">X</span>, <span class="c-var">y</span> = <span class="c-fn">preprocess</span>(<span class="c-var">df</span>)</div>
            <div class="code-line" style="margin-top:4px;"><span class="c-cm"># Balance classes</span></div>
            <div class="code-line"><span class="c-var">X_res</span>, <span class="c-var">y_res</span> = <span class="c-fn">SMOTE</span>().<span class="c-fn">fit_resample</span>(<span class="c-var">X</span>,<span class="c-var">y</span>)</div>
            <div class="code-line"><span class="c-var">model</span>.<span class="c-fn">fit</span>(<span class="c-var">X_res</span>, <span class="c-var">y_res</span>)</div>
            <div class="code-line"><span class="c-cm"># Accuracy: 97.3% ✓</span></div>
          </div>
          <!-- Dashboard panel -->
          <div class="ms-panel" style="display:flex;flex-direction:column;gap:8px;">
            <div class="ms-title">📊 Power BI · KPI Dashboard</div>
            <!-- Mini chart -->
            <div style="display:flex;align-items:flex-end;gap:3px;height:50px;">
              <div style="flex:1;background:linear-gradient(180deg,#7c3aed,#4c1d95);border-radius:2px 2px 0 0;height:60%;"></div>
              <div style="flex:1;background:linear-gradient(180deg,#06b6d4,#0e7490);border-radius:2px 2px 0 0;height:80%;"></div>
              <div style="flex:1;background:linear-gradient(180deg,#ec4899,#9d174d);border-radius:2px 2px 0 0;height:45%;"></div>
              <div style="flex:1;background:linear-gradient(180deg,#f59e0b,#92400e);border-radius:2px 2px 0 0;height:90%;"></div>
              <div style="flex:1;background:linear-gradient(180deg,#10b981,#065f46);border-radius:2px 2px 0 0;height:70%;"></div>
              <div style="flex:1;background:linear-gradient(180deg,#3b82f6,#1e3a8a);border-radius:2px 2px 0 0;height:100%;"></div>
            </div>
            <div style="display:grid;grid-template-columns:1fr 1fr;gap:6px;">
              <div style="background:rgba(139,92,246,0.15);border-radius:4px;padding:6px;text-align:center;">
                <div style="font-family:'Orbitron',sans-serif;font-size:14px;color:#c4b5fd;">97.3%</div>
                <div style="font-size:8px;color:#64748b;letter-spacing:1px;">ACCURACY</div>
              </div>
              <div style="background:rgba(6,182,212,0.12);border-radius:4px;padding:6px;text-align:center;">
                <div style="font-family:'Orbitron',sans-serif;font-size:14px;color:#67e8f9;">10K+</div>
                <div style="font-size:8px;color:#64748b;letter-spacing:1px;">CUSTOMERS</div>
              </div>
            </div>
            <div style="font-size:9px;color:#334155;font-family:'JetBrains Mono',monospace;">
              SELECT COUNT(*) FROM fraud_alerts<br>WHERE risk_score &gt; 0.8;
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Desk surface items -->
    <div class="desk-base" aria-hidden="true"></div>
    <div class="desk-surface" aria-hidden="true">
      <div class="keyboard-wrap">
        <div class="kb-row">
          <div class="kb-key"></div><div class="kb-key"></div><div class="kb-key"></div>
          <div class="kb-key"></div><div class="kb-key"></div><div class="kb-key"></div>
          <div class="kb-key"></div><div class="kb-key"></div><div class="kb-key"></div>
          <div class="kb-key"></div><div class="kb-key"></div><div class="kb-key"></div>
        </div>
        <div class="kb-row">
          <div class="kb-key"></div><div class="kb-key"></div><div class="kb-key"></div>
          <div class="kb-key"></div><div class="kb-key"></div><div class="kb-key"></div>
          <div class="kb-key"></div><div class="kb-key"></div><div class="kb-key"></div>
          <div class="kb-key"></div><div class="kb-key"></div>
        </div>
        <div class="kb-row"><div class="kb-key space"></div></div>
      </div>
      <div class="coffee-mug" role="img" aria-label="Coffee mug">☕</div>
    </div>

    <!-- Ambient glow at bottom -->
    <div aria-hidden="true" style="position:absolute;bottom:0;left:50%;transform:translateX(-50%);width:80%;height:40px;background:radial-gradient(ellipse,rgba(139,92,246,0.15) 0%,transparent 70%);pointer-events:none;"></div>
  </div>


  <!-- ══════════════════════════════════════
       EXPERIENCE
  ══════════════════════════════════════ -->
  <div class="section-label">
    <div class="section-label-line"></div>
    <span class="section-label-text">◈ Professional Experience</span>
    <div class="section-label-line" style="background:linear-gradient(90deg,transparent,var(--purple))"></div>
  </div>

  <div style="margin-bottom:24px;">
    <div class="exp-item">
      <div class="exp-dot" aria-hidden="true">💼</div>
      <div style="flex:1;">
        <div class="exp-role">Data Science Intern</div>
        <div class="exp-company">ETHER SERVICES PVT. LTD. &nbsp;·&nbsp; Tamil Nadu, India</div>
        <div class="exp-period">📅 Jan 2026 – Jun 2026</div>
        <ul class="exp-bullets">
          <li>Built ETL pipelines using Python (Pandas, NumPy) and SQL to clean and validate large business datasets, improving data quality for analytical workflows.</li>
          <li>Developed 5+ Power BI and Excel dashboards to monitor KPIs, enabling real-time stakeholder visibility and reducing manual reporting effort.</li>
          <li>Conducted EDA to uncover trends and produce strategic recommendations adopted by business leadership.</li>
          <li>Collaborated with cross-functional teams to define BI requirements and align dashboard outputs with organizational goals.</li>
        </ul>
      </div>
    </div>
  </div>


  <!-- ══════════════════════════════════════
       SKILLS
  ══════════════════════════════════════ -->
  <div class="section-label">
    <div class="section-label-line"></div>
    <span class="section-label-text">◈ Technical Arsenal</span>
    <div class="section-label-line" style="background:linear-gradient(90deg,transparent,var(--purple))"></div>
  </div>

  <div class="skills-grid" style="margin-bottom:24px;">
    <div class="skill-group">
      <div class="skill-group-title">⚡ Languages</div>
      <div class="skill-tags">
        <span class="skill-tag st-purple">Python</span>
        <span class="skill-tag st-purple">SQL</span>
        <span class="skill-tag st-purple">Java</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">📊 Data Analytics</div>
      <div class="skill-tags">
        <span class="skill-tag st-cyan">EDA</span>
        <span class="skill-tag st-cyan">Data Cleaning</span>
        <span class="skill-tag st-cyan">Statistical Analysis</span>
        <span class="skill-tag st-cyan">Visualization</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">📦 Libraries</div>
      <div class="skill-tags">
        <span class="skill-tag st-blue">Pandas</span>
        <span class="skill-tag st-blue">NumPy</span>
        <span class="skill-tag st-blue">Matplotlib</span>
        <span class="skill-tag st-blue">Seaborn</span>
        <span class="skill-tag st-blue">Scikit-Learn</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">🗄️ Databases</div>
      <div class="skill-tags">
        <span class="skill-tag st-green">MySQL</span>
        <span class="skill-tag st-green">MongoDB</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">🤖 Machine Learning</div>
      <div class="skill-tags">
        <span class="skill-tag st-pink">Scikit-Learn</span>
        <span class="skill-tag st-pink">Classification</span>
        <span class="skill-tag st-pink">Clustering</span>
        <span class="skill-tag st-pink">SMOTE</span>
        <span class="skill-tag st-pink">CNN</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">🛠️ Tools & Platforms</div>
      <div class="skill-tags">
        <span class="skill-tag st-gold">Power BI</span>
        <span class="skill-tag st-gold">Git / GitHub</span>
        <span class="skill-tag st-gold">Jupyter</span>
        <span class="skill-tag st-gold">VS Code</span>
        <span class="skill-tag st-gold">Google Colab</span>
        <span class="skill-tag st-gold">Excel</span>
      </div>
    </div>
  </div>


  <!-- ══════════════════════════════════════
       PROJECTS
  ══════════════════════════════════════ -->
  <div class="section-label">
    <div class="section-label-line"></div>
    <span class="section-label-text">◈ Featured Projects</span>
    <div class="section-label-line" style="background:linear-gradient(90deg,transparent,var(--purple))"></div>
  </div>

  <div class="projects-grid" style="margin-bottom:24px;">

    <div class="project-card pc-fraud">
      <div class="project-card-top">
        <div class="project-icon">🛡️</div>
        <span class="project-arrow">↗</span>
      </div>
      <div class="project-title">Financial Fraud Detection & Analytics</div>
      <p class="project-desc">Logistic Regression & Random Forest models for fraud detection with SMOTE for class imbalance. Power BI risk dashboards visualizing fraud patterns and alert trends.</p>
      <div class="project-tags">
        <span class="project-tag" style="background:rgba(236,72,153,0.15);color:#f9a8d4;">Python</span>
        <span class="project-tag" style="background:rgba(236,72,153,0.15);color:#f9a8d4;">Scikit-Learn</span>
        <span class="project-tag" style="background:rgba(236,72,153,0.15);color:#f9a8d4;">Power BI</span>
        <span class="project-tag" style="background:rgba(236,72,153,0.15);color:#f9a8d4;">SMOTE</span>
        <span class="project-tag" style="background:rgba(236,72,153,0.15);color:#f9a8d4;">SQL</span>
      </div>
    </div>

    <div class="project-card pc-seg">
      <div class="project-card-top">
        <div class="project-icon">👥</div>
        <span class="project-arrow">↗</span>
      </div>
      <div class="project-title">Customer Segmentation & Behavioral Analysis</div>
      <p class="project-desc">Segmented 10,000+ customers into 4 behavioral clusters via K-Means. Power BI dashboards surfacing purchasing trends and customer lifetime value metrics.</p>
      <div class="project-tags">
        <span class="project-tag" style="background:rgba(6,182,212,0.12);color:#67e8f9;">K-Means</span>
        <span class="project-tag" style="background:rgba(6,182,212,0.12);color:#67e8f9;">Python</span>
        <span class="project-tag" style="background:rgba(6,182,212,0.12);color:#67e8f9;">Power BI</span>
        <span class="project-tag" style="background:rgba(6,182,212,0.12);color:#67e8f9;">EDA</span>
        <span class="project-tag" style="background:rgba(6,182,212,0.12);color:#67e8f9;">SQL</span>
      </div>
    </div>

    <div class="project-card pc-aqi">
      <div class="project-card-top">
        <div class="project-icon">🌬️</div>
        <span class="project-arrow">↗</span>
      </div>
      <div class="project-title">AQI Prediction System</div>
      <p class="project-desc">Machine learning system to predict Air Quality Index from environmental sensor data. Regression models with feature engineering and real-time visualization dashboards.</p>
      <div class="project-tags">
        <span class="project-tag" style="background:rgba(16,185,129,0.12);color:#6ee7b7;">Python</span>
        <span class="project-tag" style="background:rgba(16,185,129,0.12);color:#6ee7b7;">Regression</span>
        <span class="project-tag" style="background:rgba(16,185,129,0.12);color:#6ee7b7;">Pandas</span>
        <span class="project-tag" style="background:rgba(16,185,129,0.12);color:#6ee7b7;">Matplotlib</span>
      </div>
    </div>

    <div class="project-card pc-deep">
      <div class="project-card-top">
        <div class="project-icon">🎭</div>
        <span class="project-arrow">↗</span>
      </div>
      <div class="project-title">Deep Audio/Video Fake Detection</div>
      <p class="project-desc">CNN-based binary classification framework for detecting manipulated media using deep feature extraction. Optimized across Accuracy, Precision, Recall, and F1-Score.</p>
      <div class="project-tags">
        <span class="project-tag" style="background:rgba(139,92,246,0.12);color:#c4b5fd;">CNN</span>
        <span class="project-tag" style="background:rgba(139,92,246,0.12);color:#c4b5fd;">Deep Learning</span>
        <span class="project-tag" style="background:rgba(139,92,246,0.12);color:#c4b5fd;">Computer Vision</span>
        <span class="project-tag" style="background:rgba(139,92,246,0.12);color:#c4b5fd;">Python</span>
      </div>
    </div>

    <div class="project-card pc-plate">
      <div class="project-card-top">
        <div class="project-icon">🚗</div>
        <span class="project-arrow">↗</span>
      </div>
      <div class="project-title">License Plate Recognition</div>
      <p class="project-desc">Automated license plate detection and character recognition system using computer vision and OCR. Real-time recognition pipeline with high accuracy on diverse plate formats.</p>
      <div class="project-tags">
        <span class="project-tag" style="background:rgba(245,158,11,0.12);color:#fcd34d;">OpenCV</span>
        <span class="project-tag" style="background:rgba(245,158,11,0.12);color:#fcd34d;">Python</span>
        <span class="project-tag" style="background:rgba(245,158,11,0.12);color:#fcd34d;">OCR</span>
        <span class="project-tag" style="background:rgba(245,158,11,0.12);color:#fcd34d;">CV</span>
      </div>
    </div>

    <div class="project-card pc-tour">
      <div class="project-card-top">
        <div class="project-icon">✈️</div>
        <span class="project-arrow">↗</span>
      </div>
      <div class="project-title">Tourism Management System</div>
      <p class="project-desc">Full-stack tourism platform with database-backed booking, itinerary management, and analytics dashboard. SQL-powered backend with data-driven recommendation engine.</p>
      <div class="project-tags">
        <span class="project-tag" style="background:rgba(59,130,246,0.12);color:#93c5fd;">SQL</span>
        <span class="project-tag" style="background:rgba(59,130,246,0.12);color:#93c5fd;">Python</span>
        <span class="project-tag" style="background:rgba(59,130,246,0.12);color:#93c5fd;">MySQL</span>
        <span class="project-tag" style="background:rgba(59,130,246,0.12);color:#93c5fd;">Analytics</span>
      </div>
    </div>

  </div>


  <!-- ══════════════════════════════════════
       GITHUB ANALYTICS
  ══════════════════════════════════════ -->
  <div class="section-label">
    <div class="section-label-line"></div>
    <span class="section-label-text">◈ GitHub Analytics Dashboard</span>
    <div class="section-label-line" style="background:linear-gradient(90deg,transparent,var(--purple))"></div>
  </div>

  <div class="analytics-grid" style="margin-bottom:24px;">

    <!-- Contribution Calendar -->
    <div class="analytics-card">
      <div class="analytics-title">◈ Contribution Activity · 2024–2025</div>
      <div class="contrib-grid" id="contrib-cal" aria-label="GitHub contribution calendar visualization" style="flex-wrap:wrap;gap:2px;" role="img">
        <!-- Generated by JS -->
      </div>
      <div style="display:flex;gap:6px;align-items:center;margin-top:10px;">
        <span style="font-size:10px;color:var(--text3);">Less</span>
        <div style="width:10px;height:10px;border-radius:2px;background:rgba(139,92,246,0.1);"></div>
        <div style="width:10px;height:10px;border-radius:2px;background:rgba(139,92,246,0.3);"></div>
        <div style="width:10px;height:10px;border-radius:2px;background:rgba(139,92,246,0.5);"></div>
        <div style="width:10px;height:10px;border-radius:2px;background:rgba(139,92,246,0.75);"></div>
        <div style="width:10px;height:10px;border-radius:2px;background:#a855f7;"></div>
        <span style="font-size:10px;color:var(--text3);">More</span>
      </div>
    </div>

    <!-- Top Languages -->
    <div class="analytics-card">
      <div class="analytics-title">◈ Top Languages</div>
      <div class="lang-bar">
        <span class="lang-name">Python</span>
        <div class="lang-track"><div class="lang-fill" style="width:72%;background:linear-gradient(90deg,#7c3aed,#a855f7);"></div></div>
        <span class="lang-pct">72%</span>
      </div>
      <div class="lang-bar">
        <span class="lang-name">SQL</span>
        <div class="lang-track"><div class="lang-fill" style="width:15%;background:linear-gradient(90deg,#06b6d4,#22d3ee);"></div></div>
        <span class="lang-pct">15%</span>
      </div>
      <div class="lang-bar">
        <span class="lang-name">Jupyter</span>
        <div class="lang-track"><div class="lang-fill" style="width:8%;background:linear-gradient(90deg,#f59e0b,#fcd34d);"></div></div>
        <span class="lang-pct">8%</span>
      </div>
      <div class="lang-bar">
        <span class="lang-name">Java</span>
        <div class="lang-track"><div class="lang-fill" style="width:5%;background:linear-gradient(90deg,#ec4899,#f9a8d4);"></div></div>
        <span class="lang-pct">5%</span>
      </div>
    </div>

    <!-- Activity Chart -->
    <div class="analytics-card">
      <div class="analytics-title">◈ Commit Activity · Last 12 Months</div>
      <div class="activity-bars" aria-label="Monthly commit activity bar chart">
        <div class="act-bar" style="height:45%;background:linear-gradient(180deg,#7c3aed,rgba(124,58,237,0.3));" title="Jul"></div>
        <div class="act-bar" style="height:60%;background:linear-gradient(180deg,#7c3aed,rgba(124,58,237,0.3));" title="Aug"></div>
        <div class="act-bar" style="height:35%;background:linear-gradient(180deg,#7c3aed,rgba(124,58,237,0.3));" title="Sep"></div>
        <div class="act-bar" style="height:80%;background:linear-gradient(180deg,#a855f7,rgba(168,85,247,0.3));" title="Oct"></div>
        <div class="act-bar" style="height:55%;background:linear-gradient(180deg,#7c3aed,rgba(124,58,237,0.3));" title="Nov"></div>
        <div class="act-bar" style="height:70%;background:linear-gradient(180deg,#a855f7,rgba(168,85,247,0.3));" title="Dec"></div>
        <div class="act-bar" style="height:90%;background:linear-gradient(180deg,#c084fc,rgba(192,132,252,0.3));" title="Jan"></div>
        <div class="act-bar" style="height:65%;background:linear-gradient(180deg,#a855f7,rgba(168,85,247,0.3));" title="Feb"></div>
        <div class="act-bar" style="height:100%;background:linear-gradient(180deg,#c084fc,rgba(192,132,252,0.3));" title="Mar"></div>
        <div class="act-bar" style="height:78%;background:linear-gradient(180deg,#a855f7,rgba(168,85,247,0.3));" title="Apr"></div>
        <div class="act-bar" style="height:85%;background:linear-gradient(180deg,#c084fc,rgba(192,132,252,0.3));" title="May"></div>
        <div class="act-bar" style="height:92%;background:linear-gradient(180deg,#e879f9,rgba(232,121,249,0.3));" title="Jun"></div>
      </div>
      <div style="display:flex;justify-content:space-between;margin-top:6px;">
        <span style="font-size:9px;color:var(--text3);letter-spacing:1px;">JUL</span>
        <span style="font-size:9px;color:var(--text3);letter-spacing:1px;">SEP</span>
        <span style="font-size:9px;color:var(--text3);letter-spacing:1px;">NOV</span>
        <span style="font-size:9px;color:var(--text3);letter-spacing:1px;">JAN</span>
        <span style="font-size:9px;color:var(--text3);letter-spacing:1px;">MAR</span>
        <span style="font-size:9px;color:var(--text3);letter-spacing:1px;">MAY</span>
        <span style="font-size:9px;color:var(--text3);letter-spacing:1px;">JUN</span>
      </div>
    </div>

    <!-- Quick metrics -->
    <div class="analytics-card" style="display:flex;flex-direction:column;gap:12px;">
      <div class="analytics-title">◈ Profile Metrics</div>
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:8px;">
        <div style="background:rgba(139,92,246,0.1);border:1px solid rgba(139,92,246,0.2);border-radius:8px;padding:10px;text-align:center;">
          <div style="font-family:'Orbitron',sans-serif;font-size:18px;color:#c4b5fd;">15+</div>
          <div style="font-size:9px;color:var(--text3);letter-spacing:1px;margin-top:2px;">REPOS</div>
        </div>
        <div style="background:rgba(6,182,212,0.08);border:1px solid rgba(6,182,212,0.2);border-radius:8px;padding:10px;text-align:center;">
          <div style="font-family:'Orbitron',sans-serif;font-size:18px;color:#67e8f9;">200+</div>
          <div style="font-size:9px;color:var(--text3);letter-spacing:1px;margin-top:2px;">COMMITS</div>
        </div>
        <div style="background:rgba(16,185,129,0.08);border:1px solid rgba(16,185,129,0.2);border-radius:8px;padding:10px;text-align:center;">
          <div style="font-family:'Orbitron',sans-serif;font-size:18px;color:#6ee7b7;">50+</div>
          <div style="font-size:9px;color:var(--text3);letter-spacing:1px;margin-top:2px;">CONTRIB</div>
        </div>
        <div style="background:rgba(245,158,11,0.08);border:1px solid rgba(245,158,11,0.2);border-radius:8px;padding:10px;text-align:center;">
          <div style="font-family:'Orbitron',sans-serif;font-size:18px;color:#fcd34d;">A+</div>
          <div style="font-size:9px;color:var(--text3);letter-spacing:1px;margin-top:2px;">STREAK</div>
        </div>
      </div>
    </div>

  </div>


  <!-- ══════════════════════════════════════
       EDUCATION
  ══════════════════════════════════════ -->
  <div class="section-label">
    <div class="section-label-line"></div>
    <span class="section-label-text">◈ Education</span>
    <div class="section-label-line" style="background:linear-gradient(90deg,transparent,var(--purple))"></div>
  </div>

  <div class="edu-grid" style="margin-bottom:24px;">
    <div class="edu-card">
      <div class="edu-icon" aria-hidden="true">🎓</div>
      <div>
        <div class="edu-degree">B.Tech — AI & Data Science</div>
        <div class="edu-school">Muthayammal College of Engineering</div>
        <div class="edu-detail">CGPA: <strong style="color:var(--purple3)">8.15 / 10.0</strong> &nbsp;·&nbsp; 2022 – 2026</div>
      </div>
    </div>
    <div class="edu-card">
      <div class="edu-icon" aria-hidden="true">📚</div>
      <div>
        <div class="edu-degree">Class XII — Higher Secondary</div>
        <div class="edu-school">Selvam Matric Higher Sec School</div>
        <div class="edu-detail">Score: <strong style="color:var(--cyan2)">76%</strong> &nbsp;·&nbsp; 2021 – 2022</div>
      </div>
    </div>
    <div class="edu-card">
      <div class="edu-icon" aria-hidden="true">🏫</div>
      <div>
        <div class="edu-degree">Class X — Secondary</div>
        <div class="edu-school">The Spectrum Academy</div>
        <div class="edu-detail">Score: <strong style="color:var(--green)">89.8%</strong> &nbsp;·&nbsp; 2019 – 2020</div>
      </div>
    </div>
  </div>


  <!-- ══════════════════════════════════════
       FOOTER
  ══════════════════════════════════════ -->
  <div class="readme-footer">
    <div style="display:flex;justify-content:center;gap:16px;margin-bottom:20px;flex-wrap:wrap;">
      <span style="font-size:20px;" title="Python" role="img" aria-label="Python">🐍</span>
      <span style="font-size:20px;" title="SQL" role="img" aria-label="SQL">🗃️</span>
      <span style="font-size:20px;" title="Machine Learning" role="img" aria-label="Machine Learning">🤖</span>
      <span style="font-size:20px;" title="Power BI" role="img" aria-label="Power BI">📊</span>
      <span style="font-size:20px;" title="Data Science" role="img" aria-label="Data Science">🔬</span>
      <span style="font-size:20px;" title="Deep Learning" role="img" aria-label="Deep Learning">🧠</span>
      <span style="font-size:20px;" title="Analytics" role="img" aria-label="Analytics">📈</span>
    </div>
    <p class="footer-text">Thanks for visiting! Let's connect and build something amazing together.</p>
    <p class="footer-glow" style="margin-top:12px;">
      ✦ &nbsp; KRANIKSA WILLIAMS &nbsp;·&nbsp; DATA ANALYST &nbsp;·&nbsp; AI & DATA SCIENCE &nbsp; ✦
    </p>
    <p style="font-size:10px;color:var(--text3);margin-top:16px;letter-spacing:1px;">
      © 2026 · Tamil Nadu, India · Made with 💜 & Data
    </p>
  </div>

</div>

<script>
  /* ── Particles ── */
  const pc = document.getElementById('particles');
  for(let i=0;i<30;i++){
    const p = document.createElement('div');
    p.className = 'particle';
    const size = Math.random()*4+2;
    p.style.cssText = `
      width:${size}px;height:${size}px;
      left:${Math.random()*100}%;
      animation-duration:${Math.random()*15+10}s;
      animation-delay:${Math.random()*-20}s;
    `;
    pc.appendChild(p);
  }

  /* ── Workspace stars ── */
  const ws = document.getElementById('ws-stars');
  if(ws){
    for(let i=0;i<60;i++){
      const s = document.createElement('div');
      const size = Math.random()*2+0.5;
      s.style.cssText = `
        position:absolute;
        width:${size}px;height:${size}px;
        border-radius:50%;
        background:#fff;
        left:${Math.random()*100}%;
        top:${Math.random()*60}%;
        opacity:${Math.random()*0.4+0.1};
      `;
      ws.appendChild(s);
    }
  }

  /* ── Contribution Calendar ── */
  const cal = document.getElementById('contrib-cal');
  const levels = [0,0,0,1,1,1,2,2,3,3,4];
  const colors = [
    'rgba(139,92,246,0.08)',
    'rgba(139,92,246,0.25)',
    'rgba(139,92,246,0.45)',
    'rgba(168,85,247,0.65)',
    '#a855f7'
  ];
  const totalWeeks = 52;
  for(let w=0;w<totalWeeks;w++){
    const wk = document.createElement('div');
    wk.className = 'contrib-week';
    for(let d=0;d<7;d++){
      const day = document.createElement('div');
      day.className = 'contrib-day';
      const lvl = levels[Math.floor(Math.random()*levels.length)];
      day.style.background = colors[lvl];
      day.setAttribute('aria-hidden','true');
      wk.appendChild(day);
    }
    cal.appendChild(wk);
  }

  /* ── Animate stats on scroll ── */
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if(e.isIntersecting){
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.15 });
  document.querySelectorAll('.glass-card,.stat-card,.project-card,.skill-group,.edu-card').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(20px)';
    el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
    observer.observe(el);
  });

  /* ── Monitor glow pulse ── */
  const monitor = document.querySelector('.monitor');
  if(monitor){
    setInterval(()=>{
      const intensity = 0.15 + Math.random()*0.1;
      monitor.style.boxShadow = `0 0 ${40+Math.random()*30}px rgba(139,92,246,${intensity}), 0 0 ${80+Math.random()*40}px rgba(59,130,246,0.06), inset 0 1px 0 rgba(255,255,255,0.05)`;
    }, 2000);
  }
</script>
</body>
</html>

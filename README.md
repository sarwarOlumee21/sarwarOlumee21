<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Sarwar Olumee | Backend Developer &amp; Laravel Enthusiast</title>
<meta name="description" content="Software Engineering student from Herat, Afghanistan. Backend developer focused on Laravel, Livewire and clean architecture.">
<meta name="theme-color" content="#0A1226">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,600..800&family=DM+Sans:wght@400;500;600&display=swap" rel="stylesheet">

<script>document.documentElement.classList.add('js');</script>

<style>
/* =========================================================
   Sarwar Olumee — Portfolio
   Visual idea: the turquoise tilework and eight-pointed
   geometric stars of Herat's Friday Mosque, drawn in code.
   Palette: lapis night, tile turquoise, saffron gold,
   and one small Laravel red.
========================================================= */

:root{
  --bg:#0A1226;
  --bg-2:#0F1A36;
  --surface:rgba(16,28,58,.72);
  --line:rgba(140,170,230,.16);
  --text:#E9EFFC;
  --muted:#A5B4D4;
  --turq:#3DD6C6;
  --gold:#F2B84B;
  --red:#FF2D20;

  --display:'Bricolage Grotesque','Segoe UI',system-ui,sans-serif;
  --body:'DM Sans','Segoe UI',system-ui,-apple-system,sans-serif;
  --mono:ui-monospace,'SF Mono',Menlo,Consolas,monospace;

  --ease:cubic-bezier(.2,.8,.2,1);
}

*,*::before,*::after{ box-sizing:border-box; }
html{ scroll-behavior:smooth; }
body{
  margin:0;
  font-family:var(--body);
  font-size:17px;
  line-height:1.7;
  color:var(--text);
  background:
    radial-gradient(900px 520px at 88% -6%, rgba(61,214,198,.14), transparent 62%),
    radial-gradient(700px 520px at -4% 32%, rgba(242,184,75,.07), transparent 60%),
    var(--bg);
  -webkit-font-smoothing:antialiased;
  overflow-x:hidden;
}

/* Tile lattice that fades out toward the bottom-left */
body::before{
  content:"";
  position:fixed; inset:0; z-index:-1; pointer-events:none;
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='88' height='88' viewBox='0 0 88 88' fill='none' stroke='%233DD6C6' stroke-opacity='.12'%3E%3Cpath d='M18 18h52v52H18zM44 7l37 37-37 37L7 44z'/%3E%3Cpath d='M0 0h.01M88 0h.01M0 88h.01M88 88h.01' stroke-width='3' stroke-linecap='round'/%3E%3C/svg%3E");
  -webkit-mask-image:radial-gradient(ellipse 80% 70% at 75% 0%, #000 0%, transparent 70%);
          mask-image:radial-gradient(ellipse 80% 70% at 75% 0%, #000 0%, transparent 70%);
}

img,svg{ max-width:100%; }
a{ color:inherit; text-decoration:none; }
ul{ list-style:none; margin:0; padding:0; }
h1,h2,h3,p,dl,dd,blockquote{ margin:0; }

:focus-visible{ outline:2px solid var(--gold); outline-offset:3px; border-radius:6px; }

.wrap{ width:min(1120px, 100% - 48px); margin-inline:auto; }

/* ---------- Icons ---------- */
.ic{ width:20px; height:20px; fill:none; stroke:currentColor; stroke-width:1.8; stroke-linecap:round; stroke-linejoin:round; flex:none; }
.ic-fill{ fill:currentColor; stroke:none; }

/* ---------- Scroll progress ---------- */
.progress{
  position:fixed; top:0; left:0; width:100%; height:3px; z-index:100;
  transform:scaleX(0); transform-origin:0 50%;
  background:linear-gradient(90deg,var(--turq),var(--gold));
}

/* ---------- Navigation ---------- */
.nav{
  position:sticky; top:0; z-index:50;
  backdrop-filter:blur(14px); -webkit-backdrop-filter:blur(14px);
  background:rgba(10,18,38,.62);
  border-bottom:1px solid transparent;
  transition:border-color .3s ease, background .3s ease;
}
.nav.scrolled{ border-bottom-color:var(--line); background:rgba(10,18,38,.86); }
.nav-in{ display:flex; align-items:center; justify-content:space-between; height:68px; }
.brand{ display:flex; align-items:center; gap:10px; font-family:var(--display); font-weight:700; font-size:18px; letter-spacing:-.01em; }
.brand .ic{ color:var(--gold); width:24px; height:24px; animation:spin 24s linear infinite; }
.nav nav{ display:flex; align-items:center; gap:30px; font-size:15px; font-weight:500; color:var(--muted); }
.nav nav a:not(.btn){ position:relative; padding:4px 0; transition:color .2s ease; }
.nav nav a:not(.btn)::after{
  content:""; position:absolute; left:0; right:0; bottom:-2px; height:2px; background:var(--turq);
  transform:scaleX(0); transform-origin:left; transition:transform .35s var(--ease);
}
.nav nav a:not(.btn):hover{ color:var(--text); }
.nav nav a:not(.btn):hover::after{ transform:scaleX(1); }

/* ---------- Buttons ---------- */
.btn{
  display:inline-flex; align-items:center; gap:10px;
  padding:14px 24px; border-radius:999px;
  font-weight:600; font-size:16px; line-height:1;
  border:1.5px solid var(--line); color:var(--text);
  transition:transform .25s var(--ease), background .25s ease, border-color .25s ease, color .25s ease, box-shadow .25s ease;
}
.btn:hover{ transform:translateY(-2px); border-color:var(--turq); }
.btn-primary{ background:var(--turq); color:#04272A; border-color:var(--turq); }
.btn-primary:hover{ box-shadow:0 10px 30px -8px rgba(61,214,198,.55); background:#5BE3D4; }
.btn-sm{ padding:10px 20px; font-size:15px; color:var(--text) !important; border-color:rgba(61,214,198,.5); }
.btn-sm:hover{ background:var(--turq); color:#04272A !important; }

/* =========================================================
   HERO
========================================================= */
.hero{ position:relative; padding:88px 0 96px; }
.hero-grid{ position:relative; z-index:1; display:grid; grid-template-columns:1.08fr .92fr; gap:56px; align-items:center; }

.rosette{
  position:absolute; z-index:0; pointer-events:none;
  right:-140px; top:50%; width:min(760px, 92vw); aspect-ratio:1;
  transform:translateY(-50%); opacity:.55;
}
.rosette .spin{ transform-origin:200px 200px; animation:spin 120s linear infinite; }
.dr{
  fill:none; stroke-width:.9;
  stroke-dasharray:1; stroke-dashoffset:1;
  animation:draw 2.6s ease forwards; animation-delay:var(--d,0s);
}
.dr.t{ stroke:var(--turq); }
.dr.g{ stroke:var(--gold); }

.name{
  font-family:var(--display); font-weight:800;
  font-size:clamp(50px, 8.2vw, 96px);
  line-height:1; letter-spacing:-.035em;
  margin-bottom:22px;
}
.name .w{ display:block; overflow:hidden; padding:.04em 0 .08em; }
.name .w > span{
  display:block; transform:translateY(108%);
  animation:rise 1s var(--ease) forwards; animation-delay:var(--d);
}

.roles{ display:flex; flex-wrap:wrap; align-items:center; gap:6px 0; margin-bottom:26px; font-family:var(--display); font-weight:600; font-size:clamp(17px,2vw,21px); color:var(--muted); }
.roles li + li::before{ content:""; display:inline-block; width:7px; height:7px; margin:0 16px; background:var(--gold); transform:rotate(45deg); vertical-align:middle; }
.roles li:last-child{ color:var(--text); }

.intro{ max-width:54ch; color:var(--muted); margin-bottom:34px; }
.cta{ display:flex; flex-wrap:wrap; gap:14px; }

.fade{ opacity:0; transform:translateY(14px); animation:fadeup .8s var(--ease) forwards; animation-delay:var(--d,0s); }

/* ---------- Terminal ---------- */
.term{
  border:1px solid var(--line); border-radius:16px;
  background:rgba(6,12,30,.82);
  backdrop-filter:blur(10px); -webkit-backdrop-filter:blur(10px);
  box-shadow:0 30px 80px -30px rgba(0,0,0,.7), 0 0 0 1px rgba(61,214,198,.05) inset;
  overflow:hidden;
}
.term-bar{ display:flex; align-items:center; gap:8px; padding:14px 18px; border-bottom:1px solid var(--line); font-family:var(--mono); font-size:13px; color:var(--muted); }
.term-bar i{ width:11px; height:11px; border-radius:50%; display:block; }
.term-bar i:nth-child(1){ background:var(--red); }
.term-bar i:nth-child(2){ background:var(--gold); }
.term-bar i:nth-child(3){ background:var(--turq); }
.term-bar span{ margin-left:10px; }

.term-body{ padding:24px 24px 26px; font-family:var(--mono); font-size:14.5px; line-height:1.7; }
.prompt{ color:var(--gold); margin-right:10px; }
.typed{
  display:inline-block; overflow:hidden; white-space:nowrap; vertical-align:bottom;
  width:0; border-right:2px solid var(--turq);
  animation:typing 1.4s steps(24) .9s forwards, caretoff 0s 2.3s forwards;
}
.out{ margin:16px 0 14px; display:grid; gap:9px; }
.out > div{
  display:grid; grid-template-columns:104px 1fr; gap:14px;
  opacity:0; transform:translateY(6px);
  animation:fadeup .5s ease forwards; animation-delay:calc(2.4s + var(--i) * .28s);
}
.out dt{ color:var(--turq); }
.out dd{ color:var(--text); }
.caret-line{ opacity:0; animation:fadeup .4s ease 4.5s forwards; }
.caret{ display:inline-block; width:9px; height:17px; background:var(--turq); vertical-align:text-bottom; animation:blink 1.1s steps(1) infinite; }

/* =========================================================
   SECTIONS
========================================================= */
.section{ padding:92px 0; scroll-margin-top:60px; }
.section-head{ margin-bottom:44px; max-width:640px; }
.section-head h2{ font-family:var(--display); font-weight:700; font-size:clamp(32px,4.4vw,48px); line-height:1.1; letter-spacing:-.025em; margin-bottom:12px; }
.section-head p{ color:var(--muted); }

.rule{ display:flex; align-items:center; gap:18px; color:var(--gold); }
.rule::before,.rule::after{ content:""; flex:1; height:1px; background:linear-gradient(90deg,transparent,var(--line),transparent); }
.rule .ic{ width:18px; height:18px; opacity:.8; }

/* Scroll reveal (only when JS is on, so no-JS visitors still see everything) */
.js .reveal{ opacity:0; transform:translateY(16px); transition:opacity .8s var(--ease), transform .8s var(--ease); }
.js .reveal.in{ opacity:1; transform:none; }

/* ---------- Stack (bento) ---------- */
.bento{ display:grid; grid-template-columns:repeat(12,1fr); gap:18px; }
.cell{
  position:relative;
  padding:28px; border:1px solid var(--line); border-radius:18px;
  background:var(--surface);
}
.cell h3{ display:flex; align-items:center; gap:12px; font-family:var(--display); font-size:21px; font-weight:700; margin-bottom:20px; }
.cell h3 .ic{ color:var(--turq); width:24px; height:24px; }
.c5{ grid-column:span 5; } .c7{ grid-column:span 7; } .c4{ grid-column:span 4; } .c8{ grid-column:span 8; }

.chips{ display:flex; flex-wrap:wrap; gap:10px; }
.chips li{
  display:inline-flex; align-items:center; gap:9px;
  padding:9px 16px; border-radius:999px;
  border:1px solid var(--line); background:rgba(10,18,38,.6);
  font-size:15px; font-weight:500;
  transition:border-color .25s ease, background .25s ease, transform .25s var(--ease);
}
.chips li::before{ content:""; width:7px; height:7px; border-radius:50%; background:var(--turq); }
.chips li.laravel::before{ background:var(--red); box-shadow:0 0 12px var(--red); }
.chips li.big{ font-size:17px; padding:11px 20px; }
.chips li:hover{ border-color:var(--turq); background:rgba(61,214,198,.09); transform:translateY(-3px); transition-delay:0s !important; }

.js .chips li{ opacity:0; transform:translateY(10px) scale(.96); transition:opacity .5s ease calc(var(--i) * 70ms + 150ms), transform .5s var(--ease) calc(var(--i) * 70ms + 150ms), border-color .25s ease, background .25s ease; }
.js .cell.in .chips li{ opacity:1; transform:none; }
.js .cell.in .chips li:hover{ transform:translateY(-3px); }

/* ---------- Ticker (core skills) ---------- */
.ticker{
  overflow:hidden; padding:22px 0;
  border-block:1px solid var(--line); background:rgba(15,26,54,.55);
  -webkit-mask-image:linear-gradient(90deg,transparent,#000 8%,#000 92%,transparent);
          mask-image:linear-gradient(90deg,transparent,#000 8%,#000 92%,transparent);
}
.ticker-track{ display:flex; width:max-content; animation:tick 46s linear infinite; }
.ticker:hover .ticker-track{ animation-play-state:paused; }
.ticker ul{ display:flex; align-items:center; gap:44px; padding-right:44px; }
.ticker li{ display:flex; align-items:center; gap:44px; font-family:var(--display); font-weight:600; font-size:clamp(20px,2.4vw,26px); white-space:nowrap; }
.ticker li::after{ content:""; width:9px; height:9px; background:var(--gold); transform:rotate(45deg); }

/* ---------- Learning ---------- */
.learn{ display:grid; grid-template-columns:1fr 1fr; gap:0 56px; }
.learn li{ position:relative; display:flex; align-items:center; gap:16px; padding:22px 0; font-family:var(--display); font-size:22px; font-weight:600; }
.learn li::after{
  content:""; position:absolute; left:0; right:0; bottom:0; height:1px;
  background:linear-gradient(90deg,var(--turq),rgba(61,214,198,.05));
}
.js .learn li::after{ transform:scaleX(0); transform-origin:left; transition:transform 1.1s var(--ease) calc(var(--i) * 110ms); }
.js .learn.in li::after{ transform:scaleX(1); }
.dot{ position:relative; width:10px; height:10px; border-radius:50%; background:var(--turq); flex:none; }
.dot::after{ content:""; position:absolute; inset:0; border-radius:50%; border:2px solid var(--turq); animation:ping 2.4s ease-out infinite; animation-delay:calc(var(--i) * .3s); }

/* ---------- Projects ---------- */
.projects{ display:grid; grid-template-columns:repeat(6,1fr); gap:20px; }
.card{
  --mx:50%; --my:50%;
  position:relative; overflow:hidden;
  padding:34px; border:1px solid var(--line); border-radius:20px;
  background:var(--surface);
  display:flex; flex-direction:column; gap:16px;
  transition:border-color .3s ease;
}
.card::after{
  content:""; position:absolute; inset:0; pointer-events:none; opacity:0; transition:opacity .35s ease;
  background:radial-gradient(340px circle at var(--mx) var(--my), rgba(61,214,198,.16), transparent 60%);
}
.card:hover{ border-color:rgba(61,214,198,.45); }
.card:hover::after{ opacity:1; }
.card > *{ position:relative; z-index:1; }
.p-wide{ grid-column:span 6; } .p-half{ grid-column:span 3; }
.p-icon{ width:52px; height:52px; border-radius:14px; display:grid; place-items:center; color:var(--turq); border:1px solid rgba(61,214,198,.35); background:rgba(61,214,198,.07); }
.p-icon .ic{ width:26px; height:26px; }
.card h3{ font-family:var(--display); font-size:clamp(24px,2.6vw,30px); font-weight:700; letter-spacing:-.02em; line-height:1.2; }
.card p{ color:var(--muted); max-width:62ch; }
.tags{ display:flex; flex-wrap:wrap; gap:8px; margin-top:auto; padding-top:6px; }
.tags li{ padding:5px 13px; border-radius:8px; font-size:14px; color:var(--gold); background:rgba(242,184,75,.09); border:1px solid rgba(242,184,75,.22); }
.more{ margin-top:28px; }
.more a{ display:inline-flex; align-items:center; gap:10px; color:var(--turq); font-weight:600; border-bottom:1px solid transparent; transition:border-color .2s ease; }
.more a:hover{ border-bottom-color:var(--turq); }

/* ---------- Goals ---------- */
.goals{ display:grid; grid-template-columns:1fr 1fr; gap:16px 40px; }
.goals li{ display:flex; align-items:center; gap:18px; padding:18px 22px; border:1px solid var(--line); border-radius:14px; background:var(--surface); font-weight:500; font-size:18px; }
.box{ position:relative; width:28px; height:28px; border-radius:8px; border:1.5px solid var(--turq); display:grid; place-items:center; color:var(--turq); flex:none; background:rgba(61,214,198,.08); }
.box .ic{ width:18px; height:18px; stroke-width:2.6; }
.box path{ stroke-dasharray:1; stroke-dashoffset:0; }
.js .box path{ stroke-dashoffset:1; }
.js .goals.in .box path{ animation:draw .6s ease forwards; animation-delay:calc(var(--i) * .16s + .35s); }

/* ---------- Contact + languages ---------- */
.contact-grid{ display:grid; grid-template-columns:1.25fr .75fr; gap:28px; align-items:start; }
.contact-list{ display:grid; gap:14px; }
.row{
  display:flex; align-items:center; gap:20px;
  padding:22px 26px; border:1px solid var(--line); border-radius:16px; background:var(--surface);
  transition:transform .3s var(--ease), border-color .3s ease;
}
.row:hover{ transform:translateX(6px); border-color:var(--turq); }
.row .ico{ width:48px; height:48px; border-radius:12px; display:grid; place-items:center; background:rgba(61,214,198,.09); color:var(--turq); flex:none; }
.row small{ display:block; font-size:14px; color:var(--muted); line-height:1.3; }
.row strong{ font-family:var(--display); font-size:clamp(17px,2vw,21px); font-weight:600; word-break:break-word; }

.lang{ padding:28px; border:1px solid var(--line); border-radius:18px; background:var(--surface); }
.lang h3{ font-family:var(--display); font-size:21px; margin-bottom:22px; }
.lang li + li{ margin-top:22px; }
.lang .top{ display:flex; justify-content:space-between; align-items:baseline; margin-bottom:10px; font-weight:600; }
.lang .top span{ color:var(--muted); font-weight:500; font-size:15px; }
.segs{ display:flex; gap:6px; }
.seg{ flex:1; height:6px; border-radius:4px; background:rgba(140,170,230,.16); }
.seg.on{ background:linear-gradient(90deg,var(--turq),#7CE9DD); }
.js .seg.on{ transform:scaleX(0); transform-origin:left; }
.js .lang.in .seg.on{ transform:scaleX(1); transition:transform .8s var(--ease) calc(var(--i) * 140ms + 300ms); }

/* ---------- Quote ---------- */
.quote{ position:relative; text-align:center; padding:110px 0 100px; overflow:hidden; }
.quote .rosette-bg{ position:absolute; left:50%; top:50%; width:min(560px, 90vw); aspect-ratio:1; transform:translate(-50%,-50%); opacity:.16; pointer-events:none; }
.quote .rosette-bg g{ transform-origin:200px 200px; animation:spin 160s linear infinite reverse; }
.quote blockquote{
  position:relative; max-width:20ch; margin-inline:auto;
  font-family:var(--display); font-weight:700; font-size:clamp(34px,5.4vw,60px); line-height:1.12; letter-spacing:-.03em;
}
.quote .sub{ position:relative; margin-top:22px; color:var(--muted); }

footer{ border-top:1px solid var(--line); padding:30px 0 40px; color:var(--muted); font-size:15px; }
footer .wrap{ display:flex; flex-wrap:wrap; justify-content:space-between; gap:10px; }

/* =========================================================
   KEYFRAMES
========================================================= */
@keyframes rise{ to{ transform:translateY(0); } }
@keyframes fadeup{ to{ opacity:1; transform:none; } }
@keyframes draw{ to{ stroke-dashoffset:0; } }
@keyframes spin{ to{ transform:rotate(360deg); } }
@keyframes typing{ to{ width:24ch; } }
@keyframes caretoff{ to{ border-right-color:transparent; } }
@keyframes blink{ 50%{ opacity:0; } }
@keyframes tick{ to{ transform:translateX(-50%); } }
@keyframes ping{ 0%{ transform:scale(1); opacity:.7; } 80%,100%{ transform:scale(2.6); opacity:0; } }

/* =========================================================
   RESPONSIVE
========================================================= */
@media (max-width:960px){
  .hero{ padding:56px 0 72px; }
  .hero-grid{ grid-template-columns:1fr; gap:44px; }
  .rosette{ right:50%; transform:translate(50%,-50%); top:38%; opacity:.4; }
  .c5,.c7,.c4,.c8{ grid-column:span 12; }
  .p-half{ grid-column:span 6; }
  .learn{ grid-template-columns:1fr; }
  .goals{ grid-template-columns:1fr; }
  .contact-grid{ grid-template-columns:1fr; }
  .nav nav a:not(.btn){ display:none; }
}
@media (max-width:560px){
  body{ font-size:16px; }
  .wrap{ width:min(1120px, 100% - 32px); }
  .section{ padding:68px 0; }
  .term-body{ padding:20px 18px; font-size:13.5px; }
  .out > div{ grid-template-columns:1fr; gap:0; }
  .cell,.card,.lang{ padding:24px 20px; }
  .row{ padding:18px; gap:14px; }
  .roles li + li::before{ margin:0 11px; }
}

/* =========================================================
   REDUCED MOTION
========================================================= */
@media (prefers-reduced-motion: reduce){
  *,*::before,*::after{
    animation-duration:.001ms !important; animation-delay:0s !important; animation-iteration-count:1 !important;
    transition-duration:.001ms !important; transition-delay:0s !important; scroll-behavior:auto !important;
  }
  .ticker{ -webkit-mask-image:none; mask-image:none; }
  .ticker-track{ animation:none !important; width:auto; }
  .ticker ul{ flex-wrap:wrap; justify-content:center; row-gap:12px; }
  .ticker ul[aria-hidden="true"]{ display:none; }
}
</style>
</head>

<body>

<!-- ============ Icon sprite ============ -->
<svg width="0" height="0" style="position:absolute" aria-hidden="true" focusable="false">
  <symbol id="i-star" viewBox="0 0 24 24"><path d="M6 6h12v12H6zM12 2l10 10-10 10L2 12z"/></symbol>
  <symbol id="i-github" viewBox="0 0 16 16"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></symbol>
  <symbol id="i-mail" viewBox="0 0 24 24"><rect x="3" y="5" width="18" height="14" rx="2"/><path d="M3 7l9 6 9-6"/></symbol>
  <symbol id="i-phone" viewBox="0 0 24 24"><path d="M5 4h4l2 5-2.5 1.5a11 11 0 005 5L15 13l5 2v4a2 2 0 01-2 2A16 16 0 013 6a2 2 0 012-2z"/></symbol>
  <symbol id="i-server" viewBox="0 0 24 24"><rect x="3" y="4" width="18" height="7" rx="2"/><rect x="3" y="13" width="18" height="7" rx="2"/><path d="M7 7.5h.01M7 16.5h.01"/></symbol>
  <symbol id="i-layout" viewBox="0 0 24 24"><rect x="3" y="4" width="18" height="16" rx="2"/><path d="M3 9h18M9 9v11"/></symbol>
  <symbol id="i-db" viewBox="0 0 24 24"><ellipse cx="12" cy="6" rx="8" ry="3"/><path d="M4 6v6c0 1.7 3.6 3 8 3s8-1.3 8-3V6M4 12v6c0 1.7 3.6 3 8 3s8-1.3 8-3v-6"/></symbol>
  <symbol id="i-term" viewBox="0 0 24 24"><path d="M4 17l6-5-6-5M12 19h8"/></symbol>
  <symbol id="i-box" viewBox="0 0 24 24"><path d="M21 8l-9-5-9 5v8l9 5 9-5V8zM3 8l9 5 9-5M12 13v8"/></symbol>
  <symbol id="i-building" viewBox="0 0 24 24"><path d="M4 21V5a1 1 0 011-1h9a1 1 0 011 1v16M15 10h4a1 1 0 011 1v10M2 21h20M8 8h3M8 12h3M8 16h3"/></symbol>
  <symbol id="i-globe" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9"/><path d="M3 12h18M12 3c3 3.2 3 14.8 0 18M12 3c-3 3.2-3 14.8 0 18"/></symbol>
  <symbol id="i-check" viewBox="0 0 24 24"><path pathLength="1" d="M5 12.5l4.5 4.5L19 7.5"/></symbol>
</svg>

<div class="progress" aria-hidden="true"></div>

<!-- ============ NAV ============ -->
<header class="nav" id="top">
  <div class="wrap nav-in">
    <a class="brand" href="#home" aria-label="Sarwar Olumee, home">
      <svg class="ic"><use href="#i-star"/></svg>
      <span>Sarwar Olumee</span>
    </a>
    <nav aria-label="Primary">
      <a href="#stack">Tech stack</a>
      <a href="#projects">Projects</a>
      <a href="#goals">Goals</a>
      <a class="btn btn-sm" href="#contact">Contact</a>
    </nav>
  </div>
</header>

<main id="home">

<!-- ============ HERO ============ -->
<section class="hero">
  <div class="wrap" style="position:relative">

    <svg class="rosette" viewBox="0 0 400 400" aria-hidden="true">
      <g class="spin">
        <circle class="dr t" cx="200" cy="200" r="190" pathLength="1" style="--d:.2s"/>
        <path class="dr g" pathLength="1" d="M79.8 79.8H320.2V320.2H79.8Z" style="--d:.5s"/>
        <path class="dr g" pathLength="1" d="M200 30L370 200L200 370L30 200Z" style="--d:.8s"/>
        <circle class="dr t" cx="200" cy="200" r="130" pathLength="1" style="--d:1.1s"/>
        <path class="dr t" pathLength="1" d="M129.3 129.3H270.7V270.7H129.3Z" style="--d:1.4s"/>
        <path class="dr t" pathLength="1" d="M200 100L300 200L200 300L100 200Z" style="--d:1.7s"/>
        <circle class="dr g" cx="200" cy="200" r="76.5" pathLength="1" style="--d:2s"/>
        <circle class="dr t" cx="200" cy="200" r="30" pathLength="1" style="--d:2.3s"/>
      </g>
    </svg>

    <div class="hero-grid">
      <div>
        <h1 class="name" aria-label="Sarwar Olumee">
          <span class="w"><span style="--d:.1s">Sarwar</span></span>
          <span class="w"><span style="--d:.25s">Olumee</span></span>
        </h1>

        <ul class="roles fade" style="--d:.6s">
          <li>Software Engineering Student</li>
          <li>Backend Developer</li>
          <li>Laravel Enthusiast</li>
        </ul>

        <p class="intro fade" style="--d:.75s">
          I'm a passionate Software Engineering student from Afghanistan with a strong interest in building scalable, maintainable, and user-friendly web applications. I enjoy solving real-world problems through software and continuously improving my development skills by learning modern technologies and best practices.
        </p>

        <div class="cta fade" style="--d:.9s">
          <a class="btn btn-primary" href="https://github.com/sarwarOlumee21" target="_blank" rel="noopener">
            <svg class="ic ic-fill" viewBox="0 0 16 16"><use href="#i-github"/></svg>
            View my GitHub
          </a>
          <a class="btn" href="mailto:sarwarolumi220@gmail.com">
            <svg class="ic"><use href="#i-mail"/></svg>
            Send an email
          </a>
        </div>
      </div>

      <div class="term fade" style="--d:.5s" role="group" aria-label="About Sarwar, shown as terminal output">
        <div class="term-bar"><i></i><i></i><i></i><span>~/herat : artisan</span></div>
        <div class="term-body">
          <p><span class="prompt">$</span><span class="typed">php artisan about:sarwar</span></p>
          <dl class="out">
            <div style="--i:0"><dt>Education</dt><dd>BSc in Software Engineering</dd></div>
            <div style="--i:1"><dt>University</dt><dd>Herat University</dd></div>
            <div style="--i:2"><dt>Location</dt><dd>Herat, Afghanistan</dd></div>
            <div style="--i:3"><dt>Focus</dt><dd>Backend Web Development</dd></div>
            <div style="--i:4"><dt>Framework</dt><dd>Laravel</dd></div>
            <div style="--i:5"><dt>Learning</dt><dd>Livewire, Design Patterns, Clean Architecture</dd></div>
            <div style="--i:6"><dt>Goal</dt><dd>Become a Professional Laravel Developer</dd></div>
          </dl>
          <p class="caret-line"><span class="prompt">$</span><span class="caret"></span></p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============ TICKER: CORE SKILLS ============ -->
<section class="ticker" aria-label="Core skills">
  <div class="ticker-track">
    <ul>
      <li>Clean Code</li>
      <li>MVC Architecture</li>
      <li>Object-Oriented Programming</li>
      <li>RESTful API Development</li>
      <li>Database Design</li>
      <li>Authentication &amp; Authorization</li>
      <li>Git Workflow</li>
      <li>Problem Solving</li>
    </ul>
    <ul aria-hidden="true">
      <li>Clean Code</li>
      <li>MVC Architecture</li>
      <li>Object-Oriented Programming</li>
      <li>RESTful API Development</li>
      <li>Database Design</li>
      <li>Authentication &amp; Authorization</li>
      <li>Git Workflow</li>
      <li>Problem Solving</li>
    </ul>
  </div>
</section>

<!-- ============ TECH STACK ============ -->
<section class="section" id="stack">
  <div class="wrap">
    <div class="section-head reveal">
      <h2>What I build with</h2>
      <p>The languages, frameworks and tools I use to design, build and ship web applications.</p>
    </div>

    <div class="bento">
      <article class="cell c5 reveal">
        <h3><svg class="ic"><use href="#i-server"/></svg>Backend</h3>
        <ul class="chips">
          <li class="laravel big" style="--i:0">Laravel</li>
          <li class="big" style="--i:1">PHP</li>
          <li class="big" style="--i:2">Livewire</li>
          <li class="big" style="--i:3">REST APIs</li>
        </ul>
      </article>

      <article class="cell c7 reveal">
        <h3><svg class="ic"><use href="#i-layout"/></svg>Frontend</h3>
        <ul class="chips">
          <li style="--i:0">HTML5</li>
          <li style="--i:1">CSS3</li>
          <li style="--i:2">JavaScript</li>
          <li style="--i:3">Bootstrap</li>
          <li style="--i:4">Tailwind CSS</li>
        </ul>
      </article>

      <article class="cell c4 reveal">
        <h3><svg class="ic"><use href="#i-db"/></svg>Database</h3>
        <ul class="chips">
          <li class="big" style="--i:0">MySQL</li>
        </ul>
      </article>

      <article class="cell c8 reveal">
        <h3><svg class="ic"><use href="#i-term"/></svg>Tools</h3>
        <ul class="chips">
          <li style="--i:0">Git</li>
          <li style="--i:1">GitHub</li>
          <li style="--i:2">Composer</li>
          <li style="--i:3">NPM</li>
          <li style="--i:4">Vite</li>
          <li style="--i:5">VS Code</li>
          <li style="--i:6">XAMPP</li>
        </ul>
      </article>
    </div>
  </div>
</section>

<div class="wrap"><div class="rule" aria-hidden="true"><svg class="ic"><use href="#i-star"/></svg></div></div>

<!-- ============ LEARNING ============ -->
<section class="section" id="learning">
  <div class="wrap">
    <div class="section-head reveal">
      <h2>Currently learning</h2>
      <p>What I'm studying right now to grow as a backend developer.</p>
    </div>

    <ul class="learn reveal">
      <li style="--i:0"><span class="dot" style="--i:0"></span>Advanced Laravel</li>
      <li style="--i:1"><span class="dot" style="--i:1"></span>Livewire</li>
      <li style="--i:2"><span class="dot" style="--i:2"></span>Design Patterns</li>
      <li style="--i:3"><span class="dot" style="--i:3"></span>SOLID Principles</li>
      <li style="--i:4"><span class="dot" style="--i:4"></span>Software Architecture</li>
      <li style="--i:5"><span class="dot" style="--i:5"></span>REST API Development</li>
    </ul>
  </div>
</section>

<div class="wrap"><div class="rule" aria-hidden="true"><svg class="ic"><use href="#i-star"/></svg></div></div>

<!-- ============ PROJECTS ============ -->
<section class="section" id="projects">
  <div class="wrap">
    <div class="section-head reveal">
      <h2>Featured projects</h2>
      <p>Real-world systems built around everyday business problems.</p>
    </div>

    <div class="projects">
      <article class="card p-wide glow reveal">
        <div class="p-icon"><svg class="ic"><use href="#i-box"/></svg></div>
        <h3>Inventory Management System</h3>
        <p>Complete inventory system with sales, purchases, warehouse management, POS, reports, and stock tracking.</p>
        <ul class="tags">
          <li>Sales</li><li>Purchases</li><li>Warehouse</li><li>POS</li><li>Reports</li><li>Stock tracking</li>
        </ul>
      </article>

      <article class="card p-half glow reveal">
        <div class="p-icon"><svg class="ic"><use href="#i-building"/></svg></div>
        <h3>Dormitory Management System</h3>
        <p>Resident management, room allocation, contracts, billing, and maintenance request management.</p>
        <ul class="tags">
          <li>Residents</li><li>Rooms</li><li>Contracts</li><li>Billing</li><li>Maintenance</li>
        </ul>
      </article>

      <article class="card p-half glow reveal">
        <div class="p-icon"><svg class="ic"><use href="#i-globe"/></svg></div>
        <h3>Personal Portfolio</h3>
        <p>Responsive portfolio website showcasing projects and skills.</p>
        <ul class="tags">
          <li>Responsive</li><li>Projects</li><li>Skills</li>
        </ul>
      </article>
    </div>

    <p class="more reveal">
      <a href="https://github.com/sarwarOlumee21" target="_blank" rel="noopener">
        <svg class="ic ic-fill" viewBox="0 0 16 16"><use href="#i-github"/></svg>
        See more on GitHub
      </a>
    </p>
  </div>
</section>

<div class="wrap"><div class="rule" aria-hidden="true"><svg class="ic"><use href="#i-star"/></svg></div></div>

<!-- ============ GOALS ============ -->
<section class="section" id="goals">
  <div class="wrap">
    <div class="section-head reveal">
      <h2>Goals for 2026</h2>
      <p>Where I'm heading this year.</p>
    </div>

    <ul class="goals reveal">
      <li style="--i:0"><span class="box"><svg class="ic"><use href="#i-check"/></svg></span>Master Laravel</li>
      <li style="--i:1"><span class="box"><svg class="ic"><use href="#i-check"/></svg></span>Master Livewire</li>
      <li style="--i:2"><span class="box"><svg class="ic"><use href="#i-check"/></svg></span>Learn Docker</li>
      <li style="--i:3"><span class="box"><svg class="ic"><use href="#i-check"/></svg></span>Learn Testing in Laravel</li>
      <li style="--i:4"><span class="box"><svg class="ic"><use href="#i-check"/></svg></span>Contribute to Open Source</li>
      <li style="--i:5"><span class="box"><svg class="ic"><use href="#i-check"/></svg></span>Build Production-Ready Applications</li>
    </ul>
  </div>
</section>

<!-- ============ CONTACT + LANGUAGES ============ -->
<section class="section" id="contact">
  <div class="wrap">
    <div class="section-head reveal">
      <h2>Get in touch</h2>
      <p>The quickest ways to reach me.</p>
    </div>

    <div class="contact-grid">
      <div class="contact-list reveal">
        <a class="row" href="https://github.com/sarwarOlumee21" target="_blank" rel="noopener">
          <span class="ico"><svg class="ic ic-fill" viewBox="0 0 16 16"><use href="#i-github"/></svg></span>
          <span><small>GitHub</small><strong>github.com/sarwarOlumee21</strong></span>
        </a>
        <a class="row" href="mailto:sarwarolumi220@gmail.com">
          <span class="ico"><svg class="ic"><use href="#i-mail"/></svg></span>
          <span><small>Email</small><strong>sarwarolumi220@gmail.com</strong></span>
        </a>
        <a class="row" href="tel:+93793448759">
          <span class="ico"><svg class="ic"><use href="#i-phone"/></svg></span>
          <span><small>Phone</small><strong>+93 793 448 759</strong></span>
        </a>
      </div>

      <div class="lang reveal">
        <h3>Languages</h3>
        <ul>
          <li>
            <div class="top">Dari <span>Native</span></div>
            <div class="segs"><i class="seg on" style="--i:0"></i><i class="seg on" style="--i:1"></i><i class="seg on" style="--i:2"></i></div>
          </li>
          <li>
            <div class="top">English <span>Intermediate</span></div>
            <div class="segs"><i class="seg on" style="--i:0"></i><i class="seg on" style="--i:1"></i><i class="seg"></i></div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- ============ QUOTE ============ -->
<section class="quote">
  <svg class="rosette-bg" viewBox="0 0 400 400" aria-hidden="true" fill="none" stroke="#3DD6C6" stroke-width="1.2">
    <g>
      <circle cx="200" cy="200" r="190"/>
      <path d="M79.8 79.8H320.2V320.2H79.8Z"/>
      <path d="M200 30L370 200L200 370L30 200Z"/>
      <circle cx="200" cy="200" r="130"/>
      <path d="M129.3 129.3H270.7V270.7H129.3Z"/>
      <path d="M200 100L300 200L200 300L100 200Z"/>
    </g>
  </svg>
  <div class="wrap reveal">
    <blockquote>Code with purpose. Learn continuously. Build solutions that make a difference.</blockquote>
    <p class="sub">Sarwar Olumee, Herat, Afghanistan</p>
  </div>
</section>

</main>

<footer>
  <div class="wrap">
    <span>&copy; 2026 Sarwar Olumee</span>
    <a href="#top">Back to top</a>
  </div>
</footer>

<script>
(function(){
  'use strict';
  var doc = document, root = doc.documentElement;

  /* Scroll reveal */
  var items = doc.querySelectorAll('.reveal');
  if ('IntersectionObserver' in window) {
    var io = new IntersectionObserver(function(entries){
      entries.forEach(function(e){
        if (e.isIntersecting) { e.target.classList.add('in'); io.unobserve(e.target); }
      });
    }, { threshold: 0.15, rootMargin: '0px 0px -6% 0px' });
    items.forEach(function(el){ io.observe(el); });
  } else {
    items.forEach(function(el){ el.classList.add('in'); });
  }

  /* Scroll progress + nav border */
  var bar = doc.querySelector('.progress');
  var nav = doc.querySelector('.nav');
  var ticking = false;
  function update(){
    var max = root.scrollHeight - root.clientHeight;
    var y = window.pageYOffset || root.scrollTop;
    bar.style.transform = 'scaleX(' + (max > 0 ? y / max : 0) + ')';
    nav.classList.toggle('scrolled', y > 10);
    ticking = false;
  }
  window.addEventListener('scroll', function(){
    if (!ticking) { ticking = true; requestAnimationFrame(update); }
  }, { passive: true });
  update();

  /* Cursor glow on project cards */
  doc.querySelectorAll('.glow').forEach(function(card){
    card.addEventListener('pointermove', function(e){
      var r = card.getBoundingClientRect();
      card.style.setProperty('--mx', (e.clientX - r.left) + 'px');
      card.style.setProperty('--my', (e.clientY - r.top) + 'px');
    });
  });
})();
</script>

</body>
</html>

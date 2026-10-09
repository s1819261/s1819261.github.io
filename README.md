<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="theme-color" content="#0D1117">
<title>Tone &amp; Shape — Training Plan</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Anton&family=DM+Mono:wght@400;500&family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
:root[data-theme="dark"]{
  --page:#0D1117;--surface:#161C26;--surface-2:#1F2733;
  --line:rgba(255,255,255,0.09);--line-soft:rgba(255,255,255,0.05);
  --text:#EDF2F7;--text-dim:#8FA3BC;--muted:#5A6B82;
  --accent:#4D8DFF;--accent-2:#7FB0FF;--accent-soft:rgba(77,141,255,0.15);--on-accent:#04182F;
  --danger:#FF6B4A;
  --cat-leg:#4D8DFF;--cat-arm:#22D3EE;--cat-cardio:#A78BFA;--cat-rest:#5A6B82;
  --glow:radial-gradient(circle at 12% 0%, rgba(77,141,255,0.10), transparent 55%);
}
:root[data-theme="light"]{
  --page:#FAF9FF;--surface:#FFFFFF;--surface-2:#F3EEFE;
  --line:rgba(26,21,38,0.11);--line-soft:rgba(26,21,38,0.06);
  --text:#1A1526;--text-dim:#5B5470;--muted:#8B84A3;
  --accent:#6D28D9;--accent-2:#8B5CF6;--accent-soft:#F1EBFE;--on-accent:#FFFFFF;
  --danger:#D6401F;
  --cat-leg:#6D28D9;--cat-arm:#C026D3;--cat-cardio:#0E7490;--cat-rest:#8B84A3;
  --glow:radial-gradient(circle at 12% 0%, rgba(109,40,217,0.09), transparent 55%);
}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent;}
html,body{margin:0;padding:0;}
body{background:var(--page);color:var(--text);font-family:'Inter',system-ui,sans-serif;min-height:100vh;padding-bottom:60px;transition:background .2s ease,color .2s ease;}
.wrap{max-width:560px;margin:0 auto;padding:0 16px;}
button,select,input{font-family:inherit;}
:focus-visible{outline:2px solid var(--accent);outline-offset:2px;}

.hero{padding:26px 16px 18px;background:var(--glow),var(--page);border-bottom:1px solid var(--line);}
.hero-top{display:flex;align-items:flex-start;justify-content:space-between;gap:12px;}
.eyebrow{font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.18em;text-transform:uppercase;color:var(--accent);margin-bottom:10px;}
h1{font-family:'Anton',sans-serif;font-weight:400;font-size:40px;line-height:.92;letter-spacing:.01em;margin:0 0 10px;text-transform:uppercase;}
h1 span{color:var(--accent);}
.hero-sub{color:var(--text-dim);font-size:14px;line-height:1.5;max-width:46ch;margin:0;}
.icon-btn{flex:0 0 auto;width:40px;height:40px;border-radius:12px;border:1px solid var(--line);background:var(--surface);color:var(--text-dim);font-size:17px;cursor:pointer;display:flex;align-items:center;justify-content:center;}
.icon-btn:hover{color:var(--accent);border-color:var(--accent);}

.settings{display:flex;flex-wrap:wrap;gap:10px;align-items:center;margin-top:16px;}
.mini-label{font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.04em;color:var(--text-dim);text-transform:uppercase;}
.num-input{width:62px;font-family:'DM Mono',monospace;font-size:13px;color:var(--text);background:var(--surface);border:1px solid var(--line);border-radius:8px;padding:7px 8px;}
.ghost-btn{font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.04em;color:var(--text-dim);background:var(--surface);border:1px solid var(--line);padding:8px 12px;border-radius:8px;cursor:pointer;text-transform:uppercase;}
.ghost-btn:hover{color:var(--accent);border-color:var(--accent);}
.ghost-btn.confirming{color:var(--danger)!important;border-color:var(--danger)!important;}

.target-card,.quick-card{margin-top:18px;border:1px solid var(--line);border-radius:14px;background:var(--surface);overflow:hidden;}
.target-head{display:flex;align-items:center;justify-content:space-between;gap:10px;padding:14px 16px 10px;}
.target-title{font-weight:800;font-size:15px;}
.target-status{font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.05em;text-transform:uppercase;color:var(--text-dim);text-align:right;}
.target-status.ok{color:var(--accent);}
.target-status.off{color:var(--danger);}
.target-grid{display:flex;gap:8px;padding:0 16px 14px;flex-wrap:wrap;}
.target-pill{flex:1 1 90px;background:var(--surface-2);border-radius:10px;padding:10px 12px;border-left:3px solid var(--muted);}
.target-pill .tp-name{font-family:'DM Mono',monospace;font-size:10.5px;letter-spacing:.08em;text-transform:uppercase;color:var(--text-dim);margin-bottom:4px;}
.target-pill .tp-count{font-family:'Anton',sans-serif;font-size:20px;line-height:1;}
.target-pill .tp-need{font-size:11px;color:var(--text-dim);margin-top:4px;}
.target-edit{padding:12px 16px 14px;display:none;gap:10px;flex-wrap:wrap;align-items:center;border-top:1px solid var(--line-soft);}
.target-edit.open{display:flex;}
.target-edit .field{display:flex;align-items:center;gap:6px;}

/* QUICK LOG */
.quick-body{padding:0 16px 14px;}
.quick-btns{display:grid;grid-template-columns:repeat(4,1fr);gap:6px;}
.qbtn{font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.05em;text-transform:uppercase;padding:10px 0;border-radius:9px;border:1px solid var(--line);background:var(--surface-2);color:var(--text-dim);cursor:pointer;display:flex;flex-direction:column;align-items:center;gap:6px;}
.qbtn i{width:8px;height:8px;border-radius:50%;display:block;}
.qbtn.on{background:var(--accent);border-color:var(--accent);color:var(--on-accent);font-weight:700;}
.qbtn.on i{background:var(--on-accent)!important;}
.quick-extra{display:none;gap:8px;align-items:center;margin-top:10px;flex-wrap:wrap;}
.quick-extra.open{display:flex;}
.quick-hint{font-size:12px;color:var(--text-dim);margin:10px 0 0;line-height:1.5;}

.week-strip{position:sticky;top:0;z-index:20;display:flex;gap:6px;overflow-x:auto;padding:10px 16px;background:var(--page);border-bottom:1px solid var(--line);scrollbar-width:none;margin-top:18px;}
.week-strip::-webkit-scrollbar{display:none;}
.chip{flex:0 0 auto;font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.05em;padding:8px 12px;border-radius:999px;border:1px solid var(--line);color:var(--text-dim);background:var(--surface);white-space:nowrap;cursor:pointer;display:flex;align-items:center;gap:6px;}
.chip .cdot{width:7px;height:7px;border-radius:50%;background:var(--muted);}
.chip.active{color:var(--on-accent);background:var(--accent);border-color:var(--accent);font-weight:700;}
.chip.active .cdot{background:var(--on-accent)!important;}

.day{margin-top:18px;border:1px solid var(--line);border-radius:14px;overflow:hidden;background:var(--surface);scroll-margin-top:64px;}
.day-head{width:100%;display:flex;align-items:center;gap:12px;padding:16px;background:none;border:none;color:var(--text);text-align:left;cursor:pointer;}
.day-num{font-family:'Anton',sans-serif;font-size:22px;color:var(--muted);width:34px;flex-shrink:0;}
.day.rest .day-num{color:var(--line);}
.day-titles{flex:1;min-width:0;}
.day-name{font-weight:800;font-size:15px;letter-spacing:.01em;}
.today-tag{font-family:'DM Mono',monospace;font-size:10px;color:var(--on-accent);background:var(--accent);padding:2px 6px;border-radius:5px;margin-left:6px;vertical-align:2px;font-weight:700;}
.day-date{font-family:'DM Mono',monospace;font-size:11px;color:var(--text-dim);margin-top:2px;}
.day-focus{font-family:'DM Mono',monospace;font-size:11.5px;color:var(--accent);margin-top:2px;text-transform:uppercase;letter-spacing:.04em;}
.day.rest .day-focus{color:var(--text-dim);}
.chevron{width:20px;height:20px;flex-shrink:0;color:var(--text-dim);transition:transform .25s ease;}
.day.open .chevron{transform:rotate(180deg);}
.day-body{max-height:0;overflow:hidden;transition:max-height .3s ease;}
.day.open .day-body{max-height:9000px;}
.day-inner{padding:0 16px 18px;}
.day-note{font-size:12.5px;color:var(--text-dim);line-height:1.5;margin:0 0 14px;padding:10px 12px;background:var(--surface-2);border-left:2px solid var(--accent);}
.assign-row{display:flex;gap:8px;flex-wrap:wrap;margin:0 0 12px;align-items:center;}
.assign-select,.rename-input,.add-input,.unit-select{font-family:'DM Mono',monospace;font-size:12px;color:var(--text);background:var(--surface-2);border:1px solid var(--line);border-radius:8px;padding:9px 10px;}
.assign-select{flex:1 1 170px;min-width:0;}
.rename-input{flex:1 1 120px;min-width:0;}

.ex{display:flex;gap:12px;padding:12px 0;border-top:1px solid var(--line-soft);}
.ex-list .ex:first-child{border-top:none;}
.ex-check{width:24px;height:24px;border-radius:7px;border:1.5px solid var(--muted);flex-shrink:0;margin-top:2px;display:flex;align-items:center;justify-content:center;cursor:pointer;transition:all .15s ease;background:transparent;padding:0;}
.ex-check.done{background:var(--accent);border-color:var(--accent);}
.ex-check svg{width:15px;height:15px;opacity:0;color:var(--on-accent);}
.ex-check.done svg{opacity:1;}
.ex-main{flex:1;min-width:0;}
.ex-name{font-weight:700;font-size:14.5px;margin-bottom:3px;}
.ex.done .ex-name{color:var(--text-dim);text-decoration:line-through;text-decoration-color:var(--muted);}
.ex-cue{font-size:12px;color:var(--text-dim);line-height:1.4;}
.tag{font-family:'DM Mono',monospace;font-size:9.5px;letter-spacing:.06em;margin-left:6px;padding:1px 5px;border-radius:5px;vertical-align:2px;font-weight:500;}
.tag.heavy{color:var(--danger);border:1px solid var(--danger);}
.tag.added{color:var(--accent);border:1px solid var(--accent);}
.tag.typed{color:var(--cat-arm);border:1px solid var(--cat-arm);}
.ex-swap{display:block;margin-top:8px;font-family:'DM Mono',monospace;font-size:11px;color:var(--text);background:var(--surface-2);border:1px solid var(--line);border-radius:6px;padding:5px 8px;max-width:100%;cursor:pointer;}
.ex-stats{display:flex;gap:6px;margin-top:7px;flex-wrap:wrap;}
.stat{font-family:'DM Mono',monospace;font-size:11px;padding:3px 8px;border-radius:6px;background:var(--surface-2);color:var(--text);border:1px solid var(--line-soft);}
.stat.sets{color:var(--accent);border-color:var(--accent-soft);}
.set-boxes{display:flex;gap:6px;margin-top:9px;flex-wrap:wrap;}
.set-box{width:30px;height:30px;border-radius:8px;border:1.5px solid var(--muted);background:var(--surface-2);display:flex;align-items:center;justify-content:center;font-family:'DM Mono',monospace;font-size:11px;color:var(--text-dim);cursor:pointer;transition:all .15s ease;flex-shrink:0;padding:0;}
.set-box.done{background:var(--accent);border-color:var(--accent);color:var(--on-accent);font-weight:700;}
.set-box:active{transform:scale(.92);}
.weight-row{display:flex;align-items:center;gap:8px;margin-top:9px;flex-wrap:wrap;}
.weight-input{width:72px;}
.last-time{font-family:'DM Mono',monospace;font-size:11px;color:var(--text-dim);}
.last-time b{color:var(--text);font-weight:500;}
.ex-remove{width:22px;height:22px;border-radius:6px;border:1px solid var(--line);background:var(--surface-2);color:var(--text-dim);display:flex;align-items:center;justify-content:center;cursor:pointer;flex-shrink:0;font-size:13px;line-height:1;margin-top:2px;padding:0;}
.ex-remove:hover{color:var(--danger);border-color:var(--danger);}
.add-exercise-row{display:flex;gap:8px;margin-top:14px;flex-wrap:wrap;align-items:center;padding-top:14px;border-top:1px solid var(--line-soft);}
.add-input{flex:1 1 170px;min-width:0;}
.add-btn{font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.04em;color:var(--on-accent);background:var(--accent);border:1px solid var(--accent);border-radius:8px;padding:9px 14px;font-weight:700;cursor:pointer;white-space:nowrap;}
.add-err{width:100%;font-size:12px;color:var(--danger);margin:0;display:none;}
.add-err.show{display:block;}
.add-label{width:100%;font-size:12px;color:var(--text-dim);margin:0;}
.rest-block{padding:18px 14px;background:var(--surface-2);border-radius:10px;font-size:13.5px;line-height:1.6;color:var(--text-dim);text-align:center;}
.day-progress{display:flex;align-items:center;gap:8px;padding:10px 16px 14px;font-family:'DM Mono',monospace;font-size:11px;color:var(--text-dim);}
.bar{flex:1;height:4px;background:var(--surface-2);border-radius:2px;overflow:hidden;}
.bar-fill{height:100%;background:var(--accent);width:0%;transition:width .3s ease;}
.log-row{display:flex;gap:8px;padding:0 16px 16px;flex-wrap:wrap;}
.log-btn{font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.04em;text-transform:uppercase;color:var(--accent);background:var(--accent-soft);border:1px solid var(--accent);border-radius:8px;padding:9px 14px;cursor:pointer;font-weight:700;}
.log-btn.logged{background:var(--accent);color:var(--on-accent);}

.cal-section{margin-top:30px;border:1px solid var(--line);border-radius:14px;background:var(--surface);overflow:hidden;}
.cal-head{display:flex;align-items:center;justify-content:space-between;padding:16px;gap:10px;}
.cal-month{font-family:'Anton',sans-serif;font-size:22px;text-transform:uppercase;letter-spacing:.02em;}
.cal-nav{display:flex;gap:6px;}
.cal-nav button{width:32px;height:32px;border-radius:8px;border:1px solid var(--line);background:var(--surface-2);color:var(--text-dim);cursor:pointer;font-size:14px;line-height:1;display:flex;align-items:center;justify-content:center;}
.cal-nav button:hover{color:var(--accent);border-color:var(--accent);}
.cal-stats{display:flex;gap:8px;padding:0 16px 14px;flex-wrap:wrap;}
.cal-stat{flex:1 1 90px;background:var(--surface-2);border-radius:10px;padding:10px 12px;}
.cal-stat .cs-num{font-family:'Anton',sans-serif;font-size:22px;line-height:1;color:var(--accent);}
.cal-stat .cs-label{font-family:'DM Mono',monospace;font-size:10px;letter-spacing:.07em;text-transform:uppercase;color:var(--text-dim);margin-top:5px;}
.cal-grid{display:grid;grid-template-columns:repeat(7,1fr);gap:5px;padding:0 16px 8px;}
.cal-dow{font-family:'DM Mono',monospace;font-size:10px;letter-spacing:.06em;text-transform:uppercase;color:var(--muted);text-align:center;padding-bottom:4px;}
.cal-cell{aspect-ratio:1;border-radius:9px;background:var(--surface-2);border:1px solid transparent;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:3px;font-family:'DM Mono',monospace;font-size:11.5px;color:var(--text-dim);cursor:pointer;padding:0;}
.cal-cell.blank{background:transparent;cursor:default;}
.cal-cell.today{border-color:var(--accent);}
.cal-cell.future{opacity:.4;}
.cal-cell .cal-dot{width:7px;height:7px;border-radius:50%;background:transparent;}
.cal-cell.logged{color:var(--text);}
.cal-legend{display:flex;gap:12px;flex-wrap:wrap;padding:10px 16px 16px;font-family:'DM Mono',monospace;font-size:10.5px;letter-spacing:.05em;text-transform:uppercase;color:var(--text-dim);}
.cal-legend span{display:flex;align-items:center;gap:5px;}
.cal-legend i{width:8px;height:8px;border-radius:50%;display:block;}
.cal-hint{padding:0 16px 16px;font-size:12px;color:var(--text-dim);line-height:1.5;margin:0;}
footer{margin-top:26px;padding:18px 16px 30px;text-align:center;font-family:'DM Mono',monospace;font-size:11px;color:var(--text-dim);letter-spacing:.03em;}
@media (prefers-reduced-motion:reduce){*{transition:none!important;}}
</style>
</head>
<body>

<div class="hero">
  <div class="wrap" style="padding:0;">
    <div class="hero-top">
      <div>
        <div class="eyebrow" id="heroEyebrow">7-day plan · your gym</div>
        <h1>Tone &amp; <span>Shape</span><br>Training Plan</h1>
      </div>
      <button class="icon-btn" id="themeBtn" aria-label="Switch theme" title="Switch theme">◐</button>
    </div>
    <p class="hero-sub">Set each day to whatever you want. Tap a set to check it off and log your weights so you know when to go heavier. Everything saves to this device.</p>

    <div class="settings">
      <label class="mini-label" for="weightInput">Body weight (lbs)</label>
      <input id="weightInput" class="num-input" type="number" min="70" max="400" value="172" aria-label="Your body weight in pounds">
      <button class="ghost-btn" id="targetToggle">Edit targets</button>
      <button class="ghost-btn" id="resetBtn">Reset this week</button>
      <button class="ghost-btn" id="exportBtn">Back up</button>
      <button class="ghost-btn" id="importBtn">Restore</button>
      <input type="file" id="importFile" accept="application/json,.json" style="display:none">
    </div>
  </div>
</div>

<div class="wrap">
  <div class="quick-card">
    <div class="target-head">
      <div class="target-title">Quick log · today</div>
      <div class="target-status" id="quickStatus"></div>
    </div>
    <div class="quick-body">
      <div class="quick-btns">
        <button class="qbtn" data-cat="cardio"><i style="background:var(--cat-cardio)"></i>Cardio</button>
        <button class="qbtn" data-cat="leg"><i style="background:var(--cat-leg)"></i>Leg</button>
        <button class="qbtn" data-cat="arm"><i style="background:var(--cat-arm)"></i>Arm</button>
        <button class="qbtn" data-cat="rest"><i style="background:var(--cat-rest)"></i>Rest</button>
      </div>
      <div class="quick-extra" id="quickExtra">
        <input class="num-input" id="quickMin" type="number" min="5" max="300" step="5" value="30" aria-label="Minutes">
        <span class="mini-label">min</span>
        <select class="assign-select" id="quickType" aria-label="Cardio type"></select>
      </div>
      <p class="quick-hint">For days you go off-plan. Tap a type to log today, tap it again to undo.</p>
    </div>
  </div>

  <div class="target-card">
    <div class="target-head">
      <div class="target-title">This week's split</div>
      <div class="target-status" id="targetStatus"></div>
    </div>
    <div class="target-grid" id="targetGrid"></div>
    <div class="target-edit" id="targetEdit">
      <div class="field"><span class="mini-label">Leg</span><input class="num-input" id="tLeg" type="number" min="0" max="7" aria-label="Leg days target"></div>
      <div class="field"><span class="mini-label">Arm</span><input class="num-input" id="tArm" type="number" min="0" max="7" aria-label="Arm days target"></div>
      <div class="field"><span class="mini-label">Cardio</span><input class="num-input" id="tCardio" type="number" min="0" max="7" aria-label="Cardio days target"></div>
    </div>
  </div>
</div>

<div class="week-strip" id="weekStrip"></div>

<div class="wrap" id="days"></div>

<div class="wrap">
  <div class="cal-section">
    <div class="cal-head">
      <div class="cal-month" id="calMonth">—</div>
      <div class="cal-nav">
        <button id="calPrev" aria-label="Previous month">‹</button>
        <button id="calToday" aria-label="Jump to this month" style="width:auto;padding:0 10px;font-family:'DM Mono',monospace;font-size:10px;letter-spacing:.06em;">TODAY</button>
        <button id="calNext" aria-label="Next month">›</button>
      </div>
    </div>
    <div class="cal-stats" id="calStats"></div>
    <div class="cal-grid" id="calGrid"></div>
    <div class="cal-legend">
      <span><i style="background:var(--cat-leg)"></i>Leg</span>
      <span><i style="background:var(--cat-arm)"></i>Arm</span>
      <span><i style="background:var(--cat-cardio)"></i>Cardio</span>
      <span><i style="background:var(--cat-rest)"></i>Rest</span>
    </div>
    <p class="cal-hint">Tap any date to cycle it: scheduled workout → rest → clear. Finishing every set on a day logs it automatically. Calorie numbers are estimates.</p>
  </div>
</div>

<footer>SAVED ON THIS DEVICE · TAP "BACK UP" NOW AND THEN</footer>

<script>
/* ---------- EXERCISE DATA ---------- */
var TEMPLATES = {
  'leg-glute': {
    focus: 'Glutes — heavy hip thrust day',
    estMinutes: {strength: 55},
    note: '⏱ ~50–60 min. Heavy hip thrust first, while you\u2019re fresh: 1–2 lighter warm-up sets, then pick a weight where the last 2 reps are hard. When you hit 10 reps on all 4 sets, go up in weight next time.',
    exercises: [
      { options: [
        {name:'Smith Machine Hip Thrust', cue:'Heavy. Upper back on bench, pause and squeeze hard at the top', sets:4, reps:'6–10', rest:'2–3 min', heavy:true},
        {name:'Dumbbell Hip Thrust', cue:'Heaviest dumbbell you can control, pause at the top', sets:4, reps:'8–10', rest:'2 min', heavy:true},
        {name:'Leg Press', cue:'Feet high & wide, heavy, full depth you can control', sets:4, reps:'8–10', rest:'2 min', heavy:true}
      ]},
      { options: [
        {name:'Cable Romanian Deadlift', cue:'Moderate weight, feel the hamstring stretch, hips back', sets:3, reps:'10–12', rest:'90 sec'},
        {name:'Romanian Deadlifts (dumbbell)', cue:'Moderate weight, feel the stretch in hamstrings', sets:3, reps:'10–12', rest:'90 sec'},
        {name:'Smith Machine Good Mornings', cue:'Hip hinge with soft knees, push hips back', sets:3, reps:'10–12', rest:'90 sec'}
      ]},
      { options: [
        {name:'Bulgarian Split Squat (dumbbell)', cue:'Lean torso slightly forward to bias glutes, drive through front heel', sets:3, reps:'8–12 / leg', rest:'90 sec'},
        {name:'Walking Lunges (dumbbell)', cue:'Long stride, slight forward lean', sets:3, reps:'12 / leg', rest:'90 sec'},
        {name:'Step-Ups (bench, dumbbell)', cue:'Drive through the front heel, control the step down', sets:3, reps:'10 / leg', rest:'90 sec'},
        {name:'Curtsy Lunge (dumbbell)', cue:'Step back and across, squeeze the glute of the standing leg', sets:3, reps:'12 / leg', rest:'90 sec'}
      ]},
      { options: [
        {name:'Leg Press', cue:'Feet high & wide on platform for glute emphasis', sets:3, reps:'10–15', rest:'90 sec'},
        {name:'Hack Squat Machine', cue:'Feet slightly forward, control the descent', sets:3, reps:'10–15', rest:'90 sec'},
        {name:'Goblet Squats (dumbbell/kettlebell)', cue:'Elbows inside knees at the bottom, chest up', sets:3, reps:'12–15', rest:'90 sec'}
      ]},
      { options: [
        {name:'Abductor Machine', cue:'Lean forward on the last set to hit the upper glute', sets:3, reps:'15–20', rest:'60 sec'},
        {name:'Standing Cable Hip Abduction', cue:'Ankle cuff, kick out to the side and control the return', sets:3, reps:'15 / leg', rest:'60 sec'},
        {name:'Side-Lying Hip Abduction (dumbbell)', cue:'Top leg raises straight up, control the lower', sets:3, reps:'15 / leg', rest:'60 sec'}
      ]},
      { options: [
        {name:'Cable Glute Kickback', cue:'Finisher. Slight forward lean, kick back and squeeze', sets:2, reps:'15 / leg', rest:'45 sec'},
        {name:'Glute Elite Machine', cue:'Finisher. Full range, squeeze at top', sets:2, reps:'15 / leg', rest:'45 sec'},
        {name:'Glute Bridge (bodyweight or dumbbell)', cue:'Finisher. Fast up, slow down, squeeze', sets:2, reps:'20', rest:'45 sec'}
      ]}
    ]
  },
  'leg-hinge': {
    focus: 'Glutes — heavy RDL day, knee-friendly',
    estMinutes: {strength: 55},
    note: '⏱ ~50–60 min. Heavy Romanian deadlift first, then everything else saves your lower back. Easy on the knees throughout.',
    exercises: [
      { options: [
        {name:'Romanian Deadlifts (dumbbell)', cue:'Heavy. Flat back, hips back until hamstrings stretch, squeeze up', sets:4, reps:'6–10', rest:'2–3 min', heavy:true},
        {name:'Cable Romanian Deadlift', cue:'Heavy. Constant tension, hips back, squeeze up', sets:4, reps:'8–10', rest:'2 min', heavy:true},
        {name:'Kettlebell Deadlift', cue:'Heavy. Hip hinge, bell close to shins', sets:4, reps:'8–10', rest:'2 min', heavy:true}
      ]},
      { options: [
        {name:'Dumbbell Hip Thrust', cue:'Moderate weight, 1-second squeeze at the top', sets:3, reps:'10–12', rest:'90 sec'},
        {name:'Smith Machine Hip Thrust', cue:'Moderate weight, 1-second squeeze at the top', sets:3, reps:'10–12', rest:'90 sec'},
        {name:'Single-Leg Hip Thrust (bench)', cue:'One foot planted, drive through the heel and squeeze', sets:3, reps:'10–12 / leg', rest:'75 sec'}
      ]},
      { options: [
        {name:'Lying Leg Curl Machine', cue:'Full stretch at bottom, squeeze at top', sets:3, reps:'10–15', rest:'60 sec'},
        {name:'Seated Leg Curl Machine', cue:'Controlled tempo, supports the hamstring-glute tie-in', sets:3, reps:'10–15', rest:'60 sec'},
        {name:'Stability Ball Hamstring Curl', cue:'Heels on the ball, lift hips and curl the ball in', sets:3, reps:'12–15', rest:'60 sec'}
      ]},
      { options: [
        {name:'Standing Cable Hip Extension', cue:'Ankle cuff, kick straight back from the hip, knee soft', sets:3, reps:'12–15 / leg', rest:'60 sec'},
        {name:'Cable Glute Kickback', cue:'Slight forward lean, kick back and squeeze', sets:3, reps:'12–15 / leg', rest:'60 sec'},
        {name:'Glute Elite Machine', cue:'Full range of motion, squeeze at top', sets:3, reps:'12–15 / leg', rest:'60 sec'}
      ]},
      { options: [
        {name:'Hip Abductor Machine', cue:'Seated, outer glute, no knee stress', sets:3, reps:'15–20', rest:'60 sec'},
        {name:'Standing Cable Hip Abduction', cue:'Ankle cuff, kick out to the side, no knee load', sets:3, reps:'15 / leg', rest:'60 sec'},
        {name:'Side-Lying Hip Abduction (dumbbell)', cue:'Top leg raises straight up, controlled', sets:3, reps:'15 / leg', rest:'60 sec'}
      ]},
      { options: [
        {name:'Glute Bridge (bodyweight or dumbbell)', cue:'Burnout finisher. Fast up, slow down', sets:2, reps:'20', rest:'45 sec'},
        {name:'Single-Leg Glute Bridge', cue:'Burnout finisher. One leg up, drive through the planted heel', sets:2, reps:'12 / leg', rest:'45 sec'},
        {name:'Frog Pumps', cue:'Soles of feet together, knees out, pump hips up', sets:2, reps:'25', rest:'45 sec'}
      ]}
    ]
  },
  'leg-standard': {
    focus: 'Glutes & legs — tone',
    estMinutes: {strength: 60},
    note: '⏱ ~55–65 min total (incl. 5–8 min warm-up). No hip thrust machine needed — swapped in a Smith machine hip thrust, which most gyms have. Use the dropdown on any exercise to swap it.',
    exercises: [
      { options: [
        {name:'Smith Machine Hip Thrust', cue:'Upper back on bench, bar across hips, squeeze glutes hard at top', sets:4, reps:'12–15', rest:'90 sec'},
        {name:'Dumbbell Hip Thrust', cue:'Upper back on bench, dumbbell across hips, squeeze at top', sets:4, reps:'12–15', rest:'90 sec'},
        {name:'Single-Leg Hip Thrust (bench)', cue:'One foot planted, drive through the heel and squeeze', sets:3, reps:'10–12 / leg', rest:'75 sec'},
        {name:'Leg Press', cue:'Feet high & wide on platform for glute emphasis', sets:3, reps:'12–15', rest:'90 sec'}
      ]},
      { options: [
        {name:'Leg Press', cue:'Feet high & wide on platform for glute emphasis', sets:3, reps:'12–15', rest:'90 sec'},
        {name:'Hack Squat Machine', cue:'Feet slightly forward, control the descent', sets:3, reps:'12–15', rest:'90 sec'},
        {name:'Walking Lunges (dumbbell)', cue:'Long stride, back knee taps close to the floor', sets:3, reps:'12 / leg', rest:'90 sec'}
      ]},
      { options: [
        {name:'Smith Machine Squats', cue:'Feet slightly wider than hips', sets:3, reps:'10–12', rest:'90 sec'},
        {name:'Goblet Squats (dumbbell/kettlebell)', cue:'Elbows inside knees at the bottom, chest up', sets:3, reps:'12–15', rest:'90 sec'},
        {name:'Leg Extension Machine', cue:'Quad-focused, controlled squeeze at the top', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Leg Press', cue:'Feet lower & closer together for a squat-like quad/glute mix', sets:3, reps:'12–15', rest:'90 sec'}
      ]},
      { options: [
        {name:'Glute Elite Machine', cue:'Full range of motion, squeeze at top', sets:3, reps:'15 / leg', rest:'60 sec'},
        {name:'Bulgarian Split Squat (dumbbell)', cue:'Rear foot up on a bench, drive through the front heel', sets:3, reps:'12 / leg', rest:'60 sec'},
        {name:'Curtsy Lunge (dumbbell)', cue:'Step back and across, squeeze the glute of the standing leg', sets:3, reps:'12 / leg', rest:'60 sec'},
        {name:'Leg Press', cue:'Feet high & wide on platform for glute emphasis', sets:3, reps:'15 / leg', rest:'60 sec'}
      ]},
      { options: [
        {name:'Romanian Deadlifts (dumbbell)', cue:'Feel the stretch in hamstrings', sets:3, reps:'10–12', rest:'90 sec'},
        {name:'Cable Romanian Deadlift', cue:'Cable adds constant tension through the hinge', sets:3, reps:'10–12', rest:'90 sec'},
        {name:'Smith Machine Good Mornings', cue:'Hip hinge with soft knees, push hips back', sets:3, reps:'10–12', rest:'90 sec'},
        {name:'Leg Press', cue:'Feet high & wide on platform for glute emphasis', sets:3, reps:'12–15', rest:'90 sec'}
      ]},
      { options: [
        {name:'Kettlebell Squats', cue:'Goblet-style, go deep, wide stance for glutes', sets:3, reps:'12–15', rest:'90 sec'},
        {name:'Sumo Squats (dumbbell)', cue:'Wide stance, toes out, sit straight down', sets:3, reps:'12–15', rest:'90 sec'},
        {name:'Step-Ups (bench, dumbbell)', cue:'Drive through the front heel, control the step down', sets:3, reps:'12 / leg', rest:'90 sec'},
        {name:'Leg Press', cue:'Feet high & wide on platform for glute emphasis', sets:3, reps:'12–15', rest:'90 sec'}
      ]},
      { options: [
        {name:'Abductor Machine', cue:'Outer thigh, controlled tempo', sets:3, reps:'15–20', rest:'60 sec'},
        {name:'Standing Cable Hip Abduction', cue:'Ankle cuff, kick out to the side and control the return', sets:3, reps:'15 / leg', rest:'60 sec'},
        {name:'Side-Lying Hip Abduction (dumbbell)', cue:'Top leg raises straight up, control the lower', sets:3, reps:'15 / leg', rest:'60 sec'},
        {name:'Leg Press', cue:'Not a direct abductor substitute, but a solid general glute/quad builder', sets:3, reps:'15–20', rest:'60 sec'}
      ]}
    ]
  },
  'leg-knee': {
    focus: 'Glutes & legs — knee-friendly',
    estMinutes: {strength: 60},
    note: '⏱ ~55–65 min total. Heavier day, but built around hip-hinge and machine moves instead of deep knee bends — still loads the glutes hard, just keeps the knees out of it.',
    exercises: [
      { options: [
        {name:'Smith Machine Hip Thrust', cue:'Heavier load, knees stay fixed near 90°, drive through heels', sets:4, reps:'8–10', rest:'120 sec'},
        {name:'Dumbbell Hip Thrust', cue:'Heavier dumbbell across hips, knees fixed, drive through heels', sets:4, reps:'8–10', rest:'120 sec'},
        {name:'Single-Leg Hip Thrust (bench)', cue:'One foot planted, drive through the heel and squeeze', sets:3, reps:'10–12 / leg', rest:'90 sec'},
        {name:'Leg Press', cue:'Loads the knees more than the others here — pick only if knees feel good', sets:3, reps:'10–12', rest:'120 sec'}
      ]},
      { options: [
        {name:'Smith Machine Good Mornings', cue:'Hip hinge with soft knees, push hips back, chest up', sets:3, reps:'10–12', rest:'90 sec'},
        {name:'Cable Romanian Deadlift', cue:'Cable adds constant tension, minimal knee bend', sets:3, reps:'10–12', rest:'90 sec'},
        {name:'Kettlebell Deadlift', cue:'Hip hinge, kettlebell close to shins, knees soft', sets:3, reps:'10–12', rest:'90 sec'},
        {name:'Leg Press', cue:'Loads the knees more than the others here — pick only if knees feel good', sets:3, reps:'10–12', rest:'120 sec'}
      ]},
      { options: [
        {name:'Romanian Deadlifts (dumbbell)', cue:'Hinge at the hip, minimal knee bend', sets:3, reps:'8–10', rest:'120 sec'},
        {name:'Single-Leg Romanian Deadlift (dumbbell)', cue:'Balance on one leg, hinge forward, knee stays soft', sets:3, reps:'8–10 / leg', rest:'90 sec'},
        {name:'Smith Machine Good Mornings', cue:'Hip hinge with soft knees, push hips back', sets:3, reps:'10–12', rest:'90 sec'},
        {name:'Leg Press', cue:'Loads the knees more than the others here — pick only if knees feel good', sets:3, reps:'10–12', rest:'120 sec'}
      ]},
      { options: [
        {name:'Single-Leg Hip Thrust (bench)', cue:'One foot planted, drive through the heel and squeeze', sets:3, reps:'10–12 / leg', rest:'75 sec'},
        {name:'Dumbbell Hip Thrust', cue:'Bilateral, drive through heels, squeeze at top', sets:3, reps:'10–12', rest:'75 sec'},
        {name:'Glute Bridge (bodyweight or dumbbell)', cue:'Feet flat, drive hips up, squeeze glutes at top', sets:3, reps:'15', rest:'60 sec'},
        {name:'Leg Press', cue:'Loads the knees more than the others here — pick only if knees feel good', sets:3, reps:'12–15', rest:'90 sec'}
      ]},
      { options: [
        {name:'Reverse Hyperextension / Back Extension Machine', cue:'Hip-dominant lift, squeeze glutes at the top, no load through the knee', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'45° Hyperextension (bodyweight or plate)', cue:'Hinge from the hips, squeeze glutes at the top', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Standing Cable Hip Extension', cue:'Ankle cuff, kick straight back from the hip, knee stays soft', sets:3, reps:'12 / leg', rest:'60 sec'},
        {name:'Leg Press', cue:'Loads the knees more than the others here — pick only if knees feel good', sets:3, reps:'12–15', rest:'90 sec'}
      ]},
      { options: [
        {name:'Hip Abductor Machine', cue:'Seated, outer glute, no knee stress', sets:3, reps:'15–20', rest:'60 sec'},
        {name:'Standing Cable Hip Abduction', cue:'Ankle cuff, kick out to the side, no knee load', sets:3, reps:'15 / leg', rest:'60 sec'},
        {name:'Side-Lying Hip Abduction (dumbbell)', cue:'Top leg raises straight up, controlled', sets:3, reps:'15 / leg', rest:'60 sec'},
        {name:'Leg Press', cue:'Not a direct abductor substitute and harder on the knees', sets:3, reps:'15–20', rest:'90 sec'}
      ]},
      { options: [
        {name:'Seated Leg Curl Machine', cue:'Light-controlled tempo, supports the hamstring-glute tie-in', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Lying Leg Curl Machine', cue:'Full stretch at bottom, squeeze at top', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Stability Ball Hamstring Curl', cue:'Heels on the ball, lift hips and curl the ball in', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Leg Press', cue:'Not a hamstring isolation move, and harder on the knees', sets:3, reps:'12–15', rest:'90 sec'}
      ]}
    ]
  },
  'arm-a': {
    focus: 'Arms & shoulders — set A',
    estMinutes: {strength: 50},
    note: '⏱ ~45–55 min total. Moderate weight, higher reps for a lean, defined look. Use the dropdown on any exercise to swap it.',
    exercises: [
      { options: [
        {name:'Triceps Press Machine', cue:'Main driver for shaping the back of the arm', sets:4, reps:'15', rest:'60 sec'},
        {name:'Assisted Dip Machine', cue:'Lean slightly forward to bias triceps and chest', sets:4, reps:'10–12', rest:'60 sec'},
        {name:'Overhead Triceps Extension (dumbbell)', cue:'Elbows stay close to head, full stretch at bottom', sets:4, reps:'15', rest:'60 sec'}
      ]},
      { options: [
        {name:'Triceps Pushdown (cable)', cue:'Full extension, elbows pinned', sets:3, reps:'15', rest:'45 sec'},
        {name:'Skull Crushers (dumbbell)', cue:'Elbows stay fixed, lower to forehead with control', sets:3, reps:'12–15', rest:'45 sec'},
        {name:'Overhead Triceps Extension (cable)', cue:'Elbows stay close to head, full stretch at bottom', sets:3, reps:'15', rest:'45 sec'}
      ]},
      { options: [
        {name:'Bicep Curl (dumbbell)', cue:'Control the negative, no swinging', sets:3, reps:'12–15', rest:'45 sec'},
        {name:'Cable Bicep Curl', cue:'Constant tension through the whole rep', sets:3, reps:'12–15', rest:'45 sec'},
        {name:'Preacher Curl Machine', cue:'Full stretch at bottom, squeeze at top', sets:3, reps:'12–15', rest:'45 sec'}
      ]},
      { options: [
        {name:'Shoulder Press Machine', cue:'Builds capped, defined shoulders', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Dumbbell Shoulder Press', cue:'Press straight overhead, control the descent', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Smith Machine Overhead Press', cue:'Controlled press, avoid arching the lower back', sets:3, reps:'10–12', rest:'60 sec'}
      ]},
      { options: [
        {name:'Lateral Raises (dumbbell)', cue:'Light weight, slight bend in elbow', sets:3, reps:'15', rest:'45 sec'},
        {name:'Cable Lateral Raise', cue:'Constant tension, control the descent', sets:3, reps:'15', rest:'45 sec'},
        {name:'Lateral Raise Machine', cue:'Controlled squeeze at the top', sets:3, reps:'15', rest:'45 sec'}
      ]},
      { options: [
        {name:'Chest Press Machine', cue:'Supports overall upper-body shape', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Dumbbell Bench Press', cue:'Control the descent, press up and slightly in', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Push-Ups', cue:'Full range of motion, body in a straight line', sets:3, reps:'to near failure', rest:'60 sec'}
      ]},
      { options: [
        {name:'Lat Pulldown Machine', cue:'Wide grip, squeeze shoulder blades', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Assisted Pull-Up Machine', cue:'Set assist weight so the last rep is tough but clean', sets:3, reps:'10–12', rest:'60 sec'},
        {name:'Seated Cable Row', cue:'Squeeze shoulder blades together at the finish', sets:3, reps:'12–15', rest:'60 sec'}
      ]}
    ]
  },
  'arm-b': {
    focus: 'Arms & shoulders — set B',
    estMinutes: {strength: 50},
    note: '⏱ ~45–55 min total. Different exercises so the muscles get hit from new angles — leans a bit more into back and rear delts.',
    exercises: [
      { options: [
        {name:'Assisted Pull-Up Machine', cue:'Set assist weight so the last rep is tough but clean', sets:3, reps:'10–12', rest:'75 sec'},
        {name:'Lat Pulldown Machine', cue:'Wide grip, squeeze shoulder blades', sets:3, reps:'12–15', rest:'75 sec'},
        {name:'Straight-Arm Cable Pulldown', cue:'Arms stay straight, pull down using the lats', sets:3, reps:'12–15', rest:'60 sec'}
      ]},
      { options: [
        {name:'Seated Cable Row', cue:'Squeeze shoulder blades together at the finish', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Chest-Supported Row Machine', cue:'Chest stays on the pad, row with control', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Dumbbell Bent-Over Row', cue:'Flat back, row to the hip', sets:3, reps:'12–15', rest:'60 sec'}
      ]},
      { options: [
        {name:'Hammer Curl (dumbbell)', cue:'Neutral grip, control the negative', sets:3, reps:'12–15', rest:'45 sec'},
        {name:'Cable Hammer Curl (rope)', cue:'Neutral grip on the rope, control the negative', sets:3, reps:'12–15', rest:'45 sec'},
        {name:'Bicep Curl (dumbbell)', cue:'Control the negative, no swinging', sets:3, reps:'12–15', rest:'45 sec'}
      ]},
      { options: [
        {name:'Overhead Triceps Extension (cable)', cue:'Elbows stay close to head, full stretch at bottom', sets:3, reps:'15', rest:'45 sec'},
        {name:'Triceps Pushdown (cable)', cue:'Full extension, elbows pinned', sets:3, reps:'15', rest:'45 sec'},
        {name:'Skull Crushers (dumbbell)', cue:'Elbows stay fixed, lower to forehead with control', sets:3, reps:'12–15', rest:'45 sec'}
      ]},
      { options: [
        {name:'Rear Delt Fly Machine', cue:'Light weight, focus on squeezing shoulder blades', sets:3, reps:'15', rest:'45 sec'},
        {name:'Dumbbell Rear Delt Fly (bent-over)', cue:'Hinge forward, raise dumbbells out to the sides', sets:3, reps:'15', rest:'45 sec'},
        {name:'Cable Rear Delt Fly', cue:'Cross-body cable pull, squeeze shoulder blades', sets:3, reps:'15', rest:'45 sec'}
      ]},
      { options: [
        {name:'Front Raise (dumbbell)', cue:'Light weight, raise to shoulder height', sets:3, reps:'12–15', rest:'45 sec'},
        {name:'Cable Front Raise', cue:'Constant tension, raise to shoulder height', sets:3, reps:'12–15', rest:'45 sec'},
        {name:'Plate Front Raise', cue:'Hold a weight plate, raise straight out in front', sets:3, reps:'12–15', rest:'45 sec'}
      ]},
      { options: [
        {name:'Smith Machine Overhead Press', cue:'Controlled press, avoid arching the lower back', sets:3, reps:'10–12', rest:'60 sec'},
        {name:'Dumbbell Shoulder Press', cue:'Press straight overhead, control the descent', sets:3, reps:'12–15', rest:'60 sec'},
        {name:'Shoulder Press Machine', cue:'Builds capped, defined shoulders', sets:3, reps:'12–15', rest:'60 sec'}
      ]}
    ]
  },
  'cardio-a': {
    focus: 'Peloton + abs — A',
    estMinutes: {strength: 12},
    note: '⏱ ~40–45 min. A 30-min Peloton ride is the main event, then a short no-equipment ab circuit on the floor. Pick the ride type that matches your energy today.',
    exercises: [
      { options: [
        {name:'Peloton — endurance ride', cue:'Steady effort you could hold a short conversation at', cardio:'30 min', cardioMin:30, met:7.0},
        {name:'Peloton — power zone ride', cue:'Follow the zones; mostly zone 2–4 effort', cardio:'30 min', cardioMin:30, met:7.5},
        {name:'Peloton — climb ride', cue:'Heavy resistance, slower cadence, push through the hills', cardio:'30 min', cardioMin:30, met:8.0},
        {name:'Peloton — HIIT / Tabata ride', cue:'All-out bursts with recovery in between', cardio:'30 min', cardioMin:30, met:8.5},
        {name:'Peloton — low impact ride', cue:'Easy recovery spin, good after a hard leg day', cardio:'30 min', cardioMin:30, met:5.5}
      ]},
      { options: [
        {name:'Crunches', cue:'Lower back stays down, lift with the abs, not the neck', sets:3, reps:'15–20', rest:'30 sec'},
        {name:'Reverse Crunches', cue:'Curl knees toward chest, lift hips slightly off the floor', sets:3, reps:'12–15', rest:'30 sec'},
        {name:'Heel Taps', cue:'Shoulders slightly up, reach side to side to touch each heel', sets:3, reps:'15 / side', rest:'30 sec'}
      ]},
      { options: [
        {name:'Bicycle Crunches', cue:'Slow and controlled, elbow toward opposite knee', sets:3, reps:'15 / side', rest:'30 sec'},
        {name:'Dead Bug', cue:'Lower back pressed down, extend opposite arm and leg slowly', sets:3, reps:'10 / side', rest:'30 sec'},
        {name:'Russian Twists (bodyweight)', cue:'Lean back slightly, rotate side to side with control', sets:3, reps:'12 / side', rest:'30 sec'}
      ]},
      { options: [
        {name:'Plank', cue:'Straight line head to heels, brace the core', sets:2, reps:'30–45 sec', rest:'30 sec'},
        {name:'Side Plank', cue:'Stack hips, hold steady', sets:2, reps:'20–30 sec / side', rest:'30 sec'},
        {name:'Hollow Body Hold', cue:'Lower back pressed down, arms and legs extended; bend knees to make it easier', sets:2, reps:'20–30 sec', rest:'30 sec'}
      ]}
    ]
  },
  'cardio-b': {
    focus: 'Peloton + abs — B',
    estMinutes: {strength: 12},
    note: '⏱ ~40–45 min. Same format with a harder ride option first and different ab moves for variety.',
    exercises: [
      { options: [
        {name:'Peloton — HIIT / Tabata ride', cue:'All-out bursts with recovery in between', cardio:'30 min', cardioMin:30, met:8.5},
        {name:'Peloton — climb ride', cue:'Heavy resistance, slower cadence, push through the hills', cardio:'30 min', cardioMin:30, met:8.0},
        {name:'Peloton — power zone ride', cue:'Follow the zones; mostly zone 2–4 effort', cardio:'30 min', cardioMin:30, met:7.5},
        {name:'Peloton — endurance ride', cue:'Steady effort you could hold a short conversation at', cardio:'30 min', cardioMin:30, met:7.0},
        {name:'Peloton — low impact ride', cue:'Easy recovery spin, good after a hard leg day', cardio:'30 min', cardioMin:30, met:5.5}
      ]},
      { options: [
        {name:'Lying Leg Raises', cue:'Hands under hips, lower legs slowly, stop before your back arches', sets:3, reps:'12–15', rest:'30 sec'},
        {name:'Reverse Crunches', cue:'Curl knees toward chest, lift hips slightly off the floor', sets:3, reps:'12–15', rest:'30 sec'},
        {name:'Flutter Kicks', cue:'Lower back pressed down, small quick kicks', sets:3, reps:'20–30 sec', rest:'30 sec'}
      ]},
      { options: [
        {name:'Mountain Climbers', cue:'Hands under shoulders, drive knees in at a steady pace', sets:3, reps:'30 sec', rest:'30 sec'},
        {name:'Dead Bug', cue:'Lower back pressed down, extend opposite arm and leg slowly', sets:3, reps:'10 / side', rest:'30 sec'},
        {name:'Bird Dog', cue:'On hands and knees, reach opposite arm and leg, hips level', sets:3, reps:'10 / side', rest:'30 sec'}
      ]},
      { options: [
        {name:'Side Plank', cue:'Stack hips, hold steady', sets:2, reps:'20–30 sec / side', rest:'30 sec'},
        {name:'Plank Shoulder Taps', cue:'High plank, tap opposite shoulder, keep hips still', sets:2, reps:'10 / side', rest:'30 sec'},
        {name:'Plank', cue:'Straight line head to heels, brace the core', sets:2, reps:'30–45 sec', rest:'30 sec'}
      ]}
    ]
  },
  'rest': {
    focus: 'Rest',
    estMinutes: {strength: 0},
    note: 'Full rest. Recovery is when the shape you\u2019re training for actually gets built.',
    exercises: []
  }
};

/* Upper-body strength versions: one heavy lift first, then the original day */
var HEAVY_PRESS = { options: [
  {name:'Shoulder Press Machine', cue:'Strength lift. Warm up first; last 2 reps should be hard but clean', sets:4, reps:'6–10', rest:'2 min', heavy:true},
  {name:'Dumbbell Shoulder Press', cue:'Strength lift. Press straight overhead, control the descent', sets:4, reps:'6–10', rest:'2 min', heavy:true},
  {name:'Chest Press Machine', cue:'Strength lift. Controlled descent, strong press', sets:4, reps:'6–10', rest:'2 min', heavy:true}
]};
var HEAVY_PULL = { options: [
  {name:'Lat Pulldown Machine', cue:'Strength lift. Pull to upper chest, squeeze shoulder blades', sets:4, reps:'6–10', rest:'2 min', heavy:true},
  {name:'Assisted Pull-Up Machine', cue:'Strength lift. Use less assist each month', sets:4, reps:'6–8', rest:'2 min', heavy:true},
  {name:'Seated Cable Row', cue:'Strength lift. Chest up, row to the stomach', sets:4, reps:'6–10', rest:'2 min', heavy:true}
]};
TEMPLATES['arm-a-str'] = {
  focus: 'Upper body A — strength first',
  estMinutes: {strength: 55},
  note: '⏱ ~50–55 min. Starts with one heavy press for strength, then the usual set A work. When you hit 10 reps on all 4 sets, add weight.',
  exercises: [HEAVY_PRESS].concat(TEMPLATES['arm-a'].exercises.filter(function(x, i){ return i !== 3; }))
};
TEMPLATES['arm-b-str'] = {
  focus: 'Upper body B — strength first',
  estMinutes: {strength: 55},
  note: '⏱ ~50–55 min. Starts with one heavy pull for strength, then the usual set B work. Fewer reps, more weight, longer rest on the first lift.',
  exercises: [HEAVY_PULL].concat(TEMPLATES['arm-b'].exercises.filter(function(x, i){ return i !== 0; }))
};

var TEMPLATE_META = {
  'leg-glute':    {cat:'leg',    label:'Leg — glute strength (hip thrust)'},
  'leg-hinge':    {cat:'leg',    label:'Leg — glute strength (RDL, knee-friendly)'},
  'leg-standard': {cat:'leg',    label:'Leg — standard'},
  'leg-knee':     {cat:'leg',    label:'Leg — knee-friendly'},
  'arm-a-str':    {cat:'arm',    label:'Upper A — strength first'},
  'arm-b-str':    {cat:'arm',    label:'Upper B — strength first'},
  'arm-a':        {cat:'arm',    label:'Arm — set A'},
  'arm-b':        {cat:'arm',    label:'Arm — set B'},
  'cardio-a':     {cat:'cardio', label:'Peloton + abs — A'},
  'cardio-b':     {cat:'cardio', label:'Peloton + abs — B'},
  'rest':         {cat:'rest',   label:'Rest day'}
};
var TEMPLATE_ORDER = ['leg-glute','leg-hinge','leg-standard','leg-knee','arm-a-str','arm-b-str','arm-a','arm-b','cardio-a','cardio-b','rest'];
var CAT_LABEL = {leg:'Leg', arm:'Arm', cardio:'Cardio', rest:'Rest'};
var CAT_VAR = {leg:'var(--cat-leg)', arm:'var(--cat-arm)', cardio:'var(--cat-cardio)', rest:'var(--cat-rest)'};

var ADD_POOLS = {
  leg: [
    {name:'Smith Machine Hip Thrust', cue:'Upper back on bench, bar across hips, squeeze glutes hard at top', sets:3, reps:'12–15', rest:'90 sec'},
    {name:'Dumbbell Hip Thrust', cue:'Upper back on bench, dumbbell across hips, squeeze at top', sets:3, reps:'12–15', rest:'90 sec'},
    {name:'Single-Leg Hip Thrust (bench)', cue:'One foot planted, drive through the heel and squeeze', sets:3, reps:'10–12 / leg', rest:'75 sec'},
    {name:'Leg Press', cue:'Feet high & wide on platform for glute emphasis', sets:3, reps:'12–15', rest:'90 sec'},
    {name:'Hack Squat Machine', cue:'Feet slightly forward, control the descent', sets:3, reps:'12–15', rest:'90 sec'},
    {name:'Walking Lunges (dumbbell)', cue:'Long stride, back knee taps close to the floor', sets:3, reps:'12 / leg', rest:'90 sec'},
    {name:'Smith Machine Squats', cue:'Feet slightly wider than hips', sets:3, reps:'10–12', rest:'90 sec'},
    {name:'Goblet Squats (dumbbell/kettlebell)', cue:'Elbows inside knees at the bottom, chest up', sets:3, reps:'12–15', rest:'90 sec'},
    {name:'Leg Extension Machine', cue:'Quad-focused, controlled squeeze at the top', sets:3, reps:'12–15', rest:'60 sec'},
    {name:'Glute Elite Machine', cue:'Full range of motion, squeeze at top', sets:3, reps:'15 / leg', rest:'60 sec'},
    {name:'Cable Glute Kickback', cue:'Slight forward lean, kick back and squeeze', sets:3, reps:'15 / leg', rest:'45 sec'},
    {name:'Bulgarian Split Squat (dumbbell)', cue:'Rear foot up on a bench, drive through the front heel', sets:3, reps:'12 / leg', rest:'60 sec'},
    {name:'Curtsy Lunge (dumbbell)', cue:'Step back and across, squeeze the glute of the standing leg', sets:3, reps:'12 / leg', rest:'60 sec'},
    {name:'Romanian Deadlifts (dumbbell)', cue:'Feel the stretch in hamstrings', sets:3, reps:'10–12', rest:'90 sec'},
    {name:'Cable Romanian Deadlift', cue:'Cable adds constant tension through the hinge', sets:3, reps:'10–12', rest:'90 sec'},
    {name:'Smith Machine Good Mornings', cue:'Hip hinge with soft knees, push hips back', sets:3, reps:'10–12', rest:'90 sec'},
    {name:'Kettlebell Squats', cue:'Goblet-style, go deep, wide stance for glutes', sets:3, reps:'12–15', rest:'90 sec'},
    {name:'Sumo Squats (dumbbell)', cue:'Wide stance, toes out, sit straight down', sets:3, reps:'12–15', rest:'90 sec'},
    {name:'Step-Ups (bench, dumbbell)', cue:'Drive through the front heel, control the step down', sets:3, reps:'12 / leg', rest:'90 sec'},
    {name:'Abductor Machine', cue:'Outer thigh, controlled tempo', sets:3, reps:'15–20', rest:'60 sec'},
    {name:'Adductor Machine', cue:'Inner thigh, controlled tempo', sets:3, reps:'15–20', rest:'60 sec'},
    {name:'Standing Cable Hip Abduction', cue:'Ankle cuff, kick out to the side and control the return', sets:3, reps:'15 / leg', rest:'60 sec'},
    {name:'Side-Lying Hip Abduction (dumbbell)', cue:'Top leg raises straight up, control the lower', sets:3, reps:'15 / leg', rest:'60 sec'},
    {name:'Reverse Hyperextension / Back Extension Machine', cue:'Hip-dominant lift, squeeze glutes at the top', sets:3, reps:'12–15', rest:'60 sec'},
    {name:'Glute Bridge (bodyweight or dumbbell)', cue:'Feet flat, drive hips up, squeeze glutes at top', sets:3, reps:'15', rest:'60 sec'},
    {name:'Seated Leg Curl Machine', cue:'Controlled tempo, supports the hamstring-glute tie-in', sets:3, reps:'12–15', rest:'60 sec'},
    {name:'Lying Leg Curl Machine', cue:'Full stretch at bottom, squeeze at top', sets:3, reps:'12–15', rest:'60 sec'},
    {name:'Calf Raise Machine', cue:'Full stretch at the bottom, pause at the top', sets:3, reps:'15–20', rest:'45 sec'}
  ],
  arm: [
    {name:'Triceps Press Machine', cue:'Main driver for shaping the back of the arm', sets:3, reps:'15', rest:'60 sec'},
    {name:'Assisted Dip Machine', cue:'Lean slightly forward to bias triceps and chest', sets:3, reps:'10–12', rest:'60 sec'},
    {name:'Overhead Triceps Extension (dumbbell)', cue:'Elbows stay close to head, full stretch at bottom', sets:3, reps:'15', rest:'45 sec'},
    {name:'Triceps Pushdown (cable)', cue:'Full extension, elbows pinned', sets:3, reps:'15', rest:'45 sec'},
    {name:'Skull Crushers (dumbbell)', cue:'Elbows stay fixed, lower to forehead with control', sets:3, reps:'12–15', rest:'45 sec'},
    {name:'Bicep Curl (dumbbell)', cue:'Control the negative, no swinging', sets:3, reps:'12–15', rest:'45 sec'},
    {name:'Cable Bicep Curl', cue:'Constant tension through the whole rep', sets:3, reps:'12–15', rest:'45 sec'},
    {name:'Preacher Curl Machine', cue:'Full stretch at bottom, squeeze at top', sets:3, reps:'12–15', rest:'45 sec'},
    {name:'Hammer Curl (dumbbell)', cue:'Neutral grip, control the negative', sets:3, reps:'12–15', rest:'45 sec'},
    {name:'Shoulder Press Machine', cue:'Builds capped, defined shoulders', sets:3, reps:'12–15', rest:'60 sec'},
    {name:'Dumbbell Shoulder Press', cue:'Press straight overhead, control the descent', sets:3, reps:'12–15', rest:'60 sec'},
    {name:'Smith Machine Overhead Press', cue:'Controlled press, avoid arching the lower back', sets:3, reps:'10–12', rest:'60 sec'},
    {name:'Lateral Raises (dumbbell)', cue:'Light weight, slight bend in elbow', sets:3, reps:'15', rest:'45 sec'},
    {name:'Cable Lateral Raise', cue:'Constant tension, control the descent', sets:3, reps:'15', rest:'45 sec'},
    {name:'Chest Press Machine', cue:'Supports overall upper-body shape', sets:3, reps:'12–15', rest:'60 sec'},
    {name:'Dumbbell Bench Press', cue:'Control the descent, press up and slightly in', sets:3, reps:'12–15', rest:'60 sec'},
    {name:'Pec Deck / Chest Fly Machine', cue:'Controlled squeeze at the center', sets:3, reps:'12–15', rest:'45 sec'},
    {name:'Push-Ups', cue:'Full range of motion, body in a straight line', sets:3, reps:'to near failure', rest:'60 sec'},
    {name:'Lat Pulldown Machine', cue:'Wide grip, squeeze shoulder blades', sets:3, reps:'12–15', rest:'60 sec'},
    {name:'Assisted Pull-Up Machine', cue:'Set assist weight so the last rep is tough but clean', sets:3, reps:'10–12', rest:'60 sec'},
    {name:'Seated Cable Row', cue:'Squeeze shoulder blades together at the finish', sets:3, reps:'12–15', rest:'60 sec'},
    {name:'Dumbbell Bent-Over Row', cue:'Flat back, row to the hip', sets:3, reps:'12–15', rest:'60 sec'},
    {name:'Rear Delt Fly Machine', cue:'Light weight, focus on squeezing shoulder blades', sets:3, reps:'15', rest:'45 sec'},
    {name:'Front Raise (dumbbell)', cue:'Light weight, raise to shoulder height', sets:3, reps:'12–15', rest:'45 sec'}
  ],
  cardio: [
    {name:'Crunches', cue:'Lower back stays down, lift with the abs, not the neck', sets:3, reps:'15–20', rest:'30 sec'},
    {name:'Reverse Crunches', cue:'Curl knees toward chest, lift hips slightly off the floor', sets:3, reps:'12–15', rest:'30 sec'},
    {name:'Bicycle Crunches', cue:'Slow and controlled, elbow toward opposite knee', sets:3, reps:'15 / side', rest:'30 sec'},
    {name:'Heel Taps', cue:'Shoulders slightly up, reach side to side to touch each heel', sets:3, reps:'15 / side', rest:'30 sec'},
    {name:'Lying Leg Raises', cue:'Hands under hips, lower legs slowly, stop before your back arches', sets:3, reps:'12–15', rest:'30 sec'},
    {name:'Flutter Kicks', cue:'Lower back pressed down, small quick kicks', sets:3, reps:'20–30 sec', rest:'30 sec'},
    {name:'Dead Bug', cue:'Lower back pressed down, extend opposite arm and leg slowly', sets:3, reps:'10 / side', rest:'30 sec'},
    {name:'Bird Dog', cue:'On hands and knees, reach opposite arm and leg, hips level', sets:3, reps:'10 / side', rest:'30 sec'},
    {name:'Russian Twists (bodyweight)', cue:'Lean back slightly, rotate side to side with control', sets:3, reps:'12 / side', rest:'30 sec'},
    {name:'Mountain Climbers', cue:'Hands under shoulders, drive knees in at a steady pace', sets:3, reps:'30 sec', rest:'30 sec'},
    {name:'Plank', cue:'Straight line head to heels, brace the core', sets:2, reps:'30–45 sec', rest:'30 sec'},
    {name:'Side Plank', cue:'Stack hips, hold steady', sets:2, reps:'20–30 sec / side', rest:'30 sec'},
    {name:'Plank Shoulder Taps', cue:'High plank, tap opposite shoulder, keep hips still', sets:2, reps:'10 / side', rest:'30 sec'},
    {name:'Hollow Body Hold', cue:'Lower back pressed down, arms and legs extended', sets:2, reps:'20–30 sec', rest:'30 sec'},
    {name:'V-Ups', cue:'Reach hands toward feet, bend knees to make it easier', sets:3, reps:'10–12', rest:'30 sec'}
  ]
};
var CARDIO_NAMES = ['Peloton bike ride','Peloton HIIT ride','Peloton bike — low impact','Outdoor walk'];

/* Calorie estimates: MET x body weight (kg) x hours. Strength MET is
   deliberately modest because much of a lifting session is rest. */
var MET_STRENGTH = 3.5;
var QUICK_TYPES = [
  {id:'pelo-end',   name:'Peloton — endurance',    met:7.0},
  {id:'pelo-pz',    name:'Peloton — power zone',   met:7.5},
  {id:'pelo-climb', name:'Peloton — climb',        met:8.0},
  {id:'pelo-hiit',  name:'Peloton — HIIT/Tabata',  met:8.5},
  {id:'pelo-low',   name:'Peloton — low impact',   met:5.5},
  {id:'other',      name:'Other cardio',           met:6.0}
];
function guessMet(name){
  var n = name.toLowerCase();
  if(n.indexOf('low impact') !== -1) return 5.5;
  if(n.indexOf('hiit') !== -1 || n.indexOf('tabata') !== -1) return 8.5;
  if(n.indexOf('climb') !== -1) return 8.0;
  if(n.indexOf('peloton') !== -1 || n.indexOf('bike') !== -1 || n.indexOf('cycl') !== -1 || n.indexOf('spin') !== -1 || n.indexOf('ride') !== -1) return 7.0;
  if(n.indexOf('run') !== -1 || n.indexOf('jog') !== -1) return 8.0;
  if(n.indexOf('walk') !== -1) return 3.5;
  if(n.indexOf('yoga') !== -1 || n.indexOf('stretch') !== -1) return 2.5;
  return 6.0;
}

var SLOTS = [
  {id:'mon', label:'MON', defaultName:'Monday',    defaultTemplate:'leg-standard'},
  {id:'tue', label:'TUE', defaultName:'Tuesday',   defaultTemplate:'arm-a'},
  {id:'wed', label:'WED', defaultName:'Wednesday', defaultTemplate:'cardio-a'},
  {id:'thu', label:'THU', defaultName:'Thursday',  defaultTemplate:'leg-knee'},
  {id:'fri', label:'FRI', defaultName:'Friday',    defaultTemplate:'arm-b'},
  {id:'sat', label:'SAT', defaultName:'Saturday',  defaultTemplate:'cardio-b'},
  {id:'sun', label:'SUN', defaultName:'Sunday',    defaultTemplate:'rest'}
];
var SLOT_INDEX = {}, SLOT_BY_ID = {};
SLOTS.forEach(function(s, i){ SLOT_INDEX[s.id] = i; SLOT_BY_ID[s.id] = s; });
var INDEX_WEEKDAY = ['sun','mon','tue','wed','thu','fri','sat'];
var MONTH_NAMES = ['January','February','March','April','May','June','July','August','September','October','November','December'];
var MONTH_SHORT = ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];

var checkSvg = '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>';
var chevronSvg = '<svg class="chevron" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"></polyline></svg>';

/* ---------- STORAGE ---------- */
var NS = 'toneshape.v1.', NS2 = 'toneshape.v2.';
var K = {
  assign: NS+'assign', names: NS+'names', choices: NS+'choices', added: NS+'added',
  targets: NS+'targets', weight: NS+'weight', theme: NS+'theme', oldLog: NS+'log',
  progress: NS2+'progress', log: NS2+'log', lifts: NS2+'lifts',
  custom: NS2+'custom', swaps: NS2+'swaps', quick: NS2+'quick'
};
function read(key, fallback){
  try{ var raw = localStorage.getItem(key); return raw === null ? fallback : JSON.parse(raw); }
  catch(e){ return fallback; }
}
function write(key, value){
  try{ localStorage.setItem(key, JSON.stringify(value)); }
  catch(e){ console.error('Could not save', key, e); }
}

var progress = {};      // {date: {templateKey: {exKey: [setIdx]}}}
var workoutLog = {};    // {date: {cat, min, kcal, src, type, slot}}
var lifts = {};         // {exerciseName: {date: weightLbs}}
var customNames = [];
var swaps = {};         // {slot: {templateKey: {exKey: typedName}}}
var quickPrefs = {min:30, type:'pelo-end'};
var dayAssign = {}, dayNames = {}, exerciseChoice = {}, addedExercises = {};
var targets = {leg:2, arm:2, cardio:2};
var userWeightLbs = 172;
var theme = 'dark';
var addedIdCounter = 0;
var currentOpenSlotId = null;
var calCursor = new Date();

function saveProgress(){ write(K.progress, progress); }
function saveLog(){ write(K.log, workoutLog); }

/* ---------- DATES ---------- */
function pad2(n){ return (n < 10 ? '0' : '') + n; }
function dateKey(d){ return d.getFullYear()+'-'+pad2(d.getMonth()+1)+'-'+pad2(d.getDate()); }
function startOfToday(){ var n = new Date(); return new Date(n.getFullYear(), n.getMonth(), n.getDate()); }
function todayKey(){ return dateKey(new Date()); }
function parseKey(k){ var p = k.split('-'); return new Date(+p[0], +p[1]-1, +p[2]); }
function shortDate(k){ var d = parseKey(k); return MONTH_SHORT[d.getMonth()]+' '+d.getDate(); }
function mondayOf(d){
  var x = new Date(d.getFullYear(), d.getMonth(), d.getDate());
  x.setDate(x.getDate() - ((x.getDay() + 6) % 7));
  return x;
}
function slotDate(slotId){
  var d = mondayOf(new Date());
  d.setDate(d.getDate() + SLOT_INDEX[slotId]);
  return d;
}
function logDateFor(slotId){
  var d = slotDate(slotId), t = startOfToday();
  return d > t ? t : d;
}
function todaySlotId(){ return INDEX_WEEKDAY[new Date().getDay()]; }

/* ---------- HELPERS ---------- */
function esc(s){ return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;'); }
function copy(o){ var out = {}; for(var p in o){ if(Object.prototype.hasOwnProperty.call(o,p)) out[p] = o[p]; } return out; }
function kg(){ return userWeightLbs * 0.453592; }
function clampInt(v, fallback){ var n = parseInt(v, 10); if(isNaN(n) || n < 0) return fallback; return Math.min(n, 7); }
function sameName(a, b){ return a.trim().toLowerCase() === b.trim().toLowerCase(); }
function findPool(name){
  var cats = ['leg','arm','cardio'];
  for(var c=0; c<cats.length; c++){
    var list = ADD_POOLS[cats[c]];
    for(var i=0; i<list.length; i++){ if(sameName(list[i].name, name)) return list[i]; }
  }
  return null;
}
function newAddedId(){ addedIdCounter += 1; return 'add'+Date.now()+'-'+addedIdCounter; }

function getTemplateKey(slotId){ var k = dayAssign[slotId]; return TEMPLATES[k] ? k : 'rest'; }
function getDayName(slot){ return dayNames[slot.id] || slot.defaultName; }
function getCategory(tk){ return TEMPLATE_META[tk] ? TEMPLATE_META[tk].cat : 'rest'; }
function getChosenOptionIdx(slotId, tk, exKey){
  return (exerciseChoice[slotId] && exerciseChoice[slotId][tk] && exerciseChoice[slotId][tk][exKey]) || 0;
}
function setChosenOptionIdx(slotId, tk, exKey, optIdx){
  if(!exerciseChoice[slotId]) exerciseChoice[slotId] = {};
  if(!exerciseChoice[slotId][tk]) exerciseChoice[slotId][tk] = {};
  exerciseChoice[slotId][tk][exKey] = optIdx;
  write(K.choices, exerciseChoice);
}
function getTypedSwap(slotId, tk, exKey){ return swaps[slotId] && swaps[slotId][tk] && swaps[slotId][tk][exKey]; }
function setTypedSwap(slotId, tk, exKey, name){
  if(!swaps[slotId]) swaps[slotId] = {};
  if(!swaps[slotId][tk]) swaps[slotId][tk] = {};
  if(name) swaps[slotId][tk][exKey] = name; else delete swaps[slotId][tk][exKey];
  write(K.swaps, swaps);
}
function ensureAddedList(slotId, tk){
  if(!addedExercises[slotId]) addedExercises[slotId] = {};
  if(!addedExercises[slotId][tk]) addedExercises[slotId][tk] = [];
  return addedExercises[slotId][tk];
}
function rememberCustom(name){
  if(findPool(name)) return;
  for(var i=0; i<customNames.length; i++){ if(sameName(customNames[i], name)) return; }
  customNames.push(name);
  write(K.custom, customNames);
}

function getResolvedEntries(slotId, tk){
  var base = TEMPLATES[tk].exercises.map(function(exSlot, ei){
    var key = String(ei);
    var typed = getTypedSwap(slotId, tk, key);
    var idx = getChosenOptionIdx(slotId, tk, key);
    if(!exSlot.options[idx]) idx = 0;
    var out = copy(typed ? exSlot.options[0] : exSlot.options[idx]);
    out.key = key; out.swapOptions = exSlot.options; out.isAdded = false;
    out.optIdx = typed ? -1 : idx; out.isTyped = !!typed;
    if(typed){
      out.name = typed;
      out.cue = 'Your swap. Same sets, reps, and rest as the original';
      if(out.cardio) out.met = guessMet(typed);
    }
    return out;
  });
  var added = ensureAddedList(slotId, tk).map(function(item){
    var out = copy(item);
    out.key = item.id; out.swapOptions = null; out.isAdded = true; out.isTyped = false;
    return out;
  });
  return base.concat(added);
}

function getEffectiveDay(slot){
  var tk = getTemplateKey(slot.id), tmpl = TEMPLATES[tk];
  return {
    id: slot.id, label: slot.label, name: getDayName(slot), templateKey: tk,
    cat: getCategory(tk), focus: tmpl.focus, note: tmpl.note, estMinutes: tmpl.estMinutes,
    exercises: getResolvedEntries(slot.id, tk)
  };
}

function strengthMinutes(day){
  if(day.cat === 'rest') return 0;
  var addedStrength = day.exercises.filter(function(e){ return e.isAdded && !e.cardio; }).length;
  return (day.estMinutes.strength || 0) + addedStrength * 5;
}
function cardioMinutes(day){
  return day.exercises.reduce(function(s, e){ return e.cardio ? s + (e.cardioMin || 0) : s; }, 0);
}
function calcCalories(day){
  if(day.cat === 'rest') return 0;
  var k = MET_STRENGTH * kg() * strengthMinutes(day) / 60;
  day.exercises.forEach(function(e){ if(e.cardio) k += (e.met || 6) * kg() * (e.cardioMin || 0) / 60; });
  return Math.round(k);
}

function getProg(slotId){
  var dk = dateKey(slotDate(slotId)), tk = getTemplateKey(slotId);
  if(!progress[dk]) progress[dk] = {};
  if(!progress[dk][tk]) progress[dk][tk] = {};
  var p = progress[dk][tk];
  getResolvedEntries(slotId, tk).forEach(function(e){ if(!Array.isArray(p[e.key])) p[e.key] = []; });
  return p;
}
function totals(day, prog){
  var total = 0, done = 0;
  day.exercises.forEach(function(e){
    var units = e.cardio ? 1 : e.sets;
    total += units;
    done += Math.min((prog[e.key] || []).length, units);
  });
  return {total: total, done: done};
}

function lastWeight(name, beforeKey){
  var h = lifts[name];
  if(!h) return null;
  var keys = Object.keys(h).filter(function(k){ return k < beforeKey; }).sort();
  if(!keys.length) return null;
  var k = keys[keys.length - 1];
  return {date: k, w: h[k]};
}

/* ---------- LOAD ---------- */
function loadAll(){
  var savedTheme = read(K.theme, null);
  if(savedTheme === 'light' || savedTheme === 'dark') theme = savedTheme;
  else if(window.matchMedia && window.matchMedia('(prefers-color-scheme: light)').matches) theme = 'light';
  applyTheme();

  var a = read(K.assign, {}) || {};
  SLOTS.forEach(function(s){ dayAssign[s.id] = TEMPLATES[a[s.id]] ? a[s.id] : s.defaultTemplate; });
  dayNames = read(K.names, {}) || {};
  exerciseChoice = read(K.choices, {}) || {};
  addedExercises = read(K.added, {}) || {};
  swaps = read(K.swaps, {}) || {};
  lifts = read(K.lifts, {}) || {};
  customNames = read(K.custom, []) || [];
  var qp = read(K.quick, null);
  if(qp && typeof qp === 'object'){ if(qp.min) quickPrefs.min = qp.min; if(qp.type) quickPrefs.type = qp.type; }

  var t = read(K.targets, null);
  if(t && typeof t === 'object'){
    targets.leg = clampInt(t.leg, 2); targets.arm = clampInt(t.arm, 2); targets.cardio = clampInt(t.cardio, 2);
  }
  var w = read(K.weight, null);
  if(typeof w === 'number' && w > 0) userWeightLbs = w;

  // Log: migrate the old format ({date: 'leg'}) the first time
  var lg = read(K.log, null);
  if(!lg){
    lg = {};
    var old = read(K.oldLog, {}) || {};
    Object.keys(old).forEach(function(k){ if(typeof old[k] === 'string') lg[k] = {cat: old[k], src:'manual'}; });
  }
  Object.keys(lg).forEach(function(k){
    if(typeof lg[k] === 'string') lg[k] = {cat: lg[k], src:'manual'};
    if(!lg[k] || !CAT_LABEL[lg[k].cat]) delete lg[k];
  });
  workoutLog = lg;
  saveLog();

  // Progress is per date; drop anything older than ~4 months
  progress = read(K.progress, {}) || {};
  var cutoff = startOfToday(); cutoff.setDate(cutoff.getDate() - 120);
  var ck = dateKey(cutoff);
  Object.keys(progress).forEach(function(k){ if(k < ck) delete progress[k]; });

  currentOpenSlotId = todaySlotId();
}

function applyTheme(){
  document.documentElement.setAttribute('data-theme', theme);
  var meta = document.querySelector('meta[name="theme-color"]');
  if(meta) meta.setAttribute('content', theme === 'dark' ? '#0D1117' : '#FAF9FF');
  var btn = document.getElementById('themeBtn');
  if(btn) btn.textContent = theme === 'dark' ? '☀' : '☾';
}

/* ---------- AUTO LOG ---------- */
function syncAutoLog(slot){
  var day = getEffectiveDay(slot);
  var t = totals(day, getProg(slot.id));
  var dk = dateKey(logDateFor(slot.id));
  var cur = workoutLog[dk];
  if(t.total > 0 && t.done === t.total){
    if(!cur){
      workoutLog[dk] = {cat: day.cat, src:'auto', slot: slot.id,
        min: strengthMinutes(day) + cardioMinutes(day), kcal: calcCalories(day)};
      saveLog();
    }
  } else if(cur && cur.src === 'auto' && cur.slot === slot.id){
    delete workoutLog[dk];
    saveLog();
  }
}

/* ---------- QUICK LOG ---------- */
function quickKcal(cat, min, type){
  if(cat === 'rest') return 0;
  var met = MET_STRENGTH;
  if(cat === 'cardio'){
    met = 6.0;
    QUICK_TYPES.forEach(function(q){ if(q.id === type) met = q.met; });
  }
  return Math.round(met * kg() * min / 60);
}
function renderQuick(){
  var e = workoutLog[todayKey()];
  document.querySelectorAll('.qbtn').forEach(function(b){
    b.classList.toggle('on', !!e && e.cat === b.getAttribute('data-cat'));
  });
  var extra = document.getElementById('quickExtra');
  var typeSel = document.getElementById('quickType');
  var minEl = document.getElementById('quickMin');
  extra.classList.toggle('open', !!e && e.cat !== 'rest');
  typeSel.style.display = (e && e.cat === 'cardio') ? '' : 'none';
  minEl.value = (e && e.min) ? e.min : quickPrefs.min;
  typeSel.value = (e && e.type) ? e.type : quickPrefs.type;
  if(typeSel.selectedIndex < 0) typeSel.selectedIndex = 0;
  var st = document.getElementById('quickStatus');
  if(!e){ st.className = 'target-status'; st.textContent = 'Not logged'; }
  else {
    st.className = 'target-status ok';
    st.textContent = CAT_LABEL[e.cat] + (e.min ? ' · ' + e.min + ' min' : '') + (e.kcal ? ' · ~' + e.kcal + ' kcal' : '');
  }
}
function updateQuickEntry(){
  var tk = todayKey(), e = workoutLog[tk];
  var min = parseInt(document.getElementById('quickMin').value, 10);
  var type = document.getElementById('quickType').value;
  if(isNaN(min) || min < 1) return;
  quickPrefs.min = min; quickPrefs.type = type;
  write(K.quick, quickPrefs);
  if(e && e.cat !== 'rest'){
    e.min = min;
    if(e.cat === 'cardio') e.type = type;
    e.kcal = quickKcal(e.cat, min, e.type);
    saveLog();
    renderQuick(); renderCalendar(); renderDays();
  }
}

/* ---------- TARGETS ---------- */
function countScheduled(){
  var counts = {leg:0, arm:0, cardio:0, rest:0};
  SLOTS.forEach(function(s){ counts[getCategory(getTemplateKey(s.id))] += 1; });
  return counts;
}
function renderTargets(){
  var counts = countScheduled(), grid = document.getElementById('targetGrid'), allMet = true, html = '';
  ['leg','arm','cardio'].forEach(function(cat){
    var have = counts[cat], want = targets[cat];
    if(have < want) allMet = false;
    var need = have < want ? 'add ' + (want-have) + ' more' : (have > want ? (have-want) + ' over target' : 'on target');
    html += '<div class="target-pill" style="border-left-color:'+CAT_VAR[cat]+'">'+
      '<div class="tp-name">'+CAT_LABEL[cat]+' days</div>'+
      '<div class="tp-count" style="color:'+CAT_VAR[cat]+'">'+have+' / '+want+'</div>'+
      '<div class="tp-need">'+need+'</div></div>';
  });
  grid.innerHTML = html;
  var status = document.getElementById('targetStatus');
  status.className = 'target-status ' + (allMet ? 'ok' : 'off');
  status.textContent = allMet ? 'On track' : 'Needs adjusting';
  document.getElementById('tLeg').value = targets.leg;
  document.getElementById('tArm').value = targets.arm;
  document.getElementById('tCardio').value = targets.cardio;
  document.getElementById('heroEyebrow').textContent = (7 - counts.rest) + ' training days · ' + counts.rest + ' rest';
}

/* ---------- WEEK ---------- */
function exHtml(ex, prog, dk){
  var doneIdxs = prog[ex.key] || [];
  var units = ex.cardio ? 1 : ex.sets;
  var isDone = doneIdxs.length >= units;
  var tags = (ex.heavy ? '<span class="tag heavy">HEAVY</span>' : '') +
             (ex.isAdded ? '<span class="tag added">ADDED</span>' : '') +
             (ex.isTyped ? '<span class="tag typed">YOUR SWAP</span>' : '');

  var swapHtml = '';
  if(ex.swapOptions){
    swapHtml = '<select class="ex-swap" data-action="swap" data-key="'+ex.key+'" aria-label="Swap this exercise">'+
      ex.swapOptions.map(function(opt, oi){
        return '<option value="'+oi+'"'+(oi === ex.optIdx ? ' selected' : '')+'>'+esc(opt.name)+'</option>';
      }).join('')+
      (ex.isTyped ? '<option value="typed" selected>✎ '+esc(ex.name)+'</option>' : '')+
      '<option value="type-new">✎ Type your own…</option>'+
    '</select>';
  }

  var main;
  if(ex.cardio){
    var ck = Math.round((ex.met || 6) * kg() * (ex.cardioMin || 0) / 60);
    main = '<div class="ex-name">'+esc(ex.name)+tags+'</div>'+
      '<div class="ex-cue">'+esc(ex.cue)+'</div>'+
      '<div class="ex-stats"><div class="stat sets">'+esc(ex.cardio)+'</div><div class="stat">~'+ck+' kcal</div></div>'+
      swapHtml;
  } else {
    var boxes = '';
    for(var si=0; si<ex.sets; si++){
      var on = doneIdxs.indexOf(si) !== -1;
      boxes += '<button class="set-box'+(on ? ' done' : '')+'" data-action="set" data-key="'+ex.key+'" data-set="'+si+'" aria-label="Set '+(si+1)+'">'+(on ? '✓' : (si+1))+'</button>';
    }
    var cur = lifts[ex.name] && lifts[ex.name][dk];
    var lw = lastWeight(ex.name, dk);
    var lastTxt = lw ? 'Last: <b>'+lw.w+' lb</b> · '+shortDate(lw.date) : 'No weight logged yet';
    main = '<div class="ex-name">'+esc(ex.name)+tags+'</div>'+
      '<div class="ex-cue">'+esc(ex.cue)+'</div>'+
      '<div class="ex-stats">'+
        '<div class="stat sets">'+ex.sets+' sets</div>'+
        '<div class="stat">'+esc(ex.reps)+' reps</div>'+
        '<div class="stat">rest '+esc(ex.rest)+'</div>'+
      '</div>'+
      '<div class="set-boxes">'+boxes+'</div>'+
      '<div class="weight-row">'+
        '<input class="num-input weight-input" type="number" inputmode="decimal" min="0" step="2.5" placeholder="—" data-action="weight" data-name="'+esc(ex.name)+'" value="'+(cur != null ? cur : '')+'" aria-label="Weight used for '+esc(ex.name)+' in pounds">'+
        '<span class="mini-label">lbs</span>'+
        '<span class="last-time">'+lastTxt+'</span>'+
      '</div>'+
      swapHtml;
  }
  var removeHtml = ex.isAdded ? '<button class="ex-remove" data-action="remove" data-key="'+ex.key+'" aria-label="Remove exercise">✕</button>' : '';
  return '<div class="ex'+(isDone ? ' done' : '')+'">'+
    '<button class="ex-check'+(isDone ? ' done' : '')+'" data-action="check" data-key="'+ex.key+'" aria-label="Mark '+esc(ex.name)+' done">'+checkSvg+'</button>'+
    '<div class="ex-main">'+main+'</div>'+removeHtml+'</div>';
}

function addRowHtml(slot, day){
  var current = day.exercises.map(function(e){ return e.name.toLowerCase(); });
  var names = [];
  var cats = [day.cat].concat(['leg','arm','cardio'].filter(function(c){ return c !== day.cat; }));
  cats.forEach(function(c){ (ADD_POOLS[c] || []).forEach(function(p){ names.push(p.name); }); });
  names = names.concat(customNames, CARDIO_NAMES);
  var seen = {}, opts = '';
  names.forEach(function(n){
    var k = n.toLowerCase();
    if(seen[k] || current.indexOf(k) !== -1) return;
    seen[k] = true;
    opts += '<option value="'+esc(n)+'"></option>';
  });
  return '<div class="add-exercise-row">'+
    '<p class="add-label">Add an exercise. Pick from the list or type anything.</p>'+
    '<input class="add-input" list="dl-'+slot.id+'" placeholder="Cable kickbacks" data-role="add-name" aria-label="Exercise name">'+
    '<datalist id="dl-'+slot.id+'">'+opts+'</datalist>'+
    '<input class="num-input" type="number" min="1" max="180" value="3" data-role="add-amt" aria-label="How many sets or minutes">'+
    '<select class="unit-select" data-role="add-unit" aria-label="Sets or minutes"><option value="sets">sets</option><option value="min">min</option></select>'+
    '<button class="add-btn" data-action="add">+ ADD</button>'+
    '<p class="add-err" data-role="add-err"></p>'+
  '</div>';
}

function renderDays(){
  var stripHtml = '', html = '';
  var tSlot = todaySlotId();

  SLOTS.forEach(function(slot, di){
    var day = getEffectiveDay(slot);
    var prog = getProg(slot.id);
    var isRest = day.cat === 'rest';
    var dk = dateKey(slotDate(slot.id));
    var t = totals(day, prog);
    var kcal = calcCalories(day);
    var open = currentOpenSlotId === slot.id;
    var complete = t.total > 0 && t.done === t.total;

    stripHtml += '<button class="chip'+(open ? ' active' : '')+'" data-slot="'+slot.id+'">'+
      '<span class="cdot" style="background:'+CAT_VAR[day.cat]+'"></span>'+slot.label+(complete ? ' ✓' : '')+'</button>';

    var assignHtml = '<div class="assign-row">'+
      '<select class="assign-select" data-action="assign" aria-label="Workout type for '+esc(day.name)+'">'+
        TEMPLATE_ORDER.map(function(k){
          return '<option value="'+k+'"'+(k === day.templateKey ? ' selected' : '')+'>'+TEMPLATE_META[k].label+'</option>';
        }).join('')+
      '</select>'+
      '<input class="rename-input" data-action="rename" type="text" maxlength="22" value="'+esc(day.name)+'" aria-label="Name for this day">'+
    '</div>';

    var bodyHtml = isRest
      ? '<div class="rest-block">'+esc(day.note)+'</div>'
      : '<p class="day-note">'+esc(day.note)+'</p><div class="ex-list">'+
          day.exercises.map(function(ex){ return exHtml(ex, prog, dk); }).join('')+'</div>'+
          addRowHtml(slot, day);

    var progressHtml = t.total > 0
      ? '<div class="day-progress"><span>'+t.done+'/'+t.total+' done</span>'+
          '<div class="bar"><div class="bar-fill" style="width:'+Math.round(t.done/t.total*100)+'%"></div></div></div>'
      : '';

    var target = dateKey(logDateFor(slot.id));
    var le = workoutLog[target];
    var logged = !!le && le.cat === day.cat;
    var where = target === todayKey() ? 'today' : shortDate(target);
    var logLabel = logged ? 'Logged ' + where + ' ✓' : (isRest ? 'Log rest day to ' : 'Log workout to ') + where;
    var logHtml = '<div class="log-row"><button class="log-btn'+(logged ? ' logged' : '')+'" data-action="log">'+logLabel+'</button></div>';

    html += '<div class="day'+(isRest ? ' rest' : '')+(open ? ' open' : '')+'" id="card-'+slot.id+'" data-slot="'+slot.id+'">'+
      '<button class="day-head" data-action="toggle" aria-expanded="'+open+'">'+
        '<div class="day-num">'+pad2(di+1)+'</div>'+
        '<div class="day-titles">'+
          '<div class="day-name">'+esc(day.name)+' · '+slot.label+(slot.id === tSlot ? '<span class="today-tag">TODAY</span>' : '')+'</div>'+
          '<div class="day-date">'+shortDate(dk)+(t.total > 0 ? ' · '+t.done+'/'+t.total+' done' : '')+'</div>'+
          '<div class="day-focus">'+esc(day.focus)+(kcal > 0 ? ' · ~'+kcal+' kcal' : '')+'</div>'+
        '</div>'+chevronSvg+
      '</button>'+
      '<div class="day-body"><div class="day-inner">'+assignHtml+bodyHtml+'</div>'+progressHtml+logHtml+'</div>'+
    '</div>';
  });

  document.getElementById('weekStrip').innerHTML = stripHtml;
  document.getElementById('days').innerHTML = html;
  saveProgress();
  renderTargets();
}

function openDay(id, open){
  SLOTS.forEach(function(s){
    var on = open && s.id === id;
    var card = document.getElementById('card-'+s.id);
    var chip = document.querySelector('.chip[data-slot="'+s.id+'"]');
    if(card){
      card.classList.toggle('open', on);
      var head = card.querySelector('.day-head');
      if(head) head.setAttribute('aria-expanded', on ? 'true' : 'false');
    }
    if(chip) chip.classList.toggle('active', on);
  });
  currentOpenSlotId = open ? id : null;
}

function renderAll(){ renderQuick(); renderDays(); renderCalendar(); }

/* ---------- DAY EVENTS (delegated) ---------- */
var daysEl = document.getElementById('days');

daysEl.addEventListener('click', function(e){
  var el = e.target.closest('[data-action]');
  if(!el) return;
  var card = el.closest('.day');
  if(!card) return;
  var slot = SLOT_BY_ID[card.getAttribute('data-slot')];
  var act = el.getAttribute('data-action');
  var tk = getTemplateKey(slot.id);

  if(act === 'toggle'){
    openDay(slot.id, !card.classList.contains('open'));
    return;
  }
  if(act === 'set'){
    var arr = getProg(slot.id)[el.getAttribute('data-key')];
    var si = parseInt(el.getAttribute('data-set'), 10);
    var pos = arr.indexOf(si);
    if(pos !== -1) arr.splice(pos, 1); else arr.push(si);
    saveProgress(); syncAutoLog(slot); renderAll();
    return;
  }
  if(act === 'check'){
    var key = el.getAttribute('data-key');
    var ex = getEffectiveDay(slot).exercises.filter(function(x){ return x.key === key; })[0];
    var p = getProg(slot.id);
    var units = ex.cardio ? 1 : ex.sets;
    if(p[key].length >= units) p[key] = [];
    else { p[key] = []; for(var i=0; i<units; i++) p[key].push(i); }
    saveProgress(); syncAutoLog(slot); renderAll();
    return;
  }
  if(act === 'remove'){
    var rk = el.getAttribute('data-key');
    var list = ensureAddedList(slot.id, tk);
    for(var j=0; j<list.length; j++){ if(list[j].id === rk){ list.splice(j, 1); break; } }
    write(K.added, addedExercises);
    delete getProg(slot.id)[rk];
    saveProgress(); syncAutoLog(slot); renderAll();
    return;
  }
  if(act === 'add'){
    var row = el.closest('.add-exercise-row');
    var nameEl = row.querySelector('[data-role="add-name"]');
    var amtEl = row.querySelector('[data-role="add-amt"]');
    var unit = row.querySelector('[data-role="add-unit"]').value;
    var errEl = row.querySelector('[data-role="add-err"]');
    var showErr = function(msg){ errEl.textContent = msg; errEl.classList.add('show'); };
    var name = nameEl.value.trim();
    if(!name){ showErr('Type an exercise name first.'); return; }
    var amt = parseInt(amtEl.value, 10);
    if(isNaN(amt) || amt < 1){ showErr('Enter how many ' + (unit === 'min' ? 'minutes.' : 'sets.')); return; }
    var day = getEffectiveDay(slot);
    if(day.exercises.some(function(x){ return sameName(x.name, name); })){ showErr('That one is already on this day.'); return; }

    var item;
    if(unit === 'min'){
      amt = Math.min(amt, 300);
      item = {id:newAddedId(), name:name, cue:'Cardio. Calories estimated from the activity type', cardio: amt+' min', cardioMin: amt, met: guessMet(name)};
    } else {
      amt = Math.min(amt, 10);
      var known = findPool(name);
      item = known ? copy(known) : {name:name, cue:'Your own exercise', reps:'10–15', rest:'60 sec'};
      item.id = newAddedId();
      item.sets = amt;
    }
    rememberCustom(name);
    ensureAddedList(slot.id, tk).push(item);
    write(K.added, addedExercises);
    getProg(slot.id)[item.id] = [];
    saveProgress(); syncAutoLog(slot); renderAll();
    return;
  }
  if(act === 'log'){
    var d = getEffectiveDay(slot);
    var dk = dateKey(logDateFor(slot.id));
    if(workoutLog[dk] && workoutLog[dk].cat === d.cat) delete workoutLog[dk];
    else workoutLog[dk] = {cat: d.cat, src:'manual', slot: slot.id,
      min: strengthMinutes(d) + cardioMinutes(d), kcal: calcCalories(d)};
    saveLog(); renderAll();
    return;
  }
});

daysEl.addEventListener('change', function(e){
  var el = e.target;
  var act = el.getAttribute('data-action');
  if(!act) return;
  var card = el.closest('.day');
  if(!card) return;
  var slot = SLOT_BY_ID[card.getAttribute('data-slot')];
  var tk = getTemplateKey(slot.id);

  if(act === 'assign'){
    dayAssign[slot.id] = el.value;
    write(K.assign, dayAssign);
    renderAll();
    return;
  }
  if(act === 'rename'){
    var v = el.value.trim();
    if(v) dayNames[slot.id] = v; else delete dayNames[slot.id];
    write(K.names, dayNames);
    renderDays();
    return;
  }
  if(act === 'swap'){
    var key = el.getAttribute('data-key');
    if(el.value === 'typed') return;
    if(el.value === 'type-new'){
      var typed = window.prompt('What exercise do you want to do instead?');
      if(typed && typed.trim()){
        setTypedSwap(slot.id, tk, key, typed.trim());
        rememberCustom(typed.trim());
        getProg(slot.id)[key] = [];
      }
    } else {
      setTypedSwap(slot.id, tk, key, null);
      setChosenOptionIdx(slot.id, tk, key, parseInt(el.value, 10));
      getProg(slot.id)[key] = [];
    }
    saveProgress(); syncAutoLog(slot); renderAll();
    return;
  }
  if(act === 'weight'){
    var name = el.getAttribute('data-name');
    var dk = dateKey(slotDate(slot.id));
    var val = parseFloat(el.value);
    if(!lifts[name]) lifts[name] = {};
    if(isNaN(val) || val < 0) delete lifts[name][dk];
    else lifts[name][dk] = Math.round(val * 10) / 10;
    write(K.lifts, lifts);
    return;
  }
});

daysEl.addEventListener('input', function(e){
  if(e.target.getAttribute('data-role') === 'add-name'){
    var err = e.target.closest('.add-exercise-row').querySelector('[data-role="add-err"]');
    err.classList.remove('show');
  }
});

document.getElementById('weekStrip').addEventListener('click', function(e){
  var chip = e.target.closest('.chip');
  if(!chip) return;
  var id = chip.getAttribute('data-slot');
  openDay(id, true);
  document.getElementById('card-'+id).scrollIntoView({behavior:'smooth', block:'start'});
});

/* ---------- CALENDAR ---------- */
function renderCalendar(){
  var y = calCursor.getFullYear(), m = calCursor.getMonth();
  document.getElementById('calMonth').textContent = MONTH_NAMES[m] + ' ' + y;
  var grid = document.getElementById('calGrid');
  grid.innerHTML = '';
  ['S','M','T','W','T','F','S'].forEach(function(d){
    var el = document.createElement('div');
    el.className = 'cal-dow'; el.textContent = d; el.setAttribute('aria-hidden','true');
    grid.appendChild(el);
  });
  var startPad = new Date(y, m, 1).getDay();
  var daysInMonth = new Date(y, m+1, 0).getDate();
  var today = startOfToday(), tk = dateKey(today);
  for(var p=0; p<startPad; p++){
    var blank = document.createElement('div');
    blank.className = 'cal-cell blank';
    grid.appendChild(blank);
  }
  for(var d=1; d<=daysInMonth; d++){
    (function(dayNum){
      var cellDate = new Date(y, m, dayNum);
      var key = dateKey(cellDate);
      var entry = workoutLog[key];
      var cell = document.createElement('button');
      cell.className = 'cal-cell' + (entry ? ' logged' : '') + (key === tk ? ' today' : '') + (cellDate > today ? ' future' : '');
      cell.setAttribute('aria-label', MONTH_NAMES[m]+' '+dayNum+(entry ? ', '+CAT_LABEL[entry.cat]+(entry.kcal ? ', about '+entry.kcal+' calories' : '') : ', not logged'));
      cell.innerHTML = '<span>'+dayNum+'</span><span class="cal-dot" style="background:'+(entry ? CAT_VAR[entry.cat] : 'transparent')+'"></span>';
      cell.addEventListener('click', function(){
        var slot = SLOT_BY_ID[INDEX_WEEKDAY[cellDate.getDay()]];
        var sched = getEffectiveDay(slot);
        var cur = workoutLog[key];
        if(!cur) workoutLog[key] = {cat: sched.cat, src:'manual', kcal: calcCalories(sched), min: strengthMinutes(sched) + cardioMinutes(sched)};
        else if(cur.cat !== 'rest') workoutLog[key] = {cat:'rest', src:'manual'};
        else delete workoutLog[key];
        saveLog(); renderAll();
      });
      grid.appendChild(cell);
    })(d);
  }
  renderCalStats(y, m);
}

function renderCalStats(y, m){
  var today = new Date();
  var isCurrentMonth = (y === today.getFullYear() && m === today.getMonth());
  var daysInMonth = new Date(y, m+1, 0).getDate();
  var elapsed = isCurrentMonth ? today.getDate() : (new Date(y, m, 1) > today ? 0 : daysInMonth);
  var workouts = 0, rests = 0, kcal = 0, byCat = {leg:0, arm:0, cardio:0};
  for(var d=1; d<=daysInMonth; d++){
    var v = workoutLog[dateKey(new Date(y, m, d))];
    if(!v) continue;
    if(v.cat === 'rest') rests += 1;
    else { workouts += 1; if(byCat[v.cat] !== undefined) byCat[v.cat] += 1; }
    kcal += v.kcal || 0;
  }
  var pct = elapsed > 0 ? Math.round(((workouts + rests) / elapsed) * 100) : 0;
  var streak = 0;
  var cursor = startOfToday();
  if(!workoutLog[dateKey(cursor)]) cursor.setDate(cursor.getDate() - 1);
  while(workoutLog[dateKey(cursor)]){ streak += 1; cursor.setDate(cursor.getDate() - 1); }
  document.getElementById('calStats').innerHTML =
    stat(workouts, 'workouts') +
    stat(streak, 'day streak') +
    stat(pct + '%', isCurrentMonth ? 'of days so far' : 'of the month') +
    stat(byCat.leg + '·' + byCat.arm + '·' + byCat.cardio, 'leg · arm · cardio') +
    stat('~' + kcal.toLocaleString(), 'est. kcal burned');
}
function stat(num, label){
  return '<div class="cal-stat"><div class="cs-num">'+num+'</div><div class="cs-label">'+label+'</div></div>';
}

/* ---------- CONTROLS ---------- */
document.getElementById('themeBtn').addEventListener('click', function(){
  theme = theme === 'dark' ? 'light' : 'dark';
  write(K.theme, theme);
  applyTheme();
});

document.getElementById('targetToggle').addEventListener('click', function(){
  document.getElementById('targetEdit').classList.toggle('open');
});
['tLeg','tArm','tCardio'].forEach(function(id){
  document.getElementById(id).addEventListener('change', function(){
    var cat = id === 'tLeg' ? 'leg' : (id === 'tArm' ? 'arm' : 'cardio');
    targets[cat] = clampInt(document.getElementById(id).value, targets[cat]);
    write(K.targets, targets);
    renderTargets();
  });
});

QUICK_TYPES.forEach(function(q){
  var o = document.createElement('option');
  o.value = q.id; o.textContent = q.name;
  document.getElementById('quickType').appendChild(o);
});
document.querySelectorAll('.qbtn').forEach(function(b){
  b.addEventListener('click', function(){
    var cat = b.getAttribute('data-cat'), tk = todayKey(), cur = workoutLog[tk];
    if(cur && cur.cat === cat){ delete workoutLog[tk]; }
    else {
      var min = cat === 'rest' ? 0 : (parseInt(document.getElementById('quickMin').value, 10) || quickPrefs.min);
      var type = cat === 'cardio' ? document.getElementById('quickType').value : null;
      workoutLog[tk] = {cat: cat, src:'quick', min: min, type: type, kcal: quickKcal(cat, min, type)};
    }
    saveLog(); renderAll();
  });
});
document.getElementById('quickMin').addEventListener('change', updateQuickEntry);
document.getElementById('quickType').addEventListener('change', updateQuickEntry);

var resetConfirming = false, resetTimeout = null;
var resetBtn = document.getElementById('resetBtn');
resetBtn.addEventListener('click', function(){
  if(!resetConfirming){
    resetConfirming = true;
    resetBtn.textContent = 'Tap again to confirm';
    resetBtn.classList.add('confirming');
    resetTimeout = setTimeout(function(){
      resetConfirming = false;
      resetBtn.textContent = 'Reset this week';
      resetBtn.classList.remove('confirming');
    }, 3000);
  } else {
    clearTimeout(resetTimeout);
    resetConfirming = false;
    resetBtn.textContent = 'Reset this week';
    resetBtn.classList.remove('confirming');
    SLOTS.forEach(function(s){ delete progress[dateKey(slotDate(s.id))]; });
    saveProgress();
    renderAll();
  }
});

document.getElementById('weightInput').addEventListener('change', function(){
  var val = parseFloat(this.value);
  if(!isNaN(val) && val > 0){
    userWeightLbs = val;
    write(K.weight, userWeightLbs);
    renderAll();
  }
});

document.getElementById('exportBtn').addEventListener('click', function(){
  var data = {app:'tone-shape', version:2, exported: new Date().toISOString(), keys:{}};
  for(var i=0; i<localStorage.length; i++){
    var k = localStorage.key(i);
    if(k && k.indexOf('toneshape.') === 0) data.keys[k] = localStorage.getItem(k);
  }
  var blob = new Blob([JSON.stringify(data, null, 2)], {type:'application/json'});
  var url = URL.createObjectURL(blob);
  var a = document.createElement('a');
  a.href = url;
  a.download = 'tone-shape-backup-' + todayKey() + '.json';
  document.body.appendChild(a);
  a.click();
  a.remove();
  setTimeout(function(){ URL.revokeObjectURL(url); }, 2000);
});
document.getElementById('importBtn').addEventListener('click', function(){
  document.getElementById('importFile').click();
});
document.getElementById('importFile').addEventListener('change', function(){
  var file = this.files && this.files[0];
  if(!file) return;
  var reader = new FileReader();
  reader.onload = function(){
    try{
      var data = JSON.parse(reader.result);
      if(!data || data.app !== 'tone-shape' || !data.keys) throw new Error('bad file');
      if(!window.confirm('Replace everything on this device with the backup from ' + (data.exported || 'this file').slice(0,10) + '?')) return;
      var toRemove = [];
      for(var i=0; i<localStorage.length; i++){
        var k = localStorage.key(i);
        if(k && k.indexOf('toneshape.') === 0) toRemove.push(k);
      }
      toRemove.forEach(function(k){ localStorage.removeItem(k); });
      Object.keys(data.keys).forEach(function(k){
        if(k.indexOf('toneshape.') === 0) localStorage.setItem(k, data.keys[k]);
      });
      location.reload();
    }catch(e){
      window.alert('That file doesn\u2019t look like a Tone & Shape backup.');
    }
  };
  reader.readAsText(file);
  this.value = '';
});

document.getElementById('calPrev').addEventListener('click', function(){
  calCursor = new Date(calCursor.getFullYear(), calCursor.getMonth()-1, 1); renderCalendar();
});
document.getElementById('calNext').addEventListener('click', function(){
  calCursor = new Date(calCursor.getFullYear(), calCursor.getMonth()+1, 1); renderCalendar();
});
document.getElementById('calToday').addEventListener('click', function(){
  calCursor = new Date(); renderCalendar();
});

/* ---------- START ---------- */
loadAll();
document.getElementById('weightInput').value = userWeightLbs;
renderAll();
</script>
</body>
</html>
   renderAll();
   </script>
   </body>
   </html>

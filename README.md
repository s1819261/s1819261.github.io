# s1819261.github.io
workout
[index.html](https://github.com/user-attachments/files/31340677/index.html)
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
  --page:#0D1117;
  --surface:#161C26;
  --surface-2:#1F2733;
  --line:rgba(255,255,255,0.09);
  --line-soft:rgba(255,255,255,0.05);
  --text:#EDF2F7;
  --text-dim:#8FA3BC;
  --muted:#5A6B82;
  --accent:#4D8DFF;
  --accent-2:#7FB0FF;
  --accent-soft:rgba(77,141,255,0.15);
  --on-accent:#04182F;
  --danger:#FF6B4A;
  --cat-leg:#4D8DFF;
  --cat-arm:#22D3EE;
  --cat-cardio:#A78BFA;
  --cat-rest:#5A6B82;
  --glow:radial-gradient(circle at 12% 0%, rgba(77,141,255,0.10), transparent 55%);
}
:root[data-theme="light"]{
  --page:#FAF9FF;
  --surface:#FFFFFF;
  --surface-2:#F3EEFE;
  --line:rgba(26,21,38,0.11);
  --line-soft:rgba(26,21,38,0.06);
  --text:#1A1526;
  --text-dim:#5B5470;
  --muted:#8B84A3;
  --accent:#6D28D9;
  --accent-2:#8B5CF6;
  --accent-soft:#F1EBFE;
  --on-accent:#FFFFFF;
  --danger:#D6401F;
  --cat-leg:#6D28D9;
  --cat-arm:#C026D3;
  --cat-cardio:#0E7490;
  --cat-rest:#8B84A3;
  --glow:radial-gradient(circle at 12% 0%, rgba(109,40,217,0.09), transparent 55%);
}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent;}
html,body{margin:0;padding:0;}
body{
  background:var(--page);
  color:var(--text);
  font-family:'Inter',system-ui,sans-serif;
  min-height:100vh;
  padding-bottom:60px;
  transition:background .2s ease,color .2s ease;
}
.wrap{max-width:560px;margin:0 auto;padding:0 16px;}
button,select,input{font-family:inherit;}
:focus-visible{outline:2px solid var(--accent);outline-offset:2px;}

/* HERO */
.hero{
  padding:26px 16px 18px;
  background:var(--glow),var(--page);
  border-bottom:1px solid var(--line);
}
.hero-top{display:flex;align-items:flex-start;justify-content:space-between;gap:12px;}
.eyebrow{
  font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.18em;
  text-transform:uppercase;color:var(--accent);margin-bottom:10px;
}
h1{
  font-family:'Anton',sans-serif;font-weight:400;font-size:40px;line-height:.92;
  letter-spacing:.01em;margin:0 0 10px;text-transform:uppercase;
}
h1 span{color:var(--accent);}
.hero-sub{color:var(--text-dim);font-size:14px;line-height:1.5;max-width:46ch;margin:0;}
.icon-btn{
  flex:0 0 auto;width:40px;height:40px;border-radius:12px;
  border:1px solid var(--line);background:var(--surface);color:var(--text-dim);
  font-size:17px;cursor:pointer;display:flex;align-items:center;justify-content:center;
}
.icon-btn:hover{color:var(--accent);border-color:var(--accent);}

/* SETTINGS ROW */
.settings{
  display:flex;flex-wrap:wrap;gap:10px;align-items:center;margin-top:16px;
}
.mini-label{
  font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.04em;
  color:var(--text-dim);text-transform:uppercase;
}
.num-input{
  width:62px;font-family:'DM Mono',monospace;font-size:13px;color:var(--text);
  background:var(--surface);border:1px solid var(--line);border-radius:8px;padding:7px 8px;
}
.ghost-btn{
  font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.04em;
  color:var(--text-dim);background:var(--surface);border:1px solid var(--line);
  padding:8px 12px;border-radius:8px;cursor:pointer;text-transform:uppercase;
}
.ghost-btn:hover{color:var(--accent);border-color:var(--accent);}
.ghost-btn.confirming{color:var(--danger)!important;border-color:var(--danger)!important;}

/* TARGET BANNER */
.target-card{
  margin-top:18px;border:1px solid var(--line);border-radius:14px;
  background:var(--surface);overflow:hidden;
}
.target-head{
  display:flex;align-items:center;justify-content:space-between;gap:10px;
  padding:14px 16px 10px;
}
.target-title{font-weight:800;font-size:15px;}
.target-status{
  font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.05em;text-transform:uppercase;
}
.target-status.ok{color:var(--accent);}
.target-status.off{color:var(--danger);}
.target-grid{display:flex;gap:8px;padding:0 16px 14px;flex-wrap:wrap;}
.target-pill{
  flex:1 1 90px;background:var(--surface-2);border-radius:10px;padding:10px 12px;
  border-left:3px solid var(--muted);
}
.target-pill .tp-name{
  font-family:'DM Mono',monospace;font-size:10.5px;letter-spacing:.08em;
  text-transform:uppercase;color:var(--text-dim);margin-bottom:4px;
}
.target-pill .tp-count{font-family:'Anton',sans-serif;font-size:20px;line-height:1;}
.target-pill .tp-need{font-size:11px;color:var(--text-dim);margin-top:4px;}
.target-edit{
  padding:0 16px 14px;display:none;gap:10px;flex-wrap:wrap;align-items:center;
  border-top:1px solid var(--line-soft);padding-top:12px;margin-top:2px;
}
.target-edit.open{display:flex;}
.target-edit .field{display:flex;align-items:center;gap:6px;}

/* WEEK STRIP */
.week-strip{
  position:sticky;top:0;z-index:20;display:flex;gap:6px;overflow-x:auto;
  padding:10px 16px;background:var(--page);
  border-bottom:1px solid var(--line);scrollbar-width:none;
}
.week-strip::-webkit-scrollbar{display:none;}
.chip{
  flex:0 0 auto;font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.05em;
  padding:8px 12px;border-radius:999px;border:1px solid var(--line);
  color:var(--text-dim);background:var(--surface);white-space:nowrap;cursor:pointer;
  display:flex;align-items:center;gap:6px;
}
.chip .cdot{width:7px;height:7px;border-radius:50%;background:var(--muted);}
.chip.active{color:var(--on-accent);background:var(--accent);border-color:var(--accent);font-weight:700;}
.chip.active .cdot{background:var(--on-accent);}

/* DAY CARD */
.day{
  margin-top:18px;border:1px solid var(--line);border-radius:14px;overflow:hidden;
  background:var(--surface);scroll-margin-top:64px;
}
.day-head{
  width:100%;display:flex;align-items:center;gap:12px;padding:16px;background:none;
  border:none;color:var(--text);text-align:left;cursor:pointer;
}
.day-num{font-family:'Anton',sans-serif;font-size:22px;color:var(--muted);width:34px;flex-shrink:0;}
.day.rest .day-num{color:var(--line);}
.day-titles{flex:1;min-width:0;}
.day-name{font-weight:800;font-size:15px;letter-spacing:.01em;}
.day-focus{
  font-family:'DM Mono',monospace;font-size:11.5px;color:var(--accent);margin-top:2px;
  text-transform:uppercase;letter-spacing:.04em;
}
.day.rest .day-focus{color:var(--text-dim);}
.chevron{width:20px;height:20px;flex-shrink:0;color:var(--text-dim);transition:transform .25s ease;}
.day.open .chevron{transform:rotate(180deg);}
.day-body{max-height:0;overflow:hidden;transition:max-height .3s ease;}
.day.open .day-body{max-height:6000px;}
.day-inner{padding:0 16px 18px;}
.day-note{
  font-size:12.5px;color:var(--text-dim);line-height:1.5;margin:0 0 14px;
  padding:10px 12px;background:var(--surface-2);border-left:2px solid var(--accent);
}
.assign-row{display:flex;gap:8px;flex-wrap:wrap;margin:0 0 12px;align-items:center;}
.assign-select,.rename-input{
  font-family:'DM Mono',monospace;font-size:12px;color:var(--text);
  background:var(--surface-2);border:1px solid var(--line);border-radius:8px;padding:9px 10px;
}
.assign-select{flex:1 1 170px;min-width:0;}
.rename-input{flex:1 1 120px;min-width:0;}

/* EXERCISE ROW */
.ex{display:flex;gap:12px;padding:12px 0;border-top:1px solid var(--line-soft);}
.ex:first-of-type{border-top:none;}
.ex-check{
  width:24px;height:24px;border-radius:7px;border:1.5px solid var(--muted);flex-shrink:0;
  margin-top:2px;display:flex;align-items:center;justify-content:center;cursor:pointer;
  transition:all .15s ease;background:transparent;padding:0;
}
.ex-check.done{background:var(--accent);border-color:var(--accent);}
.ex-check svg{width:15px;height:15px;opacity:0;color:var(--on-accent);}
.ex-check.done svg{opacity:1;}
.ex-main{flex:1;min-width:0;}
.ex-name{font-weight:700;font-size:14.5px;margin-bottom:3px;}
.ex.done .ex-name{color:var(--text-dim);text-decoration:line-through;text-decoration-color:var(--muted);}
.ex-cue{font-size:12px;color:var(--text-dim);line-height:1.4;}
.ex-swap{
  margin-top:6px;font-family:'DM Mono',monospace;font-size:11px;color:var(--text);
  background:var(--surface-2);border:1px solid var(--line);border-radius:6px;
  padding:5px 8px;max-width:100%;cursor:pointer;
}
.ex-stats{display:flex;gap:6px;margin-top:7px;flex-wrap:wrap;}
.stat{
  font-family:'DM Mono',monospace;font-size:11px;padding:3px 8px;border-radius:6px;
  background:var(--surface-2);color:var(--text);border:1px solid var(--line-soft);
}
.stat.sets{color:var(--accent);border-color:var(--accent-soft);}
.set-boxes{display:flex;gap:6px;margin-top:9px;flex-wrap:wrap;}
.set-box{
  width:30px;height:30px;border-radius:8px;border:1.5px solid var(--muted);
  background:var(--surface-2);display:flex;align-items:center;justify-content:center;
  font-family:'DM Mono',monospace;font-size:11px;color:var(--text-dim);cursor:pointer;
  transition:all .15s ease;flex-shrink:0;padding:0;
}
.set-box.done{background:var(--accent);border-color:var(--accent);color:var(--on-accent);font-weight:700;}
.set-box:active{transform:scale(.92);}
.ex-remove{
  width:22px;height:22px;border-radius:6px;border:1px solid var(--line);
  background:var(--surface-2);color:var(--text-dim);display:flex;align-items:center;
  justify-content:center;cursor:pointer;flex-shrink:0;font-size:13px;line-height:1;margin-top:2px;padding:0;
}
.ex-remove:hover{color:var(--danger);border-color:var(--danger);}
.added-tag{color:var(--accent);font-size:10px;font-family:'DM Mono',monospace;}
.add-exercise-row{display:flex;gap:8px;margin-top:14px;flex-wrap:wrap;align-items:center;}
.add-select{
  flex:1;min-width:160px;font-family:'DM Mono',monospace;font-size:12px;color:var(--text);
  background:var(--surface-2);border:1px solid var(--line);border-radius:8px;padding:9px 10px;
}
.add-btn{
  font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.04em;color:var(--on-accent);
  background:var(--accent);border:1px solid var(--accent);border-radius:8px;padding:9px 14px;
  font-weight:700;cursor:pointer;white-space:nowrap;
}
.cardio-block{
  padding:14px;background:var(--surface-2);border-radius:10px;font-size:13.5px;
  line-height:1.6;color:var(--text-dim);
}
.cardio-block b{color:var(--text);}
.rest-block{
  padding:18px 14px;background:var(--surface-2);border-radius:10px;font-size:13.5px;
  line-height:1.6;color:var(--text-dim);text-align:center;
}
.day-progress{
  display:flex;align-items:center;gap:8px;padding:10px 16px 14px;
  font-family:'DM Mono',monospace;font-size:11px;color:var(--text-dim);
}
.bar{flex:1;height:4px;background:var(--surface-2);border-radius:2px;overflow:hidden;}
.bar-fill{height:100%;background:var(--accent);width:0%;transition:width .3s ease;}
.log-row{display:flex;gap:8px;padding:0 16px 16px;flex-wrap:wrap;}
.log-btn{
  font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.04em;text-transform:uppercase;
  color:var(--accent);background:var(--accent-soft);border:1px solid var(--accent);
  border-radius:8px;padding:9px 14px;cursor:pointer;font-weight:700;
}
.log-btn.logged{background:var(--accent);color:var(--on-accent);}

/* CALENDAR */
.cal-section{margin-top:30px;border:1px solid var(--line);border-radius:14px;background:var(--surface);overflow:hidden;}
.cal-head{display:flex;align-items:center;justify-content:space-between;padding:16px;gap:10px;}
.cal-month{font-family:'Anton',sans-serif;font-size:22px;text-transform:uppercase;letter-spacing:.02em;}
.cal-nav{display:flex;gap:6px;}
.cal-nav button{
  width:32px;height:32px;border-radius:8px;border:1px solid var(--line);background:var(--surface-2);
  color:var(--text-dim);cursor:pointer;font-size:14px;line-height:1;display:flex;align-items:center;justify-content:center;
}
.cal-nav button:hover{color:var(--accent);border-color:var(--accent);}
.cal-stats{display:flex;gap:8px;padding:0 16px 14px;flex-wrap:wrap;}
.cal-stat{flex:1 1 90px;background:var(--surface-2);border-radius:10px;padding:10px 12px;}
.cal-stat .cs-num{font-family:'Anton',sans-serif;font-size:22px;line-height:1;color:var(--accent);}
.cal-stat .cs-label{
  font-family:'DM Mono',monospace;font-size:10px;letter-spacing:.07em;text-transform:uppercase;
  color:var(--text-dim);margin-top:5px;
}
.cal-grid{display:grid;grid-template-columns:repeat(7,1fr);gap:5px;padding:0 16px 8px;}
.cal-dow{
  font-family:'DM Mono',monospace;font-size:10px;letter-spacing:.06em;text-transform:uppercase;
  color:var(--muted);text-align:center;padding-bottom:4px;
}
.cal-cell{
  aspect-ratio:1;border-radius:9px;background:var(--surface-2);border:1px solid transparent;
  display:flex;flex-direction:column;align-items:center;justify-content:center;gap:3px;
  font-family:'DM Mono',monospace;font-size:11.5px;color:var(--text-dim);cursor:pointer;padding:0;
}
.cal-cell.blank{background:transparent;cursor:default;}
.cal-cell.today{border-color:var(--accent);}
.cal-cell.future{opacity:.4;}
.cal-cell .cal-dot{width:7px;height:7px;border-radius:50%;background:transparent;}
.cal-cell.logged{color:var(--text);}
.cal-legend{
  display:flex;gap:12px;flex-wrap:wrap;padding:10px 16px 16px;
  font-family:'DM Mono',monospace;font-size:10.5px;letter-spacing:.05em;
  text-transform:uppercase;color:var(--text-dim);
}
.cal-legend span{display:flex;align-items:center;gap:5px;}
.cal-legend i{width:8px;height:8px;border-radius:50%;display:block;}
.cal-hint{
  padding:0 16px 16px;font-size:12px;color:var(--text-dim);line-height:1.5;margin:0;
}
footer{
  margin-top:26px;padding:18px 16px 30px;text-align:center;font-family:'DM Mono',monospace;
  font-size:11px;color:var(--text-dim);letter-spacing:.03em;
}
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
    <p class="hero-sub">Set each day to whatever you want — legs, arms, cardio, or rest. Tap a set to check it off. Everything saves to this device automatically.</p>

    <div class="settings">
      <label class="mini-label" for="weightInput">Weight (lbs)</label>
      <input id="weightInput" class="num-input" type="number" min="70" max="400" value="150" aria-label="Your weight in pounds">
      <button class="ghost-btn" id="targetToggle">Edit targets</button>
      <button class="ghost-btn" id="resetBtn">Reset checkmarks</button>
    </div>
  </div>
</div>

<div class="wrap">
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
    <p class="cal-hint">Tap any date to cycle it: scheduled workout → rest → clear. Finishing all of a day's sets logs it here on its own.</p>
  </div>
</div>

<footer>SAVED ON THIS DEVICE · NO ACCOUNT NEEDED</footer>

<script>
var TEMPLATES = {
  'leg-standard': {
    focus: 'Glutes & legs — tone',
    estMinutes: {strength: 60, cardio: 0},
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
    estMinutes: {strength: 60, cardio: 0},
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
    estMinutes: {strength: 50, cardio: 0},
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
    estMinutes: {strength: 50, cardio: 0},
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
    focus: 'Cardio + core finisher — A',
    estMinutes: {strength: 15, cardio: 32},
    note: '⏱ ~45–50 min. One uninterrupted cardio block is the main event — pick a machine and stay on it. Core work is a short finisher.',
    exercises: [
      { options: [
        {name:'Treadmill (incline walk)', cue:'Steady pace or self-paced intervals, incline for extra work', cardio:'30–35 min'},
        {name:'Stairmaster', cue:'Steady pace or self-paced intervals', cardio:'30–35 min'},
        {name:'Elliptical', cue:'Steady pace or self-paced intervals', cardio:'30–35 min'}
      ]},
      { options: [
        {name:'Seated Ab Crunch Machine', cue:'Controlled squeeze, no momentum', sets:3, reps:'15', rest:'30 sec'},
        {name:'Kneeling Cable Crunches', cue:'Round the spine, pull elbows toward knees', sets:3, reps:'15', rest:'30 sec'},
        {name:'Decline Sit-Ups', cue:'Controlled tempo, avoid yanking the neck', sets:3, reps:'15', rest:'30 sec'}
      ]},
      { options: [
        {name:'Ab Coaster / Torso Rotation Machine', cue:'Rotate through the core, not the arms', sets:3, reps:'15', rest:'30 sec'},
        {name:'Standing Cable Rotation', cue:'Rotate from the core, keep hips mostly square', sets:3, reps:'12 / side', rest:'30 sec'},
        {name:'Russian Twists (dumbbell)', cue:'Feet up or down, rotate side to side with control', sets:3, reps:'12 / side', rest:'30 sec'}
      ]},
      { options: [
        {name:'Cable Woodchoppers', cue:'High-to-low cable, rotate from the core', sets:2, reps:'12 / side', rest:'30 sec'},
        {name:'Cable Rotational Chop (low-to-high)', cue:'Low-to-high cable, drive through the core', sets:2, reps:'12 / side', rest:'30 sec'},
        {name:'Side Plank', cue:'Stack hips, hold steady', sets:2, reps:'20–30 sec / side', rest:'30 sec'}
      ]}
    ]
  },
  'cardio-b': {
    focus: 'Cardio + core finisher — B',
    estMinutes: {strength: 15, cardio: 32},
    note: '⏱ ~45–50 min. Same format — one continuous cardio block, different core work at the end for variety.',
    exercises: [
      { options: [
        {name:'Treadmill (incline walk)', cue:'Steady pace or self-paced intervals, incline for extra work', cardio:'30–35 min'},
        {name:'Stairmaster', cue:'Steady pace or self-paced intervals', cardio:'30–35 min'},
        {name:'Elliptical', cue:'Steady pace or self-paced intervals', cardio:'30–35 min'}
      ]},
      { options: [
        {name:'Kneeling Cable Crunches', cue:'Round the spine, pull elbows toward knees', sets:3, reps:'15', rest:'30 sec'},
        {name:'Seated Ab Crunch Machine', cue:'Controlled squeeze, no momentum', sets:3, reps:'15', rest:'30 sec'},
        {name:'Hanging Knee Raises (captain\u2019s chair)', cue:'No swinging, controlled tempo', sets:3, reps:'12–15', rest:'30 sec'}
      ]},
      { options: [
        {name:'Cable Side Bends', cue:'Slow and controlled, feel it in the obliques', sets:2, reps:'12 / side', rest:'30 sec'},
        {name:'Dumbbell Side Bends', cue:'Slow and controlled, feel it in the obliques', sets:2, reps:'12 / side', rest:'30 sec'},
        {name:'Standing Oblique Cable Crunch', cue:'Crunch sideways, pull elbow toward hip', sets:2, reps:'12 / side', rest:'30 sec'}
      ]},
      { options: [
        {name:'Plank', cue:'Straight line head to heels, brace the core', sets:3, reps:'30–45 sec', rest:'30 sec'},
        {name:'Ab Coaster / Torso Rotation Machine', cue:'Rotate through the core, not the arms', sets:3, reps:'15', rest:'30 sec'},
        {name:'Decline Sit-Ups', cue:'Controlled tempo, avoid yanking the neck', sets:3, reps:'15', rest:'30 sec'}
      ]}
    ]
  },
  'rest': {
    focus: 'Rest',
    estMinutes: {strength: 0, cardio: 0},
    note: 'Full rest. Recovery is when the shape you\u2019re training for actually gets built.',
    exercises: []
  }
};

var TEMPLATE_META = {
  'leg-standard': {cat:'leg',   label:'Leg — standard'},
  'leg-knee':     {cat:'leg',   label:'Leg — knee-friendly'},
  'arm-a':        {cat:'arm',   label:'Arm — set A'},
  'arm-b':        {cat:'arm',   label:'Arm — set B'},
  'cardio-a':     {cat:'cardio',label:'Cardio — set A'},
  'cardio-b':     {cat:'cardio',label:'Cardio — set B'},
  'rest':         {cat:'rest',  label:'Rest day'}
};
var TEMPLATE_ORDER = ['leg-standard','leg-knee','arm-a','arm-b','cardio-a','cardio-b','rest'];
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
    {name:'Seated Leg Curl Machine', cue:'Light-controlled tempo, supports the hamstring-glute tie-in', sets:3, reps:'12–15', rest:'60 sec'},
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
    {name:'Seated Ab Crunch Machine', cue:'Controlled squeeze, no momentum', sets:3, reps:'15', rest:'30 sec'},
    {name:'Kneeling Cable Crunches', cue:'Round the spine, pull elbows toward knees', sets:3, reps:'15', rest:'30 sec'},
    {name:'Decline Sit-Ups', cue:'Controlled tempo, avoid yanking the neck', sets:3, reps:'15', rest:'30 sec'},
    {name:'Ab Coaster / Torso Rotation Machine', cue:'Rotate through the core, not the arms', sets:3, reps:'15', rest:'30 sec'},
    {name:'Standing Cable Rotation', cue:'Rotate from the core, keep hips mostly square', sets:3, reps:'12 / side', rest:'30 sec'},
    {name:'Russian Twists (dumbbell)', cue:'Feet up or down, rotate side to side with control', sets:3, reps:'12 / side', rest:'30 sec'},
    {name:'Cable Woodchoppers', cue:'High-to-low cable, rotate from the core', sets:2, reps:'12 / side', rest:'30 sec'},
    {name:'Side Plank', cue:'Stack hips, hold steady', sets:2, reps:'20–30 sec / side', rest:'30 sec'},
    {name:'Plank', cue:'Straight line head to heels, brace the core', sets:2, reps:'30–45 sec', rest:'30 sec'},
    {name:'Bicycle Crunches', cue:'Slow and controlled, elbow to opposite knee', sets:3, reps:'15 / side', rest:'30 sec'},
    {name:'Cable Side Bends', cue:'Slow and controlled, feel it in the obliques', sets:2, reps:'12 / side', rest:'30 sec'},
    {name:'Hanging Knee Raises (captain\u2019s chair)', cue:'No swinging, controlled tempo', sets:3, reps:'12–15', rest:'30 sec'}
  ]
};

var SLOTS = [
  {id:'mon', label:'MON', defaultName:'Monday',    defaultTemplate:'leg-standard'},
  {id:'tue', label:'TUE', defaultName:'Tuesday',   defaultTemplate:'arm-a'},
  {id:'wed', label:'WED', defaultName:'Wednesday', defaultTemplate:'cardio-a'},
  {id:'thu', label:'THU', defaultName:'Thursday',  defaultTemplate:'leg-knee'},
  {id:'fri', label:'FRI', defaultName:'Friday',    defaultTemplate:'arm-b'},
  {id:'sat', label:'SAT', defaultName:'Saturday',  defaultTemplate:'cardio-b'},
  {id:'sun', label:'SUN', defaultName:'Sunday',    defaultTemplate:'rest'}
];
var WEEKDAY_INDEX = {sun:0, mon:1, tue:2, wed:3, thu:4, fri:5, sat:6};
var INDEX_WEEKDAY = ['sun','mon','tue','wed','thu','fri','sat'];

var checkSvg = '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>';

var NS = 'toneshape.v1.';
var K = {
  progress: NS+'progress', assign: NS+'assign', names: NS+'names',
  choices: NS+'choices', added: NS+'added', targets: NS+'targets',
  weight: NS+'weight', theme: NS+'theme', log: NS+'log'
};

function read(key, fallback){
  try{
    var raw = localStorage.getItem(key);
    if(raw === null) return fallback;
    return JSON.parse(raw);
  }catch(e){ return fallback; }
}
function write(key, value){
  try{ localStorage.setItem(key, JSON.stringify(value)); }
  catch(e){ console.error('Could not save', key, e); }
}

var state = {};
var dayAssign = {};
var dayNames = {};
var exerciseChoice = {};
var addedExercises = {};
var targets = {leg:2, arm:2, cardio:2};
var workoutLog = {};
var userWeightLbs = 150;
var theme = 'dark';
var addedIdCounter = 0;
var currentOpenSlotId = null;
var calCursor = new Date();

var MET_STRENGTH = 5.0;
var MET_CARDIO = 7.0;

function dateKey(d){
  var m = d.getMonth()+1, day = d.getDate();
  return d.getFullYear()+'-'+(m<10?'0':'')+m+'-'+(day<10?'0':'')+day;
}
function todayKey(){ return dateKey(new Date()); }

function getTemplateKey(slotId){
  var k = dayAssign[slotId];
  return TEMPLATES[k] ? k : 'rest';
}
function getDayName(slot){
  return dayNames[slot.id] || slot.defaultName;
}
function getCategory(templateKey){
  return TEMPLATE_META[templateKey] ? TEMPLATE_META[templateKey].cat : 'rest';
}
function getChosenOptionIdx(slotId, templateKey, exIdx){
  return (exerciseChoice[slotId] && exerciseChoice[slotId][templateKey] && exerciseChoice[slotId][templateKey][exIdx]) || 0;
}
function setChosenOptionIdx(slotId, templateKey, exIdx, optIdx){
  if(!exerciseChoice[slotId]) exerciseChoice[slotId] = {};
  if(!exerciseChoice[slotId][templateKey]) exerciseChoice[slotId][templateKey] = {};
  exerciseChoice[slotId][templateKey][exIdx] = optIdx;
  write(K.choices, exerciseChoice);
}
function ensureAddedList(slotId, templateKey){
  if(!addedExercises[slotId]) addedExercises[slotId] = {};
  if(!addedExercises[slotId][templateKey]) addedExercises[slotId][templateKey] = [];
  return addedExercises[slotId][templateKey];
}
function newAddedId(){
  addedIdCounter += 1;
  return 'add'+Date.now()+'-'+addedIdCounter;
}

function getResolvedEntries(slotId, templateKey){
  var tmpl = TEMPLATES[templateKey];
  var base = tmpl.exercises.map(function(exSlot, ei){
    var idx = getChosenOptionIdx(slotId, templateKey, ei);
    var variant = exSlot.options[idx] || exSlot.options[0];
    var out = {key:String(ei), swapOptions:exSlot.options, isAdded:false};
    for(var p in variant){ if(Object.prototype.hasOwnProperty.call(variant,p)) out[p] = variant[p]; }
    return out;
  });
  var added = ensureAddedList(slotId, templateKey).map(function(item){
    var out = {key:item.id, swapOptions:null, isAdded:true};
    for(var p in item){ if(Object.prototype.hasOwnProperty.call(item,p)) out[p] = item[p]; }
    return out;
  });
  return base.concat(added);
}

function getEffectiveDay(slot){
  var key = getTemplateKey(slot.id);
  var tmpl = TEMPLATES[key];
  return {
    id: slot.id, label: slot.label, name: getDayName(slot),
    templateKey: key, cat: getCategory(key),
    focus: tmpl.focus, note: tmpl.note, estMinutes: tmpl.estMinutes,
    exercises: getResolvedEntries(slot.id, key)
  };
}

function calcCalories(day, weightLbs){
  if(!day.estMinutes) return 0;
  var weightKg = weightLbs * 0.453592;
  var addedStrength = day.exercises.filter(function(e){ return e.isAdded && !e.cardio; }).length;
  var strengthKcal = MET_STRENGTH * weightKg * ((day.estMinutes.strength + addedStrength*5)/60);
  var cardioKcal = MET_CARDIO * weightKg * (day.estMinutes.cardio/60);
  return Math.round(strengthKcal + cardioKcal);
}

function emptyDayState(entries){
  var obj = {};
  entries.forEach(function(e){ if(!e.cardio) obj[e.key] = []; });
  return obj;
}
function ensureSlotTemplateState(slotId){
  var key = getTemplateKey(slotId);
  if(!state[slotId]) state[slotId] = {};
  var entries = getResolvedEntries(slotId, key);
  if(!state[slotId][key]) state[slotId][key] = emptyDayState(entries);
  entries.forEach(function(e){
    if(!e.cardio && !Array.isArray(state[slotId][key][e.key])) state[slotId][key][e.key] = [];
  });
  return state[slotId][key];
}
function saveState(){ write(K.progress, state); }

function loadAll(){
  var savedTheme = read(K.theme, null);
  if(savedTheme === 'light' || savedTheme === 'dark'){
    theme = savedTheme;
  } else if(window.matchMedia && window.matchMedia('(prefers-color-scheme: light)').matches){
    theme = 'light';
  }
  applyTheme();

  var a = read(K.assign, {});
  SLOTS.forEach(function(s){
    dayAssign[s.id] = (a && TEMPLATES[a[s.id]]) ? a[s.id] : s.defaultTemplate;
  });
  dayNames = read(K.names, {}) || {};
  exerciseChoice = read(K.choices, {}) || {};
  addedExercises = read(K.added, {}) || {};
  var t = read(K.targets, null);
  if(t && typeof t === 'object'){
    targets.leg = clampInt(t.leg, 2);
    targets.arm = clampInt(t.arm, 2);
    targets.cardio = clampInt(t.cardio, 2);
  }
  workoutLog = read(K.log, {}) || {};
  var w = read(K.weight, null);
  if(typeof w === 'number' && w > 0) userWeightLbs = w;
  state = read(K.progress, {}) || {};
  SLOTS.forEach(function(s){ ensureSlotTemplateState(s.id); });
}
function clampInt(v, fallback){
  var n = parseInt(v, 10);
  if(isNaN(n) || n < 0) return fallback;
  return Math.min(n, 7);
}

function applyTheme(){
  document.documentElement.setAttribute('data-theme', theme);
  var meta = document.querySelector('meta[name="theme-color"]');
  if(meta) meta.setAttribute('content', theme === 'dark' ? '#0D1117' : '#FAF9FF');
  var btn = document.getElementById('themeBtn');
  if(btn) btn.textContent = theme === 'dark' ? '☀' : '☾';
}

/* ---------- TARGETS ---------- */
function countScheduled(){
  var counts = {leg:0, arm:0, cardio:0, rest:0};
  SLOTS.forEach(function(s){ counts[getCategory(getTemplateKey(s.id))] += 1; });
  return counts;
}
function renderTargets(){
  var counts = countScheduled();
  var grid = document.getElementById('targetGrid');
  var cats = ['leg','arm','cardio'];
  var allMet = true;
  grid.innerHTML = '';
  cats.forEach(function(cat){
    var have = counts[cat], want = targets[cat];
    if(have < want) allMet = false;
    var need = '';
    if(have < want) need = 'add ' + (want-have) + ' more';
    else if(have > want) need = (have-want) + ' over target';
    else need = 'on target';
    var el = document.createElement('div');
    el.className = 'target-pill';
    el.style.borderLeftColor = CAT_VAR[cat];
    el.innerHTML =
      '<div class="tp-name">'+CAT_LABEL[cat]+' days</div>'+
      '<div class="tp-count" style="color:'+CAT_VAR[cat]+'">'+have+' / '+want+'</div>'+
      '<div class="tp-need">'+need+'</div>';
    grid.appendChild(el);
  });
  var status = document.getElementById('targetStatus');
  if(allMet){
    status.className = 'target-status ok';
    status.textContent = 'On track';
  } else {
    status.className = 'target-status off';
    status.textContent = 'Needs adjusting';
  }
  document.getElementById('tLeg').value = targets.leg;
  document.getElementById('tArm').value = targets.arm;
  document.getElementById('tCardio').value = targets.cardio;
  var restDays = counts.rest;
  document.getElementById('heroEyebrow').textContent =
    (7 - restDays) + ' training days · ' + restDays + ' rest';
}

/* ---------- WEEK ---------- */
function render(){
  var strip = document.getElementById('weekStrip');
  var daysEl = document.getElementById('days');
  strip.innerHTML = '';
  daysEl.innerHTML = '';

  SLOTS.forEach(function(slot, di){
    var day = getEffectiveDay(slot);
    var daySets = ensureSlotTemplateState(slot.id);
    var isRest = day.cat === 'rest';

    var chip = document.createElement('button');
    chip.className = 'chip';
    chip.id = 'chip-'+slot.id;
    chip.innerHTML = '<span class="cdot" style="background:'+CAT_VAR[day.cat]+'"></span>'+slot.label;
    chip.addEventListener('click', function(){
      document.getElementById('card-'+slot.id).scrollIntoView({behavior:'smooth', block:'start'});
      openDay(slot.id, true);
    });
    strip.appendChild(chip);

    var card = document.createElement('div');
    card.className = 'day' + (isRest ? ' rest' : '');
    card.id = 'card-'+slot.id;

    var totalSets = day.exercises.reduce(function(sum, ex){ return ex.cardio ? sum : sum + ex.sets; }, 0);
    var doneSets = 0;
    Object.keys(daySets).forEach(function(k){ doneSets += (daySets[k] || []).length; });
    var kcal = calcCalories(day, userWeightLbs);

    var assignHtml =
      '<div class="assign-row">'+
        '<select class="assign-select" data-slot="'+slot.id+'" aria-label="Workout type for '+esc(day.name)+'">'+
          TEMPLATE_ORDER.map(function(k){
            return '<option value="'+k+'"'+(k===day.templateKey?' selected':'')+'>'+TEMPLATE_META[k].label+'</option>';
          }).join('')+
        '</select>'+
        '<input class="rename-input" data-slot="'+slot.id+'" type="text" maxlength="22" value="'+esc(day.name)+'" aria-label="Name for this day">'+
      '</div>';

    var addPickerHtml = '';
    if(!isRest && ADD_POOLS[day.cat]){
      var currentNames = day.exercises.map(function(e){ return e.name; });
      var pool = ADD_POOLS[day.cat].filter(function(p){ return currentNames.indexOf(p.name) === -1; });
      if(pool.length){
        addPickerHtml =
          '<div class="add-exercise-row">'+
            '<select class="add-select" data-slot="'+slot.id+'" aria-label="Choose an exercise to add">'+
              pool.map(function(p, pi){ return '<option value="'+pi+'">'+esc(p.name)+'</option>'; }).join('')+
            '</select>'+
            '<button class="add-btn" data-slot="'+slot.id+'" data-category="'+day.cat+'">+ ADD EXERCISE</button>'+
          '</div>';
      }
    }

    var bodyHtml;
    if(isRest){
      bodyHtml = '<div class="rest-block">'+esc(day.note)+'</div>';
    } else {
      bodyHtml = day.exercises.map(function(ex){
        var key = ex.key;
        var swapHtml = ex.swapOptions ?
          '<select class="ex-swap" data-slot="'+slot.id+'" data-idx="'+key+'" aria-label="Swap this exercise">'+
            ex.swapOptions.map(function(opt, oi){
              return '<option value="'+oi+'"'+(opt.name===ex.name?' selected':'')+'>'+esc(opt.name)+'</option>';
            }).join('')+
          '</select>' : '';
        if(ex.cardio){
          return '<div class="cardio-block"><b>'+esc(ex.name)+'</b> — '+esc(ex.cardio)+'<br>'+esc(ex.cue)+swapHtml+'</div>';
        }
        var doneIdxs = daySets[key] || [];
        var isDone = doneIdxs.length === ex.sets;
        var boxes = '';
        for(var si=0; si<ex.sets; si++){
          var on = doneIdxs.indexOf(si) !== -1;
          boxes += '<button class="set-box '+(on?'done':'')+'" data-slot="'+slot.id+'" data-ex="'+key+'" data-set="'+si+'" aria-label="Set '+(si+1)+'">'+(on?'✓':(si+1))+'</button>';
        }
        var removeHtml = ex.isAdded ? '<button class="ex-remove" data-slot="'+slot.id+'" data-key="'+key+'" aria-label="Remove exercise">✕</button>' : '';
        return '<div class="ex '+(isDone?'done':'')+'" data-slot="'+slot.id+'" data-idx="'+key+'">'+
          '<button class="ex-check '+(isDone?'done':'')+'" data-slot="'+slot.id+'" data-idx="'+key+'" aria-label="Toggle all sets">'+checkSvg+'</button>'+
          '<div class="ex-main">'+
            '<div class="ex-name">'+esc(ex.name)+(ex.isAdded?' <span class="added-tag">ADDED</span>':'')+'</div>'+
            '<div class="ex-cue">'+esc(ex.cue)+'</div>'+
            '<div class="ex-stats">'+
              '<div class="stat sets">'+ex.sets+' sets</div>'+
              '<div class="stat">'+esc(ex.reps)+' reps</div>'+
              '<div class="stat">rest '+esc(ex.rest)+'</div>'+
            '</div>'+
            '<div class="set-boxes">'+boxes+'</div>'+
            swapHtml+
          '</div>'+
          removeHtml+
        '</div>';
      }).join('');
    }

    var loggedToday = workoutLog[todayKey()];
    var isToday = INDEX_WEEKDAY[new Date().getDay()] === slot.id;
    var logHtml = '<div class="log-row">'+
      '<button class="log-btn '+(isToday && loggedToday ? 'logged':'')+'" data-slot="'+slot.id+'">'+
        (isToday && loggedToday ? 'Logged today ✓' : 'Log this to today')+
      '</button></div>';

    card.innerHTML =
      '<button class="day-head" data-id="'+slot.id+'">'+
        '<div class="day-num">'+(di+1<10?'0':'')+(di+1)+'</div>'+
        '<div class="day-titles">'+
          '<div class="day-name">'+esc(day.name)+' · '+slot.label+'</div>'+
          '<div class="day-focus">'+esc(day.focus)+(kcal>0?' · ~'+kcal+' kcal':'')+'</div>'+
        '</div>'+
        '<svg class="chevron" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"></polyline></svg>'+
      '</button>'+
      '<div class="day-body"><div class="day-inner">'+
        assignHtml+
        (isRest ? '' : '<p class="day-note">'+esc(day.note)+'</p>')+
        bodyHtml+
        addPickerHtml+
      '</div>'+
      (totalSets > 0 ?
        '<div class="day-progress">'+
          '<span id="prog-label-'+slot.id+'">'+doneSets+'/'+totalSets+' sets</span>'+
          '<div class="bar"><div class="bar-fill" id="prog-bar-'+slot.id+'" style="width:'+(totalSets?(doneSets/totalSets*100):0)+'%"></div></div>'+
        '</div>' : '')+
      logHtml+
      '</div>';

    daysEl.appendChild(card);
    wireCard(card, slot);
  });

  if(currentOpenSlotId){
    openDay(currentOpenSlotId, true);
  } else {
    openDay(INDEX_WEEKDAY[new Date().getDay()], true);
  }
  renderTargets();
}

function esc(s){
  return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
}

function wireCard(card, slot){
  card.querySelector('.day-head').addEventListener('click', function(){ toggleDay(slot.id); });

  var assignSel = card.querySelector('.assign-select');
  assignSel.addEventListener('click', function(e){ e.stopPropagation(); });
  assignSel.addEventListener('change', function(e){
    e.stopPropagation();
    dayAssign[slot.id] = assignSel.value;
    write(K.assign, dayAssign);
    ensureSlotTemplateState(slot.id);
    saveState();
    render();
    renderCalendar();
  });

  var renameInput = card.querySelector('.rename-input');
  renameInput.addEventListener('click', function(e){ e.stopPropagation(); });
  renameInput.addEventListener('change', function(){
    var v = renameInput.value.trim();
    if(v) dayNames[slot.id] = v; else delete dayNames[slot.id];
    write(K.names, dayNames);
    render();
  });

  card.querySelectorAll('.ex-swap').forEach(function(sel){
    sel.addEventListener('click', function(e){ e.stopPropagation(); });
    sel.addEventListener('change', function(e){
      e.stopPropagation();
      var exIdx = sel.getAttribute('data-idx');
      var templateKey = getTemplateKey(slot.id);
      setChosenOptionIdx(slot.id, templateKey, exIdx, parseInt(sel.value, 10));
      var ts = ensureSlotTemplateState(slot.id);
      ts[exIdx] = [];
      saveState();
      render();
    });
  });

  card.querySelectorAll('.ex-check').forEach(function(box){
    box.addEventListener('click', function(e){
      e.stopPropagation();
      var exIdx = box.getAttribute('data-idx');
      var day = getEffectiveDay(slot);
      var ex = day.exercises.filter(function(en){ return en.key === exIdx; })[0];
      var ts = ensureSlotTemplateState(slot.id);
      if(ts[exIdx].length === ex.sets){
        ts[exIdx] = [];
      } else {
        ts[exIdx] = [];
        for(var i=0; i<ex.sets; i++) ts[exIdx].push(i);
      }
      updateExRow(slot, exIdx);
      updateProgress(slot);
      saveState();
      maybeAutoLog(slot);
    });
  });

  card.querySelectorAll('.set-box').forEach(function(box){
    box.addEventListener('click', function(e){
      e.stopPropagation();
      var exIdx = box.getAttribute('data-ex');
      var setIdx = parseInt(box.getAttribute('data-set'), 10);
      var ts = ensureSlotTemplateState(slot.id);
      var arr = ts[exIdx];
      var pos = arr.indexOf(setIdx);
      if(pos !== -1) arr.splice(pos, 1); else arr.push(setIdx);
      updateExRow(slot, exIdx);
      updateProgress(slot);
      saveState();
      maybeAutoLog(slot);
    });
  });

  card.querySelectorAll('.ex-remove').forEach(function(btn){
    btn.addEventListener('click', function(e){
      e.stopPropagation();
      var exKey = btn.getAttribute('data-key');
      var templateKey = getTemplateKey(slot.id);
      var list = ensureAddedList(slot.id, templateKey);
      for(var i=0; i<list.length; i++){
        if(list[i].id === exKey){ list.splice(i,1); break; }
      }
      write(K.added, addedExercises);
      if(state[slot.id] && state[slot.id][templateKey]) delete state[slot.id][templateKey][exKey];
      saveState();
      render();
    });
  });

  var addBtn = card.querySelector('.add-btn');
  if(addBtn){
    addBtn.addEventListener('click', function(e){
      e.stopPropagation();
      var cat = addBtn.getAttribute('data-category');
      var select = card.querySelector('.add-select');
      var templateKey = getTemplateKey(slot.id);
      var day = getEffectiveDay(slot);
      var currentNames = day.exercises.map(function(en){ return en.name; });
      var pool = ADD_POOLS[cat].filter(function(p){ return currentNames.indexOf(p.name) === -1; });
      var chosen = pool[parseInt(select.value, 10)];
      if(!chosen) return;
      var item = {id:newAddedId()};
      for(var p in chosen){ if(Object.prototype.hasOwnProperty.call(chosen,p)) item[p] = chosen[p]; }
      ensureAddedList(slot.id, templateKey).push(item);
      write(K.added, addedExercises);
      if(!state[slot.id]) state[slot.id] = {};
      if(!state[slot.id][templateKey]) state[slot.id][templateKey] = {};
      state[slot.id][templateKey][item.id] = [];
      saveState();
      render();
    });
  }

  var logBtn = card.querySelector('.log-btn');
  if(logBtn){
    logBtn.addEventListener('click', function(e){
      e.stopPropagation();
      var cat = getCategory(getTemplateKey(slot.id));
      var tk = todayKey();
      if(workoutLog[tk] === cat) delete workoutLog[tk];
      else workoutLog[tk] = cat;
      write(K.log, workoutLog);
      render();
      renderCalendar();
    });
  }
}

function maybeAutoLog(slot){
  var day = getEffectiveDay(slot);
  var ts = ensureSlotTemplateState(slot.id);
  var total = day.exercises.reduce(function(s, ex){ return ex.cardio ? s : s + ex.sets; }, 0);
  if(total === 0) return;
  var done = 0;
  Object.keys(ts).forEach(function(k){ done += (ts[k] || []).length; });
  if(done === total){
    var tk = todayKey();
    if(!workoutLog[tk]){
      workoutLog[tk] = day.cat;
      write(K.log, workoutLog);
      renderCalendar();
      var btn = document.querySelector('#card-'+slot.id+' .log-btn');
      if(btn && INDEX_WEEKDAY[new Date().getDay()] === slot.id){
        btn.classList.add('logged');
        btn.textContent = 'Logged today ✓';
      }
    }
  }
}

function updateExRow(slot, exKey){
  var day = getEffectiveDay(slot);
  var ex = day.exercises.filter(function(en){ return en.key === exKey; })[0];
  var doneIdxs = ensureSlotTemplateState(slot.id)[exKey];
  var isDone = doneIdxs.length === ex.sets;
  var row = document.querySelector('.ex[data-slot="'+slot.id+'"][data-idx="'+exKey+'"]');
  if(!row) return;
  row.classList.toggle('done', isDone);
  row.querySelector('.ex-check').classList.toggle('done', isDone);
  row.querySelectorAll('.set-box').forEach(function(box){
    var si = parseInt(box.getAttribute('data-set'), 10);
    var on = doneIdxs.indexOf(si) !== -1;
    box.classList.toggle('done', on);
    box.textContent = on ? '✓' : (si+1);
  });
}

function updateProgress(slot){
  var day = getEffectiveDay(slot);
  var ts = ensureSlotTemplateState(slot.id);
  var total = day.exercises.reduce(function(s, ex){ return ex.cardio ? s : s + ex.sets; }, 0);
  var done = 0;
  Object.keys(ts).forEach(function(k){ done += (ts[k] || []).length; });
  var bar = document.getElementById('prog-bar-'+slot.id);
  var label = document.getElementById('prog-label-'+slot.id);
  if(bar) bar.style.width = (total ? (done/total*100) : 0) + '%';
  if(label) label.textContent = done + '/' + total + ' sets';
}

function toggleDay(id){
  var open = document.getElementById('card-'+id).classList.contains('open');
  openDay(id, !open);
}
function openDay(id, forceOpen){
  SLOTS.forEach(function(s){
    var card = document.getElementById('card-'+s.id);
    var chip = document.getElementById('chip-'+s.id);
    if(!card || !chip) return;
    if(s.id === id){
      if(forceOpen === false){
        card.classList.remove('open');
        chip.classList.remove('active');
        if(currentOpenSlotId === id) currentOpenSlotId = null;
      } else {
        card.classList.add('open');
        chip.classList.add('active');
        currentOpenSlotId = id;
      }
    }
  });
  var chip2 = document.getElementById('chip-'+id);
  if(chip2) chip2.classList.add('active');
}

/* ---------- CALENDAR ---------- */
var MONTH_NAMES = ['January','February','March','April','May','June','July','August','September','October','November','December'];

function renderCalendar(){
  var y = calCursor.getFullYear(), m = calCursor.getMonth();
  document.getElementById('calMonth').textContent = MONTH_NAMES[m] + ' ' + y;

  var grid = document.getElementById('calGrid');
  grid.innerHTML = '';
  ['S','M','T','W','T','F','S'].forEach(function(d, i){
    var el = document.createElement('div');
    el.className = 'cal-dow';
    el.textContent = d;
    el.setAttribute('aria-hidden','true');
    grid.appendChild(el);
  });

  var first = new Date(y, m, 1);
  var startPad = first.getDay();
  var daysInMonth = new Date(y, m+1, 0).getDate();
  var today = new Date();
  var tk = dateKey(today);

  for(var p=0; p<startPad; p++){
    var blank = document.createElement('div');
    blank.className = 'cal-cell blank';
    grid.appendChild(blank);
  }

  for(var d=1; d<=daysInMonth; d++){
    (function(dayNum){
      var cellDate = new Date(y, m, dayNum);
      var key = dateKey(cellDate);
      var logged = workoutLog[key];
      var cell = document.createElement('button');
      cell.className = 'cal-cell' + (logged ? ' logged' : '') + (key === tk ? ' today' : '') + (cellDate > today && key !== tk ? ' future' : '');
      cell.setAttribute('aria-label', MONTH_NAMES[m]+' '+dayNum+(logged ? ', '+CAT_LABEL[logged] : ', not logged'));
      cell.innerHTML = '<span>'+dayNum+'</span><span class="cal-dot" style="background:'+(logged ? CAT_VAR[logged] : 'transparent')+'"></span>';
      cell.addEventListener('click', function(){
        var scheduledCat = getCategory(getTemplateKey(INDEX_WEEKDAY[cellDate.getDay()]));
        if(scheduledCat === 'rest') scheduledCat = 'rest';
        var current = workoutLog[key];
        if(!current){
          workoutLog[key] = scheduledCat;
        } else if(current !== 'rest'){
          workoutLog[key] = 'rest';
        } else {
          delete workoutLog[key];
        }
        write(K.log, workoutLog);
        renderCalendar();
        render();
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

  var workouts = 0, rests = 0, byCat = {leg:0, arm:0, cardio:0};
  for(var d=1; d<=daysInMonth; d++){
    var v = workoutLog[dateKey(new Date(y, m, d))];
    if(!v) continue;
    if(v === 'rest') rests += 1;
    else { workouts += 1; if(byCat[v] !== undefined) byCat[v] += 1; }
  }
  var loggedDays = workouts + rests;
  var pct = elapsed > 0 ? Math.round((loggedDays / elapsed) * 100) : 0;

  var streak = 0;
  var cursor = new Date(today.getFullYear(), today.getMonth(), today.getDate());
  if(!workoutLog[dateKey(cursor)]) cursor.setDate(cursor.getDate() - 1);
  while(workoutLog[dateKey(cursor)]){
    streak += 1;
    cursor.setDate(cursor.getDate() - 1);
  }

  var stats = document.getElementById('calStats');
  stats.innerHTML =
    stat(workouts, 'workouts') +
    stat(streak, 'day streak') +
    stat(pct + '%', isCurrentMonth ? 'of days so far' : 'of the month') +
    stat(byCat.leg + '·' + byCat.arm + '·' + byCat.cardio, 'leg · arm · cardio');
}
function stat(num, label){
  return '<div class="cal-stat"><div class="cs-num">'+num+'</div><div class="cs-label">'+label+'</div></div>';
}

/* ---------- CONTROLS ---------- */
document.getElementById('themeBtn').addEventListener('click', function(){
  theme = (theme === 'dark') ? 'light' : 'dark';
  write(K.theme, theme);
  applyTheme();
});

document.getElementById('targetToggle').addEventListener('click', function(){
  document.getElementById('targetEdit').classList.toggle('open');
});
['tLeg','tArm','tCardio'].forEach(function(id){
  document.getElementById(id).addEventListener('change', function(){
    var el = document.getElementById(id);
    var cat = id === 'tLeg' ? 'leg' : (id === 'tArm' ? 'arm' : 'cardio');
    targets[cat] = clampInt(el.value, targets[cat]);
    write(K.targets, targets);
    renderTargets();
  });
});

var resetConfirming = false, resetTimeout = null;
var resetBtn = document.getElementById('resetBtn');
resetBtn.addEventListener('click', function(){
  if(!resetConfirming){
    resetConfirming = true;
    resetBtn.textContent = 'Tap again to confirm';
    resetBtn.classList.add('confirming');
    resetTimeout = setTimeout(function(){
      resetConfirming = false;
      resetBtn.textContent = 'Reset checkmarks';
      resetBtn.classList.remove('confirming');
    }, 3000);
  } else {
    clearTimeout(resetTimeout);
    resetConfirming = false;
    resetBtn.textContent = 'Reset checkmarks';
    resetBtn.classList.remove('confirming');
    state = {};
    SLOTS.forEach(function(s){ ensureSlotTemplateState(s.id); });
    saveState();
    render();
  }
});

document.getElementById('weightInput').addEventListener('change', function(){
  var el = document.getElementById('weightInput');
  var val = parseFloat(el.value);
  if(!isNaN(val) && val > 0){
    userWeightLbs = val;
    write(K.weight, userWeightLbs);
    render();
  }
});

document.getElementById('calPrev').addEventListener('click', function(){
  calCursor = new Date(calCursor.getFullYear(), calCursor.getMonth()-1, 1);
  renderCalendar();
});
document.getElementById('calNext').addEventListener('click', function(){
  calCursor = new Date(calCursor.getFullYear(), calCursor.getMonth()+1, 1);
  renderCalendar();
});
document.getElementById('calToday').addEventListener('click', function(){
  calCursor = new Date();
  renderCalendar();
});

loadAll();
document.getElementById('weightInput').value = userWeightLbs;
render();
renderCalendar();
</script>
</body>
</html>

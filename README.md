<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#170b13">
<title>Lulu Express 🚂💗</title>

<style>
*{
  box-sizing:border-box;
  -webkit-tap-highlight-color:transparent;
}

:root{
  --bg:#12080e;
  --panel:#26121e;
  --panel2:#35182a;
  --pink:#f39ac4;
  --pink2:#c9578d;
  --light:#ffe5f0;
  --gold:#f3ce6b;
  --green:#8fe0ac;
  --red:#ff718c;
  --muted:#d7b8c8;
}

html,body{
  margin:0;
  min-height:100%;
}

body{
  min-height:100vh;
  color:white;
  font-family:Arial,Helvetica,sans-serif;
  background:
    radial-gradient(circle at 50% -10%,#733653 0%,#321624 38%,#12080e 78%);
}

button,input,textarea{
  font:inherit;
}

button{
  cursor:pointer;
  touch-action:manipulation;
}

#app{
  width:100%;
  max-width:760px;
  margin:auto;
  padding:14px;
}

.hidden{
  display:none!important;
}

.topbar{
  display:flex;
  justify-content:space-between;
  align-items:center;
  margin-bottom:14px;
}

.logo{
  font-weight:900;
  font-size:20px;
}

.logo span{
  color:var(--pink);
}

.music-btn{
  border:1px solid #ffffff22;
  background:#ffffff10;
  color:white;
  border-radius:12px;
  padding:9px 12px;
}

.panel{
  background:linear-gradient(145deg,#321827,#1d0d16);
  border:1px solid #ffffff18;
  border-radius:24px;
  padding:20px;
  box-shadow:0 18px 50px #0009;
}

.center{
  text-align:center;
}

.badge{
  display:inline-block;
  padding:6px 11px;
  border-radius:999px;
  background:#f39ac418;
  border:1px solid #f39ac444;
  color:var(--light);
  font-size:11px;
  font-weight:bold;
  letter-spacing:1px;
  text-transform:uppercase;
}

h1{
  font-size:42px;
  line-height:1;
  margin:12px 0;
}

h2{
  font-size:28px;
  margin:9px 0;
}

h3{
  line-height:1.4;
}

p{
  color:var(--muted);
  line-height:1.55;
}

.btn{
  width:100%;
  border:0;
  border-radius:15px;
  padding:14px;
  margin-top:9px;
  font-weight:900;
  color:#32101f;
  background:linear-gradient(135deg,#f8acd0,#bd4f87);
}

.btn.gold{
  background:linear-gradient(135deg,#ffe9a4,#d8ad3f);
}

.btn.red{
  background:linear-gradient(135deg,#ff9cad,#d34f70);
}

.btn.dark{
  color:white;
  background:#ffffff0c;
  border:1px solid #ffffff20;
}

.btn:disabled{
  opacity:.45;
  cursor:not-allowed;
}

input,textarea{
  width:100%;
  background:#ffffff0b;
  color:white;
  border:1px solid #ffffff20;
  border-radius:14px;
  padding:14px;
  outline:none;
}

input:focus,textarea:focus{
  border-color:#f39ac477;
}

textarea{
  min-height:140px;
  resize:vertical;
}

.stats{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:8px;
  margin:15px 0;
}

.stat{
  padding:10px;
  border-radius:14px;
  background:#ffffff08;
  border:1px solid #ffffff10;
  text-align:center;
}

.stat strong{
  display:block;
  font-size:20px;
  color:var(--light);
}

.stat small{
  color:var(--muted);
}

.notice{
  padding:12px;
  border-radius:14px;
  background:#f39ac410;
  border:1px solid #f39ac426;
  margin:12px 0;
  color:var(--muted);
}

.round-list{
  display:grid;
  gap:7px;
  margin-top:15px;
}

.round{
  display:flex;
  align-items:center;
  gap:10px;
  padding:10px;
  border-radius:13px;
  background:#ffffff07;
  border:1px solid #ffffff0d;
}

.round.current{
  border-color:#f39ac466;
  background:#f39ac410;
}

.round.locked{
  opacity:.35;
}

.round-number{
  width:32px;
  height:32px;
  flex-shrink:0;
  display:grid;
  place-items:center;
  border-radius:50%;
  background:#ffffff10;
  font-weight:900;
}

.round.current .round-number{
  background:var(--pink);
  color:#32101f;
}

.choices{
  display:grid;
  gap:9px;
}

.choice{
  width:100%;
  padding:14px;
  border-radius:15px;
  border:1px solid #ffffff18;
  background:#ffffff09;
  color:white;
  text-align:left;
}

.choice:hover{
  background:#f39ac418;
}

.choice:disabled{
  opacity:.8;
  cursor:default;
}

.correct{
  background:#8fe0ac25!important;
  border-color:#8fe0ac88!important;
}

.wrong{
  background:#ff718c25!important;
  border-color:#ff718c88!important;
}

.big-number{
  font-size:48px;
  font-weight:1000;
  color:var(--gold);
}

.timer{
  font-size:35px;
  font-weight:1000;
  color:var(--gold);
  text-align:center;
}

.arena{
  position:relative;
  height:340px;
  overflow:hidden;
  border-radius:20px;
  background:radial-gradient(circle,#63284b,#160a12);
  border:1px solid #ffffff15;
}

.target{
  position:absolute;
  width:58px;
  height:58px;
  border:0;
  border-radius:50%;
  display:grid;
  place-items:center;
  font-size:28px;
  background:var(--pink);
  box-shadow:0 5px 25px #f39ac455;
}

.target.bad{
  background:#4b4b4b;
}

.memory-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:8px;
  margin:18px 0;
}

.memory-tile{
  aspect-ratio:1;
  border-radius:13px;
  border:1px solid #ffffff15;
  background:#ffffff0a;
  display:grid;
  place-items:center;
  font-size:24px;
  color:white;
}

.memory-tile.active{
  background:var(--pink);
  color:#32101f;
}

.card-row{
  display:flex;
  justify-content:center;
  gap:8px;
  flex-wrap:wrap;
  margin:18px 0;
}

.card{
  width:58px;
  height:78px;
  display:grid;
  place-items:center;
  background:white;
  color:#27101d;
  border-radius:9px;
  font-weight:900;
  font-size:20px;
}

.maze{
  display:grid;
  grid-template-columns:repeat(5,1fr);
  gap:5px;
  max-width:330px;
  margin:18px auto;
}

.maze-cell{
  aspect-ratio:1;
  display:grid;
  place-items:center;
  border-radius:7px;
  background:#ffffff09;
  font-size:24px;
  transition:.15s;
}

.maze-cell.wall{
  background:#080508;
  border:1px solid #ffffff08;
}

.maze-cell.player{
  background:var(--pink);
  color:#32101f;
  box-shadow:0 0 18px #f39ac455;
}

.maze-cell.goal{
  background:#f3ce6b33;
  border:1px solid var(--gold);
  box-shadow:0 0 18px #f3ce6b33;
}

.grid{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:8px;
}

.progress{
  height:8px;
  border-radius:999px;
  overflow:hidden;
  background:#ffffff10;
  margin:14px 0;
}

.progress-bar{
  height:100%;
  background:linear-gradient(90deg,var(--pink),var(--gold));
  transition:width .25s;
}

.final-box{
  border:2px solid var(--gold);
  background:radial-gradient(circle at top,#68294d,#25111c);
}

.trophy{
  font-size:65px;
}

.result-icon{
  font-size:70px;
  margin:18px 0;
}

.result-points{
  font-size:32px;
  font-weight:1000;
  color:var(--gold);
}

/* DERBY */

.derby-track{
  position:relative;
  margin:18px 0;
  padding:10px;
  border-radius:18px;
  background:#160b11;
  border:1px solid #ffffff18;
  overflow:hidden;
}

.race-lane{
  position:relative;
  height:72px;
  margin:6px 0;
  border-radius:12px;
  background:
    repeating-linear-gradient(
      90deg,
      #ffffff08 0 25px,
      #ffffff03 25px 50px
    );
  border:1px solid #ffffff0d;
}

.lane-name{
  position:absolute;
  left:8px;
  top:4px;
  z-index:5;
  font-size:11px;
  font-weight:900;
  color:var(--muted);
}

.race-road{
  position:absolute;
  left:0;
  right:0;
  bottom:0;
  top:20px;
}

.finish-line{
  position:absolute;
  right:8px;
  top:18px;
  bottom:5px;
  width:14px;
  background:
    repeating-linear-gradient(
      45deg,
      white 0 6px,
      #222 6px 12px
    );
  opacity:.9;
}

.racer{
  position:absolute;
  top:22px;
  left:0;
  width:48px;
  height:42px;
  display:grid;
  place-items:center;
  font-size:31px;
  transition:left .35s linear;
  filter:drop-shadow(0 4px 5px #0008);
  z-index:4;
}

.racer-name{
  position:absolute;
  top:-2px;
  left:53px;
  white-space:nowrap;
  font-size:10px;
  font-weight:900;
  color:white;
}

.derby-question{
  padding:18px;
  margin-top:15px;
  border-radius:18px;
  background:#ffffff08;
  border:1px solid #ffffff14;
}

.derby-question h3{
  font-size:22px;
  margin:4px 0 15px;
}

.derby-answer{
  display:flex;
  gap:8px;
}

.derby-answer input{
  flex:1;
}

.derby-answer button{
  width:auto;
  min-width:110px;
  margin:0;
}

.derby-distance{
  text-align:center;
  font-weight:900;
  color:var(--gold);
  margin-top:8px;
}

.derby-status{
  text-align:center;
  min-height:25px;
  color:var(--muted);
  font-weight:700;
}

.derby-countdown{
  font-size:76px;
  text-align:center;
  font-weight:1000;
  color:var(--gold);
  min-height:90px;
  display:grid;
  place-items:center;
}

.derby-result{
  text-align:center;
  padding:20px;
  border-radius:18px;
  background:#ffffff08;
  margin-top:15px;
}

.difficulty-grid,
.animal-grid{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:8px;
  margin:12px 0;
}

.select-card{
  border:1px solid #ffffff18;
  background:#ffffff08;
  color:white;
  border-radius:15px;
  padding:14px 8px;
  text-align:center;
}

.select-card.selected{
  border-color:var(--pink);
  background:#f39ac425;
  box-shadow:0 0 18px #f39ac422;
}

.animal{
  font-size:32px;
  display:block;
  margin-bottom:4px;
}

/* FINAL */

.final-answer-box{
  margin-top:15px;
  padding:16px;
  border-radius:18px;
  background:#ffffff07;
  border:1px solid #ffffff10;
}

.unlock{
  padding:15px;
  border-radius:18px;
  border:1px solid var(--gold);
  background:#f3ce6b10;
  margin-top:15px;
}

.shake{
  animation:shake .3s linear;
}

@keyframes shake{
  0%,100%{transform:translateX(0)}
  25%{transform:translateX(-8px)}
  75%{transform:translateX(8px)}
}

.pulse{
  animation:pulse 1s infinite;
}

@keyframes pulse{
  50%{transform:scale(1.04)}
}

@media(max-width:430px){
  h1{
    font-size:34px;
  }

  .panel{
    padding:15px;
  }

  .stats{
    grid-template-columns:repeat(3,1fr);
  }

  .derby-answer{
    flex-direction:column;
  }

  .derby-answer button{
    width:100%;
  }
}
</style>
</head>

<body>

<div id="app"></div>

<script>
"use strict";

/* =========================================================
   CORE GAME DATA
   ========================================================= */

const EVENTS = [
  "❤️ The Heart Rate",
  "🧠 The Memory Vault",
  "⚡ The Pressure Quiz",
  "🎰 The High Roller",
  "🧠 The Mind Games",
  "🃏 The Bluff",
  "⚡ The Survival Round",
  "🏎️ The Admirer Race",
  "💔 The Heartbreak Chamber",
  "🥊 The Heartbreak Boxing Match",
  "🧩 The Perfect Match",
  "🕵️ Who Knows Liliana Best?",
  "💨 The Reaction Gauntlet",
  "🗺️ The Heart Hunt",
  "🔐 The Love Lock",
  "🎯 The Cupid Shootout",
  "🧨 The Countdown",
  "🎰 The Ultimate Gamble",
  "💀 The Admirer's Last Stand",
  "🏇 THE LULU DERBY",
  "👑 THE FINAL CHALLENGE"
];

let state = {
  playerName:"",
  currentEvent:0,
  score:0,
  musicOn:true,
  finished:false
};

let eventStartScore = 0;
let audioContext = null;

/* =========================================================
   SAVE / LOAD
   ========================================================= */

function saveGame(){
  localStorage.setItem(
    "luluExpress",
    JSON.stringify(state)
  );
}

function loadGame(){
  try{
    const saved = JSON.parse(
      localStorage.getItem("luluExpress")
    );

    if(saved){
      state = {
        ...state,
        ...saved
      };
    }
  }catch(e){}
}

function resetJourney(){
  localStorage.removeItem("luluExpress");

  state = {
    playerName:"",
    currentEvent:0,
    score:0,
    musicOn:true,
    finished:false
  };

  eventStartScore = 0;
  home();
}

/* =========================================================
   AUDIO
   ========================================================= */

function toggleMusic(){
  state.musicOn = !state.musicOn;

  if(state.musicOn){
    playTone(440,.12);
  }

  saveGame();
  render();
}

function playTone(freq,duration=.08,type="sine"){
  if(!state.musicOn) return;

  try{
    audioContext =
      audioContext ||
      new (window.AudioContext || window.webkitAudioContext)();

    const oscillator =
      audioContext.createOscillator();

    const gain =
      audioContext.createGain();

    oscillator.type = type;
    oscillator.frequency.value = freq;

    gain.gain.setValueAtTime(
      .0001,
      audioContext.currentTime
    );

    gain.gain.exponentialRampToValueAtTime(
      .08,
      audioContext.currentTime + .01
    );

    gain.gain.exponentialRampToValueAtTime(
      .0001,
      audioContext.currentTime + duration
    );

    oscillator.connect(gain);
    gain.connect(audioContext.destination);

    oscillator.start();
    oscillator.stop(
      audioContext.currentTime + duration
    );
  }catch(e){}
}

/* =========================================================
   UTILITIES
   ========================================================= */

function escapeHTML(value){
  return String(value)
    .replace(/&/g,"&amp;")
    .replace(/</g,"&lt;")
    .replace(/>/g,"&gt;")
    .replace(/"/g,"&quot;")
    .replace(/'/g,"&#039;");
}

function shuffle(array){
  const a = [...array];

  for(let i=a.length-1;i>0;i--){
    const j=Math.floor(Math.random()*(i+1));
    [a[i],a[j]]=[a[j],a[i]];
  }

  return a;
}

function randomItem(array){
  return array[
    Math.floor(Math.random()*array.length)
  ];
}

function normaliseAnswer(value){
  return String(value)
    .trim()
    .toLowerCase()
    .replace(/[.,!?'"`]/g,"")
    .replace(/\s+/g," ");
}

function addPoints(amount){
  state.score += amount;

  if(state.score < 0){
    state.score = 0;
  }

  saveGame();
}

function goToEvent(index){
  state.currentEvent = index;
  eventStartScore = state.score;
  saveGame();
  render();
}

function finishEvent(points,success=true,message=""){
  if(points){
    addPoints(points);
  }

  showEventResult(
    success,
    message,
    state.score - eventStartScore
  );
}

function showEventResult(success,message,earned){
  const icon = success ? "💗" : "💔";

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <div class="result-icon">${icon}</div>

      <span class="badge">
        ${success ? "Round Complete" : "Round Over"}
      </span>

      <h2>${escapeHTML(message || (success ? "You survived!" : "Better luck next time!"))}</h2>

      <div class="result-points">
        ${earned >= 0 ? "+" : ""}${earned}
      </div>

      <p>Points earned this round</p>

      <div class="stats">
        <div class="stat">
          <strong>${state.score}</strong>
          <small>Total Score</small>
        </div>

        <div class="stat">
          <strong>${state.currentEvent + 1}</strong>
          <small>Round</small>
        </div>

        <div class="stat">
          <strong>${EVENTS.length}</strong>
          <small>Total</small>
        </div>
      </div>

      ${
        state.currentEvent < EVENTS.length - 1
        ?
        `<button class="btn" onclick="continueToNextEvent()">
          Continue 🚂
        </button>`
        :
        `<button class="btn gold" onclick="finalResult()">
          See Final Result 👑
        </button>`
      }
    </div>
  `;
}

function continueToNextEvent(){
  goToEvent(state.currentEvent + 1);
}

function continueToFinalChallenge(){
  goToEvent(20);
}

function topBar(){
  return `
    <div class="topbar">
      <div class="logo">Lulu <span>Express</span> 🚂💗</div>

      <button class="music-btn" onclick="toggleMusic()">
        ${state.musicOn ? "🔊" : "🔇"}
      </button>
    </div>
  `;
}

function stats(){
  return `
    <div class="stats">
      <div class="stat">
        <strong>${state.score}</strong>
        <small>Points</small>
      </div>

      <div class="stat">
        <strong>${state.currentEvent + 1}</strong>
        <small>Round</small>
      </div>

      <div class="stat">
        <strong>${EVENTS.length}</strong>
        <small>Rounds</small>
      </div>
    </div>
  `;
}

function roundList(){
  return `
    <div class="round-list">
      ${EVENTS.map((event,index)=>`
        <div class="round ${
          index === state.currentEvent ? "current" :
          index < state.currentEvent ? "" : "locked"
        }">
          <div class="round-number">${index+1}</div>
          <div>${escapeHTML(event)}</div>
        </div>
      `).join("")}
    </div>
  `;
}

/* =========================================================
   HOME
   ========================================================= */

function home(){
  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Welcome Aboard</span>

      <h1>Lulu Express 🚂💗</h1>

      <p>
        Welcome to the ultimate Liliana challenge.
        Twenty-one rounds stand between you and the
        final challenge.
      </p>

      <input
        id="playerName"
        maxlength="30"
        placeholder="Enter your name..."
        value="${escapeHTML(state.playerName)}"
      >

      <button class="btn" onclick="startGame()">
        🚂 Board the Lulu Express
      </button>

      <button class="btn dark" onclick="showAccessCode()">
        🔐 Secret Access
      </button>

      ${
        state.score > 0
        ?
        `<button class="btn dark" onclick="resumeGame()">
          ▶️ Continue Journey
        </button>`
        :
        ""
      }

      <div class="notice">
        💗 There are ${EVENTS.length} challenges.
        <br>
        👑 Score over <strong>3000</strong> points to unlock
        the private Lulu call.
      </div>
    </div>

    <div class="panel" style="margin-top:14px">
      <h3>🚂 The Journey</h3>
      ${roundList()}
    </div>
  `;
}

function startGame(){
  const input = document.getElementById("playerName");
  const name = input.value.trim();

  state.playerName = name || "Admirer";
  state.currentEvent = 0;
  state.score = 0;
  state.finished = false;

  eventStartScore = 0;

  saveGame();
  render();
}

function resumeGame(){
  render();
}

function showAccessCode(){
  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Restricted</span>

      <h2>🔐 Secret Access</h2>

      <p>
        Enter the four-digit access code.
      </p>

      <input
        id="accessInput"
        inputmode="numeric"
        maxlength="4"
        placeholder="••••"
      >

      <button class="btn gold" onclick="checkCode()">
        Unlock
      </button>

      <button class="btn dark" onclick="home()">
        Back
      </button>
    </div>
  `;
}

function checkCode(){
  const value =
    document.getElementById("accessInput").value.trim();

  if(value === "3333"){
    playTone(880,.2);
    goToEvent(20);
  }else{
    const box =
      document.getElementById("accessInput");

    box.classList.remove("shake");
    void box.offsetWidth;
    box.classList.add("shake");

    playTone(120,.2);
  }
}

/* =========================================================
   RENDER ROUTER
   ========================================================= */

function render(){
  switch(state.currentEvent){
    case 0: event1(); break;
    case 1: event2(); break;
    case 2: event3(); break;
    case 3: event4(); break;
    case 4: event5(); break;
    case 5: event6(); break;
    case 6: event7(); break;
    case 7: event8(); break;
    case 8: event9(); break;
    case 9: event10(); break;
    case 10: event11(); break;
    case 11: event12(); break;
    case 12: event13(); break;
    case 13: event14(); break;
    case 14: event15(); break;
    case 15: event16(); break;
    case 16: event17(); break;
    case 17: event18(); break;
    case 18: event19(); break;
    case 19: event20(); break;
    case 20: event21(); break;
    default: home();
  }
}

/* =========================================================
   EVENT 1
   HEART RATE
   ========================================================= */

let heartTimer = null;
let heartSpawner = null;
let heartHits = 0;
let heartMisses = 0;

function event1(){
  clearInterval(heartTimer);
  clearInterval(heartSpawner);

  heartHits = 0;
  heartMisses = 0;

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 1</span>
      <h2>❤️ The Heart Rate</h2>

      <p>
        Click the <strong>❤️</strong> hearts.
        Avoid the <strong>💔</strong> broken hearts.
      </p>

      <div class="stats">
        <div class="stat">
          <strong id="heartHits">0</strong>
          <small>Hearts</small>
        </div>
        <div class="stat">
          <strong id="heartMisses">0</strong>
          <small>Broken</small>
        </div>
        <div class="stat">
          <strong id="heartTime">20</strong>
          <small>Seconds</small>
        </div>
      </div>

      <div class="arena" id="heartArena"></div>
    </div>
  `;

  const arena =
    document.getElementById("heartArena");

  function spawnHeart(){
    const button =
      document.createElement("button");

    const isBad =
      Math.random() < .28;

    button.className =
      "target" + (isBad ? " bad" : "");

    button.type = "button";
    button.textContent =
      isBad ? "💔" : "❤️";

    button.style.left =
      Math.random() * 80 + "%";

    button.style.top =
      Math.random() * 72 + "%";

    button.onclick = function(e){
      e.stopPropagation();

      if(isBad){
        heartMisses++;
        addPoints(-4);
        playTone(150,.08);
      }else{
        heartHits++;
        addPoints(5);
        playTone(700,.06);
      }

      button.remove();

      document.getElementById("heartHits").textContent =
        heartHits;

      document.getElementById("heartMisses").textContent =
        heartMisses;
    };

    arena.appendChild(button);

    setTimeout(()=>{
      if(button.isConnected){
        button.remove();
      }
    },1700);
  }

  let remaining = 20;

  heartSpawner =
    setInterval(spawnHeart,900);

  heartTimer =
    setInterval(()=>{
      remaining--;

      const time =
        document.getElementById("heartTime");

      if(time){
        time.textContent = remaining;
      }

      if(remaining <= 0){
        clearInterval(heartTimer);
        clearInterval(heartSpawner);

        const bonus =
          heartHits * 2;

        finishEvent(
          bonus,
          heartHits > heartMisses,
          heartHits > heartMisses
            ? "Your heart survived the chamber! ❤️"
            : "The broken hearts got the better of you. 💔"
        );
      }
    },1000);
}

/* =========================================================
   EVENT 2
   MEMORY VAULT
   ========================================================= */

let memorySequence = [];
let memoryPlayer = [];
let memoryLevel = 3;
let memoryLocked = false;

const MEMORY_SYMBOLS =
  ["❤️","🌹","⭐","🐬","💎","🌙","🍀","🦋"];

function event2(){
  memoryLevel = 3;
  memoryPlayer = [];
  memoryLocked = false;

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 2</span>
      <h2>🧠 The Memory Vault</h2>

      <p id="memoryText">
        Memorise the sequence.
      </p>

      <div class="big-number" id="memoryLevel">
        Level 3
      </div>

      <div class="memory-grid" id="memoryGrid"></div>
    </div>
  `;

  startMemoryRound();
}

function startMemoryRound(){
  memoryLocked = true;
  memoryPlayer = [];

  memorySequence =
    Array.from(
      {length:memoryLevel},
      ()=>Math.floor(Math.random()*16)
    );

  const grid =
    document.getElementById("memoryGrid");

  grid.innerHTML =
    Array.from({length:16},(_,i)=>`
      <button
        class="memory-tile"
        id="memory-${i}"
        onclick="memoryPick(${i})"
      ></button>
    `).join("");

  document.getElementById("memoryText").textContent =
    "Watch carefully...";

  let index = 0;

  const timer =
    setInterval(()=>{
      document
        .querySelectorAll(".memory-tile")
        .forEach(x=>x.classList.remove("active"));

      if(index >= memorySequence.length){
        clearInterval(timer);

        memoryLocked = false;

        document.getElementById("memoryText").textContent =
          "Now repeat the sequence.";

        return;
      }

      const tile =
        document.getElementById(
          "memory-" + memorySequence[index]
        );

      if(tile){
        tile.classList.add("active");
      }

      index++;
    },550);
}

function memoryPick(index){
  if(memoryLocked) return;

  const expected =
    memorySequence[memoryPlayer.length];

  if(index !== expected){
    memoryLocked = true;

    finishEvent(
      -10,
      false,
      "The vault rejected your memory. 🧠💔"
    );

    return;
  }

  memoryPlayer.push(index);
  addPoints(memoryLevel * 10);

  if(memoryPlayer.length === memorySequence.length){

    if(memoryLevel >= 7){
      finishEvent(
        40,
        true,
        "You cracked the Memory Vault! 🧠🔓"
      );
      return;
    }

    memoryLevel++;

    document.getElementById("memoryLevel").textContent =
      "Level " + memoryLevel;

    setTimeout(startMemoryRound,700);
  }
}

/* =========================================================
   QUESTION GENERATOR
   1000+ UNIQUE QUESTIONS
   ========================================================= */

const GENERAL_QUESTIONS = [
  {
    q:"How many days are in a week?",
    a:"7"
  },
  {
    q:"How many months are in a year?",
    a:"12"
  },
  {
    q:"How many hours are in a day?",
    a:"24"
  },
  {
    q:"What is the capital of New Zealand?",
    a:"Wellington"
  },
  {
    q:"What planet is known as the Red Planet?",
    a:"Mars"
  },
  {
    q:"What is the largest ocean on Earth?",
    a:"Pacific Ocean"
  },
  {
    q:"How many sides does a triangle have?",
    a:"3"
  },
  {
    q:"What gas do humans need to breathe?",
    a:"Oxygen"
  },
  {
    q:"What is the opposite of north?",
    a:"South"
  },
  {
    q:"How many letters are in the English alphabet?",
    a:"26"
  },
  {
    q:"Which planet is closest to the Sun?",
    a:"Mercury"
  },
  {
    q:"How many legs does a spider have?",
    a:"8"
  },
  {
    q:"What colour do you get by mixing red and blue?",
    a:"Purple"
  },
  {
    q:"How many minutes are in an hour?",
    a:"60"
  },
  {
    q:"How many seconds are in a minute?",
    a:"60"
  }
];

function buildQuestionPool(){
  const pool = [];

  for(let a=0;a<=100;a++){
    for(let b=0;b<=100;b++){
      pool.push({
        q:`What is ${a} + ${b}?`,
        a:String(a+b)
      });
    }
  }

  for(let a=0;a<=150;a++){
    for(let b=0;b<=50;b++){
      pool.push({
        q:`What is ${Math.max(a,b)} - ${Math.min(a,b)}?`,
        a:String(Math.abs(a-b))
      });
    }
  }

  for(let a=1;a<=12;a++){
    for(let b=1;b<=12;b++){
      pool.push({
        q:`What is ${a} × ${b}?`,
        a:String(a*b)
      });
    }
  }

  for(let a=1;a<=20;a++){
    for(let b=1;b<=20;b++){
      pool.push({
        q:`What is ${a*b} ÷ ${a}?`,
        a:String(b)
      });
    }
  }

  for(let a=1;a<=100;a++){
    pool.push({
      q:`What is ${a} + 10?`,
      a:String(a+10)
    });

    pool.push({
      q:`What is ${a} × 2?`,
      a:String(a*2)
    });

    pool.push({
      q:`What is ${a} × 3?`,
      a:String(a*3)
    });
  }

  return shuffle(
    pool.concat(GENERAL_QUESTIONS)
  );
}

const QUESTION_POOL = buildQuestionPool();

/* =========================================================
   MULTIPLE CHOICE BUILDER
   ========================================================= */

function makeChoices(question){
  const correct = String(question.a);

  let distractors = [];

  if(/^\d+$/.test(correct)){
    const number = Number(correct);

    const candidates = [
      number + 1,
      number - 1,
      number + 2,
      number - 2,
      number + 5,
      number - 5,
      number + 10,
      number - 10
    ]
    .filter(x=>x>=0)
    .map(String);

    distractors =
      shuffle(
        [...new Set(candidates)]
      ).slice(0,3);
  }

  if(distractors.length < 3){
    distractors.push(
      ...shuffle(
        QUESTION_POOL
          .map(x=>String(x.a))
          .filter(x=>x!==correct)
      )
    );
  }

  return shuffle([
    correct,
    ...[...new Set(distractors)]
      .filter(x=>x!==correct)
      .slice(0,3)
  ]);
}

/* =========================================================
   EVENT 3
   PRESSURE QUIZ
   ========================================================= */

let pressureQuestions = [];
let pressureIndex = 0;
let pressurePoints = 0;

function event3(){
  pressureQuestions =
    shuffle(QUESTION_POOL).slice(0,12);

  pressureIndex = 0;
  pressurePoints = 0;

  renderPressureQuestion();
}

function renderPressureQuestion(){
  if(pressureIndex >= pressureQuestions.length){
    finishEvent(
      40,
      pressurePoints >= 90,
      pressurePoints >= 90
        ? "You crushed the Pressure Quiz! ⚡"
        : "The pressure got to you."
    );
    return;
  }

  const question =
    pressureQuestions[pressureIndex];

  const choices =
    makeChoices(question);

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel">
      <span class="badge">Event 3</span>

      <h2>⚡ The Pressure Quiz</h2>

      ${stats()}

      <div class="progress">
        <div
          class="progress-bar"
          style="width:${pressureIndex / pressureQuestions.length * 100}%"
        ></div>
      </div>

      <p>
        Question ${pressureIndex + 1}
        of ${pressureQuestions.length}
      </p>

      <h3>${escapeHTML(question.q)}</h3>

      <div class="choices">
        ${choices.map(choice=>`
          <button
            class="choice"
            onclick="pressureAnswer(this,'${escapeHTML(choice)}','${escapeHTML(question.a)}')"
          >
            ${escapeHTML(choice)}
          </button>
        `).join("")}
      </div>
    </div>
  `;
}

function pressureAnswer(button,answer,correct){
  const buttons =
    document.querySelectorAll(".choice");

  buttons.forEach(x=>x.disabled=true);

  if(normaliseAnswer(answer) === normaliseAnswer(correct)){
    button.classList.add("correct");
    pressurePoints += 15;
    addPoints(15);
    playTone(700,.08);
  }else{
    button.classList.add("wrong");
    pressurePoints -= 5;
    addPoints(-5);
    playTone(150,.1);
  }

  pressureIndex++;

  setTimeout(renderPressureQuestion,450);
}

/* =========================================================
   EVENT 4
   HIGH ROLLER
   ========================================================= */

let rollerPot = 100;
let rollerTurn = 0;

function event4(){
  rollerPot = 100;
  rollerTurn = 0;
  renderRoller();
}

function renderRoller(){
  if(rollerTurn >= 5){
    finishEvent(
      Math.floor(rollerPot / 4),
      rollerPot >= 100,
      rollerPot >= 100
        ? "The house couldn't beat you. 🎰"
        : "The house wins this time."
    );
    return;
  }

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 4</span>
      <h2>🎰 The High Roller</h2>

      <div class="big-number">
        $${rollerPot}
      </div>

      <p>
        Turn ${rollerTurn+1} of 5.
        Choose your wager.
      </p>

      <button class="btn" onclick="rollerBet(10)">Bet 10</button>
      <button class="btn" onclick="rollerBet(25)">Bet 25</button>
      <button class="btn gold" onclick="rollerBet(50)">Bet 50</button>
    </div>
  `;
}

function rollerBet(amount){
  rollerTurn++;

  const win =
    Math.random() > .42;

  if(win){
    rollerPot += amount;
    addPoints(amount);
  }else{
    rollerPot -= amount;
    addPoints(-Math.floor(amount/2));
  }

  rollerPot =
    Math.max(0,rollerPot);

  renderRoller();
}

/* =========================================================
   EVENT 5
   MIND GAMES
   ========================================================= */

const MIND_QUESTIONS = [
  ["Which number comes next: 2,4,6,8...?","10"],
  ["Which number comes next: 3,6,9,12...?","15"],
  ["What is half of 50?","25"],
  ["What is 9 × 9?","81"],
  ["Which is larger: 100 or 10?","100"],
  ["What is 100 ÷ 10?","10"],
  ["How many sides does a square have?","4"],
  ["What comes after Tuesday?","Wednesday"]
];

let mindIndex = 0;

function event5(){
  mindIndex = 0;
  renderMind();
}

function renderMind(){
  if(mindIndex >= MIND_QUESTIONS.length){
    finishEvent(
      30,
      true,
      "You outsmarted the Mind Games! 🧠"
    );
    return;
  }

  const q = MIND_QUESTIONS[mindIndex];

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel">
      <span class="badge">Event 5</span>
      <h2>🧠 The Mind Games</h2>

      ${stats()}

      <h3>${q[0]}</h3>

      <input
        id="mindAnswer"
        placeholder="Type your answer..."
        onkeydown="if(event.key==='Enter') mindAnswer()"
      >

      <button class="btn" onclick="mindAnswer()">
        Submit
      </button>
    </div>
  `;
}

function mindAnswer(){
  const input =
    document.getElementById("mindAnswer");

  const answer =
    normaliseAnswer(input.value);

  const correct =
    normaliseAnswer(MIND_QUESTIONS[mindIndex][1]);

  if(answer === correct){
    addPoints(15);
  }else{
    addPoints(3);
  }

  mindIndex++;
  renderMind();
}

/* =========================================================
   EVENT 6
   BLUFF
   ========================================================= */

let bluffChips = 100;
let bluffTurn = 0;

function event6(){
  bluffChips = 100;
  bluffTurn = 0;
  renderBluff();
}

function renderBluff(){
  if(bluffTurn >= 3){
    finishEvent(
      Math.floor(bluffChips/4),
      bluffChips >= 100,
      "You made it through the Bluff. 🃏"
    );
    return;
  }

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 6</span>
      <h2>🃏 The Bluff</h2>

      <div class="big-number">
        ${bluffChips} chips
      </div>

      <div class="card-row">
        <div class="card">A♥</div>
        <div class="card">K♦</div>
        <div class="card">Q♣</div>
      </div>

      <p>
        Turn ${bluffTurn+1} of 3.
      </p>

      <button class="btn" onclick="bluffChoice('bet')">
        🎲 Bet
      </button>

      <button class="btn gold" onclick="bluffChoice('bluff')">
        😈 Bluff
      </button>

      <button class="btn dark" onclick="bluffChoice('fold')">
        🏳️ Fold
      </button>
    </div>
  `;
}

function bluffChoice(choice){
  bluffTurn++;

  if(choice === "fold"){
    bluffChips -= 10;
    addPoints(3);
  }else{
    const win = Math.random() > .42;

    if(win){
      bluffChips += 30;
      addPoints(15);
    }else{
      bluffChips -= 25;
    }
  }

  bluffChips =
    Math.max(0,bluffChips);

  renderBluff();
}

/* =========================================================
   EVENT 7
   SURVIVAL
   ========================================================= */

let survivalLevel = 3;
let survivalSequence = [];
let survivalInput = [];
let survivalLocked = false;

function event7(){
  survivalLevel = 3;
  survivalInput = [];
  survivalLocked = false;

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 7</span>
      <h2>⚡ The Survival Round</h2>

      <p id="survivalText">
        Memorise the sequence.
      </p>

      <div class="big-number" id="survivalLevel">
        Level 3
      </div>

      <div
        class="memory-grid"
        id="survivalGrid"
      ></div>
    </div>
  `;

  startSurvival();
}

function startSurvival(){
  survivalInput = [];
  survivalLocked = true;

  const length =
    survivalLevel + 2;

  survivalSequence =
    Array.from(
      {length},
      ()=>Math.floor(Math.random()*16)
    );

  const grid =
    document.getElementById("survivalGrid");

  grid.innerHTML =
    Array.from({length:16},(_,i)=>`
      <button
        class="memory-tile"
        onclick="survivalPick(${i})"
      ></button>
    `).join("");

  let i=0;

  const timer =
    setInterval(()=>{
      grid.querySelectorAll(".memory-tile")
        .forEach(x=>x.classList.remove("active"));

      if(i >= survivalSequence.length){
        clearInterval(timer);
        survivalLocked=false;

        document.getElementById("survivalText").textContent =
          "Repeat it!";

        return;
      }

      grid.children[
        survivalSequence[i]
      ].classList.add("active");

      i++;
    },450);
}

function survivalPick(index){
  if(survivalLocked) return;

  const expected =
    survivalSequence[survivalInput.length];

  if(index !== expected){
    survivalLocked = true;

    finishEvent(
      -10,
      false,
      "You didn't survive the sequence. ⚡"
    );

    return;
  }

  survivalInput.push(index);
  addPoints(10);

  if(survivalInput.length === survivalSequence.length){

    if(survivalLevel >= 5){
      finishEvent(
        35,
        true,
        "You survived every level! ⚡"
      );
    }else{
      survivalLevel++;

      document.getElementById("survivalLevel").textContent =
        "Level " + survivalLevel;

      setTimeout(startSurvival,650);
    }
  }
}

/* =========================================================
   EVENT 8
   ADMIRER RACE
   ========================================================= */

let admirerPlayer = 0;
let admirerRival = 0;
let admirerLap = 0;

function event8(){
  admirerPlayer=0;
  admirerRival=0;
  admirerLap=0;

  renderAdmirerRace();
}

function renderAdmirerRace(){
  if(admirerLap >= 8){
    const win =
      admirerPlayer > admirerRival;

    finishEvent(
      win ? 50 : 15,
      win,
      win
        ? "You won the Admirer Race! 🏎️"
        : "Your rival just edged you out."
    );

    return;
  }

  const symbols =
    ["❤️","🌹","⭐","🐬"];

  const target =
    randomItem(symbols);

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 8</span>
      <h2>🏎️ The Admirer Race</h2>

      <p>
        Lap ${admirerLap+1} of 8
      </p>

      <div class="stats">
        <div class="stat">
          <strong>${admirerPlayer}</strong>
          <small>You</small>
        </div>
        <div class="stat">
          <strong>${admirerRival}</strong>
          <small>Rival</small>
        </div>
        <div class="stat">
          <strong>${8-admirerLap}</strong>
          <small>Laps Left</small>
        </div>
      </div>

      <h3>Click ${target}</h3>

      <button
        class="btn"
        onclick="admirerClick()"
      >
        ${target}
      </button>
    </div>
  `;

  window.currentAdmirerTarget = target;
}

function admirerClick(){
  admirerPlayer++;
  addPoints(8);

  if(Math.random() > .35){
    admirerRival++;
  }

  admirerLap++;
  renderAdmirerRace();
}

/* =========================================================
   EVENT 9
   HEARTBREAK CHAMBER
   ========================================================= */

let chamberDoors = [];
let chamberPick = 0;

function event9(){
  chamberDoors =
    shuffle([30,15,-10,50,20]);

  chamberPick = 0;

  renderChamber();
}

function renderChamber(){
  if(chamberPick >= 5){
    finishEvent(
      20,
      true,
      "You escaped the Heartbreak Chamber. 💗"
    );
    return;
  }

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 9</span>
      <h2>💔 The Heartbreak Chamber</h2>

      <p>
        Door ${chamberPick+1} of 5.
        Choose carefully.
      </p>

      <div class="grid">
        ${[1,2,3,4].map(i=>`
          <button
            class="btn ${
              i===1 ? "" :
              i===2 ? "gold" :
              i===3 ? "red" : "dark"
            }"
            onclick="chooseDoor()"
          >
            🚪 Door ${i}
          </button>
        `).join("")}
      </div>
    </div>
  `;
}

function chooseDoor(){
  const result =
    randomItem(chamberDoors);

  chamberPick++;
  addPoints(result);

  renderChamber();
}

/* =========================================================
   EVENT 10
   BOXING
   ========================================================= */

let playerHP=100;
let enemyHP=100;

function event10(){
  playerHP=100;
  enemyHP=100;
  renderBoxing();
}

function renderBoxing(){
  if(enemyHP <= 0){
    finishEvent(
      50,
      true,
      "You knocked out the Heartbreak! 🥊❤️"
    );
    return;
  }

  if(playerHP <= 0){
    finishEvent(
      0,
      false,
      "The Heartbreak knocked you out."
    );
    return;
  }

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 10</span>
      <h2>🥊 The Heartbreak Boxing Match</h2>

      <div class="stats">
        <div class="stat">
          <strong>${playerHP}</strong>
          <small>Your HP</small>
        </div>
        <div class="stat">
          <strong>${enemyHP}</strong>
          <small>Enemy HP</small>
        </div>
        <div class="stat">
          <strong>${Math.max(0,enemyHP)}</strong>
          <small>Damage Left</small>
        </div>
      </div>

      <button class="btn" onclick="boxingMove('punch')">
        👊 Punch
      </button>

      <button class="btn red" onclick="boxingMove('heavy')">
        💥 Heavy Punch
      </button>

      <button class="btn dark" onclick="boxingMove('block')">
        🛡️ Block
      </button>
    </div>
  `;
}

function boxingMove(move){
  let damage=0;

  if(move==="punch"){
    damage =
      Math.floor(Math.random()*12)+8;
  }

  if(move==="heavy"){
    damage =
      Math.floor(Math.random()*25)+5;
  }

  if(move==="block"){
    damage=0;
  }

  enemyHP -= damage;

  addPoints(damage);

  if(enemyHP > 0){
    let incoming =
      Math.floor(Math.random()*15)+5;

    if(move==="block"){
      incoming =
        Math.floor(incoming/2);
    }

    playerHP -= incoming;
  }

  renderBoxing();
}

/* =========================================================
   EVENT 11
   PERFECT MATCH
   ========================================================= */

let matchPattern=[];
let matchClicked=[];
let matchLocked=false;

function event11(){
  matchPattern =
    Array.from(
      {length:16},
      ()=>Math.random()>.55
    );

  matchClicked =
    Array(16).fill(false);

  matchLocked=false;

  const activeCount =
    matchPattern.filter(Boolean).length;

  if(activeCount < 5){
    for(let i=0;i<5;i++){
      matchPattern[i]=true;
    }
  }

  renderMatch();
}

function renderMatch(){
  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 11</span>
      <h2>🧩 The Perfect Match</h2>

      <p>
        Memorise the glowing tiles,
        then click each one once.
      </p>

      <div
        class="memory-grid"
        id="matchGrid"
      ></div>
    </div>
  `;

  const grid =
    document.getElementById("matchGrid");

  matchPattern.forEach((active,i)=>{
    const tile =
      document.createElement("button");

    tile.className =
      "memory-tile" +
      (active ? " active" : "");

    tile.textContent =
      active ? "💗" : "";

    grid.appendChild(tile);
  });

  setTimeout(()=>{
    grid
      .querySelectorAll(".memory-tile")
      .forEach(x=>{
        x.classList.remove("active");
        x.textContent="";
      });

    grid
      .querySelectorAll(".memory-tile")
      .forEach((tile,i)=>{
        tile.onclick=()=>{
          matchClick(i,tile);
        };
      });
  },1800);
}

function matchClick(index,tile){
  if(matchLocked || matchClicked[index]){
    return;
  }

  if(!matchPattern[index]){
    matchLocked=true;

    finishEvent(
      -10,
      false,
      "Wrong tile. The perfect match escaped. 💔"
    );

    return;
  }

  matchClicked[index]=true;
  tile.disabled=true;
  tile.classList.add("correct");
  tile.textContent="💗";

  addPoints(5);

  const complete =
    matchPattern.every(
      (active,i)=>
        !active || matchClicked[i]
    );

  if(complete){
    matchLocked=true;

    finishEvent(
      30,
      true,
      "Perfect match! 🧩💗"
    );
  }
}

/* =========================================================
   EVENT 12
   WHO KNOWS LILIANA BEST?
   ========================================================= */

const LILIANA_QUIZ = [
  ["Liliana's birthday is July 22.","true"],
  ["Liliana has green eyes.","true"],
  ["Liliana studied Psychology.","true"],
  ["Liliana has four piercings.","true"],
  ["Liliana has four nephews.","true"],
  ["Liliana has one niece.","true"],
  ["Liliana has two dogs.","true"],
  ["One of her dogs is called Arlo.","true"],
  ["One of her dogs is called Aayla.","true"],
  ["Liliana's favourite number is 3.","true"],
  ["Liliana likes dolphins.","true"],
  ["Liliana likes sushi.","true"],
  ["Liliana has seven siblings.","false"],
  ["Liliana has two tattoos.","false"],
  ["Liliana's favourite number is 9.","false"],
  ["Liliana is afraid of drowning.","true"]
];

let lilianaIndex=0;

function event12(){
  lilianaIndex=0;
  renderLilianaQuiz();
}

function renderLilianaQuiz(){
  if(lilianaIndex >= LILIANA_QUIZ.length){
    finishEvent(
      50,
      true,
      "You really do know Liliana. 🕵️💗"
    );
    return;
  }

  const item =
    LILIANA_QUIZ[lilianaIndex];

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel">
      <span class="badge">Event 12</span>

      <h2>🕵️ Who Knows Liliana Best?</h2>

      ${stats()}

      <p>
        Question ${lilianaIndex+1}
        of ${LILIANA_QUIZ.length}
      </p>

      <h3>${escapeHTML(item[0])}</h3>

      <div class="choices">
        <button
          class="choice"
          onclick="lilianaAnswer('true')"
        >
          ✅ True
        </button>

        <button
          class="choice"
          onclick="lilianaAnswer('false')"
        >
          ❌ False
        </button>
      </div>
    </div>
  `;
}

function lilianaAnswer(answer){
  const correct =
    LILIANA_QUIZ[lilianaIndex][1];

  if(answer===correct){
    addPoints(15);
  }else{
    addPoints(-5);
  }

  lilianaIndex++;
  renderLilianaQuiz();
}

/* =========================================================
   EVENT 13
   REACTION GAUNTLET
   ========================================================= */

let reactionRound=0;
let reactionTimer=null;
let reactionType="";

function event13(){
  reactionRound=0;
  nextReaction();
}

function nextReaction(){
  clearTimeout(reactionTimer);

  if(reactionRound >= 12){
    finishEvent(
      35,
      true,
      "Your reactions were lightning fast! 💨"
    );
    return;
  }

  const types =
    ["TAP","HOLD","DOUBLE TAP"];

  reactionType =
    randomItem(types);

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 13</span>
      <h2>💨 The Reaction Gauntlet</h2>

      <p>
        Round ${reactionRound+1} of 12
      </p>

      <div class="big-number">
        ${reactionType}
      </div>

      <button
        id="reactionButton"
        class="btn gold"
        ontouchstart="reactionDown(event)"
        onmousedown="reactionDown(event)"
        ontouchend="reactionUp(event)"
        onmouseup="reactionUp(event)"
        onclick="reactionTap(event)"
      >
        TAP ME
      </button>

      <div
        class="timer"
        id="reactionTimer"
      >
        1.8
      </div>
    </div>
  `;

  let remaining=1.8;

  reactionTimer =
    setInterval(()=>{
      remaining-=.1;

      const el =
        document.getElementById("reactionTimer");

      if(el){
        el.textContent =
          Math.max(0,remaining).toFixed(1);
      }

      if(remaining<=0){
        clearInterval(reactionTimer);
        reactionRound++;
        nextReaction();
      }
    },100);
}

let reactionStart=0;
let reactionClicks=0;

function reactionDown(e){
  if(reactionStart===0){
    reactionStart=Date.now();
  }
}

function reactionUp(e){}

function reactionTap(e){
  if(reactionType==="TAP"){
    clearInterval(reactionTimer);
    reactionStart=0;
    reactionRound++;
    addPoints(5);
    nextReaction();
  }
}

/* =========================================================
   EVENT 14
   HEART HUNT
   ========================================================= */

let mazePlayer=0;

const MAZE_WALLS =
  new Set([1,2,6,7,20,21,22]);

function event14(){
  mazePlayer=0;
  renderMaze();
}

function renderMaze(){
  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 14</span>
      <h2>🗺️ The Heart Hunt</h2>

      <p>
        Reach the golden heart.
        Use the buttons below.
      </p>

      <div class="maze">
        ${Array.from({length:25},(_,i)=>{
          const wall=MAZE_WALLS.has(i);

          return `
            <div
              class="maze-cell
                ${wall ? "wall" : ""}
                ${i===mazePlayer ? "player" : ""}
                ${i===24 ? "goal" : ""}"
            >
              ${
                i===mazePlayer
                ? "💗"
                : i===24
                ? "💛"
                : ""
              }
            </div>
          `;
        }).join("")}
      </div>

      <div class="grid">
        <button class="btn" onclick="mazeMove(-5)">⬆️</button>
        <button class="btn" onclick="mazeMove(5)">⬇️</button>
        <button class="btn" onclick="mazeMove(-1)">⬅️</button>
        <button class="btn" onclick="mazeMove(1)">➡️</button>
      </div>
    </div>
  `;
}

function mazeMove(direction){
  const next =
    mazePlayer + direction;

  if(next<0 || next>=25){
    return;
  }

  if(
    direction===1 &&
    Math.floor(mazePlayer/5)!==
    Math.floor(next/5)
  ){
    return;
  }

  if(
    direction===-1 &&
    Math.floor(mazePlayer/5)!==
    Math.floor(next/5)
  ){
    return;
  }

  if(MAZE_WALLS.has(next)){
    playTone(120,.08);
    return;
  }

  mazePlayer=next;

  if(mazePlayer===24){
    addPoints(40);

    finishEvent(
      40,
      true,
      "You found the heart! 🗺️💗"
    );

    return;
  }

  addPoints(3);
  renderMaze();
}

/* =========================================================
   EVENT 15
   LOVE LOCK
   ========================================================= */

let lockInput="";

function event15(){
  lockInput="";

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 15</span>
      <h2>🔐 The Love Lock</h2>

      <p>
        Crack the four-digit lock.
      </p>

      <div class="big-number" id="lockDisplay">
        ••••
      </div>

      <div class="grid">
        ${[1,2,3,4,5,6,7,8,9,0].map(n=>`
          <button
            class="btn dark"
            onclick="lockPress(${n})"
          >
            ${n}
          </button>
        `).join("")}
      </div>

      <button class="btn gold" onclick="lockSubmit()">
        🔓 Unlock
      </button>
    </div>
  `;
}

function lockPress(number){
  if(lockInput.length>=4) return;

  lockInput += number;

  document.getElementById("lockDisplay").textContent =
    "•".repeat(4-lockInput.length) +
    lockInput;
}

function lockSubmit(){
  if(lockInput==="3333"){
    finishEvent(
      50,
      true,
      "The Love Lock opened! 🔓💗"
    );
  }else{
    lockInput="";

    document.getElementById("lockDisplay").textContent =
      "••••";

    playTone(100,.2);
  }
}

/* =========================================================
   EVENT 16
   CUPID SHOOTOUT
   ========================================================= */

let cupidTimer=null;
let cupidSpawner=null;
let cupidHits=0;
let cupidMisses=0;

function event16(){
  clearInterval(cupidTimer);
  clearInterval(cupidSpawner);

  cupidHits=0;
  cupidMisses=0;

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 16</span>
      <h2>🎯 The Cupid Shootout</h2>

      <div class="stats">
        <div class="stat">
          <strong id="cupidHits">0</strong>
          <small>Hits</small>
        </div>
        <div class="stat">
          <strong id="cupidMisses">0</strong>
          <small>Misses</small>
        </div>
        <div class="stat">
          <strong id="cupidTime">20</strong>
          <small>Seconds</small>
        </div>
      </div>

      <div
        class="arena"
        id="cupidArena"
      ></div>
    </div>
  `;

  const arena =
    document.getElementById("cupidArena");

  function spawn(){
    const target =
      document.createElement("button");

    const bad =
      Math.random()<.25;

    target.className =
      "target" + (bad ? " bad":"");

    target.textContent =
      bad ? "💔" : "🎯";

    target.style.left =
      Math.random()*80+"%";

    target.style.top =
      Math.random()*72+"%";

    target.onclick=()=>{
      if(bad){
        cupidMisses++;
        addPoints(-4);
      }else{
        cupidHits++;
        addPoints(6);
      }

      target.remove();

      document.getElementById("cupidHits").textContent =
        cupidHits;

      document.getElementById("cupidMisses").textContent =
        cupidMisses;
    };

    arena.appendChild(target);

    setTimeout(()=>{
      if(target.isConnected){
        target.remove();
      }
    },1400);
  }

  let remaining=20;

  cupidSpawner =
    setInterval(spawn,750);

  cupidTimer =
    setInterval(()=>{
      remaining--;

      document.getElementById("cupidTime").textContent =
        remaining;

      if(remaining<=0){
        clearInterval(cupidTimer);
        clearInterval(cupidSpawner);

        finishEvent(
          cupidHits*2,
          cupidHits>cupidMisses,
          cupidHits>cupidMisses
            ? "Cupid approves. 🎯💗"
            : "Cupid needs better aim."
        );
      }
    },1000);
}

/* =========================================================
   EVENT 17
   COUNTDOWN
   ========================================================= */

let challenge=0;
let countdownTime=60;
let countdownInterval=null;

const COUNTDOWN_TASKS = [
  "❤️",
  "🌹",
  "⭐",
  "🐬",
  "GOLD"
];

function event17(){
  challenge=0;
  countdownTime=60;

  clearInterval(countdownInterval);

  renderCountdown();

  countdownInterval =
    setInterval(()=>{
      countdownTime--;

      const timer =
        document.getElementById("countdownTime");

      if(timer){
        timer.textContent =
          countdownTime;
      }

      if(countdownTime<=0){
        clearInterval(countdownInterval);

        finishEvent(
          challenge*2,
          challenge>=10,
          "The Countdown has ended! 🧨"
        );
      }
    },1000);
}

function renderCountdown(){
  if(challenge>=20){
    clearInterval(countdownInterval);

    finishEvent(
      50,
      true,
      "You completed every countdown challenge! 🧨"
    );

    return;
  }

  const correct =
    randomItem(COUNTDOWN_TASKS);

  const choices =
    shuffle([
      correct,
      ...shuffle(
        COUNTDOWN_TASKS.filter(x=>x!==correct)
      ).slice(0,3)
    ]);

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 17</span>
      <h2>🧨 The Countdown</h2>

      <div class="timer" id="countdownTime">
        ${countdownTime}
      </div>

      <p>
        Challenge ${challenge+1} of 20
      </p>

      <h3>Find:</h3>

      <div class="big-number">
        ${correct}
      </div>

      <div class="choices">
        ${choices.map(x=>`
          <button
            class="choice"
            onclick="countdownChoice('${escapeHTML(x)}','${escapeHTML(correct)}')"
          >
            ${escapeHTML(x)}
          </button>
        `).join("")}
      </div>
    </div>
  `;
}

window.countdownChoice =
  function(answer,correct){

    challenge++;

    if(
      normaliseAnswer(answer) ===
      normaliseAnswer(correct)
    ){
      addPoints(5);
    }

    renderCountdown();
  };

/* =========================================================
   EVENT 18
   ULTIMATE GAMBLE
   ========================================================= */

let gamblePot=100;
let gambleTurns=0;

function event18(){
  gamblePot=100;
  gambleTurns=0;
  renderGamble();
}

function renderGamble(){
  if(gambleTurns>=5){
    finishEvent(
      Math.floor(gamblePot/2),
      gamblePot>=100,
      "The Ultimate Gamble is over. 🎰"
    );
    return;
  }

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 18</span>
      <h2>🎰 The Ultimate Gamble</h2>

      <div class="big-number">
        ${gamblePot}
      </div>

      <p>
        Turn ${gambleTurns+1} of 5.
      </p>

      <button class="btn" onclick="gambleMove('safe')">
        🛡️ SAFE
      </button>

      <button class="btn gold" onclick="gambleMove('risk')">
        🎲 RISK
      </button>

      <button class="btn red" onclick="gambleMove('allin')">
        💀 ALL IN
      </button>
    </div>
  `;
}

function gambleMove(choice){
  gambleTurns++;

  const chance =
    choice==="safe"
      ? .7
      : choice==="risk"
      ? .5
      : .35;

  if(Math.random()<chance){
    const multiplier =
      choice==="safe"
        ? 1.2
        : choice==="risk"
        ? 1.7
        : 2.5;

    gamblePot =
      Math.floor(gamblePot*multiplier);

    addPoints(
      Math.floor(gamblePot/10)
    );
  }else{
    gamblePot =
      choice==="allin"
        ? 0
        : Math.floor(gamblePot/2);
  }

  renderGamble();
}

/* =========================================================
   EVENT 19
   ADMIRER'S LAST STAND
   ========================================================= */

let standTrial=0;
let standLives=3;

const STAND_OPTIONS =
  ["❤️","3","🐬","🌹","⭐"];

function event19(){
  standTrial=0;
  standLives=3;

  renderStand();
}

function renderStand(){
  if(standLives<=0){
    finishEvent(
      0,
      false,
      "The Admirer's Last Stand is over."
    );
    return;
  }

  if(standTrial>=6){
    finishEvent(
      60,
      true,
      "You survived the Admirer's Last Stand! 💀💗"
    );
    return;
  }

  const correct =
    STAND_OPTIONS[
      standTrial % STAND_OPTIONS.length
    ];

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">Event 19</span>
      <h2>💀 The Admirer's Last Stand</h2>

      <div class="stats">
        <div class="stat">
          <strong>${standLives}</strong>
          <small>Lives</small>
        </div>

        <div class="stat">
          <strong>${standTrial+1}</strong>
          <small>Trial</small>
        </div>

        <div class="stat">
          <strong>${state.score}</strong>
          <small>Score</small>
        </div>
      </div>

      <h3>
        Choose the symbol that belongs.
      </h3>

      <div class="choices">
        ${shuffle(STAND_OPTIONS).map(x=>`
          <button
            class="choice"
            onclick="standChoice('${x}','${correct}')"
          >
            ${x}
          </button>
        `).join("")}
      </div>
    </div>
  `;
}

function standChoice(answer,correct){
  if(answer===correct){
    addPoints(12);
  }else{
    standLives--;
  }

  standTrial++;
  renderStand();
}

/* =========================================================
   EVENT 20
   LULU DERBY
   ========================================================= */

/*
  IMPORTANT:
  This pool is intentionally very large.
  It contains thousands of unique arithmetic questions,
  including every multiplication fact from 1×1 through
  12×12, plus addition, subtraction and division.
*/

let derbyQuestions=[];
let derbyIndex=0;
let derbyPlayerPosition=0;
let derbyComputerPosition=0;
let derbyQuestionLocked=false;
let derbyRaceFinished=false;
let derbyCountdownTimer=null;
let derbyComputerTimer=null;
let derbyDifficulty="medium";
let derbyAnimal="🐰";

const DERBY_LENGTH=42;

const DERBY_ANIMALS = [
  "🐰",
  "🐼",
  "🐨",
  "🦊",
  "🐯",
  "🦁",
  "🐸",
  "🐵",
  "🐧",
  "🐬",
  "🦄",
  "🐝"
];

const DERBY_DIFFICULTIES = {
  easy:{
    label:"Easy",
    computerInterval:3400,
    accuracy:.55,
    moveMin:0.5,
    moveMax:1
  },

  medium:{
    label:"Medium",
    computerInterval:2700,
    accuracy:.68,
    moveMin:0.7,
    moveMax:1.2
  },

  hard:{
    label:"Hard",
    computerInterval:2150,
    accuracy:.80,
    moveMin:.9,
    moveMax:1.5
  },

  expert:{
    label:"Expert",
    computerInterval:1700,
    accuracy:.91,
    moveMin:1.1,
    moveMax:1.8
  }
};

function buildDerbyPool(){
  const pool=[];

  /*
    Addition: 10,000 unique combinations.
  */
  for(let a=0;a<=150;a++){
    for(let b=0;b<=150;b++){
      pool.push({
        q:`What is ${a} + ${b}?`,
        a:String(a+b)
      });
    }
  }

  /*
    Subtraction.
  */
  for(let a=0;a<=200;a++){
    for(let b=0;b<=100;b++){
      const high=Math.max(a,b);
      const low=Math.min(a,b);

      pool.push({
        q:`What is ${high} - ${low}?`,
        a:String(high-low)
      });
    }
  }

  /*
    Multiplication up to 12×12.
  */
  for(let a=1;a<=12;a++){
    for(let b=1;b<=12;b++){
      pool.push({
        q:`What is ${a} × ${b}?`,
        a:String(a*b)
      });
    }
  }

  /*
    Larger multiplication questions.
  */
  for(let a=1;a<=50;a++){
    for(let b=1;b<=20;b++){
      pool.push({
        q:`What is ${a} × ${b}?`,
        a:String(a*b)
      });
    }
  }

  /*
    Exact division.
  */
  for(let a=1;a<=50;a++){
    for(let b=1;b<=30;b++){
      pool.push({
        q:`What is ${a*b} ÷ ${a}?`,
        a:String(b)
      });
    }
  }

  /*
    Basic facts.
  */
  pool.push(
    ...GENERAL_QUESTIONS
  );

  return shuffle(pool);
}

const DERBY_QUESTIONS =
  buildDerbyPool();

function event20(){
  clearInterval(derbyComputerTimer);
  clearInterval(derbyCountdownTimer);

  derbyQuestions=[];
  derbyIndex=0;
  derbyPlayerPosition=0;
  derbyComputerPosition=0;
  derbyQuestionLocked=true;
  derbyRaceFinished=false;

  derbyDifficulty="medium";
  derbyAnimal="🐰";

  renderDerbySetup();
}

function renderDerbySetup(){
  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel">
      <span class="badge">Event 20</span>

      <h2>🏇 THE LULU DERBY</h2>

      <p>
        Race to the finish line by solving questions.
        Type your answer instead of choosing from multiple choice.
      </p>

      <div class="notice">
        🏁 <strong>42 spaces</strong><br>
        ⏱️ 5-second starting countdown<br>
        🧠 Every race uses a fresh set of questions<br>
        🤖 If nobody else is online, the computer races you
      </div>

      <h3>Choose your racer</h3>

      <div class="animal-grid">
        ${DERBY_ANIMALS.map(animal=>`
          <button
            class="select-card ${
              animal===derbyAnimal ? "selected" : ""
            }"
            onclick="selectDerbyAnimal('${animal}')"
          >
            <span class="animal">${animal}</span>
            Racer
          </button>
        `).join("")}
      </div>

      <h3>Computer difficulty</h3>

      <div class="difficulty-grid">
        ${Object.entries(DERBY_DIFFICULTIES).map(([key,value])=>`
          <button
            class="select-card ${
              key===derbyDifficulty ? "selected" : ""
            }"
            onclick="selectDerbyDifficulty('${key}')"
          >
            <strong>${value.label}</strong>
            <br>
            <small>
              ${
                key==="easy"
                ? "Relaxed"
                : key==="medium"
                ? "Balanced"
                : key==="hard"
                ? "Fast"
                : "Brutal"
              }
            </small>
          </button>
        `).join("")}
      </div>

      <div class="notice">
        👥 <strong>Active participants</strong><br>
        <span id="activeParticipants">
          ${escapeHTML(state.playerName || "You")}
          ${derbyAnimal}
          <br>
          🤖 Lulu Computer
        </span>
      </div>

      <button
        class="btn gold"
        onclick="startDerbyCountdown()"
      >
        🏁 START THE DERBY
      </button>
    </div>
  `;
}

function selectDerbyAnimal(animal){
  derbyAnimal=animal;
  renderDerbySetup();
}

function selectDerbyDifficulty(difficulty){
  derbyDifficulty=difficulty;
  renderDerbySetup();
}

function startDerbyCountdown(){
  derbyQuestions =
    shuffle(DERBY_QUESTIONS).slice(0,50);

  derbyIndex=0;
  derbyPlayerPosition=0;
  derbyComputerPosition=0;
  derbyRaceFinished=false;
  derbyQuestionLocked=true;

  renderDerbyCountdown(5);
}

function renderDerbyCountdown(number){
  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">THE LULU DERBY</span>

      <h2>🏁 Get Ready!</h2>

      <div class="derby-countdown">
        ${number > 0 ? number : "GO!"}
      </div>

      <p>
        ${number > 0
          ? "The race starts in..."
          : "TYPE FAST! 🏇💨"}
      </p>
    </div>
  `;

  if(number<=0){
    setTimeout(startDerby,700);
    return;
  }

  derbyCountdownTimer =
    setTimeout(()=>{
      renderDerbyCountdown(number-1);
    },1000);
}

function startDerby(){
  derbyQuestionLocked=false;

  renderDerby();

  const difficulty =
    DERBY_DIFFICULTIES[derbyDifficulty];

  derbyComputerTimer =
    setInterval(()=>{
      if(derbyRaceFinished) return;

      const accurate =
        Math.random() <
        difficulty.accuracy;

      if(accurate){
        const movement =
          difficulty.moveMin +
          Math.random() *
          (difficulty.moveMax -
           difficulty.moveMin);

        derbyComputerPosition += movement;
      }

      if(
        derbyComputerPosition >= DERBY_LENGTH
      ){
        derbyComputerPosition =
          DERBY_LENGTH;

        finishDerby(false);
      }

      renderDerbyTrackOnly();

    },difficulty.computerInterval);
}

function renderDerby(){
  if(derbyRaceFinished) return;

  const question =
    derbyQuestions[derbyIndex];

  if(!question){
    finishDerby(
      derbyPlayerPosition >
      derbyComputerPosition
    );
    return;
  }

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel">
      <span class="badge">Event 20</span>

      <h2>🏇 THE LULU DERBY</h2>

      <div id="derbyTrackArea">
        ${derbyTrackHTML()}
      </div>

      <div class="derby-question">
        <p>
          Question ${derbyIndex+1} of 50
        </p>

        <h3>
          ${escapeHTML(question.q)}
        </h3>

        <div class="derby-answer">
          <input
            id="derbyAnswer"
            autocomplete="off"
            inputmode="text"
            placeholder="Type your answer..."
            onkeydown="
              if(event.key==='Enter'){
                submitDerbyAnswer();
              }
            "
          >

          <button
            class="btn gold"
            onclick="submitDerbyAnswer()"
          >
            SUBMIT
          </button>
        </div>

        <div
          class="derby-status"
          id="derbyStatus"
        >
          ${derbyQuestionLocked
            ? "Question locked"
            : "Answer before your opponent catches you!"}
        </div>
      </div>
    </div>
  `;

  const input =
    document.getElementById("derbyAnswer");

  if(input){
    input.focus();
  }
}

function derbyTrackHTML(){
  const playerPercent =
    Math.min(
      94,
      derbyPlayerPosition /
      DERBY_LENGTH * 94
    );

  const computerPercent =
    Math.min(
      94,
      derbyComputerPosition /
      DERBY_LENGTH * 94
    );

  return `
    <div class="derby-track">

      <div class="race-lane">
        <div class="lane-name">
          ${escapeHTML(state.playerName || "You")}
        </div>

        <div class="race-road">
          <div
            class="racer"
            style="left:${playerPercent}%"
          >
            ${derbyAnimal}

            <span class="racer-name">
              You
            </span>
          </div>
        </div>

        <div class="finish-line"></div>
      </div>

      <div class="race-lane">
        <div class="lane-name">
          Lulu Computer
        </div>

        <div class="race-road">
          <div
            class="racer"
            style="left:${computerPercent}%"
          >
            🤖

            <span class="racer-name">
              Computer
            </span>
          </div>
        </div>

        <div class="finish-line"></div>
      </div>

      <div class="derby-distance">
        YOU:
        ${Math.floor(derbyPlayerPosition)}
        / ${DERBY_LENGTH}
        &nbsp; • &nbsp;
        COMPUTER:
        ${Math.floor(derbyComputerPosition)}
        / ${DERBY_LENGTH}
      </div>
    </div>
  `;
}

function renderDerbyTrackOnly(){
  const area =
    document.getElementById("derbyTrackArea");

  if(area){
    area.innerHTML =
      derbyTrackHTML();
  }
}

function submitDerbyAnswer(){
  if(derbyQuestionLocked ||
     derbyRaceFinished){
    return;
  }

  const input =
    document.getElementById("derbyAnswer");

  const status =
    document.getElementById("derbyStatus");

  if(!input) return;

  const answer =
    normaliseAnswer(input.value);

  if(!answer){
    return;
  }

  derbyQuestionLocked=true;

  const correct =
    normaliseAnswer(
      derbyQuestions[derbyIndex].a
    );

  if(answer===correct){
    /*
      Correct answers move the player's racer.
      The race is deliberately long.
    */
    const movement =
      1.5 + Math.random()*1.2;

    derbyPlayerPosition += movement;

    addPoints(30);

    playTone(800,.08);

    if(status){
      status.textContent =
        "✅ Correct! Your racer moves forward!";
      status.style.color =
        "var(--green)";
    }
  }else{
    /*
      Wrong answers do not move the player.
    */
    addPoints(-5);

    playTone(150,.08);

    if(status){
      status.textContent =
        "❌ Wrong answer! Keep racing!";
      status.style.color =
        "var(--red)";
    }
  }

  if(
    derbyPlayerPosition >= DERBY_LENGTH
  ){
    derbyPlayerPosition =
      DERBY_LENGTH;

    finishDerby(true);
    return;
  }

  derbyIndex++;

  setTimeout(()=>{
    if(!derbyRaceFinished){
      derbyQuestionLocked=false;
      renderDerby();
    }
  },500);
}

function finishDerby(playerWon){
  if(derbyRaceFinished) return;

  derbyRaceFinished=true;

  clearInterval(derbyComputerTimer);
  clearInterval(derbyCountdownTimer);

  if(playerWon){
    addPoints(300);
  }else{
    addPoints(75);
  }

  const playerDistance =
    Math.floor(derbyPlayerPosition);

  const computerDistance =
    Math.floor(derbyComputerPosition);

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">
      <span class="badge">
        THE LULU DERBY
      </span>

      <h2>
        ${playerWon
          ? "🏆 YOU WON!"
          : "🏁 RACE OVER"}
      </h2>

      <div class="derby-result">
        <div class="result-icon">
          ${playerWon ? derbyAnimal : "🏇"}
        </div>

        <h3>
          ${
            playerWon
            ? "Your racer crossed the finish line first!"
            : "The computer reached the finish line first."
          }
        </h3>

        <p>
          Your distance:
          <strong>${playerDistance}</strong>
          /
          ${DERBY_LENGTH}
        </p>

        <p>
          Computer:
          <strong>${computerDistance}</strong>
          /
          ${DERBY_LENGTH}
        </p>

        <div class="result-points">
          +${playerWon ? 300 : 75}
        </div>

        <p>
          ${playerWon
            ? "🏆 Derby winner bonus"
            : "🏁 Finisher bonus"}
        </p>
      </div>

      <button
        class="btn gold"
        onclick="continueToFinalChallenge()"
      >
        👑 Continue to Final Challenge
      </button>
    </div>
  `;
}

/* =========================================================
   EVENT 21
   FINAL CHALLENGE
   ========================================================= */

const FINAL_QUIZ = [
  {
    q:"What colour does Liliana love?",
    correct:"Baby pink",
    options:[
      "Baby pink",
      "Burgundy",
      "Purple",
      "Green"
    ]
  },

  {
    q:"What is Liliana's favourite number?",
    correct:"3",
    options:[
      "3",
      "7",
      "9",
      "22"
    ]
  },

  {
    q:"What is Liliana's birthday?",
    correct:"July 22",
    options:[
      "July 22",
      "June 22",
      "July 12",
      "August 22"
    ]
  },

  {
    q:"What animal does Liliana like?",
    correct:"Dolphins",
    options:[
      "Dolphins",
      "Otters",
      "Wolves",
      "Penguins"
    ]
  },

  {
    q:"What food does Liliana like?",
    correct:"Sushi",
    options:[
      "Sushi",
      "Pizza",
      "Tacos",
      "Pasta"
    ]
  },

  {
    q:"What did Liliana study at university?",
    correct:"Psychology",
    options:[
      "Psychology",
      "Law",
      "Medicine",
      "Engineering"
    ]
  },

  {
    q:"What colour are Liliana's eyes?",
    correct:"Green",
    options:[
      "Green",
      "Blue",
      "Brown",
      "Hazel"
    ]
  },

  {
    q:"How many siblings does Liliana have?",
    correct:"5",
    options:[
      "5",
      "3",
      "7",
      "4"
    ]
  },

  {
    q:"How many nieces does Liliana have?",
    correct:"1",
    options:[
      "1",
      "2",
      "3",
      "4"
    ]
  },

  {
    q:"How many nephews does Liliana have?",
    correct:"4",
    options:[
      "4",
      "2",
      "3",
      "5"
    ]
  },

  {
    q:"How many dogs does Liliana have?",
    correct:"2",
    options:[
      "2",
      "1",
      "3",
      "4"
    ]
  },

  {
    q:"What is one of Liliana's dogs called?",
    correct:"Arlo",
    options:[
      "Arlo",
      "Ayla",
      "Lola",
      "Aylaa"
    ]
  },

  {
    q:"What is her other dog's name?",
    correct:"Aayla",
    options:[
      "Aayla",
      "Aria",
      "Ayla",
      "Lulu"
    ]
  },

  {
    q:"What movie does Liliana love?",
    correct:"Me Before You",
    options:[
      "Me Before You",
      "Titanic",
      "The Notebook",
      "Frozen"
    ]
  },

  {
    q:"What is Liliana afraid of?",
    correct:"Drowning",
    options:[
      "Drowning",
      "Flying",
      "Spiders",
      "Thunder"
    ]
  },

  {
    q:"What season does Liliana like?",
    correct:"Autumn",
    options:[
      "Autumn",
      "Summer",
      "Winter",
      "Spring"
    ]
  },

  {
    q:"What holiday does Liliana like?",
    correct:"Christmas",
    options:[
      "Christmas",
      "Halloween",
      "Easter",
      "Valentine's Day"
    ]
  },

  {
    q:"Does Liliana like gambling?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "Only poker",
      "Only occasionally"
    ]
  },

  {
    q:"What does Liliana want someday?",
    correct:"A family",
    options:[
      "A family",
      "A spaceship",
      "A mansion",
      "A racehorse"
    ]
  },

  {
    q:"Does Liliana like concerts?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "Only classical concerts",
      "Only festivals"
    ]
  },

  {
    q:"Does Liliana like sad songs and poetry?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "Only poetry",
      "Only sad songs"
    ]
  },

  {
    q:"Does Liliana like rain and snow?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "Only rain",
      "Only snow"
    ]
  },

  {
    q:"What star sign is Liliana?",
    correct:"Leo",
    options:[
      "Leo",
      "Cancer",
      "Virgo",
      "Gemini"
    ]
  },

  {
    q:"Does Liliana like roses?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "Only red roses",
      "Only white roses"
    ]
  },

  {
    q:"Does Liliana like sunflowers?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "Only small ones",
      "Only yellow ones"
    ]
  },

  {
    q:"Does Liliana like sushi?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "Only cooked sushi",
      "Only sashimi"
    ]
  },

  {
    q:"Does Liliana want to be a mum someday?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "She has never wanted children",
      "Only much later"
    ]
  },

  {
    q:"Does Liliana like dolphins?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "Only whales",
      "Only seals"
    ]
  },

  {
    q:"Does Liliana like the number 3?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "She prefers 7",
      "She prefers 22"
    ]
  },

  {
    q:"Does Liliana like poker or gambling?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "Only board games",
      "Only video games"
    ]
  },

  {
    q:"Does Liliana like R&B?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "Only rock",
      "Only country"
    ]
  },

  {
    q:"Does Liliana like Twitter?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "She only uses Facebook",
      "She only uses Instagram"
    ]
  },

  {
    q:"Does Liliana like Mum's house?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "Only during Christmas",
      "Only during summer"
    ]
  },

  {
    q:"Does Liliana like the colour baby pink?",
    correct:"Yes",
    options:[
      "Yes",
      "No",
      "Only dark pink",
      "Only burgundy"
    ]
  },

  {
    q:"Does Liliana like Tits or Ass?",
    correct:"Tits",
    options:[
      "Tits",
      "Ass",
      "Neither",
      "Both"
    ]
  }
];

let finalQuestion=0;
let finalCorrect=0;
let finalAnswers=[];

function event21(){
  finalQuestion=0;
  finalCorrect=0;

  /*
    Shuffle the QUESTIONS themselves so every run can
    feel different.
  */
  finalAnswers =
    shuffle(FINAL_QUIZ);

  renderFinalQuestion();
}

function renderFinalQuestion(){
  if(finalQuestion >= finalAnswers.length){
    finalWritten();
    return;
  }

  const item =
    finalAnswers[finalQuestion];

  /*
    THIS IS THE IMPORTANT FIX:
    The correct answer is shuffled with the
    other answers every single question.
  */
  const choices =
    shuffle(item.options);

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel">
      <span class="badge">Event 21</span>

      <h2>👑 THE FINAL CHALLENGE</h2>

      ${stats()}

      <div class="progress">
        <div
          class="progress-bar"
          style="width:${
            finalQuestion /
            finalAnswers.length *
            100
          }%"
        ></div>
      </div>

      <p>
        Final Question
        ${finalQuestion+1}
        of
        ${finalAnswers.length}
      </p>

      <h3>
        ${escapeHTML(item.q)}
      </h3>

      <div class="choices">
        ${choices.map(choice=>`
          <button
            class="choice"
            onclick="finalAnswer(this,'${escapeHTML(choice)}','${escapeHTML(item.correct)}')"
          >
            ${escapeHTML(choice)}
          </button>
        `).join("")}
      </div>
    </div>
  `;
}

function finalAnswer(button,answer,correct){
  const buttons =
    document.querySelectorAll(".choice");

  buttons.forEach(x=>x.disabled=true);

  if(
    normaliseAnswer(answer) ===
    normaliseAnswer(correct)
  ){
    button.classList.add("correct");

    finalCorrect++;

    /*
      Large enough scoring potential to make the
      3001+ private-call requirement genuinely achievable.
    */
    addPoints(25);

    playTone(800,.08);
  }else{
    button.classList.add("wrong");

    addPoints(-5);

    playTone(150,.08);
  }

  finalQuestion++;

  setTimeout(
    renderFinalQuestion,
    350
  );
}

function finalWritten(){
  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel">
      <span class="badge">Final Question</span>

      <h2>💌 One Last Question</h2>

      <p>
        In your own words:
        <strong>Why should Liliana choose you?</strong>
      </p>

      <textarea
        id="finalWrittenAnswer"
        maxlength="1500"
        placeholder="Tell Liliana why..."
      ></textarea>

      <button
        class="btn gold"
        onclick="submitFinalWritten()"
      >
        👑 Submit Final Answer
      </button>
    </div>
  `;
}

function submitFinalWritten(){
  const answer =
    document
      .getElementById("finalWrittenAnswer")
      .value
      .trim();

  if(answer.length < 10){
    alert(
      "Your answer needs to be at least 10 characters."
    );
    return;
  }

  addPoints(150);

  state.finished=true;
  saveGame();

  finalResult();
}

/* =========================================================
   FINAL RESULT
   ========================================================= */

function finalResult(){
  const score =
    state.score;

  let title;
  let message;
  let trophy;

  if(score >= 3001){
    trophy="👑";
    title="LULU LEGEND";
    message=
      "You reached the ultimate score and unlocked the private Lulu call.";
  }else if(score >= 2500){
    trophy="🏆";
    title="ABSOLUTE CHAMPION";
    message=
      "That was an incredible run.";
  }else if(score >= 1800){
    trophy="💎";
    title="ELITE ADMIRER";
    message=
      "You made it through the Express in style.";
  }else if(score >= 1000){
    trophy="💗";
    title="DEDICATED ADMIRER";
    message=
      "You gave it everything.";
  }else{
    trophy="🌹";
    title="SURVIVOR";
    message=
      "You made it to the end of the Lulu Express.";
  }

  const privateCall =
    score > 3000;

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel final-box center">

      <div class="trophy">
        ${trophy}
      </div>

      <span class="badge">
        Journey Complete
      </span>

      <h1>
        ${title}
      </h1>

      <p>
        ${message}
      </p>

      <div class="result-points">
        ${score}
      </div>

      <p>
        Final Score
      </p>

      <div class="stats">
        <div class="stat">
          <strong>${finalCorrect}</strong>
          <small>Final Quiz Correct</small>
        </div>

        <div class="stat">
          <strong>${score}</strong>
          <small>Total Points</small>
        </div>

        <div class="stat">
          <strong>21</strong>
          <small>Events</small>
        </div>
      </div>

      ${
        privateCall
        ?
        `
          <div class="unlock">
            <h2>📞💗 PRIVATE LULU CALL UNLOCKED</h2>

            <p>
              You scored <strong>${score}</strong>.
              The requirement was <strong>3,001+</strong>.
            </p>

            <button
              class="btn gold"
              onclick="privateCallScreen()"
            >
              📞 Claim Private Call
            </button>
          </div>
        `
        :
        `
          <div class="notice">
            🔒 Private Lulu Call locked.<br><br>

            You needed <strong>3,001+</strong> points.
            <br>
            Your score:
            <strong>${score}</strong>
          </div>
        `
      }

      <button
        class="btn dark"
        onclick="resetJourney()"
      >
        🚂 Start Again
      </button>
    </div>
  `;
}

function privateCallScreen(){
  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel final-box center">

      <div class="trophy">
        📞💗
      </div>

      <span class="badge">
        PRIVATE REWARD
      </span>

      <h1>
        Lulu Call Unlocked
      </h1>

      <p>
        You did it.
      </p>

      <p>
        You scored
        <strong>${state.score}</strong>
        points, which is above the required
        <strong>3,000</strong>.
      </p>

      <div class="unlock">
        <h3>
          💗 Private call with Lulu
        </h3>

        <p>
          This is your final reward for completing
          the Lulu Express.
        </p>
      </div>

      <button
        class="btn gold"
        onclick="finalResult()"
      >
        Back to Results
      </button>
    </div>
  `;
}

/* =========================================================
   INITIALISE
   ========================================================= */

loadGame();

/*
  When an existing save is loaded, preserve its event
  starting score rather than resetting it every time
  render() is called.
*/
eventStartScore = state.score;

if(state.finished){
  finalResult();
}else if(
  state.score > 0 ||
  state.currentEvent > 0
){
  render();
}else{
  home();
}

</script>

</body>
</html>

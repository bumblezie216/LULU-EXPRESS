<html lang="en">
<head>
<meta charset="UTF-8">

<!-- IMPORTANT MOBILE FIXES -->
<meta name="viewport"
content="width=device-width,
initial-scale=1,
maximum-scale=1,
minimum-scale=1,
user-scalable=no,
viewport-fit=cover">

<meta name="theme-color" content="#160910">

<title>Lulu Express 🚂💗</title>

<style>
*{
  box-sizing:border-box;
  -webkit-tap-highlight-color:transparent;
}

html,
body{
  margin:0;
  padding:0;
  width:100%;
  height:100%;
  overflow:hidden;
  background:#160910;
  color:#fff;
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Arial,sans-serif;
  -webkit-text-size-adjust:100%;
  touch-action:manipulation;
  overscroll-behavior:none;
}

body{
  min-height:100svh;
}

button,
input{
  font:inherit;
}

button{
  min-height:48px;
  border:0;
  cursor:pointer;
  user-select:none;
  -webkit-user-select:none;
  touch-action:manipulation;
}

input{
  font-size:16px !important;
}

button:active{
  transform:scale(.97);
}

.screen{
  position:absolute;
  inset:0;
  width:100%;
  height:100svh;
  min-height:100svh;
  display:none;
  flex-direction:column;
  overflow:hidden;
  background:
    radial-gradient(circle at 50% 0%,rgba(255,105,170,.15),transparent 38%),
    linear-gradient(145deg,#160910,#28101e 50%,#11070d);
}

.screen.active{
  display:flex;
}

.scroll-screen{
  overflow-y:auto;
  overflow-x:hidden;
  -webkit-overflow-scrolling:touch;
  touch-action:pan-y;
}

.logo{
  font-size:clamp(28px,8vw,48px);
  font-weight:900;
  letter-spacing:-1px;
  text-align:center;
  margin:0;
}

.subtitle{
  text-align:center;
  opacity:.75;
  margin:8px auto 0;
  max-width:650px;
  line-height:1.5;
}

.topbar{
  flex:0 0 auto;
  padding:
    max(14px,env(safe-area-inset-top))
    16px
    12px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:10px;
  z-index:10;
}

.brand{
  font-weight:900;
  font-size:18px;
}

.hud{
  display:flex;
  gap:7px;
  flex-wrap:wrap;
  justify-content:flex-end;
}

.pill{
  background:rgba(255,255,255,.08);
  border:1px solid rgba(255,255,255,.12);
  padding:8px 11px;
  border-radius:999px;
  font-size:13px;
}

.menu-content{
  width:min(700px,92vw);
  margin:auto;
  padding:20px 0 40px;
  text-align:center;
}

.main-buttons{
  display:grid;
  gap:12px;
  margin-top:25px;
}

.primary{
  background:linear-gradient(135deg,#ff5fa2,#d92f78);
  color:#fff;
  border-radius:16px;
  padding:14px 20px;
  font-weight:800;
  box-shadow:0 8px 25px rgba(255,55,140,.18);
}

.secondary{
  background:rgba(255,255,255,.09);
  color:#fff;
  border:1px solid rgba(255,255,255,.15);
  border-radius:16px;
  padding:14px 20px;
  font-weight:700;
}

.danger{
  background:#5d172c;
  color:#fff;
  border-radius:16px;
  padding:14px 20px;
}

.name-box{
  width:100%;
  margin-top:20px;
  padding:16px;
  background:rgba(0,0,0,.25);
  border:1px solid rgba(255,255,255,.12);
  border-radius:18px;
  color:#fff;
  outline:none;
}

.name-box:focus{
  border-color:#ff71ac;
}

.music-btn{
  background:rgba(255,255,255,.08);
  color:#fff;
  border:1px solid rgba(255,255,255,.13);
  border-radius:12px;
  padding:9px 12px;
  min-height:44px;
}

.journey{
  width:min(900px,94vw);
  margin:10px auto 30px;
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:10px;
}

.level{
  min-height:100px;
  border-radius:18px;
  padding:12px;
  background:rgba(255,255,255,.07);
  border:1px solid rgba(255,255,255,.1);
  text-align:left;
  position:relative;
}

.level.locked{
  opacity:.4;
}

.level.done{
  border-color:#ff6fac;
  background:rgba(255,72,145,.13);
}

.level.current{
  box-shadow:0 0 0 2px rgba(255,112,174,.35);
}

.level-num{
  font-size:12px;
  opacity:.55;
}

.level-title{
  font-weight:800;
  margin-top:5px;
  line-height:1.2;
}

.level-status{
  font-size:11px;
  opacity:.65;
  margin-top:7px;
}

.game-top{
  flex:0 0 auto;
  padding:
    max(8px,env(safe-area-inset-top))
    14px
    5px;
  text-align:center;
}

.game-title{
  font-size:clamp(21px,6vw,32px);
  margin:0;
  font-weight:900;
}

.game-sub{
  margin:4px auto 0;
  font-size:13px;
  opacity:.7;
}

.game-wrap{
  width:min(720px,94vw);
  flex:1;
  min-height:0;
  margin:0 auto;
  display:flex;
  flex-direction:column;
  padding:6px 0 max(8px,env(safe-area-inset-bottom));
}

.game-card{
  background:rgba(255,255,255,.055);
  border:1px solid rgba(255,255,255,.1);
  border-radius:20px;
  padding:14px;
  flex:1;
  min-height:0;
  overflow:hidden;
}

.game-scroll{
  overflow-y:auto;
  overflow-x:hidden;
  -webkit-overflow-scrolling:touch;
  touch-action:pan-y;
}

.game-actions{
  display:flex;
  gap:10px;
  flex-wrap:wrap;
  justify-content:center;
  margin-top:10px;
}

.statline{
  display:flex;
  justify-content:center;
  gap:12px;
  flex-wrap:wrap;
  font-size:13px;
  margin-bottom:8px;
}

.big{
  font-size:30px;
  font-weight:900;
}

.choice-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
}

.choice{
  min-height:62px;
  background:rgba(255,255,255,.09);
  color:#fff;
  border:1px solid rgba(255,255,255,.12);
  border-radius:14px;
  padding:10px;
  font-weight:700;
  text-align:left;
}

.choice.correct{
  background:rgba(54,200,120,.25);
  border-color:#52e29b;
}

.choice.wrong{
  background:rgba(255,50,90,.22);
}

.message{
  text-align:center;
  min-height:25px;
  margin:8px 0;
  font-weight:700;
}

.win-panel{
  display:none;
  height:100%;
  align-items:center;
  justify-content:center;
  text-align:center;
  flex-direction:column;
  gap:14px;
}

.win-panel.show{
  display:flex;
}

.play-area.hidden{
  display:none;
}

/* =========================================================
   GAME 1 — BROKEN HEARTS
   Designed specifically for small phone screens.
   ========================================================= */

#game1 .game-wrap{
  width:min(430px,94vw);
  padding-bottom:max(8px,env(safe-area-inset-bottom));
}

#game1 .game-card{
  padding:8px;
  display:flex;
  flex-direction:column;
}

.heart-stats{
  flex:0 0 auto;
  display:flex;
  justify-content:space-around;
  font-size:13px;
  padding:3px 0 6px;
}

.heart-board{
  position:relative;
  width:100%;
  flex:1;
  min-height:0;
  overflow:hidden;
  border-radius:18px;
  background:
    radial-gradient(circle at 50% 20%,rgba(255,100,180,.16),transparent 40%),
    linear-gradient(#180c1b,#0d0710);
  border:1px solid rgba(255,255,255,.1);
  touch-action:none;
}

.falling-heart{
  position:absolute;
  line-height:1;
  user-select:none;
  pointer-events:none;
  filter:drop-shadow(0 4px 7px rgba(0,0,0,.35));
}

.catcher{
  position:absolute;
  bottom:7px;
  left:50%;
  transform:translateX(-50%);
  width:27%;
  min-width:72px;
  max-width:115px;
  height:34px;
  border-radius:18px 18px 10px 10px;
  background:linear-gradient(135deg,#ff73b1,#d9367c);
  border:2px solid rgba(255,255,255,.7);
  box-shadow:0 5px 16px rgba(255,60,140,.3);
  pointer-events:none;
}

.catch-controls{
  flex:0 0 auto;
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
  padding:8px 0 0;
}

.move-btn{
  height:54px;
  min-height:54px;
  border-radius:16px;
  background:rgba(255,255,255,.1);
  color:#fff;
  border:1px solid rgba(255,255,255,.16);
  font-size:24px;
  font-weight:900;
  touch-action:none !important;
  -webkit-touch-callout:none;
}

.move-btn:active,
.move-btn.held{
  background:rgba(255,91,160,.3);
}

.life{
  color:#ff668f;
}

/* =========================================================
   MEMORY
   ========================================================= */

.memory-grid{
  width:min(360px,82vw);
  margin:15px auto;
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:8px;
}

.memory-tile{
  aspect-ratio:1;
  border-radius:13px;
  background:#351427;
  border:2px solid rgba(255,255,255,.1);
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:24px;
  transition:.15s;
}

.memory-tile.lit{
  background:#e74b91;
  transform:scale(.96);
}

/* =========================================================
   SLOT
   ========================================================= */

.reels{
  display:flex;
  justify-content:center;
  gap:9px;
  margin:25px 0;
}

.reel{
  width:80px;
  height:90px;
  display:flex;
  justify-content:center;
  align-items:center;
  font-size:44px;
  background:#09060a;
  border:2px solid #71324d;
  border-radius:15px;
}

/* =========================================================
   RACE
   ========================================================= */

.race-meter{
  position:relative;
  height:45px;
  border-radius:22px;
  background:#26131e;
  overflow:hidden;
  margin:25px 0 12px;
}

.perfect-zone{
  position:absolute;
  left:40%;
  width:20%;
  top:0;
  bottom:0;
  background:rgba(93,224,160,.28);
  border-left:2px solid #5de0a0;
  border-right:2px solid #5de0a0;
}

.race-marker{
  position:absolute;
  width:7px;
  top:3px;
  bottom:3px;
  border-radius:5px;
  background:#fff;
  left:0;
}

/* =========================================================
   BOXING
   ========================================================= */

.hpbar{
  height:18px;
  background:#12080d;
  border-radius:10px;
  overflow:hidden;
  margin:8px 0 15px;
}

.hpfill{
  height:100%;
  width:100%;
  background:#f04c82;
  transition:.25s;
}

.fight-buttons{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:9px;
}

/* =========================================================
   MATCH
   ========================================================= */

.match-board{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:14px;
  margin-top:12px;
}

.match-side{
  display:grid;
  gap:8px;
}

.match-item{
  padding:14px;
  min-height:55px;
  border-radius:13px;
  background:rgba(255,255,255,.09);
  border:1px solid rgba(255,255,255,.1);
  text-align:center;
  font-size:24px;
  touch-action:none;
}

.match-target{
  min-height:55px;
  border:2px dashed rgba(255,255,255,.3);
  border-radius:13px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:24px;
}

/* =========================================================
   REACTION
   ========================================================= */

.reaction-button{
  width:min(330px,80vw);
  height:180px;
  margin:20px auto;
  display:flex;
  align-items:center;
  justify-content:center;
  border-radius:30px;
  background:#432034;
  font-size:28px;
  font-weight:900;
}

/* =========================================================
   HEART HUNT
   ========================================================= */

.hunt-area{
  position:relative;
  height:min(55vh,420px);
  border-radius:18px;
  background:
    radial-gradient(circle,#392033 1px,transparent 1px);
  background-size:22px 22px;
  overflow:hidden;
}

.hunt-heart{
  position:absolute;
  font-size:25px;
  padding:5px;
  background:transparent;
}

/* =========================================================
   LOCK
   ========================================================= */

.lock-display{
  text-align:center;
  font-size:32px;
  letter-spacing:8px;
  margin:15px;
  min-height:45px;
}

.keypad{
  width:min(300px,85vw);
  margin:auto;
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:8px;
}

.key{
  min-height:58px;
  border-radius:13px;
  background:rgba(255,255,255,.09);
  color:#fff;
}

/* =========================================================
   SHOOTOUT
   ========================================================= */

.shoot-area{
  position:relative;
  height:min(58vh,440px);
  border-radius:18px;
  overflow:hidden;
  background:#120914;
  border:1px solid rgba(255,255,255,.1);
  touch-action:none;
}

.shoot-target{
  position:absolute;
  font-size:30px;
  padding:7px;
}

/* =========================================================
   COUNTDOWN
   ========================================================= */

.mini-bar{
  height:40px;
  background:#12080d;
  border-radius:20px;
  overflow:hidden;
  margin:20px 0;
  position:relative;
}

.mini-zone{
  position:absolute;
  left:42%;
  width:16%;
  top:0;
  bottom:0;
  background:#5de0a0;
  opacity:.45;
}

.mini-pointer{
  position:absolute;
  width:6px;
  top:0;
  bottom:0;
  background:#fff;
}

/* =========================================================
   WORD FIND
   ========================================================= */

.word-grid{
  display:grid;
  grid-template-columns:repeat(14,1fr);
  gap:2px;
  width:min(430px,94vw);
  margin:auto;
  touch-action:none;
  user-select:none;
}

.word-letter{
  aspect-ratio:1;
  display:flex;
  align-items:center;
  justify-content:center;
  background:#29131f;
  border-radius:4px;
  font-size:clamp(10px,3.2vw,16px);
  font-weight:800;
}

.word-letter.selected{
  background:#7b3157;
}

.word-letter.found{
  background:#d94686;
}

.words-list{
  display:flex;
  flex-wrap:wrap;
  gap:5px;
  justify-content:center;
  margin-top:8px;
  max-height:80px;
  overflow:auto;
}

.word-tag{
  padding:4px 7px;
  border-radius:7px;
  background:rgba(255,255,255,.08);
  font-size:10px;
}

.word-tag.found{
  text-decoration:line-through;
  opacity:.45;
}

/* =========================================================
   DRAW
   ========================================================= */

#drawCanvas{
  width:100%;
  height:min(50vh,400px);
  background:#fffafc;
  border-radius:15px;
  touch-action:none;
  display:block;
}

.draw-tools{
  display:flex;
  gap:6px;
  flex-wrap:wrap;
  justify-content:center;
  margin:7px 0;
}

.draw-tools button{
  min-width:48px;
  min-height:44px;
  border-radius:10px;
}

/* =========================================================
   DERBY
   ========================================================= */

.horse-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
}

.horse{
  padding:15px 10px;
  border-radius:16px;
  background:rgba(255,255,255,.08);
  color:#fff;
  border:2px solid transparent;
}

.horse.selected{
  border-color:#ff6ba8;
  background:rgba(255,79,151,.15);
}

.track{
  display:grid;
  gap:9px;
  margin:12px 0;
}

.track-row{
  display:grid;
  grid-template-columns:70px 1fr;
  align-items:center;
  gap:7px;
}

.track-line{
  height:24px;
  border-radius:15px;
  background:#160b11;
  overflow:hidden;
}

.horse-run{
  height:100%;
  width:0;
  background:#e95895;
  border-radius:15px;
  transition:.3s;
}

/* =========================================================
   GENERAL
   ========================================================= */

.progress{
  height:7px;
  background:rgba(255,255,255,.08);
  border-radius:5px;
  overflow:hidden;
  margin:8px 0 12px;
}

.progress > div{
  height:100%;
  background:#f45b9b;
  width:0;
}

.small{
  font-size:12px;
  opacity:.65;
}

.center{
  text-align:center;
}

.notice{
  padding:10px;
  background:rgba(255,255,255,.06);
  border-radius:12px;
  line-height:1.45;
  font-size:13px;
}

@media(max-width:500px){
  .journey{
    grid-template-columns:repeat(2,1fr);
  }

  .game-card{
    border-radius:17px;
  }

  .choice-grid{
    gap:7px;
  }

  .choice{
    min-height:58px;
    font-size:13px;
  }
}

@media(max-height:700px){
  .game-top{
    padding-top:max(5px,env(safe-area-inset-top));
  }

  .game-title{
    font-size:21px;
  }

  .game-sub{
    font-size:11px;
  }

  .heart-stats{
    padding-bottom:3px;
  }

  .catch-controls{
    padding-top:5px;
  }

  .move-btn{
    height:48px;
    min-height:48px;
  }
}
</style>
</head>

<body>

<!-- =========================================================
     HOME
     ========================================================= -->

<section id="home" class="screen active scroll-screen">

  <div class="topbar">
    <div class="brand">Lulu Express 🚂💗</div>

    <div class="hud">
      <div class="pill">⭐ <span id="homeScore">0</span></div>
      <div class="pill">🪙 <span id="homeTokens">0</span></div>
      <button id="musicButton" class="music-btn">♫ Music: OFF</button>
    </div>
  </div>

  <div class="menu-content">

    <div style="font-size:55px">🚂💗</div>

    <h1 class="logo">Lulu Express</h1>

    <p class="subtitle">
      A 23-level journey made especially for Liliana.
      Pass each challenge to unlock the next one.
    </p>

    <div id="welcomeBox">
      <input
        id="playerName"
        class="name-box"
        maxlength="24"
        placeholder="Enter your name"
        autocomplete="off"
      >

      <div class="main-buttons">
        <button class="primary" onclick="beginJourney()">
          🚂 Start the Journey
        </button>
      </div>
    </div>

    <div id="journeyBox" style="display:none">

      <div class="notice" style="margin-top:20px">
        Welcome, <b id="welcomeName"></b> 💗<br>
        Complete a level to unlock the next one.
      </div>

      <div class="main-buttons">
        <button class="primary" onclick="continueJourney()">
          Continue Journey →
        </button>

        <button class="secondary" onclick="showScreen('home');renderJourney()">
          View Journey
        </button>

        <button class="danger" onclick="resetEverything()">
          Reset Journey
        </button>
      </div>

      <h2 style="margin-top:28px">Your Journey</h2>

      <div id="journey" class="journey"></div>

    </div>

  </div>
</section>

<!-- =========================================================
     GENERIC GAME SCREENS
     ========================================================= -->

<div id="gameScreens"></div>

<script>
/* =========================================================
   CORE STATE
   ========================================================= */

const STORAGE_KEY = "luluExpress23_mobile_v3";

const levels = [
  ["💔","Broken Hearts"],
  ["🧠","Memory Vault"],
  ["⏱️","Pressure Quiz"],
  ["🎰","High Roller"],
  ["🧩","Mind Games"],
  ["🃏","The Bluff"],
  ["🛡️","Survival Round"],
  ["🏇","The Admirer Race"],
  ["🔎","Heartbreak Chamber"],
  ["🥊","Heartbreak Boxing"],
  ["🧲","Perfect Match"],
  ["💗","Who Knows Liliana Best?"],
  ["⚡","Reaction Gauntlet"],
  ["💘","Heart Hunt"],
  ["🔐","Love Lock"],
  ["🏹","Cupid Shootout"],
  ["⏳","The Countdown"],
  ["🎲","Ultimate Gamble"],
  ["👑","Admirer's Last Stand"],
  ["🔎","Liliana's Word Find"],
  ["🌻","Draw a Sunflower"],
  ["🏇","THE LULU DERBY"],
  ["💕","THE FINAL CHALLENGE"]
];

let state = {
  name:"",
  score:0,
  tokens:0,
  completed:[],
  music:false
};

let timers = [];
let animationFrames = [];
let cleanupFns = [];

function loadState(){
  try{
    const saved=JSON.parse(localStorage.getItem(STORAGE_KEY));
    if(saved){
      state={...state,...saved};
    }
  }catch(e){}
}

function saveState(){
  localStorage.setItem(STORAGE_KEY,JSON.stringify(state));
  updateHUD();
}

function updateHUD(){
  document.getElementById("homeScore").textContent=state.score;
  document.getElementById("homeTokens").textContent=state.tokens;
}

function addScore(n){
  state.score+=n;
  saveState();
}

function addTokens(n){
  state.tokens+=n;
  saveState();
}

function clearGameLoops(){
  timers.forEach(clearTimeout);
  timers.forEach(clearInterval);
  timers=[];
  animationFrames.forEach(cancelAnimationFrame);
  animationFrames=[];
  cleanupFns.forEach(fn=>{
    try{fn()}catch(e){}
  });
  cleanupFns=[];
}

function timer(fn,ms){
  const id=setTimeout(fn,ms);
  timers.push(id);
  return id;
}

function interval(fn,ms){
  const id=setInterval(fn,ms);
  timers.push(id);
  return id;
}

function frame(fn){
  const id=requestAnimationFrame(fn);
  animationFrames.push(id);
  return id;
}

function showScreen(id){
  clearGameLoops();

  document.querySelectorAll(".screen").forEach(s=>{
    s.classList.remove("active");
  });

  const screen=document.getElementById(id);

  if(screen){
    screen.classList.add("active");
  }

  window.scrollTo(0,0);
  updateHUD();
}

function completeLevel(n,bonus=50){
  if(!state.completed.includes(n)){
    state.completed.push(n);
    state.completed.sort((a,b)=>a-b);
    addScore(bonus);
    addTokens(Math.max(2,Math.floor(bonus/25)));
  }

  saveState();

  const next=n+1;

  const play=document.querySelector(`#game${n} .play-area`);
  const win=document.querySelector(`#game${n} .win-panel`);

  if(play) play.classList.add("hidden");

  if(win){
    win.classList.add("show");

    const nextButton=win.querySelector(".next-button");

    if(nextButton){
      if(next<=23){
        nextButton.textContent=`Next Level →`;
        nextButton.onclick=()=>startGame(next);
      }else{
        nextButton.textContent="Finish Journey 💗";
        nextButton.onclick=()=>showFinalResult();
      }
    }
  }

  updateHUD();
  saveState();
}

function gameHeader(n,title,sub){
  return `
    <div class="game-top">
      <h1 class="game-title">${levels[n-1][0]} ${title}</h1>
      <div class="game-sub">${sub}</div>
    </div>
  `;
}

function gameTemplate(n,title,sub,content){
  const div=document.createElement("section");
  div.id=`game${n}`;
  div.className="screen";

  div.innerHTML=`
    ${gameHeader(n,title,sub)}

    <div class="game-wrap">
      <div class="game-card">

        <div class="play-area">
          ${content}
        </div>

        <div class="win-panel">
          <div style="font-size:65px">💗</div>
          <h2>Level ${n} Complete!</h2>
          <p>${state.name ? "Amazing work, "+escapeHTML(state.name)+"!" : "Amazing!"}</p>
          <button class="primary next-button">Next Level →</button>
          <button class="secondary" onclick="showScreen('home');renderJourney()">
            Back to Journey
          </button>
        </div>

      </div>
    </div>
  `;

  document.getElementById("gameScreens").appendChild(div);
}

function escapeHTML(s){
  return String(s).replace(/[&<>"']/g,c=>({
    "&":"&amp;",
    "<":"&lt;",
    ">":"&gt;",
    '"':"&quot;",
    "'":"&#039;"
  }[c]));
}

/* =========================================================
   HOME / JOURNEY
   ========================================================= */

function beginJourney(){
  const input=document.getElementById("playerName");
  const name=input.value.trim();

  if(!name){
    input.focus();
    input.style.borderColor="#ff507f";
    return;
  }

  state.name=name;
  saveState();

  document.getElementById("welcomeBox").style.display="none";
  document.getElementById("journeyBox").style.display="block";

  renderJourney();
}

function continueJourney(){
  let next=1;

  for(let i=1;i<=23;i++){
    if(!state.completed.includes(i)){
      next=i;
      break;
    }

    if(i===23){
      next=23;
    }
  }

  startGame(next);
}

function renderJourney(){
  updateHUD();

  const box=document.getElementById("journey");

  if(!box)return;

  box.innerHTML="";

  levels.forEach((l,i)=>{
    const n=i+1;
    const done=state.completed.includes(n);
    const unlocked=n===1 || state.completed.includes(n-1);

    const el=document.createElement("div");

    el.className=
      "level "+
      (done?"done ":"")+
      (!unlocked?"locked ":"")+
      (unlocked&&!done?"current ":"");

    el.innerHTML=`
      <div class="level-num">LEVEL ${n}</div>
      <div class="level-title">${l[0]} ${l[1]}</div>
      <div class="level-status">
        ${done?"✓ Complete":unlocked?"▶ Unlocked":"🔒 Locked"}
      </div>
    `;

    if(unlocked){
      el.style.cursor="pointer";
      el.onclick=()=>startGame(n);
    }

    box.appendChild(el);
  });
}

function startGame(n){
  if(n>1 && !state.completed.includes(n-1)){
    return;
  }

  showScreen(`game${n}`);

  const fn=window[`initGame${n}`];

  if(typeof fn==="function"){
    fn();
  }
}

function showFinalResult(){
  showScreen("home");

  document.getElementById("welcomeBox").style.display="none";
  document.getElementById("journeyBox").style.display="block";

  renderJourney();

  setTimeout(()=>{
    alert(
      `🚂💗 Journey complete!\n\n`+
      `Well done, ${state.name}!\n\n`+
      `Final score: ${state.score}\n`+
      `Tokens: ${state.tokens}\n\n`+
      (state.score>3000
        ? "🎁 You unlocked the private call reward!"
        : "You finished the journey! 💗")
    );
  },100);
}

function resetEverything(){
  if(!confirm(
    "Reset the entire Lulu Express journey?\n\n"+
    "This will erase your name, score, tokens and all progress."
  ))return;

  clearGameLoops();

  try{
    localStorage.removeItem(STORAGE_KEY);
  }catch(e){}

  state={
    name:"",
    score:0,
    tokens:0,
    completed:[],
    music:false
  };

  stopMusic();

  document.getElementById("welcomeBox").style.display="block";
  document.getElementById("journeyBox").style.display="none";
  document.getElementById("playerName").value="";

  showScreen("home");
}

/* =========================================================
   MUSIC
   Built-in Web Audio.
   No external music files.
   ========================================================= */

let audioCtx=null;
let musicTimer=null;
let musicStep=0;

const melody=[
  261.63,329.63,392.00,329.63,
  293.66,349.23,440.00,349.23,
  261.63,329.63,392.00,523.25,
  440.00,392.00,329.63,261.63
];

function startMusic(){
  try{
    if(!audioCtx){
      audioCtx=new (window.AudioContext||window.webkitAudioContext)();
    }

    if(audioCtx.state==="suspended"){
      audioCtx.resume();
    }

    if(musicTimer)return;

    state.music=true;
    saveState();

    function playNote(){
      if(!audioCtx)return;

      const osc=audioCtx.createOscillator();
      const gain=audioCtx.createGain();

      osc.type="triangle";
      osc.frequency.value=melody[musicStep%melody.length];

      gain.gain.setValueAtTime(.0001,audioCtx.currentTime);
      gain.gain.exponentialRampToValueAtTime(
        .045,
        audioCtx.currentTime+.02
      );
      gain.gain.exponentialRampToValueAtTime(
        .0001,
        audioCtx.currentTime+.25
      );

      osc.connect(gain);
      gain.connect(audioCtx.destination);

      osc.start();
      osc.stop(audioCtx.currentTime+.27);

      musicStep++;
    }

    playNote();
    musicTimer=setInterval(playNote,300);

    document.getElementById("musicButton").textContent="♫ Music: ON";

  }catch(e){
    state.music=false;
  }
}

function stopMusic(){
  if(musicTimer){
    clearInterval(musicTimer);
    musicTimer=null;
  }

  if(audioCtx){
    try{audioCtx.suspend();}catch(e){}
  }

  state.music=false;
  const btn=document.getElementById("musicButton");
  if(btn)btn.textContent="♫ Music: OFF";

  saveState();
}

document.getElementById("musicButton").addEventListener("click",()=>{
  if(state.music)stopMusic();
  else startMusic();
});

loadState();

if(state.name){
  document.getElementById("playerName").value=state.name;
  document.getElementById("welcomeBox").style.display="none";
  document.getElementById("journeyBox").style.display="block";
  document.getElementById("welcomeName").textContent=state.name;
}

updateHUD();
renderJourney();

/* =========================================================
   GAME 1 — BROKEN HEARTS
   Easier mobile control.
   ========================================================= */

function initGame1(){

  const root=document.querySelector("#game1 .play-area");

  root.innerHTML=`
    <div class="heart-stats">
      <span>⭐ <b id="hScore">0</b></span>
      <span>❤️ <b id="hLives">3</b></span>
      <span>🔥 Combo <b id="hCombo">0</b></span>
    </div>

    <div id="heartBoard" class="heart-board">
      <div id="catcher" class="catcher"></div>
    </div>

    <div class="catch-controls">
      <button id="leftHeart" class="move-btn">⬅️</button>
      <button id="rightHeart" class="move-btn">➡️</button>
    </div>

    <div class="message" id="heartMessage">
      Catch the whole hearts. Avoid the broken ones. 💗
    </div>
  `;

  const board=document.getElementById("heartBoard");
  const catcher=document.getElementById("catcher");

  let x=50;
  let move=-1;
  let score=0;
  let lives=3;
  let combo=0;
  let caught=0;
  let running=true;
  let spawnDelay=900;

  function updateCatcher(){
    const width=board.clientWidth;
    const catcherWidth=catcher.offsetWidth;

    const min=catcherWidth/2;
    const max=width-catcherWidth/2;

    let px=(x/100)*width;

    px=Math.max(min,Math.min(max,px));

    x=(px/width)*100;

    catcher.style.left=x+"%";
  }

  function setMove(dir){
    move=dir;
  }

  function stopMove(){
    move=0;
  }

  function movementLoop(){
    if(!running)return;

    if(move!==0){
      x+=move*0.85;
      x=Math.max(5,Math.min(95,x));
      updateCatcher();
    }

    requestAnimationFrame(movementLoop);
  }

  function bindMoveButton(id,dir){

    const btn=document.getElementById(id);

    const down=e=>{
      e.preventDefault();
      e.stopPropagation();

      btn.classList.add("held");
      setMove(dir);

      if(e.pointerId!==undefined){
        try{btn.setPointerCapture(e.pointerId)}catch(err){}
      }
    };

    const up=e=>{
      e.preventDefault();
      e.stopPropagation();
      btn.classList.remove("held");
      stopMove();
    };

    btn.addEventListener("pointerdown",down,{passive:false});
    btn.addEventListener("pointerup",up,{passive:false});
    btn.addEventListener("pointercancel",up,{passive:false});
    btn.addEventListener("pointerleave",up,{passive:false});

    cleanupFns.push(()=>{
      btn.removeEventListener("pointerdown",down);
      btn.removeEventListener("pointerup",up);
      btn.removeEventListener("pointercancel",up);
      btn.removeEventListener("pointerleave",up);
    });
  }

  bindMoveButton("leftHeart",-1);
  bindMoveButton("rightHeart",1);

  const keydown=e=>{
    if(e.key==="ArrowLeft")move=-1;
    if(e.key==="ArrowRight")move=1;
  };

  const keyup=e=>{
    if(e.key==="ArrowLeft" || e.key==="ArrowRight"){
      move=0;
    }
  };

  window.addEventListener("keydown",keydown);
  window.addEventListener("keyup",keyup);

  cleanupFns.push(()=>{
    window.removeEventListener("keydown",keydown);
    window.removeEventListener("keyup",keyup);
  });

  function spawnHeart(){

    if(!running)return;

    const heart=document.createElement("div");

    const random=Math.random();

    let type="normal";

    if(random<.16)type="broken";
    else if(random<.25)type="gold";

    heart.className="falling-heart";

    heart.textContent=
      type==="broken" ? "💔" :
      type==="gold" ? "💛" :
      "❤️";

    const size=
      type==="gold"?25:
      type==="broken"?25:23;

    heart.style.fontSize=size+"px";

    const left=8+Math.random()*84;

    heart.style.left=left+"%";
    heart.style.top="-35px";

    board.appendChild(heart);

    const speed=
      1.35+
      Math.min(.9,caught*.025)+
      Math.random()*.45;

    let y=-35;

    function fall(){

      if(!running){
        heart.remove();
        return;
      }

      y+=speed;
      heart.style.top=y+"px";

      const boardRect=board.getBoundingClientRect();
      const heartRect=heart.getBoundingClientRect();
      const catcherRect=catcher.getBoundingClientRect();

      const horizontal=
        heartRect.right>=catcherRect.left &&
        heartRect.left<=catcherRect.right;

      const vertical=
        heartRect.bottom>=catcherRect.top &&
        heartRect.top<=catcherRect.bottom;

      if(horizontal && vertical){

        caught++;

        if(type==="broken"){

          lives--;
          combo=0;

          document.getElementById("hLives").textContent=lives;
          document.getElementById("hCombo").textContent=combo;

          heart.remove();

          if(lives<=0){
            finish(false);
            return;
          }

        }else{

          combo++;

          let points=type==="gold"?30:10;

          if(combo>=5)points+=10;

          score+=points;

          document.getElementById("hScore").textContent=score;
          document.getElementById("hCombo").textContent=combo;

          heart.remove();

          if(caught>=22){
            finish(true);
            return;
          }
        }

        return;
      }

      if(y>board.clientHeight+40){
        if(type==="normal" || type==="gold"){
          combo=0;
          document.getElementById("hCombo").textContent=combo;
        }

        heart.remove();
        return;
      }

      requestAnimationFrame(fall);
    }

    requestAnimationFrame(fall);
  }

  function finish(win){

    running=false;

    if(win){

      addScore(score);
      addTokens(3);

      completeLevel(1,0);

      document.querySelector("#game1 .win-panel p").textContent=
        `You caught enough hearts! +${score} points 💗`;

    }else{

      document.querySelector("#game1 .play-area").classList.remove("hidden");

      document.getElementById("heartMessage").textContent=
        "You ran out of lives. Try again!";

      timer(()=>{
        initGame1();
      },900);
    }
  }

  updateCatcher();
  movementLoop();

  interval(()=>{
    spawnHeart();

    if(spawnDelay>560){
      spawnDelay-=25;
    }
  },spawnDelay);
}

/* =========================================================
   GAME 2 — MEMORY VAULT
   ========================================================= */

function initGame2(){

  const root=document.querySelector("#game2 .play-area");

  root.innerHTML=`
    <div class="center">
      <div class="statline">
        <span>Round <b id="memRound">1</b>/7</span>
        <span>Correct <b id="memCorrect">0</b></span>
      </div>

      <div class="message" id="memMessage">
        Watch the sequence...
      </div>

      <div id="memoryGrid" class="memory-grid"></div>
    </div>
  `;

  const grid=document.getElementById("memoryGrid");

  let sequence=[];
  let input=[];
  let round=1;
  let correct=0;
  let accepting=false;

  for(let i=0;i<16;i++){
    const tile=document.createElement("button");
    tile.className="memory-tile";
    tile.textContent="♡";
    tile.dataset.i=i;

    tile.onclick=()=>{
      if(!accepting)return;

      const n=Number(tile.dataset.i);

      tile.classList.add("lit");
      timer(()=>tile.classList.remove("lit"),180);

      input.push(n);

      const pos=input.length-1;

      if(input[pos]!==sequence[pos]){
        accepting=false;

        document.getElementById("memMessage").textContent=
          "Almost! Watch it again. 💗";

        timer(()=>{
          input=[];
          showSequence();
        },600);

        return;
      }

      if(input.length===sequence.length){

        accepting=false;
        correct++;

        document.getElementById("memCorrect").textContent=correct;

        if(correct>=7){
          addScore(150);
          addTokens(5);
          completeLevel(2,0);
          return;
        }

        round++;
        document.getElementById("memRound").textContent=round;

        timer(()=>{
          sequence.push(Math.floor(Math.random()*16));
          showSequence();
        },700);
      }
    };

    grid.appendChild(tile);
  }

  sequence=[
    Math.floor(Math.random()*16),
    Math.floor(Math.random()*16)
  ];

  function showSequence(){

    accepting=false;
    input=[];

    document.getElementById("memMessage").textContent=
      "Watch carefully...";

    const tiles=[...grid.children];

    tiles.forEach(t=>t.classList.remove("lit"));

    sequence.forEach((n,i)=>{
      timer(()=>{
        tiles[n].classList.add("lit");

        timer(()=>{
          tiles[n].classList.remove("lit");
        },250);

      },i*450);
    });

    timer(()=>{
      accepting=true;
      document.getElementById("memMessage").textContent=
        "Your turn!";
    },sequence.length*450+250);
  }

  showSequence();
}

/* =========================================================
   QUIZ HELPER
   ========================================================= */

function shuffledQuestion(q){
  const arr=q.options.map((text,i)=>({
    text,
    correct:i===q.answer
  }));

  for(let i=arr.length-1;i>0;i--){
    const j=Math.floor(Math.random()*(i+1));
    [arr[i],arr[j]]=[arr[j],arr[i]];
  }

  return arr;
}

function runQuiz(n,questions,totalToAsk,passScore,titleText){

  const root=document.querySelector(`#game${n} .play-area`);

  root.innerHTML=`
    <div class="statline">
      <span>Question <b id="qNumber">1</b>/${totalToAsk}</span>
      <span>Score <b id="qScore">0</b></span>
    </div>

    <div class="progress">
      <div id="qProgress"></div>
    </div>

    <h2 id="qText" class="center"></h2>

    <div id="qChoices" class="choice-grid"></div>

    <div id="qMessage" class="message"></div>
  `;

  let index=0;
  let score=0;
  let selectedQuestions=[...questions]
    .sort(()=>Math.random()-.5)
    .slice(0,totalToAsk);

  function next(){

    if(index>=selectedQuestions.length){

      if(score>=passScore){
        addScore(score*10);
        addTokens(score>=passScore+2?4:3);
        completeLevel(n,0);
      }else{
        document.getElementById("qMessage").textContent=
          `You scored ${score}/${totalToAsk}. Try again!`;
        timer(()=>runQuiz(n,questions,totalToAsk,passScore,titleText),1000);
      }

      return;
    }

    const q=selectedQuestions[index];
    const answers=shuffledQuestion(q);

    document.getElementById("qNumber").textContent=index+1;
    document.getElementById("qProgress").style.width=
      `${(index/totalToAsk)*100}%`;

    document.getElementById("qText").textContent=q.q;

    const box=document.getElementById("qChoices");
    box.innerHTML="";

    answers.forEach(a=>{
      const btn=document.createElement("button");
      btn.className="choice";
      btn.textContent=a.text;

      btn.onclick=()=>{

        [...box.children].forEach(b=>b.disabled=true);

        if(a.correct){
          btn.classList.add("correct");
          score++;
          document.getElementById("qScore").textContent=score;
          document.getElementById("qMessage").textContent="Correct! 💗";
        }else{
          btn.classList.add("wrong");
          document.getElementById("qMessage").textContent="Not this time!";
        }

        index++;

        timer(next,450);
      };

      box.appendChild(btn);
    });
  }

  next();
}

/* =========================================================
   GAME 3 — PRESSURE QUIZ
   ========================================================= */

const pressureQuestions=[
{q:"What is the capital of Australia?",options:["Sydney","Canberra","Melbourne","Perth"],answer:1},
{q:"Which planet is the largest?",options:["Saturn","Earth","Jupiter","Neptune"],answer:2},
{q:"Which planet is known as the Red Planet?",options:["Mars","Venus","Mercury","Jupiter"],answer:0},
{q:"What is the chemical symbol for gold?",options:["Ag","Gd","Au","Go"],answer:2},
{q:"How many continents are there?",options:["5","6","7","8"],answer:2},
{q:"The Great Barrier Reef is off the coast of which country?",options:["New Zealand","Australia","Indonesia","Fiji"],answer:1},
{q:"Who wrote Pride and Prejudice?",options:["Jane Austen","Emily Brontë","Mary Shelley","Virginia Woolf"],answer:0},
{q:"What is Japan's currency?",options:["Won","Yuan","Yen","Ringgit"],answer:2},
{q:"Which animal is the fastest on land?",options:["Horse","Cheetah","Lion","Greyhound"],answer:1},
{q:"What is the largest ocean?",options:["Atlantic","Indian","Pacific","Arctic"],answer:2},
{q:"At sea level, water boils at approximately what temperature?",options:["80°C","90°C","100°C","120°C"],answer:2},
{q:"How many chambers does the human heart have?",options:["2","3","4","5"],answer:2},
{q:"Which gas makes up most of Earth's atmosphere?",options:["Oxygen","Nitrogen","Carbon dioxide","Hydrogen"],answer:1},
{q:"What is the smallest prime number?",options:["0","1","2","3"],answer:2},
{q:"Who painted the Mona Lisa?",options:["Michelangelo","Raphael","Leonardo da Vinci","Van Gogh"],answer:2},
{q:"What does DNA stand for?",options:["Deoxyribonucleic acid","Dinitrogen acid","Dynamic nucleic atom","Double nitrogen acid"],answer:0},
{q:"How many sides does an octagon have?",options:["6","7","8","9"],answer:2},
{q:"Which gas has the formula H₂O?",options:["Oxygen","Hydrogen","Water","Carbon dioxide"],answer:2},
{q:"Which desert covers much of northern Africa?",options:["Gobi","Sahara","Atacama","Kalahari"],answer:1},
{q:"Where is the Eiffel Tower?",options:["Rome","Paris","Madrid","Berlin"],answer:1},
{q:"Which country is Mount Fuji in?",options:["China","South Korea","Japan","Thailand"],answer:2},
{q:"What is New Zealand's currency?",options:["Australian dollar","New Zealand dollar","Pound","Franc"],answer:1},
{q:"Which animal is a mammal?",options:["Shark","Dolphin","Tuna","Octopus"],answer:1},
{q:"Which planet has famous visible rings?",options:["Mercury","Saturn","Mars","Venus"],answer:1},
{q:"Light travels faster than what?",options:["Sound","Gravity","Electricity","Heat"],answer:0},
{q:"What is the capital of France?",options:["Lyon","Paris","Nice","Bordeaux"],answer:1},
{q:"Which shape has four equal sides?",options:["Triangle","Rectangle","Square","Pentagon"],answer:2},
{q:"How many days are in a normal year?",options:["364","365","366","367"],answer:1},
{q:"Which organ pumps blood around the body?",options:["Liver","Heart","Lung","Kidney"],answer:1},
{q:"What is the largest human organ?",options:["Brain","Skin","Liver","Lung"],answer:1}
];

function initGame3(){
  runQuiz(3,pressureQuestions,10,6,"Pressure Quiz");
}

/* =========================================================
   GAME 4 — HIGH ROLLER
   ========================================================= */

function initGame4(){

  const root=document.querySelector("#game4 .play-area");

  root.innerHTML=`
    <div class="center">
      <div class="statline">
        <span>Coins: <b id="slotCoins">100</b></span>
        <span>Wins: <b id="slotWins">0</b></span>
      </div>

      <div class="reels">
        <div class="reel" id="r1">🍒</div>
        <div class="reel" id="r2">💎</div>
        <div class="reel" id="r3">7️⃣</div>
      </div>

      <p id="slotMessage" class="message">
        Start the machine!
      </p>

      <button id="spinButton" class="primary">
        🎰 SPIN
      </button>
    </div>
  `;

  const symbols=["🍒","💎","⭐","🍀","7️⃣"];

  let coins=100;
  let wins=0;
  let spins=0;
  let spinning=false;

  document.getElementById("spinButton").onclick=spin;

  function spin(){

    if(spinning)return;

    spinning=true;
    spins++;
    coins-=5;

    document.getElementById("slotCoins").textContent=coins;

    let stops=[];

    for(let i=0;i<3;i++){
      stops.push(
        timer(()=>{
          const el=document.getElementById("r"+(i+1));

          let count=0;

          const anim=setInterval(()=>{
            el.textContent=symbols[Math.floor(Math.random()*symbols.length)];
            count++;

            if(count>8){
              clearInterval(anim);

              const value=symbols[Math.floor(Math.random()*symbols.length)];
              el.textContent=value;

              if(i===2){
                evaluate();
              }
            }
          },70);

          timers.push(anim);
        },i*500)
      );
    }
  }

  function evaluate(){

    const values=[
      document.getElementById("r1").textContent,
      document.getElementById("r2").textContent,
      document.getElementById("r3").textContent
    ];

    const unique=new Set(values).size;

    if(unique===1){
      coins+=100;
      wins++;
      addScore(100);
      addTokens(4);

      document.getElementById("slotMessage").textContent=
        "🎉 JACKPOT! Three matching!";
    }else if(unique===2){
      coins+=25;
      wins++;
      addScore(30);

      document.getElementById("slotMessage").textContent=
        "✨ Two matching!";
    }else{
      document.getElementById("slotMessage").textContent=
        "Try again!";
    }

    document.getElementById("slotCoins").textContent=coins;
    document.getElementById("slotWins").textContent=wins;

    spinning=false;

    if(wins>=3 || spins>=8){
      if(wins>=1){
        completeLevel(4,0);
      }
    }

    if(coins<=0 && wins===0){
      timer(initGame4,700);
    }
  }
}

/* =========================================================
   GAME 5 — MIND GAMES
   ========================================================= */

const patternQuestions=[
{q:"❤️ 💙 ❤️ 💙 ❤️ ?",options:["❤️","💙","💚","💜"],answer:1},
{q:"1, 2, 4, 8, ?",options:["10","12","16","18"],answer:2},
{q:"🌸 🌻 🌸 🌻 🌸 ?",options:["🌸","🌻","🌹","🌺"],answer:1},
{q:"▲ ▲ ● ▲ ▲ ● ?",options:["▲","●","■","◆"],answer:0},
{q:"2, 4, 6, 8, ?",options:["9","10","11","12"],answer:1},
{q:"A, C, E, G, ?",options:["H","I","J","K"],answer:1},
{q:"⭐ ⭐ 💗 ⭐ ⭐ 💗 ?",options:["⭐","💗","🌙","☀️"],answer:0},
{q:"10, 9, 7, 4, ?",options:["2","1","0","3"],answer:1}
];

function initGame5(){
  runQuiz(5,patternQuestions,8,5,"Mind Games");
}

/* =========================================================
   GAME 6 — THE BLUFF
   ========================================================= */

function initGame6(){

  const root=document.querySelector("#game6 .play-area");

  root.innerHTML=`
    <div class="center">
      <div class="statline">
        <span>Round <b id="bluffRound">1</b>/5</span>
        <span>Score <b id="bluffScore">0</b></span>
      </div>

      <p id="bluffMessage">Choose a hidden card.</p>

      <div id="bluffCards" class="choice-grid"></div>

      <div id="bluffRisk" style="display:none">
        <div class="game-actions">
          <button id="bankBluff" class="secondary">🏦 Bank</button>
          <button id="doubleBluff" class="primary">🎲 Double</button>
        </div>
      </div>
    </div>
  `;

  let round=1;
  let score=0;
  let chosen=0;

  function makeRound(){

    document.getElementById("bluffRound").textContent=round;
    document.getElementById("bluffRisk").style.display="none";

    const box=document.getElementById("bluffCards");
    box.innerHTML="";

    for(let i=0;i<4;i++){

      const btn=document.createElement("button");
      btn.className="choice";
      btn.textContent="🂠 Mystery";

      btn.onclick=()=>{

        [...box.children].forEach(b=>b.disabled=true);

        chosen=1+Math.floor(Math.random()*20);

        btn.textContent=`💗 ${chosen}`;

        document.getElementById("bluffMessage").textContent=
          `Your card is worth ${chosen}.`;

        document.getElementById("bluffRisk").style.display="block";
      };

      box.appendChild(btn);
    }
  }

  function finishRound(value){
    score+=value;
    document.getElementById("bluffScore").textContent=score;

    if(round>=5){

      if(score>=35){
        addScore(score);
        addTokens(4);
        completeLevel(6,0);
      }else{
        timer(initGame6,700);
      }

      return;
    }

    round++;

    timer(makeRound,600);
  }

  document.getElementById("bankBluff").onclick=()=>{
    finishRound(chosen);
  };

  document.getElementById("doubleBluff").onclick=()=>{
    if(chosen>=8){
      finishRound(chosen*2);
    }else{
      finishRound(0);
    }
  };

  makeRound();
}

/* =========================================================
   GAME 7 — SURVIVAL ROUND
   ========================================================= */

const survivalRounds=[
{
  hazard:"A wave is coming 🌊",
  options:["JUMP","DUCK","FREEZE"],
  answer:"JUMP"
},
{
  hazard:"Something is falling! 🪨",
  options:["MOVE LEFT","FREEZE","SLEEP"],
  answer:"MOVE LEFT"
},
{
  hazard:"A bright light flashes ⚡",
  options:["DUCK","STARE","RUN TOWARD IT"],
  answer:"DUCK"
},
{
  hazard:"The floor shakes 🌋",
  options:["STEP BACK","JUMP FORWARD","SIT DOWN"],
  answer:"STEP BACK"
},
{
  hazard:"A branch falls 🌳",
  options:["DUCK","CLIMB","WAIT"],
  answer:"DUCK"
},
{
  hazard:"Water rises 💧",
  options:["CLIMB UP","SIT","RUN DOWN"],
  answer:"CLIMB UP"
},
{
  hazard:"A door slams 🚪",
  options:["STEP AWAY","PUSH HEAD FIRST","FREEZE"],
  answer:"STEP AWAY"
},
{
  hazard:"The alarm sounds 🚨",
  options:["MOVE TO SAFETY","IGNORE IT","TURN OFF LIGHTS"],
  answer:"MOVE TO SAFETY"
}
];

function initGame7(){

  const root=document.querySelector("#game7 .play-area");

  root.innerHTML=`
    <div class="center">
      <div class="statline">
        Wave <b id="survivalWave">1</b>/8
        • Safe <b id="survivalSafe">0</b>
      </div>

      <div class="big" id="hazardText"></div>
      <div id="survivalChoices" class="choice-grid"></div>
      <div id="survivalMessage" class="message"></div>
    </div>
  `;

  let wave=0;
  let safe=0;

  function next(){

    if(wave>=8){

      if(safe>=6){
        addScore(120);
        addTokens(4);
        completeLevel(7,0);
      }else{
        timer(initGame7,700);
      }

      return;
    }

    const r=survivalRounds[wave];

    document.getElementById("survivalWave").textContent=wave+1;
    document.getElementById("hazardText").textContent=r.hazard;

    const box=document.getElementById("survivalChoices");
    box.innerHTML="";

    r.options.forEach(o=>{
      const b=document.createElement("button");
      b.className="choice";
      b.textContent=o;

      b.onclick=()=>{
        [...box.children].forEach(x=>x.disabled=true);

        if(o===r.answer){
          b.classList.add("correct");
          safe++;
          document.getElementById("survivalMessage").textContent="Safe! 🛡️";
        }else{
          b.classList.add("wrong");
          document.getElementById("survivalMessage").textContent="That was risky!";
        }

        document.getElementById("survivalSafe").textContent=safe;
        wave++;

        timer(next,400);
      };

      box.appendChild(b);
    });
  }

  next();
}

/* =========================================================
   GAME 8 — THE ADMIRER RACE
   NO DODGING.
   ========================================================= */

function initGame8(){

  const root=document.querySelector("#game8 .play-area");

  root.innerHTML=`
    <div class="center">
      <div class="statline">
        <span>Round <b id="raceRound">1</b>/10</span>
        <span>You: <b id="playerDistance">0</b></span>
        <span>Rival: <b id="rivalDistance">0</b></span>
      </div>

      <div class="race-meter" id="raceMeter">
        <div class="perfect-zone"></div>
        <div id="raceMarker" class="race-marker"></div>
      </div>

      <button id="gallopButton" class="primary"
        style="width:100%;font-size:20px">
        🐎 GALLop!
      </button>

      <div id="raceMessage" class="message">
        Tap when the marker is inside the green zone!
      </div>

      <div class="progress">
        <div id="raceProgress"></div>
      </div>
    </div>
  `;

  let round=1;
  let player=0;
  let rival=0;
  let marker=0;
  let direction=1;
  let active=true;

  function animate(){

    if(!active)return;

    marker+=direction*2.4;

    if(marker>=100){
      marker=100;
      direction=-1;
    }

    if(marker<=0){
      marker=0;
      direction=1;
    }

    document.getElementById("raceMarker").style.left=
      `calc(${marker}% - 3px)`;

    requestAnimationFrame(animate);
  }

  function gallop(){

    if(!active)return;

    const distanceFromPerfect=Math.abs(marker-50);

    let gain;

    if(distanceFromPerfect<=8){
      gain=8;
      document.getElementById("raceMessage").textContent="PERFECT! 🔥";
    }else if(distanceFromPerfect<=20){
      gain=5;
      document.getElementById("raceMessage").textContent="GOOD! 💗";
    }else{
      gain=2;
      document.getElementById("raceMessage").textContent="Keep going!";
    }

    player+=gain;

    rival+=6;

    document.getElementById("playerDistance").textContent=player;
    document.getElementById("rivalDistance").textContent=rival;

    document.getElementById("raceProgress").style.width=
      `${Math.min(100,round*10)}%`;

    if(round>=10){

      active=false;

      if(player>rival){
        addScore(140);
        addTokens(5);
        completeLevel(8,0);
      }else{
        document.getElementById("raceMessage").textContent=
          "The rival won. Try again!";

        timer(initGame8,800);
      }

      return;
    }

    round++;
    document.getElementById("raceRound").textContent=round;
  }

  document.getElementById("gallopButton").onclick=gallop;

  animate();
}

/* =========================================================
   GAME 9 — HEARTBREAK CHAMBER
   ========================================================= */

function initGame9(){

  const root=document.querySelector("#game9 .play-area");

  root.innerHTML=`
    <div class="center">
      <p id="chamberMessage">
        Search the room and find four clues.
      </p>

      <div id="chamberObjects" class="choice-grid"></div>

      <div class="notice" id="clueBox">
        Clues found: 0/4
      </div>
    </div>
  `;

  const objects=[
    ["🗄️","Desk Drawer"],
    ["🌻","Flower Pot"],
    ["🖼️","Photo Frame"],
    ["📚","Bookshelf"],
    ["☕","Coffee Cup"],
    ["🕯️","Candle"],
    ["🧸","Teddy Bear"],
    ["🔑","Small Box"]
  ];

  const clues=new Set();

  const box=document.getElementById("chamberObjects");

  objects.forEach((o,i)=>{

    const b=document.createElement("button");
    b.className="choice";
    b.textContent=`${o[0]} ${o[1]}`;

    b.onclick=()=>{

      if(clues.has(i))return;

      if([0,2,5,7].includes(i)){

        clues.add(i);

        b.classList.add("correct");

        document.getElementById("clueBox").textContent=
          `Clues found: ${clues.size}/4`;

        if(clues.size===4){

          document.getElementById("chamberMessage").textContent=
            "You found every clue and unlocked the chamber! 🔓";

          addScore(130);
          addTokens(4);
          completeLevel(9,0);
        }

      }else{

        document.getElementById("chamberMessage").textContent=
          "Nothing useful there...";
      }
    };

    box.appendChild(b);
  });
}

/* =========================================================
   GAME 10 — HEARTBREAK BOXING
   ========================================================= */

function initGame10(){

  const root=document.querySelector("#game10 .play-area");

  root.innerHTML=`
    <div class="center">

      <div>🥊 Your Health</div>
      <div class="hpbar">
        <div id="playerHP" class="hpfill"></div>
      </div>

      <div>💥 Opponent</div>
      <div class="hpbar">
        <div id="enemyHP" class="hpfill"></div>
      </div>

      <div id="boxingMessage" class="message">
        Fight smart!
      </div>

      <div class="fight-buttons">
        <button class="primary" id="punch">🥊 Punch</button>
        <button class="primary" id="heavy">💥 Heavy</button>
        <button class="secondary" id="block">🛡️ Block</button>
        <button class="secondary" id="dodge">↔️ Dodge</button>
      </div>
    </div>
  `;

  let player=100;
  let enemy=80;
  let guard=false;
  let cooldown=false;

  function update(){

    document.getElementById("playerHP").style.width=
      Math.max(0,player)+"%";

    document.getElementById("enemyHP").style.width=
      Math.max(0,enemy/80*100)+"%";

    if(enemy<=0){
      addScore(160);
      addTokens(5);
      completeLevel(10,0);
      return;
    }

    if(player<=0){
      timer(initGame10,800);
    }
  }

  function enemyAttack(){

    if(enemy<=0)return;

    let damage=8+Math.floor(Math.random()*7);

    if(guard)damage=Math.floor(damage/2);

    player-=damage;

    guard=false;

    document.getElementById("boxingMessage").textContent=
      `Opponent hit for ${damage}!`;

    update();
  }

  document.getElementById("punch").onclick=()=>{
    enemy-=10;
    document.getElementById("boxingMessage").textContent="Punch! 🥊";
    enemyAttack();
  };

  document.getElementById("heavy").onclick=()=>{
    if(cooldown)return;

    cooldown=true;
    enemy-=18;

    document.getElementById("boxingMessage").textContent=
      "Heavy hit! 💥";

    enemyAttack();

    timer(()=>{
      cooldown=false;
    },1000);
  };

  document.getElementById("block").onclick=()=>{
    guard=true;
    document.getElementById("boxingMessage").textContent=
      "Guard up! 🛡️";
  };

  document.getElementById("dodge").onclick=()=>{
    if(Math.random()<.75){
      document.getElementById("boxingMessage").textContent=
        "Perfect dodge! ↔️";
    }else{
      enemyAttack();
    }
  };

  update();
}

/* =========================================================
   GAME 11 — PERFECT MATCH
   ========================================================= */

function initGame11(){

  const root=document.querySelector("#game11 .play-area");

  root.innerHTML=`
    <div class="center">
      <p>Match each object with its outline.</p>

      <div class="match-board">
        <div class="match-side" id="matchItems"></div>
        <div class="match-side" id="matchTargets"></div>
      </div>

      <div id="matchMessage" class="message">
        Drag or touch an item onto its matching target.
      </div>
    </div>
  `;

  const pairs=[
    ["❤️","heart"],
    ["🌻","sunflower"],
    ["🐬","dolphin"],
    ["🌹","rose"],
    ["💎","diamond"]
  ];

  let matched=0;

  const items=document.getElementById("matchItems");
  const targets=document.getElementById("matchTargets");

  pairs
    .slice()
    .sort(()=>Math.random()-.5)
    .forEach((p,i)=>{

      const el=document.createElement("div");

      el.className="match-item";
      el.textContent=p[0];
      el.draggable=true;
      el.dataset.match=p[1];

      el.addEventListener("dragstart",e=>{
        e.dataTransfer.setData("text/plain",p[1]);
      });

      let startX=0,startY=0;

      el.addEventListener("pointerdown",e=>{
        startX=e.clientX;
        startY=e.clientY;
      });

      targets.appendChild(
        (()=> {
          const t=document.createElement("div");
          t.className="match-target";
          t.textContent="♡";
          t.dataset.match=p[1];

          t.addEventListener("dragover",e=>e.preventDefault());

          t.addEventListener("drop",e=>{
            e.preventDefault();

            if(e.dataTransfer.getData("text/plain")===p[1]){
              matchSuccess(el,t);
            }
          });

          t.addEventListener("pointerup",e=>{
            const dx=Math.abs(e.clientX-startX);
            const dy=Math.abs(e.clientY-startY);

            if(dx+dy>25){
              matchSuccess(el,t);
            }
          });

          return t;
        })()
      );

      items.appendChild(el);
    });

  function matchSuccess(el,target){

    if(el.dataset.done)return;

    el.dataset.done="1";
    el.style.opacity=".25";
    target.textContent=el.textContent;
    target.style.borderStyle="solid";
    target.style.opacity=".8";

    matched++;

    if(matched===pairs.length){
      addScore(130);
      addTokens(4);
      completeLevel(11,0);
    }
  }
}

/* =========================================================
   GAME 12 — WHO KNOWS LILIANA BEST?
   ========================================================= */

const lilianaQuiz=[
{q:"What is Liliana's favourite colour?",options:["Baby pink","Burgundy","Sky blue","Purple"],answer:0},
{q:"What is Liliana's favourite number?",options:["3","7","9","11"],answer:0},
{q:"Which food does Liliana like?",options:["Sushi","Fish and chips","Tacos","Curry"],answer:0},
{q:"Which animal does Liliana like?",options:["Dolphins","Tigers","Koalas","Penguins"],answer:0},
{q:"Which flowers does Liliana like?",options:["Sunflowers and roses","Lilies and tulips","Orchids and daisies","Lavender and violets"],answer:0},
{q:"What month is Liliana's birthday in?",options:["July","June","August","May"],answer:0},
{q:"What day is Liliana's birthday?",options:["22","12","20","27"],answer:0},
{q:"What colour are Liliana's eyes?",options:["Green","Blue","Brown","Hazel"],answer:0},
{q:"What is Liliana's zodiac sign?",options:["Leo","Cancer","Virgo","Gemini"],answer:0},
{q:"What is Liliana afraid of?",options:["Drowning","Flying","Heights","Thunder"],answer:0},
{q:"What is Liliana's favourite movie?",options:["Me Before You","Titanic","The Notebook","Frozen"],answer:0},
{q:"What subject did Liliana study at university?",options:["Psychology","Law","Biology","Art"],answer:0},
{q:"How many nieces does Liliana have?",options:["1","2","3","4"],answer:0},
{q:"How many nephews does Liliana have?",options:["4","2","5","3"],answer:0},
{q:"How many siblings does Liliana have?",options:["5","4","6","3"],answer:0},
{q:"How many piercings does Liliana have?",options:["4","2","3","5"],answer:0},
{q:"What are Liliana's dogs called?",options:["Aayla and Arlo","Luna and Milo","Bella and Max","Coco and Leo"],answer:0},
{q:"What kind of songs does Liliana like?",options:["Sad songs","Only dance songs","Only country songs","Only rock songs"],answer:0},
{q:"What type of writing does Liliana enjoy?",options:["Poetry","News","Biographies","Cookbooks"],answer:0},
{q:"What does Liliana enjoy playing?",options:["Poker and gambling games","Chess only","Football","Golf"],answer:0}
];

function initGame12(){
  runQuiz(12,lilianaQuiz,12,8,"Liliana Quiz");
}

/* =========================================================
   GAME 13 — REACTION GAUNTLET
   ========================================================= */

function initGame13(){

  const root=document.querySelector("#game13 .play-area");

  root.innerHTML=`
    <div class="center">
      <div class="statline">
        Round <b id="reactionRound">1</b>/10
        • Score <b id="reactionScore">0</b>
      </div>

      <div id="reactionButton" class="reaction-button">
        GET READY
      </div>

      <div id="reactionMessage" class="message"></div>
    </div>
  `;

  let round=0;
  let score=0;
  let active=false;
  let command="";

  const button=document.getElementById("reactionButton");

  function newRound(){

    round++;

    if(round>10){

      if(score>=7){
        addScore(140);
        addTokens(4);
        completeLevel(13,0);
      }else{
        timer(initGame13,700);
      }

      return;
    }

    document.getElementById("reactionRound").textContent=round;

    const commands=[
      "TAP NOW",
      "DON'T TAP",
      "TAP NOW",
      "TAP NOW"
    ];

    command=commands[Math.floor(Math.random()*commands.length)];

    active=false;

    button.textContent="WAIT...";
    button.style.background="#432034";

    const delay=500+Math.random()*1300;

    timer(()=>{

      active=true;
      button.textContent=command;
      button.style.background=
        command==="DON'T TAP" ? "#7c203f" : "#315c48";

    },delay);
  }

  button.onclick=()=>{

    if(!active){

      if(command==="DON'T TAP"){
        score++;
      }else{
        score=Math.max(0,score-1);
      }

    }else{

      if(command==="TAP NOW"){
        score++;
        document.getElementById("reactionMessage").textContent="FAST! ⚡";
      }else{
        score=Math.max(0,score-1);
      }

      active=false;
    }

    document.getElementById("reactionScore").textContent=score;

    timer(newRound,350);
  };

  newRound();
}

/* =========================================================
   GAME 14 — HEART HUNT
   ========================================================= */

function initGame14(){

  const root=document.querySelector("#game14 .play-area");

  root.innerHTML=`
    <div class="center">
      <div class="statline">
        Hearts found <b id="huntFound">0</b>/10
      </div>

      <div id="huntArea" class="hunt-area"></div>

      <div id="huntMessage" class="message">
        Find the hidden hearts!
      </div>
    </div>
  `;

  const area=document.getElementById("huntArea");

  let found=0;

  for(let i=0;i<20;i++){

    const h=document.createElement("button");
    h.className="hunt-heart";

    h.textContent=
      i<12 ? "💗" :
      ["🌸","✨","•","♡","🌹"][Math.floor(Math.random()*5)];

    h.style.left=(3+Math.random()*90)+"%";
    h.style.top=(3+Math.random()*88)+"%";

    if(i>=12){
      h.style.opacity=".6";
      h.style.fontSize="18px";
    }

    h.onclick=()=>{

      if(i>=12)return;

      if(h.dataset.found)return;

      h.dataset.found="1";
      h.style.opacity=".25";

      found++;

      document.getElementById("huntFound").textContent=found;

      if(found>=10){
        addScore(130);
        addTokens(4);
        completeLevel(14,0);
      }
    };

    area.appendChild(h);
  }
}

/* =========================================================
   GAME 15 — LOVE LOCK
   ========================================================= */

function initGame15(){

  const root=document.querySelector("#game15 .play-area");

  root.innerHTML=`
    <div class="center">

      <div class="notice">
        🔐 Find the six-digit combination.<br><br>
        Liliana's birthday is <b>July 22</b>,
        and you have been best friends for <b>6 years</b>.
      </div>

      <div id="lockDisplay" class="lock-display">______</div>

      <div id="keypad" class="keypad"></div>

      <div id="lockMessage" class="message"></div>
    </div>
  `;

  const display=document.getElementById("lockDisplay");
  const keypad=document.getElementById("keypad");

  let value="";

  for(let i=1;i<=9;i++){
    createKey(i);
  }

  createKey(0);

  function createKey(n){

    const b=document.createElement("button");
    b.className="key";
    b.textContent=n;

    b.onclick=()=>{

      if(value.length>=6)return;

      value+=n;
      display.textContent=value.padEnd(6,"_");

      if(value.length===6){

        if(value==="060722"){

          document.getElementById("lockMessage").textContent=
            "🔓 LOCK OPEN!";

          addScore(160);
          addTokens(5);
          completeLevel(15,0);

        }else{

          document.getElementById("lockMessage").textContent=
            "Wrong combination. Try again.";

          timer(()=>{
            value="";
            display.textContent="______";
          },600);
        }
      }
    };

    keypad.appendChild(b);
  }
}

/* =========================================================
   GAME 16 — CUPID SHOOTOUT
   ========================================================= */

function initGame16(){

  const root=document.querySelector("#game16 .play-area");

  root.innerHTML=`
    <div class="center">
      <div class="statline">
        Score <b id="shootScore">0</b>/80
        • Hits <b id="shootHits">0</b>
      </div>

      <div id="shootArea" class="shoot-area"></div>

      <div id="shootMessage" class="message">
        Tap the hearts!
      </div>
    </div>
  `;

  const area=document.getElementById("shootArea");

  let score=0;
  let hits=0;

  for(let i=0;i<15;i++){

    const target=document.createElement("button");
    target.className="shoot-target";

    target.textContent=
      Math.random()<.18 ? "💛" : "💗";

    target.style.left=(5+Math.random()*85)+"%";
    target.style.top=(5+Math.random()*82)+"%";

    target.onclick=()=>{

      if(target.dataset.hit)return;

      target.dataset.hit="1";
      target.style.transform="scale(1.6)";
      target.style.opacity=".2";

      const points=target.textContent==="💛"?20:10;

      score+=points;
      hits++;

      document.getElementById("shootScore").textContent=score;
      document.getElementById("shootHits").textContent=hits;

      if(score>=80 || hits>=10){

        addScore(score);
        addTokens(4);
        completeLevel(16,0);
      }
    };

    area.appendChild(target);
  }
}

/* =========================================================
   GAME 17 — THE COUNTDOWN
   Six mini-games.
   ========================================================= */

function initGame17(){

  const root=document.querySelector("#game17 .play-area");

  root.innerHTML=`
    <div class="center">
      <div class="statline">
        Challenge <b id="countChallenge">1</b>/6
        • Passed <b id="countPassed">0</b>
      </div>

      <h2 id="countTitle"></h2>

      <div id="countContent"></div>

      <div id="countMessage" class="message"></div>
    </div>
  `;

  let challenge=0;
  let passed=0;

  function next(){

    challenge++;

    if(challenge>6){

      if(passed>=4){
        addScore(130);
        addTokens(4);
        completeLevel(17,0);
      }else{
        timer(initGame17,700);
      }

      return;
    }

    document.getElementById("countChallenge").textContent=challenge;

    const content=document.getElementById("countContent");
    content.innerHTML="";

    if(challenge===1){
      stopBar(content);
    }else if(challenge===2){
      tapThree(content);
    }else if(challenge===3){
      greenRed(content);
    }else if(challenge===4){
      smallest(content);
    }else if(challenge===5){
      holdRelease(content);
    }else{
      miniMemory(content);
    }
  }

  function success(){
    passed++;
    document.getElementById("countPassed").textContent=passed;
    document.getElementById("countMessage").textContent="Passed! 💗";
    timer(next,450);
  }

  function fail(){
    document.getElementById("countMessage").textContent="Missed!";
    timer(next,450);
  }

  function stopBar(box){

    document.getElementById("countTitle").textContent=
      "Stop the pointer in the green zone!";

    box.innerHTML=`
      <div class="mini-bar">
        <div class="mini-zone"></div>
        <div id="miniPointer" class="mini-pointer"></div>
      </div>

      <button class="primary" id="stopMini">
        STOP
      </button>
    `;

    let p=0;
    let d=1;

    function animate(){

      p+=d*3;

      if(p>=100){
        p=100;
        d=-1;
      }

      if(p<=0){
        p=0;
        d=1;
      }

      document.getElementById("miniPointer").style.left=p+"%";

      requestAnimationFrame(animate);
    }

    animate();

    document.getElementById("stopMini").onclick=()=>{
      if(p>=42 && p<=58)success();
      else fail();
    };
  }

  function tapThree(box){

    document.getElementById("countTitle").textContent=
      "Tap the circles in order!";

    box.innerHTML="";

    let current=1;

    for(let i=1;i<=3;i++){

      const b=document.createElement("button");
      b.className="primary";
      b.style.margin="6px";
      b.textContent=i;

      b.onclick=()=>{
        if(i===current){
          b.disabled=true;
          current++;

          if(current===4)success();
        }else{
          fail();
        }
      };

      box.appendChild(b);
    }
  }

  function greenRed(box){

    document.getElementById("countTitle").textContent=
      "Tap GREEN. Avoid RED.";

    const b=document.createElement("button");
    b.className="reaction-button";
    b.textContent=Math.random()<.65?"GREEN":"RED";

    box.appendChild(b);

    b.onclick=()=>{
      if(b.textContent==="GREEN")success();
      else fail();
    };
  }

  function smallest(box){

    document.getElementById("countTitle").textContent=
      "Tap the smallest number.";

    const nums=[3,9,5,7].sort(()=>Math.random()-.5);

    nums.forEach(n=>{
      const b=document.createElement("button");
      b.className="secondary";
      b.style.margin="5px";
      b.textContent=n;

      b.onclick=()=>{
        if(n===3)success();
        else fail();
      };

      box.appendChild(b);
    });
  }

  function holdRelease(box){

    document.getElementById("countTitle").textContent=
      "Hold the button until the meter reaches the middle.";

    box.innerHTML=`
      <div class="mini-bar">
        <div class="mini-zone"></div>
        <div id="holdPointer" class="mini-pointer"></div>
      </div>
      <button class="primary" id="holdBtn">HOLD</button>
    `;

    let p=0;
    let holding=false;

    const b=document.getElementById("holdBtn");

    const down=e=>{
      e.preventDefault();
      holding=true;
    };

    const up=e=>{
      e.preventDefault();
      holding=false;

      if(p>=40 && p<=60)success();
      else fail();
    };

    b.addEventListener("pointerdown",down);
    b.addEventListener("pointerup",up);
    b.addEventListener("pointercancel",up);

    cleanupFns.push(()=>{
      b.removeEventListener("pointerdown",down);
      b.removeEventListener("pointerup",up);
      b.removeEventListener("pointercancel",up);
    });

    function tick(){
      if(holding){
        p+=2;

        if(p>100)p=0;

        document.getElementById("holdPointer").style.left=p+"%";
      }

      requestAnimationFrame(tick);
    }

    tick();
  }

  function miniMemory(box){

    document.getElementById("countTitle").textContent=
      "Remember the 3-button sequence.";

    const seq=[
      Math.floor(Math.random()*3),
      Math.floor(Math.random()*3),
      Math.floor(Math.random()*3)
    ];

    box.innerHTML="";

    const buttons=[];

    for(let i=0;i<3;i++){
      const b=document.createElement("button");
      b.className="secondary";
      b.textContent="♡";
      b.style.margin="5px";

      buttons.push(b);
      box.appendChild(b);
    }

    seq.forEach((n,i)=>{
      timer(()=>{
        buttons[n].style.background="#d94d8c";

        timer(()=>{
          buttons[n].style.background="";
        },250);
      },i*400);
    });

    let pos=0;

    timer(()=>{

      buttons.forEach((b,i)=>{
        b.onclick=()=>{
          if(i===seq[pos]){
            pos++;

            if(pos===seq.length)success();
          }else{
            fail();
          }
        };
      });

    },1400);
  }

  next();
}

/* =========================================================
   GAME 18 — ULTIMATE GAMBLE
   ========================================================= */

function initGame18(){

  const root=document.querySelector("#game18 .play-area");

  root.innerHTML=`
    <div class="center">

      <div class="big">
        Pot: <span id="gamblePot">100</span>
      </div>

      <p id="gambleMessage">
        Reach 300 or cash out with more than 100.
      </p>

      <div class="game-actions">
        <button class="primary" id="safeGamble">
          50/50 ×2
        </button>

        <button class="secondary" id="riskyGamble">
          25% ×4
        </button>

        <button class="secondary" id="cashGamble">
          💰 Cash Out
        </button>
      </div>
    </div>
  `;

  let pot=100;

  function update(){
    document.getElementById("gamblePot").textContent=pot;
  }

  function check(){

    if(pot>=300){
      addScore(pot);
      addTokens(6);
      completeLevel(18,0);
      return true;
    }

    return false;
  }

  document.getElementById("safeGamble").onclick=()=>{

    if(Math.random()<.5){
      pot*=2;
      document.getElementById("gambleMessage").textContent=
        "🎉 Double!";
    }else{
      pot=Math.floor(pot/2);
      document.getElementById("gambleMessage").textContent=
        "Ouch! You lost half.";
    }

    update();
    check();
  };

  document.getElementById("riskyGamble").onclick=()=>{

    if(Math.random()<.25){
      pot*=4;
      document.getElementById("gambleMessage").textContent=
        "🔥 HUGE WIN!";
    }else{
      pot=0;
      document.getElementById("gambleMessage").textContent=
        "You lost the risky gamble.";
    }

    update();

    if(pot>=300)check();

    if(pot===0){
      timer(initGame18,700);
    }
  };

  document.getElementById("cashGamble").onclick=()=>{

    if(pot>100){
      addScore(pot);
      addTokens(4);
      completeLevel(18,0);
    }else{
      document.getElementById("gambleMessage").textContent=
        "Build the pot above 100 first!";
    }
  };

  update();
}

/* =========================================================
   GAME 19 — ADMIRER'S LAST STAND
   ========================================================= */

function initGame19(){

  const root=document.querySelector("#game19 .play-area");

  root.innerHTML=`
    <div class="center">

      <div>👑 Boss Health</div>

      <div class="hpbar">
        <div id="bossHP" class="hpfill"></div>
      </div>

      <div class="big" id="bossPhase">PHASE 1</div>

      <p id="bossMessage">
        The Admirer approaches...
      </p>

      <div class="fight-buttons">
        <button class="primary" id="bossAttack">⚔️ Attack</button>
        <button class="secondary" id="bossGuard">🛡️ Guard</button>
        <button class="primary" id="bossSpecial">💗 Special</button>
      </div>
    </div>
  `;

  let hp=120;
  let guard=false;
  let specialReady=true;

  function update(){

    document.getElementById("bossHP").style.width=
      Math.max(0,hp/120*100)+"%";

    if(hp>80){
      document.getElementById("bossPhase").textContent="PHASE 1";
    }else if(hp>40){
      document.getElementById("bossPhase").textContent="PHASE 2";
    }else{
      document.getElementById("bossPhase").textContent="PHASE 3";
    }

    if(hp<=0){
      addScore(200);
      addTokens(6);
      completeLevel(19,0);
    }
  }

  function bossMove(){

    if(hp<=0)return;

    let damage=10+Math.floor(Math.random()*8);

    if(guard){
      damage=Math.floor(damage/2);
      guard=false;
    }

    document.getElementById("bossMessage").textContent=
      `The boss strikes for ${damage}!`;

    update();
  }

  document.getElementById("bossAttack").onclick=()=>{
    hp-=12;
    document.getElementById("bossMessage").textContent=
      "Direct hit! ⚔️";
    bossMove();
  };

  document.getElementById("bossGuard").onclick=()=>{
    guard=true;
    document.getElementById("bossMessage").textContent=
      "You prepare to guard.";
  };

  document.getElementById("bossSpecial").onclick=()=>{
    if(!specialReady)return;

    specialReady=false;
    hp-=30;

    document.getElementById("bossMessage").textContent=
      "💗 HEART SPECIAL!";

    update();

    timer(()=>{
      specialReady=true;
    },1800);
  };

  update();
}

/* =========================================================
   GAME 20 — WORD FIND
   ========================================================= */

const wordList=[
"LILIANA","LULU","FRIENDS","PINK","DOLPHIN",
"SUNFLOWER","ROSE","SUSHI","POETRY","MUSIC",
"PSYCHOLOGY","LEO","JULY","LOVE","FAMILY",
"HEART","DREAM","AAYLA","ARLO","OCEAN",
"FOREVER","THREE","SIXYEARS","CHARM","EMPATHY"
];

function initGame20(){

  const root=document.querySelector("#game20 .play-area");

  root.innerHTML=`
    <div class="center">
      <div class="statline">
        Found <b id="wordsFound">0</b>/25
      </div>

      <div id="wordGrid" class="word-grid"></div>

      <div id="wordsList" class="words-list"></div>

      <div id="wordMessage" class="message">
        Drag across a word in any direction.
      </div>
    </div>
  `;

  const size=14;
  const grid=Array.from(
    {length:size},
    ()=>Array(size).fill("")
  );

  const placed={};

  const directions=[
    [0,1],
    [0,-1],
    [1,0],
    [-1,0],
    [1,1],
    [1,-1],
    [-1,1],
    [-1,-1]
  ];

  function canPlace(word,r,c,dr,dc){

    for(let i=0;i<word.length;i++){

      const rr=r+dr*i;
      const cc=c+dc*i;

      if(rr<0||rr>=size||cc<0||cc>=size)return false;

      if(grid[rr][cc] &&
         grid[rr][cc]!==word[i]){
        return false;
      }
    }

    return true;
  }

  function placeWord(word){

    for(let attempt=0;attempt<1000;attempt++){

      const d=directions[
        Math.floor(Math.random()*directions.length)
      ];

      const r=Math.floor(Math.random()*size);
      const c=Math.floor(Math.random()*size);

      if(canPlace(word,r,c,d[0],d[1])){

        const cells=[];

        for(let i=0;i<word.length;i++){

          const rr=r+d[0]*i;
          const cc=c+d[1]*i;

          grid[rr][cc]=word[i];

          cells.push(`${rr},${cc}`);
        }

        placed[word]=cells;
        return true;
      }
    }

    return false;
  }

  [...wordList]
    .sort((a,b)=>b.length-a.length)
    .forEach(placeWord);

  const letters="ABCDEFGHIJKLMNOPQRSTUVWXYZ";

  for(let r=0;r<size;r++){
    for(let c=0;c<size;c++){

      if(!grid[r][c]){
        grid[r][c]=letters[
          Math.floor(Math.random()*letters.length)
        ];
      }
    }
  }

  const gridEl=document.getElementById("wordGrid");

  for(let r=0;r<size;r++){
    for(let c=0;c<size;c++){

      const cell=document.createElement("div");

      cell.className="word-letter";
      cell.textContent=grid[r][c];
      cell.dataset.r=r;
      cell.dataset.c=c;

      gridEl.appendChild(cell);
    }
  }

  const listEl=document.getElementById("wordsList");

  wordList.forEach(word=>{
    const tag=document.createElement("div");
    tag.className="word-tag";
    tag.textContent=word;
    tag.id="tag-"+word;
    listEl.appendChild(tag);
  });

  let startCell=null;
  let selecting=false;

  function cellFromPoint(x,y){

    const el=document.elementFromPoint(x,y);

    if(!el || !el.classList.contains("word-letter")){
      return null;
    }

    return el;
  }

  function getLine(a,b){

    const r1=Number(a.dataset.r);
    const c1=Number(a.dataset.c);

    const r2=Number(b.dataset.r);
    const c2=Number(b.dataset.c);

    const dr=Math.sign(r2-r1);
    const dc=Math.sign(c2-c1);

    if(
      !(r1===r2 ||
        c1===c2 ||
        Math.abs(r2-r1)===Math.abs(c2-c1))
    ){
      return [];
    }

    const length=Math.max(
      Math.abs(r2-r1),
      Math.abs(c2-c1)
    )+1;

    const cells=[];

    for(let i=0;i<length;i++){

      const r=r1+dr*i;
      const c=c1+dc*i;

      cells.push(
        gridEl.children[r*size+c]
      );
    }

    return cells;
  }

  function selectLine(a,b){

    const cells=getLine(a,b);

    [...gridEl.children].forEach(c=>{
      c.classList.remove("selected");
    });

    cells.forEach(c=>{
      if(c)c.classList.add("selected");
    });

    return cells;
  }

  function finishSelection(a,b){

    if(!a||!b)return;

    const cells=selectLine(a,b);

    const word=cells.map(c=>c.textContent).join("");

    const reversed=word.split("").reverse().join("");

    let foundWord=null;

    for(const w of wordList){

      if(!document.getElementById("tag-"+w).classList.contains("found")){

        if(w===word || w===reversed){
          foundWord=w;
          break;
        }
      }
    }

    if(foundWord){

      cells.forEach(c=>c.classList.add("found"));

      document.getElementById("tag-"+foundWord)
        .classList.add("found");

      const count=
        document.querySelectorAll(".word-tag.found").length;

      document.getElementById("wordsFound").textContent=count;

      if(count===25){

        addScore(200);
        addTokens(7);
        completeLevel(20,0);
      }
    }
  }

  gridEl.addEventListener("pointerdown",e=>{

    const cell=cellFromPoint(e.clientX,e.clientY);

    if(!cell)return;

    e.preventDefault();

    startCell=cell;
    selecting=true;

    try{gridEl.setPointerCapture(e.pointerId)}catch(err){}
  },{passive:false});

  gridEl.addEventListener("pointermove",e=>{

    if(!selecting)return;

    const cell=cellFromPoint(e.clientX,e.clientY);

    if(cell){
      selectLine(startCell,cell);
    }

    e.preventDefault();

  },{passive:false});

  gridEl.addEventListener("pointerup",e=>{

    if(!selecting)return;

    const cell=cellFromPoint(e.clientX,e.clientY);

    selecting=false;

    finishSelection(startCell,cell);

    startCell=null;

    e.preventDefault();

  },{passive:false});
}

/* =========================================================
   GAME 21 — DRAW A SUNFLOWER
   ========================================================= */

function initGame21(){

  const root=document.querySelector("#game21 .play-area");

  root.innerHTML=`
    <div class="center">

      <p>Draw a sunflower 🌻</p>

      <canvas id="drawCanvas"></canvas>

      <div class="draw-tools">
        <button class="secondary" data-size="3">Thin</button>
        <button class="secondary" data-size="7">Medium</button>
        <button class="secondary" data-size="14">Thick</button>
        <button class="secondary" id="undoDraw">↩️</button>
        <button class="secondary" id="clearDraw">Clear</button>
      </div>

      <button class="primary" id="finishDraw">
        🌻 Finish Flower
      </button>

      <div id="drawMessage" class="message"></div>
    </div>
  `;

  const canvas=document.getElementById("drawCanvas");
  const ctx=canvas.getContext("2d");

  function resize(){

    const rect=canvas.getBoundingClientRect();

    const ratio=window.devicePixelRatio||1;

    canvas.width=rect.width*ratio;
    canvas.height=rect.height*ratio;

    ctx.scale(ratio,ratio);

    ctx.lineCap="round";
    ctx.lineJoin="round";
  }

  resize();

  let drawing=false;
  let size=7;
  let strokes=0;
  let history=[];

  function position(e){

    const r=canvas.getBoundingClientRect();

    return {
      x:e.clientX-r.left,
      y:e.clientY-r.top
    };
  }

  canvas.addEventListener("pointerdown",e=>{

    e.preventDefault();

    drawing=true;
    strokes++;

    const p=position(e);

    ctx.beginPath();
    ctx.moveTo(p.x,p.y);

    try{canvas.setPointerCapture(e.pointerId)}catch(err){}

  },{passive:false});

  canvas.addEventListener("pointermove",e=>{

    if(!drawing)return;

    e.preventDefault();

    const p=position(e);

    ctx.lineWidth=size;
    ctx.strokeStyle="#b43d72";

    ctx.lineTo(p.x,p.y);
    ctx.stroke();

  },{passive:false});

  const end=e=>{
    if(!drawing)return;

    drawing=false;

    try{
      history.push(ctx.getImageData(
        0,0,canvas.width,canvas.height
      ));
    }catch(err){}
  };

  canvas.addEventListener("pointerup",end);
  canvas.addEventListener("pointercancel",end);

  document.querySelectorAll("[data-size]").forEach(b=>{
    b.onclick=()=>{
      size=Number(b.dataset.size);
    };
  });

  document.getElementById("undoDraw").onclick=()=>{

    if(history.length){
      history.pop();

      ctx.clearRect(
        0,0,
        canvas.width,
        canvas.height
      );

      if(history.length){
        ctx.putImageData(history[history.length-1],0,0);
      }
    }
  };

  document.getElementById("clearDraw").onclick=()=>{

    ctx.clearRect(
      0,0,
      canvas.width,
      canvas.height
    );

    history=[];
    strokes=0;
  };

  document.getElementById("finishDraw").onclick=()=>{

    if(strokes<8){
      document.getElementById("drawMessage").textContent=
        "Add a few more strokes to your sunflower! 🌻";
      return;
    }

    addScore(150);
    addTokens(5);
    completeLevel(21,0);
  };
}

/* =========================================================
   DERBY QUESTIONS — 100 MIXED QUESTIONS
   ========================================================= */

const derbyQuestions=[
{q:"What is the capital of Canada?",o:["Ottawa","Toronto","Vancouver","Montreal"],a:0},
{q:"What is the largest mammal?",o:["Elephant","Blue whale","Giraffe","Orca"],a:1},
{q:"How many months are in a year?",o:["10","11","12","13"],a:2},
{q:"What is the currency of the United Kingdom?",o:["Euro","Pound sterling","Dollar","Franc"],a:1},
{q:"Which planet is closest to the Sun?",o:["Venus","Earth","Mercury","Mars"],a:2},
{q:"How many chess pieces does each player start with?",o:["12","14","16","18"],a:2},
{q:"Who wrote the Harry Potter books?",o:["J.K. Rowling","Suzanne Collins","C.S. Lewis","Roald Dahl"],a:0},
{q:"What is the largest continent?",o:["Africa","Europe","Asia","North America"],a:2},
{q:"Which instrument normally has 88 keys?",o:["Violin","Piano","Trumpet","Flute"],a:1},
{q:"What is the chemical symbol for oxygen?",o:["Ox","O","Og","On"],a:1},
{q:"What is the square root of 81?",o:["7","8","9","10"],a:2},
{q:"In what year did humans first land on the Moon?",o:["1959","1969","1979","1989"],a:1},
{q:"The Great Pyramid is at Giza in which country?",o:["Egypt","Greece","Turkey","Jordan"],a:0},
{q:"What is the main language of Brazil?",o:["Spanish","Portuguese","French","Italian"],a:1},
{q:"What is the world's largest desert?",o:["Sahara","Gobi","Antarctic Desert","Arabian Desert"],a:2},
{q:"Which sport uses the score terms love, 15, 30 and 40?",o:["Tennis","Cricket","Rugby","Golf"],a:0},
{q:"Which vitamin is commonly produced in skin through sunlight exposure?",o:["Vitamin A","Vitamin C","Vitamin D","Vitamin K"],a:2},
{q:"Approximately how many bones are in an adult human body?",o:["106","206","306","406"],a:1},
{q:"The Amazon rainforest is primarily in which continent?",o:["Africa","Asia","South America","Europe"],a:2},
{q:"Big Ben is associated with which city?",o:["London","Dublin","Paris","Edinburgh"],a:0},
{q:"How many moons does Mars have?",o:["1","2","3","4"],a:1},
{q:"Which planet is the hottest in our solar system?",o:["Mercury","Venus","Mars","Jupiter"],a:1},
{q:"Approximately how fast does light travel in vacuum?",o:["30,000 km/s","300,000 km/s","3,000 km/s","3,000,000 km/s"],a:1},
{q:"Who wrote Romeo and Juliet?",o:["Shakespeare","Dickens","Austen","Homer"],a:0},
{q:"Which animal is strongly associated with Antarctica?",o:["Penguin","Camel","Panda","Kangaroo"],a:0},
{q:"What is India's currency?",o:["Rupee","Rial","Yen","Peso"],a:0},
{q:"The Taj Mahal is in which country?",o:["India","Pakistan","Nepal","Bangladesh"],a:0},
{q:"Who was the Greek god of the sea?",o:["Zeus","Apollo","Poseidon","Hermes"],a:2},
{q:"What number does the Roman numeral X represent?",o:["5","10","15","20"],a:1},
{q:"How many rings are on the Olympic symbol?",o:["4","5","6","7"],a:1},
{q:"How many suits are in a standard deck of cards?",o:["2","3","4","5"],a:2},
{q:"How many cards are in a standard deck?",o:["48","50","52","54"],a:2},
{q:"How many sides does a square have?",o:["3","4","5","6"],a:1},
{q:"The Nile is primarily associated with which continent?",o:["Africa","Asia","Europe","South America"],a:0},
{q:"The Alps are mainly in which part of the world?",o:["Europe","Africa","Australia","South America"],a:0},
{q:"At approximately what temperature does water freeze?",o:["0°C","10°C","32°C","50°C"],a:0},
{q:"How many metres are in one kilometre?",o:["100","500","1000","1500"],a:2},
{q:"How many seconds are in a minute?",o:["30","45","60","90"],a:2},
{q:"How many hours are in a day?",o:["12","18","24","36"],a:2},
{q:"How many days are normally in a week?",o:["5","6","7","8"],a:2},
{q:"Which planet is farthest from the Sun among the eight planets?",o:["Uranus","Neptune","Saturn","Jupiter"],a:1},
{q:"What is Pluto classified as?",o:["Planet","Star","Dwarf planet","Moon"],a:2},
{q:"What shape is DNA commonly described as having?",o:["Single spiral","Double helix","Triangle","Cube"],a:1},
{q:"What process allows green plants to make food using light?",o:["Respiration","Photosynthesis","Fermentation","Digestion"],a:1},
{q:"Which organs are primarily used for breathing?",o:["Kidneys","Lungs","Stomach","Liver"],a:1},
{q:"What do red blood cells primarily carry?",o:["Oxygen","Bones","Food","Hair"],a:0},
{q:"What part of the eye controls how much light enters?",o:["Iris","Retina","Cornea","Lens"],a:0},
{q:"Which organ is responsible for many higher thinking functions?",o:["Heart","Brain","Lung","Kidney"],a:1},
{q:"What is the chemical symbol for iron?",o:["Ir","Fe","In","I"],a:1},
{q:"What is the chemical symbol for sodium?",o:["So","S","Na","Sd"],a:2},
{q:"What is the chemical symbol for potassium?",o:["P","Pt","K","Po"],a:2},
{q:"What is the chemical symbol for silver?",o:["Si","Ag","Au","Sr"],a:1},
{q:"What is the chemical symbol for copper?",o:["Co","Cp","Cu","Cr"],a:2},
{q:"What is CO₂?",o:["Oxygen","Carbon dioxide","Carbon monoxide","Methane"],a:1},
{q:"A pH of 7 is generally considered what?",o:["Acidic","Neutral","Alkaline only","Radioactive"],a:1},
{q:"Which force pulls objects toward Earth?",o:["Magnetism","Gravity","Friction","Pressure"],a:1},
{q:"What is the SI unit of energy?",o:["Joule","Watt","Volt","Newton"],a:0},
{q:"What is the SI unit of electric current?",o:["Ampere","Joule","Ohm","Tesla"],a:0},
{q:"Sound level is commonly measured in what?",o:["Decibels","Litres","Watts","Metres"],a:0},
{q:"What instrument detects and records earthquakes?",o:["Thermometer","Seismometer","Barometer","Compass"],a:1},
{q:"Molten rock beneath Earth's surface is called what?",o:["Lava","Magma","Ash","Granite"],a:1},
{q:"Clouds are mainly made of what?",o:["Sand","Water droplets and/or ice","Smoke","Salt"],a:1},
{q:"How many commonly taught colours are in a rainbow?",o:["5","6","7","8"],a:2},
{q:"What symmetry do typical snowflakes have?",o:["Five-fold","Six-fold","Eight-fold","Ten-fold"],a:1},
{q:"How do honey bees famously communicate locations?",o:["Dance","Whistling","Singing","Colouring"],a:0},
{q:"Butterflies have taste receptors on which body part?",o:["Feet","Wings","Eyes","Antennae only"],a:0},
{q:"How many hearts does an octopus have?",o:["1","2","3","4"],a:2},
{q:"How many neck vertebrae does a giraffe normally have?",o:["5","7","9","12"],a:1},
{q:"Which bird is the largest living bird?",o:["Eagle","Ostrich","Albatross","Swan"],a:1},
{q:"Which country is strongly associated with kangaroos?",o:["Australia","Canada","India","Brazil"],a:0},
{q:"Which bird is native to New Zealand?",o:["Kiwi","Emu","Toucan","Flamingo"],a:0},
{q:"Koalas are native to which country?",o:["Australia","New Zealand","Japan","South Africa"],a:0},
{q:"Mount Kilimanjaro is in which country?",o:["Kenya","Tanzania","Ethiopia","Uganda"],a:1},
{q:"The Gobi Desert is mainly in which region?",o:["Asia","Africa","Europe","South America"],a:0},
{q:"The Mediterranean Sea lies between Europe and which other major regions?",o:["Africa and Asia","Australia and Asia","North America and Asia","Antarctica and Africa"],a:0},
{q:"The Panama Canal connects the Atlantic and which ocean?",o:["Pacific","Indian","Arctic","Southern"],a:0},
{q:"The Suez Canal connects the Mediterranean Sea with which sea?",o:["Red Sea","Black Sea","Caribbean Sea","Baltic Sea"],a:0},
{q:"The Prime Meridian passes through which London district?",o:["Greenwich","Chelsea","Soho","Camden"],a:0},
{q:"What latitude is the Equator?",o:["0°","23.5°","45°","90°"],a:0},
{q:"The Tropic of Cancer is in which hemisphere?",o:["Northern","Southern","Eastern only","Western only"],a:0},
{q:"Which continent is the coldest?",o:["Europe","Antarctica","Asia","Australia"],a:1},
{q:"Which is the smallest continent by land area?",o:["Australia","Europe","Antarctica","South America"],a:0},
{q:"Which country is the smallest by land area?",o:["Monaco","Vatican City","Malta","Liechtenstein"],a:1},
{q:"Which country has the largest land area?",o:["China","Canada","Russia","Brazil"],a:2},
{q:"Which sport is played at Wimbledon?",o:["Tennis","Football","Cricket","Rugby"],a:0},
{q:"The FIFA World Cup is associated with which sport?",o:["Football","Tennis","Basketball","Golf"],a:0},
{q:"The Tour de France is primarily what?",o:["Cycling race","Horse race","Car race","Running race"],a:0},
{q:"The Super Bowl is associated with which sport?",o:["American football","Baseball","Basketball","Ice hockey"],a:0},
{q:"How many players are on the field for one football team during normal play?",o:["9","10","11","12"],a:2},
{q:"Which sport uses a shuttlecock?",o:["Badminton","Tennis","Squash","Table tennis"],a:0},
{q:"Which board game uses kings, queens, rooks and bishops?",o:["Chess","Cluedo","Monopoly","Risk"],a:0},
{q:"What colour do you get by mixing blue and yellow paint?",o:["Green","Purple","Orange","Pink"],a:0},
{q:"How many degrees are in a right angle?",o:["45","90","120","180"],a:1},
{q:"How many sides does a pentagon have?",o:["4","5","6","7"],a:1},
{q:"Which metal is liquid at ordinary room temperature?",o:["Iron","Mercury","Copper","Silver"],a:1},
{q:"What is the nearest star to Earth?",o:["Sirius","The Sun","Polaris","Betelgeuse"],a:1},
{q:"What is Earth's natural satellite?",o:["Mars","The Moon","Venus","Europa"],a:1},
{q:"Which direction does a compass needle generally point toward?",o:["North","South","East","West"],a:0},
{q:"How many letters are in the English alphabet?",o:["24","25","26","27"],a:2}
];

/* =========================================================
   GAME 22 — LULU DERBY
   ========================================================= */

function initGame22(){

  const root=document.querySelector("#game22 .play-area");

  root.innerHTML=`
    <div id="derbyChoose">
      <div class="center">
        <h2>Choose your horse 🏇</h2>
        <p>Answer 100 random trivia questions to race your horse to victory.</p>

        <div id="horseGrid" class="horse-grid"></div>
      </div>
    </div>

    <div id="derbyPlay" style="display:none">

      <div class="statline">
        <span>Question <b id="derbyQ">1</b>/100</span>
        <span>Horse: <b id="derbyHorseName"></b></span>
      </div>

      <div class="track" id="derbyTrack"></div>

      <h3 id="derbyQuestion"></h3>

      <div id="derbyChoices" class="choice-grid"></div>

      <div id="derbyMessage" class="message"></div>

    </div>
  `;

  const horses=[
    ["🌸","Pink Star"],
    ["💗","Love Bug"],
    ["🌻","Sunshine"],
    ["💎","Lucky Lulu"]
  ];

  const horseGrid=document.getElementById("horseGrid");

  let chosen=-1;
  let distances=[0,0,0,0];
  let questionIndex=0;
  let questions=[];

  horses.forEach((h,i)=>{

    const b=document.createElement("button");

    b.className="horse";
    b.innerHTML=`${h[0]}<br><b>${h[1]}</b>`;

    b.onclick=()=>{

      chosen=i;

      [...horseGrid.children].forEach(x=>
        x.classList.remove("selected")
      );

      b.classList.add("selected");

      timer(startRace,300);
    };

    horseGrid.appendChild(b);
  });

  function startRace(){

    if(chosen<0)return;

    questions=[...derbyQuestions]
      .sort(()=>Math.random()-.5);

    document.getElementById("derbyChoose").style.display="none";
    document.getElementById("derbyPlay").style.display="block";

    document.getElementById("derbyHorseName").textContent=
      horses[chosen][1];

    renderTrack();
    nextQuestion();
  }

  function renderTrack(){

    const track=document.getElementById("derbyTrack");

    track.innerHTML="";

    horses.forEach((h,i)=>{

      track.innerHTML+=`
        <div class="track-row">
          <div>${h[0]} ${i===chosen?"YOU":""}</div>
          <div class="track-line">
            <div
              id="horse${i}"
              class="horse-run"
            ></div>
          </div>
        </div>
      `;
    });
  }

  function updateTrack(){

    horses.forEach((h,i)=>{
      document.getElementById(`horse${i}`).style.width=
        Math.min(100,distances[i])+"%";
    });
  }

  function nextQuestion(){

    if(questionIndex>=100){
      finishDerby();
      return;
    }

    const q=questions[questionIndex];

    document.getElementById("derbyQ").textContent=
      questionIndex+1;

    document.getElementById("derbyQuestion").textContent=q.q;

    const answers=shuffledQuestion({
      q:q.q,
      options:q.o,
      answer:q.a
    });

    const box=document.getElementById("derbyChoices");

    box.innerHTML="";

    answers.forEach(a=>{

      const b=document.createElement("button");

      b.className="choice";
      b.textContent=a.text;

      b.onclick=()=>{

        [...box.children].forEach(x=>x.disabled=true);

        if(a.correct){

          b.classList.add("correct");

          distances[chosen]+=
            3+Math.floor(Math.random()*3);

          document.getElementById("derbyMessage").textContent=
            "Correct! Your horse surges ahead! 🏇💗";

          addTokens(1);

        }else{

          b.classList.add("wrong");

          distances[chosen]+=1;

          const rival=(chosen+1+
            Math.floor(Math.random()*3))%4;

          distances[rival]+=
            2+Math.floor(Math.random()*2);

          document.getElementById("derbyMessage").textContent=
            "Not quite! Keep racing!";
        }

        updateTrack();

        questionIndex++;

        timer(nextQuestion,180);
      };

      box.appendChild(b);
    });
  }

  function finishDerby(){

    updateTrack();

    const winner=distances.indexOf(
      Math.max(...distances)
    );

    if(winner===chosen){

      addScore(300);
      addTokens(20);
      completeLevel(22,0);

      document.getElementById("derbyMessage").textContent=
        `🏆 ${horses[chosen][1]} WINS THE LULU DERBY!`;

    }else{

      document.getElementById("derbyMessage").textContent=
        `The winner was ${horses[winner][1]}. Try the Derby again!`;

      timer(initGame22,1200);
    }
  }
}

/* =========================================================
   GAME 23 — FINAL CHALLENGE
   50 UNIQUE LILIANA QUESTIONS
   ========================================================= */

const finalQuestions=[
{
q:"Which colour best matches Liliana's favourite colour?",
o:["Baby pink","Burgundy","Navy","Emerald"],
a:0
},
{
q:"What number has special significance as Liliana's favourite number?",
o:["2","3","6","9"],
a:1
},
{
q:"Which food is one of Liliana's favourites?",
o:["Sushi","Pizza","Pasta","Burgers"],
a:0
},
{
q:"Which sea animal does Liliana like?",
o:["Dolphins","Seals","Whales","Turtles"],
a:0
},
{
q:"Which pair of flowers does Liliana like?",
o:["Sunflowers and roses","Tulips and lilies","Orchids and violets","Daisies and lavender"],
a:0
},
{
q:"Which month contains Liliana's birthday?",
o:["July","June","August","September"],
a:0
},
{
q:"On which day of the month is Liliana's birthday?",
o:["12","17","22","27"],
a:2
},
{
q:"What colour are Liliana's eyes?",
o:["Green","Brown","Blue","Hazel"],
a:0
},
{
q:"Which zodiac sign is Liliana?",
o:["Leo","Cancer","Virgo","Libra"],
a:0
},
{
q:"Which fear is associated with Liliana?",
o:["Drowning","Flying","Heights","Thunder"],
a:0
},
{
q:"Which film is Liliana's favourite?",
o:["Me Before You","The Notebook","Titanic","About Time"],
a:0
},
{
q:"What kind of music does Liliana enjoy?",
o:["Sad songs","Only classical music","Only country music","Only metal"],
a:0
},
{
q:"What type of writing does Liliana enjoy?",
o:["Poetry","History textbooks","News reports","Travel guides"],
a:0
},
{
q:"Which games does Liliana enjoy?",
o:["Poker and gambling games","Only chess","Only racing games","Only word games"],
a:0
},
{
q:"What did Liliana study at university?",
o:["Psychology","Medicine","Engineering","Accounting"],
a:0
},
{
q:"How many nieces does Liliana have?",
o:["1","2","3","4"],
a:0
},
{
q:"How many nephews does Liliana have?",
o:["2","3","4","5"],
a:2
},
{
q:"How many siblings does Liliana have?",
o:["3","4","5","6"],
a:2
},
{
q:"How many piercings does Liliana have?",
o:["2","3","4","5"],
a:2
},
{
q:"Which name belongs to one of Liliana's dogs?",
o:["Aayla","Lola","Mika","Yuna"],
a:0
},
{
q:"Which other name belongs to one of Liliana's dogs?",
o:["Arlo","Kai","Rene","Mikael"],
a:0
},
{
q:"What is the total number of nieces and nephews Liliana has?",
o:["4","5","6","7"],
a:1
},
{
q:"How long have Bree and Liliana been best friends?",
o:["4 years","5 years","6 years","7 years"],
a:2
},
{
q:"Which personality trait is associated with Liliana?",
o:["Caring","Cold","Unfriendly","Uninterested"],
a:0
},
{
q:"Which other personality trait describes Liliana?",
o:["Charismatic","Distant","Impatient","Quietly hostile"],
a:0
},
{
q:"Which quality is associated with Liliana?",
o:["Empathetic","Careless","Selfish","Unkind"],
a:0
},
{
q:"Liliana is known for being particularly sweet and what?",
o:["Caring","Competitive","Strict","Serious"],
a:0
},
{
q:"What does Liliana like that is connected with children?",
o:["She likes children","She dislikes children","She avoids children","She has no interest in children"],
a:0
},
{
q:"What future family dream has Liliana talked about?",
o:["Being a mum to a baby girl","Owning a football team","Living on Mars","Opening a circus"],
a:0
},
{
q:"Which ocean-related dream is associated with Liliana?",
o:["Seeing the ocean someday","Living on a boat forever","Becoming a sailor","Owning a submarine"],
a:0
},
{
q:"Which colour would make the most sense for a Liliana-themed birthday design?",
o:["Baby pink","Black","Orange","Grey"],
a:0
},
{
q:"Which combination correctly describes two of Liliana's favourites?",
o:["Sushi and dolphins","Tacos and lions","Pizza and wolves","Pasta and bears"],
a:0
},
{
q:"Which combination correctly matches two things Liliana likes?",
o:["Sunflowers and poetry","Football and opera","Rugby and painting","Golf and science fiction"],
a:0
},
{
q:"Which combination correctly describes Liliana?",
o:["Green eyes and Leo","Blue eyes and Taurus","Brown eyes and Virgo","Hazel eyes and Gemini"],
a:0
},
{
q:"Which date represents Liliana's birthday?",
o:["22 July","12 June","27 August","6 July"],
a:0
},
{
q:"Which number combination represents the birthday month and day?",
o:["7 and 22","6 and 22","7 and 12","8 and 22"],
a:0
},
{
q:"Which pair are both of Liliana's dogs?",
o:["Aayla and Arlo","Aayla and Luna","Arlo and Max","Lola and Arlo"],
a:0
},
{
q:"Which university subject is connected with Liliana?",
o:["Psychology","Architecture","Physics","Economics"],
a:0
},
{
q:"Which statement about Liliana's flowers is correct?",
o:["She likes sunflowers and roses","She only likes orchids","She dislikes flowers","She only likes tulips"],
a:0
},
{
q:"Which statement about Liliana's hobbies is correct?",
o:["She likes poker and gambling games","She only likes swimming","She dislikes games","She only plays football"],
a:0
},
{
q:"Which statement about Liliana's music taste is correct?",
o:["She likes sad songs","She only listens to opera","She dislikes music","She only listens to marches"],
a:0
},
{
q:"Which statement about Liliana's creative interests is correct?",
o:["She likes poetry","She dislikes writing","She only reads textbooks","She only likes manuals"],
a:0
},
{
q:"Which statement about Liliana's family is correct?",
o:["She has 5 siblings","She has 2 siblings","She has 8 siblings","She is an only child"],
a:0
},
{
q:"Which statement about Liliana's pets is correct?",
o:["Her dogs are Aayla and Arlo","Her dogs are Luna and Bella","Her dog is called Max","She has no dogs"],
a:0
},
{
q:"Which statement about Liliana's birthday is correct?",
o:["It is July 22","It is June 22","It is July 12","It is August 22"],
a:0
},
{
q:"Which statement combines two correct Liliana facts?",
o:["She likes sushi and dolphins","She likes pizza and tigers","She likes curry and horses","She likes pasta and wolves"],
a:0
},
{
q:"Which statement combines her interests correctly?",
o:["She likes poetry and sad songs","She dislikes poetry and music","She only likes documentaries","She dislikes all songs"],
a:0
},
{
q:"Which statement about her university background is correct?",
o:["She studied Psychology","She studied Law","She studied Chemistry","She studied Engineering"],
a:0
},
{
q:"Which statement about her personality is correct?",
o:["She is sweet, caring and charismatic","She is cold and distant","She dislikes people","She avoids friendships"],
a:0
},
{
q:"Which statement about Liliana's future wishes is correct?",
o:["She would like to be a mum to a baby girl","She never wants children","She wants to avoid family life","She wants to live alone forever"],
a:0
},
{
q:"Which answer contains only things associated with Liliana?",
o:["Baby pink, dolphins, sushi","Orange, tigers, pizza","Purple, wolves, curry","Blue, horses, burgers"],
a:0
},
{
q:"Which description best brings together Liliana's known favourites and personality?",
o:["A caring, empathetic person who likes baby pink, dolphins, poetry and sushi","A person who dislikes flowers and games","A person who only likes sports","A person who dislikes music and children"],
a:0
}
];

function initGame23(){

  const root=document.querySelector("#game23 .play-area");

  root.innerHTML=`
    <div class="statline">
      <span>Question <b id="finalQ">1</b>/50</span>
      <span>Correct <b id="finalScore">0</b></span>
    </div>

    <div class="progress">
      <div id="finalProgress"></div>
    </div>

    <h2 id="finalQuestion" class="center"></h2>

    <div id="finalChoices" class="choice-grid"></div>

    <div id="finalMessage" class="message"></div>
  `;

  let index=0;
  let score=0;

  const questions=[...finalQuestions]
    .sort(()=>Math.random()-.5);

  function next(){

    if(index>=50){

      if(score>=40){

        addScore(500);
        addTokens(25);

        completeLevel(23,0);

        document.querySelector("#game23 .win-panel p").textContent=
          `You scored ${score}/50! You truly know Liliana. 💗`;

      }else{

        document.getElementById("finalMessage").textContent=
          `You scored ${score}/50. You need 40 to pass.`;

        timer(initGame23,1000);
      }

      return;
    }

    const q=questions[index];

    const answers=shuffledQuestion({
      q:q.q,
      options:q.o,
      answer:q.a
    });

    document.getElementById("finalQ").textContent=index+1;
    document.getElementById("finalQuestion").textContent=q.q;
    document.getElementById("finalProgress").style.width=
      `${index/50*100}%`;

    const box=document.getElementById("finalChoices");
    box.innerHTML="";

    answers.forEach(a=>{

      const b=document.createElement("button");

      b.className="choice";
      b.textContent=a.text;

      b.onclick=()=>{

        [...box.children].forEach(x=>x.disabled=true);

        if(a.correct){

          b.classList.add("correct");
          score++;

          document.getElementById("finalScore").textContent=score;

          document.getElementById("finalMessage").textContent=
            "Correct! 💗";

        }else{

          b.classList.add("wrong");

          document.getElementById("finalMessage").textContent=
            "Not quite!";
        }

        index++;

        timer(next,250);
      };

      box.appendChild(b);
    });
  }

  next();
}

/* =========================================================
   BUILD ALL 23 GAME SCREENS
   ========================================================= */

gameTemplate(
1,
"Broken Hearts",
"Catch whole hearts. Avoid broken hearts.",
""
);

gameTemplate(
2,
"Memory Vault",
"Remember the glowing sequence.",
""
);

gameTemplate(
3,
"Pressure Quiz",
"Ten quick general-knowledge questions.",
""
);

gameTemplate(
4,
"High Roller",
"Spin, stop and chase the jackpot.",
""
);

gameTemplate(
5,
"Mind Games",
"Find the pattern.",
""
);

gameTemplate(
6,
"The Bluff",
"Choose a card, then decide whether to bank or double.",
""
);

gameTemplate(
7,
"Survival Round",
"Make the safest decision through eight hazards.",
""
);

gameTemplate(
8,
"The Admirer Race",
"Tap GALLop when the marker reaches the perfect zone.",
""
);

gameTemplate(
9,
"Heartbreak Chamber",
"Search the room for four hidden clues.",
""
);

gameTemplate(
10,
"Heartbreak Boxing",
"Attack, guard and dodge your opponent.",
""
);

gameTemplate(
11,
"Perfect Match",
"Match every object to its target.",
""
);

gameTemplate(
12,
"Who Knows Liliana Best?",
"How well do you know Lulu?",
""
);

gameTemplate(
13,
"Reaction Gauntlet",
"React quickly and don't fall for the traps.",
""
);

gameTemplate(
14,
"Heart Hunt",
"Find the hidden hearts.",
""
);

gameTemplate(
15,
"Love Lock",
"Crack the combination.",
""
);

gameTemplate(
16,
"Cupid Shootout",
"Hit the moving hearts.",
""
);

gameTemplate(
17,
"The Countdown",
"Six quick mini-challenges.",
""
);

gameTemplate(
18,
"Ultimate Gamble",
"Risk your pot or cash out.",
""
);

gameTemplate(
19,
"Admirer's Last Stand",
"Defeat the final boss.",
""
);

gameTemplate(
20,
"Liliana's Word Find",
"Find all 25 hidden words.",
""
);

gameTemplate(
21,
"Draw a Sunflower",
"Create your own sunflower.",
""
);

gameTemplate(
22,
"THE LULU DERBY",
"100 random trivia questions. Race your horse to victory.",
""
);

gameTemplate(
23,
"THE FINAL CHALLENGE",
"50 unique questions about Liliana.",
""
);

/* =========================================================
   RESTORE JOURNEY VIEW
   ========================================================= */

if(state.name){

  document.getElementById("welcomeBox").style.display="none";
  document.getElementById("journeyBox").style.display="block";
  document.getElementById("welcomeName").textContent=state.name;

}else{

  document.getElementById("welcomeBox").style.display="block";
  document.getElementById("journeyBox").style.display="none";
}

updateHUD();
renderJourney();

/* =========================================================
   PREVENT ACCIDENTAL MOBILE GESTURES DURING GAMES
   ========================================================= */

document.addEventListener("gesturestart",e=>{
  e.preventDefault();
},{passive:false});

document.addEventListener("gesturechange",e=>{
  e.preventDefault();
},{passive:false});

document.addEventListener("gestureend",e=>{
  e.preventDefault();
},{passive:false});

/*
  Prevent double-tap zoom while still allowing normal taps.
*/
let lastTouch=0;

document.addEventListener("touchend",e=>{

  const now=Date.now();

  if(now-lastTouch<=280){
    e.preventDefault();
  }

  lastTouch=now;

},{passive:false});

/*
  Keep the viewport correct if the iPhone address bar
  changes the available visual height.
*/
function updateViewportHeight(){

  document.documentElement.style.setProperty(
    "--vh",
    `${window.innerHeight*0.01}px`
  );
}

window.addEventListener("resize",updateViewportHeight);
window.addEventListener("orientationchange",()=>{
  timer(updateViewportHeight,250);
});

updateViewportHeight();

/* =========================================================
   PRIVATE CALL RULE
   IMPORTANT: STRICTLY GREATER THAN 3000.
   3000 DOES NOT QUALIFY.
   ========================================================= */

window.privateCallUnlocked=function(){
  return state.score>3000;
};

</script>

</body>
</html>

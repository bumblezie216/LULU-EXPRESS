<html lang="en">
<head>
<meta charset="UTF-8">

<meta
  name="viewport"
  content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover"
>

<meta name="theme-color" content="#170910">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="mobile-web-app-capable" content="yes">

<title>Lulu Express 🚂💗</title>

<style>
*{
  box-sizing:border-box;
  -webkit-tap-highlight-color:transparent;
  touch-action:manipulation;
}

html,
body{
  margin:0;
  padding:0;
  width:100%;
  min-height:100%;
  background:#12070d;
  color:#fff;
  font-family:Arial,Helvetica,sans-serif;
  overflow-x:hidden;
}

body{
  overscroll-behavior:none;
  -webkit-text-size-adjust:100%;
}

button,
input,
select,
textarea{
  font:inherit;
}

button{
  border:0;
  cursor:pointer;
  user-select:none;
  -webkit-user-select:none;
  touch-action:manipulation;
}

input{
  font-size:16px !important;
}

.hidden{
  display:none!important;
}

.screen{
  min-height:100svh;
  width:100%;
  display:none;
  padding:
    max(18px,env(safe-area-inset-top))
    max(16px,env(safe-area-inset-right))
    max(22px,env(safe-area-inset-bottom))
    max(16px,env(safe-area-inset-left));
}

.screen.active{
  display:flex;
  flex-direction:column;
}

.game-screen{
  padding:0;
  min-height:100svh;
  height:100svh;
  overflow:hidden;
  background:
    radial-gradient(circle at 50% 15%,#492034 0,#24101c 35%,#10070c 100%);
}

.game-inner{
  width:100%;
  max-width:700px;
  margin:auto;
  min-height:100svh;
  height:100%;
  display:flex;
  flex-direction:column;
  padding:
    max(12px,env(safe-area-inset-top))
    max(12px,env(safe-area-inset-right))
    max(12px,env(safe-area-inset-bottom))
    max(12px,env(safe-area-inset-left));
}

h1,h2,h3,p{
  margin-top:0;
}

h1{
  font-size:clamp(2rem,8vw,3.5rem);
  margin-bottom:10px;
}

h2{
  font-size:clamp(1.4rem,6vw,2.2rem);
}

p{
  color:#e8cbd8;
  line-height:1.5;
}

.card{
  width:100%;
  max-width:700px;
  margin:auto;
  background:rgba(43,18,32,.92);
  border:1px solid #69324e;
  border-radius:24px;
  padding:24px;
  box-shadow:0 18px 60px rgba(0,0,0,.4);
}

.logo{
  font-size:clamp(2.5rem,12vw,5rem);
  text-align:center;
  margin-bottom:8px;
}

.subtitle{
  text-align:center;
  color:#e7b8cc;
}

.name-input{
  width:100%;
  height:56px;
  border-radius:16px;
  border:2px solid #753954;
  background:#170a11;
  color:#fff;
  padding:0 16px;
  outline:none;
  margin:15px 0;
}

.name-input:focus{
  border-color:#ff8fbd;
}

.primary,
.secondary,
.danger{
  width:100%;
  min-height:52px;
  border-radius:16px;
  margin-top:10px;
  font-weight:800;
  padding:12px 18px;
}

.primary{
  background:#d85c91;
  color:#fff;
}

.secondary{
  background:#472034;
  color:#ffd7e7;
  border:1px solid #78415b;
}

.danger{
  background:#6d2438;
  color:#fff;
}

.primary:active,
.secondary:active,
.danger:active,
.control-button:active{
  transform:scale(.97);
}

.menu-tools{
  width:100%;
  max-width:700px;
  margin:0 auto 15px;
  display:flex;
  gap:8px;
}

.menu-tools button{
  flex:1;
  min-height:48px;
  border-radius:14px;
  background:#2e1422;
  color:#ffd9e8;
  border:1px solid #66334b;
}

.journey{
  width:100%;
  max-width:700px;
  margin:auto;
}

.journey-title{
  text-align:center;
  margin-bottom:15px;
}

.level-list{
  display:flex;
  flex-direction:column;
  gap:9px;
}

.level{
  width:100%;
  min-height:62px;
  border-radius:18px;
  padding:10px 14px;
  display:flex;
  align-items:center;
  gap:12px;
  text-align:left;
  background:#281320;
  color:#fff;
  border:1px solid #583047;
}

.level.unlocked{
  background:#3a1a2b;
  border-color:#a04c70;
}

.level.completed{
  background:#422034;
  border-color:#d878a0;
}

.level.locked{
  opacity:.42;
  cursor:not-allowed;
}

.level-number{
  min-width:38px;
  height:38px;
  display:grid;
  place-items:center;
  border-radius:50%;
  background:#170a11;
  font-weight:900;
}

.level-name{
  flex:1;
  font-weight:800;
}

.level-status{
  font-size:1.3rem;
}

.journey-bottom{
  margin-top:15px;
}

.game-top{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:8px;
  margin-bottom:8px;
}

.game-title{
  font-size:clamp(1.25rem,6vw,2rem);
  font-weight:900;
}

.game-small{
  color:#dcb7c8;
  font-size:.9rem;
}

.game-content{
  flex:1;
  min-height:0;
  display:flex;
  flex-direction:column;
  justify-content:center;
}

.game-card{
  width:100%;
  background:rgba(38,16,28,.96);
  border:1px solid #713650;
  border-radius:22px;
  padding:16px;
  overflow:hidden;
}

.game-card h2{
  text-align:center;
  margin-bottom:8px;
}

.game-card p{
  text-align:center;
  margin-bottom:12px;
}

.game-buttons{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:9px;
}

.game-buttons.three{
  grid-template-columns:repeat(3,1fr);
}

.game-buttons.four{
  grid-template-columns:repeat(2,1fr);
}

.answer-button{
  min-height:58px;
  padding:10px;
  border-radius:15px;
  background:#321728;
  color:#fff;
  border:1px solid #75405a;
  font-weight:700;
  font-size:1rem;
}

.answer-button.correct{
  background:#28734e;
}

.answer-button.wrong{
  background:#84384c;
}

.answer-button:disabled{
  opacity:.9;
}

.result-box{
  text-align:center;
  background:#2c1522;
  border:1px solid #743750;
  border-radius:22px;
  padding:25px;
  width:100%;
  max-width:600px;
  margin:auto;
}

.result-box .big{
  font-size:3rem;
}

.result-box button{
  margin-top:12px;
}

.progress-bar{
  width:100%;
  height:13px;
  border-radius:20px;
  background:#180a11;
  overflow:hidden;
  border:1px solid #66334b;
}

.progress-fill{
  height:100%;
  width:0%;
  background:#ed76a7;
  transition:width .25s;
}

/* =========================================================
   BROKEN HEARTS
========================================================= */

.heart-game{
  position:relative;
  width:100%;
  flex:1;
  min-height:0;
  max-height:600px;
  margin:auto;
  overflow:hidden;
  border-radius:22px;
  background:
    radial-gradient(circle at 50% 0,#522139 0,#28121e 48%,#13080e 100%);
  border:1px solid #713650;
}

.heart-lanes{
  position:absolute;
  inset:0;
  display:grid;
  grid-template-columns:repeat(5,1fr);
}

.heart-lane{
  border-left:1px solid rgba(255,255,255,.035);
}

.falling-heart{
  position:absolute;
  transform:translateX(-50%);
  font-size:2rem;
  z-index:3;
  pointer-events:none;
}

.catcher{
  position:absolute;
  bottom:20px;
  width:19%;
  min-width:48px;
  height:50px;
  border-radius:17px;
  background:#d85c91;
  display:grid;
  place-items:center;
  font-size:1.5rem;
  z-index:5;
  transition:left .12s ease;
  box-shadow:0 5px 18px rgba(0,0,0,.35);
}

.heart-info{
  display:flex;
  justify-content:space-between;
  gap:8px;
  padding:7px 0;
  font-weight:800;
}

.move-controls{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
  margin-top:9px;
}

.move-button{
  min-height:70px;
  border-radius:20px;
  background:#d85c91;
  color:#fff;
  font-size:1.15rem;
  font-weight:900;
  border:2px solid #f39ac0;
  box-shadow:0 5px 15px rgba(0,0,0,.25);
}

.move-button span{
  display:block;
  font-size:1.7rem;
}

/* =========================================================
   MEMORY
========================================================= */

.memory-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:8px;
  max-width:430px;
  width:100%;
  margin:10px auto;
}

.memory-tile{
  aspect-ratio:1;
  border-radius:13px;
  background:#3b1b2c;
  border:1px solid #75405a;
  color:#fff;
  font-size:1.4rem;
}

.memory-tile.flash{
  background:#d85c91;
}

.memory-tile.selected{
  background:#71324f;
}

/* =========================================================
   SLOTS
========================================================= */

.reels{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:8px;
  margin:15px 0;
}

.reel{
  height:100px;
  border-radius:20px;
  background:#160910;
  border:2px solid #7b3b58;
  display:grid;
  place-items:center;
  font-size:3rem;
}

.slot-result{
  min-height:35px;
  text-align:center;
  font-weight:900;
  color:#ffb6d1;
}

/* =========================================================
   RACE
========================================================= */

.race-track{
  background:#160910;
  border:1px solid #713650;
  border-radius:20px;
  padding:15px;
}

.horse-row{
  position:relative;
  height:55px;
  background:#24111b;
  border-radius:15px;
  margin:8px 0;
  overflow:hidden;
}

.horse{
  position:absolute;
  left:0;
  top:5px;
  font-size:2.3rem;
  transition:left .35s ease;
}

.timing-meter{
  height:42px;
  border-radius:20px;
  background:#170910;
  border:2px solid #70405a;
  position:relative;
  overflow:hidden;
  margin:14px 0;
}

.timing-perfect{
  position:absolute;
  left:42%;
  width:16%;
  height:100%;
  background:#4a9d70;
}

.timing-good{
  position:absolute;
  left:27%;
  width:46%;
  height:100%;
  border-left:2px solid #c77b99;
  border-right:2px solid #c77b99;
}

.timing-marker{
  position:absolute;
  top:0;
  width:5px;
  height:100%;
  background:#fff;
}

/* =========================================================
   BOXING
========================================================= */

.fighter{
  text-align:center;
  font-size:5rem;
  margin:10px;
}

.health{
  height:18px;
  border-radius:20px;
  background:#160910;
  overflow:hidden;
  border:1px solid #69334c;
  margin:7px 0 12px;
}

.health-fill{
  height:100%;
  background:#d85c91;
  width:100%;
  transition:width .25s;
}

/* =========================================================
   MATCHING
========================================================= */

.match-board{
  position:relative;
  min-height:360px;
  border-radius:20px;
  background:#180a11;
  border:1px solid #713650;
}

.match-item{
  position:absolute;
  width:60px;
  height:60px;
  border-radius:18px;
  background:#3a1b2b;
  display:grid;
  place-items:center;
  font-size:2rem;
  border:2px solid #a45275;
  z-index:3;
}

.match-target{
  position:absolute;
  width:70px;
  height:70px;
  border-radius:20px;
  border:2px dashed #b76789;
  display:grid;
  place-items:center;
  font-size:1.5rem;
  opacity:.5;
}

/* =========================================================
   HEART HUNT
========================================================= */

.hunt-area{
  position:relative;
  height:55vh;
  min-height:330px;
  max-height:500px;
  border-radius:22px;
  background:
    radial-gradient(circle at 30% 25%,#4c2038,#22101b 55%,#13080e);
  border:1px solid #713650;
  overflow:hidden;
}

.hunt-heart{
  position:absolute;
  font-size:2rem;
  transition:all .4s ease;
  z-index:3;
}

/* =========================================================
   LOVE LOCK
========================================================= */

.lock-display{
  height:65px;
  border-radius:17px;
  background:#13080e;
  border:2px solid #753953;
  display:grid;
  place-items:center;
  font-size:2rem;
  letter-spacing:8px;
  margin-bottom:10px;
}

.keypad{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:8px;
}

.keypad button{
  min-height:58px;
  border-radius:15px;
  background:#3a1a2b;
  color:#fff;
  font-weight:900;
  font-size:1.15rem;
  border:1px solid #78405a;
}

/* =========================================================
   CUPID
========================================================= */

.shoot-area{
  position:relative;
  height:55vh;
  min-height:330px;
  max-height:500px;
  background:#170910;
  border:1px solid #713650;
  border-radius:22px;
  overflow:hidden;
}

.shoot-heart{
  position:absolute;
  font-size:2.4rem;
  padding:8px;
}

/* =========================================================
   DRAW
========================================================= */

.canvas-wrap{
  width:100%;
  height:min(55vh,470px);
  background:#f8e4c6;
  border-radius:20px;
  overflow:hidden;
  touch-action:none;
}

#drawingCanvas{
  width:100%;
  height:100%;
  display:block;
  touch-action:none;
}

.brush-row{
  display:flex;
  gap:7px;
  margin:8px 0;
}

.brush-row button{
  flex:1;
  min-height:45px;
  border-radius:13px;
  background:#3a1a2b;
  color:#fff;
  border:1px solid #75405a;
}

/* =========================================================
   WORD FIND
========================================================= */

.word-grid{
  display:grid;
  grid-template-columns:repeat(12,1fr);
  gap:2px;
  max-width:550px;
  width:100%;
  margin:7px auto;
  touch-action:none;
}

.word-letter{
  aspect-ratio:1;
  min-width:0;
  border-radius:4px;
  background:#2d1421;
  display:grid;
  place-items:center;
  font-size:clamp(.55rem,3.1vw,1rem);
  font-weight:900;
  color:#f6d5e2;
  border:1px solid #4c2638;
}

.word-letter.selected{
  background:#9b4d70;
}

.word-letter.found{
  background:#438261;
}

.word-list{
  display:flex;
  flex-wrap:wrap;
  gap:5px;
  max-height:110px;
  overflow:auto;
  margin-top:5px;
}

.word-chip{
  padding:5px 8px;
  border-radius:9px;
  background:#321728;
  border:1px solid #61334a;
  font-size:.72rem;
}

.word-chip.done{
  background:#347252;
  text-decoration:line-through;
}

/* =========================================================
   DERBY
========================================================= */

.derby-horses{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:9px;
  margin:10px 0;
}

.horse-choice{
  min-height:80px;
  border-radius:18px;
  background:#341726;
  border:2px solid #6e3b54;
  color:#fff;
  font-size:2rem;
}

.horse-choice.selected{
  border-color:#ff9dc3;
  background:#61304a;
}

.derby-track{
  background:#170910;
  border-radius:20px;
  border:1px solid #713650;
  padding:10px;
}

.derby-line{
  display:flex;
  align-items:center;
  gap:8px;
  margin:7px 0;
}

.derby-name{
  width:65px;
  font-size:.8rem;
}

.derby-bar{
  flex:1;
  height:24px;
  border-radius:20px;
  background:#29131f;
  overflow:hidden;
}

.derby-progress{
  height:100%;
  width:0%;
  background:#d85c91;
  transition:width .3s;
}

/* =========================================================
   COUNTDOWN
========================================================= */

.countdown-bar{
  position:relative;
  height:55px;
  background:#170910;
  border:2px solid #69334c;
  border-radius:20px;
  overflow:hidden;
}

.countdown-zone{
  position:absolute;
  left:40%;
  width:20%;
  top:0;
  bottom:0;
  background:#438261;
}

.countdown-marker{
  position:absolute;
  width:6px;
  height:100%;
  background:#fff;
}

/* =========================================================
   GAMBLE
========================================================= */

.gamble-pot{
  text-align:center;
  font-size:3.2rem;
  font-weight:900;
  color:#ffc0d7;
}

.coin{
  text-align:center;
  font-size:4rem;
  min-height:100px;
}

/* =========================================================
   BOSS
========================================================= */

.boss{
  text-align:center;
  font-size:5rem;
  animation:bob 1.5s infinite ease-in-out;
}

@keyframes bob{
  50%{transform:translateY(-7px)}
}

/* =========================================================
   GENERAL MINI GAME
========================================================= */

.mini-display{
  min-height:180px;
  display:grid;
  place-items:center;
  text-align:center;
  font-size:2rem;
  font-weight:900;
  background:#180a11;
  border:1px solid #66334b;
  border-radius:20px;
  padding:15px;
}

.score-display{
  text-align:center;
  font-weight:900;
  color:#ffb5d1;
  margin:8px 0;
}

/* =========================================================
   DESKTOP
========================================================= */

@media(min-width:700px){
  .game-inner{
    padding-left:25px;
    padding-right:25px;
  }

  .game-card{
    padding:22px;
  }
}
</style>
</head>

<body>

<!-- =======================================================
     START SCREEN
======================================================= -->

<section id="startScreen" class="screen active">
  <div class="card">
    <div class="logo">🚂💗</div>
    <h1 style="text-align:center">Lulu Express</h1>
    <p class="subtitle">
      A little journey made especially for Liliana.
    </p>

    <input
      id="playerName"
      class="name-input"
      type="text"
      maxlength="25"
      autocomplete="off"
      placeholder="Enter your name"
    >

    <button class="primary" onclick="startJourney()">
      🚂 Start Journey
    </button>

    <button class="secondary" onclick="showJourney()">
      Continue Journey
    </button>
  </div>
</section>

<!-- =======================================================
     JOURNEY SCREEN
======================================================= -->

<section id="journeyScreen" class="screen">

  <div class="menu-tools">
    <button onclick="toggleMusic()" id="musicButton">🎵 Music Off</button>
    <button onclick="resetJourney()">↻ Reset</button>
  </div>

  <div class="journey">
    <div class="card" style="margin-bottom:15px">
      <h2 class="journey-title">🚂 Lulu Express</h2>
      <p id="welcomeText" style="text-align:center"></p>

      <div style="display:flex;justify-content:space-around;text-align:center">
        <div>
          <strong id="menuScore">0</strong>
          <br>
          <small>Points</small>
        </div>
        <div>
          <strong id="menuTokens">0</strong>
          <br>
          <small>Tokens</small>
        </div>
        <div>
          <strong id="menuProgress">0/23</strong>
          <br>
          <small>Levels</small>
        </div>
      </div>
    </div>

    <div class="level-list" id="levelList"></div>

    <div class="journey-bottom">
      <button class="primary" onclick="continueJourney()">
        Continue Journey 🚂
      </button>
    </div>
  </div>
</section>

<!-- =======================================================
     GAME SCREEN
======================================================= -->

<section id="gameScreen" class="screen game-screen">
  <div class="game-inner">

    <div id="gameContent" class="game-content"></div>

  </div>
</section>

<script>
/* =========================================================
   GLOBAL STATE
========================================================= */

const TOTAL_LEVELS = 23;

const gameNames = [
  "💔 Broken Hearts",
  "🧠 Memory Vault",
  "⏱️ Pressure Quiz",
  "🎰 High Roller",
  "🧩 Mind Games",
  "🃏 The Bluff",
  "🛡️ Survival Round",
  "🏇 The Admirer Race",
  "🔎 Heartbreak Chamber",
  "🥊 Heartbreak Boxing Match",
  "🧲 Perfect Match",
  "💗 Who Knows Liliana Best?",
  "⚡ Reaction Gauntlet",
  "🕵️ Heart Hunt",
  "🔐 Love Lock",
  "🏹 Cupid Shootout",
  "⏳ The Countdown",
  "🎲 Ultimate Gamble",
  "👑 Admirer's Last Stand",
  "🔎 Liliana's Word Find",
  "🌻 Draw a Sunflower",
  "🏇 THE LULU DERBY",
  "💕 THE FINAL CHALLENGE"
];

let state = {
  name:"",
  score:0,
  tokens:0,
  unlocked:1,
  completed:[],
  current:0
};

let timers = [];
let animationFrames = [];
let cleanupFunctions = [];

function saveState(){
  localStorage.setItem("luluExpressState",JSON.stringify(state));
}

function loadState(){
  try{
    const saved=JSON.parse(localStorage.getItem("luluExpressState"));
    if(saved){
      state={...state,...saved};
    }
  }catch(e){}
}

loadState();

function clearGameTimers(){
  timers.forEach(clearTimeout);
  timers.forEach(clearInterval);
  timers=[];
  animationFrames.forEach(cancelAnimationFrame);
  animationFrames=[];
  cleanupFunctions.forEach(fn=>{
    try{fn()}catch(e){}
  });
  cleanupFunctions=[];
}

function later(fn,ms){
  const id=setTimeout(fn,ms);
  timers.push(id);
  return id;
}

function every(fn,ms){
  const id=setInterval(fn,ms);
  timers.push(id);
  return id;
}

function raf(fn){
  const id=requestAnimationFrame(fn);
  animationFrames.push(id);
  return id;
}

function addPoints(n){
  state.score+=n;
  saveState();
}

function addTokens(n){
  state.tokens+=n;
  saveState();
}

/* =========================================================
   MUSIC
   Simple Web Audio game music. No external audio.
========================================================= */

let audioCtx=null;
let musicGain=null;
let musicTimer=null;
let musicOn=false;

const melody=[
  261.63,329.63,392.00,329.63,
  293.66,349.23,440.00,349.23,
  261.63,329.63,392.00,523.25,
  392.00,329.63,293.66,261.63
];

function startMusic(){
  if(musicOn) return;

  try{
    const AudioContext=window.AudioContext||window.webkitAudioContext;
    if(!AudioContext) return;

    if(!audioCtx){
      audioCtx=new AudioContext();
      musicGain=audioCtx.createGain();
      musicGain.gain.value=.055;
      musicGain.connect(audioCtx.destination);
    }

    if(audioCtx.state==="suspended"){
      audioCtx.resume();
    }

    musicOn=true;
    playMusicNote(0);

    updateMusicButtons();

  }catch(e){
    console.log("Music unavailable");
  }
}

function playMusicNote(index){
  if(!musicOn || !audioCtx) return;

  const osc=audioCtx.createOscillator();
  const gain=audioCtx.createGain();

  osc.type="sine";
  osc.frequency.value=melody[index%melody.length];

  gain.gain.setValueAtTime(0,audioCtx.currentTime);
  gain.gain.linearRampToValueAtTime(.75,audioCtx.currentTime+.025);
  gain.gain.exponentialRampToValueAtTime(.001,audioCtx.currentTime+.32);

  osc.connect(gain);
  gain.connect(musicGain);

  osc.start();
  osc.stop(audioCtx.currentTime+.34);

  musicTimer=setTimeout(
    ()=>playMusicNote(index+1),
    370
  );
}

function stopMusic(){
  musicOn=false;

  if(musicTimer){
    clearTimeout(musicTimer);
    musicTimer=null;
  }

  updateMusicButtons();
}

function toggleMusic(){
  if(musicOn) stopMusic();
  else startMusic();
}

function updateMusicButtons(){
  const b=document.getElementById("musicButton");
  if(b){
    b.textContent=musicOn ? "🎵 Music On" : "🎵 Music Off";
  }
}

/* =========================================================
   NAVIGATION
========================================================= */

function showScreen(id){
  document.querySelectorAll(".screen").forEach(s=>{
    s.classList.remove("active");
  });

  document.getElementById(id).classList.add("active");

  window.scrollTo(0,0);
}

function startJourney(){
  const input=document.getElementById("playerName");
  const name=input.value.trim();

  if(!name){
    input.focus();
    input.placeholder="Please enter your name first 💗";
    return;
  }

  state.name=name;

  if(state.unlocked<1) state.unlocked=1;

  saveState();
  renderJourney();
  showScreen("journeyScreen");
}

function showJourney(){
  if(!state.name){
    showScreen("startScreen");
    return;
  }

  renderJourney();
  showScreen("journeyScreen");
}

function continueJourney(){
  let level=state.completed.length+1;

  if(level<1) level=1;
  if(level>23) level=23;

  if(level>state.unlocked){
    level=state.unlocked;
  }

  startGame(level);
}

function renderJourney(){
  document.getElementById("welcomeText").textContent=
    state.name
    ? `Welcome back, ${state.name} 💗`
    : "Your Lulu Express journey awaits.";

  document.getElementById("menuScore").textContent=state.score;
  document.getElementById("menuTokens").textContent=state.tokens;
  document.getElementById("menuProgress").textContent=
    `${state.completed.length}/23`;

  const list=document.getElementById("levelList");
  list.innerHTML="";

  for(let i=1;i<=23;i++){

    const unlocked=i<=state.unlocked;
    const completed=state.completed.includes(i);

    const button=document.createElement("button");

    button.className=
      "level "+
      (completed?"completed ":"")+
      (unlocked?"unlocked":"locked");

    button.disabled=!unlocked;

    button.innerHTML=`
      <span class="level-number">${i}</span>
      <span class="level-name">${gameNames[i-1]}</span>
      <span class="level-status">
        ${completed?"✓":unlocked?"▶":"🔒"}
      </span>
    `;

    if(unlocked){
      button.onclick=()=>startGame(i);
    }

    list.appendChild(button);
  }
}

function startGame(level){
  if(level>state.unlocked) return;

  clearGameTimers();

  state.current=level;
  saveState();

  /*
    IMPORTANT:
    We only show the game screen here.
    The journey HUD, token display and music button
    are therefore completely off-screen while playing.
  */

  showScreen("gameScreen");

  const content=document.getElementById("gameContent");
  content.innerHTML="";

  switch(level){
    case 1: gameBrokenHearts(); break;
    case 2: gameMemory(); break;
    case 3: gamePressureQuiz(); break;
    case 4: gameSlots(); break;
    case 5: gameMindGames(); break;
    case 6: gameBluff(); break;
    case 7: gameSurvival(); break;
    case 8: gameRace(); break;
    case 9: gameChamber(); break;
    case 10: gameBoxing(); break;
    case 11: gamePerfectMatch(); break;
    case 12: gameLilianaQuiz(); break;
    case 13: gameReaction(); break;
    case 14: gameHeartHunt(); break;
    case 15: gameLoveLock(); break;
    case 16: gameCupid(); break;
    case 17: gameCountdown(); break;
    case 18: gameGamble(); break;
    case 19: gameLastStand(); break;
    case 20: gameWordFind(); break;
    case 21: gameSunflower(); break;
    case 22: gameDerby(); break;
    case 23: gameFinalChallenge(); break;
  }
}

function gameHeader(title,subtitle=""){
  return `
    <div class="game-top">
      <div class="game-title">${title}</div>
      <div class="game-small">${subtitle}</div>
    </div>
  `;
}

function finishGame(level,passed,message,points=0){
  clearGameTimers();

  if(passed){
    addPoints(points);
    addTokens(Math.max(1,Math.floor(points/25)));

    if(!state.completed.includes(level)){
      state.completed.push(level);
    }

    if(level===state.unlocked && state.unlocked<TOTAL_LEVELS){
      state.unlocked++;
    }

    saveState();
  }

  const next=level<TOTAL_LEVELS;

  document.getElementById("gameContent").innerHTML=`
    <div class="result-box">
      <div class="big">${passed?"🎉":"💔"}</div>

      <h2>
        ${passed?"Level Passed!":"Try Again"}
      </h2>

      <p>${message}</p>

      ${points ? `<p><strong>+${points} points</strong></p>`:""}

      ${
        passed && next
        ?
        `<button class="primary" onclick="startGame(${level+1})">
          Next Level →
        </button>`
        :
        passed
        ?
        `<button class="primary" onclick="showFinalResults()">
          Finish Journey 💕
        </button>`
        :
        `<button class="primary" onclick="startGame(${level})">
          Try Again
        </button>`
      }

      <button class="secondary" onclick="showJourney()">
        Journey Map
      </button>
    </div>
  `;
}

function showFinalResults(){
  clearGameTimers();

  const privateCall=state.score>3000;

  showScreen("journeyScreen");

  alert(
    privateCall
    ? `🎉 ${state.name}, you finished Lulu Express with ${state.score} points! You unlocked the private call reward! 💗`
    : `🎉 ${state.name}, you finished Lulu Express with ${state.score} points! 💗`
  );

  renderJourney();
}

function resetJourney(){
  if(!confirm(
    "Reset the entire Lulu Express journey?\n\nThis will erase your progress, points and tokens."
  )) return;

  stopMusic();

  state={
    name:"",
    score:0,
    tokens:0,
    unlocked:1,
    completed:[],
    current:0
  };

  localStorage.removeItem("luluExpressState");

  clearGameTimers();

  document.getElementById("playerName").value="";

  showScreen("startScreen");
}

/* =========================================================
   SHUFFLE HELPERS
========================================================= */

function shuffle(arr){
  const a=[...arr];

  for(let i=a.length-1;i>0;i--){
    const j=Math.floor(Math.random()*(i+1));
    [a[i],a[j]]=[a[j],a[i]];
  }

  return a;
}

function shuffledQuestion(q){
  const options=q.options.map((text,index)=>({
    text,
    correct:index===q.answer
  }));

  return shuffle(options);
}

/* =========================================================
   1. BROKEN HEARTS
   EASY LANE CONTROL
========================================================= */

function gameBrokenHearts(){

  let lane=2;
  let lives=3;
  let caught=0;
  let combo=0;
  let running=true;
  let spawnTimer;

  const content=document.getElementById("gameContent");

  content.innerHTML=`
    ${gameHeader("💔 Broken Hearts","Catch 15 whole hearts")}

    <div class="heart-info">
      <span id="bhCaught">💗 0 / 15</span>
      <span id="bhLives">❤️❤️❤️</span>
      <span id="bhCombo">Combo x1</span>
    </div>

    <div class="heart-game" id="heartGame">
      <div class="heart-lanes">
        <div class="heart-lane"></div>
        <div class="heart-lane"></div>
        <div class="heart-lane"></div>
        <div class="heart-lane"></div>
        <div class="heart-lane"></div>
      </div>

      <div class="catcher" id="catcher">🧺</div>
    </div>

    <div class="move-controls">
      <button class="move-button" id="leftButton">
        <span>⬅️</span>
        LEFT
      </button>

      <button class="move-button" id="rightButton">
        <span>➡️</span>
        RIGHT
      </button>
    </div>
  `;

  const area=document.getElementById("heartGame");
  const catcher=document.getElementById("catcher");

  function updateCatcher(){
    const left=lane*20+0.5;
    catcher.style.left=`${left}%`;
  }

  function moveLeft(){
    if(!running)return;
    lane=Math.max(0,lane-1);
    updateCatcher();
  }

  function moveRight(){
    if(!running)return;
    lane=Math.min(4,lane+1);
    updateCatcher();
  }

  /*
    Hold controls are supported, but a normal tap is enough.
    There is NO dragging.
  */

  const left=document.getElementById("leftButton");
  const right=document.getElementById("rightButton");

  let holdTimer=null;

  function hold(fn){
    fn();

    clearInterval(holdTimer);

    holdTimer=setInterval(fn,130);
  }

  function release(){
    clearInterval(holdTimer);
    holdTimer=null;
  }

  left.addEventListener("pointerdown",e=>{
    e.preventDefault();
    hold(moveLeft);
  });

  right.addEventListener("pointerdown",e=>{
    e.preventDefault();
    hold(moveRight);
  });

  ["pointerup","pointercancel","pointerleave"].forEach(type=>{
    left.addEventListener(type,release);
    right.addEventListener(type,release);
  });

  function key(e){
    if(e.key==="ArrowLeft"){
      e.preventDefault();
      moveLeft();
    }

    if(e.key==="ArrowRight"){
      e.preventDefault();
      moveRight();
    }
  }

  window.addEventListener("keydown",key);
  cleanupFunctions.push(()=>{
    window.removeEventListener("keydown",key);
    release();
  });

  updateCatcher();

  function spawn(){

    if(!running)return;

    const el=document.createElement("div");
    const type=Math.random();

    let emoji="💗";
    let value=10;

    if(type<.12){
      emoji="💔";
      value=-1;
    }else if(type<.20){
      emoji="💛";
      value=30;
    }

    el.className="falling-heart";
    el.textContent=emoji;

    const heartLane=Math.floor(Math.random()*5);
    const x=heartLane*20+10;

    el.style.left=x+"%";
    el.style.top="-45px";

    area.appendChild(el);

    const duration=
      4300+
      Math.random()*1300+
      Math.max(0,(15-caught)*35);

    const start=performance.now();

    function fall(now){

      if(!running){
        el.remove();
        return;
      }

      const progress=Math.min(1,(now-start)/duration);
      el.style.top=(progress*(area.clientHeight-60)-20)+"px";

      if(progress>=1){

        const catcherLane=lane;

        if(heartLane===catcherLane){

          if(emoji==="💔"){
            lives--;
            combo=0;
          }else{
            caught++;
            combo++;

            const multiplier=Math.min(3,1+Math.floor(combo/5));
            addPoints(value*multiplier);
          }

          update();

          if(lives<=0){
            running=false;
            finishGame(
              1,
              false,
              "The broken hearts got through too many times. 💔",
              0
            );
            return;
          }

          if(caught>=15){
            running=false;
            finishGame(
              1,
              true,
              `You caught all 15 hearts, ${state.name}! 💗`,
              180
            );
            return;
          }
        }

        el.remove();
        return;
      }

      raf(fall);
    }

    raf(fall);
  }

  function update(){
    document.getElementById("bhCaught").textContent=
      `💗 ${caught} / 15`;

    document.getElementById("bhLives").textContent=
      "❤️".repeat(lives)+"🖤".repeat(3-lives);

    document.getElementById("bhCombo").textContent=
      `Combo x${Math.min(3,1+Math.floor(combo/5))}`;
  }

  update();

  spawnTimer=every(spawn,900);
  spawn();
}

/* =========================================================
   2. MEMORY VAULT
========================================================= */

function gameMemory(){

  let round=0;
  let sequence=[];
  let input=[];
  let accepting=false;
  const symbols=["💗","🌸","🐬","🌻","🌹","⭐","☀️","🌙",
                  "🦋","🎀","🍓","✨","💎","🌊","🩷","🍀"];

  const content=document.getElementById("gameContent");

  content.innerHTML=`
    ${gameHeader("🧠 Memory Vault","Repeat the glowing pattern")}

    <div class="score-display" id="memoryStatus">
      Round 1 of 7
    </div>

    <div id="memoryGrid" class="memory-grid"></div>

    <button
      class="primary"
      id="memoryStart"
      onclick="window.memoryBegin()"
    >
      Show Pattern
    </button>
  `;

  const grid=document.getElementById("memoryGrid");

  grid.innerHTML=Array.from(
    {length:16},
    (_,i)=>`
      <button
        class="memory-tile"
        data-index="${i}"
      >
        ${symbols[i]}
      </button>
    `
  ).join("");

  const tiles=[...grid.querySelectorAll(".memory-tile")];

  tiles.forEach((tile,i)=>{
    tile.onclick=()=>{
      if(!accepting)return;

      tile.classList.add("selected");

      later(()=>{
        tile.classList.remove("selected");
      },180);

      if(i!==sequence[input.length]){
        accepting=false;
        input=[];

        document.getElementById("memoryStatus").textContent=
          "Not quite! Watch the pattern again.";

        later(showPattern,700);
        return;
      }

      input++;

      if(input.length===sequence.length){

        accepting=false;
        round++;

        addPoints(20);

        if(round>=7){
          finishGame(
            2,
            true,
            "Your memory made it through the vault! 🧠💗",
            160
          );
          return;
        }

        document.getElementById("memoryStatus").textContent=
          `Round ${round+1} of 7`;

        later(nextRound,700);
      }
    };
  });

  function nextRound(){
    sequence.push(
      Math.floor(Math.random()*16)
    );

    showPattern();
  }

  function showPattern(){

    accepting=false;
    input=[];

    tiles.forEach(t=>t.classList.remove("flash"));

    let i=0;

    function flash(){

      if(i>=sequence.length){
        accepting=true;
        return;
      }

      const tile=tiles[sequence[i]];

      tile.classList.add("flash");

      later(()=>{
        tile.classList.remove("flash");
        later(()=>{
          i++;
          flash();
        },110);
      },420);
    }

    flash();
  }

  window.memoryBegin=function(){
    document.getElementById("memoryStart").style.display="none";

    sequence=[
      Math.floor(Math.random()*16),
      Math.floor(Math.random()*16)
    ];

    showPattern();
  };
}

/* =========================================================
   3. PRESSURE QUIZ
========================================================= */

const pressureQuestions=[
  ["What is the capital of Australia?",["Canberra","Sydney","Melbourne","Perth"],0],
  ["Which planet is the largest?",["Jupiter","Saturn","Neptune","Earth"],0],
  ["Which planet is known as the Red Planet?",["Mars","Venus","Mercury","Jupiter"],0],
  ["What is the chemical symbol for gold?",["Au","Ag","Gd","Go"],0],
  ["How many continents are there?",["7","5","6","8"],0],
  ["Where is the Great Barrier Reef?",["Australia","Brazil","India","Mexico"],0],
  ["Who wrote Pride and Prejudice?",["Jane Austen","Emily Brontë","Virginia Woolf","Mary Shelley"],0],
  ["What is Japan's currency?",["Yen","Won","Yuan","Ringgit"],0],
  ["What is the fastest land animal?",["Cheetah","Lion","Horse","Leopard"],0],
  ["What is the largest ocean?",["Pacific","Atlantic","Indian","Arctic"],0],
  ["Water boils at what temperature at sea level?",["100°C","90°C","110°C","80°C"],0],
  ["How many chambers does the human heart have?",["4","2","3","5"],0],
  ["Which gas makes up most of Earth's atmosphere?",["Nitrogen","Oxygen","Carbon dioxide","Hydrogen"],0],
  ["What is the tallest mountain above sea level?",["Mount Everest","K2","Kilimanjaro","Denali"],0],
  ["What is the smallest prime number?",["2","1","3","0"],0],
  ["Who wrote Hamlet?",["William Shakespeare","Charles Dickens","Mark Twain","Oscar Wilde"],0],
  ["Who painted the Mona Lisa?",["Leonardo da Vinci","Michelangelo","Raphael","Van Gogh"],0],
  ["What does DNA stand for?",["Deoxyribonucleic acid","Dynamic Nuclear Acid","Double Nitrogen Acid","Deoxygenated Nucleic Acid"],0],
  ["How long does Earth take to orbit the Sun?",["About 365 days","About 30 days","About 180 days","About 700 days"],0],
  ["How many sides does an octagon have?",["8","6","7","10"],0],
  ["Which animal produces honey?",["Bees","Ants","Wasps","Butterflies"],0],
  ["Which planet is famous for its rings?",["Saturn","Mars","Venus","Mercury"],0],
  ["A whale is what type of animal?",["Mammal","Fish","Reptile","Amphibian"],0],
  ["What is H2O?",["Water","Oxygen","Hydrogen","Salt"],0],
  ["Which travels faster?",["Light","Sound","Wind","Water"],0],
  ["The Sahara is on which continent?",["Africa","Asia","Europe","Australia"],0],
  ["Where is the Eiffel Tower?",["Paris","Rome","Madrid","Berlin"],0],
  ["Mount Fuji is in which country?",["Japan","China","South Korea","Thailand"],0],
  ["The Great Wall is in which country?",["China","India","Mongolia","Japan"],0],
  ["What is New Zealand's currency?",["New Zealand dollar","Australian dollar","Pound","Yen"],0]
].map(q=>({question:q[0],options:q[1],answer:q[2]}));

function gamePressureQuiz(){

  let questions=shuffle(pressureQuestions).slice(0,10);
  let index=0;
  let score=0;
  let answered=false;
  let timer=null;

  const content=document.getElementById("gameContent");

  function show(){

    clearTimeout(timer);
    answered=false;

    const q=questions[index];
    const answers=shuffledQuestion(q);

    content.innerHTML=`
      ${gameHeader("⏱️ Pressure Quiz",`${index+1}/10`)}

      <div class="game-card">
        <div class="score-display" id="quizTimer">7</div>
        <div class="progress-bar">
          <div
            class="progress-fill"
            style="width:${index/10*100}%"
          ></div>
        </div>

        <h2 style="margin-top:16px">${q.question}</h2>

        <div class="game-buttons four">
          ${answers.map((a,i)=>`
            <button
              class="answer-button"
              onclick="window.pressureAnswer(${a.correct?1:0},this)"
            >
              ${String.fromCharCode(65+i)}. ${a.text}
            </button>
          `).join("")}
        </div>
      </div>
    `;

    let seconds=7;

    timer=setInterval(()=>{

      seconds--;

      const el=document.getElementById("quizTimer");
      if(el)el.textContent=seconds;

      if(seconds<=0){
        clearInterval(timer);

        if(!answered){
          answered=true;
          index++;

          if(index>=10){
            end();
          }else{
            show();
          }
        }
      }
    },1000);

    timers.push(timer);
  }

  window.pressureAnswer=function(correct,button){

    if(answered)return;

    answered=true;
    clearInterval(timer);

    if(correct){
      score++;
      addPoints(25);
      button.classList.add("correct");
    }else{
      button.classList.add("wrong");
    }

    [...document.querySelectorAll(".answer-button")]
      .forEach(b=>b.disabled=true);

    later(()=>{
      index++;

      if(index>=10){
        end();
      }else{
        show();
      }
    },500);
  };

  function end(){

    const passed=score>=6;

    finishGame(
      3,
      passed,
      `You scored ${score}/10. ${
        passed
        ?"Fast thinking! ⏱️💗"
        :"You needed 6 correct answers."
      }`,
      score*10
    );
  }

  show();
}

/* =========================================================
   4. HIGH ROLLER
========================================================= */

function gameSlots(){

  const symbols=["🍒","💎","⭐","7️⃣","🌸","💗"];

  let reels=["❔","❔","❔"];
  let stopped=[false,false,false];
  let spinning=false;
  let spinInterval;

  const content=document.getElementById("gameContent");

  content.innerHTML=`
    ${gameHeader("🎰 High Roller","Stop all three reels")}

    <div class="game-card">
      <div class="reels">
        <div class="reel" id="reel0">❔</div>
        <div class="reel" id="reel1">❔</div>
        <div class="reel" id="reel2">❔</div>
      </div>

      <div class="slot-result" id="slotResult">
        Pull the lever!
      </div>

      <button class="primary" onclick="window.startSlots()">
        🎰 SPIN
      </button>

      <div class="game-buttons three">
        <button class="secondary" onclick="window.stopReel(0)">Stop 1</button>
        <button class="secondary" onclick="window.stopReel(1)">Stop 2</button>
        <button class="secondary" onclick="window.stopReel(2)">Stop 3</button>
      </div>
    </div>
  `;

  window.startSlots=function(){

    if(spinning)return;

    spinning=true;
    stopped=[false,false,false];

    document.getElementById("slotResult").textContent=
      "Stop each reel!";

    spinInterval=setInterval(()=>{

      for(let i=0;i<3;i++){

        if(!stopped[i]){
          reels[i]=symbols[
            Math.floor(Math.random()*symbols.length)
          ];

          document.getElementById("reel"+i).textContent=
            reels[i];
        }
      }

    },90);

    timers.push(spinInterval);
  };

  window.stopReel=function(i){

    if(!spinning || stopped[i])return;

    stopped[i]=true;

    reels[i]=symbols[
      Math.floor(Math.random()*symbols.length)
    ];

    document.getElementById("reel"+i).textContent=reels[i];

    if(stopped.every(Boolean)){
      clearInterval(spinInterval);
      spinning=false;

      const counts={};

      reels.forEach(x=>{
        counts[x]=(counts[x]||0)+1;
      });

      const values=Object.values(counts);
      const max=Math.max(...values);

      let reward=0;
      let message="No match this time!";

      if(max===3){
        reward=250;
        message="🎉 JACKPOT! Three matching symbols!";
      }else if(max===2){
        reward=80;
        message="✨ Two matched! Nice win!";
      }else{
        reward=20;
        message="💗 Lucky try! You still get a little reward.";
      }

      addPoints(reward);

      document.getElementById("slotResult").textContent=
        message;

      later(()=>{
        finishGame(
          4,
          true,
          message,
          reward
        );
      },1000);
    }
  };
}

/* =========================================================
   5. MIND GAMES
========================================================= */

function gameMindGames(){

  const puzzles=[
    {
      q:"Which symbol comes next? 2, 4, 6, 8, ?",
      o:["10","11","12","14"],a:0
    },
    {
      q:"Which one does NOT belong?",
      o:["Apple","Pear","Carrot","Peach"],a:2
    },
    {
      q:"Complete the pattern: 🔴 🔵 🔴 🔵 ?",
      o:["🔴","🟢","🟡","⚫"],a:0
    },
    {
      q:"Which number is smallest?",
      o:["0.2","0.02","0.22","0.202"],a:1
    },
    {
      q:"If CAT becomes DBU, what does DOG become?",
      o:["EPH","EOH","DPG","FQI"],a:0
    },
    {
      q:"Which shape has no corners?",
      o:["Circle","Triangle","Square","Pentagon"],a:0
    },
    {
      q:"What comes next? A, C, E, G, ?",
      o:["I","H","J","K"],a:0
    },
    {
      q:"Which is the odd one out?",
      o:["Monday","Tuesday","January","Friday"],a:2
    }
  ];

  let index=0;
  let correct=0;

  function show(){

    const q=puzzles[index];
    const answers=shuffle(
      q.o.map((text,i)=>({text,correct:i===q.a}))
    );

    document.getElementById("gameContent").innerHTML=`
      ${gameHeader("🧩 Mind Games",`${index+1}/8`)}

      <div class="game-card">
        <div class="score-display">
          Correct: ${correct}
        </div>

        <h2>${q.q}</h2>

        <div class="game-buttons four">
          ${answers.map(a=>`
            <button
              class="answer-button"
              onclick="window.mindAnswer(${a.correct?1:0})"
            >
              ${a.text}
            </button>
          `).join("")}
        </div>
      </div>
    `;
  }

  window.mindAnswer=function(ok){

    if(ok){
      correct++;
      addPoints(20);
    }

    index++;

    if(index>=8){

      finishGame(
        5,
        correct>=5,
        `You solved ${correct}/8 puzzles.`,
        correct*10
      );

    }else{
      show();
    }
  };

  show();
}

/* =========================================================
   6. THE BLUFF
========================================================= */

function gameBluff(){

  let round=1;
  let pot=100;
  let selected=null;

  const content=document.getElementById("gameContent");

  function show(){

    selected=null;

    const cards=Array.from(
      {length:4},
      ()=>Math.floor(Math.random()*20)+1
    );

    content.innerHTML=`
      ${gameHeader("🃏 The Bluff",`Round ${round}/5`)}

      <div class="game-card">
        <div class="gamble-pot">$${pot}</div>

        <p>Choose one hidden card.</p>

        <div class="game-buttons four">
          ${cards.map((_,i)=>`
            <button
              class="answer-button"
              onclick="window.pickBluff(${i},${cards[i]})"
            >
              🂠<br>Card ${i+1}
            </button>
          `).join("")}
        </div>

        <div id="bluffChoice"></div>
      </div>
    `;
  }

  window.pickBluff=function(i,value){

    if(selected!==null)return;

    selected=value;

    const box=document.getElementById("bluffChoice");

    box.innerHTML=`
      <div class="mini-display" style="margin-top:12px">
        You drew <strong>${value}</strong>!
      </div>

      <div class="game-buttons">
        <button
          class="primary"
          onclick="window.bluffBank(${value})"
        >
          💰 Bank
        </button>

        <button
          class="secondary"
          onclick="window.bluffDouble(${value})"
        >
          🎲 Double
        </button>
      </div>
    `;
  };

  window.bluffBank=function(value){

    pot+=value*3;
    addPoints(value*4);

    next();
  };

  window.bluffDouble=function(value){

    if(value>=10){
      pot+=value*6;
      addPoints(value*8);
    }else{
      pot=Math.max(0,pot-value*3);
    }

    next();
  };

  function next(){

    round++;

    if(round>5){

      finishGame(
        6,
        pot>=100,
        `You finished The Bluff with $${pot}.`,
        Math.max(50,pot)
      );

    }else{
      show();
    }
  }

  show();
}

/* =========================================================
   7. SURVIVAL ROUND
========================================================= */

function gameSurvival(){

  const waves=[
    ["🔥 Fire!","🪣 Water","🪨 Rock","🌬️ Wind","Water"],
    ["🌊 Wave!","🏄 Jump","🧱 Hide","🧊 Freeze","Jump"],
    ["⚡ Lightning!","🏃 Move","🛌 Sleep","🪑 Sit","Move"],
    ["🐝 Swarm!","🧥 Cover","🍯 Feed","📣 Shout","Cover"],
    ["❄️ Ice!","🔥 Warm up","💧 Pour water","🧊 Touch it","Warm up"],
    ["🌪️ Wind!","⚓ Hold on","🎈 Fly","🚪 Open door","Hold on"],
    ["🌋 Lava!","⬆️ Climb","⬇️ Dig","🏊 Swim","Climb"],
    ["🌧️ Storm!","🏠 Shelter","🌳 Stand outside","🌊 Swim","Shelter"]
  ];

  let index=0;
  let correct=0;
  let answered=false;

  function show(){

    answered=false;

    const w=waves[index];

    const choices=shuffle(
      w.slice(1,4)
    );

    document.getElementById("gameContent").innerHTML=`
      ${gameHeader("🛡️ Survival Round",`Wave ${index+1}/8`)}

      <div class="game-card">
        <div class="mini-display">
          ${w[0]}
        </div>

        <p>Choose the safest action.</p>

        <div class="game-buttons">
          ${choices.map(x=>`
            <button
              class="answer-button"
              onclick="window.survivalAnswer('${x}','${w[4]}')"
            >
              ${x}
            </button>
          `).join("")}
        </div>
      </div>
    `;
  }

  window.survivalAnswer=function(choice,correctAnswer){

    if(answered)return;
    answered=true;

    if(choice===correctAnswer){
      correct++;
      addPoints(25);
    }

    later(()=>{
      index++;

      if(index>=8){

        finishGame(
          7,
          correct>=5,
          `You survived ${correct}/8 waves! 🛡️`,
          correct*12
        );

      }else{
        show();
      }
    },350);
  };

  show();
}

/* =========================================================
   8. ADMIRER RACE
   NO OBSTACLES
   TIMING ONLY
========================================================= */

function gameRace(){

  let round=0;
  let player=0;
  let ai=0;
  let marker=0;
  let direction=1;
  let running=true;

  const content=document.getElementById("gameContent");

  content.innerHTML=`
    ${gameHeader("🏇 The Admirer Race","Time your gallop")}

    <div class="game-card">

      <div class="race-track">

        <div class="horse-row">
          <span
            id="playerHorse"
            class="horse"
          >🐎</span>
        </div>

        <div class="horse-row">
          <span
            id="aiHorse"
            class="horse"
          >🐴</span>
        </div>

      </div>

      <div class="score-display" id="raceScore">
        Round 1 / 10
      </div>

      <div class="timing-meter" id="timingMeter">
        <div class="timing-good"></div>
        <div class="timing-perfect"></div>
        <div
          id="timingMarker"
          class="timing-marker"
        ></div>
      </div>

      <button
        class="primary"
        onclick="window.gallop()"
      >
        🏇 GALLop!
      </button>

      <p>
        Hit the green area for a PERFECT boost.
        There are no obstacles to dodge.
      </p>

    </div>
  `;

  const markerEl=document.getElementById("timingMarker");

  function moveMarker(){

    if(!running)return;

    marker+=direction*1.4;

    if(marker>=97){
      marker=97;
      direction=-1;
    }

    if(marker<=1){
      marker=1;
      direction=1;
    }

    markerEl.style.left=marker+"%";

    raf(moveMarker);
  }

  raf(moveMarker);

  window.gallop=function(){

    if(!running)return;

    let points=2;

    if(marker>=42 && marker<=58){
      points=8;
    }else if(marker>=27 && marker<=73){
      points=5;
    }

    player+=points;

    ai+=6;

    round++;

    document.getElementById("playerHorse").style.left=
      Math.min(88,player*1.8)+"%";

    document.getElementById("aiHorse").style.left=
      Math.min(88,ai*1.8)+"%";

    document.getElementById("raceScore").textContent=
      `Round ${Math.min(round,10)} / 10 • You ${player} • AI ${ai}`;

    if(round>=10){

      running=false;

      const passed=player>ai;

      finishGame(
        8,
        passed,
        passed
        ?`You beat the admirer! 🏇💗`
        :`The admirer reached the finish first.`,
        passed?180:0
      );
    }
  };
}

/* =========================================================
   9. HEARTBREAK CHAMBER
========================================================= */

function gameChamber(){

  const clues={
    desk:"A note says: the first digit is 0.",
    drawer:"A little card says: the second digit is 6.",
    flower:"A birthday clue points to July: 07.",
    frame:"The final clue says: the birthday day is 22."
  };

  let found=[];

  document.getElementById("gameContent").innerHTML=`
    ${gameHeader("🔎 Heartbreak Chamber","Find four clues")}

    <div class="game-card">
      <p>Search the room and collect every clue.</p>

      <div class="game-buttons">
        <button class="answer-button" onclick="window.findClue('desk')">
          🗄️ Desk
        </button>

        <button class="answer-button" onclick="window.findClue('drawer')">
          📦 Drawer
        </button>

        <button class="answer-button" onclick="window.findClue('flower')">
          🌸 Flower Pot
        </button>

        <button class="answer-button" onclick="window.findClue('frame')">
          🖼️ Photo Frame
        </button>
      </div>

      <div id="clueBox" class="mini-display" style="margin-top:12px">
        🔐 The door is locked.
      </div>
    </div>
  `;

  window.findClue=function(name){

    if(found.includes(name))return;

    found.push(name);

    document.getElementById("clueBox").innerHTML=
      found.map(x=>clues[x]).join("<br><br>");

    if(found.length===4){

      later(()=>{
        finishGame(
          9,
          true,
          "You found every clue and escaped the chamber! 🔓💗",
          170
        );
      },800);
    }
  };
}

/* =========================================================
   10. BOXING
========================================================= */

function gameBoxing(){

  let playerHP=100;
  let enemyHP=80;
  let busy=false;
  let guarding=false;

  document.getElementById("gameContent").innerHTML=`
    ${gameHeader("🥊 Heartbreak Boxing Match","Knock out the opponent")}

    <div class="game-card">

      <div class="fighter">🥊</div>

      <div>Opponent</div>
      <div class="health">
        <div
          id="enemyHealth"
          class="health-fill"
          style="width:100%"
        ></div>
      </div>

      <div class="fighter">💗</div>

      <div>You</div>
      <div class="health">
        <div
          id="playerHealth"
          class="health-fill"
          style="width:100%"
        ></div>
      </div>

      <div
        id="boxingMessage"
        class="score-display"
      >
        Choose your move!
      </div>

      <div class="game-buttons four">
        <button class="answer-button" onclick="window.boxMove('punch')">
          👊 Punch
        </button>

        <button class="answer-button" onclick="window.boxMove('heavy')">
          💥 Heavy
        </button>

        <button class="answer-button" onclick="window.boxMove('block')">
          🛡️ Block
        </button>

        <button class="answer-button" onclick="window.boxMove('dodge')">
          💨 Dodge
        </button>
      </div>
    </div>
  `;

  function update(){

    document.getElementById("enemyHealth").style.width=
      Math.max(0,enemyHP)/80*100+"%";

    document.getElementById("playerHealth").style.width=
      Math.max(0,playerHP)+"%";
  }

  window.boxMove=function(move){

    if(busy)return;
    busy=true;

    let damage=0;

    if(move==="punch")damage=10;
    if(move==="heavy")damage=18;

    if(move==="block"){
      guarding=true;
    }else{
      guarding=false;
    }

    if(move==="dodge"){
      document.getElementById("boxingMessage").textContent=
        "You dodged!";
    }else{

      enemyHP-=damage;

      document.getElementById("boxingMessage").textContent=
        damage
        ?`You dealt ${damage} damage!`
        :"You guarded!";
    }

    update();

    if(enemyHP<=0){
      finishGame(
        10,
        true,
        "You won the heartbreak boxing match! 🥊💗",
        190
      );
      return;
    }

    later(()=>{

      const enemyDamage=
        Math.floor(Math.random()*11)+7;

      if(!guarding){
        playerHP-=enemyDamage;

        document.getElementById("boxingMessage").textContent=
          `The opponent hit you for ${enemyDamage}!`;
      }else{
        document.getElementById("boxingMessage").textContent=
          "Your guard blocked the attack!";
      }

      update();

      if(playerHP<=0){

        finishGame(
          10,
          false,
          "You were knocked out!",
          0
        );

      }else{
        busy=false;
      }

    },600);
  };
}

/* =========================================================
   11. PERFECT MATCH
========================================================= */

function gamePerfectMatch(){

  const objects=[
    ["🌸","target0"],
    ["🐬","target1"],
    ["🌻","target2"],
    ["🌹","target3"],
    ["💗","target4"]
  ];

  let matched=0;

  document.getElementById("gameContent").innerHTML=`
    ${gameHeader("🧲 Perfect Match","Match each object")}

    <div class="game-card">
      <p>Drag each item onto its matching outline.</p>

      <div class="match-board" id="matchBoard">

        ${objects.map((o,i)=>`
          <div
            class="match-target"
            id="target${i}"
            data-value="${o[0]}"
            style="
              right:${10+i%2*45}%;
              top:${20+Math.floor(i/2)*90}px;
            "
          >
            ${o[0]}
          </div>

          <div
            class="match-item"
            id="match${i}"
            data-value="${o[0]}"
            style="
              left:${5+(i%3)*31}%;
              top:${10+Math.floor(i/3)*150}px;
            "
          >
            ${o[0]}
          </div>
        `).join("")}

      </div>
    </div>
  `;

  const board=document.getElementById("matchBoard");

  objects.forEach((o,i)=>{

    const item=document.getElementById("match"+i);

    let dragging=false;

    function move(e){

      if(!dragging)return;

      const rect=board.getBoundingClientRect();

      let x=e.clientX-rect.left-30;
      let y=e.clientY-rect.top-30;

      x=Math.max(0,Math.min(rect.width-60,x));
      y=Math.max(0,Math.min(rect.height-60,y));

      item.style.left=x+"px";
      item.style.top=y+"px";
    }

    item.addEventListener("pointerdown",e=>{
      e.preventDefault();
      dragging=true;
      item.setPointerCapture(e.pointerId);
    });

    item.addEventListener("pointermove",move);

    item.addEventListener("pointerup",e=>{

      dragging=false;

      const target=document.getElementById("target"+i);

      const a=item.getBoundingClientRect();
      const b=target.getBoundingClientRect();

      const overlap=
        a.left<b.right &&
        a.right>b.left &&
        a.top<b.bottom &&
        a.bottom>b.top;

      if(overlap){

        item.style.left=
          target.offsetLeft+
          (target.offsetWidth-60)/2+
          "px";

        item.style.top=
          target.offsetTop+
          (target.offsetHeight-60)/2+
          "px";

        item.style.opacity=".3";
        item.style.pointerEvents="none";

        matched++;
        addPoints(25);

        if(matched===objects.length){

          finishGame(
            11,
            true,
            "Every object found its perfect match! 🧲💗",
            160
          );
        }
      }
    });
  });
}

/* =========================================================
   12. WHO KNOWS LILIANA BEST
========================================================= */

const lilianaQuiz=[
  ["What is Liliana's favourite colour?",["Baby pink","Burgundy","Sky blue","Purple"],0],
  ["What is Liliana's favourite number?",["3","7","6","22"],0],
  ["Which food does Liliana like?",["Sushi","Pizza","Tacos","Curry"],0],
  ["Which animal does Liliana like?",["Dolphins","Lions","Foxes","Penguins"],0],
  ["Which flowers does Liliana like?",["Sunflowers and roses","Lilies and tulips","Orchids and daisies","Lavender and violets"],0],
  ["When is Liliana's birthday?",["22 July","7 February","22 June","12 July"],0],
  ["What colour are Liliana's eyes?",["Green","Blue","Brown","Hazel"],0],
  ["What is Liliana's star sign?",["Leo","Cancer","Virgo","Libra"],0],
  ["What is Liliana afraid of?",["Drowning","Flying","Heights","Spiders"],0],
  ["What is Liliana's favourite movie?",["Me Before You","Titanic","Frozen","The Notebook"],0],
  ["What does Liliana enjoy reading or writing?",["Poetry","History","Crime novels","Comics"],0],
  ["What subject did Liliana study at university?",["Psychology","Law","Biology","Art"],0],
  ["How many nieces does Liliana have?",["1","2","3","4"],0],
  ["How many nephews does Liliana have?",["4","1","2","5"],0],
  ["How many siblings does Liliana have?",["5","3","4","6"],0],
  ["How many piercings does Liliana have?",["4","2","3","5"],0],
  ["What are the names of Liliana's dogs?",["Aayla and Arlo","Luna and Milo","Bella and Max","Ayla and Leo"],0],
  ["How long have Bree and Liliana been best friends?",["6 years","3 years","5 years","7 years"],0]
].map(q=>({question:q[0],options:q[1],answer:q[2]}));

function gameLilianaQuiz(){

  let qs=shuffle(lilianaQuiz).slice(0,12);
  let i=0;
  let correct=0;

  function show(){

    const q=qs[i];
    const answers=shuffledQuestion(q);

    document.getElementById("gameContent").innerHTML=`
      ${gameHeader("💗 Who Knows Liliana Best?",`${i+1}/12`)}

      <div class="game-card">
        <h2>${q.question}</h2>

        <div class="game-buttons four">
          ${answers.map(a=>`
            <button
              class="answer-button"
              onclick="window.luluQuizAnswer(${a.correct?1:0})"
            >
              ${a.text}
            </button>
          `).join("")}
        </div>
      </div>
    `;
  }

  window.luluQuizAnswer=function(ok){

    if(ok){
      correct++;
      addPoints(30);
    }

    i++;

    if(i>=12){

      finishGame(
        12,
        correct>=8,
        `You knew ${correct}/12 answers about Liliana!`,
        correct*12
      );

    }else{
      show();
    }
  };

  show();
}

/* =========================================================
   13. REACTION GAUNTLET
========================================================= */

function gameReaction(){

  const commands=[
    "TAP NOW",
    "DON'T TAP",
    "LEFT",
    "RIGHT"
  ];

  let round=0;
  let score=0;
  let active=false;
  let expected="";
  let timer=null;

  function show(){

    active=false;

    expected=
      commands[Math.floor(Math.random()*commands.length)];

    document.getElementById("gameContent").innerHTML=`
      ${gameHeader("⚡ Reaction Gauntlet",`${round+1}/10`)}

      <div class="game-card">

        <div
          id="reactionDisplay"
          class="mini-display"
        >
          ${expected}
        </div>

        <button
          class="primary"
          onclick="window.reactionPress()"
        >
          TAP
        </button>

        <div class="game-buttons">
          <button class="secondary" onclick="window.reactionSide('LEFT')">
            ⬅️ LEFT
          </button>

          <button class="secondary" onclick="window.reactionSide('RIGHT')">
            RIGHT ➡️
          </button>
        </div>
      </div>
    `;

    active=true;

    timer=setTimeout(()=>{

      if(active){
        active=false;

        if(expected==="DON'T TAP"){
          score++;
          addPoints(20);
        }

        next();
      }

    },1200);

    timers.push(timer);
  }

  window.reactionPress=function(){

    if(!active)return;

    active=false;
    clearTimeout(timer);

    if(expected==="TAP NOW"){
      score++;
      addPoints(20);
    }

    next();
  };

  window.reactionSide=function(side){

    if(!active)return;

    active=false;
    clearTimeout(timer);

    if(expected===side){
      score++;
      addPoints(20);
    }

    next();
  };

  function next(){

    round++;

    if(round>=10){

      finishGame(
        13,
        score>=7,
        `You got ${score}/10 reactions right!`,
        score*10
      );

    }else{
      later(show,300);
    }
  }

  show();
}

/* =========================================================
   14. HEART HUNT
========================================================= */

function gameHeartHunt(){

  let found=0;
  let running=true;
  let hearts=[];

  document.getElementById("gameContent").innerHTML=`
    ${gameHeader("🕵️ Heart Hunt","Find 10 hidden hearts")}

    <div class="score-display" id="huntScore">
      💗 0 / 10
    </div>

    <div class="hunt-area" id="huntArea"></div>
  `;

  const area=document.getElementById("huntArea");

  for(let i=0;i<12;i++){

    const h=document.createElement("button");

    h.className="hunt-heart";
    h.textContent=i<10?"💗":"🌸";

    h.style.left=(5+Math.random()*85)+"%";
    h.style.top=(5+Math.random()*85)+"%";

    h.onclick=()=>{

      if(!running)return;

      if(h.textContent==="💗"){

        found++;
        addPoints(12);

        h.remove();

        document.getElementById("huntScore").textContent=
          `💗 ${found} / 10`;

        if(found>=10){

          running=false;

          finishGame(
            14,
            true,
            "You found all the hidden hearts! 💗",
            150
          );
        }
      }
    };

    area.appendChild(h);
    hearts.push(h);
  }

  every(()=>{

    if(!running)return;

    hearts.forEach(h=>{

      if(!h.isConnected)return;

      h.style.left=
        Math.max(3,Math.min(88,
          parseFloat(h.style.left)+(Math.random()*10-5)
        ))+"%";

      h.style.top=
        Math.max(3,Math.min(88,
          parseFloat(h.style.top)+(Math.random()*10-5)
        ))+"%";
    });

  },900);
}

/* =========================================================
   15. LOVE LOCK
========================================================= */

function gameLoveLock(){

  let code="";
  const answer="060722";

  document.getElementById("gameContent").innerHTML=`
    ${gameHeader("🔐 Love Lock","Crack the combination")}

    <div class="game-card">

      <p>
        The clue is hidden in the friendship:
        <br><br>
        🎂 Liliana's birthday is <strong>22 July</strong>.
        <br>
        💗 You've been best friends for <strong>6 years</strong>.
      </p>

      <div class="lock-display" id="lockDisplay">••••••</div>

      <div class="keypad">
        ${[1,2,3,4,5,6,7,8,9,0].map(n=>`
          <button onclick="window.lockKey('${n}')">
            ${n}
          </button>
        `).join("")}
        <button onclick="window.lockClear()">C</button>
        <button onclick="window.lockEnter()">🔓</button>
      </div>
    </div>
  `;

  window.lockKey=function(n){

    if(code.length>=6)return;

    code+=n;

    document.getElementById("lockDisplay").textContent=
      code.padEnd(6,"•");
  };

  window.lockClear=function(){
    code="";
    document.getElementById("lockDisplay").textContent="••••••";
  };

  window.lockEnter=function(){

    if(code===answer){

      addPoints(250);

      finishGame(
        15,
        true,
        "🔓 The Love Lock opened! The code was 060722.",
        250
      );

    }else{

      document.getElementById("lockDisplay").textContent=
        "❌";

      later(()=>{
        code="";
        document.getElementById("lockDisplay").textContent="••••••";
      },700);
    }
  };
}

/* =========================================================
   16. CUPID SHOOTOUT
========================================================= */

function gameCupid(){

  let score=0;
  let shots=0;
  let running=true;

  document.getElementById("gameContent").innerHTML=`
    ${gameHeader("🏹 Cupid Shootout","Hit 8 hearts")}

    <div class="score-display" id="cupidScore">
      Score: 0 • Shots: 0/15
    </div>

    <div class="shoot-area" id="shootArea"></div>
  `;

  const area=document.getElementById("shootArea");

  function spawn(){

    if(!running)return;

    const h=document.createElement("button");

    h.className="shoot-heart";

    const gold=Math.random()<.18;

    h.textContent=gold?"💛":"💗";
    h.dataset.value=gold?"30":"10";

    h.style.left=(5+Math.random()*80)+"%";
    h.style.top=(5+Math.random()*80)+"%";

    h.onclick=()=>{

      if(!running)return;

      score+=Number(h.dataset.value);
      shots++;

      addPoints(Number(h.dataset.value));

      h.remove();

      update();

      if(score>=80 || shots>=15){

        running=false;

        finishGame(
          16,
          score>=80,
          `Cupid scored ${score} points in ${shots} shots!`,
          score
        );
      }else{
        spawn();
      }
    };

    area.appendChild(h);

    later(()=>{
      if(h.isConnected){

        h.remove();
        shots++;

        update();

        if(shots>=15){

          running=false;

          finishGame(
            16,
            score>=80,
            `Cupid scored ${score} points.`,
            score
          );

        }else{
          spawn();
        }
      }
    },1700);
  }

  function update(){

    document.getElementById("cupidScore").textContent=
      `Score: ${score} • Shots: ${shots}/15`;
  }

  spawn();
}

/* =========================================================
   17. COUNTDOWN
========================================================= */

function gameCountdown(){

  let challenge=0;
  let successes=0;

  const types=[
    "bar",
    "sequence",
    "green",
    "smallest",
    "hold",
    "miniMemory"
  ];

  function next(){

    if(challenge>=6){

      finishGame(
        17,
        successes>=4,
        `You passed ${successes}/6 Countdown challenges!`,
        successes*30
      );

      return;
    }

    const type=types[challenge];

    if(type==="bar")barChallenge();
    if(type==="sequence")sequenceChallenge();
    if(type==="green")greenChallenge();
    if(type==="smallest")smallestChallenge();
    if(type==="hold")holdChallenge();
    if(type==="miniMemory")miniMemoryChallenge();
  }

  function heading(name){
    document.getElementById("gameContent").innerHTML=`
      ${gameHeader("⏳ The Countdown",`${challenge+1}/6`)}
      <div class="game-card">
        <h2>${name}</h2>
        <div id="countdownChallenge"></div>
      </div>
    `;
  }

  function result(ok){
    if(ok){
      successes++;
      addPoints(30);
    }

    challenge++;
    later(next,500);
  }

  function barChallenge(){

    heading("Stop the marker in the green zone!");

    const box=document.getElementById("countdownChallenge");

    box.innerHTML=`
      <div class="countdown-bar">
        <div class="countdown-zone"></div>
        <div
          id="cdMarker"
          class="countdown-marker"
          style="left:0%"
        ></div>
      </div>

      <button class="primary" onclick="window.stopCountdownBar()">
        STOP
      </button>
    `;

    let pos=0;
    let dir=1;

    function move(){

      pos+=dir*1.7;

      if(pos>=97){
        pos=97;
        dir=-1;
      }

      if(pos<=0){
        pos=0;
        dir=1;
      }

      const marker=document.getElementById("cdMarker");

      if(marker)marker.style.left=pos+"%";

      raf(move);
    }

    raf(move);

    window.stopCountdownBar=function(){
      result(pos>=40 && pos<=60);
    };
  }

  function sequenceChallenge(){

    heading("Tap the numbers in order: 1 → 2 → 3");

    document.getElementById("countdownChallenge").innerHTML=`
      <div class="game-buttons three">
        ${shuffle([1,2,3]).map(n=>`
          <button
            class="answer-button"
            onclick="window.sequenceTap(${n},this)"
          >
            ${n}
          </button>
        `).join("")}
      </div>
    `;

    let expected=1;

    window.sequenceTap=function(n){

      if(n===expected){

        expected++;

        if(expected===4){
          result(true);
        }

      }else{
        result(false);
      }
    };
  }

  function greenChallenge(){

    heading("Tap only the hearts!");

    let taps=0;
    let good=0;

    const box=document.getElementById("countdownChallenge");

    box.innerHTML=`
      <div class="game-buttons">
        ${Array.from({length:6},(_,i)=>`
          <button
            class="answer-button"
            onclick="window.greenTap(${i})"
          >
            ${i%2===0?"💗":"🔴"}
          </button>
        `).join("")}
      </div>
    `;

    window.greenTap=function(i){

      taps++;

      if(i%2===0)good++;

      if(taps>=3){
        result(good>=2);
      }
    };
  }

  function smallestChallenge(){

    heading("Choose the smallest number");

    const nums=shuffle([17,4,9,12]);

    document.getElementById("countdownChallenge").innerHTML=`
      <div class="game-buttons four">
        ${nums.map(n=>`
          <button
            class="answer-button"
            onclick="window.smallestTap(${n})"
          >
            ${n}
          </button>
        `).join("")}
      </div>
    `;

    window.smallestTap=function(n){
      result(n===4);
    };
  }

  function holdChallenge(){

    heading("Hold the button until the meter is full!");

    document.getElementById("countdownChallenge").innerHTML=`
      <div class="progress-bar">
        <div
          id="holdProgress"
          class="progress-fill"
        ></div>
      </div>

      <button
        id="holdButton"
        class="primary"
      >
        HOLD
      </button>
    `;

    let value=0;
    let holding=false;

    const button=document.getElementById("holdButton");

    button.addEventListener("pointerdown",()=>{
      holding=true;
    });

    ["pointerup","pointercancel","pointerleave"].forEach(type=>{
      button.addEventListener(type,()=>{
        holding=false;
      });
    });

    const id=setInterval(()=>{

      if(holding)value+=5;
      else value-=2;

      value=Math.max(0,Math.min(100,value));

      const p=document.getElementById("holdProgress");

      if(p)p.style.width=value+"%";

      if(value>=100){
        clearInterval(id);
        result(true);
      }

    },100);

    timers.push(id);
  }

  function miniMemoryChallenge(){

    heading("Remember the three symbols!");

    const symbols=["🌸","💗","🐬","🌻"];

    const sequence=Array.from(
      {length:3},
      ()=>symbols[Math.floor(Math.random()*symbols.length)]
    );

    const box=document.getElementById("countdownChallenge");

    box.innerHTML=`
      <div class="mini-display" id="miniMemoryDisplay">
        ${sequence.join(" ")}
      </div>
    `;

    later(()=>{

      box.innerHTML=`
        <p>Which symbol was FIRST?</p>

        <div class="game-buttons four">
          ${shuffle(symbols).map(s=>`
            <button
              class="answer-button"
              onclick="window.memoryMini('${s}')"
            >
              ${s}
            </button>
          `).join("")}
        </div>
      `;

    },1200);

    window.memoryMini=function(s){
      result(s===sequence[0]);
    };
  }

  next();
}

/* =========================================================
   18. ULTIMATE GAMBLE
========================================================= */

function gameGamble(){

  let pot=100;
  let turns=0;
  let finished=false;

  function show(){

    document.getElementById("gameContent").innerHTML=`
      ${gameHeader("🎲 Ultimate Gamble","Risk it or bank it")}

      <div class="game-card">

        <div class="gamble-pot">
          $${pot}
        </div>

        <div class="coin">
          ${pot>=300?"💰":"🪙"}
        </div>

        <p>
          Turn ${turns}/6
        </p>

        <div class="game-buttons">
          <button class="answer-button" onclick="window.gamble50()">
            🎲 Gamble 50%
            <br>
            Win ×2 / Lose half
          </button>

          <button class="answer-button" onclick="window.gamble25()">
            🔥 Risk 25%
            <br>
            Win ×4 / Lose all
          </button>

          <button class="primary" onclick="window.gambleBank()">
            💰 Safe Bank
          </button>

          <button class="secondary" onclick="window.gambleCash()">
            💗 Cash Out
          </button>
        </div>
      </div>
    `;
  }

  window.gamble50=function(){

    if(finished)return;

    turns++;

    if(Math.random()<.5){
      pot*=2;
    }else{
      pot=Math.floor(pot/2);
    }

    addPoints(Math.max(5,pot));

    check();
  };

  window.gamble25=function(){

    if(finished)return;

    turns++;

    if(Math.random()<.25){
      pot*=4;
    }else{
      pot=0;
    }

    check();
  };

  window.gambleBank=function(){

    if(finished)return;

    finished=true;

    finishGame(
      18,
      pot>100,
      `You banked $${pot}.`,
      Math.max(50,pot)
    );
  };

  window.gambleCash=function(){

    if(finished)return;

    finished=true;

    finishGame(
      18,
      pot>100,
      `You cashed out with $${pot}.`,
      Math.max(50,pot)
    );
  };

  function check(){

    if(pot>=300){

      finished=true;

      finishGame(
        18,
        true,
        `You reached the $300 target with $${pot}! 🎲`,
        pot
      );

    }else if(turns>=6){

      finished=true;

      finishGame(
        18,
        pot>100,
        `Your final pot was $${pot}.`,
        pot
      );

    }else{
      show();
    }
  }

  show();
}

/* =========================================================
   19. ADMIRER'S LAST STAND
========================================================= */

function gameLastStand(){

  let bossHP=120;
  let playerHP=100;
  let turn=0;
  let busy=false;

  function phase(){
    if(bossHP>80)return "PHASE 1";
    if(bossHP>40)return "PHASE 2";
    return "FINAL PHASE";
  }

  function show(){

    document.getElementById("gameContent").innerHTML=`
      ${gameHeader("👑 Admirer's Last Stand",phase())}

      <div class="game-card">

        <div class="boss">👑</div>

        <div>Admirer</div>
        <div class="health">
          <div
            id="bossHealth"
            class="health-fill"
            style="width:${bossHP/120*100}%"
          ></div>
        </div>

        <div>You</div>
        <div class="health">
          <div
            id="standHealth"
            class="health-fill"
            style="width:${playerHP}%"
          ></div>
        </div>

        <div class="score-display" id="standMessage">
          Choose your move.
        </div>

        <div class="game-buttons three">
          <button class="answer-button" onclick="window.standMove('attack')">
            ⚔️ Attack
          </button>

          <button class="answer-button" onclick="window.standMove('guard')">
            🛡️ Guard
          </button>

          <button class="answer-button" onclick="window.standMove('special')">
            💗 Special
          </button>
        </div>

      </div>
    `;
  }

  window.standMove=function(move){

    if(busy)return;

    busy=true;

    let damage=0;

    if(move==="attack")damage=13;
    if(move==="special")damage=25;

    if(move==="guard")damage=0;

    bossHP-=damage;

    if(bossHP<=0){

      finishGame(
        19,
        true,
        "You defeated the Admirer's Last Stand! 👑💗",
        260
      );

      return;
    }

    const phaseNow=phase();

    let bossDamage=
      phaseNow==="PHASE 1"
      ?10
      :phaseNow==="PHASE 2"
      ?14
      :18;

    if(move==="guard"){
      bossDamage=Math.floor(bossDamage/2);
    }

    playerHP-=bossDamage;

    if(playerHP<=0){

      finishGame(
        19,
        false,
        "The Admirer won the final stand.",
        0
      );

      return;
    }

    turn++;

    addPoints(damage);

    later(()=>{
      busy=false;
      show();
    },450);
  };

  show();
}

/* =========================================================
   20. LILIANA'S WORD FIND
========================================================= */

const wordList=[
  "LILIANA","LULU","FRIENDS","PINK","DOLPHIN",
  "SUNFLOWER","ROSE","SUSHI","POETRY","MUSIC",
  "PSYCHOLOGY","LEO","JULY","LOVE","FAMILY",
  "HEART","DREAM","AAYLA","ARLO","OCEAN",
  "FOREVER","THREE","SIXYEARS","CHARM","EMPATHY"
];

function gameWordFind(){

  const size=12;
  const grid=Array.from(
    {length:size},
    ()=>Array(size).fill("")
  );

  const placed=[];

  const directions=[
    [0,1],[0,-1],
    [1,0],[-1,0],
    [1,1],[1,-1],
    [-1,1],[-1,-1]
  ];

  function canPlace(word,r,c,dr,dc){

    for(let i=0;i<word.length;i++){

      const rr=r+dr*i;
      const cc=c+dc*i;

      if(
        rr<0 || rr>=size ||
        cc<0 || cc>=size
      )return false;

      if(
        grid[rr][cc] &&
        grid[rr][cc]!==word[i]
      )return false;
    }

    return true;
  }

  const sorted=shuffle(wordList)
    .sort((a,b)=>b.length-a.length);

  sorted.forEach(word=>{

    let done=false;

    for(let tries=0;tries<300 && !done;tries++){

      const [dr,dc]=
        directions[
          Math.floor(Math.random()*directions.length)
        ];

      const r=Math.floor(Math.random()*size);
      const c=Math.floor(Math.random()*size);

      if(canPlace(word,r,c,dr,dc)){

        const cells=[];

        for(let i=0;i<word.length;i++){

          const rr=r+dr*i;
          const cc=c+dc*i;

          grid[rr][cc]=word[i];

          cells.push(rr+","+cc);
        }

        placed.push({word,cells});
        done=true;
      }
    }
  });

  const alphabet="ABCDEFGHIJKLMNOPQRSTUVWXYZ";

  for(let r=0;r<size;r++){
    for(let c=0;c<size;c++){

      if(!grid[r][c]){
        grid[r][c]=
          alphabet[
            Math.floor(Math.random()*alphabet.length)
          ];
      }
    }
  }

  let found=new Set();
  let selecting=false;
  let selectedCells=[];

  document.getElementById("gameContent").innerHTML=`
    ${gameHeader("🔎 Liliana's Word Find","Find all 25 words")}

    <div class="game-card">

      <div class="word-grid" id="wordGrid"></div>

      <div class="word-list" id="wordList"></div>

    </div>
  `;

  const wordGrid=document.getElementById("wordGrid");
  const list=document.getElementById("wordList");

  list.innerHTML=wordList.map(w=>`
    <span
      class="word-chip"
      id="wordChip-${w}"
    >
      ${w}
    </span>
  `).join("");

  grid.forEach((row,r)=>{
    row.forEach((letter,c)=>{

      const button=document.createElement("button");

      button.className="word-letter";
      button.textContent=letter;
      button.dataset.r=r;
      button.dataset.c=c;

      wordGrid.appendChild(button);
    });
  });

  function cellFromPoint(x,y){

    const el=document.elementFromPoint(x,y);

    if(
      el &&
      el.classList.contains("word-letter")
    ){
      return el;
    }

    return null;
  }

  function addCell(el){

    if(!el)return;

    const key=
      el.dataset.r+","+el.dataset.c;

    if(!selectedCells.includes(key)){

      selectedCells.push(key);
      el.classList.add("selected");
    }
  }

  function checkSelection(){

    const forward=selectedCells.join("|");
    const reverse=[...selectedCells].reverse().join("|");

    placed.forEach(item=>{

      const target=item.cells.join("|");
      const reverseTarget=[...item.cells].reverse().join("|");

      if(
        (forward===target || forward===reverseTarget) &&
        !found.has(item.word)
      ){

        found.add(item.word);

        item.cells.forEach(key=>{

          const [r,c]=key.split(",").map(Number);

          const el=wordGrid.querySelector(
            `[data-r="${r}"][data-c="${c}"]`
          );

          if(el){
            el.classList.remove("selected");
            el.classList.add("found");
          }
        });

        document.getElementById(
          "wordChip-"+item.word
        ).classList.add("done");

        addPoints(20);
      }
    });

    document.querySelectorAll(".word-letter.selected")
      .forEach(el=>el.classList.remove("selected"));

    selectedCells=[];

    if(found.size>=placed.length){

      finishGame(
        20,
        true,
        "You found every word in Liliana's Word Find! 🔎💗",
        300
      );
    }
  }

  wordGrid.addEventListener("pointerdown",e=>{

    e.preventDefault();

    selecting=true;
    selectedCells=[];

    const el=cellFromPoint(e.clientX,e.clientY);
    addCell(el);

    wordGrid.setPointerCapture(e.pointerId);
  });

  wordGrid.addEventListener("pointermove",e=>{

    if(!selecting)return;

    e.preventDefault();

    addCell(
      cellFromPoint(e.clientX,e.clientY)
    );
  });

  wordGrid.addEventListener("pointerup",e=>{

    if(!selecting)return;

    selecting=false;

    checkSelection();
  });
}

/* =========================================================
   21. DRAW A SUNFLOWER
========================================================= */

function gameSunflower(){

  document.getElementById("gameContent").innerHTML=`
    ${gameHeader("🌻 Draw a Sunflower","Make your own")}

    <div class="game-card">

      <div class="canvas-wrap">
        <canvas id="drawingCanvas"></canvas>
      </div>

      <div class="brush-row">
        <button onclick="window.setBrush('#5b351c')">🤎</button>
        <button onclick="window.setBrush('#39734c')">💚</button>
        <button onclick="window.setBrush('#d99b2b')">💛</button>
        <button onclick="window.setBrush('#e65b86')">🩷</button>
        <button onclick="window.setBrush('#5b4c91')">💜</button>
      </div>

      <div class="brush-row">
        <button onclick="window.brushSize(4)">Small</button>
        <button onclick="window.brushSize(9)">Medium</button>
        <button onclick="window.brushSize(16)">Large</button>
        <button onclick="window.undoDrawing()">Undo</button>
        <button onclick="window.clearDrawing()">Clear</button>
      </div>

      <button class="primary" onclick="window.finishDrawing()">
        🌻 Finish Sunflower
      </button>
    </div>
  `;

  const canvas=document.getElementById("drawingCanvas");
  const ctx=canvas.getContext("2d");

  let drawing=false;
  let colour="#d99b2b";
  let size=9;
  let strokes=[];
  let current=[];

  function resize(){

    const rect=canvas.getBoundingClientRect();

    const old=document.createElement("canvas");

    old.width=canvas.width;
    old.height=canvas.height;

    if(canvas.width){
      old.getContext("2d").drawImage(canvas,0,0);
    }

    canvas.width=rect.width*devicePixelRatio;
    canvas.height=rect.height*devicePixelRatio;

    canvas.style.width=rect.width+"px";
    canvas.style.height=rect.height+"px";

    ctx.scale(devicePixelRatio,devicePixelRatio);

    if(old.width){
      ctx.drawImage(
        old,
        0,
        0,
        old.width,
        old.height,
        0,
        0,
        rect.width,
        rect.height
      );
    }
  }

  resize();

  function point(e){

    const rect=canvas.getBoundingClientRect();

    return {
      x:e.clientX-rect.left,
      y:e.clientY-rect.top
    };
  }

  canvas.addEventListener("pointerdown",e=>{

    e.preventDefault();

    drawing=true;
    current=[point(e)];

    canvas.setPointerCapture(e.pointerId);
  });

  canvas.addEventListener("pointermove",e=>{

    if(!drawing)return;

    e.preventDefault();

    const p=point(e);

    current.push(p);

    ctx.strokeStyle=colour;
    ctx.lineWidth=size;
    ctx.lineCap="round";
    ctx.lineJoin="round";

    const last=current[current.length-2];

    ctx.beginPath();
    ctx.moveTo(last.x,last.y);
    ctx.lineTo(p.x,p.y);
    ctx.stroke();
  });

  canvas.addEventListener("pointerup",()=>{
    if(drawing){
      drawing=false;
      strokes.push(current);
    }
  });

  window.setBrush=function(c){
    colour=c;
  };

  window.brushSize=function(s){
    size=s;
  };

  window.undoDrawing=function(){

    if(!strokes.length){
      window.clearDrawing();
      return;
    }

    strokes.pop();

    window.clearDrawing();

    strokes.forEach(stroke=>{

      for(let i=1;i<stroke.length;i++){

        ctx.strokeStyle=colour;
        ctx.lineWidth=size;
        ctx.lineCap="round";

        ctx.beginPath();
        ctx.moveTo(
          stroke[i-1].x,
          stroke[i-1].y
        );
        ctx.lineTo(
          stroke[i].x,
          stroke[i].y
        );
        ctx.stroke();
      }
    });
  };

  window.clearDrawing=function(){

    ctx.clearRect(
      0,
      0,
      canvas.width,
      canvas.height
    );

    strokes=[];
  };

  window.finishDrawing=function(){

    const points=strokes.reduce(
      (total,s)=>total+s.length,
      0
    );

    const score=
      points>300
      ?180
      :points>100
      ?120
      :70;

    finishGame(
      21,
      true,
      "Your sunflower is officially part of the Lulu Express garden. 🌻💗",
      score
    );
  };
}

/* =========================================================
   22. LULU DERBY
   EXACTLY 100 RANDOM TRIVIA QUESTIONS
========================================================= */

const derbyQuestions=[
  ["What is the capital of Canada?",["Ottawa","Toronto","Vancouver","Montreal"],0],
  ["What is the largest mammal?",["Blue whale","Elephant","Giraffe","Orca"],0],
  ["How many months are in a year?",["12","10","11","13"],0],
  ["What is the currency of the United Kingdom?",["Pound","Euro","Dollar","Franc"],0],
  ["Which planet is closest to the Sun?",["Mercury","Venus","Mars","Earth"],0],
  ["How many chess pieces does each player start with?",["16","12","18","20"],0],
  ["Who wrote the Harry Potter books?",["J.K. Rowling","Suzanne Collins","Stephen King","C.S. Lewis"],0],
  ["What is the largest continent?",["Asia","Africa","Europe","North America"],0],
  ["Which instrument usually has 88 keys?",["Piano","Violin","Flute","Trumpet"],0],
  ["What is the chemical symbol for oxygen?",["O","Ox","Og","C"],0],
  ["What is the square root of 81?",["9","8","7","10"],0],
  ["In which year did Apollo 11 land on the Moon?",["1969","1965","1972","1959"],0],
  ["Where is the Great Pyramid of Giza?",["Egypt","Greece","Mexico","Jordan"],0],
  ["What is the main language of Brazil?",["Portuguese","Spanish","French","Italian"],0],
  ["What is the world's largest desert?",["Antarctica","Sahara","Gobi","Arabian"],0],
  ["What is the highest score called in tennis before game point?",["40","30","45","50"],0],
  ["Which vitamin is commonly produced by the body through sunlight exposure?",["Vitamin D","Vitamin C","Vitamin B12","Vitamin K"],0],
  ["About how many bones are in an adult human body?",["206","186","216","256"],0],
  ["The Amazon rainforest is mainly in which continent?",["South America","Africa","Asia","Europe"],0],
  ["Big Ben is associated with which city?",["London","Paris","Rome","Dublin"],0],
  ["Which ocean is the largest?",["Pacific","Atlantic","Indian","Arctic"],0],
  ["How many moons does Mars have?",["2","1","3","4"],0],
  ["Which planet is the hottest on average?",["Venus","Mercury","Mars","Jupiter"],0],
  ["Approximately how fast does light travel?",["300,000 km/s","30,000 km/s","3,000 km/s","3 million km/s"],0],
  ["Who wrote Romeo and Juliet?",["William Shakespeare","Charles Dickens","Homer","George Orwell"],0],
  ["Which continent is home to most wild penguins?",["Antarctica","Europe","Africa","Asia"],0],
  ["What is India's currency?",["Rupee","Yen","Won","Peso"],0],
  ["The Taj Mahal is in which country?",["India","Pakistan","Nepal","Bangladesh"],0],
  ["Who was the Greek god of the sea?",["Poseidon","Zeus","Apollo","Ares"],0],
  ["What does the Roman numeral X represent?",["10","5","50","100"],0],
  ["How many Olympic rings are there?",["5","4","6","7"],0],
  ["How many suits are in a standard deck of cards?",["4","3","5","6"],0],
  ["How many cards are in a standard deck?",["52","48","54","50"],0],
  ["How many sides does a square have?",["4","3","5","6"],0],
  ["The Nile River is mainly associated with which continent?",["Africa","Asia","Europe","South America"],0],
  ["The Alps are a mountain range in which continent?",["Europe","Africa","Asia","Australia"],0],
  ["Approximately how many strings does a concert piano have?",["About 230","About 50","About 500","About 100"],0],
  ["At what temperature does water freeze in Celsius?",["0°C","10°C","-10°C","5°C"],0],
  ["How many metres are in one kilometre?",["1000","100","500","10,000"],0],
  ["How many seconds are in one minute?",["60","30","100","90"],0],
  ["How many hours are in a day?",["24","12","36","48"],0],
  ["How many days are normally in a week?",["7","5","6","8"],0],
  ["How many days are in a common year?",["365","360","364","366"],0],
  ["Which planet is the eighth from the Sun?",["Neptune","Uranus","Saturn","Jupiter"],0],
  ["What is Pluto classified as?",["Dwarf planet","Gas giant","Moon","Star"],0],
  ["What shape is DNA commonly described as?",["Double helix","Single ring","Triangle","Cube"],0],
  ["What process allows plants to make food using sunlight?",["Photosynthesis","Respiration","Fermentation","Digestion"],0],
  ["Which organs are mainly used for breathing?",["Lungs","Kidneys","Liver","Stomach"],0],
  ["What do red blood cells mainly carry?",["Oxygen","Calcium","Food","Bile"],0],
  ["What is the largest organ of the human body?",["Skin","Liver","Heart","Lung"],0],
  ["Which part of the eye controls how much light enters?",["Iris","Retina","Lens","Cornea"],0],
  ["Which part of the brain is especially associated with higher thinking?",["Cerebrum","Cerebellum","Brain stem","Spinal cord"],0],
  ["What element has the symbol Fe?",["Iron","Fluorine","Francium","Fermium"],0],
  ["What element has the symbol Na?",["Sodium","Nitrogen","Neon","Nickel"],0],
  ["What element has the symbol K?",["Potassium","Krypton","Calcium","Copper"],0],
  ["What element has the symbol Ag?",["Silver","Gold","Argon","Aluminium"],0],
  ["What element has the symbol Cu?",["Copper","Carbon","Calcium","Cobalt"],0],
  ["What is CO₂?",["Carbon dioxide","Carbon monoxide","Oxygen","Methane"],0],
  ["A pH of 7 is generally considered what?",["Neutral","Strongly acidic","Strongly alkaline","Salty"],0],
  ["What force pulls objects toward Earth?",["Gravity","Friction","Magnetism","Pressure"],0],
  ["What is the SI unit of energy?",["Joule","Watt","Volt","Newton"],0],
  ["What is the SI unit of electric current?",["Ampere","Volt","Ohm","Watt"],0],
  ["Sound level is commonly measured in what?",["Decibels","Watts","Metres","Litres"],0],
  ["What instrument detects and records earthquakes?",["Seismometer","Barometer","Thermometer","Altimeter"],0],
  ["Molten rock beneath Earth's surface is called what?",["Magma","Lava","Granite","Basalt"],0],
  ["Clouds are mainly made from what?",["Water droplets and ice","Smoke","Dust only","Salt crystals"],0],
  ["How many colours are traditionally listed in a rainbow?",["7","5","6","8"],0],
  ["What shape is commonly associated with snowflake symmetry?",["Six-fold","Four-fold","Five-fold","Eight-fold"],0],
  ["How can honeybees communicate directions to food?",["Dance movements","Singing","Changing colour","Digging"],0],
  ["Where are butterfly taste receptors found?",["Feet","Wings","Antennae only","Eyes"],0],
  ["How many hearts does an octopus have?",["3","1","2","4"],0],
  ["How many neck vertebrae does a giraffe normally have?",["7","5","9","12"],0],
  ["Which bird is the largest living bird?",["Ostrich","Eagle","Emu","Swan"],0],
  ["Which animal is native to Australia?",["Kangaroo","Panda","Tiger","Moose"],0],
  ["Which bird is strongly associated with New Zealand?",["Kiwi","Toucan","Flamingo","Pelican"],0],
  ["Which animal is strongly associated with Australia and eucalyptus?",["Koala","Panda","Lemur","Sloth"],0],
  ["Mount Kilimanjaro is in which country?",["Tanzania","Kenya","Uganda","Ethiopia"],0],
  ["The Gobi Desert is mainly in which part of the world?",["Asia","Africa","Europe","South America"],0],
  ["The Amazon River is in which continent?",["South America","North America","Africa","Asia"],0],
  ["The Mediterranean Sea lies between which major regions?",["Europe and Africa","Asia and Australia","North and South America","Africa and Antarctica"],0],
  ["The Panama Canal connects which two major oceans?",["Atlantic and Pacific","Pacific and Indian","Atlantic and Arctic","Indian and Arctic"],0],
  ["The Suez Canal connects the Mediterranean Sea with which sea?",["Red Sea","Black Sea","Arabian Sea","Baltic Sea"],0],
  ["The Greenwich Meridian represents what longitude?",["0°","90°","180°","45°"],0],
  ["The Equator represents what latitude?",["0°","23.5°","45°","90°"],0],
  ["Which tropic lies in the Northern Hemisphere?",["Tropic of Cancer","Tropic of Capricorn","Arctic Circle","Equator"],0],
  ["Which continent is the coldest?",["Antarctica","Europe","Asia","North America"],0],
  ["Which is the smallest continent by land area?",["Australia","Europe","Antarctica","South America"],0],
  ["Which country contains Vatican City?",["Italy","France","Spain","Austria"],0],
  ["Which is the largest country by land area?",["Russia","Canada","China","Brazil"],0],
  ["Which sport is associated with Wimbledon?",["Tennis","Football","Golf","Cricket"],0],
  ["Which sport is played in the FIFA World Cup?",["Football","Basketball","Tennis","Rugby"],0],
  ["The Tour de France is mainly what type of event?",["Cycling race","Horse race","Car race","Running race"],0],
  ["The Super Bowl is associated with which sport?",["American football","Baseball","Ice hockey","Basketball"],0],
  ["How many players are on a basketball team on court for one side?",["5","6","7","11"],0],
  ["How many bases are there in baseball?",["4","3","5","6"],0],
  ["How many players are on a football/soccer team on the field?",["11","9","10","12"],0],
  ["How many points is a touchdown worth before any extra play?",["6","5","7","3"],0],
  ["Which chess piece moves in an L shape?",["Knight","Bishop","Rook","Queen"],0],
  ["Which chess piece can move diagonally any distance?",["Bishop","Knight","Rook","King"],0],
  ["Which chess piece is usually the most powerful?",["Queen","King","Bishop","Knight"],0],
  ["How many squares are on a chessboard?",["64","54","72","81"],0],
  ["What colour are bananas commonly when ripe?",["Yellow","Blue","Purple","Black"],0],
  ["Which fruit is traditionally associated with keeping doctors away?",["Apple","Orange","Pear","Banana"],0],
  ["Which drink is made from roasted coffee beans?",["Coffee","Tea","Lemonade","Cocoa"],0],
  ["What is sushi traditionally associated with?",["Japan","Italy","Brazil","Egypt"],0],
  ["Which instrument has black and white keys?",["Piano","Drum","Violin","Harp"],0],
  ["How many strings does a standard violin have?",["4","5","6","3"],0],
  ["Which material is made by bees and used in candles?",["Beeswax","Silk","Cotton","Latex"],0],
  ["What do caterpillars become?",["Butterflies or moths","Bees","Spiders","Beetles only"],0],
  ["What is a baby frog called?",["Tadpole","Calf","Pup","Cub"],0],
  ["Which planet is famous for the Great Red Spot?",["Jupiter","Mars","Saturn","Neptune"],0],
  ["What is Earth's natural satellite?",["Moon","Sun","Mars","Venus"],0],
  ["Which star is at the centre of our solar system?",["Sun","Sirius","Polaris","Vega"],0],
  ["What is the closest star to Earth?",["Sun","Sirius","Proxima Centauri","Polaris"],0],
  ["What is a group of stars forming a recognisable pattern called?",["Constellation","Galaxy","Planet","Nebula"],0]
];

function gameDerby(){

  let questions=shuffle(derbyQuestions).slice(0,100);
  let qIndex=0;
  let selectedHorse=null;

  const horses=[
    {name:"Lulu",emoji:"🐎",distance:0},
    {name:"Rosie",emoji:"🐴",distance:0},
    {name:"Daisy",emoji:"🦄",distance:0},
    {name:"Lucky",emoji:"🏇",distance:0}
  ];

  document.getElementById("gameContent").innerHTML=`
    ${gameHeader("🏇 THE LULU DERBY","100 trivia races")}

    <div class="game-card">

      <h2>Choose your horse</h2>

      <div class="derby-horses">
        ${horses.map((h,i)=>`
          <button
            class="horse-choice"
            onclick="window.chooseDerbyHorse(${i})"
            id="horseChoice${i}"
          >
            ${h.emoji}
            <br>
            <small>${h.name}</small>
          </button>
        `).join("")}
      </div>

      <div id="derbyQuestion"></div>

      <div class="derby-track">
        ${horses.map((h,i)=>`
          <div class="derby-line">
            <span class="derby-name">${h.emoji} ${h.name}</span>
            <div class="derby-bar">
              <div
                id="derbyProgress${i}"
                class="derby-progress"
              ></div>
            </div>
          </div>
        `).join("")}
      </div>

    </div>
  `;

  window.chooseDerbyHorse=function(i){

    selectedHorse=i;

    horses.forEach((_,n)=>{
      document.getElementById("horseChoice"+n)
        .classList.toggle("selected",n===i);
    });

    showQuestion();
  };

  function showQuestion(){

    if(selectedHorse===null)return;

    const q=questions[qIndex];
    const answers=shuffledQuestion(q);

    document.getElementById("derbyQuestion").innerHTML=`
      <div style="margin:15px 0">

        <div class="score-display">
          Question ${qIndex+1}/100
        </div>

        <h3 style="text-align:center">
          ${q.question}
        </h3>

        <div class="game-buttons">
          ${answers.map(a=>`
            <button
              class="answer-button"
              onclick="window.derbyAnswer(${a.correct?1:0})"
            >
              ${a.text}
            </button>
          `).join("")}
        </div>

      </div>
    `;
  }

  window.derbyAnswer=function(ok){

    if(selectedHorse===null)return;

    if(ok){

      horses[selectedHorse].distance+=
        2+Math.floor(Math.random()*3);

      addPoints(15);

    }else{

      horses[selectedHorse].distance+=
        Math.floor(Math.random()*2);

      const rivalIndexes=
        horses
          .map((_,i)=>i)
          .filter(i=>i!==selectedHorse);

      const rival=
        rivalIndexes[
          Math.floor(Math.random()*rivalIndexes.length)
        ];

      horses[rival].distance+=
        1+Math.floor(Math.random()*3);
    }

    qIndex++;

    updateTrack();

    if(qIndex>=100){

      const winnerIndex=
        horses.reduce(
          (best,h,i)=>
            h.distance>horses[best].distance?i:best,
          0
        );

      const passed=
        winnerIndex===selectedHorse;

      finishGame(
        22,
        passed,
        passed
        ?`🏆 ${horses[selectedHorse].name} won The Lulu Derby after 100 trivia questions!`
        :`${horses[winnerIndex].name} won the Derby. Your horse came second this time!`,
        passed?350:50
      );

    }else{
      showQuestion();
    }
  };

  function updateTrack(){

    const max=Math.max(
      1,
      ...horses.map(h=>h.distance)
    );

    horses.forEach((h,i)=>{

      document.getElementById(
        "derbyProgress"+i
      ).style.width=
        Math.min(100,h.distance/max*100)+"%";
    });
  }

  document.getElementById("derbyQuestion").innerHTML=`
    <div class="mini-display">
      Pick a horse to begin! 🏇
    </div>
  `;
}

/* =========================================================
   23. FINAL CHALLENGE
   50 UNIQUE LILIANA QUESTIONS
========================================================= */

const finalQuestions=[
  ["Which colour would Liliana most likely choose for a birthday theme?",["Baby pink","Navy blue","Bright orange","Forest green"],0],
  ["Which number has special significance for Liliana?",["3","8","11","27"],0],
  ["Which Japanese food does Liliana like?",["Sushi","Ramen","Tempura","Udon"],0],
  ["Which sea animal is one of Liliana's favourites?",["Dolphin","Shark","Seal","Walrus"],0],
  ["Which flower is one of Liliana's favourites?",["Sunflower","Daffodil","Orchid","Iris"],0],
  ["Which other flower does Liliana like?",["Rose","Lily","Carnation","Hydrangea"],0],
  ["Which month is Liliana's birthday in?",["July","June","August","May"],0],
  ["What day of the month is Liliana's birthday?",["22","12","27","7"],0],
  ["Which eye colour does Liliana have?",["Green","Hazel","Blue","Brown"],0],
  ["Which zodiac sign is Liliana?",["Leo","Cancer","Aries","Libra"],0],
  ["What is Liliana's biggest listed fear?",["Drowning","Flying","Thunder","Darkness"],0],
  ["Which movie is a favourite of Liliana's?",["Me Before You","The Notebook","Mamma Mia","Frozen"],0],
  ["What kind of songs does Liliana like?",["Sad songs","Only rock songs","Only classical songs","Only country songs"],0],
  ["Which form of writing does Liliana enjoy?",["Poetry","Biographies","News reports","Textbooks"],0],
  ["Which card game is associated with Liliana's interests?",["Poker","Bridge","Solitaire","Go Fish"],0],
  ["Liliana enjoys which type of games involving chance?",["Gambling games","Trivia only","Puzzle books","Racing simulators"],0],
  ["What does Liliana hope to become one day?",["A mum","A pilot","A chef","A singer"],0],
  ["What kind of baby does Liliana dream of having?",["A baby girl","Twin boys","A baby boy","Triplets"],0],
  ["What did Liliana study at university?",["Psychology","Medicine","Engineering","History"],0],
  ["How many nieces does Liliana have?",["1","2","3","4"],0],
  ["How many nephews does Liliana have?",["4","2","3","5"],0],
  ["How many siblings does Liliana have?",["5","4","6","3"],0],
  ["How many piercings does Liliana have?",["4","3","5","2"],0],
  ["Which dog is one of Liliana's pets?",["Aayla","Lola","Mika","Yuna"],0],
  ["What is the name of Liliana's other dog?",["Arlo","Kai","Rene","Doris"],0],
  ["How long have Bree and Liliana been best friends?",["6 years","4 years","7 years","5 years"],0],
  ["Which description best fits Liliana?",["Sweet and caring","Cold and distant","Quiet and unfriendly","Serious and stern"],0],
  ["Which quality is associated with Liliana?",["Charismatic","Impatient","Unkind","Careless"],0],
  ["Which quality describes Liliana's ability to understand others?",["Empathetic","Forgetful","Competitive","Reserved"],0],
  ["Which word fits Liliana's personality in the friendship?",["Caring","Hostile","Strict","Uninterested"],0],
  ["What does Liliana like when it comes to children?",["She likes children","She dislikes children","She avoids children","She has no opinion"],0],
  ["Which playful personality description has been associated with Liliana?",["Flirtatious","Shy","Serious","Stoic"],0],
  ["What place does Liliana want to see someday?",["The ocean","The desert","The Arctic","The Moon"],0],
  ["Which colour pairs naturally with Liliana's favourite colour for her theme?",["Pink and soft white","Black and neon green","Orange and purple","Brown and grey"],0],
  ["Which combination contains two of Liliana's favourite flowers?",["Sunflower and rose","Tulip and orchid","Daisy and lily","Violet and iris"],0],
  ["Which combination contains one food and one animal Liliana likes?",["Sushi and dolphins","Pizza and wolves","Tacos and bears","Pasta and horses"],0],
  ["What is the complete birthday date?",["22 July","7 July","22 August","12 July"],0],
  ["What number is formed by the day of Liliana's birthday?",["22","7","6","3"],0],
  ["What number represents the years of friendship?",["6","5","7","10"],0],
  ["How many nieces and nephews does Liliana have altogether?",["5","4","6","7"],0],
  ["Which pair correctly names Liliana's dogs?",["Aayla and Arlo","Aayla and Aria","Arlo and Luna","Bella and Arlo"],0],
  ["Which pair combines Liliana's university subject and favourite movie?",["Psychology and Me Before You","Law and Titanic","Art and Frozen","Biology and Mamma Mia"],0],
  ["Which pair combines Liliana's favourite number and birthday day?",["3 and 22","6 and 7","4 and 22","3 and 12"],0],
  ["Which pair combines Liliana's favourite colour and favourite animal?",["Baby pink and dolphins","Blue and lions","Purple and cats","Green and wolves"],0],
  ["Which statement about Liliana's flowers is correct?",["She likes sunflowers and roses","She only likes orchids","She only likes lilies","She dislikes flowers"],0],
  ["Which statement about Liliana's interests is correct?",["She likes poetry and sad songs","She only likes documentaries","She dislikes music","She only reads textbooks"],0],
  ["Which statement about Liliana's education is correct?",["She studied Psychology","She studied Engineering","She studied Architecture","She studied Chemistry"],0],
  ["Which statement about Liliana's future dream is correct?",["She wants to be a mum to a baby girl","She wants to become an astronaut","She wants to avoid having children","She wants to become a professional racer"],0],
  ["Which collection contains only known Liliana facts?",["Baby pink, dolphins, sushi","Blue, sharks, pizza","Purple, horses, curry","Orange, pandas, burgers"],0]
].map(q=>({question:q[0],options:q[1],answer:q[2]}));

function gameFinalChallenge(){

  let questions=shuffle(finalQuestions);
  let index=0;
  let correct=0;

  function show(){

    const q=questions[index];
    const answers=shuffledQuestion(q);

    document.getElementById("gameContent").innerHTML=`
      ${gameHeader("💕 THE FINAL CHALLENGE",`${index+1}/50`)}

      <div class="game-card">

        <div class="progress-bar">
          <div
            class="progress-fill"
            style="width:${index/50*100}%"
          ></div>
        </div>

        <div class="score-display">
          Correct: ${correct}
        </div>

        <h2>${q.question}</h2>

        <div class="game-buttons four">
          ${answers.map(a=>`
            <button
              class="answer-button"
              onclick="window.finalAnswer(${a.correct?1:0})"
            >
              ${a.text}
            </button>
          `).join("")}
        </div>

      </div>
    `;
  }

  window.finalAnswer=function(ok){

    if(ok){
      correct++;
      addPoints(40);
    }

    index++;

    if(index>=50){

      const passed=correct>=40;

      finishGame(
        23,
        passed,
        passed
        ?`You got ${correct}/50 and conquered the Final Challenge! 💕`
        :`You got ${correct}/50. You needed 40 correct answers to pass.`,
        correct*15
      );

    }else{
      show();
    }
  };

  show();
}

/* =========================================================
   STARTUP
========================================================= */

renderJourney();
updateMusicButtons();

/*
  Prevent accidental browser gestures that make the game
  zoom or scroll while the user is interacting with it.
*/

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
  Prevent double-tap zoom on the game area.
*/

let lastTouchEnd=0;

document.addEventListener("touchend",e=>{

  const now=Date.now();

  if(now-lastTouchEnd<=300){
    e.preventDefault();
  }

  lastTouchEnd=now;

},{passive:false});

/*
  Do not allow accidental page scrolling while a game
  screen is active.
*/

document.addEventListener("touchmove",e=>{

  const game=document.getElementById("gameScreen");

  if(
    game.classList.contains("active") &&
    !e.target.closest("input,textarea")
  ){
    e.preventDefault();
  }

},{passive:false});

</script>

</body>
</html>

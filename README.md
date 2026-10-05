<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0,user-scalable=no">
<meta name="theme-color" content="#170b13">
<title>Lulu Express 🚂💗</title>

<style>
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
:root{
 --bg:#11070d;
 --panel:#21101a;
 --panel2:#2c1421;
 --pink:#f59ac2;
 --pink2:#ffbfdc;
 --burg:#8e3159;
 --gold:#ffd36b;
 --text:#fff7fb;
 --muted:#c9aeba;
 --green:#77dfa2;
 --red:#ff7185;
}
html,body{
 margin:0;
 padding:0;
 min-height:100%;
 background:
 radial-gradient(circle at 20% 10%,#3a1729 0,transparent 30%),
 radial-gradient(circle at 85% 20%,#321225 0,transparent 28%),
 var(--bg);
 color:var(--text);
 font-family:system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;
}
body{overflow-x:hidden}
button,input{font:inherit}
button{
 border:0;
 cursor:pointer;
 color:var(--text);
 min-height:48px;
 border-radius:14px;
 padding:12px 18px;
 font-weight:800;
 transition:.15s transform,.15s opacity,.15s background;
}
button:active{transform:scale(.96)}
button:disabled{opacity:.45;cursor:not-allowed}
#app{min-height:100vh}
.topbar{
 position:sticky;
 top:0;
 z-index:50;
 background:rgba(17,7,13,.94);
 backdrop-filter:blur(12px);
 border-bottom:1px solid rgba(255,255,255,.08);
 padding:10px;
}
.topinner{
 max-width:850px;
 margin:auto;
 display:flex;
 gap:8px;
 align-items:center;
 justify-content:space-between;
}
.logo{font-size:18px;font-weight:900;white-space:nowrap}
.stats{display:flex;gap:7px;flex-wrap:wrap;justify-content:flex-end}
.stat{
 background:#2b1420;
 border:1px solid rgba(255,255,255,.08);
 padding:7px 10px;
 border-radius:10px;
 font-size:12px;
 font-weight:800;
}
.music{
 background:#5d2340;
 padding:8px 11px;
 font-size:12px;
}
.reset{
 background:#321724;
 padding:8px 11px;
 font-size:12px;
}
.screen{
 display:none;
 width:100%;
 min-height:calc(100vh - 70px);
 padding:22px 14px 45px;
}
.screen.active{display:block}
.page{
 width:min(760px,100%);
 margin:auto;
}
.hero{text-align:center;padding:25px 5px 20px}
.emoji{font-size:58px;display:block;margin-bottom:8px}
h1{font-size:clamp(30px,8vw,54px);margin:5px 0 10px}
h2{font-size:clamp(25px,7vw,38px);margin:5px 0 8px}
h3{margin:7px 0}
.subtitle{color:var(--muted);line-height:1.5}
.card{
 background:linear-gradient(145deg,rgba(54,24,39,.96),rgba(30,13,23,.96));
 border:1px solid rgba(255,255,255,.08);
 border-radius:22px;
 padding:18px;
 margin:12px 0;
 box-shadow:0 12px 35px rgba(0,0,0,.22);
}
.center{text-align:center}
.primary{
 background:linear-gradient(135deg,#b94775,#e17aa5);
 box-shadow:0 7px 18px rgba(190,62,113,.25);
}
.secondary{background:#4b2035}
.green{background:#246846}
.gold{background:#775b20}
.danger{background:#76263b}
.bigbtn{width:100%;font-size:18px;margin-top:12px}
input[type=text]{
 width:100%;
 background:#160a10;
 color:white;
 border:1px solid #70445a;
 border-radius:14px;
 padding:15px;
 outline:none;
}
input:focus{border-color:var(--pink)}
.progress{
 height:10px;
 background:#160a10;
 border-radius:99px;
 overflow:hidden;
 margin:12px 0;
}
.progress i{
 display:block;
 height:100%;
 width:0%;
 background:linear-gradient(90deg,var(--burg),var(--pink));
 transition:.3s width;
}
.message{
 min-height:28px;
 text-align:center;
 color:var(--pink2);
 font-weight:800;
 margin:10px 0;
}
.levelhead{text-align:center;margin-bottom:12px}
.levelnum{
 display:inline-block;
 background:#512039;
 border-radius:99px;
 padding:6px 12px;
 font-size:12px;
 font-weight:900;
 letter-spacing:.08em;
}
.nextbox{text-align:center;margin-top:18px}
.hidden{display:none!important}
.small{font-size:13px;color:var(--muted)}
.scorepop{
 position:fixed;
 pointer-events:none;
 font-weight:1000;
 color:var(--gold);
 animation:pop 1s forwards;
 z-index:100;
}
@keyframes pop{
 0%{opacity:1;transform:translateY(0)}
 100%{opacity:0;transform:translateY(-55px)}
}
.answergrid{
 display:grid;
 grid-template-columns:1fr 1fr;
 gap:10px;
}
.answer{
 background:#341726;
 border:1px solid #61364b;
 min-height:58px;
}
.answer.correct{background:#246846;border-color:#77dfa2}
.answer.wrong{background:#76263b}
@media(max-width:480px){
 .answergrid{grid-template-columns:1fr}
 .stats{max-width:250px}
 .logo{font-size:15px}
 .screen{padding-left:10px;padding-right:10px}
}

/* START */
.namebox{max-width:500px;margin:25px auto}
.heartfield{
 position:relative;
 height:170px;
 overflow:hidden;
 border-radius:18px;
 background:radial-gradient(circle,#471a31,#180b12);
}
.floatingheart{
 position:absolute;
 font-size:25px;
 animation:float 5s infinite ease-in-out;
}
@keyframes float{50%{transform:translateY(-25px) rotate(10deg)}}

/* BROKEN HEARTS */
.catchgame{
 position:relative;
 width:min(100%,380px);
 height:430px;
 margin:15px auto;
 overflow:hidden;
 background:linear-gradient(#1b0d25,#331427);
 border:2px solid #63324d;
 border-radius:20px;
 touch-action:none;
}
.catchheart{
 position:absolute;
 font-size:35px;
 user-select:none;
}
.catcher{
 position:absolute;
 bottom:10px;
 width:90px;
 height:42px;
 border-radius:20px;
 background:#d86f9d;
 display:flex;
 align-items:center;
 justify-content:center;
 font-size:27px;
}

/* MEMORY */
.memorygrid{
 display:grid;
 grid-template-columns:repeat(4,1fr);
 gap:8px;
 max-width:430px;
 margin:15px auto;
}
.memorytile{
 aspect-ratio:1;
 background:#321625;
 border:2px solid #63334c;
 font-size:25px;
}
.memorytile.lit{background:#e58ab2;color:#220b17}
.memorytile.done{background:#286b49}

/* SLOTS */
.reels{display:flex;gap:10px;justify-content:center;margin:25px 0}
.reel{
 width:85px;
 height:90px;
 display:flex;
 align-items:center;
 justify-content:center;
 background:#10070c;
 border:2px solid #9a4166;
 border-radius:16px;
 font-size:45px;
}
.lever{
 display:block;
 margin:auto;
 width:130px;
 background:#b94775;
}

/* VISUAL PUZZLE */
.patternrow,.choicevisuals{
 display:flex;
 gap:9px;
 justify-content:center;
 flex-wrap:wrap;
 margin:16px 0;
}
.tile{
 width:58px;height:58px;
 border-radius:12px;
 background:#543044;
 display:flex;align-items:center;justify-content:center;
 font-size:28px;
}
.visualchoice{
 min-width:90px;
 min-height:80px;
 background:#351827;
 border:2px solid #62344c;
 font-size:30px;
}

/* BLUFF */
.cardsrow{display:flex;gap:9px;justify-content:center;flex-wrap:wrap}
.playcard{
 width:70px;height:100px;
 background:#5c2240;
 border:2px solid #a45477;
 display:flex;align-items:center;justify-content:center;
 font-size:28px;
}
.playcard.revealed{background:#eee;color:#351522}

/* RACE */
.racehorse{
 font-size:48px;
 transition:margin-left .25s ease;
}
.racetrack{
 position:relative;
 height:80px;
 background:#171019;
 border-radius:15px;
 overflow:hidden;
 padding:10px;
}
.raceline{
 position:absolute;
 right:5px;top:0;
 height:100%;
 border-left:3px dashed var(--gold);
}
.timing{
 height:45px;
 background:#171019;
 border-radius:99px;
 position:relative;
 overflow:hidden;
 margin:15px 0;
}
.timingzone{
 position:absolute;
 left:42%;
 width:16%;
 height:100%;
 background:rgba(119,223,162,.65);
}
.timingneedle{
 position:absolute;
 top:0;
 left:0;
 width:5px;
 height:100%;
 background:white;
}
.gallop{font-size:22px;width:100%}

/* CHAMBER */
.room{
 display:grid;
 grid-template-columns:repeat(2,1fr);
 gap:10px;
}
.roomitem{
 min-height:105px;
 background:#351827;
 border:1px solid #64354c;
 display:flex;
 align-items:center;
 justify-content:center;
 flex-direction:column;
 font-size:32px;
}
.clues{display:flex;gap:7px;flex-wrap:wrap}
.clue{
 background:#563047;
 padding:8px 11px;
 border-radius:10px;
 font-size:13px;
}

/* BOXING */
.fighters{
 display:flex;
 justify-content:space-around;
 align-items:center;
 font-size:65px;
}
.health{
 height:16px;
 background:#13080e;
 border-radius:99px;
 overflow:hidden;
 margin:8px 0 16px;
}
.health i{display:block;height:100%;background:#d55a7f;width:100%}
.combatgrid{
 display:grid;
 grid-template-columns:1fr 1fr;
 gap:10px;
}

/* MATCH */
.matcharea{
 display:grid;
 grid-template-columns:1fr 1fr;
 gap:18px;
}
.matchitem,.matchtarget{
 min-height:70px;
 display:flex;
 align-items:center;
 justify-content:center;
 border-radius:15px;
 font-size:30px;
}
.matchitem{background:#4c2437;cursor:grab}
.matchtarget{border:2px dashed #9d6680}
.matchtarget.matched{background:#286b49;border-style:solid}

/* REACTION */
.reactionbox{
 min-height:230px;
 display:flex;
 align-items:center;
 justify-content:center;
 flex-direction:column;
 border-radius:20px;
 background:#2d1522;
 font-size:24px;
 text-align:center;
}
.reactionbutton{
 width:85%;
 min-height:85px;
 font-size:25px;
}

/* HEART HUNT */
.hunt{
 position:relative;
 height:390px;
 overflow:hidden;
 border-radius:20px;
 background:
 radial-gradient(circle at 30% 30%,#5c2944,transparent 12%),
 radial-gradient(circle at 75% 65%,#4a2038,transparent 18%),
 #190c14;
}
.huntheart{
 position:absolute;
 font-size:31px;
 cursor:pointer;
}
.decoy{position:absolute;font-size:28px;opacity:.45}

/* LOCK */
.lockdisplay{
 font-size:35px;
 letter-spacing:10px;
 text-align:center;
 background:#12080d;
 padding:18px;
 border-radius:14px;
 margin-bottom:12px;
}
.keypad{
 display:grid;
 grid-template-columns:repeat(3,1fr);
 gap:8px;
 max-width:350px;
 margin:auto;
}
.key{background:#422035;font-size:20px}

/* SHOOTOUT */
.shooting{
 position:relative;
 height:380px;
 border-radius:20px;
 background:linear-gradient(#24112d,#351629);
 overflow:hidden;
}
.target{
 position:absolute;
 font-size:38px;
 cursor:pointer;
}

/* COUNTDOWN */
.countbar{
 position:relative;
 height:42px;
 border-radius:99px;
 background:#14090e;
 overflow:hidden;
}
.countzone{
 position:absolute;
 left:42%;
 width:16%;
 top:0;
 height:100%;
 background:#4c9c6d;
}
.countneedle{
 position:absolute;
 top:0;
 left:0;
 height:100%;
 width:6px;
 background:white;
}

/* GAMBLE */
.pot{
 font-size:45px;
 text-align:center;
 color:var(--gold);
 font-weight:1000;
}
.gamblegrid{display:grid;grid-template-columns:1fr 1fr;gap:10px}

/* BOSS */
.boss{
 text-align:center;
 font-size:90px;
}
.bossactions{display:grid;grid-template-columns:1fr 1fr;gap:10px}

/* WORD FIND */
.wordwrap{overflow:auto}
.wordgrid{
 display:grid;
 grid-template-columns:repeat(12,1fr);
 gap:3px;
 max-width:600px;
 margin:15px auto;
}
.letter{
 aspect-ratio:1;
 min-width:0;
 padding:0;
 background:#321625;
 border-radius:5px;
 font-size:clamp(11px,3vw,18px);
}
.letter.selected,.letter.found{background:#a94c76}
.wordlist{
 display:flex;
 gap:6px;
 flex-wrap:wrap;
}
.wordtag{
 background:#3d2130;
 border-radius:9px;
 padding:6px 8px;
 font-size:11px;
}
.wordtag.found{background:#286b49;text-decoration:line-through}

/* DRAW */
#drawCanvas{
 display:block;
 width:100%;
 max-width:600px;
 height:430px;
 background:#fffafc;
 border-radius:16px;
 touch-action:none;
 cursor:crosshair;
 margin:auto;
}
.tools{
 display:flex;
 gap:8px;
 flex-wrap:wrap;
 margin:10px 0;
}
.tools button{background:#4a2336}
.colorinput{width:50px;height:48px;padding:3px}

/* DERBY */
.horselist{display:grid;grid-template-columns:repeat(2,1fr);gap:10px}
.horsechoice{
 background:#3b1d2d;
 border:2px solid #62354c;
 font-size:23px;
}
.horsechoice.selected{border-color:var(--gold);background:#624b20}
.derbytrack{margin:15px 0}
.horseline{
 background:#1b0d13;
 padding:9px;
 border-radius:12px;
 margin:7px 0;
}
.horsebar{
 height:13px;
 background:#12080d;
 border-radius:99px;
 overflow:hidden;
}
.horsebar i{display:block;height:100%;background:#d9789f;width:0%}

/* FINAL */
.finalnumber{
 font-size:14px;
 color:var(--pink);
 font-weight:900;
}
.results{text-align:center}
.reward{
 padding:20px;
 border-radius:20px;
 background:linear-gradient(135deg,#5c2740,#2b1320);
 border:1px solid #9c4c70;
}
</style>
</head>

<body>

<div id="app">

<header class="topbar">
 <div class="topinner">
  <div class="logo">🚂 Lulu Express</div>
  <div class="stats">
   <div class="stat">⭐ <span id="score">0</span></div>
   <div class="stat">🪙 <span id="tokens">0</span></div>
   <div class="stat">📍 <span id="progressText">0/23</span></div>
   <button class="music" id="musicBtn">🎵 Music</button>
   <button class="reset" id="resetBtn">↻ Reset</button>
  </div>
 </div>
</header>

<!-- START -->
<section class="screen active" id="startScreen">
 <div class="page">
  <div class="hero">
   <span class="emoji">🚂💗</span>
   <h1>Lulu Express</h1>
   <p class="subtitle">A 23-level journey made especially for Liliana.</p>
  </div>

  <div class="card namebox">
   <h2>Ready to begin?</h2>
   <p class="subtitle">Enter your name before the journey starts.</p>
   <form id="nameForm">
    <input id="playerName" type="text" maxlength="30" placeholder="Your name..." autocomplete="off" required>
    <button class="primary bigbtn" type="submit">🚂 Start the Journey</button>
   </form>
  </div>

  <div class="heartfield">
   <span class="floatingheart" style="left:8%;top:50%">💗</span>
   <span class="floatingheart" style="left:28%;top:20%;animation-delay:.5s">💖</span>
   <span class="floatingheart" style="left:50%;top:60%;animation-delay:1s">💕</span>
   <span class="floatingheart" style="left:70%;top:25%;animation-delay:1.5s">💗</span>
   <span class="floatingheart" style="left:88%;top:65%;animation-delay:2s">💞</span>
  </div>

  <div class="card center">
   <b>23 levels</b>
   <p class="small">Pass each level to unlock the next one. You can replay completed levels.</p>
  </div>
 </div>
</section>

<!-- GENERIC GAME SCREENS -->
<section class="screen" id="game1"><div class="page" id="g1"></div></section>
<section class="screen" id="game2"><div class="page" id="g2"></div></section>
<section class="screen" id="game3"><div class="page" id="g3"></div></section>
<section class="screen" id="game4"><div class="page" id="g4"></div></section>
<section class="screen" id="game5"><div class="page" id="g5"></div></section>
<section class="screen" id="game6"><div class="page" id="g6"></div></section>
<section class="screen" id="game7"><div class="page" id="g7"></div></section>
<section class="screen" id="game8"><div class="page" id="g8"></div></section>
<section class="screen" id="game9"><div class="page" id="g9"></div></section>
<section class="screen" id="game10"><div class="page" id="g10"></div></section>
<section class="screen" id="game11"><div class="page" id="g11"></div></section>
<section class="screen" id="game12"><div class="page" id="g12"></div></section>
<section class="screen" id="game13"><div class="page" id="g13"></div></section>
<section class="screen" id="game14"><div class="page" id="g14"></div></section>
<section class="screen" id="game15"><div class="page" id="g15"></div></section>
<section class="screen" id="game16"><div class="page" id="g16"></div></section>
<section class="screen" id="game17"><div class="page" id="g17"></div></section>
<section class="screen" id="game18"><div class="page" id="g18"></div></section>
<section class="screen" id="game19"><div class="page" id="g19"></div></section>
<section class="screen" id="game20"><div class="page" id="g20"></div></section>
<section class="screen" id="game21"><div class="page" id="g21"></div></section>
<section class="screen" id="game22"><div class="page" id="g22"></div></section>
<section class="screen" id="game23"><div class="page" id="g23"></div></section>
<section class="screen" id="results"><div class="page" id="resultsPage"></div></section>

</div>

<script>
"use strict";

/* =========================================================
   CORE STATE
========================================================= */

const TOTAL_LEVELS=23;
const SAVE_KEY="luluExpressFinal_v3";

let state={
 name:"",
 score:0,
 tokens:0,
 completed:0,
 unlocked:1
};

let currentLevel=0;
let cleanupFns=[];
let timers=[];
let intervals=[];
let rafs=[];

const $=id=>document.getElementById(id);

function save(){
 try{
  localStorage.setItem(SAVE_KEY,JSON.stringify(state));
 }catch(e){}
}

function load(){
 try{
  const s=JSON.parse(localStorage.getItem(SAVE_KEY)||"null");
  if(s && typeof s==="object"){
   state={...state,...s};
  }
 }catch(e){}
 updateStats();
}

function updateStats(){
 $("score").textContent=state.score;
 $("tokens").textContent=state.tokens;
 $("progressText").textContent=state.completed+"/23";
}

function addPoints(n){
 n=Math.max(0,Math.round(n||0));
 state.score+=n;
 updateStats();
 save();
}

function addTokens(n){
 n=Math.max(0,Math.round(n||0));
 state.tokens+=n;
 updateStats();
 save();
}

function popScore(text){
 const el=document.createElement("div");
 el.className="scorepop";
 el.textContent=text;
 el.style.left=(window.innerWidth/2-25)+"px";
 el.style.top=(window.innerHeight/2)+"px";
 document.body.appendChild(el);
 setTimeout(()=>el.remove(),1000);
}

function clearRuntime(){
 cleanupFns.forEach(fn=>{
  try{fn()}catch(e){}
 });
 cleanupFns=[];
 timers.forEach(clearTimeout);
 intervals.forEach(clearInterval);
 timers=[];
 intervals=[];
 rafs.forEach(cancelAnimationFrame);
 rafs=[];
}

function later(fn,ms){
 const id=setTimeout(fn,ms);
 timers.push(id);
 return id;
}

function every(fn,ms){
 const id=setInterval(fn,ms);
 intervals.push(id);
 return id;
}

function listen(el,event,fn,opts){
 if(!el)return;
 el.addEventListener(event,fn,opts);
 cleanupFns.push(()=>el.removeEventListener(event,fn,opts));
}

function shuffle(arr){
 for(let i=arr.length-1;i>0;i--){
  const j=Math.floor(Math.random()*(i+1));
  [arr[i],arr[j]]=[arr[j],arr[i]];
 }
 return arr;
}

function shuffledAnswers(q){
 const a=q.options.map((text,i)=>({
  text,
  correct:i===q.answer
 }));
 return shuffle(a);
}

function showScreen(id){
 document.querySelectorAll(".screen").forEach(s=>s.classList.remove("active"));
 $(id).classList.add("active");
 window.scrollTo(0,0);
}

function levelHeader(n,title,emoji,desc){
 return `
 <div class="levelhead">
  <div class="levelnum">LEVEL ${n} OF 23</div>
  <h2>${emoji} ${title}</h2>
  <p class="subtitle">${desc}</p>
 </div>`;
}

function finishLevel(n,message="Level complete!"){
 if(n>state.completed){
  state.completed=n;
  state.unlocked=Math.min(23,n+1);
  addTokens(3);
  save();
 }
 updateStats();

 const box=$(`g${n}`).querySelector(".nextbox");
 if(box){
  box.innerHTML=`
   <div class="card center">
    <h2>🎉 ${message}</h2>
    <p>⭐ Score: ${state.score} &nbsp; 🪙 Tokens: ${state.tokens}</p>
    ${
      n<TOTAL_LEVELS
      ? `<button class="primary bigbtn" id="nextLevel">➡️ Next Level</button>`
      : `<button class="primary bigbtn" id="finishJourney">💕 Finish Journey</button>`
    }
   </div>`;
  const btn=$("nextLevel")||$("finishJourney");
  listen(btn,"click",()=>{
   if(n<TOTAL_LEVELS)startLevel(n+1);
   else showResults();
  });
 }
}

function lockedScreen(n){
 showScreen("startScreen");
 alert("Finish the earlier levels first!");
}

/* =========================================================
   NAME / RESET
========================================================= */

$("nameForm").addEventListener("submit",e=>{
 e.preventDefault();
 const name=$("playerName").value.trim();
 if(!name)return;
 state.name=name;
 save();
 startLevel(1);
});

$("resetBtn").addEventListener("click",()=>{
 if(!confirm("Reset the entire Lulu Express journey?"))return;
 clearRuntime();
 localStorage.removeItem(SAVE_KEY);
 state={name:"",score:0,tokens:0,completed:0,unlocked:1};
 $("playerName").value="";
 updateStats();
 showScreen("startScreen");
});

load();

function startLevel(n){
 if(n<1||n>23)return;
 if(n>state.unlocked)return lockedScreen(n);
 clearRuntime();
 currentLevel=n;
 showScreen("game"+n);
 const fn=games[n];
 if(fn)fn();
}

/* =========================================================
   MUSIC
========================================================= */

const music=new Audio();
music.loop=true;
music.volume=.45;

let musicLoaded=false;

const musicBtn=$("musicBtn");

musicBtn.addEventListener("click",()=>{
 if(!musicLoaded){
  const input=document.createElement("input");
  input.type="file";
  input.accept="audio/*";
  input.style.display="none";
  document.body.appendChild(input);

  input.addEventListener("change",()=>{
   const file=input.files[0];
   if(!file)return;
   music.src=URL.createObjectURL(file);
   musicLoaded=true;
   music.play().then(()=>{
    musicBtn.textContent="⏸️ Music";
   }).catch(()=>{
    musicBtn.textContent="▶️ Music";
   });
  },{once:true});

  input.click();
  return;
 }

 if(music.paused){
  music.play().then(()=>musicBtn.textContent="⏸️ Music").catch(()=>{});
 }else{
  music.pause();
  musicBtn.textContent="▶️ Music";
 }
});

/* =========================================================
   1 BROKEN HEARTS
========================================================= */

function game1(){
 const root=$("g1");
 root.innerHTML=`
 ${levelHeader(1,"Broken Hearts","💔","Move your heart basket and catch 15 whole hearts. Avoid the broken ones!")}
 <div class="card">
  <div class="center">Caught: <b id="caught">0</b>/15 &nbsp; ❤️ Lives: <b id="lives">3</b></div>
  <div class="progress"><i id="catchProgress"></i></div>
  <div class="catchgame" id="catchgame">
   <div class="catcher" id="catcher">🧺💗</div>
  </div>
  <div class="message" id="catchMsg">Use your finger to move the basket.</div>
 </div>
 <div class="nextbox"></div>`;

 const area=$("catchgame"), catcher=$("catcher");
 let x=145,caught=0,lives=3,active=true;
 const hearts=new Set();

 function move(px){
  const r=area.getBoundingClientRect();
  x=Math.max(0,Math.min(r.width-90,px-r.left-45));
  catcher.style.left=x+"px";
 }
 listen(area,"pointermove",e=>{
  if(e.buttons)move(e.clientX);
 });
 listen(area,"pointerdown",e=>move(e.clientX));

 const spawn=()=>{
  if(!active)return;
  const h=document.createElement("div");
  h.className="catchheart";
  h.textContent=Math.random()<.16?"💔":"💗";
  h.dataset.x=String(Math.random()*(area.clientWidth-40));
  h.dataset.y="-40";
  h.style.left=h.dataset.x+"px";
  h.style.top="-40px";
  area.appendChild(h);
  hearts.add(h);
 };

 every(spawn,650);

 const tick=every(()=>{
  if(!active)return;
  hearts.forEach(h=>{
   let y=parseFloat(h.dataset.y)+3.2;
   h.dataset.y=y;
   h.style.top=y+"px";

   const hx=parseFloat(h.dataset.x);
   if(y>area.clientHeight-70){
    const hit=hx<x+90&&hx+35>x;
    if(hit){
     if(h.textContent==="💗"){
      caught++;
      $("caught").textContent=caught;
      $("catchProgress").style.width=(caught/15*100)+"%";
      addPoints(10);
      popScore("+10");
      if(caught>=15){
       active=false;
       hearts.forEach(q=>q.remove());
       finishLevel(1,"You caught all the hearts! 💗");
      }
     }else{
      lives--;
      $("lives").textContent=lives;
      addPoints(0);
      if(lives<=0){
       active=false;
       hearts.forEach(q=>q.remove());
       $("catchMsg").textContent="💔 Try again! You caught too many broken hearts.";
       later(game1,1200);
      }
     }
    }
    h.remove();
    hearts.delete(h);
   }
  });
 },45);

 cleanupFns.push(()=>{
  active=false;
  hearts.forEach(h=>h.remove());
 });
}

/* =========================================================
   2 MEMORY VAULT
========================================================= */

function game2(){
 const root=$("g2");
 root.innerHTML=`
 ${levelHeader(2,"Memory Vault","🧠","Watch the glowing sequence, then tap the same tiles. Eight rounds wins the level.")}
 <div class="card center">
  <b>Round <span id="memRound">1</span>/8</b>
  <div class="memorygrid" id="memoryGrid"></div>
  <div class="message" id="memMsg">Watch carefully...</div>
 </div>
 <div class="nextbox"></div>`;

 const grid=$("memoryGrid");
 let round=1,sequence=[],input=0,accepting=false;

 for(let i=0;i<16;i++){
  const b=document.createElement("button");
  b.className="memorytile";
  b.dataset.i=i;
  b.textContent="♥";
  listen(b,"click",()=>{
   if(!accepting)return;
   const i2=Number(b.dataset.i);
   if(i2===sequence[input]){
    b.classList.add("done");
    later(()=>b.classList.remove("done"),180);
    input++;
    if(input===sequence.length){
     accepting=false;
     addPoints(15+round*2);
     addTokens(1);
     if(round>=8){
      finishLevel(2,"Your memory is seriously impressive! 🧠💗");
     }else{
      round++;
      $("memRound").textContent=round;
      later(newRound,600);
     }
    }
   }else{
    accepting=false;
    $("memMsg").textContent="Almost! Let's give you another try.";
    later(newRound,700);
   }
  });
  grid.appendChild(b);
 }

 function newRound(){
  sequence=[];
  input=0;
  accepting=false;
  while(sequence.length<Math.min(2+Math.floor(round/2),6)){
   const n=Math.floor(Math.random()*16);
   if(!sequence.includes(n))sequence.push(n);
  }
  $("memMsg").textContent="Watch...";
  let i=0;
  const show=every(()=>{
   if(i>=sequence.length){
    clearInterval(show);
    accepting=true;
    $("memMsg").textContent="Your turn!";
    return;
   }
   const tile=grid.children[sequence[i]];
   tile.classList.add("lit");
   later(()=>tile.classList.remove("lit"),350);
   i++;
  },500);
  cleanupFns.push(()=>clearInterval(show));
 }
 newRound();
}

/* =========================================================
   3 PRESSURE QUIZ
========================================================= */

const pressureQuestions=[
["Which planet is known as the Red Planet?",["Mars","Venus","Jupiter","Mercury"],0],
["How many sides does a hexagon have?",["5","6","7","8"],1],
["What is the largest ocean on Earth?",["Atlantic","Indian","Pacific","Arctic"],2],
["Which animal is the fastest on land?",["Lion","Cheetah","Horse","Kangaroo"],1],
["How many minutes are in one hour?",["30","45","60","90"],2],
["What is H2O commonly called?",["Salt","Water","Oxygen","Hydrogen"],1],
["Which country is famous for the pyramids of Giza?",["Egypt","Greece","Italy","Mexico"],0],
["What colour do you get by mixing blue and yellow?",["Purple","Orange","Green","Pink"],2],
["Which is the smallest prime number?",["0","1","2","3"],2],
["What is the capital of Japan?",["Seoul","Tokyo","Beijing","Bangkok"],1],
["Which bird is commonly associated with delivering messages?",["Penguin","Pigeon","Owl","Swan"],1],
["How many days are in a leap year?",["364","365","366","367"],2],
["Which gas do humans need to breathe?",["Oxygen","Helium","Carbon dioxide","Neon"],0],
["What is the largest mammal?",["Elephant","Blue whale","Giraffe","Orca"],1],
["Which instrument has black and white keys?",["Violin","Flute","Piano","Trumpet"],2],
["What is 9 × 9?",["72","81","90","99"],1],
["Which continent is Australia part of?",["Europe","Oceania","Africa","Asia"],1],
["What do bees make?",["Honey","Milk","Silk","Bread"],0],
["Which season usually follows spring?",["Winter","Autumn","Summer","Monsoon"],2],
["What is the freezing point of water in Celsius?",["0","10","32","100"],0],
["Which shape has three sides?",["Square","Triangle","Circle","Pentagon"],1],
["Which planet is famous for its rings?",["Mars","Saturn","Earth","Venus"],1],
["What is the opposite of nocturnal?",["Diurnal","Circular","Seasonal","Lunar"],0],
["Which metal is strongly associated with the Olympic medals' top rank?",["Copper","Gold","Iron","Tin"],1],
["How many colours are traditionally in a rainbow?",["5","6","7","8"],2]
];

function game3(){
 const root=$("g3");
 root.innerHTML=`
 ${levelHeader(3,"Pressure Quiz","⏱️","Ten quick general-knowledge questions. The answers move around every time.")}
 <div class="card">
  <div class="center">Question <b id="pqNum">1</b>/10</div>
  <div class="progress"><i id="pqProg"></i></div>
  <h3 id="pqQuestion"></h3>
  <div class="answergrid" id="pqAnswers"></div>
  <div class="message" id="pqMsg"></div>
 </div>
 <div class="nextbox"></div>`;

 const qs=shuffle([...pressureQuestions]).slice(0,10);
 let index=0;

 function show(){
  const q=qs[index];
  $("pqNum").textContent=index+1;
  $("pqProg").style.width=(index/10*100)+"%";
  $("pqQuestion").textContent=q[0];
  const answers=shuffledAnswers({options:q[1],answer:q[2]});
  const box=$("pqAnswers");
  box.innerHTML="";
  answers.forEach(a=>{
   const b=document.createElement("button");
   b.className="answer";
   b.textContent=a.text;
   listen(b,"click",()=>{
    box.querySelectorAll("button").forEach(x=>x.disabled=true);
    if(a.correct){
     b.classList.add("correct");
     addPoints(20);
     addTokens(1);
     $("pqMsg").textContent="Correct! 💗";
    }else{
     b.classList.add("wrong");
     $("pqMsg").textContent="Not quite!";
    }
    index++;
    if(index>=10){
     later(()=>finishLevel(3,"Pressure Quiz complete! ⏱️"),500);
    }else later(show,500);
   });
   box.appendChild(b);
  });
 }
 show();
}

/* =========================================================
   4 HIGH ROLLER
========================================================= */

function game4(){
 const root=$("g4");
 root.innerHTML=`
 ${levelHeader(4,"High Roller","🎰","Pull the lever and stop each reel. Matching symbols win points.")}
 <div class="card center">
  <div class="reels">
   <div class="reel" id="r1">🍒</div>
   <div class="reel" id="r2">⭐</div>
   <div class="reel" id="r3">💎</div>
  </div>
  <button class="primary lever" id="spin">🎰 PULL LEVER</button>
  <div class="message" id="slotMsg">You get three spins.</div>
  <b>Spins: <span id="spins">0</span>/3</b>
 </div>
 <div class="nextbox"></div>`;

 const symbols=["🍒","🍋","⭐","💎","💗","7️⃣"];
 let spins=0;

 $("spin").addEventListener("click",()=>{
  if(spins>=3)return;
  spins++;
  $("spins").textContent=spins;
  const vals=[];
  for(let i=1;i<=3;i++){
   const v=symbols[Math.floor(Math.random()*symbols.length)];
   vals.push(v);
   $(`r${i}`).textContent=v;
  }

  if(vals[0]===vals[1]&&vals[1]===vals[2]){
   addPoints(80);
   addTokens(5);
   $("slotMsg").textContent="🎉 JACKPOT! Three matching symbols!";
  }else if(vals[0]===vals[1]||vals[1]===vals[2]||vals[0]===vals[2]){
   addPoints(30);
   addTokens(2);
   $("slotMsg").textContent="✨ Two matched!";
  }else{
   addPoints(5);
   $("slotMsg").textContent="Try another spin!";
  }

  if(spins>=3)later(()=>finishLevel(4,"High Roller complete! 🎰"),700);
 });
}

/* =========================================================
   5 MIND GAMES
========================================================= */

const patterns=[
 {tiles:["❤️","💗","❤️","💗"],choices:["❤️","💗","💔","⭐"],answer:"❤️"},
 {tiles:["⭐","⭐","💎","⭐"],choices:["⭐","💎","💗","🍒"],answer:"💎"},
 {tiles:["🌸","🌻","🌸","🌻"],choices:["🌻","🌸","🌹","🌼"],answer:"🌸"},
 {tiles:["1","2","3","4"],choices:["5","6","4","7"],answer:"5"},
 {tiles:["🔵","🔴","🔵","🔴"],choices:["🔵","🔴","🟢","🟡"],answer:"🔵"},
 {tiles:["🐶","🐱","🐶","🐱"],choices:["🐱","🐶","🐭","🐰"],answer:"🐶"},
 {tiles:["A","B","A","B"],choices:["A","B","C","D"],answer:"A"},
 {tiles:["🌙","☀️","🌙","☀️"],choices:["🌙","☀️","⭐","🌈"],answer:"🌙"}
];

function game5(){
 const root=$("g5");
 root.innerHTML=`
 ${levelHeader(5,"Mind Games","🧩","Complete eight simple visual patterns.")}
 <div class="card center">
  <b>Pattern <span id="mindNum">1</span>/8</b>
  <div class="patternrow" id="pattern"></div>
  <p class="small">What comes next?</p>
  <div class="choicevisuals" id="mindChoices"></div>
  <div class="message" id="mindMsg"></div>
 </div>
 <div class="nextbox"></div>`;

 let i=0;

 function show(){
  const p=patterns[i];
  $("mindNum").textContent=i+1;
  $("pattern").innerHTML=p.tiles.map(x=>`<div class="tile">${x}</div>`).join("")+
   `<div class="tile">?</div>`;
  const box=$("mindChoices");
  box.innerHTML="";
  shuffle([...p.choices]).forEach(c=>{
   const b=document.createElement("button");
   b.className="visualchoice";
   b.textContent=c;
   listen(b,"click",()=>{
    box.querySelectorAll("button").forEach(x=>x.disabled=true);
    if(c===p.answer){
     b.classList.add("correct");
     addPoints(15);
     $("mindMsg").textContent="Perfect pattern! ✨";
    }else{
     b.classList.add("wrong");
     $("mindMsg").textContent="Close!";
    }
    i++;
    if(i>=patterns.length)later(()=>finishLevel(5,"Your brain solved the Mind Games! 🧩"),450);
    else later(show,450);
   });
   box.appendChild(b);
  });
 }
 show();
}

/* =========================================================
   6 THE BLUFF
========================================================= */

function game6(){
 const root=$("g6");
 root.innerHTML=`
 ${levelHeader(6,"The Bluff","🃏","Pick a hidden card. Then decide whether to risk your winnings or bank them.")}
 <div class="card center">
  <div>Round <b id="bluffRound">1</b>/5</div>
  <div class="pot">🪙 <span id="bluffPot">0</span></div>
  <div class="cardsrow" id="bluffCards"></div>
  <div class="message" id="bluffMsg">Choose one card.</div>
  <div id="bluffActions"></div>
 </div>
 <div class="nextbox"></div>`;

 let round=1,pot=0;

 function newRound(){
  $("bluffRound").textContent=round;
  $("bluffMsg").textContent="Choose one hidden card.";
  $("bluffActions").innerHTML="";
  const box=$("bluffCards");
  box.innerHTML="";
  for(let i=0;i<4;i++){
   const b=document.createElement("button");
   b.className="playcard";
   b.textContent="❓";
   listen(b,"click",()=>{
    box.querySelectorAll("button").forEach(x=>x.disabled=true);
    const value=1+Math.floor(Math.random()*20);
    b.textContent=value;
    b.classList.add("revealed");
    pot+=value*5;
    $("bluffPot").textContent=pot;
    $("bluffMsg").textContent=`You found ${value * 5} coins!`;
    const actions=$("bluffActions");
    actions.innerHTML=`
     <button class="gold bigbtn" id="risk">🔥 Risk it</button>
     <button class="green bigbtn" id="bank">🪙 Bank it</button>`;
    $("bank").addEventListener("click",()=>{
     addPoints(Math.round(pot/2));
     addTokens(1);
     round++;
     if(round>5)finishLevel(6,"You played The Bluff! 🃏");
     else newRound();
    });
    $("risk").addEventListener("click",()=>{
     if(Math.random()<.72){
      pot=Math.round(pot*1.5);
      $("bluffPot").textContent=pot;
      $("bluffMsg").textContent="🔥 Risk paid off!";
      round++;
      if(round>5)finishLevel(6,"You survived The Bluff! 🃏");
      else later(newRound,500);
     }else{
      pot=Math.floor(pot/2);
      $("bluffPot").textContent=pot;
      $("bluffMsg").textContent="😅 You lost half. Bank it or risk again.";
     }
    });
   });
   box.appendChild(b);
  }
 }
 newRound();
}

/* =========================================================
   7 SURVIVAL
========================================================= */

function game7(){
 const root=$("g7");
 root.innerHTML=`
 ${levelHeader(7,"Survival Round","🛡️","Eight easy survival decisions. Pick the safest action before the timer runs out.")}
 <div class="card center">
  <b>Wave <span id="survNum">1</span>/8</b>
  <div class="progress"><i id="survProg"></i></div>
  <h3 id="survSituation"></h3>
  <div class="answergrid" id="survChoices"></div>
  <div class="message" id="survMsg"></div>
 </div>
 <div class="nextbox"></div>`;

 const situations=[
  ["A ball flies toward your face!","JUMP","DUCK"],
  ["Something falls from above!","MOVE","FREEZE"],
  ["A bright flash appears!","SHIELD","STARE"],
  ["A puddle blocks the path!","STEP OVER","SIT DOWN"],
  ["A door starts closing!","MOVE","WAIT"],
  ["A loud noise comes from behind!","TURN SAFELY","RUN BLINDLY"],
  ["A low branch is ahead!","DUCK","JUMP"],
  ["The floor looks slippery!","WALK SLOWLY","SPRINT"]
 ];
 let i=0;

 function show(){
  const s=situations[i];
  $("survNum").textContent=i+1;
  $("survProg").style.width=(i/8*100)+"%";
  $("survSituation").textContent=s[0];
  const correct=s[1];
  const options=shuffle([s[1],s[2]]);
  $("survChoices").innerHTML="";
  options.forEach(x=>{
   const b=document.createElement("button");
   b.className="answer";
   b.textContent=x;
   listen(b,"click",()=>{
    $("survChoices").querySelectorAll("button").forEach(q=>q.disabled=true);
    if(x===correct){
     b.classList.add("correct");
     addPoints(18);
     $("survMsg").textContent="🛡️ Safe!";
    }else{
     b.classList.add("wrong");
     $("survMsg").textContent="You survived anyway! 😅";
     addPoints(5);
    }
    i++;
    if(i>=8)later(()=>finishLevel(7,"You survived every wave! 🛡️"),400);
    else later(show,400);
   });
   $("survChoices").appendChild(b);
  });
 }
 show();
}

/* =========================================================
   8 NEW ADMIRER RACE
========================================================= */

function game8(){
 const root=$("g8");
 root.innerHTML=`
 ${levelHeader(8,"The Admirer Race","🏇","No obstacles. No dodging. Just tap GALLop when the marker reaches the green zone!")}
 <div class="card center">
  <div>🏇 You <b id="playerDist">0</b>%</div>
  <div class="progress"><i id="playerBar"></i></div>
  <div class="racetrack">
   <div class="racehorse" id="playerHorse">🏇</div>
   <div class="raceline"></div>
  </div>
  <div>💨 Admirer <b id="aiDist">0</b>%</div>
  <div class="progress"><i id="aiBar"></i></div>
  <div class="timing">
   <div class="timingzone"></div>
   <div class="timingneedle" id="needle"></div>
  </div>
  <button class="primary gallop" id="gallop">🏇 GALLop!</button>
  <div class="message" id="raceMsg">Hit the button while the marker is green.</div>
  <div>Round <b id="raceRound">1</b>/12</div>
 </div>
 <div class="nextbox"></div>`;

 let player=0,ai=0,round=1,running=true,dir=1,needle=0;

 const animate=()=>{
  if(!running)return;
  needle+=dir*2.7;
  if(needle>=100){needle=100;dir=-1}
  if(needle<=0){needle=0;dir=1}
  $("needle").style.left=needle+"%";
  rafs[0]=requestAnimationFrame(animate);
 };
 animate();

 every(()=>{
  if(!running)return;
  ai=Math.min(100,ai+5.3);
  $("aiDist").textContent=Math.round(ai);
  $("aiBar").style.width=ai+"%";
 },600);

 $("gallop").addEventListener("click",()=>{
  if(!running)return;

  let gain;
  if(needle>=42&&needle<=58){
   gain=10;
   $("raceMsg").textContent="🌟 PERFECT GALLop!";
   addPoints(18);
  }else if(needle>=30&&needle<=70){
   gain=7;
   $("raceMsg").textContent="✨ Good timing!";
   addPoints(12);
  }else{
   gain=4;
   $("raceMsg").textContent="💗 Keep going!";
   addPoints(7);
  }

  player=Math.min(100,player+gain);
  round++;
  $("playerDist").textContent=Math.round(player);
  $("playerBar").style.width=player+"%";
  $("raceRound").textContent=Math.min(round,12);

  if(player>=100){
   running=false;
   finishLevel(8,"You won The Admirer Race! 🏆");
  }else if(round>12){
   if(player>=ai){
    running=false;
    finishLevel(8,"You won the race! 🏆");
   }else{
    player=Math.min(100,player+12);
    $("playerDist").textContent=Math.round(player);
    $("playerBar").style.width=player+"%";
    if(player>=ai){
     running=false;
     finishLevel(8,"Photo finish! You won! 🏆");
    }
   }
  }
 });
}

/* =========================================================
   9 HEARTBREAK CHAMBER
========================================================= */

function game9(){
 const root=$("g9");
 root.innerHTML=`
 ${levelHeader(9,"Heartbreak Chamber","🔎","Search the room, collect three clues, then unlock the exit.")}
 <div class="card">
  <div class="room" id="room">
   <button class="roomitem" data-clue="key">🔑<small>Drawer</small></button>
   <button class="roomitem" data-clue="star">⭐<small>Painting</small></button>
   <button class="roomitem" data-clue="number">7️⃣<small>Clock</small></button>
   <button class="roomitem" data-clue="nothing">🪴<small>Plant</small></button>
  </div>
  <div class="clues" id="clues"></div>
  <div class="message" id="chamberMsg">Find three useful clues.</div>
  <button class="primary bigbtn hidden" id="unlockDoor">🔓 Unlock the Door</button>
 </div>
 <div class="nextbox"></div>`;

 const found=new Set();
 const names={key:"🔑 Golden Key",star:"⭐ Star Clue",number:"7️⃣ Number Clue"};

 document.querySelectorAll("#room .roomitem").forEach(b=>{
  b.addEventListener("click",()=>{
   const c=b.dataset.clue;
   if(c==="nothing"){
    $("chamberMsg").textContent="Just a plant. 🌱";
    return;
   }
   if(found.has(c))return;
   found.add(c);
   const tag=document.createElement("span");
   tag.className="clue";
   tag.textContent=names[c];
   $("clues").appendChild(tag);
   b.disabled=true;
   if(found.size===3){
    $("chamberMsg").textContent="You found everything!";
    $("unlockDoor").classList.remove("hidden");
   }
  });
 });

 $("unlockDoor").addEventListener("click",()=>{
  addPoints(40);
  finishLevel(9,"You escaped the Heartbreak Chamber! 🔓");
 });
}

/* =========================================================
   10 BOXING
========================================================= */

function game10(){
 const root=$("g10");
 root.innerHTML=`
 ${levelHeader(10,"Heartbreak Boxing Match","🥊","Beat the opponent using simple attacks and defence.")}
 <div class="card">
  <div class="fighters"><span>🥊</span><span id="enemy">💔</span></div>
  <small>Opponent</small>
  <div class="health"><i id="enemyHP"></i></div>
  <small>You</small>
  <div class="health"><i id="playerHP"></i></div>
  <div class="combatgrid">
   <button class="primary" data-fight="punch">👊 Punch</button>
   <button class="secondary" data-fight="block">🛡️ Block</button>
   <button class="secondary" data-fight="dodge">↪️ Dodge</button>
   <button class="gold" data-fight="special">💥 Special</button>
  </div>
  <div class="message" id="fightMsg">Choose your move!</div>
 </div>
 <div class="nextbox"></div>`;

 let hp=100,enemy=100,blocking=false;

 function update(){
  $("playerHP").style.width=Math.max(0,hp)+"%";
  $("enemyHP").style.width=Math.max(0,enemy)+"%";
 }

 document.querySelectorAll("[data-fight]").forEach(b=>{
  b.addEventListener("click",()=>{
   const move=b.dataset.fight;
   let damage=0;

   blocking=false;
   if(move==="punch")damage=12;
   if(move==="special")damage=25;
   if(move==="block"){blocking=true;hp=Math.min(100,hp+5)}
   if(move==="dodge")damage=6;

   enemy=Math.max(0,enemy-damage);

   if(enemy<=0){
    update();
    addPoints(80);
    addTokens(3);
    finishLevel(10,"You won the boxing match! 🥊");
    return;
   }

   const enemyAttack=8+Math.floor(Math.random()*10);
   if(!blocking && move!=="dodge")hp=Math.max(0,hp-enemyAttack);
   else if(move==="dodge")hp=Math.max(0,hp-3);

   update();

   if(hp<=0){
    $("fightMsg").textContent="You were knocked down. Try again!";
    later(game10,900);
    return;
   }

   $("fightMsg").textContent=
    move==="block"?"🛡️ Nice block!":
    move==="dodge"?"↪️ You slipped away!":
    move==="special"?"💥 Big hit!":"👊 Direct hit!";
  });
 });
 update();
}

/* =========================================================
   11 PERFECT MATCH
========================================================= */

function game11(){
 const root=$("g11");
 root.innerHTML=`
 ${levelHeader(11,"Perfect Match","🧲","Tap an item, then tap its matching target. Five matches wins.")}
 <div class="card">
  <div class="matcharea">
   <div><h3 class="center">Items</h3><div id="matchItems"></div></div>
   <div><h3 class="center">Targets</h3><div id="matchTargets"></div></div>
  </div>
  <div class="message" id="matchMsg">Choose an item.</div>
 </div>
 <div class="nextbox"></div>`;

 const pairs=[
  ["🌻","SUNFLOWER"],
  ["🐬","DOLPHIN"],
  ["🌹","ROSE"],
  ["💗","HEART"],
  ["🍣","SUSHI"]
 ];
 let selected=null,matched=0;

 const items=$("matchItems"),targets=$("matchTargets");

 shuffle([...pairs]).forEach((p,i)=>{
  const b=document.createElement("button");
  b.className="matchitem";
  b.textContent=p[0];
  b.dataset.id=p[1];
  b.style.width="100%";
  b.style.marginBottom="8px";
  b.addEventListener("click",()=>{
   selected=b;
   $("matchMsg").textContent=`Now choose the ${p[1]} target.`;
  });
  items.appendChild(b);
 });

 shuffle([...pairs]).forEach(p=>{
  const b=document.createElement("button");
  b.className="matchtarget";
  b.textContent=p[1];
  b.dataset.id=p[1];
  b.style.width="100%";
  b.style.marginBottom="8px";
  b.addEventListener("click",()=>{
   if(!selected)return;
   if(selected.dataset.id===b.dataset.id){
    selected.disabled=true;
    b.disabled=true;
    b.classList.add("matched");
    matched++;
    addPoints(15);
    selected=null;
    $("matchMsg").textContent="Perfect match! 💗";
    if(matched===5)finishLevel(11,"Five perfect matches! 🧲");
   }else{
    $("matchMsg").textContent="Not that one. Try another target!";
   }
  });
  targets.appendChild(b);
 });
}

/* =========================================================
   12 WHO KNOWS LILIANA BEST
========================================================= */

const lilianaQuiz=[
["What is Liliana's favourite colour?",["Baby pink","Burgundy","Purple","Green"],0],
["What is Liliana's favourite number?",["3","7","5","9"],0],
["Which food does Liliana like?",["Sushi","Curry","Tacos","Porridge"],0],
["Which animal does Liliana like?",["Dolphins","Tigers","Koalas","Foxes"],0],
["What flowers does Liliana like?",["Sunflowers and roses","Tulips and lilies","Daisies and orchids","Lavender and violets"],0],
["When is Liliana's birthday?",["22 July","12 June","7 August","2 May"],0],
["What colour are Liliana's eyes?",["Green","Blue","Brown","Grey"],0],
["What is Liliana's star sign?",["Leo","Gemini","Libra","Aries"],0],
["What is Liliana afraid of?",["Drowning","Flying","Spiders","Heights"],0],
["Which film is a favourite of Liliana's?",["Me Before You","Titanic","Frozen","The Notebook"],0],
["What did Liliana study at university?",["Psychology","Law","Medicine","Art"],0],
["Which dogs belong to Liliana?",["Aayla and Arlo","Luna and Milo","Bella and Coco","Max and Teddy"],0]
];

function makeLilianaQuiz(n,questions,finishText){
 const root=$(`g${n}`);
 root.innerHTML=`
 ${levelHeader(n,n===12?"Who Knows Liliana Best?":"The Final Challenge",n===12?"💗":"💕",
 n===12?"How well do you know Liliana?":"The ultimate 50-question Liliana challenge.")}
 <div class="card">
  <div class="center">${n===23?`<span class="finalnumber">FINAL CHALLENGE</span>`:`Question <b id="lqNum">1</b>/${questions.length}`}</div>
  <div class="progress"><i id="lqProg"></i></div>
  <h3 id="lqQuestion"></h3>
  <div class="answergrid" id="lqAnswers"></div>
  <div class="message" id="lqMsg"></div>
 </div>
 <div class="nextbox"></div>`;

 let i=0;

 function show(){
  const q=questions[i];
  if($("lqNum"))$("lqNum").textContent=i+1;
  $("lqProg").style.width=(i/questions.length*100)+"%";
  $("lqQuestion").textContent=q[0];
  $("lqMsg").textContent="";
  const box=$("lqAnswers");
  box.innerHTML="";
  shuffledAnswers({options:q[1],answer:q[2]}).forEach(a=>{
   const b=document.createElement("button");
   b.className="answer";
   b.textContent=a.text;
   listen(b,"click",()=>{
    box.querySelectorAll("button").forEach(x=>x.disabled=true);
    if(a.correct){
     b.classList.add("correct");
     addPoints(n===23?12:20);
     addTokens(1);
     $("lqMsg").textContent="Correct! 💗";
    }else{
     b.classList.add("wrong");
     $("lqMsg").textContent="Not quite!";
    }
    i++;
    if(i>=questions.length){
     later(()=>finishLevel(n,finishText),350);
    }else later(show,350);
   });
   box.appendChild(b);
  });
 }
 show();
}

function game12(){
 makeLilianaQuiz(12,shuffle([...lilianaQuiz]).slice(0,12),"You know Liliana so well! 💗");
}

/* =========================================================
   13 REACTION GAUNTLET
========================================================= */

function game13(){
 const root=$("g13");
 root.innerHTML=`
 ${levelHeader(13,"Reaction Gauntlet","⚡","Ten tiny reaction challenges. Read the instruction and tap the correct button.")}
 <div class="card center">
  <b>Round <span id="reactNum">1</span>/10</b>
  <div class="reactionbox" id="reactionBox">
   <div id="reactionText">Get ready...</div>
   <button class="primary reactionbutton hidden" id="reactionButton">TAP!</button>
  </div>
  <div class="message" id="reactionMsg"></div>
 </div>
 <div class="nextbox"></div>`;

 let round=0,active=false,trap=false;

 function next(){
  round++;
  if(round>10){
   finishLevel(13,"Reaction Gauntlet complete! ⚡");
   return;
  }
  $("reactNum").textContent=round;
  const box=$("reactionBox"),btn=$("reactionButton");
  trap=Math.random()<.25;
  const type=Math.floor(Math.random()*3);
  active=false;
  btn.classList.remove("hidden");

  if(trap){
   $("reactionText").textContent="🚫 DON'T TAP!";
   btn.textContent="WAIT";
   btn.className="danger reactionbutton";
  }else if(type===0){
   $("reactionText").textContent="💗 TAP NOW!";
   btn.textContent="TAP!";
   btn.className="primary reactionbutton";
  }else if(type===1){
   $("reactionText").textContent="🌸 TAP THE HEART";
   btn.textContent="💗";
   btn.className="primary reactionbutton";
  }else{
   $("reactionText").textContent="⭐ TAP THE STAR";
   btn.textContent="⭐";
   btn.className="gold reactionbutton";
  }
  active=true;

  const wait=900+Math.random()*1000;
  later(()=>{
   if(!active)return;
   if(!trap){
    $("reactionText").textContent="NOW! ⚡";
   }
  },wait);
 }

 $("reactionButton").addEventListener("click",()=>{
  if(!active)return;
  active=false;
  if(trap){
   $("reactionMsg").textContent="😅 Too early! But you can keep going.";
   addPoints(5);
  }else{
   $("reactionMsg").textContent="⚡ Great reaction!";
   addPoints(15);
  }
  later(next,350);
 });

 next();
}

/* =========================================================
   14 HEART HUNT
========================================================= */

function game14(){
 const root=$("g14");
 root.innerHTML=`
 ${levelHeader(14,"Heart Hunt","🕵️","Find and tap 12 hidden hearts. Some things in the scene are decoys!")}
 <div class="card">
  <div class="center">Hearts found: <b id="huntFound">0</b>/12</div>
  <div class="hunt" id="hunt"></div>
  <div class="message" id="huntMsg">Find the hearts! 💗</div>
 </div>
 <div class="nextbox"></div>`;

 const hunt=$("hunt");
 let found=0;

 for(let i=0;i<12;i++){
  const h=document.createElement("button");
  h.className="huntheart";
  h.textContent=["💗","💖","💕","💘"][Math.floor(Math.random()*4)];
  h.style.left=(5+Math.random()*85)+"%";
  h.style.top=(5+Math.random()*85)+"%";
  h.style.background="none";
  listen(h,"click",()=>{
   h.disabled=true;
   h.style.transform="scale(1.5)";
   found++;
   $("huntFound").textContent=found;
   addPoints(8);
   if(found>=12)finishLevel(14,"You found every hidden heart! 💗");
  });
  hunt.appendChild(h);
 }

 for(let i=0;i<10;i++){
  const d=document.createElement("span");
  d.className="decoy";
  d.textContent=["⭐","🌸","✨","🌙"][Math.floor(Math.random()*4)];
  d.style.left=(Math.random()*90)+"%";
  d.style.top=(Math.random()*90)+"%";
  hunt.appendChild(d);
 }
}

/* =========================================================
   15 LOVE LOCK
========================================================= */

function game15(){
 const root=$("g15");
 root.innerHTML=`
 ${levelHeader(15,"Love Lock","🔐","Use the clues to discover the six-digit combination.")}
 <div class="card center">
  <p class="subtitle">
   🎂 Liliana's birthday is <b>22 July</b>.<br>
   💗 You have been best friends for <b>6 years</b>.
  </p>
  <p class="small">Put the birthday first, then the friendship years.</p>
  <div class="lockdisplay" id="lockDisplay">______</div>
  <div class="keypad" id="keypad"></div>
  <button class="danger bigbtn" id="lockClear">Clear</button>
  <div class="message" id="lockMsg"></div>
 </div>
 <div class="nextbox"></div>`;

 const code="060722";
 let entered="";

 for(let i=1;i<=9;i++)makeKey(String(i));
 makeKey("0");

 function makeKey(x){
  const b=document.createElement("button");
  b.className="key";
  b.textContent=x;
  listen(b,"click",()=>{
   if(entered.length>=6)return;
   entered+=x;
   $("lockDisplay").textContent=entered.padEnd(6,"_");
   if(entered.length===6){
    if(entered===code){
     $("lockMsg").textContent="🔓 LOCK OPEN!";
     addPoints(60);
     addTokens(3);
     finishLevel(15,"You cracked the Love Lock! 🔐");
    }else{
     $("lockMsg").textContent="❌ Not quite. Try again.";
     later(()=>{
      entered="";
      $("lockDisplay").textContent="______";
     },500);
    }
   }
  });
  $("keypad").appendChild(b);
 }

 $("lockClear").addEventListener("click",()=>{
  entered="";
  $("lockDisplay").textContent="______";
  $("lockMsg").textContent="";
 });
}

/* =========================================================
   16 CUPID SHOOTOUT
========================================================= */

function game16(){
 const root=$("g16");
 root.innerHTML=`
 ${levelHeader(16,"Cupid Shootout","🏹","Tap 15 moving hearts before Cupid runs out of arrows.")}
 <div class="card">
  <div class="center">🎯 Hits: <b id="shotHits">0</b>/15 &nbsp; 🏹 Arrows: <b id="arrows">20</b></div>
  <div class="shooting" id="shooting"></div>
  <div class="message" id="shotMsg">Tap a heart!</div>
 </div>
 <div class="nextbox"></div>`;

 const area=$("shooting");
 let hits=0,arrows=20;

 function spawn(){
  if(hits>=15)return;
  area.querySelectorAll(".target").forEach(x=>x.remove());
  const t=document.createElement("button");
  t.className="target";
  t.textContent=Math.random()<.2?"💖":"💗";
  t.style.left=(5+Math.random()*80)+"%";
  t.style.top=(5+Math.random()*80)+"%";
  listen(t,"click",()=>{
   hits++;
   arrows++;
   $("shotHits").textContent=hits;
   $("arrows").textContent=arrows;
   addPoints(t.textContent==="💖"?15:10);
   t.remove();
   if(hits>=15)finishLevel(16,"Cupid hit every target! 🏹");
   else later(spawn,200);
  });
  area.appendChild(t);
  arrows--;
  $("arrows").textContent=arrows;
  if(arrows<=0){
   arrows=20;
   $("arrows").textContent=20;
  }
 }

 every(spawn,850);
 spawn();
}

/* =========================================================
   17 COUNTDOWN MINI GAMES
========================================================= */

function game17(){
 const root=$("g17");
 root.innerHTML=`
 ${levelHeader(17,"The Countdown","⏳","Six tiny challenges. The game changes every round, so it never feels like another quiz.")}
 <div class="card center">
  <b>Challenge <span id="cdNum">1</span>/6</b>
  <div id="cdArea"></div>
  <div class="message" id="cdMsg"></div>
 </div>
 <div class="nextbox"></div>`;

 let round=0;

 function next(){
  round++;
  if(round>6){
   finishLevel(17,"You conquered The Countdown! ⏳");
   return;
  }
  $("cdNum").textContent=round;
  const area=$("cdArea");
  area.innerHTML="";
  const type=round%4;

  if(type===1){
   area.innerHTML=`
    <p>Stop the marker inside the green zone.</p>
    <div class="countbar"><div class="countzone"></div><div class="countneedle" id="cdNeedle"></div></div>
    <button class="primary bigbtn" id="cdStop">STOP!</button>`;
   let x=0,d=1;
   const id=every(()=>{
    x+=d*4;
    if(x>=100){x=100;d=-1}
    if(x<=0){x=0;d=1}
    $("cdNeedle").style.left=x+"%";
   },30);
   cleanupFns.push(()=>clearInterval(id));
   $("cdStop").addEventListener("click",()=>{
    clearInterval(id);
    addPoints(x>=42&&x<=58?25:10);
    $("cdMsg").textContent=x>=35&&x<=65?"Perfect!":"Nice try!";
    later(next,400);
   });
  }else if(type===2){
   const seq=shuffle(["💗","🌸","⭐","🌻"]).slice(0,3);
   area.innerHTML=`
    <p>Tap these in order:</p>
    <h2>${seq.join(" → ")}</h2>
    <div class="answergrid" id="cdButtons"></div>`;
   let pos=0;
   ["💗","🌸","⭐","🌻"].forEach(x=>{
    const b=document.createElement("button");
    b.className="answer";
    b.textContent=x;
    b.addEventListener("click",()=>{
     if(x===seq[pos]){
      pos++;
      b.disabled=true;
      if(pos===seq.length){
       addPoints(25);
       $("cdMsg").textContent="Sequence complete! ✨";
       later(next,400);
      }
     }else{
      $("cdMsg").textContent="Close! Try this challenge again.";
      pos=0;
      document.querySelectorAll("#cdButtons button").forEach(q=>q.disabled=false);
     }
    });
    $("cdButtons").appendChild(b);
   });
  }else if(type===3){
   const nums=shuffle([1,2,3,4]);
   area.innerHTML=`
    <p>Tap the numbers from 1 to 4.</p>
    <div class="answergrid" id="numButtons"></div>`;
   let want=1;
   nums.forEach(n=>{
    const b=document.createElement("button");
    b.className="answer";
    b.textContent=n;
    b.addEventListener("click",()=>{
     if(n===want){
      b.disabled=true;
      want++;
      if(want===5){
       addPoints(25);
       $("cdMsg").textContent="Perfect order! 🔢";
       later(next,400);
      }
     }else{
      $("cdMsg").textContent="Oops! Start again.";
      want=1;
      document.querySelectorAll("#numButtons button").forEach(q=>q.disabled=false);
     }
    });
    $("numButtons").appendChild(b);
   });
  }else{
   area.innerHTML=`
    <p>Tap the giant heart as many times as you can!</p>
    <button class="primary" id="bigHeart" style="font-size:60px;width:100%">💗</button>
    <p>Hits: <b id="heartTaps">0</b>/8</p>`;
   let taps=0;
   $("bigHeart").addEventListener("click",()=>{
    taps++;
    $("heartTaps").textContent=taps;
    if(taps>=8){
     addPoints(25);
     $("cdMsg").textContent="💗 Done!";
     later(next,400);
    }
   });
  }
 }
 next();
}

/* =========================================================
   18 ULTIMATE GAMBLE
========================================================= */

function game18(){
 const root=$("g18");
 root.innerHTML=`
 ${levelHeader(18,"Ultimate Gamble","🎲","Start with 100 coins. Keep risking for a bigger prize, or cash out.")}
 <div class="card center">
  <div class="pot">🪙 <span id="gamblePot">100</span></div>
  <p>Turn <b id="gambleTurn">0</b>/6</p>
  <div class="gamblegrid">
   <button class="gold" id="gambleRisk">🎲 Risk</button>
   <button class="green" id="gambleCash">🪙 Cash Out</button>
  </div>
  <div class="message" id="gambleMsg">Will you risk it?</div>
 </div>
 <div class="nextbox"></div>`;

 let pot=100,turn=0,done=false;

 $("gambleRisk").addEventListener("click",()=>{
  if(done)return;
  turn++;
  if(Math.random()<.68){
   pot+=Math.floor(30+Math.random()*90);
   $("gambleMsg").textContent="🎉 You won more coins!";
  }else{
   pot=Math.max(0,Math.floor(pot/2));
   $("gambleMsg").textContent="😅 You lost half.";
  }
  $("gamblePot").textContent=pot;
  $("gambleTurn").textContent=turn;

  if(turn>=6){
   done=true;
   addPoints(Math.max(20,Math.floor(pot/2)));
   finishLevel(18,"You finished the Ultimate Gamble! 🎲");
  }
 });

 $("gambleCash").addEventListener("click",()=>{
  if(done)return;
  done=true;
  addPoints(Math.max(20,Math.floor(pot/2)));
  addTokens(2);
  finishLevel(18,"You cashed out! 🪙");
 });
}

/* =========================================================
   19 ADMIRER'S LAST STAND
========================================================= */

function game19(){
 const root=$("g19");
 root.innerHTML=`
 ${levelHeader(19,"Admirer's Last Stand","👑","A friendly boss battle with three simple phases.")}
 <div class="card">
  <div class="boss" id="boss">👑</div>
  <div class="center">Boss HP</div>
  <div class="health"><i id="bossHP"></i></div>
  <div class="center">Your Energy: <b id="bossEnergy">3</b></div>
  <div class="bossactions">
   <button class="primary" id="bossAttack">👊 Attack</button>
   <button class="secondary" id="bossGuard">🛡️ Guard</button>
   <button class="gold" id="bossSpecial">💥 Special</button>
   <button class="secondary" id="bossHeal">💗 Heal</button>
  </div>
  <div class="message" id="bossMsg">Phase 1: attack carefully!</div>
 </div>
 <div class="nextbox"></div>`;

 let hp=100,energy=3,guard=false;

 function update(){
  $("bossHP").style.width=hp+"%";
  $("bossEnergy").textContent=energy;
  $("boss").textContent=hp>65?"👑":hp>30?"😈":"🔥";
 }

 function enemyTurn(){
  if(guard){
   guard=false;
   $("bossMsg").textContent="🛡️ Blocked!";
   return;
  }
  if(Math.random()<.65)energy=Math.max(0,energy-1);
 }

 $("bossAttack").addEventListener("click",()=>{
  hp=Math.max(0,hp-11);
  enemyTurn();
  addPoints(8);
  if(hp<=0)win();
  else{
   $("bossMsg").textContent=hp>65?"Phase 1":"The boss is getting angry!";
   update();
  }
 });

 $("bossGuard").addEventListener("click",()=>{
  guard=true;
  enemyTurn();
  update();
  $("bossMsg").textContent="🛡️ Guard ready!";
 });

 $("bossSpecial").addEventListener("click",()=>{
  if(energy<2){
   $("bossMsg").textContent="Need 2 energy!";
   return;
  }
  energy-=2;
  hp=Math.max(0,hp-25);
  addPoints(20);
  enemyTurn();
  if(hp<=0)win();
  else{
   $("bossMsg").textContent="💥 Special attack!";
   update();
  }
 });

 $("bossHeal").addEventListener("click",()=>{
  energy=Math.min(5,energy+1);
  $("bossMsg").textContent="💗 Energy restored.";
  update();
 });

 function win(){
  update();
  addPoints(80);
  addTokens(3);
  finishLevel(19,"The Admirer's Last Stand is defeated! 👑");
 }
 update();
}

/* =========================================================
   20 WORD FIND
========================================================= */

const wordBank=[
"LILIANA","LULU","FRIENDS","PINK","DOLPHIN","SUNFLOWER",
"ROSE","SUSHI","POETRY","MUSIC","PSYCHOLOGY","LEO",
"JULY","LOVE","FAMILY","HEART","DREAM","AAYLA","ARLO",
"OCEAN","FOREVER","THREE","SIXYEARS","CHARM","EMPATHY"
];

function game20(){
 const root=$("g20");
 root.innerHTML=`
 ${levelHeader(20,"Liliana's Word Find","🔎","Find all 25 hidden words. Words may go forwards, backwards, up, down or diagonally.")}
 <div class="card">
  <div class="center">Found <b id="wordsFound">0</b>/25</div>
  <div class="wordwrap"><div class="wordgrid" id="wordGrid"></div></div>
  <div class="wordlist" id="wordList"></div>
  <div class="message" id="wordMsg">Drag across a word.</div>
 </div>
 <div class="nextbox"></div>`;

 const SIZE=12;
 const grid=Array.from({length:SIZE},()=>Array(SIZE).fill(""));
 const placed=[];
 const dirs=[
  [0,1],[0,-1],[1,0],[-1,0],
  [1,1],[1,-1],[-1,1],[-1,-1]
 ];

 function tryPlace(word){
  for(let tries=0;tries<300;tries++){
   const [dr,dc]=dirs[Math.floor(Math.random()*dirs.length)];
   const r=Math.floor(Math.random()*SIZE);
   const c=Math.floor(Math.random()*SIZE);
   const er=r+dr*(word.length-1);
   const ec=c+dc*(word.length-1);
   if(er<0||er>=SIZE||ec<0||ec>=SIZE)continue;
   let ok=true;
   for(let i=0;i<word.length;i++){
    const x=grid[r+dr*i][c+dc*i];
    if(x!==""&&x!==word[i]){ok=false;break}
   }
   if(!ok)continue;
   for(let i=0;i<word.length;i++)grid[r+dr*i][c+dc*i]=word[i];
   placed.push({word,r,c,dr,dc});
   return true;
  }
  return false;
 }

 shuffle([...wordBank]).forEach(w=>tryPlace(w));

 const letters="ABCDEFGHIJKLMNOPQRSTUVWXYZ";
 for(let r=0;r<SIZE;r++){
  for(let c=0;c<SIZE;c++){
   if(!grid[r][c])grid[r][c]=letters[Math.floor(Math.random()*26)];
  }
 }

 const gridEl=$("wordGrid");
 const cells=[];
 for(let r=0;r<SIZE;r++){
  for(let c=0;c<SIZE;c++){
   const b=document.createElement("button");
   b.className="letter";
   b.textContent=grid[r][c];
   b.dataset.r=r;
   b.dataset.c=c;
   gridEl.appendChild(b);
   cells.push(b);
  }
 }

 $("wordList").innerHTML=wordBank.map(w=>`<span class="wordtag" data-word="${w}">${w}</span>`).join("");

 let start=null;
 let found=new Set();

 function cellAt(e){
  const el=document.elementFromPoint(e.clientX,e.clientY);
  return el&&el.classList.contains("letter")?el:null;
 }

 function selectLine(a,b){
  if(!a||!b)return;
  const r1=Number(a.dataset.r),c1=Number(a.dataset.c);
  const r2=Number(b.dataset.r),c2=Number(b.dataset.c);
  const dr=Math.sign(r2-r1),dc=Math.sign(c2-c1);
  if(r1!==r2&&c1!==c2&&Math.abs(r2-r1)!==Math.abs(c2-c1))return;

  const len=Math.max(Math.abs(r2-r1),Math.abs(c2-c1))+1;
  let word="";
  const selected=[];
  for(let i=0;i<len;i++){
   const r=r1+dr*i,c=c1+dc*i;
   const cell=cells[r*SIZE+c];
   selected.push(cell);
   word+=grid[r][c];
  }

  const reverse=word.split("").reverse().join("");
  const match=wordBank.find(w=>w===word||w===reverse);

  cells.forEach(x=>x.classList.remove("selected"));
  selected.forEach(x=>x.classList.add("selected"));

  if(match&&!found.has(match)){
   found.add(match);
   selected.forEach(x=>x.classList.add("found"));
   const tag=document.querySelector(`[data-word="${match}"]`);
   if(tag)tag.classList.add("found");
   $("wordsFound").textContent=found.size;
   addPoints(12);
   $("wordMsg").textContent=`Found ${match}!`;
   if(found.size===wordBank.length)finishLevel(20,"You found every word! 🔎");
  }
 }

 gridEl.addEventListener("pointerdown",e=>{
  const c=cellAt(e);
  if(c){
   start=c;
   gridEl.setPointerCapture?.(e.pointerId);
  }
 });

 gridEl.addEventListener("pointerup",e=>{
  const end=cellAt(e);
  if(start&&end)selectLine(start,end);
  start=null;
 });
}

/* =========================================================
   21 DRAW A SUNFLOWER
========================================================= */

function game21(){
 const root=$("g21");
 root.innerHTML=`
 ${levelHeader(21,"Draw a Sunflower","🌻","Draw your own sunflower. There is no wrong way to make it!")}
 <div class="card">
  <canvas id="drawCanvas" width="600" height="430"></canvas>
  <div class="tools">
   <button data-size="4">Small</button>
   <button data-size="9">Medium</button>
   <button data-size="16">Large</button>
   <input class="colorinput" type="color" id="brushColor" value="#8e3159" aria-label="Brush colour">
   <button id="undoDraw">↩ Undo</button>
   <button id="clearDraw">🗑 Clear</button>
  </div>
  <div class="message" id="drawMsg">Draw petals, leaves, a stem, or anything you like! 🌻</div>
  <button class="primary bigbtn" id="finishDrawing">🌻 I'm Finished!</button>
 </div>
 <div class="nextbox"></div>`;

 const canvas=$("drawCanvas"),ctx=canvas.getContext("2d");
 let drawing=false,lastX=0,lastY=0,size=9,color="#8e3159";
 const history=[];

 function pos(e){
  const r=canvas.getBoundingClientRect();
  return {
   x:(e.clientX-r.left)*canvas.width/r.width,
   y:(e.clientY-r.top)*canvas.height/r.height
  };
 }

 function saveHistory(){
  if(history.length>8)history.shift();
  history.push(ctx.getImageData(0,0,canvas.width,canvas.height));
 }

 listen(canvas,"pointerdown",e=>{
  saveHistory();
  drawing=true;
  const p=pos(e);
  lastX=p.x;lastY=p.y;
  canvas.setPointerCapture?.(e.pointerId);
 });

 listen(canvas,"pointermove",e=>{
  if(!drawing)return;
  const p=pos(e);
  ctx.strokeStyle=color;
  ctx.lineWidth=size;
  ctx.lineCap="round";
  ctx.beginPath();
  ctx.moveTo(lastX,lastY);
  ctx.lineTo(p.x,p.y);
  ctx.stroke();
  lastX=p.x;lastY=p.y;
 });

 listen(canvas,"pointerup",()=>drawing=false);
 listen(canvas,"pointercancel",()=>drawing=false);

 document.querySelectorAll("[data-size]").forEach(b=>{
  listen(b,"click",()=>size=Number(b.dataset.size));
 });

 listen($("brushColor"),"input",e=>color=e.target.value);

 listen($("undoDraw"),"click",()=>{
  const last=history.pop();
  if(last)ctx.putImageData(last,0,0);
 });

 listen($("clearDraw"),"click",()=>{
  saveHistory();
  ctx.clearRect(0,0,canvas.width,canvas.height);
 });

 listen($("finishDrawing"),"click",()=>{
  addPoints(50);
  addTokens(3);
  finishLevel(21,"Your sunflower is beautiful! 🌻");
 });
}

/* =========================================================
   22 LULU DERBY — 100 RANDOM TRIVIA
========================================================= */

const derbyQuestions=[
["Which planet is closest to the Sun?",["Mercury","Venus","Earth","Mars"],0],
["How many continents are there?",["5","6","7","8"],2],
["What is the capital of France?",["Paris","Rome","Madrid","Berlin"],0],
["Which animal is known as the king of the jungle?",["Lion","Tiger","Bear","Wolf"],0],
["What is 12 × 5?",["50","60","70","80"],1],
["Which ocean is between Africa and Australia?",["Atlantic","Indian","Pacific","Arctic"],1],
["What is the chemical symbol for gold?",["Ag","Au","Fe","Gd"],1],
["Which language has the most native speakers?",["English","Spanish","Mandarin Chinese","French"],2],
["How many legs does a spider have?",["6","8","10","12"],1],
["Which country is shaped like a boot?",["Italy","Spain","Greece","Portugal"],0],
["What is the largest planet?",["Earth","Jupiter","Saturn","Neptune"],1],
["Which organ pumps blood around the body?",["Lung","Heart","Liver","Kidney"],1],
["What is the square root of 64?",["6","7","8","9"],2],
["Which month has 28 days in a normal year?",["January","February","March","April"],1],
["Which animal is the largest land animal?",["Rhino","Elephant","Hippo","Giraffe"],1],
["What is the capital of Canada?",["Toronto","Vancouver","Ottawa","Montreal"],2],
["Which gas makes up most of Earth's atmosphere?",["Oxygen","Nitrogen","Helium","Hydrogen"],1],
["How many players are on a soccer team on the field?",["9","10","11","12"],2],
["Which planet is famous for a giant red storm?",["Mars","Jupiter","Saturn","Uranus"],1],
["What is the hardest natural substance?",["Gold","Diamond","Iron","Quartz"],1],
["Which country gave the Statue of Liberty to the United States?",["France","Canada","Italy","Spain"],0],
["What is 100 divided by 4?",["20","25","30","40"],1],
["Which mammal can fly?",["Bat","Squirrel","Monkey","Rabbit"],0],
["What is the capital of Italy?",["Venice","Milan","Rome","Naples"],2],
["Which sea creature has eight arms?",["Shark","Octopus","Dolphin","Seal"],1],
["How many colours are traditionally in a rainbow?",["5","6","7","8"],2],
["Which metal is liquid at room temperature?",["Iron","Mercury","Copper","Aluminium"],1],
["What is the largest desert in the world by area?",["Sahara","Antarctic Desert","Gobi","Arabian"],1],
["Which country is home to the Great Barrier Reef?",["Australia","Brazil","India","Mexico"],0],
["How many degrees are in a full circle?",["90","180","270","360"],3],
["Which instrument measures temperature?",["Barometer","Thermometer","Compass","Altimeter"],1],
["What is the capital of New Zealand?",["Auckland","Wellington","Christchurch","Hamilton"],1],
["Which bird cannot fly?",["Eagle","Penguin","Falcon","Hawk"],1],
["What is the opposite of north?",["East","West","South","Up"],2],
["Which planet is called Earth's twin because of similar size?",["Venus","Mars","Mercury","Neptune"],0],
["How many bones are in the adult human body approximately?",["106","206","306","406"],1],
["Which sport uses a racket and shuttlecock?",["Tennis","Badminton","Golf","Cricket"],1],
["What is the capital of Spain?",["Barcelona","Madrid","Seville","Valencia"],1],
["Which animal is famous for changing colour?",["Chameleon","Horse","Elephant","Penguin"],0],
["What is 15 + 27?",["40","41","42","43"],2],
["Which planet has the most prominent rings?",["Mars","Saturn","Earth","Venus"],1],
["Which country is home to Machu Picchu?",["Peru","Chile","Brazil","Bolivia"],0],
["What do plants absorb from the air for photosynthesis?",["Oxygen","Nitrogen","Carbon dioxide","Helium"],2],
["How many sides does an octagon have?",["6","7","8","9"],2],
["Which animal is known for its black and white stripes?",["Zebra","Leopard","Panda","Skunk"],0],
["What is the capital of Germany?",["Berlin","Munich","Hamburg","Frankfurt"],0],
["Which famous scientist developed the theory of relativity?",["Newton","Einstein","Darwin","Galileo"],1],
["How many hours are in two days?",["24","36","48","72"],2],
["Which fruit is traditionally associated with keeping doctors away?",["Apple","Banana","Orange","Pear"],0],
["What is the boiling point of water at sea level in Celsius?",["50","75","100","125"],2],
["Which country has the city of Cairo?",["Egypt","Jordan","Morocco","Turkey"],0],
["Which animal is known for building dams?",["Beaver","Otter","Badger","Fox"],0],
["What is the largest internal organ in the human body?",["Heart","Liver","Lung","Kidney"],1],
["Which planet rotates on its side?",["Uranus","Mars","Venus","Mercury"],0],
["What is 7 × 8?",["48","54","56","64"],2],
["Which continent contains the Sahara Desert?",["Asia","Africa","Europe","Australia"],1],
["Which famous ship sank in 1912?",["Titanic","Endeavour","Mayflower","Beagle"],0],
["What is the capital of Greece?",["Athens","Sparta","Thessaloniki","Corinth"],0],
["Which animal is the fastest bird in a dive?",["Eagle","Peregrine falcon","Owl","Swan"],1],
["How many planets are in our Solar System?",["7","8","9","10"],1],
["Which country is famous for the ancient city of Petra?",["Jordan","Egypt","Greece","Lebanon"],0],
["What is the primary ingredient in bread?",["Rice","Flour","Corn","Potato"],1],
["Which sport is played at Wimbledon?",["Tennis","Football","Rugby","Golf"],0],
["What is the capital of Ireland?",["Dublin","Cork","Galway","Limerick"],0],
["Which animal has a trunk?",["Elephant","Rhino","Giraffe","Walrus"],0],
["What is 144 ÷ 12?",["10","11","12","14"],2],
["Which planet is farthest from the Sun?",["Saturn","Uranus","Neptune","Jupiter"],2],
["What do caterpillars become?",["Bees","Butterflies or moths","Birds","Beetles"],1],
["Which country is home to the city of Kyoto?",["China","Japan","South Korea","Thailand"],1],
["Which blood cells help fight infection?",["Red cells","White cells","Platelets","Plasma"],1],
["What is the capital of Portugal?",["Lisbon","Porto","Faro","Braga"],0],
["Which animal is known for carrying its baby in a pouch?",["Kangaroo","Tiger","Panda","Wolf"],0],
["What is the largest planet's main composition?",["Gas","Rock","Ice","Metal"],0],
["Which ancient civilisation built the Colosseum?",["Romans","Vikings","Aztecs","Maya"],0],
["What is 11 squared?",["111","121","131","141"],1],
["Which country is famous for the Taj Mahal?",["India","Pakistan","Nepal","Bangladesh"],0],
["What is the name of our galaxy?",["Andromeda","Milky Way","Whirlpool","Sombrero"],1],
["Which animal is famous for its long neck?",["Giraffe","Camel","Llama","Horse"],0],
["Which planet is closest in size to Earth?",["Venus","Mars","Mercury","Jupiter"],0],
["What is the capital of Norway?",["Oslo","Bergen","Stockholm","Helsinki"],0],
["Which sport uses wickets?",["Cricket","Tennis","Basketball","Hockey"],0],
["What is the main language spoken in Brazil?",["Spanish","Portuguese","French","English"],1],
["Which shape has four equal sides?",["Triangle","Rectangle","Square","Pentagon"],2],
["Which animal produces wool?",["Sheep","Cow","Horse","Goat"],0],
["What is 5 cubed?",["25","75","100","125"],3],
["Which country is famous for the Eiffel Tower?",["France","Belgium","Switzerland","Austria"],0],
["What is the name of the Earth's natural satellite?",["Mars","Moon","Sun","Europa"],1],
["Which bird is often associated with wisdom?",["Owl","Pigeon","Duck","Chicken"],0],
["What is the capital of South Korea?",["Seoul","Busan","Incheon","Daegu"],0],
["Which ocean is the smallest?",["Arctic","Indian","Atlantic","Southern"],0],
["Which animal is known for its ability to echolocate?",["Bat","Horse","Rabbit","Sheep"],0],
["What is 9 + 17?",["24","25","26","27"],2],
["Which country has Mount Fuji?",["Japan","China","Nepal","Indonesia"],0],
["What is the process by which plants make food using sunlight?",["Respiration","Photosynthesis","Digestion","Fermentation"],1],
["Which planet is known for its blue colour and strong winds?",["Neptune","Mars","Mercury","Venus"],0],
["What is the capital of Iceland?",["Reykjavik","Oslo","Dublin","Helsinki"],0],
["Which animal is often called man's best friend?",["Dog","Cat","Horse","Rabbit"],0],
["How many months are in a year?",["10","11","12","13"],2],
["Which famous wall divided Berlin during the Cold War?",["Berlin Wall","Iron Wall","Eastern Wall","German Wall"],0],
["What is the largest continent?",["Africa","Asia","Europe","North America"],1],
["Which country is home to the Acropolis?",["Greece","Italy","Turkey","Egypt"],0],
["What is 50% of 80?",["20","30","40","50"],2],
["Which animal is famous for its quills?",["Porcupine","Rabbit","Deer","Otter"],0],
["What is the capital of China?",["Beijing","Shanghai","Hong Kong","Shenzhen"],0],
["Which planet is sometimes visible as the morning or evening star?",["Venus","Mars","Jupiter","Saturn"],0]
];

function game22(){
 const root=$("g22");
 root.innerHTML=`
 ${levelHeader(22,"THE LULU DERBY","🏇","Choose your horse, then answer 100 random trivia questions to help it race!")}
 <div class="card" id="derbySelectCard">
  <h3 class="center">Choose your horse</h3>
  <div class="horselist" id="horseChoices">
   <button class="horsechoice" data-horse="0">🌸 Pink Lulu</button>
   <button class="horsechoice" data-horse="1">💙 Blue Star</button>
   <button class="horsechoice" data-horse="2">💜 Purple Dream</button>
   <button class="horsechoice" data-horse="3">💛 Golden Heart</button>
  </div>
  <button class="primary bigbtn hidden" id="startDerby">🏁 Start Derby</button>
 </div>
 <div class="card hidden" id="derbyGame">
  <div class="center">Question <b id="derbyNum">1</b>/100</div>
  <div class="progress"><i id="derbyProg"></i></div>
  <div class="derbytrack">
   <div>🌸 <span id="dh0">Pink Lulu</span><div class="horsebar"><i id="db0"></i></div></div>
   <div>💙 Blue Star<div class="horsebar"><i id="db1"></i></div></div>
   <div>💜 Purple Dream<div class="horsebar"><i id="db2"></i></div></div>
   <div>💛 Golden Heart<div class="horsebar"><i id="db3"></i></div></div>
  </div>
  <h3 id="derbyQuestion"></h3>
  <div class="answergrid" id="derbyAnswers"></div>
  <div class="message" id="derbyMsg"></div>
 </div>
 <div class="nextbox"></div>`;

 let selected=-1;
 let questions=[];
 let qi=0;
 let distance=[0,0,0,0];
 let running=false;

 document.querySelectorAll(".horsechoice").forEach(b=>{
  b.addEventListener("click",()=>{
   selected=Number(b.dataset.horse);
   document.querySelectorAll(".horsechoice").forEach(x=>x.classList.remove("selected"));
   b.classList.add("selected");
   $("startDerby").classList.remove("hidden");
  });
 });

 $("startDerby").addEventListener("click",()=>{
  if(selected<0)return;
  questions=shuffle([...derbyQuestions]).slice(0,100);
  qi=0;
  running=true;
  $("derbySelectCard").classList.add("hidden");
  $("derbyGame").classList.remove("hidden");
  showQuestion();
 });

 function showQuestion(){
  const q=questions[qi];
  $("derbyNum").textContent=qi+1;
  $("derbyProg").style.width=(qi/100*100)+"%";
  $("derbyQuestion").textContent=q[0];
  $("derbyMsg").textContent="";
  const box=$("derbyAnswers");
  box.innerHTML="";

  shuffledAnswers({options:q[1],answer:q[2]}).forEach(a=>{
   const b=document.createElement("button");
   b.className="answer";
   b.textContent=a.text;
   b.addEventListener("click",()=>{
    box.querySelectorAll("button").forEach(x=>x.disabled=true);

    if(a.correct){
     distance[selected]=Math.min(100,distance[selected]+1.7);
     addPoints(5);
     addTokens(1);
     $("derbyMsg").textContent="🏇 Correct! Your horse surges ahead!";
    }else{
     distance[selected]=Math.max(0,distance[selected]-.3);
     const rival=Math.floor(Math.random()*4);
     if(rival!==selected)distance[rival]=Math.min(100,distance[rival]+.7);
     $("derbyMsg").textContent="The field moves on!";
    }

    for(let i=0;i<4;i++)$(`db${i}`).style.width=distance[i]+"%";

    qi++;
    if(qi>=100){
     running=false;
     const winner=distance.indexOf(Math.max(...distance));
     const won=winner===selected;
     if(won){
      addPoints(120);
      addTokens(10);
      $("derbyMsg").textContent="🏆 YOUR HORSE WON THE LULU DERBY!";
     }else{
      addPoints(40);
      $("derbyMsg").textContent="🏇 What a race! Your horse gave it everything.";
     }
     later(()=>finishLevel(22,won?"You won THE LULU DERBY! 🏆":"THE LULU DERBY is complete! 🏇"),500);
    }else{
     later(showQuestion,120);
    }
   });
   box.appendChild(b);
  });
 }
}

/* =========================================================
   23 FINAL CHALLENGE — 50 UNIQUE LILIANA QUESTIONS
========================================================= */

const finalQuestions=[
["What is Liliana's favourite colour?",["Baby pink","Burgundy","Navy","Yellow"],0],
["Which number has special meaning as Liliana's favourite?",["3","4","6","9"],0],
["Which food is Liliana known to like?",["Sushi","Steak","Pasta","Cereal"],0],
["Which sea animal does Liliana like?",["Dolphin","Shark","Seal","Whale"],0],
["Which yellow flower does Liliana like?",["Sunflower","Daffodil","Tulip","Marigold"],0],
["Which other flower does Liliana like?",["Rose","Orchid","Violet","Lily"],0],
["What day of the month is Liliana's birthday?",["22","12","2","27"],0],
["Which month is Liliana's birthday in?",["July","June","August","May"],0],
["What colour are Liliana's eyes?",["Green","Hazel","Blue","Brown"],0],
["What is Liliana's star sign?",["Leo","Cancer","Virgo","Libra"],0],
["What fear has Liliana shared?",["Drowning","Thunder","Flying","Darkness"],0],
["Which film is one of Liliana's favourites?",["Me Before You","Clueless","Frozen","Mamma Mia"],0],
["What type of songs does Liliana like?",["Sad songs","Only dance songs","Only rock","Only country"],0],
["What type of writing does Liliana enjoy?",["Poetry","News articles","Manuals","Textbooks"],0],
["Which card game does Liliana enjoy?",["Poker","Solitaire only","Bridge only","Go Fish"],0],
["Liliana enjoys poker and what broader type of activity?",["Gambling games","Cooking competitions","Chess tournaments","Marathons"],0],
["What career-related subject did Liliana study at university?",["Psychology","Engineering","History","Physics"],0],
["How many nieces does Liliana have?",["1","2","3","4"],0],
["How many nephews does Liliana have?",["4","1","2","5"],0],
["How many siblings does Liliana have?",["5","3","4","6"],0],
["How many piercings does Liliana have?",["4","2","5","6"],0],
["What is the name of one of Liliana's dogs?",["Aayla","Bella","Luna","Daisy"],0],
["What is the name of Liliana's other dog?",["Arlo","Milo","Teddy","Coco"],0],
["Which pair are Liliana's dogs?",["Aayla and Arlo","Luna and Milo","Bella and Coco","Daisy and Max"],0],
["How long have Bree and Liliana been best friends?",["6 years","2 years","4 years","8 years"],0],
["Which word best describes Liliana?",["Caring","Careless","Distant","Impatient"],0],
["Which quality is associated with Liliana?",["Empathy","Indifference","Rudeness","Impatience"],0],
["Which personality description fits Liliana?",["Charismatic","Shy and unfriendly","Cold and distant","Uninterested"],0],
["Which description fits Liliana's nature?",["Sweet","Mean","Unkind","Aloof"],0],
["Liliana is known for being what with people she likes?",["Flirtatious","Silent","Hostile","Reserved"],0],
["What does Liliana like about children?",["She likes children","She dislikes children","She avoids children","She is frightened of children"],0],
["What future family dream has Liliana shared?",["Being a mum","Owning a yacht","Becoming a pilot","Living alone forever"],0],
["What kind of child does Liliana dream of having?",["A baby girl","Twin boys","A teenage son","No children"],0],
["Which ocean-related dream belongs to Liliana?",["Seeing the ocean someday","Never seeing water","Learning to surf professionally","Living on a boat"],0],
["Which combination contains two of Liliana's favourite things?",["Baby pink and sushi","Green and steak","Black and curry","Orange and pizza"],0],
["Which combination correctly pairs Liliana with an animal she likes?",["Dolphin","Crocodile","Snake","Scorpion"],0],
["Which combination contains two flowers Liliana likes?",["Sunflowers and roses","Roses and orchids","Tulips and lilies","Daisies and violets"],0],
["Which statement about Liliana's birthday is correct?",["It is 22 July","It is 22 June","It is 12 July","It is 27 July"],0],
["Which statement about Liliana's eyes is correct?",["They are green","They are blue","They are brown","They are grey"],0],
["Which statement about Liliana's studies is correct?",["She studied Psychology","She studied Architecture","She studied Chemistry","She studied Music"],0],
["Which statement about Liliana's pets is correct?",["She has dogs named Aayla and Arlo","She has cats named Aayla and Arlo","She has horses named Aayla and Arlo","She has birds named Aayla and Arlo"],0],
["Which statement combines Liliana's favourite number and birthday?",["3 and 22 July","6 and 12 June","4 and 7 August","5 and 2 May"],0],
["Which statement combines Liliana's flowers correctly?",["Sunflowers and roses","Daffodils and orchids","Tulips and lilies","Violets and daisies"],0],
["Which statement combines Liliana's interests correctly?",["Poetry and sad songs","Only science and maths","Only sports and cooking","Only documentaries"],0],
["Which statement combines Liliana's games correctly?",["Poker and gambling games","Only board puzzles","Only video games","Only crossword puzzles"],0],
["Which statement correctly combines Liliana's family numbers?",["1 niece and 4 nephews","4 nieces and 1 nephew","2 nieces and 2 nephews","5 nieces and no nephews"],0],
["Which statement correctly describes the friendship?",["Bree and Liliana have been best friends for 6 years","They have been friends for 1 year","They met last month","They have been friends for 12 years"],0],
["Which description brings together several known Liliana traits?",["Sweet, caring, charismatic and empathetic","Quiet, distant, impatient and careless","Strict, cold, shy and indifferent","Competitive, rude, distant and serious"],0],
["Which final combination is entirely correct about Liliana?",["Baby pink, dolphins, poetry and sushi","Blue, sharks, football and steak","Purple, horses, opera and curry","Green, snakes, chess and soup"],0]
];

function game23(){
 makeLilianaQuiz(23,shuffle([...finalQuestions]),"THE FINAL CHALLENGE COMPLETE! 💕");
}

/* =========================================================
   RESULTS
========================================================= */

function showResults(){
 clearRuntime();
 showScreen("results");

 const qualifies=state.score>3000;

 $("resultsPage").innerHTML=`
 <div class="hero">
  <span class="emoji">🎉🚂💗</span>
  <h1>Journey Complete!</h1>
  <p class="subtitle">${escapeHTML(state.name)}, you made it through all 23 levels.</p>
 </div>

 <div class="card results">
  <h2>🏆 Final Score</h2>
  <div class="pot">${state.score}</div>
  <p>🪙 Tokens earned: <b>${state.tokens}</b></p>
  <p>📍 Levels completed: <b>23/23</b></p>
 </div>

 <div class="reward center">
  ${
   qualifies
   ? `<h2>📞 PRIVATE CALL UNLOCKED!</h2>
      <p>You finished with <b>${state.score}</b> points, which is above the 3000-point requirement.</p>
      <p>💗 3001+ qualifies. Exactly 3000 would not qualify.</p>`
   : `<h2>💕 You did it!</h2>
      <p>You completed the whole Lulu Express journey.</p>
      <p>Private call reward requires a score of <b>3001+</b>.</p>`
  }
 </div>

 <button class="secondary bigbtn" id="replayJourney">🔄 Replay From Level 1</button>
 `;

 $("replayJourney").addEventListener("click",()=>{
  state.completed=0;
  state.unlocked=1;
  state.score=0;
  state.tokens=0;
  save();
  updateStats();
  startLevel(1);
 });
}

function escapeHTML(s){
 return String(s||"").replace(/[&<>"']/g,c=>({
  "&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#039;"
 }[c]));
}

/* =========================================================
   GAME REGISTRY
========================================================= */

const games={
 1:game1,
 2:game2,
 3:game3,
 4:game4,
 5:game5,
 6:game6,
 7:game7,
 8:game8,
 9:game9,
 10:game10,
 11:game11,
 12:game12,
 13:game13,
 14:game14,
 15:game15,
 16:game16,
 17:game17,
 18:game18,
 19:game19,
 20:game20,
 21:game21,
 22:game22,
 23:game23
};

</script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#170b13">
<title>Lulu Express 🚂💗</title>

<style>
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
:root{
  --bg:#12080e;
  --panel:#26121e;
  --panel2:#351827;
  --pink:#ff8fbd;
  --pink2:#ffb7d5;
  --burgundy:#721d3d;
  --gold:#ffd76b;
  --green:#83e6a5;
  --red:#ff6d7e;
  --text:#fff5fa;
  --muted:#cdaabd;
}
body{
  margin:0;
  background:
    radial-gradient(circle at 20% 10%,#55203d 0,transparent 30%),
    radial-gradient(circle at 80% 90%,#42162e 0,transparent 35%),
    var(--bg);
  color:var(--text);
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Arial,sans-serif;
  min-height:100vh;
}
button,input{
  font:inherit;
}
button{
  border:0;
  cursor:pointer;
}
.hidden{display:none!important}

header{
  position:sticky;
  top:0;
  z-index:50;
  background:rgba(18,8,14,.94);
  backdrop-filter:blur(12px);
  border-bottom:1px solid #633047;
  padding:10px;
}
.header-inner{
  max-width:1050px;
  margin:auto;
  display:flex;
  gap:8px;
  align-items:center;
  flex-wrap:wrap;
}
.logo{
  font-size:20px;
  font-weight:900;
  margin-right:auto;
}
.stat{
  background:#29131f;
  border:1px solid #5a2c42;
  padding:7px 10px;
  border-radius:12px;
  font-size:13px;
}
.music{
  display:flex;
  align-items:center;
  gap:5px;
}
.music button,.small-btn{
  background:#452034;
  color:white;
  padding:7px 10px;
  border-radius:9px;
}
#volume{width:70px}
.reset{
  background:#5a182b!important;
  color:#ffdce8!important;
}

main{
  max-width:1050px;
  margin:auto;
  padding:20px 12px 70px;
}
.panel{
  background:linear-gradient(145deg,rgba(53,24,39,.96),rgba(30,13,23,.97));
  border:1px solid #66334b;
  border-radius:20px;
  padding:20px;
  box-shadow:0 15px 45px rgba(0,0,0,.25);
}
h1,h2,h3{margin-top:0}
h1{font-size:34px}
h2{font-size:26px}
p{line-height:1.55;color:#f1dce6}

.primary{
  background:linear-gradient(135deg,#ff78ad,#b62f61);
  color:white;
  font-weight:900;
  padding:13px 18px;
  border-radius:13px;
  box-shadow:0 7px 20px rgba(255,80,145,.22);
}
.secondary{
  background:#472238;
  color:white;
  padding:12px 16px;
  border-radius:12px;
  border:1px solid #74405a;
}
.danger{
  background:#5b172b;
  color:#ffdce8;
  padding:10px 14px;
  border-radius:10px;
}
.center{text-align:center}

#startScreen{
  max-width:650px;
  margin:35px auto;
}
.train{
  font-size:70px;
  animation:float 2s ease-in-out infinite;
}
@keyframes float{
  50%{transform:translateY(-8px)}
}

.name-input{
  width:100%;
  padding:14px;
  border-radius:12px;
  border:1px solid #79405a;
  background:#160a11;
  color:white;
  margin:10px 0 14px;
  outline:none;
}

.progress-wrap{
  height:10px;
  background:#180a11;
  border-radius:20px;
  overflow:hidden;
  margin:10px 0 20px;
}
.progress{
  height:100%;
  background:linear-gradient(90deg,#ff83b7,#ffd76b);
  width:0%;
  transition:.3s;
}

.journey-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
  gap:12px;
}
.level-card{
  position:relative;
  background:#21101a;
  border:1px solid #5d3045;
  border-radius:16px;
  padding:15px;
  min-height:150px;
}
.level-card.available{
  border-color:#d45d8a;
  box-shadow:0 0 20px rgba(255,100,160,.1);
}
.level-card.completed{
  border-color:#6dcc8e;
}
.level-card.locked{
  opacity:.5;
}
.level-number{
  color:#ff9fc5;
  font-weight:900;
}
.level-icon{
  font-size:30px;
  margin:7px 0;
}
.status{
  font-size:12px;
  color:#dcb7c8;
}
.level-card button{
  margin-top:10px;
  width:100%;
}

.game-top{
  display:flex;
  align-items:center;
  gap:10px;
  flex-wrap:wrap;
}
.game-top .game-info{
  margin-right:auto;
}
.game-area{
  margin-top:18px;
}

.notice{
  padding:12px;
  border-radius:12px;
  background:#1b0d15;
  border:1px solid #533047;
  margin:10px 0;
}
.success{border-color:#4f9c6b;background:#12251a}
.failure{border-color:#934356;background:#2b111a}

.choice-grid{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:10px;
}
.choice{
  background:#402035;
  color:white;
  border:1px solid #72425a;
  padding:14px;
  border-radius:13px;
  text-align:left;
}
.choice:hover{background:#583047}
.choice.correct{background:#235c3a;border-color:#79d79b}
.choice.wrong{background:#662032;border-color:#ff7184}

.timer{
  font-size:25px;
  font-weight:900;
  color:#ffd76b;
}

.game-controls{
  display:flex;
  gap:8px;
  flex-wrap:wrap;
  justify-content:center;
  margin-top:15px;
}

/* Broken hearts */
#heartField{
  height:430px;
  max-width:420px;
  margin:auto;
  background:linear-gradient(#1c0b17,#321225);
  border:2px solid #66334c;
  border-radius:18px;
  position:relative;
  overflow:hidden;
  touch-action:none;
}
.catcher{
  position:absolute;
  bottom:12px;
  left:50%;
  width:85px;
  height:24px;
  transform:translateX(-50%);
  border-radius:20px;
  background:#ff91bd;
}
.falling-heart{
  position:absolute;
  font-size:27px;
  user-select:none;
}

/* Memory */
.memory-grid{
  display:grid;
  grid-template-columns:repeat(4,65px);
  justify-content:center;
  gap:7px;
}
.memory-tile{
  width:65px;
  height:65px;
  border-radius:10px;
  background:#3c1d31;
  color:transparent;
  border:1px solid #63374e;
}
.memory-tile.flash{
  background:#ff86b6;
  color:white;
}

/* Slots */
.reels{
  display:flex;
  justify-content:center;
  gap:10px;
  margin:20px 0;
}
.reel{
  width:90px;
  height:90px;
  background:#13090e;
  border:3px solid #b65a7d;
  border-radius:15px;
  display:grid;
  place-items:center;
  font-size:45px;
}
.lever{
  font-size:35px;
  background:#5b1c35;
  color:white;
  padding:15px;
  border-radius:50%;
}

/* Logic */
.logic-row{
  display:flex;
  justify-content:center;
  gap:8px;
  margin:20px 0;
  flex-wrap:wrap;
}
.logic-tile{
  width:60px;
  height:60px;
  display:grid;
  place-items:center;
  background:#140a10;
  border:1px solid #704058;
  border-radius:10px;
  font-size:28px;
}

/* Bluff */
.cards{
  display:flex;
  justify-content:center;
  gap:10px;
  flex-wrap:wrap;
}
.bluff-card{
  width:75px;
  height:105px;
  border-radius:10px;
  background:linear-gradient(135deg,#652044,#29101e);
  border:2px solid #a85278;
  color:white;
  font-size:28px;
}

/* Survival */
.survival-actions{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:10px;
}
.survival-actions button{
  padding:22px;
  background:#412036;
  color:white;
  border-radius:14px;
  font-weight:900;
}

/* New Admirer Race */
.race-track{
  background:#190b12;
  border:2px solid #66344b;
  border-radius:18px;
  padding:18px;
  overflow:hidden;
}
.horse-lane{
  position:relative;
  height:65px;
  background:repeating-linear-gradient(
    90deg,#2c1720 0,#2c1720 35px,#24121a 35px,#24121a 70px
  );
  border-bottom:1px solid #593044;
  margin-bottom:7px;
  border-radius:8px;
}
.horse{
  position:absolute;
  left:2%;
  top:12px;
  font-size:36px;
  transition:left .4s ease-out;
}
.finish-line{
  position:absolute;
  right:3%;
  top:0;
  height:100%;
  width:8px;
  background:repeating-linear-gradient(
    0deg,#fff 0 8px,#111 8px 16px
  );
}
.timing-bar{
  height:45px;
  background:#170a10;
  border:2px solid #5e3045;
  border-radius:12px;
  position:relative;
  overflow:hidden;
  margin:20px 0 10px;
}
.good-zone{
  position:absolute;
  left:40%;
  width:20%;
  top:0;
  bottom:0;
  background:#4b9b62;
  opacity:.7;
}
.marker{
  position:absolute;
  width:6px;
  top:0;
  bottom:0;
  background:#fff;
  left:0;
}
.go-btn{
  width:100%;
  padding:18px;
  font-size:21px;
  font-weight:900;
  background:#ff79ad;
  color:white;
  border-radius:14px;
}
.horse-select{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:8px;
}
.horse-choice{
  padding:12px 5px;
  background:#3d1b2d;
  color:white;
  border-radius:12px;
}
.horse-choice.selected{
  outline:3px solid #ff9ac4;
}

/* Chamber */
.room-grid{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:10px;
}
.room-item{
  padding:25px 10px;
  background:#3a1b2d;
  border-radius:14px;
  text-align:center;
  cursor:pointer;
}
.keypad{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  max-width:300px;
  margin:auto;
  gap:8px;
}
.keypad button{
  padding:17px;
  background:#3e1e31;
  color:white;
  border-radius:10px;
}

/* Boxing */
.health{
  height:18px;
  background:#16090f;
  border-radius:20px;
  overflow:hidden;
  margin:7px 0 15px;
}
.health-fill{
  height:100%;
  background:#ff6680;
  transition:.3s;
}
.fight-actions{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:9px;
}
.fight-actions button{
  padding:15px;
  border-radius:12px;
  background:#472035;
  color:white;
}

/* Match */
.match-board{
  display:grid;
  grid-template-columns:repeat(5,1fr);
  gap:10px;
}
.match-object,.match-target{
  min-height:75px;
  display:grid;
  place-items:center;
  border-radius:14px;
  font-size:32px;
}
.match-object{
  background:#4b2138;
  border:2px solid #81415e;
  cursor:grab;
}
.match-target{
  border:2px dashed #a96582;
  background:#1a0c13;
}

/* Reaction */
.reaction-box{
  min-height:230px;
  display:grid;
  place-items:center;
  border-radius:20px;
  background:#1b0b14;
  border:2px solid #5f3047;
  font-size:30px;
  font-weight:900;
  text-align:center;
  padding:20px;
}

/* Heart hunt */
#huntArea{
  height:420px;
  position:relative;
  overflow:hidden;
  border-radius:18px;
  background:
    radial-gradient(circle at 30% 30%,#642343,transparent 20%),
    radial-gradient(circle at 80% 60%,#4c1a35,transparent 20%),
    #170a11;
}
.hunt-heart{
  position:absolute;
  font-size:28px;
  cursor:pointer;
}

/* Cupid */
#shootArea{
  height:400px;
  position:relative;
  background:#180a11;
  border:2px solid #5d3045;
  border-radius:18px;
  overflow:hidden;
}
.target-heart{
  position:absolute;
  font-size:35px;
  cursor:pointer;
}

/* Countdown */
.mini-bar{
  height:45px;
  background:#160910;
  border:1px solid #603147;
  border-radius:12px;
  position:relative;
  overflow:hidden;
}
.mini-zone{
  position:absolute;
  left:43%;
  width:14%;
  height:100%;
  background:#4f9e64;
}
.mini-marker{
  position:absolute;
  width:7px;
  height:100%;
  background:white;
}

/* Gamble */
.gamble-pot{
  font-size:42px;
  color:#ffd76b;
  font-weight:900;
}
.gamble-actions{
  display:flex;
  justify-content:center;
  gap:10px;
  flex-wrap:wrap;
}

/* Boss */
.boss{
  font-size:80px;
  text-align:center;
  animation:bossFloat 1.5s ease-in-out infinite;
}
@keyframes bossFloat{50%{transform:translateY(-7px)}}

/* Word find */
.word-list{
  display:flex;
  flex-wrap:wrap;
  gap:5px;
  margin:12px 0;
}
.word{
  background:#301725;
  border:1px solid #63344a;
  padding:4px 7px;
  border-radius:7px;
  font-size:12px;
}
.word.found{
  text-decoration:line-through;
  opacity:.45;
}
.word-grid{
  display:grid;
  grid-template-columns:repeat(12,1fr);
  max-width:600px;
  margin:auto;
  user-select:none;
  touch-action:none;
}
.letter{
  aspect-ratio:1;
  display:grid;
  place-items:center;
  background:#27121e;
  border:1px solid #4c293b;
  font-weight:800;
  font-size:clamp(11px,3vw,18px);
}
.letter.selected{background:#8d3156}
.letter.found{background:#4c9d67}

/* Drawing */
canvas{
  display:block;
  width:100%;
  max-width:700px;
  height:400px;
  background:#fff9fb;
  border-radius:15px;
  touch-action:none;
  margin:auto;
}
.draw-controls{
  display:flex;
  gap:8px;
  flex-wrap:wrap;
  justify-content:center;
  margin:10px 0;
}
.draw-controls button{
  padding:9px 13px;
  border-radius:9px;
}

/* Derby */
.derby-track{
  background:#1b0d13;
  border:2px solid #603147;
  border-radius:15px;
  padding:10px;
}
.derby-lane{
  height:52px;
  position:relative;
  background:#2c1720;
  border-bottom:1px solid #5a3043;
  margin:4px;
}
.derby-horse{
  position:absolute;
  left:0;
  top:5px;
  font-size:32px;
  transition:left .3s;
}

/* Finale */
.final-score{
  font-size:30px;
  color:#ffd76b;
  font-weight:900;
}

@media(max-width:600px){
  h1{font-size:28px}
  h2{font-size:22px}
  .choice-grid{grid-template-columns:1fr}
  .memory-grid{grid-template-columns:repeat(4,58px)}
  .memory-tile{width:58px;height:58px}
  .horse-select{grid-template-columns:repeat(2,1fr)}
  .match-board{grid-template-columns:repeat(3,1fr)}
  .room-grid{grid-template-columns:1fr}
  header .logo{width:100%}
  canvas{height:330px}
}
</style>
</head>

<body>

<header>
  <div class="header-inner">
    <div class="logo">🚂 Lulu Express 💗</div>
    <div class="stat">👤 <span id="playerName">Guest</span></div>
    <div class="stat">⭐ <span id="score">0</span></div>
    <div class="stat">🪙 <span id="tokens">0</span></div>
    <div class="stat">🗺️ <span id="journeyProgress">0/23</span></div>

    <div class="music">
      <button id="musicToggle" onclick="toggleMusic()">▶️</button>
      <input id="volume" type="range" min="0" max="1" step=".05" value=".5">
      <label class="small-btn">
        🎵 Music
        <input id="musicFile" type="file" accept="audio/*" hidden>
      </label>
    </div>

    <button class="small-btn reset" onclick="resetGame()">Reset</button>
  </div>
</header>

<audio id="music" loop></audio>

<main>

<section id="startScreen" class="panel center">
  <div class="train">🚂💗</div>
  <h1>Lulu Express</h1>
  <h2>A Journey Made For Liliana</h2>
  <p>
    Welcome to the ultimate Lulu Express journey.  
    Pass each level to unlock the next one, collect points and tokens,
    and make it all the way to the Final Challenge.
  </p>

  <input
    id="nameInput"
    class="name-input"
    maxlength="30"
    placeholder="Enter your name..."
    autocomplete="off"
  >

  <button class="primary" onclick="startJourney()">
    🚂 Start My Journey
  </button>
</section>

<section id="journeyScreen" class="hidden">
  <div class="panel">
    <h1>🗺️ Your Lulu Express Journey</h1>
    <p id="journeyMessage">
      Pass each level to unlock the next.
    </p>

    <div class="progress-wrap">
      <div id="journeyBar" class="progress"></div>
    </div>

    <div id="journeyGrid" class="journey-grid"></div>
  </div>
</section>

<section id="gameScreen" class="hidden">
  <div class="panel">
    <div class="game-top">
      <div class="game-info">
        <div class="level-number" id="gameLevel"></div>
        <h2 id="gameTitle"></h2>
      </div>
      <button class="secondary" onclick="showJourney()">🗺️ Journey</button>
    </div>

    <div id="gameArea" class="game-area"></div>
  </div>
</section>

</main>

<script>
/* =========================================================
   CORE STATE
========================================================= */

const levels = [
  ["💔","Broken Hearts"],
  ["🧠","Memory Vault"],
  ["⏱️","Pressure Quiz"],
  ["🎰","High Roller"],
  ["🧩","Mind Games"],
  ["🃏","The Bluff"],
  ["🛡️","The Survival Round"],
  ["🏇","The Admirer Race"],
  ["🔎","The Heartbreak Chamber"],
  ["🥊","The Heartbreak Boxing Match"],
  ["🧲","The Perfect Match"],
  ["💗","Who Knows Liliana Best?"],
  ["⚡","The Reaction Gauntlet"],
  ["❤️","The Heart Hunt"],
  ["🔐","The Love Lock"],
  ["🏹","The Cupid Shootout"],
  ["⏳","The Countdown"],
  ["🎲","The Ultimate Gamble"],
  ["👑","The Admirer's Last Stand"],
  ["🔎","Liliana's Word Find"],
  ["🌻","Draw a Sunflower"],
  ["🏇","THE LULU DERBY"],
  ["💕","THE FINAL CHALLENGE"]
];

let state = {
  name:"",
  score:0,
  tokens:0,
  unlocked:1,
  completed:{},
  gameBest:{},
  currentLevel:1
};

let game = {};
let timerInterval = null;
let animationFrame = null;

function save(){
  localStorage.setItem("luluExpressState",JSON.stringify(state));
}

function load(){
  try{
    const saved=JSON.parse(localStorage.getItem("luluExpressState"));
    if(saved) state={...state,...saved};
  }catch(e){}
}

function updateHeader(){
  document.getElementById("playerName").textContent=state.name||"Guest";
  document.getElementById("score").textContent=state.score;
  document.getElementById("tokens").textContent=state.tokens;

  const done=Object.keys(state.completed).length;
  document.getElementById("journeyProgress").textContent=done+"/23";
  document.getElementById("journeyBar").style.width=(done/23*100)+"%";
}

function addPoints(n){
  state.score+=n;
  if(state.score<0)state.score=0;
  updateHeader();
  save();
}

function addTokens(n){
  state.tokens+=n;
  if(state.tokens<0)state.tokens=0;
  updateHeader();
  save();
}

function startJourney(){
  const input=document.getElementById("nameInput");
  const name=input.value.trim();

  if(!name){
    input.focus();
    input.style.borderColor="#ff6d7e";
    return;
  }

  state.name=name;
  state.unlocked=Math.max(1,state.unlocked||1);
  save();

  document.getElementById("startScreen").classList.add("hidden");
  showJourney();
}

function showJourney(){
  clearTimers();

  document.getElementById("startScreen").classList.add("hidden");
  document.getElementById("gameScreen").classList.add("hidden");
  document.getElementById("journeyScreen").classList.remove("hidden");

  updateHeader();

  const grid=document.getElementById("journeyGrid");
  grid.innerHTML="";

  levels.forEach((level,i)=>{
    const number=i+1;
    const completed=!!state.completed[number];
    const unlocked=number<=state.unlocked;

    const card=document.createElement("div");
    card.className="level-card "+
      (completed?"completed ":"")+
      (unlocked&&!completed?"available ":"")+
      (!unlocked?"locked":"");

    let status="🔒 Locked";
    if(completed)status="✅ Completed";
    else if(unlocked)status="▶️ Ready";

    card.innerHTML=`
      <div class="level-number">LEVEL ${number}</div>
      <div class="level-icon">${level[0]}</div>
      <h3>${level[1]}</h3>
      <div class="status">${status}</div>
      ${
        unlocked
        ? `<button class="${completed?"secondary":"primary"}"
             onclick="openLevel(${number})">
             ${completed?"Replay":"Play Level"}
           </button>`
        : ""
      }
    `;

    grid.appendChild(card);
  });

  const next=state.unlocked;
  const msg=next<=23
    ? `Keep going, ${escapeHtml(state.name)}! Level ${next} is waiting for you.`
    : `You have reached the end of the journey, ${escapeHtml(state.name)}! 💗`;

  document.getElementById("journeyMessage").innerHTML=msg;
}

function openLevel(number){
  if(number>state.unlocked)return;

  clearTimers();
  state.currentLevel=number;
  save();

  document.getElementById("journeyScreen").classList.add("hidden");
  document.getElementById("gameScreen").classList.remove("hidden");

  document.getElementById("gameLevel").textContent="LEVEL "+number;
  document.getElementById("gameTitle").textContent=
    levels[number-1][0]+" "+levels[number-1][1];

  const area=document.getElementById("gameArea");
  area.innerHTML="";

  game={};

  const funcs=[
    gameBrokenHearts,
    gameMemoryVault,
    gamePressureQuiz,
    gameHighRoller,
    gameMindGames,
    gameBluff,
    gameSurvival,
    gameAdmirerRace,
    gameHeartbreakChamber,
    gameBoxing,
    gamePerfectMatch,
    gameLilianaQuiz,
    gameReaction,
    gameHeartHunt,
    gameLoveLock,
    gameCupid,
    gameCountdown,
    gameUltimateGamble,
    gameLastStand,
    gameWordFind,
    gameSunflower,
    gameDerby,
    gameFinal
  ];

  funcs[number-1]();
}

function completeLevel(number,points=50,tokens=5){
  if(state.completed[number]){
    showJourney();
    return;
  }

  state.completed[number]=true;
  addPoints(points);
  addTokens(tokens);

  if(number===23){
    state.unlocked=23;
  }else{
    state.unlocked=Math.max(state.unlocked,number+1);
  }

  save();

  document.getElementById("gameArea").innerHTML=`
    <div class="notice success center">
      <h2>🎉 Level Passed!</h2>
      <p>Excellent work, ${escapeHtml(state.name)}!</p>
      <p><strong>+${points} points</strong> &nbsp; <strong>+${tokens} tokens</strong></p>
      ${
        number===23
        ? finalReward()
        : `<button class="primary" onclick="showJourney()">
             Continue Journey 🚂
           </button>`
      }
    </div>
  `;

  updateHeader();
}

function finalReward(){
  if(state.score>3000){
    return `
      <div class="notice success">
        <h2>💗 PRIVATE CALL UNLOCKED 💗</h2>
        <p>Your final score is <strong>${state.score}</strong>.</p>
        <p>You reached the required <strong>3001+</strong> points.</p>
        <p>🎉 The private call reward is unlocked!</p>
      </div>
      <button class="primary" onclick="showJourney()">🗺️ View Journey</button>
    `;
  }

  return `
    <div class="notice">
      <h2>🚂 Journey Complete!</h2>
      <p>Your final score is <strong>${state.score}</strong>.</p>
      <p>You needed <strong>3001+</strong> points for the private call reward.</p>
    </div>
    <button class="primary" onclick="showJourney()">🗺️ View Journey</button>
  `;
}

function clearTimers(){
  if(timerInterval)clearInterval(timerInterval);
  if(animationFrame)cancelAnimationFrame(animationFrame);
  timerInterval=null;
  animationFrame=null;
}

function escapeHtml(s){
  return String(s).replace(/[&<>"']/g,m=>({
    "&":"&amp;","<":"&lt;",">":"&gt;",
    '"':"&quot;","'":"&#039;"
  }[m]));
}

/* =========================================================
   ANSWER RANDOMISATION
========================================================= */

function shuffle(arr){
  const a=[...arr];
  for(let i=a.length-1;i>0;i--){
    const j=Math.floor(Math.random()*(i+1));
    [a[i],a[j]]=[a[j],a[i]];
  }
  return a;
}

function shuffledAnswers(options,correctIndex){
  return shuffle(
    options.map((text,i)=>({
      text,
      correct:i===correctIndex
    }))
  );
}

function renderQuestion(q,container,onAnswer){
  const answers=shuffledAnswers(q.options,q.answer);

  container.innerHTML=`
    <div class="notice">${q.q}</div>
    <div class="choice-grid"></div>
  `;

  const grid=container.querySelector(".choice-grid");

  answers.forEach(a=>{
    const btn=document.createElement("button");
    btn.className="choice";
    btn.textContent=a.text;

    btn.onclick=()=>{
      if(grid.dataset.done)return;
      grid.dataset.done="1";

      [...grid.children].forEach(b=>b.disabled=true);

      if(a.correct){
        btn.classList.add("correct");
        onAnswer(true);
      }else{
        btn.classList.add("wrong");
        onAnswer(false);
      }
    };

    grid.appendChild(btn);
  });
}

/* =========================================================
   1. BROKEN HEARTS
========================================================= */

function gameBrokenHearts(){
  const area=document.getElementById("gameArea");

  area.innerHTML=`
    <p class="center">
      Move your catcher and catch the whole hearts. Avoid 💔 and grab 💛!
    </p>
    <div class="notice center">
      Hearts: <b id="heartScore">0</b> &nbsp; Misses: <b id="heartLives">0</b>/3
    </div>
    <div id="heartField">
      <div id="catcher" class="catcher"></div>
    </div>
    <div class="game-controls">
      <button class="secondary" onpointerdown="moveCatcher(-1)">⬅️</button>
      <button class="secondary" onpointerdown="moveCatcher(1)">➡️</button>
    </div>
  `;

  game.catchScore=0;
  game.misses=0;
  game.heartStart=Date.now();
  game.catcherX=50;
  game.hearts=[];
  game.running=true;

  const field=document.getElementById("heartField");

  function spawn(){
    if(!game.running)return;

    const el=document.createElement("div");
    const type=Math.random()<.15?"💛":Math.random()<.25?"💔":"❤️";

    el.className="falling-heart";
    el.textContent=type;
    el.dataset.type=type;
    el.style.left=(Math.random()*88+4)+"%";
    el.style.top="-35px";

    field.appendChild(el);
    game.hearts.push({
      el,
      y:-35,
      speed:1.5+Math.random()*1.3
    });
  }

  game.spawn=spawn;

  function loop(){
    if(!game.running)return;

    const elapsed=(Date.now()-game.heartStart)/1000;

    game.hearts.forEach(h=>{
      h.y+=h.speed;
      h.el.style.top=h.y+"px";

      const r=h.el.getBoundingClientRect();
      const c=document.getElementById("catcher").getBoundingClientRect();

      if(
        r.bottom>=c.top &&
        r.left<c.right &&
        r.right>c.left &&
        r.top<c.bottom
      ){
        if(h.el.dataset.type==="💔"){
          game.misses++;
        }else{
          const pts=h.el.dataset.type==="💛"?30:10;
          game.catchScore+=pts;
        }

        h.el.remove();
        h.dead=true;
      }

      if(h.y>430){
        if(h.el.dataset.type==="❤️")game.misses++;
        h.el.remove();
        h.dead=true;
      }
    });

    game.hearts=game.hearts.filter(h=>!h.dead);

    document.getElementById("heartScore").textContent=game.catchScore;
    document.getElementById("heartLives").textContent=game.misses;

    if(game.misses>=3 || elapsed>=45){
      game.running=false;

      if(game.catchScore>=100){
        addPoints(game.catchScore);
        completeLevel(1,80,5);
      }else{
        area.innerHTML=`
          <div class="notice failure center">
            <h2>💔 Try Again</h2>
            <p>You caught ${game.catchScore} points.</p>
            <p>You need 100 points to pass.</p>
            <button class="primary" onclick="openLevel(1)">Retry</button>
          </div>`;
      }
      return;
    }

    animationFrame=requestAnimationFrame(loop);
  }

  timerInterval=setInterval(spawn,650);
  loop();
}

function moveCatcher(dir){
  if(!game.running)return;
  game.catcherX=Math.max(8,Math.min(92,game.catcherX+dir*8));
  document.getElementById("catcher").style.left=game.catcherX+"%";
}

/* =========================================================
   2. MEMORY VAULT
========================================================= */

function gameMemoryVault(){
  const area=document.getElementById("gameArea");

  area.innerHTML=`
    <p class="center">Watch the sequence, then repeat it.</p>
    <div class="notice center">
      Round <b id="memoryRound">1</b>/7
    </div>
    <div id="memoryGrid" class="memory-grid"></div>
    <div id="memoryMessage" class="notice center">Get ready...</div>
  `;

  game.round=1;
  game.sequence=[];
  game.input=0;
  game.accepting=false;

  const grid=document.getElementById("memoryGrid");

  for(let i=0;i<16;i++){
    const b=document.createElement("button");
    b.className="memory-tile";
    b.dataset.index=i;
    b.textContent="💗";
    b.onclick=()=>memoryClick(i);
    grid.appendChild(b);
  }

  showMemorySequence();
}

function showMemorySequence(){
  game.sequence=[];

  const length=Math.min(3+game.round,9);

  for(let i=0;i<length;i++){
    game.sequence.push(Math.floor(Math.random()*16));
  }

  game.input=0;
  game.accepting=false;

  document.getElementById("memoryRound").textContent=game.round;

  const tiles=[...document.querySelectorAll(".memory-tile")];

  let i=0;

  timerInterval=setInterval(()=>{
    tiles.forEach(t=>t.classList.remove("flash"));

    if(i>=game.sequence.length){
      clearInterval(timerInterval);
      timerInterval=null;
      game.accepting=true;
      document.getElementById("memoryMessage").textContent="Your turn!";
      return;
    }

    tiles[game.sequence[i]].classList.add("flash");
    i++;
  },600);
}

function memoryClick(index){
  if(!game.accepting)return;

  const tiles=[...document.querySelectorAll(".memory-tile")];

  if(index!==game.sequence[game.input]){
    game.accepting=false;
    document.getElementById("memoryMessage").textContent="❌ Wrong tile.";
    setTimeout(()=>openLevel(2),700);
    return;
  }

  tiles[index].classList.add("flash");
  setTimeout(()=>tiles[index].classList.remove("flash"),180);

  game.input++;

  if(game.input>=game.sequence.length){
    game.accepting=false;
    addPoints(20);

    if(game.round>=7){
      completeLevel(2,100,7);
    }else{
      game.round++;
      setTimeout(showMemorySequence,500);
    }
  }
}

/* =========================================================
   3. PRESSURE QUIZ
========================================================= */

const pressureQuestions=[
["What planet is known as the Red Planet?",["Mars","Venus","Jupiter","Mercury"],0],
["How many sides does a hexagon have?",["Five","Six","Seven","Eight"],1],
["Which ocean is the largest?",["Atlantic","Indian","Pacific","Arctic"],2],
["What gas do plants absorb?",["Oxygen","Helium","Carbon dioxide","Hydrogen"],2],
["Which animal is the fastest on land?",["Lion","Cheetah","Horse","Leopard"],1],
["What is the capital of Japan?",["Tokyo","Kyoto","Osaka","Hiroshima"],0],
["How many minutes are in two hours?",["100","110","120","140"],2],
["Which metal has the chemical symbol Au?",["Silver","Gold","Iron","Copper"],1],
["What is H2O?",["Salt","Water","Oxygen","Hydrogen"],1],
["Which continent is Egypt in?",["Asia","Europe","Africa","South America"],2],
["What is the largest mammal?",["Elephant","Blue whale","Giraffe","Orca"],1],
["Which instrument has black and white keys?",["Violin","Trumpet","Piano","Flute"],2],
["How many legs does a spider have?",["Six","Eight","Ten","Twelve"],1],
["Which shape has three sides?",["Square","Triangle","Circle","Pentagon"],1],
["What is the boiling point of water at sea level?",["50°C","75°C","100°C","150°C"],2],
["Which country is famous for the pyramids of Giza?",["Greece","Egypt","Mexico","Peru"],1],
["Which season comes after spring?",["Winter","Autumn","Summer","Monsoon"],2],
["What is the closest star to Earth?",["Sirius","The Sun","Polaris","Betelgeuse"],1],
["Which bird cannot fly?",["Eagle","Penguin","Falcon","Swallow"],1],
["What is 9 × 9?",["72","81","89","99"],1]
];

function gamePressureQuiz(){
  const area=document.getElementById("gameArea");

  game.questions=shuffle(pressureQuestions).slice(0,10);
  game.index=0;
  game.correct=0;

  area.innerHTML=`
    <div class="notice center">
      Question <b id="quizNumber">1</b>/10
      <br>
      <span class="timer" id="quizTimer">7</span>
    </div>
    <div id="quizQuestion"></div>
  `;

  pressureNext();
}

function pressureNext(){
  if(game.index>=10){
    if(game.correct>=7){
      completeLevel(3,100,7);
    }else{
      document.getElementById("gameArea").innerHTML=`
        <div class="notice failure center">
          <h2>⏱️ Pressure Got You!</h2>
          <p>You got ${game.correct}/10.</p>
          <p>You need 7 correct answers to pass.</p>
          <button class="primary" onclick="openLevel(3)">Retry</button>
        </div>`;
    }
    return;
  }

  const raw=game.questions[game.index];
  const q={q:raw[0],options:raw[1],answer:raw[2]};
  const box=document.getElementById("quizQuestion");

  document.getElementById("quizNumber").textContent=game.index+1;

  let time=7;
  document.getElementById("quizTimer").textContent=time;

  clearInterval(timerInterval);

  timerInterval=setInterval(()=>{
    time--;
    document.getElementById("quizTimer").textContent=time;

    if(time<=0){
      clearInterval(timerInterval);
      game.index++;
      pressureNext();
    }
  },1000);

  renderQuestion(q,box,correct=>{
    clearInterval(timerInterval);

    if(correct){
      game.correct++;
      addPoints(10);
    }

    setTimeout(()=>{
      game.index++;
      pressureNext();
    },450);
  });
}

/* =========================================================
   4. HIGH ROLLER
========================================================= */

function gameHighRoller(){
  const area=document.getElementById("gameArea");

  area.innerHTML=`
    <p class="center">Spin the reels and try to hit a winning combination.</p>
    <div class="reels">
      <div id="reel0" class="reel">❔</div>
      <div id="reel1" class="reel">❔</div>
      <div id="reel2" class="reel">❔</div>
    </div>
    <div class="center">
      <button class="lever" onclick="spinSlots()">🎰</button>
    </div>
    <div id="slotMessage" class="notice center">
      Hit a combination worth 30+ points to pass.
    </div>
  `;

  game.slotScore=0;
  game.spins=0;
}

function spinSlots(){
  if(game.spinning)return;

  game.spinning=true;
  const symbols=["🍒","🍋","🔔","💎","7️⃣","💗"];

  let ticks=0;

  timerInterval=setInterval(()=>{
    for(let i=0;i<3;i++){
      document.getElementById("reel"+i).textContent=
        symbols[Math.floor(Math.random()*symbols.length)];
    }

    ticks++;

    if(ticks>=10){
      clearInterval(timerInterval);

      const vals=[];
      for(let i=0;i<3;i++){
        vals.push(document.getElementById("reel"+i).textContent);
      }

      let pts=0;

      if(vals[0]===vals[1]&&vals[1]===vals[2]){
        pts=vals[0]==="7️⃣"?100:60;
      }else if(
        vals[0]===vals[1]||
        vals[1]===vals[2]||
        vals[0]===vals[2]
      ){
        pts=30;
      }

      game.slotScore+=pts;
      game.spins++;
      addPoints(pts);

      document.getElementById("slotMessage").innerHTML=
        pts
        ? `🎉 You won <b>${pts}</b> points!`
        : "No match this time.";

      game.spinning=false;

      if(game.slotScore>=30){
        setTimeout(()=>completeLevel(4,60,5),500);
      }else if(game.spins>=6){
        document.getElementById("slotMessage").innerHTML+=
          `<br><button class="primary" onclick="openLevel(4)">Retry</button>`;
      }
    }
  },100);
}

/* =========================================================
   5. MIND GAMES
========================================================= */

function gameMindGames(){
  const area=document.getElementById("gameArea");

  game.round=0;
  game.correct=0;

  area.innerHTML=`
    <div class="notice center">
      Find the pattern. Round <b id="mindRound">1</b>/8
    </div>
    <div id="mindArea"></div>
  `;

  nextMind();
}

function nextMind(){
  if(game.round>=8){
    completeLevel(5,90,6);
    return;
  }

  game.round++;

  document.getElementById("mindRound").textContent=game.round;

  const patterns=[
    ["▲","▲","●","●","?",["▲","●","■","◆"],1],
    ["1","2","3","4","?",["5","6","7","8"],0],
    ["●","■","●","■","?",["●","▲","■","◆"],0],
    ["2","4","6","8","?",["9","10","12","14"],2],
    ["A","C","E","G","?",["H","I","J","K"],1],
    ["🌙","⭐","🌙","⭐","?",["☀️","🌙","⭐","💗"],1],
    ["5","10","15","20","?",["21","25","30","35"],1],
    ["◆","◆","○","○","?",["◆","○","□","△"],1]
  ];

  const p=patterns[game.round-1];

  const area=document.getElementById("mindArea");

  area.innerHTML=`
    <div class="logic-row">
      ${p.slice(0,5).map(x=>`<div class="logic-tile">${x}</div>`).join("")}
    </div>
    <div class="choice-grid"></div>
  `;

  const answers=shuffle(
    p[5].map((x,i)=>({text:x,correct:i===p[6]}))
  );

  const grid=area.querySelector(".choice-grid");

  answers.forEach(a=>{
    const b=document.createElement("button");
    b.className="choice";
    b.textContent=a.text;
    b.onclick=()=>{
      [...grid.children].forEach(x=>x.disabled=true);

      if(a.correct){
        b.classList.add("correct");
        addPoints(8);
        game.correct++;
        setTimeout(nextMind,350);
      }else{
        b.classList.add("wrong");
        setTimeout(()=>openLevel(5),500);
      }
    };
    grid.appendChild(b);
  });
}

/* =========================================================
   6. THE BLUFF
========================================================= */

function gameBluff(){
  const area=document.getElementById("gameArea");

  game.round=1;
  game.points=0;

  renderBluff();
}

function renderBluff(){
  const area=document.getElementById("gameArea");

  area.innerHTML=`
    <div class="notice center">
      Round ${game.round}/5 · Choose one hidden card.
    </div>
    <div class="cards" id="bluffCards"></div>
    <div id="bluffMessage" class="notice center">
      Pick your risk.
    </div>
  `;

  const cards=document.getElementById("bluffCards");

  for(let i=0;i<4;i++){
    const b=document.createElement("button");
    b.className="bluff-card";
    b.textContent="🂠";
    b.onclick=()=>revealBluff(b);
    cards.appendChild(b);
  }
}

function revealBluff(btn){
  if(game.revealed)return;
  game.revealed=true;

  const value=Math.floor(Math.random()*20)+1;
  btn.textContent=value;

  document.getElementById("bluffMessage").innerHTML=`
    Your card is worth <b>${value}</b>.
    <div class="game-controls">
      <button class="primary" onclick="bluffBank(${value})">💰 Bank</button>
      <button class="secondary" onclick="bluffRisk(${value})">🎲 Risk It</button>
    </div>
  `;
}

function bluffBank(value){
  game.points+=value;
  addPoints(value);

  if(game.round>=5){
    completeLevel(6,Math.max(50,game.points),5);
  }else{
    game.round++;
    game.revealed=false;
    renderBluff();
  }
}

function bluffRisk(value){
  if(Math.random()<.55){
    const bonus=value*2;
    document.getElementById("bluffMessage").innerHTML=
      `🔥 You doubled it! +${bonus}`;
    game.points+=bonus;
    addPoints(bonus);
  }else{
    document.getElementById("bluffMessage").innerHTML=
      `💔 The bluff failed.`;
  }

  setTimeout(()=>{
    if(game.round>=5){
      if(game.points>=25)completeLevel(6,60,5);
      else openLevel(6);
    }else{
      game.round++;
      game.revealed=false;
      renderBluff();
    }
  },600);
}

/* =========================================================
   7. SURVIVAL
========================================================= */

function gameSurvival(){
  const area=document.getElementById("gameArea");

  game.wave=1;
  game.correct=0;

  renderSurvival();
}

function renderSurvival(){
  if(game.wave>8){
    completeLevel(7,90,6);
    return;
  }

  const actions=["JUMP","DUCK","SHIELD","MOVE"];
  const safe=actions[Math.floor(Math.random()*4)];

  game.safe=safe;

  document.getElementById("gameArea").innerHTML=`
    <div class="notice center">
      WAVE ${game.wave}/8
      <h2>${randomHazard()}</h2>
      Choose the correct survival move.
    </div>
    <div class="survival-actions">
      ${actions.map(a=>`
        <button onclick="survivalChoice('${a}')">${actionEmoji(a)} ${a}</button>
      `).join("")}
    </div>
    <div id="survivalMessage" class="notice center"></div>
  `;
}

function randomHazard(){
  const h=["A falling branch!","A swinging object!","A wave rushes toward you!",
           "Something flies overhead!","A low barrier appears!","A dark tunnel closes in!"];
  return h[Math.floor(Math.random()*h.length)];
}

function actionEmoji(a){
  return {JUMP:"🦘",DUCK:"🙇",SHIELD:"🛡️",MOVE:"🏃"}[a];
}

function survivalChoice(a){
  if(a===game.safe){
    addPoints(10);
    game.wave++;
    setTimeout(renderSurvival,350);
  }else{
    document.getElementById("survivalMessage").textContent=
      "❌ Wrong move! You survived the hit, but this round restarts.";
    setTimeout(renderSurvival,700);
  }
}

/* =========================================================
   8. NEW ADMIRER RACE
========================================================= */

function gameAdmirerRace(){
  const area=document.getElementById("gameArea");

  game.horse=0;
  game.positions=[0,0,0,0];
  game.round=1;
  game.finished=false;
  game.marker=0;
  game.direction=1;
  game.selected=0;

  area.innerHTML=`
    <p class="center">
      🏇 <strong>New race mechanic!</strong><br>
      No dodging. No obstacles. Just tap <strong>GO!</strong>
      when the marker is inside the green zone.
    </p>

    <div class="horse-select">
      ${["🐎","🦄","🏇","🐴"].map((x,i)=>`
        <button class="horse-choice ${i===0?"selected":""}"
          onclick="selectRaceHorse(${i})">
          ${x}<br>Horse ${i+1}
        </button>
      `).join("")}
    </div>

    <div class="notice center">
      Round <b id="raceRound">1</b>/8
    </div>

    <div class="race-track">
      ${["🐎","🦄","🏇","🐴"].map((x,i)=>`
        <div class="horse-lane">
          <span id="raceHorse${i}" class="horse">${x}</span>
          <span class="finish-line"></span>
        </div>
      `).join("")}
    </div>

    <div class="notice center">
      <b>Time your tap!</b>
    </div>

    <div class="timing-bar">
      <div class="good-zone"></div>
      <div id="raceMarker" class="marker"></div>
    </div>

    <button id="raceGo" class="go-btn" onclick="raceGo()">
      🏁 GO!
    </button>

    <div id="raceMessage" class="notice center">
      Get ready...
    </div>
  `;

  startRaceMarker();
}

function selectRaceHorse(i){
  if(game.round>1)return;

  game.selected=i;

  document.querySelectorAll(".horse-choice").forEach((b,n)=>{
    b.classList.toggle("selected",n===i);
  });
}

function startRaceMarker(){
  clearInterval(timerInterval);

  game.marker=0;
  game.direction=1;

  timerInterval=setInterval(()=>{
    game.marker+=game.direction*1.7;

    if(game.marker>=100){
      game.marker=100;
      game.direction=-1;
    }

    if(game.marker<=0){
      game.marker=0;
      game.direction=1;
    }

    const marker=document.getElementById("raceMarker");
    if(marker)marker.style.left=game.marker+"%";
  },25);
}

function raceGo(){
  if(game.finished)return;

  const m=game.marker;

  let boost;

  /*
    Very generous zones:
    40-60 = perfect
    30-70 = good
    otherwise small boost
  */

  if(m>=40&&m<=60){
    boost=18;
    document.getElementById("raceMessage").innerHTML=
      "🌟 PERFECT TIMING! Huge boost!";
  }else if(m>=30&&m<=70){
    boost=13;
    document.getElementById("raceMessage").innerHTML=
      "✨ Great timing! Nice boost!";
  }else{
    boost=8;
    document.getElementById("raceMessage").innerHTML=
      "💗 Good enough! Your horse keeps moving!";
  }

  /*
    The player's horse always receives the boost.
    Rivals move more slowly so the level is intentionally
    much easier than the old obstacle version.
  */

  game.positions[game.selected]+=boost;

  for(let i=0;i<4;i++){
    if(i!==game.selected){
      game.positions[i]+=5+Math.random()*4;
    }
  }

  game.positions=game.positions.map(x=>Math.min(100,x));

  game.positions.forEach((p,i)=>{
    const el=document.getElementById("raceHorse"+i);
    if(el)el.style.left=Math.min(91,p)+"%";
  });

  if(game.positions[game.selected]>=100){
    game.finished=true;
    clearInterval(timerInterval);

    setTimeout(()=>{
      completeLevel(8,120,8);
    },500);

    return;
  }

  game.round++;

  if(game.round>8){
    /*
      Even after 8 taps, give the player a final automatic boost.
      This makes the level forgiving rather than frustrating.
    */
    game.positions[game.selected]+=30;

    game.positions[game.selected]=Math.min(
      100,
      game.positions[game.selected]
    );

    const el=document.getElementById("raceHorse"+game.selected);
    if(el)el.style.left=Math.min(91,game.positions[game.selected])+"%";

    if(game.positions[game.selected]>=100){
      game.finished=true;
      clearInterval(timerInterval);
      setTimeout(()=>completeLevel(8,120,8),500);
      return;
    }

    game.round=8;
  }

  document.getElementById("raceRound").textContent=Math.min(game.round,8);
}

/* =========================================================
   9. HEARTBREAK CHAMBER
========================================================= */

function gameHeartbreakChamber(){
  const area=document.getElementById("gameArea");

  game.clues=[];
  game.keyFound=false;
  game.locked=false;

  area.innerHTML=`
    <p class="center">
      Search the room and collect three clues. Then enter the final code.
    </p>

    <div class="room-grid">
      <button class="room-item" onclick="searchRoom('desk')">🗄️ Desk</button>
      <button class="room-item" onclick="searchRoom('painting')">🖼️ Painting</button>
      <button class="room-item" onclick="searchRoom('plant')">🌿 Plant</button>
      <button class="room-item" onclick="searchRoom('book')">📚 Books</button>
    </div>

    <div id="chamberMessage" class="notice center">
      There must be something hidden here...
    </div>

    <div id="chamberLock"></div>
  `;
}

function searchRoom(item){
  if(game.clues.includes(item))return;

  game.clues.push(item);

  const clues={
    desk:"🔎 A note says: the first number is 0.",
    painting:"🔎 Behind the painting: the next number is 6.",
    plant:"🔎 Under the plant: the final clue is 0722.",
    book:"📖 A book contains a reminder: look carefully."
  };

  document.getElementById("chamberMessage").innerHTML=
    clues[item];

  if(game.clues.length>=3){
    document.getElementById("chamberLock").innerHTML=`
      <div class="notice center">
        🔐 You found enough clues.<br>
        Enter <b>060722</b>.
      </div>
      <div class="keypad" id="chamberKeypad"></div>
    `;

    for(let i=1;i<=9;i++)addKey(i);
    addKey(0);

    function addKey(n){
      const b=document.createElement("button");
      b.textContent=n;
      b.onclick=()=>chamberDigit(n);
      document.getElementById("chamberKeypad").appendChild(b);
    }
  }
}

function chamberDigit(n){
  if(!game.code)game.code="";
  if(game.code.length>=6)return;

  game.code+=n;

  document.getElementById("chamberMessage").textContent=
    "Code: "+"•".repeat(game.code.length);

  if(game.code.length===6){
    if(game.code==="060722"){
      completeLevel(9,90,6);
    }else{
      game.code="";
      document.getElementById("chamberMessage").textContent=
        "❌ Wrong code. Try again.";
    }
  }
}

/* =========================================================
   10. BOXING
========================================================= */

function gameBoxing(){
  const area=document.getElementById("gameArea");

  game.playerHP=100;
  game.enemyHP=100;
  game.busy=false;

  renderBoxing();
}

function renderBoxing(){
  document.getElementById("gameArea").innerHTML=`
    <div class="center">
      <h3>🥊 Your Health</h3>
      <div class="health"><div id="playerHP" class="health-fill"></div></div>
      <h3>👊 Opponent</h3>
      <div class="health"><div id="enemyHP" class="health-fill"></div></div>
    </div>

    <div class="fight-actions">
      <button onclick="fightMove('punch')">🥊 Punch</button>
      <button onclick="fightMove('charge')">💥 Heavy Punch</button>
      <button onclick="fightMove('block')">🛡️ Block</button>
      <button onclick="fightMove('dodge')">💨 Dodge</button>
    </div>

    <div id="fightMessage" class="notice center">
      Choose your move.
    </div>
  `;

  updateFightBars();
}

function updateFightBars(){
  document.getElementById("playerHP").style.width=game.playerHP+"%";
  document.getElementById("enemyHP").style.width=game.enemyHP+"%";
}

function fightMove(move){
  if(game.busy)return;
  game.busy=true;

  let damage=0;

  if(move==="punch")damage=12;
  if(move==="charge")damage=20;

  if(move==="punch"||move==="charge"){
    game.enemyHP=Math.max(0,game.enemyHP-damage);
    addPoints(3);
  }

  if(game.enemyHP<=0){
    updateFightBars();
    completeLevel(10,100,7);
    return;
  }

  let enemyDamage=Math.floor(Math.random()*10)+5;

  if(move==="block")enemyDamage=Math.floor(enemyDamage*.35);
  if(move==="dodge")enemyDamage=Math.random()<.7?0:enemyDamage;

  game.playerHP=Math.max(0,game.playerHP-enemyDamage);

  updateFightBars();

  document.getElementById("fightMessage").textContent=
    enemyDamage===0
    ?"💨 Perfect dodge!"
    :`💥 You took ${enemyDamage} damage.`;

  if(game.playerHP<=0){
    setTimeout(()=>openLevel(10),600);
    return;
  }

  setTimeout(()=>{
    game.busy=false;
  },400);
}

/* =========================================================
   11. PERFECT MATCH
========================================================= */

function gamePerfectMatch(){
  const area=document.getElementById("gameArea");

  const items=[
    ["🌻","sunflower"],
    ["🐬","dolphin"],
    ["🌹","rose"],
    ["🍣","sushi"],
    ["💗","heart"]
  ];

  game.matches=0;

  area.innerHTML=`
    <p class="center">Drag each object onto its matching target.</p>
    <div class="match-board" id="matchBoard"></div>
    <div id="matchMessage" class="notice center">0/5 matched</div>
  `;

  const board=document.getElementById("matchBoard");

  const shuffledObjects=shuffle(items);
  const targets=items;

  shuffledObjects.forEach(item=>{
    const d=document.createElement("div");
    d.className="match-object";
    d.textContent=item[0];
    d.draggable=true;
    d.dataset.match=item[1];

    d.addEventListener("dragstart",e=>{
      e.dataTransfer.setData("match",item[1]);
    });

    board.appendChild(d);
  });

  targets.forEach(item=>{
    const t=document.createElement("div");
    t.className="match-target";
    t.textContent="⭕";
    t.dataset.target=item[1];

    t.addEventListener("dragover",e=>e.preventDefault());

    t.addEventListener("drop",e=>{
      const value=e.dataTransfer.getData("match");

      if(value===t.dataset.target&&!t.dataset.done){
        t.dataset.done="1";
        t.textContent=items.find(x=>x[1]===value)[0];
        game.matches++;
        addPoints(10);
        document.getElementById("matchMessage").textContent=
          `${game.matches}/5 matched`;

        if(game.matches>=5)completeLevel(11,80,5);
      }
    });

    board.appendChild(t);
  });
}

/* =========================================================
   12. WHO KNOWS LILIANA BEST
========================================================= */

const lilianaQuiz=[
["What is Liliana's favourite colour?",["Baby pink","Royal blue","Emerald green","Burgundy"],0],
["What is Liliana's favourite number?",["3","7","11","22"],0],
["Which food does Liliana like?",["Sushi","Fish and chips","Tacos only","Curry only"],0],
["Which animal does Liliana like?",["Dolphins","Wolves","Tigers","Koalas"],0],
["Which flower does Liliana like?",["Sunflowers","Tulips","Lilies","Orchids"],0],
["What is Liliana's favourite movie?",["Me Before You","Titanic","Frozen","The Notebook"],0],
["What did Liliana study at university?",["Psychology","Engineering","Law","Architecture"],0],
["What colour are Liliana's eyes?",["Green","Blue","Brown","Grey"],0],
["What is Liliana's zodiac sign?",["Leo","Cancer","Libra","Pisces"],0],
["What is Liliana afraid of?",["Drowning","Flying","Heights","Spiders"],0],
["How many siblings does Liliana have?",["5","2","3","7"],0],
["How many piercings does Liliana have?",["4","2","6","8"],0],
["How many nieces does Liliana have?",["1","2","3","4"],0],
["How many nephews does Liliana have?",["4","1","2","5"],0],
["Which two pets belong to Liliana?",["Aayla and Arlo","Milo and Luna","Bella and Coco","Max and Daisy"],0],
["What kind of songs does Liliana enjoy?",["Sad songs","Only country songs","Only metal","Only opera"],0],
["What kind of writing does Liliana like?",["Poetry","News articles","Technical manuals","Biographies only"],0],
["Which games does Liliana enjoy?",["Poker and gambling games","Chess only","Golf only","Crosswords only"],0],
["What does Liliana hope to become one day?",["A mum","A pilot","A chef","A dancer"],0],
["How long have Bree and Liliana been best friends?",["6 years","2 years","4 years","10 years"],0]
];

function gameLilianaQuiz(){
  const area=document.getElementById("gameArea");

  game.questions=shuffle(lilianaQuiz).slice(0,12);
  game.index=0;
  game.correct=0;

  area.innerHTML=`
    <div class="notice center">
      Liliana Quiz · <b id="lqNumber">1</b>/12
    </div>
    <div id="lq"></div>
  `;

  nextLilianaQuestion();
}

function nextLilianaQuestion(){
  if(game.index>=12){
    if(game.correct>=8){
      completeLevel(12,120,8);
    }else{
      document.getElementById("gameArea").innerHTML=`
        <div class="notice failure center">
          <h2>💗 Not quite!</h2>
          <p>You got ${game.correct}/12.</p>
          <p>You need 8 correct answers.</p>
          <button class="primary" onclick="openLevel(12)">Retry</button>
        </div>`;
    }
    return;
  }

  document.getElementById("lqNumber").textContent=game.index+1;

  const raw=game.questions[game.index];

  renderQuestion(
    {q:raw[0],options:raw[1],answer:raw[2]},
    document.getElementById("lq"),
    correct=>{
      if(correct){
        game.correct++;
        addPoints(8);
      }

      setTimeout(()=>{
        game.index++;
        nextLilianaQuestion();
      },400);
    }
  );
}

/* =========================================================
   13. REACTION GAUNTLET
========================================================= */

function gameReaction(){
  const area=document.getElementById("gameArea");

  game.round=0;
  game.score=0;
  game.waiting=false;

  area.innerHTML=`
    <div class="notice center">
      10 reaction rounds. Follow the instruction exactly.
    </div>
    <div id="reactionBox" class="reaction-box">
      GET READY...
    </div>
  `;

  reactionNext();
}

function reactionNext(){
  if(game.round>=10){
    if(game.score>=7)completeLevel(13,100,7);
    else openLevel(13);
    return;
  }

  game.round++;

  const commands=[
    {text:"TAP NOW!",tap:true},
    {text:"DON'T TAP!",tap:false},
    {text:"TAP NOW!",tap:true},
    {text:"TAP NOW!",tap:true},
    {text:"DON'T TAP!",tap:false}
  ];

  const cmd=commands[Math.floor(Math.random()*commands.length)];

  const box=document.getElementById("reactionBox");

  box.textContent=cmd.text;
  box.dataset.answer=cmd.tap?"tap":"dont";
  game.waiting=true;

  box.onclick=()=>{
    if(!game.waiting)return;
    game.waiting=false;

    if(box.dataset.answer==="tap"){
      game.score++;
      addPoints(7);
      box.textContent="✅";
    }else{
      box.textContent="❌";
    }

    setTimeout(reactionNext,350);
  };

  if(!cmd.tap){
    timerInterval=setTimeout(()=>{
      if(game.waiting){
        game.waiting=false;
        game.score++;
        addPoints(7);
        box.textContent="✅ Great restraint!";
        setTimeout(reactionNext,350);
      }
    },900);
  }else{
    timerInterval=setTimeout(()=>{
      if(game.waiting){
        game.waiting=false;
        box.textContent="⏱️ Too slow!";
        setTimeout(reactionNext,350);
      }
    },1300);
  }
}

/* =========================================================
   14. HEART HUNT
========================================================= */

function gameHeartHunt(){
  const area=document.getElementById("gameArea");

  game.found=0;
  game.targetCount=12;
  game.start=Date.now();

  area.innerHTML=`
    <div class="notice center">
      Find <b>12 hidden hearts</b> before time runs out!
      <br>Found: <b id="huntScore">0</b>/12
    </div>
    <div id="huntArea"></div>
  `;

  spawnHuntHeart();
}

function spawnHuntHeart(){
  const hunt=document.getElementById("huntArea");

  if(!hunt)return;

  if(game.found>=game.targetCount){
    completeLevel(14,90,6);
    return;
  }

  hunt.innerHTML="";

  const decoys=8;

  for(let i=0;i<decoys;i++){
    const d=document.createElement("div");
    d.className="hunt-heart";
    d.textContent=["✨","🌸","⭐","💫"][Math.floor(Math.random()*4)];
    d.style.left=Math.random()*90+"%";
    d.style.top=Math.random()*85+"%";
    d.style.opacity=".35";
    hunt.appendChild(d);
  }

  const h=document.createElement("button");
  h.className="hunt-heart";
  h.textContent="💗";
  h.style.left=Math.random()*88+"%";
  h.style.top=Math.random()*82+"%";

  h.onclick=()=>{
    game.found++;
    addPoints(5);
    document.getElementById("huntScore").textContent=game.found;
    spawnHuntHeart();
  };

  hunt.appendChild(h);
}

/* =========================================================
   15. LOVE LOCK
========================================================= */

function gameLoveLock(){
  const area=document.getElementById("gameArea");

  game.lockCode="";

  area.innerHTML=`
    <div class="notice center">
      🔐 Crack the Love Lock.
      <p>
        Clue 1: The friendship is measured in years.<br>
        Clue 2: The birthday is in July.<br>
        Clue 3: The birthday day is 22.
      </p>
      <strong>Combine the friendship years + birthday.</strong>
    </div>

    <div class="notice center">
      Enter your 6-digit code:
      <h2 id="loveCode">______</h2>
    </div>

    <div class="keypad" id="loveKeypad"></div>
  `;

  for(let i=1;i<=9;i++)loveKey(i);
  loveKey(0);
}

function loveKey(n){
  const b=document.createElement("button");
  b.textContent=n;
  b.onclick=()=>{
    if(game.lockCode.length>=6)return;

    game.lockCode+=n;
    document.getElementById("loveCode").textContent=
      game.lockCode.padEnd(6,"_");

    if(game.lockCode.length===6){
      if(game.lockCode==="060722"){
        completeLevel(15,90,6);
      }else{
        game.lockCode="";
        document.getElementById("loveCode").textContent="______";
      }
    }
  };

  document.getElementById("loveKeypad").appendChild(b);
}

/* =========================================================
   16. CUPID SHOOTOUT
========================================================= */

function gameCupid(){
  const area=document.getElementById("gameArea");

  game.arrows=15;
  game.points=0;

  area.innerHTML=`
    <div class="notice center">
      🏹 Arrows: <b id="arrowCount">15</b> · Score: <b id="cupidScore">0</b>
    </div>
    <div id="shootArea"></div>
  `;

  moveTarget();
}

function moveTarget(){
  const area=document.getElementById("shootArea");

  if(!area)return;

  area.innerHTML="";

  if(game.arrows<=0){
    if(game.points>=70)completeLevel(16,100,7);
    else{
      area.innerHTML=`
        <div class="notice failure center">
          You scored ${game.points}/70.
          <br><button class="primary" onclick="openLevel(16)">Retry</button>
        </div>`;
    }
    return;
  }

  const target=document.createElement("button");
  target.className="target-heart";
  target.textContent=Math.random()<.2?"💛":"💗";
  target.style.left=Math.random()*85+"%";
  target.style.top=Math.random()*80+"%";

  target.onclick=()=>{
    game.arrows--;

    const pts=target.textContent==="💛"?20:8;

    game.points+=pts;
    addPoints(pts);

    document.getElementById("arrowCount").textContent=game.arrows;
    document.getElementById("cupidScore").textContent=game.points;

    moveTarget();
  };

  area.appendChild(target);

  timerInterval=setTimeout(()=>{
    if(document.body.contains(target)){
      game.arrows--;
      document.getElementById("arrowCount").textContent=game.arrows;
      moveTarget();
    }
  },1400);
}

/* =========================================================
   17. COUNTDOWN
========================================================= */

function gameCountdown(){
  const area=document.getElementById("gameArea");

  game.round=0;
  game.points=0;

  countdownNext();
}

function countdownNext(){
  if(game.round>=6){
    completeLevel(17,90,6);
    return;
  }

  game.round++;

  const type=game.round%3;

  if(type===1)countdownBar();
  if(type===2)countdownSequence();
  if(type===0)countdownNumber();
}

function countdownBar(){
  document.getElementById("gameArea").innerHTML=`
    <div class="notice center">
      Mini-game ${game.round}/6<br>
      Tap STOP when the marker is inside the green zone.
    </div>
    <div class="mini-bar">
      <div class="mini-zone"></div>
      <div id="miniMarker" class="mini-marker"></div>
    </div>
    <button class="go-btn" onclick="stopCountdownBar()">STOP!</button>
  `;

  game.marker=0;
  game.dir=1;

  timerInterval=setInterval(()=>{
    game.marker+=game.dir*2;

    if(game.marker>=100){
      game.marker=100;
      game.dir=-1;
    }
    if(game.marker<=0){
      game.marker=0;
      game.dir=1;
    }

    document.getElementById("miniMarker").style.left=game.marker+"%";
  },30);
}

function stopCountdownBar(){
  clearInterval(timerInterval);

  if(game.marker>=35&&game.marker<=65){
    game.points++;
    addPoints(10);
    setTimeout(countdownNext,350);
  }else{
    setTimeout(countdownNext,350);
  }
}

function countdownSequence(){
  const nums=shuffle([1,2,3,4]);

  document.getElementById("gameArea").innerHTML=`
    <div class="notice center">
      Tap the numbers in order: 1 → 2 → 3 → 4
    </div>
    <div class="choice-grid" id="numberButtons"></div>
  `;

  let expected=1;

  nums.forEach(n=>{
    const b=document.createElement("button");
    b.className="choice";
    b.textContent=n;
    b.onclick=()=>{
      if(n===expected){
        expected++;
        b.disabled=true;
        b.classList.add("correct");

        if(expected===5){
          game.points++;
          addPoints(10);
          setTimeout(countdownNext,300);
        }
      }else{
        b.classList.add("wrong");
        setTimeout(countdownNext,300);
      }
    };
    document.getElementById("numberButtons").appendChild(b);
  });
}

function countdownNumber(){
  const target=Math.floor(Math.random()*5)+1;

  document.getElementById("gameArea").innerHTML=`
    <div class="notice center">
      <h2>Tap exactly ${target} times!</h2>
      <p id="tapCount">0</p>
      <button class="go-btn" onclick="countdownTap(${target})">💗 TAP</button>
    </div>
  `;

  game.tap=0;
}

function countdownTap(target){
  game.tap++;

  document.getElementById("tapCount").textContent=game.tap;

  if(game.tap===target){
    game.points++;
    addPoints(10);
    setTimeout(countdownNext,300);
  }else if(game.tap>target){
    setTimeout(countdownNext,300);
  }
}

/* =========================================================
   18. ULTIMATE GAMBLE
========================================================= */

function gameUltimateGamble(){
  const area=document.getElementById("gameArea");

  game.pot=100;
  game.turns=0;

  renderGamble();
}

function renderGamble(){
  document.getElementById("gameArea").innerHTML=`
    <div class="center">
      <h2>🎲 Ultimate Gamble</h2>
      <div class="gamble-pot">$<span id="gamblePot">${game.pot}</span></div>
      <p>Starting pot: 100 · Turn ${game.turns}</p>
    </div>

    <div class="gamble-actions">
      <button class="primary" onclick="gambleRisk()">🎲 Risk It</button>
      <button class="secondary" onclick="gambleCashOut()">💰 Cash Out</button>
    </div>

    <div id="gambleMessage" class="notice center">
      Reach $300 or cash out after at least 3 turns to pass.
    </div>
  `;
}

function gambleRisk(){
  game.turns++;

  if(Math.random()<.62){
    const gain=Math.floor(game.pot*(.25+Math.random()*.5));
    game.pot+=gain;
    addPoints(Math.floor(gain/2));
    document.getElementById("gambleMessage").textContent=
      `🔥 You won $${gain}!`;
  }else{
    const loss=Math.floor(game.pot*.35);
    game.pot=Math.max(0,game.pot-loss);
    document.getElementById("gambleMessage").textContent=
      `💔 You lost $${loss}.`;
  }

  document.getElementById("gamblePot").textContent=game.pot;

  if(game.pot>=300){
    completeLevel(18,120,10);
    return;
  }

  if(game.pot<=0){
    setTimeout(()=>openLevel(18),500);
  }
}

function gambleCashOut(){
  if(game.turns<3){
    document.getElementById("gambleMessage").textContent=
      "You need at least 3 turns before cashing out.";
    return;
  }

  if(game.pot>=180){
    addPoints(game.pot);
    completeLevel(18,100,8);
  }else{
    document.getElementById("gambleMessage").textContent=
      "Cash-out was too small. Reach at least $180.";
  }
}

/* =========================================================
   19. ADMIRER'S LAST STAND
========================================================= */

function gameLastStand(){
  const area=document.getElementById("gameArea");

  game.bossHP=180;
  game.playerHP=100;
  game.phase=1;

  renderBoss();
}

function renderBoss(){
  document.getElementById("gameArea").innerHTML=`
    <div class="boss">👑💔</div>

    <div class="notice center">
      Phase ${game.phase}/3
      <br>Boss HP: ${game.bossHP}
      <br>Your HP: ${game.playerHP}
    </div>

    <div class="fight-actions">
      <button onclick="bossMove('attack')">⚔️ Attack</button>
      <button onclick="bossMove('guard')">🛡️ Guard</button>
      <button onclick="bossMove('special')">💗 Heart Strike</button>
    </div>

    <div id="bossMessage" class="notice center">
      The Admirer is waiting...
    </div>
  `;
}

function bossMove(move){
  let damage=0;

  if(move==="attack")damage=16;
  if(move==="special")damage=28;

  if(move==="guard")damage=5;

  game.bossHP=Math.max(0,game.bossHP-damage);

  if(game.bossHP<=120)game.phase=2;
  if(game.bossHP<=60)game.phase=3;

  let incoming=game.phase*7;

  if(move==="guard")incoming=Math.floor(incoming*.3);

  game.playerHP=Math.max(0,game.playerHP-incoming);

  addPoints(damage);

  if(game.bossHP<=0){
    completeLevel(19,150,10);
    return;
  }

  if(game.playerHP<=0){
    openLevel(19);
    return;
  }

  document.getElementById("bossMessage").textContent=
    `You dealt ${damage} damage. The boss dealt ${incoming}.`;

  renderBoss();
}

/* =========================================================
   20. WORD FIND
========================================================= */

const wordBank=[
"LILIANA","LULU","FRIENDS","PINK","DOLPHIN",
"SUNFLOWER","ROSE","SUSHI","POETRY","MUSIC",
"PSYCHOLOGY","LEO","JULY","LOVE","FAMILY",
"HEART","DREAM","AAYLA","ARLO","OCEAN",
"FOREVER","THREE","SIXYEARS","CHARM","EMPATHY"
];

function gameWordFind(){
  const area=document.getElementById("gameArea");

  game.size=12;
  game.grid=Array.from(
    {length:game.size*game.size},
    ()=>""
  );
  game.words=shuffle(wordBank);
  game.found=new Set();
  game.startCell=null;

  createWordPuzzle();

  area.innerHTML=`
    <p class="center">
      Find all 25 words. Words can go horizontally, vertically,
      diagonally, forwards or backwards.
    </p>

    <div id="wordList" class="word-list"></div>
    <div id="wordGrid" class="word-grid"></div>
    <div id="wordMessage" class="notice center">0/25 found</div>
  `;

  renderWordList();
  renderWordGrid();
}

function createWordPuzzle(){
  const size=game.size;

  const dirs=[
    [0,1],[0,-1],[1,0],[-1,0],
    [1,1],[-1,-1],[1,-1],[-1,1]
  ];

  for(const word of game.words){
    let placed=false;

    for(let attempt=0;attempt<500&&!placed;attempt++){
      const d=dirs[Math.floor(Math.random()*dirs.length)];
      const r=Math.floor(Math.random()*size);
      const c=Math.floor(Math.random()*size);

      const endR=r+d[0]*(word.length-1);
      const endC=c+d[1]*(word.length-1);

      if(
        endR<0||endR>=size||
        endC<0||endC>=size
      )continue;

      let good=true;

      for(let i=0;i<word.length;i++){
        const rr=r+d[0]*i;
        const cc=c+d[1]*i;
        const idx=rr*size+cc;

        if(game.grid[idx] &&
           game.grid[idx]!==word[i]){
          good=false;
          break;
        }
      }

      if(!good)continue;

      for(let i=0;i<word.length;i++){
        const rr=r+d[0]*i;
        const cc=c+d[1]*i;
        game.grid[rr*size+cc]=word[i];
      }

      placed=true;
    }
  }

  const letters="ABCDEFGHIJKLMNOPQRSTUVWXYZ";

  game.grid=game.grid.map(x=>
    x||letters[Math.floor(Math.random()*letters.length)]
  );
}

function renderWordList(){
  const list=document.getElementById("wordList");

  list.innerHTML=game.words.map(w=>`
    <span class="word ${game.found.has(w)?"found":""}">
      ${w}
    </span>
  `).join("");
}

function renderWordGrid(){
  const grid=document.getElementById("wordGrid");
  grid.innerHTML="";

  game.grid.forEach((letter,i)=>{
    const b=document.createElement("div");
    b.className="letter";
    b.textContent=letter;
    b.dataset.i=i;

    b.onpointerdown=e=>{
      e.preventDefault();
      game.startCell=i;
      b.classList.add("selected");
    };

    b.onpointerenter=()=>{
      if(game.startCell!==null)b.classList.add("selected");
    };

    b.onpointerup=()=>{
      if(game.startCell===null)return;

      const end=i;
      checkWordSelection(game.startCell,end);

      document.querySelectorAll(".letter")
        .forEach(x=>x.classList.remove("selected"));

      game.startCell=null;
    };

    grid.appendChild(b);
  });
}

document.addEventListener("pointerup",()=>{
  if(game.startCell!==null){
    game.startCell=null;
    document.querySelectorAll(".letter")
      .forEach(x=>x.classList.remove("selected"));
  }
});

function checkWordSelection(start,end){
  const size=game.size;

  const sr=Math.floor(start/size);
  const sc=start%size;
  const er=Math.floor(end/size);
  const ec=end%size;

  const dr=er-sr;
  const dc=ec-sc;

  const stepR=dr===0?0:dr>0?1:-1;
  const stepC=dc===0?0:dc>0?1:-1;

  if(
    dr!==0&&dc!==0&&Math.abs(dr)!==Math.abs(dc)
  )return;

  const len=Math.max(Math.abs(dr),Math.abs(dc))+1;

  let word="";

  for(let i=0;i<len;i++){
    const r=sr+stepR*i;
    const c=sc+stepC*i;
    word+=game.grid[r*size+c];
  }

  const reverse=word.split("").reverse().join("");

  const foundWord=
    game.words.find(w=>
      !game.found.has(w)&&(w===word||w===reverse)
    );

  if(!foundWord)return;

  game.found.add(foundWord);
  addPoints(6);

  renderWordList();

  document.getElementById("wordMessage").textContent=
    `${game.found.size}/25 found`;

  if(game.found.size>=25){
    completeLevel(20,150,10);
  }
}

/* =========================================================
   21. DRAW A SUNFLOWER
========================================================= */

function gameSunflower(){
  const area=document.getElementById("gameArea");

  area.innerHTML=`
    <p class="center">
      Draw a sunflower! Add a stem, leaves, petals and a centre.
    </p>

    <div class="draw-controls">
      <button onclick="setBrush('#4d9b57',8)">🌿 Stem</button>
      <button onclick="setBrush('#e6b83d',10)">🌻 Petals</button>
      <button onclick="setBrush('#7a4b25',15)">🟤 Centre</button>
      <button onclick="setBrush('#4b73c2',5)">💙 Decoration</button>
      <button onclick="undoDraw()">↩️ Undo</button>
      <button onclick="clearDraw()">🗑️ Clear</button>
    </div>

    <canvas id="sunCanvas" width="900" height="500"></canvas>

    <div class="game-controls">
      <button class="primary" onclick="finishDrawing()">
        🌻 Finish Sunflower
      </button>
    </div>

    <div id="drawMessage" class="notice center">
      Use your finger or mouse to draw.
    </div>
  `;

  const canvas=document.getElementById("sunCanvas");
  const ctx=canvas.getContext("2d");

  game.canvas=canvas;
  game.ctx=ctx;
  game.drawing=false;
  game.history=[];
  game.brush="#4d9b57";
  game.size=8;

  ctx.fillStyle="#fff9fb";
  ctx.fillRect(0,0,canvas.width,canvas.height);

  function pos(e){
    const r=canvas.getBoundingClientRect();
    const touch=e.touches?e.touches[0]:e;
    return {
      x:(touch.clientX-r.left)*canvas.width/r.width,
      y:(touch.clientY-r.top)*canvas.height/r.height
    };
  }

  canvas.addEventListener("pointerdown",e=>{
    game.drawing=true;
    game.history.push(ctx.getImageData(0,0,canvas.width,canvas.height));

    const p=pos(e);
    ctx.beginPath();
    ctx.moveTo(p.x,p.y);
  });

  canvas.addEventListener("pointermove",e=>{
    if(!game.drawing)return;

    const p=pos(e);

    ctx.lineTo(p.x,p.y);
    ctx.strokeStyle=game.brush;
    ctx.lineWidth=game.size;
    ctx.lineCap="round";
    ctx.lineJoin="round";
    ctx.stroke();
  });

  canvas.addEventListener("pointerup",()=>{
    game.drawing=false;
  });

  canvas.addEventListener("pointerleave",()=>{
    game.drawing=false;
  });
}

function setBrush(color,size){
  game.brush=color;
  game.size=size;
}

function undoDraw(){
  if(!game.history.length)return;
  game.ctx.putImageData(game.history.pop(),0,0);
}

function clearDraw(){
  game.ctx.fillStyle="#fff9fb";
  game.ctx.fillRect(0,0,game.canvas.width,game.canvas.height);
  game.history=[];
}

function finishDrawing(){
  completeLevel(21,100,7);
}

/* =========================================================
   22. LULU DERBY
   100 UNIQUE RANDOM TRIVIA QUESTIONS
========================================================= */

const derbyQuestions=[
["Which planet is closest to the Sun?",["Mercury","Venus","Earth","Mars"],0],
["What is the capital of Canada?",["Toronto","Ottawa","Vancouver","Montreal"],1],
["Which animal is known for changing colour?",["Chameleon","Elephant","Penguin","Horse"],0],
["How many bones are in the adult human body approximately?",["106","206","306","406"],1],
["Which country invented pizza in its modern form?",["Italy","France","Spain","Greece"],0],
["What is the largest desert on Earth?",["Sahara","Gobi","Antarctic Desert","Arabian"],2],
["Which sport uses a shuttlecock?",["Tennis","Badminton","Hockey","Rugby"],1],
["What is the chemical symbol for oxygen?",["Ox","O","Og","On"],1],
["Which city is known as the Big Apple?",["Chicago","Boston","New York City","Seattle"],2],
["How many players are on a standard football team on the field?",["9","10","11","12"],2],
["Which bird is famous for mimicking human speech?",["Parrot","Penguin","Swan","Ostrich"],0],
["What is the hardest natural substance?",["Iron","Diamond","Quartz","Granite"],1],
["Which country has the maple leaf on its flag?",["Canada","Austria","Sweden","Norway"],0],
["What is the smallest prime number?",["0","1","2","3"],2],
["Which ocean lies between Africa and Australia?",["Atlantic","Indian","Pacific","Arctic"],1],
["What is the main ingredient in hummus?",["Chickpeas","Potatoes","Rice","Lentils"],0],
["Which planet has famous rings?",["Mars","Saturn","Venus","Mercury"],1],
["Who painted the Mona Lisa?",["Michelangelo","Leonardo da Vinci","Raphael","Van Gogh"],1],
["Which animal is the largest land animal?",["Rhino","Hippo","Elephant","Giraffe"],2],
["What is the currency of Japan?",["Won","Yuan","Yen","Ringgit"],2],
["Which NZ city is known as the Garden City?",["Hamilton","Christchurch","Dunedin","Napier"],1],
["What is the capital of Australia?",["Sydney","Melbourne","Canberra","Perth"],2],
["Which gas makes up most of Earth's atmosphere?",["Oxygen","Nitrogen","Carbon dioxide","Hydrogen"],1],
["How many continents are there commonly taught?",["5","6","7","8"],2],
["Which animal is known for building dams?",["Beaver","Otter","Badger","Fox"],0],
["Which sport is played at Wimbledon?",["Cricket","Tennis","Golf","Rugby"],1],
["What is the largest organ of the human body?",["Heart","Liver","Skin","Lung"],2],
["Which country is shaped like a boot?",["Portugal","Italy","Chile","Croatia"],1],
["How many degrees are in a right angle?",["45","90","180","360"],1],
["What is the freezing point of water in Celsius?",["0","10","32","100"],0],
["Which instrument measures temperature?",["Barometer","Thermometer","Compass","Altimeter"],1],
["Which animal is known as the king of the jungle?",["Tiger","Lion","Jaguar","Leopard"],1],
["Which country is home to Machu Picchu?",["Peru","Brazil","Bolivia","Ecuador"],0],
["What is the largest planet in our solar system?",["Earth","Jupiter","Saturn","Neptune"],1],
["Which fruit is traditionally used to make guacamole?",["Avocado","Mango","Apple","Pear"],0],
["What is the capital of France?",["Lyon","Paris","Nice","Marseille"],1],
["Which sport uses a bat, ball and wickets?",["Baseball","Cricket","Hockey","Tennis"],1],
["What is the opposite of nocturnal?",["Aquatic","Diurnal","Tropical","Arctic"],1],
["Which sea creature has eight arms?",["Squid","Octopus","Jellyfish","Starfish"],1],
["What is the square root of 64?",["6","7","8","9"],2],
["Which country is famous for the Eiffel Tower?",["Italy","France","Belgium","Germany"],1],
["Which planet is famous for its Great Red Spot?",["Jupiter","Saturn","Neptune","Mars"],0],
["What do bees collect from flowers?",["Nectar","Sand","Leaves","Bark"],0],
["Which animal is a marsupial?",["Kangaroo","Tiger","Horse","Wolf"],0],
["What is the capital of Spain?",["Madrid","Barcelona","Seville","Valencia"],0],
["Which vitamin is commonly associated with sunlight?",["Vitamin A","Vitamin B12","Vitamin C","Vitamin D"],3],
["What is 12 × 12?",["124","132","144","154"],2],
["Which country is home to the Taj Mahal?",["India","Pakistan","Nepal","Sri Lanka"],0],
["Which ocean is smallest?",["Arctic","Indian","Atlantic","Southern"],0],
["What is the name of Earth's natural satellite?",["Mars","The Moon","Europa","Titan"],1],
["Which animal has black and white stripes?",["Zebra","Cheetah","Moose","Camel"],0],
["Which city is the capital of New Zealand?",["Auckland","Wellington","Hamilton","Tauranga"],1],
["What is the largest internal organ?",["Brain","Liver","Heart","Kidney"],1],
["Which food is traditionally made from fermented cabbage?",["Kimchi","Hummus","Falafel","Paella"],0],
["Which planet is known for its blue colour?",["Neptune","Mercury","Mars","Venus"],0],
["What is the capital of Italy?",["Rome","Milan","Naples","Turin"],0],
["Which animal can sleep standing up?",["Horse","Dolphin","Rabbit","Penguin"],0],
["Which sport uses a puck?",["Basketball","Ice hockey","Cricket","Tennis"],1],
["What is the largest species of shark?",["Great white","Hammerhead","Whale shark","Tiger shark"],2],
["Which language has the most native speakers?",["English","Mandarin Chinese","French","Spanish"],1],
["What is the main language spoken in Brazil?",["Spanish","Portuguese","French","Italian"],1],
["Which planet is sometimes called Earth's twin?",["Venus","Mars","Mercury","Neptune"],0],
["Which animal is famous for having a pouch?",["Kangaroo","Elephant","Lion","Polar bear"],0],
["What is the capital of Germany?",["Berlin","Munich","Hamburg","Frankfurt"],0],
["Which material is made from trees?",["Glass","Paper","Steel","Ceramic"],1],
["What is 100 divided by 4?",["20","25","30","40"],1],
["Which continent contains the Amazon rainforest?",["Africa","Asia","South America","Europe"],2],
["Which animal is known for its long neck?",["Giraffe","Hippo","Seal","Panda"],0],
["Which sport has a scrum?",["Rugby","Tennis","Golf","Swimming"],0],
["What is the capital of Greece?",["Athens","Rome","Sofia","Lisbon"],0],
["Which metal is liquid at room temperature?",["Iron","Mercury","Copper","Gold"],1],
["What is the largest ocean?",["Atlantic","Pacific","Indian","Southern"],1],
["Which country is famous for tulips and windmills?",["Netherlands","Denmark","Ireland","Poland"],0],
["What is the process plants use to make food from light?",["Respiration","Photosynthesis","Digestion","Fermentation"],1],
["Which animal is the tallest?",["Giraffe","Elephant","Moose","Camel"],0],
["Which sport is associated with a hole-in-one?",["Golf","Tennis","Rugby","Cricket"],0],
["What is the capital of Ireland?",["Dublin","Cork","Galway","Limerick"],0],
["Which planet has the most prominent visible rings?",["Saturn","Earth","Mars","Venus"],0],
["Which fruit is yellow and curved?",["Banana","Apple","Peach","Plum"],0],
["What is the largest country by land area?",["China","Canada","Russia","USA"],2],
["Which animal is known for echolocation?",["Bat","Horse","Giraffe","Panda"],0],
["What is the capital of Portugal?",["Lisbon","Porto","Madrid","Faro"],0],
["Which sport uses a hoop and backboard?",["Basketball","Volleyball","Football","Baseball"],0],
["Which famous ship sank in 1912?",["Titanic","Endeavour","Bismarck","Mayflower"],0],
["What is the nearest planet to Earth on average?",["Mercury","Mars","Venus","Jupiter"],0],
["Which animal is a feline?",["Lion","Wolf","Otter","Horse"],0],
["What is the capital of South Korea?",["Seoul","Busan","Incheon","Daegu"],0],
["Which food is made from cocoa beans?",["Chocolate","Bread","Cheese","Pasta"],0],
["Which number comes after 999?",["1000","1001","9990","990"],0],
["Which country is home to the Great Barrier Reef?",["Australia","New Zealand","Indonesia","Fiji"],0],
["Which animal is known for carrying its home on its back?",["Turtle","Rabbit","Fox","Horse"],0],
["What is the capital of Mexico?",["Cancun","Mexico City","Tijuana","Puebla"],1],
["Which planet is farthest from the Sun?",["Uranus","Neptune","Saturn","Jupiter"],1],
["Which sport is famous for touchdowns?",["American football","Tennis","Golf","Cricket"],0],
["What is the largest bird?",["Eagle","Ostrich","Albatross","Emu"],1],
["Which NZ animal is flightless and iconic?",["Kiwi","Swan","Falcon","Penguin"],0],
["Which country is home to Mount Fuji?",["China","Japan","Thailand","South Korea"],1],
["What is the capital of Norway?",["Oslo","Bergen","Stockholm","Helsinki"],0],
["Which animal is famous for producing honey?",["Bee","Ant","Butterfly","Moth"],0],
["What is the boiling point of water in Celsius at sea level?",["80","90","100","120"],2],
["Which sport is played on a diamond-shaped field?",["Baseball","Rugby","Golf","Tennis"],0]
];

function gameDerby(){
  const area=document.getElementById("gameArea");

  game.questions=shuffle(derbyQuestions);
  game.q=0;
  game.horse=0;
  game.horses=[0,0,0,0];
  game.correct=0;

  area.innerHTML=`
    <p class="center">
      🏇 Pick your horse. Answer 100 trivia questions.
      Correct answers give your horse a boost!
    </p>

    <div class="horse-select">
      ${["🐎","🦄","🏇","🐴"].map((x,i)=>`
        <button class="horse-choice ${i===0?"selected":""}"
          onclick="selectDerbyHorse(${i})">
          ${x}<br>Horse ${i+1}
        </button>
      `).join("")}
    </div>

    <div class="derby-track">
      ${["🐎","🦄","🏇","🐴"].map((x,i)=>`
        <div class="derby-lane">
          <span id="derbyHorse${i}" class="derby-horse">${x}</span>
        </div>
      `).join("")}
    </div>

    <div class="notice center">
      Question <b id="derbyNumber">1</b>/100
    </div>

    <div id="derbyQuestion"></div>
  `;

  derbyNext();
}

function selectDerbyHorse(i){
  if(game.q>0)return;

  game.horse=i;

  document.querySelectorAll(".horse-choice").forEach((b,n)=>{
    b.classList.toggle("selected",n===i);
  });
}

function derbyNext(){
  if(game.q>=100){
    completeLevel(22,250,15);
    return;
  }

  const raw=game.questions[game.q];

  document.getElementById("derbyNumber").textContent=game.q+1;

  renderQuestion(
    {q:raw[0],options:raw[1],answer:raw[2]},
    document.getElementById("derbyQuestion"),
    correct=>{
      if(correct){
        game.correct++;
        game.horses[game.horse]+=3;
        addPoints(5);
      }else{
        game.horses[game.horse]+=1;
      }

      /*
        Keep all horses moving so the race remains visually active.
      */
      for(let i=0;i<4;i++){
        if(i!==game.horse){
          game.horses[i]+=Math.random()*2;
        }
      }

      game.horses=game.horses.map(x=>Math.min(100,x));

      game.horses.forEach((p,i)=>{
        const el=document.getElementById("derbyHorse"+i);
        if(el)el.style.left=Math.min(92,p)+"%";
      });

      game.q++;

      setTimeout(derbyNext,80);
    }
  );
}

/* =========================================================
   23. FINAL CHALLENGE
   50 UNIQUE LILIANA QUESTIONS
========================================================= */

const finalQuestions=[
["Which colour is most associated with Liliana's favourite colour?",["Baby pink","Navy blue","Bright orange","Forest green"],0],
["Which number is Liliana's favourite?",["3","5","7","9"],0],
["Which food is one of Liliana's favourites?",["Sushi","Porridge","Steak","Pancakes"],0],
["Which sea animal does Liliana like?",["Dolphin","Shark","Seal","Walrus"],0],
["Which pair of flowers does Liliana like?",["Sunflowers and roses","Tulips and lilies","Orchids and daisies","Lavender and violets"],0],
["On what date is Liliana's birthday?",["July 22","June 22","July 12","August 22"],0],
["What colour are Liliana's eyes?",["Green","Hazel","Blue","Brown"],0],
["What is Liliana's zodiac sign?",["Leo","Virgo","Gemini","Taurus"],0],
["Which fear is associated with Liliana?",["Drowning","Thunder","Flying","Dark rooms"],0],
["What is Liliana's favourite movie?",["Me Before You","The Notebook","Titanic","La La Land"],0],
["What kind of songs does Liliana enjoy?",["Sad songs","Only happy songs","Only classical music","Only instrumental music"],0],
["What type of writing does Liliana enjoy?",["Poetry","Manuals","Textbooks","Newspapers"],0],
["Which games does Liliana enjoy?",["Poker and gambling games","Only chess","Only golf","Only racing games"],0],
["What did Liliana study at university?",["Psychology","Medicine","Physics","Accounting"],0],
["How many nieces does Liliana have?",["1","2","3","4"],0],
["How many nephews does Liliana have?",["4","2","5","6"],0],
["How many siblings does Liliana have?",["5","3","4","6"],0],
["How many piercings does Liliana have?",["4","2","5","7"],0],
["Which pair are Liliana's dogs?",["Aayla and Arlo","Bella and Luna","Milo and Max","Daisy and Coco"],0],
["What does Liliana hope to become someday?",["A mum","A pilot","A doctor","A singer"],0],
["What kind of child does Liliana hope to have?",["A baby girl","Twin boys","A baby boy only","Triplets"],0],
["How long have Bree and Liliana been best friends?",["6 years","3 years","5 years","8 years"],0],
["Which combination correctly matches Liliana's favourite number and colour?",["3 and baby pink","7 and blue","22 and burgundy","5 and green"],0],
["Which combination correctly matches her favourite animal and food?",["Dolphin and sushi","Otter and pizza","Horse and pasta","Koala and curry"],0],
["Which combination correctly matches her flowers?",["Sunflowers and roses","Roses and orchids","Tulips and roses","Lilies and daisies"],0],
["Which combination correctly matches her birthday month and day?",["July 22","June 27","July 12","August 22"],0],
["Which combination correctly matches her eyes and zodiac sign?",["Green and Leo","Blue and Virgo","Brown and Leo","Hazel and Taurus"],0],
["Which combination correctly matches her movie and writing interest?",["Me Before You and poetry","Titanic and history","Frozen and novels","The Notebook and journalism"],0],
["Which combination correctly matches her study area and games?",["Psychology and poker","Law and chess","Medicine and golf","Engineering and tennis"],0],
["Which combination correctly matches her family counts?",["1 niece and 4 nephews","2 nieces and 3 nephews","4 nieces and 1 nephew","3 nieces and 2 nephews"],0],
["Which combination correctly matches her siblings and piercings?",["5 siblings and 4 piercings","4 siblings and 5 piercings","6 siblings and 2 piercings","3 siblings and 6 piercings"],0],
["Which pair of names belongs together as Liliana's dogs?",["Aayla and Arlo","Aayla and Luna","Arlo and Bella","Milo and Arlo"],0],
["Which statement about Liliana's personality is known?",["She is caring","She dislikes helping people","She avoids children","She is described as unfriendly"],0],
["Which quality is associated with Liliana?",["Empathy","Impatience","Coldness","Indifference"],0],
["Which description fits Liliana?",["Sweet and charismatic","Quiet and uncaring","Unfriendly and distant","Strict and serious"],0],
["What does Liliana like involving children?",["She likes children","She dislikes children","She avoids children","She has no interest in children"],0],
["Which word best matches Liliana's social personality?",["Flirtatious","Withdrawn","Hostile","Unapproachable"],0],
["Which ocean-related wish is associated with Liliana?",["Seeing the ocean someday","Living on a submarine","Avoiding beaches forever","Becoming a sailor"],0],
["Which pair combines one of Liliana's hobbies with something she enjoys reading/writing?",["Gambling games and poetry","Golf and manuals","Chess and textbooks","Running and newspapers"],0],
["Which pair combines one of Liliana's favourite things with her zodiac sign?",["Baby pink and Leo","Blue and Virgo","Green and Taurus","Purple and Gemini"],0],
["How many children-related family members are counted when combining her niece and nephews?",["5","4","6","7"],0],
["Which number connects her favourite number with her friendship length?",["3 and 6","4 and 5","7 and 8","2 and 10"],0],
["Which pair combines her birthday with the length of the friendship?",["July 22 and 6 years","June 22 and 4 years","July 12 and 5 years","August 7 and 3 years"],0],
["Which set contains only things known to be associated with Liliana?",["Sushi, dolphins and sunflowers","Pizza, wolves and tulips","Pasta, horses and orchids","Curry, tigers and lilies"],0],
["Which set contains only Liliana's known interests?",["Poetry, sad songs and gambling games","Football, opera and painting","Golf, ballet and chess","Fishing, metal and coding"],0],
["Which set correctly includes her favourite film and academic subject?",["Me Before You and Psychology","Titanic and Medicine","Frozen and Physics","The Notebook and Law"],0],
["Which set correctly includes her pets and eye colour?",["Aayla and Arlo, green eyes","Bella and Coco, blue eyes","Milo and Luna, brown eyes","Max and Daisy, hazel eyes"],0],
["Which set correctly includes her birthday and zodiac sign?",["July 22 and Leo","June 22 and Cancer","July 12 and Virgo","August 22 and Gemini"],0],
["Which set correctly describes several things Liliana likes?",["Sushi, dolphins, sunflowers and roses","Pizza, sharks, orchids and chess","Pasta, wolves, tulips and golf","Rice, horses, lilies and football"],0],
["Which set correctly combines her family dream and her university study?",["Becoming a mum and studying Psychology","Becoming a pilot and studying Physics","Becoming a chef and studying Chemistry","Becoming an artist and studying Engineering"],0]
];

function gameFinal(){
  const area=document.getElementById("gameArea");

  game.questions=finalQuestions;
  game.index=0;
  game.correct=0;

  area.innerHTML=`
    <div class="notice center">
      💕 THE FINAL CHALLENGE 💕
      <br>
      50 unique questions about Liliana.
      <br>
      <strong>No tattoo questions.</strong>
      <br><br>
      Question <b id="finalNumber">1</b>/50
    </div>
    <div id="finalQuestion"></div>
  `;

  finalNext();
}

function finalNext(){
  if(game.index>=50){
    const finalScore=game.correct;

    if(finalScore>=40){
      addPoints(200);
      completeLevel(23,250,20);
    }else{
      document.getElementById("gameArea").innerHTML=`
        <div class="notice failure center">
          <h2>💕 Final Challenge Complete</h2>
          <div class="final-score">${finalScore}/50</div>
          <p>You need 40/50 to pass.</p>
          <button class="primary" onclick="openLevel(23)">Try Again</button>
        </div>
      `;
    }

    return;
  }

  document.getElementById("finalNumber").textContent=game.index+1;

  const raw=game.questions[game.index];

  renderQuestion(
    {
      q:raw[0],
      options:raw[1],
      answer:raw[2]
    },
    document.getElementById("finalQuestion"),
    correct=>{
      if(correct){
        game.correct++;
        addPoints(10);
      }

      setTimeout(()=>{
        game.index++;
        finalNext();
      },250);
    }
  );
}

/* =========================================================
   MUSIC
========================================================= */

const audio=document.getElementById("music");

document.getElementById("volume").addEventListener("input",e=>{
  audio.volume=e.target.value;
});

document.getElementById("musicFile").addEventListener("change",e=>{
  const file=e.target.files[0];

  if(!file)return;

  const url=URL.createObjectURL(file);
  audio.src=url;
  audio.volume=document.getElementById("volume").value;

  audio.play()
    .then(()=>{
      document.getElementById("musicToggle").textContent="⏸️";
    })
    .catch(()=>{
      document.getElementById("musicToggle").textContent="▶️";
    });
});

function toggleMusic(){
  if(!audio.src){
    document.getElementById("musicFile").click();
    return;
  }

  if(audio.paused){
    audio.play();
    document.getElementById("musicToggle").textContent="⏸️";
  }else{
    audio.pause();
    document.getElementById("musicToggle").textContent="▶️";
  }
}

/* =========================================================
   RESET
========================================================= */

function resetGame(){
  const yes=confirm(
    "Reset Lulu Express completely?\n\n"+
    "This will erase your name, score, tokens, completed levels "+
    "and journey progress."
  );

  if(!yes)return;

  clearTimers();

  localStorage.removeItem("luluExpressState");

  state={
    name:"",
    score:0,
    tokens:0,
    unlocked:1,
    completed:{},
    gameBest:{},
    currentLevel:1
  };

  audio.pause();
  audio.removeAttribute("src");
  audio.load();

  document.getElementById("nameInput").value="";
  document.getElementById("musicToggle").textContent="▶️";

  document.getElementById("journeyScreen").classList.add("hidden");
  document.getElementById("gameScreen").classList.add("hidden");
  document.getElementById("startScreen").classList.remove("hidden");

  updateHeader();
}

/* =========================================================
   STARTUP
========================================================= */

load();

if(state.name){
  document.getElementById("startScreen").classList.add("hidden");
  document.getElementById("journeyScreen").classList.remove("hidden");
}

updateHeader();

document.getElementById("nameInput").addEventListener("keydown",e=>{
  if(e.key==="Enter")startJourney();
});
</script>

</body>
</html>

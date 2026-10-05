<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport"
      content="width=device-width, initial-scale=1.0,
      maximum-scale=1.0,user-scalable=no">

<meta name="theme-color" content="#170b13">

<title>Lulu Express 🚂💗</title>

<style>

*{
  box-sizing:border-box;
  -webkit-tap-highlight-color:transparent;
}

:root{
  --bg:#12080e;
  --bg2:#1b0b14;
  --panel:#28121e;
  --panel2:#351827;
  --pink:#f3a4c5;
  --pink2:#ffd5e6;
  --burgundy:#8e315c;
  --burgundy2:#6d2345;
  --gold:#ffd166;
  --green:#8fe0a3;
  --red:#ff7d91;
  --text:#fff4f8;
  --muted:#caa8b8;
}

html,
body{
  margin:0;
  min-height:100%;
  background:
    radial-gradient(circle at top,#471c32 0,#1a0a13 42%,#0d060a 100%);
  color:var(--text);
  font-family:
    system-ui,
    -apple-system,
    BlinkMacSystemFont,
    "Segoe UI",
    sans-serif;
}

body{
  min-height:100vh;
}

button,
input{
  font:inherit;
}

button{
  border:0;
  color:white;
  background:var(--burgundy);
  border-radius:14px;
  padding:12px 16px;
  min-height:44px;
  font-weight:800;
  cursor:pointer;
  transition:.15s;
}

button:hover{
  filter:brightness(1.12);
  transform:translateY(-1px);
}

button:active{
  transform:scale(.97);
}

button:disabled{
  opacity:.45;
  cursor:not-allowed;
  transform:none;
}

.wrap{
  width:100%;
  max-width:1100px;
  margin:auto;
  padding:14px;
}

header{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:12px;
  flex-wrap:wrap;
}

.logo{
  font-size:clamp(27px,7vw,44px);
  font-weight:1000;
  letter-spacing:-1px;
}

.subtitle{
  color:var(--muted);
  margin-top:2px;
}

.topbar{
  display:flex;
  align-items:center;
  gap:7px;
  flex-wrap:wrap;
}

.stat{
  background:rgba(39,17,29,.95);
  border:1px solid #66324c;
  border-radius:12px;
  padding:9px 12px;
  white-space:nowrap;
}

main{
  margin-top:15px;
}

.panel{
  background:rgba(40,18,30,.96);
  border:1px solid #66324c;
  border-radius:22px;
  padding:18px;
  box-shadow:
    0 15px 45px rgba(0,0,0,.3);
}

.hidden{
  display:none!important;
}

h1,
h2,
h3{
  margin-top:0;
}

p{
  line-height:1.5;
}

.muted{
  color:var(--muted);
}

.badge{
  display:inline-block;
  background:#4b2036;
  color:var(--pink2);
  border-radius:999px;
  padding:5px 10px;
  font-size:12px;
  font-weight:900;
}

.menu{
  display:grid;
  grid-template-columns:
    repeat(auto-fit,minmax(220px,1fr));
  gap:10px;
  margin-top:16px;
}

.game-button{
  text-align:left;
  background:#2d1523;
  border:1px solid #60304a;
  min-height:82px;
}

.game-button.locked{
  opacity:.45;
}

.game-button.completed{
  border-color:#75bd87;
}

.game-button-title{
  font-weight:900;
  font-size:16px;
}

.game-description{
  display:block;
  color:var(--muted);
  font-weight:500;
  font-size:12px;
  margin-top:5px;
}

.game-head{
  display:flex;
  justify-content:space-between;
  gap:12px;
  align-items:flex-start;
  flex-wrap:wrap;
}

.actions{
  display:flex;
  gap:8px;
  flex-wrap:wrap;
  align-items:center;
}

.center{
  text-align:center;
}

.score-big{
  font-size:38px;
  font-weight:1000;
  color:var(--gold);
}

.feedback{
  min-height:30px;
  margin-top:10px;
  color:var(--pink2);
  font-weight:700;
}

.choice-grid{
  display:grid;
  grid-template-columns:repeat(2,minmax(0,1fr));
  gap:10px;
  margin-top:15px;
}

.choice{
  background:#3a1a2b;
  border:1px solid #6b3450;
  text-align:left;
}

.choice.correct{
  outline:3px solid var(--green);
}

.choice.wrong{
  outline:3px solid var(--red);
}

.progress{
  height:10px;
  background:#492136;
  border-radius:999px;
  overflow:hidden;
  margin:15px 0;
}

.progress-fill{
  width:0;
  height:100%;
  background:var(--pink);
  transition:.2s;
}

.big-emoji{
  font-size:55px;
}

.card-row{
  display:flex;
  justify-content:center;
  align-items:center;
  gap:10px;
  flex-wrap:wrap;
}

.card{
  width:92px;
  height:125px;
  background:#f8dce8;
  color:#401326;
  border-radius:14px;
  font-size:35px;
}

.arena{
  position:relative;
  height:330px;
  overflow:hidden;
  border-radius:18px;
  border:1px solid #64304b;
  background:
    radial-gradient(circle at 50% 30%,#341526,#13080e);
}

.target{
  position:absolute;
  padding:4px;
  min-height:0;
  background:transparent;
  font-size:32px;
}

.obstacle{
  position:absolute;
  background:#a84e75;
  border-radius:8px;
}

.falling-area{
  position:relative;
  height:420px;
  overflow:hidden;
  border-radius:18px;
  border:1px solid #63304a;
  background:
    linear-gradient(#29111e,#10070c);
}

.falling-object{
  position:absolute;
  font-size:32px;
  user-select:none;
  pointer-events:none;
}

.catch-bar{
  position:absolute;
  bottom:12px;
  left:50%;
  width:100px;
  height:19px;
  margin-left:-50px;
  border-radius:20px;
  background:var(--pink);
  box-shadow:0 0 15px rgba(243,164,197,.5);
}

.memory-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:7px;
  width:min(430px,100%);
  margin:18px auto;
}

.memory-tile{
  aspect-ratio:1;
  padding:0;
  background:#52253d;
  border:1px solid #6e3450;
  font-size:22px;
}

.memory-tile.flash{
  background:var(--pink);
  color:#351020;
}

.memory-tile.selected{
  background:#b75a83;
}

.slot-machine{
  display:flex;
  justify-content:center;
  gap:8px;
  margin:25px 0;
}

.reel{
  min-width:82px;
  padding:16px 10px;
  background:#f8dce8;
  color:#351020;
  border-radius:16px;
  font-size:48px;
  text-align:center;
}

.lock-grid{
  display:grid;
  grid-template-columns:repeat(3,70px);
  justify-content:center;
  gap:8px;
  margin:18px auto;
}

.lock-grid button{
  font-size:21px;
}

.race{
  position:relative;
  overflow:hidden;
  height:340px;
  border-radius:18px;
  background:#211019;
  border:1px solid #60304a;
}

.lane{
  position:relative;
  height:25%;
  border-bottom:1px dashed #75435d;
}

.horse{
  position:absolute;
  left:5px;
  top:7px;
  font-size:30px;
  transition:left .2s;
}

.finish-line{
  position:absolute;
  right:12px;
  top:0;
  height:100%;
  border-left:5px dashed white;
}

.word-grid{
  display:grid;
  grid-template-columns:repeat(15,1fr);
  width:min(650px,100%);
  margin:16px auto;
  user-select:none;
  touch-action:none;
}

.word-letter{
  aspect-ratio:1;
  min-width:0;
  padding:0;
  border-radius:0;
  border:1px solid #592942;
  background:#381a2a;
  color:white;
  font-size:clamp(9px,2.8vw,18px);
}

.word-letter.selected{
  background:var(--pink);
  color:#32101f;
}

.word-letter.found{
  background:#83bd91;
  color:#162419;
}

.word-list{
  display:flex;
  justify-content:center;
  flex-wrap:wrap;
  gap:6px;
}

.word-item{
  padding:5px 8px;
  border-radius:8px;
  background:#432032;
  color:var(--pink2);
  font-size:12px;
}

.word-item.found{
  color:var(--green);
  text-decoration:line-through;
}

canvas{
  display:block;
  width:100%;
  max-width:760px;
  height:auto;
  margin:auto;
  background:#fff7fb;
  border-radius:18px;
  touch-action:none;
}

.draw-tools{
  display:flex;
  justify-content:center;
  flex-wrap:wrap;
  gap:7px;
  margin:12px 0;
}

.draw-tools button{
  padding:9px 12px;
}

.quiz-question{
  font-size:19px;
  line-height:1.5;
}

.trivia-label{
  font-size:13px;
  color:var(--muted);
}

.mini-bar{
  height:16px;
  background:#4a2135;
  border-radius:20px;
  overflow:hidden;
  margin:20px 0;
}

.mini-bar-fill{
  height:100%;
  width:0;
  background:var(--pink);
}

.toast{
  position:fixed;
  left:50%;
  bottom:18px;
  transform:translateX(-50%);
  background:#f7d8e6;
  color:#351020;
  padding:10px 16px;
  border-radius:13px;
  font-weight:900;
  z-index:9999;
  box-shadow:0 8px 25px rgba(0,0,0,.3);
}

.reward{
  margin-top:18px;
  padding:18px;
  border-radius:18px;
  background:#3b182b;
  border:1px solid #70405a;
}

@media(max-width:600px){

  .wrap{
    padding:10px;
  }

  .panel{
    padding:13px;
  }

  .choice-grid{
    grid-template-columns:1fr;
  }

  .falling-area{
    height:360px;
  }

  .arena{
    height:280px;
  }

  .slot-machine{
    gap:5px;
  }

  .reel{
    min-width:70px;
    font-size:38px;
  }

  .lock-grid{
    grid-template-columns:repeat(3,62px);
  }

}

</style>
</head>

<body>

<div class="wrap">

<header>

<div>
  <div class="logo">🚂 Lulu Express 💗</div>
  <div class="subtitle">
    A little universe of games made for Liliana
  </div>
</div>

<div class="topbar">

<div class="stat">
  ⭐ Score:
  <b id="score">0</b>
</div>

<div class="stat">
  💗 Tokens:
  <b id="tokens">0</b>
</div>

<button id="musicButton">
  🎵 Music
</button>

<button id="resetButton">
  🔄 Reset
</button>

</div>

</header>

<main>

<section id="home" class="panel">

<span class="badge">23 GAMES</span>

<h1>
  All aboard, Lulu Express! 🚂💗
</h1>

<p>
  Twenty-three completely different challenges,
  ending with the ultimate Liliana quiz.
</p>

<p class="muted">
  💕 Private call reward:
  you need a score of <b>3001+</b>.
  A score of exactly 3000 does not qualify.
</p>

<div id="menu" class="menu"></div>

</section>


<section id="gameScreen" class="panel hidden">

<div class="game-head">

<div>
  <span id="gameNumber" class="badge"></span>
  <h2 id="gameTitle"></h2>
</div>

<button id="backButton">
  ← Games
</button>

</div>

<div id="gameArea"></div>

</section>

</main>

</div>

<div id="toast" class="toast hidden"></div>


<script>

"use strict";


/* =========================================================
   CORE
========================================================= */

const $ = selector =>
  document.querySelector(selector);

let score = 0;
let tokens = 0;
let currentGame = -1;

let completedGames = new Set();

let timers = [];
let animationFrame = null;

let musicContext = null;
let musicGain = null;
let musicTimer = null;
let musicPlaying = false;


const games = [

["💔","Broken Hearts",
"Catch whole hearts and avoid the broken ones."],

["🧠","Memory Vault",
"Remember and reproduce a 4×4 sequence."],

["⏱️","Pressure Quiz",
"Fast general knowledge with shuffled answers."],

["🎰","High Roller",
"Stop the reels and chase multipliers."],

["🧩","Mind Games",
"Solve visual logic and pattern puzzles."],

["🃏","The Bluff",
"Choose cards, risk points and cash out."],

["🛡️","The Survival Round",
"Survive waves using different decisions."],

["🏇","The Admirer Race",
"Guide your admirer through an obstacle course."],

["🔎","The Heartbreak Chamber",
"Search clues and escape the chamber."],

["🥊","The Heartbreak Boxing Match",
"Punch, block, dodge and counter."],

["🧲","The Perfect Match",
"Match objects with their partners."],

["💗","Who Knows Liliana Best?",
"Personal trivia about Liliana."],

["⚡","The Reaction Gauntlet",
"React quickly to changing commands."],

["🕵️","The Heart Hunt",
"Find hidden and disguised hearts."],

["🔐","The Love Lock",
"Crack a changing combination."],

["🏹","The Cupid Shootout",
"Aim at moving targets."],

["⏳","The Countdown",
"A rotating collection of mini-games."],

["🎲","Ultimate Gamble",
"Risk the pot or cash out."],

["👑","The Admirer's Last Stand",
"Defeat the multi-phase boss."],

["🔎","Liliana's Word Find",
"Find 25 Liliana-related words."],

["🌻","Draw a Sunflower",
"Create a sunflower for Liliana."],

["🏇","THE LULU DERBY",
"100 random trivia questions while racing."],

["💕","THE FINAL CHALLENGE",
"50 unique questions about Liliana."]

];


function shuffle(array){

  const result = [...array];

  for(let i=result.length-1;i>0;i--){

    const j =
      Math.floor(Math.random()*(i+1));

    [result[i],result[j]] =
      [result[j],result[i]];

  }

  return result;
}


function clearGameTimers(){

  timers.forEach(clearTimeout);
  timers=[];

  if(animationFrame){
    cancelAnimationFrame(animationFrame);
    animationFrame=null;
  }

}


function later(fn,ms){

  const timer=setTimeout(fn,ms);

  timers.push(timer);

  return timer;

}


function toast(message){

  const t=$("#toast");

  t.textContent=message;

  t.classList.remove("hidden");

  later(
    ()=>t.classList.add("hidden"),
    1800
  );

}


function addPoints(amount){

  score=Math.max(0,score+amount);

  if(amount>0){

    tokens+=
      Math.max(1,Math.floor(amount/25));

  }

  updateStats();

}


function updateStats(){

  $("#score").textContent=score;

  $("#tokens").textContent=tokens;

  renderMenu();

}


function finishGame(
  points=100,
  message="Game complete!"
){

  addPoints(points);

  completedGames.add(currentGame);

  renderMenu();

  $("#gameArea").insertAdjacentHTML(
    "beforeend",
    `
    <div class="reward center">

      <h3>✨ ${message}</h3>

      <p>
        You earned
        <b>${points}</b>
        points.
      </p>

      <p>
        Current score:
        <b>${score}</b>
      </p>

      <button onclick="goNextGame()">
        Next game →
      </button>

    </div>
    `
  );

}


function goNextGame(){

  if(currentGame<22){

    startGame(currentGame+1);

  }else{

    showFinalScreen();

  }

}


function renderMenu(){

  const menu=$("#menu");

  if(!menu)return;

  menu.innerHTML="";

  games.forEach((game,index)=>{

    const button =
      document.createElement("button");

    button.className="game-button";

    if(completedGames.has(index))
      button.classList.add("completed");

    button.innerHTML=`
      <div class="game-button-title">
        ${game[0]}
        ${index+1}. ${game[1]}
      </div>

      <span class="game-description">
        ${
          completedGames.has(index)
          ?"✓ Completed • "
          :""
        }
        ${game[2]}
      </span>
    `;

    button.onclick=()=>startGame(index);

    menu.appendChild(button);

  });

}


function startGame(index){

  clearGameTimers();

  currentGame=index;

  $("#home").classList.add("hidden");

  $("#gameScreen").classList.remove("hidden");

  $("#gameNumber").textContent=
    `GAME ${index+1} OF 23`;

  $("#gameTitle").textContent=
    `${games[index][0]} ${games[index][1]}`;

  $("#gameArea").innerHTML="";

  gameFunctions[index]();

  window.scrollTo({
    top:0,
    behavior:"smooth"
  });

}


function showFinalScreen(){

  clearGameTimers();

  $("#gameScreen").classList.remove("hidden");

  $("#home").classList.add("hidden");

  $("#gameNumber").textContent=
    "JOURNEY COMPLETE";

  $("#gameTitle").textContent=
    "🚂 Lulu Express has arrived!";

  const unlocked=score>3000;

  $("#gameArea").innerHTML=`

    <div class="center">

      <div class="big-emoji">
        💗✨🚂✨💗
      </div>

      <h2>
        You made it through all 23 games!
      </h2>

      <div class="score-big">
        ${score}
      </div>

      <p>
        Final Score
      </p>

      ${
        unlocked
        ?
        `
        <div class="reward">

          <h2>
            📞💗 PRIVATE CALL UNLOCKED! 💗📞
          </h2>

          <p>
            You scored <b>${score}</b>,
            which is 3001 or higher.
          </p>

        </div>
        `
        :
        `
        <div class="reward">

          <h3>
            You were so close! 💗
          </h3>

          <p>
            You need <b>3001+</b> points
            to unlock the private call.
          </p>

          <p>
            Exactly 3000 points does not qualify.
          </p>

        </div>
        `
      }

      <div class="actions"
           style="justify-content:center;margin-top:18px">

        <button onclick="startGame(0)">
          🔁 Play Again
        </button>

        <button onclick="returnHome()">
          🏠 Main Menu
        </button>

      </div>

    </div>
  `;

}


function returnHome(){

  clearGameTimers();

  $("#gameScreen").classList.add("hidden");

  $("#home").classList.remove("hidden");

  renderMenu();

}


/* =========================================================
   RESET
========================================================= */

$("#resetButton").onclick=()=>{

  const confirmed=
    confirm(
      "Are you sure you want to reset Lulu Express?\n\n"+
      "This will reset your score, tokens, completed games "+
      "and all game progress."
    );

  if(!confirmed)return;

  clearGameTimers();

  score=0;

  tokens=0;

  completedGames.clear();

  currentGame=-1;

  localStorage.removeItem(
    "luluExpressProgress"
  );

  $("#gameScreen").classList.add("hidden");

  $("#home").classList.remove("hidden");

  updateStats();

  toast("Lulu Express has been reset 💗");

};


/* =========================================================
   MUSIC
========================================================= */

/*
   This uses a tiny built-in generated melody.
   No external audio file is required.
*/

const melodyNotes=[
  261.63,
  329.63,
  392.00,
  329.63,
  293.66,
  349.23,
  440.00,
  349.23,
  261.63,
  329.63,
  392.00,
  523.25
];


function startMusic(){

  if(!musicContext){

    const AudioContext=
      window.AudioContext ||
      window.webkitAudioContext;

    if(!AudioContext){

      toast("Music isn't supported here.");

      return;

    }

    musicContext=
      new AudioContext();

    musicGain=
      musicContext.createGain();

    musicGain.gain.value=.045;

    musicGain.connect(
      musicContext.destination
    );

  }

  if(
    musicContext.state==="suspended"
  ){

    musicContext.resume();

  }

  musicPlaying=true;

  $("#musicButton").textContent=
    "🔇 Music On";

  let note=0;

  function playNote(){

    if(!musicPlaying)return;

    const oscillator=
      musicContext.createOscillator();

    const gain=
      musicContext.createGain();

    oscillator.type="sine";

    oscillator.frequency.value=
      melodyNotes[
        note%melodyNotes.length
      ];

    gain.gain.setValueAtTime(
      .001,
      musicContext.currentTime
    );

    gain.gain.linearRampToValueAtTime(
      .7,
      musicContext.currentTime+.04
    );

    gain.gain.exponentialRampToValueAtTime(
      .001,
      musicContext.currentTime+.58
    );

    oscillator.connect(gain);

    gain.connect(musicGain);

    oscillator.start();

    oscillator.stop(
      musicContext.currentTime+.6
    );

    note++;

    musicTimer=
      setTimeout(playNote,620);

  }

  clearTimeout(musicTimer);

  playNote();

}


function stopMusic(){

  musicPlaying=false;

  clearTimeout(musicTimer);

  $("#musicButton").textContent=
    "🎵 Music";

}


$("#musicButton").onclick=()=>{

  if(!musicPlaying)
    startMusic();
  else
    stopMusic();

};


/* =========================================================
   GAME 1
   BROKEN HEARTS
========================================================= */

function game1(){

  const area=$("#gameArea");

  area.innerHTML=`

    <p>
      Move the catcher with your finger or mouse.
      Catch whole hearts and golden stars.
      Avoid broken hearts!
    </p>

    <div
      class="falling-area"
      id="heartArea"
    >

      <div
        class="catch-bar"
        id="catchBar"
      ></div>

    </div>

    <div
      class="feedback"
      id="heartFeedback"
    >
      ❤️ Lives: 3
      • Score: 0
      • Combo: 0
    </div>

  `;

  const box=$("#heartArea");
  const catcher=$("#catchBar");

  let catcherX=.5;
  let lives=3;
  let points=0;
  let combo=0;
  let objects=[];
  let running=true;


  function moveCatcher(event){

    const rect=
      box.getBoundingClientRect();

    const x=
      event.clientX-rect.left;

    catcherX=
      Math.max(
        .06,
        Math.min(
          .94,
          x/rect.width
        )
      );

    catcher.style.left=
      `calc(${catcherX*100}% - 50px)`;

  }


  box.addEventListener(
    "pointermove",
    moveCatcher
  );

  box.addEventListener(
    "pointerdown",
    moveCatcher
  );


  function spawn(){

    if(!running)return;

    const item=
      document.createElement("div");

    const golden=
      Math.random()<.08;

    const broken=
      Math.random()<.18;

    item.className=
      "falling-object";

    item.textContent=
      broken
      ?"💔"
      :(golden?"⭐":"💗");

    const left=
      4+Math.random()*92;

    item.style.left=
      left+"%";

    item.style.top="-45px";

    box.appendChild(item);

    objects.push({
      element:item,
      x:left,
      y:-45,
      broken,
      golden,
      speed:2.3+points/120
    });

    later(
      spawn,
      Math.max(
        240,
        700-points*2
      )
    );

  }


  function loop(){

    if(!running)return;

    const width=box.clientWidth;
    const height=box.clientHeight;

    objects.forEach(obj=>{

      obj.y+=obj.speed;

      obj.element.style.top=
        obj.y+"px";

      const objectX=
        obj.x/100*width;

      const catcherXPixel=
        catcherX*width;

      if(
        obj.y>height-65 &&
        obj.y<height &&
        Math.abs(
          objectX-catcherXPixel
        )<65
      ){

        if(obj.broken){

          lives--;

          combo=0;

          points=
            Math.max(
              0,
              points-15
            );

        }else{

          combo++;

          const base=
            obj.golden?30:10;

          points+=
            base+
            Math.min(
              combo*2,
              20
            );

        }

        obj.element.remove();

        obj.dead=true;

      }

    });


    objects=
      objects.filter(
        obj=>
          !obj.dead &&
          obj.y<height+60
      );


    $("#heartFeedback").textContent=
      `❤️ Lives: ${lives} • `+
      `Score: ${points} • `+
      `Combo: ${combo}`;


    if(lives<=0){

      running=false;

      finishGame(
        points,
        "The hearts have settled."
      );

      return;

    }


    animationFrame=
      requestAnimationFrame(loop);

  }


  spawn();

  animationFrame=
    requestAnimationFrame(loop);


  later(()=>{

    if(!running)return;

    running=false;

    finishGame(
      points,
      "Broken Hearts complete!"
    );

  },30000);

}


/* =========================================================
   GAME 2
   MEMORY VAULT
========================================================= */

function game2(){

  $("#gameArea").innerHTML=`

    <p>
      Watch the glowing sequence.
      Then tap the tiles in exactly the same order.
    </p>

    <div
      class="memory-grid"
      id="memoryGrid"
    ></div>

    <div class="center">

      <b id="memoryRound">
        Round 1
      </b>

      <div
        class="feedback"
        id="memoryFeedback"
      ></div>

    </div>

  `;

  const grid=$("#memoryGrid");

  let sequence=[];
  let input=[];
  let round=1;
  let accepting=false;


  function drawGrid(){

    grid.innerHTML="";

    for(let i=0;i<16;i++){

      const button=
        document.createElement("button");

      button.className=
        "memory-tile";

      button.textContent=
        i+1;

      button.onclick=
        ()=>chooseTile(i);

      grid.appendChild(button);

    }

  }


  function showSequence(){

    accepting=false;

    input=[];

    drawGrid();

    sequence.push(
      Math.floor(Math.random()*16)
    );


    sequence.forEach(
      (tile,index)=>{

        later(()=>{

          grid.children[tile]
            .classList.add("flash");

        },index*450);

        later(()=>{

          grid.children[tile]
            .classList.remove("flash");

        },index*450+300);

      }
    );


    later(()=>{

      accepting=true;

    },sequence.length*450+450);

  }


  function chooseTile(index){

    if(!accepting)return;

    input.push(index);

    grid.children[index]
      .classList.add("selected");


    const current=
      input.length-1;


    if(
      input[current] !==
      sequence[current]
    ){

      accepting=false;

      $("#memoryFeedback")
        .textContent=
        "❌ Wrong sequence!";

      finishGame(
        round*40,
        "Memory Vault complete."
      );

      return;

    }


    if(
      input.length===
      sequence.length
    ){

      accepting=false;

      const reward=
        round*60;

      addPoints(reward);

      round++;

      $("#memoryRound")
        .textContent=
        `Round ${round}`;

      if(round>8){

        finishGame(
          250,
          "Memory Vault mastered!"
        );

      }else{

        later(
          showSequence,
          650
        );

      }

    }

  }


  showSequence();

}


/* =========================================================
   GENERAL TRIVIA
========================================================= */

const generalQuestions=[

[
"Which planet has the shortest year?",
["Mercury","Venus","Mars","Earth"],
0
],

[
"What is the largest ocean on Earth?",
["Atlantic Ocean","Indian Ocean","Pacific Ocean","Arctic Ocean"],
2
],

[
"Which gas makes up most of Earth's atmosphere?",
["Oxygen","Nitrogen","Carbon dioxide","Argon"],
1
],

[
"Who painted the Mona Lisa?",
["Michelangelo","Leonardo da Vinci","Raphael","Caravaggio"],
1
],

[
"What is the chemical symbol for gold?",
["Ag","Gd","Au","Go"],
2
],

[
"Which country is home to Petra?",
["Jordan","Egypt","Greece","Turkey"],
0
],

[
"How many sides does a dodecagon have?",
["10","11","12","14"],
2
],

[
"Which animal is the largest living mammal?",
["African elephant","Blue whale","Giraffe","Orca"],
1
],

[
"What is the capital of Canada?",
["Toronto","Vancouver","Ottawa","Montreal"],
2
],

[
"Which instrument normally has 88 keys?",
["Violin","Piano","Clarinet","Trumpet"],
1
],

[
"What is H2O?",
["Hydrogen peroxide","Water","Oxygen","Salt water"],
1
],

[
"Which continent contains the Sahara Desert?",
["Asia","Africa","South America","Australia"],
1
],

[
"What is the hardest natural mineral?",
["Quartz","Diamond","Topaz","Corundum"],
1
],

[
"Which sport uses a shuttlecock?",
["Squash","Badminton","Tennis","Table tennis"],
1
],

[
"What is the smallest prime number?",
["0","1","2","3"],
2
],

[
"Which organ pumps blood around the body?",
["Liver","Lung","Heart","Kidney"],
2
],

[
"Which language has the most native speakers?",
["English","Spanish","Mandarin Chinese","Hindi"],
2
],

[
"What is the name of our galaxy?",
["Andromeda","Milky Way","Whirlpool","Sombrero"],
1
],

[
"Which metal is liquid at room temperature?",
["Iron","Mercury","Copper","Aluminium"],
1
],

[
"How many players are on a soccer team on the field?",
["9","10","11","12"],
2
],

[
"Which planet is called the Red Planet?",
["Mars","Venus","Mercury","Jupiter"],
0
],

[
"What is the square root of 64?",
["6","7","8","9"],
2
],

[
"Which country is shaped like a boot?",
["Portugal","Italy","Chile","Croatia"],
1
],

[
"What is the largest planet?",
["Saturn","Neptune","Jupiter","Uranus"],
2
],

[
"Which animal is known for building dams?",
["Beaver","Otter","Badger","Fox"],
0
],

[
"What is the capital of New Zealand?",
["Auckland","Wellington","Christchurch","Dunedin"],
1
],

[
"Which famous ship sank in 1912?",
["Lusitania","Titanic","Endeavour","Mayflower"],
1
],

[
"What is the freezing point of water in Celsius?",
["0","10","32","-10"],
0
],

[
"Which country is home to Mount Fuji?",
["China","Japan","South Korea","Thailand"],
1
],

[
"Which animal is a marsupial?",
["Kangaroo","Wolf","Horse","Polar bear"],
0
],

[
"What is the largest continent?",
["Africa","Asia","Europe","North America"],
1
],

[
"Which sport uses wickets?",
["Baseball","Cricket","Hockey","Tennis"],
1
],

[
"What is the process where water vapour becomes liquid?",
["Evaporation","Condensation","Sublimation","Melting"],
1
],

[
"Which planet is Earth's approximate size twin?",
["Venus","Mars","Mercury","Neptune"],
0
],

[
"Which force pulls objects toward Earth?",
["Magnetism","Gravity","Friction","Pressure"],
1
],

[
"Which famous scientist developed relativity?",
["Newton","Einstein","Darwin","Galileo"],
1
],

[
"Which city is famous for the Eiffel Tower?",
["Rome","Paris","Madrid","Vienna"],
1
],

[
"How many minutes are in an hour?",
["30","45","60","90"],
2
],

[
"Which gas do plants absorb for photosynthesis?",
["Oxygen","Carbon dioxide","Nitrogen","Helium"],
1
],

[
"Which bird cannot fly and is native to New Zealand?",
["Kiwi","Eagle","Swan","Falcon"],
0
],

[
"Which dessert is associated with New Zealand and Australia?",
["Pavlova","Tiramisu","Baklava","Gelato"],
0
]

];


/* =========================================================
   GENERIC QUIZ ENGINE
========================================================= */

function runQuiz(
  questionBank,
  numberOfQuestions,
  pointsPerCorrect,
  finalQuiz=false
){

  const questions=
    shuffle(questionBank)
      .slice(0,numberOfQuestions);

  let questionIndex=0;
  let correctAnswers=0;

  $("#gameArea").innerHTML=`

    <div
      class="quiz-question"
      id="quizQuestion"
    ></div>

    <div
      class="choice-grid"
      id="quizChoices"
    ></div>

    <div
      class="feedback"
      id="quizFeedback"
    ></div>

    <div class="progress">
      <div
        class="progress-fill"
        id="quizProgress"
      ></div>
    </div>

  `;


  function showQuestion(){

    if(questionIndex>=questions.length){

      finishGame(
        correctAnswers*pointsPerCorrect,
        finalQuiz
        ?"THE FINAL CHALLENGE COMPLETE! 💗"
        :"Quiz complete!"
      );

      return;

    }


    const question=
      questions[questionIndex];

    const answers=
      question[1]
        .map(
          (answer,index)=>({
            answer,
            correct:
              index===question[2]
          })
        );


    const shuffledAnswers=
      shuffle(answers);


    $("#quizQuestion").innerHTML=`

      <div class="trivia-label">
        Question
        ${questionIndex+1}
        /
        ${questions.length}
      </div>

      <br>

      <b>
        ${question[0]}
      </b>

    `;


    const choices=
      $("#quizChoices");

    choices.innerHTML="";

    $("#quizFeedback")
      .textContent="";


    shuffledAnswers.forEach(option=>{

      const button=
        document.createElement("button");

      button.className="choice";

      button.textContent=
        option.answer;

      button.onclick=()=>{

        [
          ...choices.children
        ].forEach(
          b=>b.disabled=true
        );


        if(option.correct){

          correctAnswers++;

          button.classList.add("correct");

          $("#quizFeedback")
            .textContent=
            "✅ Correct!";

        }else{

          button.classList.add("wrong");

          $("#quizFeedback")
            .textContent=
            "❌ Not quite!";

        }


        questionIndex++;

        $("#quizProgress")
          .style.width=
          (
            questionIndex/
            questions.length*
            100
          )+"%";


        later(
          showQuestion,
          650
        );

      };


      choices.appendChild(button);

    });

  }


  showQuestion();

}


/* =========================================================
   GAME 3
   PRESSURE QUIZ
========================================================= */

function game3(){

  runQuiz(
    generalQuestions,
    12,
    20
  );

}


/* =========================================================
   GAME 4
   HIGH ROLLER
========================================================= */

function game4(){

  $("#gameArea").innerHTML=`

    <div class="slot-machine">

      <div class="reel" id="reel1">
        🍒
      </div>

      <div class="reel" id="reel2">
        ⭐
      </div>

      <div class="reel" id="reel3">
        💎
      </div>

    </div>

    <div class="center">

      <p>
        Pull the lever, then stop the reels.
      </p>

      <button id="slotPull">
        🎰 Pull Lever
      </button>

      <button
        id="slotStop"
        disabled
      >
        🛑 Stop Reels
      </button>

      <div
        class="feedback"
        id="slotFeedback"
      ></div>

    </div>

  `;


  const symbols=[
    "🍒",
    "🍋",
    "⭐",
    "💎",
    "7️⃣",
    "💗"
  ];

  let spinning=false;
  let values=[
    "🍒",
    "⭐",
    "💎"
  ];


  $("#slotPull").onclick=()=>{

    if(spinning)return;

    spinning=true;

    $("#slotStop")
      .disabled=false;

    let count=0;


    function spin(){

      if(!spinning)return;

      values=
        values.map(
          ()=>
            symbols[
              Math.floor(
                Math.random()*
                symbols.length
              )
            ]
        );


      $("#reel1").textContent=values[0];
      $("#reel2").textContent=values[1];
      $("#reel3").textContent=values[2];

      count++;

      if(count<40){

        animationFrame=
          requestAnimationFrame(spin);

      }

    }

    spin();

  };


  $("#slotStop").onclick=()=>{

    if(!spinning)return;

    spinning=false;

    const unique=
      new Set(values).size;

    let points;

    if(unique===1){

      if(values[0]==="7️⃣")
        points=600;

      else if(values[0]==="💎")
        points=350;

      else
        points=200;

      $("#slotFeedback")
        .textContent=
        "🎉 JACKPOT!";

    }else if(unique===2){

      points=80;

      $("#slotFeedback")
        .textContent=
        "Two symbols matched!";

    }else{

      points=20;

      $("#slotFeedback")
        .textContent=
        "Keep rolling!";

    }


    finishGame(
      points,
      "High Roller complete!"
    );

  };

}


/* =========================================================
   GAME 5
   MIND GAMES
========================================================= */

function game5(){

  const puzzles=[

    [
      "🔴 🔵 🔴 🔵 ?",
      ["🔴","🟢","🔵","🟡"],
      "🔴"
    ],

    [
      "2, 4, 8, 16, ?",
      ["24","30","32","36"],
      "32"
    ],

    [
      "▲ ■ ▲ ■ ?",
      ["■","▲","●","◆"],
      "▲"
    ],

    [
      "A, C, E, G, ?",
      ["H","I","J","K"],
      "I"
    ],

    [
      "1, 1, 2, 3, 5, ?",
      ["6","7","8","9"],
      "8"
    ],

    [
      "Which does not belong?",
      ["🍎","🍌","🍓","🚗"],
      "🚗"
    ],

    [
      "3, 6, 9, 12, ?",
      ["14","15","16","18"],
      "15"
    ]

  ];


  const selected=
    shuffle(puzzles).slice(0,5);

  let index=0;
  let points=0;


  $("#gameArea").innerHTML=`

    <div
      class="quiz-question"
      id="mindQuestion"
    ></div>

    <div
      class="choice-grid"
      id="mindChoices"
    ></div>

    <div
      class="feedback"
      id="mindFeedback"
    ></div>

  `;


  function show(){

    if(index>=selected.length){

      finishGame(
        points,
        "Mind Games solved!"
      );

      return;

    }


    const puzzle=
      selected[index];

    $("#mindQuestion").innerHTML=`

      <div class="trivia-label">
        Puzzle ${index+1}/${selected.length}
      </div>

      <br>

      <b>${puzzle[0]}</b>

    `;


    const choices=
      $("#mindChoices");

    choices.innerHTML="";

    shuffle(puzzle[1]).forEach(answer=>{

      const button=
        document.createElement("button");

      button.className="choice";

      button.textContent=answer;

      button.onclick=()=>{

        [
          ...choices.children
        ].forEach(
          b=>b.disabled=true
        );


        if(answer===puzzle[2]){

          points+=55;

          addPoints(55);

          $("#mindFeedback")
            .textContent=
            "🧠 Correct!";

        }else{

          $("#mindFeedback")
            .textContent=
            "Not quite.";

        }


        index++;

        later(show,550);

      };

      choices.appendChild(button);

    });

  }


  show();

}


/* =========================================================
   GAME 6
   THE BLUFF
========================================================= */

function game6(){

  let pot=100;
  let round=0;

  $("#gameArea").innerHTML=`

    <div class="center">

      <div class="score-big" id="bluffPot">
        100
      </div>

      <p>
        Choose a hidden card.
        Red doubles the pot.
        Black halves it.
      </p>

      <div
        class="card-row"
        id="bluffCards"
      ></div>

      <button id="bluffCash">
        💰 Cash Out
      </button>

      <div
        class="feedback"
        id="bluffFeedback"
      ></div>

    </div>

  `;


  function drawCards(){

    const container=
      $("#bluffCards");

    container.innerHTML="";


    for(let i=0;i<3;i++){

      const button=
        document.createElement("button");

      button.className="card";

      button.textContent="🂠";

      button.onclick=()=>{

        const red=
          Math.random()>.5;

        button.textContent=
          red?"♥️":"♣️";

        round++;


        if(red){

          pot*=2;

          $("#bluffFeedback")
            .textContent=
            "❤️ Red! The pot doubled.";

        }else{

          pot=
            Math.floor(pot/2);

          $("#bluffFeedback")
            .textContent=
            "♣️ Black! The pot was halved.";

        }


        $("#bluffPot")
          .textContent=pot;


        if(pot<=10){

          finishGame(
            pot,
            "The Bluff got risky!"
          );

          return;

        }


        if(round>=7){

          finishGame(
            pot,
            "You survived The Bluff!"
          );

          return;

        }


        later(
          drawCards,
          500
        );

      };


      container.appendChild(button);

    }

  }


  $("#bluffCash").onclick=()=>{

    finishGame(
      pot,
      "You cashed out!"
    );

  };


  drawCards();

}


/* =========================================================
   GAME 7
   SURVIVAL ROUND
========================================================= */

function game7(){

  const waves=[

    [
      "A storm approaches.",
      [
        "Take proper shelter",
        "Run into the open",
        "Stand under a tree",
        "Ignore it"
      ],
      0
    ],

    [
      "A fire blocks the path.",
      [
        "Use the clear exit",
        "Walk through flames",
        "Hide in smoke",
        "Sprint blindly"
      ],
      0
    ],

    [
      "A bridge looks unstable.",
      [
        "Cross at a safe point",
        "Jump on the rail",
        "Run without looking",
        "Shake the bridge"
      ],
      0
    ],

    [
      "A dangerous wave approaches.",
      [
        "Move to higher ground",
        "Stand at the waterline",
        "Swim toward rocks",
        "Lie in the surf"
      ],
      0
    ],

    [
      "Debris is falling from above.",
      [
        "Wait for a safe gap",
        "Run directly beneath it",
        "Climb underneath it",
        "Stand directly below it"
      ],
      0
    ],

    [
      "You hear an alarm in an unfamiliar building.",
      [
        "Follow marked emergency signs",
        "Hide in a cupboard",
        "Ignore it",
        "Run toward the alarm"
      ],
      0
    ]

  ];


  let wave=0;
  let health=100;


  $("#gameArea").innerHTML=`

    <div class="center">

      <div class="score-big">
        ❤️
        <span id="survivalHealth">
          100
        </span>
      </div>

      <h3 id="survivalWave">
        Wave 1
      </h3>

      <p>
        Make the safest decision.
      </p>

      <div
        class="choice-grid"
        id="survivalChoices"
      ></div>

      <div
        class="feedback"
        id="survivalFeedback"
      ></div>

    </div>

  `;


  function nextWave(){

    if(wave>=waves.length){

      finishGame(
        350,
        "You survived every wave!"
      );

      return;

    }


    const data=waves[wave];

    $("#survivalWave")
      .textContent=
      `Wave ${wave+1}: ${data[0]}`;


    const choices=
      $("#survivalChoices");

    choices.innerHTML="";


    shuffle(
      data[1].map(
        (answer,index)=>({
          answer,
          correct:index===data[2]
        })
      )
    ).forEach(option=>{

      const button=
        document.createElement("button");

      button.className="choice";

      button.textContent=
        option.answer;

      button.onclick=()=>{

        [
          ...choices.children
        ].forEach(
          b=>b.disabled=true
        );


        if(option.correct){

          health+=5;

          addPoints(35);

          $("#survivalFeedback")
            .textContent=
            "🛡️ Good decision!";

        }else{

          health-=25;

          $("#survivalFeedback")
            .textContent=
            "⚠️ That choice cost health.";

        }


        health=
          Math.max(0,health);

        $("#survivalHealth")
          .textContent=health;


        if(health<=0){

          finishGame(
            25,
            "The Survival Round is over."
          );

          return;

        }


        wave++;

        later(
          nextWave,
          500
        );

      };

      choices.appendChild(button);

    });

  }


  nextWave();

}


/* =========================================================
   GAME 8
   ADMIRER RACE
========================================================= */

function game8(){

  $("#gameArea").innerHTML=`

    <p>
      Guide your admirer to the finish.
      Avoid the obstacles.
    </p>

    <div
      class="arena"
      id="admirerArena"
    >

      <div
        class="player"
        id="admirerPlayer"
        style="
          position:absolute;
          left:5%;
          top:45%;
          font-size:35px;
        "
      >
        🏃‍♀️
      </div>

      <div
        style="
          position:absolute;
          right:8px;
          bottom:8px;
          font-size:30px;
        "
      >
        🏁
      </div>

    </div>

    <div
      class="actions"
      style="justify-content:center"
    >

      <button data-race="up">⬆️</button>
      <button data-race="left">⬅️</button>
      <button data-race="down">⬇️</button>
      <button data-race="right">➡️</button>

    </div>

    <div
      class="feedback"
      id="raceFeedback"
    >
      Reach the finish!
    </div>

  `;


  const arena=
    $("#admirerArena");

  const player=
    $("#admirerPlayer");

  let x=5;
  let y=45;


  const obstacles=[];


  for(let i=0;i<10;i++){

    const obstacle=
      document.createElement("div");

    obstacle.className=
      "obstacle";

    obstacle.style.width="35px";

    obstacle.style.height="45px";

    obstacle.style.left=
      (15+i*7+Math.random()*4)+"%";

    obstacle.style.top=
      (8+Math.random()*80)+"%";

    arena.appendChild(obstacle);

    obstacles.push(obstacle);

  }


  function move(dx,dy){

    x=
      Math.max(
        2,
        Math.min(94,x+dx)
      );

    y=
      Math.max(
        2,
        Math.min(90,y+dy)
      );


    player.style.left=x+"%";
    player.style.top=y+"%";


    const playerRect=
      player.getBoundingClientRect();


    for(const obstacle of obstacles){

      const rect=
        obstacle.getBoundingClientRect();

      if(
        playerRect.left<rect.right &&
        playerRect.right>rect.left &&
        playerRect.top<rect.bottom &&
        playerRect.bottom>rect.top
      ){

        x=5;
        y=45;

        player.style.left=x+"%";
        player.style.top=y+"%";

        $("#raceFeedback")
          .textContent=
          "💥 Obstacle! Back to the start.";

        return;

      }

    }


    if(x>=88){

      finishGame(
        250,
        "You reached the finish!"
      );

    }

  }


  document
    .querySelectorAll("[data-race]")
    .forEach(button=>{

      button.onclick=()=>{

        const direction=
          button.dataset.race;

        if(direction==="up")
          move(0,-5);

        if(direction==="down")
          move(0,5);

        if(direction==="left")
          move(-5,0);

        if(direction==="right")
          move(5,0);

      };

    });


  document.onkeydown=event=>{

    if(currentGame!==7)return;

    if(event.key==="ArrowUp")
      move(0,-5);

    if(event.key==="ArrowDown")
      move(0,5);

    if(event.key==="ArrowLeft")
      move(-5,0);

    if(event.key==="ArrowRight")
      move(5,0);

  };

}


/* =========================================================
   GAME 9
   HEARTBREAK CHAMBER
========================================================= */

function game9(){

  $("#gameArea").innerHTML=`

    <p>
      Search the chamber and discover all five clues.
      Each clue reveals another part of the escape.
    </p>

    <div
      class="arena"
      id="chamber"
    >

      <button
        class="target"
        style="left:10%;top:20%"
      >
        🪟
      </button>

      <button
        class="target"
        style="left:70%;top:18%"
      >
        🖼️
      </button>

      <button
        class="target"
        style="left:43%;top:60%"
      >
        🪴
      </button>

      <button
        class="target"
        style="left:82%;top:72%"
      >
        📦
      </button>

      <button
        class="target"
        style="left:18%;top:72%"
      >
        🕯️
      </button>

      <button
        class="target"
        style="left:52%;top:20%"
      >
        🔎
      </button>

    </div>

    <div
      class="feedback"
      id="chamberFeedback"
    >
      Clues found: 0/5
    </div>

    <div id="clueList"></div>

  `;


  const clues=[

    "A blue petal is beside the window.",

    "A number is carved into the picture frame.",

    "The painting faces the locked door.",

    "The plant hides a small metal key.",

    "The key belongs to the door."

  ];


  let found=0;


  document
    .querySelectorAll("#chamber .target")
    .forEach(button=>{

      button.onclick=()=>{

        if(button.disabled)return;

        button.disabled=true;

        button.style.opacity=".25";

        if(found<5){

          $("#clueList")
            .insertAdjacentHTML(
              "beforeend",
              `<p>
                🔐 Clue ${found+1}:
                ${clues[found]}
              </p>`
            );

          found++;

        }


        $("#chamberFeedback")
          .textContent=
          `Clues found: ${found}/5`;


        if(found>=5){

          finishGame(
            260,
            "You escaped the Heartbreak Chamber!"
          );

        }

      };

    });

}


/* =========================================================
   GAME 10
   HEARTBREAK BOXING
========================================================= */

function game10(){

  let playerHealth=100;
  let enemyHealth=100;
  let blocking=false;


  $("#gameArea").innerHTML=`

    <div class="center">

      <h3>
        🥊 Heartbreak Boxing
      </h3>

      <p>
        You ❤️
        <b id="playerHealth">100</b>
        &nbsp;&nbsp;
        Opponent 💔
        <b id="enemyHealth">100</b>
      </p>

      <div
        class="actions"
        style="justify-content:center"
      >

        <button id="punch">
          🥊 Punch
        </button>

        <button id="block">
          🛡️ Block
        </button>

        <button id="dodge">
          💨 Dodge
        </button>

        <button id="charge">
          ⚡ Charge
        </button>

        <button id="counter">
          🔥 Counter
        </button>

      </div>

      <div
        class="feedback"
        id="boxingFeedback"
      ></div>

    </div>

  `;


  function enemyTurn(){

    if(enemyHealth<=0){

      finishGame(
        300,
        "You won the Heartbreak Boxing Match!"
      );

      return;

    }


    let damage=
      8+
      Math.floor(
        Math.random()*16
      );


    if(blocking){

      damage=
        Math.floor(damage/2);

      blocking=false;

      $("#boxingFeedback")
        .textContent=
        "🛡️ Your block reduced the hit.";

    }


    playerHealth-=damage;

    $("#playerHealth")
      .textContent=
      Math.max(
        0,
        playerHealth
      );


    if(playerHealth<=0){

      finishGame(
        20,
        "The boxing match is over."
      );

    }

  }


  $("#punch").onclick=()=>{

    enemyHealth-=15;

    $("#enemyHealth")
      .textContent=
      Math.max(0,enemyHealth);

    enemyTurn();

  };


  $("#block").onclick=()=>{

    blocking=true;

    $("#boxingFeedback")
      .textContent=
      "🛡️ Guard ready.";

    enemyTurn();

  };


  $("#dodge").onclick=()=>{

    if(Math.random()>.35){

      $("#boxingFeedback")
        .textContent=
        "💨 Perfect dodge!";

    }else{

      enemyTurn();

    }

  };


  $("#charge").onclick=()=>{

    if(Math.random()>.25){

      enemyHealth-=30;

      $("#enemyHealth")
        .textContent=
        Math.max(0,enemyHealth);

      $("#boxingFeedback")
        .textContent=
        "⚡ Charged hit!";

      enemyTurn();

    }else{

      playerHealth-=12;

      $("#playerHealth")
        .textContent=
        Math.max(0,playerHealth);

      $("#boxingFeedback")
        .textContent=
        "⚡ The charge backfired.";

      enemyTurn();

    }

  };


  $("#counter").onclick=()=>{

    if(Math.random()>.45){

      enemyHealth-=25;

      $("#enemyHealth")
        .textContent=
        Math.max(0,enemyHealth);

      $("#boxingFeedback")
        .textContent=
        "🔥 Counter landed!";

      enemyTurn();

    }else{

      enemyTurn();

    }

  };

}


/* =========================================================
   GAME 11
   PERFECT MATCH
========================================================= */

function game11(){

  const pairs=[

    ["🌻",0],
    ["🐬",1],
    ["🌹",2],
    ["🎵",3],
    ["🍣",4],
    ["💗",5]

  ];


  let selected=null;
  let matched=new Set();


  $("#gameArea").innerHTML=`

    <p>
      Click two objects to reveal whether
      they belong together.
    </p>

    <div
      class="card-row"
      id="matchCards"
    ></div>

    <div
      class="feedback"
      id="matchFeedback"
    ></div>

  `;


  const all=
    shuffle(
      pairs.flatMap(
        pair=>[
          {
            symbol:pair[0],
            id:pair[1]
          },
          {
            symbol:pair[0],
            id:pair[1]
          }
        ]
      )
    );


  const container=
    $("#matchCards");


  all.forEach((item,index)=>{

    const button=
      document.createElement("button");

    button.className="card";

    button.textContent="❓";

    button.dataset.id=item.id;

    button.dataset.index=index;

    button.onclick=()=>{

      if(
        button.disabled ||
        matched.has(item.id)
      )return;


      if(!selected){

        selected={
          button,
          item
        };

        button.textContent=
          item.symbol;

        return;

      }


      button.textContent=
        item.symbol;


      if(
        selected.item.id===
        item.id &&
        selected.button!==button
      ){

        matched.add(item.id);

        selected.button.disabled=true;

        button.disabled=true;

        addPoints(35);

        $("#matchFeedback")
          .textContent=
          "🧲 Perfect match!";

        selected=null;


        if(matched.size===pairs.length){

          finishGame(
            200,
            "Every match is perfect!"
          );

        }

      }else{

        $("#matchFeedback")
          .textContent=
          "Those two don't match.";

        const first=selected.button;

        selected=null;

        later(()=>{

          if(!first.disabled)
            first.textContent="❓";

          if(!button.disabled)
            button.textContent="❓";

        },500);

      }

    };


    container.appendChild(button);

  });

}


/* =========================================================
   LILIANA FACTS
========================================================= */

const lilianaQuestions=[

[
"What is Liliana's favourite colour?",
["Baby pink","Burgundy","Lavender","Sky blue"],
0
],

[
"What is Liliana's favourite number?",
["3","7","13","27"],
0
],

[
"Which food does Liliana love?",
["Sushi","Pizza","Pasta","Tacos"],
0
],

[
"Which sea animal does Liliana like?",
["Dolphins","Seals","Whales","Turtles"],
0
],

[
"Which flowers does Liliana like?",
["Sunflowers and roses","Lilies and tulips","Orchids and daisies","Peonies and violets"],
0
],

[
"When is Liliana's birthday?",
["22 July","22 June","12 July","27 July"],
0
],

[
"What colour are Liliana's eyes?",
["Green","Blue","Brown","Hazel"],
0
],

[
"What is Liliana's zodiac sign?",
["Leo","Cancer","Virgo","Gemini"],
0
],

[
"Which movie is a favourite of Liliana's?",
["Me Before You","The Notebook","Titanic","La La Land"],
0
],

[
"What kind of songs does Liliana enjoy?",
["Sad songs","Only dance songs","Only rock songs","Only classical songs"],
0
],

[
"What type of writing does Liliana like?",
["Poetry","Only biographies","Only textbooks","Only comics"],
0
],

[
"What did Liliana study at university?",
["Psychology","Law","Architecture","Engineering"],
0
],

[
"How many nieces does Liliana have?",
["1","2","3","4"],
0
],

[
"How many nephews does Liliana have?",
["4","2","5","6"],
0
],

[
"How many siblings does Liliana have?",
["5","3","4","6"],
0
],

[
"What are Liliana's dogs called?",
["Aayla and Arlo","Luna and Milo","Bella and Coco","Nala and Leo"],
0
],

[
"How many dogs does Liliana have?",
["2","1","3","4"],
0
],

[
"How many piercings does Liliana have?",
["4","2","3","5"],
0
],

[
"What is Liliana afraid of?",
["Drowning","Flying","Heights","Spiders"],
0
],

[
"What type of games does Liliana enjoy?",
["Poker and gambling games","Only word games","Only racing games","Only puzzle games"],
0
],

[
"What does Liliana hope to be someday?",
["A mum to a baby girl","A pilot","A professional athlete","A chef"],
0
],

[
"How long have Bree and Liliana been best friends?",
["6 years","4 years","5 years","7 years"],
0
],

[
"Which flower is one of Liliana's favourites?",
["Sunflower","Carnation","Iris","Daffodil"],
0
],

[
"Which other flower is one of Liliana's favourites?",
["Rose","Hydrangea","Gerbera","Magnolia"],
0
],

[
"Which colour is specifically Liliana's favourite?",
["Baby pink","Deep red","Emerald","Navy"],
0
],

[
"Which number is Liliana's favourite?",
["Three","Six","Nine","Twelve"],
0
],

[
"What day of the month is Liliana's birthday?",
["22","12","17","27"],
0
],

[
"Which month is Liliana's birthday in?",
["July","May","August","October"],
0
],

[
"Which of these is one of Liliana's dogs?",
["Aayla","Mabel","Ruby","Poppy"],
0
],

[
"Which of these is Liliana's other dog?",
["Arlo","Oscar","Teddy","Bailey"],
0
],

[
"Which university subject is associated with Liliana?",
["Psychology","Medicine","Physics","Accounting"],
0
],

[
"Which genre does Liliana like?",
["Poetry","Biography","History","Journalism"],
0
],

[
"Which film title belongs among Liliana's favourites?",
["Me Before You","About Time","The Holiday","Wonder"],
0
],

[
"Which activity matches one of Liliana's interests?",
["Poker","Golf","Surfing","Skiing"],
0
],

[
"Which sea creature appears among Liliana's likes?",
["Dolphin","Jellyfish","Seahorse","Stingray"],
0
],

[
"Which statement about Liliana's favourite colour is accurate?",
["It is a soft shade of pink","It is a dark green","It is bright orange","It is metallic silver"],
0
],

[
"Which combination contains only Liliana-related favourites?",
["Sushi, dolphins and sunflowers","Pizza, whales and orchids","Pasta, seals and tulips","Tacos, turtles and violets"],
0
],

[
"Which pair are both Liliana's dogs?",
["Aayla and Arlo","Aayla and Luna","Arlo and Milo","Bella and Arlo"],
0
],

[
"Which pair describes two of Liliana's interests?",
["Poetry and sad songs","Chess and opera","Hiking and pottery","Fishing and astronomy"],
0
],

[
"Which combination matches Liliana's birthday information?",
["22 July and Leo","12 July and Cancer","22 August and Virgo","27 July and Gemini"],
0
],

[
"Which family detail belongs to Liliana?",
["One niece and four nephews","Two nieces and two nephews","Three nieces and one nephew","Four nieces and no nephews"],
0
],

[
"Which number combination matches two Liliana facts?",
["Favourite number 3 and 5 siblings","Favourite number 7 and 3 siblings","Favourite number 13 and 4 siblings","Favourite number 27 and 6 siblings"],
0
],

[
"Which combination contains Liliana's favourite colour and food?",
["Baby pink and sushi","Burgundy and pasta","Lavender and pizza","Sky blue and tacos"],
0
],

[
"Which combination contains a favourite flower and animal?",
["Rose and dolphin","Tulip and seal","Daisy and whale","Lily and turtle"],
0
],

[
"Which combination contains a film and hobby Liliana likes?",
["Me Before You and poker","Titanic and golf","The Notebook and fishing","La La Land and chess"],
0
],

[
"Which statement combines two Liliana interests?",
["She likes poetry and sad songs","She dislikes all music","She only likes comedy films","She avoids games"],
0
],

[
"Which combination contains her study area and pastime?",
["Psychology and poker","Engineering and cricket","Law and golf","Physics and chess"],
0
],

[
"Which combination contains her favourite number and birthday month?",
["3 and July","7 and June","13 and August","27 and October"],
0
],

[
"Which combination contains her eye colour and zodiac sign?",
["Green and Leo","Blue and Cancer","Brown and Virgo","Hazel and Gemini"],
0
]

];


/* =========================================================
   GAME 12
   WHO KNOWS LILIANA BEST
========================================================= */

function game12(){

  runQuiz(
    lilianaQuestions,
    15,
    30
  );

}


/* =========================================================
   GAME 13
   REACTION GAUNTLET
========================================================= */

function game13(){

  const commands=[

    {
      type:"tap",
      symbol:"💗",
      instruction:"TAP 💗"
    },

    {
      type:"hold",
      symbol:"⭐",
      instruction:"HOLD ⭐"
    },

    {
      type:"left",
      symbol:"⬅️",
      instruction:"SWIPE LEFT"
    },

    {
      type:"right",
      symbol:"➡️",
      instruction:"SWIPE RIGHT"
    },

    {
      type:"tap",
      symbol:"🌻",
      instruction:"TAP 🌻"
    },

    {
      type:"hold",
      symbol:"🐬",
      instruction:"HOLD 🐬"
    },

    {
      type:"left",
      symbol:"⬅️",
      instruction:"SWIPE LEFT"
    },

    {
      type:"right",
      symbol:"➡️",
      instruction:"SWIPE RIGHT"
    }

  ];


  let index=0;
  let lives=3;
  let holding=false;
  let completed=false;


  $("#gameArea").innerHTML=`

    <div class="center">

      <div
        class="big-emoji"
        id="reactionCommand"
      >
        READY?
      </div>

      <p>
        Follow the command exactly.
      </p>

      <button id="reactionButton">
        START
      </button>

      <div
        class="feedback"
        id="reactionFeedback"
      >
        Lives: 3
      </div>

    </div>

  `;


  const button=
    $("#reactionButton");


  function next(){

    if(index>=commands.length){

      finishGame(
        320,
        "Reaction Gauntlet cleared!"
      );

      return;

    }


    const command=
      commands[index];

    let active=true;
    let start=performance.now();


    $("#reactionCommand")
      .textContent=
      command.instruction;

    button.textContent=
      command.type==="hold"
      ?"HOLD"
      :
      command.type==="tap"
      ?"TAP"
      :"SWIPE";


    function timeoutCheck(time){

      if(!active)return;

      if(
        time-start>1400
      ){

        active=false;

        lives--;

        $("#reactionFeedback")
          .textContent=
          `Too slow! Lives: ${lives}`;

        if(lives<=0){

          finishGame(
            25,
            "Reaction Gauntlet over."
          );

        }else{

          index++;

          later(
            next,
            350
          );

        }

        return;

      }


      animationFrame=
        requestAnimationFrame(
          timeoutCheck
        );

    }


    animationFrame=
      requestAnimationFrame(
        timeoutCheck
      );


    function action(event){

      if(!active)return;

      const elapsed=
        performance.now()-start;

      if(elapsed>1400)return;


      let correct=false;


      if(command.type==="tap"){

        correct=
          event.type==="click" &&
          !holding;

      }


      if(command.type==="hold"){

        correct=
          holding;

      }


      if(
        command.type==="left" ||
        command.type==="right"
      ){

        correct=
          event.key===(
            command.type==="left"
            ?"ArrowLeft"
            :"ArrowRight"
          );

      }


      if(correct){

        active=false;

        addPoints(40);

        $("#reactionFeedback")
          .textContent=
          "⚡ Perfect reaction!";

        index++;

        later(
          next,
          250
        );

      }

    }


    button.onclick=
      event=>{
        action(event);
      };


    button.onpointerdown=()=>{

      holding=true;

      if(command.type==="hold")
        action({type:"hold"});

    };


    button.onpointerup=()=>{

      holding=false;

    };


    document.onkeydown=
      event=>{

        if(
          command.type==="left" ||
          command.type==="right"
        ){

          action(event);

        }

      };

  }


  button.onclick=()=>{

    if(index===0){

      index=0;
      lives=3;
      next();

    }

  };

}


/* =========================================================
   GAME 14
   HEART HUNT
========================================================= */

function game14(){

  $("#gameArea").innerHTML=`

    <p>
      Some hearts are hiding among ordinary objects.
      Find all 10!
    </p>

    <div
      class="arena"
      id="heartHunt"
    ></div>

    <div
      class="feedback"
      id="huntFeedback"
    >
      💗 Hearts found: 0/10
    </div>

  `;


  const arena=
    $("#heartHunt");

  let found=0;


  const objects=[
    "🌸",
    "🌿",
    "⭐",
    "🪨",
    "🌹",
    "🦋",
    "🍃",
    "🌙",
    "✨",
    "🌷",
    "🍀",
    "☁️",
    "🌱",
    "🎀",
    "🪻",
    "🌺",
    "🍂",
    "🌼",
    "🪽",
    "🌴"
  ];


  for(let i=0;i<40;i++){

    const button=
      document.createElement("button");

    button.className="target";

    button.textContent=
      objects[
        Math.floor(
          Math.random()*objects.length
        )
      ];

    button.style.left=
      Math.random()*93+"%";

    button.style.top=
      Math.random()*88+"%";


    const hiddenHeart=
      found<10 &&
      i<22 &&
      Math.random()<.45;


    if(hiddenHeart){

      button.dataset.heart="true";

    }


    button.onclick=()=>{

      if(button.disabled)return;

      button.disabled=true;

      if(
        button.dataset.heart==="true"
      ){

        button.textContent="💗";

        found++;

        addPoints(20);

        $("#huntFeedback")
          .textContent=
          `💗 Hearts found: ${found}/10`;


        if(found>=10){

          finishGame(
            250,
            "Every hidden heart was found!"
          );

        }

      }else{

        button.style.opacity=".2";

        $("#huntFeedback")
          .textContent=
          `Not a heart! ${found}/10 found.`;

      }

    };


    arena.appendChild(button);

  }

}


/* =========================================================
   GAME 15
   LOVE LOCK
========================================================= */

function game15(){

  let code="";

  while(code.length<4){

    const digit=
      String(
        Math.floor(
          Math.random()*10
        )
      );

    if(!code.includes(digit))
      code+=digit;

  }


  let guess="";


  $("#gameArea").innerHTML=`

    <div class="center">

      <p>
        Crack the four-digit lock.
        Every digit is different.
      </p>

      <div class="reward">

        <p>
          🔐 The first digit is
          <b>
            ${
              Number(code[0])%2===0
              ?"even"
              :"odd"
            }
          </b>.
        </p>

        <p>
          🔐
          ${
            code.includes("5")
            ?"The code contains a 5."
            :"The code does not contain a 5."
          }
        </p>

      </div>

      <h2 id="lockDisplay">
        ••••
      </h2>

      <div
        class="lock-grid"
        id="lockGrid"
      ></div>

      <div
        class="feedback"
        id="lockFeedback"
      >
        Enter a four-digit code.
      </div>

    </div>

  `;


  const display=
    $("#lockDisplay");


  function updateDisplay(){

    display.textContent=
      guess.padEnd(4,"•");

  }


  function pressDigit(digit){

    if(
      guess.length<4 &&
      !guess.includes(digit)
    ){

      guess+=digit;

      updateDisplay();

    }

  }


  function check(){

    if(guess.length!==4){

      $("#lockFeedback")
        .textContent=
        "You need four different digits.";

      return;

    }


    let exact=0;
    let misplaced=0;


    for(let i=0;i<4;i++){

      if(
        guess[i]===code[i]
      ){

        exact++;

      }else if(
        code.includes(guess[i])
      ){

        misplaced++;

      }

    }


    $("#lockFeedback")
      .textContent=
      `Exact: ${exact} • `+
      `Right digit, wrong place: ${misplaced}`;


    if(guess===code){

      finishGame(
        300,
        "Love Lock opened! 🔐💗"
      );

    }else{

      guess="";

      updateDisplay();

    }

  }


  const grid=
    $("#lockGrid");


  for(let i=1;i<=9;i++){

    const button=
      document.createElement("button");

    button.textContent=i;

    button.onclick=
      ()=>pressDigit(String(i));

    grid.appendChild(button);

  }


  const zero=
    document.createElement("button");

  zero.textContent="0";

  zero.onclick=
    ()=>pressDigit("0");

  grid.appendChild(zero);


  const deleteButton=
    document.createElement("button");

  deleteButton.textContent="⌫";

  deleteButton.onclick=()=>{

    guess=
      guess.slice(0,-1);

    updateDisplay();

  };

  grid.appendChild(deleteButton);


  const enter=
    document.createElement("button");

  enter.textContent="✓";

  enter.onclick=check;

  grid.appendChild(enter);

}


/* =========================================================
   GAME 16
   CUPID SHOOTOUT
========================================================= */

function game16(){

  $("#gameArea").innerHTML=`

    <p>
      Move Cupid's crosshair close to the target
      and fire.
    </p>

    <div
      class="arena"
      id="shootArena"
    >

      <div
        id="crosshair"
        style="
          position:absolute;
          left:8%;
          top:10%;
          font-size:34px;
        "
      >
        ✚
      </div>

      <div
        id="shootTarget"
        style="
          position:absolute;
          font-size:34px;
        "
      >
        🎯
      </div>

    </div>

    <div
      class="actions"
      style="justify-content:center"
    >

      <button id="shootUp">⬆️</button>
      <button id="shootLeft">⬅️</button>
      <button id="shootDown">⬇️</button>
      <button id="shootRight">➡️</button>

      <button id="fireCupid">
        🏹 FIRE
      </button>

    </div>

    <div
      class="feedback"
      id="shootFeedback"
    >
      Hits: 0/8
    </div>

  `;


  let x=8;
  let y=10;
  let hits=0;


  const crosshair=
    $("#crosshair");

  const target=
    $("#shootTarget");


  function placeTarget(){

    target.style.left=
      (10+Math.random()*82)+"%";

    target.style.top=
      (8+Math.random()*80)+"%";

  }


  function move(dx,dy){

    x=
      Math.max(
        2,
        Math.min(94,x+dx)
      );

    y=
      Math.max(
        2,
        Math.min(90,y+dy)
      );

    crosshair.style.left=x+"%";
    crosshair.style.top=y+"%";

  }


  $("#shootUp").onclick=
    ()=>move(0,-5);

  $("#shootDown").onclick=
    ()=>move(0,5);

  $("#shootLeft").onclick=
    ()=>move(-5,0);

  $("#shootRight").onclick=
    ()=>move(5,0);


  document.onkeydown=event=>{

    if(currentGame!==15)return;

    if(event.key==="ArrowUp")
      move(0,-5);

    if(event.key==="ArrowDown")
      move(0,5);

    if(event.key==="ArrowLeft")
      move(-5,0);

    if(event.key==="ArrowRight")
      move(5,0);

  };


  $("#fireCupid").onclick=()=>{

    const c=
      crosshair.getBoundingClientRect();

    const t=
      target.getBoundingClientRect();


    const distance=
      Math.hypot(
        c.left-t.left,
        c.top-t.top
      );


    if(distance<75){

      hits++;

      addPoints(30);

      $("#shootFeedback")
        .textContent=
        `🎯 Hit! ${hits}/8`;

      placeTarget();


      if(hits>=8){

        finishGame(
          250,
          "Cupid hit every target!"
        );

      }

    }else{

      $("#shootFeedback")
        .textContent=
        "🏹 Miss! Move closer.";

    }

  };


  placeTarget();

}


/* =========================================================
   GAME 17
   THE COUNTDOWN
========================================================= */

function game17(){

  let round=0;
  let total=0;


  $("#gameArea").innerHTML=`

    <div class="center">

      <h3 id="countdownTitle">
        Mini-game 1
      </h3>

      <div id="countdownMini"></div>

      <div
        class="feedback"
        id="countdownFeedback"
      ></div>

    </div>

  `;


  function nextMini(){

    if(round>=6){

      finishGame(
        total,
        "The Countdown is complete!"
      );

      return;

    }


    $("#countdownTitle")
      .textContent=
      `Mini-game ${round+1}/6`;


    const container=
      $("#countdownMini");

    container.innerHTML="";


    const type=round%3;


    /* Stop bar */

    if(type===0){

      container.innerHTML=`

        <p>
          Stop the moving bar inside the centre zone.
        </p>

        <div class="mini-bar">

          <div
            class="mini-bar-fill"
            id="movingBar"
          ></div>

        </div>

        <button id="stopMovingBar">
          🛑 STOP
        </button>

      `;


      let position=0;
      let direction=1;


      function moveBar(){

        position+=
          direction*2.5;

        if(
          position>=100 ||
          position<=0
        ){

          direction*=-1;

        }


        $("#movingBar")
          .style.width=
          position+"%";


        animationFrame=
          requestAnimationFrame(
            moveBar
          );

      }


      moveBar();


      $("#stopMovingBar")
        .onclick=()=>{

          cancelAnimationFrame(
            animationFrame
          );

          if(
            position>=35 &&
            position<=65
          ){

            total+=60;

            addPoints(60);

            $("#countdownFeedback")
              .textContent=
              "🎯 Perfect timing!";

          }else{

            $("#countdownFeedback")
              .textContent=
              "Close!";

          }


          round++;

          later(
            nextMini,
            450
          );

        };

    }


    /* Pattern */

    else if(type===1){

      const pattern=
        shuffle([
          "A","B","C","D"
        ]).slice(0,3);

      container.innerHTML=`

        <p>
          Remember this sequence:
        </p>

        <h2>
          ${pattern.join(" • ")}
        </h2>

        <div
          id="patternButtons"
          class="actions"
          style="justify-content:center"
        ></div>

      `;


      later(()=>{

        container.querySelector("h2")
          .textContent=
          "Repeat it!";


        const buttons=
          $("#patternButtons");

        let input=[];


        ["A","B","C","D"]
          .forEach(letter=>{

            const button=
              document.createElement("button");

            button.textContent=letter;

            button.onclick=()=>{

              input.push(letter);

              if(
                input[
                  input.length-1
                ] !==
                pattern[
                  input.length-1
                ]
              ){

                $("#countdownFeedback")
                  .textContent=
                  "❌ Wrong pattern.";

                round++;

                later(
                  nextMini,
                  400
                );

                return;

              }


              if(
                input.length===
                pattern.length
              ){

                total+=60;

                addPoints(60);

                $("#countdownFeedback")
                  .textContent=
                  "🧠 Perfect memory!";

                round++;

                later(
                  nextMini,
                  400
                );

              }

            };

            buttons.appendChild(button);

          });

      },1000);

    }


    /* Exact taps */

    else{

      const targetNumber=
        Math.floor(
          Math.random()*7
        )+4;


      container.innerHTML=`

        <p>
          Tap exactly
          <b>${targetNumber}</b>
          times.
        </p>

        <button id="countTap">
          💗 TAP
        </button>

        <span id="tapCount">
          0
        </span>

      `;


      let count=0;


      $("#countTap").onclick=()=>{

        count++;

        $("#tapCount")
          .textContent=count;


        if(count===targetNumber){

          total+=60;

          addPoints(60);

          $("#countdownFeedback")
            .textContent=
            "💗 Perfect!";

          round++;

          later(
            nextMini,
            350
          );

        }else if(
          count>targetNumber
        ){

          $("#countdownFeedback")
            .textContent=
            "Too many!";

          round++;

          later(
            nextMini,
            350
          );

        }

      };

    }

  }


  nextMini();

}


/* =========================================================
   GAME 18
   ULTIMATE GAMBLE
========================================================= */

function game18(){

  let pot=100;
  let turns=0;


  $("#gameArea").innerHTML=`

    <div class="center">

      <div
        class="score-big"
        id="gamblePot"
      >
        100
      </div>

      <p>
        The original Ultimate Gamble.
        Start with <b>100</b>.
        Risk the pot or cash out.
      </p>

      <button id="gambleRisk">
        🎲 Risk It
      </button>

      <button id="gambleCash">
        💰 Cash Out
      </button>

      <div
        class="feedback"
        id="gambleFeedback"
      ></div>

    </div>

  `;


  $("#gambleRisk").onclick=()=>{

    turns++;

    const roll=Math.random();

    if(roll<.22){

      pot=0;

      $("#gamblePot")
        .textContent=0;

      finishGame(
        0,
        "The Ultimate Gamble took the pot."
      );

      return;

    }


    let multiplier;

    if(roll>.86)
      multiplier=3;
    else if(roll>.58)
      multiplier=2;
    else
      multiplier=1.25;


    pot=
      Math.floor(
        pot*multiplier
      );


    $("#gamblePot")
      .textContent=pot;


    $("#gambleFeedback")
      .textContent=
      `🎲 You hit ×${multiplier}!`;


    if(turns>=8){

      finishGame(
        pot,
        "You survived the Ultimate Gamble!"
      );

    }

  };


  $("#gambleCash").onclick=()=>{

    finishGame(
      pot,
      "You cashed out!"
    );

  };

}


/* =========================================================
   GAME 19
   ADMIRER'S LAST STAND
========================================================= */

function game19(){

  let phase=1;
  let playerHealth=100;
  let bossHealth=170;


  $("#gameArea").innerHTML=`

    <div class="center">

      <h3>
        👑 Phase
        <span id="bossPhase">1</span>
      </h3>

      <p>
        You ❤️
        <b id="bossPlayerHealth">
          100
        </b>

        &nbsp;&nbsp;

        Boss 👑
        <b id="bossHealth">
          170
        </b>
      </p>

      <div class="choice-grid">

        <button id="bossStrike">
          ⚔️ Strike
        </button>

        <button id="bossGuard">
          🛡️ Guard
        </button>

        <button id="bossSpecial">
          ✨ Special
        </button>

        <button id="bossRecover">
          💗 Recover
        </button>

      </div>

      <div
        class="feedback"
        id="bossFeedback"
      ></div>

    </div>

  `;


  function bossTurn(){

    if(bossHealth<=0){

      if(phase<3){

        phase++;

        bossHealth=
          160+phase*25;

        $("#bossPhase")
          .textContent=phase;

        $("#bossHealth")
          .textContent=bossHealth;

        $("#bossFeedback")
          .textContent=
          `👑 Phase ${phase}!`;

        return;

      }


      finishGame(
        450,
        "The Admirer's Last Stand is defeated!"
      );

      return;

    }


    let damage=
      phase===1
      ?12
      :phase===2
      ?18
      :24;


    if(Math.random()<.2)
      damage*=2;


    playerHealth-=damage;


    $("#bossPlayerHealth")
      .textContent=
      Math.max(
        0,
        playerHealth
      );


    if(playerHealth<=0){

      finishGame(
        25,
        "The Admirer's Last Stand won."
      );

    }

  }


  $("#bossStrike").onclick=()=>{

    bossHealth-=22;

    $("#bossHealth")
      .textContent=
      Math.max(
        0,
        bossHealth
      );

    bossTurn();

  };


  $("#bossGuard").onclick=()=>{

    const before=
      playerHealth;

    bossTurn();

    const damage=
      before-playerHealth;

    playerHealth+=
      Math.floor(damage*.5);

    $("#bossPlayerHealth")
      .textContent=
      Math.max(
        0,
        playerHealth
      );

    $("#bossFeedback")
      .textContent=
      "🛡️ Guard reduced the attack.";

  };


  $("#bossSpecial").onclick=()=>{

    if(Math.random()>.3){

      bossHealth-=40;

      $("#bossHealth")
        .textContent=
        Math.max(
          0,
          bossHealth
        );

      $("#bossFeedback")
        .textContent=
        "✨ Special attack landed!";

      bossTurn();

    }else{

      playerHealth-=18;

      $("#bossPlayerHealth")
        .textContent=
        Math.max(
          0,
          playerHealth
        );

      $("#bossFeedback")
        .textContent=
        "✨ Special attack backfired.";

      bossTurn();

    }

  };


  $("#bossRecover").onclick=()=>{

    playerHealth=
      Math.min(
        100,
        playerHealth+25
      );

    $("#bossPlayerHealth")
      .textContent=
      playerHealth;

    bossTurn();

  };

}


/* =========================================================
   WORD FIND DATA
========================================================= */

const wordList=[

"LILIANA",
"LULU",
"FRIENDS",
"PINK",
"DOLPHIN",
"SUNFLOWER",
"ROSE",
"SUSHI",
"POETRY",
"MUSIC",
"PSYCHOLOGY",
"LEO",
"JULY",
"LOVE",
"FAMILY",
"HEART",
"DREAM",
"AAYLA",
"ARLO",
"OCEAN",
"FOREVER",
"THREE",
"SIXYEARS",
"CHARM",
"EMPATHY"

];


function createWordSearch(words){

  const size=15;

  const grid=
    Array.from(
      {length:size},
      ()=>Array(size).fill("")
    );


  const directions=[

    [1,0],
    [-1,0],
    [0,1],
    [0,-1],

    [1,1],
    [-1,-1],
    [1,-1],
    [-1,1]

  ];


  const placements=[];


  function placeWord(word){

    for(let attempt=0;attempt<1000;attempt++){

      const direction=
        directions[
          Math.floor(
            Math.random()*
            directions.length
          )
        ];


      const row=
        Math.floor(
          Math.random()*size
        );

      const col=
        Math.floor(
          Math.random()*size
        );


      const endRow=
        row+
        direction[1]*
        (word.length-1);

      const endCol=
        col+
        direction[0]*
        (word.length-1);


      if(
        endRow<0 ||
        endRow>=size ||
        endCol<0 ||
        endCol>=size
      )continue;


      let valid=true;


      for(
        let i=0;
        i<word.length;
        i++
      ){

        const r=
          row+
          direction[1]*i;

        const c=
          col+
          direction[0]*i;

        const existing=
          grid[r][c];

        if(
          existing &&
          existing!==word[i]
        ){

          valid=false;
          break;

        }

      }


      if(!valid)continue;


      for(
        let i=0;
        i<word.length;
        i++
      ){

        const r=
          row+
          direction[1]*i;

        const c=
          col+
          direction[0]*i;

        grid[r][c]=word[i];

      }


      placements.push({
        word,
        start:[row,col],
        end:[endRow,endCol]
      });


      return true;

    }


    return false;

  }


  shuffle(words)
    .forEach(placeWord);


  const alphabet=
    "ABCDEFGHIJKLMNOPQRSTUVWXYZ";


  for(let r=0;r<size;r++){

    for(let c=0;c<size;c++){

      if(!grid[r][c]){

        grid[r][c]=
          alphabet[
            Math.floor(
              Math.random()*
              alphabet.length
            )
          ];

      }

    }

  }


  return {
    grid,
    placements
  };

}


/* =========================================================
   GAME 20
   LILIANA'S WORD FIND
========================================================= */

function game20(){

  const data=
    createWordSearch(wordList);


  $("#gameArea").innerHTML=`

    <p>
      Find all 25 words.
      Words can run horizontally,
      vertically, diagonally,
      forwards or backwards.
    </p>

    <div
      class="word-list"
      id="wordList"
    ></div>

    <div
      class="word-grid"
      id="wordGrid"
    ></div>

    <div
      class="feedback"
      id="wordFeedback"
    >
      Words found: 0/25
    </div>

  `;


  const grid=
    $("#wordGrid");


  const found=new Set();

  let selection=[];
  let selecting=false;


  wordList.forEach(word=>{

    const span=
      document.createElement("span");

    span.className=
      "word-item";

    span.dataset.word=word;

    span.textContent=word;

    $("#wordList")
      .appendChild(span);

  });


  data.grid.forEach(
    (row,r)=>{

      row.forEach(
        (letter,c)=>{

          const button=
            document.createElement("button");

          button.className=
            "word-letter";

          button.textContent=letter;

          button.dataset.row=r;
          button.dataset.col=c;


          button.addEventListener(
            "pointerdown",
            event=>{

              event.preventDefault();

              selecting=true;

              selection=[
                [r,c]
              ];

              clearSelected();

              button.classList.add(
                "selected"
              );

            }
          );


          button.addEventListener(
            "pointerenter",
            ()=>{

              if(!selecting)return;

              if(
                !selection.some(
                  point=>
                    point[0]===r &&
                    point[1]===c
                )
              ){

                selection.push(
                  [r,c]
                );

                button.classList.add(
                  "selected"
                );

              }

            }
          );


          grid.appendChild(button);

        }
      );

    }
  );


  function clearSelected(){

    document
      .querySelectorAll(
        ".word-letter.selected"
      )
      .forEach(
        b=>b.classList.remove(
          "selected"
        )
      );

  }


  function finishSelection(){

    if(!selecting)return;

    selecting=false;


    const letters=
      selection.map(
        ([r,c])=>
          data.grid[r][c]
      );


    const word=
      letters.join("");

    const reverse=
      [...letters]
        .reverse()
        .join("");


    const placement=
      data.placements.find(
        item=>
          !found.has(item.word) &&
          (
            item.word===word ||
            item.word===reverse
          )
      );


    if(placement){

      found.add(
        placement.word
      );


      const span=
        document.querySelector(
          `[data-word="${placement.word}"]`
        );


      if(span)
        span.classList.add("found");


      selection.forEach(
        ([r,c])=>{

          const cell=
            document.querySelector(
              `.word-letter[data-row="${r}"][data-col="${c}"]`
            );

          if(cell)
            cell.classList.add("found");

        }
      );


      addPoints(25);


      $("#wordFeedback")
        .textContent=
        `Words found: ${found.size}/25`;


      if(found.size===25){

        finishGame(
          300,
          "All 25 words found! 🔎💗"
        );

      }

    }


    clearSelected();

    selection=[];

  }


  document.addEventListener(
    "pointerup",
    finishSelection
  );

}


/* =========================================================
   GAME 21
   DRAW A SUNFLOWER
========================================================= */

function game21(){

  $("#gameArea").innerHTML=`

    <p>
      Draw a sunflower for Liliana.
      Use your finger or mouse.
    </p>

    <canvas
      id="sunflowerCanvas"
      width="760"
      height="520"
    ></canvas>

    <div class="draw-tools">

      <button data-brush="petal">
        🌻 Petal
      </button>

      <button data-brush="stem">
        🌿 Stem
      </button>

      <button data-brush="leaf">
        🍃 Leaf
      </button>

      <button data-brush="centre">
        🟤 Centre
      </button>

      <button id="undoDrawing">
        ↩️ Undo
      </button>

      <button id="clearDrawing">
        🧹 Clear
      </button>

      <button id="finishDrawing">
        ✨ Finish
      </button>

    </div>

    <div class="center">

      <label>

        Brush size

        <input
          id="brushSize"
          type="range"
          min="3"
          max="35"
          value="12"
        >

      </label>

      <div
        class="feedback"
        id="drawingFeedback"
      >
        Draw at least 20 strokes.
      </div>

    </div>

  `;


  const canvas=
    $("#sunflowerCanvas");

  const ctx=
    canvas.getContext("2d");


  ctx.fillStyle="#fff7fb";

  ctx.fillRect(
    0,
    0,
    canvas.width,
    canvas.height
  );


  let drawing=false;
  let strokes=0;
  let history=[];

  let brushColour="#8e315c";


  const colours={

    petal:"#e5a72c",

    stem:"#4f8d58",

    leaf:"#4f8d58",

    centre:"#70482a"

  };


  function position(event){

    const rect=
      canvas.getBoundingClientRect();

    return {

      x:
        (event.clientX-rect.left)*
        canvas.width/
        rect.width,

      y:
        (event.clientY-rect.top)*
        canvas.height/
        rect.height

    };

  }


  function startDrawing(event){

    drawing=true;

    history.push(
      ctx.getImageData(
        0,
        0,
        canvas.width,
        canvas.height
      )
    );


    const p=
      position(event);

    ctx.beginPath();

    ctx.moveTo(
      p.x,
      p.y
    );

  }


  function draw(event){

    if(!drawing)return;


    const p=
      position(event);


    ctx.lineTo(
      p.x,
      p.y
    );


    ctx.lineWidth=
      Number(
        $("#brushSize").value
      );

    ctx.lineCap="round";

    ctx.strokeStyle=
      brushColour;

    ctx.stroke();


    strokes++;


    $("#drawingFeedback")
      .textContent=
      `${strokes} strokes • Keep creating!`;

  }


  function stopDrawing(){

    drawing=false;

  }


  canvas.addEventListener(
    "pointerdown",
    startDrawing
  );

  canvas.addEventListener(
    "pointermove",
    draw
  );

  canvas.addEventListener(
    "pointerup",
    stopDrawing
  );

  canvas.addEventListener(
    "pointerleave",
    stopDrawing
  );


  document
    .querySelectorAll("[data-brush]")
    .forEach(button=>{

      button.onclick=()=>{

        brushColour=
          colours[
            button.dataset.brush
          ];

      };

    });


  $("#undoDrawing").onclick=()=>{

    if(!history.length)return;

    const previous=
      history.pop();

    ctx.putImageData(
      previous,
      0,
      0
    );

    strokes=
      Math.max(
        0,
        strokes-1
      );

  };


  $("#clearDrawing").onclick=()=>{

    history.push(
      ctx.getImageData(
        0,
        0,
        canvas.width,
        canvas.height
      )
    );

    ctx.fillStyle="#fff7fb";

    ctx.fillRect(
      0,
      0,
      canvas.width,
      canvas.height
    );

    strokes=0;

    $("#drawingFeedback")
      .textContent=
      "Canvas cleared. Start again!";

  };


  $("#finishDrawing").onclick=()=>{

    if(strokes<20){

      $("#drawingFeedback")
        .textContent=
        "🌻 Keep drawing! Your sunflower needs a few more strokes.";

      return;

    }


    finishGame(
      250,
      "A sunflower made for Liliana! 🌻"
    );

  };

}


/* =========================================================
   100 DERBY QUESTIONS
========================================================= */

const derbyQuestions=[

[
"Which ocean is the largest?",
["Atlantic","Pacific","Indian","Southern"],
1
],

[
"What is the fastest land animal?",
["Lion","Cheetah","Horse","Leopard"],
1
],

[
"Which planet has prominent rings?",
["Jupiter","Saturn","Uranus","Neptune"],
1
],

[
"What is the capital of Japan?",
["Kyoto","Tokyo","Osaka","Nagoya"],
1
],

[
"What is 9 × 7?",
["56","63","72","81"],
1
],

[
"Which country is shaped like a boot?",
["Portugal","Italy","Chile","Croatia"],
1
],

[
"What do bees collect from flowers?",
["Nectar","Salt","Bark","Moss"],
0
],

[
"Which planet is closest to the Sun?",
["Venus","Earth","Mercury","Mars"],
2
],

[
"What is the largest internal organ?",
["Heart","Liver","Lung","Kidney"],
1
],

[
"Which animal changes colour for camouflage?",
["Chameleon","Koala","Penguin","Otter"],
0
],

[
"How many continents are commonly recognised?",
["5","6","7","8"],
2
],

[
"What fruit is used to make guacamole?",
["Mango","Avocado","Papaya","Lime"],
1
],

[
"What is water's boiling point at sea level?",
["90°C","95°C","100°C","110°C"],
2
],

[
"Which famous ship sank in 1912?",
["Lusitania","Titanic","Endeavour","Mayflower"],
1
],

[
"Which star is at the centre of our Solar System?",
["Sirius","Polaris","The Sun","Betelgeuse"],
2
],

[
"What is the main ingredient in hummus?",
["Chickpeas","Lentils","Potatoes","Rice"],
0
],

[
"Which country gave the Statue of Liberty to the US?",
["Spain","France","Italy","Germany"],
1
],

[
"Which animal is a mammal that lays eggs?",
["Dolphin","Platypus","Seal","Bat"],
1
],

[
"What is the largest planet?",
["Saturn","Neptune","Jupiter","Uranus"],
2
],

[
"Which instrument is played with a bow?",
["Violin","Flute","Drum","Piano"],
0
],

[
"What colour results from blue and yellow paint?",
["Purple","Green","Orange","Brown"],
1
],

[
"Which city has the Eiffel Tower?",
["Rome","Paris","Madrid","Vienna"],
1
],

[
"What is water's freezing point in Celsius?",
["0","10","32","-10"],
0
],

[
"Which animal is often called man's best friend?",
["Cat","Dog","Horse","Rabbit"],
1
],

[
"Which planet is the Red Planet?",
["Mars","Venus","Mercury","Jupiter"],
0
],

[
"What is the largest desert by area?",
["Sahara","Gobi","Antarctica","Arabian"],
2
],

[
"Which ocean lies between Africa and Australia?",
["Atlantic","Indian","Pacific","Arctic"],
1
],

[
"What is the square root of 81?",
["7","8","9","10"],
2
],

[
"Which shape has three sides?",
["Square","Triangle","Pentagon","Hexagon"],
1
],

[
"What is the main language of Brazil?",
["Spanish","Portuguese","French","Italian"],
1
],

[
"Which animal has black-and-white stripes?",
["Zebra","Tiger","Panda","Skunk"],
0
],

[
"What is the nearest star to Earth?",
["Sirius","Proxima Centauri","The Sun","Polaris"],
2
],

[
"Where are the pyramids of Giza?",
["Egypt","Mexico","Peru","Sudan"],
0
],

[
"What do plants use sunlight for?",
["Making food","Making sound","Making soil","Making seeds only"],
0
],

[
"Which sea creature has eight arms?",
["Squid","Octopus","Starfish","Crab"],
1
],

[
"How many days are in a leap year?",
["364","365","366","367"],
2
],

[
"What material is primarily used to make glass?",
["Sand","Coal","Clay","Cotton"],
0
],

[
"What is the largest bone in the body?",
["Femur","Tibia","Humerus","Pelvis"],
0
],

[
"Where is the Taj Mahal?",
["India","Nepal","Pakistan","Bangladesh"],
0
],

[
"Which sport is played at Wimbledon?",
["Golf","Tennis","Cricket","Rugby"],
1
],

[
"Which animal builds dams?",
["Beaver","Otter","Badger","Fox"],
0
],

[
"What is oxygen's chemical symbol?",
["O","Ox","Og","C"],
0
],

[
"Which planet has the Great Red Spot?",
["Mars","Jupiter","Saturn","Venus"],
1
],

[
"Which month has 28 days in a common year?",
["February","April","June","All of them"],
0
],

[
"Which is the largest big cat species?",
["Tiger","Lion","Jaguar","Leopard"],
0
],

[
"Where is Machu Picchu?",
["Chile","Peru","Bolivia","Ecuador"],
1
],

[
"What is the UK's currency?",
["Euro","Pound sterling","Franc","Krone"],
1
],

[
"What does the Richter scale measure?",
["Tornadoes","Earthquakes","Hurricanes","Floods"],
1
],

[
"Which vitamin is produced through sunlight exposure?",
["Vitamin A","Vitamin B12","Vitamin C","Vitamin D"],
3
],

[
"What is the tallest land animal?",
["Elephant","Giraffe","Camel","Moose"],
1
],

[
"Which country is home to the Great Barrier Reef?",
["Australia","New Zealand","Indonesia","South Africa"],
0
],

[
"What force pulls objects toward Earth?",
["Magnetism","Gravity","Friction","Pressure"],
1
],

[
"Which planet is hottest on average?",
["Mercury","Venus","Mars","Jupiter"],
1
],

[
"What is the world's largest island?",
["Greenland","New Guinea","Borneo","Madagascar"],
0
],

[
"Which detective lives at 221B Baker Street?",
["Hercule Poirot","Sherlock Holmes","Miss Marple","Columbo"],
1
],

[
"What food is traditionally made from fermented cabbage?",
["Kimchi","Hummus","Risotto","Falafel"],
0
],

[
"Which country is home to Mount Fuji?",
["China","Japan","South Korea","Thailand"],
1
],

[
"What is the opposite of nocturnal?",
["Aquatic","Diurnal","Arboreal","Migratory"],
1
],

[
"Which animal has a trunk?",
["Elephant","Rhino","Hippo","Walrus"],
0
],

[
"Which planet is famous for its ring system?",
["Earth","Saturn","Mars","Mercury"],
1
],

[
"What gas do humans breathe in for respiration?",
["Oxygen","Nitrogen","Hydrogen","Helium"],
0
],

[
"Who developed the theory of relativity?",
["Newton","Einstein","Darwin","Galileo"],
1
],

[
"Which country is Venice in?",
["Italy","Spain","France","Greece"],
0
],

[
"Which part of a plant absorbs water?",
["Flower","Root","Fruit","Seed"],
1
],

[
"How many minutes are in an hour?",
["30","45","60","90"],
2
],

[
"Which animal is a marsupial?",
["Kangaroo","Wolf","Horse","Polar bear"],
0
],

[
"What is the largest continent?",
["Africa","Asia","Europe","North America"],
1
],

[
"Which sport uses a bat, ball and wickets?",
["Baseball","Cricket","Hockey","Tennis"],
1
],

[
"What is water vapour becoming liquid called?",
["Evaporation","Condensation","Sublimation","Melting"],
1
],

[
"Which planet is similar in size to Earth?",
["Venus","Mars","Mercury","Neptune"],
0
],

[
"Which animal is famous for its long neck?",
["Giraffe","Zebra","Yak","Bison"],
0
],

[
"What is the capital of New Zealand?",
["Auckland","Wellington","Christchurch","Dunedin"],
1
],

[
"What gas do plants absorb?",
["Oxygen","Carbon dioxide","Nitrogen","Helium"],
1
],

[
"What is the largest ocean animal?",
["Blue whale","Great white shark","Giant squid","Orca"],
0
],

[
"Which civilisation built Machu Picchu?",
["Roman","Inca","Viking","Mayan"],
1
],

[
"Which colour is associated with chlorophyll?",
["Red","Blue","Green","Purple"],
2
],

[
"What is 12 × 12?",
["124","132","144","156"],
2
],

[
"Which animal is known for a pouch?",
["Kangaroo","Penguin","Crocodile","Horse"],
0
],

[
"Which geographic region is New Zealand part of?",
["Europe","Oceania","Asia","Antarctica"],
1
],

[
"What is Earth's natural satellite?",
["Mars","Moon","Sun","Europa"],
1
],

[
"What type of animal is a frog?",
["Mammal","Reptile","Amphibian","Bird"],
2
],

[
"Which metal has the symbol Fe?",
["Iron","Fluorine","Francium","Fermium"],
0
],

[
"Which landmark is in New York Harbour?",
["Big Ben","Statue of Liberty","Colosseum","Sydney Opera House"],
1
],

[
"Which animal can sleep while floating in water?",
["Otter","Giraffe","Elephant","Camel"],
0
],

[
"Which number is neither prime nor composite?",
["0","1","2","3"],
1
],

[
"Where is Barcelona?",
["Portugal","Spain","France","Italy"],
1
],

[
"What is the second-largest planet?",
["Saturn","Neptune","Uranus","Earth"],
0
],

[
"Which organ is primarily responsible for breathing?",
["Lung","Kidney","Liver","Stomach"],
0
],

[
"Which bird is native to New Zealand and cannot fly?",
["Kiwi","Eagle","Swan","Falcon"],
0
],

[
"Which dessert is made with meringue and fruit?",
["Pavlova","Tiramisu","Baklava","Gelato"],
0
],

[
"What force opposes motion between surfaces?",
["Gravity","Friction","Buoyancy","Radiation"],
1
],

[
"What is the capital of France?",
["Paris","Lyon","Nice","Marseille"],
0
],

[
"Which animal eats mainly bamboo?",
["Panda","Zebra","Lemur","Penguin"],
0
],

[
"Which planet is farthest from the Sun?",
["Uranus","Neptune","Saturn","Jupiter"],
1
],

[
"What is sodium chloride commonly called?",
["Sugar","Baking soda","Table salt","Vinegar"],
2
],

[
"What separates England and France?",
["English Channel","Baltic Sea","Black Sea","North Sea"],
0
],

[
"Who wrote Romeo and Juliet?",
["Shakespeare","Dickens","Austen","Milton"],
0
],

[
"Which animal is known for echolocation?",
["Bat","Rabbit","Horse","Kangaroo"],
0
],

[
"How many sides does a hexagon have?",
["5","6","7","8"],
1
],

[
"Which planet is known for its blue colour?",
["Mars","Neptune","Mercury","Venus"],
1
],

[
"What is the largest organ of the human body?",
["Heart","Skin","Liver","Lung"],
1
],

[
"Which country is famous for the Colosseum?",
["Italy","Greece","Spain","France"],
0
],

[
"Which sport uses a puck?",
["Ice hockey","Tennis","Cricket","Golf"],
0
],

[
"What is 15 + 27?",
["32","40","42","44"],
2
],

[
"Which animal is known for its black-and-white coat and bamboo diet?",
["Panda","Zebra","Skunk","Penguin"],
0
],

[
"Which planet has a day longer than its year?",
["Venus","Mars","Jupiter","Neptune"],
0
],

[
"Which natural satellite orbits Earth?",
["Moon","Europa","Titan","Phobos"],
0
]

];


/* =========================================================
   GAME 22
   THE LULU DERBY
========================================================= */

function game22(){

  const questions=
    shuffle(derbyQuestions)
      .slice(0,100);


  let questionIndex=0;
  let horsePosition=5;


  $("#gameArea").innerHTML=`

    <div class="race">

      <div class="finish-line"></div>

      <div class="lane">
        <div
          class="horse"
          id="horse0"
        >
          🏇
        </div>
      </div>

      <div class="lane">
        <div
          class="horse"
          id="horse1"
        >
          🏇
        </div>
      </div>

      <div class="lane">
        <div
          class="horse"
          id="horse2"
        >
          🏇
        </div>
      </div>

      <div class="lane">
        <div
          class="horse"
          id="horse3"
        >
          🏇
        </div>
      </div>

    </div>

    <div
      class="quiz-question"
      id="derbyQuestion"
      style="margin-top:15px"
    ></div>

    <div
      class="choice-grid"
      id="derbyChoices"
    ></div>

    <div
      class="feedback"
      id="derbyFeedback"
    ></div>

    <div class="progress">

      <div
        class="progress-fill"
        id="derbyProgress"
      ></div>

    </div>

    <p class="trivia-label">
      🏇 100 completely random trivia questions.
      Correct answers help your horse surge forward.
    </p>

  `;


  function moveHorses(){

    $("#horse0")
      .style.left=
      horsePosition+"%";


    for(let i=1;i<4;i++){

      $("#horse"+i)
        .style.left=
        (
          5+
          Math.random()*80
        )+"%";

    }

  }


  function askQuestion(){

    if(questionIndex>=100){

      finishGame(
        300+
        Math.floor(
          horsePosition*5
        ),
        "THE LULU DERBY is complete! 🏇💗"
      );

      return;

    }


    const question=
      questions[questionIndex];


    const answers=
      shuffle(
        question[1]
          .map(
            (answer,index)=>({
              answer,
              correct:
                index===question[2]
            })
          )
      );


    $("#derbyQuestion")
      .innerHTML=`

      <div class="trivia-label">
        Derby Trivia
        ${questionIndex+1}/100
      </div>

      <br>

      <b>${question[0]}</b>

    `;


    const choices=
      $("#derbyChoices");

    choices.innerHTML="";


    answers.forEach(option=>{

      const button=
        document.createElement("button");

      button.className="choice";

      button.textContent=
        option.answer;


      button.onclick=()=>{

        [
          ...choices.children
        ].forEach(
          b=>b.disabled=true
        );


        if(option.correct){

          horsePosition=
            Math.min(
              94,
              horsePosition+
              3+
              Math.floor(
                Math.random()*4
              )
            );

          addPoints(8);

          $("#derbyFeedback")
            .textContent=
            "🏇💨 Correct! Your horse surges forward!";

        }else{

          horsePosition=
            Math.max(
              5,
              horsePosition-2
            );

          $("#derbyFeedback")
            .textContent=
            "Your horse lost some ground.";

        }


        moveHorses();


        questionIndex++;


        $("#derbyProgress")
          .style.width=
          questionIndex+"%";


        later(
          askQuestion,
          170
        );

      };


      choices.appendChild(button);

    });

  }


  moveHorses();

  askQuestion();

}


/* =========================================================
   GAME 23
   FINAL CHALLENGE
========================================================= */

function game23(){

  /*
    The final challenge uses all 50 Liliana questions.
    They are separate from the Derby and separate from
    the Pressure Quiz.
  */

  runQuiz(
    lilianaQuestions,
    50,
    45,
    true
  );

}


/* =========================================================
   GAME FUNCTION LIST
========================================================= */

const gameFunctions=[

  game1,
  game2,
  game3,
  game4,
  game5,
  game6,
  game7,
  game8,
  game9,
  game10,
  game11,
  game12,
  game13,
  game14,
  game15,
  game16,
  game17,
  game18,
  game19,
  game20,
  game21,
  game22,
  game23

];


/* =========================================================
   NAVIGATION
========================================================= */

$("#backButton").onclick=()=>{

  clearGameTimers();

  returnHome();

};


/* =========================================================
   START
========================================================= */

renderMenu();

updateStats();

</script>

</body>
</html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
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
 --panel2:#321626;
 --pink:#ff75ad;
 --pink2:#ffb5d2;
 --burgundy:#741f43;
 --gold:#ffd76a;
 --green:#73e59b;
 --red:#ff657c;
 --muted:#cdaabd;
}

body{
 margin:0;
 min-height:100vh;
 background:
 radial-gradient(circle at top,#4b1731 0%,#1d0b15 38%,#0d060a 100%);
 color:#fff3f8;
 font-family:Arial,sans-serif;
}

button,input{
 font:inherit;
}

button{
 cursor:pointer;
}

.hidden{
 display:none!important;
}

/* START */

#startScreen{
 min-height:100vh;
 display:flex;
 justify-content:center;
 align-items:center;
 padding:20px;
}

.startCard{
 width:min(600px,100%);
 background:rgba(38,18,30,.97);
 border:1px solid rgba(255,117,173,.35);
 border-radius:28px;
 padding:35px 25px;
 text-align:center;
 box-shadow:0 20px 70px rgba(0,0,0,.5);
}

.trainLogo{
 font-size:75px;
 animation:trainFloat 2s ease-in-out infinite;
}

@keyframes trainFloat{
 0%,100%{transform:translateX(-5px)}
 50%{transform:translateX(5px)}
}

.startCard h1{
 font-size:42px;
 margin:8px 0;
}

.startCard p{
 color:var(--muted);
 line-height:1.6;
}

.nameInput{
 width:100%;
 padding:16px;
 border-radius:15px;
 border:1px solid #81415e;
 background:#160a11;
 color:#fff;
 text-align:center;
 outline:none;
 margin:15px 0;
}

.nameInput:focus{
 border-color:var(--pink);
}

.primary{
 width:100%;
 padding:15px;
 border:0;
 border-radius:15px;
 color:#fff;
 font-weight:bold;
 background:linear-gradient(135deg,#ff75ad,#a9275e);
}

/* HEADER */

#app{
 display:none;
 min-height:100vh;
}

.topbar{
 position:sticky;
 top:0;
 z-index:100;
 background:rgba(18,8,14,.95);
 backdrop-filter:blur(12px);
 border-bottom:1px solid rgba(255,117,173,.2);
 padding:10px;
}

.topbarInner{
 max-width:1100px;
 margin:auto;
 display:flex;
 align-items:center;
 justify-content:space-between;
 gap:10px;
}

.logo{
 font-weight:bold;
}

.stats{
 display:flex;
 flex-wrap:wrap;
 justify-content:center;
 gap:7px;
}

.stat{
 background:var(--panel);
 border-radius:11px;
 padding:7px 10px;
 font-size:13px;
}

.reset{
 background:#35121f;
 border:1px solid #71314c;
 color:#ffb5c9;
 border-radius:10px;
 padding:8px 11px;
 font-size:12px;
}

/* JOURNEY */

#journeyScreen{
 max-width:1100px;
 margin:auto;
 padding:20px 15px 50px;
}

.welcome{
 background:linear-gradient(135deg,#341526,#21101a);
 border:1px solid rgba(255,117,173,.25);
 border-radius:22px;
 padding:20px;
 margin-bottom:18px;
}

.welcome h2{
 margin-top:0;
}

.welcome p{
 color:var(--muted);
}

.progressBox{
 background:var(--panel);
 border-radius:20px;
 padding:17px;
 margin-bottom:20px;
}

.progressTrack{
 height:12px;
 background:#10070c;
 border-radius:20px;
 overflow:hidden;
}

.progressFill{
 width:0%;
 height:100%;
 background:linear-gradient(90deg,#ff75ad,#ffd76a);
 transition:.5s;
}

.progressText{
 text-align:center;
 color:var(--muted);
 font-size:13px;
 margin-top:8px;
}

.journey{
 display:grid;
 grid-template-columns:repeat(4,1fr);
 gap:15px;
}

.station{
 background:#21101a;
 border:1px solid #492333;
 border-radius:21px;
 min-height:130px;
 padding:13px 8px;
 text-align:center;
 transition:.2s;
}

.station.current{
 border-color:var(--pink);
 box-shadow:0 0 25px rgba(255,117,173,.25);
 transform:translateY(-4px);
 cursor:pointer;
}

.station.completed{
 border-color:#4bbd73;
 background:#14231a;
}

.station.locked{
 opacity:.4;
 filter:grayscale(.5);
}

.stationNumber{
 color:var(--muted);
 font-size:11px;
}

.stationIcon{
 font-size:35px;
 margin:6px;
}

.stationName{
 font-size:12px;
 font-weight:bold;
}

.stationStatus{
 font-size:11px;
 margin-top:8px;
}

.trainMarker{
 margin-top:5px;
 font-size:25px;
}

/* GAME */

#gameScreen{
 max-width:1050px;
 margin:25px auto;
 padding:0 15px 50px;
}

.gamePanel{
 background:rgba(38,18,30,.97);
 border:1px solid rgba(255,117,173,.25);
 border-radius:25px;
 padding:22px;
 min-height:500px;
}

.gameHeader{
 text-align:center;
}

.gameHeaderIcon{
 font-size:55px;
}

.gameHeader h2{
 margin:5px 0;
}

.gameHeader p{
 color:var(--muted);
}

.gameContent{
 max-width:850px;
 margin:auto;
}

.gameBtn{
 border:1px solid #69304a;
 background:#301521;
 color:#fff;
 border-radius:13px;
 padding:12px 17px;
 margin:5px;
}

.gameBtn:hover{
 border-color:var(--pink);
}

.nextBtn{
 border:0;
 background:linear-gradient(135deg,#ff75ad,#a9275e);
 color:#fff;
 padding:15px 28px;
 border-radius:15px;
 font-weight:bold;
 margin-top:15px;
}

.backBtn{
 border:1px solid #633047;
 background:#321521;
 color:#fff;
 border-radius:12px;
 padding:11px 17px;
 margin-top:20px;
}

.complete{
 text-align:center;
 padding:30px 10px;
}

.completeIcon{
 font-size:70px;
}

.complete h2{
 color:var(--pink2);
}

/* COMMON GAME UI */

.answerGrid{
 display:grid;
 grid-template-columns:1fr 1fr;
 gap:10px;
}

.questionBox{
 background:#1a0c13;
 border-radius:18px;
 padding:18px;
 margin-bottom:15px;
 text-align:center;
}

.timer{
 font-size:24px;
 color:var(--gold);
 text-align:center;
 margin:10px;
}

.scoreBox{
 text-align:center;
 margin:12px;
 color:var(--pink2);
 font-weight:bold;
}

/* MEMORY */

.memoryGrid{
 display:grid;
 grid-template-columns:repeat(4,1fr);
 gap:8px;
 max-width:430px;
 margin:20px auto;
}

.memoryTile{
 aspect-ratio:1;
 border:1px solid #71314f;
 border-radius:12px;
 background:#2a1321;
 color:transparent;
}

.memoryTile.show{
 background:#ff75ad;
 color:#fff;
}

.memoryTile.clicked{
 background:#71314f;
}

/* SLOTS */

.slots{
 display:flex;
 justify-content:center;
 gap:10px;
 margin:25px 0;
}

.reel{
 width:85px;
 height:85px;
 display:flex;
 align-items:center;
 justify-content:center;
 background:#13080e;
 border:2px solid #743250;
 border-radius:15px;
 font-size:42px;
}

/* CARDS */

.cardGrid{
 display:grid;
 grid-template-columns:repeat(4,1fr);
 gap:10px;
}

.riskCard{
 min-height:100px;
 border-radius:15px;
 border:1px solid #743250;
 background:#311521;
 color:#fff;
 font-size:30px;
}

/* HEARTBREAK CHAMBER / MAZE */

.mazeWrap{
 display:flex;
 flex-direction:column;
 align-items:center;
}

.maze{
 display:grid;
 gap:2px;
 background:#080408;
 border:4px solid #71314f;
 padding:4px;
 width:min(92vw,520px);
 aspect-ratio:1;
 touch-action:none;
}

.mazeCell{
 background:#26121e;
 position:relative;
}

.mazeCell.wall{
 background:#090509;
}

.mazeCell.start{
 background:#321a28;
}

.mazeCell.exit{
 background:#321b18;
}

.player{
 position:absolute;
 inset:12%;
 background:#ff75ad;
 border-radius:50%;
 box-shadow:0 0 12px #ff75ad;
}

.exitMark{
 position:absolute;
 inset:8%;
 display:flex;
 align-items:center;
 justify-content:center;
 font-size:clamp(12px,4vw,25px);
}

.mazeControls{
 display:grid;
 grid-template-columns:repeat(3,65px);
 gap:7px;
 justify-content:center;
 margin:15px;
}

.mazeControls button{
 width:65px;
 height:55px;
 border-radius:13px;
 border:1px solid #71314f;
 background:#321521;
 color:#fff;
 font-size:22px;
}

.mazeHint{
 text-align:center;
 color:var(--muted);
}

/* BOXING */

.fighterArena{
 background:#160a10;
 border:1px solid #613048;
 border-radius:20px;
 padding:20px;
 text-align:center;
}

.healthBar{
 height:20px;
 background:#090509;
 border-radius:20px;
 overflow:hidden;
 margin:8px 0 15px;
}

.healthFill{
 height:100%;
 background:#ff657c;
 width:100%;
 transition:.3s;
}

/* MATCH */

.matchBoard{
 display:flex;
 flex-wrap:wrap;
 justify-content:center;
 gap:15px;
}

.matchItem{
 width:105px;
 height:105px;
 border:2px dashed #71314f;
 border-radius:18px;
 display:flex;
 align-items:center;
 justify-content:center;
 font-size:42px;
 background:#1b0d14;
 touch-action:none;
}

.matchTarget{
 width:105px;
 height:105px;
 border:2px dashed #ff75ad;
 border-radius:18px;
 display:flex;
 align-items:center;
 justify-content:center;
 color:#714057;
}

/* HEART HUNT */

.huntArea{
 height:420px;
 position:relative;
 overflow:hidden;
 border-radius:20px;
 background:
 radial-gradient(circle,#442038,#180a12);
 border:1px solid #71314f;
}

.huntHeart{
 position:absolute;
 font-size:30px;
 cursor:pointer;
 user-select:none;
 transition:.1s;
}

/* CUPID */

.shootArea{
 position:relative;
 height:420px;
 overflow:hidden;
 background:#160a10;
 border:1px solid #71314f;
 border-radius:20px;
 cursor:crosshair;
}

.target{
 position:absolute;
 font-size:38px;
 user-select:none;
}

/* WORD FIND */

.wordGrid{
 display:grid;
 grid-template-columns:repeat(12,1fr);
 gap:2px;
 max-width:650px;
 margin:15px auto;
 touch-action:none;
}

.wordCell{
 aspect-ratio:1;
 display:flex;
 align-items:center;
 justify-content:center;
 background:#21101a;
 border:1px solid #3c1d2b;
 font-size:clamp(11px,3.3vw,20px);
 font-weight:bold;
 user-select:none;
}

.wordCell.found{
 background:#8e2d59;
 color:#fff;
}

.wordList{
 display:flex;
 flex-wrap:wrap;
 gap:5px;
 justify-content:center;
 margin:15px 0;
}

.wordTag{
 background:#321521;
 border-radius:8px;
 padding:5px 8px;
 font-size:11px;
}

.wordTag.found{
 text-decoration:line-through;
 opacity:.5;
}

/* DRAW */

.canvasWrap{
 display:flex;
 flex-direction:column;
 align-items:center;
}

#sunflowerCanvas{
 width:min(90vw,650px);
 height:430px;
 background:#fffafc;
 border-radius:18px;
 touch-action:none;
 border:2px solid #71314f;
}

.tools{
 display:flex;
 flex-wrap:wrap;
 justify-content:center;
 gap:7px;
 margin:12px;
}

.tools button{
 border:1px solid #71314f;
 background:#321521;
 color:#fff;
 border-radius:10px;
 padding:8px 12px;
}

/* DERBY */

.raceTrack{
 background:#120b0e;
 border:1px solid #613048;
 border-radius:18px;
 padding:15px;
}

.horseLane{
 position:relative;
 height:55px;
 border-bottom:2px dashed #5a3445;
 overflow:hidden;
}

.horse{
 position:absolute;
 left:0;
 font-size:30px;
 transition:left .4s;
}

.finish{
 position:absolute;
 right:5px;
 top:0;
 height:100%;
 border-left:4px solid #fff;
}

/* RESPONSIVE */

@media(max-width:700px){

 .topbarInner{
  flex-direction:column;
 }

 .journey{
  grid-template-columns:1fr 1fr;
 }

 .answerGrid{
  grid-template-columns:1fr;
 }

 .cardGrid{
  grid-template-columns:1fr 1fr;
 }

 .startCard h1{
  font-size:32px;
 }

}

@media(max-width:420px){

 .journey{
  gap:8px;
 }

 .station{
  min-height:120px;
 }

 .stationIcon{
  font-size:28px;
 }

 .stationName{
  font-size:10px;
 }

}

</style>
</head>

<body>

<!-- =====================================================
START
===================================================== -->

<section id="startScreen">

 <div class="startCard">

  <div class="trainLogo">🚂💗</div>

  <h1>Lulu Express</h1>

  <p>
   A journey made especially for Liliana.
   <br><br>
   Enter your name to board the train.
   You will have to pass every level to reach
   the final destination.
  </p>

  <input
   id="nameInput"
   class="nameInput"
   maxlength="30"
   placeholder="Enter your name..."
   autocomplete="off"
  >

  <button class="primary" onclick="beginJourney()">
   BOARD THE TRAIN 🚂
  </button>

 </div>

</section>


<!-- =====================================================
APP
===================================================== -->

<div id="app">

 <header class="topbar">

  <div class="topbarInner">

   <div class="logo">
    🚂 Lulu Express
   </div>

   <div class="stats">

    <div class="stat">
     👤 <span id="nameDisplay"></span>
    </div>

    <div class="stat">
     ⭐ <span id="scoreDisplay">0</span>
    </div>

    <div class="stat">
     🎟️ <span id="tokenDisplay">0</span>
    </div>

   </div>

   <button class="reset" onclick="resetGame()">
    Reset
   </button>

  </div>

 </header>


 <!-- JOURNEY -->

 <main id="journeyScreen">

  <div class="welcome">

   <h2>
    Welcome aboard,
    <span id="welcomeName"></span> 💗
   </h2>

   <p>
    Your train is waiting.
    Complete each level to move to the next station.
    Every station must be passed before the next one opens.
   </p>

  </div>


  <div class="progressBox">

   <div class="progressTrack">
    <div id="progressFill" class="progressFill"></div>
   </div>

   <div id="progressText" class="progressText"></div>

  </div>


  <div id="journey" class="journey"></div>

 </main>


 <!-- GAME -->

 <section id="gameScreen" class="hidden">

  <div class="gamePanel">

   <div class="gameHeader">

    <div id="gameIcon" class="gameHeaderIcon"></div>

    <h2 id="gameTitle"></h2>

    <p id="gameDescription"></p>

   </div>

   <div id="gameContent" class="gameContent"></div>

  </div>

 </section>

</div>


<script>

/* =====================================================
GAME DATA
===================================================== */

const games=[
 ["💔","Broken Hearts","Catch the whole hearts and avoid the broken ones."],
 ["🧠","Memory Vault","Remember the sequence on the 4 × 4 grid."],
 ["⏱️","Pressure Quiz","Answer fast before time runs out."],
 ["🎰","High Roller","Spin the reels and chase the jackpot."],
 ["🧩","Mind Games","Solve the visual logic challenges."],
 ["🃏","The Bluff","Risk your cards or cash out."],
 ["🛡️","The Survival Round","Survive every wave."],
 ["🏇","The Admirer Race","Race through the obstacles."],
 ["🔎","The Heartbreak Chamber","Find the clues and escape the maze."],
 ["🥊","The Heartbreak Boxing Match","Punch, block, dodge and counter."],
 ["🧲","The Perfect Match","Drag each object to its matching target."],
 ["💗","Who Knows Liliana Best?","Test how well you know Liliana."],
 ["⚡","Reaction Gauntlet","React before the timer catches you."],
 ["🕵️","The Heart Hunt","Find the hidden hearts."],
 ["🔐","Love Lock","Crack the combination."],
 ["🏹","Cupid Shootout","Hit the moving hearts."],
 ["⏳","The Countdown","Complete the changing mini challenges."],
 ["🎲","The Ultimate Gamble","Risk the pot or cash out."],
 ["👑","The Admirer's Last Stand","Defeat the final admirer."],
 ["🔎","Liliana's Word Find","Find all 25 hidden words."],
 ["🌻","Draw a Sunflower","Create your sunflower."],
 ["🏇","THE LULU DERBY","Answer 100 random trivia questions while racing."],
 ["💕","THE FINAL CHALLENGE","Answer 50 unique questions about Liliana."]
];


/* =====================================================
STATE
===================================================== */

let state={
 name:"",
 score:0,
 tokens:0,
 level:1,
 completed:{}
};

let activeCleanup=null;

function save(){
 localStorage.setItem(
  "luluExpressJourney",
  JSON.stringify(state)
 );
}

function load(){

 const data=
  localStorage.getItem("luluExpressJourney");

 if(!data) return false;

 try{

  const parsed=JSON.parse(data);

  state={
   ...state,
   ...parsed
  };

  return !!state.name;

 }catch{
  return false;
 }
}


/* =====================================================
START
===================================================== */

function beginJourney(){

 const input=
  document.getElementById("nameInput");

 const name=input.value.trim();

 if(!name){

  input.placeholder="Please enter your name 💗";
  input.focus();
  return;

 }

 state={
  name,
  score:0,
  tokens:0,
  level:1,
  completed:{}
 };

 save();
 showApp();
}


function showApp(){

 document.getElementById("startScreen")
  .style.display="none";

 document.getElementById("app")
  .style.display="block";

 document.getElementById("nameDisplay")
  .textContent=state.name;

 document.getElementById("welcomeName")
  .textContent=state.name;

 updateStats();
 renderJourney();
}


/* =====================================================
STATS
===================================================== */

function addPoints(points){

 state.score+=points;

 if(state.score<0)
  state.score=0;

 updateStats();
 save();
}

function addTokens(tokens){

 state.tokens+=tokens;

 if(state.tokens<0)
  state.tokens=0;

 updateStats();
 save();
}

function updateStats(){

 document.getElementById("scoreDisplay")
  .textContent=state.score;

 document.getElementById("tokenDisplay")
  .textContent=state.tokens;

}


/* =====================================================
JOURNEY
===================================================== */

function renderJourney(){

 const journey=
  document.getElementById("journey");

 journey.innerHTML="";

 games.forEach((game,index)=>{

  const level=index+1;

  const completed=
   !!state.completed[level];

  const current=
   level===state.level;

  const locked=
   level>state.level;

  const div=
   document.createElement("div");

  div.className=
   "station "+
   (completed?"completed ":"")+
   (current?"current ":"")+
   (locked?"locked":"");

  let status;

  if(completed)
   status="✅ Complete";
  else if(current)
   status="🚂 Current stop";
  else
   status="🔒 Locked";

  div.innerHTML=`

   <div class="stationNumber">
    LEVEL ${level}
   </div>

   <div class="stationIcon">
    ${game[0]}
   </div>

   <div class="stationName">
    ${game[1]}
   </div>

   <div class="stationStatus">
    ${status}
   </div>

   ${
    current
     ? `<div class="trainMarker">🚂</div>`
     : ""
   }

  `;

  if(current)
   div.onclick=()=>openLevel(level);

  journey.appendChild(div);

 });

 const completed=
  Object.keys(state.completed).length;

 document.getElementById("progressFill")
  .style.width=
  (completed/23*100)+"%";

 document.getElementById("progressText")
  .textContent=
  completed===23
   ?"🏁 Journey complete!"
   :`Level ${state.level} of 23`;

}


/* =====================================================
OPEN LEVEL
===================================================== */

function openLevel(level){

 if(level!==state.level)
  return;

 if(activeCleanup)
  activeCleanup();

 document.getElementById("journeyScreen")
  .classList.add("hidden");

 document.getElementById("gameScreen")
  .classList.remove("hidden");

 const game=games[level-1];

 document.getElementById("gameIcon")
  .textContent=game[0];

 document.getElementById("gameTitle")
  .textContent=
   `Level ${level}: ${game[1]}`;

 document.getElementById("gameDescription")
  .textContent=game[2];

 launchGame(level);

}


/* =====================================================
LEVEL COMPLETION
===================================================== */

function passLevel(level,points=100){

 if(state.completed[level])
  return;

 state.completed[level]=true;

 addPoints(points);
 addTokens(1);

 if(level<23)
  state.level=level+1;
 else
  state.level=23;

 save();

 showCompletion(level);

}


function showCompletion(level){

 const final=level===23;

 document.getElementById("gameContent")
  .innerHTML=`

  <div class="complete">

   <div class="completeIcon">
    ${final?"🏁💗":"🚂✨"}
   </div>

   <h2>
    ${final
     ?"YOU REACHED THE FINAL DESTINATION!"
     :"LEVEL PASSED!"
    }
   </h2>

   <p>
    Amazing work, ${escapeHTML(state.name)}!
   </p>

   <p>
    ⭐ ${state.score} points
    <br>
    🎟️ ${state.tokens} token${state.tokens===1?"":"s"}
   </p>

   ${
    final
     ?finalReward()
     :`
      <button
       class="nextBtn"
       onclick="returnJourney()"
      >
       NEXT STATION 🚂
      </button>
     `
   }

  </div>
 `;
}


function finalReward(){

 if(state.score>=3001){

  return`

   <div class="questionBox">

    <div style="font-size:55px">
     💕📞💕
    </div>

    <h2>
     PRIVATE CALL UNLOCKED!
    </h2>

    <p>
     You finished the entire journey with
     <strong>${state.score}</strong> points!
    </p>

    <p>
     You needed <strong>3001+</strong>.
     You made it. 💗
    </p>

   </div>
  `;

 }

 return`

  <div class="questionBox">

   <div style="font-size:55px">
    💗
   </div>

   <h2>JOURNEY COMPLETE</h2>

   <p>
    You passed all 23 levels!
   </p>

   <p>
    Final score:
    <strong>${state.score}</strong>
   </p>

   <p>
    You needed 3001+ points for the private call reward.
   </p>

  </div>
 `;
}


function returnJourney(){

 if(activeCleanup)
  activeCleanup();

 document.getElementById("gameScreen")
  .classList.add("hidden");

 document.getElementById("journeyScreen")
  .classList.remove("hidden");

 renderJourney();

 window.scrollTo({
  top:0,
  behavior:"smooth"
 });
}


/* =====================================================
RESET
===================================================== */

function resetGame(){

 if(!confirm(
  "Reset Lulu Express?\n\n"+
  "This will erase your name, score, tokens "+
  "and all journey progress."
 )) return;

 localStorage.removeItem("luluExpressJourney");

 location.reload();
}


/* =====================================================
GAME ROUTER
===================================================== */

function launchGame(level){

 switch(level){

  case 1: brokenHearts();break;
  case 2: memoryVault();break;
  case 3: pressureQuiz();break;
  case 4: highRoller();break;
  case 5: mindGames();break;
  case 6: bluff();break;
  case 7: survival();break;
  case 8: admirerRace();break;
  case 9: heartbreakChamber();break;
  case 10: boxing();break;
  case 11: perfectMatch();break;
  case 12: lilianaQuiz();break;
  case 13: reaction();break;
  case 14: heartHunt();break;
  case 15: loveLock();break;
  case 16: cupid();break;
  case 17: countdown();break;
  case 18: ultimateGamble();break;
  case 19: lastStand();break;
  case 20: wordFind();break;
  case 21: sunflower();break;
  case 22: derby();break;
  case 23: finalChallenge();break;

 }
}


/* =====================================================
1. BROKEN HEARTS
===================================================== */

function brokenHearts(){

 let score=0;
 let lives=3;
 let caught=0;
 let time=30;
 let interval;
 let timer;

 const content=
  document.getElementById("gameContent");

 content.innerHTML=`

  <div class="questionBox">

   <h3>Catch the hearts! 💗</h3>

   <p>
    Move the catcher with your finger,
    mouse or arrow keys.
   </p>

   <div>
    ❤️ = points
    <br>
    💔 = lose a life
    <br>
    💛 = bonus
   </div>

   <div class="scoreBox">
    Score: <span id="heartScore">0</span>
    &nbsp; Lives: <span id="heartLives">3</span>
    &nbsp; Time: <span id="heartTime">30</span>
   </div>

  </div>

  <div
   id="heartArea"
   style="
    position:relative;
    height:420px;
    overflow:hidden;
    background:#170912;
    border:1px solid #71314f;
    border-radius:20px;
    touch-action:none;
   "
  >

   <div
    id="catcher"
    style="
     position:absolute;
     bottom:15px;
     left:42%;
     width:80px;
     height:35px;
     background:#ff75ad;
     border-radius:20px;
     box-shadow:0 0 15px rgba(255,117,173,.5);
    "
   ></div>

  </div>
 `;

 const area=document.getElementById("heartArea");
 const catcher=document.getElementById("catcher");

 let catcherX=area.clientWidth*.42;

 function move(x){

  catcherX=
   Math.max(
    0,
    Math.min(
     area.clientWidth-80,
     x-40
    )
   );

  catcher.style.left=
   catcherX+"px";
 }

 function pointer(e){

  const r=area.getBoundingClientRect();

  move(e.clientX-r.left);

 }

 area.addEventListener("pointermove",pointer);

 function key(e){

  if(e.key==="ArrowLeft"||e.key.toLowerCase()==="a")
   move(catcherX-25);

  if(e.key==="ArrowRight"||e.key.toLowerCase()==="d")
   move(catcherX+25);

 }

 window.addEventListener("keydown",key);

 function spawn(){

  const el=document.createElement("div");

  const type=
   Math.random()<.15
    ?"💛"
    :Math.random()<.25
     ?"💔"
     :"❤️";

  el.textContent=type;

  el.style.position="absolute";
  el.style.fontSize="30px";
  el.style.left=
   Math.random()*(area.clientWidth-35)+"px";
  el.style.top="-40px";

  area.appendChild(el);

  let y=-40;

  const speed=3+Math.random()*3;

  function fall(){

   y+=speed;
   el.style.top=y+"px";

   const ex=el.offsetLeft;
   const ey=el.offsetTop;

   const hit=
    ey>area.clientHeight-70 &&
    ex<catcherX+80 &&
    ex+35>catcherX;

   if(hit){

    if(type==="💔"){

     lives--;

     document.getElementById("heartLives")
      .textContent=lives;

     el.remove();

     if(lives<=0)
      finish();

     return;
    }

    const pts=
     type==="💛"?30:10;

    score+=pts;
    caught++;

    document.getElementById("heartScore")
     .textContent=score;

    el.remove();
    return;
   }

   if(y>area.clientHeight){

    if(type==="❤️"){

     lives--;

     document.getElementById("heartLives")
      .textContent=lives;

     if(lives<=0){

      el.remove();
      finish();
      return;
     }
    }

    el.remove();
    return;
   }

   requestAnimationFrame(fall);
  }

  requestAnimationFrame(fall);
 }

 function finish(){

  clearInterval(interval);
  clearInterval(timer);

  window.removeEventListener("keydown",key);

  if(lives>0 && caught>=10){

   passLevel(1,Math.max(100,score));

  }else{

   content.innerHTML=`

    <div class="complete">

     <div class="completeIcon">💔</div>

     <h2>Heartbreak got you!</h2>

     <p>
      You caught ${caught} hearts.
     </p>

     <button
      class="nextBtn"
      onclick="brokenHearts()"
     >
      TRY AGAIN
     </button>

     <br>

     <button
      class="backBtn"
      onclick="returnJourney()"
     >
      ← Journey
     </button>

    </div>

   `;

  }

 }

 interval=setInterval(spawn,650);

 timer=setInterval(()=>{

  time--;

  document.getElementById("heartTime")
   .textContent=time;

  if(time<=0)
   finish();

 },1000);

 activeCleanup=()=>{

  clearInterval(interval);
  clearInterval(timer);
  window.removeEventListener("keydown",key);

 };

}


/* =====================================================
2. MEMORY VAULT
===================================================== */

function memoryVault(){

 let sequence=[];
 let input=[];
 let round=0;
 let accepting=false;

 const content=
  document.getElementById("gameContent");

 content.innerHTML=`

  <div class="questionBox">

   <h3>Memory Vault 🧠</h3>

   <p>
    Watch the glowing tiles.
    Then repeat the exact sequence.
   </p>

   <div class="scoreBox">
    Round <span id="memoryRound">1</span> / 8
   </div>

  </div>

  <div id="memoryGrid" class="memoryGrid"></div>

 `;

 const grid=
  document.getElementById("memoryGrid");

 function create(){

  grid.innerHTML="";

  for(let i=0;i<16;i++){

   const b=
    document.createElement("button");

   b.className="memoryTile";

   b.dataset.i=i;

   b.onclick=()=>clickTile(i);

   grid.appendChild(b);
  }
 }

 function nextRound(){

  round++;

  document.getElementById("memoryRound")
   .textContent=Math.min(round,8);

  input=[];
  accepting=false;

  sequence.push(
   Math.floor(Math.random()*16)
  );

  showSequence();
 }

 async function showSequence(){

  const tiles=
   [...grid.children];

  for(const index of sequence){

   await new Promise(r=>setTimeout(r,300));

   tiles[index].classList.add("show");

   await new Promise(r=>setTimeout(r,550));

   tiles[index].classList.remove("show");

  }

  accepting=true;
 }

 function clickTile(i){

  if(!accepting) return;

  const tiles=
   [...grid.children];

  tiles[i].classList.add("clicked");

  setTimeout(()=>{
   tiles[i].classList.remove("clicked");
  },150);

  if(i!==sequence[input.length]){

   accepting=false;

   content.innerHTML=`

    <div class="complete">

     <div class="completeIcon">🧠💥</div>

     <h2>Vault Locked!</h2>

     <p>
      You reached round ${round}.
     </p>

     <button
      class="nextBtn"
      onclick="memoryVault()"
     >
      TRY AGAIN
     </button>

     <br>

     <button
      class="backBtn"
      onclick="returnJourney()"
     >
      ← Journey
     </button>

    </div>

   `;

   return;
  }

  input.push(i);

  if(input.length===sequence.length){

   accepting=false;

   if(round>=8){

    passLevel(2,250);

   }else{

    setTimeout(nextRound,700);

   }
  }
 }

 create();

 setTimeout(nextRound,500);
}


/* =====================================================
3. PRESSURE QUIZ
===================================================== */

const pressureQuestions=[

 ["What planet is known as the Red Planet?",
  ["Mars","Venus","Jupiter","Mercury"],0],

 ["How many sides does a hexagon have?",
  ["Six","Five","Seven","Eight"],0],

 ["Which ocean is the largest?",
  ["Pacific","Atlantic","Indian","Arctic"],0],

 ["What gas do humans need to breathe?",
  ["Oxygen","Helium","Carbon dioxide","Hydrogen"],0],

 ["Which animal is the largest living mammal?",
  ["Blue whale","Elephant","Giraffe","Orca"],0],

 ["How many minutes are in one hour?",
  ["60","50","90","100"],0],

 ["What is H2O commonly called?",
  ["Water","Salt","Oxygen","Hydrogen"],0],

 ["Which continent is Egypt in?",
  ["Africa","Asia","Europe","South America"],0],

 ["Which instrument has black and white keys?",
  ["Piano","Trumpet","Violin","Flute"],0],

 ["What is the freezing point of water in Celsius?",
  ["0°C","10°C","-10°C","100°C"],0],

 ["Which shape has three sides?",
  ["Triangle","Square","Circle","Pentagon"],0],

 ["What is the closest star to Earth?",
  ["The Sun","Sirius","Polaris","Vega"],0]

];


function shuffleQuestion(q){

 const answers=
  q[1].map((answer,index)=>({
   answer,
   correct:index===q[2]
  }));

 for(let i=answers.length-1;i>0;i--){

  const j=Math.floor(Math.random()*(i+1));

  [answers[i],answers[j]]=
   [answers[j],answers[i]];

 }

 return answers;
}


function pressureQuiz(){

 let questions=
  [...pressureQuestions]
   .sort(()=>Math.random()-.5)
   .slice(0,10);

 let index=0;
 let score=0;
 let timer;

 const content=
  document.getElementById("gameContent");

 function show(){

  if(index>=questions.length){

   passLevel(3,score+100);
   return;
  }

  clearInterval(timer);

  let seconds=7;

  const q=questions[index];
  const answers=shuffleQuestion(q);

  content.innerHTML=`

   <div class="questionBox">

    <div class="timer">
     ⏱️ <span id="quizTimer">7</span>
    </div>

    <h3>${escapeHTML(q[0])}</h3>

   </div>

   <div class="answerGrid">

    ${answers.map((a,i)=>`

     <button
      class="gameBtn"
      data-answer="${a.correct}"
      onclick="window.pressureAnswer(${a.correct})"
     >
      ${String.fromCharCode(65+i)}.
      ${escapeHTML(a.answer)}
     </button>

    `).join("")}

   </div>

   <div class="scoreBox">
    Question ${index+1} / ${questions.length}
   </div>

  `;

  timer=setInterval(()=>{

   seconds--;

   const el=
    document.getElementById("quizTimer");

   if(el) el.textContent=seconds;

   if(seconds<=0){

    clearInterval(timer);
    index++;
    show();

   }

  },1000);

 }

 window.pressureAnswer=function(correct){

  clearInterval(timer);

  if(correct){

   score+=15;

  }

  index++;
  show();

 };

 activeCleanup=()=>{
  clearInterval(timer);
  delete window.pressureAnswer;
 };

 show();
}


/* =====================================================
4. HIGH ROLLER
===================================================== */

function highRoller(){

 const symbols=["🍒","💎","7️⃣","⭐","💗"];

 let spinning=false;
 let stops=0;

 const reels=["r1","r2","r3"];

 const content=
  document.getElementById("gameContent");

 content.innerHTML=`

  <div class="questionBox">

   <h3>High Roller 🎰</h3>

   <p>
    Start the reels, then stop each one.
    Match all three for the jackpot.
   </p>

  </div>

  <div class="slots">

   <div id="r1" class="reel">❔</div>
   <div id="r2" class="reel">❔</div>
   <div id="r3" class="reel">❔</div>

  </div>

  <div style="text-align:center">

   <button
    id="spinBtn"
    class="nextBtn"
    onclick="spinRoller()"
   >
    PULL LEVER 🎰
   </button>

   <div id="stopButtons"></div>

  </div>

 `;

 window.spinRoller=function(){

  if(spinning) return;

  spinning=true;
  stops=0;

  const values=[];

  reels.forEach((id,i)=>{

   const el=document.getElementById(id);

   let ticks=0;

   const interval=setInterval(()=>{

    el.textContent=
     symbols[Math.floor(Math.random()*symbols.length)];

    ticks++;

    if(ticks>=20+i*7){

     clearInterval(interval);

     values[i]=el.textContent;
     stops++;

     if(stops===3){

      spinning=false;

      const unique=
       new Set(values).size;

      let points=100;

      if(unique===1)
       points=500;

      else if(
       values.filter(x=>x==="7️⃣").length>=2
      )
       points=300;

      addPoints(points);

      setTimeout(()=>{

       if(points>=300){

        passLevel(4,0);

       }else{

        document.getElementById("spinBtn")
         .textContent="SPIN AGAIN";

       }

      },500);

     }

    }

   },80);

  });

 };

 activeCleanup=()=>{
  delete window.spinRoller;
 };

}


/* =====================================================
5. MIND GAMES
===================================================== */

function mindGames(){

 const rounds=[

  ["🔴 🔵 🔴 🔵 ?",["🔴","🟢","🟡","🟣"],0],
  ["⭐ ⭐ 🌙 ⭐ ⭐ ?",["🌙","⭐","☀️","💗"],0],
  ["1️⃣ 2️⃣ 3️⃣ 1️⃣ 2️⃣ ?",["3️⃣","4️⃣","1️⃣","5️⃣"],0],
  ["❤️ 💔 ❤️ 💔 ?",["❤️","💔","💛","💙"],0],
  ["🐱 🐶 🐱 🐶 ?",["🐱","🐶","🦊","🐰"],0],
  ["⬆️ ➡️ ⬇️ ⬅️ ?",["⬆️","➡️","⬇️","⬅️"],0]

 ];

 let i=0;
 let points=0;

 const content=
  document.getElementById("gameContent");

 function show(){

  if(i>=rounds.length){

   passLevel(5,points+100);
   return;
  }

  const q=rounds[i];

  content.innerHTML=`

   <div class="questionBox">

    <h2>${q[0]}</h2>

    <p>
     Which symbol completes the pattern?
    </p>

   </div>

   <div class="answerGrid">

    ${q[1].map((a,n)=>`

     <button
      class="gameBtn"
      onclick="mindAnswer(${n})"
     >
      ${a}
     </button>

    `).join("")}

   </div>

   <div class="scoreBox">
    Pattern ${i+1} / ${rounds.length}
   </div>
  `;

 }

 window.mindAnswer=function(n){

  if(n===rounds[i][2])
   points+=25;

  i++;
  show();

 };

 activeCleanup=()=>{
  delete window.mindAnswer;
 };

 show();
}


/* =====================================================
6. BLUFF
===================================================== */

function bluff(){

 let round=0;
 let total=0;

 const content=
  document.getElementById("gameContent");

 function show(){

  if(round>=5){

   if(total>=60)
    passLevel(6,total+100);
   else
    fail();

   return;
  }

  const values=
   Array.from(
    {length:4},
    ()=>Math.floor(Math.random()*20)+1
   );

  content.innerHTML=`

   <div class="questionBox">

    <h3>Round ${round+1} / 5</h3>

    <p>
     Choose one hidden card.
     You may bank it or double the risk.
    </p>

    <strong>
     Current score: ${total}
    </strong>

   </div>

   <div class="cardGrid">

    ${values.map((_,i)=>`

     <button
      class="riskCard"
      onclick="chooseBluff(${values[i]})"
     >
      🃏
     </button>

    `).join("")}

   </div>
  `;

 }

 window.chooseBluff=function(value){

  content.innerHTML=`

   <div class="complete">

    <div class="completeIcon">🃏</div>

    <h2>
     Your card is ${value}
    </h2>

    <p>
     Bank the points or double the risk?
    </p>

    <button
     class="gameBtn"
     onclick="bankBluff(${value})"
    >
     BANK IT 💰
    </button>

    <button
     class="gameBtn"
     onclick="doubleBluff(${value})"
    >
     DOUBLE 🎲
    </button>

   </div>
  `;

 };

 window.bankBluff=function(value){

  total+=value;
  round++;
  show();

 };

 window.doubleBluff=function(value){

  if(Math.random()<.35){

   total=0;
   round++;

  }else{

   total+=value*2;
   round++;

  }

  show();

 };

 function fail(){

  content.innerHTML=`

   <div class="complete">

    <div class="completeIcon">🃏💥</div>

    <h2>The Bluff beat you!</h2>

    <p>
     You need at least 60 points to pass.
    </p>

    <button class="nextBtn" onclick="bluff()">
     TRY AGAIN
    </button>

    <br>

    <button class="backBtn" onclick="returnJourney()">
     ← Journey
    </button>

   </div>
  `;

 }

 activeCleanup=()=>{

  delete window.chooseBluff;
  delete window.bankBluff;
  delete window.doubleBluff;

 };

 show();
}


/* =====================================================
7. SURVIVAL
===================================================== */

function survival(){

 let wave=0;
 let lives=3;

 const hazards=[
  ["🔥","JUMP"],
  ["🪨","DUCK"],
  ["⚡","SHIELD"],
  ["🌊","MOVE"]
 ];

 const content=
  document.getElementById("gameContent");

 function show(){

  if(wave>=8){

   passLevel(7,250);
   return;
  }

  const hazard=
   hazards[Math.floor(Math.random()*hazards.length)];

  const options=
   [...new Set([
    hazard[1],
    "JUMP",
    "DUCK",
    "SHIELD",
    "MOVE"
   ])].slice(0,4)
    .sort(()=>Math.random()-.5);

  content.innerHTML=`

   <div class="questionBox">

    <h2>Wave ${wave+1} / 8</h2>

    <div style="font-size:65px">
     ${hazard[0]}
    </div>

    <p>
     What is your best move?
    </p>

    <strong>
     ❤️ Lives: ${lives}
    </strong>

   </div>

   <div class="answerGrid">

    ${options.map(x=>`

     <button
      class="gameBtn"
      onclick="surviveMove('${x}','${hazard[1]}')"
     >
      ${x}
     </button>

    `).join("")}

   </div>
  `;

 }

 window.surviveMove=function(choice,correct){

  if(choice===correct){

   addPoints(15);
   wave++;
   show();

  }else{

   lives--;

   if(lives<=0){

    content.innerHTML=`

     <div class="complete">

      <div class="completeIcon">🛡️💥</div>

      <h2>You didn't survive!</h2>

      <button class="nextBtn" onclick="survival()">
       TRY AGAIN
      </button>

     </div>
    `;

   }else{

    wave++;
    show();

   }

  }

 };

 activeCleanup=()=>{
  delete window.surviveMove;
 };

 show();
}


/* =====================================================
8. ADMIRER RACE
===================================================== */

function admirerRace(){

 let position=0;
 let distance=0;
 let running=true;
 let obstacleTimer;

 const content=
  document.getElementById("gameContent");

 content.innerHTML=`

  <div class="questionBox">

   <h3>🏇 The Admirer Race</h3>

   <p>
    Move left and right to avoid obstacles.
    Reach 100 metres.
   </p>

   <div class="scoreBox">
    Distance:
    <span id="raceDistance">0</span> / 100
   </div>

  </div>

  <div
   id="raceArea"
   style="
    height:300px;
    position:relative;
    overflow:hidden;
    background:#180b11;
    border:1px solid #71314f;
    border-radius:20px;
    touch-action:none;
   "
  >

   <div
    id="runner"
    style="
     position:absolute;
     bottom:20px;
     left:45%;
     font-size:40px;
    "
   >
    🏇
   </div>

  </div>

  <div style="text-align:center">

   <button class="gameBtn" onclick="raceMove(-1)">
    ◀️ LEFT
   </button>

   <button class="gameBtn" onclick="raceMove(1)">
    RIGHT ▶️
   </button>

  </div>
 `;

 const area=
  document.getElementById("raceArea");

 const runner=
  document.getElementById("runner");

 window.raceMove=function(dir){

  position+=dir*35;

  position=
   Math.max(
    0,
    Math.min(
     area.clientWidth-50,
     position
    )
   );

  runner.style.left=position+"px";
 };

 function spawn(){

  if(!running) return;

  const obstacle=
   document.createElement("div");

  obstacle.textContent=
   Math.random()<.5?"🪨":"💔";

  obstacle.style.position="absolute";
  obstacle.style.top="-40px";
  obstacle.style.left=
   Math.random()*(area.clientWidth-40)+"px";
  obstacle.style.fontSize="35px";

  area.appendChild(obstacle);

  let y=-40;

  function move(){

   if(!running) return;

   y+=4;

   obstacle.style.top=y+"px";

   const ox=obstacle.offsetLeft;
   const oy=obstacle.offsetTop;

   if(
    oy>area.clientHeight-90 &&
    ox<position+50 &&
    ox+35>position
   ){

    running=false;

    content.innerHTML=`

     <div class="complete">

      <div class="completeIcon">💥</div>

      <h2>You crashed!</h2>

      <button class="nextBtn" onclick="admirerRace()">
       TRY AGAIN
      </button>

     </div>
    `;

    return;
   }

   if(y>area.clientHeight){

    obstacle.remove();

    distance+=5;

    document.getElementById("raceDistance")
     .textContent=distance;

    if(distance>=100){

     running=false;
     passLevel(8,250);
     return;

    }

    return;
   }

   requestAnimationFrame(move);
  }

  requestAnimationFrame(move);
 }

 obstacleTimer=setInterval(spawn,700);

 activeCleanup=()=>{
  running=false;
  clearInterval(obstacleTimer);
  delete window.raceMove;
 };

}


/* =====================================================
9. HEARTBREAK CHAMBER
SOLVABLE MAZE
===================================================== */

function heartbreakChamber(){

 const SIZE=13;

 let maze=[];
 let player={x:1,y:1};
 const exit={x:SIZE-2,y:SIZE-2};

 const content=
  document.getElementById("gameContent");

 content.innerHTML=`

  <div class="questionBox">

   <h3>🔎 Heartbreak Chamber</h3>

   <p>
    Find your way through the chamber.
    Reach the 💗 exit.
   </p>

   <p class="mazeHint">
    Use the buttons, arrow keys or WASD.
   </p>

  </div>

  <div class="mazeWrap">

   <div id="maze" class="maze"></div>

   <div class="mazeControls">

    <div></div>

    <button onclick="moveMaze(0,-1)">
     ▲
    </button>

    <div></div>

    <button onclick="moveMaze(-1,0)">
     ◀
    </button>

    <button onclick="moveMaze(0,1)">
     ▼
    </button>

    <button onclick="moveMaze(1,0)">
     ▶
    </button>

   </div>

   <button class="backBtn" onclick="returnJourney()">
    ← Journey
   </button>

  </div>

 `;

 const mazeElement=
  document.getElementById("maze");


 /*
  IMPORTANT:
  The maze is generated by starting with every
  cell as a wall and carving passages.

  This means there is ALWAYS a connected route
  between the start and exit.
 */

 function generateMaze(){

  maze=
   Array.from(
    {length:SIZE},
    ()=>Array(SIZE).fill(1)
   );

  function carve(x,y){

   maze[y][x]=0;

   const dirs=[
    [2,0],
    [-2,0],
    [0,2],
    [0,-2]
   ].sort(()=>Math.random()-.5);

   for(const [dx,dy] of dirs){

    const nx=x+dx;
    const ny=y+dy;

    if(
     nx>0 &&
     nx<SIZE-1 &&
     ny>0 &&
     ny<SIZE-1 &&
     maze[ny][nx]===1
    ){

     maze[y+dy/2][x+dx/2]=0;

     carve(nx,ny);

    }

   }

  }

  carve(1,1);

  /*
   Guarantee the exit is open and connected.
  */

  maze[exit.y][exit.x]=0;

  maze[SIZE-2][SIZE-3]=0;
  maze[SIZE-3][SIZE-2]=0;

 }

 function render(){

  mazeElement.innerHTML="";

  for(let y=0;y<SIZE;y++){

   for(let x=0;x<SIZE;x++){

    const cell=
     document.createElement("div");

    cell.className="mazeCell";

    if(maze[y][x]===1)
     cell.classList.add("wall");

    if(x===1&&y===1)
     cell.classList.add("start");

    if(x===exit.x&&y===exit.y)
     cell.classList.add("exit");

    if(
     x===player.x &&
     y===player.y
    ){

     cell.innerHTML=
      `<div class="player"></div>`;

    }

    if(
     x===exit.x &&
     y===exit.y
    ){

     cell.innerHTML+=
      `<div class="exitMark">💗</div>`;

    }

    mazeElement.appendChild(cell);

   }

  }

 }

 window.moveMaze=function(dx,dy){

  const nx=player.x+dx;
  const ny=player.y+dy;

  if(
   nx<0 ||
   ny<0 ||
   nx>=SIZE ||
   ny>=SIZE
  )
   return;

  if(maze[ny][nx]===1)
   return;

  player.x=nx;
  player.y=ny;

  render();

  if(
   player.x===exit.x &&
   player.y===exit.y
  ){

   passLevel(9,350);

  }

 };

 function keyboard(e){

  const key=e.key.toLowerCase();

  if(
   key==="arrowup"||
   key==="w"
  )
   moveMaze(0,-1);

  else if(
   key==="arrowdown"||
   key==="s"
  )
   moveMaze(0,1);

  else if(
   key==="arrowleft"||
   key==="a"
  )
   moveMaze(-1,0);

  else if(
   key==="arrowright"||
   key==="d"
  )
   moveMaze(1,0);

 }

 generateMaze();
 render();

 window.addEventListener("keydown",keyboard);

 activeCleanup=()=>{

  window.removeEventListener(
   "keydown",
   keyboard
  );

  delete window.moveMaze;

 };

}


/* =====================================================
10. BOXING
===================================================== */

function boxing(){

 let playerHP=100;
 let enemyHP=100;
 let defending=false;
 let enemyTimer;

 const content=
  document.getElementById("gameContent");

 content.innerHTML=`

  <div class="fighterArena">

   <h3>🥊 Heartbreak Boxing Match</h3>

   <p>
    Defeat the opponent before they defeat you.
   </p>

   <p>Opponent</p>

   <div class="healthBar">
    <div id="enemyHP" class="healthFill"></div>
   </div>

   <p>You</p>

   <div class="healthBar">
    <div
     id="playerHP"
     class="healthFill"
    ></div>
   </div>

   <div>

    <button class="gameBtn" onclick="boxMove('punch')">
     👊 Punch
    </button>

    <button class="gameBtn" onclick="boxMove('heavy')">
     💥 Heavy
    </button>

    <button class="gameBtn" onclick="boxMove('block')">
     🛡️ Block
    </button>

    <button class="gameBtn" onclick="boxMove('dodge')">
     💨 Dodge
    </button>

   </div>

   <p id="boxingMessage"></p>

  </div>
 `;

 function update(){

  document.getElementById("enemyHP")
   .style.width=
   Math.max(0,enemyHP)+"%";

  document.getElementById("playerHP")
   .style.width=
   Math.max(0,playerHP)+"%";

 }

 window.boxMove=function(move){

  if(enemyHP<=0||playerHP<=0)
   return;

  let damage=0;

  if(move==="punch")
   damage=10;

  if(move==="heavy")
   damage=20;

  if(move==="dodge")
   damage=0;

  if(move==="block")
   defending=true;

  enemyHP-=damage;

  if(enemyHP<=0){

   clearInterval(enemyTimer);
   passLevel(10,300);
   return;

  }

  if(Math.random()<.65){

   let enemyDamage=
    Math.floor(Math.random()*14)+7;

   if(defending)
    enemyDamage=Math.floor(enemyDamage*.35);

   if(move==="dodge")
    enemyDamage=0;

   playerHP-=enemyDamage;

  }

  defending=false;

  update();

  if(playerHP<=0){

   clearInterval(enemyTimer);

   content.innerHTML=`

    <div class="complete">

     <div class="completeIcon">🥊💥</div>

     <h2>You lost!</h2>

     <button class="nextBtn" onclick="boxing()">
      REMATCH
     </button>

    </div>
   `;

  }

 };

 activeCleanup=()=>{

  clearInterval(enemyTimer);
  delete window.boxMove;

 };

 update();
}


/* =====================================================
11. PERFECT MATCH
===================================================== */

function perfectMatch(){

 const pairs=[
  ["🌻","🌻"],
  ["🐬","🐬"],
  ["🌹","🌹"],
  ["💗","💗"],
  ["⭐","⭐"]
 ];

 let matched=0;
 let dragging=null;

 const content=
  document.getElementById("gameContent");

 content.innerHTML=`

  <div class="questionBox">

   <h3>🧲 The Perfect Match</h3>

   <p>
    Drag each object onto its matching target.
   </p>

  </div>

  <div id="matchBoard" class="matchBoard"></div>

 `;

 const board=
  document.getElementById("matchBoard");

 const objects=
  pairs.map((p,i)=>({
   symbol:p[0],
   id:i
  }));

 const shuffled=
  [...objects].sort(()=>Math.random()-.5);

 shuffled.forEach(obj=>{

  const item=
   document.createElement("div");

  item.className="matchItem";
  item.textContent=obj.symbol;
  item.draggable=true;
  item.dataset.id=obj.id;

  item.addEventListener(
   "dragstart",
   ()=>dragging=obj.id
  );

  item.addEventListener(
   "pointerdown",
   ()=>{
    dragging=obj.id;
   }
  );

  board.appendChild(item);

 });

 pairs.forEach((p,i)=>{

  const target=
   document.createElement("div");

  target.className="matchTarget";
  target.textContent="DROP";
  target.dataset.id=i;

  target.addEventListener(
   "dragover",
   e=>e.preventDefault()
  );

  target.addEventListener(
   "drop",
   ()=>{
    if(String(dragging)===target.dataset.id)
     success(target,dragging);
   }
  );

  target.addEventListener(
   "pointerup",
   ()=>{
    if(String(dragging)===target.dataset.id)
     success(target,dragging);
   }
  );

  board.appendChild(target);

 });

 function success(target,id){

  if(target.dataset.done)
   return;

  target.dataset.done="1";
  target.textContent=pairs[id][0];
  target.style.background="#3c1830";

  const item=
   [...board.querySelectorAll(".matchItem")]
    .find(x=>x.dataset.id===String(id));

  if(item)
   item.style.display="none";

  matched++;

  if(matched===pairs.length)
   passLevel(11,300);

 }

}


/* =====================================================
12. LILIANA QUIZ
===================================================== */

const lilianaQuestions=[

 ["What is Liliana's favourite colour?",
  ["Baby pink","Purple","Burgundy","Sky blue"],0],

 ["What is Liliana's favourite number?",
  ["3","7","5","9"],0],

 ["Which food does Liliana like?",
  ["Sushi","Tacos","Pizza","Pasta"],0],

 ["Which animal does Liliana like?",
  ["Dolphins","Penguins","Tigers","Koalas"],0],

 ["Which flower is one of Liliana's favourites?",
  ["Sunflowers","Tulips","Lilies","Daisies"],0],

 ["Which other flower does Liliana like?",
  ["Roses","Orchids","Lavender","Peonies"],0],

 ["What month is Liliana's birthday?",
  ["July","June","August","May"],0],

 ["What day is Liliana's birthday?",
  ["22","12","27","7"],0],

 ["What colour are Liliana's eyes?",
  ["Green","Blue","Brown","Grey"],0],

 ["What is Liliana's star sign?",
  ["Leo","Cancer","Virgo","Gemini"],0],

 ["What is Liliana afraid of?",
  ["Drowning","Flying","Heights","Spiders"],0],

 ["What is Liliana's favourite movie?",
  ["Me Before You","Titanic","The Notebook","Frozen"],0],

 ["What subject did Liliana study?",
  ["Psychology","Law","Biology","Art"],0],

 ["How many nieces does Liliana have?",
  ["1","2","3","4"],0],

 ["How many nephews does Liliana have?",
  ["4","2","5","3"],0],

 ["How many siblings does Liliana have?",
  ["5","3","4","6"],0],

 ["How many piercings does Liliana have?",
  ["4","2","3","5"],0],

 ["What are Liliana's dogs called?",
  ["Aayla and Arlo","Luna and Milo","Bella and Max","Ayla and Leo"],0],

 ["What does Liliana enjoy?",
  ["Poetry","Car racing","Fishing","Chess"],0],

 ["What does Liliana like listening to?",
  ["Sad songs","Only classical music","Only country music","Opera"],0]

];


function lilianaQuiz(){

 let qs=
  [...lilianaQuestions]
   .sort(()=>Math.random()-.5)
   .slice(0,12);

 let index=0;
 let score=0;

 const content=
  document.getElementById("gameContent");

 function show(){

  if(index>=qs.length){

   passLevel(12,score+100);
   return;
  }

  const q=qs[index];
  const answers=shuffleQuestion(q);

  content.innerHTML=`

   <div class="questionBox">

    <h3>${escapeHTML(q[0])}</h3>

   </div>

   <div class="answerGrid">

    ${answers.map((a,i)=>`

     <button
      class="gameBtn"
      onclick="luluAnswer(${a.correct})"
     >
      ${String.fromCharCode(65+i)}.
      ${escapeHTML(a.answer)}
     </button>

    `).join("")}

   </div>

   <div class="scoreBox">
    ${index+1} / ${qs.length}
   </div>

  `;

 }

 window.luluAnswer=function(correct){

  if(correct)
   score+=20;

  index++;
  show();

 };

 activeCleanup=()=>{
  delete window.luluAnswer;
 };

 show();
}


/* =====================================================
13. REACTION GAUNTLET
===================================================== */

function reaction(){

 let round=0;
 let points=0;
 let startTime;
 let timeout;

 const content=
  document.getElementById("gameContent");

 function next(){

  if(round>=10){

   passLevel(13,points+100);
   return;
  }

  const wait=
   700+Math.random()*1800;

  content.innerHTML=`

   <div class="questionBox">

    <h3>⚡ Round ${round+1} / 10</h3>

    <p>
     Wait for the command...
    </p>

    <div
     id="reactionTarget"
     style="
      height:220px;
      display:flex;
      align-items:center;
      justify-content:center;
      border-radius:20px;
      background:#1a0b12;
      font-size:30px;
     "
    >
     WAIT
    </div>

   </div>
  `;

  const target=
   document.getElementById("reactionTarget");

  let ready=false;

  const delay=
   setTimeout(()=>{

    ready=true;
    startTime=performance.now();

    target.textContent="TAP NOW! ⚡";
    target.style.background="#71314f";

   },wait);

  timeout=setTimeout(()=>{

   if(!ready){

    clearTimeout(delay);
    round++;

    target.textContent="TOO SLOW!";

    setTimeout(next,500);

   }

  },wait+1700);

  target.onclick=()=>{

   if(!ready){

    clearTimeout(delay);
    clearTimeout(timeout);

    round++;

    setTimeout(next,400);

    return;
   }

   clearTimeout(timeout);

   const reactionTime=
    performance.now()-startTime;

   points+=
    Math.max(
     5,
     Math.floor(35-reactionTime/20)
    );

   round++;

   setTimeout(next,300);

  };

 }

 activeCleanup=()=>{
  clearTimeout(timeout);
 };

 next();
}


/* =====================================================
14. HEART HUNT
===================================================== */

function heartHunt(){

 let found=0;
 let timer;
 let hearts=[];

 const content=
  document.getElementById("gameContent");

 content.innerHTML=`

  <div class="questionBox">

   <h3>🕵️ The Heart Hunt</h3>

   <p>
    Find 12 hidden hearts before time runs out.
   </p>

   <div class="scoreBox">
    Found:
    <span id="foundHearts">0</span> / 12
    &nbsp;
    Time:
    <span id="huntTime">30</span>
   </div>

  </div>

  <div id="huntArea" class="huntArea"></div>
 `;

 const area=
  document.getElementById("huntArea");

 for(let i=0;i<12;i++){

  const heart=
   document.createElement("div");

  heart.className="huntHeart";
  heart.textContent=
   Math.random()<.25?"💗":"❤️";

  heart.style.left=
   Math.random()*90+"%";

  heart.style.top=
   Math.random()*88+"%";

  heart.onclick=()=>{

   if(heart.dataset.found)
    return;

   heart.dataset.found="1";
   heart.style.transform="scale(1.6)";
   heart.style.opacity="0";

   found++;

   document.getElementById("foundHearts")
    .textContent=found;

   if(found>=12){

    clearInterval(timer);
    passLevel(14,300);

   }

  };

  area.appendChild(heart);
  hearts.push(heart);

 }

 let seconds=30;

 timer=setInterval(()=>{

  seconds--;

  document.getElementById("huntTime")
   .textContent=seconds;

  if(seconds<=0 && found<12){

   clearInterval(timer);

   content.innerHTML=`

    <div class="complete">

     <div class="completeIcon">🕵️</div>

     <h2>The hearts escaped!</h2>

     <p>
      You found ${found} / 12.
     </p>

     <button class="nextBtn" onclick="heartHunt()">
      TRY AGAIN
     </button>

    </div>
   `;

  }

 },1000);

 activeCleanup=()=>{
  clearInterval(timer);
 };

}


/* =====================================================
15. LOVE LOCK
===================================================== */

function loveLock(){

 let entered="";

 const code="060722";

 const content=
  document.getElementById("gameContent");

 function render(){

  content.innerHTML=`

   <div class="questionBox">

    <h3>🔐 Love Lock</h3>

    <p>
     Crack the six digit combination.
    </p>

    <p>
     💡 Clues:
     <br>
     Years of friendship + birthday month + birthday day
    </p>

    <div
     style="
      font-size:28px;
      letter-spacing:7px;
      margin:15px;
     "
    >
     ${entered.replace(/./g,"●")}
    </div>

   </div>

   <div
    style="
     display:grid;
     grid-template-columns:repeat(3,1fr);
     max-width:350px;
     margin:auto;
    "
   >

    ${[1,2,3,4,5,6,7,8,9,0].map(n=>`

     <button
      class="gameBtn"
      onclick="lockNumber(${n})"
     >
      ${n}
     </button>

    `).join("")}

   </div>

   <div style="text-align:center">

    <button
     class="gameBtn"
     onclick="lockClear()"
    >
     CLEAR
    </button>

    <button
     class="nextBtn"
     onclick="lockCheck()"
    >
     UNLOCK 🔐
    </button>

   </div>
  `;

 }

 window.lockNumber=function(n){

  if(entered.length<6)
   entered+=n;

  render();

 };

 window.lockClear=function(){

  entered="";
  render();

 };

 window.lockCheck=function(){

  if(entered===code){

   passLevel(15,350);

  }else{

   entered="";
   render();

   const p=
    document.createElement("p");

   p.textContent="Wrong combination 💔";

   p.style.color="#ff657c";

   content.querySelector(".questionBox")
    .appendChild(p);

  }

 };

 activeCleanup=()=>{

  delete window.lockNumber;
  delete window.lockClear;
  delete window.lockCheck;

 };

 render();
}


/* =====================================================
16. CUPID SHOOTOUT
===================================================== */

function cupid(){

 let hits=0;
 let shots=15;
 let timer;

 const content=
  document.getElementById("gameContent");

 content.innerHTML=`

  <div class="questionBox">

   <h3>🏹 Cupid Shootout</h3>

   <p>
    Hit 8 moving hearts with 15 arrows.
   </p>

   <div class="scoreBox">
    Hits:
    <span id="cupidHits">0</span> / 8
    &nbsp;
    Arrows:
    <span id="cupidShots">15</span>
   </div>

  </div>

  <div id="shootArea" class="shootArea"></div>
 `;

 const area=
  document.getElementById("shootArea");

 function spawn(){

  if(shots<=0||hits>=8)
   return;

  const target=
   document.createElement("div");

  target.className="target";
  target.textContent=
   Math.random()<.2?"💛":"💗";

  target.style.left=
   Math.random()*88+"%";

  target.style.top=
   Math.random()*85+"%";

  target.onclick=()=>{

   hits++;

   target.remove();

   document.getElementById("cupidHits")
    .textContent=hits;

   if(hits>=8){

    clearInterval(timer);
    passLevel(16,350);

   }else{

    spawn();

   }

  };

  area.appendChild(target);

 }

 area.onclick=e=>{

  if(e.target.classList.contains("target"))
   return;

  shots--;

  document.getElementById("cupidShots")
   .textContent=shots;

  if(shots<=0 && hits<8){

   clearInterval(timer);

   content.innerHTML=`

    <div class="complete">

     <div class="completeIcon">🏹💔</div>

     <h2>Out of arrows!</h2>

     <p>
      You hit ${hits} / 8 hearts.
     </p>

     <button class="nextBtn" onclick="cupid()">
      TRY AGAIN
     </button>

    </div>
   `;

  }

 };

 for(let i=0;i<4;i++)
  spawn();

 timer=setInterval(()=>{

  [...area.children].forEach(t=>{

   t.style.left=
    Math.random()*88+"%";

   t.style.top=
    Math.random()*85+"%";

  });

 },700);

 activeCleanup=()=>{
  clearInterval(timer);
 };

}


/* =====================================================
17. COUNTDOWN
===================================================== */

function countdown(){

 let round=0;
 let points=0;

 const content=
  document.getElementById("gameContent");

 const gamesMini=[
  "tap",
  "number",
  "stop"
 ];

 function next(){

  if(round>=6){

   passLevel(17,points+100);
   return;

  }

  const type=
   gamesMini[
    Math.floor(Math.random()*gamesMini.length)
   ];

  if(type==="tap")
   tapGame();

  if(type==="number")
   numberGame();

  if(type==="stop")
   stopGame();

 }

 function tapGame(){

  let taps=0;
  let time=5;

  content.innerHTML=`

   <div class="questionBox">

    <h3>⏳ Tap Challenge</h3>

    <p>
     Tap the button 12 times!
    </p>

    <div class="timer">
     ${time}
    </div>

    <button
     id="tapButton"
     class="nextBtn"
    >
     TAP! 💗
    </button>

   </div>
  `;

  const btn=
   document.getElementById("tapButton");

  btn.onclick=()=>{

   taps++;
   btn.textContent=
    `TAP! 💗 ${taps}`;

   if(taps>=12){

    points+=25;
    round++;
    setTimeout(next,300);

   }

  };

  const t=setInterval(()=>{

   time--;

   if(time<=0){

    clearInterval(t);

    if(taps<12)
     round++;

    setTimeout(next,300);

   }

  },1000);

  activeCleanup=()=>clearInterval(t);

 }

 function numberGame(){

  const nums=
   [1,2,3,4]
    .sort(()=>Math.random()-.5);

  let nextNumber=1;

  content.innerHTML=`

   <div class="questionBox">

    <h3>⏳ Number Order</h3>

    <p>
     Tap 1, 2, 3, 4 in order.
    </p>

   </div>

   <div class="answerGrid">

    ${nums.map(n=>`

     <button
      class="gameBtn"
      onclick="countNumber(${n})"
     >
      ${n}
     </button>

    `).join("")}

   </div>
  `;

  window.countNumber=function(n){

   if(n===nextNumber){

    nextNumber++;

    if(nextNumber===5){

     points+=25;
     round++;
     delete window.countNumber;
     setTimeout(next,300);

    }

   }else{

    round++;
    delete window.countNumber;
    setTimeout(next,300);

   }

  };

 }

 function stopGame(){

  let position=0;
  let direction=1;
  let stopped=false;

  content.innerHTML=`

   <div class="questionBox">

    <h3>⏳ Stop The Bar</h3>

    <p>
     Stop the marker inside the pink zone.
    </p>

    <div
     style="
      position:relative;
      height:45px;
      background:#10070c;
      border-radius:15px;
      overflow:hidden;
     "
    >

     <div
      style="
       position:absolute;
       left:40%;
       width:20%;
       height:100%;
       background:#71314f;
      "
     ></div>

     <div
      id="stopMarker"
      style="
       position:absolute;
       width:10px;
       height:100%;
       background:#ffd76a;
      "
     ></div>

    </div>

    <button
     class="nextBtn"
     onclick="stopBar()"
    >
     STOP!
    </button>

   </div>
  `;

  const marker=
   document.getElementById("stopMarker");

  const interval=setInterval(()=>{

   if(stopped) return;

   position+=direction*2;

   if(position>=98){

    position=98;
    direction=-1;

   }

   if(position<=0){

    position=0;
    direction=1;

   }

   marker.style.left=position+"%";

  },20);

  window.stopBar=function(){

   stopped=true;
   clearInterval(interval);

   if(position>=40&&position<=60)
    points+=30;

   round++;

   delete window.stopBar;

   setTimeout(next,300);

  };

  activeCleanup=()=>clearInterval(interval);

 }

 next();
}


/* =====================================================
18. ULTIMATE GAMBLE
===================================================== */

function ultimateGamble(){

 let pot=100;
 let turns=0;

 const content=
  document.getElementById("gameContent");

 function render(){

  content.innerHTML=`

   <div class="questionBox">

    <h3>🎲 The Ultimate Gamble</h3>

    <p>
     Starting pot: <strong>100</strong>
    </p>

    <div style="
     font-size:40px;
     color:#ffd76a;
     margin:15px;
    ">
     💰 ${pot}
    </div>

    <p>
     Turn ${turns}
    </p>

   </div>

   <div style="text-align:center">

    <button
     class="gameBtn"
     onclick="gamble(1.5)"
    >
     1.5×
    </button>

    <button
     class="gameBtn"
     onclick="gamble(2)"
    >
     2×
    </button>

    <button
     class="gameBtn"
     onclick="cashOut()"
    >
     CASH OUT 💰
    </button>

   </div>
  `;

 }

 window.gamble=function(multiplier){

  turns++;

  if(Math.random()<.25){

   pot=0;

   content.innerHTML=`

    <div class="complete">

     <div class="completeIcon">💥🎲</div>

     <h2>BUST!</h2>

     <p>
      Your gamble wiped out the pot.
     </p>

     <button class="nextBtn" onclick="ultimateGamble()">
      TRY AGAIN
     </button>

    </div>
   `;

   return;

  }

  pot=Math.floor(pot*multiplier);

  render();

 };

 window.cashOut=function(){

  if(pot>=250){

   passLevel(18,pot);

  }else{

   content.innerHTML=`

    <div class="complete">

     <div class="completeIcon">🎲</div>

     <h2>Not enough!</h2>

     <p>
      You need at least 250 in the pot
      to pass.
     </p>

     <button class="nextBtn" onclick="ultimateGamble()">
      TRY AGAIN
     </button>

    </div>
   `;

  }

 };

 activeCleanup=()=>{

  delete window.gamble;
  delete window.cashOut;

 };

 render();
}


/* =====================================================
19. LAST STAND
===================================================== */

function lastStand(){

 let boss=150;
 let player=100;
 let phase=1;

 const content=
  document.getElementById("gameContent");

 function render(){

  if(boss<=0){

   passLevel(19,400);
   return;

  }

  if(player<=0){

   content.innerHTML=`

    <div class="complete">

     <div class="completeIcon">👑💥</div>

     <h2>The Admirer Won!</h2>

     <button class="nextBtn" onclick="lastStand()">
      TRY AGAIN
     </button>

    </div>
   `;

   return;

  }

  phase=
   boss<=50?3:
   boss<=100?2:1;

  content.innerHTML=`

   <div class="fighterArena">

    <h3>
     👑 The Admirer's Last Stand
    </h3>

    <p>
     Phase ${phase}
    </p>

    <p>
     Boss: ${boss} HP
    </p>

    <div class="healthBar">
     <div
      class="healthFill"
      style="width:${Math.max(0,boss/150*100)}%"
     ></div>
    </div>

    <p>
     You: ${player} HP
    </p>

    <div class="healthBar">
     <div
      class="healthFill"
      style="width:${player}%"
     ></div>
    </div>

    <button
     class="gameBtn"
     onclick="standMove('attack')"
    >
     ⚔️ Attack
    </button>

    <button
     class="gameBtn"
     onclick="standMove('guard')"
    >
     🛡️ Guard
    </button>

    <button
     class="gameBtn"
     onclick="standMove('special')"
    >
     💥 Special
    </button>

    <p id="standMessage"></p>

   </div>
  `;

 }

 window.standMove=function(move){

  let damage=0;

  if(move==="attack")
   damage=12;

  if(move==="special")
   damage=Math.random()<.7?25:0;

  boss-=damage;

  if(boss<=0){

   render();
   return;

  }

  let enemyDamage;

  if(phase===1)
   enemyDamage=10;
  else if(phase===2)
   enemyDamage=15;
  else
   enemyDamage=20;

  if(move==="guard")
   enemyDamage=Math.floor(enemyDamage*.3);

  if(move==="special" && Math.random()<.25)
   enemyDamage=0;

  player-=enemyDamage;

  render();

 };

 activeCleanup=()=>{
  delete window.standMove;
 };

 render();
}


/* =====================================================
20. WORD FIND
===================================================== */

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


function wordFind(){

 const size=12;

 let grid=
  Array.from(
   {length:size},
   ()=>Array(size).fill("")
  );

 let placements=[];

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

 function canPlace(word,x,y,dx,dy){

  for(let i=0;i<word.length;i++){

   const nx=x+dx*i;
   const ny=y+dy*i;

   if(
    nx<0||
    ny<0||
    nx>=size||
    ny>=size
   )
    return false;

   if(
    grid[ny][nx] &&
    grid[ny][nx]!==word[i]
   )
    return false;

  }

  return true;
 }

 function place(word){

  for(let attempt=0;attempt<1000;attempt++){

   const dir=
    directions[
     Math.floor(Math.random()*directions.length)
    ];

   const x=
    Math.floor(Math.random()*size);

   const y=
    Math.floor(Math.random()*size);

   if(canPlace(word,x,y,dir[0],dir[1])){

    for(let i=0;i<word.length;i++){

     grid[
      y+dir[1]*i
     ][
      x+dir[0]*i
     ]=word[i];

    }

    placements.push({
     word,
     x,
     y,
     dx:dir[0],
     dy:dir[1]
    });

    return true;
   }

  }

  return false;
 }

 /*
  Longer words first makes the generator
  much more reliable.
 */
 [...wordList]
  .sort((a,b)=>b.length-a.length)
  .forEach(place);

 const letters="ABCDEFGHIJKLMNOPQRSTUVWXYZ";

 for(let y=0;y<size;y++)
  for(let x=0;x<size;x++)
   if(!grid[y][x])
    grid[y][x]=
     letters[Math.floor(Math.random()*26)];

 let found=new Set();
 let selecting=null;

 const content=
  document.getElementById("gameContent");

 content.innerHTML=`

  <div class="questionBox">

   <h3>🔎 Liliana's Word Find</h3>

   <p>
    Drag from the first letter to the last letter
    of a word.
   </p>

   <div class="scoreBox">
    Found:
    <span id="wordFound">0</span> / ${placements.length}
   </div>

  </div>

  <div id="wordGrid" class="wordGrid"></div>

  <div id="wordList" class="wordList"></div>

 `;

 const wordGrid=
  document.getElementById("wordGrid");

 const list=
  document.getElementById("wordList");

 function cellIndex(x,y){

  return y*size+x;

 }

 for(let y=0;y<size;y++){

  for(let x=0;x<size;x++){

   const cell=
    document.createElement("div");

   cell.className="wordCell";
   cell.textContent=grid[y][x];

   cell.dataset.x=x;
   cell.dataset.y=y;

   cell.addEventListener(
    "pointerdown",
    e=>{
     e.preventDefault();
     selecting={
      x,
      y
     };
    }
   );

   cell.addEventListener(
    "pointerenter",
    ()=>{
     if(selecting)
      highlightTemporary(
       selecting.x,
       selecting.y,
       x,
       y
      );
   }
   );

   cell.addEventListener(
    "pointerup",
    ()=>{
     if(!selecting) return;

     checkSelection(
      selecting.x,
      selecting.y,
      x,
      y
     );

     selecting=null;
     clearTemporary();
    }
   );

   wordGrid.appendChild(cell);

  }

 }

 wordGrid.addEventListener(
  "pointerleave",
  ()=>{
   clearTemporary();
  }
 );

 wordList.innerHTML=
  wordList.map(word=>`

   <span
    class="wordTag"
    data-word="${word}"
   >
    ${word}
   </span>

  `).join("");

 function cellsBetween(x1,y1,x2,y2){

  const dx=Math.sign(x2-x1);
  const dy=Math.sign(y2-y1);

  const length=
   Math.max(
    Math.abs(x2-x1),
    Math.abs(y2-y1)
   )+1;

  if(
   x1+dx*(length-1)!==x2||
   y1+dy*(length-1)!==y2
  )
   return [];

  return Array.from(
   {length},
   (_,i)=>({
    x:x1+dx*i,
    y:y1+dy*i
   })
  );

 }

 function highlightTemporary(
  x1,y1,x2,y2
 ){

  clearTemporary();

  const cells=
   cellsBetween(x1,y1,x2,y2);

  cells.forEach(c=>{

   const cell=
    wordGrid.children[
     cellIndex(c.x,c.y)
    ];

   if(cell)
    cell.style.background="#71314f";

  });

 }

 function clearTemporary(){

  [...wordGrid.children].forEach(c=>{

   if(!c.classList.contains("found"))
    c.style.background="";

  });

 }

 function checkSelection(x1,y1,x2,y2){

  const cells=
   cellsBetween(x1,y1,x2,y2);

  if(!cells.length)
   return;

  const text=
   cells.map(c=>grid[c.y][c.x]).join("");

  const reverse=
   text.split("").reverse().join("");

  const match=
   placements.find(p=>
    !found.has(p.word)&&
    (p.word===text||p.word===reverse)
   );

  if(!match)
   return;

  found.add(match.word);

  cells.forEach(c=>{

   const cell=
    wordGrid.children[
     cellIndex(c.x,c.y)
    ];

   cell.classList.add("found");

  });

  const tag=
   list.querySelector(
    `[data-word="${match.word}"]`
   );

  if(tag)
   tag.classList.add("found");

  document.getElementById("wordFound")
   .textContent=found.size;

  if(found.size===placements.length)
   passLevel(20,500);

 }

}


/* =====================================================
21. SUNFLOWER
===================================================== */

function sunflower(){

 const content=
  document.getElementById("gameContent");

 content.innerHTML=`

  <div class="questionBox">

   <h3>🌻 Draw a Sunflower</h3>

   <p>
    Draw your own sunflower.
    Your drawing does not need to be perfect.
   </p>

  </div>

  <div class="canvasWrap">

   <canvas
    id="sunflowerCanvas"
    width="650"
    height="430"
   ></canvas>

   <div class="tools">

    <button onclick="setBrush(3)">
     Small
    </button>

    <button onclick="setBrush(7)">
     Medium
    </button>

    <button onclick="setBrush(13)">
     Large
    </button>

    <button onclick="undoDrawing()">
     Undo
    </button>

    <button onclick="clearDrawing()">
     Clear
    </button>

   </div>

   <button
    class="nextBtn"
    onclick="finishSunflower()"
   >
    FINISH SUNFLOWER 🌻
   </button>

  </div>
 `;

 const canvas=
  document.getElementById("sunflowerCanvas");

 const ctx=
  canvas.getContext("2d");

 ctx.lineWidth=7;
 ctx.lineCap="round";
 ctx.strokeStyle="#8b355a";

 let drawing=false;
 let strokes=0;
 let history=[];

 function position(e){

  const r=
   canvas.getBoundingClientRect();

  return {
   x:(e.clientX-r.left)*
    canvas.width/r.width,

   y:(e.clientY-r.top)*
    canvas.height/r.height
  };

 }

 canvas.addEventListener(
  "pointerdown",
  e=>{

   drawing=true;
   strokes++;

   const p=position(e);

   ctx.beginPath();
   ctx.moveTo(p.x,p.y);

   history.push(
    ctx.getImageData(
     0,
     0,
     canvas.width,
     canvas.height
    )
   );

  }
 );

 canvas.addEventListener(
  "pointermove",
  e=>{

   if(!drawing) return;

   const p=position(e);

   ctx.lineTo(p.x,p.y);
   ctx.stroke();

  }
 );

 canvas.addEventListener(
  "pointerup",
  ()=>{
   drawing=false;
  }
 );

 canvas.addEventListener(
  "pointercancel",
  ()=>{
   drawing=false;
  }
 );

 window.setBrush=function(size){

  ctx.lineWidth=size;

 };

 window.undoDrawing=function(){

  if(history.length){

   const previous=
    history.pop();

   ctx.putImageData(previous,0,0);

  }

 };

 window.clearDrawing=function(){

  ctx.clearRect(
   0,
   0,
   canvas.width,
   canvas.height
  );

  history=[];

 };

 window.finishSunflower=function(){

  if(strokes<5){

   alert(
    "Add a few more strokes to your sunflower 🌻"
   );

   return;

  }

  passLevel(
   21,
   Math.min(400,100+strokes*5)
  );

 };

 activeCleanup=()=>{

  delete window.setBrush;
  delete window.undoDrawing;
  delete window.clearDrawing;
  delete window.finishSunflower;

 };

}


/* =====================================================
22. LULU DERBY
100 RANDOM TRIVIA QUESTIONS
===================================================== */

const derbyQuestions=[

["What is the capital of France?",["Paris","Rome","Madrid","Berlin"],0],
["Which planet is closest to the Sun?",["Mercury","Venus","Mars","Earth"],0],
["How many continents are there?",["Seven","Six","Eight","Five"],0],
["Which animal is known as the king of the jungle?",["Lion","Tiger","Leopard","Jaguar"],0],
["What is the largest ocean?",["Pacific","Atlantic","Indian","Arctic"],0],
["Which country is famous for the pyramids of Giza?",["Egypt","Greece","Mexico","Peru"],0],
["How many legs does a spider have?",["Eight","Six","Ten","Twelve"],0],
["Which gas do plants absorb?",["Carbon dioxide","Oxygen","Nitrogen","Helium"],0],
["What is the largest planet?",["Jupiter","Saturn","Neptune","Earth"],0],
["Which bird cannot fly?",["Penguin","Eagle","Falcon","Sparrow"],0],
["What is the capital of Japan?",["Tokyo","Kyoto","Osaka","Nagoya"],0],
["Which metal has the chemical symbol Au?",["Gold","Silver","Iron","Copper"],0],
["How many days are in a leap year?",["366","365","364","367"],0],
["Which organ pumps blood?",["Heart","Lung","Liver","Kidney"],0],
["What is the fastest land animal?",["Cheetah","Lion","Horse","Leopard"],0],
["Which country is shaped like a boot?",["Italy","Spain","Portugal","Greece"],0],
["What is the smallest prime number?",["2","1","3","0"],0],
["Which planet has famous rings?",["Saturn","Mars","Venus","Mercury"],0],
["What is the capital of New Zealand?",["Wellington","Auckland","Hamilton","Dunedin"],0],
["Which mammal lays eggs?",["Platypus","Dolphin","Koala","Whale"],0],
["How many colours are traditionally in a rainbow?",["Seven","Six","Eight","Five"],0],
["Which language has the most native speakers?",["Mandarin Chinese","English","Spanish","Hindi"],0],
["What is the hardest natural substance?",["Diamond","Quartz","Iron","Granite"],0],
["Which ocean surrounds Antarctica?",["Southern","Pacific","Atlantic","Indian"],0],
["What is the tallest mountain above sea level?",["Mount Everest","K2","Kilimanjaro","Denali"],0],
["Which country gave the Statue of Liberty to the United States?",["France","Spain","Italy","Canada"],0],
["What is the boiling point of water at sea level in Celsius?",["100","90","80","120"],0],
["Which animal is the largest bird?",["Ostrich","Emu","Eagle","Albatross"],0],
["Which planet is known as the Blue Planet?",["Earth","Neptune","Uranus","Venus"],0],
["How many sides does an octagon have?",["Eight","Seven","Nine","Six"],0],
["What is the capital of Australia?",["Canberra","Sydney","Melbourne","Perth"],0],
["Which fruit is traditionally used to make guacamole?",["Avocado","Mango","Apple","Pear"],0],
["What is the main ingredient in bread?",["Flour","Rice","Corn","Potato"],0],
["Which instrument measures temperature?",["Thermometer","Barometer","Compass","Altimeter"],0],
["What is Earth's natural satellite?",["Moon","Sun","Mars","Venus"],0],
["Which animal is famous for changing colour?",["Chameleon","Elephant","Giraffe","Zebra"],0],
["What is the capital of Canada?",["Ottawa","Toronto","Vancouver","Montreal"],0],
["Which sport uses a shuttlecock?",["Badminton","Tennis","Squash","Hockey"],0],
["How many players are on a football team on the field?",["11","10","12","9"],0],
["Which sea creature has eight arms?",["Octopus","Squid","Starfish","Crab"],0],
["Which country is home to the Great Barrier Reef?",["Australia","New Zealand","Indonesia","South Africa"],0],
["What is the largest internal organ in the human body?",["Liver","Heart","Lung","Kidney"],0],
["Which planet is famous for its Great Red Spot?",["Jupiter","Saturn","Mars","Neptune"],0],
["Which animal is known for its black and white stripes?",["Zebra","Tiger","Panda","Skunk"],0],
["What is the capital of Italy?",["Rome","Milan","Venice","Naples"],0],
["Which food is made from fermented milk?",["Yoghurt","Bread","Rice","Pasta"],0],
["How many bones are in the adult human body approximately?",["206","150","306","256"],0],
["Which natural force keeps us on the ground?",["Gravity","Magnetism","Friction","Pressure"],0],
["What is the largest desert in the world?",["Antarctic Desert","Sahara","Gobi","Arabian"],0],
["Which country is famous for the Taj Mahal?",["India","Pakistan","Nepal","Bangladesh"],0],
["What is the capital of Spain?",["Madrid","Barcelona","Seville","Valencia"],0],
["Which animal is known for building dams?",["Beaver","Otter","Badger","Fox"],0],
["What is the nearest planet to Earth in size?",["Venus","Mars","Mercury","Neptune"],0],
["Which sport is played at Wimbledon?",["Tennis","Golf","Cricket","Rugby"],0],
["What is the chemical symbol for oxygen?",["O","Ox","Og","C"],0],
["Which country has the city of Cairo?",["Egypt","Jordan","Turkey","Morocco"],0],
["What is the largest species of shark?",["Whale shark","Great white","Tiger shark","Hammerhead"],0],
["Which animal is famous for its long neck?",["Giraffe","Camel","Llama","Horse"],0],
["What is the capital of Germany?",["Berlin","Munich","Hamburg","Frankfurt"],0],
["Which planet is farthest from the Sun?",["Neptune","Uranus","Saturn","Jupiter"],0],
["What do bees collect from flowers?",["Nectar","Sand","Leaves","Water"],0],
["Which instrument usually has six strings?",["Guitar","Piano","Trumpet","Flute"],0],
["What is the largest country by land area?",["Russia","Canada","China","USA"],0],
["Which animal is known for carrying its baby in a pouch?",["Kangaroo","Elephant","Tiger","Wolf"],0],
["What is the capital of Greece?",["Athens","Sparta","Corinth","Rhodes"],0],
["Which vitamin is commonly produced by sunlight exposure?",["Vitamin D","Vitamin C","Vitamin B12","Vitamin A"],0],
["Which planet is known for its blue-green colour?",["Uranus","Mars","Venus","Mercury"],0],
["What is the main language of Brazil?",["Portuguese","Spanish","English","French"],0],
["Which animal is the largest living reptile?",["Saltwater crocodile","Komodo dragon","Green anaconda","Leatherback turtle"],0],
["What is the capital of Norway?",["Oslo","Bergen","Trondheim","Stavanger"],0],
["Which sport uses a bat and ball and wickets?",["Cricket","Baseball","Tennis","Hockey"],0],
["What is the centre of an atom called?",["Nucleus","Electron","Shell","Ion"],0],
["Which country is famous for sushi?",["Japan","China","Korea","Thailand"],0],
["What is the capital of Ireland?",["Dublin","Cork","Galway","Limerick"],0],
["Which animal has a trunk?",["Elephant","Rhino","Hippo","Tapir"],0],
["What is the largest moon in the Solar System?",["Ganymede","Titan","Europa","Moon"],0],
["Which country is known for the Eiffel Tower?",["France","Belgium","Italy","Switzerland"],0],
["What is the capital of South Korea?",["Seoul","Busan","Incheon","Daegu"],0],
["Which animal can regenerate lost limbs?",["Starfish","Shark","Whale","Penguin"],0],
["What is the main gas in Earth's atmosphere?",["Nitrogen","Oxygen","Carbon dioxide","Hydrogen"],0],
["Which country is home to Machu Picchu?",["Peru","Chile","Brazil","Bolivia"],0],
["What is the capital of Portugal?",["Lisbon","Porto","Braga","Faro"],0],
["Which animal is famous for its pouch and hopping?",["Kangaroo","Rabbit","Deer","Goat"],0],
["What is the largest land animal?",["African elephant","Giraffe","Rhino","Hippo"],0],
["Which planet has the strongest winds in the Solar System?",["Neptune","Mars","Earth","Mercury"],0],
["What is the capital of Mexico?",["Mexico City","Cancun","Guadalajara","Monterrey"],0],
["Which food is traditionally associated with Italy?",["Pizza","Sushi","Curry","Tacos"],0],
["What is the name of our galaxy?",["Milky Way","Andromeda","Whirlpool","Sombrero"],0],
["Which animal is known for producing wool?",["Sheep","Goat","Cow","Horse"],0],
["What is the capital of China?",["Beijing","Shanghai","Hong Kong","Shenzhen"],0],
["Which sport is associated with a puck?",["Ice hockey","Cricket","Rugby","Golf"],0],
["What is the largest continent?",["Asia","Africa","Europe","North America"],0],
["Which animal is known for its distinctive black-and-white face markings?",["Giant panda","Polar bear","Raccoon","Badger"],0],
["What is the capital of Iceland?",["Reykjavik","Akureyri","Kopavogur","Hafnarfjordur"],0],
["Which planet is famous for having Olympus Mons?",["Mars","Earth","Venus","Jupiter"],0],
["What is the capital of Argentina?",["Buenos Aires","Cordoba","Rosario","Mendoza"],0],
["Which animal is famous for its ability to echolocate?",["Bat","Rabbit","Horse","Deer"],0],
["What is the capital of Thailand?",["Bangkok","Phuket","Pattaya","Chiang Mai"],0],
["Which element has the symbol Fe?",["Iron","Fluorine","Francium","Fermium"],0],
["What is the largest rainforest?",["Amazon","Congo","Daintree","Borneo"],0],
["Which animal is often associated with honey?",["Bee","Butterfly","Ant","Wasp"],0],
["What is the capital of Turkey?",["Ankara","Istanbul","Izmir","Bursa"],0],
["Which planet rotates on its side?",["Uranus","Mars","Earth","Saturn"],0],
["What is the capital of Sweden?",["Stockholm","Gothenburg","Malmo","Uppsala"],0],
["Which animal is known as man's best friend?",["Dog","Horse","Cat","Rabbit"],0]

];


/* =====================================================
DERBY
===================================================== */

function derby(){

 let questions=
  [...derbyQuestions]
   .sort(()=>Math.random()-.5);

 let index=0;
 let playerHorse=0;
 let positions=[0,0,0,0];

 const content=
  document.getElementById("gameContent");

 content.innerHTML=`

  <div class="questionBox">

   <h3>🏇 THE LULU DERBY</h3>

   <p>
    Choose your horse.
    Answer all 100 random trivia questions
    to drive the race.
   </p>

   <div class="answerGrid">

    <button class="gameBtn" onclick="chooseHorse(0)">
     🐎 Rose Runner
    </button>

    <button class="gameBtn" onclick="chooseHorse(1)">
     🐴 Lulu Lightning
    </button>

    <button class="gameBtn" onclick="chooseHorse(2)">
     🦄 Pink Comet
    </button>

    <button class="gameBtn" onclick="chooseHorse(3)">
     🏇 Heart Racer
    </button>

   </div>

   <div id="derbyRace"></div>

  </div>
 `;

 window.chooseHorse=function(horse){

  playerHorse=horse;

  showQuestion();

 };

 function renderRace(){

  return`

   <div class="raceTrack">

    ${positions.map((p,i)=>`

     <div class="horseLane">

      <div
       class="horse"
       style="left:${Math.min(92,p)}%"
      >
       ${["🐎","🐴","🦄","🏇"][i]}
      </div>

      <div class="finish"></div>

     </div>

    `).join("")}

   </div>
  `;

 }

 function showQuestion(){

  if(index>=100){

   const winner=
    positions.indexOf(
     Math.max(...positions)
    );

   if(winner===playerHorse){

    passLevel(22,700);

   }else{

    content.innerHTML=`

     <div class="complete">

      <div class="completeIcon">🏇</div>

      <h2>So close!</h2>

      <p>
       You answered all 100 questions,
       but another horse won the derby.
      </p>

      <button class="nextBtn" onclick="derby()">
       RACE AGAIN
      </button>

     </div>
    `;

   }

   return;
  }

  const q=questions[index];
  const answers=shuffleQuestion(q);

  document.getElementById("derbyRace")
   .innerHTML=`

    ${renderRace()}

    <div class="questionBox">

     <p>
      Question ${index+1} / 100
     </p>

     <h3>
      ${escapeHTML(q[0])}
     </h3>

    </div>

    <div class="answerGrid">

     ${answers.map(a=>`

      <button
       class="gameBtn"
       onclick="derbyAnswer(${a.correct})"
      >
       ${escapeHTML(a.answer)}
      </button>

     `).join("")}

    </div>

   `;

 }

 window.derbyAnswer=function(correct){

  if(correct){

   positions[playerHorse]+=4;

   for(let i=0;i<4;i++){

    if(i!==playerHorse)
     positions[i]+=Math.random()<.35?1:0;

   }

   addPoints(5);

  }else{

   positions[playerHorse]+=1;

   for(let i=0;i<4;i++){

    if(i!==playerHorse)
     positions[i]+=2;

   }

  }

  index++;
  showQuestion();

 };

 activeCleanup=()=>{

  delete window.chooseHorse;
  delete window.derbyAnswer;

 };

}


/* =====================================================
23. FINAL CHALLENGE
50 UNIQUE LILIANA QUESTIONS
===================================================== */

const finalQuestions=[

 ["Which colour is most associated with Liliana's favourite colour?",
  ["Baby pink","Emerald green","Navy blue","Orange"],0],

 ["Which number is Liliana's favourite?",
  ["3","4","6","8"],0],

 ["Which food would Liliana be most likely to choose from these?",
  ["Sushi","Steak","Fish and chips","Lasagne"],0],

 ["Which sea animal does Liliana like?",
  ["Dolphins","Seals","Whales","Turtles"],0],

 ["Which pair contains two flowers Liliana likes?",
  ["Sunflowers and roses","Lilies and tulips","Daisies and orchids","Violets and poppies"],0],

 ["What month should you associate with Liliana's birthday?",
  ["July","January","October","December"],0],

 ["What date is Liliana's birthday?",
  ["22 July","3 July","27 July","6 July"],0],

 ["What colour are Liliana's eyes?",
  ["Green","Hazel","Blue","Brown"],0],

 ["Which star sign belongs to Liliana?",
  ["Leo","Libra","Aries","Pisces"],0],

 ["Which fear is associated with Liliana?",
  ["Drowning","Flying","Thunder","Darkness"],0],

 ["Which film is Liliana's favourite?",
  ["Me Before You","The Notebook","Titanic","A Walk to Remember"],0],

 ["Which university subject did Liliana study?",
  ["Psychology","History","Nursing","Business"],0],

 ["How many nieces does Liliana have?",
  ["1","2","3","5"],0],

 ["How many nephews does Liliana have?",
  ["4","1","3","6"],0],

 ["How many siblings does Liliana have?",
  ["5","2","4","7"],0],

 ["How many piercings does Liliana have?",
  ["4","1","2","6"],0],

 ["Which two names belong to Liliana's dogs?",
  ["Aayla and Arlo","Luna and Milo","Bella and Max","Coco and Leo"],0],

 ["Which creative interest is associated with Liliana?",
  ["Poetry","Pottery","Photography","Knitting"],0],

 ["What kind of songs does Liliana like?",
  ["Sad songs","Only happy songs","Only rock songs","Only instrumental songs"],0],

 ["Which type of game does Liliana enjoy?",
  ["Poker","Chess","Scrabble","Bingo"],0],

 ["What does Liliana hope to become one day?",
  ["A mum","A pilot","A chef","A dancer"],0],

 ["What kind of child does Liliana hope to have?",
  ["A baby girl","Twin boys","A baby boy","Triplets"],0],

 ["Which combination correctly describes two of Liliana's interests?",
  ["Poetry and sad songs","Fishing and golf","Cars and boxing","Hiking and skiing"],0],

 ["Which combination correctly matches Liliana's food and animal interests?",
  ["Sushi and dolphins","Pizza and horses","Pasta and cats","Curry and pandas"],0],

 ["Which pair correctly matches Liliana's favourite number and birthday day?",
  ["3 and 22","5 and 7","6 and 27","4 and 12"],0],

 ["Which pair correctly matches Liliana's birthday month and star sign?",
  ["July and Leo","July and Cancer","June and Leo","August and Virgo"],0],

 ["Which pair correctly matches Liliana's eyes and favourite colour?",
  ["Green and baby pink","Blue and purple","Brown and burgundy","Hazel and red"],0],

 ["Which pair correctly matches Liliana's dogs?",
  ["Aayla and Arlo","Arlo and Luna","Aayla and Bella","Max and Arlo"],0],

 ["What field best connects Liliana's university studies with understanding people?",
  ["Psychology","Astronomy","Geology","Architecture"],0],

 ["Which number is connected to Liliana's favourite-number preference?",
  ["Three","Five","Seven","Ten"],0],

 ["Which flower would fit Liliana's known favourites?",
  ["Sunflower","Cactus","Bamboo","Fern"],0],

 ["Which other flower belongs on the list of Liliana's favourites?",
  ["Rose","Iris","Crocus","Dahlia"],0],

 ["Which animal would be the most fitting choice for a Liliana-themed picture?",
  ["Dolphin","Tiger","Eagle","Wolf"],0],

 ["Which food would fit a Liliana-themed dinner based on her known preference?",
  ["Sushi","Burgers","Curry","Tacos"],0],

 ["Which movie belongs in Liliana's favourite-film category?",
  ["Me Before You","Mean Girls","Mamma Mia!","Encanto"],0],

 ["Which hobby combination best reflects Liliana's known interests?",
  ["Poker and poetry","Golf and fishing","Cars and coding","Running and cycling"],0],

 ["Which statement about Liliana's family is correct?",
  ["She has 1 niece and 4 nephews","She has 4 nieces and 1 nephew","She has 2 nieces and 3 nephews","She has 5 nieces"],0],

 ["Which number describes Liliana's siblings?",
  ["5","3","6","8"],0],

 ["Which number describes Liliana's piercings?",
  ["4","3","5","7"],0],

 ["Which pair represents Liliana's two dogs rather than flowers?",
  ["Aayla and Arlo","Sunflower and rose","Dolphin and sushi","Leo and July"],0],

 ["Which pair represents Liliana's birthday details?",
  ["22 July","3 August","6 July","27 June"],0],

 ["Which pairing correctly connects Liliana with a film?",
  ["Me Before You","Frozen","Moana","The Lion King"],0],

 ["Which pairing correctly connects Liliana with a field of study?",
  ["Psychology","Physics","Engineering","Medicine"],0],

 ["Which pairing correctly connects Liliana with an animal?",
  ["Dolphin","Elephant","Panda","Fox"],0],

 ["Which pairing correctly connects Liliana with food?",
  ["Sushi","Ramen","Pizza","Pancakes"],0],

 ["Which pairing correctly connects Liliana with flowers?",
  ["Sunflowers and roses","Lilies and orchids","Tulips and daisies","Violets and lilies"],0],

 ["Which statement about Liliana's future wish is correct?",
  ["She wants to be a mum to a baby girl","She wants to become a professional athlete","She wants to own a restaurant","She wants to become a singer"],0],

 ["Which statement best matches Liliana's personality?",
  ["Sweet, caring and empathetic","Quiet, cold and distant","Competitive, serious and stern","Shy, impatient and reserved"],0],

 ["How long have Bree and Liliana been best friends?",
  ["6 years","3 years","4 years","8 years"],0]

];


function finalChallenge(){

 let questions=
  [...finalQuestions]
   .sort(()=>Math.random()-.5);

 let index=0;
 let score=0;

 const content=
  document.getElementById("gameContent");

 function show(){

  if(index>=questions.length){

   passLevel(23,score+500);
   return;

  }

  const q=questions[index];

  const answers=shuffleQuestion(q);

  content.innerHTML=`

   <div class="questionBox">

    <div class="timer">
     💕 FINAL CHALLENGE
    </div>

    <h3>
     ${escapeHTML(q[0])}
    </h3>

   </div>

   <div class="answerGrid">

    ${answers.map(a=>`

     <button
      class="gameBtn"
      onclick="finalAnswer(${a.correct})"
     >
      ${escapeHTML(a.answer)}
     </button>

    `).join("")}

   </div>

   <div class="scoreBox">

    Question ${index+1} / 50
    <br>
    ⭐ ${score} points

   </div>

  `;

 }

 window.finalAnswer=function(correct){

  if(correct){

   score+=25;
   addPoints(25);

  }

  index++;
  show();

 };

 activeCleanup=()=>{
  delete window.finalAnswer;
 };

 show();
}


/* =====================================================
UTILITY
===================================================== */

function escapeHTML(value){

 return String(value)
  .replace(/&/g,"&amp;")
  .replace(/</g,"&lt;")
  .replace(/>/g,"&gt;")
  .replace(/"/g,"&quot;")
  .replace(/'/g,"&#039;");

}


/* =====================================================
LOAD SAVED JOURNEY
===================================================== */

window.addEventListener("load",()=>{

 if(load()){

  showApp();

 }

});


/* ENTER NAME WITH ENTER */

document
 .getElementById("nameInput")
 .addEventListener("keydown",e=>{

  if(e.key==="Enter")
   beginJourney();

 });

</script>

</body>
</html>

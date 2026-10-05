<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport"
      content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no,viewport-fit=cover">

<title>Lulu Express 💗</title>

<style>
*{
  box-sizing:border-box;
  -webkit-tap-highlight-color:transparent;
}

html,body{
  margin:0;
  width:100%;
  height:100%;
  overflow:hidden;
  font-family:Arial,sans-serif;
  background:#160b16;
  color:white;
}

button{
  font:inherit;
  touch-action:manipulation;
}

#app{
  width:100%;
  height:100%;
  position:relative;
}

.screen{
  display:none;
  width:100%;
  height:100%;
  overflow-y:auto;
  padding:22px 16px;
  text-align:center;
}

.screen.active{
  display:flex;
  flex-direction:column;
  align-items:center;
}

.card{
  width:min(100%,520px);
  margin:auto;
  padding:24px 18px;
  border-radius:28px;
  background:rgba(255,192,220,.12);
  border:1px solid rgba(255,190,220,.35);
  box-shadow:0 15px 50px rgba(0,0,0,.35);
}

h1{
  font-size:2.2rem;
  margin:5px 0 12px;
}

h2{
  margin:5px 0 12px;
}

p{
  line-height:1.5;
}

.big-heart{
  font-size:4rem;
  animation:pulse 1.5s infinite;
}

@keyframes pulse{
  50%{transform:scale(1.12)}
}

input{
  width:100%;
  padding:15px;
  border-radius:15px;
  border:2px solid #ff9ac7;
  background:#fff;
  color:#321;
  font-size:1rem;
  text-align:center;
  margin:10px 0;
}

.main-btn{
  width:100%;
  max-width:380px;
  border:0;
  border-radius:18px;
  padding:16px;
  margin:7px 0;
  background:#ff9ac7;
  color:#351329;
  font-weight:bold;
  box-shadow:0 6px 15px rgba(0,0,0,.2);
}

.main-btn:active{
  transform:scale(.97);
}

.secondary{
  background:#ffffff1a;
  color:white;
  border:1px solid #ffffff44;
}

.game-title{
  font-size:1.8rem;
  margin:5px 0;
}

.progress{
  width:min(100%,500px);
  height:8px;
  background:#ffffff22;
  border-radius:10px;
  margin:8px 0 16px;
}

.progress div{
  height:100%;
  width:0;
  background:#ff9ac7;
  border-radius:10px;
}

.choice-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
  width:100%;
  margin:15px 0;
}

.choice{
  border:0;
  border-radius:16px;
  padding:15px 8px;
  background:#ffffff18;
  color:white;
  border:1px solid #ffffff33;
  min-height:60px;
}

.choice.correct{
  background:#62d394;
  color:#102;
}

.choice.wrong{
  background:#e96b85;
}

.choice:active{
  transform:scale(.96);
}

.status{
  min-height:30px;
  font-weight:bold;
}

.next-area{
  width:100%;
  margin-top:15px;
}

.hidden{
  display:none!important;
}

/* Memory */

.memory-grid{
  width:min(100%,380px);
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:8px;
  margin:15px auto;
}

.memory-card{
  aspect-ratio:1;
  border:0;
  border-radius:14px;
  background:#ff9ac7;
  color:#351329;
  font-size:1.8rem;
}

.memory-card.open{
  background:white;
}

.memory-card.matched{
  background:#8ee8bd;
}

/* Falling hearts */

.fall-area{
  width:100%;
  height:58vh;
  min-height:330px;
  position:relative;
  overflow:hidden;
  border-radius:22px;
  background:#08050d;
  border:1px solid #ffffff22;
}

.falling{
  position:absolute;
  font-size:2.3rem;
  border:0;
  background:none;
  padding:5px;
}

/* Pattern */

.pattern-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:8px;
  width:min(100%,350px);
  margin:15px auto;
}

.pattern-cell{
  aspect-ratio:1;
  border:0;
  border-radius:12px;
  background:#ffffff18;
}

.pattern-cell.lit{
  background:#ff9ac7;
}

/* Word find */

.word-grid{
  display:grid;
  grid-template-columns:repeat(10,1fr);
  gap:3px;
  width:min(100%,390px);
  margin:10px auto;
}

.letter{
  aspect-ratio:1;
  border:0;
  border-radius:5px;
  background:#ffffff16;
  color:white;
  font-size:.9rem;
  font-weight:bold;
}

.letter.selected{
  background:#ff9ac7;
  color:#351329;
}

.letter.found{
  background:#76dba5;
  color:#123;
}

.word-list{
  display:flex;
  flex-wrap:wrap;
  justify-content:center;
  gap:6px;
  margin:10px 0;
}

.word{
  padding:6px 9px;
  border-radius:10px;
  background:#ffffff16;
  font-size:.8rem;
}

.word.done{
  text-decoration:line-through;
  background:#76dba5;
  color:#123;
}

/* Drawing */

#drawCanvas{
  width:100%;
  max-width:380px;
  height:380px;
  background:white;
  border-radius:20px;
  touch-action:none;
}

/* Derby */

.animal-grid{
  display:grid;
  grid-template-columns:1fr 1fr 1fr;
  gap:8px;
}

.animal{
  border:0;
  border-radius:15px;
  padding:12px 5px;
  background:#ffffff15;
  color:white;
  font-size:1.8rem;
}

.animal small{
  display:block;
  font-size:.7rem;
}

.race-track{
  width:100%;
  padding:15px 0;
}

.racer{
  height:42px;
  border-radius:12px;
  background:#ffffff12;
  margin:8px 0;
  position:relative;
  overflow:hidden;
}

.racer span{
  position:absolute;
  left:5px;
  top:5px;
  font-size:1.5rem;
  transition:left .3s;
}

/* casino */

.bank{
  font-size:1.3rem;
  font-weight:bold;
  margin:10px;
}

/* final */

.final-question{
  font-size:1.15rem;
  font-weight:bold;
  margin:15px 0;
}

/* completion */

.reward{
  font-size:2.5rem;
  margin:15px;
}

@media(max-height:650px){
  .screen{padding:12px}
  .card{padding:16px}
  h1{font-size:1.8rem}
  .big-heart{font-size:3rem}
  .fall-area{min-height:280px;height:48vh}
}
</style>
</head>

<body>

<div id="app">

<!-- START -->
<section id="start" class="screen active">
  <div class="card">
    <div class="big-heart">💗</div>
    <h1>Lulu Express</h1>
    <p>
      Welcome to your very own birthday adventure, Lulu.
      <br><br>
      23 games. One journey. One very special person.
    </p>

    <button class="main-btn secondary" onclick="toggleMusic()">
      🎵 <span id="musicText">Music: OFF</span>
    </button>

    <input id="playerName" placeholder="Enter your name">

    <button class="main-btn" onclick="startJourney()">
      🚂 START THE JOURNEY
    </button>
  </div>
</section>

<!-- GAME -->
<section id="game" class="screen">
  <div class="card">
    <div id="levelLabel"></div>
    <div class="progress"><div id="progressBar"></div></div>
    <h2 id="gameTitle" class="game-title"></h2>
    <div id="gameArea"></div>
    <div id="nextArea" class="next-area hidden">
      <button class="main-btn" onclick="nextLevel()">NEXT LEVEL 💗</button>
    </div>
  </div>
</section>

<!-- FINISH -->
<section id="finish" class="screen">
  <div class="card">
    <div class="big-heart">🏆</div>
    <h1>Journey Complete!</h1>
    <p id="finishText"></p>
    <div id="rewardBox"></div>
    <button class="main-btn" onclick="resetJourney()">
      🔄 RESET JOURNEY
    </button>
  </div>
</section>

</div>

<script>
/* =========================================================
   CORE
========================================================= */

const TOTAL_LEVELS = 23;

let currentLevel = 1;
let player = "";
let score = 0;
let tokens = 0;
let musicOn = false;
let audioCtx = null;

let gameTimer = null;
let gameTimeouts = [];

const gameArea = document.getElementById("gameArea");
const gameTitle = document.getElementById("gameTitle");
const nextArea = document.getElementById("nextArea");
const levelLabel = document.getElementById("levelLabel");
const progressBar = document.getElementById("progressBar");

function clearTimers(){
  if(gameTimer){
    clearInterval(gameTimer);
    gameTimer = null;
  }

  gameTimeouts.forEach(t => clearTimeout(t));
  gameTimeouts = [];
}

function later(fn,ms){
  const t=setTimeout(fn,ms);
  gameTimeouts.push(t);
  return t;
}

function showScreen(id){
  document.querySelectorAll(".screen").forEach(s=>s.classList.remove("active"));
  document.getElementById(id).classList.add("active");
}

function startJourney(){
  const input=document.getElementById("playerName");
  player=input.value.trim();

  if(!player){
    input.focus();
    input.placeholder="Please enter your name 💗";
    return;
  }

  score=0;
  tokens=0;
  currentLevel=1;

  playTone(660,.12);
  showScreen("game");
  loadLevel();
}

function loadLevel(){
  clearTimers();

  nextArea.classList.add("hidden");

  levelLabel.textContent=`LEVEL ${currentLevel} OF ${TOTAL_LEVELS}`;
  progressBar.style.width=(currentLevel/TOTAL_LEVELS*100)+"%";

  const games=[
    brokenHearts,
    memoryVault,
    pressureQuiz,
    highRoller,
    mindGames,
    bluffGame,
    survivalRound,
    admirerRace,
    heartbreakChamber,
    boxingMatch,
    perfectMatch,
    whoKnowsLiliana,
    reactionGauntlet,
    heartHunt,
    loveLock,
    cupidShootout,
    countdownGame,
    ultimateGamble,
    admirersLastStand,
    wordFind,
    drawSunflower,
    luluDerby,
    finalChallenge
  ];

  games[currentLevel-1]();
}

function completeGame(points=200,rewardTokens=100){
  clearTimers();

  score += points;
  tokens += rewardTokens;

  gameArea.innerHTML=`
    <div class="reward">✨</div>
    <h2>Level Complete!</h2>
    <p>Beautiful work, ${escapeHTML(player)}! 💗</p>
    <p>+${points} points</p>
  `;

  nextArea.classList.remove("hidden");
  playTone(880,.15);
}

function nextLevel(){
  if(currentLevel>=TOTAL_LEVELS){
    finishJourney();
    return;
  }

  currentLevel++;
  loadLevel();
}

function escapeHTML(s){
  return s.replace(/[&<>"']/g,m=>({
    "&":"&amp;",
    "<":"&lt;",
    ">":"&gt;",
    '"':"&quot;",
    "'":"&#039;"
  }[m]));
}

/* =========================================================
   1. BROKEN HEARTS
========================================================= */

function brokenHearts(){
  gameTitle.textContent="💔 Broken Hearts";

  gameArea.innerHTML=`
    <p>Catch ❤️ and 💖. Avoid 💔!</p>
    <p id="bhScore">Hearts: 0 / 15</p>
    <div class="fall-area" id="fallArea"></div>
  `;

  const area=document.getElementById("fallArea");
  let caught=0;

  function spawn(){
    if(caught>=15) return;

    const b=document.createElement("button");
    const good=Math.random()>.25;

    b.className="falling";
    b.textContent=good?(Math.random()>.5?"❤️":"💖"):"💔";
    b.style.left=Math.random()*85+"%";
    b.style.top="0";

    area.appendChild(b);

    let y=0;
    const speed=2.2+currentLevel*.08;

    const id=setInterval(()=>{
      y+=speed;
      b.style.top=y+"px";

      if(y>area.clientHeight){
        clearInterval(id);
        b.remove();
      }
    },30);

    b.onclick=()=>{
      clearInterval(id);

      if(good){
        caught++;
        document.getElementById("bhScore").textContent=`Hearts: ${caught} / 15`;
        b.remove();

        if(caught>=15){
          completeGame(250,150);
        }
      }else{
        score=Math.max(0,score-50);
        b.remove();
      }
    };
  }

  let spawns=0;
  gameTimer=setInterval(()=>{
    if(caught<15 && spawns<35){
      spawn();
      spawns++;
    }
    if(spawns>=35) clearInterval(gameTimer);
  },650);
}

/* =========================================================
   2. MEMORY VAULT
========================================================= */

function memoryVault(){
  gameTitle.textContent="🧠 Memory Vault";

  gameArea.innerHTML=`
    <p>Match all 8 pairs.</p>
    <p id="memoryStatus">Pairs: 0 / 8</p>
    <div class="memory-grid" id="memoryGrid"></div>
  `;

  const symbols=[
    "🌸","🌸","💗","💗","⭐","⭐","🦋","🦋",
    "🐬","🐬","🌻","🌻","🌙","🌙","💎","💎"
  ];

  symbols.sort(()=>Math.random()-.5);

  const grid=document.getElementById("memoryGrid");

  let first=null;
  let locked=false;
  let pairs=0;
  let mistakes=0;

  symbols.forEach(symbol=>{
    const card=document.createElement("button");
    card.className="memory-card";
    card.textContent="❓";
    card.dataset.symbol=symbol;

    card.onclick=()=>{
      if(locked || card.classList.contains("matched") || card===first)
        return;

      card.textContent=symbol;
      card.classList.add("open");

      if(!first){
        first=card;
        return;
      }

      locked=true;

      if(first.dataset.symbol===card.dataset.symbol){
        first.classList.add("matched");
        card.classList.add("matched");

        pairs++;

        document.getElementById("memoryStatus").textContent=
          `Pairs: ${pairs} / 8`;

        first=null;
        locked=false;

        if(pairs===8){
          completeGame(Math.max(180,300-mistakes*10),180);
        }

      }else{
        mistakes++;

        const old=first;
        const second=card;

        later(()=>{
          old.textContent="❓";
          second.textContent="❓";
          old.classList.remove("open");
          second.classList.remove("open");
          first=null;
          locked=false;
        },650);
      }
    };

    grid.appendChild(card);
  });
}

/* =========================================================
   3. PRESSURE QUIZ
========================================================= */

const pressureQuestions=[
 ["Which animal does Liliana love most?","Dolphin",["Dolphin","Tiger","Horse","Penguin"]],
 ["What is Liliana's favourite food?","Sushi",["Pizza","Sushi","Pasta","Tacos"]],
 ["What colour does Liliana love?","Baby pink",["Purple","Baby pink","Blue","Green"]],
 ["What is Liliana's star sign?","Leo",["Leo","Cancer","Gemini","Aries"]],
 ["What did Liliana study at university?","Psychology",["Law","Psychology","Medicine","Art"]],
 ["What type of songs does Liliana like?","Sad songs",["Country songs","Sad songs","Metal","Opera"]],
 ["What flower does Liliana like?","Sunflowers",["Lilies","Sunflowers","Tulips","Orchids"]],
 ["How many siblings does Liliana have?","5",["3","4","5","6"]]
];

function pressureQuiz(){
  gameTitle.textContent="⚡ Pressure Quiz";

  let questions=[...pressureQuestions].sort(()=>Math.random()-.5);
  let index=0;
  let correct=0;
  let answered=false;
  let time=8;

  function render(){
    if(index>=questions.length){
      completeGame(150+correct*35,100+correct*10);
      return;
    }

    answered=false;
    time=8;

    const q=questions[index];

    gameArea.innerHTML=`
      <p>Question ${index+1} / ${questions.length}</p>
      <h3>${q[0]}</h3>
      <div id="quizTimer">⏱️ ${time}</div>
      <div class="choice-grid" id="quizChoices"></div>
      <div class="status" id="quizStatus"></div>
    `;

    const box=document.getElementById("quizChoices");

    [...q[2]].sort(()=>Math.random()-.5).forEach(answer=>{
      const b=document.createElement("button");
      b.className="choice";
      b.textContent=answer;

      b.onclick=()=>{
        if(answered)return;
        answered=true;

        if(answer===q[1]){
          correct++;
          b.classList.add("correct");
          document.getElementById("quizStatus").textContent="Correct! 💗";
        }else{
          b.classList.add("wrong");
          document.getElementById("quizStatus").textContent=`The answer was ${q[1]}`;
        }

        clearInterval(gameTimer);
        later(()=>{
          index++;
          render();
        },550);
      };

      box.appendChild(b);
    });

    gameTimer=setInterval(()=>{
      time--;
      document.getElementById("quizTimer").textContent=`⏱️ ${time}`;

      if(time<=0){
        clearInterval(gameTimer);

        if(!answered){
          answered=true;
          document.getElementById("quizStatus").textContent="Time! ⏰";
          later(()=>{
            index++;
            render();
          },500);
        }
      }
    },1000);
  }

  render();
}

/* =========================================================
   4. HIGH ROLLER
========================================================= */

function highRoller(){
  gameTitle.textContent="🎰 High Roller";

  let rounds=0;
  let bank=500;

  function render(){
    gameArea.innerHTML=`
      <div class="bank">💰 ${bank} tokens</div>
      <p>Choose a mystery card.</p>
      <div class="choice-grid" id="cards"></div>
      <p id="hrStatus"></p>
    `;

    const values=[100,250,500,-100,750]
      .sort(()=>Math.random()-.5);

    values.forEach((value,i)=>{
      const b=document.createElement("button");
      b.className="choice";
      b.textContent=["🂠","🂠","🂠","🂠","🂠"][i];

      b.onclick=()=>{
        bank=Math.max(0,bank+value);
        rounds++;

        document.getElementById("hrStatus").textContent=
          value>=0?`You won +${value}! 💰`:`Oh no! ${value} 💔`;

        if(rounds>=5){
          score+=bank;
          completeGame(Math.min(500,200+Math.floor(bank/5)),Math.floor(bank/10));
        }else{
          later(render,600);
        }
      };

      document.getElementById("cards").appendChild(b);
    });
  }

  render();
}

/* =========================================================
   5. MIND GAMES
========================================================= */

function mindGames(){
  gameTitle.textContent="🧩 Mind Games";

  const round=4;
  const length=4;
  const pattern=[];

  while(pattern.length<length){
    const n=Math.floor(Math.random()*16);
    if(!pattern.includes(n))pattern.push(n);
  }

  gameArea.innerHTML=`
    <p>Remember the glowing sequence.</p>
    <p id="mindStatus">Watch carefully...</p>
    <div class="pattern-grid" id="patternGrid"></div>
  `;

  const grid=document.getElementById("patternGrid");

  for(let i=0;i<16;i++){
    const b=document.createElement("button");
    b.className="pattern-cell";
    b.dataset.i=i;
    grid.appendChild(b);
  }

  pattern.forEach((n,i)=>{
    later(()=>{
      grid.children[n].classList.add("lit");
      later(()=>grid.children[n].classList.remove("lit"),450);
    },i*650+400);
  });

  later(()=>{
    document.getElementById("mindStatus").textContent=
      "Now tap the pattern in order!";

    let pos=0;

    [...grid.children].forEach((b,i)=>{
      b.onclick=()=>{
        if(i===pattern[pos]){
          b.classList.add("lit");
          pos++;

          if(pos===pattern.length){
            completeGame(300,180);
          }
        }else{
          document.getElementById("mindStatus").textContent=
            "Wrong square! Try the pattern again.";
          pos=0;
          [...grid.children].forEach(x=>x.classList.remove("lit"));
        }
      };
    });
  },3200);
}

/* =========================================================
   6. BLUFF
========================================================= */

function bluffGame(){
  gameTitle.textContent="🤥 The Bluff";

  const facts=[
    ["Liliana loves dolphins.","TRUE"],
    ["Liliana's favourite colour is baby pink.","TRUE"],
    ["Liliana studied Psychology.","TRUE"]
  ];

  const liar=Math.floor(Math.random()*3);

  gameArea.innerHTML=`
    <p>Two statements are true. One is a lie.</p>
    <div id="bluffBox"></div>
  `;

  const box=document.getElementById("bluffBox");

  facts.forEach((f,i)=>{
    const b=document.createElement("button");
    b.className="choice";
    b.style.width="100%";
    b.textContent=f[0];

    b.onclick=()=>{
      if(i===liar){
        completeGame(300,180);
      }else{
        b.classList.add("wrong");
        document.getElementById("bluffBox").insertAdjacentHTML(
          "beforeend","<p>Not the bluff! Try again.</p>"
        );
      }
    };

    box.appendChild(b);
  });
}

/* =========================================================
   7. SURVIVAL
========================================================= */

function survivalRound(){
  gameTitle.textContent="🚪 Survival Round";

  let round=1;
  let lives=3;

  function render(){
    if(round>5){
      completeGame(350,200);
      return;
    }

    const doors=round<3?3:4;
    const safe=Math.floor(Math.random()*doors);

    gameArea.innerHTML=`
      <p>Round ${round} / 5</p>
      <p>❤️ Lives: ${lives}</p>
      <div class="choice-grid" id="doors"></div>
      <p id="surviveStatus"></p>
    `;

    for(let i=0;i<doors;i++){
      const b=document.createElement("button");
      b.className="choice";
      b.textContent="🚪";

      b.onclick=()=>{
        if(i===safe){
          round++;
          document.getElementById("surviveStatus").textContent="Safe! 💗";
          later(render,450);
        }else{
          lives--;
          document.getElementById("surviveStatus").textContent="Trap! 💔";

          if(lives<=0){
            score=Math.max(0,score-100);
            completeGame(100,50);
          }else{
            later(render,500);
          }
        }
      };

      document.getElementById("doors").appendChild(b);
    }
  }

  render();
}

/* =========================================================
   8. ADMIRER RACE
========================================================= */

function admirerRace(){
  gameTitle.textContent="🏇 Admirer's Race";

  let you=0;
  let rival=0;
  let stamina=5;
  let round=0;

  function render(){
    gameArea.innerHTML=`
      <p>Beat the admirer to the finish!</p>
      <div class="race-track">
        <div class="racer">💗 <span style="left:${you}%">🏃</span></div>
        <div class="racer">💔 <span style="left:${rival}%">😏</span></div>
      </div>
      <p>⚡ Stamina: ${stamina}</p>
      <div class="choice-grid">
        <button class="choice" id="run">🏃 RUN</button>
        <button class="choice" id="boost">⚡ BOOST</button>
        <button class="choice" id="rest">😴 REST</button>
      </div>
    `;

    run.onclick=()=>move(18,-1);
    boost.onclick=()=>{
      if(stamina>0)move(30,-2);
      else move(5,-1);
    };
    rest.onclick=()=>move(5,2);
  }

  function move(amount,cost){
    stamina=Math.max(0,stamina+cost);
    you+=amount;

    if(Math.random()<.65) rival+=12;
    else rival+=7;

    round++;

    if(you>=100){
      completeGame(350,200);
      return;
    }

    if(rival>=100){
      you=Math.max(0,you-10);
      rival=80;
    }

    if(round>=8 && you<100){
      rival=Math.max(0,rival-15);
    }

    render();
  }

  render();
}

/* =========================================================
   9. HEARTBREAK CHAMBER
========================================================= */

function heartbreakChamber(){
  gameTitle.textContent="💔 Heartbreak Chamber";

  let stage=0;

  function render(){
    if(stage>=3){
      completeGame(350,200);
      return;
    }

    const puzzles=[
      ["🔢 Which number comes next? 2, 4, 8, 16, ?","32"],
      ["🧩 Which symbol doesn't belong?","💔"],
      ["🔐 What is 3 + 6 × 2?","15"]
    ];

    const q=puzzles[stage];

    gameArea.innerHTML=`
      <p>Puzzle ${stage+1} / 3</p>
      <h3>${q[0]}</h3>
      <div class="choice-grid" id="chChoices"></div>
    `;

    let answers;

    if(stage===0)answers=["24","32","30","20"];
    if(stage===1)answers=["❤️","💗","💖","💔"];
    if(stage===2)answers=["18","12","15","21"];

    answers.sort(()=>Math.random()-.5).forEach(a=>{
      const b=document.createElement("button");
      b.className="choice";
      b.textContent=a;
      b.onclick=()=>{
        if(a===q[1]){
          stage++;
          render();
        }else{
          b.classList.add("wrong");
        }
      };
      document.getElementById("chChoices").appendChild(b);
    });
  }

  render();
}

/* =========================================================
   10. BOXING
========================================================= */

function boxingMatch(){
  gameTitle.textContent="🥊 Heartbreak Boxing";

  let you=0;
  let enemy=0;
  let round=1;

  function render(){
    if(you>=5){
      completeGame(350,200);
      return;
    }

    if(enemy>=5){
      you=0;
      enemy=0;
      round=1;
    }

    const moves=[
      ["PUNCH","BLOCK"],
      ["BLOCK","PUNCH"],
      ["DODGE","PUNCH"]
    ];

    const move=moves[Math.floor(Math.random()*moves.length)];

    gameArea.innerHTML=`
      <p>Round ${round}</p>
      <h2>Opponent: ${"❤️".repeat(Math.max(0,5-enemy))}</h2>
      <p>The opponent used:</p>
      <div class="reward">${move[0]==="PUNCH"?"🥊":move[0]==="BLOCK"?"🛡️":"↪️"}</div>
      <p>Choose your response!</p>
      <div class="choice-grid" id="fight"></div>
      <p id="fightStatus"></p>
    `;

    ["🥊 PUNCH","🛡️ BLOCK","↪️ DODGE"].forEach(a=>{
      const b=document.createElement("button");
      b.className="choice";
      b.textContent=a;

      b.onclick=()=>{
        const chosen=a.split(" ")[1];

        if(chosen===move[1]){
          enemy++;
          document.getElementById("fightStatus").textContent="Great hit! 💥";
        }else{
          document.getElementById("fightStatus").textContent="Miss! 😭";
        }

        round++;
        later(render,450);
      };

      document.getElementById("fight").appendChild(b);
    });
  }

  render();
}

/* =========================================================
   11. PERFECT MATCH
========================================================= */

function perfectMatch(){
  gameTitle.textContent="💕 Perfect Match";

  const pairs=[
    ["🐬","🌊"],
    ["🌻","☀️"],
    ["☕","🖤"],
    ["🎵","🎤"]
  ];

  const cards=pairs.flat().sort(()=>Math.random()-.5);

  gameArea.innerHTML=`
    <p>Find things that belong together.</p>
    <div class="memory-grid" id="pmGrid"></div>
    <p id="pmStatus">Pairs: 0 / 4</p>
  `;

  let first=null;
  let locked=false;
  let found=0;

  cards.forEach(symbol=>{
    const b=document.createElement("button");
    b.className="memory-card";
    b.textContent="❓";
    b.dataset.symbol=symbol;

    b.onclick=()=>{
      if(locked||b.classList.contains("matched")||b===first)return;

      b.textContent=symbol;
      b.classList.add("open");

      if(!first){
        first=b;
        return;
      }

      locked=true;

      const match=pairs.some(p=>
        p.includes(first.dataset.symbol)&&p.includes(b.dataset.symbol)
      );

      if(match){
        first.classList.add("matched");
        b.classList.add("matched");
        found++;
        document.getElementById("pmStatus").textContent=`Pairs: ${found} / 4`;
        first=null;
        locked=false;

        if(found===4)completeGame(300,180);
      }else{
        const old=first;
        later(()=>{
          old.textContent="❓";
          b.textContent="❓";
          old.classList.remove("open");
          b.classList.remove("open");
          first=null;
          locked=false;
        },650);
      }
    };

    document.getElementById("pmGrid").appendChild(b);
  });
}

/* =========================================================
   12. WHO KNOWS LILIANA
========================================================= */

const luluQuestions=[
 ["What is Liliana's favourite number?","3",["3","7","9","5"]],
 ["How many siblings does Liliana have?","5",["2","4","5","6"]],
 ["How many nephews does Liliana have?","4",["2","3","4","5"]],
 ["How many nieces does Liliana have?","1",["1","2","3","4"]],
 ["What are Liliana's dogs called?","Aayla & Arlo",["Aayla & Arlo","Luna & Max","Bella & Milo","Coco & Arlo"]],
 ["What colour are Liliana's eyes?","Green",["Brown","Blue","Green","Hazel"]],
 ["What movie does Liliana like?","Me Before You",["Titanic","Me Before You","Frozen","The Notebook"]],
 ["What does Liliana want someday?","A baby girl",["A baby boy","A baby girl","Twins","No children"]],
 ["What does Liliana like writing?","Poetry",["Poetry","Novels","News","Recipes"]],
 ["What is Liliana's zodiac sign?","Leo",["Leo","Virgo","Libra","Taurus"]]
];

function whoKnowsLiliana(){
  gameTitle.textContent="👑 Who Knows Liliana Best?";

  let qs=[...luluQuestions].sort(()=>Math.random()-.5);
  let i=0;
  let correct=0;

  function show(){
    if(i>=qs.length){
      completeGame(200+correct*25,120+correct*8);
      return;
    }

    const q=qs[i];

    gameArea.innerHTML=`
      <p>Question ${i+1} / ${qs.length}</p>
      <h3>${q[0]}</h3>
      <div class="choice-grid" id="lq"></div>
    `;

    [...q[2]].sort(()=>Math.random()-.5).forEach(a=>{
      const b=document.createElement("button");
      b.className="choice";
      b.textContent=a;
      b.onclick=()=>{
        if(a===q[1])correct++;
        i++;
        show();
      };
      document.getElementById("lq").appendChild(b);
    });
  }

  show();
}

/* =========================================================
   13. REACTION GAUNTLET
========================================================= */

function reactionGauntlet(){
  gameTitle.textContent="⚡ Reaction Gauntlet";

  let round=0;
  let hits=0;

  function render(){
    if(round>=10){
      completeGame(150+hits*20,100+hits*10);
      return;
    }

    const symbols=["❤️","⭐","💎","🌸"];
    const target=symbols[Math.floor(Math.random()*symbols.length)];
    const forbidden=Math.random()<.35;

    gameArea.innerHTML=`
      <p>Round ${round+1} / 10</p>
      <h3>${forbidden?"DON'T TAP":"TAP"} ${target}</h3>
      <div class="choice-grid" id="reaction"></div>
    `;

    [...symbols].sort(()=>Math.random()-.5).forEach(s=>{
      const b=document.createElement("button");
      b.className="choice";
      b.textContent=s;

      b.onclick=()=>{
        const correct=forbidden?s!==target:s===target;
        if(correct)hits++;
        round++;
        render();
      };

      document.getElementById("reaction").appendChild(b);
    });
  }

  render();
}

/* =========================================================
   14. HEART HUNT
========================================================= */

function heartHunt(){
  gameTitle.textContent="💗 Heart Hunt";

  const cells=Array(25).fill(" ");
  let positions=[...Array(25).keys()]
    .sort(()=>Math.random()-.5)
    .slice(0,10);

  positions.forEach(i=>cells[i]="❤️");

  let found=0;
  let misses=0;

  gameArea.innerHTML=`
    <p>Find all 10 hearts!</p>
    <p id="huntStatus">❤️ 0 / 10</p>
    <div class="pattern-grid" id="huntGrid"></div>
  `;

  cells.forEach((v,i)=>{
    const b=document.createElement("button");
    b.className="pattern-cell";
    b.textContent="✨";

    b.onclick=()=>{
      if(b.disabled)return;

      b.disabled=true;

      if(v==="❤️"){
        b.textContent="❤️";
        b.classList.add("lit");
        found++;
      }else{
        b.textContent="💨";
        misses++;
      }

      document.getElementById("huntStatus").textContent=
        `❤️ ${found} / 10  |  Misses: ${misses}`;

      if(found===10){
        completeGame(Math.max(180,350-misses*15),150);
      }
    };

    document.getElementById("huntGrid").appendChild(b);
  });
}

/* =========================================================
   15. LOVE LOCK
========================================================= */

function loveLock(){
  gameTitle.textContent="🔐 Love Lock";

  gameArea.innerHTML=`
    <p>Three clues. One six-digit combination.</p>
    <div class="card" style="margin:10px 0;padding:15px">
      <p>🔎 Clue 1: The month is July.</p>
      <p>🔎 Clue 2: The day is the 6th.</p>
      <p>🔎 Clue 3: The year is 22.</p>
    </div>
    <input id="lockInput" inputmode="numeric" maxlength="6"
           placeholder="Enter 6-digit code">
    <button class="main-btn" id="unlock">🔓 UNLOCK</button>
    <p id="lockStatus"></p>
  `;

  document.getElementById("unlock").onclick=()=>{
    const value=document.getElementById("lockInput").value;

    if(value==="060722"){
      completeGame(350,250);
    }else{
      document.getElementById("lockStatus").textContent=
        "❌ Not quite. Check the clues!";
    }
  };
}

/* =========================================================
   16. CUPID SHOOTOUT
========================================================= */

function cupidShootout(){
  gameTitle.textContent="🏹 Cupid Shootout";

  let hits=0;
  let shots=0;

  gameArea.innerHTML=`
    <p>Hit 10 targets!</p>
    <p id="shootStatus">Hits: 0 / 10</p>
    <div class="fall-area" id="shootArea"></div>
  `;

  const area=document.getElementById("shootArea");

  function target(){
    if(shots>=18)return;

    shots++;

    const b=document.createElement("button");
    b.className="falling";
    b.textContent=Math.random()<.15?"💎":
      Math.random()<.25?"💔":"💖";

    b.style.left=Math.random()*80+"%";
    b.style.top=Math.random()*80+"%";

    area.appendChild(b);

    later(()=>{
      if(b.parentNode)b.remove();
    },1200);

    b.onclick=()=>{
      if(b.textContent==="💔"){
        score=Math.max(0,score-75);
      }else{
        hits++;
        document.getElementById("shootStatus").textContent=
          `Hits: ${hits} / 10`;

        if(hits>=10){
          completeGame(300,180);
        }
      }

      b.remove();
    };
  }

  gameTimer=setInterval(target,600);
}

/* =========================================================
   17. COUNTDOWN
========================================================= */

function countdownGame(){
  gameTitle.textContent="⏳ The Countdown";

  let round=0;
  let correct=0;

  const questions=[
    ["Pick the lucky number","3",["3","8","4","9"]],
    ["Pick Lulu's favourite animal","Dolphin",["Cat","Dolphin","Horse","Fox"]],
    ["Pick the flower she likes","Sunflower",["Rose","Lily","Sunflower","Daisy"]],
    ["Pick the colour she loves","Baby pink",["Red","Baby pink","Orange","Green"]],
    ["Pick the movie","Me Before You",["Frozen","Me Before You","Cars","Shrek"]]
  ];

  function show(){
    if(round>=5){
      completeGame(200+correct*30,120);
      return;
    }

    let seconds=5;
    const q=questions[round];

    gameArea.innerHTML=`
      <p>Round ${round+1} / 5</p>
      <h2 id="count">⏱️ ${seconds}</h2>
      <h3>${q[0]}</h3>
      <div class="choice-grid" id="countChoices"></div>
    `;

    let done=false;

    [...q[2]].sort(()=>Math.random()-.5).forEach(a=>{
      const b=document.createElement("button");
      b.className="choice";
      b.textContent=a;

      b.onclick=()=>{
        if(done)return;
        done=true;

        if(a===q[1])correct++;

        clearInterval(gameTimer);
        round++;
        later(show,300);
      };

      document.getElementById("countChoices").appendChild(b);
    });

    gameTimer=setInterval(()=>{
      seconds--;
      document.getElementById("count").textContent=`⏱️ ${seconds}`;

      if(seconds<=0){
        clearInterval(gameTimer);

        if(!done){
          done=true;
          round++;
          later(show,300);
        }
      }
    },1000);
  }

  show();
}

/* =========================================================
   18. ULTIMATE GAMBLE
========================================================= */

function ultimateGamble(){
  gameTitle.textContent="🎰 Ultimate Gamble";

  let bank=1000;
  let round=0;

  function show(){
    if(round>=6){
      score+=Math.floor(bank/2);
      completeGame(Math.min(500,Math.floor(bank/3)),Math.floor(bank/10));
      return;
    }

    gameArea.innerHTML=`
      <div class="bank">💰 Bank: ${bank}</div>
      <p>Choose your risk.</p>
      <div class="choice-grid">
        <button class="choice" id="safe">🟢 SAFE<br>Small win</button>
        <button class="choice" id="risky">🟡 RISKY<br>Bigger win</button>
        <button class="choice" id="crazy">🔴 CRAZY<br>Huge win</button>
        <button class="choice" id="allin">🟣 ALL IN<br>Everything</button>
      </div>
      <p id="gambleStatus"></p>
    `;

    function gamble(type){
      let change;

      if(type==="safe")
        change=Math.floor(Math.random()*150)+50;
      else if(type==="risky")
        change=Math.random()<.65?300:-150;
      else if(type==="crazy")
        change=Math.random()<.5?700:-400;
      else
        change=Math.random()<.45?bank:-bank;

      bank=Math.max(0,bank+change);
      round++;

      document.getElementById("gambleStatus").textContent=
        change>=0?`WIN +${change}! 🎉`:`LOSS ${change} 💔`;

      later(show,550);
    }

    safe.onclick=()=>gamble("safe");
    risky.onclick=()=>gamble("risky");
    crazy.onclick=()=>gamble("crazy");
    allin.onclick=()=>gamble("allin");
  }

  show();
}

/* =========================================================
   19. ADMIRER'S LAST STAND
========================================================= */

function admirersLastStand(){
  gameTitle.textContent="💘 Admirer's Last Stand";

  let enemy=5;
  let health=5;
  let round=0;

  function render(){
    if(enemy<=0){
      completeGame(400,250);
      return;
    }

    if(health<=0){
      completeGame(150,80);
      return;
    }

    round++;

    gameArea.innerHTML=`
      <p>Round ${round}</p>
      <h3>Admirer's hearts: ${"❤️".repeat(enemy)}</h3>
      <h3>Your hearts: ${"💗".repeat(health)}</h3>
      <div class="choice-grid">
        <button class="choice" id="attack">💘 ATTACK</button>
        <button class="choice" id="defend">🛡️ DEFEND</button>
        <button class="choice" id="charm">✨ CHARM</button>
      </div>
    `;

    attack.onclick=()=>{
      enemy-=2;
      if(Math.random()<.4)health--;
      render();
    };

    defend.onclick=()=>{
      health=Math.min(5,health+1);
      render();
    };

    charm.onclick=()=>{
      if(Math.random()<.7)enemy--;
      else health--;
      render();
    };
  }

  render();
}

/* =========================================================
   20. WORD FIND
========================================================= */

function wordFind(){
  gameTitle.textContent="🔎 Liliana's Word Find";

  const words=[
    "LULU",
    "LOVE",
    "DOLPHIN",
    "SUNFLOWER",
    "ROSE",
    "SUSHI",
    "LUCKY",
    "LEO",
    "POETRY",
    "FOREVER"
  ];

  const SIZE=10;
  const grid=Array(SIZE*SIZE).fill("");
  const placed=[];

  const dirs=[
    [0,1],
    [0,-1],
    [1,0],
    [-1,0],
    [1,1],
    [1,-1],
    [-1,1],
    [-1,-1]
  ];

  function placeWord(word){
    for(let attempt=0;attempt<1000;attempt++){
      const d=dirs[Math.floor(Math.random()*dirs.length)];
      const r=Math.floor(Math.random()*SIZE);
      const c=Math.floor(Math.random()*SIZE);

      const cells=[];
      let ok=true;

      for(let i=0;i<word.length;i++){
        const rr=r+d[0]*i;
        const cc=c+d[1]*i;

        if(rr<0||rr>=SIZE||cc<0||cc>=SIZE){
          ok=false;
          break;
        }

        const pos=rr*SIZE+cc;

        if(grid[pos] && grid[pos]!==word[i]){
          ok=false;
          break;
        }

        cells.push(pos);
      }

      if(ok){
        cells.forEach((pos,i)=>grid[pos]=word[i]);
        placed.push({word,cells});
        return true;
      }
    }

    return false;
  }

  [...words]
    .sort((a,b)=>b.length-a.length)
    .forEach(placeWord);

  const letters="ABCDEFGHIJKLMNOPQRSTUVWXYZ";

  for(let i=0;i<grid.length;i++){
    if(!grid[i])
      grid[i]=letters[Math.floor(Math.random()*letters.length)];
  }

  gameArea.innerHTML=`
    <p>Find all 10 words.</p>
    <div class="word-list" id="wordList"></div>
    <div class="word-grid" id="wordGrid"></div>
    <p id="wordStatus">Tap letters in order.</p>
  `;

  words.forEach(w=>{
    const s=document.createElement("span");
    s.className="word";
    s.id="word-"+w;
    s.textContent=w;
    document.getElementById("wordList").appendChild(s);
  });

  let selected=[];
  let found=0;

  grid.forEach((letter,i)=>{
    const b=document.createElement("button");
    b.className="letter";
    b.textContent=letter;

    b.onclick=()=>{
      if(b.classList.contains("found"))return;

      selected.push({i,b});

      b.classList.add("selected");

      const sequence=selected.map(x=>grid[x.i]).join("");

      const reverse=sequence.split("").reverse().join("");

      const match=placed.find(p=>
        !document.getElementById("word-"+p.word).classList.contains("done") &&
        (sequence===p.word || reverse===p.word)
      );

      if(match){
        selected.forEach(x=>{
          x.b.classList.remove("selected");
          x.b.classList.add("found");
        });

        document.getElementById("word-"+match.word).classList.add("done");

        found++;
        selected=[];

        document.getElementById("wordStatus").textContent=
          `Found ${found} / 10`;

        if(found===10){
          completeGame(400,250);
        }

      }else if(selected.length>=10){
        selected.forEach(x=>x.b.classList.remove("selected"));
        selected=[];
      }
    };

    document.getElementById("wordGrid").appendChild(b);
  });
}

/* =========================================================
   21. DRAW SUNFLOWER
========================================================= */

function drawSunflower(){
  gameTitle.textContent="🌻 Draw a Sunflower";

  gameArea.innerHTML=`
    <p>Draw a sunflower! Fill the canvas with your own drawing.</p>
    <canvas id="drawCanvas" width="380" height="380"></canvas>
    <button class="main-btn secondary" id="clearDraw">CLEAR</button>
    <button class="main-btn" id="finishDraw">🌻 I'M DONE</button>
    <p id="drawStatus"></p>
  `;

  const canvas=document.getElementById("drawCanvas");
  const ctx=canvas.getContext("2d");

  ctx.lineWidth=7;
  ctx.lineCap="round";
  ctx.strokeStyle="#6b3454";

  let drawing=false;
  let strokes=0;

  function pos(e){
    const r=canvas.getBoundingClientRect();
    const touch=e.touches?e.touches[0]:e;
    return {
      x:(touch.clientX-r.left)*canvas.width/r.width,
      y:(touch.clientY-r.top)*canvas.height/r.height
    };
  }

  canvas.addEventListener("pointerdown",e=>{
    drawing=true;
    strokes++;
    const p=pos(e);
    ctx.beginPath();
    ctx.moveTo(p.x,p.y);
  });

  canvas.addEventListener("pointermove",e=>{
    if(!drawing)return;
    const p=pos(e);
    ctx.lineTo(p.x,p.y);
    ctx.stroke();
  });

  canvas.addEventListener("pointerup",()=>{
    drawing=false;
  });

  document.getElementById("clearDraw").onclick=()=>{
    ctx.clearRect(0,0,canvas.width,canvas.height);
    strokes=0;
  };

  document.getElementById("finishDraw").onclick=()=>{
    if(strokes<5){
      document.getElementById("drawStatus").textContent=
        "Add a few more strokes first! 🌻";
      return;
    }

    completeGame(350,220);
  };
}

/* =========================================================
   22. LULU DERBY
========================================================= */

function luluDerby(){
  gameTitle.textContent="🏇 Lulu Derby";

  gameArea.innerHTML=`
    <h3>Choose your animal</h3>
    <div class="animal-grid" id="animals"></div>
    <h3>Choose difficulty</h3>
    <div class="choice-grid" id="difficulty"></div>
  `;

  let chosen=null;

  const animals=[
    ["🐎","Horse"],
    ["🦄","Unicorn"],
    ["🐬","Dolphin"],
    ["🦋","Butterfly"],
    ["🐰","Bunny"],
    ["🦊","Fox"]
  ];

  animals.forEach(a=>{
    const b=document.createElement("button");
    b.className="animal";
    b.innerHTML=`${a[0]}<small>${a[1]}</small>`;

    b.onclick=()=>{
      chosen=a;
      document.querySelectorAll(".animal").forEach(x=>x.style.outline="none");
      b.style.outline="3px solid #ff9ac7";
    };

    document.getElementById("animals").appendChild(b);
  });

  ["EASY","MEDIUM","HARD","EXPERT"].forEach(level=>{
    const b=document.createElement("button");
    b.className="choice";
    b.textContent=level;

    b.onclick=()=>{
      if(!chosen)return;
      derbyRace(chosen,level);
    };

    document.getElementById("difficulty").appendChild(b);
  });
}

function derbyRace(animal,difficulty){
  const rules={
    EASY:{rounds:5,move:25,rival:13,stamina:6},
    MEDIUM:{rounds:6,move:22,rival:15,stamina:5},
    HARD:{rounds:7,move:20,rival:17,stamina:4},
    EXPERT:{rounds:8,move:18,rival:19,stamina:3}
  };

  const r=rules[difficulty];

  let you=0;
  let rival=0;
  let stamina=r.stamina;
  let round=0;

  function render(){
    if(round>=r.rounds){
      const win=you>rival;

      if(win){
        completeGame(
          difficulty==="EXPERT"?500:
          difficulty==="HARD"?450:
          difficulty==="MEDIUM"?400:350,
          250
        );
      }else{
        gameArea.innerHTML=`
          <div class="reward">😱</div>
          <h2>So close!</h2>
          <p>${animal[0]} finished ${you}% against ${rival}%.</p>
          <button class="main-btn" onclick="luluDerby()">TRY AGAIN</button>
        `;
      }
      return;
    }

    gameArea.innerHTML=`
      <p>${animal[0]} ${animal[1]} • ${difficulty}</p>
      <p>Round ${round+1} / ${r.rounds}</p>

      <div class="race-track">
        <div class="racer">
          ${animal[0]} <span style="left:${Math.min(90,you)}%">🏇</span>
        </div>

        <div class="racer">
          😈 <span style="left:${Math.min(90,rival)}%">🏇</span>
        </div>
      </div>

      <p>⚡ Stamina: ${stamina}</p>

      <div class="choice-grid">
        <button class="choice" id="dRun">🏃 RUN</button>
        <button class="choice" id="dBoost">⚡ BOOST</button>
        <button class="choice" id="dRest">😴 REST</button>
      </div>
    `;

    dRun.onclick=()=>{
      you+=r.move;
      rival+=r.rival;
      round++;
      render();
    };

    dBoost.onclick=()=>{
      if(stamina>0){
        stamina--;
        you+=r.move+10;
      }else{
        you+=5;
      }

      rival+=r.rival;
      round++;
      render();
    };

    dRest.onclick=()=>{
      stamina=Math.min(r.stamina,stamina+2);
      you+=7;
      rival+=r.rival;
      round++;
      render();
    };
  }

  render();
}

/* =========================================================
   23. FINAL CHALLENGE
========================================================= */

const finalQuestions=[
["What is Liliana's favourite number?","3",["3","5","7","9"]],
["What is her favourite food?","Sushi",["Pizza","Sushi","Tacos","Pasta"]],
["What animal does she love?","Dolphins",["Dolphins","Cats","Horses","Foxes"]],
["What colour does she love?","Baby pink",["Baby pink","Purple","Red","Green"]],
["What flowers does she like?","Sunflowers and roses",["Tulips","Sunflowers and roses","Lilies","Daisies"]],
["What is her star sign?","Leo",["Leo","Aries","Cancer","Libra"]],
["What did she study?","Psychology",["Psychology","Law","Nursing","Art"]],
["How many siblings does she have?","5",["3","4","5","6"]],
["How many nephews does she have?","4",["2","3","4","5"]],
["How many nieces does she have?","1",["1","2","3","4"]],
["What are her dogs called?","Aayla and Arlo",["Aayla and Arlo","Luna and Max","Milo and Coco","Bella and Arlo"]],
["What colour are her eyes?","Green",["Blue","Brown","Green","Hazel"]],
["What movie does she like?","Me Before You",["Titanic","Me Before You","Frozen","The Notebook"]],
["What does she enjoy?","Sad songs and poetry",["Comedy","Sad songs and poetry","Only podcasts","Action films"]],
["What does she want someday?","A baby girl",["A baby boy","A baby girl","Twins","No children"]],
["How many years have you been best friends?","6",["4","5","6","7"]],
["Which animal is in her favourite animal list?","Dolphin",["Dolphin","Lion","Koala","Panda"]],
["Which flower is one she likes?","Rose",["Rose","Orchid","Lily","Daffodil"]],
["What personality description fits her?","Caring",["Caring","Cold","Unfriendly","Quiet"]],
["What hobby does she enjoy?","Poker",["Golf","Poker","Fishing","Cycling"]],
["What subject is connected to her university study?","Psychology",["Physics","Psychology","Chemistry","Engineering"]],
["What does she like to read/write?","Poetry",["Poetry","Cookbooks","Textbooks only","Comics only"]],
["What is one of her favourite flowers?","Sunflower",["Sunflower","Iris","Carnation","Violet"]],
["What food does she love?","Sushi",["Sushi","Steak","Curry","Burgers"]],
["What animal represents her favourite?","Dolphin",["Dolphin","Wolf","Bear","Rabbit"]],
["What colour is her favourite?","Baby pink",["Baby pink","Burgundy","Yellow","Orange"]],
["What is her zodiac sign?","Leo",["Leo","Gemini","Leo","Capricorn"]],
["How many dogs does she have?","2",["1","2","3","4"]],
["Name one dog.","Aayla",["Aayla","Lola","Arlo","Mika"]],
["Name the other dog.","Arlo",["Arlo","Aayla","Ayla","Luna"]],
["How many piercings does she have?","4",["2","3","4","5"]],
["What does she fear?","Drowning",["Heights","Drowning","Flying","Spiders"]],
["What kind of game does she like?","Poker",["Poker","Chess","Golf","Cricket"]],
["What does she want to be someday?","A mum",["A pilot","A mum","A lawyer","A singer"]],
["What would her baby girl wish connect to?","Motherhood",["Motherhood","Space travel","Racing","Cooking"]],
["Which flower has a sunny name?","Sunflower",["Sunflower","Rose","Lily","Orchid"]],
["Which animal lives in the ocean?","Dolphin",["Dolphin","Fox","Horse","Bunny"]],
["What colour is associated with her favourite aesthetic?","Baby pink",["Baby pink","Black","Orange","Brown"]],
["What number keeps appearing in her story?","3",["3","8","1","6"]],
["What kind of songs does she enjoy?","Sad songs",["Sad songs","Only rap","Only classical","Only rock"]],
["What kind of writing does she like?","Poetry",["Poetry","Manuals","Reports","News only"]],
["What film is a favourite?","Me Before You",["Me Before You","Cars","Avatar","Shrek"]],
["What is her eye colour?","Green",["Green","Blue","Grey","Brown"]],
["What is her favourite animal?","Dolphin",["Dolphin","Penguin","Tiger","Horse"]],
["What did she study at university?","Psychology",["Psychology","Biology","Music","Business"]],
["How many siblings?","5",["4","5","6","7"]],
["How many nephews?","4",["1","2","4","6"]],
["How many nieces?","1",["1","2","4","5"]],
["What colour does Liliana love?","Baby pink",["Blue","Baby pink","Green","Red"]],
["What is Liliana's favourite food?","Sushi",["Sushi","Pizza","Rice","Pasta"]]
];

function finalChallenge(){
  gameTitle.textContent="🏆 Final Challenge";

  let questions=[...finalQuestions]
    .sort(()=>Math.random()-.5)
    .slice(0,50);

  let index=0;
  let correct=0;

  function show(){
    if(index>=50){
      score += correct*70;
      tokens += correct*15;

      completeGame(
        correct*70,
        correct*15
      );

      return;
    }

    const q=questions[index];

    gameArea.innerHTML=`
      <p>FINAL CHALLENGE</p>
      <p>Question ${index+1} / 50</p>
      <div class="final-question">${q[0]}</div>
      <div class="choice-grid" id="finalChoices"></div>
      <p id="finalStatus"></p>
    `;

    [...q[2]].sort(()=>Math.random()-.5).forEach(answer=>{
      const b=document.createElement("button");
      b.className="choice";
      b.textContent=answer;

      b.onclick=()=>{
        if(answer===q[1]){
          correct++;
          document.getElementById("finalStatus").textContent="Correct! 💗";
        }else{
          document.getElementById("finalStatus").textContent=
            "Not quite! 💔";
        }

        document.querySelectorAll("#finalChoices button")
          .forEach(x=>x.disabled=true);

        index++;
        later(show,300);
      };

      document.getElementById("finalChoices").appendChild(b);
    });
  }

  show();
}

/* =========================================================
   FINISH
========================================================= */

function finishJourney(){
  clearTimers();

  showScreen("finish");

  const privateCall=score>3000;

  document.getElementById("finishText").innerHTML=
    `You made it through all 23 levels, ${escapeHTML(player)}!<br><br>
     Final score: <strong>${score}</strong>`;

  document.getElementById("rewardBox").innerHTML=
    privateCall
    ? `
      <div class="card">
        <div class="reward">💌📞</div>
        <h2>PRIVATE CALL UNLOCKED!</h2>
        <p>You scored <strong>${score}</strong>.</p>
        <p>You needed more than 3000 points and you did it! 💗</p>
      </div>
    `
    : `
      <div class="card">
        <div class="reward">💗</div>
        <h2>YOU DID IT!</h2>
        <p>You finished the whole journey.</p>
        <p>Final score: <strong>${score}</strong></p>
        <p>Keep this little universe forever.</p>
      </div>
    `;
}

/* =========================================================
   MUSIC
========================================================= */

function toggleMusic(){
  musicOn=!musicOn;

  document.getElementById("musicText").textContent=
    `Music: ${musicOn?"ON":"OFF"}`;

  if(musicOn){
    if(!audioCtx)
      audioCtx=new (window.AudioContext||window.webkitAudioContext)();

    playTone(523,.15);
  }
}

function playTone(freq,duration){
  if(!musicOn)return;

  if(!audioCtx)
    audioCtx=new (window.AudioContext||window.webkitAudioContext)();

  const osc=audioCtx.createOscillator();
  const gain=audioCtx.createGain();

  osc.frequency.value=freq;
  osc.type="sine";

  gain.gain.setValueAtTime(.035,audioCtx.currentTime);
  gain.gain.exponentialRampToValueAtTime(
    .001,
    audioCtx.currentTime+duration
  );

  osc.connect(gain);
  gain.connect(audioCtx.destination);

  osc.start();
  osc.stop(audioCtx.currentTime+duration);
}

/* =========================================================
   RESET
========================================================= */

function resetJourney(){
  clearTimers();

  score=0;
  tokens=0;
  currentLevel=1;
  player="";

  document.getElementById("playerName").value="";
  document.getElementById("playerName").placeholder="Enter your name";

  showScreen("start");
}
</script>

</body>
</html>

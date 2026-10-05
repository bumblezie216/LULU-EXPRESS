<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<meta name="apple-mobile-web-app-capable" content="yes">

<title>Lulu Express 💗</title>

<style>
*{
  box-sizing:border-box;
  -webkit-tap-highlight-color:transparent;
}

html,body{
  margin:0;
  padding:0;
  width:100%;
  min-height:100%;
  font-family:Arial,Helvetica,sans-serif;
  background:#f7bfd6;
  color:#571b38;
  overflow-x:hidden;
}

button{
  font-family:inherit;
  border:0;
  cursor:pointer;
  touch-action:manipulation;
}

.hidden{
  display:none!important;
}

.screen{
  min-height:100vh;
  min-height:100dvh;
  width:100%;
  padding:20px;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  text-align:center;
}

.card{
  width:100%;
  max-width:600px;
  background:rgba(255,255,255,.96);
  border-radius:28px;
  padding:25px;
  box-shadow:0 12px 40px rgba(80,0,40,.18);
}

h1{
  font-size:clamp(30px,8vw,52px);
  margin:5px 0 12px;
}

h2{
  font-size:clamp(24px,6vw,36px);
  margin:5px 0 15px;
}

p{
  font-size:18px;
  line-height:1.5;
}

.small{
  font-size:14px;
}

input{
  width:100%;
  max-width:420px;
  padding:17px;
  border-radius:15px;
  border:2px solid #e58db0;
  font-size:18px;
  text-align:center;
  outline:none;
  margin:10px 0;
}

.mainBtn{
  width:100%;
  max-width:420px;
  padding:17px 20px;
  border-radius:18px;
  background:#8d2458;
  color:white;
  font-size:18px;
  font-weight:bold;
  margin:8px 0;
}

.mainBtn:active{
  transform:scale(.97);
}

.secondary{
  background:#e99abd;
  color:#571b38;
}

.danger{
  background:#7c193f;
  color:white;
}

.topbar{
  position:fixed;
  top:0;
  left:0;
  width:100%;
  z-index:100;
  padding:10px 12px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  background:rgba(87,27,56,.96);
  color:white;
  font-size:14px;
}

.topbar button{
  padding:9px 12px;
  border-radius:12px;
  background:#f3aac8;
  color:#571b38;
  font-weight:bold;
}

.gameScreen{
  padding-top:70px;
  padding-bottom:30px;
}

.gameNumber{
  font-size:14px;
  font-weight:bold;
  opacity:.75;
  margin-bottom:5px;
}

.choiceGrid{
  display:grid;
  grid-template-columns:1fr;
  gap:12px;
  margin-top:18px;
}

.choice{
  width:100%;
  padding:17px 14px;
  background:#f6d1df;
  color:#571b38;
  border:2px solid #e8a3bf;
  border-radius:17px;
  font-size:17px;
  font-weight:bold;
}

.choice:active{
  transform:scale(.97);
}

.choice.correct{
  background:#b8e7c4;
  border-color:#5baf70;
}

.choice.wrong{
  background:#f2b4b4;
  border-color:#c65d5d;
}

.message{
  min-height:30px;
  margin-top:15px;
  font-weight:bold;
  font-size:18px;
}

.progress{
  width:100%;
  height:12px;
  background:#f0d8e2;
  border-radius:20px;
  overflow:hidden;
  margin:15px 0;
}

.progressBar{
  height:100%;
  width:0%;
  background:#8d2458;
  transition:.25s;
}

.bigHeart{
  font-size:70px;
  margin:10px;
}

.tileGrid{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:12px;
  margin-top:20px;
}

.tile{
  aspect-ratio:1;
  border-radius:18px;
  background:#f4d2df;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:35px;
  font-weight:bold;
  border:2px solid #e7a4be;
}

.tile.selected{
  background:#ef9fbd;
}

.tile.found{
  background:#b8e7c4;
}

.numberBox{
  font-size:60px;
  font-weight:bold;
  margin:20px;
}

.lock{
  font-size:85px;
  margin:10px;
}

.stat{
  display:inline-block;
  padding:8px 12px;
  background:#f6d1df;
  border-radius:15px;
  margin:3px;
  font-weight:bold;
}

.reward{
  background:#fff0a8;
  border:2px solid #e5c83c;
  padding:20px;
  border-radius:20px;
  margin-top:20px;
}

.questionCount{
  font-size:15px;
  font-weight:bold;
  margin-bottom:8px;
}

.timer{
  font-size:28px;
  font-weight:bold;
  margin:10px;
}

.letters{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:8px;
  margin-top:15px;
}

.letter{
  padding:15px 5px;
  border-radius:13px;
  background:#f4d2df;
  font-weight:bold;
  font-size:17px;
}

.wordList{
  display:flex;
  flex-wrap:wrap;
  justify-content:center;
  gap:8px;
  margin:15px 0;
}

.word{
  padding:10px 13px;
  background:#f5d5e1;
  border-radius:13px;
  font-weight:bold;
}

#gameArea{
  width:100%;
  display:flex;
  justify-content:center;
}

@media(min-width:600px){
  .choiceGrid.two{
    grid-template-columns:1fr 1fr;
  }
}
</style>
</head>

<body>

<div id="startScreen" class="screen">
  <div class="card">
    <div style="font-size:80px">💗</div>
    <h1>Lulu Express</h1>
    <p>
      Welcome to the ultimate journey for Lulu.
      <br><br>
      23 levels stand between you and the final challenge.
    </p>

    <input id="playerName" type="text" maxlength="30" placeholder="Enter your name">

    <button class="mainBtn" id="startBtn">
      🚂 Start the Journey
    </button>

    <button class="mainBtn secondary" id="musicBtnStart">
      🎵 Music: OFF
    </button>
  </div>
</div>

<div id="gameScreen" class="screen gameScreen hidden">

  <div class="topbar">
    <div>
      <span id="topName">Player</span>
      ·
      <span id="topScore">0</span> pts
      ·
      <span id="topTokens">0</span> tokens
    </div>

    <div>
      <button id="musicBtn">🎵</button>
      <button id="resetBtn">↻</button>
    </div>
  </div>

  <div id="gameArea"></div>

</div>

<script>

/* =========================================================
   BASIC GAME STATE
========================================================= */

const state = {
  name:"",
  level:1,
  score:0,
  tokens:0,
  music:false
};

let gameData = {};
let audioContext = null;


/* =========================================================
   MUSIC
========================================================= */

function toggleMusic(){

  state.music = !state.music;

  updateMusicButtons();

  if(state.music){
    startSimpleMusic();
  }
}

function updateMusicButtons(){

  document.getElementById("musicBtnStart").textContent =
    state.music ? "🎵 Music: ON" : "🎵 Music: OFF";

  document.getElementById("musicBtn").textContent =
    state.music ? "🎵 ON" : "🎵";
}

function startSimpleMusic(){

  try{

    if(!audioContext){
      audioContext =
        new (window.AudioContext || window.webkitAudioContext)();
    }

    if(audioContext.state === "suspended"){
      audioContext.resume();
    }

    playNote(392,0);
    setTimeout(()=>playNote(523,0),180);
    setTimeout(()=>playNote(659,0),360);

  }catch(e){}
}

function playNote(freq,delay){

  setTimeout(()=>{

    try{

      const osc = audioContext.createOscillator();
      const gain = audioContext.createGain();

      osc.frequency.value = freq;
      osc.type = "sine";

      gain.gain.setValueAtTime(.06,audioContext.currentTime);
      gain.gain.exponentialRampToValueAtTime(
        .001,
        audioContext.currentTime+.45
      );

      osc.connect(gain);
      gain.connect(audioContext.destination);

      osc.start();
      osc.stop(audioContext.currentTime+.45);

    }catch(e){}

  },delay);
}


/* =========================================================
   TOP BAR
========================================================= */

function updateTop(){

  document.getElementById("topName").textContent = state.name;
  document.getElementById("topScore").textContent = state.score;
  document.getElementById("topTokens").textContent = state.tokens;

}


/* =========================================================
   REWARDS
========================================================= */

function reward(points,tokens){

  state.score += points;
  state.tokens += tokens;

  updateTop();
}


/* =========================================================
   START / RESET
========================================================= */

document.getElementById("startBtn").addEventListener("click",()=>{

  const name =
    document.getElementById("playerName").value.trim();

  if(!name){
    alert("Please enter your name first 💗");
    return;
  }

  state.name = name;
  state.level = 1;
  state.score = 0;
  state.tokens = 0;

  document.getElementById("startScreen")
    .classList.add("hidden");

  document.getElementById("gameScreen")
    .classList.remove("hidden");

  updateTop();
  showGame();

});


document.getElementById("musicBtnStart")
  .addEventListener("click",toggleMusic);

document.getElementById("musicBtn")
  .addEventListener("click",toggleMusic);

document.getElementById("resetBtn")
  .addEventListener("click",()=>{

    if(confirm("Restart the whole Lulu Express journey?")){
      location.reload();
    }

  });


/* =========================================================
   GAME FINISH
========================================================= */

function finishGame(points,tokens,message){

  reward(points,tokens);

  const area = document.getElementById("gameArea");

  area.innerHTML += `
    <div class="card" style="margin-top:18px">
      <div style="font-size:50px">🎉</div>
      <h2>Level Complete!</h2>
      <p>${message}</p>
      <p>
        <span class="stat">+${points} points</span>
        <span class="stat">+${tokens} tokens</span>
      </p>
      <button class="mainBtn" id="nextBtn">
        Continue to Level ${state.level + 1} →
      </button>
    </div>
  `;

  document.getElementById("nextBtn")
    .addEventListener("click",()=>{

      state.level++;

      if(state.level > 23){
        showFinalResult();
      }else{
        showGame();
      }

    });

}


/* =========================================================
   SHOW GAME
========================================================= */

function showGame(){

  const area = document.getElementById("gameArea");

  area.innerHTML = "";

  updateTop();

  const games = [

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

  games[state.level-1]();

}


/* =========================================================
   GAME 1
   BROKEN HEARTS
========================================================= */

function game1(){

  let found = 0;

  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <div class="gameNumber">LEVEL 1 OF 23</div>
      <h2>💔 Broken Hearts</h2>
      <p>Tap all 8 hearts to repair Lulu's broken heart!</p>

      <div class="tileGrid" id="heartGrid"></div>

      <div class="message" id="g1msg">
        Hearts found: 0 / 8
      </div>
    </div>
  `;

  const grid = document.getElementById("heartGrid");

  for(let i=0;i<12;i++){

    const tile = document.createElement("button");

    tile.className="tile";

    const heart = i < 8;

    tile.textContent =
      heart ? "💗" : "🌸";

    tile.addEventListener("click",()=>{

      if(tile.classList.contains("found")) return;

      if(heart){

        tile.classList.add("found");
        found++;

        document.getElementById("g1msg").textContent =
          `Hearts found: ${found} / 8`;

        if(found===8){

          setTimeout(()=>{
            finishGame(
              150,
              25,
              "You repaired Lulu's heart! 💗"
            );
          },300);

        }

      }else{

        tile.classList.add("selected");

      }

    });

    grid.appendChild(tile);
  }

}


/* =========================================================
   GAME 2
   MEMORY
========================================================= */

function game2(){

  const symbols = ["🌹","🌹","🐬","🐬","🌻","🌻","💗","💗"];

  symbols.sort(()=>Math.random()-.5);

  let open = [];
  let matched = 0;

  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <div class="gameNumber">LEVEL 2 OF 23</div>
      <h2>🧠 Memory Match</h2>
      <p>Find all 4 matching pairs.</p>
      <div class="tileGrid" id="memoryGrid"></div>
      <div class="message" id="g2msg">Pairs: 0 / 4</div>
    </div>
  `;

  const grid=document.getElementById("memoryGrid");

  symbols.forEach(symbol=>{

    const tile=document.createElement("button");

    tile.className="tile";
    tile.textContent="❓";

    tile.addEventListener("click",()=>{

      if(tile.dataset.done==="yes") return;
      if(open.includes(tile)) return;
      if(open.length>=2) return;

      tile.textContent=symbol;
      tile.dataset.symbol=symbol;
      open.push(tile);

      if(open.length===2){

        if(open[0].dataset.symbol===open[1].dataset.symbol){

          open.forEach(x=>{
            x.dataset.done="yes";
            x.classList.add("found");
          });

          matched++;

          document.getElementById("g2msg").textContent =
            `Pairs: ${matched} / 4`;

          open=[];

          if(matched===4){

            setTimeout(()=>{
              finishGame(
                150,
                25,
                "Perfect memory! 🧠💗"
              );
            },300);

          }

        }else{

          const pair=open;
          open=[];

          setTimeout(()=>{

            pair.forEach(x=>{
              x.textContent="❓";
            });

          },600);

        }

      }

    });

    grid.appendChild(tile);

  });

}


/* =========================================================
   GAME 3
   PRESSURE QUIZ
========================================================= */

const pressureQuestions = [

  ["What is Liliana's favourite number?",["3","5","7","9"],0],
  ["What colour does Liliana love?",["Baby pink","Green","Orange","Purple"],0],
  ["What animal does Liliana love?",["Dolphins","Lions","Penguins","Tigers"],0],
  ["What is Liliana's star sign?",["Leo","Gemini","Taurus","Pisces"],0],
  ["What food does Liliana love?",["Sushi","Pizza","Pasta","Tacos"],0]

];

function game3(){

  let q=0;
  let correct=0;

  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <div class="gameNumber">LEVEL 3 OF 23</div>
      <h2>⏱️ Pressure Quiz</h2>

      <div class="questionCount" id="g3count"></div>
      <div class="progress">
        <div class="progressBar" id="g3bar"></div>
      </div>

      <h3 id="g3question"></h3>
      <div class="choiceGrid" id="g3choices"></div>
      <div class="message" id="g3msg"></div>
    </div>
  `;

  function load(){

    if(q>=pressureQuestions.length){

      finishGame(
        correct*50,
        correct*5,
        `You got ${correct}/${pressureQuestions.length} correct!`
      );

      return;
    }

    const item=pressureQuestions[q];

    document.getElementById("g3count").textContent =
      `Question ${q+1} of ${pressureQuestions.length}`;

    document.getElementById("g3bar").style.width =
      `${(q/pressureQuestions.length)*100}%`;

    document.getElementById("g3question").textContent=item[0];

    const choices=document.getElementById("g3choices");

    choices.innerHTML="";

    item[1].forEach((answer,index)=>{

      const btn=document.createElement("button");
      btn.className="choice";
      btn.textContent=answer;

      btn.addEventListener("click",()=>{

        if(index===item[2]){

          btn.classList.add("correct");
          correct++;

        }else{

          btn.classList.add("wrong");

        }

        q++;

        setTimeout(load,400);

      });

      choices.appendChild(btn);

    });

  }

  load();

}


/* =========================================================
   GAME 4
   HIGH ROLLER
========================================================= */

function game4(){

  let tries=0;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 4 OF 23</div>
      <h2>🎲 High Roller</h2>
      <p>Roll the dice. You need a 4, 5 or 6.</p>
      <div class="numberBox" id="dice">?</div>
      <button class="mainBtn" id="rollBtn">ROLL 🎲</button>
      <div class="message" id="g4msg"></div>
    </div>
  `;

  document.getElementById("rollBtn")
    .addEventListener("click",()=>{

      tries++;

      const number=Math.floor(Math.random()*6)+1;

      document.getElementById("dice").textContent=number;

      if(number>=4){

        document.getElementById("g4msg").textContent=
          "🎉 Lucky roll!";

        setTimeout(()=>{
          finishGame(150,25,"The house lost this time! 🎲");
        },500);

      }else{

        document.getElementById("g4msg").textContent=
          "Not high enough. Roll again!";

      }

    });

}


/* =========================================================
   GAME 5
   ODD ONE OUT
========================================================= */

function game5(){

  const symbols=["🌸","🌸","🌸","🌹"];

  const oddIndex=Math.floor(Math.random()*4);

  symbols[oddIndex]="🌹";

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 5 OF 23</div>
      <h2>🔎 Odd One Out</h2>
      <p>Tap the different flower.</p>
      <div class="choiceGrid two" id="g5grid"></div>
      <div class="message" id="g5msg"></div>
    </div>
  `;

  const grid=document.getElementById("g5grid");

  for(let i=0;i<4;i++){

    const btn=document.createElement("button");
    btn.className="choice";
    btn.textContent=symbols[i];

    btn.addEventListener("click",()=>{

      if(i===oddIndex){

        btn.classList.add("correct");

        setTimeout(()=>{
          finishGame(150,25,"Sharp eyes! 🔎");
        },400);

      }else{

        btn.classList.add("wrong");

        document.getElementById("g5msg").textContent=
          "Try another one!";

      }

    });

    grid.appendChild(btn);

  }

}


/* =========================================================
   GAME 6
   BLUFF
========================================================= */

function game6(){

  const winner=Math.floor(Math.random()*3);

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 6 OF 23</div>
      <h2>🃏 Bluff</h2>
      <p>One card wins. Choose wisely.</p>
      <div class="choiceGrid">
        <button class="choice" data-card="0">🂠 CARD 1</button>
        <button class="choice" data-card="1">🂠 CARD 2</button>
        <button class="choice" data-card="2">🂠 CARD 3</button>
      </div>
      <div class="message" id="g6msg"></div>
    </div>
  `;

  document.querySelectorAll("[data-card]").forEach(btn=>{

    btn.addEventListener("click",()=>{

      const chosen=Number(btn.dataset.card);

      if(chosen===winner){

        btn.classList.add("correct");

        setTimeout(()=>{
          finishGame(150,25,"You beat the bluff! 🃏");
        },400);

      }else{

        btn.classList.add("wrong");

        document.getElementById("g6msg").textContent=
          "That wasn't the winning card. Try again.";

      }

    });

  });

}


/* =========================================================
   GAME 7
   SAFE CHOICE
========================================================= */

function game7(){

  let round=0;
  let safe=Math.floor(Math.random()*3);

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 7 OF 23</div>
      <h2>🛡️ Safe Choice</h2>
      <p>Choose the safe door.</p>
      <div class="questionCount" id="g7round">
        Round 1 of 3
      </div>
      <div class="choiceGrid">
        <button class="choice" data-door="0">🚪 Door 1</button>
        <button class="choice" data-door="1">🚪 Door 2</button>
        <button class="choice" data-door="2">🚪 Door 3</button>
      </div>
      <div class="message" id="g7msg"></div>
    </div>
  `;

  document.querySelectorAll("[data-door]").forEach(btn=>{

    btn.addEventListener("click",()=>{

      const chosen=Number(btn.dataset.door);

      if(chosen!==safe){

        document.getElementById("g7msg").textContent=
          "💥 Danger! Choose again.";

        return;

      }

      round++;

      if(round>=3){

        finishGame(150,25,"You survived all three rounds! 🛡️");

        return;

      }

      safe=Math.floor(Math.random()*3);

      document.getElementById("g7round").textContent=
        `Round ${round+1} of 3`;

      document.getElementById("g7msg").textContent=
        "Safe! Next round.";

    });

  });

}


/* =========================================================
   GAME 8
   LULU RACE
========================================================= */

function game8(){

  let taps=0;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 8 OF 23</div>
      <h2>🏁 Lulu Race</h2>
      <p>Tap the button 10 times to win the race!</p>

      <div class="progress">
        <div class="progressBar" id="g8bar"></div>
      </div>

      <div class="numberBox" id="g8count">0 / 10</div>

      <button class="mainBtn" id="raceBtn">
        TAP! 🏁
      </button>
    </div>
  `;

  document.getElementById("raceBtn")
    .addEventListener("click",()=>{

      taps++;

      document.getElementById("g8count").textContent=
        `${taps} / 10`;

      document.getElementById("g8bar").style.width=
        `${taps*10}%`;

      if(taps>=10){

        finishGame(150,25,"You crossed the finish line! 🏁");

      }

    });

}


/* =========================================================
   GAME 9
   HEARTBREAK
========================================================= */

function game9(){

  let hits=0;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 9 OF 23</div>
      <h2>💔 Heartbreak Chamber</h2>
      <p>Tap the broken heart 10 times.</p>

      <div class="bigHeart" id="g9heart">💔</div>

      <div class="numberBox" id="g9count">0 / 10</div>

      <button class="mainBtn" id="g9btn">
        SMASH 💔
      </button>
    </div>
  `;

  document.getElementById("g9btn")
    .addEventListener("click",()=>{

      hits++;

      document.getElementById("g9count").textContent=
        `${hits} / 10`;

      if(hits>=10){

        finishGame(150,25,"Heartbreak defeated! ❤️‍🩹");

      }

    });

}


/* =========================================================
   GAME 10
   BOXING
========================================================= */

function game10(){

  let punches=0;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 10 OF 23</div>
      <h2>🥊 Heart Boxing</h2>
      <p>Punch the target 12 times.</p>

      <div style="font-size:80px;margin:20px">🥊</div>

      <div class="numberBox" id="g10count">
        0 / 12
      </div>

      <button class="mainBtn" id="punchBtn">
        PUNCH! 🥊
      </button>
    </div>
  `;

  document.getElementById("punchBtn")
    .addEventListener("click",()=>{

      punches++;

      document.getElementById("g10count").textContent=
        `${punches} / 12`;

      if(punches>=12){

        finishGame(150,25,"You knocked out the challenge! 🥊");

      }

    });

}


/* =========================================================
   GAME 11
   PERFECT MATCH
========================================================= */

function game11(){

  const answers=[
    ["Liliana's favourite colour?","Baby pink"],
    ["Liliana's favourite number?","3"],
    ["Liliana's star sign?","Leo"],
    ["Liliana's favourite animal?","Dolphins"],
    ["Liliana's favourite food?","Sushi"]
  ];

  let q=0;
  let correct=0;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 11 OF 23</div>
      <h2>💞 Perfect Match</h2>
      <div id="g11area"></div>
    </div>
  `;

  function load(){

    if(q>=answers.length){

      finishGame(
        correct*30,
        correct*4,
        `You matched ${correct}/${answers.length}! 💞`
      );

      return;
    }

    const item=answers[q];

    const options=[
      item[1],
      "Purple",
      "9",
      "Tiger"
    ];

    const unique=[...new Set(options)];

    unique.sort(()=>Math.random()-.5);

    document.getElementById("g11area").innerHTML=`
      <p>Question ${q+1} of ${answers.length}</p>
      <h3>${item[0]}</h3>
      <div class="choiceGrid" id="g11choices"></div>
    `;

    unique.forEach(option=>{

      const btn=document.createElement("button");
      btn.className="choice";
      btn.textContent=option;

      btn.addEventListener("click",()=>{

        if(option===item[1]){
          correct++;
          btn.classList.add("correct");
        }else{
          btn.classList.add("wrong");
        }

        q++;

        setTimeout(load,350);

      });

      document.getElementById("g11choices")
        .appendChild(btn);

    });

  }

  load();

}


/* =========================================================
   GAME 12
   LILiana QUIZ
========================================================= */

const quiz12=[

 ["What is Liliana's favourite number?",["3","8","11","4"],"3"],
 ["What colour does Liliana love?",["Baby pink","Black","Yellow","Orange"],"Baby pink"],
 ["What food does Liliana love?",["Sushi","Fish and chips","Pasta","Burgers"],"Sushi"],
 ["What animal does Liliana love?",["Dolphins","Cats","Horses","Rabbits"],"Dolphins"],
 ["What is Liliana's star sign?",["Leo","Cancer","Virgo","Aries"],"Leo"],
 ["What does Liliana want someday?",["To be a mum","To become a pilot","To live on Mars","To climb Everest"],"To be a mum"],
 ["What subject did Liliana study?",["Psychology","Physics","Law","Engineering"],"Psychology"],
 ["What movie is a favourite?",["Me Before You","Titanic","Frozen","Avatar"],"Me Before You"],
 ["How many siblings does Liliana have?",["5","2","7","3"],"5"],
 ["How many dogs does Liliana have?",["2","1","3","4"],"2"]

];

function game12(){

  let q=0;
  let correct=0;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 12 OF 23</div>
      <h2>💗 How Well Do You Know Lulu?</h2>
      <div id="g12area"></div>
    </div>
  `;

  function load(){

    if(q>=quiz12.length){

      finishGame(
        correct*35,
        correct*5,
        `You scored ${correct}/${quiz12.length}!`
      );

      return;
    }

    const item=quiz12[q];

    document.getElementById("g12area").innerHTML=`
      <div class="questionCount">
        Question ${q+1} of ${quiz12.length}
      </div>

      <h3>${item[0]}</h3>

      <div class="choiceGrid" id="g12choices"></div>

      <div class="message" id="g12msg"></div>
    `;

    const answers=[...item[1]]
      .sort(()=>Math.random()-.5);

    answers.forEach(answer=>{

      const btn=document.createElement("button");
      btn.className="choice";
      btn.textContent=answer;

      btn.addEventListener("click",()=>{

        if(answer===item[2]){

          correct++;
          btn.classList.add("correct");

        }else{

          btn.classList.add("wrong");

        }

        q++;

        setTimeout(load,400);

      });

      document.getElementById("g12choices")
        .appendChild(btn);

    });

  }

  load();

}


/* =========================================================
   GAME 13
   REACTION
========================================================= */

function game13(){

  let rounds=0;
  let target=Math.floor(Math.random()*4);

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 13 OF 23</div>
      <h2>⚡ Quick Choice</h2>
      <p>Tap the pink heart.</p>
      <p id="g13round">Round 1 of 5</p>
      <div class="choiceGrid two" id="g13grid"></div>
      <div class="message" id="g13msg"></div>
    </div>
  `;

  function load(){

    target=Math.floor(Math.random()*4);

    const grid=document.getElementById("g13grid");

    grid.innerHTML="";

    for(let i=0;i<4;i++){

      const btn=document.createElement("button");

      btn.className="choice";

      btn.textContent =
        i===target ? "💗" : "🌸";

      btn.addEventListener("click",()=>{

        if(i===target){

          rounds++;

          if(rounds>=5){

            finishGame(150,25,"Lightning fast! ⚡");

            return;

          }

          document.getElementById("g13round").textContent=
            `Round ${rounds+1} of 5`;

          load();

        }else{

          document.getElementById("g13msg").textContent=
            "Wrong flower! Try again.";

        }

      });

      grid.appendChild(btn);

    }

  }

  load();

}


/* =========================================================
   GAME 14
   HEART HUNT
========================================================= */

function game14(){

  const hearts=new Set();

  while(hearts.size<5){
    hearts.add(Math.floor(Math.random()*12));
  }

  let found=0;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 14 OF 23</div>
      <h2>💗 Heart Hunt</h2>
      <p>Find all 5 hidden hearts.</p>
      <div class="tileGrid" id="g14grid"></div>
      <div class="message" id="g14msg">0 / 5 hearts found</div>
    </div>
  `;

  for(let i=0;i<12;i++){

    const btn=document.createElement("button");

    btn.className="tile";
    btn.textContent="❔";

    btn.addEventListener("click",()=>{

      if(btn.dataset.clicked) return;

      btn.dataset.clicked="yes";

      if(hearts.has(i)){

        btn.textContent="💗";
        btn.classList.add("found");
        found++;

      }else{

        btn.textContent="🌸";

      }

      document.getElementById("g14msg").textContent=
        `${found} / 5 hearts found`;

      if(found===5){

        setTimeout(()=>{
          finishGame(150,25,"You found every heart! 💗");
        },300);

      }

    });

    document.getElementById("g14grid").appendChild(btn);

  }

}


/* =========================================================
   GAME 15
   LOVE LOCK
========================================================= */

function game15(){

  const clues=[

    ["What is Liliana's favourite number?",["3","5","7"],"3"],
    ["How many years have you been best friends?",["4","6","8"],"6"],
    ["What month is Liliana's birthday?",["May","July","September"],"July"]

  ];

  let q=0;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 15 OF 23</div>
      <h2>🔒 Love Lock</h2>

      <div class="lock">🔐</div>

      <div id="g15area"></div>
    </div>
  `;

  function load(){

    if(q>=clues.length){

      finishGame(
        300,
        40,
        "🔓 LOVE LOCK OPENED! The code was 367!"
      );

      return;

    }

    const clue=clues[q];

    document.getElementById("g15area").innerHTML=`
      <p><b>Clue ${q+1} of 3</b></p>
      <h3>${clue[0]}</h3>
      <div class="choiceGrid" id="g15choices"></div>
      <div class="message" id="g15msg"></div>
    `;

    clue[1].forEach(answer=>{

      const btn=document.createElement("button");
      btn.className="choice";
      btn.textContent=answer;

      btn.addEventListener("click",()=>{

        if(answer===clue[2]){

          btn.classList.add("correct");
          q++;

          setTimeout(load,350);

        }else{

          btn.classList.add("wrong");

          document.getElementById("g15msg").textContent=
            "❌ Not quite. Try again.";

        }

      });

      document.getElementById("g15choices")
        .appendChild(btn);

    });

  }

  load();

}


/* =========================================================
   GAME 16
   CUPID
========================================================= */

function game16(){

  let hits=0;

  const targetIndices=[];

  while(targetIndices.length<6){

    const x=Math.floor(Math.random()*9);

    if(!targetIndices.includes(x)){
      targetIndices.push(x);
    }

  }

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 16 OF 23</div>
      <h2>🏹 Cupid Shootout</h2>
      <p>Hit all 6 hearts.</p>
      <div class="tileGrid" id="g16grid"></div>
      <div class="message" id="g16msg">0 / 6</div>
    </div>
  `;

  for(let i=0;i<9;i++){

    const btn=document.createElement("button");

    btn.className="tile";
    btn.textContent="🎯";

    btn.addEventListener("click",()=>{

      if(btn.dataset.clicked) return;

      btn.dataset.clicked="yes";

      if(targetIndices.includes(i)){

        btn.textContent="💗";
        btn.classList.add("found");
        hits++;

      }else{

        btn.textContent="❌";

      }

      document.getElementById("g16msg").textContent=
        `${hits} / 6`;

      if(hits===6){

        setTimeout(()=>{
          finishGame(150,25,"Cupid approves! 🏹💗");
        },300);

      }

    });

    document.getElementById("g16grid").appendChild(btn);

  }

}


/* =========================================================
   GAME 17
   COUNTDOWN
========================================================= */

function game17(){

  let number=3;
  let stopped=false;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 17 OF 23</div>
      <h2>⏳ Stop at 1</h2>
      <p>Press STOP when the number reaches 1.</p>

      <div class="numberBox" id="g17number">
        3
      </div>

      <button class="mainBtn" id="g17stop">
        STOP!
      </button>

      <div class="message" id="g17msg"></div>
    </div>
  `;

  const timer=setInterval(()=>{

    if(stopped) return;

    number--;

    if(number<1){
      number=3;
    }

    document.getElementById("g17number").textContent=number;

  },800);

  document.getElementById("g17stop")
    .addEventListener("click",()=>{

      stopped=true;
      clearInterval(timer);

      if(number===1){

        finishGame(150,25,"Perfect timing! ⏳");

      }else{

        document.getElementById("g17msg").textContent=
          "Missed it! Press again to restart.";

        setTimeout(()=>{

          number=3;
          stopped=false;

        },700);

      }

    });

}


/* =========================================================
   GAME 18
   ULTIMATE GAMBLE
========================================================= */

function game18(){

  const winner=Math.floor(Math.random()*3);

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 18 OF 23</div>
      <h2>🎰 Ultimate Gamble</h2>
      <p>One of these gives you the jackpot.</p>

      <div class="choiceGrid">
        <button class="choice" data-slot="0">🎰 SLOT 1</button>
        <button class="choice" data-slot="1">🎰 SLOT 2</button>
        <button class="choice" data-slot="2">🎰 SLOT 3</button>
      </div>

      <div class="message" id="g18msg"></div>
    </div>
  `;

  document.querySelectorAll("[data-slot]")
    .forEach(btn=>{

      btn.addEventListener("click",()=>{

        const chosen=Number(btn.dataset.slot);

        if(chosen===winner){

          btn.classList.add("correct");

          setTimeout(()=>{
            finishGame(
              300,
              100,
              "🎰 JACKPOT! You won!"
            );
          },400);

        }else{

          btn.classList.add("wrong");

          document.getElementById("g18msg").textContent=
            "No jackpot there. Try another.";

        }

      });

    });

}


/* =========================================================
   GAME 19
   LAST STAND
========================================================= */

function game19(){

  const rounds=[
    "A storm is coming. What do you choose?",
    "A challenge appears. What protects you?",
    "One final attack. What do you use?"
  ];

  const correct=[
    "Shield",
    "Shield",
    "Shield"
  ];

  let q=0;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 19 OF 23</div>
      <h2>🛡️ Last Stand</h2>
      <div id="g19area"></div>
    </div>
  `;

  function load(){

    if(q>=rounds.length){

      finishGame(150,25,"You survived the Last Stand! 🛡️");

      return;

    }

    document.getElementById("g19area").innerHTML=`
      <p>Round ${q+1} of 3</p>
      <h3>${rounds[q]}</h3>

      <div class="choiceGrid">
        <button class="choice" data-answer="Shield">🛡️ Shield</button>
        <button class="choice" data-answer="Sword">⚔️ Sword</button>
        <button class="choice" data-answer="Flower">🌸 Flower</button>
      </div>

      <div class="message" id="g19msg"></div>
    `;

    document.querySelectorAll("[data-answer]")
      .forEach(btn=>{

        btn.addEventListener("click",()=>{

          if(btn.dataset.answer===correct[q]){

            q++;
            load();

          }else{

            document.getElementById("g19msg").textContent=
              "The shield was the safe choice! 🛡️";

          }

        });

      });

  }

  load();

}


/* =========================================================
   GAME 20
   WORD FIND
========================================================= */

function game20(){

  const words=[
    "LULU",
    "ROSE",
    "DOLPHIN",
    "SUNFLOWER",
    "SUSHI"
  ];

  let found=0;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 20 OF 23</div>
      <h2>🔤 Lulu Word Find</h2>

      <p>Tap each Lulu-related word.</p>

      <div class="wordList" id="g20words"></div>

      <div class="message" id="g20msg">
        Found 0 / 5
      </div>
    </div>
  `;

  const distractors=[
    "CHAIR",
    "MOON",
    "TRAIN",
    "BOOK",
    "CLOUD",
    "PHONE"
  ];

  const all=[...words,...distractors]
    .sort(()=>Math.random()-.5);

  all.forEach(word=>{

    const btn=document.createElement("button");

    btn.className="word";
    btn.textContent=word;

    btn.addEventListener("click",()=>{

      if(btn.dataset.found) return;

      if(words.includes(word)){

        btn.dataset.found="yes";
        btn.style.background="#b8e7c4";

        found++;

        document.getElementById("g20msg").textContent=
          `Found ${found} / 5`;

        if(found===5){

          setTimeout(()=>{
            finishGame(150,25,"You found all Lulu words! 🔤💗");
          },300);

        }

      }

    });

    document.getElementById("g20words")
      .appendChild(btn);

  });

}


/* =========================================================
   GAME 21
   SUNFLOWER BUILDER
========================================================= */

function game21(){

  let petals=0;
  let centre=false;
  let stem=false;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 21 OF 23</div>
      <h2>🌻 Build a Sunflower</h2>

      <p>Build your sunflower.</p>

      <div style="font-size:80px" id="flowerDisplay">
        🌱
      </div>

      <button class="mainBtn" id="petalBtn">
        Add Petal 🌼
      </button>

      <button class="mainBtn secondary" id="centreBtn">
        Add Centre 🟤
      </button>

      <button class="mainBtn secondary" id="stemBtn">
        Add Stem 🌿
      </button>

      <div class="message" id="g21msg">
        Petals: 0 / 5
      </div>
    </div>
  `;

  document.getElementById("petalBtn")
    .addEventListener("click",()=>{

      if(petals<5){
        petals++;
      }

      updateFlower();

    });

  document.getElementById("centreBtn")
    .addEventListener("click",()=>{

      centre=true;
      updateFlower();

    });

  document.getElementById("stemBtn")
    .addEventListener("click",()=>{

      stem=true;
      updateFlower();

    });


  function updateFlower(){

    document.getElementById("g21msg").textContent=
      `Petals: ${petals}/5 · Centre: ${centre?"✓":"✗"} · Stem: ${stem?"✓":"✗"}`;

    if(petals>=5 && centre && stem){

      document.getElementById("flowerDisplay").textContent="🌻";

      setTimeout(()=>{
        finishGame(
          150,
          25,
          "Your sunflower is complete! 🌻"
        );
      },400);

    }else{

      document.getElementById("flowerDisplay").textContent=
        petals>=5 ? "🌼" : "🌱";

    }

  }

}


/* =========================================================
   GAME 22
   LULU DERBY
   100 QUESTIONS
========================================================= */

const derbyQuestions=[

["What is the capital of New Zealand?","Wellington"],
["What is the capital of Australia?","Canberra"],
["How many days are in a week?","7"],
["How many months are in a year?","12"],
["What planet do we live on?","Earth"],
["How many sides does a triangle have?","3"],
["How many sides does a square have?","4"],
["What is the largest ocean?","Pacific Ocean"],
["What is the fastest land animal?","Cheetah"],
["What is the largest mammal?","Blue whale"],
["What colour is a ripe banana?","Yellow"],
["How many legs does a spider have?","8"],
["What do bees make?","Honey"],
["What is frozen water called?","Ice"],
["How many hours are in a day?","24"],
["How many minutes are in an hour?","60"],
["What is H2O commonly called?","Water"],
["Which animal says moo?","Cow"],
["Which animal is known as man's best friend?","Dog"],
["What is the opposite of hot?","Cold"],
["What colour do you get by mixing red and white?","Pink"],
["What is 5 + 5?","10"],
["What is 10 - 4?","6"],
["What is 3 x 3?","9"],
["What is 20 divided by 4?","5"],
["Which season comes after winter?","Spring"],
["Which season comes after summer?","Autumn"],
["What star is at the centre of our solar system?","The Sun"],
["What is Earth's natural satellite?","The Moon"],
["How many planets are in our solar system?","8"],
["What is the smallest prime number?","2"],
["What is the first letter of the alphabet?","A"],
["What is the last letter of the alphabet?","Z"],
["Which ocean is between Africa and Australia?","Indian Ocean"],
["What is the largest continent?","Asia"],
["What is the smallest continent?","Australia"],
["What language is mainly spoken in Brazil?","Portuguese"],
["What language is mainly spoken in Mexico?","Spanish"],
["What is the capital of France?","Paris"],
["What is the capital of Japan?","Tokyo"],
["What is the capital of Italy?","Rome"],
["What is the capital of Canada?","Ottawa"],
["What is the capital of the United States?","Washington, D.C."],
["How many colours are traditionally in a rainbow?","7"],
["What colour is grass usually?","Green"],
["What animal has a long trunk?","Elephant"],
["What animal has black and white stripes?","Zebra"],
["What animal is famous for its pouch?","Kangaroo"],
["What bird cannot fly and lives in Antarctica?","Penguin"],
["What is a baby cat called?","Kitten"],
["What is a baby dog called?","Puppy"],
["What is a baby horse called?","Foal"],
["What is a baby sheep called?","Lamb"],
["How many fingers are on one hand?","5"],
["How many toes are on two feet?","10"],
["How many wheels does a bicycle have?","2"],
["How many wheels does a tricycle have?","3"],
["What vehicle travels on rails?","Train"],
["What vehicle flies in the sky?","Aeroplane"],
["What vehicle travels on water?","Boat"],
["What do you use to tell time?","Clock"],
["What do you use to cut paper?","Scissors"],
["What do you use to write on paper?","Pen"],
["What do you use to erase pencil marks?","Eraser"],
["What is the opposite of up?","Down"],
["What is the opposite of left?","Right"],
["What is the opposite of day?","Night"],
["What is the opposite of inside?","Outside"],
["What shape is a football usually?","Oval"],
["What shape has no corners?","Circle"],
["What shape has three sides?","Triangle"],
["What shape has four equal sides?","Square"],
["How many letters are in the English alphabet?","26"],
["What comes after Tuesday?","Wednesday"],
["What comes before Friday?","Thursday"],
["What day comes after Saturday?","Sunday"],
["What month comes after January?","February"],
["What month comes before December?","November"],
["What is the first month of the year?","January"],
["What is the last month of the year?","December"],
["What is the colour of a typical emerald?","Green"],
["What is the colour of a typical ruby?","Red"],
["What precious stone is often blue?","Sapphire"],
["What gas do humans breathe in to survive?","Oxygen"],
["What organ pumps blood around the body?","Heart"],
["What organ helps us think?","Brain"],
["What do plants need from the Sun?","Light"],
["What process do plants use to make food?","Photosynthesis"],
["What is the hardest natural substance?","Diamond"],
["What metal is represented by Au?","Gold"],
["What metal is represented by Ag?","Silver"],
["What is the tallest animal?","Giraffe"],
["What is the largest land animal?","Elephant"],
["What is the fastest bird?","Peregrine falcon"],
["What animal is known for changing colour?","Chameleon"],
["What animal carries its home on its back?","Turtle"],
["What animal has eight arms?","Octopus"],
["What animal is famous for its black-and-white fur and bamboo diet?","Panda"],
["What is the main ingredient in bread?","Flour"],
["What fruit is famous for having seeds on its outside?","Strawberry"],
["What fruit is usually yellow and curved?","Banana"],
["What vegetable is orange and associated with rabbits?","Carrot"],
["What is the traditional sport involving a bat and ball called?","Cricket"],
["How many players are on a football team on the field?","11"]

];


/* Make sure exactly 100 are used */
const derbyBank=derbyQuestions.slice(0,100);


function game22(){

  let questions=[...derbyBank]
    .sort(()=>Math.random()-.5);

  let q=0;
  let correct=0;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 22 OF 23</div>
      <h2>🏇 Lulu Derby</h2>

      <p>
        100 random trivia questions.
        Answer them one at a time.
      </p>

      <div id="g22area"></div>
    </div>
  `;

  function makeOptions(correctAnswer){

    const pool=[
      "London",
      "Blue",
      "12",
      "8",
      "Mars",
      "5",
      "Pacific Ocean",
      "Elephant",
      "60",
      "7"
    ];

    let options=[correctAnswer];

    while(options.length<4){

      const x=
        pool[Math.floor(Math.random()*pool.length)];

      if(!options.includes(x)){
        options.push(x);
      }

    }

    return options.sort(()=>Math.random()-.5);

  }


  function load(){

    if(q>=100){

      finishGame(
        correct*25,
        correct*2,
        `Derby complete! You got ${correct}/100 correct! 🏇`
      );

      return;
    }

    const item=questions[q];

    const options=makeOptions(item[1]);

    document.getElementById("g22area").innerHTML=`

      <div class="questionCount">
        Question ${q+1} of 100
      </div>

      <div class="progress">
        <div class="progressBar"
          style="width:${q}%">
        </div>
      </div>

      <h3>${item[0]}</h3>

      <div class="choiceGrid" id="g22choices"></div>

      <div class="message" id="g22msg"></div>

    `;

    options.forEach(answer=>{

      const btn=document.createElement("button");

      btn.className="choice";
      btn.textContent=answer;

      btn.addEventListener("click",()=>{

        if(answer===item[1]){

          correct++;
          btn.classList.add("correct");

        }else{

          btn.classList.add("wrong");

        }

        q++;

        setTimeout(load,120);

      });

      document.getElementById("g22choices")
        .appendChild(btn);

    });

  }

  load();

}


/* =========================================================
   GAME 23
   FINAL CHALLENGE
   EXACTLY 50 QUESTIONS
========================================================= */

const finalQuestions=[

["What is Liliana's favourite colour?","Baby pink"],
["What is Liliana's favourite number?","3"],
["What food does Liliana love?","Sushi"],
["What animal does Liliana love?","Dolphins"],
["What is Liliana's birthday month?","July"],
["What is Liliana's star sign?","Leo"],
["How many years have you been best friends?","6"],
["What university subject did Liliana study?","Psychology"],
["What movie is one of Liliana's favourites?","Me Before You"],
["How many siblings does Liliana have?","5"],
["How many dogs does Liliana have?","2"],
["What are Liliana's dogs called?","Aayla and Arlo"],
["What colour are Liliana's eyes?","Green"],
["How many nephews does Liliana have?","4"],
["How many nieces does Liliana have?","1"],
["What does Liliana want to be someday?","A mum"],
["What gender would Liliana love to have for her future baby?","A girl"],
["What type of songs does Liliana like?","Sad songs"],
["What kind of writing does Liliana enjoy?","Poetry"],
["What flowers does Liliana like?","Sunflowers and roses"],
["What type of game does Liliana enjoy?","Poker"],
["What other type of gambling does Liliana enjoy?","Casino games"],
["What personality trait describes Liliana?","Caring"],
["What other personality trait describes Liliana?","Sweet"],
["What other personality trait describes Liliana?","Charismatic"],
["What is Liliana's birthday date?","July 22"],
["What is Liliana's zodiac sign?","Leo"],
["What colour is associated with Lulu's favourite aesthetic?","Baby pink"],
["What sea animal is connected with Liliana?","Dolphin"],
["What food would Liliana choose over sushi?","This question has no correct answer"],
["How many piercings does Liliana have?","4"],
["What is Liliana's tattoo symbol?","Semicolon"],
["What subject did Liliana study at university?","Psychology"],
["What does Liliana love about poetry?","Its emotion"],
["What kind of music can Liliana enjoy?","Sad music"],
["What does Liliana hope to become?","A mother"],
["How many children does Liliana currently have?","0"],
["What is one thing Liliana likes to gamble on?","Poker"],
["What animal is one of Liliana's favourite animals?","Dolphins"],
["What is one flower Liliana likes?","Rose"],
["What is another flower Liliana likes?","Sunflower"],
["What is one of Liliana's favourite foods?","Sushi"],
["What is Liliana's favourite number written as a word?","Three"],
["What colour would fit Liliana's favourite aesthetic?","Baby pink"],
["What is the name of one of Liliana's dogs?","Aayla"],
["What is the name of Liliana's other dog?","Arlo"],
["What kind of person is Liliana to her friends?","Caring"],
["How long have Bree and Liliana been best friends?","6 years"],
["What is this entire final challenge about?","Liliana"],
["Who is Lulu?","Liliana"]

];


/* EXACTLY 50 */
const finalBank=finalQuestions.slice(0,50);


function game23(){

  let questions=[...finalBank]
    .sort(()=>Math.random()-.5);

  let q=0;
  let correct=0;

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div class="gameNumber">LEVEL 23 OF 23</div>

      <h2>👑 FINAL CHALLENGE</h2>

      <p>
        50 questions about Liliana.
        This is the final test.
      </p>

      <div id="g23area"></div>
    </div>
  `;


  function makeOptions(correctAnswer){

    const possible=[

      "Baby pink",
      "3",
      "Sushi",
      "Dolphins",
      "July",
      "Leo",
      "6 years",
      "Psychology",
      "Me Before You",
      "5",
      "2",
      "Green",
      "4",
      "1",
      "A mum",
      "A girl",
      "Sad songs",
      "Poetry",
      "Sunflowers and roses",
      "Poker",
      "Charismatic",
      "July 22",
      "Aayla",
      "Arlo",
      "Caring",
      "Liliana"

    ];

    let options=[correctAnswer];

    while(options.length<4){

      const answer=
        possible[Math.floor(Math.random()*possible.length)];

      if(!options.includes(answer)){
        options.push(answer);
      }

    }

    return options.sort(()=>Math.random()-.5);

  }


  function load(){

    if(q>=50){

      const bonus = state.score > 3000;

      document.getElementById("gameArea").innerHTML=`

        <div class="card">

          <div style="font-size:80px">👑💗</div>

          <h1>FINAL CHALLENGE COMPLETE!</h1>

          <p>
            Amazing, ${state.name}!
          </p>

          <p>
            You got <b>${correct}/50</b> questions correct.
          </p>

          <p>
            Final score:
            <b>${state.score}</b>
          </p>

          <p>
            Tokens:
            <b>${state.tokens}</b>
          </p>

          ${
            bonus
            ?
            `
            <div class="reward">
              <h2>📞 PRIVATE CALL UNLOCKED!</h2>
              <p>
                You scored more than 3000 points!
              </p>
              <p>
                Your final score is
                <b>${state.score}</b>.
              </p>
            </div>
            `
            :
            `
            <div class="reward">
              <h2>💗 Journey Complete!</h2>
              <p>
                You finished Lulu Express!
              </p>
              <p>
                You needed <b>3001+</b> points
                for the private call reward.
              </p>
            </div>
            `
          }

          <button class="mainBtn" id="restartFinal">
            🔄 Play Again
          </button>

        </div>

      `;

      document.getElementById("restartFinal")
        .addEventListener("click",()=>{
          location.reload();
        });

      return;

    }


    const item=questions[q];

    const options=makeOptions(item[1]);

    document.getElementById("g23area").innerHTML=`

      <div class="questionCount">
        Question ${q+1} of 50
      </div>

      <div class="progress">
        <div class="progressBar"
          style="width:${(q/50)*100}%">
        </div>
      </div>

      <h3>${item[0]}</h3>

      <div class="choiceGrid" id="g23choices"></div>

      <div class="message" id="g23msg"></div>

    `;

    options.forEach(answer=>{

      const btn=document.createElement("button");

      btn.className="choice";
      btn.textContent=answer;

      btn.addEventListener("click",()=>{

        if(answer===item[1]){

          correct++;

          reward(25,3);

          btn.classList.add("correct");

        }else{

          btn.classList.add("wrong");

        }

        q++;

        setTimeout(load,150);

      });

      document.getElementById("g23choices")
        .appendChild(btn);

    });

  }

  load();

}


/* =========================================================
   FINAL RESULT FALLBACK
========================================================= */

function showFinalResult(){

  document.getElementById("gameArea").innerHTML=`
    <div class="card">
      <div style="font-size:80px">💗</div>
      <h1>Congratulations!</h1>
      <p>You completed Lulu Express.</p>
      <p>Final score: <b>${state.score}</b></p>
      <p>Tokens: <b>${state.tokens}</b></p>

      <button class="mainBtn"
        onclick="location.reload()">
        Play Again
      </button>
    </div>
  `;

}

</script>

</body>
</html>

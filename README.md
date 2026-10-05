<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport"
      content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no, viewport-fit=cover">

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
  background:#160912;
  color:#fff;
  overflow-x:hidden;
}

body{
  touch-action:manipulation;
}

button{
  font-family:inherit;
  cursor:pointer;
  touch-action:manipulation;
}

.hidden{
  display:none!important;
}

#app{
  min-height:100vh;
  width:100%;
}

.screen{
  min-height:100vh;
  width:100%;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  padding:20px;
}

.startScreen{
  background:
    radial-gradient(circle at 20% 20%,#8d315f 0,#42162f 25%,transparent 45%),
    radial-gradient(circle at 80% 70%,#70234b 0,#260e1c 35%,transparent 60%),
    #160912;
}

.logo{
  font-size:clamp(42px,12vw,80px);
  margin:0;
  text-align:center;
}

.subtitle{
  color:#ffd6e8;
  font-size:18px;
  text-align:center;
  max-width:600px;
  line-height:1.5;
}

.startCard{
  width:min(94%,560px);
  background:rgba(255,255,255,.09);
  border:1px solid rgba(255,255,255,.18);
  border-radius:28px;
  padding:30px 22px;
  text-align:center;
  box-shadow:0 20px 70px rgba(0,0,0,.35);
  backdrop-filter:blur(10px);
}

input{
  width:100%;
  max-width:420px;
  padding:17px;
  border-radius:15px;
  border:2px solid #f6a7c9;
  background:#fff;
  color:#32101f;
  font-size:18px;
  text-align:center;
  outline:none;
}

.primary{
  border:0;
  border-radius:16px;
  padding:16px 25px;
  background:#f18ab6;
  color:#3b0d22;
  font-weight:bold;
  font-size:18px;
  margin-top:15px;
  min-height:54px;
  box-shadow:0 7px 0 #a94776;
}

.primary:active{
  transform:translateY(4px);
  box-shadow:0 3px 0 #a94776;
}

.secondary{
  border:1px solid #f5a7c7;
  border-radius:14px;
  padding:12px 18px;
  background:#371322;
  color:#fff;
  font-weight:bold;
  min-height:48px;
}

#gameScreen{
  display:none;
  min-height:100vh;
  background:
    radial-gradient(circle at top,#64203f 0,#24101b 38%,#12070c 100%);
  padding:0;
}

.topbar{
  width:100%;
  min-height:72px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:8px;
  padding:10px 14px;
  background:rgba(0,0,0,.35);
  border-bottom:1px solid rgba(255,255,255,.1);
  position:relative;
  z-index:20;
}

.topInfo{
  font-size:14px;
  line-height:1.3;
}

.topButtons{
  display:flex;
  gap:7px;
}

.smallBtn{
  border:1px solid #e98ab1;
  background:#32111f;
  color:#fff;
  border-radius:11px;
  padding:9px 10px;
  font-weight:bold;
  font-size:12px;
}

#gameArea{
  width:100%;
  min-height:calc(100vh - 72px);
  display:flex;
  align-items:center;
  justify-content:center;
  padding:15px;
}

.card{
  width:min(100%,650px);
  background:rgba(255,255,255,.075);
  border:1px solid rgba(255,255,255,.14);
  border-radius:25px;
  padding:22px;
  text-align:center;
  box-shadow:0 15px 50px rgba(0,0,0,.3);
}

.card h2{
  margin-top:0;
  font-size:clamp(27px,7vw,40px);
}

.gameDescription{
  color:#ffd9e9;
  line-height:1.5;
}

.gameButton{
  width:100%;
  max-width:430px;
  min-height:58px;
  margin:7px auto;
  display:block;
  border:2px solid #e993b8;
  background:#45152b;
  color:white;
  border-radius:15px;
  font-size:17px;
  font-weight:bold;
  padding:13px;
}

.gameButton:active{
  transform:scale(.98);
}

.grid{
  display:grid;
  gap:10px;
  width:100%;
}

.grid2{
  grid-template-columns:repeat(2,1fr);
}

.grid3{
  grid-template-columns:repeat(3,1fr);
}

.bigNumber{
  font-size:48px;
  font-weight:bold;
  margin:15px;
  color:#ffd0e4;
}

.status{
  min-height:28px;
  margin:12px 0;
  font-weight:bold;
}

.progress{
  height:12px;
  background:#3a1626;
  border-radius:20px;
  overflow:hidden;
  margin:15px 0;
}

.progressFill{
  height:100%;
  width:0;
  background:#f394bd;
  transition:width .2s;
}

/* Hearts */

.heartArena{
  position:relative;
  width:100%;
  max-width:600px;
  height:55vh;
  min-height:360px;
  max-height:600px;
  background:
    radial-gradient(circle at 50% 20%,rgba(255,180,210,.16),transparent 35%),
    #180914;
  border:2px solid #79334f;
  border-radius:22px;
  overflow:hidden;
  touch-action:none;
}

.heart{
  position:absolute;
  font-size:35px;
  user-select:none;
  pointer-events:none;
}

.basket{
  position:absolute;
  bottom:10px;
  width:90px;
  height:48px;
  border-radius:15px 15px 25px 25px;
  background:#f0a0c3;
  color:#4a1029;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:28px;
  font-weight:bold;
}

/* Memory */

.memoryGrid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:9px;
  max-width:500px;
  margin:auto;
}

.memoryCard{
  aspect-ratio:1;
  border-radius:13px;
  border:2px solid #e997bb;
  background:#3a1225;
  color:transparent;
  font-size:28px;
}

.memoryCard.flipped,
.memoryCard.matched{
  background:#f5bfd7;
  color:#4a122d;
}

/* Timer */

.timer{
  font-size:44px;
  font-weight:bold;
  color:#ffd2e5;
}

/* Race */

.raceTrack{
  position:relative;
  height:220px;
  border:2px solid #71304c;
  background:#180a12;
  border-radius:18px;
  overflow:hidden;
  margin:15px 0;
}

.racer{
  position:absolute;
  left:0;
  font-size:38px;
  transition:left .15s linear;
}

.finish{
  position:absolute;
  right:5px;
  top:0;
  height:100%;
  border-left:4px dashed white;
}

/* Wheel */

.wheel{
  width:min(75vw,280px);
  aspect-ratio:1;
  border-radius:50%;
  margin:20px auto;
  border:8px solid #f2a0c2;
  background:
    conic-gradient(
      #f6a5c5 0deg 45deg,
      #682342 45deg 90deg,
      #f6a5c5 90deg 135deg,
      #682342 135deg 180deg,
      #f6a5c5 180deg 225deg,
      #682342 225deg 270deg,
      #f6a5c5 270deg 315deg,
      #682342 315deg 360deg
    );
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:25px;
  font-weight:bold;
  transition:transform 2s cubic-bezier(.15,.8,.25,1);
}

/* Word Find */

.wordGrid{
  display:grid;
  grid-template-columns:repeat(6,1fr);
  gap:4px;
  max-width:500px;
  margin:15px auto;
}

.letter{
  aspect-ratio:1;
  border:1px solid #b85d86;
  background:#311121;
  color:#fff;
  border-radius:7px;
  font-weight:bold;
  font-size:17px;
  padding:0;
}

.letter.selected{
  background:#f29bc0;
  color:#3b1023;
}

/* Flower */

.flowerCanvas{
  width:100%;
  max-width:550px;
  height:360px;
  background:#fff4f8;
  border-radius:20px;
  touch-action:none;
  display:block;
}

/* Derby */

.derby{
  position:relative;
  width:100%;
  height:270px;
  border-radius:20px;
  overflow:hidden;
  background:
    repeating-linear-gradient(
      0deg,
      #402217 0 40px,
      #4e2b1d 40px 80px
    );
  border:3px solid #a9673d;
}

.horse{
  position:absolute;
  left:5px;
  font-size:38px;
  transition:left .2s;
}

.derbyFinish{
  position:absolute;
  right:8px;
  top:0;
  height:100%;
  border-left:5px dashed #fff;
}

/* Results */

.resultBox{
  margin-top:18px;
  padding:18px;
  border-radius:18px;
  background:rgba(255,255,255,.08);
}

.success{
  color:#a9ffd3;
}

.fail{
  color:#ff9ab9;
}

.stars{
  font-size:25px;
  letter-spacing:5px;
}

/* Mobile */

@media(max-width:600px){
  .screen{
    padding:14px;
  }

  .card{
    padding:17px 13px;
    border-radius:20px;
  }

  .topbar{
    min-height:68px;
  }

  #gameArea{
    min-height:calc(100vh - 68px);
    padding:9px;
  }

  .memoryGrid{
    gap:6px;
  }

  .memoryCard{
    font-size:21px;
  }

  .gameButton{
    min-height:56px;
  }

  .wordGrid{
    gap:3px;
  }

  .letter{
    font-size:14px;
  }
}
</style>
</head>

<body>

<div id="app">

<!-- START -->
<section id="startScreen" class="screen startScreen">

  <div class="startCard">

    <div class="logo">💗</div>

    <h1>LULU EXPRESS</h1>

    <p class="subtitle">
      A 23-level adventure made especially for Liliana.
      Six years of friendship. One very big journey.
    </p>

    <p>
      Enter your name to begin.
    </p>

    <input
      id="playerName"
      type="text"
      maxlength="25"
      placeholder="Your name..."
      autocomplete="off"
    >

    <br>

    <button class="primary" onclick="startGame()">
      🚂 START THE JOURNEY
    </button>

    <p style="font-size:13px;color:#eab4ca;margin-top:20px;">
      Every level must be completed to continue.
    </p>

  </div>
</section>


<!-- GAME -->
<section id="gameScreen">

  <div class="topbar">

    <div class="topInfo">
      <b id="levelText">Level 1 / 23</b><br>
      <span id="playerDisplay"></span>
    </div>

    <div class="topInfo">
      💗 <span id="scoreText">0</span><br>
      🪙 <span id="tokenText">0</span>
    </div>

    <div class="topButtons">
      <button class="smallBtn" onclick="toggleMusic()">🎵</button>
      <button class="smallBtn" onclick="resetGame()">↻</button>
    </div>

  </div>

  <div id="gameArea"></div>

</section>

</div>


<script>
/* =========================================================
   LULU EXPRESS
   COMPLETE 23 LEVEL GAME
========================================================= */

let playerName = "";
let level = 1;
let score = 0;
let tokens = 0;
let musicOn = false;

let gameTimer = null;
let gameInterval = null;
let audioContext = null;


/* =========================================================
   LILiana DATA
========================================================= */

const facts = [
  {
    q:"What is Liliana's favourite number?",
    options:["3","7","9","12"],
    answer:"3"
  },
  {
    q:"What colour does Liliana love?",
    options:["Baby pink","Black","Green","Orange"],
    answer:"Baby pink"
  },
  {
    q:"What animal does Liliana love?",
    options:["Dolphins","Tigers","Penguins","Foxes"],
    answer:"Dolphins"
  },
  {
    q:"What flower does Liliana like?",
    options:["Sunflowers","Tulips","Lilies","Orchids"],
    answer:"Sunflowers"
  },
  {
    q:"What other flower does Liliana like?",
    options:["Roses","Daisies","Lavender","Carnations"],
    answer:"Roses"
  },
  {
    q:"What food does Liliana love?",
    options:["Sushi","Pizza","Tacos","Pasta"],
    answer:"Sushi"
  },
  {
    q:"What is Liliana's star sign?",
    options:["Leo","Gemini","Scorpio","Pisces"],
    answer:"Leo"
  },
  {
    q:"What colour are Liliana's eyes?",
    options:["Green","Blue","Brown","Hazel"],
    answer:"Green"
  },
  {
    q:"How many siblings does Liliana have?",
    options:["5","2","4","7"],
    answer:"5"
  },
  {
    q:"How many nephews does Liliana have?",
    options:["4","1","2","6"],
    answer:"4"
  },
  {
    q:"How many nieces does Liliana have?",
    options:["1","3","5","2"],
    answer:"1"
  },
  {
    q:"What does Liliana want to be someday?",
    options:[
      "A mum",
      "A pilot",
      "A singer",
      "A professional athlete"
    ],
    answer:"A mum"
  },
  {
    q:"What would Liliana especially love to have?",
    options:[
      "A baby girl",
      "A pet snake",
      "A boat",
      "A motorbike"
    ],
    answer:"A baby girl"
  },
  {
    q:"What did Liliana study at university?",
    options:[
      "Psychology",
      "Law",
      "Engineering",
      "Medicine"
    ],
    answer:"Psychology"
  },
  {
    q:"What is Liliana's favourite movie?",
    options:[
      "Me Before You",
      "Titanic",
      "Frozen",
      "The Notebook"
    ],
    answer:"Me Before You"
  },
  {
    q:"Which activity does Liliana enjoy?",
    options:[
      "Poker",
      "Surfing",
      "Mountain climbing",
      "Fishing"
    ],
    answer:"Poker"
  },
  {
    q:"What kind of music does Liliana enjoy?",
    options:[
      "Sad songs",
      "Only classical music",
      "Only heavy metal",
      "Only country music"
    ],
    answer:"Sad songs"
  },
  {
    q:"What does Liliana enjoy reading or creating?",
    options:[
      "Poetry",
      "Cookbooks",
      "Textbooks only",
      "Travel guides"
    ],
    answer:"Poetry"
  },
  {
    q:"What is one thing Liliana is afraid of?",
    options:[
      "Drowning",
      "Dogs",
      "Butterflies",
      "Heights"
    ],
    answer:"Drowning"
  },
  {
    q:"How many years have Bree and Liliana been best friends?",
    options:["6","2","4","10"],
    answer:"6"
  }
];


/* 50 FINAL QUESTIONS
   No tattoo question included.
========================================================= */

const finalQuestions = [
 ...facts,

 {
  q:"What is Liliana's birthday?",
  options:["July 22","June 12","August 7","May 22"],
  answer:"July 22"
 },
 {
  q:"What nationality/cultural background is associated with Liliana?",
  options:["Mexican American","Australian","Canadian","Brazilian"],
  answer:"Mexican American"
 },
 {
  q:"How many piercings does Liliana have?",
  options:["4","2","6","8"],
  answer:"4"
 },
 {
  q:"What are Liliana's dogs called?",
  options:[
   "Aayla & Arlo",
   "Bella & Luna",
   "Milo & Max",
   "Coco & Daisy"
  ],
  answer:"Aayla & Arlo"
 },
 {
  q:"Which number has special meaning to Liliana?",
  options:["3","11","8","13"],
  answer:"3"
 },
 {
  q:"Which colour is associated with Liliana?",
  options:["Baby pink","Purple","Navy","Yellow"],
  answer:"Baby pink"
 },
 {
  q:"Which animal appears in the Lulu Express theme?",
  options:["Dolphin","Lion","Bear","Wolf"],
  answer:"Dolphin"
 },
 {
  q:"Which of these is one of Liliana's favourite flowers?",
  options:["Sunflower","Cactus","Fern","Bamboo"],
  answer:"Sunflower"
 },
 {
  q:"Which of these is another flower Liliana likes?",
  options:["Rose","Pine tree","Moss","Ivy"],
  answer:"Rose"
 },
 {
  q:"What food would Liliana be more likely to choose?",
  options:["Sushi","Plain toast","Cereal","Soup"],
  answer:"Sushi"
 },
 {
  q:"Which subject did Liliana study?",
  options:["Psychology","Physics","Accounting","Architecture"],
  answer:"Psychology"
 },
 {
  q:"Which film is a favourite?",
  options:["Me Before You","Shrek","Cars","Matilda"],
  answer:"Me Before You"
 },
 {
  q:"What kind of songs does Liliana like?",
  options:["Sad songs","Only nursery songs","Only opera","Only instrumental music"],
  answer:"Sad songs"
 },
 {
  q:"What does Liliana like to write or enjoy?",
  options:["Poetry","Recipes only","News articles","Manuals"],
  answer:"Poetry"
 },
 {
  q:"Which casino-style game does Liliana like?",
  options:["Poker","Chess","Sudoku","Monopoly"],
  answer:"Poker"
 },
 {
  q:"How many nieces does Liliana have?",
  options:["1","2","3","4"],
  answer:"1"
 },
 {
  q:"How many nephews does Liliana have?",
  options:["4","2","5","7"],
  answer:"4"
 },
 {
  q:"How many siblings does Liliana have?",
  options:["5","3","6","8"],
  answer:"5"
 },
 {
  q:"What is Liliana's star sign?",
  options:["Leo","Virgo","Aries","Libra"],
  answer:"Leo"
 },
 {
  q:"What colour are Liliana's eyes?",
  options:["Green","Brown","Blue","Grey"],
  answer:"Green"
 },
 {
  q:"How many piercings does Liliana have?",
  options:["4","1","3","7"],
  answer:"4"
 },
 {
  q:"What are Liliana's dogs called?",
  options:["Aayla & Arlo","Ruby & Rose","Loki & Luna","Max & Milo"],
  answer:"Aayla & Arlo"
 },
 {
  q:"What does Liliana want in her future?",
  options:["To be a mum","To become a race car driver","To live on a boat","To climb Everest"],
  answer:"To be a mum"
 },
 {
  q:"What would Liliana especially love?",
  options:["A baby girl","A spaceship","A private island","A castle"],
  answer:"A baby girl"
 },
 {
  q:"How long have Bree and Liliana been best friends?",
  options:["6 years","1 year","3 years","12 years"],
  answer:"6 years"
 },
 {
  q:"When is Liliana's birthday month?",
  options:["July","January","March","December"],
  answer:"July"
 },
 {
  q:"What day of the month is Liliana's birthday?",
  options:["22","7","16","30"],
  answer:"22"
 },
 {
  q:"Which animal is most connected to Liliana's birthday website?",
  options:["Dolphin","Horse","Cat","Rabbit"],
  answer:"Dolphin"
 },
 {
  q:"Which colour best matches the Lulu Express casino?",
  options:["Baby pink","Neon green","Orange","Purple"],
  answer:"Baby pink"
 },
 {
  q:"What is Liliana known for being?",
  options:["Sweet and caring","Quiet and cold","Mean and serious","Shy and distant"],
  answer:"Sweet and caring"
 },
 {
  q:"Which description fits Liliana?",
  options:["Charismatic","Unfriendly","Boring","Uninterested"],
  answer:"Charismatic"
 },
 {
  q:"What kind of personality is part of Liliana's canon?",
  options:["Flirtatious","Grumpy","Strict","Timid"],
  answer:"Flirtatious"
 },
 {
  q:"Which animal is connected to Liliana's interests?",
  options:["Dolphin","Crocodile","Eagle","Snake"],
  answer:"Dolphin"
 },
 {
  q:"What type of number is 3 for Liliana?",
  options:["Favourite number","Lucky shoe size","House number","Bus route"],
  answer:"Favourite number"
 },
 {
  q:"Which flower is bright and cheerful?",
  options:["Sunflower","Fern","Moss","Bamboo"],
  answer:"Sunflower"
 },
 {
  q:"Which food is specifically part of Liliana's favourites?",
  options:["Sushi","Fish and chips","Pie","Burgers"],
  answer:"Sushi"
 },
 {
  q:"Which film is associated with Liliana?",
  options:["Me Before You","Avatar","Moana","Up"],
  answer:"Me Before You"
 },
 {
  q:"Which of these is NOT Liliana's favourite number?",
  options:["8","3","3 is her favourite","The number 3"],
  answer:"8"
 },
 {
  q:"Which subject is connected to her university studies?",
  options:["Psychology","Dentistry","Chemistry","Music"],
  answer:"Psychology"
 },
 {
  q:"Which of these is one of her fears?",
  options:["Drowning","Rainbows","Flowers","Music"],
  answer:"Drowning"
 },
 {
  q:"Which pair are Liliana's dogs?",
  options:[
   "Aayla & Arlo",
   "Aayla & Luna",
   "Arlo & Bella",
   "Luna & Arlo"
  ],
  answer:"Aayla & Arlo"
 },
 {
  q:"What colour should the Lulu casino background lean towards?",
  options:["Darker baby pink","Purple","Bright blue","Green"],
  answer:"Darker baby pink"
 },
 {
  q:"Which game style belongs in the Lulu Express casino?",
  options:["Gin rummy","Football manager","Golf","Crossword only"],
  answer:"Gin rummy"
 },
 {
  q:"Which big prize belongs on the big slot?",
  options:["1,000,000 tokens","100 tokens","3 tokens","50 tokens"],
  answer:"1,000,000 tokens"
 },
 {
  q:"What kind of race is Lulu Derby?",
  options:["A horse race","A swimming race","A bicycle race","A car race"],
  answer:"A horse race"
 },
 {
  q:"What should happen after passing a Lulu Express level?",
  options:[
   "The next level unlocks",
   "The whole game resets",
   "The player loses all points",
   "The website closes"
  ],
  answer:"The next level unlocks"
 },
 {
  q:"What is the final challenge?",
  options:[
   "50 questions about Liliana",
   "A typing test",
   "A drawing exam",
   "A maths exam"
  ],
  answer:"50 questions about Liliana"
 },
 {
  q:"What is the purpose of the Lulu Express journey?",
  options:[
   "Celebrate Liliana",
   "Train for a job",
   "Learn coding",
   "Practise driving"
  ],
  answer:"Celebrate Liliana"
 }
];


/* =========================================================
   BASIC SYSTEM
========================================================= */

function startGame(){

  const input=document.getElementById("playerName");
  playerName=input.value.trim();

  if(!playerName){
    input.focus();
    input.style.borderColor="#ff5f8f";
    return;
  }

  level=1;
  score=0;
  tokens=0;

  document.getElementById("startScreen").style.display="none";
  document.getElementById("gameScreen").style.display="block";

  document.getElementById("playerDisplay").textContent=playerName;

  updateTop();
  loadLevel();
}


function updateTop(){

  document.getElementById("levelText").textContent=
    "Level "+level+" / 23";

  document.getElementById("scoreText").textContent=score;

  document.getElementById("tokenText").textContent=tokens;
}


function clearTimers(){

  if(gameTimer){
    clearTimeout(gameTimer);
    gameTimer=null;
  }

  if(gameInterval){
    clearInterval(gameInterval);
    gameInterval=null;
  }
}


function loadLevel(){

  clearTimers();

  updateTop();

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

  if(games[level]){
    games[level]();
  }
}


function finishGame(points=100,reward=20,message="Level complete! 💗"){

  clearTimers();

  score+=points;
  tokens+=reward;

  updateTop();

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <div class="stars">★★★★★</div>

      <h2 class="success">LEVEL COMPLETE! 💗</h2>

      <p>${message}</p>

      <div class="resultBox">
        <p>🏆 +${points} points</p>
        <p>🪙 +${reward} tokens</p>
        <p>Total score: <b>${score}</b></p>
      </div>

      ${
        level<23
        ?
        `<button class="primary" onclick="nextLevel()">
          🚂 NEXT LEVEL
        </button>`
        :
        `<button class="primary" onclick="showFinalResults()">
          💗 FINISH JOURNEY
        </button>`
      }

    </div>
  `;
}


function nextLevel(){

  if(level<23){
    level++;
    loadLevel();
  }
}


function resetGame(){

  if(confirm("Restart the entire Lulu Express journey?")){

    clearTimers();

    playerName="";
    level=1;
    score=0;
    tokens=0;

    document.getElementById("gameScreen").style.display="none";
    document.getElementById("startScreen").style.display="flex";

    document.getElementById("playerName").value="";
  }
}


/* =========================================================
   SIMPLE MUSIC
========================================================= */

function toggleMusic(){

  if(!audioContext){
    audioContext=
      new (window.AudioContext||window.webkitAudioContext)();
  }

  musicOn=!musicOn;

  if(musicOn){
    playTone(523,.15);
    setTimeout(()=>playTone(659,.15),170);
    setTimeout(()=>playTone(784,.2),340);
  }
}


function playTone(freq,duration){

  if(!audioContext) return;

  const osc=audioContext.createOscillator();
  const gain=audioContext.createGain();

  osc.frequency.value=freq;
  osc.type="sine";

  gain.gain.setValueAtTime(.04,audioContext.currentTime);
  gain.gain.exponentialRampToValueAtTime(
    .001,
    audioContext.currentTime+duration
  );

  osc.connect(gain);
  gain.connect(audioContext.destination);

  osc.start();
  osc.stop(audioContext.currentTime+duration);
}


/* =========================================================
   GAME 1
   BROKEN HEARTS
========================================================= */

function game1(){

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>💔 Broken Hearts</h2>

      <p class="gameDescription">
        Catch the falling hearts before they reach the bottom!
        This version is deliberately slower and easier on phones.
      </p>

      <div>
        Hearts caught:
        <b id="heartScore">0</b> / 8
      </div>

      <div class="heartArena" id="heartArena">

        <div id="basket" class="basket">💗</div>

      </div>

      <div class="status" id="heartStatus">
        Move the basket underneath the hearts.
      </div>

    </div>
  `;

  const arena=document.getElementById("heartArena");
  const basket=document.getElementById("basket");

  let basketX=50;
  let caught=0;
  let hearts=[];
  let running=true;

  function moveBasket(x){

    const rect=arena.getBoundingClientRect();

    basketX=
      Math.max(
        8,
        Math.min(
          92,
          ((x-rect.left)/rect.width)*100
        )
      );

    basket.style.left="calc("+basketX+"% - 45px)";
  }

  arena.addEventListener("pointermove",e=>{
    moveBasket(e.clientX);
  });

  arena.addEventListener("pointerdown",e=>{
    moveBasket(e.clientX);
  });

  function spawnHeart(){

    if(!running)return;

    const h=document.createElement("div");
    h.className="heart";
    h.textContent=Math.random()<.5?"💗":"💖";

    const x=8+Math.random()*84;

    h.style.left=x+"%";
    h.style.top="-45px";

    arena.appendChild(h);

    hearts.push({
      el:h,
      x:x,
      y:-45
    });
  }

  gameInterval=setInterval(()=>{

    if(!running)return;

    if(Math.random()<.75){
      spawnHeart();
    }

    hearts.forEach((h,index)=>{

      h.y+=1.7;
      h.el.style.top=h.y+"px";

      const arenaHeight=arena.clientHeight;

      const basketLeft=basketX-8;
      const basketRight=basketX+8;

      if(
        h.y>arenaHeight-85 &&
        h.x>basketLeft &&
        h.x<basketRight
      ){

        caught++;

        document.getElementById("heartScore").textContent=caught;

        h.el.remove();
        hearts.splice(index,1);

        if(caught>=8){

          running=false;

          finishGame(
            250,
            30,
            "You caught all the hearts! 💗"
          );
        }
      }

      else if(h.y>arenaHeight){

        h.el.remove();
        hearts.splice(index,1);
      }

    });

  },45);

  gameTimer=setTimeout(()=>{

    if(running){

      running=false;

      if(caught>=6){

        finishGame(
          200,
          25,
          "You saved enough hearts! 💗"
        );

      }else{

        document.getElementById("heartStatus").innerHTML=
          "Almost! You need 6 hearts. Try again.";

        clearTimers();

        setTimeout(game1,1000);
      }
    }

  },30000);
}


/* =========================================================
   GAME 2
   MEMORY VAULT
========================================================= */

function game2(){

  const symbols=[
    "🌸","🌸",
    "🐬","🐬",
    "🌻","🌻",
    "💗","💗",
    "🎲","🎲",
    "🌹","🌹"
  ].sort(()=>Math.random()-.5);

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>🗝️ Memory Vault</h2>

      <p>Match all six pairs.</p>

      <div class="memoryGrid" id="memoryGrid"></div>

      <div class="status" id="memoryStatus">
        Find the matching pairs.
      </div>

    </div>
  `;

  const grid=document.getElementById("memoryGrid");

  let first=null;
  let second=null;
  let locked=false;
  let matches=0;

  symbols.forEach((symbol,i)=>{

    const card=document.createElement("button");

    card.className="memoryCard";
    card.textContent=symbol;
    card.dataset.symbol=symbol;

    card.onclick=()=>{

      if(
        locked ||
        card.classList.contains("flipped") ||
        card.classList.contains("matched")
      )return;

      card.classList.add("flipped");

      if(!first){
        first=card;
        return;
      }

      second=card;
      locked=true;

      if(first.dataset.symbol===second.dataset.symbol){

        first.classList.add("matched");
        second.classList.add("matched");

        matches++;

        first=null;
        second=null;
        locked=false;

        if(matches===6){

          finishGame(
            300,
            35,
            "The Memory Vault has been opened! 🗝️"
          );
        }

      }else{

        setTimeout(()=>{

          first.classList.remove("flipped");
          second.classList.remove("flipped");

          first=null;
          second=null;
          locked=false;

        },650);
      }
    };

    grid.appendChild(card);
  });
}


/* =========================================================
   GAME 3
   PRESSURE QUIZ
========================================================= */

function game3(){

  const questions=[
    facts[0],
    facts[5],
    facts[7],
    facts[14],
    facts[8]
  ];

  let current=0;
  let time=8;
  let answered=false;

  function render(){

    clearTimers();

    answered=false;
    time=8;

    const q=questions[current];

    const options=[...q.options].sort(()=>Math.random()-.5);

    document.getElementById("gameArea").innerHTML=`

      <div class="card">

        <h2>⏱️ Pressure Quiz</h2>

        <p>
          Question ${current+1} / ${questions.length}
        </p>

        <div class="timer" id="pressureTimer">8</div>

        <div class="progress">
          <div
            class="progressFill"
            style="width:${current/questions.length*100}%">
          </div>
        </div>

        <h3>${q.q}</h3>

        <div id="pressureOptions"></div>

        <div class="status" id="pressureStatus"></div>

      </div>
    `;

    const box=document.getElementById("pressureOptions");

    options.forEach(option=>{

      const b=document.createElement("button");
      b.className="gameButton";
      b.textContent=option;

      b.onclick=()=>answerPressure(option,q.answer);

      box.appendChild(b);
    });

    gameInterval=setInterval(()=>{

      time--;

      const timer=document.getElementById("pressureTimer");

      if(timer)timer.textContent=time;

      if(time<=0){

        clearInterval(gameInterval);

        if(!answered){

          answered=true;

          document.getElementById("pressureStatus").innerHTML=
            `<span class="fail">⏰ Time's up!</span>`;

          setTimeout(()=>{

            current++;

            if(current>=questions.length){

              finishGame(
                250,
                30,
                "You survived the pressure quiz! ⏱️"
              );

            }else{
              render();
            }

          },700);
        }
      }

    },1000);
  }

  function answerPressure(selected,correct){

    if(answered)return;

    answered=true;
    clearTimers();

    if(selected===correct){

      score+=50;
      tokens+=5;

      document.getElementById("pressureStatus").innerHTML=
        `<span class="success">✓ Correct!</span>`;

      updateTop();

    }else{

      document.getElementById("pressureStatus").innerHTML=
        `<span class="fail">✗ Correct answer: ${correct}</span>`;
    }

    setTimeout(()=>{

      current++;

      if(current>=questions.length){

        finishGame(
          250,
          30,
          "You survived the pressure quiz! ⏱️"
        );

      }else{
        render();
      }

    },700);
  }

  render();
}


/* =========================================================
   GAME 4
   HIGH ROLLER
========================================================= */

function game4(){

  let number=1+Math.floor(Math.random()*6);

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>🎲 High Roller</h2>

      <p>
        Pick a lucky number. Roll the dice and beat it!
      </p>

      <div class="bigNumber" id="dice">?</div>

      <button class="primary" id="rollBtn">
        🎲 ROLL
      </button>

      <div class="status" id="rollStatus"></div>

    </div>
  `;

  document.getElementById("rollBtn").onclick=()=>{

    const roll=1+Math.floor(Math.random()*6);

    document.getElementById("dice").textContent=roll;

    if(roll>=number){

      finishGame(
        250,
        30,
        "Lucky roll! The house couldn't stop you. 🎲"
      );

    }else{

      document.getElementById("rollStatus").innerHTML=
        `Your target was ${number}. Try again!`;

      number=1+Math.floor(Math.random()*6);
    }
  };
}


/* =========================================================
   GAME 5
   MIND GAMES
========================================================= */

function game5(){

  const rounds=[
    ["🐬","🐬","🌸","🐬"],
    ["🌻","🌹","🌻","🌻"],
    ["💗","💗","💔","💗"],
    ["🎲","🎲","🎲","🎯"],
    ["🌸","🌸","🌸","🌹"]
  ];

  let round=0;

  function render(){

    if(round>=rounds.length){

      finishGame(
        250,
        30,
        "Your eyes caught every odd one out! 👀"
      );

      return;
    }

    const arr=rounds[round];

    document.getElementById("gameArea").innerHTML=`

      <div class="card">

        <h2>🧠 Mind Games</h2>

        <p>
          Tap the symbol that doesn't belong.
        </p>

        <h3>Round ${round+1} / ${rounds.length}</h3>

        <div class="grid grid2">

          ${arr.map((x,i)=>
            `<button
              class="gameButton"
              onclick="mindPick(${i})">
              ${x}
            </button>`
          ).join("")}

        </div>

        <div class="status" id="mindStatus"></div>

      </div>
    `;

    window.mindPick=function(i){

      const correct=rounds[round];

      let odd=0;

      for(let j=1;j<correct.length;j++){

        if(correct[j]!==correct[0]){
          odd=j;
          break;
        }
      }

      if(i===odd){

        round++;
        render();

      }else{

        document.getElementById("mindStatus").innerHTML=
          `<span class="fail">Not that one! Try again.</span>`;
      }
    };
  }

  render();
}


/* =========================================================
   GAME 6
   BLUFF
========================================================= */

function game6(){

  let cards=["🂡","🂢","🂣","🂤","🂥","🂦"];

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>🃏 Bluff</h2>

      <p>
        Find the hidden winning card.
      </p>

      <div class="grid grid3" id="bluffCards"></div>

      <div class="status" id="bluffStatus"></div>

    </div>
  `;

  const winning=Math.floor(Math.random()*cards.length);
  const box=document.getElementById("bluffCards");

  cards.forEach((c,i)=>{

    const b=document.createElement("button");

    b.className="gameButton";
    b.textContent="🂠";

    b.onclick=()=>{

      if(i===winning){

        b.textContent=c;

        finishGame(
          250,
          30,
          "You called the bluff! 🃏"
        );

      }else{

        b.textContent="❌";

        document.getElementById("bluffStatus").textContent=
          "Not this card. Keep looking!";
      }
    };

    box.appendChild(b);
  });
}


/* =========================================================
   GAME 7
   SURVIVAL
========================================================= */

function game7(){

  let lives=3;
  let danger=0;

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>❤️ Survival</h2>

      <p>
        Keep your heart alive. Tap SAFE whenever danger appears.
      </p>

      <div class="bigNumber" id="survivalHeart">
        ❤️
      </div>

      <p>
        Lives: <span id="lives">❤️❤️❤️</span>
      </p>

      <button class="primary" onclick="survivalSafe()">
        🛡️ SAFE
      </button>

      <div class="status" id="survivalStatus"></div>

    </div>
  `;

  function dangerEvent(){

    danger=1;

    document.getElementById("survivalHeart").textContent="⚠️";

    document.getElementById("survivalStatus").textContent=
      "DANGER!";

    gameTimer=setTimeout(()=>{

      if(danger===1){

        lives--;

        document.getElementById("lives").textContent=
          "❤️".repeat(lives)+"🖤".repeat(3-lives);

        danger=0;

        if(lives<=0){

          document.getElementById("survivalStatus").textContent=
            "The heart broke. Restarting...";

          setTimeout(game7,900);

        }else{

          document.getElementById("survivalHeart").textContent="❤️";

          setTimeout(dangerEvent,700);
        }

      }

    },1200);
  }

  window.survivalSafe=function(){

    if(danger===1){

      danger=0;
      clearTimeout(gameTimer);

      document.getElementById("survivalHeart").textContent="❤️";

      document.getElementById("survivalStatus").textContent=
        "Saved! 💗";

      setTimeout(dangerEvent,650);

      if(lives===3){

        score+=50;
        tokens+=5;
        updateTop();
      }

    }else{

      document.getElementById("survivalStatus").textContent=
        "Wait for danger!";
    }
  };

  setTimeout(dangerEvent,900);
}


/* =========================================================
   GAME 8
   ADMIRER RACE
========================================================= */

function game8(){

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>🏃 Admirer Race</h2>

      <p>
        Tap the button to make your character run.
        Reach the finish first!
      </p>

      <div class="raceTrack">

        <div id="playerRacer"
             class="racer"
             style="top:35px;">
          💗
        </div>

        <div id="enemyRacer"
             class="racer"
             style="top:135px;">
          😈
        </div>

        <div class="finish"></div>

      </div>

      <button class="primary" id="runBtn">
        TAP TO RUN 🏃
      </button>

      <div class="status" id="raceStatus"></div>

    </div>
  `;

  let player=0;
  let enemy=0;
  let active=true;

  document.getElementById("runBtn").onclick=()=>{

    if(!active)return;

    player+=8;

    document.getElementById("playerRacer").style.left=
      player+"%";

    if(player>=88){

      active=false;

      finishGame(
        300,
        35,
        "You won the race! 🏆"
      );

      return;
    }

    enemy+=3+Math.random()*4;

    document.getElementById("enemyRacer").style.left=
      Math.min(enemy,88)+"%";

    if(enemy>=88){

      active=false;

      document.getElementById("raceStatus").innerHTML=
        `<span class="fail">You were caught! Try again.</span>`;

      setTimeout(game8,900);
    }
  };
}


/* =========================================================
   GAME 9
   HEARTBREAK CHAMBER
========================================================= */

function game9(){

  let hearts=10;

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>💔 Heartbreak Chamber</h2>

      <p>
        Break the heartbreak by tapping the broken heart.
      </p>

      <div class="bigNumber" id="breakHeart">
        💔
      </div>

      <p>
        Hits remaining: <b id="hits">10</b>
      </p>

      <button class="primary" id="hitButton">
        💥 HEAL HEART
      </button>

    </div>
  `;

  document.getElementById("hitButton").onclick=()=>{

    hearts--;

    document.getElementById("hits").textContent=hearts;

    if(hearts<=0){

      document.getElementById("breakHeart").textContent="💗";

      finishGame(
        250,
        30,
        "The broken heart has been healed! 💗"
      );
    }
  };
}


/* =========================================================
   GAME 10
   BOXING
========================================================= */

function game10(){

  let punches=0;

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>🥊 Love Boxing</h2>

      <p>
        Land 12 punches before the timer runs out.
      </p>

      <div class="bigNumber" id="boxingTarget">
        🥊
      </div>

      <p>
        Punches: <b id="punchCount">0</b> / 12
      </p>

      <div class="timer" id="boxingTimer">15</div>

      <button class="primary" id="punch">
        🥊 PUNCH
      </button>

      <div class="status" id="boxingStatus"></div>

    </div>
  `;

  let time=15;

  document.getElementById("punch").onclick=()=>{

    punches++;

    document.getElementById("punchCount").textContent=punches;

    if(punches>=12){

      finishGame(
        250,
        30,
        "Knockout! 🥊💗"
      );
    }
  };

  gameInterval=setInterval(()=>{

    time--;

    document.getElementById("boxingTimer").textContent=time;

    if(time<=0){

      clearTimers();

      if(punches>=8){

        finishGame(
          200,
          25,
          "You survived the boxing round! 🥊"
        );

      }else{

        document.getElementById("boxingStatus").innerHTML=
          "You need 8 punches. Try again.";

        setTimeout(game10,800);
      }
    }

  },1000);
}


/* =========================================================
   GAME 11
   PERFECT MATCH
========================================================= */

function game11(){

  const pairs=[
    ["💗","💖"],
    ["🌸","🌻"],
    ["🐬","🌊"],
    ["🌹","💐"]
  ];

  let index=0;

  function render(){

    if(index>=pairs.length){

      finishGame(
        250,
        30,
        "Every match was perfect! 💗"
      );

      return;
    }

    const p=pairs[index];

    document.getElementById("gameArea").innerHTML=`

      <div class="card">

        <h2>💞 Perfect Match</h2>

        <p>
          Which symbol belongs with:
        </p>

        <div class="bigNumber">${p[0]}</div>

        <button
          class="gameButton"
          onclick="matchChoice(0)">
          ${p[1]}
        </button>

        <button
          class="gameButton"
          onclick="matchChoice(1)">
          ${
            ["🎲","🍕","⚽","🌙"][index]
          }
        </button>

        <div class="status" id="matchStatus"></div>

      </div>
    `;

    window.matchChoice=function(choice){

      if(choice===0){

        index++;
        render();

      }else{

        document.getElementById("matchStatus").textContent=
          "Not quite! Try again.";
      }
    };
  }

  render();
}


/* =========================================================
   GAME 12
   LILIANA QUIZ
========================================================= */

function game12(){

  let qs=[...facts.slice(0,10)]
    .sort(()=>Math.random()-.5);

  let current=0;
  let correct=0;

  function render(){

    if(current>=qs.length){

      finishGame(
        300,
        40,
        "You really know Lulu! 💗"
      );

      return;
    }

    const q=qs[current];
    const options=[...q.options].sort(()=>Math.random()-.5);

    document.getElementById("gameArea").innerHTML=`

      <div class="card">

        <h2>🌸 Liliana Quiz</h2>

        <p>
          ${current+1} / ${qs.length}
        </p>

        <h3>${q.q}</h3>

        ${options.map(o=>
          `<button
             class="gameButton"
             onclick="quiz12Answer('${escapeJS(o)}','${escapeJS(q.answer)}')">
             ${o}
           </button>`
        ).join("")}

        <div class="status" id="quiz12Status"></div>

      </div>
    `;

    window.quiz12Answer=function(selected,answer){

      if(selected===answer){

        correct++;
        score+=30;
        tokens+=3;
        updateTop();

        current++;
        render();

      }else{

        document.getElementById("quiz12Status").innerHTML=
          `<span class="fail">Try again! 💗</span>`;
      }
    };
  }

  render();
}


/* =========================================================
   GAME 13
   REACTION GAUNTLET
========================================================= */

function game13(){

  let round=0;
  let good=0;

  function next(){

    if(round>=7){

      if(good>=5){

        finishGame(
          300,
          35,
          "Your reactions were lightning fast! ⚡"
        );

      }else{

        document.getElementById("gameArea").innerHTML=`

          <div class="card">

            <h2>⚡ Reaction Gauntlet</h2>

            <p>
              You need 5 successful reactions.
            </p>

            <p>
              You got ${good}.
            </p>

            <button class="primary" onclick="game13()">
              TRY AGAIN
            </button>

          </div>
        `;
      }

      return;
    }

    document.getElementById("gameArea").innerHTML=`

      <div class="card">

        <h2>⚡ Reaction Gauntlet</h2>

        <p>
          Round ${round+1} / 7
        </p>

        <div class="bigNumber" id="reactionSymbol">
          ⏳
        </div>

        <button
          class="primary"
          id="reactionButton"
          disabled>
          WAIT...
        </button>

      </div>
    `;

    const delay=700+Math.random()*1800;

    gameTimer=setTimeout(()=>{

      const button=document.getElementById("reactionButton");
      const symbol=document.getElementById("reactionSymbol");

      if(!button)return;

      symbol.textContent="💗";
      button.disabled=false;
      button.textContent="TAP NOW!";

      const start=Date.now();

      button.onclick=()=>{

        const reaction=Date.now()-start;

        if(reaction<1000){
          good++;
        }

        round++;

        next();
      };

    },delay);
  }

  next();
}


/* =========================================================
   GAME 14
   HEART HUNT
========================================================= */

function game14(){

  let found=0;

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>🔎 Heart Hunt</h2>

      <p>
        Find all 5 hidden hearts.
      </p>

      <div
        id="huntArea"
        style="
          position:relative;
          height:430px;
          max-width:550px;
          margin:auto;
          border-radius:20px;
          background:#24101a;
          overflow:hidden;
          border:2px solid #75304e;
        ">
      </div>

      <p>
        Found:
        <b id="foundCount">0</b> / 5
      </p>

    </div>
  `;

  const area=document.getElementById("huntArea");

  for(let i=0;i<5;i++){

    const b=document.createElement("button");

    b.textContent="💗";
    b.style.position="absolute";
    b.style.left=(5+Math.random()*85)+"%";
    b.style.top=(5+Math.random()*85)+"%";
    b.style.fontSize="25px";
    b.style.background="transparent";
    b.style.border="0";

    b.onclick=()=>{

      if(b.disabled)return;

      b.disabled=true;
      b.style.opacity=".25";

      found++;

      document.getElementById("foundCount").textContent=found;

      if(found===5){

        finishGame(
          250,
          30,
          "You found every hidden heart! 💗"
        );
      }
    };

    area.appendChild(b);
  }
}


/* =========================================================
   GAME 15
   LOVE LOCK
========================================================= */

function game15(){

  let step=0;
  const answers=[3,6,7];

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>🔒 Love Lock</h2>

      <p class="gameDescription">
        Solve all three clues to unlock the love lock.
      </p>

      <div
        class="bigNumber"
        id="lockDisplay">
        ???
      </div>

      <div id="lockClue"></div>

      <div id="lockButtons"></div>

      <div class="status" id="lockStatus"></div>

    </div>
  `;

  function render(){

    const clues=[
      "What is Liliana's favourite number?",
      "How many years have you been best friends?",
      "What month is Liliana's birthday?"
    ];

    const options=[
      [3,5,7],
      [4,6,8],
      [5,7,9]
    ];

    document.getElementById("lockClue").innerHTML=
      `<h3>Clue ${step+1}: ${clues[step]}</h3>`;

    const box=document.getElementById("lockButtons");
    box.innerHTML="";

    options[step].sort(()=>Math.random()-.5);

    options[step].forEach(number=>{

      const b=document.createElement("button");

      b.className="gameButton";
      b.textContent=number;

      b.onclick=()=>{

        if(number===answers[step]){

          step++;

          document.getElementById("lockDisplay").textContent=
            "•".repeat(step)+"•".repeat(3-step);

          if(step===3){

            document.getElementById("lockDisplay").textContent=
              "367";

            finishGame(
              300,
              40,
              "The Love Lock opened! 🔓💗"
            );

          }else{

            render();
          }

        }else{

          document.getElementById("lockStatus").innerHTML=
            `<span class="fail">
              ❌ Not quite. Try this clue again.
            </span>`;
        }
      };

      box.appendChild(b);
    });
  }

  render();
}


/* =========================================================
   GAME 16
   CUPID SHOOTOUT
========================================================= */

function game16(){

  let hits=0;

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>🏹 Cupid Shootout</h2>

      <p>
        Hit 8 hearts!
      </p>

      <div
        id="cupidArea"
        style="
          position:relative;
          height:430px;
          max-width:550px;
          margin:auto;
          background:#1d0b15;
          border-radius:20px;
          border:2px solid #71304b;
          overflow:hidden;
        ">
      </div>

      <p>
        Hits:
        <b id="cupidHits">0</b> / 8
      </p>

    </div>
  `;

  const area=document.getElementById("cupidArea");

  function spawn(){

    const b=document.createElement("button");

    b.textContent="💗";

    b.style.position="absolute";
    b.style.left=(5+Math.random()*85)+"%";
    b.style.top=(5+Math.random()*85)+"%";
    b.style.fontSize="28px";
    b.style.background="transparent";
    b.style.border="0";

    b.onclick=()=>{

      if(b.disabled)return;

      b.disabled=true;
      b.remove();

      hits++;

      document.getElementById("cupidHits").textContent=hits;

      if(hits>=8){

        finishGame(
          300,
          35,
          "Cupid hit every target! 🏹💗"
        );

      }else{

        spawn();
      }
    };

    area.appendChild(b);
  }

  for(let i=0;i<3;i++)spawn();
}


/* =========================================================
   GAME 17
   COUNTDOWN
========================================================= */

function game17(){

  let number=10;

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>⏳ Countdown</h2>

      <p>
        Tap STOP when the counter reaches exactly 1.
      </p>

      <div class="timer" id="countdownNumber">
        10
      </div>

      <button class="primary" id="stopCountdown">
        🛑 STOP
      </button>

      <div class="status" id="countdownStatus"></div>

    </div>
  `;

  gameInterval=setInterval(()=>{

    number--;

    document.getElementById("countdownNumber").textContent=
      number;

    if(number<=0){

      clearTimers();

      document.getElementById("countdownStatus").textContent=
        "Too late! Try again.";

      setTimeout(game17,900);
    }

  },600);

  document.getElementById("stopCountdown").onclick=()=>{

    clearTimers();

    if(number===1){

      finishGame(
        300,
        35,
        "Perfect timing! ⏳💗"
      );

    }else{

      document.getElementById("countdownStatus").textContent=
        "Not quite! Try again.";

      setTimeout(game17,800);
    }
  };
}


/* =========================================================
   GAME 18
   ULTIMATE GAMBLE
========================================================= */

function game18(){

  let tokensBet=50;

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>🎰 Ultimate Gamble</h2>

      <p>
        Pick a door. One contains the jackpot.
      </p>

      <div class="bigNumber">
        🪙
      </div>

      <div class="grid grid3">

        <button class="gameButton" onclick="gambleDoor(0)">
          🚪 1
        </button>

        <button class="gameButton" onclick="gambleDoor(1)">
          🚪 2
        </button>

        <button class="gameButton" onclick="gambleDoor(2)">
          🚪 3
        </button>

      </div>

      <div class="status" id="gambleStatus"></div>

    </div>
  `;

  const winning=Math.floor(Math.random()*3);

  window.gambleDoor=function(choice){

    if(choice===winning){

      tokens+=tokensBet;
      score+=300;

      updateTop();

      finishGame(
        300,
        50,
        "You hit the winning door! 🎰🪙"
      );

    }else{

      document.getElementById("gambleStatus").innerHTML=
        `<span class="fail">Wrong door! Choose again.</span>`;
    }
  };
}


/* =========================================================
   GAME 19
   LAST STAND
========================================================= */

function game19(){

  let clicks=0;
  let target=15;

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>🛡️ Last Stand</h2>

      <p>
        Defend the heart with 15 taps!
      </p>

      <div class="bigNumber" id="standHeart">
        💗
      </div>

      <p>
        Defence:
        <b id="standCount">0</b> / ${target}
      </p>

      <button class="primary" id="defend">
        🛡️ DEFEND
      </button>

    </div>
  `;

  document.getElementById("defend").onclick=()=>{

    clicks++;

    document.getElementById("standCount").textContent=clicks;

    if(clicks>=target){

      finishGame(
        300,
        35,
        "You protected the heart! 🛡️💗"
      );
    }
  };
}


/* =========================================================
   GAME 20
   WORD FIND
========================================================= */

function game20(){

  const words=[
    "LULU",
    "DOLPHIN",
    "ROSE",
    "SUSHI",
    "POETRY",
    "SUNFLOWER",
    "PINK"
  ];

  const size=10;

  let board=Array(size*size).fill("");

  function placeWord(word){

    const directions=[
      [0,1],
      [1,0],
      [1,1],
      [0,-1]
    ];

    for(let attempt=0;attempt<200;attempt++){

      const d=directions[
        Math.floor(Math.random()*directions.length)
      ];

      const row=Math.floor(Math.random()*size);
      const col=Math.floor(Math.random()*size);

      const cells=[];

      let valid=true;

      for(let i=0;i<word.length;i++){

        const r=row+d[0]*i;
        const c=col+d[1]*i;

        if(
          r<0 ||
          r>=size ||
          c<0 ||
          c>=size
        ){
          valid=false;
          break;
        }

        const idx=r*size+c;

        if(board[idx] && board[idx]!==word[i]){
          valid=false;
          break;
        }

        cells.push(idx);
      }

      if(valid){

        cells.forEach((idx,i)=>{
          board[idx]=word[i];
        });

        return true;
      }
    }

    return false;
  }

  words.forEach(placeWord);

  const letters="ABCDEFGHIJKLMNOPQRSTUVWXYZ";

  board=board.map(x=>
    x || letters[Math.floor(Math.random()*letters.length)]
  );

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>🔤 Lulu Word Find</h2>

      <p>
        Find:
        <b>${words.join(", ")}</b>
      </p>

      <div class="wordGrid" id="wordGrid"></div>

      <div class="status" id="wordStatus">
        Tap letters in order.
      </div>

    </div>
  `;

  const grid=document.getElementById("wordGrid");

  let selected=[];
  let foundWords=[];

  board.forEach((letter,i)=>{

    const b=document.createElement("button");

    b.className="letter";
    b.textContent=letter;

    b.onclick=()=>{

      b.classList.toggle("selected");

      if(b.classList.contains("selected")){
        selected.push({
          letter:letter,
          index:i
        });
      }else{
        selected=selected.filter(x=>x.index!==i);
      }

      const word=selected.map(x=>x.letter).join("");

      if(words.includes(word) && !foundWords.includes(word)){

        foundWords.push(word);

        selected.forEach(x=>{
          grid.children[x.index].style.background="#d884aa";
        });

        selected=[];

        grid.querySelectorAll(".selected")
          .forEach(x=>x.classList.remove("selected"));

        document.getElementById("wordStatus").textContent=
          "Found "+word+"! 💗";

        if(foundWords.length===words.length){

          finishGame(
            350,
            45,
            "You found every Lulu word! 🔤💗"
          );
        }
      }
    };

    grid.appendChild(b);
  });
}


/* =========================================================
   GAME 21
   DRAW A SUNFLOWER
========================================================= */

function game21(){

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <h2>🌻 Draw a Sunflower</h2>

      <p>
        Draw your own sunflower inside the canvas.
      </p>

      <canvas
        id="flowerCanvas"
        class="flowerCanvas"
        width="550"
        height="360">
      </canvas>

      <button class="primary" onclick="submitFlower()">
        🌻 FINISH DRAWING
      </button>

      <button class="secondary" onclick="clearFlower()">
        Clear
      </button>

      <div class="status" id="flowerStatus"></div>

    </div>
  `;

  const canvas=document.getElementById("flowerCanvas");
  const ctx=canvas.getContext("2d");

  ctx.lineWidth=7;
  ctx.lineCap="round";
  ctx.strokeStyle="#7a2348";

  let drawing=false;

  function position(e){

    const rect=canvas.getBoundingClientRect();

    return {
      x:(e.clientX-rect.left)*(canvas.width/rect.width),
      y:(e.clientY-rect.top)*(canvas.height/rect.height)
    };
  }

  canvas.addEventListener("pointerdown",e=>{

    drawing=true;

    const p=position(e);

    ctx.beginPath();
    ctx.moveTo(p.x,p.y);
  });

  canvas.addEventListener("pointermove",e=>{

    if(!drawing)return;

    const p=position(e);

    ctx.lineTo(p.x,p.y);
    ctx.stroke();
  });

  canvas.addEventListener("pointerup",()=>{
    drawing=false;
  });

  canvas.addEventListener("pointerleave",()=>{
    drawing=false;
  });

  window.clearFlower=function(){

    ctx.clearRect(0,0,canvas.width,canvas.height);

    document.getElementById("flowerStatus").textContent="";
  };

  window.submitFlower=function(){

    finishGame(
      300,
      40,
      "Your sunflower masterpiece is complete! 🌻"
    );
  };
}


/* =========================================================
   GAME 22
   LULU DERBY
   100 RANDOM TRIVIA QUESTIONS
========================================================= */

function game22(){

  const trivia=[

    ["How many days are in a week?","7"],
    ["How many months are in a year?","12"],
    ["What planet do we live on?","Earth"],
    ["What is the capital of France?","Paris"],
    ["How many legs does a spider have?","8"],
    ["What colour do you get by mixing red and blue?","Purple"],
    ["How many sides does a triangle have?","3"],
    ["What is the opposite of hot?","Cold"],
    ["What is frozen water called?","Ice"],
    ["Which animal says moo?","Cow"],
    ["How many hours are in a day?","24"],
    ["How many minutes are in an hour?","60"],
    ["What is 5 + 5?","10"],
    ["What is 10 - 4?","6"],
    ["What is 3 x 3?","9"],
    ["What is 20 divided by 2?","10"],
    ["Which season comes after winter?","Spring"],
    ["Which season is usually hottest?","Summer"],
    ["What do bees make?","Honey"],
    ["What do chickens lay?","Eggs"],
    ["Which animal is known as man's best friend?","Dog"],
    ["How many continents are there?","7"],
    ["What is the largest ocean?","Pacific"],
    ["What is the colour of grass?","Green"],
    ["What is the colour of a banana?","Yellow"],
    ["What do you call a baby cat?","Kitten"],
    ["What do you call a baby dog?","Puppy"],
    ["Which bird cannot fly and lives in Antarctica?","Penguin"],
    ["What is the tallest animal?","Giraffe"],
    ["What is the fastest land animal?","Cheetah"],
    ["What is the largest land animal?","Elephant"],
    ["What is the largest mammal?","Blue whale"],
    ["What is the smallest prime number?","2"],
    ["How many wheels does a bicycle have?","2"],
    ["How many wheels does a car usually have?","4"],
    ["What is the opposite of day?","Night"],
    ["What is the opposite of up?","Down"],
    ["What is the opposite of left?","Right"],
    ["What is the opposite of happy?","Sad"],
    ["What shape has four equal sides?","Square"],
    ["How many sides does a pentagon have?","5"],
    ["How many sides does a hexagon have?","6"],
    ["What star is closest to Earth?","Sun"],
    ["What is Earth's natural satellite?","Moon"],
    ["Which planet is known as the Red Planet?","Mars"],
    ["Which planet is famous for its rings?","Saturn"],
    ["What gas do humans breathe in?","Oxygen"],
    ["What do plants need for photosynthesis?","Sunlight"],
    ["What is the boiling point of water in Celsius?","100"],
    ["What is the freezing point of water in Celsius?","0"],
    ["How many letters are in the English alphabet?","26"],
    ["What is the first letter of the alphabet?","A"],
    ["What is the last letter of the alphabet?","Z"],
    ["Which instrument has black and white keys?","Piano"],
    ["How many strings does a standard guitar have?","6"],
    ["What sport uses a racket and shuttlecock?","Badminton"],
    ["What sport has touchdowns?","American football"],
    ["What sport uses a hoop?","Basketball"],
    ["What sport is played at Wimbledon?","Tennis"],
    ["How many players are on a soccer team on the field?","11"],
    ["What colour are emeralds usually?","Green"],
    ["What colour is a ruby usually?","Red"],
    ["What is the hardest natural mineral?","Diamond"],
    ["What do you call molten rock underground?","Magma"],
    ["What do you call molten rock above ground?","Lava"],
    ["Which country is famous for sushi?","Japan"],
    ["Which country is shaped like a boot?","Italy"],
    ["What is the capital of New Zealand?","Wellington"],
    ["What is the capital of Australia?","Canberra"],
    ["What is the capital of Japan?","Tokyo"],
    ["What is the capital of Spain?","Madrid"],
    ["Which language is mainly spoken in Brazil?","Portuguese"],
    ["What currency is used in New Zealand?","Dollar"],
    ["How many colours are traditionally in a rainbow?","7"],
    ["What is a group of stars called?","Constellation"],
    ["What do you call a scientist who studies space?","Astronomer"],
    ["What is the centre of our solar system?","Sun"],
    ["Which direction does the sun rise from?","East"],
    ["Which direction does the sun set?","West"],
    ["What is the largest planet?","Jupiter"],
    ["What is the smallest planet?","Mercury"],
    ["Which planet is closest to the Sun?","Mercury"],
    ["What animal is famous for its long neck?","Giraffe"],
    ["What animal is famous for black and white stripes?","Zebra"],
    ["What animal is known for carrying a pouch?","Kangaroo"],
    ["What animal can change colour?","Chameleon"],
    ["What insect has colourful wings?","Butterfly"],
    ["What insect makes honey?","Bee"],
    ["What animal lives in a shell and moves slowly?","Snail"],
    ["What animal is known for building dams?","Beaver"],
    ["What animal is known for its black mask and ringed tail?","Raccoon"],
    ["What is a baby horse called?","Foal"],
    ["What is a baby sheep called?","Lamb"],
    ["What is a baby goat called?","Kid"],
    ["What is a baby cow called?","Calf"],
    ["What is a baby pig called?","Piglet"],
    ["What is a baby deer called?","Fawn"],
    ["What is the opposite of early?","Late"],
    ["What is the opposite of fast?","Slow"],
    ["What is the opposite of big?","Small"],
    ["What is the opposite of full?","Empty"]
  ];

  let questions=[...trivia]
    .sort(()=>Math.random()-.5)
    .slice(0,10);

  let current=0;
  let derbyScore=0;

  function render(){

    if(current>=questions.length){

      finishGame(
        500,
        60,
        "You won the Lulu Derby! 🏇🏆"
      );

      return;
    }

    const q=questions[current];

    let options=[
      q[1],
      randomWrong(q[1]),
      randomWrong(q[1]),
      randomWrong(q[1])
    ].sort(()=>Math.random()-.5);

    document.getElementById("gameArea").innerHTML=`

      <div class="card">

        <h2>🏇 Lulu Derby</h2>

        <p>
          Trivia Race
          ${current+1} / ${questions.length}
        </p>

        <div class="derby">

          <div
            id="derbyHorse"
            class="horse"
            style="top:105px;">
            🐎
          </div>

          <div class="derbyFinish"></div>

        </div>

        <h3>${q[0]}</h3>

        ${options.map(o=>
          `<button
            class="gameButton"
            onclick="derbyAnswer('${escapeJS(o)}','${escapeJS(q[1])}')">
            ${o}
          </button>`
        ).join("")}

        <div class="status" id="derbyStatus"></div>

      </div>
    `;

    window.derbyAnswer=function(selected,answer){

      if(selected===answer){

        derbyScore++;
        current++;

        score+=50;
        tokens+=5;

        updateTop();

        const horse=document.getElementById("derbyHorse");

        if(horse){
          horse.style.left=
            Math.min(90,derbyScore*9)+"%";
        }

        setTimeout(render,350);

      }else{

        document.getElementById("derbyStatus").innerHTML=
          `<span class="fail">Wrong! The horse slows down. 🐎</span>`;
      }
    };
  }

  render();
}


function randomWrong(correct){

  const wrongs=[
    "Banana",
    "Blue",
    "12",
    "Moon",
    "Tiger",
    "Green",
    "Paris",
    "4",
    "Winter",
    "Piano",
    "Mars",
    "Dog"
  ];

  let x=wrongs[Math.floor(Math.random()*wrongs.length)];

  if(x===correct){
    return "7";
  }

  return x;
}


/* =========================================================
   GAME 23
   FINAL CHALLENGE
   EXACTLY 50 QUESTIONS
========================================================= */

function game23(){

  let questions=[...finalQuestions];

  /*
    Guarantee exactly 50 questions.
  */
  questions=questions.slice(0,50);

  let current=0;
  let correct=0;
  let finalAnswered=false;

  function render(){

    if(current>=50){

      showFinalChallengeResult(correct);

      return;
    }

    finalAnswered=false;

    const q=questions[current];

    const options=[...q.options]
      .sort(()=>Math.random()-.5);

    document.getElementById("gameArea").innerHTML=`

      <div class="card">

        <h2>💗 FINAL CHALLENGE</h2>

        <p>
          Question ${current+1} / 50
        </p>

        <div class="progress">
          <div
            class="progressFill"
            style="width:${current/50*100}%">
          </div>
        </div>

        <h3>${q.q}</h3>

        ${options.map(o=>
          `<button
             class="gameButton"
             onclick="finalAnswer('${escapeJS(o)}','${escapeJS(q.answer)}')">
             ${o}
           </button>`
        ).join("")}

        <div
          class="status"
          id="finalStatus">
        </div>

      </div>
    `;

    window.finalAnswer=function(selected,answer){

      if(finalAnswered)return;

      if(selected===answer){

        finalAnswered=true;
        correct++;

        score+=75;
        tokens+=7;

        updateTop();

        document.getElementById("finalStatus").innerHTML=
          `<span class="success">✓ Correct! 💗</span>`;

        setTimeout(()=>{

          current++;
          render();

        },300);

      }else{

        document.getElementById("finalStatus").innerHTML=
          `<span class="fail">
            ✗ Not quite. Try again.
          </span>`;
      }
    };
  }

  render();

  window.currentFinalCorrect=()=>correct;
}


function showFinalChallengeResult(correct){

  clearTimers();

  /*
    Private call requirement:
    STRICTLY GREATER THAN 3000.
    3000 does NOT qualify.
  */

  const qualifies=score>3000;

  document.getElementById("gameArea").innerHTML=`

    <div class="card">

      <div class="stars">💗 💗 💗 💗 💗</div>

      <h2>🎉 JOURNEY COMPLETE 🎉</h2>

      <p>
        ${playerName}, you made it through
        all 23 levels!
      </p>

      <div class="resultBox">

        <h3>Final Challenge</h3>

        <p>
          Correct:
          <b>${correct} / 50</b>
        </p>

        <p>
          Final Score:
          <b>${score}</b>
        </p>

        <p>
          Tokens:
          <b>${tokens}</b>
        </p>

      </div>

      ${
        qualifies
        ?
        `
        <div class="resultBox">

          <h2 class="success">
            📞 PRIVATE CALL UNLOCKED
          </h2>

          <p>
            You scored more than 3000 points!
          </p>

          <p>
            Your final score of
            <b>${score}</b>
            qualifies for the private call reward. 💗
          </p>

        </div>
        `
        :
        `
        <div class="resultBox">

          <h3>💗 Almost there!</h3>

          <p>
            The private call requires a score
            <b>strictly above 3000</b>.
          </p>

          <p>
            Your score was
            <b>${score}</b>.
          </p>

        </div>
        `
      }

      <button class="primary" onclick="resetGame()">
        ↻ PLAY AGAIN
      </button>

    </div>
  `;
}


/* =========================================================
   FINAL RESULTS HELPER
========================================================= */

function showFinalResults(){

  if(level===23){

    /*
      If the user reaches this screen through finishGame,
      the Final Challenge has already calculated the result.
    */

    document.getElementById("gameArea").innerHTML=`

      <div class="card">

        <h2>💗 Lulu Express</h2>

        <p>
          Congratulations, ${playerName}!
        </p>

        <p>
          You completed the entire journey.
        </p>

        <p>
          Final score:
          <b>${score}</b>
        </p>

        <button class="primary" onclick="resetGame()">
          ↻ PLAY AGAIN
        </button>

      </div>
    `;
  }
}


/* =========================================================
   UTILITIES
========================================================= */

function escapeJS(value){

  return String(value)
    .replace(/\\/g,"\\\\")
    .replace(/'/g,"\\'")
    .replace(/\n/g,"\\n")
    .replace(/\r/g,"\\r");
}


/* =========================================================
   PREVENT ACCIDENTAL DOUBLE TAP ZOOM
========================================================= */

let lastTouchEnd=0;

document.addEventListener(
  "touchend",
  function(event){

    const now=Date.now();

    if(now-lastTouchEnd<=300){
      event.preventDefault();
    }

    lastTouchEnd=now;
  },
  false
);


/* =========================================================
   PREVENT PINCH ZOOM
========================================================= */

document.addEventListener(
  "gesturestart",
  function(e){
    e.preventDefault();
  }
);

document.addEventListener(
  "gesturechange",
  function(e){
    e.preventDefault();
  }
);

document.addEventListener(
  "gestureend",
  function(e){
    e.preventDefault();
  }
);


/* =========================================================
   START
========================================================= */

document.getElementById("playerName")
  .addEventListener("keydown",function(e){

    if(e.key==="Enter"){
      startGame();
    }

  });

</script>

</body>
</html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport"
      content="width=device-width, initial-scale=1.0,
               maximum-scale=1.0, user-scalable=no,
               viewport-fit=cover">

<title>Lulu Express ♡</title>

<style>
* {
  box-sizing: border-box;
  -webkit-tap-highlight-color: transparent;
}

html, body {
  margin: 0;
  padding: 0;
  width: 100%;
  min-height: 100%;
  overflow-x: hidden;
  touch-action: manipulation;
  font-family: Arial, Helvetica, sans-serif;
  background:
    radial-gradient(circle at top, #5d183e 0%, #270d24 42%, #090712 100%);
  color: white;
}

body {
  overscroll-behavior: none;
}

button,
input {
  font: inherit;
}

button {
  cursor: pointer;
  border: none;
}

.hidden {
  display: none !important;
}

/* =========================
   GLOBAL
========================= */

#app {
  width: 100%;
  min-height: 100vh;
}

.screen {
  min-height: 100vh;
  width: 100%;
  padding:
    max(18px, env(safe-area-inset-top))
    14px
    max(22px, env(safe-area-inset-bottom))
    14px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.card {
  width: min(760px, 100%);
  background: rgba(20, 8, 22, .88);
  border: 1px solid rgba(255, 177, 218, .25);
  border-radius: 24px;
  padding: 20px;
  box-shadow: 0 15px 50px rgba(0,0,0,.35);
}

h1, h2, h3 {
  text-align: center;
  margin-top: 0;
}

h1 {
  font-size: clamp(32px, 9vw, 64px);
  margin-bottom: 8px;
}

h2 {
  font-size: clamp(24px, 7vw, 40px);
}

p {
  line-height: 1.55;
}

.subtitle {
  text-align: center;
  opacity: .85;
}

.primary,
.secondary,
.danger,
.option,
.game-button {
  width: 100%;
  min-height: 54px;
  border-radius: 16px;
  margin-top: 10px;
  padding: 12px 16px;
  font-weight: 800;
  transition: transform .12s ease, opacity .12s ease;
}

.primary {
  background: linear-gradient(135deg, #ff8bc4, #ff4f9a);
  color: #26091d;
}

.secondary {
  background: rgba(255,255,255,.12);
  color: white;
  border: 1px solid rgba(255,255,255,.15);
}

.danger {
  background: #8e214e;
  color: white;
}

.primary:active,
.secondary:active,
.danger:active,
.option:active,
.game-button:active {
  transform: scale(.97);
}

.topbar {
  width: min(900px, 100%);
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
  justify-content: center;
  margin-bottom: 12px;
}

.stat {
  background: rgba(255,255,255,.09);
  border: 1px solid rgba(255,255,255,.12);
  border-radius: 999px;
  padding: 8px 13px;
  font-weight: 700;
}

.musicBox {
  position: fixed;
  z-index: 1000;
  right: 10px;
  top: max(10px, env(safe-area-inset-top));
  display: flex;
  gap: 5px;
}

.musicBox button {
  width: 43px;
  height: 43px;
  border-radius: 50%;
  background: rgba(25,5,25,.88);
  color: white;
  border: 1px solid rgba(255,255,255,.2);
}

.progress {
  width: min(760px, 100%);
  height: 10px;
  background: rgba(255,255,255,.1);
  border-radius: 20px;
  overflow: hidden;
  margin-bottom: 12px;
}

.progress > div {
  height: 100%;
  background: linear-gradient(90deg,#ff80bd,#ffd0e7);
  width: 0%;
  transition: width .3s ease;
}

/* =========================
   START
========================= */

#startScreen {
  justify-content: center;
}

.logoHeart {
  font-size: 72px;
  animation: float 2.5s ease-in-out infinite;
}

.nameInput {
  width: 100%;
  min-height: 58px;
  border-radius: 16px;
  border: 1px solid rgba(255,255,255,.2);
  background: rgba(255,255,255,.08);
  color: white;
  padding: 0 16px;
  outline: none;
  margin: 12px 0;
}

.nameInput::placeholder {
  color: rgba(255,255,255,.55);
}

/* =========================
   MENU
========================= */

.gameList {
  display: grid;
  grid-template-columns: 1fr;
  gap: 9px;
}

.gameButton {
  background: rgba(255,255,255,.07);
  color: white;
  text-align: left;
  border: 1px solid rgba(255,255,255,.1);
}

.gameButton.locked {
  opacity: .38;
}

.gameButton.completed {
  border-color: rgba(255,140,195,.55);
}

.gameNumber {
  font-size: 12px;
  opacity: .65;
}

.gameName {
  font-weight: 800;
  font-size: 16px;
}

.menuActions {
  margin-top: 15px;
}

/* =========================
   GAME AREA
========================= */

.gameArea {
  width: min(760px, 100%);
  flex: 1;
  display: flex;
  flex-direction: column;
}

.gamePanel {
  flex: 1;
  position: relative;
  overflow: hidden;
}

.gameDescription {
  text-align: center;
  opacity: .82;
}

.scoreBig {
  text-align: center;
  font-size: 32px;
  font-weight: 900;
  margin: 8px;
}

.message {
  text-align: center;
  min-height: 28px;
  margin: 8px 0;
  font-weight: 700;
}

.gameControls {
  margin-top: auto;
  padding-top: 12px;
}

/* =========================
   GAME 1 HEART CATCHER
========================= */

#heartGame {
  position: relative;
  height: min(58vh, 560px);
  min-height: 360px;
  background:
    linear-gradient(rgba(35,8,32,.3), rgba(5,4,15,.65)),
    radial-gradient(circle at 50% 20%, #61204f, #160b1d 70%);
  border-radius: 22px;
  overflow: hidden;
  border: 1px solid rgba(255,255,255,.1);
  touch-action: none;
}

.fallingHeart {
  position: absolute;
  top: -50px;
  font-size: 32px;
  width: 54px;
  height: 54px;
  display: flex;
  align-items: center;
  justify-content: center;
  user-select: none;
  pointer-events: none;
  filter: drop-shadow(0 0 8px rgba(255,100,180,.55));
}

.catchBasket {
  position: absolute;
  bottom: 16px;
  left: 50%;
  transform: translateX(-50%);
  width: 120px;
  height: 70px;
  border-radius: 35px 35px 18px 18px;
  background: rgba(255,110,178,.35);
  border: 3px solid #ffb1d5;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 38px;
  pointer-events: none;
}

.moveButtons {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin-top: 12px;
}

.moveButtons button {
  height: 70px;
  border-radius: 20px;
  background: rgba(255,125,188,.2);
  border: 2px solid rgba(255,177,218,.4);
  color: white;
  font-size: 34px;
  font-weight: 900;
  touch-action: none;
}

/* =========================
   MEMORY
========================= */

.memoryGrid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 9px;
  max-width: 500px;
  margin: 20px auto;
}

.memoryCard {
  aspect-ratio: 1;
  border-radius: 15px;
  background: #441536;
  color: transparent;
  border: 2px solid rgba(255,255,255,.1);
  font-size: 27px;
}

.memoryCard.flipped,
.memoryCard.matched {
  background: #a74279;
  color: white;
}

.memoryCard.matched {
  opacity: .6;
}

/* =========================
   QUIZ
========================= */

.quizQuestion {
  font-size: clamp(20px, 5vw, 30px);
  font-weight: 800;
  text-align: center;
  margin: 25px 0;
}

.timer {
  text-align: center;
  font-size: 28px;
  font-weight: 900;
  margin: 10px;
}

.options {
  display: grid;
  gap: 10px;
}

.option {
  margin-top: 0;
  text-align: left;
  background: rgba(255,255,255,.08);
  color: white;
  border: 1px solid rgba(255,255,255,.13);
}

.option.correct {
  background: rgba(63,185,115,.35);
}

.option.wrong {
  background: rgba(205,52,88,.35);
}

/* =========================
   SIMPLE GAMES
========================= */

.bigChoice {
  display: grid;
  gap: 12px;
  margin-top: 20px;
}

.choiceCard {
  padding: 20px;
  border-radius: 18px;
  background: rgba(255,255,255,.07);
  border: 1px solid rgba(255,255,255,.12);
  text-align: center;
  font-size: 20px;
  font-weight: 800;
}

.choiceCard:active {
  transform: scale(.97);
}

.luckNumber {
  font-size: 72px;
  text-align: center;
  font-weight: 900;
  margin: 25px 0;
}

/* =========================
   SLOTS
========================= */

.slotMachine {
  max-width: 500px;
  margin: auto;
  text-align: center;
}

.slotReels {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 8px;
  margin: 20px 0;
}

.reel {
  min-height: 90px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #140b16;
  border: 3px solid #a6537f;
  border-radius: 16px;
  font-size: 45px;
}

/* =========================
   RACE
========================= */

.raceTrack {
  height: 280px;
  position: relative;
  background:
    repeating-linear-gradient(
      to bottom,
      rgba(255,255,255,.04) 0px,
      rgba(255,255,255,.04) 44px,
      rgba(255,255,255,.08) 45px
    );
  border-radius: 18px;
  overflow: hidden;
}

.racer {
  position: absolute;
  left: 5px;
  font-size: 35px;
  transition: left .15s linear;
}

.finish {
  position: absolute;
  right: 5px;
  top: 0;
  bottom: 0;
  width: 8px;
  background: white;
}

/* =========================
   WORD FIND
========================= */

.wordGrid {
  display: grid;
  grid-template-columns: repeat(8, 1fr);
  max-width: 560px;
  margin: 15px auto;
  gap: 2px;
}

.letter {
  aspect-ratio: 1;
  border-radius: 5px;
  background: rgba(255,255,255,.08);
  color: white;
  font-weight: 800;
  font-size: clamp(12px, 3.5vw, 21px);
}

.letter.selected {
  background: #e45b9b;
}

.wordList {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 7px;
}

.wordTag {
  padding: 6px 10px;
  border-radius: 999px;
  background: rgba(255,255,255,.08);
}

.wordTag.found {
  text-decoration: line-through;
  opacity: .45;
}

/* =========================
   DRAW
========================= */

#drawingCanvas {
  width: 100%;
  max-width: 600px;
  height: 430px;
  display: block;
  margin: 15px auto;
  background: #fff9fc;
  border-radius: 18px;
  touch-action: none;
}

/* =========================
   DERBY
========================= */

.derbyTrack {
  position: relative;
  height: 330px;
  background:
    repeating-linear-gradient(
      to bottom,
      rgba(255,255,255,.04) 0,
      rgba(255,255,255,.04) 59px,
      rgba(255,255,255,.09) 60px
    );
  border-radius: 18px;
  overflow: hidden;
}

.horse {
  position: absolute;
  left: 5px;
  font-size: 32px;
  transition: left .12s linear;
}

.derbyFinish {
  position: absolute;
  right: 0;
  top: 0;
  bottom: 0;
  width: 10px;
  background: repeating-linear-gradient(
    to bottom,
    white 0,
    white 15px,
    #222 15px,
    #222 30px
  );
}

/* =========================
   END
========================= */

.endCard {
  text-align: center;
}

.bigHeart {
  font-size: 90px;
  animation: pulse 1.3s infinite;
}

.unlock {
  padding: 20px;
  border-radius: 20px;
  background: rgba(255,125,188,.14);
  border: 1px solid rgba(255,125,188,.4);
  margin-top: 15px;
}

@keyframes pulse {
  50% { transform: scale(1.12); }
}

@keyframes float {
  50% { transform: translateY(-12px); }
}

@media (min-width: 650px) {
  .gameList {
    grid-template-columns: 1fr 1fr;
  }
}

@media (max-height: 650px) {
  .screen {
    padding-top: 12px;
  }

  #heartGame {
    min-height: 300px;
    height: 48vh;
  }
}
</style>
</head>

<body>

<div id="app">

  <div class="musicBox">
    <button id="musicButton" onclick="toggleMusic()">♫</button>
    <button onclick="changeVolume()">🔊</button>
  </div>

  <!-- START -->
  <section id="startScreen" class="screen">
    <div class="card">
      <div class="logoHeart">💗</div>
      <h1>Lulu Express</h1>
      <p class="subtitle">
        A little journey made especially for Liliana ♡
      </p>

      <input
        id="playerName"
        class="nameInput"
        maxlength="30"
        placeholder="Enter your name"
        autocomplete="off"
      >

      <button class="primary" onclick="startJourney()">
        Start the Journey ♡
      </button>

      <button class="secondary" onclick="showHowTo()">
        How to Play
      </button>
    </div>
  </section>

  <!-- MENU -->
  <section id="menuScreen" class="screen hidden">
    <div class="topbar">
      <div class="stat">Player: <span id="nameDisplay"></span></div>
      <div class="stat">⭐ Score: <span id="scoreDisplay">0</span></div>
      <div class="stat">🪙 Tokens: <span id="tokenDisplay">0</span></div>
    </div>

    <div class="card">
      <h2>Lulu Express</h2>
      <p class="subtitle">
        Complete each challenge to unlock the next part of the journey.
      </p>

      <div class="progress">
        <div id="journeyProgress"></div>
      </div>

      <div id="gameList" class="gameList"></div>

      <div class="menuActions">
        <button class="secondary" onclick="resetGame()">
          Reset Lulu Express
        </button>
      </div>
    </div>
  </section>

  <!-- GAME -->
  <section id="gameScreen" class="screen hidden">
    <div class="topbar">
      <div class="stat">Game <span id="currentGameNumber"></span>/23</div>
      <div class="stat">⭐ <span id="gameScore">0</span></div>
      <div class="stat">🪙 <span id="gameTokens">0</span></div>
    </div>

    <div class="progress">
      <div id="gameProgress"></div>
    </div>

    <div id="gameArea" class="gameArea"></div>
  </section>

</div>

<script>
/* ============================================================
   LULU EXPRESS
   FULL 23 GAME VERSION
============================================================ */

/* -------------------------
   STATE
------------------------- */

const TOTAL_GAMES = 23;

let playerName = "";
let score = 0;
let tokens = 0;
let currentGame = 0;
let unlocked = 1;
let completed = {};

let quizTimer = null;
let gameTimer = null;
let active = false;

let musicOn = false;
let volume = 0.08;
let audioCtx = null;
let musicInterval = null;

let derbyState = null;
let finalState = null;

let wordState = {
  selected: [],
  found: []
};

let drawingStarted = false;

/* -------------------------
   GAME NAMES
------------------------- */

const gameNames = [
  "Broken Hearts",
  "Memory Vault",
  "Pressure Quiz",
  "High Roller",
  "Mind Games",
  "Bluff",
  "Survival",
  "Admirer Race",
  "Heartbreak Chamber",
  "Boxing",
  "Perfect Match",
  "Liliana Quiz",
  "Reaction Gauntlet",
  "Heart Hunt",
  "Love Lock",
  "Cupid Shootout",
  "Countdown",
  "Ultimate Gamble",
  "Last Stand",
  "Word Find",
  "Draw a Sunflower",
  "Lulu Derby",
  "Final Challenge"
];

/* -------------------------
   LILIANA DATA
------------------------- */

const lilianaFacts = [
  {
    q:"What is Liliana's favourite colour?",
    a:["Baby pink","Baby blue","Burgundy","Purple"],
    c:0
  },
  {
    q:"What flower is associated with Liliana?",
    a:["Sunflower","Tulip","Lily","Daisy"],
    c:0
  },
  {
    q:"What animal does Liliana like?",
    a:["Dolphins","Penguins","Otters","Koalas"],
    c:0
  },
  {
    q:"What is Liliana's favourite number?",
    a:["3","7","13","22"],
    c:0
  },
  {
    q:"What is Liliana's favourite movie?",
    a:["Me Before You","Titanic","The Notebook","Frozen"],
    c:0
  },
  {
    q:"What subject did Liliana study at university?",
    a:["Psychology","Law","Medicine","Art"],
    c:0
  },
  {
    q:"How many nieces does Liliana have?",
    a:["1","2","3","4"],
    c:0
  },
  {
    q:"How many nephews does Liliana have?",
    a:["2","3","4","5"],
    c:2
  },
  {
    q:"How many siblings does Liliana have?",
    a:["3","4","5","6"],
    c:2
  },
  {
    q:"What is Liliana's star sign?",
    a:["Leo","Cancer","Virgo","Gemini"],
    c:0
  },
  {
    q:"What is Liliana afraid of?",
    a:["Drowning","Heights","Thunder","Spiders"],
    c:0
  },
  {
    q:"What kind of person is Liliana?",
    a:["Sweet and caring","Cold and distant","Quiet and serious","Strict"],
    c:0
  },
  {
    q:"What does Liliana want someday?",
    a:["To be a mum","To become famous","To live alone","To move to space"],
    c:0
  },
  {
    q:"What colour are Liliana's eyes?",
    a:["Green","Blue","Brown","Hazel"],
    c:0
  },
  {
    q:"How many piercings does Liliana have?",
    a:["2","3","4","5"],
    c:2
  },
  {
    q:"What are Liliana's dogs called?",
    a:["Aayla and Arlo","Luna and Milo","Bella and Max","Ayla and Leo"],
    c:0
  }
];

/* ============================================================
   50 UNIQUE FINAL CHALLENGE QUESTIONS
   NO TATTOO QUESTION
============================================================ */

const finalQuestions = [
  ["What is Liliana's favourite colour?","Baby pink"],
  ["What is Liliana's favourite number?","3"],
  ["What animal does Liliana love?","Dolphins"],
  ["What flower does Liliana like?","Sunflowers"],
  ["What other flower is associated with Liliana?","Roses"],
  ["What is Liliana's favourite movie?","Me Before You"],
  ["What did Liliana study at university?","Psychology"],
  ["How many nieces does Liliana have?","1"],
  ["How many nephews does Liliana have?","4"],
  ["How many siblings does Liliana have?","5"],
  ["What is Liliana's star sign?","Leo"],
  ["What is Liliana afraid of?","Drowning"],
  ["What are Liliana's dogs called?","Aayla and Arlo"],
  ["What colour are Liliana's eyes?","Green"],
  ["How many piercings does Liliana have?","4"],
  ["What does Liliana want to be someday?","A mum"],
  ["What kind of music does Liliana enjoy?","Sad songs"],
  ["What type of writing does Liliana enjoy?","Poetry"],
  ["What type of games does Liliana enjoy?","Poker"],
  ["What kind of slot game is associated with Liliana's casino?","Buffalo"],
  ["What kind of place inspired Lulu Express?","A casino"],
  ["How long have Bree and Liliana been best friends?","6 years"],
  ["What number is connected to the friendship vault?","060722"],
  ["What does the number 6 represent?","Years of friendship"],
  ["What does 07 represent in the vault code?","July"],
  ["What does 22 represent in the vault code?","Liliana's birthday"],
  ["What type of animal appears in Liliana's website theme?","Dolphin"],
  ["What colour should the casino background feel like?","Dark baby pink"],
  ["What is Liliana described as?","Sweet and caring"],
  ["What personality trait does Liliana have?","Charismatic"],
  ["What is Liliana known for romantically?","Being flirtatious"],
  ["What kind of family does Liliana hope to have?","A family with children"],
  ["What gender does Liliana imagine for a future baby?","Girl"],
  ["What does Liliana enjoy alongside sad songs?","Poetry"],
  ["What game can appear in the casino?","Gin rummy"],
  ["What can the lucky wheel award?","Tokens"],
  ["What can tokens be used for in the casino?","Game rewards"],
  ["What happens after completing a game?","The next game unlocks"],
  ["What is the final challenge?","50 questions about Liliana"],
  ["How many questions are in the final challenge?","50"],
  ["How many trivia questions are in Lulu Derby?","100"],
  ["Which game comes immediately before the Final Challenge?","Lulu Derby"],
  ["What game number is Lulu Derby?","22"],
  ["What game number is the Final Challenge?","23"],
  ["What score unlocks the private call?","More than 3000"],
  ["Does exactly 3000 unlock the private call?","No"],
  ["What score is the first qualifying score?","3001"],
  ["What should the player do if they want the next challenge?","Complete the current game"],
  ["What is the purpose of Lulu Express?","To celebrate Liliana"],
  ["Who is Lulu Express made for?","Liliana"]
];

/* ============================================================
   100 DERBY TRIVIA QUESTIONS
============================================================ */

const derbyQuestions = [
["What is the capital of New Zealand?","Wellington"],
["What is the capital of Australia?","Canberra"],
["How many days are in a leap year?","366"],
["What planet is known as the Red Planet?","Mars"],
["How many sides does a triangle have?","3"],
["What is the largest ocean?","Pacific Ocean"],
["How many continents are there?","7"],
["What gas do humans need to breathe?","Oxygen"],
["How many hours are in a day?","24"],
["What is 10 x 10?","100"],
["What is the fastest land animal?","Cheetah"],
["What is the largest mammal?","Blue whale"],
["What is the capital of France?","Paris"],
["What colour is a ruby?","Red"],
["How many legs does a spider have?","8"],
["What is H2O commonly called?","Water"],
["Which animal is known as man's best friend?","Dog"],
["What is the opposite of hot?","Cold"],
["How many months are in a year?","12"],
["Which bird cannot fly and is strongly associated with New Zealand?","Kiwi"],
["What is the capital of Japan?","Tokyo"],
["How many wheels does a bicycle have?","2"],
["Which planet is closest to the Sun?","Mercury"],
["What is 5 + 7?","12"],
["What is the largest planet?","Jupiter"],
["Which animal has a trunk?","Elephant"],
["What do bees make?","Honey"],
["What is the freezing point of water in Celsius?","0°C"],
["How many colours are traditionally in a rainbow?","7"],
["Which season follows winter?","Spring"],
["What is the capital of Italy?","Rome"],
["How many fingers are on one hand?","5"],
["Which ocean is between Africa and Australia?","Indian Ocean"],
["What is the opposite of night?","Day"],
["Which fruit is traditionally yellow and curved?","Banana"],
["How many letters are in the English alphabet?","26"],
["What is the capital of Canada?","Ottawa"],
["What animal is famous for black and white stripes?","Zebra"],
["What is 100 divided by 10?","10"],
["Which planet is famous for its rings?","Saturn"],
["What do caterpillars become?","Butterflies"],
["What is the capital of Spain?","Madrid"],
["How many sides does a square have?","4"],
["Which animal is famous for carrying its baby in a pouch?","Kangaroo"],
["What is the largest desert in the world?","Antarctica"],
["What colour do you get by mixing blue and yellow?","Green"],
["What is the capital of Greece?","Athens"],
["Which organ pumps blood around the body?","Heart"],
["How many minutes are in an hour?","60"],
["What is the capital of the United Kingdom?","London"],
["Which animal is known for its long neck?","Giraffe"],
["What is 9 x 9?","81"],
["What planet do we live on?","Earth"],
["What is the opposite of up?","Down"],
["How many sides does a pentagon have?","5"],
["Which animal is known for saying 'meow'?","Cat"],
["What is the capital of Ireland?","Dublin"],
["Which metal is commonly associated with being yellow and valuable?","Gold"],
["How many seconds are in a minute?","60"],
["Which animal is known for its shell and slow movement?","Turtle"],
["What is 50 + 50?","100"],
["Which planet is known for its beautiful blue colour?","Neptune"],
["What is the capital of China?","Beijing"],
["Which animal is called the king of the jungle?","Lion"],
["What is the opposite of left?","Right"],
["How many sides does a hexagon have?","6"],
["Which fruit is often associated with keeping doctors away?","Apple"],
["What is the capital of Germany?","Berlin"],
["Which animal produces milk commonly consumed by humans?","Cow"],
["What is 12 x 2?","24"],
["Which star is at the centre of our solar system?","The Sun"],
["What is the capital of Mexico?","Mexico City"],
["What is the opposite of big?","Small"],
["How many planets are in our solar system?","8"],
["Which animal is famous for its spots and fast running?","Cheetah"],
["What is 20 + 30?","50"],
["What is the capital of Brazil?","Brasília"],
["Which animal can change colour and has a long tongue?","Chameleon"],
["What is the capital of Norway?","Oslo"],
["What is 7 x 7?","49"],
["Which animal is famous for building dams?","Beaver"],
["What is the capital of South Korea?","Seoul"],
["Which fruit is often red or green and grows on trees?","Apple"],
["What is the opposite of old?","Young"],
["Which animal is famous for its black and white fur and bamboo diet?","Panda"],
["What is the capital of Sweden?","Stockholm"],
["What is 15 - 5?","10"],
["Which animal is famous for hopping?","Kangaroo"],
["What is the capital of Thailand?","Bangkok"],
["Which planet is famous for its Great Red Spot?","Jupiter"],
["What is the capital of Portugal?","Lisbon"],
["Which animal is known for its mane?","Lion"],
["What is 8 x 8?","64"],
["What is the capital of Egypt?","Cairo"],
["Which animal is known for producing pearls?","Oyster"],
["What is the capital of Iceland?","Reykjavík"],
["Which animal is famous for its ability to fly backwards?","Hummingbird"],
["What is 100 - 25?","75"],
["What is the capital of Argentina?","Buenos Aires"],
["Which animal is known for laughing-like sounds?","Hyena"],
["What is the capital of Fiji?","Suva"],
["Which animal is famous for its black and white colouring and lives in the Arctic?","Polar bear"]
];

/* ============================================================
   HELPERS
============================================================ */

function saveState() {
  localStorage.setItem("luluExpressState", JSON.stringify({
    playerName,
    score,
    tokens,
    unlocked,
    completed,
    derbyState,
    finalState,
    wordState,
    drawingStarted
  }));
}

function loadState() {
  const raw = localStorage.getItem("luluExpressState");
  if (!raw) return;

  try {
    const s = JSON.parse(raw);

    playerName = s.playerName || "";
    score = Number(s.score) || 0;
    tokens = Number(s.tokens) || 0;
    unlocked = Number(s.unlocked) || 1;
    completed = s.completed || {};
    derbyState = s.derbyState || null;
    finalState = s.finalState || null;
    wordState = s.wordState || {selected:[],found:[]};
    drawingStarted = !!s.drawingStarted;
  } catch(e) {
    localStorage.removeItem("luluExpressState");
  }
}

function shuffle(array) {
  const a = [...array];

  for (let i = a.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [a[i], a[j]] = [a[j], a[i]];
  }

  return a;
}

function addScore(points) {
  score += points;
  if (score < 0) score = 0;
  updateStats();
  saveState();
}

function addTokens(amount) {
  tokens += amount;
  if (tokens < 0) tokens = 0;
  updateStats();
  saveState();
}

function updateStats() {
  document.getElementById("scoreDisplay").textContent = score;
  document.getElementById("tokenDisplay").textContent = tokens;
  document.getElementById("gameScore").textContent = score;
  document.getElementById("gameTokens").textContent = tokens;
}

function clearTimers() {
  if (quizTimer) {
    clearInterval(quizTimer);
    quizTimer = null;
  }

  if (gameTimer) {
    clearInterval(gameTimer);
    gameTimer = null;
  }

  active = false;
}

function escapeHTML(str) {
  return String(str)
    .replaceAll("&","&amp;")
    .replaceAll("<","&lt;")
    .replaceAll(">","&gt;")
    .replaceAll('"',"&quot;")
    .replaceAll("'","&#039;");
}

/* ============================================================
   START / MENU
============================================================ */

function startJourney() {
  const input = document.getElementById("playerName");
  const entered = input.value.trim();

  if (!entered) {
    input.focus();
    input.placeholder = "Please enter your name ♡";
    return;
  }

  playerName = entered;

  if (!unlocked || unlocked < 1) {
    unlocked = 1;
  }

  saveState();
  showMenu();
}

function showHowTo() {
  alert(
    "Welcome to Lulu Express! ♡\\n\\n" +
    "Enter your name, then complete each game in order. " +
    "Passing a game unlocks the next one.\\n\\n" +
    "You earn points and tokens as you play. " +
    "Game 22 is Lulu Derby and Game 23 is the Final Challenge.\\n\\n" +
    "Score MORE than 3000 points to unlock the private call reward."
  );
}

function showMenu() {
  clearTimers();

  document.getElementById("startScreen").classList.add("hidden");
  document.getElementById("gameScreen").classList.add("hidden");
  document.getElementById("menuScreen").classList.remove("hidden");

  document.getElementById("nameDisplay").textContent = playerName;
  updateStats();
  renderMenu();
}

function renderMenu() {
  const list = document.getElementById("gameList");
  list.innerHTML = "";

  for (let i = 1; i <= TOTAL_GAMES; i++) {
    const button = document.createElement("button");
    button.className = "gameButton";

    if (i > unlocked) {
      button.classList.add("locked");
      button.disabled = true;
    }

    if (completed[i]) {
      button.classList.add("completed");
    }

    button.innerHTML =
      `<span class="gameNumber">GAME ${i}</span><br>` +
      `<span class="gameName">${gameNames[i-1]}</span>` +
      `${completed[i] ? " ✓" : i > unlocked ? " 🔒" : ""}`;

    if (i <= unlocked) {
      button.onclick = () => launchGame(i);
    }

    list.appendChild(button);
  }

  const percentage =
    Math.min(100, ((unlocked - 1) / TOTAL_GAMES) * 100);

  document.getElementById("journeyProgress").style.width =
    percentage + "%";
}

/* ============================================================
   LAUNCH / COMPLETE
============================================================ */

function launchGame(number) {
  if (number > unlocked) return;

  clearTimers();

  currentGame = number;

  document.getElementById("menuScreen").classList.add("hidden");
  document.getElementById("gameScreen").classList.remove("hidden");

  document.getElementById("currentGameNumber").textContent = number;
  document.getElementById("gameProgress").style.width =
    ((number - 1) / TOTAL_GAMES * 100) + "%";

  const area = document.getElementById("gameArea");
  area.innerHTML = "";

  const builders = {
    1: game1,
    2: game2,
    3: game3,
    4: game4,
    5: game5,
    6: game6,
    7: game7,
    8: game8,
    9: game9,
    10: game10,
    11: game11,
    12: game12,
    13: game13,
    14: game14,
    15: game15,
    16: game16,
    17: game17,
    18: game18,
    19: game19,
    20: game20,
    21: game21,
    22: game22,
    23: game23
  };

  builders[number]();
}

function finishGame(points, tokenReward = 0, message = "Challenge complete! ♡") {
  clearTimers();

  addScore(points);
  addTokens(tokenReward);

  completed[currentGame] = true;

  if (currentGame === unlocked && unlocked < TOTAL_GAMES) {
    unlocked++;
  }

  saveState();

  const next = currentGame < TOTAL_GAMES
    ? `<button class="primary" onclick="launchGame(${currentGame + 1})">
         Next Game →
       </button>`
    : "";

  document.getElementById("gameArea").innerHTML = `
    <div class="card endCard">
      <div class="bigHeart">💗</div>
      <h2>Completed!</h2>
      <p>${message}</p>
      <p>+${points} points</p>
      ${tokenReward ? `<p>+${tokenReward} tokens</p>` : ""}
      ${next}
      <button class="secondary" onclick="showMenu()">Game Menu</button>
    </div>
  `;

  document.getElementById("gameProgress").style.width =
    (currentGame / TOTAL_GAMES * 100) + "%";
}

/* ============================================================
   GAME 1
   MUCH EASIER MOBILE HEART CATCHER
============================================================ */

function game1() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>💗 Broken Hearts</h2>
      <p class="gameDescription">
        Catch the falling hearts! This version is deliberately
        gentle and phone-friendly.
      </p>

      <div class="scoreBig">
        Hearts: <span id="heartScore">0</span>/8
      </div>

      <div class="message" id="heartMessage">
        Move left and right and catch 8 hearts!
      </div>

      <div id="heartGame">
        <div id="catchBasket" class="catchBasket">💗</div>
      </div>

      <div class="moveButtons">
        <button id="leftButton">◀</button>
        <button id="rightButton">▶</button>
      </div>

      <button class="secondary" onclick="showMenu()">
        Back to Games
      </button>
    </div>
  `;

  startEasyHeartGame();
}

function startEasyHeartGame() {
  const field = document.getElementById("heartGame");
  const basket = document.getElementById("catchBasket");
  const scoreEl = document.getElementById("heartScore");
  const message = document.getElementById("heartMessage");

  let basketX = 50;
  let caught = 0;
  let missed = 0;
  let running = true;
  let lastTime = performance.now();
  let spawnClock = 0;
  let hearts = [];

  /*
    EASY SETTINGS:
    - only 8 hearts required
    - hearts move slowly
    - basket is wide
    - missed hearts do NOT cost lives
    - more generous collision
    - 45 second timer
    - movement uses large buttons
  */

  const duration = 45000;
  const speed = 55;
  const spawnEvery = 1700;

  function setBasket() {
    const max =
      field.clientWidth -
      basket.offsetWidth -
      8;

    const x =
      (basketX / 100) * max + 4;

    basket.style.left = x + "px";
    basket.style.transform = "none";
  }

  function move(direction) {
    if (!running) return;

    basketX += direction * 7;

    if (basketX < 0) basketX = 0;
    if (basketX > 100) basketX = 100;

    setBasket();
  }

  const left = document.getElementById("leftButton");
  const right = document.getElementById("rightButton");

  left.addEventListener("pointerdown", e => {
    e.preventDefault();
    move(-1);
  });

  right.addEventListener("pointerdown", e => {
    e.preventDefault();
    move(1);
  });

  /*
    Holding the buttons gives slow repeated movement,
    but it is intentionally capped.
  */

  let holdDirection = 0;
  let holdInterval = null;

  function beginHold(dir) {
    holdDirection = dir;
    move(dir);

    clearInterval(holdInterval);

    holdInterval = setInterval(() => {
      if (holdDirection) move(holdDirection);
    }, 100);
  }

  function endHold() {
    holdDirection = 0;
    clearInterval(holdInterval);
  }

  left.addEventListener("pointerdown", () => beginHold(-1));
  right.addEventListener("pointerdown", () => beginHold(1));

  ["pointerup","pointercancel","pointerleave"].forEach(ev => {
    left.addEventListener(ev,endHold);
    right.addEventListener(ev,endHold);
  });

  function spawnHeart() {
    const el = document.createElement("div");
    el.className = "fallingHeart";
    el.textContent = Math.random() > .18 ? "❤️" : "💗";

    /*
      Spawn mostly around the player's general area so
      the game remains forgiving rather than frustrating.
    */

    const target =
      basketX +
      (Math.random() * 34 - 17);

    const x =
      Math.max(
        4,
        Math.min(92, target)
      );

    el.style.left = x + "%";
    field.appendChild(el);

    hearts.push({
      el,
      x: x / 100 * field.clientWidth,
      y: -50
    });
  }

  function loop(now) {
    if (!running) return;

    const dt = Math.min(40, now - lastTime);
    lastTime = now;

    spawnClock += dt;

    if (spawnClock >= spawnEvery) {
      spawnClock = 0;
      spawnHeart();
    }

    const basketRect = basket.getBoundingClientRect();
    const fieldRect = field.getBoundingClientRect();

    hearts.forEach((h, index) => {
      h.y += speed * dt / 1000;
      h.el.style.transform =
        `translateY(${h.y}px)`;

      const heartRect =
        h.el.getBoundingClientRect();

      const overlap =
        heartRect.right > basketRect.left - 18 &&
        heartRect.left < basketRect.right + 18 &&
        heartRect.bottom > basketRect.top - 20 &&
        heartRect.top < basketRect.bottom + 20;

      if (overlap) {
        caught++;

        scoreEl.textContent = caught;

        h.el.remove();
        hearts.splice(index,1);

        if (caught >= 8) {
          running = false;
          clearInterval(holdInterval);
          finishGame(
            250,
            30,
            "You caught all 8 hearts! That was the easy route to the next challenge. 💗"
          );
          return;
        }
      }
      else if (h.y > field.clientHeight + 60) {
        missed++;
        h.el.remove();
        hearts.splice(index,1);
      }
    });

    requestAnimationFrame(loop);
  }

  setBasket();

  /*
    Gentle first heart appears quickly so the player
    understands the controls immediately.
  */
  setTimeout(spawnHeart, 400);

  let start = performance.now();

  function timerCheck(now) {
    if (!running) return;

    if (now - start >= duration) {
      running = false;
      clearInterval(holdInterval);

      if (caught >= 5) {
        finishGame(
          200,
          20,
          "You caught enough hearts to pass! 💗"
        );
      } else {
        document.getElementById("heartMessage").textContent =
          "Almost! Try again. You only need 8 hearts.";
        setTimeout(() => {
          if (currentGame === 1) {
            startEasyHeartGame();
          }
        }, 1200);
      }

      return;
    }

    requestAnimationFrame(timerCheck);
  }

  requestAnimationFrame(loop);
  requestAnimationFrame(timerCheck);
}

/* ============================================================
   GAME 2 MEMORY VAULT
============================================================ */

function game2() {
  const symbols = shuffle([
    "💗","💗",
    "🌸","🌸",
    "🐬","🐬",
    "🌻","🌻",
    "⭐","⭐",
    "🌙","🌙",
    "🦋","🦋",
    "🎀","🎀"
  ]);

  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🔐 Memory Vault</h2>
      <p class="gameDescription">
        Match all the pairs.
      </p>
      <div id="memoryGrid" class="memoryGrid"></div>
      <div id="memoryMessage" class="message">
        Find every pair!
      </div>
      <button class="secondary" onclick="showMenu()">Back</button>
    </div>
  `;

  const grid = document.getElementById("memoryGrid");

  let first = null;
  let second = null;
  let lock = false;
  let matches = 0;

  symbols.forEach((symbol,i) => {
    const card = document.createElement("button");
    card.className = "memoryCard";
    card.textContent = symbol;

    card.onclick = () => {
      if (
        lock ||
        card.classList.contains("flipped") ||
        card.classList.contains("matched")
      ) return;

      card.classList.add("flipped");

      if (!first) {
        first = {card,symbol};
        return;
      }

      second = {card,symbol};
      lock = true;

      if (first.symbol === second.symbol) {
        first.card.classList.add("matched");
        second.card.classList.add("matched");
        matches++;

        first = null;
        second = null;
        lock = false;

        if (matches === 8) {
          finishGame(250,35,"The Memory Vault is open! 🔐");
        }
      } else {
        setTimeout(() => {
          first.card.classList.remove("flipped");
          second.card.classList.remove("flipped");
          first = null;
          second = null;
          lock = false;
        },650);
      }
    };

    grid.appendChild(card);
  });
}

/* ============================================================
   GENERIC QUIZ ENGINE
============================================================ */

function runQuiz(title, questions, points, tokenReward, seconds = 15) {
  let bank = shuffle(questions);
  let index = 0;
  let correct = 0;
  let remaining = seconds;

  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>${title}</h2>
      <div class="timer" id="quizTimer">${remaining}</div>
      <div class="quizQuestion" id="quizQuestion"></div>
      <div id="quizOptions" class="options"></div>
      <div id="quizMessage" class="message"></div>
    </div>
  `;

  function render() {
    if (index >= bank.length) {
      const earned =
        Math.round(points * (correct / bank.length));

      finishGame(
        earned,
        tokenReward,
        `You got ${correct} out of ${bank.length} correct!`
      );
      return;
    }

    clearInterval(quizTimer);
    remaining = seconds;

    document.getElementById("quizTimer").textContent =
      remaining;

    const q = bank[index];

    document.getElementById("quizQuestion").textContent =
      `${index + 1}. ${q.q}`;

    const options = document.getElementById("quizOptions");
    options.innerHTML = "";

    /*
      Answers are shuffled every question.
      The correct answer is never locked to one position.
    */

    const answerObjects =
      q.a.map((answer,original) => ({
        answer,
        correct: original === q.c
      }));

    shuffle(answerObjects).forEach(obj => {
      const button = document.createElement("button");
      button.className = "option";
      button.textContent = obj.answer;

      button.onclick = () => {
        clearInterval(quizTimer);

        [...options.children].forEach(b =>
          b.disabled = true
        );

        if (obj.correct) {
          button.classList.add("correct");
          correct++;
        } else {
          button.classList.add("wrong");
        }

        index++;

        setTimeout(render,450);
      };

      options.appendChild(button);
    });

    quizTimer = setInterval(() => {
      remaining--;

      document.getElementById("quizTimer").textContent =
        remaining;

      if (remaining <= 0) {
        clearInterval(quizTimer);

        [...options.children].forEach(b =>
          b.disabled = true
        );

        index++;
        setTimeout(render,350);
      }
    },1000);
  }

  render();
}

/* ============================================================
   GAME 3 PRESSURE QUIZ
   FIXED TIMER / NO SKIPPING
============================================================ */

function game3() {
  const questions = shuffle([
    {
      q:"What is Liliana's favourite colour?",
      a:["Baby pink","Baby blue","Red","Black"],
      c:0
    },
    {
      q:"What is Liliana's favourite number?",
      a:["3","7","8","22"],
      c:0
    },
    {
      q:"What animal does Liliana like?",
      a:["Dolphins","Otters","Cats","Horses"],
      c:0
    },
    {
      q:"What is Liliana's favourite movie?",
      a:["Me Before You","Frozen","Titanic","Shrek"],
      c:0
    },
    {
      q:"What did Liliana study?",
      a:["Psychology","Medicine","Law","History"],
      c:0
    },
    {
      q:"What is Liliana afraid of?",
      a:["Drowning","Thunder","Knives","Heights"],
      c:0
    },
    {
      q:"What are Liliana's dogs called?",
      a:["Aayla and Arlo","Luna and Leo","Milo and Max","Bella and Arlo"],
      c:0
    }
  ]);

  runQuiz(
    "⏱️ Pressure Quiz",
    questions,
    300,
    40,
    12
  );
}

/* ============================================================
   GAME 4 HIGH ROLLER
============================================================ */

function game4() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🎰 High Roller</h2>
      <p class="gameDescription">
        Pick a number from 1 to 6. Roll the die and beat it!
      </p>
      <div id="highRollNumber" class="luckNumber">?</div>
      <div id="highRollChoices" class="bigChoice"></div>
    </div>
  `;

  const box = document.getElementById("highRollChoices");

  for (let i=1;i<=6;i++) {
    const b = document.createElement("button");
    b.className = "choiceCard";
    b.textContent = `Choose ${i}`;

    b.onclick = () => {
      const roll = Math.floor(Math.random()*6)+1;

      document.getElementById("highRollNumber").textContent =
        "🎲 " + roll;

      setTimeout(() => {
        if (roll >= i) {
          finishGame(220,35,
            `The die landed on ${roll}. You rolled high enough!`
          );
        } else {
          finishGame(100,10,
            `The die landed on ${roll}. You still survive the round!`
          );
        }
      },700);
    };

    box.appendChild(b);
  }
}

/* ============================================================
   GAME 5 MIND GAMES
============================================================ */

function game5() {
  const qs = [
    {
      q:"Which word does NOT belong?",
      a:["Rose","Sunflower","Dolphin","Tulip"],
      c:2
    },
    {
      q:"What comes next? 2, 4, 6, 8...",
      a:["10","11","12","14"],
      c:0
    },
    {
      q:"Which is the odd one out?",
      a:["Pink","Baby pink","Burgundy","Dolphin"],
      c:3
    },
    {
      q:"What comes next? 5, 10, 15...",
      a:["20","21","25","30"],
      c:0
    }
  ];

  runQuiz("🧠 Mind Games",qs,250,30,15);
}

/* ============================================================
   GAME 6 BLUFF
============================================================ */

function game6() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🎭 Bluff</h2>
      <p class="gameDescription">
        One card is the winner. Trust your instincts.
      </p>
      <div id="bluffChoices" class="bigChoice"></div>
    </div>
  `;

  const choices = document.getElementById("bluffChoices");

  const cards = shuffle(["♥️","♥️","♥️","♠️"]);

  cards.forEach((card,i) => {
    const b = document.createElement("button");
    b.className = "choiceCard";
    b.textContent = `Card ${i+1} 🂠`;

    b.onclick = () => {
      b.textContent = card;

      setTimeout(() => {
        if (card === "♥️") {
          finishGame(240,30,"You found a winning heart! ♥️");
        } else {
          finishGame(110,10,"The bluff got you, but you survived!");
        }
      },600);
    };

    choices.appendChild(b);
  });
}

/* ============================================================
   GAME 7 SURVIVAL
============================================================ */

function game7() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🛡️ Survival</h2>
      <p class="gameDescription">
        Pick the safest door.
      </p>
      <div id="survival" class="bigChoice"></div>
    </div>
  `;

  const safe = Math.floor(Math.random()*3);
  const box = document.getElementById("survival");

  ["🌸 Door One","💗 Door Two","🌻 Door Three"]
    .forEach((label,i) => {
      const b = document.createElement("button");
      b.className = "choiceCard";
      b.textContent = label;

      b.onclick = () => {
        if (i === safe) {
          finishGame(230,30,"You found the safe route!");
        } else {
          finishGame(100,10,"That door was risky, but you survived.");
        }
      };

      box.appendChild(b);
    });
}

/* ============================================================
   GAME 8 ADMIRER RACE
============================================================ */

function game8() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>💌 Admirer Race</h2>
      <p class="gameDescription">
        Tap the button 15 times before the admirer reaches the finish!
      </p>

      <div class="raceTrack">
        <div class="racer" id="playerRacer" style="top:30px">💗</div>
        <div class="racer" id="enemyRacer" style="top:150px">💌</div>
        <div class="finish"></div>
      </div>

      <div class="scoreBig">
        <span id="raceCount">0</span>/15
      </div>

      <button class="primary" id="raceTap">
        TAP! 💗
      </button>
    </div>
  `;

  let taps = 0;
  let enemy = 0;

  const button = document.getElementById("raceTap");

  const interval = setInterval(() => {
    enemy += 3;
    document.getElementById("enemyRacer").style.left =
      enemy + "%";

    if (enemy >= 94) {
      clearInterval(interval);
      finishGame(100,10,"The admirer reached the finish first!");
    }
  },500);

  button.onclick = () => {
    taps++;
    document.getElementById("raceCount").textContent = taps;

    document.getElementById("playerRacer").style.left =
      Math.min(94,taps*6) + "%";

    if (taps >= 15) {
      clearInterval(interval);
      finishGame(250,35,"You won the Admirer Race! 💌");
    }
  };
}

/* ============================================================
   GAME 9 HEARTBREAK CHAMBER
============================================================ */

function game9() {
  const qs = [
    {
      q:"Which one represents love?",
      a:["❤️","💀","🧊","⚡"],
      c:0
    },
    {
      q:"Which one represents friendship?",
      a:["🤝","🔥","💣","🌪️"],
      c:0
    },
    {
      q:"Which flower is Liliana associated with?",
      a:["🌻","🌵","🥀","🌿"],
      c:0
    },
    {
      q:"Which animal is associated with Liliana?",
      a:["🐬","🦈","🐊","🦁"],
      c:0
    }
  ];

  runQuiz("💔 Heartbreak Chamber",qs,250,30,15);
}

/* ============================================================
   GAME 10 BOXING
============================================================ */

function game10() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🥊 Boxing</h2>
      <p class="gameDescription">
        Hit the target before it moves!
      </p>

      <div id="boxingArena"
           style="
             height:320px;
             position:relative;
             background:rgba(255,255,255,.05);
             border-radius:20px;
           ">
        <button id="boxingTarget"
          style="
            position:absolute;
            width:75px;
            height:75px;
            border-radius:50%;
            font-size:32px;
            background:#e55a9e;
          ">💗</button>
      </div>

      <div class="scoreBig">
        Hits: <span id="boxingHits">0</span>/8
      </div>
    </div>
  `;

  const arena = document.getElementById("boxingArena");
  const target = document.getElementById("boxingTarget");

  let hits = 0;

  function moveTarget() {
    target.style.left =
      Math.random() *
      Math.max(10,arena.clientWidth-85) + "px";

    target.style.top =
      Math.random() *
      Math.max(10,arena.clientHeight-85) + "px";
  }

  target.onclick = () => {
    hits++;
    document.getElementById("boxingHits").textContent = hits;
    moveTarget();

    if (hits >= 8) {
      finishGame(240,30,"Knockout! 🥊");
    }
  };

  moveTarget();
}

/* ============================================================
   GAME 11 PERFECT MATCH
============================================================ */

function game11() {
  const qs = [
    {
      q:"Which combination fits Liliana best?",
      a:["Baby pink + dolphins","Blue + sharks","Black + wolves","Green + snakes"],
      c:0
    },
    {
      q:"Which flower pairing fits?",
      a:["Sunflowers + roses","Lilies + orchids","Tulips + daisies","Lavender + violets"],
      c:0
    },
    {
      q:"Which activity fits her interests?",
      a:["Poker","Chess only","Golf only","Fishing only"],
      c:0
    },
    {
      q:"Which combination is correct?",
      a:["Psychology + Me Before You","Physics + Avatar","Law + Titanic","Medicine + Shrek"],
      c:0
    }
  ];

  runQuiz("💞 Perfect Match",qs,260,35,15);
}

/* ============================================================
   GAME 12 LILIANA QUIZ
============================================================ */

function game12() {
  runQuiz(
    "🌸 Liliana Quiz",
    shuffle(lilianaFacts).slice(0,10),
    350,
    50,
    15
  );
}

/* ============================================================
   GAME 13 REACTION GAUNTLET
============================================================ */

function game13() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>⚡ Reaction Gauntlet</h2>
      <p class="gameDescription">
        Wait for the heart to appear, then tap it!
      </p>

      <div id="reactionBox"
        style="
          height:300px;
          border-radius:20px;
          background:rgba(255,255,255,.06);
          display:flex;
          align-items:center;
          justify-content:center;
          font-size:70px;
        ">
        WAIT...
      </div>

      <div class="scoreBig">
        Round <span id="reactionRound">0</span>/5
      </div>
    </div>
  `;

  let round = 0;
  let ready = false;
  let timer;

  const box = document.getElementById("reactionBox");

  function next() {
    ready = false;
    box.textContent = "WAIT...";

    const delay = 900 + Math.random()*1600;

    timer = setTimeout(() => {
      ready = true;
      box.textContent = "💗";
    },delay);
  }

  box.onclick = () => {
    if (!ready) return;

    clearTimeout(timer);
    round++;

    document.getElementById("reactionRound").textContent =
      round;

    if (round >= 5) {
      finishGame(280,35,"Lightning-fast reactions! ⚡");
      return;
    }

    next();
  };

  next();
}

/* ============================================================
   GAME 14 HEART HUNT
============================================================ */

function game14() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🔎 Heart Hunt</h2>
      <p class="gameDescription">
        Find the hidden heart 6 times.
      </p>

      <div id="huntArea"
        style="
          position:relative;
          height:380px;
          background:rgba(255,255,255,.05);
          border-radius:20px;
        ">
      </div>

      <div class="scoreBig">
        Found: <span id="huntScore">0</span>/6
      </div>
    </div>
  `;

  const area = document.getElementById("huntArea");
  let found = 0;

  function place() {
    area.innerHTML = "";

    const heart = document.createElement("button");
    heart.textContent = "💗";
    heart.style.position = "absolute";
    heart.style.fontSize = "42px";
    heart.style.background = "transparent";

    heart.style.left =
      Math.random() * 82 + "%";

    heart.style.top =
      Math.random() * 78 + "%";

    heart.onclick = () => {
      found++;

      document.getElementById("huntScore").textContent =
        found;

      if (found >= 6) {
        finishGame(250,30,"You found every hidden heart! 🔎");
      } else {
        place();
      }
    };

    area.appendChild(heart);
  }

  place();
}

/* ============================================================
   GAME 15 LOVE LOCK
============================================================ */

function game15() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🔒 Love Lock</h2>
      <p class="gameDescription">
        Crack the three-number combination.
        Each digit is between 1 and 5.
      </p>

      <div id="lockDisplay"
        class="luckNumber">???</div>

      <div id="lockButtons"></div>
    </div>
  `;

  let answer = [
    1 + Math.floor(Math.random()*5),
    1 + Math.floor(Math.random()*5),
    1 + Math.floor(Math.random()*5)
  ];

  let guess = [];

  function renderButtons() {
    const box = document.getElementById("lockButtons");
    box.innerHTML = "";

    for (let i=1;i<=5;i++) {
      const b = document.createElement("button");
      b.className = "option";
      b.textContent = i;

      b.onclick = () => {
        guess.push(i);

        document.getElementById("lockDisplay").textContent =
          guess.join("");

        if (guess.length === 3) {
          const correct =
            guess.every((n,i) => n === answer[i]);

          if (correct) {
            finishGame(300,40,"The Love Lock opened! 🔓");
          } else {
            guess = [];
            document.getElementById("lockDisplay").textContent =
              "???";
          }
        }
      };

      box.appendChild(b);
    }
  }

  renderButtons();
}

/* ============================================================
   GAME 16 CUPID SHOOTOUT
============================================================ */

function game16() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🏹 Cupid Shootout</h2>
      <p class="gameDescription">
        Hit 7 hearts.
      </p>

      <div id="cupidArena"
        style="
          height:350px;
          position:relative;
          background:rgba(255,255,255,.05);
          border-radius:20px;
          overflow:hidden;
        ">
      </div>

      <div class="scoreBig">
        Hits: <span id="cupidScore">0</span>/7
      </div>
    </div>
  `;

  const arena = document.getElementById("cupidArena");
  let hits = 0;

  function spawn() {
    const h = document.createElement("button");

    h.textContent = "💗";
    h.style.position = "absolute";
    h.style.fontSize = "38px";
    h.style.background = "transparent";
    h.style.left = Math.random()*85 + "%";
    h.style.top = Math.random()*80 + "%";

    h.onclick = () => {
      hits++;
      document.getElementById("cupidScore").textContent = hits;
      h.remove();

      if (hits >= 7) {
        finishGame(260,35,"Cupid hit every target! 🏹");
      } else {
        spawn();
      }
    };

    arena.appendChild(h);
  }

  spawn();
}

/* ============================================================
   GAME 17 COUNTDOWN
============================================================ */

function game17() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>⏳ Countdown</h2>
      <p class="gameDescription">
        Stop the countdown as close to 10 seconds as possible.
      </p>

      <div id="countNumber" class="luckNumber">10.0</div>

      <button id="countButton" class="primary">
        STOP!
      </button>
    </div>
  `;

  let start = performance.now();
  let running = true;

  function loop(now) {
    if (!running) return;

    const elapsed = (now-start)/1000;
    const remaining = Math.max(0,10-elapsed);

    document.getElementById("countNumber").textContent =
      remaining.toFixed(1);

    if (remaining <= 0) {
      running = false;
      finishGame(100,10,"Time ran out!");
      return;
    }

    requestAnimationFrame(loop);
  }

  document.getElementById("countButton").onclick = () => {
    if (!running) return;

    running = false;

    const elapsed = (performance.now()-start)/1000;
    const difference = Math.abs(10-elapsed);

    let points = 100;

    if (difference < .15) points = 350;
    else if (difference < .4) points = 280;
    else if (difference < .8) points = 200;
    else if (difference < 1.5) points = 150;

    finishGame(points,40,
      `You stopped it ${difference.toFixed(2)} seconds from perfect!`
    );
  };

  requestAnimationFrame(loop);
}

/* ============================================================
   GAME 18 ULTIMATE GAMBLE
   STARTING POT 100
============================================================ */

function game18() {
  let pot = 100;
  let round = 1;

  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🎰 Ultimate Gamble</h2>
      <p class="gameDescription">
        Start with a 100 token pot. Keep gambling or cash out.
      </p>

      <div id="gamblePot" class="luckNumber">100</div>

      <div class="bigChoice">
        <button class="choiceCard" id="gamble">
          🎲 Gamble
        </button>

        <button class="choiceCard" id="cash">
          💰 Cash Out
        </button>
      </div>

      <div id="gambleMessage" class="message">
        Round 1
      </div>
    </div>
  `;

  document.getElementById("gamble").onclick = () => {
    const win = Math.random() < .62;

    if (win) {
      pot *= 2;
      round++;

      document.getElementById("gamblePot").textContent =
        pot;

      document.getElementById("gambleMessage").textContent =
        "You doubled the pot!";

      if (pot >= 1600) {
        finishGame(400,80,"You became the Ultimate High Roller!");
      }
    } else {
      pot = Math.max(20,Math.floor(pot/2));

      document.getElementById("gamblePot").textContent =
        pot;

      document.getElementById("gambleMessage").textContent =
        "The gamble went badly, but your pot survived.";
    }
  };

  document.getElementById("cash").onclick = () => {
    finishGame(
      Math.min(450,pot),
      Math.floor(pot/10),
      `You cashed out with ${pot} tokens!`
    );
  };
}

/* ============================================================
   GAME 19 LAST STAND
============================================================ */

function game19() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🛡️ Last Stand</h2>
      <p class="gameDescription">
        Survive five rounds. Pick the correct defence.
      </p>

      <div class="scoreBig">
        Round <span id="standRound">0</span>/5
      </div>

      <div id="standChoices" class="bigChoice"></div>
    </div>
  `;

  let round = 0;

  function nextRound() {
    const box = document.getElementById("standChoices");
    box.innerHTML = "";

    const correct = Math.floor(Math.random()*3);

    ["❤️ Love","🧠 Mind","💪 Courage"].forEach((text,i) => {
      const b = document.createElement("button");
      b.className = "choiceCard";
      b.textContent = text;

      b.onclick = () => {
        if (i === correct) {
          round++;
          document.getElementById("standRound").textContent =
            round;

          if (round >= 5) {
            finishGame(300,40,"You survived the Last Stand! 🛡️");
          } else {
            nextRound();
          }
        } else {
          finishGame(100,10,"You survived, but the stand was broken.");
        }
      };

      box.appendChild(b);
    });
  }

  nextRound();
}

/* ============================================================
   GAME 20 WORD FIND
   25 LILIANA WORDS
============================================================ */

const wordFindWords = [
  "LILIANA",
  "DOLPHIN",
  "SUNFLOWER",
  "ROSES",
  "PINK",
  "PSYCHOLOGY",
  "POETRY",
  "MUSIC",
  "POKER",
  "CASINO",
  "FAMILY",
  "CHILDREN",
  "MUMMY",
  "AAYLA",
  "ARLO",
  "LEO",
  "MEXICO",
  "FRIENDSHIP",
  "SIXYEARS",
  "LOVE",
  "HEART",
  "BABY",
  "GIRL",
  "CHARISMA",
  "LULU"
];

function game20() {
  wordState = {
    selected: [],
    found: []
  };

  const size = 8;
  const letters = Array(size*size).fill("");

  /*
    Simple guaranteed placements.
    The remaining cells are random letters.
  */

  const placements = [
    [0,"LILIANA",1],
    [8,"DOLPHIN",1],
    [16,"SUNFLOWER",1],
    [24,"ROSES",1],
    [32,"PSYCHOLOGY",1],
    [40,"POETRY",1],
    [48,"POKER",1],
    [56,"CASINO",1]
  ];

  placements.forEach(([start,word,dir]) => {
    for (let i=0;i<word.length;i++) {
      if (start+i < letters.length) {
        letters[start+i] = word[i];
      }
    }
  });

  const alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";

  for (let i=0;i<letters.length;i++) {
    if (!letters[i]) {
      letters[i] =
        alphabet[Math.floor(Math.random()*alphabet.length)];
    }
  }

  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🔤 Word Find</h2>
      <p class="gameDescription">
        Find the hidden words related to Liliana.
        Tap the letters in order.
      </p>

      <div id="wordGrid" class="wordGrid"></div>

      <div class="wordList" id="wordList"></div>

      <div id="wordMessage" class="message">
        Find at least 6 words to pass.
      </div>

      <button class="secondary" onclick="clearWordSelection()">
        Clear Selection
      </button>
    </div>
  `;

  const grid = document.getElementById("wordGrid");

  letters.forEach((letter,i) => {
    const b = document.createElement("button");
    b.className = "letter";
    b.textContent = letter;

    b.onclick = () => selectWordLetter(i,b);

    grid.appendChild(b);
  });

  renderWordList();
}

function selectWordLetter(index,button) {
  if (wordState.selected.includes(index)) return;

  wordState.selected.push(index);
  button.classList.add("selected");

  const current =
    wordState.selected
      .map(i => document.querySelectorAll(".letter")[i].textContent)
      .join("");

  const exact = wordFindWords.find(
    w => w === current
  );

  if (exact && !wordState.found.includes(exact)) {
    wordState.found.push(exact);

    wordState.selected.forEach(i =>
      document.querySelectorAll(".letter")[i]
        .classList.remove("selected")
    );

    wordState.selected = [];

    renderWordList();

    if (wordState.found.length >= 6) {
      finishGame(
        300,
        45,
        "You found enough Liliana words to unlock the next challenge! 🔤"
      );
    }
  }
}

function clearWordSelection() {
  document.querySelectorAll(".letter").forEach(b =>
    b.classList.remove("selected")
  );

  wordState.selected = [];
}

function renderWordList() {
  const list = document.getElementById("wordList");
  if (!list) return;

  list.innerHTML = "";

  wordFindWords.forEach(word => {
    const tag = document.createElement("div");
    tag.className = "wordTag";

    if (wordState.found.includes(word)) {
      tag.classList.add("found");
    }

    tag.textContent = word;
    list.appendChild(tag);
  });
}

/* ============================================================
   GAME 21 DRAW SUNFLOWER
============================================================ */

function game21() {
  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🌻 Draw a Sunflower</h2>
      <p class="gameDescription">
        Draw a sunflower for Liliana.
      </p>

      <canvas id="drawingCanvas"
              width="900"
              height="650"></canvas>

      <button class="primary" onclick="finishDrawing()">
        🌻 Finish Drawing
      </button>

      <button class="secondary" onclick="clearDrawing()">
        Clear Drawing
      </button>
    </div>
  `;

  setupCanvas();
}

function setupCanvas() {
  const canvas = document.getElementById("drawingCanvas");
  if (!canvas) return;

  const ctx = canvas.getContext("2d");

  ctx.fillStyle = "#fff9fc";
  ctx.fillRect(0,0,canvas.width,canvas.height);

  ctx.lineWidth = 10;
  ctx.lineCap = "round";
  ctx.strokeStyle = "#542040";

  let drawing = false;

  function position(e) {
    const rect = canvas.getBoundingClientRect();

    let clientX;
    let clientY;

    if (e.touches && e.touches[0]) {
      clientX = e.touches[0].clientX;
      clientY = e.touches[0].clientY;
    } else {
      clientX = e.clientX;
      clientY = e.clientY;
    }

    return {
      x:(clientX-rect.left) * canvas.width/rect.width,
      y:(clientY-rect.top) * canvas.height/rect.height
    };
  }

  function start(e) {
    e.preventDefault();
    drawing = true;
    drawingStarted = true;

    const p = position(e);
    ctx.beginPath();
    ctx.moveTo(p.x,p.y);
  }

  function draw(e) {
    if (!drawing) return;
    e.preventDefault();

    const p = position(e);
    ctx.lineTo(p.x,p.y);
    ctx.stroke();
  }

  function stop(e) {
    if (e) e.preventDefault();
    drawing = false;
    ctx.closePath();
  }

  canvas.addEventListener("pointerdown",start);
  canvas.addEventListener("pointermove",draw);
  canvas.addEventListener("pointerup",stop);
  canvas.addEventListener("pointercancel",stop);
  canvas.addEventListener("pointerleave",stop);
}

function clearDrawing() {
  const canvas = document.getElementById("drawingCanvas");
  if (!canvas) return;

  const ctx = canvas.getContext("2d");

  ctx.fillStyle = "#fff9fc";
  ctx.fillRect(0,0,canvas.width,canvas.height);

  drawingStarted = false;
  saveState();
}

function finishDrawing() {
  if (!drawingStarted) {
    alert("Draw something first 🌻");
    return;
  }

  finishGame(
    350,
    50,
    "Your sunflower is ready for Liliana. 🌻"
  );
}

/* ============================================================
   GAME 22 LULU DERBY
   100 RANDOM TRIVIA QUESTIONS
============================================================ */

function game22() {
  let questions = shuffle(derbyQuestions);

  let qIndex = 0;
  let correct = 0;
  let racer = 0;
  let playerHorse = 0;
  let computerHorse = 0;

  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>🏇 Lulu Derby</h2>

      <p class="gameDescription">
        Answer 10 random trivia questions to power your horse.
        There are 100 unique questions in the full Derby bank.
      </p>

      <div class="derbyTrack">
        <div class="horse" id="horsePlayer" style="top:35px">🐎</div>
        <div class="horse" id="horseComputer" style="top:145px">🏇</div>
        <div class="horse" id="horseThird" style="top:255px">🐴</div>
        <div class="derbyFinish"></div>
      </div>

      <div class="quizQuestion" id="derbyQuestion"></div>
      <div id="derbyOptions" class="options"></div>
      <div class="message" id="derbyMessage"></div>
    </div>
  `;

  function renderQuestion() {
    if (qIndex >= 10) {
      const bonus = correct * 35;

      finishGame(
        250 + bonus,
        30 + correct * 3,
        `Your horse finished the Derby with ${correct}/10 correct answers! 🏇`
      );

      return;
    }

    const q = questions[qIndex];

    document.getElementById("derbyQuestion").textContent =
      `${qIndex+1}/10 — ${q[0]}`;

    const options = shuffle([
      q[1],
      makeWrongAnswer(q[1]),
      makeWrongAnswer(q[1]),
      makeWrongAnswer(q[1])
    ]);

    const box = document.getElementById("derbyOptions");
    box.innerHTML = "";

    options.forEach(answer => {
      const b = document.createElement("button");
      b.className = "option";
      b.textContent = answer;

      b.onclick = () => {
        [...box.children].forEach(x => x.disabled=true);

        if (answer === q[1]) {
          correct++;
          playerHorse += 8;
          b.classList.add("correct");
          document.getElementById("derbyMessage").textContent =
            "Correct! Your horse races forward! 🐎";
        } else {
          playerHorse += 3;
          b.classList.add("wrong");
          document.getElementById("derbyMessage").textContent =
            "Not quite, but your horse keeps racing!";
        }

        computerHorse +=
          3 + Math.floor(Math.random()*5);

        document.getElementById("horsePlayer").style.left =
          Math.min(92,playerHorse) + "%";

        document.getElementById("horseComputer").style.left =
          Math.min(92,computerHorse) + "%";

        qIndex++;

        setTimeout(renderQuestion,600);
      };

      box.appendChild(b);
    });
  }

  renderQuestion();
}

function makeWrongAnswer(correct) {
  const generic = [
    "The Moon",
    "Blue",
    "12",
    "London",
    "Elephant",
    "Spring",
    "7",
    "Jupiter",
    "Green",
    "60",
    "Paris",
    "Water"
  ];

  let choice =
    generic[Math.floor(Math.random()*generic.length)];

  while (choice === correct) {
    choice =
      generic[Math.floor(Math.random()*generic.length)];
  }

  return choice;
}

/* ============================================================
   GAME 23 FINAL CHALLENGE
   EXACTLY 50 QUESTIONS
============================================================ */

function game23() {
  finalState = {
    index:0,
    correct:0,
    questions:shuffle(finalQuestions)
  };

  renderFinalQuestion();
}

function renderFinalQuestion() {
  const state = finalState;

  if (state.index >= 50) {
    completeFinalChallenge();
    return;
  }

  const q = state.questions[state.index];

  const wrongPool = shuffle(
    finalQuestions
      .filter(x => x[1] !== q[1])
      .map(x => x[1])
  );

  const options = shuffle([
    q[1],
    wrongPool[0],
    wrongPool[1],
    wrongPool[2]
  ]);

  document.getElementById("gameArea").innerHTML = `
    <div class="card">
      <h2>💗 Final Challenge</h2>

      <p class="gameDescription">
        The final challenge: 50 questions about Liliana.
      </p>

      <div class="scoreBig">
        Question ${state.index+1}/50
      </div>

      <div class="quizQuestion">
        ${escapeHTML(q[0])}
      </div>

      <div id="finalOptions" class="options"></div>

      <div class="message" id="finalMessage"></div>
    </div>
  `;

  const box = document.getElementById("finalOptions");

  options.forEach(answer => {
    const b = document.createElement("button");
    b.className = "option";
    b.textContent = answer;

    b.onclick = () => {
      [...box.children].forEach(x => x.disabled=true);

      if (answer === q[1]) {
        state.correct++;
        b.classList.add("correct");
        document.getElementById("finalMessage").textContent =
          "Correct! 💗";
      } else {
        b.classList.add("wrong");
        document.getElementById("finalMessage").textContent =
          "Not quite!";
      }

      state.index++;

      saveState();

      setTimeout(renderFinalQuestion,450);
    };

    box.appendChild(b);
  });
}

function completeFinalChallenge() {
  const correct = finalState.correct;

  /*
    IMPORTANT:
    Private call unlock is strictly >3000.
    Exactly 3000 does NOT qualify.
  */

  const qualifyingScore = score > 3000;

  completed[23] = true;
  saveState();

  let rewardHTML = "";

  if (qualifyingScore) {
    rewardHTML = `
      <div class="unlock">
        <h2>📞 PRIVATE CALL UNLOCKED</h2>
        <p>
          You finished Lulu Express with a score of
          <strong>${score}</strong> points.
        </p>
        <p>
          You reached the required score of 3001+.
          🎉
        </p>
      </div>
    `;
  } else {
    rewardHTML = `
      <div class="unlock">
        <h3>Almost there 💗</h3>
        <p>
          Your final score was <strong>${score}</strong>.
        </p>
        <p>
          The private call requires a score strictly
          greater than 3000.
        </p>
        <p>
          Exactly 3000 does not qualify.
        </p>
      </div>
    `;
  }

  document.getElementById("gameArea").innerHTML = `
    <div class="card endCard">
      <div class="bigHeart">💗</div>

      <h2>Journey Complete!</h2>

      <p>
        You answered <strong>${correct}/50</strong>
        questions correctly.
      </p>

      <p>
        Final Score:
        <strong>${score}</strong>
      </p>

      <p>
        Tokens:
        <strong>${tokens}</strong>
      </p>

      ${rewardHTML}

      <button class="primary" onclick="showMenu()">
        Return to Lulu Express
      </button>
    </div>
  `;
}

/* ============================================================
   MUSIC
   SIMPLE GENERATED GAME MUSIC
============================================================ */

function setupAudio() {
  if (!audioCtx) {
    audioCtx =
      new (window.AudioContext ||
           window.webkitAudioContext)();
  }

  if (audioCtx.state === "suspended") {
    audioCtx.resume();
  }
}

function playNote(freq,duration=.16) {
  if (!musicOn) return;

  setupAudio();

  const osc = audioCtx.createOscillator();
  const gain = audioCtx.createGain();

  osc.type = "sine";
  osc.frequency.value = freq;

  gain.gain.setValueAtTime(
    volume,
    audioCtx.currentTime
  );

  gain.gain.exponentialRampToValueAtTime(
    .001,
    audioCtx.currentTime + duration
  );

  osc.connect(gain);
  gain.connect(audioCtx.destination);

  osc.start();
  osc.stop(audioCtx.currentTime + duration);
}

function startMusic() {
  if (musicInterval) return;

  const notes = [
    261.63,
    329.63,
    392.00,
    329.63,
    293.66,
    349.23,
    440.00,
    349.23
  ];

  let i = 0;

  musicInterval = setInterval(() => {
    if (musicOn) {
      playNote(notes[i % notes.length],.18);
      i++;
    }
  },420);
}

function toggleMusic() {
  musicOn = !musicOn;

  if (musicOn) {
    setupAudio();
    startMusic();
    document.getElementById("musicButton").textContent =
      "🔊";
  } else {
    document.getElementById("musicButton").textContent =
      "♫";
  }
}

function changeVolume() {
  volume += .03;

  if (volume > .15) {
    volume = 0;
  }

  if (volume === 0) {
    document.querySelector(".musicBox button:nth-child(2)")
      .textContent = "🔇";
  } else {
    document.querySelector(".musicBox button:nth-child(2)")
      .textContent = "🔊";
  }
}

/* ============================================================
   RESET
============================================================ */

function resetGame() {
  const confirmed = confirm(
    "Reset Lulu Express completely?\\n\\n" +
    "This will erase:\\n" +
    "• Your score\\n" +
    "• Tokens\\n" +
    "• All unlocked games\\n" +
    "• Completed games\\n" +
    "• Derby progress\\n" +
    "• Final Challenge progress\\n" +
    "• Word Find progress\\n" +
    "• Drawing progress\\n\\n" +
    "This cannot be undone."
  );

  if (!confirmed) return;

  clearTimers();

  localStorage.removeItem("luluExpressState");

  playerName = "";
  score = 0;
  tokens = 0;
  currentGame = 0;
  unlocked = 1;
  completed = {};
  derbyState = null;
  finalState = null;
  wordState = {
    selected:[],
    found:[]
  };
  drawingStarted = false;

  document.getElementById("playerName").value = "";

  document.getElementById("menuScreen")
    .classList.add("hidden");

  document.getElementById("gameScreen")
    .classList.add("hidden");

  document.getElementById("startScreen")
    .classList.remove("hidden");

  updateStats();
}

/* ============================================================
   INITIAL LOAD
============================================================ */

loadState();

if (playerName) {
  document.getElementById("playerName").value =
    playerName;
}

updateStats();

/*
  Prevent accidental browser gestures from interfering
  with the game on mobile.
*/

document.addEventListener("gesturestart", e => {
  e.preventDefault();
});

document.addEventListener("gesturechange", e => {
  e.preventDefault();
});

document.addEventListener("gestureend", e => {
  e.preventDefault();
});

/*
  Prevent double-tap zoom while still allowing normal taps.
*/

let lastTouchEnd = 0;

document.addEventListener("touchend", e => {
  const now = Date.now();

  if (now - lastTouchEnd <= 300) {
    e.preventDefault();
  }

  lastTouchEnd = now;
}, {passive:false});

</script>

</body>
</html>

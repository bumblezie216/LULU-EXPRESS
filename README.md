<html lang="en">
<head>
<meta charset="UTF-8">

<meta
  name="viewport"
  content="width=device-width,
  initial-scale=1,
  maximum-scale=1,
  user-scalable=no,
  viewport-fit=cover"
>

<title>Lulu Express 💗</title>

<style>

/* =========================================================
   RESET + PHONE VIEW
========================================================= */

* {
  box-sizing: border-box;
  -webkit-tap-highlight-color: transparent;
}

html,
body {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  min-height: 100%;
  overflow: hidden;
  overscroll-behavior: none;
  font-family: Arial, sans-serif;
  background: #160b16;
  color: white;
}

body {
  position: fixed;
  inset: 0;
}

button,
input {
  font: inherit;
  touch-action: manipulation;
}

button {
  cursor: pointer;
}

#app {
  position: fixed;
  inset: 0;
  width: 100%;
  height: 100dvh;
  overflow: hidden;
}


/* =========================================================
   BACKGROUND
========================================================= */

#app::before {
  content: "";
  position: fixed;
  inset: 0;
  pointer-events: none;

  background:
    radial-gradient(circle at 20% 20%, rgba(255,150,200,.18), transparent 25%),
    radial-gradient(circle at 80% 70%, rgba(180,120,255,.12), transparent 30%),
    radial-gradient(circle at 50% 100%, rgba(255,100,170,.08), transparent 35%);
}


/* =========================================================
   SCREENS
========================================================= */

.screen {
  display: none;

  position: absolute;
  inset: 0;

  width: 100%;
  height: 100dvh;

  padding:
    max(7px, env(safe-area-inset-top))
    10px
    max(7px, env(safe-area-inset-bottom))
    10px;

  overflow: hidden;

  align-items: center;
  justify-content: center;
}

.screen.active {
  display: flex;
}


/* =========================================================
   CARD
========================================================= */

.card {
  width: 100%;
  max-width: 520px;

  height: calc(
    100dvh
    - env(safe-area-inset-top)
    - env(safe-area-inset-bottom)
    - 14px
  );

  padding: 13px;

  border-radius: 24px;

  background: rgba(255,192,220,.12);

  border: 1px solid rgba(255,190,220,.35);

  box-shadow:
    0 10px 40px rgba(0,0,0,.4);

  display: flex;
  flex-direction: column;

  overflow: hidden;

  position: relative;
  z-index: 1;
}


/* =========================================================
   START SCREEN
========================================================= */

#start .card {
  justify-content: center;
  text-align: center;
}


/* =========================================================
   GAME CARD
========================================================= */

#game .card {
  height: calc(
    100dvh
    - env(safe-area-inset-top)
    - env(safe-area-inset-bottom)
    - 10px
  );

  padding: 9px 11px;
}


/* =========================================================
   HEADINGS
========================================================= */

h1 {
  font-size: clamp(1.7rem, 8vw, 2.4rem);
  margin: 5px 0 10px;
}

h2 {
  margin: 4px 0 8px;
}

h3 {
  margin: 5px 0;
}

p {
  line-height: 1.35;
  margin: 5px 0;
}

.big-heart {
  font-size: clamp(3rem, 15vw, 5rem);

  animation: heartPulse 1.5s infinite;
}

@keyframes heartPulse {
  50% {
    transform: scale(1.1);
  }
}


/* =========================================================
   INPUT
========================================================= */

input {
  width: 100%;

  padding: 12px;

  border-radius: 14px;

  border: 2px solid #ff9ac7;

  background: white;
  color: #321;

  font-size: 1rem;

  text-align: center;

  margin: 5px 0;
}


/* =========================================================
   BUTTONS
========================================================= */

.main-btn {
  width: 100%;
  max-width: 390px;

  border: 0;

  border-radius: 15px;

  padding: 12px;

  min-height: 44px;

  margin: 4px auto;

  background: #ff9ac7;

  color: #351329;

  font-weight: bold;

  box-shadow:
    0 5px 12px rgba(0,0,0,.2);
}

.main-btn:active {
  transform: scale(.97);
}

.secondary {
  background: rgba(255,255,255,.12);
  color: white;

  border: 1px solid rgba(255,255,255,.25);
}


/* =========================================================
   LEVEL HEADER
========================================================= */

#levelLabel {
  flex: 0 0 auto;

  font-size: .7rem;

  opacity: .8;

  margin-bottom: 2px;
}

.progress {
  flex: 0 0 auto;

  width: 100%;

  height: 6px;

  background: rgba(255,255,255,.15);

  border-radius: 20px;

  overflow: hidden;

  margin: 2px 0 6px;
}

.progress div {
  height: 100%;

  width: 0;

  background: #ff9ac7;

  border-radius: 20px;

  transition: width .3s ease;
}

.game-title {
  flex: 0 0 auto;

  font-size: clamp(1.15rem, 5vw, 1.7rem);

  margin: 2px 0 4px;
}


/* =========================================================
   GAME AREA
========================================================= */

#gameArea {
  width: 100%;

  flex: 1 1 auto;

  min-height: 0;

  overflow-y: auto;
  overflow-x: hidden;

  padding: 0 2px 4px;

  overscroll-behavior: contain;

  scrollbar-width: none;
}

#gameArea::-webkit-scrollbar {
  display: none;
}


/* =========================================================
   NEXT AREA
========================================================= */

.next-area {
  flex: 0 0 auto;

  width: 100%;

  padding-top: 3px;
}

.hidden {
  display: none !important;
}


/* =========================================================
   CHOICES
========================================================= */

.choice-grid {
  width: 100%;

  display: grid;

  grid-template-columns: 1fr 1fr;

  gap: 7px;

  margin: 8px 0;
}

.choice {
  width: 100%;

  min-height: 46px;

  border: 1px solid rgba(255,255,255,.18);

  border-radius: 13px;

  padding: 9px 6px;

  background: rgba(255,255,255,.1);

  color: white;

  font-size: .88rem;
}

.choice:active {
  transform: scale(.96);
}

.choice.correct {
  background: #62d394;
  color: #102;
}

.choice.wrong {
  background: #e96b85;
}


/* =========================================================
   STATUS
========================================================= */

.status {
  min-height: 24px;

  font-weight: bold;

  font-size: .9rem;
}


/* =========================================================
   MEMORY VAULT
========================================================= */

.memory-grid {
  width: min(100%, 340px);

  display: grid;

  grid-template-columns: repeat(4, 1fr);

  gap: 6px;

  margin: 8px auto;
}

.memory-card {
  width: 100%;

  aspect-ratio: 1 / 1;

  border: 0;

  border-radius: 11px;

  background: #ff9ac7;

  color: #351329;

  font-size: clamp(1.25rem, 7vw, 1.8rem);

  padding: 0;
}

.memory-card.open {
  background: white;
}

.memory-card.matched {
  background: #8ee8bd;
}


/* =========================================================
   PATTERN GRID
========================================================= */

.pattern-grid {
  width: min(100%, 310px);

  display: grid;

  grid-template-columns: repeat(4, 1fr);

  gap: 6px;

  margin: 8px auto;
}

.pattern-cell {
  aspect-ratio: 1;

  border: 0;

  border-radius: 10px;

  background: rgba(255,255,255,.12);

  padding: 0;
}

.pattern-cell.lit {
  background: #ff9ac7;
}


/* =========================================================
   FALLING / TARGET AREA
========================================================= */

.fall-area {
  width: 100%;

  height: min(48dvh, 400px);

  min-height: 190px;

  position: relative;

  overflow: hidden;

  border-radius: 18px;

  background: #08050d;

  border: 1px solid rgba(255,255,255,.15);
}

.falling {
  position: absolute;

  border: 0;

  background: none;

  padding: 4px;

  font-size: clamp(1.7rem, 8vw, 2.3rem);
}


/* =========================================================
   WORD FIND
========================================================= */

.word-list {
  display: flex;

  flex-wrap: wrap;

  justify-content: center;

  gap: 4px;

  margin: 4px 0;

  max-height: 68px;

  overflow: hidden;
}

.word {
  padding: 4px 6px;

  border-radius: 7px;

  background: rgba(255,255,255,.12);

  font-size: .66rem;
}

.word.done {
  background: #76dba5;

  color: #123;

  text-decoration: line-through;
}

.word-grid {
  width: min(100%, 355px);

  display: grid;

  grid-template-columns: repeat(10, 1fr);

  gap: 2px;

  margin: 5px auto;
}

.letter {
  width: 100%;

  aspect-ratio: 1;

  border: 0;

  border-radius: 4px;

  padding: 0;

  background: rgba(255,255,255,.1);

  color: white;

  font-size: clamp(.52rem, 2.6vw, .78rem);

  font-weight: bold;
}

.letter.selected {
  background: #ff9ac7;

  color: #351329;
}

.letter.found {
  background: #76dba5;

  color: #123;
}


/* =========================================================
   DRAWING
========================================================= */

#drawCanvas {
  display: block;

  width: min(100%, 330px);

  height: auto;

  aspect-ratio: 1 / 1;

  margin: 5px auto;

  background: white;

  border-radius: 16px;

  touch-action: none;
}


/* =========================================================
   ANIMALS
========================================================= */

.animal-grid {
  display: grid;

  grid-template-columns: repeat(3, 1fr);

  gap: 6px;

  width: 100%;

  margin-bottom: 6px;
}

.animal {
  border: 0;

  border-radius: 12px;

  padding: 8px 4px;

  background: rgba(255,255,255,.1);

  color: white;

  font-size: 1.4rem;
}

.animal small {
  display: block;

  font-size: .58rem;
}


/* =========================================================
   RACE
========================================================= */

.race-track {
  width: 100%;

  padding: 4px 0;
}

.racer {
  width: 100%;

  height: 34px;

  border-radius: 10px;

  background: rgba(255,255,255,.1);

  margin: 5px 0;

  position: relative;

  overflow: hidden;
}

.racer span {
  position: absolute;

  left: 2px;

  top: 2px;

  font-size: 1.25rem;

  transition: left .2s;
}


/* =========================================================
   CASINO
========================================================= */

.bank {
  font-size: 1.05rem;

  font-weight: bold;

  margin: 5px;
}

.reward {
  font-size: clamp(2rem, 12vw, 3.2rem);

  margin: 5px;
}


/* =========================================================
   FINISH
========================================================= */

#finish .card {
  justify-content: center;

  overflow-y: auto;
}


/* =========================================================
   SMALL PHONES
========================================================= */

@media (max-height: 700px) {

  .screen {
    padding: 5px 7px;
  }

  .card,
  #game .card {
    height: calc(100dvh - 10px);

    padding: 7px 9px;

    border-radius: 20px;
  }

  .game-title {
    font-size: 1.15rem;
  }

  .choice {
    min-height: 40px;

    padding: 7px 5px;

    font-size: .8rem;
  }

  .main-btn {
    min-height: 39px;

    padding: 8px;
  }

  .memory-grid {
    max-width: 295px;

    gap: 5px;
  }

  .pattern-grid {
    max-width: 275px;

    gap: 5px;
  }

  .fall-area {
    height: 40dvh;

    min-height: 175px;
  }

  #drawCanvas {
    max-width: min(285px, 75vw);
  }
}


/* =========================================================
   VERY SMALL PHONES
========================================================= */

@media (max-height: 580px) {

  .screen {
    padding: 3px 5px;
  }

  .card,
  #game .card {
    height: calc(100dvh - 6px);

    padding: 5px 7px;
  }

  #levelLabel {
    font-size: .6rem;
  }

  .progress {
    height: 4px;

    margin-bottom: 3px;
  }

  .game-title {
    font-size: 1rem;
  }

  #gameArea p {
    font-size: .78rem;

    margin: 2px 0;
  }

  .choice-grid {
    gap: 4px;

    margin: 4px 0;
  }

  .choice {
    min-height: 34px;

    padding: 5px 3px;

    font-size: .72rem;
  }

  .memory-grid {
    max-width: 250px;
  }

  .pattern-grid {
    max-width: 235px;
  }

  .fall-area {
    height: 34dvh;

    min-height: 145px;
  }

  #drawCanvas {
    max-width: min(225px, 62vw);
  }
}

</style>
</head>

<body>

<div id="app">

<!-- =======================================================
     START SCREEN
======================================================= -->

<section id="start" class="screen active">

  <div class="card">

    <div class="big-heart">💗</div>

    <h1>Lulu Express</h1>

    <p>
      Welcome to your very own birthday adventure, Lulu.
    </p>

    <p>
      23 games.<br>
      One journey.<br>
      One very special person.
    </p>

    <button
      class="main-btn secondary"
      onclick="toggleMusic()"
    >
      🎵 <span id="musicText">Music: OFF</span>
    </button>

    <input
      id="playerName"
      placeholder="Enter your name"
      autocomplete="off"
    >

    <button
      class="main-btn"
      onclick="startJourney()"
    >
      🚂 START THE JOURNEY
    </button>

  </div>

</section>


<!-- =======================================================
     GAME SCREEN
======================================================= -->

<section id="game" class="screen">

  <div class="card">

    <div id="levelLabel">
      LEVEL 1 OF 23
    </div>

    <div class="progress">
      <div id="progressBar"></div>
    </div>

    <h2
      id="gameTitle"
      class="game-title"
    ></h2>

    <div id="gameArea"></div>

    <div
      id="nextArea"
      class="next-area hidden"
    >
      <button
        class="main-btn"
        onclick="nextLevel()"
      >
        NEXT LEVEL 💗
      </button>
    </div>

  </div>

</section>


<!-- =======================================================
     FINISH SCREEN
======================================================= -->

<section id="finish" class="screen">

  <div class="card">

    <div class="big-heart">🏆</div>

    <h1>Journey Complete!</h1>

    <p id="finishText"></p>

    <div id="rewardBox"></div>

    <button
      class="main-btn"
      onclick="resetJourney()"
    >
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


const gameArea =
  document.getElementById("gameArea");

const gameTitle =
  document.getElementById("gameTitle");

const nextArea =
  document.getElementById("nextArea");

const levelLabel =
  document.getElementById("levelLabel");

const progressBar =
  document.getElementById("progressBar");


/* =========================================================
   TIMER CLEANUP
========================================================= */

function clearTimers() {

  if (gameTimer) {

    clearInterval(gameTimer);

    gameTimer = null;

  }

  gameTimeouts.forEach(
    t => clearTimeout(t)
  );

  gameTimeouts = [];

}


function later(fn, ms) {

  const timer =
    setTimeout(fn, ms);

  gameTimeouts.push(timer);

  return timer;

}


/* =========================================================
   SCREEN CONTROL
========================================================= */

function showScreen(id) {

  document
    .querySelectorAll(".screen")
    .forEach(screen => {

      screen.classList.remove("active");

    });

  document
    .getElementById(id)
    .classList.add("active");

}


/* =========================================================
   START
========================================================= */

function startJourney() {

  const input =
    document.getElementById("playerName");

  player =
    input.value.trim();

  if (!player) {

    input.placeholder =
      "Please enter your name 💗";

    input.focus();

    return;

  }

  score = 0;

  tokens = 0;

  currentLevel = 1;

  playTone(660, .12);

  showScreen("game");

  loadLevel();

}


/* =========================================================
   LOAD LEVEL
========================================================= */

function loadLevel() {

  clearTimers();

  nextArea.classList.add("hidden");

  levelLabel.textContent =
    `LEVEL ${currentLevel} OF ${TOTAL_LEVELS}`;

  progressBar.style.width =
    `${currentLevel / TOTAL_LEVELS * 100}%`;


  const games = [

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


  games[currentLevel - 1]();

}


/* =========================================================
   COMPLETE GAME
========================================================= */

function completeGame(
  points = 200,
  rewardTokens = 100
) {

  clearTimers();

  score += points;

  tokens += rewardTokens;


  gameArea.innerHTML = `

    <div class="reward">
      ✨
    </div>

    <h2>
      Level Complete!
    </h2>

    <p>
      Beautiful work,
      ${escapeHTML(player)}! 💗
    </p>

    <p>
      +${points} points
    </p>

  `;


  nextArea.classList.remove("hidden");

  playTone(880, .15);

}


/* =========================================================
   NEXT LEVEL
========================================================= */

function nextLevel() {

  if (currentLevel >= TOTAL_LEVELS) {

    finishJourney();

    return;

  }

  currentLevel++;

  loadLevel();

}


/* =========================================================
   ESCAPE HTML
========================================================= */

function escapeHTML(text) {

  return text.replace(
    /[&<>"']/g,
    char => ({

      "&": "&amp;",
      "<": "&lt;",
      ">": "&gt;",
      '"': "&quot;",
      "'": "&#039;"

    }[char])
  );

}


/* =========================================================
   1. BROKEN HEARTS
========================================================= */

function brokenHearts() {

  gameTitle.textContent =
    "💔 Broken Hearts";

  gameArea.innerHTML = `

    <p>
      Catch the good hearts!
    </p>

    <p>
      Avoid 💔
    </p>

    <p id="bhScore">
      Hearts: 0 / 15
    </p>

    <div
      class="fall-area"
      id="fallArea"
    ></div>

  `;


  const area =
    document.getElementById("fallArea");

  let caught = 0;

  let spawned = 0;


  function spawnHeart() {

    if (caught >= 15)
      return;

    spawned++;

    const heart =
      document.createElement("button");

    const good =
      Math.random() > .25;

    heart.className =
      "falling";

    heart.textContent =
      good
        ? (Math.random() > .5 ? "❤️" : "💖")
        : "💔";

    heart.style.left =
      Math.random() * 85 + "%";

    heart.style.top =
      "0px";

    area.appendChild(heart);


    let y = 0;

    const speed =
      2 + Math.min(currentLevel * .08, 1);


    const movement =
      setInterval(() => {

        y += speed;

        heart.style.top =
          y + "px";


        if (
          y >
          area.clientHeight
        ) {

          clearInterval(movement);

          heart.remove();

        }

      }, 30);


    heart.onclick = () => {

      clearInterval(movement);

      heart.remove();


      if (good) {

        caught++;

        document
          .getElementById("bhScore")
          .textContent =
          `Hearts: ${caught} / 15`;


        if (caught >= 15) {

          completeGame(250, 150);

        }

      } else {

        score =
          Math.max(0, score - 50);

      }

    };

  }


  gameTimer =
    setInterval(() => {

      if (spawned >= 35) {

        clearInterval(gameTimer);

        gameTimer = null;

        return;

      }

      spawnHeart();

    }, 650);

}


/* =========================================================
   2. MEMORY VAULT
========================================================= */

function memoryVault() {

  gameTitle.textContent =
    "🧠 Memory Vault";


  gameArea.innerHTML = `

    <p>
      Match all 8 pairs.
    </p>

    <p id="memoryStatus">
      Pairs: 0 / 8
    </p>

    <div
      class="memory-grid"
      id="memoryGrid"
    ></div>

  `;


  const symbols = [

    "🌸","🌸",
    "💗","💗",
    "⭐","⭐",
    "🦋","🦋",
    "🐬","🐬",
    "🌻","🌻",
    "🌙","🌙",
    "💎","💎"

  ];


  symbols.sort(
    () => Math.random() - .5
  );


  const grid =
    document.getElementById("memoryGrid");


  let first = null;

  let locked = false;

  let pairs = 0;

  let mistakes = 0;


  symbols.forEach(symbol => {

    const card =
      document.createElement("button");

    card.className =
      "memory-card";

    card.textContent =
      "❓";

    card.dataset.symbol =
      symbol;


    card.onclick = () => {

      if (
        locked ||
        card.classList.contains("matched") ||
        card === first
      ) {

        return;

      }


      card.textContent =
        symbol;

      card.classList.add("open");


      if (!first) {

        first = card;

        return;

      }


      locked = true;


      if (
        first.dataset.symbol ===
        card.dataset.symbol
      ) {

        first.classList.add("matched");

        card.classList.add("matched");

        pairs++;


        document
          .getElementById("memoryStatus")
          .textContent =
          `Pairs: ${pairs} / 8`;


        first = null;

        locked = false;


        if (pairs === 8) {

          completeGame(
            Math.max(
              180,
              300 - mistakes * 10
            ),
            180
          );

        }

      } else {

        mistakes++;

        const old =
          first;

        const second =
          card;


        later(() => {

          old.textContent =
            "❓";

          second.textContent =
            "❓";

          old.classList.remove("open");

          second.classList.remove("open");

          first = null;

          locked = false;

        }, 650);

      }

    };


    grid.appendChild(card);

  });

}


/* =========================================================
   3. PRESSURE QUIZ
========================================================= */

const pressureQuestions = [

  [
    "Which animal does Liliana love most?",
    "Dolphin",
    [
      "Dolphin",
      "Tiger",
      "Horse",
      "Penguin"
    ]
  ],

  [
    "What is Liliana's favourite food?",
    "Sushi",
    [
      "Pizza",
      "Sushi",
      "Pasta",
      "Tacos"
    ]
  ],

  [
    "What colour does Liliana love?",
    "Baby pink",
    [
      "Purple",
      "Baby pink",
      "Blue",
      "Green"
    ]
  ],

  [
    "What is Liliana's star sign?",
    "Leo",
    [
      "Leo",
      "Cancer",
      "Gemini",
      "Aries"
    ]
  ],

  [
    "What did Liliana study at university?",
    "Psychology",
    [
      "Law",
      "Psychology",
      "Medicine",
      "Art"
    ]
  ],

  [
    "What type of songs does Liliana like?",
    "Sad songs",
    [
      "Country songs",
      "Sad songs",
      "Metal",
      "Opera"
    ]
  ],

  [
    "Which flower does Liliana like?",
    "Sunflowers",
    [
      "Lilies",
      "Sunflowers",
      "Tulips",
      "Orchids"
    ]
  ],

  [
    "How many siblings does Liliana have?",
    "5",
    [
      "3",
      "4",
      "5",
      "6"
    ]
  ]

];


function pressureQuiz() {

  gameTitle.textContent =
    "⚡ Pressure Quiz";


  let questions =
    [...pressureQuestions]
      .sort(() => Math.random() - .5)
      .slice(0, 6);


  let index = 0;

  let correct = 0;

  let answered = false;

  let time = 7;


  function render() {

    if (index >= questions.length) {

      completeGame(
        150 + correct * 35,
        100 + correct * 10
      );

      return;

    }


    answered = false;

    time = 7;


    const q =
      questions[index];


    gameArea.innerHTML = `

      <p>
        Question
        ${index + 1}
        /
        ${questions.length}
      </p>

      <h3>
        ${q[0]}
      </h3>

      <div id="quizTimer">
        ⏱️ ${time}
      </div>

      <div
        class="choice-grid"
        id="quizChoices"
      ></div>

      <div
        class="status"
        id="quizStatus"
      ></div>

    `;


    const choices =
      document.getElementById("quizChoices");


    [...q[2]]
      .sort(() => Math.random() - .5)
      .forEach(answer => {

        const button =
          document.createElement("button");

        button.className =
          "choice";

        button.textContent =
          answer;


        button.onclick = () => {

          if (answered)
            return;

          answered = true;

          clearInterval(gameTimer);

          if (answer === q[1]) {

            correct++;

            button.classList.add("correct");

            document
              .getElementById("quizStatus")
              .textContent =
              "Correct! 💗";

          } else {

            button.classList.add("wrong");

            document
              .getElementById("quizStatus")
              .textContent =
              `The answer was ${q[1]}`;

          }


          later(() => {

            index++;

            render();

          }, 500);

        };


        choices.appendChild(button);

      });


    gameTimer =
      setInterval(() => {

        if (answered)
          return;

        time--;

        const timer =
          document.getElementById("quizTimer");

        if (timer)
          timer.textContent =
            `⏱️ ${time}`;


        if (time <= 0) {

          clearInterval(gameTimer);

          answered = true;

          document
            .getElementById("quizStatus")
            .textContent =
            "Time! ⏰";


          later(() => {

            index++;

            render();

          }, 500);

        }

      }, 1000);

  }


  render();

}


/* =========================================================
   4. HIGH ROLLER
========================================================= */

function highRoller() {

  gameTitle.textContent =
    "🎰 High Roller";


  let rounds = 0;

  let bank = 500;


  function render() {

    gameArea.innerHTML = `

      <div class="bank">
        💰 ${bank} tokens
      </div>

      <p>
        Pick a mystery card.
      </p>

      <div
        class="choice-grid"
        id="cards"
      ></div>

      <p
        id="hrStatus"
        class="status"
      ></p>

    `;


    const values = [

      100,
      250,
      500,
      -100,
      750

    ].sort(() => Math.random() - .5);


    values.forEach((value, index) => {

      const button =
        document.createElement("button");

      button.className =
        "choice";

      button.textContent =
        ["🂠","🂠","🂠","🂠","🂠"][index];


      button.onclick = () => {

        bank =
          Math.max(
            0,
            bank + value
          );

        rounds++;


        document
          .getElementById("hrStatus")
          .textContent =
          value >= 0
            ? `You won +${value}! 💰`
            : `Oh no! ${value} 💔`;


        if (rounds >= 5) {

          score += bank;

          completeGame(
            Math.min(
              500,
              200 + Math.floor(bank / 5)
            ),
            Math.floor(bank / 10)
          );

        } else {

          later(render, 500);

        }

      };


      document
        .getElementById("cards")
        .appendChild(button);

    });

  }


  render();

}


/* =========================================================
   5. MIND GAMES
========================================================= */

function mindGames() {

  gameTitle.textContent =
    "🧩 Mind Games";


  const pattern = [];

  while (pattern.length < 5) {

    const n =
      Math.floor(Math.random() * 16);

    if (!pattern.includes(n))
      pattern.push(n);

  }


  gameArea.innerHTML = `

    <p>
      Remember the glowing sequence.
    </p>

    <p id="mindStatus">
      Watch carefully...
    </p>

    <div
      class="pattern-grid"
      id="patternGrid"
    ></div>

  `;


  const grid =
    document.getElementById("patternGrid");


  for (let i = 0; i < 16; i++) {

    const button =
      document.createElement("button");

    button.className =
      "pattern-cell";

    grid.appendChild(button);

  }


  pattern.forEach((number, index) => {

    later(() => {

      grid.children[number]
        .classList.add("lit");


      later(() => {

        grid.children[number]
          .classList.remove("lit");

      }, 400);

    }, index * 600 + 400);

  });


  later(() => {

    document
      .getElementById("mindStatus")
      .textContent =
      "Now repeat it!";


    let position = 0;


    [...grid.children]
      .forEach((button, index) => {

        button.onclick = () => {

          if (
            index === pattern[position]
          ) {

            button.classList.add("lit");

            later(() => {

              button.classList.remove("lit");

            }, 250);

            position++;


            if (
              position ===
              pattern.length
            ) {

              completeGame(
                320,
                190
              );

            }

          } else {

            position = 0;

            document
              .getElementById("mindStatus")
              .textContent =
              "Wrong! Start the sequence again.";

            [...grid.children]
              .forEach(x =>
                x.classList.remove("lit")
              );

          }

        };

      });

  }, 3400);

}


/* =========================================================
   6. THE BLUFF
========================================================= */

function bluffGame() {

  gameTitle.textContent =
    "🤥 The Bluff";


  const statements = [

    "Liliana loves dolphins.",

    "Liliana studied Psychology.",

    "Liliana's favourite colour is baby pink."

  ];


  const liar =
    Math.floor(
      Math.random() *
      statements.length
    );


  gameArea.innerHTML = `

    <p>
      One statement is the bluff.
    </p>

    <div id="bluffBox"></div>

  `;


  const box =
    document.getElementById("bluffBox");


  statements.forEach((statement, index) => {

    const button =
      document.createElement("button");

    button.className =
      "choice";

    button.style.width =
      "100%";

    button.textContent =
      statement;


    button.onclick = () => {

      if (index === liar) {

        completeGame(
          300,
          180
        );

      } else {

        button.classList.add("wrong");

        document
          .getElementById("bluffBox")
          .insertAdjacentHTML(
            "beforeend",
            "<p>Not the bluff! Try again 💗</p>"
          );

      }

    };


    box.appendChild(button);

  });

}


/* =========================================================
   7. SURVIVAL ROUND
========================================================= */

function survivalRound() {

  gameTitle.textContent =
    "🚪 Survival Round";


  let round = 1;

  let lives = 3;


  function render() {

    if (round > 5) {

      completeGame(
        350,
        200
      );

      return;

    }


    const doorCount =
      round < 3 ? 3 : 4;


    const safe =
      Math.floor(
        Math.random() *
        doorCount
      );


    gameArea.innerHTML = `

      <p>
        Round ${round} / 5
      </p>

      <p>
        ❤️ Lives: ${lives}
      </p>

      <div
        class="choice-grid"
        id="doors"
      ></div>

      <p
        id="surviveStatus"
        class="status"
      ></p>

    `;


    for (
      let i = 0;
      i < doorCount;
      i++
    ) {

      const button =
        document.createElement("button");

      button.className =
        "choice";

      button.textContent =
        "🚪";


      button.onclick = () => {

        if (i === safe) {

          round++;

          document
            .getElementById("surviveStatus")
            .textContent =
            "Safe! 💗";


          later(
            render,
            450
          );

        } else {

          lives--;

          document
            .getElementById("surviveStatus")
            .textContent =
            "Trap! 💔";


          if (lives <= 0) {

            completeGame(
              120,
              60
            );

          } else {

            later(
              render,
              500
            );

          }

        }

      };


      document
        .getElementById("doors")
        .appendChild(button);

    }

  }


  render();

}


/* =========================================================
   8. ADMIRER RACE
========================================================= */

function admirerRace() {

  gameTitle.textContent =
    "🏇 Admirer's Race";


  let you = 0;

  let rival = 0;

  let stamina = 5;

  let round = 0;


  function render() {

    if (you >= 100) {

      completeGame(
        350,
        200
      );

      return;

    }


    if (round >= 8) {

      completeGame(
        250,
        120
      );

      return;

    }


    gameArea.innerHTML = `

      <p>
        Beat the admirer!
      </p>

      <div class="race-track">

        <div class="racer">

          💗

          <span
            style="left:${Math.min(90,you)}%"
          >
            🏃
          </span>

        </div>


        <div class="racer">

          💔

          <span
            style="left:${Math.min(90,rival)}%"
          >
            😏
          </span>

        </div>

      </div>

      <p>
        ⚡ Stamina: ${stamina}
      </p>

      <div class="choice-grid">

        <button
          class="choice"
          id="run"
        >
          🏃 RUN
        </button>

        <button
          class="choice"
          id="boost"
        >
          ⚡ BOOST
        </button>

        <button
          class="choice"
          id="rest"
        >
          😴 REST
        </button>

      </div>

    `;


    document
      .getElementById("run")
      .onclick = () => {

        you += 18;

        rival += 12;

        round++;

        render();

      };


    document
      .getElementById("boost")
      .onclick = () => {

        if (stamina > 0) {

          stamina--;

          you += 30;

        } else {

          you += 5;

        }

        rival += 12;

        round++;

        render();

      };


    document
      .getElementById("rest")
      .onclick = () => {

        stamina =
          Math.min(
            5,
            stamina + 2
          );

        you += 5;

        rival += 10;

        round++;

        render();

      };

  }


  render();

}


/* =========================================================
   9. HEARTBREAK CHAMBER
========================================================= */

function heartbreakChamber() {

  gameTitle.textContent =
    "💔 Heartbreak Chamber";


  const puzzles = [

    {
      question:
        "2, 4, 8, 16, ?",
      answer:
        "32",
      options:
        ["24","32","30","20"]
    },

    {
      question:
        "Which symbol doesn't belong?",
      answer:
        "💔",
      options:
        ["❤️","💗","💖","💔"]
    },

    {
      question:
        "What is 3 + 6 × 2?",
      answer:
        "15",
      options:
        ["18","12","15","21"]
    }

  ];


  let stage = 0;


  function render() {

    if (stage >= 3) {

      completeGame(
        350,
        200
      );

      return;

    }


    const puzzle =
      puzzles[stage];


    gameArea.innerHTML = `

      <p>
        Puzzle ${stage + 1} / 3
      </p>

      <h3>
        ${puzzle.question}
      </h3>

      <div
        class="choice-grid"
        id="chChoices"
      ></div>

    `;


    [...puzzle.options]
      .sort(() => Math.random() - .5)
      .forEach(answer => {

        const button =
          document.createElement("button");

        button.className =
          "choice";

        button.textContent =
          answer;


        button.onclick = () => {

          if (
            answer ===
            puzzle.answer
          ) {

            stage++;

            render();

          } else {

            button.classList.add("wrong");

          }

        };


        document
          .getElementById("chChoices")
          .appendChild(button);

      });

  }


  render();

}


/* =========================================================
   10. HEARTBREAK BOXING
========================================================= */

function boxingMatch() {

  gameTitle.textContent =
    "🥊 Heartbreak Boxing";


  let enemyHealth = 5;

  let yourHealth = 5;

  let round = 0;


  function render() {

    if (enemyHealth <= 0) {

      completeGame(
        380,
        220
      );

      return;

    }


    if (yourHealth <= 0) {

      enemyHealth = 5;

      yourHealth = 5;

      round = 0;

    }


    round++;


    const attacks = [
      "PUNCH",
      "BLOCK",
      "DODGE"
    ];


    const enemyMove =
      attacks[
        Math.floor(
          Math.random() *
          attacks.length
        )
      ];


    gameArea.innerHTML = `

      <p>
        Round ${round}
      </p>

      <p>
        Enemy:
        ${"❤️".repeat(enemyHealth)}
      </p>

      <p>
        You:
        ${"💗".repeat(yourHealth)}
      </p>

      <div class="reward">

        ${
          enemyMove === "PUNCH"
          ? "🥊"
          : enemyMove === "BLOCK"
          ? "🛡️"
          : "↪️"
        }

      </div>

      <p>
        Choose your move!
      </p>

      <div
        class="choice-grid"
        id="fight"
      ></div>

    `;


    const choices = [

      ["🥊 PUNCH","PUNCH"],

      ["🛡️ BLOCK","BLOCK"],

      ["↪️ DODGE","DODGE"]

    ];


    choices.forEach(item => {

      const button =
        document.createElement("button");

      button.className =
        "choice";

      button.textContent =
        item[0];


      button.onclick = () => {

        const move =
          item[1];


        if (
          (enemyMove === "PUNCH" &&
           move === "BLOCK") ||

          (enemyMove === "BLOCK" &&
           move === "PUNCH") ||

          (enemyMove === "DODGE" &&
           move === "DODGE")
        ) {

          enemyHealth--;

        } else {

          yourHealth--;

        }


        later(
          render,
          350
        );

      };


      document
        .getElementById("fight")
        .appendChild(button);

    });

  }


  render();

}


/* =========================================================
   11. PERFECT MATCH
========================================================= */

function perfectMatch() {

  gameTitle.textContent =
    "💕 Perfect Match";


  const pairs = [

    ["🐬","🌊"],

    ["🌻","☀️"],

    ["☕","🖤"],

    ["🎵","🎤"]

  ];


  const cards =
    pairs
      .flat()
      .sort(() => Math.random() - .5);


  gameArea.innerHTML = `

    <p>
      Find the things that belong together.
    </p>

    <div
      class="memory-grid"
      id="pmGrid"
    ></div>

    <p id="pmStatus">
      Pairs: 0 / 4
    </p>

  `;


  let first = null;

  let locked = false;

  let found = 0;


  cards.forEach(symbol => {

    const button =
      document.createElement("button");

    button.className =
      "memory-card";

    button.textContent =
      "❓";

    button.dataset.symbol =
      symbol;


    button.onclick = () => {

      if (
        locked ||
        button.classList.contains("matched") ||
        button === first
      ) {

        return;

      }


      button.textContent =
        symbol;

      button.classList.add("open");


      if (!first) {

        first = button;

        return;

      }


      locked = true;


      const match =
        pairs.some(pair =>
          pair.includes(
            first.dataset.symbol
          ) &&
          pair.includes(
            button.dataset.symbol
          )
        );


      if (match) {

        first.classList.add("matched");

        button.classList.add("matched");

        found++;


        document
          .getElementById("pmStatus")
          .textContent =
          `Pairs: ${found} / 4`;


        first = null;

        locked = false;


        if (found === 4) {

          completeGame(
            300,
            180
          );

        }

      } else {

        const old =
          first;


        later(() => {

          old.textContent =
            "❓";

          button.textContent =
            "❓";

          old.classList.remove("open");

          button.classList.remove("open");

          first = null;

          locked = false;

        }, 650);

      }

    };


    document
      .getElementById("pmGrid")
      .appendChild(button);

  });

}


/* =========================================================
   12. WHO KNOWS LILIANA
========================================================= */

const luluQuestions = [

  [
    "What is Liliana's favourite number?",
    "3",
    ["3","7","9","5"]
  ],

  [
    "How many siblings does Liliana have?",
    "5",
    ["2","4","5","6"]
  ],

  [
    "How many nephews does Liliana have?",
    "4",
    ["2","3","4","5"]
  ],

  [
    "How many nieces does Liliana have?",
    "1",
    ["1","2","3","4"]
  ],

  [
    "What are Liliana's dogs called?",
    "Aayla & Arlo",
    [
      "Aayla & Arlo",
      "Luna & Max",
      "Bella & Milo",
      "Coco & Arlo"
    ]
  ],

  [
    "What colour are Liliana's eyes?",
    "Green",
    ["Brown","Blue","Green","Hazel"]
  ],

  [
    "What movie does Liliana like?",
    "Me Before You",
    [
      "Titanic",
      "Me Before You",
      "Frozen",
      "The Notebook"
    ]
  ],

  [
    "What does Liliana want someday?",
    "A baby girl",
    [
      "A baby boy",
      "A baby girl",
      "Twins",
      "No children"
    ]
  ],

  [
    "What does Liliana like writing?",
    "Poetry",
    [
      "Poetry",
      "News",
      "Recipes",
      "Manuals"
    ]
  ],

  [
    "What is Liliana's zodiac sign?",
    "Leo",
    ["Leo","Virgo","Libra","Taurus"]
  ]

];


function whoKnowsLiliana() {

  gameTitle.textContent =
    "👑 Who Knows Liliana Best?";


  let questions =
    [...luluQuestions]
      .sort(() => Math.random() - .5);


  let index = 0;

  let correct = 0;


  function show() {

    if (
      index >=
      questions.length
    ) {

      completeGame(
        200 + correct * 25,
        120 + correct * 8
      );

      return;

    }


    const q =
      questions[index];


    gameArea.innerHTML = `

      <p>
        Question
        ${index + 1}
        /
        ${questions.length}
      </p>

      <h3>
        ${q[0]}
      </h3>

      <div
        class="choice-grid"
        id="lq"
      ></div>

    `;


    [...q[2]]
      .sort(() => Math.random() - .5)
      .forEach(answer => {

        const button =
          document.createElement("button");

        button.className =
          "choice";

        button.textContent =
          answer;


        button.onclick = () => {

          if (
            answer ===
            q[1]
          ) {

            correct++;

          }


          index++;

          show();

        };


        document
          .getElementById("lq")
          .appendChild(button);

      });

  }


  show();

}


/* =========================================================
   13. REACTION GAUNTLET
========================================================= */

function reactionGauntlet() {

  gameTitle.textContent =
    "⚡ Reaction Gauntlet";


  let round = 0;

  let hits = 0;


  function render() {

    if (round >= 10) {

      completeGame(
        150 + hits * 20,
        100 + hits * 10
      );

      return;

    }


    const symbols = [

      "❤️",
      "⭐",
      "💎",
      "🌸"

    ];


    const target =
      symbols[
        Math.floor(
          Math.random() *
          symbols.length
        )
      ];


    const forbidden =
      Math.random() < .35;


    gameArea.innerHTML = `

      <p>
        Round ${round + 1} / 10
      </p>

      <h3>
        ${
          forbidden
          ? "DON'T TAP"
          : "TAP"
        }
        ${target}
      </h3>

      <div
        class="choice-grid"
        id="reaction"
      ></div>

    `;


    [...symbols]
      .sort(() => Math.random() - .5)
      .forEach(symbol => {

        const button =
          document.createElement("button");

        button.className =
          "choice";

        button.textContent =
          symbol;


        button.onclick = () => {

          const correct =
            forbidden
              ? symbol !== target
              : symbol === target;


          if (correct)
            hits++;


          round++;

          render();

        };


        document
          .getElementById("reaction")
          .appendChild(button);

      });

  }


  render();

}


/* =========================================================
   14. HEART HUNT
========================================================= */

function heartHunt() {

  gameTitle.textContent =
    "💗 Heart Hunt";


  const cells =
    Array(25).fill("");


  const positions =
    [...Array(25).keys()]
      .sort(() => Math.random() - .5)
      .slice(0,10);


  positions.forEach(index => {

    cells[index] =
      "❤️";

  });


  let found = 0;

  let misses = 0;


  gameArea.innerHTML = `

    <p>
      Find all 10 hearts!
    </p>

    <p id="huntStatus">
      ❤️ 0 / 10
    </p>

    <div
      class="pattern-grid"
      id="huntGrid"
    ></div>

  `;


  cells.forEach(value => {

    const button =
      document.createElement("button");

    button.className =
      "pattern-cell";

    button.textContent =
      "✨";


    button.onclick = () => {

      if (button.disabled)
        return;


      button.disabled = true;


      if (value === "❤️") {

        button.textContent =
          "❤️";

        button.classList.add("lit");

        found++;

      } else {

        button.textContent =
          "💨";

        misses++;

      }


      document
        .getElementById("huntStatus")
        .textContent =
        `❤️ ${found} / 10 | Misses: ${misses}`;


      if (found >= 10) {

        completeGame(
          Math.max(
            180,
            350 - misses * 15
          ),
          150
        );

      }

    };


    document
      .getElementById("huntGrid")
      .appendChild(button);

  });

}


/* =========================================================
   15. LOVE LOCK
========================================================= */

function loveLock() {

  gameTitle.textContent =
    "🔐 Love Lock";


  gameArea.innerHTML = `

    <p>
      Solve the clues to unlock the love lock.
    </p>

    <div
      class="card"
      style="
        height:auto;
        margin:8px 0;
        padding:10px;
      "
    >

      <p>
        🔎 Clue 1:
        The month is July.
      </p>

      <p>
        🔎 Clue 2:
        The day is the 6th.
      </p>

      <p>
        🔎 Clue 3:
        The year ends in 22.
      </p>

    </div>

    <input
      id="lockInput"
      inputmode="numeric"
      maxlength="6"
      placeholder="6-digit code"
    >

    <button
      class="main-btn"
      id="unlock"
    >
      🔓 UNLOCK
    </button>

    <p
      id="lockStatus"
      class="status"
    ></p>

  `;


  document
    .getElementById("unlock")
    .onclick = () => {

      const value =
        document
          .getElementById("lockInput")
          .value;


      if (value === "060722") {

        completeGame(
          350,
          250
        );

      } else {

        document
          .getElementById("lockStatus")
          .textContent =
          "❌ Not quite. Check the clues!";

      }

    };

}


/* =========================================================
   16. CUPID SHOOTOUT
========================================================= */

function cupidShootout() {

  gameTitle.textContent =
    "🏹 Cupid Shootout";


  let hits = 0;

  let shots = 0;


  gameArea.innerHTML = `

    <p>
      Hit 10 targets!
    </p>

    <p id="shootStatus">
      Hits: 0 / 10
    </p>

    <div
      class="fall-area"
      id="shootArea"
    ></div>

  `;


  const area =
    document.getElementById("shootArea");


  function target() {

    if (
      shots >= 20 ||
      hits >= 10
    )
      return;


    shots++;


    const button =
      document.createElement("button");

    button.className =
      "falling";


    const roll =
      Math.random();


    button.textContent =
      roll < .15
        ? "💎"
        : roll < .35
        ? "💔"
        : "💖";


    button.style.left =
      Math.random() * 80 + "%";

    button.style.top =
      Math.random() * 80 + "%";


    area.appendChild(button);


    later(() => {

      if (button.parentNode)
        button.remove();

    }, 1200);


    button.onclick = () => {

      if (
        button.textContent ===
        "💔"
      ) {

        score =
          Math.max(
            0,
            score - 75
          );

      } else {

        hits++;

        document
          .getElementById("shootStatus")
          .textContent =
          `Hits: ${hits} / 10`;


        if (hits >= 10) {

          completeGame(
            300,
            180
          );

        }

      }


      button.remove();

    };

  }


  gameTimer =
    setInterval(target, 600);

}


/* =========================================================
   17. COUNTDOWN
========================================================= */

function countdownGame() {

  gameTitle.textContent =
    "⏳ The Countdown";


  const questions = [

    [
      "Pick the lucky number",
      "3",
      ["3","8","4","9"]
    ],

    [
      "Pick Lulu's favourite animal",
      "Dolphin",
      ["Cat","Dolphin","Horse","Fox"]
    ],

    [
      "Pick the flower she likes",
      "Sunflower",
      ["Rose","Lily","Sunflower","Daisy"]
    ],

    [
      "Pick the colour she loves",
      "Baby pink",
      ["Red","Baby pink","Orange","Green"]
    ],

    [
      "Pick the movie",
      "Me Before You",
      [
        "Frozen",
        "Me Before You",
        "Cars",
        "Shrek"
      ]
    ]

  ];


  let round = 0;

  let correct = 0;


  function show() {

    if (round >= 5) {

      completeGame(
        200 + correct * 30,
        120
      );

      return;

    }


    let seconds = 5;

    let done = false;


    const q =
      questions[round];


    gameArea.innerHTML = `

      <p>
        Round ${round + 1} / 5
      </p>

      <h2 id="count">
        ⏱️ ${seconds}
      </h2>

      <h3>
        ${q[0]}
      </h3>

      <div
        class="choice-grid"
        id="countChoices"
      ></div>

    `;


    [...q[2]]
      .sort(() => Math.random() - .5)
      .forEach(answer => {

        const button =
          document.createElement("button");

        button.className =
          "choice";

        button.textContent =
          answer;


        button.onclick = () => {

          if (done)
            return;

          done = true;

          clearInterval(gameTimer);


          if (
            answer === q[1]
          )
            correct++;


          round++;

          later(
            show,
            300
          );

        };


        document
          .getElementById("countChoices")
          .appendChild(button);

      });


    gameTimer =
      setInterval(() => {

        if (done)
          return;

        seconds--;


        const counter =
          document.getElementById("count");


        if (counter)
          counter.textContent =
            `⏱️ ${seconds}`;


        if (seconds <= 0) {

          clearInterval(gameTimer);

          done = true;

          round++;

          later(
            show,
            300
          );

        }

      }, 1000);

  }


  show();

}


/* =========================================================
   18. ULTIMATE GAMBLE
========================================================= */

function ultimateGamble() {

  gameTitle.textContent =
    "🎰 Ultimate Gamble";


  let bank = 1000;

  let round = 0;


  function show() {

    if (round >= 6) {

      score +=
        Math.floor(bank / 2);


      completeGame(
        Math.min(
          500,
          Math.floor(bank / 3)
        ),
        Math.floor(bank / 10)
      );

      return;

    }


    gameArea.innerHTML = `

      <div class="bank">
        💰 Bank: ${bank}
      </div>

      <p>
        Choose your risk.
      </p>

      <div class="choice-grid">

        <button
          class="choice"
          id="safe"
        >
          🟢 SAFE<br>
          Small win
        </button>

        <button
          class="choice"
          id="risky"
        >
          🟡 RISKY<br>
          Bigger win
        </button>

        <button
          class="choice"
          id="crazy"
        >
          🔴 CRAZY<br>
          Huge win
        </button>

        <button
          class="choice"
          id="allin"
        >
          🟣 ALL IN<br>
          Everything
        </button>

      </div>

      <p
        id="gambleStatus"
        class="status"
      ></p>

    `;


    function gamble(type) {

      let change;


      if (type === "safe") {

        change =
          Math.floor(
            Math.random() * 150
          ) + 50;

      }

      else if (type === "risky") {

        change =
          Math.random() < .65
            ? 300
            : -150;

      }

      else if (type === "crazy") {

        change =
          Math.random() < .5
            ? 700
            : -400;

      }

      else {

        change =
          Math.random() < .45
            ? bank
            : -bank;

      }


      bank =
        Math.max(
          0,
          bank + change
        );


      round++;


      document
        .getElementById("gambleStatus")
        .textContent =
        change >= 0
          ? `WIN +${change}! 🎉`
          : `LOSS ${change} 💔`;


      later(
        show,
        500
      );

    }


    document
      .getElementById("safe")
      .onclick =
      () => gamble("safe");


    document
      .getElementById("risky")
      .onclick =
      () => gamble("risky");


    document
      .getElementById("crazy")
      .onclick =
      () => gamble("crazy");


    document
      .getElementById("allin")
      .onclick =
      () => gamble("allin");

  }


  show();

}


/* =========================================================
   19. ADMIRER'S LAST STAND
========================================================= */

function admirersLastStand() {

  gameTitle.textContent =
    "💘 Admirer's Last Stand";


  let enemy = 5;

  let health = 5;

  let round = 0;


  function render() {

    if (enemy <= 0) {

      completeGame(
        400,
        250
      );

      return;

    }


    if (health <= 0) {

      completeGame(
        150,
        80
      );

      return;

    }


    round++;


    gameArea.innerHTML = `

      <p>
        Round ${round}
      </p>

      <p>
        Admirer:
        ${"❤️".repeat(enemy)}
      </p>

      <p>
        You:
        ${"💗".repeat(health)}
      </p>

      <div class="choice-grid">

        <button
          class="choice"
          id="attack"
        >
          💘 ATTACK
        </button>

        <button
          class="choice"
          id="defend"
        >
          🛡️ DEFEND
        </button>

        <button
          class="choice"
          id="charm"
        >
          ✨ CHARM
        </button>

      </div>

    `;


    document
      .getElementById("attack")
      .onclick = () => {

        enemy -= 2;

        if (
          Math.random() < .4
        )
          health--;

        render();

      };


    document
      .getElementById("defend")
      .onclick = () => {

        health =
          Math.min(
            5,
            health + 1
          );

        render();

      };


    document
      .getElementById("charm")
      .onclick = () => {

        if (
          Math.random() < .7
        ) {

          enemy--;

        } else {

          health--;

        }

        render();

      };

  }


  render();

}


/* =========================================================
   20. WORD FIND
========================================================= */

function wordFind() {

  gameTitle.textContent =
    "🔎 Liliana's Word Find";


  const words = [

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


  const SIZE = 10;

  const grid =
    Array(SIZE * SIZE).fill("");


  const placed = [];


  const directions = [

    [0,1],
    [0,-1],
    [1,0],
    [-1,0],
    [1,1],
    [1,-1],
    [-1,1],
    [-1,-1]

  ];


  function placeWord(word) {

    for (
      let attempt = 0;
      attempt < 1000;
      attempt++
    ) {

      const direction =
        directions[
          Math.floor(
            Math.random() *
            directions.length
          )
        ];


      const row =
        Math.floor(
          Math.random() * SIZE
        );


      const col =
        Math.floor(
          Math.random() * SIZE
        );


      const cells = [];

      let valid = true;


      for (
        let i = 0;
        i < word.length;
        i++
      ) {

        const r =
          row +
          direction[0] * i;

        const c =
          col +
          direction[1] * i;


        if (
          r < 0 ||
          r >= SIZE ||
          c < 0 ||
          c >= SIZE
        ) {

          valid = false;

          break;

        }


        const position =
          r * SIZE + c;


        if (
          grid[position] &&
          grid[position] !== word[i]
        ) {

          valid = false;

          break;

        }


        cells.push(position);

      }


      if (valid) {

        cells.forEach(
          (position, i) => {

            grid[position] =
              word[i];

          }
        );


        placed.push({
          word,
          cells
        });


        return true;

      }

    }


    return false;

  }


  [...words]
    .sort(
      (a,b) =>
        b.length - a.length
    )
    .forEach(placeWord);


  const alphabet =
    "ABCDEFGHIJKLMNOPQRSTUVWXYZ";


  for (
    let i = 0;
    i < grid.length;
    i++
  ) {

    if (!grid[i]) {

      grid[i] =
        alphabet[
          Math.floor(
            Math.random() *
            alphabet.length
          )
        ];

    }

  }


  gameArea.innerHTML = `

    <p>
      Find all 10 words.
    </p>

    <div
      class="word-list"
      id="wordList"
    ></div>

    <div
      class="word-grid"
      id="wordGrid"
    ></div>

    <p
      id="wordStatus"
      class="status"
    >
      Tap letters in order.
    </p>

  `;


  words.forEach(word => {

    const span =
      document.createElement("span");

    span.className =
      "word";

    span.id =
      "word-" + word;

    span.textContent =
      word;


    document
      .getElementById("wordList")
      .appendChild(span);

  });


  let selected = [];

  let found = 0;


  grid.forEach((letter, index) => {

    const button =
      document.createElement("button");

    button.className =
      "letter";

    button.textContent =
      letter;


    button.onclick = () => {

      if (
        button.classList.contains("found")
      )
        return;


      selected.push({
        index,
        button
      });


      button.classList.add(
        "selected"
      );


      const sequence =
        selected
          .map(item =>
            grid[item.index]
          )
          .join("");


      const reverse =
        sequence
          .split("")
          .reverse()
          .join("");


      const match =
        placed.find(item => {

          const wordElement =
            document.getElementById(
              "word-" + item.word
            );


          if (
            wordElement.classList.contains(
              "done"
            )
          )
            return false;


          return (
            sequence === item.word ||
            reverse === item.word
          );

        });


      if (match) {

        selected.forEach(item => {

          item.button.classList.remove(
            "selected"
          );

          item.button.classList.add(
            "found"
          );

        });


        document
          .getElementById(
            "word-" + match.word
          )
          .classList.add("done");


        found++;

        selected = [];


        document
          .getElementById("wordStatus")
          .textContent =
          `Found ${found} / 10`;


        if (found >= 10) {

          completeGame(
            400,
            250
          );

        }

      }


      if (
        selected.length >= 10
      ) {

        selected.forEach(item =>
          item.button.classList.remove(
            "selected"
          )
        );

        selected = [];

      }

    };


    document
      .getElementById("wordGrid")
      .appendChild(button);

  });

}


/* =========================================================
   21. DRAW A SUNFLOWER
========================================================= */

function drawSunflower() {

  gameTitle.textContent =
    "🌻 Draw a Sunflower";


  gameArea.innerHTML = `

    <p>
      Draw your own sunflower!
    </p>

    <canvas
      id="drawCanvas"
      width="360"
      height="360"
    ></canvas>

    <button
      class="main-btn secondary"
      id="clearDraw"
    >
      CLEAR
    </button>

    <button
      class="main-btn"
      id="finishDraw"
    >
      🌻 I'M DONE
    </button>

    <p
      id="drawStatus"
      class="status"
    ></p>

  `;


  const canvas =
    document.getElementById(
      "drawCanvas"
    );


  const ctx =
    canvas.getContext("2d");


  ctx.lineWidth = 6;

  ctx.lineCap = "round";

  ctx.strokeStyle =
    "#6b3454";


  let drawing = false;

  let strokes = 0;


  function getPosition(event) {

    const rect =
      canvas.getBoundingClientRect();


    return {

      x:
        (event.clientX - rect.left) *
        canvas.width /
        rect.width,

      y:
        (event.clientY - rect.top) *
        canvas.height /
        rect.height

    };

  }


  canvas.addEventListener(
    "pointerdown",
    event => {

      drawing = true;

      strokes++;


      const position =
        getPosition(event);


      ctx.beginPath();

      ctx.moveTo(
        position.x,
        position.y
      );

    }
  );


  canvas.addEventListener(
    "pointermove",
    event => {

      if (!drawing)
        return;


      const position =
        getPosition(event);


      ctx.lineTo(
        position.x,
        position.y
      );

      ctx.stroke();

    }
  );


  canvas.addEventListener(
    "pointerup",
    () => {

      drawing = false;

    }
  );


  canvas.addEventListener(
    "pointercancel",
    () => {

      drawing = false;

    }
  );


  document
    .getElementById("clearDraw")
    .onclick = () => {

      ctx.clearRect(
        0,
        0,
        canvas.width,
        canvas.height
      );

      strokes = 0;

    };


  document
    .getElementById("finishDraw")
    .onclick = () => {

      if (strokes < 5) {

        document
          .getElementById("drawStatus")
          .textContent =
          "Draw a little more first! 🌻";

        return;

      }


      completeGame(
        350,
        220
      );

    };

}


/* =========================================================
   22. LULU DERBY
========================================================= */

function luluDerby() {

  gameTitle.textContent =
    "🏇 Lulu Derby";


  gameArea.innerHTML = `

    <h3>
      Choose your animal
    </h3>

    <div
      class="animal-grid"
      id="animals"
    ></div>

    <h3>
      Choose difficulty
    </h3>

    <div
      class="choice-grid"
      id="difficulty"
    ></div>

  `;


  let chosen = null;


  const animals = [

    ["🐎","Horse"],
    ["🦄","Unicorn"],
    ["🐬","Dolphin"],
    ["🦋","Butterfly"],
    ["🐰","Bunny"],
    ["🦊","Fox"]

  ];


  animals.forEach(animal => {

    const button =
      document.createElement("button");

    button.className =
      "animal";

    button.innerHTML =
      `${animal[0]}
       <small>${animal[1]}</small>`;


    button.onclick = () => {

      chosen = animal;


      document
        .querySelectorAll(".animal")
        .forEach(
          item =>
            item.style.outline =
            "none"
        );


      button.style.outline =
        "3px solid #ff9ac7";

    };


    document
      .getElementById("animals")
      .appendChild(button);

  });


  [
    "EASY",
    "MEDIUM",
    "HARD",
    "EXPERT"
  ].forEach(level => {

    const button =
      document.createElement("button");

    button.className =
      "choice";

    button.textContent =
      level;


    button.onclick = () => {

      if (!chosen) {

        alert(
          "Choose an animal first! 🐬"
        );

        return;

      }


      derbyRace(
        chosen,
        level
      );

    };


    document
      .getElementById("difficulty")
      .appendChild(button);

  });

}


/* =========================================================
   DERBY RACE
========================================================= */

function derbyRace(
  animal,
  difficulty
) {

  gameTitle.textContent =
    "🏇 Lulu Derby";


  const rules = {

    EASY: {
      rounds: 5,
      move: 25,
      rival: 12,
      stamina: 6
    },

    MEDIUM: {
      rounds: 6,
      move: 22,
      rival: 15,
      stamina: 5
    },

    HARD: {
      rounds: 7,
      move: 20,
      rival: 17,
      stamina: 4
    },

    EXPERT: {
      rounds: 8,
      move: 18,
      rival: 19,
      stamina: 3
    }

  };


  const rule =
    rules[difficulty];


  let you = 0;

  let rival = 0;

  let stamina =
    rule.stamina;

  let round = 0;


  function render() {

    if (
      round >=
      rule.rounds
    ) {

      const win =
        you > rival;


      if (win) {

        const points =
          difficulty === "EXPERT"
            ? 500
            : difficulty === "HARD"
            ? 450
            : difficulty === "MEDIUM"
            ? 400
            : 350;


        completeGame(
          points,
          250
        );

      } else {

        gameArea.innerHTML = `

          <div class="reward">
            😱
          </div>

          <h2>
            So close!
          </h2>

          <p>
            ${animal[0]}
            finished at
            ${you}%.
          </p>

          <p>
            Rival:
            ${rival}%.
          </p>

          <button
            class="main-btn"
            id="tryDerby"
          >
            TRY AGAIN
          </button>

        `;


        document
          .getElementById("tryDerby")
          .onclick =
          () =>
            derbyRace(
              animal,
              difficulty
            );

      }


      return;

    }


    gameArea.innerHTML = `

      <p>
        ${animal[0]}
        ${animal[1]}
      </p>

      <p>
        ${difficulty}
      </p>

      <p>
        Round
        ${round + 1}
        /
        ${rule.rounds}
      </p>


      <div class="race-track">

        <div class="racer">

          ${animal[0]}

          <span
            style="
              left:${Math.min(90,you)}%
            "
          >
            🏇
          </span>

        </div>


        <div class="racer">

          😈

          <span
            style="
              left:${Math.min(90,rival)}%
            "
          >
            🏇
          </span>

        </div>

      </div>


      <p>
        ⚡ Stamina: ${stamina}
      </p>


      <div class="choice-grid">

        <button
          class="choice"
          id="dRun"
        >
          🏃 RUN
        </button>

        <button
          class="choice"
          id="dBoost"
        >
          ⚡ BOOST
        </button>

        <button
          class="choice"
          id="dRest"
        >
          😴 REST
        </button>

      </div>

    `;


    document
      .getElementById("dRun")
      .onclick = () => {

        you += rule.move;

        rival += rule.rival;

        round++;

        render();

      };


    document
      .getElementById("dBoost")
      .onclick = () => {

        if (stamina > 0) {

          stamina--;

          you +=
            rule.move + 10;

        } else {

          you += 5;

        }


        rival += rule.rival;

        round++;

        render();

      };


    document
      .getElementById("dRest")
      .onclick = () => {

        stamina =
          Math.min(
            rule.stamina,
            stamina + 2
          );

        you += 7;

        rival += rule.rival;

        round++;

        render();

      };

  }


  render();

}


/* =========================================================
   23. FINAL CHALLENGE
========================================================= */

const finalQuestions = [

  [
    "What is Liliana's favourite number?",
    "3",
    ["3","5","7","9"]
  ],

  [
    "What is her favourite food?",
    "Sushi",
    ["Pizza","Sushi","Tacos","Pasta"]
  ],

  [
    "What animal does she love?",
    "Dolphins",
    ["Dolphins","Cats","Horses","Foxes"]
  ],

  [
    "What colour does she love?",
    "Baby pink",
    ["Baby pink","Purple","Red","Green"]
  ],

  [
    "What flowers does she like?",
    "Sunflowers and roses",
    [
      "Tulips",
      "Sunflowers and roses",
      "Lilies",
      "Daisies"
    ]
  ],

  [
    "What is her star sign?",
    "Leo",
    ["Leo","Aries","Cancer","Libra"]
  ],

  [
    "What did she study?",
    "Psychology",
    [
      "Psychology",
      "Law",
      "Nursing",
      "Art"
    ]
  ],

  [
    "How many siblings does she have?",
    "5",
    ["3","4","5","6"]
  ],

  [
    "How many nephews does she have?",
    "4",
    ["2","3","4","5"]
  ],

  [
    "How many nieces does she have?",
    "1",
    ["1","2","3","4"]
  ],

  [
    "What are her dogs called?",
    "Aayla and Arlo",
    [
      "Aayla and Arlo",
      "Luna and Max",
      "Milo and Coco",
      "Bella and Arlo"
    ]
  ],

  [
    "What colour are her eyes?",
    "Green",
    ["Blue","Brown","Green","Hazel"]
  ],

  [
    "What movie does she like?",
    "Me Before You",
    [
      "Titanic",
      "Me Before You",
      "Frozen",
      "The Notebook"
    ]
  ],

  [
    "What does she enjoy?",
    "Sad songs and poetry",
    [
      "Comedy",
      "Sad songs and poetry",
      "Only podcasts",
      "Action films"
    ]
  ],

  [
    "What does she want someday?",
    "A baby girl",
    [
      "A baby boy",
      "A baby girl",
      "Twins",
      "No children"
    ]
  ],

  [
    "How many years have you been best friends?",
    "6",
    ["4","5","6","7"]
  ],

  [
    "Which animal is connected to her favourite?",
    "Dolphin",
    ["Dolphin","Lion","Koala","Panda"]
  ],

  [
    "Which flower is one she likes?",
    "Rose",
    ["Rose","Orchid","Lily","Daffodil"]
  ],

  [
    "Which personality description fits her?",
    "Caring",
    ["Caring","Cold","Unfriendly","Quiet"]
  ],

  [
    "Which game does she enjoy?",
    "Poker",
    ["Golf","Poker","Fishing","Cycling"]
  ],

  [
    "Which subject is connected to her university study?",
    "Psychology",
    [
      "Physics",
      "Psychology",
      "Chemistry",
      "Engineering"
    ]
  ],

  [
    "What kind of writing does she like?",
    "Poetry",
    [
      "Poetry",
      "Manuals",
      "Reports",
      "News"
    ]
  ],

  [
    "Which flower has a sunny name?",
    "Sunflower",
    [
      "Sunflower",
      "Rose",
      "Lily",
      "Orchid"
    ]
  ],

  [
    "Which animal lives in the ocean?",
    "Dolphin",
    [
      "Dolphin",
      "Fox",
      "Horse",
      "Bunny"
    ]
  ],

  [
    "What colour is associated with her favourite aesthetic?",
    "Baby pink",
    [
      "Baby pink",
      "Black",
      "Orange",
      "Brown"
    ]
  ],

  [
    "What number is special to her?",
    "3",
    ["3","8","1","6"]
  ],

  [
    "What kind of songs does she enjoy?",
    "Sad songs",
    [
      "Sad songs",
      "Only rap",
      "Only classical",
      "Only rock"
    ]
  ],

  [
    "What kind of writing does she like?",
    "Poetry",
    [
      "Poetry",
      "Manuals",
      "Reports",
      "News"
    ]
  ],

  [
    "What film is a favourite?",
    "Me Before You",
    [
      "Me Before You",
      "Cars",
      "Avatar",
      "Shrek"
    ]
  ],

  [
    "What is her eye colour?",
    "Green",
    ["Green","Blue","Grey","Brown"]
  ],

  [
    "What is her favourite animal?",
    "Dolphin",
    [
      "Dolphin",
      "Penguin",
      "Tiger",
      "Horse"
    ]
  ],

  [
    "What did she study at university?",
    "Psychology",
    [
      "Psychology",
      "Biology",
      "Music",
      "Business"
    ]
  ],

  [
    "How many siblings does she have?",
    "5",
    ["4","5","6","7"]
  ],

  [
    "How many nephews does she have?",
    "4",
    ["1","2","4","6"]
  ],

  [
    "How many nieces does she have?",
    "1",
    ["1","2","4","5"]
  ],

  [
    "What colour does Liliana love?",
    "Baby pink",
    [
      "Blue",
      "Baby pink",
      "Green",
      "Red"
    ]
  ],

  [
    "What is Liliana's favourite food?",
    "Sushi",
    [
      "Sushi",
      "Pizza",
      "Rice",
      "Pasta"
    ]
  ],

  [
    "How many dogs does she have?",
    "2",
    ["1","2","3","4"]
  ],

  [
    "What is one of her dogs called?",
    "Aayla",
    ["Aayla","Lola","Mika","Luna"]
  ],

  [
    "What is her other dog's name?",
    "Arlo",
    ["Arlo","Aayla","Ayla","Luna"]
  ],

  [
    "How many piercings does she have?",
    "4",
    ["2","3","4","5"]
  ],

  [
    "What is one thing she is afraid of?",
    "Drowning",
    [
      "Heights",
      "Drowning",
      "Flying",
      "Spiders"
    ]
  ],

  [
    "What kind of game does she like?",
    "Poker",
    [
      "Poker",
      "Chess",
      "Golf",
      "Cricket"
    ]
  ],

  [
    "What does she want to be someday?",
    "A mum",
    [
      "A pilot",
      "A mum",
      "A lawyer",
      "A singer"
    ]
  ],

  [
    "Which flower is one of her favourites?",
    "Sunflower",
    [
      "Sunflower",
      "Iris",
      "Carnation",
      "Violet"
    ]
  ],

  [
    "Which animal is associated with her favourite animal?",
    "Dolphin",
    [
      "Dolphin",
      "Wolf",
      "Bear",
      "Rabbit"
    ]
  ],

  [
    "What is her favourite colour?",
    "Baby pink",
    [
      "Baby pink",
      "Burgundy",
      "Yellow",
      "Orange"
    ]
  ],

  [
    "What is her zodiac sign?",
    "Leo",
    [
      "Leo",
      "Gemini",
      "Capricorn",
      "Virgo"
    ]
  ],

  [
    "What is one of her favourite flowers?",
    "Rose",
    [
      "Rose",
      "Orchid",
      "Lily",
      "Daffodil"
    ]
  ],

  [
    "What does she enjoy listening to?",
    "Sad songs",
    [
      "Sad songs",
      "Only rap",
      "Only rock",
      "Only country"
    ]
  ],

  [
    "What subject did she study?",
    "Psychology",
    [
      "Psychology",
      "Physics",
      "Music",
      "Engineering"
    ]
  ],

  [
    "What food does she love?",
    "Sushi",
    [
      "Sushi",
      "Pizza",
      "Steak",
      "Pasta"
    ]
  ]

];


function finalChallenge() {

  gameTitle.textContent =
    "🏆 Final Challenge";


  const questions =
    [...finalQuestions]
      .sort(() => Math.random() - .5)
      .slice(0, 50);


  let index = 0;

  let correct = 0;


  function showQuestion() {

    if (index >= 50) {

      const finalPoints =
        correct * 70;


      score += finalPoints;

      tokens +=
        correct * 15;


      finishJourney();

      return;

    }


    const question =
      questions[index];


    gameArea.innerHTML = `

      <p>
        FINAL CHALLENGE
      </p>

      <p>
        Question
        ${index + 1}
        / 50
      </p>

      <div
        class="final-question"
      >
        ${question[0]}
      </div>

      <div
        class="choice-grid"
        id="finalChoices"
      ></div>

      <p
        id="finalStatus"
        class="status"
      ></p>

    `;


    [...question[2]]
      .sort(() => Math.random() - .5)
      .forEach(answer => {

        const button =
          document.createElement("button");

        button.className =
          "choice";

        button.textContent =
          answer;


        button.onclick = () => {

          if (
            answer ===
            question[1]
          ) {

            correct++;

            document
              .getElementById("finalStatus")
              .textContent =
              "Correct! 💗";

          } else {

            document
              .getElementById("finalStatus")
              .textContent =
              "Not quite! 💔";

          }


          document
            .querySelectorAll(
              "#finalChoices button"
            )
            .forEach(
              item =>
                item.disabled = true
            );


          index++;


          later(
            showQuestion,
            250
          );

        };


        document
          .getElementById("finalChoices")
          .appendChild(button);

      });

  }


  showQuestion();

}


/* =========================================================
   FINISH
========================================================= */

function finishJourney() {

  clearTimers();

  showScreen("finish");


  const privateCall =
    score > 3000;


  document
    .getElementById("finishText")
    .innerHTML = `

      You made it through all
      23 levels,
      ${escapeHTML(player)}! 💗

      <br><br>

      Final score:
      <strong>${score}</strong>

    `;


  document
    .getElementById("rewardBox")
    .innerHTML =

    privateCall

      ? `

        <div
          class="card"
          style="
            height:auto;
            max-height:none;
            padding:12px;
          "
        >

          <div class="reward">
            💌📞
          </div>

          <h2>
            PRIVATE CALL UNLOCKED!
          </h2>

          <p>
            You scored
            <strong>${score}</strong>.
          </p>

          <p>
            You needed more than
            3000 points and you did it! 💗
          </p>

        </div>

      `

      : `

        <div
          class="card"
          style="
            height:auto;
            max-height:none;
            padding:12px;
          "
        >

          <div class="reward">
            💗
          </div>

          <h2>
            YOU DID IT!
          </h2>

          <p>
            You finished the whole journey.
          </p>

          <p>
            Final score:
            <strong>${score}</strong>
          </p>

          <p>
            Keep this little universe forever.
          </p>

        </div>

      `;

}


/* =========================================================
   MUSIC
========================================================= */

function toggleMusic() {

  musicOn =
    !musicOn;


  document
    .getElementById("musicText")
    .textContent =
    `Music: ${musicOn ? "ON" : "OFF"}`;


  if (musicOn) {

    if (!audioCtx) {

      audioCtx =
        new (
          window.AudioContext ||
          window.webkitAudioContext
        )();

    }


    playTone(
      523,
      .15
    );

  }

}


function playTone(
  frequency,
  duration
) {

  if (!musicOn)
    return;


  if (!audioCtx) {

    audioCtx =
      new (
        window.AudioContext ||
        window.webkitAudioContext
      )();

  }


  const oscillator =
    audioCtx.createOscillator();


  const gain =
    audioCtx.createGain();


  oscillator.frequency.value =
    frequency;

  oscillator.type =
    "sine";


  gain.gain.setValueAtTime(
    .035,
    audioCtx.currentTime
  );


  gain.gain.exponentialRampToValueAtTime(
    .001,
    audioCtx.currentTime +
    duration
  );


  oscillator.connect(gain);

  gain.connect(
    audioCtx.destination
  );


  oscillator.start();

  oscillator.stop(
    audioCtx.currentTime +
    duration
  );

}


/* =========================================================
   RESET
========================================================= */

function resetJourney() {

  clearTimers();


  score = 0;

  tokens = 0;

  currentLevel = 1;

  player = "";


  document
    .getElementById("playerName")
    .value = "";


  document
    .getElementById("playerName")
    .placeholder =
    "Enter your name";


  showScreen("start");

}

</script>

</body>
</html>

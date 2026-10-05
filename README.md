<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport"
      content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<meta name="theme-color" content="#e9a9c5">
<title>Lulu Express 💗</title>
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
  font-family: Arial, Helvetica, sans-serif;
  background: #120b16;
  color: white;
  touch-action: manipulation;
}
body {
  overflow-x: hidden;
}
button,
input {
  font: inherit;
}
button {
  border: 0;
  cursor: pointer;
  touch-action: manipulation;
}
#app {
  min-height: 100vh;
  width: 100%;
  position: relative;
  overflow: hidden;
}
.screen {
  min-height: 100vh;
  width: 100%;
  display: none;
  padding: 22px 16px;
  position: relative;
  overflow-x: hidden;
}
.screen.active {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.bg {
  background:
    radial-gradient(circle at 15% 15%, rgba(255,190,220,.22), transparent 25%),
    radial-gradient(circle at 85% 20%, rgba(190,150,255,.18), transparent 25%),
    radial-gradient(circle at 50% 90%, rgba(255,180,210,.14), transparent 30%),
    linear-gradient(145deg, #130b19, #241126 50%, #100912);
}
.start-wrap {
  width: 100%;
  max-width: 520px;
  margin: auto;
  text-align: center;
}
.logo {
  font-size: clamp(42px, 12vw, 72px);
  margin-bottom: 4px;
}
h1 {
  margin: 0 0 8px;
  font-size: clamp(30px, 8vw, 50px);
}
h2 {
  margin: 0 0 12px;
  font-size: clamp(25px, 7vw, 38px);
}
p {
  line-height: 1.5;
}
.subtitle {
  color: #f5c7dc;
  font-size: 17px;
  margin: 8px auto 24px;
  max-width: 430px;
}
.card {
  width: 100%;
  max-width: 520px;
  background: rgba(255,255,255,.08);
  border: 1px solid rgba(255,255,255,.14);
  border-radius: 24px;
  padding: 20px;
  box-shadow: 0 15px 45px rgba(0,0,0,.25);
}
.name-input {
  width: 100%;
  min-height: 52px;
  border-radius: 16px;
  border: 2px solid rgba(255,255,255,.18);
  background: rgba(0,0,0,.25);
  color: white;
  padding: 12px 15px;
  font-size: 17px;
  outline: none;
}
.name-input:focus {
  border-color: #f2a8ca;
}
.primary,
.secondary,
.danger {
  width: 100%;
  min-height: 50px;
  border-radius: 16px;
  margin-top: 12px;
  font-weight: 800;
  font-size: 16px;
  padding: 12px 18px;
}
.primary {
  background: #ef9fc5;
  color: #301323;
}
.secondary {
  background: rgba(255,255,255,.12);
  color: white;
  border: 1px solid rgba(255,255,255,.16);
}
.danger {
  background: #b95a78;
  color: white;
}
.primary:active,
.secondary:active,
.danger:active,
.choice:active,
.animal:active,
.difficulty:active {
  transform: scale(.97);
}
.music-button {
  width: auto;
  min-width: 170px;
  margin: 0 auto 10px;
}
.error {
  min-height: 24px;
  color: #ffb7c9;
  font-weight: 700;
  margin-top: 8px;
}
.journey-head {
  width: 100%;
  max-width: 650px;
  text-align: center;
  margin-bottom: 16px;
}
.level-number {
  color: #f3abc9;
  font-weight: 800;
  letter-spacing: 1px;
}
.game-area {
  width: 100%;
  max-width: 650px;
  margin: auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.game-card {
  width: 100%;
  background: rgba(255,255,255,.075);
  border: 1px solid rgba(255,255,255,.13);
  border-radius: 24px;
  padding: 18px;
}
.game-instruction {
  color: #ead7e1;
  text-align: center;
  margin: 4px auto 18px;
  max-width: 500px;
}
.status {
  text-align: center;
  min-height: 28px;
  margin: 10px 0;
  font-weight: 800;
  color: #f7b7d4;
}
.choices {
  display: grid;
  grid-template-columns: 1fr;
  gap: 10px;
}
.choice {
  width: 100%;
  min-height: 50px;
  border-radius: 15px;
  background: rgba(255,255,255,.10);
  color: white;
  padding: 12px;
  border: 1px solid rgba(255,255,255,.13);
  font-weight: 700;
  text-align: left;
}
.choice.correct {
  background: #47866a;
}
.choice.wrong {
  background: #984d62;
}
.big-number {
  font-size: clamp(55px, 16vw, 90px);
  font-weight: 900;
  text-align: center;
  margin: 12px 0;
}
.progress {
  width: 100%;
  height: 10px;
  background: rgba(255,255,255,.12);
  border-radius: 99px;
  overflow: hidden;
  margin: 10px 0 18px;
}
.progress-bar {
  height: 100%;
  width: 0%;
  background: #ef9fc5;
  transition: width .2s;
}
.tap-button {
  width: min(230px, 70vw);
  aspect-ratio: 1;
  border-radius: 50%;
  background: #ef9fc5;
  color: #351526;
  font-size: 22px;
  font-weight: 900;
  margin: 15px auto;
  display: block;
}
.memory-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 8px;
  max-width: 420px;
  margin: auto;
}
.memory-card {
  aspect-ratio: 1;
  border-radius: 12px;
  background: #2d1930;
  color: transparent;
  font-size: 25px;
  font-weight: 900;
}
.memory-card.revealed,
.memory-card.matched {
  color: white;
  background: #754263;
}
.lock-input {
  text-align: center;
  letter-spacing: 8px;
  font-size: 25px;
}
.word-grid {
  display: grid;
  grid-template-columns: repeat(8, 1fr);
  gap: 4px;
  max-width: 420px;
  margin: auto;
}
.word-cell {
  aspect-ratio: 1;
  border-radius: 5px;
  background: rgba(255,255,255,.09);
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 800;
  font-size: clamp(12px, 4vw, 18px);
  user-select: none;
}
.word-cell.selected {
  background: #c36f96;
}
.animal-grid,
.difficulty-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 10px;
}
.animal,
.difficulty {
  min-height: 80px;
  border-radius: 17px;
  background: rgba(255,255,255,.09);
  color: white;
  padding: 10px;
  font-weight: 800;
  border: 1px solid rgba(255,255,255,.12);
}
.animal.selected,
.difficulty.selected {
  background: #8d4d6d;
  border-color: #f2aac9;
}
.animal-icon {
  font-size: 32px;
  display: block;
  margin-bottom: 5px;
}
.derby-track {
  width: 100%;
  background: rgba(255,255,255,.07);
  border-radius: 18px;
  padding: 12px;
  margin-top: 10px;
}
.runner {
  display: flex;
  align-items: center;
  gap: 8px;
  margin: 8px 0;
}
.runner-label {
  width: 75px;
  font-size: 13px;
  flex-shrink: 0;
}
.track {
  flex: 1;
  height: 28px;
  background: rgba(255,255,255,.10);
  border-radius: 99px;
  overflow: hidden;
}
.runner-fill {
  height: 100%;
  width: 5%;
  background: #ef9fc5;
  border-radius: 99px;
  transition: width .12s linear;
}
.reward {
  font-size: 48px;
  text-align: center;
  margin: 10px;
}
.score-box {
  text-align: center;
  font-size: 20px;
  margin: 12px 0;
}
.final-big {
  font-size: clamp(34px, 10vw, 60px);
  font-weight: 900;
  text-align: center;
}
canvas {
  display: block;
  width: 100%;
  max-width: 460px;
  height: auto;
  aspect-ratio: 1 / 1;
  background: #fffafc;
  border-radius: 20px;
  margin: 10px auto;
  touch-action: none;
}
@media (min-width: 600px) {
  .choices {
    grid-template-columns: 1fr 1fr;
  }
  .screen {
    padding: 32px;
  }
}
</style>
</head>
<body>
<div id="app">
  <!-- START -->
  <section id="startScreen" class="screen active bg">
    <div class="start-wrap">
      <div class="logo">💗</div>
      <h1>Lulu Express</h1>
      <p class="subtitle">
        A little adventure made especially for Lulu.
        23 levels. One journey. One very special person.
      </p>
      <div class="card">
        <button id="musicBtn" class="secondary music-button">
          🎵 Music: OFF
        </button>
        <label for="playerName">Your name</label>
        <input
          id="playerName"
          class="name-input"
          type="text"
          maxlength="30"
          placeholder="Enter your name"
          autocomplete="off"
        >
        <div id="startError" class="error"></div>
        <button id="startBtn" class="primary">
          💗 START THE JOURNEY
        </button>
      </div>
    </div>
  </section>
  <!-- JOURNEY INTRO -->
  <section id="introScreen" class="screen bg">
    <div class="start-wrap">
      <div class="logo">🌸</div>
      <h1>The Journey Begins</h1>
      <p id="introText" class="subtitle"></p>
      <div class="card">
        <p>
          There are 23 levels waiting for you.
          Complete each one to unlock the next.
        </p>
        <button id="beginGameBtn" class="primary">
          START LEVEL 1
        </button>
      </div>
    </div>
  </section>
  <!-- GAME -->
  <section id="gameScreen" class="screen bg">
    <div class="journey-head">
      <div id="levelNumber" class="level-number"></div>
      <h2 id="gameTitle"></h2>
    </div>
    <div class="game-area">
      <div id="gameCard" class="game-card"></div>
    </div>
  </section>
  <!-- COMPLETE -->
  <section id="completeScreen" class="screen bg">
    <div class="start-wrap">
      <div class="reward">💗</div>
      <h1>Level Complete!</h1>
      <p id="completeText" class="subtitle"></p>
      <div class="card">
        <button id="nextBtn" class="primary">NEXT LEVEL →</button>
      </div>
    </div>
  </section>
  <!-- FINAL -->
  <section id="finalScreen" class="screen bg">
    <div class="start-wrap">
      <div class="reward">🏆</div>
      <div class="final-big">JOURNEY COMPLETE!</div>
      <p id="finalText" class="subtitle"></p>
      <div class="card">
        <div id="finalScore" class="score-box"></div>
        <div id="finalTokens" class="score-box"></div>
        <p style="text-align:center;">
          You made it through all 23 levels. 💗
        </p>
        <button id="resetBtn" class="danger">
          🔄 RESET JOURNEY
        </button>
      </div>
    </div>
  </section>
</div>
<script>
(function () {
  "use strict";
  const app = document.getElementById("app");
  const screens = {
    start: document.getElementById("startScreen"),
    intro: document.getElementById("introScreen"),
    game: document.getElementById("gameScreen"),
    complete: document.getElementById("completeScreen"),
    final: document.getElementById("finalScreen")
  };
  const gameCard = document.getElementById("gameCard");
  const gameTitle = document.getElementById("gameTitle");
  const levelNumber = document.getElementById("levelNumber");
  const completeText = document.getElementById("completeText");
  let playerName = "";
  let level = 0;
  let score = 0;
  let tokens = 0;
  let musicOn = false;
  let gameTimer = null;
  let animationFrame = null;
  const TOTAL_LEVELS = 23;
  const levels = [
    {
      title: "Broken Hearts",
      type: "broken"
    },
    {
      title: "Memory Vault",
      type: "memory"
    },
    {
      title: "Pressure Quiz",
      type: "pressure"
    },
    {
      title: "High Roller",
      type: "roller"
    },
    {
      title: "Mind Games",
      type: "mind"
    },
    {
      title: "The Bluff",
      type: "bluff"
    },
    {
      title: "Survival Round",
      type: "survival"
    },
    {
      title: "Admirer Race",
      type: "admirer"
    },
    {
      title: "Heartbreak Chamber",
      type: "chamber"
    },
    {
      title: "Heartbreak Boxing Match",
      type: "boxing"
    },
    {
      title: "Perfect Match",
      type: "match"
    },
    {
      title: "Who Knows Liliana Best?",
      type: "quiz"
    },
    {
      title: "Reaction Gauntlet",
      type: "reaction"
    },
    {
      title: "Heart Hunt",
      type: "hunt"
    },
    {
      title: "Love Lock",
      type: "lock"
    },
    {
      title: "Cupid Shootout",
      type: "cupid"
    },
    {
      title: "The Countdown",
      type: "countdown"
    },
    {
      title: "Ultimate Gamble",
      type: "gamble"
    },
    {
      title: "Admirer's Last Stand",
      type: "laststand"
    },
    {
      title: "Liliana's Word Find",
      type: "wordfind"
    },
    {
      title: "Draw a Sunflower",
      type: "sunflower"
    },
    {
      title: "Lulu Derby",
      type: "derby"
    },
    {
      title: "Final Challenge",
      type: "finalquiz"
    }
  ];
  /*
   * FINAL 50 QUESTION BANK
   * Correct answers are shuffled every time the quiz starts.
   */
  const quizQuestions = [
    ["What is Liliana's favourite number?", ["3", "7", "5", "9"], "3"],
    ["What is Liliana's favourite colour?", ["Baby pink", "Burgundy", "Baby blue", "Purple"], "Baby pink"],
    ["What food does Liliana love?", ["Sushi", "Pizza", "Pasta", "Burgers"], "Sushi"],
    ["Which animal is one of Liliana's favourites?", ["Dolphins", "Penguins", "Koalas", "Tigers"], "Dolphins"],
    ["Which flower does Liliana love?", ["Sunflowers", "Tulips", "Lilies", "Daisies"], "Sunflowers"],
    ["Which other flower is one of Liliana's favourites?", ["Roses", "Orchids", "Lavender", "Daffodils"], "Roses"],
    ["What is Liliana's favourite movie?", ["Me Before You", "The Notebook", "Titanic", "The Fault in Our Stars"], "Me Before You"],
    ["What did Liliana study at university?", ["Psychology", "Law", "Nursing", "Business"], "Psychology"],
    ["What is Liliana's zodiac sign?", ["Leo", "Cancer", "Libra", "Aries"], "Leo"],
    ["What colour are Liliana's eyes?", ["Green", "Brown", "Blue", "Hazel"], "Green"],
    ["How many siblings does Liliana have?", ["5", "3", "4", "6"], "5"],
    ["How many nieces does Liliana have?", ["1", "2", "3", "4"], "1"],
    ["How many nephews does Liliana have?", ["4", "2", "5", "3"], "4"],
    ["How many piercings does Liliana have?", ["4", "2", "3", "5"], "4"],
    ["What are Liliana's dogs called?", ["Aayla and Arlo", "Luna and Milo", "Bella and Arlo", "Aayla and Luna"], "Aayla and Arlo"],
    ["What is Liliana afraid of?", ["Drowning", "Flying", "Heights", "Spiders"], "Drowning"],
    ["What does Liliana dream of becoming one day?", ["A mum to a baby girl", "A famous singer", "A professional dancer", "A world traveller"], "A mum to a baby girl"],
    ["What type of songs does Liliana like?", ["Sad songs", "Country songs", "Heavy metal", "Classical music"], "Sad songs"],
    ["What type of writing does Liliana enjoy?", ["Poetry", "Novels", "News articles", "Biographies"], "Poetry"],
    ["Which game or activity is Liliana known to enjoy?", ["Poker", "Golf", "Chess", "Bowling"], "Poker"],
    ["What kind of activity does Liliana enjoy besides poker?", ["Gambling", "Fishing", "Hiking", "Cooking"], "Gambling"],
    ["How long have Bree and Liliana been best friends?", ["6 years", "4 years", "5 years", "8 years"], "6 years"],
    ["Which pair contains both of Liliana's favourite flowers?", ["Sunflowers and roses", "Roses and lilies", "Tulips and sunflowers", "Daisies and roses"], "Sunflowers and roses"],
    ["Which pair contains both of Liliana's dogs?", ["Aayla and Arlo", "Arlo and Milo", "Aayla and Bella", "Luna and Arlo"], "Aayla and Arlo"],
    ["Which pair correctly combines Liliana's favourite colour and food?", ["Baby pink and sushi", "Purple and pizza", "Baby blue and pasta", "Burgundy and sushi"], "Baby pink and sushi"],
    ["Which pair correctly combines Liliana's favourite animal and flower?", ["Dolphins and sunflowers", "Tigers and roses", "Koalas and tulips", "Penguins and lilies"], "Dolphins and sunflowers"],
    ["Which pair correctly combines Liliana's university subject and favourite movie?", ["Psychology and Me Before You", "Law and Titanic", "Nursing and The Notebook", "Business and The Fault in Our Stars"], "Psychology and Me Before You"],
    ["Which pair correctly combines Liliana's music and writing interests?", ["Sad songs and poetry", "Country music and novels", "Classical music and biographies", "Rock music and journalism"], "Sad songs and poetry"],
    ["Which pair correctly combines Liliana's zodiac sign and eye colour?", ["Leo and green", "Aries and blue", "Cancer and brown", "Libra and hazel"], "Leo and green"],
    ["Which pair correctly combines Liliana's family numbers?", ["1 niece and 4 nephews", "2 nieces and 3 nephews", "1 niece and 5 nephews", "3 nieces and 4 nephews"], "1 niece and 4 nephews"],
    ["Which pair correctly combines Liliana's sibling count and piercings?", ["5 siblings and 4 piercings", "4 siblings and 5 piercings", "6 siblings and 3 piercings", "3 siblings and 4 piercings"], "5 siblings and 4 piercings"],
    ["Which statement about Liliana's favourites is correct?", ["She loves sushi and dolphins", "She loves pizza and tigers", "She loves pasta and penguins", "She loves burgers and koalas"], "She loves sushi and dolphins"],
    ["Which statement about Liliana's flowers is correct?", ["She likes sunflowers and roses", "She likes tulips and lilies", "She likes daisies and orchids", "She likes lavender and tulips"], "She likes sunflowers and roses"],
    ["Which statement about Liliana's pets is correct?", ["She has dogs named Aayla and Arlo", "She has cats named Aayla and Arlo", "She has dogs named Luna and Milo", "She has rabbits named Aayla and Bella"], "She has dogs named Aayla and Arlo"],
    ["Which statement about Liliana's education is correct?", ["She studied Psychology at university", "She studied Law at university", "She studied Nursing at university", "She studied Business at university"], "She studied Psychology at university"],
    ["Which statement about Liliana's future dream is correct?", ["She wants to be a mum to a baby girl", "She wants to become a professional athlete", "She wants to become a pilot", "She wants to become a chef"], "She wants to be a mum to a baby girl"],
    ["Which statement about Liliana's personality interests is correct?", ["She likes sad songs and poetry", "She dislikes music and writing", "She only likes comedy films", "She prefers only documentaries"], "She likes sad songs and poetry"],
    ["Which statement about Liliana's games is correct?", ["She enjoys poker and gambling", "She dislikes all games", "She only enjoys football", "She only enjoys board games"], "She enjoys poker and gambling"],
    ["Which statement about Liliana's family is correct?", ["She has 5 siblings", "She has 2 siblings", "She has 7 siblings", "She has 1 sibling"], "She has 5 siblings"],
    ["Which statement about Liliana's eyes is correct?", ["Her eyes are green", "Her eyes are blue", "Her eyes are brown", "Her eyes are hazel"], "Her eyes are green"],
    ["Which statement about Liliana's zodiac sign is correct?", ["She is a Leo", "She is a Virgo", "She is a Taurus", "She is a Gemini"], "She is a Leo"],
    ["Which statement about Liliana's favourite film is correct?", ["Me Before You is her favourite movie", "Titanic is her favourite movie", "The Notebook is her favourite movie", "Frozen is her favourite movie"], "Me Before You is her favourite movie"],
    ["Which statement correctly connects Liliana's fear with something she loves?", ["She is afraid of drowning and loves dolphins", "She is afraid of heights and loves mountains", "She is afraid of spiders and loves insects", "She is afraid of flying and loves aeroplanes"], "She is afraid of drowning and loves dolphins"],
    ["Which statement correctly connects Liliana's favourite number with her zodiac sign?", ["3 and Leo", "7 and Leo", "3 and Aries", "5 and Cancer"], "3 and Leo"],
    ["Which statement correctly connects Liliana's favourite food with her favourite film?", ["Sushi and Me Before You", "Pizza and Titanic", "Pasta and The Notebook", "Burgers and Frozen"], "Sushi and Me Before You"],
    ["Which statement correctly connects Liliana's flowers with her favourite colour?", ["Sunflowers, roses and baby pink", "Tulips, lilies and purple", "Daisies, orchids and blue", "Lavender, roses and burgundy"], "Sunflowers, roses and baby pink"],
    ["Which statement correctly connects Liliana's dogs with her family?", ["Aayla and Arlo, with 1 niece and 4 nephews", "Luna and Milo, with 2 nieces and 3 nephews", "Bella and Arlo, with 3 nieces and 2 nephews", "Aayla and Luna, with 4 nieces and 1 nephew"], "Aayla and Arlo, with 1 niece and 4 nephews"],
    ["Which statement correctly connects Liliana's university subject with her favourite type of writing?", ["Psychology and poetry", "Law and journalism", "Nursing and novels", "Business and biographies"], "Psychology and poetry"],
    ["Which statement correctly connects Liliana's best-friend history with her favourite number?", ["6 years of friendship and favourite number 3", "4 years of friendship and favourite number 7", "5 years of friendship and favourite number 9", "8 years of friendship and favourite number 5"], "6 years of friendship and favourite number 3"],
    ["Which statement correctly brings together Liliana's favourite colour, food and animal?", ["Baby pink, sushi and dolphins", "Purple, pizza and tigers", "Blue, pasta and koalas", "Burgundy, burgers and penguins"], "Baby pink, sushi and dolphins"]
  ];
  function shuffle(array) {
    const copy = array.slice();
    for (let i = copy.length - 1; i > 0; i--) {
      const j = Math.floor(Math.random() * (i + 1));
      [copy[i], copy[j]] = [copy[j], copy[i]];
    }
    return copy;
  }
  function clearGameSystems() {
    if (gameTimer !== null) {
      clearInterval(gameTimer);
      clearTimeout(gameTimer);
      gameTimer = null;
    }
    if (animationFrame !== null) {
      cancelAnimationFrame(animationFrame);
      animationFrame = null;
    }
  }
  function showScreen(name) {
    Object.values(screens).forEach(screen => {
      screen.classList.remove("active");
    });
    screens[name].classList.add("active");
    window.scrollTo(0, 0);
  }
  function finishLevel(message, points = 100, tokenReward = 100) {
    clearGameSystems();
    score += Math.max(0, points);
    tokens += Math.max(0, tokenReward);
    completeText.textContent =
      message || "You completed this level!";
    showScreen("complete");
  }
  function renderLevel() {
    clearGameSystems();
    if (level >= TOTAL_LEVELS) {
      finishJourney();
      return;
    }
    const current = levels[level];
    levelNumber.textContent =
      "LEVEL " + (level + 1) + " OF " + TOTAL_LEVELS;
    gameTitle.textContent = current.title;
    gameCard.innerHTML = "";
    showScreen("game");
    switch (current.type) {
      case "broken": gameBroken(); break;
      case "memory": gameMemory(); break;
      case "pressure": gamePressure(); break;
      case "roller": gameHighRoller(); break;
      case "mind": gameMind(); break;
      case "bluff": gameBluff(); break;
      case "survival": gameSurvival(); break;
      case "admirer": gameAdmirerRace(); break;
      case "chamber": gameChamber(); break;
      case "boxing": gameBoxing(); break;
      case "match": gamePerfectMatch(); break;
      case "quiz": gameQuiz(); break;
      case "reaction": gameReaction(); break;
      case "hunt": gameHeartHunt(); break;
      case "lock": gameLoveLock(); break;
      case "cupid": gameCupid(); break;
      case "countdown": gameCountdown(); break;
      case "gamble": gameGamble(); break;
      case "laststand": gameLastStand(); break;
      case "wordfind": gameWordFind(); break;
      case "sunflower": gameSunflower(); break;
      case "derby": gameDerby(); break;
      case "finalquiz": gameFinalQuiz(); break;
      default:
        finishLevel();
    }
  }
  function makeButton(text, callback, className = "primary") {
    const button = document.createElement("button");
    button.type = "button";
    button.textContent = text;
    button.className = className;
    button.addEventListener("click", callback);
    return button;
  }
  function makeInstruction(text) {
    const p = document.createElement("p");
    p.className = "game-instruction";
    p.textContent = text;
    return p;
  }
  /* LEVEL 1 */
  function gameBroken() {
    gameCard.appendChild(
      makeInstruction("Tap every broken heart to repair the heart. Repair 8 hearts to win.")
    );
    const area = document.createElement("div");
    area.style.display = "grid";
    area.style.gridTemplateColumns = "repeat(4,1fr)";
    area.style.gap = "10px";
    let fixed = 0;
    for (let i = 0; i < 8; i++) {
      const b = makeButton("💔", () => {
        if (b.disabled) return;
        b.disabled = true;
        b.textContent = "❤️";
        fixed++;
        if (fixed === 8) {
          finishLevel("Every broken heart was repaired. ❤️", 100, 100);
        }
      }, "choice");
      b.style.textAlign = "center";
      b.style.fontSize = "30px";
      area.appendChild(b);
    }
    gameCard.appendChild(area);
  }
  /* LEVEL 2 */
  function gameMemory() {
    gameCard.appendChild(
      makeInstruction("Find all 4 matching pairs. Tap two cards at a time.")
    );
    const values = shuffle(["🌸","🌸","💗","💗","⭐","⭐","🦋","🦋"]);
    const grid = document.createElement("div");
    grid.className = "memory-grid";
    let first = null;
    let locked = false;
    let matches = 0;
    values.forEach((value, index) => {
      const card = document.createElement("button");
      card.type = "button";
      card.className = "memory-card";
      card.textContent = value;
      card.dataset.value = value;
      card.dataset.index = index;
      card.addEventListener("click", () => {
        if (
          locked ||
          card.classList.contains("revealed") ||
          card.classList.contains("matched")
        ) return;
        card.classList.add("revealed");
        if (!first) {
          first = card;
          return;
        }
        if (first.dataset.value === card.dataset.value) {
          first.classList.add("matched");
          card.classList.add("matched");
          first = null;
          matches++;
          if (matches === 4) {
            finishLevel("The memory vault has been unlocked! 🔐", 120, 120);
          }
        } else {
          locked = true;
          const oldFirst = first;
          setTimeout(() => {
            oldFirst.classList.remove("revealed");
            card.classList.remove("revealed");
            first = null;
            locked = false;
          }, 550);
        }
      });
      grid.appendChild(card);
    });
    gameCard.appendChild(grid);
  }
  /* LEVEL 3 */
  function gamePressure() {
    const questions = [
      ["Liliana's favourite colour?", ["Baby pink","Purple","Burgundy","Blue"], "Baby pink"],
      ["Liliana's favourite food?", ["Sushi","Pizza","Pasta","Rice"], "Sushi"],
      ["Liliana's favourite animal?", ["Dolphins","Cats","Horses","Koalas"], "Dolphins"],
      ["Liliana's zodiac sign?", ["Leo","Cancer","Aries","Libra"], "Leo"],
      ["Liliana's favourite number?", ["3","5","7","9"], "3"]
    ];
    let index = 0;
    let answered = false;
    const title = document.createElement("h3");
    title.style.textAlign = "center";
    const status = document.createElement("div");
    status.className = "status";
    const choices = document.createElement("div");
    choices.className = "choices";
    gameCard.appendChild(makeInstruction("Five quick questions. Choose one answer for each."));
    gameCard.appendChild(title);
    gameCard.appendChild(choices);
    gameCard.appendChild(status);
    function showQuestion() {
      answered = false;
      const q = questions[index];
      title.textContent =
        (index + 1) + " / " + questions.length + " — " + q[0];
      choices.innerHTML = "";
      shuffle(q[1]).forEach(answer => {
        const button = makeButton(answer, () => {
          if (answered) return;
          answered = true;
          if (answer === q[2]) {
            button.classList.add("correct");
            status.textContent = "Correct! 💗";
            setTimeout(() => {
              index++;
              if (index >= questions.length) {
                finishLevel("Pressure quiz conquered! 🔥", 150, 150);
              } else {
                showQuestion();
              }
            }, 450);
          } else {
            button.classList.add("wrong");
            status.textContent = "Not quite. Try this question again.";
            setTimeout(() => {
              button.classList.remove("wrong");
              status.textContent = "";
              answered = false;
            }, 600);
          }
        }, "choice");
        choices.appendChild(button);
      });
    }
    showQuestion();
  }
  /* LEVEL 4 */
  function gameHighRoller() {
    gameCard.appendChild(
      makeInstruction("Pick one of three mystery cards. One card contains the winning roll.")
    );
    const result = document.createElement("div");
    result.className = "big-number";
    result.textContent = "🎰";
    const choices = document.createElement("div");
    choices.className = "choices";
    const winner = Math.floor(Math.random() * 3);
    ["CARD 1","CARD 2","CARD 3"].forEach((name, i) => {
      choices.appendChild(
        makeButton(name, () => {
          if (i === winner) {
            result.textContent = "🎉";
            finishLevel("High roller! You hit the winning card.", 150, 150);
          } else {
            result.textContent = "🎲";
          }
        }, "choice")
      );
    });
    gameCard.appendChild(result);
    gameCard.appendChild(choices);
  }
  /* LEVEL 5 */
  function gameMind() {
    gameCard.appendChild(
      makeInstruction("Remember the pattern. Then tap the buttons in the same order.")
    );
    const pattern = shuffle([1,2,3,4]).slice(0,4);
    const display = document.createElement("div");
    display.className = "big-number";
    display.textContent = pattern.join(" ");
    gameCard.appendChild(display);
    const buttons = document.createElement("div");
    buttons.className = "choices";
    let input = [];
    setTimeout(() => {
      display.textContent = "Now!";
    }, 1800);
    [1,2,3,4].forEach(n => {
      buttons.appendChild(
        makeButton(String(n), () => {
          input.push(n);
          if (input[input.length - 1] !== pattern[input.length - 1]) {
            input = [];
            display.textContent = "Try again!";
            setTimeout(() => display.textContent = "Now!", 500);
            return;
          }
          if (input.length === pattern.length) {
            finishLevel("Perfect memory and focus! 🧠", 150, 150);
          }
        }, "choice")
      );
    });
    gameCard.appendChild(buttons);
  }
  /* LEVEL 6 */
  function gameBluff() {
    gameCard.appendChild(
      makeInstruction("Three cards are shown. Find the Queen. There is no penalty for trying again.")
    );
    const choices = document.createElement("div");
    choices.className = "choices";
    let winner = Math.floor(Math.random() * 3);
    for (let i = 0; i < 3; i++) {
      choices.appendChild(
        makeButton("🂠 CARD " + (i + 1), () => {
          if (i === winner) {
            finishLevel("You saw straight through the bluff! 🃏", 160, 160);
          }
        }, "choice")
      );
    }
    gameCard.appendChild(choices);
  }
  /* LEVEL 7 */
  function gameSurvival() {
    gameCard.appendChild(
      makeInstruction("Survive 10 rounds. Tap the safe heart each round.")
    );
    let round = 0;
    const status = document.createElement("div");
    status.className = "status";
    const choices = document.createElement("div");
    choices.className = "choices";
    gameCard.appendChild(status);
    gameCard.appendChild(choices);
    function next() {
      round++;
      if (round > 10) {
        finishLevel("You survived the whole round! 💗", 160, 160);
        return;
      }
      status.textContent = "Round " + round + " of 10";
      choices.innerHTML = "";
      const safe = Math.floor(Math.random() * 3);
      for (let i = 0; i < 3; i++) {
        choices.appendChild(
          makeButton("❤️", () => {
            if (i === safe) {
              next();
            } else {
              status.textContent = "That one was dangerous! Pick again.";
            }
          }, "choice")
        );
      }
    }
    next();
  }
  /* LEVEL 8 */
  function gameAdmirerRace() {
    gameCard.appendChild(
      makeInstruction("Tap the button 20 times before your admirer reaches the finish.")
    );
    let taps = 0;
    let enemy = 0;
    const progress = document.createElement("div");
    progress.className = "progress";
    const bar = document.createElement("div");
    bar.className = "progress-bar";
    progress.appendChild(bar);
    const status = document.createElement("div");
    status.className = "status";
    const button = makeButton("💗 TAP!", () => {
      taps++;
      bar.style.width = Math.min(100, taps * 5) + "%";
      if (taps >= 20) {
        finishLevel("You reached the finish first! 🏁", 170, 170);
      }
    }, "tap-button");
    gameCard.appendChild(progress);
    gameCard.appendChild(status);
    gameCard.appendChild(button);
    gameTimer = setInterval(() => {
      enemy += 1;
      if (enemy >= 19 && taps < 20) {
        enemy = 0;
        taps = Math.max(0, taps - 2);
        status.textContent = "Keep going! 💗";
      }
    }, 500);
  }
  /* LEVEL 9 */
  function gameChamber() {
    gameCard.appendChild(
      makeInstruction("The chamber has 5 doors. One door leads out. Try as many as you need.")
    );
    const choices = document.createElement("div");
    choices.className = "choices";
    const winner = Math.floor(Math.random() * 5);
    for (let i = 0; i < 5; i++) {
      choices.appendChild(
        makeButton("🚪 Door " + (i + 1), () => {
          if (i === winner) {
            finishLevel("You escaped the heartbreak chamber! 💗", 170, 170);
          }
        }, "choice")
      );
    }
    gameCard.appendChild(choices);
  }
  /* LEVEL 10 */
  function gameBoxing() {
    gameCard.appendChild(
      makeInstruction("Land 12 heart punches. Tap the punch button whenever it is ready.")
    );
    let punches = 0;
    const status = document.createElement("div");
    status.className = "status";
    status.textContent = "0 / 12";
    const button = makeButton("🥊 ❤️", () => {
      punches++;
      status.textContent = punches + " / 12";
      if (punches >= 12) {
        finishLevel("You won the heartbreak boxing match! 🥊", 180, 180);
      }
    }, "tap-button");
    gameCard.appendChild(status);
    gameCard.appendChild(button);
  }
  /* LEVEL 11 */
  function gamePerfectMatch() {
    gameCard.appendChild(
      makeInstruction("Choose the item that belongs with the heart.")
    );
    const choices = document.createElement("div");
    choices.className = "choices";
    const correct = "💗 + 🌸";
    shuffle([
      correct,
      "💗 + 🔥",
      "💗 + 🌧️",
      "💗 + 🪨"
    ]).forEach(answer => {
      choices.appendChild(
        makeButton(answer, () => {
          if (answer === correct) {
            finishLevel("Perfect match! 🌸", 180, 180);
          }
        }, "choice")
      );
    });
    gameCard.appendChild(choices);
  }
  /* LEVEL 12 */
  function gameQuiz() {
    const questions = [
      ["Favourite number?", ["3","5","7","9"], "3"],
      ["Favourite animal?", ["Dolphins","Cats","Horses","Foxes"], "Dolphins"],
      ["Favourite colour?", ["Baby pink","Purple","Blue","Green"], "Baby pink"],
      ["Favourite food?", ["Sushi","Pizza","Pasta","Burgers"], "Sushi"]
    ];
    runSimpleQuiz(questions, "You really know Lulu! 💗", 200);
  }
  /* LEVEL 13 */
  function gameReaction() {
    gameCard.appendChild(
      makeInstruction("Wait for the heart to appear, then tap it. Do this 5 times.")
    );
    let round = 0;
    let ready = false;
    const button = makeButton("WAIT…", () => {
      if (!ready) return;
      round++;
      ready = false;
      if (round >= 5) {
        finishLevel("Lightning-fast reactions! ⚡", 180, 180);
        return;
      }
      button.textContent = "WAIT…";
      setTimeout(() => {
        ready = true;
        button.textContent = "💗 TAP!";
      }, 500 + Math.random() * 900);
    }, "tap-button");
    gameCard.appendChild(button);
    setTimeout(() => {
      ready = true;
      button.textContent = "💗 TAP!";
    }, 800);
  }
  /* LEVEL 14 */
  function gameHeartHunt() {
    gameCard.appendChild(
      makeInstruction("Find and tap 10 hidden hearts.")
    );
    const area = document.createElement("div");
    area.style.display = "grid";
    area.style.gridTemplateColumns = "repeat(5,1fr)";
    area.style.gap = "7px";
    let found = 0;
    for (let i = 0; i < 25; i++) {
      const button = makeButton("·", () => {
        if (button.disabled) return;
        button.disabled = true;
        if (Math.random() < .45 || found >= 7) {
          button.textContent = "❤️";
          found++;
          if (found >= 10) {
            finishLevel("You found every hidden heart! 💗", 190, 190);
          }
        } else {
          button.textContent = "·";
        }
      }, "choice");
      button.style.textAlign = "center";
      button.style.fontSize = "25px";
      area.appendChild(button);
    }
    gameCard.appendChild(area);
  }
  /* LEVEL 15 */
  function gameLoveLock() {
    gameCard.appendChild(
      makeInstruction("Enter the love-lock code: 060722")
    );
    const input = document.createElement("input");
    input.className = "name-input lock-input";
    input.type = "tel";
    input.inputMode = "numeric";
    input.maxLength = 6;
    input.placeholder = "••••••";
    const status = document.createElement("div");
    status.className = "status";
    const button = makeButton("🔐 UNLOCK", () => {
      if (input.value === "060722") {
        finishLevel("The Love Lock is open! 🔓💗", 200, 200);
      } else {
        status.textContent = "That code didn't work. Try again.";
      }
    });
    gameCard.appendChild(input);
    gameCard.appendChild(button);
    gameCard.appendChild(status);
  }
  /* LEVEL 16 */
  function gameCupid() {
    gameCard.appendChild(
      makeInstruction("Cupid needs 10 successful shots. Tap the target.")
    );
    let shots = 0;
    const status = document.createElement("div");
    status.className = "status";
    status.textContent = "0 / 10";
    const button = makeButton("🎯 💗", () => {
      shots++;
      status.textContent = shots + " / 10";
      if (shots >= 10) {
        finishLevel("Cupid's aim is perfect! 🏹", 190, 190);
      }
    }, "tap-button");
    gameCard.appendChild(status);
    gameCard.appendChild(button);
  }
  /* LEVEL 17 */
  function gameCountdown() {
    gameCard.appendChild(
      makeInstruction("Tap when the countdown reaches 1. You have 3 attempts.")
    );
    const number = document.createElement("div");
    number.className = "big-number";
    number.textContent = "5";
    const button = makeButton("WAIT", () => {
      if (number.textContent === "1") {
        finishLevel("Perfect countdown timing! ⏱️", 200, 200);
      }
    }, "tap-button");
    gameCard.appendChild(number);
    gameCard.appendChild(button);
    let n = 5;
    gameTimer = setInterval(() => {
      n--;
      if (n <= 0) {
        n = 5;
      }
      number.textContent = String(n);
      button.textContent = n === 1 ? "💗 TAP NOW!" : "WAIT";
    }, 800);
  }
  /* LEVEL 18 */
  function gameGamble() {
    gameCard.appendChild(
      makeInstruction("Choose whether to play it safe or gamble. Get 3 wins to finish.")
    );
    let wins = 0;
    const status = document.createElement("div");
    status.className = "status";
    status.textContent = "Wins: 0 / 3";
    const choices = document.createElement("div");
    choices.className = "choices";
    const safe = makeButton("💗 PLAY SAFE", () => {
      wins++;
      status.textContent = "Wins: " + wins + " / 3";
      if (wins >= 3) {
        finishLevel("You played the perfect hand! 🎰", 220, 220);
      }
    }, "choice");
    const gamble = makeButton("🔥 GAMBLE", () => {
      if (Math.random() < .65) {
        wins++;
        status.textContent = "Wins: " + wins + " / 3";
      } else {
        status.textContent = "The gamble missed! Try again.";
      }
      if (wins >= 3) {
        finishLevel("The ultimate gamble paid off! 🎰", 220, 220);
      }
    }, "choice");
    choices.appendChild(safe);
    choices.appendChild(gamble);
    gameCard.appendChild(status);
    gameCard.appendChild(choices);
  }
  /* LEVEL 19 */
  function gameLastStand() {
    gameCard.appendChild(
      makeInstruction("Defend your heart 8 times. Tap BLOCK whenever the attack appears.")
    );
    let blocks = 0;
    const status = document.createElement("div");
    status.className = "status";
    status.textContent = "0 / 8";
    const button = makeButton("🛡️ BLOCK", () => {
      blocks++;
      status.textContent = blocks + " / 8";
      if (blocks >= 8) {
        finishLevel("Your heart survived the last stand! 🛡️", 220, 220);
      }
    }, "tap-button");
    gameCard.appendChild(status);
    gameCard.appendChild(button);
  }
  /* LEVEL 20 */
  function gameWordFind() {
    const target = "LULU";
    const letters = [
      "L","U","L","U","A","B","C","D",
      "E","F","G","H","I","J","K","M",
      "N","O","P","Q","R","S","T","V",
      "W","X","Y","Z","L","U","L","U",
      "A","R","O","S","E","S","D","O",
      "L","P","H","A","I","N","K","S",
      "S","U","N","F","L","O","W","E",
      "R","D","O","L","P","H","I","N","S"
    ];
    gameCard.appendChild(
      makeInstruction("Find LULU four times. Tap letters in order: L → U → L → U.")
    );
    const grid = document.createElement("div");
    grid.className = "word-grid";
    let progress = "";
    let found = 0;
    shuffle(letters).slice(0, 64).forEach(letter => {
      const cell = document.createElement("button");
      cell.type = "button";
      cell.className = "word-cell";
      cell.textContent = letter;
      cell.addEventListener("click", () => {
        if (cell.disabled) return;
        const expected = target[progress.length];
        if (letter === expected) {
          cell.classList.add("selected");
          cell.disabled = true;
          progress += letter;
          if (progress === target) {
            found++;
            progress = "";
            if (found >= 4) {
              finishLevel("You found Lulu hidden in the word find! 🔎", 220, 220);
            }
          }
        }
      });
      grid.appendChild(cell);
    });
    gameCard.appendChild(grid);
  }
  /* LEVEL 21 */
  function gameSunflower() {
    gameCard.appendChild(
      makeInstruction("Draw a simple sunflower. Tap DRAW when you are happy with it.")
    );
    const canvas = document.createElement("canvas");
    canvas.width = 500;
    canvas.height = 500;
    const ctx = canvas.getContext("2d");
    ctx.lineWidth = 7;
    ctx.lineCap = "round";
    ctx.strokeStyle = "#6b3b4d";
    let drawing = false;
    function position(event) {
      const rect = canvas.getBoundingClientRect();
      return {
        x: (event.clientX - rect.left) * (canvas.width / rect.width),
        y: (event.clientY - rect.top) * (canvas.height / rect.height)
      };
    }
    canvas.addEventListener("pointerdown", event => {
      drawing = true;
      const p = position(event);
      ctx.beginPath();
      ctx.moveTo(p.x, p.y);
      canvas.setPointerCapture(event.pointerId);
    });
    canvas.addEventListener("pointermove", event => {
      if (!drawing) return;
      const p = position(event);
      ctx.lineTo(p.x, p.y);
      ctx.stroke();
    });
    canvas.addEventListener("pointerup", () => {
      drawing = false;
    });
    canvas.addEventListener("pointercancel", () => {
      drawing = false;
    });
    const buttons = document.createElement("div");
    const clear = makeButton("CLEAR", () => {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
    }, "secondary");
    const done = makeButton("🌻 DRAWN!", () => {
      finishLevel("A beautiful sunflower for Lulu! 🌻", 250, 250);
    });
    buttons.appendChild(clear);
    buttons.appendChild(done);
    gameCard.appendChild(canvas);
    gameCard.appendChild(buttons);
  }
  /* LEVEL 22 */
  function gameDerby() {
    gameCard.appendChild(
      makeInstruction("Choose your animal, choose your difficulty, then race to the finish!")
    );
    const animals = [
      ["🐎","Horse"],
      ["🦄","Unicorn"],
      ["🐬","Dolphin"],
      ["🦋","Butterfly"],
      ["🐇","Bunny"],
      ["🦊","Fox"]
    ];
    const difficulties = [
      ["🌸","Easy"],
      ["💗","Medium"],
      ["🔥","Hard"],
      ["👑","Expert"]
    ];
    const animalTitle = document.createElement("h3");
    animalTitle.textContent = "Choose your animal";
    gameCard.appendChild(animalTitle);
    const animalGrid = document.createElement("div");
    animalGrid.className = "animal-grid";
    let selectedAnimal = null;
    let selectedDifficulty = null;
    animals.forEach(([icon,name]) => {
      const button = document.createElement("button");
      button.type = "button";
      button.className = "animal";
      button.innerHTML =
        '<span class="animal-icon">' + icon + '</span>' + name;
      button.addEventListener("click", () => {
        selectedAnimal = name;
        [...animalGrid.children].forEach(x =>
          x.classList.remove("selected")
        );
        button.classList.add("selected");
      });
      animalGrid.appendChild(button);
    });
    gameCard.appendChild(animalGrid);
    const difficultyTitle = document.createElement("h3");
    difficultyTitle.textContent = "Choose your difficulty";
    difficultyTitle.style.marginTop = "22px";
    gameCard.appendChild(difficultyTitle);
    const difficultyGrid = document.createElement("div");
    difficultyGrid.className = "difficulty-grid";
    difficulties.forEach(([icon,name]) => {
      const button = document.createElement("button");
      button.type = "button";
      button.className = "difficulty";
      button.innerHTML =
        '<span class="animal-icon">' + icon + '</span>' + name;
      button.addEventListener("click", () => {
        selectedDifficulty = name;
        [...difficultyGrid.children].forEach(x =>
          x.classList.remove("selected")
        );
        button.classList.add("selected");
      });
      difficultyGrid.appendChild(button);
    });
    gameCard.appendChild(difficultyGrid);
    const startRace = makeButton("🏁 START DERBY", start);
    gameCard.appendChild(startRace);
    function start() {
      if (!selectedAnimal || !selectedDifficulty) return;
      startRace.disabled = true;
      animalGrid.querySelectorAll("button").forEach(b => b.disabled = true);
      difficultyGrid.querySelectorAll("button").forEach(b => b.disabled = true);
      const settings = {
        Easy:   {distance: 80, speed: .18, opponent: .105},
        Medium: {distance: 100, speed: .16, opponent: .125},
        Hard:   {distance: 120, speed: .145, opponent: .135},
        Expert: {distance: 140, speed: .13, opponent: .142}
      };
      const config = settings[selectedDifficulty];
      gameCard.innerHTML = "";
      const chosen = document.createElement("h3");
      chosen.style.textAlign = "center";
      chosen.textContent =
        selectedAnimal + " — " + selectedDifficulty + " Derby";
      gameCard.appendChild(chosen);
      const instruction = makeInstruction(
        "Tap RUN to move your animal. Reach 100% before the opponent."
      );
      gameCard.appendChild(instruction);
      const track = document.createElement("div");
      track.className = "derby-track";
      const playerRow = document.createElement("div");
      playerRow.className = "runner";
      const playerLabel = document.createElement("div");
      playerLabel.className = "runner-label";
      playerLabel.textContent = selectedAnimal;
      const playerTrack = document.createElement("div");
      playerTrack.className = "track";
      const playerFill = document.createElement("div");
      playerFill.className = "runner-fill";
      playerTrack.appendChild(playerFill);
      playerRow.appendChild(playerLabel);
      playerRow.appendChild(playerTrack);
      const opponentRow = document.createElement("div");
      opponentRow.className = "runner";
      const opponentLabel = document.createElement("div");
      opponentLabel.className = "runner-label";
      opponentLabel.textContent = "Rival";
      const opponentTrack = document.createElement("div");
      opponentTrack.className = "track";
      const opponentFill = document.createElement("div");
      opponentFill.className = "runner-fill";
      opponentTrack.appendChild(opponentFill);
      opponentRow.appendChild(opponentLabel);
      opponentRow.appendChild(opponentTrack);
      track.appendChild(playerRow);
      track.appendChild(opponentRow);
      gameCard.appendChild(track);
      const status = document.createElement("div");
      status.className = "status";
      status.textContent = "Ready!";
      const runButton = makeButton("🏃 RUN!", () => {
        player += config.speed;
        update();
        if (player >= config.distance) {
          finishLevel(
            "🏆 " + selectedAnimal + " won the " +
            selectedDifficulty.toLowerCase() + " derby!",
            selectedDifficulty === "Expert" ? 350 : 280,
            selectedDifficulty === "Expert" ? 350 : 280
          );
        }
      }, "tap-button");
      gameCard.appendChild(status);
      gameCard.appendChild(runButton);
      let player = 0;
      let rival = 0;
      function update() {
        playerFill.style.width =
          Math.min(100, (player / config.distance) * 100) + "%";
        opponentFill.style.width =
          Math.min(100, (rival / config.distance) * 100) + "%";
      }
      gameTimer = setInterval(() => {
        rival += config.opponent;
        if (rival >= config.distance && player < config.distance) {
          rival = config.distance - 1;
          status.textContent =
            "The rival is close! Keep tapping! 💗";
        }
        update();
      }, 100);
    }
  }
  /* LEVEL 23 */
  function gameFinalQuiz() {
    gameCard.appendChild(
      makeInstruction("The Final Challenge! Answer all 50 questions about Liliana.")
    );
    runQuizBank();
  }
  function runSimpleQuiz(questions, successMessage, points) {
    let index = 0;
    const title = document.createElement("h3");
    title.style.textAlign = "center";
    const choices = document.createElement("div");
    choices.className = "choices";
    const status = document.createElement("div");
    status.className = "status";
    gameCard.appendChild(title);
    gameCard.appendChild(choices);
    gameCard.appendChild(status);
    function show() {
      const q = questions[index];
      title.textContent =
        (index + 1) + " / " + questions.length + " — " + q[0];
      choices.innerHTML = "";
      shuffle(q[1]).forEach(answer => {
        choices.appendChild(
          makeButton(answer, () => {
            if (answer === q[2]) {
              index++;
              if (index >= questions.length) {
                finishLevel(successMessage, points, points);
              } else {
                show();
              }
            } else {
              status.textContent = "Try again 💗";
              setTimeout(() => {
                status.textContent = "";
              }, 600);
            }
          }, "choice")
        );
      });
    }
    show();
  }
  function runQuizBank() {
    let questions = shuffle(quizQuestions);
    let index = 0;
    let correct = 0;
    let locked = false;
    const title = document.createElement("h3");
    title.style.textAlign = "center";
    const progress = document.createElement("div");
    progress.className = "progress";
    const progressBar = document.createElement("div");
    progressBar.className = "progress-bar";
    progress.appendChild(progressBar);
    const choices = document.createElement("div");
    choices.className = "choices";
    const status = document.createElement("div");
    status.className = "status";
    gameCard.appendChild(title);
    gameCard.appendChild(progress);
    gameCard.appendChild(choices);
    gameCard.appendChild(status);
    function showQuestion() {
      locked = false;
      const q = questions[index];
      const answers = shuffle(q[1]);
      title.textContent =
        "Question " + (index + 1) + " of " + questions.length;
      progressBar.style.width =
        ((index / questions.length) * 100) + "%";
      choices.innerHTML = "";
      status.textContent = "";
      answers.forEach(answer => {
        const button = makeButton(answer, () => {
          if (locked) return;
          locked = true;
          if (answer === q[2]) {
            correct++;
            button.classList.add("correct");
            status.textContent = "Correct! 💗";
          } else {
            button.classList.add("wrong");
            status.textContent = "Not quite, but keep going! 💗";
          }
          setTimeout(() => {
            index++;
            if (index >= questions.length) {
              finishFinalQuiz(correct);
            } else {
              showQuestion();
            }
          }, 500);
        }, "choice");
        choices.appendChild(button);
      });
    }
    showQuestion();
  }
  function finishFinalQuiz(correct) {
    clearGameSystems();
    /*
     * The final challenge awards a strong score for every correct answer.
     * The separate website reward rule remains:
     * only a score STRICTLY GREATER THAN 3000 qualifies for the private call.
     */
    const quizPoints = correct * 70;
    score += quizPoints;
    tokens += correct * 20;
    const qualifies = score > 3000;
    const message =
      "You scored " + correct + " / 50 on the Final Challenge.";
    completeText.textContent = message;
    document.getElementById("nextBtn").textContent =
      "FINISH JOURNEY →";
    document.getElementById("nextBtn").onclick = () => {
      finishJourney(qualifies);
    };
    showScreen("complete");
  }
  function finishJourney(qualifies) {
    clearGameSystems();
    document.getElementById("finalText").textContent =
      "Well done, " + (playerName || "you") +
      ". You completed the entire Lulu Express journey. 💗";
    document.getElementById("finalScore").textContent =
      "⭐ Final score: " + score;
    document.getElementById("finalTokens").textContent =
      "🎟️ Total tokens: " + tokens;
    const oldReward = document.getElementById("privateReward");
    if (oldReward) {
      oldReward.remove();
    }
    if (qualifies === true || score > 3000) {
      const reward = document.createElement("div");
      reward.id = "privateReward";
      reward.className = "card";
      reward.style.marginTop = "15px";
      reward.innerHTML =
        "<h2>📞 Private Call Unlocked!</h2>" +
        "<p style='text-align:center;'>" +
        "Your final score is above 3000, so the special private-call reward is unlocked. 💗" +
        "</p>";
      screens.final.querySelector(".start-wrap").appendChild(reward);
    }
    showScreen("final");
  }
  /* START / RESET */
  document.getElementById("musicBtn").addEventListener("click", () => {
    musicOn = !musicOn;
    document.getElementById("musicBtn").textContent =
      musicOn ? "🎵 Music: ON" : "🎵 Music: OFF";
    /*
     * No external audio file is required.
     * The button is intentionally simple so it cannot break because
     * a remote music file disappears.
     */
  });
  document.getElementById("startBtn").addEventListener("click", () => {
    const input = document.getElementById("playerName");
    const value = input.value.trim();
    if (!value) {
      document.getElementById("startError").textContent =
        "Please enter your name first. 💗";
      input.focus();
      return;
    }
    playerName = value.slice(0, 30);
    level = 0;
    score = 0;
    tokens = 0;
    document.getElementById("introText").textContent =
      "Welcome, " + playerName +
      ". Your journey through Lulu's universe starts now. 🌸";
    showScreen("intro");
  });
  document.getElementById("beginGameBtn").addEventListener("click", () => {
    renderLevel();
  });
  document.getElementById("nextBtn").addEventListener("click", () => {
    level++;
    if (level >= TOTAL_LEVELS) {
      finishJourney();
    } else {
      renderLevel();
    }
  });
  document.getElementById("resetBtn").addEventListener("click", () => {
    clearGameSystems();
    playerName = "";
    level = 0;
    score = 0;
    tokens = 0;
    document.getElementById("playerName").value = "";
    document.getElementById("startError").textContent = "";
    document.getElementById("nextBtn").textContent =
      "NEXT LEVEL →";
    document.getElementById("nextBtn").onclick = null;
    const reward = document.getElementById("privateReward");
    if (reward) reward.remove();
    showScreen("start");
  });
})();
</script>
</body>
</html>

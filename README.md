<html lang="en">
<head>
<meta charset="UTF-8">

<meta
  name="viewport"
  content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no, viewport-fit=cover"
>

<meta name="theme-color" content="#170b13">

<title>Lulu Express 🚂💗</title>

<style>

* {
  box-sizing: border-box;
  -webkit-tap-highlight-color: transparent;
}

html,
body {
  margin: 0;
  width: 100%;
  min-height: 100%;
  overflow: hidden;
  background: #12080e;
  color: #fff;
  font-family:
    -apple-system,
    BlinkMacSystemFont,
    "Segoe UI",
    sans-serif;
  -webkit-text-size-adjust: 100%;
  touch-action: manipulation;
}

button,
input {
  font-family: inherit;
  font-size: 16px;
}

button {
  min-height: 48px;
  border: 0;
  cursor: pointer;
  touch-action: manipulation;
}

button:active {
  transform: scale(.96);
}

:root {
  --bg: #12080e;
  --panel: #26121e;
  --panel2: #321626;
  --pink: #ff7eb6;
  --pink2: #ffb1d2;
  --burgundy: #7d173f;
  --darkpink: #4b102b;
  --gold: #ffd166;
  --green: #7ee787;
  --red: #ff667d;
  --white: #fff7fb;
}

#app {
  width: 100%;
  height: 100svh;
  min-height: 100svh;
}

.screen {
  display: none;
  width: 100%;
  height: 100svh;
  min-height: 100svh;
  overflow: hidden;
  padding:
    max(12px, env(safe-area-inset-top))
    max(12px, env(safe-area-inset-right))
    max(12px, env(safe-area-inset-bottom))
    max(12px, env(safe-area-inset-left));
}

.screen.active {
  display: flex;
  flex-direction: column;
}

.scroll {
  overflow-y: auto;
  overflow-x: hidden;
  touch-action: pan-y;
  padding-bottom: 30px;
}

.center {
  align-items: center;
  justify-content: center;
  text-align: center;
}

.logo {
  font-size: clamp(30px, 8vw, 52px);
  font-weight: 900;
  color: var(--pink);
  text-shadow: 0 0 25px rgba(255,126,182,.35);
}

.subtitle {
  color: #d9a9bd;
  margin: 8px 0 25px;
}

.card {
  width: min(92vw, 620px);
  background:
    linear-gradient(
      145deg,
      rgba(255,255,255,.06),
      rgba(255,255,255,.02)
    );
  border: 1px solid rgba(255,126,182,.18);
  border-radius: 22px;
  padding: 22px;
  box-shadow: 0 20px 50px rgba(0,0,0,.35);
}

input {
  width: 100%;
  min-height: 54px;
  border-radius: 15px;
  border: 1px solid #69304c;
  background: #170b13;
  color: white;
  padding: 12px 15px;
  outline: none;
}

input:focus {
  border-color: var(--pink);
}

.primary {
  width: 100%;
  border-radius: 15px;
  background: linear-gradient(135deg,#ff6fae,#a52b61);
  color: white;
  font-weight: 800;
  margin-top: 12px;
  box-shadow: 0 10px 25px rgba(255,91,155,.2);
}

.secondary {
  width: 100%;
  border-radius: 15px;
  background: #321626;
  border: 1px solid #713652;
  color: #ffd7e8;
  font-weight: 700;
  margin-top: 10px;
}

.smallBtn {
  padding: 8px 14px;
  min-height: 42px;
  border-radius: 12px;
  background: #321626;
  color: #ffd9e9;
  border: 1px solid #69304c;
}

.topbar {
  flex-shrink: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 8px;
  padding: 4px 0 12px;
}

.topbar h1 {
  font-size: 20px;
  margin: 0;
}

.stats {
  display: flex;
  gap: 7px;
  flex-wrap: wrap;
  justify-content: flex-end;
}

.stat {
  background: #2a1420;
  border: 1px solid #54283d;
  border-radius: 10px;
  padding: 7px 9px;
  font-size: 13px;
}

.journey {
  flex: 1;
  min-height: 0;
  overflow-y: auto;
  padding: 5px 4px 35px;
}

.journey-title {
  text-align: center;
  color: var(--pink2);
  margin: 4px 0 18px;
}

.level {
  width: min(94vw, 650px);
  margin: 8px auto;
  display: grid;
  grid-template-columns: 55px 1fr auto;
  align-items: center;
  gap: 12px;
  padding: 13px;
  border-radius: 18px;
  background: #24111c;
  border: 1px solid #482235;
}

.level-number {
  width: 48px;
  height: 48px;
  display: grid;
  place-items: center;
  border-radius: 50%;
  background: #42162a;
  color: #ffc5dc;
  font-weight: 900;
}

.level.locked {
  opacity: .42;
}

.level.complete .level-number {
  background: #5d2443;
  color: #7ee787;
}

.level-name {
  font-weight: 800;
}

.level-desc {
  color: #bd8fa3;
  font-size: 12px;
  margin-top: 3px;
}

.play {
  flex: 1;
  min-height: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;
}

.game-title {
  flex-shrink: 0;
  text-align: center;
  margin: 0 0 5px;
  font-size: clamp(22px, 6vw, 32px);
}

.game-help {
  flex-shrink: 0;
  text-align: center;
  color: #d1a7b9;
  font-size: 13px;
  max-width: 650px;
  margin: 0 0 8px;
}

.game-area {
  width: min(94vw, 650px);
  flex: 1;
  min-height: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.game-card {
  width: min(94vw, 600px);
  max-height: 100%;
  background: #24111c;
  border: 1px solid #54283d;
  border-radius: 20px;
  padding: 15px;
  overflow: hidden;
}

.message {
  text-align: center;
  color: #ffd3e5;
  min-height: 24px;
  font-weight: 700;
}

.result {
  width: min(92vw, 600px);
  text-align: center;
  background: #291321;
  border: 1px solid #67324d;
  border-radius: 22px;
  padding: 25px;
}

.result h2 {
  color: var(--pink);
  margin-top: 0;
}

.nextBtn {
  width: 100%;
  margin-top: 15px;
  background: linear-gradient(135deg,#ff72ad,#a52b61);
  color: white;
  border-radius: 15px;
  font-weight: 900;
}

/* GAME 1 */

.broken-shell {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-rows: auto minmax(220px, 1fr) auto;
  gap: 7px;
  align-items: center;
}

.broken-stats {
  display: flex;
  justify-content: center;
  gap: 12px;
  font-size: 13px;
  flex-wrap: wrap;
}

.broken-arena {
  position: relative;
  width: min(88vw, 340px);
  height: min(46svh, 300px);
  min-height: 220px;
  max-height: 300px;
  background:
    radial-gradient(circle at 50% 20%, #4b1731, #1a0b13 75%);
  border: 2px solid #69304c;
  border-radius: 22px;
  overflow: hidden;
  touch-action: none;
  user-select: none;
  box-shadow:
    inset 0 0 35px rgba(255,126,182,.08),
    0 15px 35px rgba(0,0,0,.35);
}

.broken-arena::before {
  content: "💗";
  position: absolute;
  top: 20px;
  left: 25px;
  opacity: .08;
  font-size: 50px;
}

.falling-heart {
  position: absolute;
  top: -42px;
  left: 0;
  width: 36px;
  height: 36px;
  display: grid;
  place-items: center;
  font-size: 29px;
  line-height: 1;
  pointer-events: none;
  z-index: 5;
  will-change: transform;
}

.catcher {
  position: absolute;
  bottom: 7px;
  left: 0;
  width: 29%;
  max-width: 100px;
  min-width: 76px;
  height: 32px;
  border-radius: 18px;
  background: linear-gradient(180deg,#ffb1d2,#ff5e9d);
  box-shadow: 0 0 18px rgba(255,105,164,.4);
  z-index: 10;
  transform: translateX(0);
  pointer-events: none;
}

.broken-controls {
  width: min(88vw,340px);
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
  height: 58px;
}

.move-btn {
  border-radius: 17px;
  background: #42172d;
  border: 2px solid #743554;
  color: white;
  font-size: 25px;
  font-weight: 900;
  touch-action: none;
  user-select: none;
}

.move-btn.active {
  background: #8d2451;
  border-color: var(--pink);
}

/* MEMORY */

.memory-grid {
  display: grid;
  grid-template-columns: repeat(4,1fr);
  gap: 8px;
  width: min(90vw,390px);
  margin: auto;
}

.memory-tile {
  aspect-ratio: 1;
  border-radius: 13px;
  background: #351627;
  border: 2px solid #5d2944;
  color: transparent;
  font-size: 25px;
}

.memory-tile.show,
.memory-tile.correct {
  background: #8d3158;
  color: white;
}

/* QUESTIONS */

.question-card {
  width: min(94vw,650px);
  max-height: 100%;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.question-number {
  color: var(--pink2);
  font-weight: 800;
}

.question {
  font-size: clamp(19px,5vw,27px);
  font-weight: 800;
  text-align: center;
}

.answers {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 9px;
}

.answer {
  background: #321626;
  border: 1px solid #69304c;
  color: white;
  border-radius: 14px;
  padding: 13px 8px;
  min-height: 58px;
  font-weight: 700;
}

.answer.correct {
  background: #20552e;
  border-color: #7ee787;
}

.answer.wrong {
  background: #622333;
  border-color: #ff667d;
}

.timerbar {
  width: 100%;
  height: 8px;
  border-radius: 20px;
  background: #160a10;
  overflow: hidden;
}

.timerfill {
  height: 100%;
  width: 100%;
  background: var(--pink);
}

/* SLOT */

.reels {
  display: flex;
  justify-content: center;
  gap: 8px;
  margin: 15px 0;
}

.reel {
  width: min(25vw,100px);
  height: min(25vw,100px);
  display: grid;
  place-items: center;
  background: #160a10;
  border: 2px solid #713653;
  border-radius: 18px;
  font-size: clamp(35px,10vw,55px);
}

.slot-controls {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 7px;
}

/* GENERIC BUTTON GRID */

.action-grid {
  display: grid;
  grid-template-columns: repeat(2,1fr);
  gap: 10px;
  width: min(94vw,600px);
}

.action {
  background: #321626;
  color: white;
  border: 1px solid #69304c;
  border-radius: 15px;
  padding: 14px 8px;
  font-weight: 800;
}

/* RACE */

.race-track {
  width: min(94vw,600px);
  background: #170a10;
  border-radius: 18px;
  padding: 15px;
}

.race-row {
  margin: 14px 0;
}

.race-name {
  display: flex;
  justify-content: space-between;
  margin-bottom: 5px;
}

.race-bar {
  height: 25px;
  background: #321626;
  border-radius: 20px;
  overflow: hidden;
}

.race-fill {
  height: 100%;
  width: 0;
  background: linear-gradient(90deg,#ff75af,#ffd166);
  transition: width .25s;
}

.timing {
  width: min(92vw,500px);
  height: 30px;
  background: #160a10;
  border-radius: 20px;
  overflow: hidden;
  position: relative;
  margin: 14px auto;
}

.timing-perfect {
  position: absolute;
  left: 42%;
  width: 16%;
  height: 100%;
  background: #7ee787;
  opacity: .8;
}

.timing-cursor {
  position: absolute;
  width: 5px;
  height: 100%;
  background: white;
  left: 0;
}

/* HEART HUNT */

.hunt-area {
  position: relative;
  width: min(94vw,550px);
  height: min(55svh,400px);
  background:
    radial-gradient(circle,#46182f,#1a0a12);
  border-radius: 20px;
  border: 1px solid #69304c;
  overflow: hidden;
}

.hunt-heart {
  position: absolute;
  font-size: 28px;
  cursor: pointer;
  touch-action: manipulation;
  transition: transform .15s;
}

/* WORD FIND */

.word-grid {
  display: grid;
  grid-template-columns: repeat(12,1fr);
  gap: 2px;
  width: min(94vw,500px);
  margin: auto;
  touch-action: none;
}

.word-cell {
  aspect-ratio: 1;
  display: grid;
  place-items: center;
  background: #2a1420;
  border-radius: 4px;
  font-size: clamp(10px,3.2vw,17px);
  font-weight: 800;
  color: #f5c7da;
}

.word-cell.selected {
  background: #a32d62;
  color: white;
}

.word-cell.found {
  background: #5d9d6a;
  color: white;
}

/* DRAW */

#flowerCanvas {
  width: min(92vw,500px);
  height: min(50svh,390px);
  background: #fff8fb;
  border-radius: 18px;
  touch-action: none;
  border: 3px solid #713653;
}

.draw-controls {
  display: flex;
  flex-wrap: wrap;
  gap: 7px;
  justify-content: center;
  margin-top: 8px;
}

.draw-controls button {
  min-height: 42px;
  border-radius: 11px;
  padding: 7px 12px;
  background: #321626;
  color: white;
}

/* LOCK */

.lock-display {
  font-size: 30px;
  letter-spacing: 8px;
  text-align: center;
  margin: 10px;
}

.keypad {
  display: grid;
  grid-template-columns: repeat(3,1fr);
  gap: 8px;
  width: min(86vw,320px);
  margin: auto;
}

.key {
  background: #321626;
  color: white;
  border-radius: 13px;
  font-size: 22px;
}

/* BOX / BOSS */

.health {
  width: min(90vw,500px);
  height: 18px;
  background: #160a10;
  border-radius: 20px;
  overflow: hidden;
  margin: 7px auto;
}

.health-fill {
  height: 100%;
  transition: width .2s;
}

.player-health {
  background: #ff7eb6;
}

.enemy-health {
  background: #ff667d;
}

/* COUNTDOWN */

.mini-box {
  width: min(92vw,500px);
  height: 230px;
  background: #1a0a12;
  border: 1px solid #67314c;
  border-radius: 20px;
  display: grid;
  place-items: center;
  padding: 15px;
  margin: auto;
}

.stop-bar {
  width: 90%;
  height: 32px;
  background: #321626;
  border-radius: 20px;
  position: relative;
}

.stop-zone {
  position: absolute;
  left: 43%;
  width: 14%;
  height: 100%;
  background: #7ee787;
}

.stop-pointer {
  position: absolute;
  left: 0;
  top: -5px;
  width: 7px;
  height: 42px;
  background: white;
}

/* GAMBLE */

.pot {
  font-size: clamp(38px,11vw,65px);
  color: var(--gold);
  text-align: center;
  font-weight: 900;
}

/* BOSS */

.boss {
  font-size: 80px;
  text-align: center;
  margin: 5px;
}

/* MOBILE */

@media(max-width:430px) {

  .screen {
    padding:
      max(8px, env(safe-area-inset-top))
      max(8px, env(safe-area-inset-right))
      max(8px, env(safe-area-inset-bottom))
      max(8px, env(safe-area-inset-left));
  }

  .game-title {
    font-size: 22px;
  }

  .game-help {
    font-size: 12px;
  }

  .game-card {
    padding: 11px;
  }

  .answers {
    gap: 7px;
  }

  .answer {
    min-height: 54px;
    padding: 9px 5px;
    font-size: 14px;
  }

  .broken-shell {
    grid-template-rows: auto minmax(220px,1fr) auto;
  }

  .broken-arena {
    width: min(86vw,330px);
    height: min(43svh,285px);
  }

  .broken-controls {
    width: min(86vw,330px);
  }

  .level {
    grid-template-columns: 45px 1fr auto;
    padding: 10px;
    gap: 8px;
  }

  .level-number {
    width: 42px;
    height: 42px;
  }
}

</style>
</head>

<body>

<div id="app">

<!-- HOME -->

<section id="home" class="screen active center">

  <div class="logo">Lulu Express 🚂💗</div>

  <div class="subtitle">
    A little journey made especially for Liliana
  </div>

  <div class="card">

    <h2>Welcome aboard 💗</h2>

    <p>
      Complete every level to travel all the way to
      the Final Challenge.
    </p>

    <button class="primary" onclick="showIntro()">
      Start the Journey 🚂
    </button>

    <button class="secondary" onclick="continueJourney()">
      Continue Journey
    </button>

    <button class="secondary" onclick="toggleMusic()">
      <span id="homeMusicText">♫ Music Off</span>
    </button>

    <button class="secondary" onclick="resetEverything()">
      Reset Journey
    </button>

  </div>

</section>


<!-- INTRO -->

<section id="intro" class="screen center">

  <div class="logo">Lulu Express 🚂</div>

  <div class="card">

    <h2>Before we begin 💗</h2>

    <p>
      Enter your name for your journey.
    </p>

    <input
      id="playerName"
      maxlength="30"
      placeholder="Your name"
      autocomplete="off"
    >

    <button class="primary" onclick="beginJourney()">
      Board the Train 🚂
    </button>

    <button class="secondary" onclick="showScreen('home')">
      Back
    </button>

  </div>

</section>


<!-- JOURNEY -->

<section id="journey" class="screen">

  <div class="topbar">

    <h1>Lulu Express 🚂💗</h1>

    <div class="stats">

      <div class="stat">
        ⭐ <span id="scoreDisplay">0</span>
      </div>

      <div class="stat">
        💗 <span id="tokenDisplay">0</span>
      </div>

      <button
        class="smallBtn"
        id="musicButton"
        onclick="toggleMusic()"
      >
        ♫ Music Off
      </button>

    </div>

  </div>

  <div class="journey">

    <h2 class="journey-title">
      <span id="journeyName">Your</span>'s Journey
    </h2>

    <div id="levelList"></div>

    <button class="secondary" onclick="resetEverything()">
      Reset Journey
    </button>

  </div>

</section>


<!-- GAME SCREENS -->

<section id="game1" class="screen game-screen">
  <div class="play" id="game1Play">

    <h1 class="game-title">💔 Broken Hearts</h1>

    <p class="game-help">
      Catch the whole hearts. Avoid the broken ones.
      Use the big buttons to move.
    </p>

    <div class="broken-shell">

      <div class="broken-stats">
        <span>💗 <b id="bhScore">0</b></span>
        <span>❤️ Lives: <b id="bhLives">3</b></span>
        <span>🔥 Combo: <b id="bhCombo">0</b></span>
      </div>

      <div id="brokenArena" class="broken-arena">
        <div id="catcher" class="catcher"></div>
      </div>

      <div class="broken-controls">

        <button
          id="leftButton"
          class="move-btn"
          onpointerdown="moveStart(-1,event)"
          onpointerup="moveStop(event)"
          onpointercancel="moveStop(event)"
          onpointerleave="moveStop(event)"
        >
          ◀
        </button>

        <button
          id="rightButton"
          class="move-btn"
          onpointerdown="moveStart(1,event)"
          onpointerup="moveStop(event)"
          onpointercancel="moveStop(event)"
          onpointerleave="moveStop(event)"
        >
          ▶
        </button>

      </div>

    </div>

  </div>

  <div id="game1Result" style="display:none"></div>
</section>


<section id="game2" class="screen game-screen">
  <div class="play" id="game2Play"></div>
  <div id="game2Result" style="display:none"></div>
</section>


<section id="game3" class="screen game-screen">
  <div class="play" id="game3Play"></div>
  <div id="game3Result" style="display:none"></div>
</section>


<section id="game4" class="screen game-screen">
  <div class="play" id="game4Play"></div>
  <div id="game4Result" style="display:none"></div>
</section>


<section id="game5" class="screen game-screen">
  <div class="play" id="game5Play"></div>
  <div id="game5Result" style="display:none"></div>
</section>


<section id="game6" class="screen game-screen">
  <div class="play" id="game6Play"></div>
  <div id="game6Result" style="display:none"></div>
</section>


<section id="game7" class="screen game-screen">
  <div class="play" id="game7Play"></div>
  <div id="game7Result" style="display:none"></div>
</section>


<section id="game8" class="screen game-screen">
  <div class="play" id="game8Play"></div>
  <div id="game8Result" style="display:none"></div>
</section>


<section id="game9" class="screen game-screen">
  <div class="play" id="game9Play"></div>
  <div id="game9Result" style="display:none"></div>
</section>


<section id="game10" class="screen game-screen">
  <div class="play" id="game10Play"></div>
  <div id="game10Result" style="display:none"></div>
</section>


<section id="game11" class="screen game-screen">
  <div class="play" id="game11Play"></div>
  <div id="game11Result" style="display:none"></div>
</section>


<section id="game12" class="screen game-screen">
  <div class="play" id="game12Play"></div>
  <div id="game12Result" style="display:none"></div>
</section>


<section id="game13" class="screen game-screen">
  <div class="play" id="game13Play"></div>
  <div id="game13Result" style="display:none"></div>
</section>


<section id="game14" class="screen game-screen">
  <div class="play" id="game14Play"></div>
  <div id="game14Result" style="display:none"></div>
</section>


<section id="game15" class="screen game-screen">
  <div class="play" id="game15Play"></div>
  <div id="game15Result" style="display:none"></div>
</section>


<section id="game16" class="screen game-screen">
  <div class="play" id="game16Play"></div>
  <div id="game16Result" style="display:none"></div>
</section>


<section id="game17" class="screen game-screen">
  <div class="play" id="game17Play"></div>
  <div id="game17Result" style="display:none"></div>
</section>


<section id="game18" class="screen game-screen">
  <div class="play" id="game18Play"></div>
  <div id="game18Result" style="display:none"></div>
</section>


<section id="game19" class="screen game-screen">
  <div class="play" id="game19Play"></div>
  <div id="game19Result" style="display:none"></div>
</section>


<section id="game20" class="screen game-screen">
  <div class="play" id="game20Play"></div>
  <div id="game20Result" style="display:none"></div>
</section>


<section id="game21" class="screen game-screen">
  <div class="play" id="game21Play"></div>
  <div id="game21Result" style="display:none"></div>
</section>


<section id="game22" class="screen game-screen">
  <div class="play" id="game22Play"></div>
  <div id="game22Result" style="display:none"></div>
</section>


<section id="game23" class="screen game-screen">
  <div class="play" id="game23Play"></div>
  <div id="game23Result" style="display:none"></div>
</section>


<!-- FINAL -->

<section id="ending" class="screen center">

  <div class="logo">🏆 Lulu Express 🏆</div>

  <div class="card">

    <h2>Journey Complete 💗</h2>

    <p id="endingText"></p>

    <p>
      Final Score:
      <strong id="endingScore"></strong>
    </p>

    <div id="callReward"></div>

    <button class="primary" onclick="showScreen('journey')">
      View Journey
    </button>

  </div>

</section>

</div>


<script>

/* =========================================================
   GLOBAL STATE
========================================================= */

const TOTAL_GAMES = 23;

let state = {
  name: "",
  score: 0,
  tokens: 0,
  completed: [],
  started: false
};

const STORAGE_KEY = "luluExpress23";

let timers = [];
let intervals = [];
let animationFrames = [];

function saveState() {
  localStorage.setItem(STORAGE_KEY, JSON.stringify(state));
}

function loadState() {

  try {

    const saved =
      JSON.parse(localStorage.getItem(STORAGE_KEY));

    if (saved) {
      state = {
        ...state,
        ...saved
      };
    }

  } catch(e) {}

}

loadState();


/* =========================================================
   SCREEN CONTROL
========================================================= */

function showScreen(id) {

  stopAllLoops();

  document
    .querySelectorAll(".screen")
    .forEach(s => s.classList.remove("active"));

  const el = document.getElementById(id);

  if (el) {
    el.classList.add("active");
  }

  const isGame =
    /^game\d+$/.test(id);

  if (isGame) {

    document.body.classList.add("playing");

  } else {

    document.body.classList.remove("playing");
    updateJourney();
  }

}


function stopAllLoops() {

  timers.forEach(clearTimeout);
  intervals.forEach(clearInterval);

  animationFrames.forEach(cancelAnimationFrame);

  timers = [];
  intervals = [];
  animationFrames = [];

  document
    .querySelectorAll(".falling-heart")
    .forEach(x => x.remove());
}


function later(fn,ms) {
  const id = setTimeout(fn,ms);
  timers.push(id);
  return id;
}

function every(fn,ms) {
  const id = setInterval(fn,ms);
  intervals.push(id);
  return id;
}


/* =========================================================
   POINTS
========================================================= */

function addPoints(amount) {

  state.score += amount;

  if (amount > 0) {
    state.tokens += Math.max(1,Math.floor(amount / 10));
  }

  saveState();
  updateStats();
}

function updateStats() {

  document.getElementById("scoreDisplay").textContent =
    state.score;

  document.getElementById("tokenDisplay").textContent =
    state.tokens;

}


/* =========================================================
   HOME / JOURNEY
========================================================= */

function showIntro() {
  showScreen("intro");

  later(() => {
    document.getElementById("playerName").focus();
  },100);
}


function beginJourney() {

  const input =
    document.getElementById("playerName");

  const name =
    input.value.trim();

  if (!name) {
    alert("Please enter your name first 💗");
    return;
  }

  state.name = name;
  state.started = true;

  saveState();

  showScreen("journey");
}


function continueJourney() {

  if (!state.name) {
    showIntro();
    return;
  }

  showScreen("journey");
}


function resetEverything() {

  if (
    !confirm(
      "Reset the entire Lulu Express journey?"
    )
  ) {
    return;
  }

  stopAllLoops();

  state = {
    name: "",
    score: 0,
    tokens: 0,
    completed: [],
    started: false
  };

  localStorage.removeItem(STORAGE_KEY);

  if (audioContext) {
    try {
      audioContext.suspend();
    } catch(e) {}
  }

  musicOn = false;

  updateStats();

  document.getElementById("homeMusicText").textContent =
    "♫ Music Off";

  document.getElementById("musicButton").textContent =
    "♫ Music Off";

  showScreen("home");
}


function updateJourney() {

  const list =
    document.getElementById("levelList");

  if (!list) return;

  list.innerHTML = "";

  const names = [
    ["💔","Broken Hearts","Catch the whole hearts"],
    ["🧠","Memory Vault","Remember the sequence"],
    ["⏱️","Pressure Quiz","Beat the clock"],
    ["🎰","High Roller","Spin the reels"],
    ["🧩","Mind Games","Solve the patterns"],
    ["🃏","The Bluff","Risk your cards"],
    ["🛡️","Survival Round","Survive the waves"],
    ["🏇","The Admirer Race","Beat the rival"],
    ["🔎","Heartbreak Chamber","Find the clues"],
    ["🥊","Heartbreak Boxing Match","Win the fight"],
    ["🧲","Perfect Match","Match everything"],
    ["💗","Who Knows Liliana Best?","How well do you know her?"],
    ["⚡","Reaction Gauntlet","React quickly"],
    ["🕵️","Heart Hunt","Find the hidden hearts"],
    ["🔐","Love Lock","Crack the code"],
    ["🏹","Cupid Shootout","Hit the targets"],
    ["⏳","The Countdown","Beat the mini-games"],
    ["🎲","Ultimate Gamble","Risk it all"],
    ["👑","Admirer's Last Stand","Defeat the boss"],
    ["🔎","Liliana's Word Find","Find all 25 words"],
    ["🌻","Draw a Sunflower","Create your flower"],
    ["🏇","THE LULU DERBY","100 trivia questions"],
    ["💕","THE FINAL CHALLENGE","50 questions about Liliana"]
  ];

  for (let i=0;i<TOTAL_GAMES;i++) {

    const n = i + 1;

    const completed =
      state.completed.includes(n);

    const unlocked =
      n === 1 ||
      state.completed.includes(n - 1);

    const div =
      document.createElement("div");

    div.className =
      "level" +
      (completed ? " complete" : "") +
      (!unlocked ? " locked" : "");

    div.innerHTML = `
      <div class="level-number">
        ${completed ? "✓" : names[i][0]}
      </div>

      <div>
        <div class="level-name">
          ${n}. ${names[i][1]}
        </div>
        <div class="level-desc">
          ${names[i][2]}
        </div>
      </div>

      <div>
        ${
          unlocked
          ? `<button class="smallBtn"
              onclick="startGame(${n})">
              ${completed ? "Replay" : "Play"}
             </button>`
          : "🔒"
        }
      </div>
    `;

    list.appendChild(div);
  }

  document.getElementById("journeyName").textContent =
    state.name || "Your";

  updateStats();
}


/* =========================================================
   COMPLETE GAME
========================================================= */

function completeGame(gameNumber,points=100) {

  stopAllLoops();

  if (!state.completed.includes(gameNumber)) {

    state.completed.push(gameNumber);

    state.completed.sort((a,b)=>a-b);

    addPoints(points);

  }

  saveState();

  showGameResult(gameNumber);
}


function showGameResult(n) {

  const play =
    document.getElementById("game"+n+"Play");

  const result =
    document.getElementById("game"+n+"Result");

  if (!play || !result) return;

  play.style.display = "none";

  result.style.display = "flex";
  result.style.width = "100%";
  result.style.height = "100%";
  result.style.alignItems = "center";
  result.style.justifyContent = "center";

  const next =
    n < TOTAL_GAMES
    ? `
      <button
        class="nextBtn"
        onclick="startGame(${n+1})">
        Next Level →
      </button>
    `
    : `
      <button
        class="nextBtn"
        onclick="finishJourney()">
        Finish Journey 🏆
      </button>
    `;

  result.innerHTML = `
    <div class="result">

      <h2>Level ${n} Complete! 💗</h2>

      <p>
        Amazing work, ${escapeHTML(state.name)}.
      </p>

      <p>
        ⭐ Score: ${state.score}
      </p>

      ${next}

      <button
        class="secondary"
        onclick="showScreen('journey')">
        Journey Map
      </button>

    </div>
  `;
}


function escapeHTML(text) {

  return String(text)
    .replaceAll("&","&amp;")
    .replaceAll("<","&lt;")
    .replaceAll(">","&gt;")
    .replaceAll('"',"&quot;")
    .replaceAll("'","&#039;");
}


function resetGameScreen(n) {

  const play =
    document.getElementById("game"+n+"Play");

  const result =
    document.getElementById("game"+n+"Result");

  if (play) {
    play.style.display = "flex";
  }

  if (result) {
    result.style.display = "none";
    result.innerHTML = "";
  }

}


/* =========================================================
   START GAME
========================================================= */

function startGame(n) {

  if (!state.name) {
    showIntro();
    return;
  }

  if (
    n > 1 &&
    !state.completed.includes(n - 1)
  ) {
    alert("You need to pass the previous level first 💗");
    return;
  }

  stopAllLoops();

  resetGameScreen(n);

  showScreen("game"+n);

  switch(n) {

    case 1: initBrokenHearts(); break;
    case 2: initMemory(); break;
    case 3: initPressureQuiz(); break;
    case 4: initHighRoller(); break;
    case 5: initMindGames(); break;
    case 6: initBluff(); break;
    case 7: initSurvival(); break;
    case 8: initAdmirerRace(); break;
    case 9: initHeartbreakChamber(); break;
    case 10: initBoxing(); break;
    case 11: initPerfectMatch(); break;
    case 12: initLilianaQuiz(); break;
    case 13: initReaction(); break;
    case 14: initHeartHunt(); break;
    case 15: initLoveLock(); break;
    case 16: initCupid(); break;
    case 17: initCountdown(); break;
    case 18: initGamble(); break;
    case 19: initBoss(); break;
    case 20: initWordFind(); break;
    case 21: initSunflower(); break;
    case 22: initDerby(); break;
    case 23: initFinalChallenge(); break;

  }

}


/* =========================================================
   GAME 1 — BROKEN HEARTS
========================================================= */

let bh = {
  score: 0,
  lives: 3,
  combo: 0,
  catcherX: 50,
  moving: 0,
  speed: 105,
  spawnTimer: null,
  running: false,
  lastTime: 0
};


function initBrokenHearts() {

  const arena =
    document.getElementById("brokenArena");

  arena.innerHTML =
    `<div id="catcher" class="catcher"></div>`;

  bh = {
    score: 0,
    lives: 3,
    combo: 0,
    catcherX: 50,
    moving: 0,
    speed: 105,
    spawnTimer: null,
    running: true,
    lastTime: performance.now()
  };

  updateBrokenStats();

  moveCatcher();

  /*
    IMPORTANT:
    Start the animation loop FIRST.
    This guarantees that spawned hearts
    are continuously updated.
  */

  const frame =
    requestAnimationFrame(brokenLoop);

  animationFrames.push(frame);

  spawnBrokenHeart();

  /*
    New heart every 700ms.
    This is intentionally much slower
    and easier on a phone.
  */

  bh.spawnTimer =
    every(spawnBrokenHeart,700);

}


function spawnBrokenHeart() {

  if (!bh.running) return;

  const arena =
    document.getElementById("brokenArena");

  if (!arena) return;

  const heart =
    document.createElement("div");

  const roll =
    Math.random();

  let type;

  if (roll < .13) {
    type = "💔";
  } else if (roll < .20) {
    type = "💛";
  } else {
    type = "❤️";
  }

  heart.className = "falling-heart";

  heart.textContent = type;

  const maxLeft =
    Math.max(
      5,
      arena.clientWidth - 42
    );

  const x =
    Math.random() * maxLeft;

  heart.dataset.x = x;
  heart.dataset.y = -40;

  /*
    Each heart gets its own fall speed.
    Broken hearts are not excessively fast.
  */

  heart.dataset.speed =
    82 + Math.random() * 38;

  heart.dataset.type = type;

  heart.style.left =
    x + "px";

  heart.style.top =
    "-42px";

  arena.appendChild(heart);
}


function brokenLoop(now) {

  if (!bh.running) return;

  const arena =
    document.getElementById("brokenArena");

  if (!arena) return;

  const dt =
    Math.min(
      (now - bh.lastTime) / 1000,
      .05
    );

  bh.lastTime = now;

  const catcher =
    document.getElementById("catcher");

  const catcherWidth =
    catcher.offsetWidth;

  const catcherLeft =
    bh.catcherX / 100 *
    (arena.clientWidth - catcherWidth);

  catcher.style.transform =
    `translateX(${catcherLeft}px)`;

  const hearts =
    arena.querySelectorAll(".falling-heart");

  hearts.forEach(heart => {

    let y =
      parseFloat(heart.dataset.y);

    const speed =
      parseFloat(heart.dataset.speed);

    y += speed * dt;

    heart.dataset.y = y;

    heart.style.transform =
      `translateY(${y + 42}px)`;

    const x =
      parseFloat(heart.dataset.x);

    const heartBottom =
      y + 42;

    const arenaHeight =
      arena.clientHeight;

    /*
      Collision zone is intentionally generous.
      This makes the game easier on small screens.
    */

    const catcherTop =
      arenaHeight - 52;

    const overlapsX =
      x + 32 >= catcherLeft &&
      x <= catcherLeft + catcherWidth;

    const overlapsY =
      heartBottom >= catcherTop &&
      heartBottom <= arenaHeight;

    if (overlapsX && overlapsY) {

      collectBrokenHeart(heart);

      return;
    }

    if (heartBottom > arenaHeight + 5) {

      if (
        heart.dataset.type === "❤️" ||
        heart.dataset.type === "💛"
      ) {

        bh.combo = 0;

      }

      heart.remove();

    }

  });

  /*
    Gradually increase speed.
    Never becomes ridiculously fast.
  */

  bh.speed += dt * 1.5;

  const next =
    requestAnimationFrame(brokenLoop);

  animationFrames.push(next);
}


function collectBrokenHeart(heart) {

  const type =
    heart.dataset.type;

  heart.remove();

  if (type === "💔") {

    bh.lives--;
    bh.combo = 0;

    updateBrokenStats();

    if (bh.lives <= 0) {

      bh.running = false;

      brokenLose();

    }

    return;
  }

  bh.combo++;

  let points = 10;

  if (type === "💛") {
    points = 30;
  }

  if (bh.combo >= 5) {
    points += 10;
  }

  bh.score += points;

  updateBrokenStats();

  /*
    Pass condition:
    20 hearts caught.
    This is easier than requiring a very
    high score.
  */

  if (bh.score >= 200) {

    bh.running = false;

    completeGame(1,120);

  }

}


function updateBrokenStats() {

  const score =
    document.getElementById("bhScore");

  const lives =
    document.getElementById("bhLives");

  const combo =
    document.getElementById("bhCombo");

  if (score) score.textContent = bh.score;
  if (lives) lives.textContent = bh.lives;
  if (combo) combo.textContent = bh.combo;
}


function moveStart(direction,event) {

  event.preventDefault();

  bh.moving = direction;

  const id =
    direction === -1
    ? "leftButton"
    : "rightButton";

  document
    .getElementById(id)
    .classList.add("active");

  /*
    Immediate movement means the user
    doesn't need to hold the button for
    the movement to begin.
  */

  moveCatcherImmediate(direction);
}


function moveStop(event) {

  event.preventDefault();

  bh.moving = 0;

  document
    .querySelectorAll(".move-btn")
    .forEach(btn =>
      btn.classList.remove("active")
    );
}


function moveCatcherImmediate(direction) {

  if (!bh.running) return;

  bh.catcherX +=
    direction * 8;

  bh.catcherX =
    Math.max(
      0,
      Math.min(100,bh.catcherX)
    );

  moveCatcher();
}


function moveCatcher() {

  const catcher =
    document.getElementById("catcher");

  const arena =
    document.getElementById("brokenArena");

  if (!catcher || !arena) return;

  const max =
    arena.clientWidth -
    catcher.offsetWidth;

  const x =
    bh.catcherX / 100 * max;

  catcher.style.transform =
    `translateX(${x}px)`;
}


/*
  Continuous movement while holding.
*/

every(function(){

  if (
    bh &&
    bh.running &&
    bh.moving !== 0
  ) {

    bh.catcherX +=
      bh.moving * 3.2;

    bh.catcherX =
      Math.max(
        0,
        Math.min(100,bh.catcherX)
      );

    moveCatcher();
  }

},40);


function brokenLose() {

  const play =
    document.getElementById("game1Play");

  const result =
    document.getElementById("game1Result");

  play.style.display = "none";

  result.style.display = "flex";
  result.style.width = "100%";
  result.style.height = "100%";
  result.style.alignItems = "center";
  result.style.justifyContent = "center";

  result.innerHTML = `
    <div class="result">

      <h2>💔 Almost!</h2>

      <p>
        You ran out of lives.
      </p>

      <p>
        You can try Level 1 again.
      </p>

      <button
        class="nextBtn"
        onclick="startGame(1)">
        Try Again
      </button>

      <button
        class="secondary"
        onclick="showScreen('journey')">
        Journey Map
      </button>

    </div>
  `;
}


/* =========================================================
   SHUFFLE
========================================================= */

function shuffle(array) {

  const a = [...array];

  for (
    let i = a.length - 1;
    i > 0;
    i--
  ) {

    const j =
      Math.floor(
        Math.random() * (i + 1)
      );

    [
      a[i],
      a[j]
    ] =
    [
      a[j],
      a[i]
    ];
  }

  return a;
}


function shuffleAnswers(q) {

  return shuffle(
    q.options.map(
      (text,i) => ({
        text,
        correct:
          i === q.answer
      })
    )
  );
}


/* =========================================================
   GAME 2 — MEMORY VAULT
========================================================= */

function initMemory() {

  const el =
    document.getElementById("game2Play");

  el.innerHTML = `
    <h1 class="game-title">🧠 Memory Vault</h1>

    <p class="game-help">
      Watch the glowing sequence, then repeat it.
    </p>

    <div class="message" id="memoryMsg">
      Round 1
    </div>

    <div class="memory-grid" id="memoryGrid"></div>

    <div class="message">
      <span id="memoryRound">1</span> / 7
    </div>
  `;

  let sequence = [];
  let player = [];
  let round = 1;
  let accepting = false;

  const grid =
    document.getElementById("memoryGrid");

  for(let i=0;i<16;i++) {

    const b =
      document.createElement("button");

    b.className = "memory-tile";
    b.textContent = "💗";

    b.onclick = () => {

      if (!accepting) return;

      const index =
        Number(b.dataset.index);

      player.push(index);

      b.classList.add("show");

      later(
        () => b.classList.remove("show"),
        180
      );

      const position =
        player.length - 1;

      if (
        player[position] !==
        sequence[position]
      ) {

        accepting = false;

        document.getElementById("memoryMsg")
          .textContent =
          "Oops! Watch it again 💗";

        later(startRound,700);

        return;
      }

      if (
        player.length ===
        sequence.length
      ) {

        accepting = false;

        if (round >= 7) {

          completeGame(2,130);

          return;
        }

        round++;

        document.getElementById("memoryRound")
          .textContent = round;

        later(startRound,650);
      }

    };

    b.dataset.index = i;

    grid.appendChild(b);
  }

  function startRound() {

    player = [];

    accepting = false;

    sequence = [];

    for(let i=0;i<round+1;i++) {

      sequence.push(
        Math.floor(
          Math.random()*16
        )
      );

    }

    document.getElementById("memoryMsg")
      .textContent =
      "Watch carefully…";

    let delay = 400;

    sequence.forEach(index => {

      later(() => {

        const tile =
          grid.children[index];

        tile.classList.add("show");

        later(
          () => tile.classList.remove("show"),
          350
        );

      },delay);

      delay += 520;
    });

    later(() => {

      accepting = true;

      document.getElementById("memoryMsg")
        .textContent =
        "Your turn!";

    },delay);
  }

  startRound();
}


/* =========================================================
   GENERAL QUIZ
========================================================= */

const generalQuestions = [

["What is the capital of Australia?",
["Sydney","Canberra","Melbourne","Perth"],1],

["Which planet is the largest?",
["Saturn","Earth","Jupiter","Neptune"],2],

["Which planet is known as the Red Planet?",
["Mars","Venus","Mercury","Jupiter"],0],

["What is the chemical symbol for gold?",
["Ag","Au","Fe","Go"],1],

["How many continents are there?",
["5","6","7","8"],2],

["Where is the Great Barrier Reef?",
["Australia","Brazil","India","Mexico"],0],

["Who wrote Pride and Prejudice?",
["Charlotte Brontë","Jane Austen","Emily Brontë","Mary Shelley"],1],

["What is the currency of Japan?",
["Won","Yuan","Yen","Ringgit"],2],

["What is the fastest land animal?",
["Lion","Horse","Cheetah","Leopard"],2],

["What is the largest ocean?",
["Atlantic","Indian","Arctic","Pacific"],3],

["At sea level, water boils at what temperature?",
["50°C","75°C","100°C","120°C"],2],

["How many chambers does the human heart have?",
["2","3","4","5"],2],

["Which gas makes up most of Earth's atmosphere?",
["Oxygen","Nitrogen","Carbon dioxide","Hydrogen"],1],

["What is the tallest mountain above sea level?",
["K2","Mount Everest","Kilimanjaro","Denali"],1],

["What is the smallest prime number?",
["0","1","2","3"],2],

["Who wrote Hamlet?",
["William Shakespeare","Charles Dickens","Mark Twain","Oscar Wilde"],0],

["Who painted the Mona Lisa?",
["Michelangelo","Leonardo da Vinci","Raphael","Van Gogh"],1],

["What does DNA stand for?",
["Deoxyribonucleic acid","Dynamic nitrogen acid","Double nucleic atom","Deoxygenated nitrogen acid"],0],

["How many sides does an octagon have?",
["6","7","8","9"],2],

["Which animal produces honey?",
["Ants","Bees","Butterflies","Wasps"],1],

["Which planet is famous for its rings?",
["Mars","Saturn","Venus","Mercury"],1],

["A whale is what type of animal?",
["Fish","Reptile","Mammal","Amphibian"],2],

["What is H2O?",
["Salt","Water","Oxygen","Hydrogen"],1],

["Which travels faster?",
["Sound","Light","They are equal","Wind"],1],

["The Sahara is located in which continent?",
["Asia","Africa","Europe","Australia"],1],

["The Eiffel Tower is in which city?",
["Rome","London","Paris","Madrid"],2],

["Mount Fuji is in which country?",
["China","Japan","South Korea","Thailand"],1],

["The Great Wall is associated with which country?",
["China","India","Mongolia","Japan"],0],

["What is the currency of New Zealand?",
["Australian dollar","New Zealand dollar","Pound","Peso"],1]

];


function initQuizGame(
  gameNumber,
  questions,
  passScore,
  title,
  description
) {

  const el =
    document.getElementById(
      "game"+gameNumber+"Play"
    );

  let list =
    shuffle(questions);

  let index = 0;
  let score = 0;
  let locked = false;

  el.innerHTML = `
    <h1 class="game-title">${title}</h1>

    <p class="game-help">
      ${description}
    </p>

    <div class="question-card">

      <div class="question-number"
           id="quizNumber"></div>

      <div class="timerbar">
        <div
          class="timerfill"
          id="quizTimer">
        </div>
      </div>

      <div
        class="question"
        id="quizQuestion">
      </div>

      <div
        class="answers"
        id="quizAnswers">
      </div>

      <div
        class="message"
        id="quizMessage">
      </div>

    </div>
  `;

  showQuestion();

  function showQuestion() {

    if (index >= 10) {

      if (score >= passScore) {

        completeGame(
          gameNumber,
          120 + score * 4
        );

      } else {

        quizLose();

      }

      return;
    }

    locked = false;

    const q = list[index];

    const answers =
      shuffleAnswers({
        options:q[1],
        answer:q[2]
      });

    document.getElementById("quizNumber")
      .textContent =
      `Question ${index+1} / 10`;

    document.getElementById("quizQuestion")
      .textContent = q[0];

    const box =
      document.getElementById("quizAnswers");

    box.innerHTML = "";

    answers.forEach(answer => {

      const b =
        document.createElement("button");

      b.className = "answer";

      b.textContent =
        answer.text;

      b.onclick = () => {

        if (locked) return;

        locked = true;

        if (answer.correct) {

          score++;

          b.classList.add("correct");

          document.getElementById("quizMessage")
            .textContent =
            "Correct! 💗";

        } else {

          b.classList.add("wrong");

          document.getElementById("quizMessage")
            .textContent =
            "Not quite!";

          box
            .querySelectorAll(".answer")
            .forEach(x => {

              if (
                x.textContent ===
                q[1][q[2]]
              ) {
                x.classList.add("correct");
              }

            });

        }

        index++;

        later(showQuestion,550);

      };

      box.appendChild(b);
    });

    let time = 7;

    const fill =
      document.getElementById("quizTimer");

    fill.style.width = "100%";

    const tick =
      every(() => {

        time -= .1;

        fill.style.width =
          Math.max(0,time/7*100) + "%";

        if (time <= 0) {

          clearInterval(tick);

          if (!locked) {

            locked = true;

            document.getElementById("quizMessage")
              .textContent =
              "Time! ⏱️";

            index++;

            later(showQuestion,400);

          }

        }

      },100);

  }


  function quizLose() {

    const play =
      document.getElementById(
        "game"+gameNumber+"Play"
      );

    const result =
      document.getElementById(
        "game"+gameNumber+"Result"
      );

    play.style.display = "none";

    result.style.display = "flex";
    result.style.width = "100%";
    result.style.height = "100%";
    result.style.alignItems = "center";
    result.style.justifyContent = "center";

    result.innerHTML = `
      <div class="result">

        <h2>Keep going 💗</h2>

        <p>
          You scored ${score}/10.
        </p>

        <p>
          You need ${passScore}/10 to pass.
        </p>

        <button
          class="nextBtn"
          onclick="startGame(${gameNumber})">
          Try Again
        </button>

      </div>
    `;
  }

}


/* =========================================================
   GAME 3
========================================================= */

function initPressureQuiz() {

  initQuizGame(
    3,
    generalQuestions,
    6,
    "⏱️ Pressure Quiz",
    "Ten quick general-knowledge questions."
  );

}


/* =========================================================
   GAME 4 — HIGH ROLLER
========================================================= */

function initHighRoller() {

  const el =
    document.getElementById("game4Play");

  el.innerHTML = `
    <h1 class="game-title">🎰 High Roller</h1>

    <p class="game-help">
      Spin the reels and stop them one at a time.
      Three matching symbols wins big.
    </p>

    <div class="game-card">

      <div class="reels">

        <div class="reel" id="reel1">🍒</div>
        <div class="reel" id="reel2">🍋</div>
        <div class="reel" id="reel3">💎</div>

      </div>

      <div class="message" id="slotMsg">
        Start the machine!
      </div>

      <div class="slot-controls">

        <button class="action"
          onclick="slotStart()">
          SPIN
        </button>

        <button class="action"
          onclick="slotStop(1)">
          STOP 1
        </button>

        <button class="action"
          onclick="slotStop(2)">
          STOP 2
        </button>

        <button class="action"
          onclick="slotStop(3)">
          STOP 3
        </button>

      </div>

    </div>
  `;

  window.slotState = {
    spinning:false,
    stopped:[false,false,false],
    values:["🍒","🍋","💎"]
  };

}


function slotStart() {

  if (slotState.spinning) return;

  slotState.spinning = true;
  slotState.stopped =
    [false,false,false];

  const symbols =
    ["🍒","🍋","⭐","💎","7️⃣"];

  slotState.values =
    [0,1,2].map(() =>
      symbols[
        Math.floor(
          Math.random()*symbols.length
        )
      ]
    );

  [1,2,3].forEach(i => {

    const reel =
      document.getElementById("reel"+i);

    reel.textContent =
      symbols[
        Math.floor(
          Math.random()*symbols.length
        )
      ];

  });

  document.getElementById("slotMsg")
    .textContent =
    "Stop each reel!";

  const spin =
    every(() => {

      [1,2,3].forEach(i => {

        if (!slotState.stopped[i-1]) {

          document.getElementById("reel"+i)
            .textContent =
            symbols[
              Math.floor(
                Math.random()*symbols.length
              )
            ];

        }

      });

    },100);

  slotState.spinInterval = spin;

}


function slotStop(n) {

  if (!slotState.spinning) return;

  if (slotState.stopped[n-1]) return;

  slotState.stopped[n-1] = true;

  document.getElementById("reel"+n)
    .textContent =
    slotState.values[n-1];

  if (
    slotState.stopped.every(Boolean)
  ) {

    slotState.spinning = false;

    const values =
      slotState.values;

    let points = 20;

    if (
      values[0] === values[1] &&
      values[1] === values[2]
    ) {
      points = 250;

      document.getElementById("slotMsg")
        .textContent =
        "JACKPOT! 💎💎💎";

    } else if (
      values[0] === values[1] ||
      values[1] === values[2] ||
      values[0] === values[2]
    ) {

      points = 90;

      document.getElementById("slotMsg")
        .textContent =
        "Two matched! 🎰";

    } else {

      document.getElementById("slotMsg")
        .textContent =
        "No match, but you still get points!";

    }

    completeGame(4,points);
  }

}


/* =========================================================
   GAME 5 — MIND GAMES
========================================================= */

function initMindGames() {

  const patterns = [

    ["🔴","🔵","🔴","🔵","?","🔴"],
    ["⭐","⭐","💗","⭐","⭐","?"],
    ["1","2","3","1","2","?"],
    ["🌙","☀️","🌙","☀️","?","☀️"],
    ["A","C","E","G","?","K"],
    ["2","4","6","8","?","12"],
    ["🐶","🐱","🐶","🐱","?","🐱"],
    ["▲","■","▲","■","?","■"]
  ];

  const answers = [
    ["🔵","🟢","🟡","🟣"],
    ["💗","⭐","🌙","💔"],
    ["3","4","5","6"],
    ["🌙","⭐","☁️","🌧️"],
    ["I","H","J","K"],
    ["10","9","11","14"],
    ["🐶","🐱","🐭","🐹"],
    ["▲","■","●","◆"]
  ];

  const el =
    document.getElementById("game5Play");

  let index = 0;
  let score = 0;

  function render() {

    if (index >= patterns.length) {

      if (score >= 5) {
        completeGame(5,130);
      } else {
        el.innerHTML = `
          <div class="result">
            <h2>Almost!</h2>
            <p>${score}/8 correct.</p>
            <button class="nextBtn"
              onclick="startGame(5)">
              Try Again
            </button>
          </div>
        `;
      }

      return;
    }

    const p = patterns[index];

    el.innerHTML = `
      <h1 class="game-title">🧩 Mind Games</h1>

      <p class="game-help">
        What belongs in the missing space?
      </p>

      <div class="game-card">

        <div style="
          display:flex;
          justify-content:center;
          gap:10px;
          font-size:32px;
          margin:20px 0;
        ">
          ${p.map(x => `<span>${x}</span>`).join("")}
        </div>

        <div class="action-grid" id="patternAnswers">
        </div>

        <div class="message">
          ${index+1} / ${patterns.length}
        </div>

      </div>
    `;

    answers[index].forEach(answer => {

      const b =
        document.createElement("button");

      b.className = "action";

      b.textContent = answer;

      b.onclick = () => {

        if (
          answer ===
          answers[index][0]
        ) score++;

        index++;

        later(render,250);
      };

      document
        .getElementById("patternAnswers")
        .appendChild(b);

    });

  }

  render();
}


/* =========================================================
   GAME 6 — BLUFF
========================================================= */

function initBluff() {

  const el =
    document.getElementById("game6Play");

  let round = 0;
  let total = 0;

  function render() {

    if (round >= 5) {

      if (total >= 30) {
        completeGame(6,150);
      } else {
        el.innerHTML = `
          <div class="result">
            <h2>Close call 🃏</h2>
            <p>Your total was ${total}.</p>
            <button class="nextBtn"
              onclick="startGame(6)">
              Try Again
            </button>
          </div>
        `;
      }

      return;
    }

    const cards =
      shuffle([
        5+Math.floor(Math.random()*16),
        5+Math.floor(Math.random()*16),
        5+Math.floor(Math.random()*16),
        5+Math.floor(Math.random()*16)
      ]);

    el.innerHTML = `
      <h1 class="game-title">🃏 The Bluff</h1>

      <p class="game-help">
        Pick a hidden card. Then decide whether
        to bank it or risk it.
      </p>

      <div class="game-card">

        <div class="action-grid"
             id="cards"></div>

        <div class="message">
          Round ${round+1}/5
          · Total ${total}
        </div>

      </div>
    `;

    cards.forEach((value,index) => {

      const b =
        document.createElement("button");

      b.className = "action";

      b.textContent = "🂠";

      b.onclick = () => {

        el.innerHTML = `
          <h1 class="game-title">
            🃏 The Bluff
          </h1>

          <div class="result">

            <h2>
              Your card was ${value}!
            </h2>

            <p>
              Bank it safely or double it?
            </p>

            <button class="nextBtn"
              onclick="bluffBank(${value})">
              BANK +${value}
            </button>

            <button class="secondary"
              onclick="bluffDouble(${value})">
              DOUBLE
            </button>

          </div>
        `;

      };

      document
        .getElementById("cards")
        .appendChild(b);

    });

    window.bluffBank = value => {

      total += value;
      round++;
      render();

    };

    window.bluffDouble = value => {

      if (value >= 10) {
        total += value * 2;
      } else {
        total = Math.max(0,total-10);
      }

      round++;
      render();

    };

  }

  render();
}


/* =========================================================
   GAME 7 — SURVIVAL
========================================================= */

function initSurvival() {

  const hazards = [

    ["⚡","Lightning!","SHIELD","JUMP","FREEZE",0],
    ["🌊","Wave!","DUCK","RUN","WAIT",0],
    ["🔥","Fire!","RUN","SLEEP","SING",0],
    ["🪨","Falling rocks!","MOVE","SIT","DANCE",0],
    ["❄️","Ice!","STEP","SPRINT","SLEEP",0],
    ["🐝","Bees!","DUCK","WAVE","RUN",0],
    ["🌪️","Wind!","LEAN","JUMP","SIT",0],
    ["🌧️","Heavy rain!","SHELTER","RUN","SING",0]
  ];

  let round = 0;
  let score = 0;

  const el =
    document.getElementById("game7Play");

  function render() {

    if (round >= hazards.length) {

      if (score >= 5) {
        completeGame(7,140);
      } else {
        el.innerHTML = `
          <div class="result">
            <h2>You survived ${score}/8</h2>
            <button class="nextBtn"
              onclick="startGame(7)">
              Try Again
            </button>
          </div>
        `;
      }

      return;
    }

    const h = hazards[round];

    el.innerHTML = `
      <h1 class="game-title">🛡️ Survival Round</h1>

      <p class="game-help">
        Choose the safest response.
      </p>

      <div class="game-card">

        <div style="
          text-align:center;
          font-size:65px;
        ">
          ${h[0]}
        </div>

        <div class="question">
          ${h[1]}
        </div>

        <div class="action-grid"
             id="survivalAnswers">
        </div>

        <div class="message">
          Wave ${round+1}/8
        </div>

      </div>
    `;

    h.slice(2,5).forEach(
      (answer,i) => {

        const b =
          document.createElement("button");

        b.className = "action";

        b.textContent = answer;

        b.onclick = () => {

          if (i === h[5]) {
            score++;
          }

          round++;

          later(render,250);

        };

        document
          .getElementById("survivalAnswers")
          .appendChild(b);

      }
    );

  }

  render();
}


/* =========================================================
   GAME 8 — ADMIRER RACE
========================================================= */

function initAdmirerRace() {

  const el =
    document.getElementById("game8Play");

  let round = 0;
  let player = 0;
  let rival = 0;
  let cursor = 0;
  let direction = 1;
  let accepting = false;

  el.innerHTML = `
    <h1 class="game-title">
      🏇 The Admirer Race
    </h1>

    <p class="game-help">
      Tap GALLop when the marker reaches the green zone.
    </p>

    <div class="race-track">

      <div class="race-row">
        <div class="race-name">
          <span>💗 You</span>
          <span id="racePlayer">0</span>
        </div>

        <div class="race-bar">
          <div
            id="racePlayerBar"
            class="race-fill">
          </div>
        </div>
      </div>

      <div class="race-row">
        <div class="race-name">
          <span>🏇 Rival</span>
          <span id="raceRival">0</span>
        </div>

        <div class="race-bar">
          <div
            id="raceRivalBar"
            class="race-fill">
          </div>
        </div>
      </div>

    </div>

    <div class="timing">

      <div class="timing-perfect"></div>

      <div
        id="raceCursor"
        class="timing-cursor">
      </div>

    </div>

    <button
      class="primary"
      id="gallopButton">
      🏇 GALLop!
    </button>

    <div class="message" id="raceMessage">
      Round 1 / 10
    </div>
  `;

  every(() => {

    if (!accepting) return;

    cursor += direction * 3;

    if (cursor >= 100) {
      cursor = 100;
      direction = -1;
    }

    if (cursor <= 0) {
      cursor = 0;
      direction = 1;
    }

    document.getElementById("raceCursor")
      .style.left =
      cursor + "%";

  },40);

  document
    .getElementById("gallopButton")
    .onclick = () => {

      if (!accepting) return;

      accepting = false;

      let gain;

      if (cursor >= 42 && cursor <= 58) {

        gain = 8;

        document.getElementById("raceMessage")
          .textContent =
          "PERFECT! 💗";

      } else if (
        cursor >= 30 &&
        cursor <= 70
      ) {

        gain = 5;

        document.getElementById("raceMessage")
          .textContent =
          "GOOD!";

      } else {

        gain = 2;

        document.getElementById("raceMessage")
          .textContent =
          "Missed the perfect zone!";

      }

      player += gain;

      rival += 6;

      round++;

      updateRace();

      if (round >= 10) {

        if (player > rival) {

          completeGame(8,170);

        } else {

          el.innerHTML = `
            <div class="result">

              <h2>🏇 So close!</h2>

              <p>
                Rival: ${rival}
              </p>

              <p>
                You: ${player}
              </p>

              <button class="nextBtn"
                onclick="startGame(8)">
                Race Again
              </button>

            </div>
          `;

        }

        return;
      }

      later(() => {

        cursor = 0;
        direction = 1;
        accepting = true;

        document.getElementById("raceMessage")
          .textContent =
          `Round ${round+1} / 10`;

      },500);

    };

  accepting = true;

  function updateRace() {

    document.getElementById("racePlayer")
      .textContent = player;

    document.getElementById("raceRival")
      .textContent = rival;

    document.getElementById("racePlayerBar")
      .style.width =
      Math.min(player,100) + "%";

    document.getElementById("raceRivalBar")
      .style.width =
      Math.min(rival,100) + "%";

  }

}


/* =========================================================
   GAME 9 — HEARTBREAK CHAMBER
========================================================= */

function initHeartbreakChamber() {

  const el =
    document.getElementById("game9Play");

  let clues = new Set();

  const objects = [
    ["🖼️","Photo Frame","7"],
    ["🌻","Flower Pot","2"],
    ["📖","Diary","4"],
    ["🗝️","Drawer","9"]
  ];

  function render() {

    if (clues.size >= 4) {

      el.innerHTML = `
        <h1 class="game-title">
          🔎 Heartbreak Chamber
        </h1>

        <div class="result">

          <h2>All clues found! 🗝️</h2>

          <p>
            The code is 7249.
          </p>

          <button class="nextBtn"
            onclick="completeGame(9,150)">
            Unlock the Door
          </button>

        </div>
      `;

      return;
    }

    el.innerHTML = `
      <h1 class="game-title">
        🔎 Heartbreak Chamber
      </h1>

      <p class="game-help">
        Search the room for four clues.
      </p>

      <div class="action-grid"
           id="clueGrid"></div>

      <div class="message">
        Clues found: ${clues.size}/4
      </div>
    `;

    objects.forEach((obj,i) => {

      const b =
        document.createElement("button");

      b.className = "action";

      b.textContent =
        obj[0] + " " +
        (
          clues.has(i)
          ? "✓ Found"
          : obj[1]
        );

      b.onclick = () => {

        clues.add(i);

        b.textContent =
          obj[0] + " Clue: " + obj[2];

        later(render,300);

      };

      document
        .getElementById("clueGrid")
        .appendChild(b);

    });

  }

  render();
}


/* =========================================================
   GAME 10 — BOXING
========================================================= */

function initBoxing() {

  const el =
    document.getElementById("game10Play");

  let playerHP = 100;
  let enemyHP = 80;
  let cooldown = false;

  function render() {

    el.innerHTML = `
      <h1 class="game-title">
        🥊 Heartbreak Boxing Match
      </h1>

      <div class="game-card">

        <div class="boss">🥊</div>

        <div>
          You
          <div class="health">
            <div
              class="health-fill player-health"
              style="width:${playerHP}%">
            </div>
          </div>
        </div>

        <div>
          Opponent
          <div class="health">
            <div
              class="health-fill enemy-health"
              style="width:${enemyHP / .8}%">
            </div>
          </div>
        </div>

        <div class="action-grid">

          <button class="action"
            onclick="boxingAction('punch')">
            👊 Punch
          </button>

          <button class="action"
            onclick="boxingAction('heavy')">
            💥 Heavy
          </button>

          <button class="action"
            onclick="boxingAction('block')">
            🛡️ Block
          </button>

          <button class="action"
            onclick="boxingAction('dodge')">
            💨 Dodge
          </button>

        </div>

        <div class="message"
             id="boxingMessage">
        </div>

      </div>
    `;

    window.boxingAction =
      action => {

        if (cooldown) return;

        let damage = 0;
        let defence = false;

        if (action === "punch") {
          damage = 10;
        }

        if (action === "heavy") {
          damage = 18;
        }

        if (
          action === "block" ||
          action === "dodge"
        ) {
          defence = true;
        }

        enemyHP =
          Math.max(
            0,
            enemyHP - damage
          );

        if (enemyHP <= 0) {

          completeGame(10,180);
          return;
        }

        if (!defence) {

          playerHP =
            Math.max(
              0,
              playerHP -
              (6 + Math.floor(
                Math.random()*7
              ))
            );

        } else {

          playerHP =
            Math.max(
              0,
              playerHP - 2
            );

        }

        if (playerHP <= 0) {

          el.innerHTML = `
            <div class="result">

              <h2>Knocked out 💗</h2>

              <button class="nextBtn"
                onclick="startGame(10)">
                Rematch
              </button>

            </div>
          `;

          return;
        }

        cooldown = true;

        render();

        later(() => {
          cooldown = false;
        },400);

      };

  }

  render();
}


/* =========================================================
   GAME 11 — PERFECT MATCH
========================================================= */

function initPerfectMatch() {

  const el =
    document.getElementById("game11Play");

  const pairs = [
    ["🌻","🌻"],
    ["🐬","🐬"],
    ["💗","💗"],
    ["🌹","🌹"],
    ["🍣","🍣"]
  ];

  let matched = 0;

  el.innerHTML = `
    <h1 class="game-title">🧲 Perfect Match</h1>

    <p class="game-help">
      Tap an object, then tap its matching target.
    </p>

    <div class="game-card">

      <div
        id="matchObjects"
        class="action-grid">
      </div>

      <div
        id="matchTargets"
        class="action-grid">
      </div>

      <div class="message"
           id="matchMessage">
      </div>

    </div>
  `;

  let selected = null;

  const objects =
    document.getElementById("matchObjects");

  const targets =
    document.getElementById("matchTargets");

  const shuffled =
    shuffle(pairs.map((p,i)=>({
      value:p[0],
      id:i
    })));

  const targetOrder =
    shuffle(pairs.map((p,i)=>({
      value:p[1],
      id:i
    })));

  shuffled.forEach(obj => {

    const b =
      document.createElement("button");

    b.className = "action";
    b.textContent = obj.value;

    b.onclick = () => {

      selected = obj;

      document
        .querySelectorAll("#matchObjects .action")
        .forEach(x =>
          x.style.outline = ""
        );

      b.style.outline =
        "3px solid #ff7eb6";

    };

    objects.appendChild(b);

  });

  targetOrder.forEach(target => {

    const b =
      document.createElement("button");

    b.className = "action";
    b.textContent =
      "Target " + target.value;

    b.onclick = () => {

      if (!selected) return;

      if (
        selected.id === target.id
      ) {

        b.textContent =
          target.value + " ✓";

        b.disabled = true;

        matched++;

        document.getElementById("matchMessage")
          .textContent =
          `${matched}/5 matched`;

        if (matched >= 5) {

          completeGame(11,160);

        }

      } else {

        document.getElementById("matchMessage")
          .textContent =
          "That isn't the match.";

      }

      selected = null;

    };

    targets.appendChild(b);

  });

}


/* =========================================================
   LILIANA QUIZ
========================================================= */

const lilianaQuestions = [

["What is Liliana's favourite colour?",
["Baby pink","Burgundy","Sky blue","Purple"],0],

["What is Liliana's favourite number?",
["2","3","7","9"],1],

["Which food does Liliana like?",
["Sushi","Curry","Tacos","Pizza"],0],

["Which animal does Liliana like?",
["Dolphins","Tigers","Penguins","Foxes"],0],

["Which flowers does Liliana like?",
["Sunflowers and roses","Lilies and tulips","Orchids and daisies","Lavender and violets"],0],

["When is Liliana's birthday?",
["July 12","July 22","June 22","August 22"],1],

["What colour are Liliana's eyes?",
["Blue","Brown","Green","Hazel"],2],

["What is Liliana's zodiac sign?",
["Leo","Cancer","Gemini","Virgo"],0],

["What is Liliana afraid of?",
["Flying","Drowning","Heights","Spiders"],1],

["What is Liliana's favourite movie?",
["Me Before You","Titanic","The Notebook","Frozen"],0],

["What kind of songs does Liliana like?",
["Sad songs","Only rock","Only country","Only classical"],0],

["What type of writing does Liliana like?",
["Poetry","History","News","Manuals"],0],

["What game does Liliana enjoy?",
["Poker","Golf","Cricket","Chess"],0],

["What did Liliana study at university?",
["Psychology","Law","Engineering","Medicine"],0],

["How many nieces does Liliana have?",
["1","2","3","4"],0],

["How many nephews does Liliana have?",
["2","3","4","5"],2],

["How many siblings does Liliana have?",
["3","4","5","6"],2],

["How many piercings does Liliana have?",
["2","3","4","5"],2],

["What are the names of Liliana's dogs?",
["Aayla and Arlo","Luna and Milo","Bella and Max","Lola and Leo"],0],

["What does Liliana hope to be one day?",
["A mum","A pilot","A singer","A chef"],0]

];


function initLilianaQuiz() {

  initQuizGame(
    12,
    lilianaQuestions,
    8,
    "💗 Who Knows Liliana Best?",
    "Twelve questions about Liliana."
  );

}


/* =========================================================
   GAME 13 — REACTION
========================================================= */

function initReaction() {

  const el =
    document.getElementById("game13Play");

  let round = 0;
  let score = 0;
  let current = null;
  let locked = false;

  function next() {

    if (round >= 10) {

      if (score >= 7) {
        completeGame(13,160);
      } else {
        el.innerHTML = `
          <div class="result">
            <h2>⚡ ${score}/10</h2>
            <p>You need 7 correct.</p>
            <button class="nextBtn"
              onclick="startGame(13)">
              Try Again
            </button>
          </div>
        `;
      }

      return;
    }

    locked = false;

    const types = [
      "TAP NOW",
      "DON'T TAP",
      "LEFT",
      "RIGHT"
    ];

    current =
      types[
        Math.floor(
          Math.random()*types.length
        )
      ];

    el.innerHTML = `
      <h1 class="game-title">
        ⚡ Reaction Gauntlet
      </h1>

      <div class="game-card">

        <div
          style="
            text-align:center;
            font-size:40px;
            margin:20px;
          "
        >
          ${current}
        </div>

        <div class="action-grid">

          <button
            class="action"
            onclick="reactionAnswer('LEFT')">
            ◀ LEFT
          </button>

          <button
            class="action"
            onclick="reactionAnswer('RIGHT')">
            RIGHT ▶
          </button>

          <button
            class="action"
            onclick="reactionAnswer('TAP NOW')">
            💗 TAP
          </button>

          <button
            class="action"
            onclick="reactionAnswer('NOTHING')">
            DON'T TAP
          </button>

        </div>

        <div class="message">
          ${round+1}/10
        </div>

      </div>
    `;

    later(() => {

      if (!locked) {

        if (current === "DON'T TAP") {
          score++;
        }

        round++;
        next();

      }

    },1700);

  }


  window.reactionAnswer =
    answer => {

      if (locked) return;

      locked = true;

      if (
        current === "DON'T TAP"
      ) {

        if (answer === "NOTHING") {
          score++;
        }

      } else {

        if (answer === current) {
          score++;
        }

      }

      round++;

      later(next,250);

    };

  next();

}


/* =========================================================
   GAME 14 — HEART HUNT
========================================================= */

function initHeartHunt() {

  const el =
    document.getElementById("game14Play");

  let found = 0;

  el.innerHTML = `
    <h1 class="game-title">🕵️ Heart Hunt</h1>

    <p class="game-help">
      Find 10 real hearts hiding among the scene.
    </p>

    <div
      id="huntArea"
      class="hunt-area">
    </div>

    <div class="message">
      Found: <span id="huntFound">0</span>/10
    </div>
  `;

  const area =
    document.getElementById("huntArea");

  for(let i=0;i<25;i++) {

    const heart =
      document.createElement("button");

    heart.className = "hunt-heart";

    const real =
      i < 10;

    heart.textContent =
      real ? "💗" : "🌸";

    heart.style.left =
      (Math.random()*88) + "%";

    heart.style.top =
      (Math.random()*82) + "%";

    heart.style.opacity =
      real ? ".8" : ".35";

    heart.onclick = () => {

      if (!real) return;

      if (
        heart.dataset.found
      ) return;

      heart.dataset.found = "1";

      heart.style.opacity = "0";
      heart.style.pointerEvents = "none";

      found++;

      document.getElementById("huntFound")
        .textContent = found;

      if (found >= 10) {

        completeGame(14,160);

      }

    };

    area.appendChild(heart);

  }

}


/* =========================================================
   GAME 15 — LOVE LOCK
========================================================= */

function initLoveLock() {

  const el =
    document.getElementById("game15Play");

  let code = "";

  el.innerHTML = `
    <h1 class="game-title">🔐 Love Lock</h1>

    <p class="game-help">
      Her birthday is July 22 and you've been
      best friends for 6 years.
    </p>

    <div class="game-card">

      <div
        class="lock-display"
        id="lockDisplay">
        ______
      </div>

      <div
        class="keypad"
        id="keypad">
      </div>

      <button
        class="secondary"
        onclick="lockClear()">
        Clear
      </button>

    </div>
  `;

  for(let i=1;i<=9;i++) {

    makeKey(i);

  }

  makeKey(0);

  window.lockClear =
    () => {

      code = "";

      updateLock();

    };


  function makeKey(number) {

    const b =
      document.createElement("button");

    b.className = "key";

    b.textContent = number;

    b.onclick = () => {

      if (code.length >= 6) return;

      code += number;

      updateLock();

      if (code.length === 6) {

        if (code === "060722") {

          completeGame(15,180);

        } else {

          code = "";

          document.getElementById("lockDisplay")
            .textContent =
            "TRY AGAIN";

          later(updateLock,600);

        }

      }

    };

    document
      .getElementById("keypad")
      .appendChild(b);

  }


  function updateLock() {

    document.getElementById("lockDisplay")
      .textContent =
      code.padEnd(6,"_")
        .split("")
        .join(" ");

  }

}


/* =========================================================
   GAME 16 — CUPID
========================================================= */

function initCupid() {

  const el =
    document.getElementById("game16Play");

  let score = 0;
  let shots = 0;

  el.innerHTML = `
    <h1 class="game-title">
      🏹 Cupid Shootout
    </h1>

    <p class="game-help">
      Tap the moving hearts before they disappear.
    </p>

    <div
      id="cupidArea"
      class="hunt-area">
    </div>

    <div class="message">
      Score: <span id="cupidScore">0</span>
      · Shots: <span id="cupidShots">0</span>/15
    </div>
  `;

  const area =
    document.getElementById("cupidArea");

  function spawn() {

    if (shots >= 15) {

      if (score >= 80) {
        completeGame(16,170);
      } else {
        el.innerHTML = `
          <div class="result">
            <h2>🏹 ${score} points</h2>
            <button class="nextBtn"
              onclick="startGame(16)">
              Try Again
            </button>
          </div>
        `;
      }

      return;
    }

    const target =
      document.createElement("button");

    target.className =
      "hunt-heart";

    target.textContent =
      Math.random() < .15
      ? "💛"
      : "💗";

    target.style.left =
      (Math.random()*84) + "%";

    target.style.top =
      (Math.random()*78) + "%";

    area.appendChild(target);

    let clicked = false;

    target.onclick = () => {

      if (clicked) return;

      clicked = true;

      score +=
        target.textContent === "💛"
        ? 20
        : 10;

      shots++;

      document.getElementById("cupidScore")
        .textContent = score;

      document.getElementById("cupidShots")
        .textContent = shots;

      target.remove();

      later(spawn,150);

    };

    later(() => {

      if (!clicked) {

        target.remove();

        shots++;

        document.getElementById("cupidShots")
          .textContent = shots;

        later(spawn,100);

      }

    },1000);

  }

  spawn();

}


/* =========================================================
   GAME 17 — COUNTDOWN
========================================================= */

function initCountdown() {

  const el =
    document.getElementById("game17Play");

  let challenge = 0;
  let score = 0;

  const challenges = [
    "stop",
    "tap",
    "green",
    "small",
    "hold",
    "sequence"
  ];

  function render() {

    if (challenge >= 6) {

      if (score >= 4) {
        completeGame(17,170);
      } else {
        el.innerHTML = `
          <div class="result">
            <h2>⏳ ${score}/6</h2>
            <button class="nextBtn"
              onclick="startGame(17)">
              Try Again
            </button>
          </div>
        `;
      }

      return;
    }

    const type =
      challenges[challenge];

    if (type === "stop") {

      let cursor = 0;
      let dir = 1;

      el.innerHTML = `
        <h1 class="game-title">
          ⏳ The Countdown
        </h1>

        <div class="mini-box">

          <div class="stop-bar">

            <div class="stop-zone"></div>

            <div
              id="stopPointer"
              class="stop-pointer">
            </div>

          </div>

          <button
            class="primary"
            onclick="countdownStop()">
            STOP!
          </button>

        </div>
      `;

      const loop =
        every(() => {

          cursor += dir * 4;

          if(cursor >= 100) {
            cursor=100;
            dir=-1;
          }

          if(cursor <= 0) {
            cursor=0;
            dir=1;
          }

          const p =
            document.getElementById(
              "stopPointer"
            );

          if(p) p.style.left =
            cursor + "%";

        },40);

      window.countdownStop = () => {

        clearInterval(loop);

        if(cursor >= 43 && cursor <= 57) {
          score++;
        }

        challenge++;
        later(render,350);

      };

      return;
    }


    if (type === "tap") {

      el.innerHTML = `
        <h1 class="game-title">
          ⏳ The Countdown
        </h1>

        <div class="mini-box">

          <button
            class="primary"
            onclick="countdownTap()">
            TAP THE HEART 💗
          </button>

        </div>
      `;

      window.countdownTap = () => {

        score++;
        challenge++;
        render();

      };

      later(() => {

        if (challenge < 6) {

          challenge++;
          render();

        }

      },1800);

      return;
    }


    if (type === "green") {

      const correct =
        Math.random() < .5;

      el.innerHTML = `
        <h1 class="game-title">
          ⏳ The Countdown
        </h1>

        <div class="mini-box">

          <button
            class="primary"
            style="
              background:
              ${correct
                ? "#286b3a"
                : "#76243b"};
            "
            onclick="countdownColour(${correct})">
            ${correct ? "💚 GREEN" : "❤️ RED"}
          </button>

        </div>
      `;

      window.countdownColour =
        isGreen => {

          if (isGreen) score++;

          challenge++;
          render();

        };

      return;
    }


    if (type === "small") {

      const nums =
        shuffle([3,8,5,1]);

      el.innerHTML = `
        <h1 class="game-title">
          ⏳ The Countdown
        </h1>

        <p class="game-help">
          Tap the smallest number.
        </p>

        <div
          class="action-grid"
          id="numberButtons">
        </div>
      `;

      nums.forEach(num => {

        const b =
          document.createElement("button");

        b.className = "action";

        b.textContent = num;

        b.onclick = () => {

          if (num === 1) score++;

          challenge++;
          render();

        };

        document
          .getElementById("numberButtons")
          .appendChild(b);

      });

      return;
    }


    if (type === "hold") {

      el.innerHTML = `
        <h1 class="game-title">
          ⏳ The Countdown
        </h1>

        <div class="mini-box">

          <button
            id="holdButton"
            class="primary">
            HOLD
          </button>

        </div>
      `;

      const b =
        document.getElementById(
          "holdButton"
        );

      let start = 0;

      b.onpointerdown = e => {

        e.preventDefault();

        start = Date.now();

      };

      b.onpointerup = e => {

        e.preventDefault();

        const duration =
          Date.now()-start;

        if (
          duration >= 700 &&
          duration <= 1500
        ) score++;

        challenge++;
        render();

      };

      return;
    }


    if (type === "sequence") {

      const seq =
        shuffle([0,1,2]);

      let pos = 0;

      el.innerHTML = `
        <h1 class="game-title">
          ⏳ The Countdown
        </h1>

        <div class="action-grid"
             id="seqButtons">

          <button class="action">💗</button>
          <button class="action">⭐</button>
          <button class="action">🌻</button>

        </div>
      `;

      document
        .getElementById("seqButtons")
        .querySelectorAll("button")
        .forEach((b,i) => {

          b.onclick = () => {

            if(i === seq[pos]) {

              pos++;

              if(pos === 3) {

                score++;
                challenge++;
                render();

              }

            } else {

              pos = 0;

            }

          };

        });

    }

  }

  render();

}


/* =========================================================
   GAME 18 — ULTIMATE GAMBLE
========================================================= */

function initGamble() {

  const el =
    document.getElementById("game18Play");

  let pot = 100;
  let turns = 0;

  function render() {

    el.innerHTML = `
      <h1 class="game-title">
        🎲 Ultimate Gamble
      </h1>

      <p class="game-help">
        Start with 100. Cash out safely or keep risking it.
      </p>

      <div class="game-card">

        <div class="pot">
          ${pot}
        </div>

        <div class="message">
          Turn ${turns}
        </div>

        <div class="action-grid">

          <button class="action"
            onclick="gamble50()">
            50/50 ×2
          </button>

          <button class="action"
            onclick="gambleRisk()">
            25% ×4
          </button>

          <button class="action"
            onclick="gambleSafe()">
            Safe Bank
          </button>

          <button class="action"
            onclick="gambleCash()">
            Cash Out
          </button>

        </div>

      </div>
    `;

    window.gamble50 = () => {

      turns++;

      if (Math.random() < .5) {
        pot *= 2;
      } else {
        pot =
          Math.max(
            50,
            Math.floor(pot/2)
          );
      }

      render();

    };

    window.gambleRisk = () => {

      turns++;

      if (Math.random() < .25) {
        pot *= 4;
      } else {
        pot = 0;
      }

      render();

    };

    window.gambleSafe = () => {

      if (pot >= 100) {
        completeGame(18,180);
      } else {
        render();
      }

    };

    window.gambleCash = () => {

      if (pot > 100) {

        completeGame(
          18,
          100 + pot
        );

      } else {

        render();

      }

    };

  }

  render();

}


/* =========================================================
   GAME 19 — LAST STAND
========================================================= */

function initBoss() {

  const el =
    document.getElementById("game19Play");

  let bossHP = 120;
  let playerHP = 100;
  let phase = 1;

  function render() {

    phase =
      bossHP > 80
      ? 1
      : bossHP > 40
      ? 2
      : 3;

    el.innerHTML = `
      <h1 class="game-title">
        👑 Admirer's Last Stand
      </h1>

      <p class="game-help">
        Phase ${phase} · Defeat the admirer.
      </p>

      <div class="game-card">

        <div class="boss">
          ${phase === 1 ? "👑" :
            phase === 2 ? "😈" : "🔥"}
        </div>

        <div>
          Your Health
          <div class="health">
            <div
              class="health-fill player-health"
              style="width:${playerHP}%">
            </div>
          </div>
        </div>

        <div>
          Boss Health
          <div class="health">
            <div
              class="health-fill enemy-health"
              style="width:${bossHP / 1.2}%">
            </div>
          </div>
        </div>

        <div class="action-grid">

          <button class="action"
            onclick="bossMove('attack')">
            ⚔️ Attack
          </button>

          <button class="action"
            onclick="bossMove('guard')">
            🛡️ Guard
          </button>

          <button class="action"
            onclick="bossMove('special')">
            💥 Special
          </button>

        </div>

        <div class="message"
          id="bossMessage">
          Phase ${phase}
        </div>

      </div>
    `;

    window.bossMove =
      action => {

        let damage = 0;
        let taken = 8;

        if (action === "attack") {
          damage = 14;
        }

        if (action === "special") {
          damage = 24;
          taken = 12;
        }

        if (action === "guard") {
          damage = 6;
          taken = 2;
        }

        bossHP =
          Math.max(
            0,
            bossHP - damage
          );

        if (bossHP <= 0) {

          completeGame(19,220);
          return;

        }

        playerHP =
          Math.max(
            0,
            playerHP - taken
          );

        if (playerHP <= 0) {

          el.innerHTML = `
            <div class="result">

              <h2>Defeated 💗</h2>

              <button class="nextBtn"
                onclick="startGame(19)">
                Try Again
              </button>

            </div>
          `;

          return;

        }

        render();

      };

  }

  render();

}


/* =========================================================
   GAME 20 — WORD FIND
========================================================= */

const wordList = [
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


function initWordFind() {

  const el =
    document.getElementById("game20Play");

  const size = 12;

  let grid =
    Array.from(
      {length:size},
      () =>
        Array(size).fill("")
    );

  let placements = [];

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

    for(let attempt=0;attempt<300;attempt++) {

      const dir =
        directions[
          Math.floor(
            Math.random()*
            directions.length
          )
        ];

      const row =
        Math.floor(
          Math.random()*size
        );

      const col =
        Math.floor(
          Math.random()*size
        );

      const endRow =
        row + dir[0]*(word.length-1);

      const endCol =
        col + dir[1]*(word.length-1);

      if(
        endRow < 0 ||
        endRow >= size ||
        endCol < 0 ||
        endCol >= size
      ) continue;

      let good = true;

      for(let i=0;i<word.length;i++) {

        const r =
          row + dir[0]*i;

        const c =
          col + dir[1]*i;

        if(
          grid[r][c] !== "" &&
          grid[r][c] !== word[i]
        ) {

          good = false;
          break;

        }

      }

      if(!good) continue;

      for(let i=0;i<word.length;i++) {

        const r =
          row + dir[0]*i;

        const c =
          col + dir[1]*i;

        grid[r][c] =
          word[i];

      }

      placements.push({
        word,
        row,
        col,
        dr:dir[0],
        dc:dir[1]
      });

      return true;

    }

    return false;

  }


  /*
    Longer words first.
    This dramatically improves the
    chance of placing all 25.
  */

  shuffle(wordList)
    .sort((a,b)=>b.length-a.length)
    .forEach(placeWord);


  const letters =
    "ABCDEFGHIJKLMNOPQRSTUVWXYZ";

  for(let r=0;r<size;r++) {

    for(let c=0;c<size;c++) {

      if(!grid[r][c]) {

        grid[r][c] =
          letters[
            Math.floor(
              Math.random()*letters.length
            )
          ];

      }

    }

  }

  let found =
    new Set();

  let startCell = null;
  let selecting = false;

  el.innerHTML = `
    <h1 class="game-title">
      🔎 Liliana's Word Find
    </h1>

    <p class="game-help">
      Find all 25 words. Drag across letters.
    </p>

    <div
      class="word-grid"
      id="wordGrid">
    </div>

    <div
      class="message"
      id="wordMessage">
      Found 0 / ${placements.length}
    </div>

    <div
      style="
        max-height:90px;
        overflow:auto;
        text-align:center;
        color:#d8a7ba;
        font-size:12px;
      "
    >
      ${placements
        .map(x=>x.word)
        .join(" · ")}
    </div>
  `;

  const wordGrid =
    document.getElementById("wordGrid");

  for(let r=0;r<size;r++) {

    for(let c=0;c<size;c++) {

      const cell =
        document.createElement("div");

      cell.className =
        "word-cell";

      cell.textContent =
        grid[r][c];

      cell.dataset.row = r;
      cell.dataset.col = c;

      wordGrid.appendChild(cell);

    }

  }


  function getCell(e) {

    const touch =
      e.touches
      ? e.touches[0]
      : e;

    const element =
      document.elementFromPoint(
        touch.clientX,
        touch.clientY
      );

    if(
      element &&
      element.classList.contains(
        "word-cell"
      )
    ) {
      return element;
    }

    return null;

  }


  function selectBetween(a,b) {

    const r1 =
      Number(a.dataset.row);

    const c1 =
      Number(a.dataset.col);

    const r2 =
      Number(b.dataset.row);

    const c2 =
      Number(b.dataset.col);

    const dr =
      Math.sign(r2-r1);

    const dc =
      Math.sign(c2-c1);

    const distance =
      Math.max(
        Math.abs(r2-r1),
        Math.abs(c2-c1)
      );

    if(
      !(
        r1 === r2 ||
        c1 === c2 ||
        Math.abs(r2-r1) ===
        Math.abs(c2-c1)
      )
    ) return [];

    const cells = [];

    for(let i=0;i<=distance;i++) {

      const r =
        r1 + dr*i;

      const c =
        c1 + dc*i;

      const cell =
        wordGrid.querySelector(
          `[data-row="${r}"][data-col="${c}"]`
        );

      if(cell) cells.push(cell);

    }

    return cells;

  }


  function checkSelection(cells) {

    if(cells.length < 2) return;

    const letters =
      cells
        .map(c=>c.textContent)
        .join("");

    const reverse =
      letters
        .split("")
        .reverse()
        .join("");

    const match =
      placements.find(p =>
        !found.has(p.word) &&
        (
          p.word === letters ||
          p.word === reverse
        )
      );

    if(match) {

      found.add(match.word);

      cells.forEach(c =>
        c.classList.add("found")
      );

      document.getElementById("wordMessage")
        .textContent =
        `Found ${found.size} / ${placements.length}`;

      if(
        found.size >= placements.length
      ) {

        completeGame(20,260);

      }

    }

  }


  wordGrid.onpointerdown = e => {

    e.preventDefault();

    const cell = getCell(e);

    if(!cell) return;

    selecting = true;
    startCell = cell;

    cell.classList.add("selected");

  };


  wordGrid.onpointermove = e => {

    if(!selecting) return;

    e.preventDefault();

    const cell = getCell(e);

    if(!cell) return;

    const cells =
      selectBetween(
        startCell,
        cell
      );

    wordGrid
      .querySelectorAll(".selected")
      .forEach(c =>
        c.classList.remove("selected")
      );

    cells.forEach(c =>
      c.classList.add("selected")
    );

  };


  wordGrid.onpointerup = e => {

    if(!selecting) return;

    e.preventDefault();

    const cell = getCell(e);

    if(cell) {

      const cells =
        selectBetween(
          startCell,
          cell
        );

      checkSelection(cells);

    }

    wordGrid
      .querySelectorAll(".selected")
      .forEach(c =>
        c.classList.remove("selected")
      );

    selecting = false;
    startCell = null;

  };

}


/* =========================================================
   GAME 21 — SUNFLOWER
========================================================= */

function initSunflower() {

  const el =
    document.getElementById("game21Play");

  el.innerHTML = `
    <h1 class="game-title">
      🌻 Draw a Sunflower
    </h1>

    <p class="game-help">
      Draw your own sunflower. Add as much detail
      as you like.
    </p>

    <canvas
      id="flowerCanvas"
      width="700"
      height="520">
    </canvas>

    <div class="draw-controls">

      <button onclick="setBrush(5)">
        Small
      </button>

      <button onclick="setBrush(12)">
        Medium
      </button>

      <button onclick="setBrush(22)">
        Large
      </button>

      <button onclick="undoFlower()">
        Undo
      </button>

      <button onclick="clearFlower()">
        Clear
      </button>

    </div>

    <button
      class="primary"
      onclick="finishFlower()">
      Finish Flower 🌻
    </button>
  `;

  const canvas =
    document.getElementById("flowerCanvas");

  const ctx =
    canvas.getContext("2d");

  ctx.lineCap = "round";
  ctx.lineJoin = "round";

  let drawing = false;
  let brush = 10;

  let history = [];

  function position(e) {

    const rect =
      canvas.getBoundingClientRect();

    const point =
      e.touches
      ? e.touches[0]
      : e;

    return {
      x:
        (point.clientX -
        rect.left) *
        canvas.width /
        rect.width,

      y:
        (point.clientY -
        rect.top) *
        canvas.height /
        rect.height
    };

  }

  function begin(e) {

    e.preventDefault();

    drawing = true;

    const p =
      position(e);

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

  function draw(e) {

    if(!drawing) return;

    e.preventDefault();

    const p =
      position(e);

    ctx.lineWidth = brush;
    ctx.strokeStyle = "#7d173f";

    ctx.lineTo(p.x,p.y);
    ctx.stroke();

  }

  function end() {
    drawing = false;
  }

  canvas.addEventListener(
    "pointerdown",
    begin
  );

  canvas.addEventListener(
    "pointermove",
    draw
  );

  canvas.addEventListener(
    "pointerup",
    end
  );

  canvas.addEventListener(
    "pointercancel",
    end
  );

  window.setBrush = size => {
    brush = size;
  };

  window.undoFlower = () => {

    if(!history.length) return;

    const image =
      history.pop();

    ctx.putImageData(image,0,0);

  };

  window.clearFlower = () => {

    history.push(
      ctx.getImageData(
        0,
        0,
        canvas.width,
        canvas.height
      )
    );

    ctx.clearRect(
      0,
      0,
      canvas.width,
      canvas.height
    );

  };

  window.finishFlower = () => {

    completeGame(21,180);

  };

}


/* =========================================================
   GAME 22 — LULU DERBY
========================================================= */

const derbyQuestions = [

["What is the capital of Canada?",["Ottawa","Toronto","Vancouver","Montreal"],0],
["What is the largest mammal?",["Elephant","Blue whale","Giraffe","Orca"],1],
["How many months are in a year?",["10","11","12","13"],2],
["What is the currency of the United Kingdom?",["Euro","Pound","Dollar","Franc"],1],
["Which planet is closest to the Sun?",["Venus","Earth","Mercury","Mars"],2],
["How many chess pieces does each player start with?",["12","14","16","18"],2],
["Who wrote the Harry Potter books?",["J.K. Rowling","Suzanne Collins","Roald Dahl","Stephen King"],0],
["What is the largest continent?",["Africa","Asia","Europe","North America"],1],
["Which instrument has 88 keys?",["Violin","Piano","Flute","Harp"],1],
["What is the chemical symbol for oxygen?",["O","Ox","C","Og"],0],
["What is the square root of 81?",["7","8","9","10"],2],
["In which year did Apollo 11 land on the Moon?",["1959","1969","1979","1989"],1],
["Where is the Great Pyramid of Giza?",["Egypt","Greece","Mexico","Peru"],0],
["What is the main language of Brazil?",["Spanish","Portuguese","French","Italian"],1],
["What is the largest desert on Earth?",["Sahara","Gobi","Antarctica","Arabian"],2],
["In tennis, what comes after 30?",["35","40","45","50"],1],
["Which vitamin is commonly produced by sunlight exposure?",["A","B12","C","D"],3],
["Approximately how many bones does an adult human have?",["106","206","306","406"],1],
["The Amazon rainforest is mainly in which continent?",["Africa","Asia","South America","Europe"],2],
["Where is Big Ben?",["London","Paris","Rome","Berlin"],0],
["Which ocean is the largest?",["Atlantic","Pacific","Indian","Arctic"],1],
["How many moons does Mars have?",["1","2","3","4"],1],
["Which planet is the hottest?",["Mercury","Venus","Mars","Jupiter"],1],
["Approximately how fast does light travel?",["3,000 km/s","30,000 km/s","300,000 km/s","3,000,000 km/s"],2],
["Who wrote Romeo and Juliet?",["Shakespeare","Dickens","Austen","Poe"],0],
["Where are penguins naturally associated with?",["Antarctica","Sahara","Amazon","Alps"],0],
["What is the currency of India?",["Rupee","Yen","Won","Peso"],0],
["Where is the Taj Mahal?",["India","Pakistan","Nepal","Bangladesh"],0],
["Who is the Greek god associated with the sea?",["Zeus","Ares","Poseidon","Apollo"],2],
["What does Roman numeral X mean?",["5","10","50","100"],1],
["How many Olympic rings are there?",["4","5","6","7"],1],
["How many suits are in a standard deck of cards?",["2","3","4","5"],2],
["How many cards are in a standard deck?",["42","52","62","72"],1],
["How many sides does a square have?",["3","4","5","6"],1],
["The Nile is associated with which continent?",["Africa","Asia","Europe","Australia"],0],
["The Alps are mainly in which part of the world?",["Europe","Africa","Asia","South America"],0],
["At what temperature does water freeze in Celsius?",["0","10","20","32"],0],
["How many metres are in a kilometre?",["100","500","1000","1500"],2],
["How many seconds are in a minute?",["30","45","60","90"],2],
["How many hours are in a day?",["12","18","24","30"],2],
["How many days are in a week?",["5","6","7","8"],2],
["How many days are approximately in a year?",["265","300","365","400"],2],
["Which is the farthest major planet from the Sun?",["Saturn","Uranus","Neptune","Jupiter"],2],
["What is Pluto classified as?",["Planet","Dwarf planet","Moon","Star"],1],
["What shape is DNA famously described as?",["Single spiral","Double helix","Square","Triangle"],1],
["What process allows plants to use light to make food?",["Respiration","Photosynthesis","Fermentation","Digestion"],1],
["Which organs are primarily used for breathing?",["Kidneys","Lungs","Liver","Stomach"],1],
["Which blood cells carry oxygen?",["White cells","Red cells","Platelets","Stem cells"],1],
["What is the largest organ of the human body?",["Heart","Skin","Liver","Brain"],1],
["What part of the eye controls how much light enters?",["Retina","Iris","Lens","Cornea"],1],
["Which part of the brain is the largest region?",["Cerebrum","Cerebellum","Medulla","Brainstem"],0],
["What element has the symbol Fe?",["Fluorine","Iron","Francium","Fermium"],1],
["What element has the symbol Na?",["Nitrogen","Sodium","Neon","Nickel"],1],
["What element has the symbol K?",["Krypton","Potassium","Kryptonium","Calcium"],1],
["What element has the symbol Ag?",["Gold","Silver","Argon","Aluminium"],1],
["What element has the symbol Cu?",["Copper","Carbon","Cobalt","Calcium"],0],
["What gas is represented by CO2?",["Carbon monoxide","Carbon dioxide","Oxygen","Methane"],1],
["What pH is neutral?",["0","5","7","14"],2],
["What force pulls objects toward Earth?",["Magnetism","Gravity","Friction","Pressure"],1],
["What is the SI unit of energy?",["Watt","Joule","Newton","Volt"],1],
["What unit measures electric current?",["Ampere","Watt","Joule","Ohm"],0],
["Sound levels are commonly measured in?",["Decibels","Metres","Litres","Watts"],0],
["What instrument detects earthquakes?",["Barometer","Seismometer","Thermometer","Altimeter"],1],
["Molten rock beneath Earth's surface is called?",["Lava","Magma","Granite","Ash"],1],
["Clouds are mainly made of?",["Dust only","Water droplets and ice","Smoke","Salt"],1],
["How many colours are traditionally listed in a rainbow?",["5","6","7","8"],2],
["Snowflakes commonly have what symmetry?",["Five-fold","Six-fold","Eight-fold","Ten-fold"],1],
["How do honeybees famously communicate the location of food?",["Dancing","Singing","Jumping","Digging"],0],
["Butterflies can taste using their?",["Wings","Feet","Antennae","Tail"],1],
["How many hearts does an octopus have?",["1","2","3","4"],2],
["How many neck vertebrae does a giraffe usually have?",["5","7","9","12"],1],
["Which animal is the fastest land animal?",["Cheetah","Horse","Lion","Gazelle"],0],
["What is the largest living bird?",["Eagle","Ostrich","Emu","Swan"],1],
["Which country is famous for kangaroos?",["Australia","Canada","India","Brazil"],0],
["Which bird is strongly associated with New Zealand?",["Kiwi","Eagle","Flamingo","Toucan"],0],
["Koalas are native to?",["Australia","New Zealand","Japan","India"],0],
["Mount Kilimanjaro is in?",["Kenya","Tanzania","Egypt","Morocco"],1],
["The Gobi Desert is in?",["Asia","Africa","Europe","Australia"],0],
["The Amazon River is in?",["South America","Africa","Asia","Europe"],0],
["The Mediterranean Sea lies between Europe and?",["Africa","Australia","Antarctica","North America"],0],
["The Panama Canal connects the Atlantic and?",["Pacific","Indian","Arctic","Southern"],0],
["The Suez Canal connects the Mediterranean Sea with the?",["Red Sea","Black Sea","Arabian Sea","Baltic Sea"],0],
["The Prime Meridian passes through?",["Greenwich","Rome","Paris","Madrid"],0],
["The Equator represents?",["0° latitude","0° longitude","90° latitude","180° longitude"],0],
["The Tropic of Cancer is in which hemisphere?",["Northern","Southern","Both equally","Neither"],0],
["Which is the coldest continent?",["Asia","Antarctica","Europe","North America"],1],
["Which is the smallest continent by land area?",["Europe","Australia","Africa","South America"],1],
["What is the world's smallest country by area?",["Monaco","Vatican City","Malta","Liechtenstein"],1],
["Which is the largest country by land area?",["Canada","China","Russia","USA"],2],
["The Olympic Games feature how many rings?",["4","5","6","7"],1],
["The FIFA World Cup is primarily associated with?",["Football","Tennis","Cricket","Rugby"],0],
["Wimbledon is a tournament for which sport?",["Tennis","Golf","Football","Cycling"],0],
["The Tour de France is associated with?",["Cycling","Running","Swimming","Skiing"],0],
["The Super Bowl is associated with?",["American football","Baseball","Basketball","Ice hockey"],0]
];


function initDerby() {

  const el =
    document.getElementById("game22Play");

  let selected = null;
  let qIndex = 0;
  let player = 0;
  let rival = 0;

  const horses = [
    "💗 Rose Runner",
    "💙 Blue Moon",
    "💛 Golden Lulu",
    "💜 Stardust"
  ];

  el.innerHTML = `
    <h1 class="game-title">
      🏇 THE LULU DERBY
    </h1>

    <p class="game-help">
      Choose your horse. Answer 100 random trivia
      questions to race it to victory.
    </p>

    <div
      class="action-grid"
      id="horseChoices">
    </div>

    <div
      class="race-track"
      id="derbyTrack"
      style="display:none">
    </div>

    <div
      id="derbyQuestion"
      style="display:none">
    </div>
  `;

  const choices =
    document.getElementById(
      "horseChoices"
    );

  horses.forEach((horse,i) => {

    const b =
      document.createElement("button");

    b.className = "action";
    b.textContent = horse;

    b.onclick = () => {

      selected = i;

      choices.style.display = "none";

      document.getElementById("derbyTrack")
        .style.display = "block";

      document.getElementById("derbyQuestion")
        .style.display = "block";

      showDerbyQuestion();

    };

    choices.appendChild(b);

  });


  function showDerbyQuestion() {

    if(qIndex >= 100) {

      const winner =
        player > rival
        ? "YOU WIN! 🏆"
        : "The rival horses won this time!";

      if(player > rival) {

        completeGame(22,300);

      } else {

        el.innerHTML = `
          <div class="result">

            <h2>${winner}</h2>

            <p>
              Your horse: ${player}
            </p>

            <p>
              Rivals: ${rival}
            </p>

            <button
              class="nextBtn"
              onclick="startGame(22)">
              Run the Derby Again
            </button>

          </div>
        `;

      }

      return;
    }

    const q =
      derbyQuestions[
        qIndex %
        derbyQuestions.length
      ];

    /*
      The list contains exactly 100 questions.
      We randomise their order once.
    */

    if(qIndex === 0) {

      derbyQuestions
        .sort(() => Math.random()-.5);

    }

    const answers =
      shuffleAnswers({
        options:q[1],
        answer:q[2]
      });

    const box =
      document.getElementById(
        "derbyQuestion"
      );

    box.innerHTML = `
      <div class="game-card">

        <div class="question">
          ${qIndex+1} / 100
        </div>

        <div class="question">
          ${q[0]}
        </div>

        <div
          class="answers"
          id="derbyAnswers">
        </div>

        <div class="message">
          Your horse: ${player}
          · Rivals: ${rival}
        </div>

      </div>
    `;

    answers.forEach(answer => {

      const b =
        document.createElement("button");

      b.className = "answer";

      b.textContent =
        answer.text;

      b.onclick = () => {

        if(answer.correct) {

          player +=
            3 +
            Math.floor(
              Math.random()*3
            );

        } else {

          rival +=
            1 +
            Math.floor(
              Math.random()*3
            );

        }

        qIndex++;

        updateDerbyTrack();

        later(
          showDerbyQuestion,
          180
        );

      };

      document
        .getElementById("derbyAnswers")
        .appendChild(b);

    });

  }


  function updateDerbyTrack() {

    document.getElementById("derbyTrack")
      .innerHTML = `

        <div class="race-row">

          <div class="race-name">
            <span>${horses[selected]}</span>
            <span>${player}</span>
          </div>

          <div class="race-bar">
            <div
              class="race-fill"
              style="
                width:
                ${Math.min(player,100)}%
              ">
            </div>
          </div>

        </div>

        <div class="race-row">

          <div class="race-name">
            <span>Rivals</span>
            <span>${rival}</span>
          </div>

          <div class="race-bar">
            <div
              class="race-fill"
              style="
                width:
                ${Math.min(rival,100)}%
              ">
            </div>
          </div>

        </div>

      `;

  }

}


/* =========================================================
   FINAL 50 QUESTIONS
========================================================= */

const finalQuestions = [

["Which colour is most strongly associated with Liliana's favourite colour?",
["Baby pink","Burgundy","Navy","Gold"],0],

["Which number is Liliana's favourite?",
["2","3","5","8"],1],

["Which food is one of Liliana's favourites?",
["Sushi","Pasta","Burgers","Curry"],0],

["Which sea animal does Liliana like?",
["Dolphins","Seals","Sharks","Whales"],0],

["Which flower is one of Liliana's favourites?",
["Sunflower","Tulip","Orchid","Carnation"],0],

["Which other flower does Liliana like?",
["Rose","Daisy","Lily","Violet"],0],

["Which month is Liliana's birthday in?",
["June","July","August","September"],1],

["What day of July is Liliana's birthday?",
["12","17","22","27"],2],

["What colour are Liliana's eyes?",
["Green","Brown","Blue","Grey"],0],

["Which zodiac sign is Liliana?",
["Leo","Cancer","Libra","Aries"],0],

["What fear is associated with Liliana?",
["Drowning","Flying","Thunder","Darkness"],0],

["Which film is Liliana's favourite?",
["Me Before You","Frozen","Titanic","Matilda"],0],

["What type of songs does Liliana enjoy?",
["Sad songs","Only dance songs","Only metal","Only jazz"],0],

["What form of writing does Liliana like?",
["Poetry","Biographies","News","Cookbooks"],0],

["Which card game does Liliana enjoy?",
["Poker","Solitaire","Snap","Go Fish"],0],

["Liliana enjoys what kind of games besides poker?",
["Gambling games","Puzzle games only","Sports games only","Word games only"],0],

["What family dream has Liliana talked about?",
["Becoming a mum","Having ten dogs","Living on Mars","Becoming a pilot"],0],

["What gender of baby girl does Liliana hope to have someday?",
["A baby girl","A baby boy","Twins only","Triplets only"],0],

["What subject did Liliana study at university?",
["Psychology","Physics","Accounting","Geography"],0],

["How many nieces does Liliana have?",
["1","2","3","4"],0],

["How many nephews does Liliana have?",
["2","3","4","5"],2],

["How many nieces and nephews does Liliana have altogether?",
["3","4","5","6"],2],

["How many siblings does Liliana have?",
["3","4","5","6"],2],

["How many piercings does Liliana have?",
["2","3","4","5"],2],

["Which dog is one of Liliana's?",
["Aayla","Bella","Molly","Ruby"],0],

["Which other dog belongs to Liliana?",
["Arlo","Oscar","Teddy","Charlie"],0],

["Which pair are Liliana's dogs?",
["Aayla and Arlo","Luna and Milo","Bella and Max","Ruby and Teddy"],0],

["How long have Bree and Liliana been best friends?",
["4 years","5 years","6 years","7 years"],2],

["Which personality trait describes Liliana?",
["Sweet","Cold","Unfriendly","Distant"],0],

["Which other personality trait describes Liliana?",
["Caring","Careless","Impatient","Harsh"],0],

["Which word fits Liliana's personality?",
["Charismatic","Quiet","Gruff","Aloof"],0],

["Which quality is associated with Liliana?",
["Empathetic","Uncaring","Selfish","Dismissive"],0],

["Liliana likes spending time around whom?",
["Children","Only adults","Only animals","No one"],0],

["Which playful description fits Liliana?",
["Flirtatious","Serious all the time","Shy with everyone","Grumpy"],0],

["What colour would suit a Liliana-themed birthday?",
["Baby pink","Black","Brown","Grey"],0],

["Which date represents Liliana's birthday?",
["07/22","06/22","07/12","08/22"],0],

["Which pair combines two things Liliana likes?",
["Sushi and dolphins","Pizza and wolves","Curry and bears","Pasta and foxes"],0],

["Which pair contains two flowers Liliana likes?",
["Sunflowers and roses","Tulips and orchids","Daisies and lilies","Violets and carnations"],0],

["Which activity fits Liliana's interests?",
["Poker","Skiing","Fishing","Golf"],0],

["Which academic field is connected to Liliana?",
["Psychology","Engineering","Architecture","Chemistry"],0],

["What kind of music can match Liliana's taste?",
["Sad songs","Only marches","Only opera","Only nursery rhymes"],0],

["Which creative form does Liliana enjoy?",
["Poetry","Technical manuals","Legal documents","Maps"],0],

["What animal combines one of Liliana's interests with the ocean?",
["Dolphin","Horse","Eagle","Tiger"],0],

["Which flower would most likely appear in a Liliana-themed design?",
["Sunflower","Cactus","Fern","Pine tree"],0],

["Which statement about Liliana's eyes is correct?",
["They are green","They are blue","They are brown","They are grey"],0],

["Which statement about Liliana's birthday is correct?",
["It is July 22","It is June 22","It is July 12","It is August 12"],0],

["Which statement about Liliana's university study is correct?",
["She studied Psychology","She studied Medicine","She studied Law","She studied Engineering"],0],

["Which statement about Liliana's family is correct?",
["She has 5 siblings","She has 2 siblings","She has 3 siblings","She has 8 siblings"],0],

["Which statement best combines two known things about Liliana?",
["She likes sushi and dolphins","She likes pizza and lions","She likes curry and horses","She likes pasta and wolves"],0],

["Which description best fits Liliana?",
["A caring, empathetic and charismatic person","A cold and distant person","A person who dislikes children","A person who dislikes flowers"],0]

];


function initFinalChallenge() {

  const el =
    document.getElementById("game23Play");

  let questions =
    shuffle(finalQuestions);

  let index = 0;
  let score = 0;
  let locked = false;

  function show() {

    if(index >= 50) {

      if(score >= 40) {

        completeGame(
          23,
          500
        );

      } else {

        el.innerHTML = `
          <div class="result">

            <h2>💕 Final Challenge</h2>

            <p>
              You scored ${score}/50.
            </p>

            <p>
              You need 40 correct to pass.
            </p>

            <button
              class="nextBtn"
              onclick="startGame(23)">
              Try Again
            </button>

          </div>
        `;

      }

      return;
    }

    locked = false;

    const q =
      questions[index];

    const answers =
      shuffleAnswers({
        options:q[1],
        answer:q[2]
      });

    el.innerHTML = `
      <h1 class="game-title">
        💕 THE FINAL CHALLENGE
      </h1>

      <p class="game-help">
        How well do you know Liliana?
      </p>

      <div class="question-card">

        <div class="question-number">
          Question ${index+1} / 50
        </div>

        <div class="question">
          ${q[0]}
        </div>

        <div
          class="answers"
          id="finalAnswers">
        </div>

        <div
          class="message"
          id="finalMessage">
        </div>

      </div>
    `;

    answers.forEach(answer => {

      const b =
        document.createElement("button");

      b.className = "answer";

      b.textContent =
        answer.text;

      b.onclick = () => {

        if(locked) return;

        locked = true;

        if(answer.correct) {

          score++;

          b.classList.add("correct");

          document.getElementById(
            "finalMessage"
          ).textContent =
            "Correct! 💗";

        } else {

          b.classList.add("wrong");

          document.getElementById(
            "finalMessage"
          ).textContent =
            "Not quite!";

        }

        index++;

        later(show,300);

      };

      document
        .getElementById("finalAnswers")
        .appendChild(b);

    });

  }

  show();

}


/* =========================================================
   FINISH
========================================================= */

function finishJourney() {

  showScreen("ending");

  document.getElementById("endingScore")
    .textContent =
    state.score;

  document.getElementById("endingText")
    .textContent =
    `You completed all 23 levels, ${state.name}.`;

  const reward =
    document.getElementById("callReward");

  /*
    IMPORTANT:
    Exactly 3000 does NOT qualify.
    The requirement is strictly greater than 3000.
  */

  if(state.score > 3000) {

    reward.innerHTML = `
      <div
        style="
          margin-top:20px;
          padding:18px;
          border-radius:18px;
          background:#3b1830;
          border:1px solid #ff7eb6;
        "
      >

        <h2>📞 Private Call Reward!</h2>

        <p>
          You finished with more than 3000 points!
        </p>

      </div>
    `;

  } else {

    reward.innerHTML = `
      <div
        style="
          margin-top:20px;
          padding:18px;
          border-radius:18px;
          background:#291321;
        "
      >

        <p>
          You completed the journey 💗
        </p>

      </div>
    `;

  }

}


/* =========================================================
   SIMPLE BUILT-IN MUSIC
========================================================= */

let audioContext = null;
let musicGain = null;
let musicOn = false;
let musicTimer = null;

const musicNotes = [
  261.63,
  329.63,
  392.00,
  329.63,
  293.66,
  349.23,
  440.00,
  349.23
];

function startMusic() {

  if(musicOn) return;

  try {

    if(!audioContext) {

      audioContext =
        new (
          window.AudioContext ||
          window.webkitAudioContext
        )();

      musicGain =
        audioContext.createGain();

      musicGain.gain.value = .045;

      musicGain.connect(
        audioContext.destination
      );

    }

    audioContext.resume();

    musicOn = true;

    let note = 0;

    function playNote() {

      if(!musicOn) return;

      const osc =
        audioContext.createOscillator();

      const gain =
        audioContext.createGain();

      osc.type = "sine";

      osc.frequency.value =
        musicNotes[
          note % musicNotes.length
        ];

      gain.gain.setValueAtTime(
        .0001,
        audioContext.currentTime
      );

      gain.gain.exponentialRampToValueAtTime(
        .12,
        audioContext.currentTime + .03
      );

      gain.gain.exponentialRampToValueAtTime(
        .0001,
        audioContext.currentTime + .28
      );

      osc.connect(gain);
      gain.connect(musicGain);

      osc.start();
      osc.stop(
        audioContext.currentTime + .3
      );

      note++;

      musicTimer =
        setTimeout(
          playNote,
          360
        );

    }

    playNote();

    updateMusicButtons();

  } catch(e) {

    console.log(
      "Audio unavailable",
      e
    );

  }

}


function stopMusic() {

  musicOn = false;

  if(musicTimer) {

    clearTimeout(musicTimer);

    musicTimer = null;

  }

  if(audioContext) {

    try {
      audioContext.suspend();
    } catch(e) {}

  }

  updateMusicButtons();

}


function toggleMusic() {

  if(musicOn) {
    stopMusic();
  } else {
    startMusic();
  }

}


function updateMusicButtons() {

  const text =
    musicOn
    ? "♫ Music On"
    : "♫ Music Off";

  const a =
    document.getElementById(
      "homeMusicText"
    );

  const b =
    document.getElementById(
      "musicButton"
    );

  if(a) a.textContent = text;
  if(b) b.textContent = text;

}


/* =========================================================
   KEYBOARD SUPPORT
========================================================= */

document.addEventListener(
  "keydown",
  e => {

    if(
      document.getElementById("game1")
        .classList.contains("active")
    ) {

      if(e.key === "ArrowLeft") {

        e.preventDefault();

        bh.moving = -1;
        moveCatcherImmediate(-1);

      }

      if(e.key === "ArrowRight") {

        e.preventDefault();

        bh.moving = 1;
        moveCatcherImmediate(1);

      }

    }

  }
);


document.addEventListener(
  "keyup",
  e => {

    if(
      e.key === "ArrowLeft" ||
      e.key === "ArrowRight"
    ) {

      bh.moving = 0;

    }

  }
);


/* =========================================================
   PREVENT ACCIDENTAL MOBILE ZOOM / GESTURES
========================================================= */

document.addEventListener(
  "gesturestart",
  e => e.preventDefault()
);

document.addEventListener(
  "gesturechange",
  e => e.preventDefault()
);

document.addEventListener(
  "gestureend",
  e => e.preventDefault()
);


/* =========================================================
   STARTUP
========================================================= */

updateStats();
updateJourney();
updateMusicButtons();

if(state.name) {

  document.getElementById("playerName")
    .value =
    state.name;

}

</script>

</body>
</html>

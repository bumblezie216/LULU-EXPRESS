<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#170b13">

<title>Lulu Express 🚂💗</title>

<style>

* {
  box-sizing: border-box;
  -webkit-tap-highlight-color: transparent;
}

:root {
  --bg:#12080e;
  --panel:#26121e;
  --panel2:#35182a;
  --pink:#f39ac4;
  --pink2:#c9578d;
  --light:#ffe5f0;
  --gold:#f3ce6b;
  --green:#8fe0ac;
  --red:#ff718c;
  --muted:#d7b8c8;
}

body {
  margin:0;
  min-height:100vh;
  color:white;
  font-family:Arial,Helvetica,sans-serif;
  background:
    radial-gradient(
      circle at 50% -10%,
      #733653 0%,
      #321624 38%,
      #12080e 78%
    );
}

button,
input,
textarea {
  font:inherit;
}

button {
  cursor:pointer;
  touch-action:manipulation;
}

#app {
  width:100%;
  max-width:760px;
  margin:auto;
  padding:14px;
}

.topbar {
  display:flex;
  justify-content:space-between;
  align-items:center;
  margin-bottom:14px;
}

.logo {
  font-weight:900;
  font-size:20px;
}

.logo span {
  color:var(--pink);
}

.music-btn {
  border:1px solid #ffffff22;
  background:#ffffff10;
  color:white;
  border-radius:12px;
  padding:9px 12px;
}

.panel {
  background:
    linear-gradient(
      145deg,
      #321827,
      #1d0d16
    );
  border:1px solid #ffffff18;
  border-radius:24px;
  padding:20px;
  box-shadow:0 18px 50px #0009;
}

.center {
  text-align:center;
}

.badge {
  display:inline-block;
  padding:6px 11px;
  border-radius:999px;
  background:#f39ac418;
  border:1px solid #f39ac444;
  color:var(--light);
  font-size:11px;
  font-weight:bold;
  letter-spacing:1px;
  text-transform:uppercase;
}

h1 {
  font-size:42px;
  line-height:1;
  margin:12px 0;
}

h2 {
  font-size:28px;
  margin:9px 0;
}

h3 {
  line-height:1.4;
}

p {
  color:var(--muted);
  line-height:1.55;
}

.btn {
  width:100%;
  border:0;
  border-radius:15px;
  padding:14px;
  margin-top:9px;
  font-weight:900;
  color:#32101f;
  background:
    linear-gradient(
      135deg,
      #f8acd0,
      #bd4f87
    );
}

.btn.gold {
  background:
    linear-gradient(
      135deg,
      #ffe9a4,
      #d8ad3f
    );
}

.btn.red {
  background:
    linear-gradient(
      135deg,
      #ff9cad,
      #d34f70
    );
}

.btn.dark {
  color:white;
  background:#ffffff0c;
  border:1px solid #ffffff20;
}

input,
textarea {
  width:100%;
  background:#ffffff0b;
  color:white;
  border:1px solid #ffffff20;
  border-radius:14px;
  padding:14px;
  outline:none;
}

textarea {
  min-height:140px;
  resize:vertical;
}

.stats {
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:8px;
  margin:15px 0;
}

.stat {
  padding:10px;
  border-radius:14px;
  background:#ffffff08;
  border:1px solid #ffffff10;
}

.stat strong {
  display:block;
  font-size:20px;
  color:var(--light);
}

.stat small {
  color:var(--muted);
}

.notice {
  padding:12px;
  border-radius:14px;
  background:#f39ac410;
  border:1px solid #f39ac426;
  margin:12px 0;
  color:var(--muted);
}

.round-list {
  display:grid;
  gap:7px;
  margin-top:15px;
}

.round {
  display:flex;
  align-items:center;
  gap:10px;
  padding:10px;
  border-radius:13px;
  background:#ffffff07;
  border:1px solid #ffffff0d;
}

.round.current {
  border-color:#f39ac466;
  background:#f39ac410;
}

.round.locked {
  opacity:.35;
}

.round-number {
  width:32px;
  height:32px;
  flex-shrink:0;
  display:grid;
  place-items:center;
  border-radius:50%;
  background:#ffffff10;
  font-weight:900;
}

.round.current .round-number {
  background:var(--pink);
  color:#32101f;
}

.choices {
  display:grid;
  gap:9px;
}

.choice {
  width:100%;
  padding:14px;
  border-radius:15px;
  border:1px solid #ffffff18;
  background:#ffffff09;
  color:white;
  text-align:left;
}

.choice:hover {
  background:#f39ac418;
}

.choice:disabled {
  opacity:.8;
  cursor:default;
}

.correct {
  background:#8fe0ac25!important;
  border-color:#8fe0ac88!important;
}

.wrong {
  background:#ff718c25!important;
  border-color:#ff718c88!important;
}

.big-number {
  font-size:48px;
  font-weight:1000;
  color:var(--gold);
}

.timer {
  font-size:35px;
  font-weight:1000;
  color:var(--gold);
  text-align:center;
}

.arena {
  position:relative;
  height:340px;
  overflow:hidden;
  border-radius:20px;
  background:
    radial-gradient(
      circle,
      #63284b,
      #160a12
    );
  border:1px solid #ffffff15;
}

.target {
  position:absolute;
  width:58px;
  height:58px;
  border:0;
  border-radius:50%;
  display:grid;
  place-items:center;
  font-size:28px;
  background:var(--pink);
  box-shadow:0 5px 25px #f39ac455;
}

.target.bad {
  background:#4b4b4b;
}

.memory-grid {
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:8px;
  margin:18px 0;
}

.memory-tile {
  aspect-ratio:1;
  border-radius:13px;
  border:1px solid #ffffff15;
  background:#ffffff0a;
  display:grid;
  place-items:center;
  font-size:24px;
  color:white;
}

.memory-tile.active {
  background:var(--pink);
  color:#32101f;
}

.card-row {
  display:flex;
  justify-content:center;
  gap:8px;
  flex-wrap:wrap;
  margin:18px 0;
}

.card {
  width:58px;
  height:78px;
  display:grid;
  place-items:center;
  background:white;
  color:#27101d;
  border-radius:9px;
  font-weight:900;
  font-size:20px;
}

.maze {
  display:grid;
  grid-template-columns:repeat(5,1fr);
  gap:5px;
  max-width:330px;
  margin:18px auto;
}

.maze-cell {
  aspect-ratio:1;
  display:grid;
  place-items:center;
  border-radius:7px;
  background:#ffffff09;
  font-size:24px;
}

.maze-cell.wall {
  background:#080508;
  border:1px solid #ffffff08;
}

.maze-cell.player {
  background:var(--pink);
  color:#32101f;
  box-shadow:0 0 18px #f39ac455;
}

.maze-cell.goal {
  background:#f3ce6b33;
  border:1px solid var(--gold);
  box-shadow:0 0 18px #f3ce6b33;
}

.grid {
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:8px;
}

.progress {
  height:8px;
  border-radius:999px;
  overflow:hidden;
  background:#ffffff10;
  margin:14px 0;
}

.progress-bar {
  height:100%;
  background:
    linear-gradient(
      90deg,
      var(--pink),
      var(--gold)
    );
  transition:width .25s;
}

.final-box {
  border:2px solid var(--gold);
  background:
    radial-gradient(
      circle at top,
      #68294d,
      #25111c
    );
}

.trophy {
  font-size:65px;
}

.result-icon {
  font-size:70px;
  margin:18px 0;
}

.result-points {
  font-size:32px;
  font-weight:1000;
  color:var(--gold);
}

.hidden {
  display:none!important;
}

/* =========================================================
   DERBY
   ========================================================= */

.derby-track {
  position:relative;
  margin:20px 0;
  padding:10px;
  border-radius:20px;
  background:#160a12;
  border:1px solid #ffffff15;
  overflow:hidden;
}

.race-lane {
  position:relative;
  height:88px;
  margin-bottom:8px;
  border-radius:15px;
  background:
    repeating-linear-gradient(
      90deg,
      #301522 0px,
      #301522 28px,
      #27111d 28px,
      #27111d 56px
    );
  overflow:hidden;
}

.race-lane:last-child {
  margin-bottom:0;
}

.lane-name {
  position:absolute;
  left:10px;
  top:7px;
  z-index:5;
  font-size:11px;
  font-weight:900;
  color:#ffe5f0;
  background:#12080ecc;
  padding:4px 7px;
  border-radius:7px;
}

.finish-line {
  position:absolute;
  right:6px;
  top:0;
  height:100%;
  width:16px;
  background:
    repeating-conic-gradient(
      #fff 0 25%,
      #111 0 50%
    ) 0/10px 10px;
  z-index:4;
}

.racer {
  position:absolute;
  left:0;
  top:35px;
  width:50px;
  height:40px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:31px;
  transition:left 1.05s ease;
  z-index:6;
}

.racer-name {
  position:absolute;
  left:10px;
  bottom:6px;
  font-size:9px;
  color:#d7b8c8;
  font-weight:900;
}

.derby-question {
  margin-top:20px;
  padding:18px;
  border-radius:18px;
  background:#ffffff06;
  border:1px solid #ffffff12;
}

.derby-answer {
  text-align:center;
}

.derby-distance {
  display:grid;
  grid-template-columns:repeat(24,1fr);
  gap:3px;
  margin:12px 0;
}

.derby-distance span {
  height:8px;
  border-radius:3px;
  background:#ffffff10;
}

.derby-distance span.you {
  background:var(--pink);
}

.derby-distance span.bot {
  background:var(--gold);
}

.derby-distance span.you.bot {
  background:
    linear-gradient(
      90deg,
      var(--pink) 50%,
      var(--gold) 50%
    );
}

.derby-status {
  text-align:center;
  padding:11px;
  border-radius:12px;
  background:#ffffff08;
  color:var(--light);
  margin:12px 0;
}

.derby-countdown {
  font-size:52px;
  font-weight:1000;
  color:var(--gold);
  text-align:center;
  min-height:65px;
  animation:derbyPulse .8s infinite alternate;
}

@keyframes derbyPulse {
  from {
    transform:scale(1);
  }
  to {
    transform:scale(1.08);
  }
}

.derby-result {
  text-align:center;
}

.mode-grid,
.animal-grid {
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:10px;
  margin:15px 0;
}

.mode-card,
.animal-card {
  border:1px solid #ffffff18;
  border-radius:16px;
  padding:15px;
  background:#ffffff08;
  color:white;
  text-align:center;
}

.mode-card.selected,
.animal-card.selected {
  border-color:var(--pink);
  background:#f39ac425;
  box-shadow:0 0 20px #f39ac420;
}

.animal-icon {
  font-size:38px;
  display:block;
  margin-bottom:7px;
}

.typing-answer {
  text-align:center;
  font-size:20px;
  font-weight:bold;
}

.race-mode-description {
  min-height:48px;
}

@media(max-width:430px) {

  h1 {
    font-size:34px;
  }

  .panel {
    padding:15px;
  }

  .stats {
    gap:5px;
  }

  .stat {
    padding:8px 5px;
  }

  .stat strong {
    font-size:17px;
  }

  .mode-grid,
  .animal-grid {
    grid-template-columns:1fr 1fr;
  }

}

</style>
</head>

<body>

<div id="app"></div>

<script>

"use strict";

/* =========================================================
   LULU EXPRESS
   21 EVENTS
   SECRET SKIP CODE: 3333
   ========================================================= */

const EVENTS = [

  "❤️ The Heart Rate",
  "🧠 The Memory Vault",
  "⚡ The Pressure Quiz",
  "🎰 The High Roller",
  "🧠 The Mind Games",
  "🃏 The Bluff",
  "⚡ The Survival Round",
  "🏎️ The Admirer Race",
  "💔 The Heartbreak Chamber",
  "🥊 The Heartbreak Boxing Match",
  "🧩 The Perfect Match",
  "🕵️ Who Knows Liliana Best?",
  "💨 The Reaction Gauntlet",
  "🗺️ The Heart Hunt",
  "🔐 The Love Lock",
  "🎯 The Cupid Shootout",
  "🧨 The Countdown",
  "🎰 The Ultimate Gamble",
  "💀 The Admirer's Last Stand",
  "🏇 THE LULU DERBY",
  "👑 THE FINAL CHALLENGE"

];

let state = {

  playerName:"",
  currentEvent:0,
  score:0,
  musicOn:true,
  finished:false

};

let eventStartScore = 0;

/* =========================================================
   SAVE / LOAD
   ========================================================= */

function saveGame() {

  localStorage.setItem(
    "luluExpress",
    JSON.stringify(state)
  );

}

function loadGame() {

  try {

    const saved =
      JSON.parse(
        localStorage.getItem(
          "luluExpress"
        )
      );

    if(saved) {

      state = {
        ...state,
        ...saved
      };

    }

  } catch(error) {

    console.log(
      "Could not load game."
    );

  }

}

/* =========================================================
   MUSIC
   ========================================================= */

let audioContext = null;
let musicTimer = null;

function startMusic() {

  if(!state.musicOn)
    return;

  try {

    if(!audioContext) {

      audioContext =
        new (
          window.AudioContext ||
          window.webkitAudioContext
        )();

    }

    if(audioContext.state === "suspended") {

      audioContext.resume();

    }

    if(musicTimer)
      return;

    const notes =
      [
        261.63,
        329.63,
        392.00,
        329.63,
        293.66,
        349.23,
        440.00,
        349.23
      ];

    let index = 0;

    musicTimer =
      setInterval(
        () => {

          if(
            !audioContext ||
            !state.musicOn
          )
            return;

          const osc =
            audioContext.createOscillator();

          const gain =
            audioContext.createGain();

          osc.frequency.value =
            notes[index %
              notes.length];

          osc.type =
            "sine";

          gain.gain.setValueAtTime(
            0.0001,
            audioContext.currentTime
          );

          gain.gain.exponentialRampToValueAtTime(
            0.025,
            audioContext.currentTime + .03
          );

          gain.gain.exponentialRampToValueAtTime(
            0.0001,
            audioContext.currentTime + .45
          );

          osc.connect(gain);
          gain.connect(
            audioContext.destination
          );

          osc.start();
          osc.stop(
            audioContext.currentTime + .5
          );

          index++;

        },
        550
      );

  } catch(error) {}

}

function toggleMusic() {

  state.musicOn =
    !state.musicOn;

  if(!state.musicOn) {

    if(musicTimer) {

      clearInterval(
        musicTimer
      );

      musicTimer = null;

    }

  } else {

    startMusic();

  }

  saveGame();
  render();

}

/* =========================================================
   HELPERS
   ========================================================= */

function escapeHTML(value) {

  return String(value)
    .replaceAll("&","&amp;")
    .replaceAll("<","&lt;")
    .replaceAll(">","&gt;")
    .replaceAll('"',"&quot;")
    .replaceAll("'","&#039;");

}

function topBar() {

  return `

    <div class="topbar">

      <div class="logo">
        Lulu <span>Express</span> 🚂💗
      </div>

      <button
        class="music-btn"
        onclick="toggleMusic()"
      >
        ${state.musicOn ? "🔊" : "🔇"}
      </button>

    </div>

  `;

}

function addPoints(points) {

  state.score +=
    Number(points) || 0;

  if(state.score < 0)
    state.score = 0;

  saveGame();

}

function finishEvent(
  points,
  success,
  resultTitle,
  resultMessage
) {

  const earned =
    Number(points) || 0;

  addPoints(
    earned
  );

  showEventResult(
    success,
    resultTitle,
    resultMessage,
    earned
  );

}

function showEventResult(
  success,
  title,
  message,
  earned
) {

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="result-icon">
        ${success ? "💗" : "💔"}
      </div>

      <div class="badge">
        ${success ? "Challenge Complete" : "Challenge Failed"}
      </div>

      <h2>
        ${title}
      </h2>

      <p>
        ${message}
      </p>

      <div class="result-points">
        ${earned >= 0 ? "+" : ""}${earned}
      </div>

      <p>
        Heart Points
      </p>

      <div class="stats">

        <div class="stat">
          <strong>${state.score}</strong>
          <small>Total</small>
        </div>

        <div class="stat">
          <strong>${state.currentEvent + 1}</strong>
          <small>Event</small>
        </div>

        <div class="stat">
          <strong>${21 - state.currentEvent}</strong>
          <small>Remaining</small>
        </div>

      </div>

      <button
        class="btn gold"
        onclick="continueToNextEvent()"
      >
        Continue 🚂💗
      </button>

    </div>

  `;

}

function continueToNextEvent() {

  if(state.currentEvent < 20) {

    state.currentEvent++;

    saveGame();

    render();

  } else {

    state.currentEvent = 20;

    saveGame();

    render();

  }

}

/* =========================================================
   HOME
   ========================================================= */

function home() {

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Welcome aboard
      </div>

      <h1>
        Lulu Express 🚂💗
      </h1>

      <p>
        Twenty-one challenges.
        One final destination.
        One very special prize.
      </p>

      ${
        state.playerName
          ? `
            <div class="notice">
              Welcome back,
              <strong>
                ${escapeHTML(state.playerName)}
              </strong> 💗
            </div>

            <button
              class="btn gold"
              onclick="boardTrain()"
            >
              🚂 Continue Journey
            </button>
          `
          : `
            <input
              id="playerName"
              placeholder="Enter your name"
              maxlength="30"
            >

            <button
              class="btn gold"
              onclick="boardTrain()"
            >
              🚂 Board Lulu Express
            </button>
          `
      }

      <div class="stats">

        <div class="stat">
          <strong>${state.score}</strong>
          <small>Heart Points</small>
        </div>

        <div class="stat">
          <strong>${state.currentEvent + 1}</strong>
          <small>Current Event</small>
        </div>

        <div class="stat">
          <strong>21</strong>
          <small>Total Events</small>
        </div>

      </div>

    </div>

    <div class="panel" style="margin-top:14px">

      <h3>
        🚂 Your Journey
      </h3>

      <div class="round-list">

        ${EVENTS.map(
          (event,index) => `

            <div
              class="
                round
                ${
                  index === state.currentEvent
                    ? "current"
                    : ""
                }
                ${
                  index > state.currentEvent
                    ? "locked"
                    : ""
                }
              "
            >

              <div class="round-number">
                ${index + 1}
              </div>

              <div>
                ${event}
              </div>

            </div>

          `
        ).join("")}

      </div>

    </div>

    <div class="panel" style="margin-top:14px">

      <h3>
        🔐 Secret Access
      </h3>

      <p>
        Already know the secret code?
      </p>

      <button
        class="btn dark"
        onclick="accessCode()"
      >
        Enter Access Code
      </button>

      <button
        class="btn red"
        onclick="resetJourney()"
      >
        🔄 Reset Journey
      </button>

    </div>

  `;

}

function boardTrain() {

  const input =
    document.getElementById(
      "playerName"
    );

  if(input) {

    const name =
      input.value.trim();

    if(!name) {

      alert(
        "Please enter your name first. ❤️"
      );

      return;

    }

    state.playerName =
      name;

  }

  startMusic();

  saveGame();

  render();

}

/* =========================================================
   SECRET ACCESS
   ========================================================= */

function accessCode() {

  const code =
    prompt(
      "Enter the secret access code:"
    );

  if(code === "3333") {

    state.currentEvent = 20;

    saveGame();

    render();

  } else if(code !== null) {

    alert(
      "That code isn't correct. ❤️"
    );

  }

}

/* =========================================================
   RENDER
   ========================================================= */

function render() {

  eventStartScore =
    state.score;

  if(state.finished) {

    finalResult();

    return;

  }

  if(!state.playerName) {

    home();

    return;

  }

  switch(state.currentEvent) {

    case 0:
      event1();
      break;

    case 1:
      event2();
      break;

    case 2:
      event3();
      break;

    case 3:
      event4();
      break;

    case 4:
      event5();
      break;

    case 5:
      event6();
      break;

    case 6:
      event7();
      break;

    case 7:
      event8();
      break;

    case 8:
      event9();
      break;

    case 9:
      event10();
      break;

    case 10:
      event11();
      break;

    case 11:
      event12();
      break;

    case 12:
      event13();
      break;

    case 13:
      event14();
      break;

    case 14:
      event15();
      break;

    case 15:
      event16();
      break;

    case 16:
      event17();
      break;

    case 17:
      event18();
      break;

    case 18:
      event19();
      break;

    case 19:
      event20();
      break;

    case 20:
      event21();
      break;

  }

}

/* =========================================================
   EVENT 1
   HEART RATE
   ========================================================= */

function event1() {

  let time = 20;
  let hits = 0;
  let misses = 0;
  let active = true;

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 1 of 21
      </div>

      <h2>
        ❤️ The Heart Rate
      </h2>

      <div class="timer" id="heartTimer">
        20
      </div>

      <div class="stats">

        <div class="stat">
          <strong id="heartHits">0</strong>
          <small>Hearts</small>
        </div>

        <div class="stat">
          <strong id="heartMisses">0</strong>
          <small>Misses</small>
        </div>

        <div class="stat">
          <strong>20s</strong>
          <small>Time</small>
        </div>

      </div>

      <div
        id="heartArena"
        class="arena"
      ></div>

    </div>

  `;

  const timer =
    setInterval(
      () => {

        time--;

        const timerEl =
          document.getElementById(
            "heartTimer"
          );

        if(timerEl)
          timerEl.textContent =
            time;

        if(time <= 0) {

          clearInterval(timer);

          active = false;

          finishEvent(
            hits * 5,
            hits > misses,
            "❤️ HEART RATE COMPLETE",
            `You caught ${hits} hearts and missed ${misses}.`
          );

        }

      },
      1000
    );

  function spawn() {

    if(!active)
      return;

    const arena =
      document.getElementById(
        "heartArena"
      );

    if(!arena)
      return;

    arena.innerHTML = "";

    const good =
      Math.random() > .25;

    const button =
      document.createElement(
        "button"
      );

    button.className =
      "target" +
      (good ? "" : " bad");

    button.textContent =
      good ? "❤️" : "💔";

    button.style.left =
      Math.random() * 82 + "%";

    button.style.top =
      Math.random() * 75 + "%";

    button.onclick =
      () => {

        if(good) {

          hits++;

          addPoints(5);

        } else {

          misses++;

          addPoints(-2);

        }

        document.getElementById(
          "heartHits"
        ).textContent =
          hits;

        document.getElementById(
          "heartMisses"
        ).textContent =
          misses;

        spawn();

      };

    arena.appendChild(
      button
    );

  }

  spawn();

}

/* =========================================================
   EVENT 2
   MEMORY VAULT
   ========================================================= */

function event2() {

  let level = 3;
  let sequence = [];
  let inputIndex = 0;
  let accepting = false;

  const symbols =
    [
      "❤️",
      "🌹",
      "⭐",
      "🐬",
      "💗",
      "🌙",
      "🦋",
      "💎"
    ];

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 2 of 21
      </div>

      <h2>
        🧠 The Memory Vault
      </h2>

      <p id="memoryStatus">
        Watch carefully...
      </p>

      <div
        id="memoryGrid"
        class="memory-grid"
      ></div>

    </div>

  `;

  function begin() {

    sequence = [];

    for(let i=0;i<level;i++) {

      sequence.push(
        Math.floor(
          Math.random() *
          16
        )
      );

    }

    inputIndex = 0;
    accepting = false;

    showSequence();

  }

  function showSequence() {

    const grid =
      document.getElementById(
        "memoryGrid"
      );

    grid.innerHTML =
      Array.from(
        {length:16},
        (_,i) => `
          <button
            class="memory-tile"
            data-index="${i}"
          >
            ${symbols[i % symbols.length]}
          </button>
        `
      ).join("");

    let i = 0;

    const interval =
      setInterval(
        () => {

          if(i >= sequence.length) {

            clearInterval(interval);

            accepting = true;

            document.getElementById(
              "memoryStatus"
            ).textContent =
              "Now repeat the sequence.";

            return;

          }

          const tile =
            grid.querySelector(
              `[data-index="${sequence[i]}"]`
            );

          if(tile) {

            tile.classList.add(
              "active"
            );

            setTimeout(
              () => {
                tile.classList.remove(
                  "active"
                );
              },
              350
            );

          }

          i++;

        },
        550
      );

  }

  document.getElementById(
    "memoryGrid"
  ).addEventListener(
    "click",
    event => {

      const tile =
        event.target.closest(
          ".memory-tile"
        );

      if(!tile || !accepting)
        return;

      const selected =
        Number(
          tile.dataset.index
        );

      if(
        selected !==
        sequence[inputIndex]
      ) {

        finishEvent(
          10,
          false,
          "💔 MEMORY VAULT FAILED",
          "The sequence escaped your memory."
        );

        return;

      }

      tile.classList.add(
        "active"
      );

      addPoints(
        level * 10
      );

      inputIndex++;

      if(
        inputIndex >=
        sequence.length
      ) {

        if(level >= 6) {

          finishEvent(
            60,
            true,
            "🧠 MEMORY VAULT MASTERED",
            "You conquered the final memory sequence."
          );

        } else {

          level++;

          accepting = false;

          document.getElementById(
            "memoryStatus"
          ).textContent =
            `Level ${level}. Get ready...`;

          setTimeout(
            begin,
            900
          );

        }

      }

    }
  );

  begin();

}

/* =========================================================
   QUESTION BANK
   1000+ GENERATED QUESTIONS
   ========================================================= */

function createQuestionBank() {

  const bank = [];

  const facts = [

    ["What is the capital of France?","Paris"],
    ["What is the capital of England?","London"],
    ["What is the capital of New Zealand?","Wellington"],
    ["What is the capital of Australia?","Canberra"],
    ["What is the capital of Japan?","Tokyo"],
    ["What is the capital of Italy?","Rome"],
    ["What is the capital of Spain?","Madrid"],
    ["What is the capital of Canada?","Ottawa"],
    ["What is the capital of the United States?","Washington"],
    ["Which planet do we live on?","Earth"],
    ["Which planet is closest to the Sun?","Mercury"],
    ["Which planet is known as the Red Planet?","Mars"],
    ["What star is at the centre of our solar system?","The Sun"],
    ["How many days are in a week?","7"],
    ["How many months are in a year?","12"],
    ["How many hours are in one day?","24"],
    ["How many minutes are in one hour?","60"],
    ["How many seconds are in one minute?","60"],
    ["How many sides does a square have?","4"],
    ["How many sides does a triangle have?","3"],
    ["How many letters are in the English alphabet?","26"],
    ["Which ocean is the largest?","Pacific Ocean"],
    ["Which animal is known as man's best friend?","Dog"],
    ["What is the largest land animal?","Elephant"],
    ["What shape has three sides?","Triangle"],
    ["What colour is made by mixing red and blue?","Purple"],
    ["What colour is the sky commonly shown as on a clear day?","Blue"],
    ["How many legs does a spider have?","8"],
    ["How many legs does a dog have?","4"],
    ["Which direction is opposite north?","South"]

  ];

  facts.forEach(
    fact => {

      const wrongPools = [

        ["10","12","15"],
        ["London","Rome","Madrid"],
        ["Mars","Venus","Jupiter"],
        ["5","6","8"],
        ["10","11","13"],
        ["12","36","48"],
        ["30","90","100"],
        ["2","5","6"],
        ["Atlantic Ocean","Indian Ocean","Arctic Ocean"],
        ["Cat","Horse","Dolphin"],
        ["Giraffe","Hippo","Rhino"],
        ["Square","Circle","Rectangle"],
        ["Green","Orange","Yellow"],
        ["6","10","12"],
        ["Green","Orange","Pink"],
        ["North","East","West"]
      ];

      for(
        let copy = 0;
        copy < 8;
        copy++
      ) {

        const pool =
          wrongPools[
            copy %
            wrongPools.length
          ];

        const answers =
          [
            fact[1],
            ...pool.filter(
              x => x !== fact[1]
            ).slice(0,3)
          ];

        bank.push(
          makeQuestion(
            fact[0],
            fact[1],
            answers
          )
        );

      }

    }
  );

  /* multiplication 1 x 1 through 12 x 12 */

  for(let a=1;a<=12;a++) {

    for(let b=1;b<=12;b++) {

      const answer =
        String(a*b);

      const wrong = [];

      const candidates = [
        a*b + 1,
        a*b - 1,
        a*b + 2,
        a*b - 2,
        a*b + 10,
        a*b - 10
      ];

      candidates.forEach(
        n => {

          if(
            n > 0 &&
            String(n) !== answer &&
            !wrong.includes(String(n))
          ) {

            wrong.push(
              String(n)
            );

          }

        }
      );

      bank.push(
        makeQuestion(
          `What is ${a} × ${b}?`,
          answer,
          wrong.slice(0,3)
        )
      );

    }

  }

  /* addition */

  for(let a=1;a<=50;a++) {

    for(let b=1;b<=50;b++) {

      const answer =
        String(a+b);

      const wrong = [
        String(a+b+1),
        String(a+b-1),
        String(a+b+5)
      ];

      bank.push(
        makeQuestion(
          `What is ${a} + ${b}?`,
          answer,
          wrong
        )
      );

    }

  }

  /* subtraction */

  for(let a=20;a<=100;a++) {

    for(let b=1;b<=20;b++) {

      if(a <= b)
        continue;

      const answer =
        String(a-b);

      bank.push(
        makeQuestion(
          `What is ${a} − ${b}?`,
          answer,
          [
            String(a-b+1),
            String(a-b-1),
            String(a-b+5)
          ]
        )
      );

    }

  }

  /* extra generated fact variations */

  const templates = [

    ["How many hours are in ${n} days?","hours"],
    ["How many minutes are in ${n} hours?","minutes"],
    ["How many seconds are in ${n} minutes?","seconds"]

  ];

  for(
    let n=1;
    n<=100;
    n++
  ) {

    bank.push(
      makeQuestion(
        `How many hours are in ${n} days?`,
        String(n*24),
        [
          String(n*12),
          String(n*20),
          String(n*30)
        ]
      )
    );

    bank.push(
      makeQuestion(
        `How many minutes are in ${n} hours?`,
        String(n*60),
        [
          String(n*30),
          String(n*50),
          String(n*100)
        ]
      )
    );

    bank.push(
      makeQuestion(
        `How many seconds are in ${n} minutes?`,
        String(n*60),
        [
          String(n*30),
          String(n*120),
          String(n*100)
        ]
      )
    );

  }

  return bank;

}

function makeQuestion(
  q,
  correct,
  wrongAnswers
) {

  const answers =
    [
      String(correct),
      ...wrongAnswers.map(
        String
      )
    ];

  const shuffled =
    shuffle(
      answers
    );

  return {

    q,
    a:shuffled,
    correct:
      shuffled.indexOf(
        String(correct)
      )

  };

}

function shuffle(array) {

  const copy =
    [...array];

  for(
    let i =
      copy.length - 1;
    i > 0;
    i--
  ) {

    const j =
      Math.floor(
        Math.random() *
        (i + 1)
      );

    [
      copy[i],
      copy[j]
    ] =
    [
      copy[j],
      copy[i]
    ];

  }

  return copy;

}

const QUESTION_BANK =
  createQuestionBank();

/* =========================================================
   EVENT 3
   PRESSURE QUIZ
   ========================================================= */

function event3() {

  const questions =
    randomQuestions(
      QUESTION_BANK,
      12
    );

  let index = 0;
  let points = 0;
  let locked = false;

  function show() {

    if(index >= questions.length) {

      finishEvent(
        points,
        points >= 90,
        "⚡ PRESSURE QUIZ COMPLETE",
        `You earned ${points} points during the pressure round.`
      );

      return;

    }

    locked = false;

    const question =
      questions[index];

    document.getElementById(
      "app"
    ).innerHTML = `

      ${topBar()}

      <div class="panel">

        <div class="badge">
          Event 3 of 21
        </div>

        <h2>
          ⚡ The Pressure Quiz
        </h2>

        <div class="progress">

          <div
            class="progress-bar"
            style="
              width:${
                index /
                questions.length *
                100
              }%
            "
          ></div>

        </div>

        <p>
          Question ${index + 1}
          of ${questions.length}
        </p>

        <h3>
          ${escapeHTML(question.q)}
        </h3>

        <div class="choices">

          ${question.a.map(
            (
              answer,
              i
            ) => `

              <button
                class="choice"
                onclick="pressureAnswer(${i})"
              >
                ${escapeHTML(answer)}
              </button>

            `
          ).join("")}

        </div>

        <div class="notice center">
          💗 ${points} points earned
        </div>

      </div>

    `;

  }

  window.pressureAnswer =
    function(answer) {

      if(locked)
        return;

      locked = true;

      const question =
        questions[index];

      const buttons =
        document.querySelectorAll(
          ".choice"
        );

      buttons.forEach(
        button => {
          button.disabled =
            true;
        }
      );

      if(
        answer ===
        question.correct
      ) {

        buttons[answer]
          .classList.add(
            "correct"
          );

        points += 15;

        addPoints(15);

      } else {

        buttons[answer]
          .classList.add(
            "wrong"
          );

        buttons[
          question.correct
        ].classList.add(
          "correct"
        );

      }

      index++;

      setTimeout(
        show,
        450
      );

    };

  show();

}

/* =========================================================
   RANDOM QUESTION HELPER
   ========================================================= */

function randomQuestions(
  source,
  amount
) {

  return shuffle(
    source
  ).slice(
    0,
    amount
  );

}

/* =========================================================
   EVENT 4
   HIGH ROLLER
   ========================================================= */

function event4() {

  let tokens = 100;
  let turns = 0;

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 4 of 21
      </div>

      <h2>
        🎰 The High Roller
      </h2>

      <div
        id="tokens"
        class="big-number"
      >
        ${tokens}
      </div>

      <p>
        Choose your bet.
      </p>

      <button
        class="btn"
        onclick="highRoller(10)"
      >
        Bet 10
      </button>

      <button
        class="btn gold"
        onclick="highRoller(25)"
      >
        Bet 25
      </button>

      <button
        class="btn red"
        onclick="highRoller(50)"
      >
        Bet 50
      </button>

      <div
        id="rollerMessage"
        class="notice"
      >
        You have five turns.
      </div>

    </div>

  `;

  window.highRoller =
    function(bet) {

      if(turns >= 5)
        return;

      if(tokens < bet) {

        alert(
          "You don't have enough tokens."
        );

        return;

      }

      turns++;

      const win =
        Math.random() > .42;

      if(win) {

        tokens += bet;

        addPoints(
          bet
        );

      } else {

        tokens -= bet;

        addPoints(
          Math.floor(
            bet / 2
          ) * -1
        );

      }

      document.getElementById(
        "tokens"
      ).textContent =
        tokens;

      document.getElementById(
        "rollerMessage"
      ).textContent =
        win
          ? "💗 WIN! The house blinked first."
          : "💔 LOSS! The house takes the bet.";

      if(turns >= 5) {

        setTimeout(
          () => {

            finishEvent(
              Math.max(
                0,
                Math.floor(
                  tokens / 2
                )
              ),
              tokens >= 75,
              "🎰 HIGH ROLLER COMPLETE",
              `You finished with ${tokens} tokens.`
            );

          },
          600
        );

      }

    };

}

/* =========================================================
   EVENT 5
   MIND GAMES
   ========================================================= */

function event5() {

  const questions = [

    [
      "Which comes next? 2, 4, 6, 8...",
      ["10","11","12","14"],
      0
    ],

    [
      "Which word does not belong?",
      ["Apple","Banana","Carrot","Orange"],
      2
    ],

    [
      "What is 5 × 5?",
      ["20","25","30","35"],
      1
    ],

    [
      "Which is heavier?",
      ["1 kg feathers","1 kg steel","Impossible to tell","Steel by a little"],
      1
    ],

    [
      "How many corners does a rectangle have?",
      ["2","3","4","5"],
      2
    ],

    [
      "Which number comes after 99?",
      ["100","101","90","110"],
      0
    ]

  ];

  let index = 0;
  let score = 0;

  function show() {

    if(index >= questions.length) {

      finishEvent(
        score + 30,
        score >= 45,
        "🧠 MIND GAMES COMPLETE",
        "You made it through the mental maze."
      );

      return;

    }

    const q =
      questions[index];

    document.getElementById(
      "app"
    ).innerHTML = `

      ${topBar()}

      <div class="panel">

        <div class="badge">
          Event 5 of 21
        </div>

        <h2>
          🧠 The Mind Games
        </h2>

        <p>
          ${q[0]}
        </p>

        <div class="choices">

          ${q[1].map(
            (
              answer,
              i
            ) => `

              <button
                class="choice"
                onclick="mindAnswer(${i})"
              >
                ${answer}
              </button>

            `
          ).join("")}

        </div>

      </div>

    `;

  }

  window.mindAnswer =
    function(answer) {

      const q =
        questions[index];

      if(
        answer === q[2]
      ) {

        score += 15;

        addPoints(15);

      } else {

        score += 3;

        addPoints(3);

      }

      index++;

      show();

    };

  show();

}

/* =========================================================
   EVENT 6
   BLUFF
   ========================================================= */

function event6() {

  let chips = 100;
  let turn = 0;

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 6 of 21
      </div>

      <h2>
        🃏 The Bluff
      </h2>

      <div class="card-row">

        <div class="card">A♥</div>
        <div class="card">K♦</div>
        <div class="card">Q♣</div>

      </div>

      <div
        class="big-number"
        id="chips"
      >
        ${chips}
      </div>

      <p>
        Three rounds. Trust your instincts.
      </p>

      <button
        class="btn"
        onclick="bluffMove(10)"
      >
        Small Bluff — 10
      </button>

      <button
        class="btn gold"
        onclick="bluffMove(25)"
      >
        Big Bluff — 25
      </button>

      <button
        class="btn red"
        onclick="bluffMove(40)"
      >
        Fearless Bluff — 40
      </button>

      <div
        id="bluffMessage"
        class="notice"
      >
        Make your move.
      </div>

    </div>

  `;

  window.bluffMove =
    function(bet) {

      if(turn >= 3)
        return;

      if(chips < bet)
        return;

      turn++;

      const win =
        Math.random() >
        .45;

      if(win) {

        chips += bet;

        addPoints(
          15
        );

      } else {

        chips -= bet;

      }

      document.getElementById(
        "chips"
      ).textContent =
        chips;

      document.getElementById(
        "bluffMessage"
      ).textContent =
        win
          ? "🃏 Your bluff worked!"
          : "💔 They called your bluff!";

      if(turn >= 3) {

        setTimeout(
          () => {

            finishEvent(
              Math.floor(
                chips / 2
              ),
              chips >= 50,
              "🃏 BLUFF COMPLETE",
              `You finished with ${chips} chips.`
            );

          },
          600
        );

      }

    };

}

/* =========================================================
   EVENT 7
   SURVIVAL ROUND
   ========================================================= */

function event7() {

  let level = 3;
  let sequence = [];
  let input = 0;
  let accepting = false;

  const symbols =
    [
      "❤️",
      "🌹",
      "⭐",
      "🐬",
      "💎",
      "🌙"
    ];

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 7 of 21
      </div>

      <h2>
        ⚡ The Survival Round
      </h2>

      <p id="survivalStatus">
        Memorise the pattern.
      </p>

      <div
        id="survivalGrid"
        class="memory-grid"
      ></div>

    </div>

  `;

  function begin() {

    sequence = [];

    for(
      let i=0;
      i<level;
      i++
    ) {

      sequence.push(
        Math.floor(
          Math.random()*16
        )
      );

    }

    input = 0;
    accepting = false;

    showPattern();

  }

  function showPattern() {

    const grid =
      document.getElementById(
        "survivalGrid"
      );

    grid.innerHTML =
      Array.from(
        {length:16},
        (_,i) => `
          <button
            class="memory-tile"
            data-index="${i}"
          >
            ${symbols[i % symbols.length]}
          </button>
        `
      ).join("");

    let i = 0;

    const timer =
      setInterval(
        () => {

          if(
            i >=
            sequence.length
          ) {

            clearInterval(timer);

            accepting = true;

            document.getElementById(
              "survivalStatus"
            ).textContent =
              "Repeat it!";

            return;

          }

          const tile =
            grid.querySelector(
              `[data-index="${sequence[i]}"]`
            );

          tile.classList.add(
            "active"
          );

          setTimeout(
            () => {
              tile.classList.remove(
                "active"
              );
            },
            300
          );

          i++;

        },
        500
      );

  }

  document.getElementById(
    "survivalGrid"
  ).onclick =
    event => {

      const tile =
        event.target.closest(
          ".memory-tile"
        );

      if(
        !tile ||
        !accepting
      )
        return;

      if(
        Number(
          tile.dataset.index
        ) !==
        sequence[input]
      ) {

        finishEvent(
          15,
          false,
          "💔 SURVIVAL FAILED",
          "One wrong move ended the survival round."
        );

        return;

      }

      addPoints(10);

      input++;

      if(
        input >=
        sequence.length
      ) {

        if(level >= 5) {

          finishEvent(
            80,
            true,
            "⚡ SURVIVAL MASTER",
            "You survived the final pattern."
          );

        } else {

          level++;

          accepting = false;

          document.getElementById(
            "survivalStatus"
          ).textContent =
            `Level ${level} incoming...`;

          setTimeout(
            begin,
            800
          );

        }

      }

    };

  begin();

}

/* =========================================================
   EVENT 8
   ADMIRER RACE
   ========================================================= */

function event8() {

  let player = 0;
  let rival = 0;
  let lap = 0;

  function show() {

    if(lap >= 8) {

      finishEvent(
        player >= rival ? 70 : 20,
        player >= rival,
        player >= rival
          ? "🏎️ RACE WON"
          : "🏎️ RACE LOST",
        `You finished with ${player} laps against ${rival}.`
      );

      return;

    }

    const symbols =
      [
        "❤️",
        "🌹",
        "⭐",
        "🐬"
      ];

    const target =
      symbols[
        Math.floor(
          Math.random() *
          symbols.length
        )
      ];

    document.getElementById(
      "app"
    ).innerHTML = `

      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 8 of 21
        </div>

        <h2>
          🏎️ The Admirer Race
        </h2>

        <div class="stats">

          <div class="stat">
            <strong>${player}</strong>
            <small>You</small>
          </div>

          <div class="stat">
            <strong>${rival}</strong>
            <small>Rival</small>
          </div>

          <div class="stat">
            <strong>${lap+1}/8</strong>
            <small>Lap</small>
          </div>

        </div>

        <div class="big-number">
          ${target}
        </div>

        <p>
          Tap the matching symbol.
        </p>

        <div class="grid">

          ${symbols.map(
            symbol => `

              <button
                class="choice"
                onclick="raceChoice('${symbol}','${target}')"
              >
                ${symbol}
              </button>

            `
          ).join("")}

        </div>

      </div>

    `;

  }

  window.raceChoice =
    function(
      answer,
      correct
    ) {

      if(
        answer === correct
      ) {

        player++;

        addPoints(8);

      }

      if(
        Math.random() >
        .35
      ) {

        rival++;

      }

      lap++;

      show();

    };

  show();

}

/* =========================================================
   EVENT 9
   HEARTBREAK CHAMBER
   ========================================================= */

function event9() {

  let round = 0;
  let points = 0;

  const doors =
    [
      30,
      15,
      -10,
      50,
      5
    ];

  function show() {

    if(round >= 5) {

      finishEvent(
        Math.max(
          0,
          points
        ) + 30,
        points >= 40,
        "💔 HEARTBREAK CHAMBER COMPLETE",
        "You opened every door."
      );

      return;

    }

    document.getElementById(
      "app"
    ).innerHTML = `

      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 9 of 21
        </div>

        <h2>
          💔 The Heartbreak Chamber
        </h2>

        <p>
          Choose one of five doors.
        </p>

        <div class="grid">

          ${doors.map(
            (_,i) => `

              <button
                class="btn"
                onclick="heartDoor(${i})"
              >
                🚪 Door ${i+1}
              </button>

            `
          ).join("")}

        </div>

        <div class="notice">
          Door ${round+1} of 5
        </div>

      </div>

    `;

  }

  window.heartDoor =
    function(index) {

      const result =
        doors[index];

      points += result;

      addPoints(
        result
      );

      round++;

      alert(
        result >= 0
          ? `💗 You found ${result} points!`
          : `💔 You lost ${Math.abs(result)} points!`
      );

      show();

    };

  show();

}

/* =========================================================
   EVENT 10
   BOXING
   ========================================================= */

function event10() {

  let playerHP = 100;
  let enemyHP = 100;

  function show() {

    if(enemyHP <= 0) {

      finishEvent(
        100,
        true,
        "🥊 CHAMPION!",
        "You knocked out the Heartbreak opponent."
      );

      return;

    }

    if(playerHP <= 0) {

      finishEvent(
        20,
        false,
        "💔 KNOCKED OUT",
        "The opponent got the final hit."
      );

      return;

    }

    document.getElementById(
      "app"
    ).innerHTML = `

      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 10 of 21
        </div>

        <h2>
          🥊 The Heartbreak Boxing Match
        </h2>

        <div class="stats">

          <div class="stat">
            <strong>${playerHP}</strong>
            <small>Your HP</small>
          </div>

          <div class="stat">
            <strong>${enemyHP}</strong>
            <small>Enemy HP</small>
          </div>

          <div class="stat">
            <strong>${state.score}</strong>
            <small>Points</small>
          </div>

        </div>

        <button
          class="btn"
          onclick="boxingMove('punch')"
        >
          👊 Punch
        </button>

        <button
          class="btn gold"
          onclick="boxingMove('heavy')"
        >
          💥 Heavy Punch
        </button>

        <button
          class="btn dark"
          onclick="boxingMove('block')"
        >
          🛡️ Block
        </button>

      </div>

    `;

  }

  window.boxingMove =
    function(move) {

      let damage = 0;
      let defence = 0;

      if(move === "punch") {

        damage =
          Math.floor(
            Math.random()*12
          ) + 8;

      }

      if(move === "heavy") {

        damage =
          Math.floor(
            Math.random()*20
          ) + 10;

      }

      if(move === "block") {

        defence = 12;

      }

      enemyHP -= damage;

      addPoints(
        damage
      );

      if(enemyHP <= 0) {

        show();

        return;

      }

      const enemyDamage =
        Math.max(
          0,
          Math.floor(
            Math.random()*18
          ) + 8 -
          defence
        );

      playerHP -=
        enemyDamage;

      show();

    };

  show();

}

/* =========================================================
   EVENT 11
   PERFECT MATCH
   ========================================================= */

function event11() {

  const active =
    new Set();

  while(active.size < 6) {

    active.add(
      Math.floor(
        Math.random()*16
      )
    );

  }

  let clicked =
    new Set();

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 11 of 21
      </div>

      <h2>
        🧩 The Perfect Match
      </h2>

      <p>
        Memorise the six glowing tiles.
      </p>

      <div
        id="matchGrid"
        class="memory-grid"
      ></div>

    </div>

  `;

  const grid =
    document.getElementById(
      "matchGrid"
    );

  for(let i=0;i<16;i++) {

    const tile =
      document.createElement(
        "button"
      );

    tile.className =
      "memory-tile";

    tile.dataset.index =
      i;

    tile.textContent =
      "❔";

    grid.appendChild(
      tile
    );

  }

  active.forEach(
    index => {

      grid.children[
        index
      ].classList.add(
        "active"
      );

    }
  );

  setTimeout(
    () => {

      [...grid.children].forEach(
        tile => {

          tile.classList.remove(
            "active"
          );

          tile.textContent =
            "❔";

        }
      );

      grid.onclick =
        event => {

          const tile =
            event.target.closest(
              ".memory-tile"
            );

          if(!tile)
            return;

          const index =
            Number(
              tile.dataset.index
            );

          if(clicked.has(index))
            return;

          clicked.add(index);

          if(active.has(index)) {

            tile.classList.add(
              "active"
            );

            tile.textContent =
              "💗";

            addPoints(10);

            if(
              clicked.size >=
              active.size
            ) {

              finishEvent(
                80,
                true,
                "🧩 PERFECT MATCH",
                "You remembered every tile."
              );

            }

          } else {

            finishEvent(
              10,
              false,
              "💔 MATCH FAILED",
              "One of the tiles was wrong."
            );

          }

        };

    },
    1800
  );

}

/* =========================================================
   EVENT 12
   WHO KNOWS LILIANA BEST
   ========================================================= */

function event12() {

  const statements = [

    [
      "Liliana has green eyes.",
      true
    ],

    [
      "Liliana's birthday is July 22.",
      true
    ],

    [
      "Liliana studied Psychology.",
      true
    ],

    [
      "Liliana's favourite number is 3.",
      true
    ],

    [
      "Liliana has seven siblings.",
      false
    ],

    [
      "Liliana has two tattoos.",
      false
    ],

    [
      "Liliana has four piercings.",
      true
    ],

    [
      "Liliana's favourite animal is a dolphin.",
      true
    ]

  ];

  let index = 0;
  let score = 0;

  function show() {

    if(index >= statements.length) {

      finishEvent(
        score + 40,
        score >= 50,
        "🕵️ LILIANA KNOWLEDGE COMPLETE",
        `You got ${score / 10} statements right.`
      );

      return;

    }

    const statement =
      statements[index];

    document.getElementById(
      "app"
    ).innerHTML = `

      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 12 of 21
        </div>

        <h2>
          🕵️ Who Knows Liliana Best?
        </h2>

        <h3>
          ${statement[0]}
        </h3>

        <button
          class="btn"
          onclick="lilianaAnswer(true)"
        >
          TRUE
        </button>

        <button
          class="btn red"
          onclick="lilianaAnswer(false)"
        >
          FALSE
        </button>

      </div>

    `;

  }

  window.lilianaAnswer =
    function(answer) {

      if(
        answer ===
        statements[index][1]
      ) {

        score += 10;

        addPoints(10);

      }

      index++;

      show();

    };

  show();

}

/* =========================================================
   EVENT 13
   REACTION GAUNTLET
   ========================================================= */

function event13() {

  let round = 0;
  let score = 0;

  const commands =
    [
      "TAP",
      "HOLD",
      "DOUBLE TAP"
    ];

  function show() {

    if(round >= 10) {

      finishEvent(
        score + 40,
        score >= 35,
        "💨 REACTION GAUNTLET COMPLETE",
        `You scored ${score} reaction points.`
      );

      return;

    }

    const command =
      commands[
        Math.floor(
          Math.random() *
          commands.length
        )
      ];

    let tapped = 0;
    let holdTimer = null;
    let completed = false;

    document.getElementById(
      "app"
    ).innerHTML = `

      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 13 of 21
        </div>

        <h2>
          💨 The Reaction Gauntlet
        </h2>

        <div class="timer">
          ${round+1}/10
        </div>

        <h3>
          ${command}
        </h3>

        <button
          id="reactionButton"
          class="btn gold"
        >
          ⚡ ACT NOW
        </button>

        <div class="notice">
          ${score} reaction points
        </div>

      </div>

    `;

    const button =
      document.getElementById(
        "reactionButton"
      );

    function correct() {

      if(completed)
        return;

      completed = true;

      score += 5;

      addPoints(5);

      round++;

      setTimeout(
        show,
        350
      );

    }

    button.addEventListener(
      "click",
      () => {

        if(command === "TAP") {

          correct();

        } else if(
          command === "DOUBLE TAP"
        ) {

          tapped++;

          if(tapped >= 2)
            correct();

        }

      }
    );

    if(command === "HOLD") {

      button.addEventListener(
        "pointerdown",
        () => {

          holdTimer =
            setTimeout(
              correct,
              500
            );

        }
      );

      button.addEventListener(
        "pointerup",
        () => {

          clearTimeout(
            holdTimer
          );

        }
      );

    }

    setTimeout(
      () => {

        if(!completed) {

          round++;

          show();

        }

      },
      1800
    );

  }

  show();

}

/* =========================================================
   EVENT 14
   HEART HUNT
   ========================================================= */

function event14() {

  const walls =
    new Set(
      [
        1,
        2,
        6,
        7,
        20,
        21,
        22
      ]
    );

  let player = 0;
  const goal = 24;

  function show() {

    document.getElementById(
      "app"
    ).innerHTML = `

      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 14 of 21
        </div>

        <h2>
          🗺️ The Heart Hunt
        </h2>

        <p>
          Reach the heart at the end.
        </p>

        <div class="maze">

          ${Array.from(
            {length:25},
            (_,i) => `

              <div
                class="
                  maze-cell
                  ${walls.has(i) ? "wall" : ""}
                  ${i === player ? "player" : ""}
                  ${i === goal ? "goal" : ""}
                "
              >
                ${
                  i === player
                    ? "💗"
                    : i === goal
                      ? "❤️"
                      : ""
                }
              </div>

            `
          ).join("")}

        </div>

        <div class="grid">

          <button
            class="btn"
            onclick="moveMaze('up')"
          >
            ⬆️
          </button>

          <button
            class="btn"
            onclick="moveMaze('down')"
          >
            ⬇️
          </button>

          <button
            class="btn"
            onclick="moveMaze('left')"
          >
            ⬅️
          </button>

          <button
            class="btn"
            onclick="moveMaze('right')"
          >
            ➡️
          </button>

        </div>

      </div>

    `;

  }

  window.moveMaze =
    function(direction) {

      let next =
        player;

      if(direction === "up")
        next -= 5;

      if(direction === "down")
        next += 5;

      if(direction === "left") {

        if(player % 5 !== 0)
          next--;

      }

      if(direction === "right") {

        if(player % 5 !== 4)
          next++;

      }

      if(
        next < 0 ||
        next > 24 ||
        walls.has(next)
      ) {

        return;

      }

      player = next;

      addPoints(2);

      if(player === goal) {

        finishEvent(
          80,
          true,
          "❤️ HEART FOUND",
          "You found your way through the maze."
        );

        return;

      }

      show();

    };

  show();

}

/* =========================================================
   EVENT 15
   LOVE LOCK
   ========================================================= */

function event15() {

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 15 of 21
      </div>

      <h2>
        🔐 The Love Lock
      </h2>

      <p>
        Enter the secret four-digit code.
      </p>

      <input
        id="lockCode"
        inputmode="numeric"
        maxlength="4"
        placeholder="••••"
      >

      <button
        class="btn gold"
        onclick="unlockLove()"
      >
        🔓 Unlock
      </button>

    </div>

  `;

}

window.unlockLove =
  function() {

    const code =
      document.getElementById(
        "lockCode"
      ).value.trim();

    if(code === "3333") {

      finishEvent(
        100,
        true,
        "🔐 LOVE LOCK OPEN",
        "The secret lock has been opened."
      );

    } else {

      alert(
        "Wrong code. Try again."
      );

    }

  };

/* =========================================================
   EVENT 16
   CUPID SHOOTOUT
   ========================================================= */

function event16() {

  let time = 20;
  let hits = 0;
  let misses = 0;
  let active = true;

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 16 of 21
      </div>

      <h2>
        🎯 The Cupid Shootout
      </h2>

      <div
        class="timer"
        id="cupidTimer"
      >
        20
      </div>

      <div class="stats">

        <div class="stat">
          <strong id="cupidHits">0</strong>
          <small>Hearts</small>
        </div>

        <div class="stat">
          <strong id="cupidMisses">0</strong>
          <small>Misses</small>
        </div>

        <div class="stat">
          <strong>20s</strong>
          <small>Time</small>
        </div>

      </div>

      <div
        id="cupidArena"
        class="arena"
      ></div>

    </div>

  `;

  const timer =
    setInterval(
      () => {

        time--;

        document.getElementById(
          "cupidTimer"
        ).textContent =
          time;

        if(time <= 0) {

          clearInterval(
            timer
          );

          active = false;

          finishEvent(
            hits * 5,
            hits > misses,
            "🎯 CUPID SHOOTOUT COMPLETE",
            `You hit ${hits} hearts.`
          );

        }

      },
      1000
    );

  function spawn() {

    if(!active)
      return;

    const arena =
      document.getElementById(
        "cupidArena"
      );

    arena.innerHTML = "";

    const good =
      Math.random() > .28;

    const target =
      document.createElement(
        "button"
      );

    target.className =
      "target" +
      (good ? "" : " bad");

    target.textContent =
      good ? "💗" : "💔";

    target.style.left =
      Math.random()*82 + "%";

    target.style.top =
      Math.random()*75 + "%";

    target.onclick =
      () => {

        if(good) {

          hits++;

          addPoints(6);

        } else {

          misses++;

          addPoints(-3);

        }

        document.getElementById(
          "cupidHits"
        ).textContent =
          hits;

        document.getElementById(
          "cupidMisses"
        ).textContent =
          misses;

        spawn();

      };

    arena.appendChild(
      target
    );

  }

  spawn();

}

/* =========================================================
   EVENT 17
   COUNTDOWN
   ========================================================= */

function event17() {

  let challenge = 0;
  let seconds = 60;

  const tasks = [

    ["Tap ❤️","❤️"],
    ["Tap 🌹","🌹"],
    ["Tap ⭐","⭐"],
    ["Tap 🐬","🐬"],
    ["Tap GOLD","GOLD"]

  ];

  const countdown =
    setInterval(
      () => {

        seconds--;

        const timer =
          document.getElementById(
            "countdownTimer"
          );

        if(timer)
          timer.textContent =
            seconds;

        if(seconds <= 0) {

          clearInterval(
            countdown
          );

          finishEvent(
            challenge * 5,
            challenge >= 12,
            "🧨 COUNTDOWN COMPLETE",
            `You completed ${challenge} challenges.`
          );

        }

      },
      1000
    );

  function show() {

    if(challenge >= 20) {

      clearInterval(
        countdown
      );

      finishEvent(
        120,
        true,
        "🧨 COUNTDOWN MASTER",
        "You completed all twenty challenges."
      );

      return;

    }

    const task =
      tasks[
        Math.floor(
          Math.random() *
          tasks.length
        )
      ];

    document.getElementById(
      "app"
    ).innerHTML = `

      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 17 of 21
        </div>

        <h2>
          🧨 The Countdown
        </h2>

        <div
          id="countdownTimer"
          class="timer"
        >
          ${seconds}
        </div>

        <div class="big-number">
          ${task[1]}
        </div>

        <button
          class="btn gold"
          onclick="countdownChoice('${task[1]}','${task[1]}')"
        >
          ${task[0]}
        </button>

        <div class="notice">
          ${challenge}/20 completed
        </div>

      </div>

    `;

  }

  window.countdownChoice =
    function(
      answer,
      correct
    ) {

      challenge++;

      if(
        answer === correct
      ) {

        addPoints(5);

      }

      show();

    };

  show();

}

/* =========================================================
   EVENT 18
   ULTIMATE GAMBLE
   ========================================================= */

function event18() {

  let pot = 100;
  let turns = 0;

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 18 of 21
      </div>

      <h2>
        🎰 The Ultimate Gamble
      </h2>

      <p>
        Your final gamble before the Last Stand.
      </p>

      <div
        id="pot"
        class="big-number"
      >
        ${pot}
      </div>

      <button
        class="btn"
        onclick="ultimateGamble('safe')"
      >
        SAFE — Keep 75%
      </button>

      <button
        class="btn gold"
        onclick="ultimateGamble('risk')"
      >
        RISK — Double or Lose Half
      </button>

      <button
        class="btn red"
        onclick="ultimateGamble('all')"
      >
        ALL IN — Triple or Zero
      </button>

      <div
        id="ultimateMessage"
        class="notice"
      >
        Choose carefully.
      </div>

    </div>

  `;

  window.ultimateGamble =
    function(type) {

      if(turns >= 2)
        return;

      turns++;

      const win =
        Math.random() > .5;

      if(type === "safe") {

        pot =
          Math.floor(
            pot * .75
          );

        addPoints(10);

      }

      if(type === "risk") {

        pot =
          win
            ? pot * 2
            : Math.floor(
                pot * .5
              );

        addPoints(
          win ? 30 : -10
        );

      }

      if(type === "all") {

        pot =
          win
            ? pot * 3
            : 0;

        addPoints(
          win ? 60 : -20
        );

      }

      document.getElementById(
        "pot"
      ).textContent =
        pot;

      document.getElementById(
        "ultimateMessage"
      ).textContent =
        win ||
        type === "safe"
          ? "💗 The gamble paid off."
          : "💔 The house wins.";

      if(turns >= 2) {

        setTimeout(
          () => {

            finishEvent(
              Math.floor(
                pot / 2
              ),
              pot > 0,
              pot > 0
                ? "🎰 GAMBLE SURVIVED"
                : "💔 GAMBLE LOST",
              pot > 0
                ? "You still have something left for the Last Stand."
                : "The Ultimate Gamble took everything."
            );

          },
          500
        );

      }

    };

}

/* =========================================================
   EVENT 19
   LAST STAND
   ========================================================= */

function event19() {

  const trials = [

    ["Choose the heart.","❤️"],
    ["Choose the number three.","3"],
    ["Choose the dolphin.","🐬"],
    ["Choose the rose.","🌹"],
    ["Choose the star.","⭐"],
    ["Choose the heart.","❤️"]

  ];

  let index = 0;
  let lives = 3;

  function show() {

    if(index >= trials.length) {

      finishEvent(
        120,
        true,
        "💀 LAST STAND SURVIVED",
        "You survived every trial and reached the Lulu Derby."
      );

      return;

    }

    const trial =
      trials[index];

    document.getElementById(
      "app"
    ).innerHTML = `

      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 19 of 21
        </div>

        <h2>
          💀 The Admirer's Last Stand
        </h2>

        <div class="stats">

          <div class="stat">
            <strong>${lives}</strong>
            <small>Lives</small>
          </div>

          <div class="stat">
            <strong>${index+1}/6</strong>
            <small>Trial</small>
          </div>

          <div class="stat">
            <strong>${state.score}</strong>
            <small>Points</small>
          </div>

        </div>

        <h3>
          ${trial[0]}
        </h3>

        <div class="choices">

          ${[
            "❤️",
            "3",
            "🐬",
            "🌹",
            "⭐"
          ].map(
            answer => `

              <button
                class="choice"
                onclick="lastStand('${answer}')"
              >
                ${answer}
              </button>

            `
          ).join("")}

        </div>

      </div>

    `;

  }

  window.lastStand =
    function(answer) {

      if(
        answer ===
        trials[index][1]
      ) {

        addPoints(15);

      } else {

        lives--;

      }

      index++;

      if(lives <= 0) {

        finishEvent(
          20,
          false,
          "💔 LAST STAND FAILED",
          "You lost all three lives."
        );

        return;

      }

      show();

    };

  show();

}

/* =========================================================
   EVENT 20
   LULU DERBY
   ========================================================= */

const DERBY_LENGTH = 36;

const DERBY_ANIMALS = [

  {
    icon:"🐎",
    name:"Horse"
  },

  {
    icon:"🐺",
    name:"Wolf"
  },

  {
    icon:"🦊",
    name:"Fox"
  },

  {
    icon:"🐯",
    name:"Tiger"
  },

  {
    icon:"🐼",
    name:"Panda"
  },

  {
    icon:"🐨",
    name:"Koala"
  },

  {
    icon:"🐰",
    name:"Bunny"
  },

  {
    icon:"🦁",
    name:"Lion"
  }

];

const DERBY_MODES = {

  easy: {

    name:"Easy",
    description:
      "The computer moves slowly and makes mistakes.",
    interval:3200,
    twoChance:.08

  },

  medium: {

    name:"Medium",
    description:
      "A balanced race. The computer keeps you honest.",
    interval:2700,
    twoChance:.18

  },

  hard: {

    name:"Hard",
    description:
      "The computer moves quickly and rarely slows down.",
    interval:2200,
    twoChance:.32

  },

  expert: {

    name:"Expert",
    description:
      "The computer is relentless. Every answer matters.",
    interval:1800,
    twoChance:.48

  }

};

let derbyQuestion = 0;
let derbyQuestions = [];
let derbyPlayerPosition = 0;
let derbyComputerPosition = 0;
let derbyComputerTimer = null;
let derbyRaceFinished = false;
let derbyQuestionLocked = true;
let derbyMode = "medium";
let derbyPlayerIcon = "🐎";
let derbyPlayerIconName = "Horse";

/* =========================================================
   DERBY SETUP
   ========================================================= */

function event20() {

  derbyQuestion = 0;
  derbyQuestions =
    randomQuestions(
      QUESTION_BANK,
      80
    );

  derbyPlayerPosition = 0;
  derbyComputerPosition = 0;
  derbyRaceFinished = false;
  derbyQuestionLocked = true;

  if(derbyComputerTimer) {

    clearInterval(
      derbyComputerTimer
    );

    derbyComputerTimer = null;

  }

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel">

      <div class="badge">
        Event 20 of 21
      </div>

      <h2 class="center">
        🏇 THE LULU DERBY
      </h2>

      <p class="center">
        Choose your racer and computer difficulty.
        Then race all the way to the finish line.
      </p>

      <h3 class="center">
        🐎 Choose Your Racer
      </h3>

      <div class="animal-grid">

        ${DERBY_ANIMALS.map(
          animal => `

            <button
              class="
                animal-card
                ${
                  animal.icon ===
                  derbyPlayerIcon
                    ? "selected"
                    : ""
                }
              "
              onclick="
                selectDerbyAnimal(
                  '${animal.icon}',
                  '${animal.name}'
                )
              "
            >

              <span class="animal-icon">
                ${animal.icon}
              </span>

              ${animal.name}

            </button>

          `
        ).join("")}

      </div>

      <h3 class="center">
        🤖 Computer Difficulty
      </h3>

      <div class="mode-grid">

        ${Object.entries(
          DERBY_MODES
        ).map(
          (
            [key,mode]
          ) => `

            <button
              class="
                mode-card
                ${
                  key === derbyMode
                    ? "selected"
                    : ""
                }
              "
              onclick="
                selectDerbyMode('${key}')
              "
            >

              <strong>
                ${mode.name}
              </strong>

              <div
                class="race-mode-description"
              >
                ${mode.description}
              </div>

            </button>

          `
        ).join("")}

      </div>

      <div class="notice center">

        <strong>
          Your racer:
        </strong>

        ${derbyPlayerIcon}
        ${derbyPlayerIconName}

        <br><br>

        <strong>
          Difficulty:
        </strong>

        ${DERBY_MODES[derbyMode].name}

      </div>

      <button
        class="btn gold"
        onclick="startDerbyCountdown()"
      >
        🏁 Start The Derby
      </button>

      <button
        class="btn dark"
        onclick="home()"
      >
        Return Home
      </button>

    </div>

  `;

}

window.selectDerbyAnimal =
  function(
    icon,
    name
  ) {

    derbyPlayerIcon =
      icon;

    derbyPlayerIconName =
      name;

    event20();

  };

window.selectDerbyMode =
  function(mode) {

    derbyMode =
      mode;

    event20();

  };

/* =========================================================
   DERBY COUNTDOWN
   ========================================================= */

function startDerbyCountdown() {

  derbyQuestionLocked = true;

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        THE LULU DERBY
      </div>

      <h2>
        Get Ready!
      </h2>

      <p>
        ${derbyPlayerIcon}
        ${escapeHTML(state.playerName)}
        vs 🤖 Lulu Computer
      </p>

      <div
        id="derbyCountdown"
        class="derby-countdown"
      >
        5
      </div>

      <div class="notice">

        Difficulty:
        <strong>
          ${DERBY_MODES[derbyMode].name}
        </strong>

        <br><br>

        First to ${DERBY_LENGTH} spaces wins.

      </div>

    </div>

  `;

  let count = 5;

  const timer =
    setInterval(
      () => {

        count--;

        const display =
          document.getElementById(
            "derbyCountdown"
          );

        if(!display) {

          clearInterval(timer);

          return;

        }

        if(count > 0) {

          display.textContent =
            count;

        } else {

          clearInterval(timer);

          display.textContent =
            "🏁 GO!";

          setTimeout(
            startDerby,
            650
          );

        }

      },
      1000
    );

}

/* =========================================================
   START DERBY
   ========================================================= */

function startDerby() {

  derbyQuestionLocked =
    false;

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 20 of 21
      </div>

      <h2>
        🏇 THE LULU DERBY
      </h2>

      <div class="notice">

        👥 <strong>Active Participants</strong>

        <br><br>

        ${derbyPlayerIcon}
        ${escapeHTML(state.playerName)}

        <br>

        🤖 Lulu Computer

        <br><br>

        No other online participants detected.
        You have been matched against the computer.

      </div>

      <div id="derbyArea"></div>

    </div>

  `;

  renderDerby();

  const mode =
    DERBY_MODES[
      derbyMode
    ];

  derbyComputerTimer =
    setInterval(
      computerDerbyMove,
      mode.interval
    );

}

/* =========================================================
   DERBY TRACK
   ========================================================= */

function derbyTrackHTML() {

  const playerPercent =
    Math.min(
      94,
      (
        derbyPlayerPosition /
        DERBY_LENGTH
      ) * 94
    );

  const computerPercent =
    Math.min(
      94,
      (
        derbyComputerPosition /
        DERBY_LENGTH
      ) * 94
    );

  return `

    <div class="derby-track">

      <div class="race-lane">

        <div class="lane-name">
          ${derbyPlayerIcon}
          ${escapeHTML(state.playerName)}
        </div>

        <div class="finish-line"></div>

        <div
          class="racer"
          style="
            left:${playerPercent}%
          "
        >
          ${derbyPlayerIcon}
        </div>

        <div class="racer-name">
          YOU
        </div>

      </div>

      <div class="race-lane">

        <div class="lane-name">
          🤖 Lulu Computer
        </div>

        <div class="finish-line"></div>

        <div class="racer"
          style="
            left:${computerPercent}%
          "
        >
          🐎
        </div>

        <div class="racer-name">
          COMPUTER
        </div>

      </div>

    </div>

    <div class="derby-distance">

      ${Array.from(
        {
          length:DERBY_LENGTH
        }
      ).map(
        (_,i) => {

          const you =
            i <
            derbyPlayerPosition
              ? "you"
              : "";

          const bot =
            i <
            derbyComputerPosition
              ? "bot"
              : "";

          return `
            <span
              class="${you} ${bot}"
            ></span>
          `;

        }
      ).join("")}

    </div>

  `;

}

/* =========================================================
   RENDER DERBY
   ========================================================= */

function renderDerby(
  message =
    "Type the answer correctly to move your racer forward!"
) {

  if(derbyRaceFinished)
    return;

  const area =
    document.getElementById(
      "derbyArea"
    );

  if(!area)
    return;

  const question =
    derbyQuestions[
      derbyQuestion
    ];

  area.innerHTML = `

    <div class="stats">

      <div class="stat">

        <strong>
          ${derbyPlayerPosition}/${DERBY_LENGTH}
        </strong>

        <small>
          ${escapeHTML(state.playerName)}
        </small>

      </div>

      <div class="stat">

        <strong>
          ${derbyComputerPosition}/${DERBY_LENGTH}
        </strong>

        <small>
          Computer
        </small>

      </div>

      <div class="stat">

        <strong>
          ${derbyQuestion + 1}
        </strong>

        <small>
          Question
        </small>

      </div>

    </div>

    ${derbyTrackHTML()}

    <div class="derby-status">
      ${message}
    </div>

    <div class="derby-question">

      <div class="badge">
        TYPE YOUR ANSWER
      </div>

      <h3>
        ${escapeHTML(question.q)}
      </h3>

      <input
        id="derbyTypingAnswer"
        class="typing-answer"
        autocomplete="off"
        autocapitalize="off"
        spellcheck="false"
        placeholder="Type your answer here..."
        onkeydown="
          if(event.key === 'Enter')
            submitDerbyTypedAnswer();
        "
      >

      <button
        class="btn gold"
        onclick="submitDerbyTypedAnswer()"
      >
        🏁 Submit Answer
      </button>

    </div>

    <div class="notice center">

      🏁 First to ${DERBY_LENGTH} spaces wins.

      <br>

      💗 Correct answer:
      +1 or +2 spaces.

      <br>

      ❌ Wrong answer:
      You stay where you are.

      <br>

      🤖 The computer keeps racing while you think.

    </div>

  `;

  setTimeout(
    () => {

      const input =
        document.getElementById(
          "derbyTypingAnswer"
        );

      if(input)
        input.focus();

    },
    50
  );

}

/* =========================================================
   DERBY TYPED ANSWER
   ========================================================= */

function normaliseAnswer(
  answer
) {

  return String(answer)
    .trim()
    .toLowerCase()
    .replace(/[.,!?'"`]/g,"")
    .replace(/\s+/g," ");

}

window.submitDerbyTypedAnswer =
  function() {

    if(
      derbyRaceFinished ||
      derbyQuestionLocked
    )
      return;

    const input =
      document.getElementById(
        "derbyTypingAnswer"
      );

    if(!input)
      return;

    const typed =
      normaliseAnswer(
        input.value
      );

    if(!typed) {

      alert(
        "Type an answer first. ❤️"
      );

      return;

    }

    derbyQuestionLocked =
      true;

    const question =
      derbyQuestions[
        derbyQuestion
      ];

    const correct =
      normaliseAnswer(
        question.a[
          question.correct
        ]
      );

    const isCorrect =
      typed === correct;

    if(isCorrect) {

      const movement =
        Math.random() > .58
          ? 2
          : 1;

      derbyPlayerPosition =
        Math.min(
          DERBY_LENGTH,
          derbyPlayerPosition +
          movement
        );

      addPoints(20);

    } else {

      addPoints(2);

    }

    if(
      derbyPlayerPosition >=
      DERBY_LENGTH
    ) {

      finishDerby(
        true
      );

      return;

    }

    derbyQuestion++;

    if(
      derbyQuestion >=
      derbyQuestions.length
    ) {

      setTimeout(
        () => {

          finishDerby(
            derbyPlayerPosition >
            derbyComputerPosition
          );

        },
        700
      );

      return;

    }

    setTimeout(
      () => {

        derbyQuestionLocked =
          false;

        renderDerby(
          isCorrect
            ? "💗 Correct! Your racer charges forward!"
            : `💔 Wrong! The correct answer was ${escapeHTML(question.a[question.correct])}.`
        );

      },
      750
    );

  };

/* =========================================================
   COMPUTER DERBY
   ========================================================= */

function computerDerbyMove() {

  if(derbyRaceFinished)
    return;

  const mode =
    DERBY_MODES[
      derbyMode
    ];

  let movement = 1;

  if(
    Math.random() <
    mode.twoChance
  ) {

    movement = 2;

  }

  derbyComputerPosition =
    Math.min(
      DERBY_LENGTH,
      derbyComputerPosition +
      movement
    );

  if(
    derbyComputerPosition >=
    DERBY_LENGTH
  ) {

    finishDerby(
      false
    );

    return;

  }

  const area =
    document.getElementById(
      "derbyArea"
    );

  if(!area)
    return;

  const track =
    area.querySelector(
      ".derby-track"
    );

  const distance =
    area.querySelector(
      ".derby-distance"
    );

  const stats =
    area.querySelectorAll(
      ".stat strong"
    );

  if(track) {

    const percent =
      Math.min(
        94,
        (
          derbyComputerPosition /
          DERBY_LENGTH
        ) * 94
      );

    const racers =
      track.querySelectorAll(
        ".racer"
      );

    if(racers[1]) {

      racers[1].style.left =
        `${percent}%`;

    }

  }

  if(distance) {

    distance.innerHTML =
      Array.from(
        {
          length:DERBY_LENGTH
        }
      ).map(
        (_,i) => {

          const you =
            i <
            derbyPlayerPosition
              ? "you"
              : "";

          const bot =
            i <
            derbyComputerPosition
              ? "bot"
              : "";

          return `
            <span
              class="${you} ${bot}"
            ></span>
          `;

        }
      ).join("");

  }

  if(stats[1]) {

    stats[1].textContent =
      `${derbyComputerPosition}/${DERBY_LENGTH}`;

  }

}

/* =========================================================
   FINISH DERBY
   ========================================================= */

function finishDerby(
  playerWon
) {

  if(derbyRaceFinished)
    return;

  derbyRaceFinished =
    true;

  if(derbyComputerTimer) {

    clearInterval(
      derbyComputerTimer
    );

    derbyComputerTimer =
      null;

  }

  if(playerWon) {

    addPoints(200);

  } else {

    addPoints(50);

  }

  const area =
    document.getElementById(
      "derbyArea"
    );

  if(!area)
    return;

  area.innerHTML = `

    <div class="derby-result">

      <div class="result-icon">
        ${
          playerWon
            ? "🏆"
            : "🐎"
        }
      </div>

      <h2>
        ${
          playerWon
            ? "🏆 LULU DERBY CHAMPION!"
            : "🐎 THE COMPUTER WINS!"
        }
      </h2>

      <p>

        ${
          playerWon
            ? `
              ${escapeHTML(state.playerName)}
              crossed the finish line first!
              You conquered the Lulu Derby!
            `
            : `
              The computer reached the finish line first.
              You still fought all the way to the end!
            `
        }

      </p>

      ${derbyTrackHTML()}

      <div class="notice">

        🏁 Your position:
        <strong>
          ${derbyPlayerPosition}
        </strong>
        / ${DERBY_LENGTH}

        <br><br>

        🤖 Computer position:
        <strong>
          ${derbyComputerPosition}
        </strong>
        / ${DERBY_LENGTH}

        <br><br>

        ${
          playerWon
            ? "💗 +200 Heart Points"
            : "💗 +50 Heart Points"
        }

      </div>

      <button
        class="btn gold"
        onclick="finishDerbyAndContinue()"
      >
        👑 Continue to Final Challenge
      </button>

    </div>

  `;

}

window.finishDerbyAndContinue =
  function() {

    state.currentEvent =
      20;

    saveGame();

    render();

  };

/* =========================================================
   FINAL QUIZ
   ========================================================= */

const FINAL_QUIZ = [

  {
    q:"When is Liliana's birthday?",
    a:[
      "July 22",
      "July 12",
      "June 22",
      "August 22"
    ]
  },

  {
    q:"What is Liliana's favourite colour?",
    a:[
      "Baby pink",
      "Burgundy",
      "Baby blue",
      "Purple"
    ]
  },

  {
    q:"What is Liliana's favourite number?",
    a:[
      "3",
      "7",
      "22",
      "13"
    ]
  },

  {
    q:"What is Liliana's favourite food?",
    a:[
      "Sushi",
      "Pizza",
      "Burgers",
      "Pasta"
    ]
  },

  {
    q:"What is Liliana's favourite flower?",
    a:[
      "Roses and sunflowers",
      "Tulips",
      "Lilies",
      "Daisies"
    ]
  },

  {
    q:"What is Liliana's favourite animal?",
    a:[
      "Dolphins",
      "Cats",
      "Dogs",
      "Stingrays"
    ]
  },

  {
    q:"What is Liliana's favourite movie?",
    a:[
      "Me Before You",
      "Titanic",
      "The Notebook",
      "Frozen"
    ]
  },

  {
    q:"What genre of music does Liliana like?",
    a:[
      "R&B",
      "Country",
      "Classical",
      "Metal"
    ]
  },

  {
    q:"What is Liliana's zodiac sign?",
    a:[
      "Leo",
      "Cancer",
      "Virgo",
      "Gemini"
    ]
  },

  {
    q:"What colour are Liliana's eyes?",
    a:[
      "Green",
      "Blue",
      "Brown",
      "Hazel"
    ]
  },

  {
    q:"How many siblings does Liliana have?",
    a:[
      "5",
      "3",
      "4",
      "6"
    ]
  },

  {
    q:"How many nieces does Liliana have?",
    a:[
      "1",
      "2",
      "3",
      "4"
    ]
  },

  {
    q:"How many nephews does Liliana have?",
    a:[
      "2",
      "1",
      "3",
      "4"
    ]
  },

  {
    q:"How many dogs does Liliana have?",
    a:[
      "2",
      "1",
      "3",
      "4"
    ]
  },

  {
    q:"What are Liliana's dogs called?",
    a:[
      "Arlo & Aayla",
      "Aayla & Aria",
      "Arlo & Luna",
      "Ayla & Milo"
    ]
  },

  {
    q:"How many tattoos does Liliana have?",
    a:[
      "1",
      "2",
      "3",
      "4"
    ]
  },

  {
    q:"How many piercings does Liliana have?",
    a:[
      "4",
      "2",
      "3",
      "5"
    ]
  },

  {
    q:"What did Liliana study at university?",
    a:[
      "Psychology",
      "Law",
      "Medicine",
      "Business"
    ]
  },

  {
    q:"What is Liliana's favourite hobby?",
    a:[
      "Gambling",
      "Painting",
      "Swimming",
      "Cooking"
    ]
  },

  {
    q:"What does Liliana enjoy in her free time?",
    a:[
      "Concerts",
      "Gardening",
      "Running",
      "Fishing"
    ]
  },

  {
    q:"What kind of humour makes Liliana laugh?",
    a:[
      "Dark humour",
      "Slapstick",
      "Puns",
      "Dad jokes"
    ]
  },

  {
    q:"What does Liliana do when she is bored?",
    a:[
      "Go on HelloTalk",
      "Go running",
      "Watch documentaries",
      "Cook"
    ]
  },

  {
    q:"What does Liliana do when she is sad?",
    a:[
      "Listen to sad music and cry",
      "Go shopping",
      "Play games",
      "Go for a run"
    ]
  },

  {
    q:"What trait is Liliana proud of?",
    a:[
      "Honesty",
      "Patience",
      "Organisation",
      "Confidence"
    ]
  },

  {
    q:"What is Liliana's worst habit?",
    a:[
      "Smoking",
      "Sleeping late",
      "Shopping",
      "Procrastinating"
    ]
  },

  {
    q:"What is Liliana's biggest pet peeve?",
    a:[
      "Spam callers",
      "Traffic",
      "Rain",
      "Cold coffee"
    ]
  },

  {
    q:"What is Liliana good at?",
    a:[
      "Giving advice",
      "Cooking",
      "Dancing",
      "Singing"
    ]
  },

  {
    q:"What is Liliana terrible at?",
    a:[
      "Taking advice",
      "Cooking",
      "Dancing",
      "Remembering names"
    ]
  },

  {
    q:"What does Liliana hate?",
    a:[
      "Being interrupted",
      "Music",
      "Rain",
      "Animals"
    ]
  },

  {
    q:"What instantly makes Liliana happy?",
    a:[
      "Family",
      "Money",
      "Shopping",
      "Coffee"
    ]
  },

  {
    q:"What instantly makes Liliana angry?",
    a:[
      "Liars",
      "Rain",
      "Noise",
      "Traffic"
    ]
  },

  {
    q:"What is one of Liliana's biggest dreams?",
    a:[
      "To create a foundation she never had",
      "To become famous",
      "To travel everywhere",
      "To own a restaurant"
    ]
  },

  {
    q:"What is one of Liliana's biggest goals?",
    a:[
      "To get married and have a family",
      "To become a singer",
      "To move to space",
      "To become a professional athlete"
    ]
  },

  {
    q:"What would Liliana love to experience?",
    a:[
      "A Filipina",
      "A safari",
      "A polar expedition",
      "A cruise"
    ]
  },

  {
    q:"What is Liliana's favourite holiday?",
    a:[
      "Christmas",
      "Halloween",
      "Easter",
      "New Year's"
    ]
  },

  {
    q:"What is Liliana's favourite season?",
    a:[
      "Autumn",
      "Summer",
      "Winter",
      "Spring"
    ]
  },

  {
    q:"What is Liliana's favourite place?",
    a:[
      "Mum's house",
      "The beach",
      "The mountains",
      "A casino"
    ]
  },

  {
    q:"What does Liliana love receiving?",
    a:[
      "Birthday cards",
      "Flowers",
      "Jewellery",
      "Books"
    ]
  },

  {
    q:"What is something Liliana wants to do for her mum?",
    a:[
      "Buy her a house",
      "Buy her a car",
      "Take her overseas",
      "Open a business"
    ]
  },

  {
    q:"What is Liliana's biggest fear?",
    a:[
      "Losing people she loves",
      "Flying",
      "Heights",
      "Spiders"
    ]
  }

];

/* =========================================================
   EVENT 21
   FINAL CHALLENGE
   ========================================================= */

let finalQuestion = 0;
let finalCorrect = 0;
let currentFinalAnswers = [];

function event21() {

  finalQuestion = 0;
  finalCorrect = 0;
  currentFinalAnswers = [];

  showFinalQuestion();

}

function showFinalQuestion() {

  if(
    finalQuestion >=
    FINAL_QUIZ.length
  ) {

    finalWrittenChallenge();

    return;

  }

  const item =
    FINAL_QUIZ[
      finalQuestion
    ];

  /*
     IMPORTANT:
     Answers are SHUFFLED every time.
     The correct answer is NOT always first.
  */

  currentFinalAnswers =
    shuffle(
      item.a
    );

  const correct =
    item.a[0];

  const progress =
    (
      finalQuestion /
      FINAL_QUIZ.length
    ) * 100;

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel">

      <div class="badge">
        Event 21 of 21 • FINAL CHALLENGE
      </div>

      <h2>
        👑 Know Liliana
      </h2>

      <div class="progress">

        <div
          class="progress-bar"
          style="
            width:${progress}%
          "
        ></div>

      </div>

      <p>
        Question
        <strong>
          ${finalQuestion + 1}
        </strong>
        of
        <strong>
          ${FINAL_QUIZ.length}
        </strong>
      </p>

      <h3>
        ${escapeHTML(item.q)}
      </h3>

      <div class="choices">

        ${currentFinalAnswers.map(
          (
            answer,
            index
          ) => `

            <button
              class="choice"
              onclick="finalAnswer(${index})"
            >
              ${escapeHTML(answer)}
            </button>

          `
        ).join("")}

      </div>

      <div class="notice center">

        💗
        ${finalCorrect}
        correct so far

      </div>

    </div>

  `;

}

window.finalAnswer =
  function(index) {

    const item =
      FINAL_QUIZ[
        finalQuestion
      ];

    const selected =
      currentFinalAnswers[
        index
      ];

    const correct =
      item.a[0];

    const buttons =
      document.querySelectorAll(
        ".choice"
      );

    buttons.forEach(
      button => {

        button.disabled =
          true;

      }
    );

    const correctIndex =
      currentFinalAnswers.indexOf(
        correct
      );

    if(
      selected === correct
    ) {

      finalCorrect++;

      addPoints(25);

      buttons[index]
        .classList.add(
          "correct"
        );

    } else {

      buttons[index]
        .classList.add(
          "wrong"
        );

      buttons[
        correctIndex
      ].classList.add(
        "correct"
      );

    }

    finalQuestion++;

    setTimeout(
      showFinalQuestion,
      450
    );

  };

/* =========================================================
   FINAL WRITTEN CHALLENGE
   ========================================================= */

function finalWrittenChallenge() {

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Final Question
      </div>

      <h2>
        💌 One Last Thing
      </h2>

      <p>
        You've survived twenty events and answered
        the Liliana questions.
      </p>

      <h3>
        Why should Liliana choose you?
      </h3>

      <textarea
        id="finalMessage"
        placeholder="Make your case to Liliana..."
      ></textarea>

      <button
        class="btn gold"
        onclick="submitFinalMessage()"
      >
        👑 Submit My Answer
      </button>

    </div>

  `;

}

window.submitFinalMessage =
  function() {

    const message =
      document
        .getElementById(
          "finalMessage"
        )
        .value
        .trim();

    if(
      message.length < 10
    ) {

      alert(
        "You need to give Liliana a little more than that. ❤️"
      );

      return;

    }

    addPoints(150);

    state.finished =
      true;

    saveGame();

    finalResult();

  };

/* =========================================================
   RESET
   ========================================================= */

function resetJourney() {

  const confirmed =
    confirm(
      "Are you sure you want to reset the entire Lulu Express journey?"
    );

  if(!confirmed)
    return;

  state = {

    playerName:"",
    currentEvent:0,
    score:0,
    musicOn:true,
    finished:false

  };

  localStorage.removeItem(
    "luluExpress"
  );

  finalQuestion = 0;
  finalCorrect = 0;
  currentFinalAnswers = [];

  eventStartScore = 0;

  render();

}

/* =========================================================
   FINAL RESULT
   ========================================================= */

function finalResult() {

  const qualifies =
    state.score > 3000;

  let title;
  let message;

  if(state.score >= 5000) {

    title =
      "🏆 LULU EXPRESS LEGEND";

    message =
      "You absolutely dominated the entire Lulu Express.";

  } else if(state.score >= 4000) {

    title =
      "👑 LULU EXPRESS CHAMPION";

    message =
      "You didn't just survive the journey. You owned it.";

  } else if(state.score >= 3001) {

    title =
      "🥇 PRIVATE CALL QUALIFIED";

    message =
      "You pushed through every challenge and crossed the 3000 point barrier.";

  } else if(state.score >= 2500) {

    title =
      "🥈 ELITE ADMIRER";

    message =
      "You came incredibly close to unlocking the ultimate prize.";

  } else if(state.score >= 1500) {

    title =
      "💗 STRONG ADMIRER";

    message =
      "You survived an enormous journey and made it to the end.";

  } else {

    title =
      "💗 LULU EXPRESS SURVIVOR";

    message =
      "You survived the Lulu Express. That deserves respect.";

  }

  document.getElementById(
    "app"
  ).innerHTML = `

    ${topBar()}

    <div class="panel center final-box">

      <div class="trophy">
        👑
      </div>

      <div class="badge">
        Journey Complete
      </div>

      <h1>
        ${title}
      </h1>

      <p>
        <strong>
          ${escapeHTML(
            state.playerName
          )}
        </strong>
      </p>

      <p>
        ${message}
      </p>

      <div class="big-number">
        ${state.score}
      </div>

      <p>
        Final Heart Points
      </p>

      <hr
        style="
          border:0;
          border-top:1px solid #ffffff18;
          margin:22px 0;
        "
      >

      ${
        qualifies
          ? `

            <div class="trophy">
              📞
            </div>

            <div class="badge">
              3001+ POINTS UNLOCKED
            </div>

            <h2>
              Your Ultimate Prize
            </h2>

            <h2
              style="
                color:#f3ce6b;
              "
            >
              A PRIVATE CALL WITH LILIANA
            </h2>

            <p>
              You scored
              <strong>
                ${state.score}
              </strong>
              points.
            </p>

            <div class="notice">

              💗
              <strong>
                PRIVATE CALL UNLOCKED
              </strong>

              <br><br>

              You reached the required score of
              <strong>
                3001+
              </strong>
              Heart Points.

            </div>

          `
          : `

            <div class="trophy">
              🔒
            </div>

            <h2>
              The Private Call
            </h2>

            <div class="notice">

              The ultimate prize requires
              <strong>
                more than 3000 points.
              </strong>

              <br><br>

              Your score:
              <strong>
                ${state.score}
              </strong>

              <br><br>

              Required:
              <strong>
                3001+
              </strong>

              <br><br>

              ${
                state.score === 3000
                  ? "You were exactly 1 point short. 😭"
                  : "The private call remains locked."
              }

            </div>

          `
      }

      <div class="notice">

        🚂💗

        <strong>
          The Lulu Express has reached its final destination.
        </strong>

        <br><br>

        Congratulations, Admirer.

      </div>

      <button
        class="btn gold"
        onclick="resetJourney()"
      >
        🔄 Play Again
      </button>

      <button
        class="btn dark"
        onclick="home()"
      >
        Return to Lulu Express
      </button>

    </div>

  `;

}

/* =========================================================
   INITIALISE
   ========================================================= */

loadGame();

home();

</script>

</body>
</html>

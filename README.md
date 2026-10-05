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
  --bg: #12080e;
  --panel: #26121e;
  --panel2: #35182a;
  --pink: #f39ac4;
  --pink2: #c9578d;
  --light: #ffe5f0;
  --gold: #f3ce6b;
  --green: #8fe0ac;
  --red: #ff718c;
  --muted: #d7b8c8;
}

body {
  margin: 0;
  min-height: 100vh;
  color: white;
  font-family: Arial, Helvetica, sans-serif;
  background:
    radial-gradient(circle at 50% -10%, #733653 0%, #321624 38%, #12080e 78%);
}

button,
input,
textarea {
  font: inherit;
}

button {
  cursor: pointer;
}

#app {
  width: 100%;
  max-width: 760px;
  margin: auto;
  padding: 14px;
}

.topbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 14px;
}

.logo {
  font-weight: 900;
  font-size: 20px;
}

.logo span {
  color: var(--pink);
}

.music-btn {
  border: 1px solid #ffffff22;
  background: #ffffff10;
  color: white;
  border-radius: 12px;
  padding: 9px 12px;
}

.panel {
  background: linear-gradient(145deg, #321827, #1d0d16);
  border: 1px solid #ffffff18;
  border-radius: 24px;
  padding: 20px;
  box-shadow: 0 18px 50px #0009;
}

.center {
  text-align: center;
}

.badge {
  display: inline-block;
  padding: 6px 11px;
  border-radius: 999px;
  background: #f39ac418;
  border: 1px solid #f39ac444;
  color: var(--light);
  font-size: 11px;
  font-weight: bold;
  letter-spacing: 1px;
  text-transform: uppercase;
}

h1 {
  font-size: 42px;
  line-height: 1;
  margin: 12px 0;
}

h2 {
  font-size: 28px;
  margin: 9px 0;
}

h3 {
  line-height: 1.4;
}

p {
  color: var(--muted);
  line-height: 1.55;
}

.btn {
  width: 100%;
  border: 0;
  border-radius: 15px;
  padding: 14px;
  margin-top: 9px;
  font-weight: 900;
  color: #32101f;
  background: linear-gradient(135deg, #f8acd0, #bd4f87);
}

.btn.gold {
  background: linear-gradient(135deg, #ffe9a4, #d8ad3f);
}

.btn.red {
  background: linear-gradient(135deg, #ff9cad, #d34f70);
}

.btn.dark {
  color: white;
  background: #ffffff0c;
  border: 1px solid #ffffff20;
}

input,
textarea {
  width: 100%;
  background: #ffffff0b;
  color: white;
  border: 1px solid #ffffff20;
  border-radius: 14px;
  padding: 14px;
  outline: none;
}

textarea {
  min-height: 140px;
  resize: vertical;
}

.stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 8px;
  margin: 15px 0;
}

.stat {
  padding: 10px;
  border-radius: 14px;
  background: #ffffff08;
  border: 1px solid #ffffff10;
}

.stat strong {
  display: block;
  font-size: 20px;
  color: var(--light);
}

.stat small {
  color: var(--muted);
}

.notice {
  padding: 12px;
  border-radius: 14px;
  background: #f39ac410;
  border: 1px solid #f39ac426;
  margin: 12px 0;
  color: var(--muted);
}

.round-list {
  display: grid;
  gap: 7px;
  margin-top: 15px;
}

.round {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 10px;
  border-radius: 13px;
  background: #ffffff07;
  border: 1px solid #ffffff0d;
}

.round.current {
  border-color: #f39ac466;
  background: #f39ac410;
}

.round.locked {
  opacity: .35;
}

.round-number {
  width: 32px;
  height: 32px;
  flex-shrink: 0;
  display: grid;
  place-items: center;
  border-radius: 50%;
  background: #ffffff10;
  font-weight: 900;
}

.round.current .round-number {
  background: var(--pink);
  color: #32101f;
}

.choices {
  display: grid;
  gap: 9px;
}

.choice {
  width: 100%;
  padding: 14px;
  border-radius: 15px;
  border: 1px solid #ffffff18;
  background: #ffffff09;
  color: white;
  text-align: left;
}

.choice:hover {
  background: #f39ac418;
}

.choice:disabled {
  opacity: .8;
  cursor: default;
}

.correct {
  background: #8fe0ac25 !important;
  border-color: #8fe0ac88 !important;
}

.wrong {
  background: #ff718c25 !important;
  border-color: #ff718c88 !important;
}

.big-number {
  font-size: 48px;
  font-weight: 1000;
  color: var(--gold);
}

.timer {
  font-size: 35px;
  font-weight: 1000;
  color: var(--gold);
  text-align: center;
}

.arena {
  position: relative;
  height: 340px;
  overflow: hidden;
  border-radius: 20px;
  background: radial-gradient(circle, #63284b, #160a12);
  border: 1px solid #ffffff15;
}

.target {
  position: absolute;
  width: 58px;
  height: 58px;
  border: 0;
  border-radius: 50%;
  display: grid;
  place-items: center;
  font-size: 28px;
  background: var(--pink);
  box-shadow: 0 5px 25px #f39ac455;
}

.target.bad {
  background: #4b4b4b;
}

.memory-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 8px;
  margin: 18px 0;
}

.memory-tile {
  aspect-ratio: 1;
  border-radius: 13px;
  border: 1px solid #ffffff15;
  background: #ffffff0a;
  display: grid;
  place-items: center;
  font-size: 24px;
  color: white;
}

.memory-tile.active {
  background: var(--pink);
  color: #32101f;
}

.card-row {
  display: flex;
  justify-content: center;
  gap: 8px;
  flex-wrap: wrap;
  margin: 18px 0;
}

.card {
  width: 58px;
  height: 78px;
  display: grid;
  place-items: center;
  background: white;
  color: #27101d;
  border-radius: 9px;
  font-weight: 900;
  font-size: 20px;
}

.maze {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 5px;
  max-width: 330px;
  margin: 18px auto;
}

.maze-cell {
  aspect-ratio: 1;
  display: grid;
  place-items: center;
  border-radius: 7px;
  background: #ffffff09;
  font-size: 24px;
}

.maze-cell.wall {
  background: #080508;
}

.maze-cell.player {
  background: var(--pink);
  color: #32101f;
}

.maze-cell.goal {
  background: #f3ce6b33;
  border: 1px solid var(--gold);
}

.grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 8px;
}

.progress {
  height: 8px;
  border-radius: 999px;
  overflow: hidden;
  background: #ffffff10;
  margin: 14px 0;
}

.progress-bar {
  height: 100%;
  background: linear-gradient(90deg, var(--pink), var(--gold));
  transition: width .25s;
}

.final-box {
  border: 2px solid var(--gold);
  background: radial-gradient(circle at top, #68294d, #25111c);
}

.trophy {
  font-size: 65px;
}

.result-icon {
  font-size: 70px;
  margin: 18px 0;
}

.result-points {
  font-size: 32px;
  font-weight: 1000;
  color: var(--gold);
}

.hidden {
  display: none !important;
}

@media (max-width: 430px) {
  #app {
    padding: 10px;
  }

  .panel {
    padding: 16px;
  }

  h1 {
    font-size: 35px;
  }

  .grid {
    grid-template-columns: 1fr;
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
   20 EVENTS
   SECRET SKIP CODE: 3333
   NO EXTERNAL MUSIC FILE
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
  "👑 THE FINAL CHALLENGE"
];

/* =========================================================
   EVENT 3 QUESTIONS
   ========================================================= */

const PRESSURE_QUIZ = [
  {
    question: "What is 12 + 8?",
    answers: ["20", "18", "22", "24"],
    correct: 0
  },
  {
    question: "Which shape has three sides?",
    answers: ["Triangle", "Square", "Circle", "Hexagon"],
    correct: 0
  },
  {
    question: "How many hours are in a day?",
    answers: ["24", "12", "36", "48"],
    correct: 0
  },
  {
    question: "Which planet is closest to the Sun?",
    answers: ["Mercury", "Mars", "Earth", "Venus"],
    correct: 0
  },
  {
    question: "How many letters are in the English alphabet?",
    answers: ["26", "24", "28", "30"],
    correct: 0
  },
  {
    question: "What is 7 × 8?",
    answers: ["56", "48", "54", "64"],
    correct: 0
  },
  {
    question: "Which direction is opposite to north?",
    answers: ["South", "East", "West", "Up"],
    correct: 0
  },
  {
    question: "How many months are in a year?",
    answers: ["12", "10", "11", "13"],
    correct: 0
  }
];

/* =========================================================
   EVENT 20
   ========================================================= */

const FINAL_QUIZ = [

  ["When is Liliana's birthday?",
   ["July 22", "July 12", "June 22", "August 22"], 0],

  ["What is Liliana's favourite colour?",
   ["Baby pink", "Burgundy", "Purple", "Red"], 0],

  ["What is Liliana's favourite number?",
   ["3", "6", "7", "22"], 0],

  ["What food does Liliana love?",
   ["Sushi", "Pizza", "Pasta", "Burgers"], 0],

  ["Which animal is one of Liliana's favourites?",
   ["Dolphins", "Cats", "Wolves", "Horses"], 0],

  ["Which flower is one of Liliana's favourites?",
   ["Sunflowers", "Tulips", "Orchids", "Daisies"], 0],

  ["Which other flower does Liliana love?",
   ["Roses", "Lilies", "Peonies", "Lavender"], 0],

  ["What is Liliana's favourite movie?",
   ["Me Before You", "Titanic", "The Notebook", "Mamma Mia"], 0],

  ["What kind of songs does Liliana like?",
   ["Sad songs", "Only country songs", "Only metal", "Only classical"], 0],

  ["What type of writing does Liliana enjoy?",
   ["Poetry", "News articles", "Textbooks", "Manuals"], 0],

  ["What kind of games does Liliana enjoy?",
   ["Poker and gambling", "Football", "Chess only", "Golf"], 0],

  ["Which word best describes Liliana?",
   ["Sweet", "Cold", "Unfriendly", "Distant"], 0],

  ["Which other word best describes Liliana?",
   ["Caring", "Cruel", "Impatient", "Aloof"], 0],

  ["Liliana has been described as being...",
   ["Charismatic", "Unapproachable", "Silent", "Strict"], 0],

  ["Liliana is known for being...",
   ["Flirtatious", "Uninterested", "Extremely shy", "Serious"], 0],

  ["How long have Bree and Liliana been best friends?",
   ["6 years", "2 years", "4 years", "10 years"], 0],

  ["What is Liliana's heritage?",
   ["Mexican American", "Canadian American", "Australian American", "British American"], 0],

  ["How many tattoos does Liliana have?",
   ["1", "2", "3", "4"], 0],

  ["What symbol is connected to Liliana's tattoo?",
   ["A semicolon", "A star", "A rose", "A dolphin"], 0],

  ["What colour are Liliana's eyes?",
   ["Green", "Blue", "Brown", "Grey"], 0],

  ["How many piercings does Liliana have?",
   ["4", "2", "3", "5"], 0],

  ["What is one of Liliana's dogs called?",
   ["Aayla", "Lola", "Yuna", "Kai"], 0],

  ["What is Liliana's other dog's name?",
   ["Arlo", "Rene", "Mikael", "Bree"], 0],

  ["How many siblings does Liliana have?",
   ["5", "3", "4", "7"], 0],

  ["What is Liliana's star sign?",
   ["Leo", "Cancer", "Virgo", "Libra"], 0],

  ["What is Liliana afraid of?",
   ["Drowning", "Flying", "Thunder", "Heights"], 0],

  ["What did Liliana study at university?",
   ["Psychology", "Law", "Nursing", "Business"], 0],

  ["What does Liliana want to be one day?",
   ["A mum to a baby girl", "A pilot", "A professional athlete", "A chef"], 0],

  ["Which quality is associated with Liliana?",
   ["Empathy", "Indifference", "Dishonesty", "Coldness"], 0],

  ["Which flower combination belongs to Liliana's favourites?",
   ["Sunflowers and roses", "Tulips and lilies", "Orchids and daisies", "Lavender and tulips"], 0],

  ["Which number would Liliana most likely pick as her favourite?",
   ["3", "13", "30", "33"], 0],

  ["Which hobby matches Liliana's interests?",
   ["Gambling", "Fishing", "Gardening", "Knitting"], 0],

  ["Which food would you expect Liliana to be excited about?",
   ["Sushi", "Toast", "Cereal", "Soup"], 0],

  ["Which animal fits Liliana's favourite animals?",
   ["Dolphin", "Eagle", "Tiger", "Bear"], 0],

  ["Which shade is closest to Liliana's favourite colour?",
   ["Baby pink", "Navy blue", "Forest green", "Orange"], 0],

  ["Which movie belongs on Liliana's favourites list?",
   ["Me Before You", "Shrek", "Avatar", "Frozen"], 0],

  ["Which card game fits Liliana's interests?",
   ["Poker", "Go Fish", "Solitaire only", "Snap"], 0],

  ["Which flower would be a safe choice for Liliana?",
   ["Rose", "Cactus", "Fern", "Bamboo"], 0],

  ["Which month contains Liliana's birthday?",
   ["July", "June", "August", "May"], 0],

  ["What day of July is Liliana's birthday?",
   ["22nd", "12th", "20th", "27th"], 0],

  ["Which eye colour belongs to Liliana?",
   ["Green", "Hazel", "Blue", "Grey"], 0],

  ["Which university subject belongs to Liliana?",
   ["Psychology", "Physics", "Engineering", "Accounting"], 0],

  ["Which fear belongs to Liliana?",
   ["Drowning", "Dark rooms", "Needles", "Thunder"], 0],

  ["Which of these is one of Liliana's dogs?",
   ["Aayla", "Kai", "Lola", "Yuna"], 0],

  ["Which of these is her other dog?",
   ["Arlo", "Rene", "Bree", "Mikael"], 0],

  ["Which tattoo count is correct?",
   ["1", "0", "2", "5"], 0],

  ["Which piercing count is correct?",
   ["4", "1", "5", "6"], 0],

  ["Which future family wish has Liliana shared?",
   ["To be a mum to a baby girl", "To have no children", "To become a pilot", "To own a farm"], 0],

  ["Which of these is something Liliana enjoys?",
   ["Poetry", "Only textbooks", "Only documentaries", "Only sports"], 0],

  ["Which combination describes Liliana best?",
   ["Sweet, caring and charismatic", "Cold, quiet and distant", "Strict, serious and impatient", "Reserved, formal and aloof"], 0]
];

/* =========================================================
   STATE
   ========================================================= */

let state = {
  playerName: "",
  currentEvent: 0,
  score: 0,
  musicOn: true,
  finished: false
};

let eventStartScore = 0;

function loadGame() {
  try {
    const saved = localStorage.getItem("luluExpress");

    if (saved) {
      state = Object.assign(
        state,
        JSON.parse(saved)
      );
    }
  } catch (error) {
    console.log("Save data could not be loaded.");
  }
}

function saveGame() {
  try {
    localStorage.setItem(
      "luluExpress",
      JSON.stringify(state)
    );
  } catch (error) {
    console.log("Save data could not be saved.");
  }
}

loadGame();

/* =========================================================
   MUSIC
   ========================================================= */

let audioContext = null;
let masterGain = null;
let musicStarted = false;
let musicInterval = null;

function startMusic() {

  if (!state.musicOn) return;

  if (!audioContext) {

    const AudioCtx =
      window.AudioContext ||
      window.webkitAudioContext;

    if (!AudioCtx) return;

    audioContext = new AudioCtx();

    masterGain =
      audioContext.createGain();

    masterGain.gain.value = 0.035;

    masterGain.connect(
      audioContext.destination
    );
  }

  if (audioContext.state === "suspended") {
    audioContext.resume();
  }

  if (musicStarted) {

    masterGain.gain.value = 0.035;

    return;
  }

  musicStarted = true;

  const melody = [
    261.63, 329.63, 392.00, 329.63,
    293.66, 349.23, 440.00, 349.23,
    261.63, 329.63, 392.00, 493.88,
    293.66, 349.23, 440.00, 523.25
  ];

  let index = 0;

  function playNote() {

    if (
      !audioContext ||
      !masterGain ||
      !state.musicOn
    ) {
      return;
    }

    const oscillator =
      audioContext.createOscillator();

    const gain =
      audioContext.createGain();

    oscillator.type = "sine";

    oscillator.frequency.value =
      melody[index % melody.length];

    gain.gain.setValueAtTime(
      0,
      audioContext.currentTime
    );

    gain.gain.linearRampToValueAtTime(
      0.8,
      audioContext.currentTime + 0.04
    );

    gain.gain.exponentialRampToValueAtTime(
      0.001,
      audioContext.currentTime + 0.65
    );

    oscillator.connect(gain);
    gain.connect(masterGain);

    oscillator.start();

    oscillator.stop(
      audioContext.currentTime + 0.7
    );

    index++;
  }

  playNote();

  musicInterval =
    setInterval(playNote, 600);
}

function toggleMusic() {

  state.musicOn = !state.musicOn;

  saveGame();

  if (state.musicOn) {

    startMusic();

  } else if (masterGain) {

    masterGain.gain.value = 0;
  }

  render();
}

/* =========================================================
   GENERAL UI
   ========================================================= */

function escapeHTML(value) {

  return String(value)
    .replaceAll("&", "&amp;")
    .replaceAll("<", "&lt;")
    .replaceAll(">", "&gt;")
    .replaceAll('"', "&quot;")
    .replaceAll("'", "&#039;");
}

function topBar() {

  return `
    <div class="topbar">

      <div class="logo">
        🚂 <span>Lulu Express</span>
      </div>

      <button
        class="music-btn"
        onclick="toggleMusic()"
      >
        ${state.musicOn ? "🔊 Music" : "🔇 Music"}
      </button>

    </div>
  `;
}

function stats() {

  return `
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
        <strong>20</strong>
        <small>Total Events</small>
      </div>

    </div>
  `;
}

function addPoints(points) {

  state.score =
    Math.max(
      0,
      state.score + points
    );

  saveGame();
}

/* =========================================================
   EVENT RESULT SYSTEM
   ========================================================= */

function finishEvent(
  points = 0,
  success = true,
  resultTitle = "",
  resultMessage = ""
) {

  addPoints(points);

  const earned =
    state.score - eventStartScore;

  if (!resultTitle) {

    resultTitle =
      success
        ? "✅ CHALLENGE COMPLETE"
        : "❌ CHALLENGE FAILED";
  }

  if (!resultMessage) {

    resultMessage =
      success
        ? "You successfully completed this event."
        : "You didn't quite make it through this challenge.";
  }

  showEventResult(
    earned,
    success,
    resultTitle,
    resultMessage
  );
}

function showEventResult(
  points,
  success,
  title,
  message
) {

  const eventNumber =
    state.currentEvent + 1;

  const remaining =
    20 - eventNumber;

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event ${eventNumber} Result
      </div>

      <div class="result-icon">
        ${success ? "🏆" : "💔"}
      </div>

      <h1 style="
        color:${success ? "var(--green)" : "var(--red)"};
        font-size:32px;
      ">
        ${title}
      </h1>

      <p>
        ${message}
      </p>

      <div class="notice">

        <div class="result-points">
          ${points >= 0 ? "+" : ""}${points}
        </div>

        Heart Points Earned This Event

      </div>

      <div class="stats">

        <div class="stat">
          <strong>${state.score}</strong>
          <small>Total Points</small>
        </div>

        <div class="stat">
          <strong>${eventNumber}</strong>
          <small>Completed</small>
        </div>

        <div class="stat">
          <strong>${remaining}</strong>
          <small>Remaining</small>
        </div>

      </div>

      ${
        eventNumber < 20
          ? `
            <button
              class="btn gold"
              onclick="continueToNextEvent()"
            >
              🚂 Continue to Event ${eventNumber + 1}
            </button>
          `
          : `
            <button
              class="btn gold"
              onclick="continueToFinalChallenge()"
            >
              👑 Continue to the Final Challenge
            </button>
          `
      }

    </div>
  `;
}

function continueToNextEvent() {

  if (state.currentEvent < 19) {

    state.currentEvent++;

    saveGame();

    render();
  }
}

function continueToFinalChallenge() {

  state.currentEvent = 19;

  saveGame();

  render();
}

/* =========================================================
   HOME
   ========================================================= */

function home() {

  const app =
    document.getElementById("app");

  app.innerHTML = `
    ${topBar()}

    <div class="panel center">

      <div class="badge">
        🚂 All aboard
      </div>

      <h1>
        Lulu<br>Express 💗
      </h1>

      <p>
        Twenty challenges.<br>
        One final destination.<br>
        One winner.
      </p>

      ${
        state.playerName
          ? `
            <div class="notice">

              Welcome back,
              <strong>
                ${escapeHTML(state.playerName)}
              </strong>.

              <br>

              You are currently on Event
              <strong>
                ${state.currentEvent + 1}
              </strong>.

            </div>
          `
          : `
            <input
              id="playerName"
              maxlength="30"
              placeholder="Enter your name, Admirer"
            >
          `
      }

      <button
        class="btn gold"
        onclick="boardTrain()"
      >
        🚂 ${
          state.playerName
            ? "Continue Journey"
            : "Board the Lulu Express"
        }
      </button>

      ${
        state.playerName
          ? `
            ${stats()}
            ${roundList()}
          `
          : ""
      }

    </div>
  `;
}

function roundList() {

  return `
    <div class="round-list">

      ${EVENTS.map((event, index) => {

        let className = "round";

        if (
          index ===
          state.currentEvent
        ) {
          className += " current";
        }

        if (
          index >
          state.currentEvent
        ) {
          className += " locked";
        }

        const number =
          index < state.currentEvent
            ? "✓"
            : index + 1;

        return `
          <div class="${className}">

            <div class="round-number">
              ${number}
            </div>

            <div>

              <strong>${event}</strong>

              <br>

              <small>
                ${
                  index < state.currentEvent
                    ? "Completed"
                    : index === state.currentEvent
                    ? "Current"
                    : "🔒 Locked"
                }
              </small>

            </div>

          </div>
        `;

      }).join("")}

    </div>
  `;
}

function boardTrain() {

  startMusic();

  if (!state.playerName) {

    const input =
      document.getElementById("playerName");

    const name =
      input.value.trim();

    if (!name) {

      input.focus();

      return;
    }

    state.playerName = name;

    saveGame();
  }

  render();
}

/* =========================================================
   LOCKED EVENT ACCESS
   ========================================================= */

function lockedScreen() {

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">

      <div class="badge">
        🔒 Locked Carriage
      </div>

      <h2>
        This carriage is locked.
      </h2>

      <p>
        You must complete the current event before
        the next event becomes available.
      </p>

      <button
        class="btn"
        onclick="render()"
      >
        Return to Current Event
      </button>

      <button
        class="btn dark"
        onclick="accessCode()"
      >
        🔐 Secret Access
      </button>

    </div>
  `;
}

function accessCode() {

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">

      <div class="badge">
        🔐 Express Override
      </div>

      <h2>
        Enter Access Code
      </h2>

      <p>
        Know the conductor's secret?
      </p>

      <input
        id="secretCode"
        inputmode="numeric"
        maxlength="4"
        placeholder="••••"
      >

      <button
        class="btn gold"
        onclick="checkCode()"
      >
        Unlock
      </button>

      <button
        class="btn dark"
        onclick="render()"
      >
        Cancel
      </button>

    </div>
  `;
}

function checkCode() {

  const code =
    document
      .getElementById("secretCode")
      .value
      .trim();

  if (code === "3333") {

    state.currentEvent = 19;

    saveGame();

    render();

  } else {

    alert("❌ Incorrect code.");
  }
}

/* =========================================================
   EVENT ROUTER
   ========================================================= */

function render() {

  if (state.finished) {

    finalResult();

    return;
  }

  if (!state.playerName) {

    home();

    return;
  }

  eventStartScore = state.score;

  switch (state.currentEvent) {

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

    default:
      home();
  }
}

/* =========================================================
   EVENT 1
   THE HEART RATE
   ========================================================= */

function event1() {

  let hits = 0;
  let misses = 0;
  let time = 20;

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel">

      <div class="badge">
        Event 1 of 20
      </div>

      <h2>
        ❤️ The Heart Rate
      </h2>

      <p>
        Tap the hearts. Avoid the broken hearts.
      </p>

      <div class="stats">

        <div class="stat">
          <strong id="hits">0</strong>
          <small>Hearts</small>
        </div>

        <div class="stat">
          <strong id="misses">0</strong>
          <small>Broken</small>
        </div>

        <div class="stat">
          <strong id="time">20</strong>
          <small>Seconds</small>
        </div>

      </div>

      <div id="arena" class="arena"></div>

    </div>
  `;

  const arena =
    document.getElementById("arena");

  function spawn() {

    if (time <= 0) return;

    const target =
      document.createElement("button");

    const good =
      Math.random() > 0.22;

    target.className =
      good
        ? "target"
        : "target bad";

    target.textContent =
      good
        ? "❤️"
        : "💔";

    target.style.left =
      `${Math.random() * 80 + 5}%`;

    target.style.top =
      `${Math.random() * 75 + 5}%`;

    target.onclick = function() {

      if (good) {

        hits++;

        addPoints(5);

      } else {

        misses++;

        addPoints(-4);
      }

      document.getElementById(
        "hits"
      ).textContent = hits;

      document.getElementById(
        "misses"
      ).textContent = misses;

      target.remove();
    };

    arena.appendChild(target);

    setTimeout(() => {

      if (target.parentNode) {
        target.remove();
      }

    }, 900);
  }

  const spawnTimer =
    setInterval(spawn, 450);

  const countdown =
    setInterval(() => {

      time--;

      document.getElementById(
        "time"
      ).textContent = time;

      if (time <= 0) {

        clearInterval(spawnTimer);
        clearInterval(countdown);

        setTimeout(() => {

          finishEvent(
            hits * 2,
            hits > misses,
            hits > misses
              ? "❤️ HEART RATE MASTER"
              : "💔 HEART RATE FAILED",
            hits > misses
              ? "You caught more hearts than broken hearts."
              : "The broken hearts got the better of you this time."
          );

        }, 400);
      }

    }, 1000);

  spawn();
}

/* =========================================================
   EVENT 2
   MEMORY VAULT
   ========================================================= */

function event2() {

  let level = 3;

  const symbols = [
    "❤️",
    "🌹",
    "⭐",
    "🐬",
    "🎲",
    "🌙",
    "☀️",
    "🦋"
  ];

  function startLevel() {

    const sequence = [];

    for (let i = 0; i < level; i++) {

      sequence.push(
        symbols[
          Math.floor(
            Math.random() *
            symbols.length
          )
        ]
      );
    }

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 2 of 20
        </div>

        <h2>
          🧠 The Memory Vault
        </h2>

        <p>
          Memorise the sequence.
        </p>

        <div class="notice">
          Level ${level}
        </div>

        <div
          id="memoryGrid"
          class="memory-grid"
        ></div>

      </div>
    `;

    const grid =
      document.getElementById(
        "memoryGrid"
      );

    sequence.forEach(symbol => {

      const tile =
        document.createElement("div");

      tile.className =
        "memory-tile";

      tile.textContent =
        symbol;

      grid.appendChild(tile);
    });

    let current = 0;

    const flash =
      setInterval(() => {

        const tiles =
          grid.children;

        [...tiles].forEach(tile =>
          tile.classList.remove(
            "active"
          )
        );

        if (current < tiles.length) {

          tiles[
            current
          ].classList.add(
            "active"
          );

          current++;

        } else {

          clearInterval(flash);

          setTimeout(() => {

            playSequence(
              sequence
            );

          }, 300);
        }

      }, 600);
  }

  function playSequence(sequence) {

    const playerSequence = [];

    const grid =
      document.getElementById(
        "memoryGrid"
      );

    grid.innerHTML = "";

    symbols.forEach(symbol => {

      const button =
        document.createElement(
          "button"
        );

      button.className =
        "memory-tile";

      button.textContent =
        symbol;

      button.onclick =
        function() {

          const expected =
            sequence[
              playerSequence.length
            ];

          if (symbol !== expected) {

            alert(
              "💔 Wrong sequence. Try again."
            );

            setTimeout(
              startLevel,
              400
            );

            return;
          }

          playerSequence.push(
            symbol
          );

          button.classList.add(
            "active"
          );

          if (
            playerSequence.length ===
            sequence.length
          ) {

            addPoints(
              level * 10
            );

            if (level >= 6) {

              setTimeout(() => {

                finishEvent(
                  30,
                  true,
                  "🧠 MEMORY VAULT MASTER",
                  "You remembered every sequence and cracked the Memory Vault."
                );

              }, 500);

            } else {

              level++;

              setTimeout(
                startLevel,
                700
              );
            }
          }
        };

      grid.appendChild(button);
    });
  }

  startLevel();
}

/* =========================================================
   EVENT 3
   PRESSURE QUIZ
   ========================================================= */

function event3() {

  let question = 0;
  let points = 0;
  let timer = null;

  function showQuestion() {

    if (
      question >=
      PRESSURE_QUIZ.length
    ) {

      finishEvent(
        points + 20,
        points >= 60,
        points >= 60
          ? "⚡ PRESSURE QUIZ MASTER"
          : "⚡ PRESSURE QUIZ COMPLETE",
        points >= 60
          ? "You kept your head under pressure."
          : "You made it through the pressure round."
      );

      return;
    }

    const current =
      PRESSURE_QUIZ[question];

    let seconds = 5;

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel">

        <div class="badge">
          Event 3 of 20
        </div>

        <h2>
          ⚡ The Pressure Quiz
        </h2>

        <div
          id="pressureTimer"
          class="timer"
        >
          5
        </div>

        <p>
          Question
          ${question + 1}
          of
          ${PRESSURE_QUIZ.length}
        </p>

        <h3>
          ${current.question}
        </h3>

        <div class="choices">

          ${current.answers.map(
            (answer, index) => `
              <button
                class="choice"
                onclick="pressureAnswer(${index})"
              >
                ${answer}
              </button>
            `
          ).join("")}

        </div>

      </div>
    `;

    timer =
      setInterval(() => {

        seconds--;

        const display =
          document.getElementById(
            "pressureTimer"
          );

        if (display) {
          display.textContent =
            seconds;
        }

        if (seconds <= 0) {

          clearInterval(timer);

          question++;

          setTimeout(
            showQuestion,
            250
          );
        }

      }, 1000);
  }

  window.pressureAnswer =
    function(index) {

      clearInterval(timer);

      if (
        index ===
        PRESSURE_QUIZ[
          question
        ].correct
      ) {

        points += 15;

        addPoints(15);
      }

      question++;

      setTimeout(
        showQuestion,
        250
      );
    };

  showQuestion();
}

/* =========================================================
   EVENT 4
   HIGH ROLLER
   ========================================================= */

function event4() {

  let tokens = 100;
  let turns = 0;

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 4 of 20
      </div>

      <h2>
        🎰 The High Roller
      </h2>

      <p>
        Risk your Love Tokens for bigger rewards.
      </p>

      <div
        id="tokens"
        class="big-number"
      >
        100
      </div>

      <button
        class="btn"
        onclick="highRoll(10)"
      >
        SAFE — Bet 10
      </button>

      <button
        class="btn gold"
        onclick="highRoll(25)"
      >
        RISKY — Bet 25
      </button>

      <button
        class="btn red"
        onclick="highRoll(50)"
      >
        ALL IN — Bet 50
      </button>

      <div
        id="gambleMessage"
        class="notice"
      >
        Choose your bet.
      </div>

    </div>
  `;

  window.highRoll =
    function(amount) {

      turns++;

      const win =
        Math.random() > 0.42;

      if (win) {

        tokens +=
          amount * 2;

        addPoints(amount);

        document.getElementById(
          "gambleMessage"
        ).textContent =
          "💗 WIN! The Lulu Express is smiling.";

      } else {

        tokens -= amount;

        addPoints(
          -Math.floor(
            amount / 2
          )
        );

        document.getElementById(
          "gambleMessage"
        ).textContent =
          "💔 LOSS! The house takes the bet.";
      }

      tokens =
        Math.max(
          0,
          tokens
        );

      document.getElementById(
        "tokens"
      ).textContent =
        tokens;

      if (turns >= 5) {

        finishEvent(
          Math.floor(tokens / 4),
          tokens >= 75,
          tokens >= 75
            ? "🎰 HIGH ROLLER WIN"
            : "🎰 HIGH ROLLER COMPLETE",
          tokens >= 75
            ? "You kept your nerve at the table."
            : "You survived five rounds at the table."
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

    {
      q: "Liliana has had a terrible day. What do you do?",
      a: [
        "Listen without taking over.",
        "Tell her to get over it.",
        "Ignore her.",
        "Change the subject."
      ]
    },

    {
      q: "Liliana tells you something personal. What matters most?",
      a: [
        "Respecting her trust.",
        "Tell everyone.",
        "Laugh about it.",
        "Change the subject."
      ]
    },

    {
      q: "A disagreement happens. What is the strongest move?",
      a: [
        "Communicate honestly.",
        "Refuse to talk.",
        "Make it a competition.",
        "Pretend it never happened."
      ]
    },

    {
      q: "You have one free evening together. What sounds best?",
      a: [
        "Let Liliana choose something fun.",
        "Make every decision yourself.",
        "Cancel.",
        "Start an argument."
      ]
    }
  ];

  let questionIndex = 0;

  function show() {

    if (
      questionIndex >=
      questions.length
    ) {

      finishEvent(
        30,
        true,
        "🧠 MIND GAMES COMPLETE",
        "You showed strong judgement and compatibility."
      );

      return;
    }

    const item =
      questions[questionIndex];

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel">

        <div class="badge">
          Event 5 of 20
        </div>

        <h2>
          🧠 The Mind Games
        </h2>

        <p>
          Choose the response that shows the strongest
          compatibility.
        </p>

        <h3>
          ${item.q}
        </h3>

        <div class="choices">

          ${item.a.map(
            (answer, i) => `
              <button
                class="choice"
                onclick="mindChoice(${i})"
              >
                ${answer}
              </button>
            `
          ).join("")}

        </div>

      </div>
    `;
  }

  window.mindChoice =
    function(answerIndex) {

      if (answerIndex === 0) {

        addPoints(15);

      } else {

        addPoints(3);
      }

      questionIndex++;

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

  function draw() {

    const cards = [
      "A♥",
      "K♦",
      "Q♣"
    ];

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 6 of 20
        </div>

        <h2>
          🃏 The Bluff
        </h2>

        <p>
          Bet, fold or bluff your way through three hands.
        </p>

        <div class="big-number">
          ${chips}
        </div>

        <div class="card-row">

          ${cards.map(card => `
            <div class="card">
              ${card}
            </div>
          `).join("")}

        </div>

        <button
          class="btn"
          onclick="bluffMove('bet')"
        >
          BET 25
        </button>

        <button
          class="btn gold"
          onclick="bluffMove('bluff')"
        >
          BLUFF 40
        </button>

        <button
          class="btn dark"
          onclick="bluffMove('fold')"
        >
          FOLD
        </button>

        <div
          id="bluffMessage"
          class="notice"
        >
          Make your move.
        </div>

      </div>
    `;
  }

  window.bluffMove =
    function(move) {

      turn++;

      const win =
        Math.random() > 0.45;

      if (move === "fold") {

        chips =
          Math.max(
            0,
            chips - 5
          );

        document.getElementById(
          "bluffMessage"
        ).textContent =
          "You folded. Sometimes survival is the best strategy.";

      } else if (win) {

        const reward =
          move === "bluff"
            ? 40
            : 25;

        chips += reward;

        addPoints(15);

        document.getElementById(
          "bluffMessage"
        ).textContent =
          "🎉 They believed you!";

      } else {

        const loss =
          move === "bluff"
            ? 40
            : 25;

        chips =
          Math.max(
            0,
            chips - loss
          );

        document.getElementById(
          "bluffMessage"
        ).textContent =
          "💔 Your opponent called the bluff.";
      }

      if (turn >= 3) {

        setTimeout(() => {

          finishEvent(
            Math.floor(chips / 4),
            chips >= 50,
            chips >= 50
              ? "🃏 BLUFF MASTER"
              : "🃏 BLUFF ROUND FAILED",
            chips >= 50
              ? "You kept enough chips to survive the table."
              : "The table took most of your chips."
          );

        }, 500);

      } else {

        setTimeout(
          draw,
          500
        );
      }
    };

  draw();
}

/* =========================================================
   EVENT 7
   SURVIVAL ROUND
   ========================================================= */

function event7() {

  const symbols = [
    "❤️",
    "🌹",
    "⭐",
    "🐬",
    "🎲",
    "🌙",
    "☀️",
    "🦋"
  ];

  let level = 3;
  let sequence = [];
  let player = [];
  let acceptingAnswers = false;

  function start() {

    sequence = [];
    player = [];
    acceptingAnswers = false;

    for (
      let i = 0;
      i < level;
      i++
    ) {

      sequence.push(
        symbols[
          Math.floor(
            Math.random() *
            symbols.length
          )
        ]
      );
    }

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 7 of 20
        </div>

        <h2>
          ⚡ The Survival Round
        </h2>

        <p>
          Memorise the sequence.
          One mistake ends the challenge.
        </p>

        <div class="notice">
          Level ${level}
        </div>

        <div
          id="sequence"
          class="memory-grid"
        ></div>

        <div
          id="survivalStatus"
          class="notice"
        >
          Watch carefully...
        </div>

      </div>
    `;

    const display =
      document.getElementById(
        "sequence"
      );

    let flashIndex = 0;

    /*
      IMPORTANT:
      The previous version left the entire sequence
      visible. This version shows ONE symbol at a time,
      then removes it completely before showing the next.
    */

    const flashTimer =
      setInterval(() => {

        display.innerHTML = "";

        if (
          flashIndex <
          sequence.length
        ) {

          const tile =
            document.createElement(
              "div"
            );

          tile.className =
            "memory-tile active";

          tile.textContent =
            sequence[flashIndex];

          display.appendChild(
            tile
          );

          flashIndex++;

        } else {

          clearInterval(
            flashTimer
          );

          display.innerHTML = "";

          document.getElementById(
            "survivalStatus"
          ).textContent =
            "🧠 The sequence is gone. Now reproduce it.";

          setTimeout(
            showChoices,
            500
          );
        }

      }, 750);
  }

  function showChoices() {

    acceptingAnswers = true;

    const panel =
      document.querySelector(
        ".panel"
      );

    if (!panel) return;

    panel.insertAdjacentHTML(
      "beforeend",
      `
        <div
          class="choices"
          id="survivalChoices"
        >

          ${symbols.map(symbol => `
            <button
              class="choice"
              onclick="survivalPick('${symbol}')"
            >
              ${symbol}
            </button>
          `).join("")}

        </div>

        <div
          class="notice"
          id="survivalProgress"
        >
          0 / ${sequence.length}
        </div>
      `
    );
  }

  window.survivalPick =
    function(symbol) {

      if (!acceptingAnswers) {
        return;
      }

      const expected =
        sequence[player.length];

      const buttons =
        document.querySelectorAll(
          "#survivalChoices .choice"
        );

      buttons.forEach(
        button => {
          button.disabled = true;
        }
      );

      if (symbol !== expected) {

        acceptingAnswers = false;

        const clicked =
          [
            ...buttons
          ].find(
            button =>
              button.textContent.trim() ===
              symbol
          );

        if (clicked) {
          clicked.classList.add(
            "wrong"
          );
        }

        setTimeout(() => {

          finishEvent(
            10,
            false,
            "❌ SURVIVAL FAILED",
            "You remembered the sequence incorrectly. The Survival Round got you."
          );

        }, 600);

        return;
      }

      const clicked =
        [
          ...buttons
        ].find(
          button =>
            button.textContent.trim() ===
            symbol
        );

      if (clicked) {
        clicked.classList.add(
          "correct"
        );
      }

      player.push(symbol);

      addPoints(10);

      document.getElementById(
        "survivalProgress"
      ).textContent =
        `${player.length} / ${sequence.length}`;

      if (
        player.length ===
        sequence.length
      ) {

        acceptingAnswers = false;

        if (level >= 5) {

          setTimeout(() => {

            finishEvent(
              35,
              true,
              "⚡ SURVIVAL MASTER",
              "You memorised every sequence and survived the final level."
            );

          }, 700);

        } else {

          level++;

          setTimeout(
            start,
            900
          );
        }

      } else {

        setTimeout(() => {

          buttons.forEach(
            button => {
              button.disabled = false;
            }
          );

        }, 250);
      }
    };

  start();
}

/* =========================================================
   EVENT 8
   ADMIRER RACE
   ========================================================= */

function event8() {

  const symbols = [
    "❤️",
    "🌹",
    "⭐",
    "🐬"
  ];

  let player = 0;
  let rival = 0;
  let lap = 0;

  function draw() {

    if (lap >= 8) {

      finishEvent(
        player >= rival
          ? 50
          : 15,
        player >= rival,
        player >= rival
          ? "🏎️ RACE VICTORY"
          : "🏎️ RACE DEFEAT",
        player >= rival
          ? "You beat the rival to the finish line."
          : "Your rival reached the finish line first."
      );

      return;
    }

    const target =
      symbols[
        Math.floor(
          Math.random() *
          symbols.length
        )
      ];

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 8 of 20
        </div>

        <h2>
          🏎️ The Admirer Race
        </h2>

        <p>
          Tap the matching symbol before your rival moves.
        </p>

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
            <strong>${lap + 1}/8</strong>
            <small>Lap</small>
          </div>

        </div>

        <div class="big-number">
          ${target}
        </div>

        <div class="choices">

          ${symbols.map(
            symbol => `
              <button
                class="choice"
                onclick="racePick('${symbol}')"
              >
                ${symbol}
              </button>
            `
          ).join("")}

        </div>

      </div>
    `;
  }

  window.racePick =
    function(symbol) {

      const target =
        document.querySelector(
          ".big-number"
        ).textContent;

      if (symbol === target) {

        player++;

        addPoints(8);

      } else {

        rival++;
      }

      if (
        Math.random() >
        0.5
      ) {
        rival++;
      }

      lap++;

      draw();
    };

  draw();
}

/* =========================================================
   EVENT 9
   HEARTBREAK CHAMBER
   ========================================================= */

function event9() {

  let doors = 0;
  let points = 0;

  function draw() {

    if (doors >= 5) {

      const earned =
        Math.max(
          0,
          points
        ) + 15;

      finishEvent(
        earned,
        points >= 0,
        points >= 0
          ? "💗 CHAMBER SURVIVED"
          : "💔 HEARTBREAK CHAMBER FAILED",
        points >= 0
          ? "You made it through all five doors."
          : "The chamber dealt you more heartbreak than luck."
      );

      return;
    }

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 9 of 20
        </div>

        <h2>
          💔 The Heartbreak Chamber
        </h2>

        <p>
          Five doors. Five consequences.
        </p>

        <div class="big-number">
          ${points}
        </div>

        <div class="grid">

          <button
            class="btn"
            onclick="chooseDoor()"
          >
            🚪 Door 1
          </button>

          <button
            class="btn gold"
            onclick="chooseDoor()"
          >
            🚪 Door 2
          </button>

          <button
            class="btn"
            onclick="chooseDoor()"
          >
            🚪 Door 3
          </button>

          <button
            class="btn red"
            onclick="chooseDoor()"
          >
            🚪 Door 4
          </button>

        </div>

        <div class="notice">
          Door ${doors + 1} of 5
        </div>

      </div>
    `;
  }

  window.chooseDoor =
    function() {

      const outcomes = [
        30,
        15,
        -10,
        50
      ];

      const result =
        outcomes[
          Math.floor(
            Math.random() *
            outcomes.length
          )
        ];

      points += result;

      addPoints(result);

      doors++;

      draw();
    };

  draw();
}

/* =========================================================
   EVENT 10
   BOXING
   ========================================================= */

function event10() {

  let playerHP = 100;
  let enemyHP = 100;

  function draw(
    message = "Choose your move."
  ) {

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 10 of 20
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
            <small>Opponent HP</small>
          </div>

        </div>

        <button
          class="btn"
          onclick="fightMove('punch')"
        >
          🥊 Punch
        </button>

        <button
          class="btn gold"
          onclick="fightMove('heavy')"
        >
          💥 Heavy Punch
        </button>

        <button
          class="btn dark"
          onclick="fightMove('block')"
        >
          🛡️ Block
        </button>

        <div class="notice">
          ${message}
        </div>

      </div>
    `;
  }

  window.fightMove =
    function(move) {

      let damage = 0;

      if (move === "punch") {

        damage =
          Math.floor(
            Math.random() * 12
          ) + 8;
      }

      if (move === "heavy") {

        damage =
          Math.floor(
            Math.random() * 25
          ) + 5;
      }

      enemyHP =
        Math.max(
          0,
          enemyHP - damage
        );

      addPoints(damage);

      if (enemyHP > 0) {

        let enemyDamage =
          Math.floor(
            Math.random() * 12
          ) + 5;

        if (move === "block") {

          enemyDamage =
            Math.floor(
              enemyDamage / 4
            );
        }

        playerHP =
          Math.max(
            0,
            playerHP - enemyDamage
          );
      }

      if (enemyHP <= 0) {

        finishEvent(
          50,
          true,
          "🥊 MATCH WON",
          "You knocked out the heartbreak and survived the ring."
        );

      } else if (playerHP <= 0) {

        finishEvent(
          10,
          false,
          "💔 MATCH LOST",
          "The heartbreak fighter knocked you out this time."
        );

      } else {

        draw(
          move === "block"
            ? "🛡️ You blocked the attack."
            : "💥 Keep fighting!"
        );
      }
    };

  draw();
}

/* =========================================================
   EVENT 11
   PERFECT MATCH
   ========================================================= */

function event11() {

  const pattern = [];

  for (
    let i = 0;
    i < 16;
    i++
  ) {

    pattern.push(
      Math.random() > 0.55
    );
  }

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 11 of 20
      </div>

      <h2>
        🧩 The Perfect Match
      </h2>

      <p>
        Memorise the glowing pattern.
        Then recreate it.
      </p>

      <div
        id="pattern"
        class="memory-grid"
      ></div>

    </div>
  `;

  const grid =
    document.getElementById(
      "pattern"
    );

  pattern.forEach(active => {

    const tile =
      document.createElement(
        "div"
      );

    tile.className =
      "memory-tile";

    if (active) {
      tile.classList.add(
        "active"
      );
    }

    grid.appendChild(tile);
  });

  setTimeout(() => {

    [
      ...grid.children
    ].forEach(
      (tile, index) => {

        tile.classList.remove(
          "active"
        );

        tile.onclick =
          function() {

            if (pattern[index]) {

              tile.classList.add(
                "active"
              );

              addPoints(5);

              if (
                [
                  ...grid.children
                ].filter(
                  element =>
                    element.classList.contains(
                      "active"
                    )
                ).length ===
                pattern.filter(Boolean).length
              ) {

                finishEvent(
                  40,
                  true,
                  "🧩 PERFECT MATCH",
                  "You recreated Liliana's pattern perfectly."
                );
              }

            } else {

              tile.classList.add(
                "wrong"
              );

              finishEvent(
                5,
                false,
                "💔 MATCH FAILED",
                "You hit the wrong tile and broke the pattern."
              );
            }
          };
      }
    );

  }, 1700);
}

/* =========================================================
   EVENT 12
   WHO KNOWS LILIANA BEST
   ========================================================= */

function event12() {

  const statements = [

    ["Liliana has green eyes.", true],

    ["Liliana has seven siblings.", false],

    ["Liliana studied Psychology.", true],

    ["Liliana's birthday is July 22.", true],

    ["Liliana has two tattoos.", false],

    ["Liliana is afraid of drowning.", true],

    ["Liliana has four piercings.", true],

    ["Liliana's favourite number is 9.", false]

  ];

  let index = 0;

  function show() {

    if (
      index >=
      statements.length
    ) {

      finishEvent(
        40,
        true,
        "🕵️ LILIANA EXPERT",
        "You proved that you know Liliana extremely well."
      );

      return;
    }

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 12 of 20
        </div>

        <h2>
          🕵️ Who Knows Liliana Best?
        </h2>

        <p>
          Is this statement true or false?
        </p>

        <h3>
          ${statements[index][0]}
        </h3>

        <button
          class="btn gold"
          onclick="truthAnswer(true)"
        >
          TRUE
        </button>

        <button
          class="btn"
          onclick="truthAnswer(false)"
        >
          FALSE
        </button>

      </div>
    `;
  }

  window.truthAnswer =
    function(answer) {

      if (
        answer ===
        statements[index][1]
      ) {

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

  const commands = [
    "TAP",
    "TAP",
    "HOLD",
    "DOUBLE TAP"
  ];

  let round = 0;

  function show() {

    if (round >= 10) {

      finishEvent(
        40,
        true,
        "💨 REACTION MASTER",
        "You survived all ten reaction challenges."
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

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 13 of 20
        </div>

        <h2>
          💨 The Reaction Gauntlet
        </h2>

        <p>
          Follow the command as quickly as possible.
        </p>

        <div class="big-number">
          ${command}
        </div>

        <button
          id="reaction"
          class="btn gold"
        >
          DO IT
        </button>

        <div class="notice">
          Round ${round + 1} of 10
        </div>

      </div>
    `;

    const button =
      document.getElementById(
        "reaction"
      );

    let completed = false;
    let holdStart = 0;
    let taps = 0;
    let lastTap = 0;

    function success() {

      if (completed) return;

      completed = true;

      addPoints(5);

      round++;

      setTimeout(
        show,
        200
      );
    }

    const timeout =
      setTimeout(() => {

        if (!completed) {

          completed = true;

          round++;

          setTimeout(
            show,
            200
          );
        }

      }, 1800);

    if (command === "TAP") {

      button.onclick =
        success;

    } else if (
      command === "HOLD"
    ) {

      button.onpointerdown =
        () => {

          holdStart =
            Date.now();
        };

      button.onpointerup =
        () => {

          if (
            Date.now() -
            holdStart >=
            500
          ) {

            clearTimeout(
              timeout
            );

            success();
          }
        };

    } else {

      button.onclick =
        () => {

          const now =
            Date.now();

          if (
            now -
            lastTap <
            500
          ) {

            taps++;

          } else {

            taps = 1;
          }

          lastTap = now;

          if (taps >= 2) {

            clearTimeout(
              timeout
            );

            success();
          }
        };
    }
  }

  show();
}

/* =========================================================
   EVENT 14
   HEART HUNT
   ========================================================= */

function event14() {

  /*
    GUARANTEED PATH:

    0 → 5 → 10 → 11 → 16 → 21
    → 20 → 15 → 14 → 13 → 18
    → 23 → 24

    The previous wall layout blocked the goal completely.
  */

  const walls =
    new Set([
      1, 2, 3, 4,
      6, 7, 8, 9,
      12,
      17,
      19,
      22
    ]);

  let player = 0;

  const goal = 24;

  let finished = false;

  function draw() {

    if (finished) return;

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 14 of 20
        </div>

        <h2>
          🗺️ The Heart Hunt
        </h2>

        <p>
          Navigate the maze and reach ❤️.
        </p>

        <div
          id="maze"
          class="maze"
        ></div>

        <div class="grid">

          <button
            class="btn"
            onclick="movePlayer(-5)"
          >
            ⬆️
          </button>

          <button
            class="btn"
            onclick="movePlayer(-1)"
          >
            ⬅️
          </button>

          <button
            class="btn dark"
            onclick="movePlayer(5)"
          >
            ⬇️
          </button>

          <button
            class="btn"
            onclick="movePlayer(1)"
          >
            ➡️
          </button>

        </div>

        <div
          id="mazeMessage"
          class="notice"
        >
          🚂 Find the heart.
        </div>

      </div>
    `;

    const maze =
      document.getElementById(
        "maze"
      );

    for (
      let i = 0;
      i < 25;
      i++
    ) {

      const cell =
        document.createElement(
          "div"
        );

      cell.className =
        "maze-cell";

      if (walls.has(i)) {
        cell.classList.add(
          "wall"
        );
      }

      if (i === player) {

        cell.classList.add(
          "player"
        );

        cell.textContent =
          "🚂";
      }

      if (i === goal) {

        cell.classList.add(
          "goal"
        );

        cell.textContent =
          "❤️";
      }

      maze.appendChild(cell);
    }
  }

  window.movePlayer =
    function(direction) {

      if (finished) return;

      const currentRow =
        Math.floor(
          player / 5
        );

      const currentCol =
        player % 5;

      let next = player;

      if (direction === -5) {

        if (currentRow > 0) {
          next = player - 5;
        }

      } else if (
        direction === 5
      ) {

        if (currentRow < 4) {
          next = player + 5;
        }

      } else if (
        direction === -1
      ) {

        if (currentCol > 0) {
          next = player - 1;
        }

      } else if (
        direction === 1
      ) {

        if (currentCol < 4) {
          next = player + 1;
        }
      }

      if (walls.has(next)) {

        const message =
          document.getElementById(
            "mazeMessage"
          );

        if (message) {
          message.textContent =
            "🧱 Blocked! Try another direction.";
        }

        return;
      }

      if (next === player) {
        return;
      }

      player = next;

      addPoints(2);

      if (player === goal) {

        finished = true;

        setTimeout(() => {

          finishEvent(
            40,
            true,
            "❤️ HEART FOUND",
            "You navigated the Lulu Express through the maze and found Liliana's heart."
          );

        }, 300);

        return;
      }

      draw();
    };

  draw();
}

/* =========================================================
   EVENT 15
   LOVE LOCK
   ========================================================= */

function event15() {

  let entered = "";

  function draw() {

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 15 of 20
        </div>

        <h2>
          🔐 The Love Lock
        </h2>

        <p>
          Solve the clue:
        </p>

        <div class="notice">
          What four-digit number is the secret
          Lulu Express override code?
        </div>

        <div class="big-number">
          ${entered || "••••"}
        </div>

        <div class="grid">

          ${[
            1,2,3,4,5,
            6,7,8,9,0
          ].map(
            number => `
              <button
                class="choice"
                onclick="enterDigit(${number})"
              >
                ${number}
              </button>
            `
          ).join("")}

        </div>

        <button
          class="btn dark"
          onclick="clearDigits()"
        >
          Clear
        </button>

      </div>
    `;
  }

  window.enterDigit =
    function(number) {

      if (
        entered.length >= 4
      ) {
        return;
      }

      entered += number;

      if (
        entered.length === 4
      ) {

        if (
          entered === "3333"
        ) {

          finishEvent(
            50,
            true,
            "🔐 LOCK OPENED",
            "You cracked the Love Lock and opened the next carriage."
          );

        } else {

          alert(
            "🔒 The lock rejected the code."
          );

          entered = "";

          draw();
        }

      } else {

        draw();
      }
    };

  window.clearDigits =
    function() {

      entered = "";

      draw();
    };

  draw();
}

/* =========================================================
   EVENT 16
   CUPID SHOOTOUT
   ========================================================= */

function event16() {

  let hits = 0;
  let misses = 0;
  let seconds = 20;

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel">

      <div class="badge">
        Event 16 of 20
      </div>

      <h2>
        🎯 The Cupid Shootout
      </h2>

      <p>
        Hit ❤️. Avoid 💔.
      </p>

      <div class="stats">

        <div class="stat">
          <strong id="shootHits">0</strong>
          <small>Hits</small>
        </div>

        <div class="stat">
          <strong id="shootMisses">0</strong>
          <small>Misses</small>
        </div>

        <div class="stat">
          <strong id="shootTime">20</strong>
          <small>Seconds</small>
        </div>

      </div>

      <div
        id="shootArena"
        class="arena"
      ></div>

    </div>
  `;

  const arena =
    document.getElementById(
      "shootArena"
    );

  function spawn() {

    if (seconds <= 0) return;

    const target =
      document.createElement(
        "button"
      );

    const good =
      Math.random() > 0.25;

    target.className =
      good
        ? "target"
        : "target bad";

    target.textContent =
      good
        ? "❤️"
        : "💔";

    target.style.left =
      `${Math.random() * 80 + 5}%`;

    target.style.top =
      `${Math.random() * 75 + 5}%`;

    target.onclick =
      () => {

        if (good) {

          hits++;

          addPoints(6);

        } else {

          misses++;

          addPoints(-4);
        }

        document.getElementById(
          "shootHits"
        ).textContent =
          hits;

        document.getElementById(
          "shootMisses"
        ).textContent =
          misses;

        target.remove();
      };

    arena.appendChild(
      target
    );

    setTimeout(() => {

      if (target.parentNode) {
        target.remove();
      }

    }, 800);
  }

  const spawnTimer =
    setInterval(
      spawn,
      350
    );

  const timer =
    setInterval(() => {

      seconds--;

      document.getElementById(
        "shootTime"
      ).textContent =
        seconds;

      if (seconds <= 0) {

        clearInterval(
          spawnTimer
        );

        clearInterval(
          timer
        );

        setTimeout(() => {

          finishEvent(
            hits * 2,
            hits > misses,
            hits > misses
              ? "🎯 CUPID'S VICTORY"
              : "💔 CUPID'S DEFEAT",
            hits > misses
              ? "You hit more hearts than you missed."
              : "Too many broken hearts got in the way."
          );

        }, 300);
      }

    }, 1000);

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
    ["Tap ❤️", "❤️"],
    ["Tap 🌹", "🌹"],
    ["Tap ⭐", "⭐"],
    ["Tap 🐬", "🐬"],
    ["Tap GOLD", "GOLD"]
  ];

  const countdown =
    setInterval(() => {

      seconds--;

      const timer =
        document.getElementById(
          "countdown"
        );

      if (timer) {
        timer.textContent =
          seconds;
      }

      if (
        seconds <= 0
      ) {

        clearInterval(
          countdown
        );

        if (
          challenge < 20
        ) {

          finishEvent(
            challenge * 3 + 10,
            challenge >= 10,
            challenge >= 10
              ? "🧨 COUNTDOWN SURVIVED"
              : "💔 COUNTDOWN FAILED",
            challenge >= 10
              ? "You completed enough challenges before the timer ran out."
              : "The countdown beat you before you could finish."
          );
        }

      }

    }, 1000);

  function show() {

    if (
      challenge >= 20
    ) {

      clearInterval(
        countdown
      );

      finishEvent(
        60,
        true,
        "🧨 COUNTDOWN MASTER",
        "You completed all twenty challenges before the clock ran out."
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

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 17 of 20
        </div>

        <h2>
          🧨 The Countdown
        </h2>

        <div
          id="countdown"
          class="timer"
        >
          ${seconds}
        </div>

        <p>
          ${task[0]}
        </p>

        <div class="choices">

          ${tasks.map(
            item => `
              <button
                class="choice"
                onclick="countdownChoice('${item[1]}','${task[1]}')"
              >
                ${item[1]}
              </button>
            `
          ).join("")}

        </div>

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

      if (
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

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Event 18 of 20
      </div>

      <h2>
        🎰 The Ultimate Gamble
      </h2>

      <p>
        Your final gamble before the last stand.
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

      turns++;

      const win =
        Math.random() > 0.5;

      if (type === "safe") {

        pot =
          Math.floor(
            pot * 0.75
          );
      }

      if (type === "risk") {

        pot =
          win
            ? pot * 2
            : Math.floor(
                pot * 0.5
              );
      }

      if (type === "all") {

        pot =
          win
            ? pot * 3
            : 0;
      }

      document.getElementById(
        "pot"
      ).textContent =
        pot;

      document.getElementById(
        "ultimateMessage"
      ).textContent =
        win || type === "safe"
          ? "💗 The gamble paid off."
          : "💔 The house wins.";

      if (turns >= 2) {

        setTimeout(() => {

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

        }, 500);
      }
    };
}

/* =========================================================
   EVENT 19
   LAST STAND
   ========================================================= */

function event19() {

  const trials = [

    ["Choose the heart.", "❤️"],

    ["Choose the number three.", "3"],

    ["Choose the dolphin.", "🐬"],

    ["Choose the rose.", "🌹"],

    ["Choose the star.", "⭐"],

    ["Choose the heart.", "❤️"]

  ];

  let index = 0;
  let lives = 3;

  function show() {

    if (
      index >=
      trials.length
    ) {

      finishEvent(
        60,
        true,
        "💀 LAST STAND SURVIVED",
        "You survived every trial and reached the final carriage."
      );

      return;
    }

    const trial =
      trials[index];

    document.getElementById("app").innerHTML = `
      ${topBar()}

      <div class="panel center">

        <div class="badge">
          Event 19 of 20
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
            <strong>${index + 1}/6</strong>
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

          <button
            class="choice"
            onclick="lastStand('❤️')"
          >
            ❤️
          </button>

          <button
            class="choice"
            onclick="lastStand('3')"
          >
            3
          </button>

          <button
            class="choice"
            onclick="lastStand('🐬')"
          >
            🐬
          </button>

          <button
            class="choice"
            onclick="lastStand('🌹')"
          >
            🌹
          </button>

          <button
            class="choice"
            onclick="lastStand('⭐')"
          >
            ⭐
          </button>

        </div>

      </div>
    `;
  }

  window.lastStand =
    function(answer) {

      if (
        answer ===
        trials[index][1]
      ) {

        addPoints(12);

      } else {

        lives--;
      }

      index++;

      if (
        lives <= 0
      ) {

        finishEvent(
          10,
          false,
          "💔 LAST STAND FAILED",
          "You lost all three lives before reaching the end."
        );

        return;
      }

      show();
    };

  show();
}

/* =========================================================
   EVENT 20
   FINAL CHALLENGE
   ========================================================= */

let finalQuestion = 0;
let finalCorrect = 0;

function event20() {

  finalQuestion = 0;
  finalCorrect = 0;

  showFinalQuestion();
}

function showFinalQuestion() {

  if (
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

  const progress =
    (
      finalQuestion /
      FINAL_QUIZ.length
    ) * 100;

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel">

      <div class="badge">
        Event 20 of 20 • FINAL CHALLENGE
      </div>

      <h2>
        👑 Know Liliana
      </h2>

      <div class="progress">

        <div
          class="progress-bar"
          style="width:${progress}%"
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
        ${item[0]}
      </h3>

      <div class="choices">

        ${item[1].map(
          (answer, index) => `
            <button
              class="choice"
              onclick="finalAnswer(${index})"
            >
              ${answer}
            </button>
          `
        ).join("")}

      </div>

      <div class="notice center">
        💗 ${finalCorrect} correct so far
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

    const buttons =
      document.querySelectorAll(
        ".choice"
      );

    buttons.forEach(
      button => {
        button.disabled = true;
      }
    );

    if (
      index === item[2]
    ) {

      finalCorrect++;

      addPoints(10);

      buttons[index]
        .classList.add(
          "correct"
        );

    } else {

      buttons[index]
        .classList.add(
          "wrong"
        );

      buttons[item[2]]
        .classList.add(
          "correct"
        );
    }

    finalQuestion++;

    setTimeout(
      showFinalQuestion,
      500
    );
  };

/* =========================================================
   FINAL WRITTEN CHALLENGE
   ========================================================= */

function finalWrittenChallenge() {

  document.getElementById("app").innerHTML = `
    ${topBar()}

    <div class="panel center">

      <div class="badge">
        Final Question
      </div>

      <h2>
        💌 One Last Thing
      </h2>

      <p>
        You've survived nineteen events and answered
        fifty questions.
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

    if (
      message.length < 10
    ) {

      alert(
        "You need to give Liliana a little more than that. ❤️"
      );

      return;
    }

    addPoints(50);

    state.finished = true;

    saveGame();

    finalResult();
  };

/* =========================================================
   FINAL RESULT
   ========================================================= */

function finalResult() {

  let title;
  let message;

  if (
    state.score >= 500
  ) {

    title =
      "🏆 LULU EXPRESS CHAMPION";

    message =
      "You didn't just reach the final carriage. You owned the entire journey.";

  } else if (
    state.score >= 350
  ) {

    title =
      "🥇 SERIOUS CONTENDER";

    message =
      "You made it dangerously close to the top.";

  } else if (
    state.score >= 200
  ) {

    title =
      "🥈 STRONG ADMIRER";

    message =
      "You survived the journey and reached the final destination.";

  } else {

    title =
      "💗 LULU EXPRESS SURVIVOR";

    message =
      "You survived the Lulu Express. That deserves respect.";
  }

  document.getElementById("app").innerHTML = `
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

      <div class="trophy">
        📞
      </div>

      <h2>
        Your Prize
      </h2>

      <h2
        style="
          color:#f3ce6b;
        "
      >
        A PRIVATE CALL WITH LILIANA
      </h2>

      <p>
        You made it through every challenge
        and reached the final destination.
      </p>

      <div class="notice">

        🚂💗

        <strong>
          The Lulu Express has reached its final destination.
        </strong>

        <br><br>

        Congratulations, Admirer.

      </div>

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
   START
   ========================================================= */

home();

</script>

</body>
</html>

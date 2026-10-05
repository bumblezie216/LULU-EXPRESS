<html lang="en">
<head>
<meta charset="UTF-8">

<meta
  name="viewport"
  content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover"
>

<meta name="theme-color" content="#160b14">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">

<title>Lulu Express 🚂💗</title>

<style>
/* =========================================================
   LULU EXPRESS
   FULL MOBILE-FIRST VERSION
   ========================================================= */

* {
  box-sizing: border-box;
  -webkit-tap-highlight-color: transparent;
  -webkit-user-select: none;
  user-select: none;
}

html,
body {
  width: 100%;
  min-height: 100%;
  margin: 0;
  padding: 0;
  background: #12070f;
  color: #fff;
  font-family:
    -apple-system,
    BlinkMacSystemFont,
    "Segoe UI",
    Roboto,
    Helvetica,
    Arial,
    sans-serif;
  overflow-x: hidden;
}

body {
  min-height: 100dvh;
  overscroll-behavior: none;
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

input {
  -webkit-user-select: text;
  user-select: text;
}

/* Prevent accidental browser gestures */
body,
button,
.screen,
.game-area,
canvas {
  touch-action: manipulation;
}

canvas {
  display: block;
  touch-action: none;
}

/* =========================================================
   VARIABLES
   ========================================================= */

:root {
  --bg: #12070f;
  --bg2: #1c0b17;
  --panel: #28111f;
  --panel2: #351526;
  --pink: #f49bc5;
  --pink2: #ffb9d8;
  --pink3: #d86c9e;
  --darkpink: #8e3c68;
  --white: #fff7fb;
  --muted: #d8b8ca;
  --green: #8ee5b1;
  --red: #ff8099;
  --gold: #ffd76a;
  --blue: #9bdcff;
  --purple: #c7a5ff;
}

/* =========================================================
   SCREEN SYSTEM
   ========================================================= */

#app {
  width: 100%;
  min-height: 100dvh;
}

.screen {
  display: none;
  width: 100%;
  min-height: 100dvh;
  padding:
    max(18px, env(safe-area-inset-top))
    14px
    max(22px, env(safe-area-inset-bottom))
    14px;

  animation: screenIn .28s ease;
}

.screen.active {
  display: flex;
  flex-direction: column;
}

@keyframes screenIn {
  from {
    opacity: 0;
    transform: translateY(8px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* =========================================================
   BACKGROUND
   ========================================================= */

.screen::before {
  content: "";
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: -2;

  background:
    radial-gradient(circle at 15% 15%, rgba(255,150,200,.13), transparent 28%),
    radial-gradient(circle at 85% 20%, rgba(130,80,180,.12), transparent 30%),
    radial-gradient(circle at 50% 100%, rgba(255,90,160,.08), transparent 35%),
    linear-gradient(160deg, #10060e, #1a0915 45%, #10060e);
}

.stars-bg {
  position: fixed;
  inset: 0;
  pointer-events: none;
  overflow: hidden;
  z-index: -1;
}

.bg-star {
  position: absolute;
  color: rgba(255,255,255,.7);
  animation: twinkle 2.5s infinite alternate;
}

@keyframes twinkle {
  from {
    opacity: .15;
    transform: scale(.75);
  }

  to {
    opacity: .9;
    transform: scale(1.15);
  }
}

/* =========================================================
   COMMON
   ========================================================= */

.center {
  align-items: center;
  justify-content: center;
}

.container {
  width: 100%;
  max-width: 720px;
  margin: 0 auto;
}

.card {
  width: 100%;
  background:
    linear-gradient(
      145deg,
      rgba(53,21,38,.97),
      rgba(30,12,24,.97)
    );
  border: 1px solid rgba(255,185,216,.16);
  border-radius: 25px;
  padding: 20px;
  box-shadow:
    0 20px 60px rgba(0,0,0,.35),
    inset 0 1px rgba(255,255,255,.05);
}

h1,
h2,
h3,
p {
  margin-top: 0;
}

h1 {
  font-size: clamp(2.2rem, 9vw, 4.2rem);
  line-height: .95;
  margin-bottom: 12px;
}

h2 {
  font-size: clamp(1.6rem, 6vw, 2.3rem);
  margin-bottom: 8px;
}

h3 {
  margin-bottom: 8px;
}

.subtitle {
  color: var(--muted);
  line-height: 1.55;
}

.small {
  font-size: .86rem;
  color: var(--muted);
}

.big-number {
  font-size: 3rem;
  font-weight: 900;
  color: var(--pink2);
}

.heart {
  color: var(--pink2);
}

.logo {
  font-size: 4rem;
  margin-bottom: 5px;
  filter: drop-shadow(0 8px 20px rgba(255,120,180,.2));
}

/* =========================================================
   BUTTONS
   ========================================================= */

.btn {
  width: 100%;
  min-height: 54px;
  padding: 13px 18px;
  margin-top: 10px;

  border-radius: 16px;

  background:
    linear-gradient(135deg, #ef8fba, #d96c9f);

  color: #240d1b;
  font-weight: 900;
  font-size: 1rem;

  box-shadow:
    0 8px 20px rgba(215,91,145,.22),
    inset 0 1px rgba(255,255,255,.45);

  transition:
    transform .12s ease,
    filter .12s ease;
}

.btn:active {
  transform: scale(.97);
}

.btn.secondary {
  background: #432033;
  color: var(--white);
  border: 1px solid rgba(255,185,216,.14);
}

.btn.green {
  background: linear-gradient(135deg, #a7efc4, #69ce9a);
}

.btn.gold {
  background: linear-gradient(135deg, #ffe89a, #eec34e);
}

.btn.blue {
  background: linear-gradient(135deg, #b6e9ff, #72c8ef);
}

.btn.small-btn {
  min-height: 44px;
  padding: 9px 13px;
  margin-top: 5px;
  font-size: .88rem;
}

/* =========================================================
   START SCREEN
   ========================================================= */

.start-wrap {
  width: 100%;
  max-width: 620px;
  margin: auto;
  text-align: center;
}

.train {
  font-size: 5rem;
  animation: trainFloat 2.5s ease-in-out infinite;
}

@keyframes trainFloat {
  0%,100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-8px);
  }
}

.name-input {
  width: 100%;
  height: 55px;
  margin: 14px 0 4px;
  padding: 0 17px;

  border-radius: 15px;
  border: 1px solid rgba(255,185,216,.2);

  background: #160914;
  color: white;

  text-align: center;
  outline: none;
}

.name-input:focus {
  border-color: var(--pink);
  box-shadow: 0 0 0 3px rgba(244,155,197,.1);
}

/* =========================================================
   JOURNEY
   ========================================================= */

.journey-header {
  width: 100%;
  max-width: 760px;
  margin: 0 auto 14px;
}

.journey-header h2 {
  margin-bottom: 4px;
}

.score-pill {
  display: inline-flex;
  align-items: center;
  gap: 7px;

  padding: 8px 12px;
  border-radius: 999px;

  background: rgba(244,155,197,.09);
  border: 1px solid rgba(244,155,197,.13);

  color: var(--pink2);
  font-weight: 800;
}

.level-list {
  width: 100%;
  max-width: 760px;
  margin: 0 auto;
  display: grid;
  gap: 9px;
}

.level-item {
  display: grid;
  grid-template-columns: 48px 1fr auto;
  gap: 12px;
  align-items: center;

  min-height: 70px;
  padding: 10px 12px;

  border-radius: 18px;
  border: 1px solid rgba(255,255,255,.06);

  background: rgba(45,18,34,.88);
}

.level-number {
  width: 42px;
  height: 42px;

  display: grid;
  place-items: center;

  border-radius: 50%;

  background: #4b2439;
  color: var(--pink2);
  font-weight: 900;
}

.level-item.unlocked .level-number {
  background: linear-gradient(135deg,#f39bc5,#d8679c);
  color: #2a0d1c;
}

.level-item.complete .level-number {
  background: linear-gradient(135deg,#9ae7ba,#61c791);
  color: #092015;
}

.level-info strong {
  display: block;
}

.level-info span {
  display: block;
  margin-top: 3px;
  font-size: .78rem;
  color: var(--muted);
}

.level-status {
  font-size: 1.3rem;
}

/* =========================================================
   GAME HEADER
   ========================================================= */

.game-shell {
  width: 100%;
  max-width: 820px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  flex: 1;
}

.game-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 8px;
  margin-bottom: 10px;
}

.game-title {
  min-width: 0;
}

.game-title strong {
  display: block;
  font-size: 1.15rem;
}

.game-title span {
  font-size: .76rem;
  color: var(--muted);
}

.game-stats {
  display: flex;
  gap: 7px;
  flex-wrap: wrap;
  justify-content: flex-end;
}

.stat {
  padding: 7px 9px;
  border-radius: 10px;
  background: #2a1421;
  color: var(--pink2);
  font-weight: 800;
  font-size: .76rem;
}

.game-area {
  flex: 1;
  width: 100%;
  position: relative;
  overflow: hidden;

  border-radius: 24px;
  background:
    linear-gradient(145deg,#241020,#160a13);

  border: 1px solid rgba(255,185,216,.13);

  min-height: min(68dvh, 650px);
}

.game-instructions {
  margin-bottom: 10px;
  color: var(--muted);
  font-size: .88rem;
  line-height: 1.4;
}

.game-footer {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 9px;
  margin-top: 10px;
}

.game-footer .btn {
  margin-top: 0;
}

/* =========================================================
   GENERIC GAME ELEMENTS
   ========================================================= */

.choice-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}

.choice {
  min-height: 58px;
  padding: 11px;

  border-radius: 15px;
  background: #3a1a2c;
  border: 1px solid rgba(255,255,255,.07);

  color: white;
  font-weight: 800;

  transition: transform .12s, background .12s;
}

.choice:active {
  transform: scale(.96);
}

.choice.correct {
  background: #225a3d;
  border-color: #71dca3;
}

.choice.wrong {
  background: #672a3a;
  border-color: #ff7d95;
}

.feedback {
  min-height: 27px;
  margin-top: 10px;
  text-align: center;
  font-weight: 800;
}

.good {
  color: var(--green);
}

.bad {
  color: var(--red);
}

.gold-text {
  color: var(--gold);
}

/* =========================================================
   HEART CATCHER
   ========================================================= */

#heartCanvas {
  width: 100%;
  height: 100%;
  min-height: 500px;
}

.mobile-controls {
  position: absolute;
  bottom: 12px;
  left: 12px;
  right: 12px;

  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}

.move-btn {
  min-height: 62px;
  border-radius: 18px;

  background: rgba(255,185,216,.16);
  border: 1px solid rgba(255,255,255,.12);

  color: white;
  font-size: 1.8rem;
  font-weight: 900;

  backdrop-filter: blur(5px);
}

.move-btn:active {
  background: rgba(255,185,216,.3);
}

/* =========================================================
   LOVE MATCH
   ========================================================= */

.match-board {
  display: grid;
  grid-template-columns: repeat(4,1fr);
  gap: 8px;
  padding: 12px;
}

.match-tile {
  aspect-ratio: 1;
  border-radius: 16px;
  background: #3c1a2d;
  display: grid;
  place-items: center;
  font-size: 1.7rem;
  border: 1px solid rgba(255,255,255,.06);
}

.match-tile.selected {
  outline: 3px solid var(--pink);
  transform: scale(.95);
}

.match-tile.matched {
  background: #5a2743;
}

/* =========================================================
   MEMORY
   ========================================================= */

.memory-grid {
  display: grid;
  grid-template-columns: repeat(4,1fr);
  gap: 9px;
  padding: 12px;
}

.memory-card {
  aspect-ratio: .82;
  border-radius: 15px;
  perspective: 600px;
}

.memory-inner {
  width: 100%;
  height: 100%;
  position: relative;
  transition: transform .35s;
  transform-style: preserve-3d;
}

.memory-card.flipped .memory-inner,
.memory-card.matched .memory-inner {
  transform: rotateY(180deg);
}

.memory-front,
.memory-back {
  position: absolute;
  inset: 0;
  display: grid;
  place-items: center;

  border-radius: 15px;
  backface-visibility: hidden;
}

.memory-front {
  background: linear-gradient(135deg,#7e3c60,#482039);
  color: var(--pink2);
  font-size: 1.7rem;
}

.memory-back {
  background: #f7d8e7;
  color: #351327;
  transform: rotateY(180deg);
  font-size: 1.8rem;
}

/* =========================================================
   WORD FIND
   ========================================================= */

.wordfind-wrap {
  padding: 10px;
}

.word-list {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-bottom: 10px;
}

.word-tag {
  padding: 6px 9px;
  border-radius: 999px;
  background: #3b1b2d;
  font-size: .75rem;
}

.word-tag.found {
  background: #23583d;
  color: #b9ffd2;
  text-decoration: line-through;
}

.word-grid {
  display: grid;
  grid-template-columns: repeat(8,1fr);
  gap: 3px;
}

.word-cell {
  aspect-ratio: 1;
  display: grid;
  place-items: center;

  background: #311528;
  border-radius: 5px;

  font-size: clamp(.65rem, 3.2vw, 1rem);
  font-weight: 900;
}

.word-cell.selected {
  background: #a95a80;
}

.word-cell.found {
  background: #35654c;
  color: white;
}

/* =========================================================
   BROKEN HEART
   ========================================================= */

.repair-heart {
  position: relative;
  width: min(72vw,300px);
  aspect-ratio: 1;
  margin: 35px auto;
  display: grid;
  place-items: center;
}

.big-heart {
  font-size: min(45vw,190px);
  filter: drop-shadow(0 15px 30px rgba(255,70,140,.25));
}

.crack {
  position: absolute;
  color: #311322;
  font-size: 3rem;
  font-weight: 900;
  transform: rotate(20deg);
}

.repair-piece {
  position: absolute;
  min-width: 60px;
  min-height: 45px;
  border-radius: 13px;
  background: #f2a4c8;
  color: #391329;
  font-weight: 900;
  padding: 9px;
}

/* =========================================================
   WHEEL
   ========================================================= */

.wheel-wrap {
  display: grid;
  place-items: center;
  padding: 25px 15px;
}

.wheel {
  width: min(72vw,310px);
  aspect-ratio: 1;
  border-radius: 50%;

  background:
    conic-gradient(
      #f5a5c9 0 45deg,
      #52243c 45deg 90deg,
      #e783b0 90deg 135deg,
      #3e1c30 135deg 180deg,
      #f5a5c9 180deg 225deg,
      #52243c 225deg 270deg,
      #e783b0 270deg 315deg,
      #3e1c30 315deg 360deg
    );

  border: 9px solid #f5d2e2;
  box-shadow: 0 15px 40px rgba(0,0,0,.4);

  transition: transform 3s cubic-bezier(.15,.75,.12,1);
  position: relative;
}

.wheel::after {
  content: "💗";
  position: absolute;
  inset: 50%;
  transform: translate(-50%,-50%);

  width: 58px;
  height: 58px;
  border-radius: 50%;

  display: grid;
  place-items: center;

  background: #24101d;
  font-size: 1.6rem;
}

.wheel-pointer {
  font-size: 2rem;
  margin-bottom: -8px;
  z-index: 2;
}

/* =========================================================
   PAIRS
   ========================================================= */

.pair-grid {
  display: grid;
  grid-template-columns: repeat(3,1fr);
  gap: 9px;
  padding: 12px;
}

.pair-card {
  aspect-ratio: 1;
  border-radius: 16px;
  display: grid;
  place-items: center;
  background: #38192b;
  font-size: 1.7rem;
}

/* =========================================================
   STAR CATCH
   ========================================================= */

.star-field {
  position: relative;
  width: 100%;
  height: 100%;
  min-height: 500px;
  overflow: hidden;
}

.tap-star {
  position: absolute;
  width: 60px;
  height: 60px;

  display: grid;
  place-items: center;

  border-radius: 50%;

  background: rgba(255,215,106,.13);
  border: 1px solid rgba(255,215,106,.4);

  font-size: 2rem;

  animation: starPulse .7s infinite alternate;
}

@keyframes starPulse {
  to {
    transform: scale(1.14);
  }
}

/* =========================================================
   LOVE LETTERS
   ========================================================= */

.letter-slots {
  display: grid;
  grid-template-columns: repeat(5,1fr);
  gap: 6px;
  margin: 15px 0;
}

.letter-slot {
  height: 48px;
  border-bottom: 2px solid var(--pink);
  display: grid;
  place-items: center;
  font-weight: 900;
}

.letter-bank {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 8px;
}

.letter-button {
  width: 45px;
  height: 45px;
  border-radius: 12px;
  background: #442037;
  color: white;
  font-weight: 900;
}

/* =========================================================
   REACTION
   ========================================================= */

.reaction-zone {
  min-height: 500px;
  display: grid;
  place-items: center;
  position: relative;
}

.reaction-target {
  width: min(45vw,190px);
  aspect-ratio: 1;
  border-radius: 50%;
  display: grid;
  place-items: center;
  font-size: 2rem;
  font-weight: 900;
  background: #542237;
  border: 7px solid #7e3655;
}

.reaction-target.go {
  background: #4eae78;
  border-color: #a6f1c2;
  color: #092015;
}

/* =========================================================
   QUIZ
   ========================================================= */

.quiz-box {
  padding: 15px;
}

.quiz-progress {
  height: 8px;
  border-radius: 99px;
  overflow: hidden;
  background: #432033;
  margin-bottom: 14px;
}

.quiz-progress > div {
  height: 100%;
  background: linear-gradient(90deg,#f7a6ca,#d9669e);
  width: 0%;
  transition: width .2s;
}

.timer-wrap {
  display: flex;
  justify-content: center;
  margin: 12px 0;
}

.timer-circle {
  width: 75px;
  height: 75px;
  border-radius: 50%;

  display: grid;
  place-items: center;

  background: #3d1a2c;
  border: 5px solid var(--pink);

  font-size: 1.5rem;
  font-weight: 900;
}

/* =========================================================
   COLOUR MEMORY
   ========================================================= */

.colour-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  max-width: 420px;
  margin: 25px auto;
}

.colour-pad {
  aspect-ratio: 1;
  border-radius: 25px;
  opacity: .72;
  transition: transform .1s, opacity .1s;
}

.colour-pad.active {
  opacity: 1;
  transform: scale(.92);
  filter: brightness(1.7);
}

.pad-pink {
  background: #e88bb4;
}

.pad-purple {
  background: #9569c9;
}

.pad-blue {
  background: #66add7;
}

.pad-green {
  background: #66bd89;
}

/* =========================================================
   LUCKY NUMBERS
   ========================================================= */

.number-board {
  display: grid;
  grid-template-columns: repeat(5,1fr);
  gap: 7px;
  margin: 15px 0;
}

.number-tile {
  aspect-ratio: 1;
  border-radius: 13px;
  background: #3a1a2d;
  color: white;
  font-weight: 900;
  font-size: 1rem;
}

/* =========================================================
   GIN RUMMY
   ========================================================= */

.hand {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 7px;
  padding: 15px 4px;
}

.playing-card {
  width: 52px;
  height: 74px;
  border-radius: 8px;
  background: #fff3f8;
  color: #351020;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-weight: 900;
  box-shadow: 0 5px 10px rgba(0,0,0,.2);
}

.playing-card.selected {
  transform: translateY(-10px);
  box-shadow: 0 12px 18px rgba(0,0,0,.3);
  outline: 3px solid var(--pink);
}

.rummy-table {
  min-height: 130px;
  display: grid;
  place-items: center;
  border-radius: 20px;
  background: #16482f;
  border: 7px solid #6c4528;
}

/* =========================================================
   SLOTS
   ========================================================= */

.slot-machine {
  padding: 20px;
  text-align: center;
}

.reels {
  display: grid;
  grid-template-columns: repeat(3,1fr);
  gap: 9px;
  max-width: 480px;
  margin: 20px auto;
}

.reel {
  height: 100px;
  border-radius: 18px;
  display: grid;
  place-items: center;
  background: #f8dce9;
  color: #351224;
  font-size: 3rem;
  border: 5px solid #7e4661;
  box-shadow: inset 0 0 20px rgba(0,0,0,.15);
}

/* =========================================================
   DOLPHIN DIVE
   ========================================================= */

.dive-field {
  position: relative;
  height: 100%;
  min-height: 520px;
  overflow: hidden;

  background:
    linear-gradient(
      #6ac4e9 0%,
      #267aa5 35%,
      #0c4564 100%
    );
}

.dive-bubble {
  position: absolute;
  border-radius: 50%;
  border: 2px solid rgba(255,255,255,.35);
}

.dolphin {
  position: absolute;
  left: 15%;
  width: 75px;
  height: 55px;
  font-size: 3rem;
  transition: top .1s linear;
  z-index: 3;
}

.dive-object {
  position: absolute;
  right: -80px;
  width: 65px;
  height: 80px;
  display: grid;
  place-items: center;
  font-size: 2.5rem;
}

.pearl {
  position: absolute;
  right: -50px;
  font-size: 2rem;
}

/* =========================================================
   LULU TRIVIA
   ========================================================= */

.trivia-image {
  text-align: center;
  font-size: 4rem;
  margin: 10px;
}

/* =========================================================
   MILLION SLOT
   ========================================================= */

.jackpot {
  text-align: center;
  padding: 14px;
  border-radius: 20px;
  background:
    linear-gradient(135deg,#49223b,#24101d);
  border: 1px solid rgba(255,215,106,.2);
}

.jackpot-number {
  font-size: clamp(2.3rem,9vw,4rem);
  font-weight: 1000;
  color: var(--gold);
}

/* =========================================================
   PUZZLE
   ========================================================= */

.puzzle-grid {
  width: min(90vw,420px);
  margin: 20px auto;
  display: grid;
  grid-template-columns: repeat(3,1fr);
  gap: 5px;
  padding: 5px;
  background: #6b3854;
  border-radius: 17px;
}

.puzzle-tile {
  aspect-ratio: 1;
  border-radius: 10px;
  background: linear-gradient(135deg,#f5afd0,#d66c9e);
  color: #361226;
  display: grid;
  place-items: center;
  font-size: 1.5rem;
  font-weight: 1000;
}

.puzzle-tile.empty {
  background: #26101d;
}

/* =========================================================
   FINAL MEMORY
   ========================================================= */

.sequence-display {
  min-height: 180px;
  display: grid;
  place-items: center;
  text-align: center;
  font-size: 4rem;
}

.sequence-buttons {
  display: grid;
  grid-template-columns: repeat(4,1fr);
  gap: 9px;
}

.sequence-button {
  aspect-ratio: 1;
  border-radius: 17px;
  font-size: 1.8rem;
  background: #402039;
}

/* =========================================================
   DERBY
   ========================================================= */

.derby-track {
  position: relative;
  min-height: 500px;
  padding: 25px 12px;

  background:
    linear-gradient(
      #8acb78 0 24%,
      #75b765 24% 26%,
      #8acb78 26% 49%,
      #75b765 49% 51%,
      #8acb78 51% 74%,
      #75b765 74% 76%,
      #8acb78 76% 100%
    );
  overflow: hidden;
}

.race-lane {
  height: 105px;
  position: relative;
  border-bottom: 2px dashed rgba(255,255,255,.35);
}

.race-label {
  position: absolute;
  left: 5px;
  top: 4px;
  font-weight: 900;
  font-size: .75rem;
}

.horse {
  position: absolute;
  left: 4%;
  top: 25px;
  font-size: 3rem;
  transition: left .35s ease;
}

.finish-line {
  position: absolute;
  right: 30px;
  top: 0;
  bottom: 0;
  width: 12px;
  background:
    repeating-linear-gradient(
      45deg,
      #fff 0 8px,
      #222 8px 16px
    );
}

/* =========================================================
   RESULT
   ========================================================= */

.result-wrap {
  width: 100%;
  max-width: 620px;
  margin: auto;
  text-align: center;
}

.result-icon {
  font-size: 5rem;
  margin-bottom: 10px;
}

.reward-card {
  margin-top: 16px;
  padding: 18px;
  border-radius: 20px;
  background: linear-gradient(135deg,#3b2030,#24101d);
  border: 1px solid rgba(255,215,106,.2);
}

/* =========================================================
   FINAL
   ========================================================= */

.final-wrap {
  width: 100%;
  max-width: 680px;
  margin: auto;
  text-align: center;
}

.final-heart {
  font-size: 6rem;
  animation: finalBeat 1.2s infinite;
}

@keyframes finalBeat {
  0%,100% { transform: scale(1); }
  50% { transform: scale(1.12); }
}

.reward-unlocked {
  padding: 20px;
  border-radius: 22px;
  background: linear-gradient(135deg,#573d20,#35230f);
  border: 1px solid rgba(255,215,106,.45);
}

.reward-locked {
  padding: 20px;
  border-radius: 22px;
  background: #29121f;
  border: 1px solid rgba(255,255,255,.08);
}

/* =========================================================
   RESPONSIVE
   ========================================================= */

@media (max-width: 430px) {

  .screen {
    padding-left: 10px;
    padding-right: 10px;
  }

  .card {
    padding: 15px;
    border-radius: 20px;
  }

  .memory-grid {
    gap: 6px;
    padding: 7px;
  }

  .pair-grid {
    gap: 6px;
    padding: 8px;
  }

  .playing-card {
    width: 45px;
    height: 66px;
  }

  .choice-grid {
    gap: 7px;
  }

  .choice {
    min-height: 54px;
    padding: 9px;
    font-size: .86rem;
  }

  .game-area {
    min-height: 62dvh;
  }
}

@media (max-height: 680px) {

  .game-area {
    min-height: 480px;
  }

  .card {
    padding: 14px;
  }

  .game-top {
    margin-bottom: 6px;
  }
}
</style>
</head>

<body>

<div class="stars-bg" id="backgroundStars"></div>

<div id="app">

  <!-- =====================================================
       START
       ===================================================== -->

  <section id="startScreen" class="screen active center">

    <div class="start-wrap">

      <div class="train">🚂💗</div>

      <h1>
        Lulu Express
      </h1>

      <p class="subtitle">
        A little journey made especially for Lulu.
        <br>
        21 games. One journey. One very special person.
      </p>

      <div class="card">

        <h2>All aboard 💗</h2>

        <p class="subtitle">
          Enter your name to begin your journey.
          You have to pass each level before the next one unlocks.
        </p>

        <input
          id="playerName"
          class="name-input"
          maxlength="24"
          autocomplete="off"
          placeholder="Your name"
        >

        <button
          class="btn"
          id="startBtn"
        >
          Start the Journey 🚂
        </button>

        <button
          class="btn secondary"
          id="howBtn"
        >
          How to Play
        </button>

      </div>

    </div>

  </section>


  <!-- =====================================================
       HOW TO PLAY
       ===================================================== -->

  <section id="howScreen" class="screen center">

    <div class="container">

      <div class="card">

        <h2>How to Play 💗</h2>

        <p class="subtitle">
          Welcome aboard Lulu Express.
        </p>

        <p>
          🚂 Enter your name and start at Level 1.
        </p>

        <p>
          🔐 Every level must be passed before the next one opens.
        </p>

        <p>
          🎮 Each game gets its own screen so the controls stay easy
          to use on a phone.
        </p>

        <p>
          💗 Your score carries through the whole journey.
        </p>

        <p>
          🎵 The music button belongs to the current game and disappears
          when you leave that game.
        </p>

        <p>
          🔄 You can reset the entire journey at any time.
        </p>

        <p>
          ⭐ Some games award bonus points for doing especially well.
        </p>

        <button class="btn" id="backStartBtn">
          Back
        </button>

      </div>

    </div>

  </section>


  <!-- =====================================================
       JOURNEY
       ===================================================== -->

  <section id="journeyScreen" class="screen">

    <div class="journey-header">

      <h2>
        Lulu Express 🚂
      </h2>

      <p class="subtitle" id="journeyGreeting"></p>

      <div class="score-pill">
        ⭐ Score:
        <span id="journeyScore">0</span>
      </div>

    </div>

    <div
      id="levelList"
      class="level-list"
    ></div>

    <div class="container" style="margin-top:12px">

      <button
        class="btn secondary"
        id="resetJourneyBtn"
      >
        Reset Journey
      </button>

    </div>

  </section>


  <!-- =====================================================
       GAME
       ===================================================== -->

  <section id="gameScreen" class="screen">

    <div class="game-shell">

      <div class="game-top">

        <div class="game-title">
          <strong id="gameTitle"></strong>
          <span id="gameSubtitle"></span>
        </div>

        <div class="game-stats">

          <div class="stat">
            ⭐ <span id="gameScore">0</span>
          </div>

          <div class="stat">
            🪙 <span id="gameTokens">0</span>
          </div>

          <button
            id="musicBtn"
            class="btn small-btn secondary"
            style="margin:0"
          >
            🎵
          </button>

        </div>

      </div>

      <div
        id="gameArea"
        class="game-area"
      ></div>

    </div>

  </section>


  <!-- =====================================================
       RESULT
       ===================================================== -->

  <section id="resultScreen" class="screen center">

    <div class="result-wrap">

      <div
        id="resultIcon"
        class="result-icon"
      >
        💗
      </div>

      <h1 id="resultTitle">
        Level Complete!
      </h1>

      <p
        id="resultMessage"
        class="subtitle"
      ></p>

      <div class="card">

        <p>
          Level score
        </p>

        <div
          id="levelScore"
          class="big-number"
        >
          +0
        </div>

        <p>
          Total score:
          <strong id="resultTotal">0</strong>
        </p>

      </div>

      <button
        id="resultBtn"
        class="btn"
      >
        Continue
      </button>

    </div>

  </section>


  <!-- =====================================================
       FINAL
       ===================================================== -->

  <section id="finalScreen" class="screen center">

    <div class="final-wrap">

      <div class="final-heart">
        💗
      </div>

      <h1>
        Journey Complete
      </h1>

      <p
        id="finalGreeting"
        class="subtitle"
      ></p>

      <div class="card">

        <p>
          Final score
        </p>

        <div
          id="finalScore"
          class="big-number"
        >
          0
        </div>

        <p>
          You made it all the way through Lulu Express.
        </p>

      </div>

      <div
        id="rewardBox"
        style="margin-top:14px"
      ></div>

      <button
        class="btn secondary"
        id="finalResetBtn"
      >
        Start Again
      </button>

    </div>

  </section>

</div>


<script>
/* =========================================================
   LULU EXPRESS
   JAVASCRIPT
   ========================================================= */

"use strict";

/* =========================================================
   GLOBAL STATE
   ========================================================= */

const state = {
  playerName: "",
  score: 0,
  tokens: 0,

  currentLevel: 0,
  highestUnlocked: 0,
  completed: [],

  levelScore: 0,

  musicOn: false,

  gameCleanup: null
};


/* =========================================================
   LEVELS
   ========================================================= */

const LEVELS = [
  {
    name: "Heart Catcher",
    icon: "💗",
    description: "Catch the falling hearts.",
    play: gameHeartCatcher
  },

  {
    name: "Love Match",
    icon: "💕",
    description: "Create matching groups of three.",
    play: gameLoveMatch
  },

  {
    name: "Memory Flip",
    icon: "🃏",
    description: "Find all the matching pairs.",
    play: gameMemoryFlip
  },

  {
    name: "Word Find",
    icon: "🔎",
    description: "Find words hidden in the grid.",
    play: gameWordFind
  },

  {
    name: "Broken Heart",
    icon: "💔",
    description: "Repair the broken heart.",
    play: gameBrokenHeart
  },

  {
    name: "Lucky Wheel",
    icon: "🎡",
    description: "Spin for your reward.",
    play: gameLuckyWheel
  },

  {
    name: "Perfect Pairs",
    icon: "🩷",
    description: "Match every pair.",
    play: gamePerfectPairs
  },

  {
    name: "Star Catch",
    icon: "⭐",
    description: "Catch the stars before they disappear.",
    play: gameStarCatch
  },

  {
    name: "Love Letters",
    icon: "💌",
    description: "Build the hidden message.",
    play: gameLoveLetters
  },

  {
    name: "Reaction Rush",
    icon: "⚡",
    description: "React at exactly the right moment.",
    play: gameReactionRush
  },

  {
    name: "Pressure Quiz",
    icon: "⏱️",
    description: "Answer before the timer reaches zero.",
    play: gamePressureQuiz
  },

  {
    name: "Colour Memory",
    icon: "🎨",
    description: "Remember the glowing sequence.",
    play: gameColourMemory
  },

  {
    name: "Lucky Numbers",
    icon: "🔢",
    description: "Find the lucky number.",
    play: gameLuckyNumbers
  },

  {
    name: "Gin Rummy",
    icon: "🃏",
    description: "Build a winning meld.",
    play: gameGinRummy
  },

  {
    name: "Buffalo Slots",
    icon: "🎰",
    description: "Spin the reels and win tokens.",
    play: gameBuffaloSlots
  },

  {
    name: "Dolphin Dive",
    icon: "🐬",
    description: "Dive, collect pearls and avoid obstacles.",
    play: gameDolphinDive
  },

  {
    name: "Lulu Trivia",
    icon: "💗",
    description: "How well do you know Lulu?",
    play: gameLuluTrivia
  },

  {
    name: "Million Token Slot",
    icon: "💰",
    description: "Chase the one-million-token jackpot.",
    play: gameMillionSlot
  },

  {
    name: "Lulu Puzzle",
    icon: "🧩",
    description: "Solve the little sliding puzzle.",
    play: gameLuluPuzzle
  },

  {
    name: "Final Memory",
    icon: "🧠",
    description: "Remember the final sequence.",
    play: gameFinalMemory
  },

  {
    name: "Final Quiz",
    icon: "💗",
    description: "50 questions about Liliana.",
    play: gameFinalQuiz
  }
];


/* =========================================================
   DOM
   ========================================================= */

const $ = id => document.getElementById(id);

const screens = {
  start: $("startScreen"),
  how: $("howScreen"),
  journey: $("journeyScreen"),
  game: $("gameScreen"),
  result: $("resultScreen"),
  final: $("finalScreen")
};


/* =========================================================
   BACKGROUND STARS
   ========================================================= */

function makeBackgroundStars() {

  const container = $("backgroundStars");

  for (let i = 0; i < 55; i++) {

    const star = document.createElement("span");

    star.className = "bg-star";
    star.textContent = Math.random() > .5 ? "✦" : "·";

    star.style.left = `${Math.random() * 100}%`;
    star.style.top = `${Math.random() * 100}%`;
    star.style.fontSize = `${6 + Math.random() * 10}px`;
    star.style.animationDelay = `${Math.random() * 3}s`;

    container.appendChild(star);
  }
}

makeBackgroundStars();


/* =========================================================
   UTILITY
   ========================================================= */

function shuffle(array) {

  const a = [...array];

  for (let i = a.length - 1; i > 0; i--) {

    const j = Math.floor(Math.random() * (i + 1));

    [a[i], a[j]] = [a[j], a[i]];
  }

  return a;
}


function randomInt(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}


function clamp(value, min, max) {
  return Math.max(min, Math.min(max, value));
}


function sleep(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}


/* =========================================================
   SCREEN NAVIGATION
   ========================================================= */

function showScreen(screen) {

  Object.values(screens).forEach(s => {
    s.classList.remove("active");
  });

  screen.classList.add("active");

  window.scrollTo({
    top: 0,
    behavior: "instant"
  });
}


function stopCurrentGame() {

  if (typeof state.gameCleanup === "function") {

    try {
      state.gameCleanup();
    } catch (error) {
      console.warn(error);
    }
  }

  state.gameCleanup = null;
}


/* =========================================================
   START
   ========================================================= */

$("startBtn").addEventListener("click", () => {

  const name = $("playerName").value.trim();

  if (!name) {

    $("playerName").focus();

    $("playerName").placeholder = "Please enter your name 💗";

    return;
  }

  state.playerName = name;

  state.score = 0;
  state.tokens = 0;
  state.currentLevel = 0;
  state.highestUnlocked = 0;
  state.completed = [];

  renderJourney();

  showScreen(screens.journey);
});


$("playerName").addEventListener("keydown", event => {

  if (event.key === "Enter") {
    $("startBtn").click();
  }
});


$("howBtn").addEventListener("click", () => {
  showScreen(screens.how);
});


$("backStartBtn").addEventListener("click", () => {
  showScreen(screens.start);
});


$("resetJourneyBtn").addEventListener("click", resetJourney);


$("finalResetBtn").addEventListener("click", resetJourney);


/* =========================================================
   RESET
   ========================================================= */

function resetJourney() {

  stopCurrentGame();

  state.playerName = "";
  state.score = 0;
  state.tokens = 0;
  state.currentLevel = 0;
  state.highestUnlocked = 0;
  state.completed = [];

  $("playerName").value = "";

  showScreen(screens.start);
}


/* =========================================================
   JOURNEY
   ========================================================= */

function renderJourney() {

  $("journeyGreeting").textContent =
    `Good luck, ${state.playerName}. Your journey starts here. 💗`;

  $("journeyScore").textContent = state.score;

  const list = $("levelList");

  list.innerHTML = "";

  LEVELS.forEach((level, index) => {

    const unlocked =
      index <= state.highestUnlocked;

    const complete =
      state.completed.includes(index);

    const item = document.createElement("div");

    item.className =
      "level-item" +
      (unlocked ? " unlocked" : "") +
      (complete ? " complete" : "");

    const number = document.createElement("div");

    number.className = "level-number";
    number.textContent = index + 1;

    const info = document.createElement("div");

    info.className = "level-info";

    const title = document.createElement("strong");

    title.textContent =
      `${level.icon} ${level.name}`;

    const description = document.createElement("span");

    description.textContent = level.description;

    info.appendChild(title);
    info.appendChild(description);

    const status = document.createElement("div");

    status.className = "level-status";

    if (complete) {
      status.textContent = "✓";
    } else if (unlocked) {
      status.textContent = "▶";
    } else {
      status.textContent = "🔒";
    }

    item.appendChild(number);
    item.appendChild(info);
    item.appendChild(status);

    if (unlocked) {

      item.addEventListener("click", () => {
        startLevel(index);
      });

      item.style.cursor = "pointer";
    }

    list.appendChild(item);
  });
}


/* =========================================================
   START LEVEL
   ========================================================= */

function startLevel(index) {

  stopCurrentGame();

  state.currentLevel = index;
  state.levelScore = 0;

  const level = LEVELS[index];

  $("gameTitle").textContent =
    `${level.icon} ${level.name}`;

  $("gameSubtitle").textContent =
    `Level ${index + 1} of ${LEVELS.length}`;

  $("gameScore").textContent = state.score;
  $("gameTokens").textContent = state.tokens;

  $("gameArea").innerHTML = "";

  showScreen(screens.game);

  level.play();
}


/* =========================================================
   GAME FINISH
   ========================================================= */

function finishLevel(passed, points, message = "") {

  stopCurrentGame();

  points = Math.max(0, Math.floor(points || 0));

  state.levelScore = points;

  if (passed) {

    state.score += points;

    if (!state.completed.includes(state.currentLevel)) {
      state.completed.push(state.currentLevel);
    }

    state.highestUnlocked =
      Math.max(
        state.highestUnlocked,
        state.currentLevel + 1
      );
  }

  $("resultIcon").textContent =
    passed ? "💗" : "💔";

  $("resultTitle").textContent =
    passed
      ? "Level Complete!"
      : "Not quite yet!";

  $("resultMessage").textContent =
    message ||
    (
      passed
        ? "You passed this level and the next part of the journey is unlocked."
        : "You need to pass this level before the next one opens."
    );

  $("levelScore").textContent =
    passed ? `+${points}` : "+0";

  $("resultTotal").textContent =
    state.score;

  const button = $("resultBtn");

  if (passed) {

    button.textContent =
      state.currentLevel === LEVELS.length - 1
        ? "See Final Result 💗"
        : "Continue to Journey 🚂";

    button.className = "btn";

    button.onclick = () => {

      if (state.currentLevel === LEVELS.length - 1) {
        showFinal();
      } else {
        renderJourney();
        showScreen(screens.journey);
      }
    };

  } else {

    button.textContent = "Retry Level";

    button.className = "btn secondary";

    button.onclick = () => {
      startLevel(state.currentLevel);
    };
  }

  showScreen(screens.result);
}


/* =========================================================
   MUSIC
   ========================================================= */

let audioContext = null;
let musicTimer = null;

function toggleMusic() {

  if (!audioContext) {

    audioContext =
      new (window.AudioContext || window.webkitAudioContext)();
  }

  if (audioContext.state === "suspended") {
    audioContext.resume();
  }

  state.musicOn = !state.musicOn;

  $("musicBtn").textContent =
    state.musicOn ? "🔊" : "🎵";

  if (state.musicOn) {
    startMusic();
  } else {
    stopMusic();
  }
}


function startMusic() {

  stopMusic();

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

  let index = 0;

  function playNote() {

    if (!state.musicOn || !audioContext) {
      return;
    }

    const osc = audioContext.createOscillator();
    const gain = audioContext.createGain();

    osc.type = "sine";

    osc.frequency.value =
      notes[index % notes.length];

    gain.gain.setValueAtTime(
      0.0001,
      audioContext.currentTime
    );

    gain.gain.exponentialRampToValueAtTime(
      0.035,
      audioContext.currentTime + .03
    );

    gain.gain.exponentialRampToValueAtTime(
      0.0001,
      audioContext.currentTime + .32
    );

    osc.connect(gain);
    gain.connect(audioContext.destination);

    osc.start();
    osc.stop(audioContext.currentTime + .34);

    index++;
  }

  playNote();

  musicTimer =
    setInterval(playNote, 430);
}


function stopMusic() {

  if (musicTimer) {
    clearInterval(musicTimer);
    musicTimer = null;
  }
}


$("musicBtn").addEventListener("click", toggleMusic);


/* =========================================================
   GAME 1
   HEART CATCHER
   ========================================================= */

function gameHeartCatcher() {

  const area = $("gameArea");

  area.innerHTML = `
    <canvas id="heartCanvas"></canvas>

    <div class="mobile-controls">
      <button class="move-btn" id="heartLeft">◀</button>
      <button class="move-btn" id="heartRight">▶</button>
    </div>
  `;

  const canvas = $("heartCanvas");
  const ctx = canvas.getContext("2d");

  let width = 0;
  let height = 0;

  let playerX = 0;

  const playerWidth = 82;
  const playerHeight = 25;

  let hearts = [];

  let score = 0;
  let lives = 3;

  let running = true;

  let lastSpawn = 0;

  function resize() {

    const rect =
      canvas.getBoundingClientRect();

    width = rect.width;
    height = rect.height;

    canvas.width =
      Math.floor(width * devicePixelRatio);

    canvas.height =
      Math.floor(height * devicePixelRatio);

    ctx.setTransform(
      devicePixelRatio,
      0,
      0,
      devicePixelRatio,
      0,
      0
    );

    if (!playerX) {
      playerX = width / 2;
    }
  }

  resize();

  window.addEventListener("resize", resize);

  function spawnHeart() {

    hearts.push({
      x: randomInt(25, Math.max(25, width - 25)),
      y: -30,
      speed: 1.7 + Math.random() * 1.8,
      size: 19 + Math.random() * 7,
      rotation: Math.random() * Math.PI,
      wobble: Math.random() * Math.PI * 2
    });
  }

  function movePlayer(amount) {

    playerX =
      clamp(
        playerX + amount,
        playerWidth / 2 + 8,
        width - playerWidth / 2 - 8
      );
  }

  $("heartLeft").addEventListener(
    "pointerdown",
    () => movePlayer(-55)
  );

  $("heartRight").addEventListener(
    "pointerdown",
    () => movePlayer(55)
  );

  canvas.addEventListener(
    "pointermove",
    event => {

      const rect =
        canvas.getBoundingClientRect();

      playerX =
        clamp(
          event.clientX - rect.left,
          playerWidth / 2,
          width - playerWidth / 2
        );
    }
  );

  function drawHeart(x, y, size) {

    ctx.save();

    ctx.translate(x, y);

    ctx.fillStyle = "#ff9fc9";

    ctx.beginPath();

    const s = size;

    ctx.moveTo(0, s * .35);

    ctx.bezierCurveTo(
      -s * .7,
      -s * .1,
      -s * .5,
      -s * .65,
      0,
      -s * .25
    );

    ctx.bezierCurveTo(
      s * .5,
      -s * .65,
      s * .7,
      -s * .1,
      0,
      s * .35
    );

    ctx.fill();

    ctx.restore();
  }

  function draw() {

    if (!running) return;

    ctx.clearRect(0,0,width,height);

    const gradient =
      ctx.createLinearGradient(0,0,0,height);

    gradient.addColorStop(0,"#2c1326");
    gradient.addColorStop(1,"#120914");

    ctx.fillStyle = gradient;

    ctx.fillRect(0,0,width,height);

    ctx.fillStyle =
      "rgba(255,255,255,.35)";

    for (let i = 0; i < 18; i++) {

      const x =
        (i * 73) % Math.max(1,width);

      const y =
        (i * 113) % Math.max(1,height);

      ctx.fillText("✦",x,y);
    }

    hearts.forEach(h => {
      drawHeart(h.x,h.y,h.size);
    });

    /* basket */

    ctx.fillStyle = "#f4a4c9";

    const px =
      playerX - playerWidth / 2;

    const py =
      height - 80;

    ctx.beginPath();

    ctx.roundRect(
      px,
      py,
      playerWidth,
      playerHeight,
      10
    );

    ctx.fill();

    ctx.fillStyle = "#42152c";

    ctx.font = "bold 18px sans-serif";

    ctx.textAlign = "center";

    ctx.fillText(
      "LULU",
      playerX,
      py + 19
    );

    ctx.textAlign = "left";
  }

  function update(time) {

    if (!running) return;

    if (time - lastSpawn > 520) {

      spawnHeart();

      lastSpawn = time;
    }

    hearts.forEach(h => {

      h.y += h.speed;

      h.x +=
        Math.sin(h.y * .015 + h.wobble) * .35;
    });

    const py = height - 80;

    hearts = hearts.filter(h => {

      const caught =
        h.y > py - 10 &&
        h.y < py + 35 &&
        h.x > playerX - playerWidth / 2 &&
        h.x < playerX + playerWidth / 2;

      if (caught) {

        score++;

        return false;
      }

      if (h.y > height + 30) {

        lives--;

        if (lives <= 0) {

          running = false;

          finishLevel(
            score >= 8,
            score * 14,
            score >= 8
              ? `You caught ${score} hearts! 💗`
              : `You caught ${score} hearts. You need 8 to pass.`
          );

          return false;
        }

        return false;
      }

      return true;
    });

    $("gameScore").textContent =
      state.score + score * 14;

    requestAnimationFrame(update);
  }

  function loop(time) {

    draw();
    update(time);
  }

  const animation =
    requestAnimationFrame(function frame(time) {

      loop(time);

      if (running) {
        requestAnimationFrame(frame);
      }
    });

  state.gameCleanup = () => {

    running = false;

    window.removeEventListener(
      "resize",
      resize
    );

    cancelAnimationFrame(animation);
  };
}


/* =========================================================
   GAME 2
   LOVE MATCH
   ========================================================= */

function gameLoveMatch() {

  const area = $("gameArea");

  const symbols = [
    "💗","💗","⭐","⭐",
    "🌸","🌸","🦋","🦋",
    "🌙","🌙","✨","✨",
    "💌","💌","🌹","🌹"
  ];

  let board = shuffle(symbols);

  let selected = [];
  let moves = 0;
  let matched = 0;

  area.innerHTML = `
    <div class="card" style="height:100%;overflow:auto">

      <div class="game-instructions">
        Swap adjacent tiles to make a row or column of three.
        Make <strong>5 matches</strong> to pass.
      </div>

      <div id="matchBoard" class="match-board"></div>

      <div class="feedback" id="matchFeedback">
        0 / 5 matches
      </div>

    </div>
  `;

  const boardEl = $("matchBoard");

  function render() {

    boardEl.innerHTML = "";

    board.forEach((symbol,index) => {

      const button =
        document.createElement("button");

      button.className = "match-tile";

      button.textContent = symbol;

      if (selected.includes(index)) {
        button.classList.add("selected");
      }

      button.addEventListener(
        "click",
        () => selectTile(index)
      );

      boardEl.appendChild(button);
    });
  }

  function adjacent(a,b) {

    const ar = Math.floor(a / 4);
    const ac = a % 4;

    const br = Math.floor(b / 4);
    const bc = b % 4;

    return (
      Math.abs(ar - br) +
      Math.abs(ac - bc)
    ) === 1;
  }

  function findMatches() {

    const matches = new Set();

    for (let r = 0; r < 4; r++) {

      for (let c = 0; c < 2; c++) {

        const i = r * 4 + c;

        if (
          board[i] &&
          board[i] === board[i+1] &&
          board[i] === board[i+2]
        ) {

          matches.add(i);
          matches.add(i+1);
          matches.add(i+2);
        }
      }
    }

    for (let c = 0; c < 4; c++) {

      for (let r = 0; r < 2; r++) {

        const i = r * 4 + c;

        if (
          board[i] &&
          board[i] === board[i+4] &&
          board[i] === board[i+8]
        ) {

          matches.add(i);
          matches.add(i+4);
          matches.add(i+8);
        }
      }
    }

    return [...matches];
  }

  async function selectTile(index) {

    if (selected.length === 0) {

      selected = [index];

      render();

      return;
    }

    if (selected[0] === index) {

      selected = [];

      render();

      return;
    }

    if (!adjacent(selected[0],index)) {

      selected = [index];

      render();

      return;
    }

    const first = selected[0];

    [board[first],board[index]] =
      [board[index],board[first]];

    moves++;

    selected = [];

    render();

    await sleep(80);

    const matches =
      findMatches();

    if (matches.length) {

      matched++;

      matches.forEach(i => {
        board[i] = null;
      });

      render();

      await sleep(180);

      while (board.includes(null)) {

        for (let c = 0; c < 4; c++) {

          for (let r = 3; r > 0; r--) {

            const i = r * 4 + c;

            if (board[i] === null) {
              board[i] = board[i - 4];
              board[i - 4] = null;
            }
          }
        }

        for (let c = 0; c < 4; c++) {

          if (board[c] === null) {

            board[c] =
              symbols[randomInt(0,symbols.length - 1)];
          }
        }
      }

      render();

      $("matchFeedback").textContent =
        `${matched} / 5 matches`;

      if (matched >= 5) {

        finishLevel(
          true,
          80 + Math.max(0,100 - moves * 3),
          "Perfect! You created five matching groups. 💕"
        );
      }

    } else {

      $("matchFeedback").textContent =
        `${matched} / 5 matches • Try another swap`;
    }
  }

  render();

  state.gameCleanup = () => {};
}


/* =========================================================
   GAME 3
   MEMORY FLIP
   ========================================================= */

function gameMemoryFlip() {

  const area = $("gameArea");

  const symbols = [
    "💗","🌹","🐬","⭐",
    "🌸","🦋","🌙","💌"
  ];

  const cards =
    shuffle([...symbols,...symbols]);

  let first = null;
  let second = null;
  let locked = false;
  let pairs = 0;
  let moves = 0;

  area.innerHTML = `
    <div class="card" style="height:100%;overflow:auto">

      <div class="game-instructions">
        Find all 8 pairs.
      </div>

      <div id="memoryGrid" class="memory-grid"></div>

      <div
        class="feedback"
        id="memoryFeedback"
      >
        0 / 8 pairs
      </div>

    </div>
  `;

  const grid = $("memoryGrid");

  function render() {

    grid.innerHTML = "";

    cards.forEach((symbol,index) => {

      const card =
        document.createElement("button");

      card.className =
        "memory-card";

      card.innerHTML = `
        <div class="memory-inner">
          <div class="memory-front">?</div>
          <div class="memory-back">${symbol}</div>
        </div>
      `;

      if (
        index === first ||
        index === second ||
        card.dataset.matched === "true"
      ) {
        card.classList.add("flipped");
      }

      if (cards[index] === null) {
        card.classList.add("matched");
      }

      card.addEventListener(
        "click",
        () => flip(index)
      );

      grid.appendChild(card);
    });
  }

  async function flip(index) {

    if (
      locked ||
      cards[index] === null ||
      index === first
    ) {
      return;
    }

    if (first === null) {

      first = index;

      render();

      return;
    }

    second = index;

    moves++;

    render();

    locked = true;

    await sleep(650);

    if (cards[first] === cards[second]) {

      cards[first] = null;
      cards[second] = null;

      pairs++;

      $("memoryFeedback").textContent =
        `${pairs} / 8 pairs`;

      first = null;
      second = null;
      locked = false;

      render();

      if (pairs === 8) {

        finishLevel(
          true,
          Math.max(60,150 - moves * 2),
          `You found all 8 pairs in ${moves} moves!`
        );
      }

    } else {

      first = null;
      second = null;

      locked = false;

      render();
    }
  }

  render();

  state.gameCleanup = () => {};
}


/* =========================================================
   GAME 4
   WORD FIND
   ========================================================= */

function gameWordFind() {

  const area = $("gameArea");

  const words = [
    "LULU",
    "DOLPHIN",
    "ROSE",
    "SUSHI",
    "POETRY",
    "SUNFLOWER"
  ];

  const size = 8;

  const grid = Array.from(
    {length:size * size},
    () => ""
  );

  const placements = {};

  function canPlace(word,row,col,dr,dc) {

    for (let i = 0; i < word.length; i++) {

      const r = row + dr * i;
      const c = col + dc * i;

      if (
        r < 0 ||
        r >= size ||
        c < 0 ||
        c >= size
      ) {
        return false;
      }

      const existing =
        grid[r * size + c];

      if (
        existing &&
        existing !== word[i]
      ) {
        return false;
      }
    }

    return true;
  }

  function placeWord(word) {

    const dirs = shuffle([
      [0,1],
      [1,0],
      [1,1],
      [1,-1],
      [0,-1],
      [-1,0]
    ]);

    for (let attempt = 0; attempt < 300; attempt++) {

      const [dr,dc] =
        dirs[attempt % dirs.length];

      const row =
        randomInt(0,size - 1);

      const col =
        randomInt(0,size - 1);

      if (canPlace(word,row,col,dr,dc)) {

        const cells = [];

        for (let i = 0; i < word.length; i++) {

          const r = row + dr * i;
          const c = col + dc * i;

          grid[r * size + c] =
            word[i];

          cells.push(r * size + c);
        }

        placements[word] = cells;

        return true;
      }
    }

    return false;
  }

  words.forEach(placeWord);

  const letters =
    "ABCDEFGHIJKLMNOPQRSTUVWXYZ";

  for (let i = 0; i < grid.length; i++) {

    if (!grid[i]) {

      grid[i] =
        letters[randomInt(0,letters.length - 1)];
    }
  }

  area.innerHTML = `
    <div class="card" style="height:100%;overflow:auto">

      <div class="game-instructions">
        Tap the first letter and then the last letter of a word.
        Words can run horizontally, vertically or diagonally.
      </div>

      <div id="wordList" class="word-list"></div>

      <div id="wordGrid" class="word-grid"></div>

      <div
        id="wordFeedback"
        class="feedback"
      >
        0 / ${words.length} found
      </div>

    </div>
  `;

  const wordList = $("wordList");
  const wordGrid = $("wordGrid");

  const found = new Set();

  let startCell = null;

  words.forEach(word => {

    const tag =
      document.createElement("span");

    tag.className = "word-tag";
    tag.dataset.word = word;
    tag.textContent = word;

    wordList.appendChild(tag);
  });

  function renderGrid() {

    wordGrid.innerHTML = "";

    grid.forEach((letter,index) => {

      const cell =
        document.createElement("button");

      cell.className = "word-cell";

      cell.textContent = letter;

      if (
        [...found]
          .some(word =>
            placements[word].includes(index)
          )
      ) {
        cell.classList.add("found");
      }

      cell.addEventListener(
        "click",
        () => selectCell(index)
      );

      wordGrid.appendChild(cell);
    });
  }

  function selectCell(index) {

    if (startCell === null) {

      startCell = index;

      wordGrid.children[index]
        .classList.add("selected");

      return;
    }

    const endCell = index;

    const sr =
      Math.floor(startCell / size);

    const sc =
      startCell % size;

    const er =
      Math.floor(endCell / size);

    const ec =
      endCell % size;

    const dr =
      Math.sign(er - sr);

    const dc =
      Math.sign(ec - sc);

    const distance =
      Math.max(
        Math.abs(er - sr),
        Math.abs(ec - sc)
      );

    const selectedCells = [];

    for (let i = 0; i <= distance; i++) {

      const r = sr + dr * i;
      const c = sc + dc * i;

      selectedCells.push(
        r * size + c
      );
    }

    const letters =
      selectedCells
        .map(i => grid[i])
        .join("");

    const reverse =
      letters
        .split("")
        .reverse()
        .join("");

    const match =
      words.find(word =>
        !found.has(word) &&
        (
          word === letters ||
          word === reverse
        )
      );

    if (match) {

      found.add(match);

      const tag =
        wordList.querySelector(
          `[data-word="${match}"]`
        );

      if (tag) {
        tag.classList.add("found");
      }

      $("wordFeedback").textContent =
        `${found.size} / ${words.length} found`;

      renderGrid();

      if (found.size === words.length) {

        finishLevel(
          true,
          130,
          "You found every Lulu word! 🔎💗"
        );
      }

    } else {

      $("wordFeedback").textContent =
        `${found.size} / ${words.length} found • Not a word`;

      renderGrid();
    }

    startCell = null;
  }

  renderGrid();

  state.gameCleanup = () => {};
}


/* =========================================================
   GAME 5
   BROKEN HEART
   ========================================================= */

function gameBrokenHeart() {

  const area = $("gameArea");

  const targets = [
    "❤️",
    "💗",
    "💖",
    "💕"
  ];

  let placed = 0;

  area.innerHTML = `
    <div class="card" style="height:100%;text-align:center">

      <div class="game-instructions">
        The heart is broken. Tap the repair pieces in the correct
        order before the cracks take over.
      </div>

      <div class="repair-heart">

        <div class="big-heart">
          💔
        </div>

        <div
          class="crack"
          style="top:32%;left:44%"
        >
          ╱
        </div>

        <div
          class="repair-piece"
          style="top:5%;left:5%"
          data-piece="0"
        >
          ❤️
        </div>

        <div
          class="repair-piece"
          style="top:7%;right:4%"
          data-piece="1"
        >
          💗
        </div>

        <div
          class="repair-piece"
          style="bottom:5%;left:7%"
          data-piece="2"
        >
          💖
        </div>

        <div
          class="repair-piece"
          style="bottom:5%;right:5%"
          data-piece="3"
        >
          💕
        </div>

      </div>

      <div
        id="repairFeedback"
        class="feedback"
      >
        Repair piece 1 of 4
      </div>

    </div>
  `;

  const pieces =
    [...area.querySelectorAll(".repair-piece")];

  pieces.forEach(piece => {

    piece.addEventListener(
      "click",
      () => {

        const number =
          Number(piece.dataset.piece);

        if (number === placed) {

          piece.style.opacity = ".35";
          piece.style.pointerEvents = "none";

          placed++;

          $("repairFeedback").textContent =
            placed < 4
              ? `Repair piece ${placed + 1} of 4`
              : "Heart repaired! 💗";

          if (placed === 4) {

            setTimeout(() => {

              finishLevel(
                true,
                110,
                "You put every piece back together. 💗"
              );

            },300);
          }

        } else {

          $("repairFeedback").textContent =
            "That's not the next piece. Follow the order. 💔";
        }
      }
    );
  });

  state.gameCleanup = () => {};
}


/* =========================================================
   GAME 6
   LUCKY WHEEL
   ========================================================= */

function gameLuckyWheel() {

  const area = $("gameArea");

  let spinning = false;

  const rewards = [
    30,
    50,
    70,
    100,
    40,
    80,
    120,
    60
  ];

  area.innerHTML = `
    <div class="card" style="height:100%;text-align:center">

      <div class="game-instructions">
        Spin the wheel and accept whatever luck sends your way.
      </div>

      <div class="wheel-wrap">

        <div class="wheel-pointer">
          ▼
        </div>

        <div
          class="wheel"
          id="luckyWheel"
        ></div>

      </div>

      <div
        class="feedback"
        id="wheelFeedback"
      >
        Ready?
      </div>

      <button
        class="btn gold"
        id="spinWheelBtn"
      >
        Spin the Wheel 🎡
      </button>

    </div>
  `;

  const wheel = $("luckyWheel");
  const button = $("spinWheelBtn");

  button.addEventListener("click", () => {

    if (spinning) return;

    spinning = true;

    const extra =
      randomInt(0,7);

    const rotation =
      1440 +
      extra * 45;

    wheel.style.transform =
      `rotate(${rotation}deg)`;

    setTimeout(() => {

      const reward =
        rewards[extra];

      $("wheelFeedback").textContent =
        `You won ${reward} points! 💗`;

      button.disabled = true;
      button.style.opacity = ".6";

      finishLevel(
        true,
        reward,
        `The wheel landed on ${reward} points!`
      );

    },3100);
  });

  state.gameCleanup = () => {
    spinning = false;
  };
}


/* =========================================================
   GAME 7
   PERFECT PAIRS
   ========================================================= */

function gamePerfectPairs() {

  const area = $("gameArea");

  const pairs = [
    ["💗","Heart"],
    ["🌹","Rose"],
    ["🐬","Dolphin"],
    ["⭐","Star"],
    ["🌻","Sunflower"],
    ["💌","Letter"]
  ];

  const cards = shuffle(
    pairs.flatMap(pair => [
      {
        icon: pair[0],
        name: pair[1]
      },
      {
        icon: pair[0],
        name: pair[1]
      }
    ])
  );

  let selected = [];
  let matched = 0;
  let locked = false;

  area.innerHTML = `
    <div class="card" style="height:100%;overflow:auto">

      <div class="game-instructions">
        Find the matching symbol pairs.
      </div>

      <div id="pairGrid" class="pair-grid"></div>

      <div
        id="pairFeedback"
        class="feedback"
      >
        0 / 6 pairs
      </div>

    </div>
  `;

  const grid = $("pairGrid");

  function render() {

    grid.innerHTML = "";

    cards.forEach((card,index) => {

      const button =
        document.createElement("button");

      button.className = "pair-card";

      if (
        selected.includes(index) ||
        card.matched
      ) {
        button.textContent = card.icon;
      } else {
        button.textContent = "♡";
      }

      button.addEventListener(
        "click",
        () => choose(index)
      );

      grid.appendChild(button);
    });
  }

  async function choose(index) {

    if (
      locked ||
      cards[index].matched ||
      selected.includes(index)
    ) {
      return;
    }

    selected.push(index);

    render();

    if (selected.length < 2) {
      return;
    }

    locked = true;

    const [a,b] = selected;

    await sleep(500);

    if (cards[a].name === cards[b].name) {

      cards[a].matched = true;
      cards[b].matched = true;

      matched++;

      $("pairFeedback").textContent =
        `${matched} / 6 pairs`;

      selected = [];
      locked = false;

      render();

      if (matched === 6) {

        finishLevel(
          true,
          125,
          "Every pair is perfect. 💗"
        );
      }

    } else {

      selected = [];
      locked = false;

      render();
    }
  }

  render();

  state.gameCleanup = () => {};
}


/* =========================================================
   GAME 8
   STAR CATCH
   ========================================================= */

function gameStarCatch() {

  const area = $("gameArea");

  area.innerHTML = `
    <div
      class="star-field"
      id="starField"
    >
      <div
        class="feedback"
        id="starFeedback"
        style="
          position:absolute;
          top:15px;
          left:0;
          right:0;
          z-index:4;
        "
      >
        Catch 12 stars!
      </div>
    </div>
  `;

  const field = $("starField");

  let caught = 0;
  let active = true;
  let currentStar = null;

  function spawn() {

    if (!active) return;

    if (currentStar) {
      currentStar.remove();
    }

    const star =
      document.createElement("button");

    star.className = "tap-star";
    star.textContent = "⭐";

    star.style.left =
      `${randomInt(8,82)}%`;

    star.style.top =
      `${randomInt(12,80)}%`;

    field.appendChild(star);

    currentStar = star;

    const timeout =
      setTimeout(() => {

        if (active) {
          spawn();
        }

      },900);

    star.addEventListener("click", () => {

      clearTimeout(timeout);

      caught++;

      star.remove();

      currentStar = null;

      $("starFeedback").textContent =
        `${caught} / 12 stars`;

      if (caught >= 12) {

        active = false;

        finishLevel(
          true,
          100 + caught * 3,
          "You caught every star! ⭐"
        );

      } else {

        setTimeout(spawn,100);
      }
    });
  }

  spawn();

  state.gameCleanup = () => {
    active = false;

    if (currentStar) {
      currentStar.remove();
    }
  };
}


/* =========================================================
   GAME 9
   LOVE LETTERS
   ========================================================= */

function gameLoveLetters() {

  const area = $("gameArea");

  const target =
    "LULU";

  let answer = [];

  const letters =
    shuffle([
      "L","U","L","U",
      "X","M","A","P"
    ]);

  area.innerHTML = `
    <div class="card" style="height:100%;text-align:center">

      <div class="game-instructions">
        Build the hidden four-letter message.
      </div>

      <div
        id="letterSlots"
        class="letter-slots"
      >
        ${[0,1,2,3]
          .map(() =>
            `<div class="letter-slot"></div>`
          )
          .join("")}
      </div>

      <div
        id="letterBank"
        class="letter-bank"
      ></div>

      <div
        id="letterFeedback"
        class="feedback"
      >
        Choose a letter.
      </div>

      <button
        class="btn secondary"
        id="letterClear"
      >
        Clear
      </button>

    </div>
  `;

  const bank = $("letterBank");

  letters.forEach((letter,index) => {

    const button =
      document.createElement("button");

    button.className =
      "letter-button";

    button.textContent = letter;

    button.dataset.index = index;

    button.addEventListener(
      "click",
      () => {

        if (answer.length >= 4) return;

        answer.push(letter);

        button.disabled = true;
        button.style.opacity = ".3";

        render();

        if (answer.length === 4) {

          const word =
            answer.join("");

          if (word === target) {

            finishLevel(
              true,
              120,
              "You found the hidden message: LULU 💌"
            );

          } else {

            $("letterFeedback").textContent =
              "Not quite. Try again.";

            setTimeout(clearAnswer,500);
          }
        }
      }
    );

    bank.appendChild(button);
  });

  function render() {

    const slots =
      [...$("letterSlots").children];

    slots.forEach((slot,index) => {

      slot.textContent =
        answer[index] || "";
    });
  }

  function clearAnswer() {

    answer = [];

    [...bank.children].forEach(button => {

      button.disabled = false;
      button.style.opacity = "1";
    });

    render();

    $("letterFeedback").textContent =
      "Choose a letter.";
  }

  $("letterClear").addEventListener(
    "click",
    clearAnswer
  );

  state.gameCleanup = () => {};
}


/* =========================================================
   GAME 10
   REACTION RUSH
   ========================================================= */

function gameReactionRush() {

  const area = $("gameArea");

  area.innerHTML = `
    <div class="card" style="height:100%;text-align:center">

      <div class="game-instructions">
        Wait for the circle to turn green, then tap it.
        Do not tap while it is red.
      </div>

      <div
        id="reactionRound"
        class="feedback"
      >
        Round 1 of 5
      </div>

      <div class="reaction-zone">

        <button
          id="reactionTarget"
          class="reaction-target"
        >
          WAIT
        </button>

      </div>

      <div
        id="reactionFeedback"
        class="feedback"
      >
        Get ready...
      </div>

    </div>
  `;

  const target = $("reactionTarget");

  let round = 1;
  let good = 0;
  let ready = false;
  let timeoutId = null;
  let startTime = 0;
  let finished = false;

  function nextRound() {

    if (round > 5) {

      finishLevel(
        good >= 4,
        good * 35,
        good >= 4
          ? `Excellent reactions! ${good}/5 successful.`
          : `You got ${good}/5. You need 4 to pass.`
      );

      return;
    }

    ready = false;

    target.classList.remove("go");

    target.textContent = "WAIT";

    $("reactionRound").textContent =
      `Round ${round} of 5`;

    const delay =
      randomInt(900,2400);

    timeoutId =
      setTimeout(() => {

        if (finished) return;

        ready = true;
        startTime = performance.now();

        target.classList.add("go");
        target.textContent = "TAP!";

      },delay);
  }

  target.addEventListener("click", () => {

    if (!ready) {

      if (timeoutId) {
        clearTimeout(timeoutId);
      }

      $("reactionFeedback").textContent =
        "Too early! ❌";

      round++;

      setTimeout(nextRound,500);

      return;
    }

    const reaction =
      performance.now() - startTime;

    if (reaction <= 850) {

      good++;

      $("reactionFeedback").textContent =
        `${Math.round(reaction)} ms — nice! 💗`;

    } else {

      $("reactionFeedback").textContent =
        `${Math.round(reaction)} ms — a little slow.`;
    }

    round++;

    ready = false;

    target.classList.remove("go");

    setTimeout(nextRound,600);
  });

  nextRound();

  state.gameCleanup = () => {

    finished = true;

    if (timeoutId) {
      clearTimeout(timeoutId);
    }
  };
}


/* =========================================================
   PRESSURE QUIZ QUESTIONS
   ========================================================= */

const PRESSURE_QUESTIONS = [

  {
    q:"Which planet is known as the Red Planet?",
    a:["Mars","Venus","Jupiter","Mercury"]
  },

  {
    q:"How many sides does a hexagon have?",
    a:["Six","Five","Seven","Eight"]
  },

  {
    q:"Which ocean is the largest?",
    a:["Pacific Ocean","Atlantic Ocean","Indian Ocean","Arctic Ocean"]
  },

  {
    q:"What gas do humans need to breathe?",
    a:["Oxygen","Helium","Carbon dioxide","Hydrogen"]
  },

  {
    q:"What is 12 × 5?",
    a:["60","50","65","70"]
  },

  {
    q:"Which animal is the largest mammal?",
    a:["Blue whale","Elephant","Giraffe","Hippopotamus"]
  },

  {
    q:"What is the capital of France?",
    a:["Paris","Rome","Madrid","Lisbon"]
  },

  {
    q:"Which instrument has black and white keys?",
    a:["Piano","Trumpet","Violin","Flute"]
  },

  {
    q:"How many days are in a leap year?",
    a:["366","365","364","367"]
  },

  {
    q:"Which colour is made by mixing blue and yellow?",
    a:["Green","Purple","Orange","Pink"]
  },

  {
    q:"What is the freezing point of water in Celsius?",
    a:["0°C","10°C","-10°C","5°C"]
  },

  {
    q:"Which continent is Australia part of?",
    a:["Oceania","Europe","Asia","Africa"]
  },

  {
    q:"How many legs does a spider have?",
    a:["Eight","Six","Ten","Twelve"]
  },

  {
    q:"Which shape has three sides?",
    a:["Triangle","Square","Circle","Pentagon"]
  },

  {
    q:"What is the largest planet in our solar system?",
    a:["Jupiter","Saturn","Earth","Neptune"]
  },

  {
    q:"Which bird is famous for not being able to fly?",
    a:["Penguin","Eagle","Falcon","Swallow"]
  },

  {
    q:"What is H2O?",
    a:["Water","Oxygen","Salt","Hydrogen"]
  },

  {
    q:"How many minutes are in an hour?",
    a:["60","50","90","100"]
  },

  {
    q:"Which country is famous for the Eiffel Tower?",
    a:["France","Italy","Spain","Germany"]
  },

  {
    q:"What is the smallest prime number?",
    a:["2","1","3","0"]
  },

  {
    q:"Which animal is known for its black and white stripes?",
    a:["Zebra","Tiger","Panda","Skunk"]
  },

  {
    q:"What is the opposite of north?",
    a:["South","East","West","Down"]
  },

  {
    q:"Which month comes after September?",
    a:["October","November","August","December"]
  },

  {
    q:"How many colours are traditionally in a rainbow?",
    a:["Seven","Five","Six","Eight"]
  },

  {
    q:"Which planet do we live on?",
    a:["Earth","Mars","Venus","Saturn"]
  },

  {
    q:"Which fruit is traditionally yellow and curved?",
    a:["Banana","Apple","Blueberry","Cherry"]
  },

  {
    q:"What is the capital of New Zealand?",
    a:["Wellington","Auckland","Christchurch","Dunedin"]
  },

  {
    q:"Which sense uses the eyes?",
    a:["Sight","Hearing","Taste","Touch"]
  },

  {
    q:"What do bees make?",
    a:["Honey","Milk","Bread","Cheese"]
  },

  {
    q:"Which season comes after winter?",
    a:["Spring","Summer","Autumn","Monsoon"]
  }
];


/* =========================================================
   GAME 11
   PRESSURE QUIZ
   ========================================================= */

function gamePressureQuiz() {

  const area = $("gameArea");

  const questions =
    shuffle(PRESSURE_QUESTIONS).slice(0,10);

  let index = 0;
  let correct = 0;

  let timerId = null;
  let questionLocked = false;
  let remaining = 8;

  area.innerHTML = `
    <div class="card quiz-box" style="height:100%;overflow:auto">

      <div class="quiz-progress">
        <div id="pressureProgress"></div>
      </div>

      <div
        class="small"
        id="pressureCount"
      ></div>

      <h2 id="pressureQuestion"></h2>

      <div class="timer-wrap">
        <div
          class="timer-circle"
          id="pressureTimer"
        >
          8
        </div>
      </div>

      <div
        class="choice-grid"
        id="pressureAnswers"
      ></div>

      <div
        class="feedback"
        id="pressureFeedback"
      ></div>

    </div>
  `;

  function clearTimer() {

    if (timerId !== null) {

      clearInterval(timerId);
      timerId = null;
    }
  }

  function startTimer() {

    clearTimer();

    remaining = 8;

    $("pressureTimer").textContent =
      remaining;

    timerId =
      setInterval(() => {

        remaining--;

        $("pressureTimer").textContent =
          remaining;

        if (remaining <= 0) {

          clearTimer();

          answerQuestion(-1);
        }

      },1000);
  }

  function renderQuestion() {

    questionLocked = false;

    clearTimer();

    const current =
      questions[index];

    $("pressureCount").textContent =
      `Question ${index + 1} of ${questions.length}`;

    $("pressureQuestion").textContent =
      current.q;

    $("pressureProgress").style.width =
      `${(index / questions.length) * 100}%`;

    const answers =
      current.a.map(
        (text,originalIndex) => ({
          text,
          correct: originalIndex === 0
        })
      );

    const shuffledAnswers =
      shuffle(answers);

    const container =
      $("pressureAnswers");

    container.innerHTML = "";

    shuffledAnswers.forEach(answer => {

      const button =
        document.createElement("button");

      button.className = "choice";

      button.textContent =
        answer.text;

      button.addEventListener(
        "click",
        () => answerQuestion(answer.correct ? 0 : 1,button)
      );

      container.appendChild(button);
    });

    $("pressureFeedback").textContent =
      "";

    startTimer();
  }

  function answerQuestion(result, clickedButton = null) {

    if (questionLocked) return;

    questionLocked = true;

    clearTimer();

    const buttons =
      [...$("pressureAnswers").children];

    buttons.forEach(button => {
      button.disabled = true;
    });

    const isCorrect =
      result === 0;

    if (clickedButton) {

      clickedButton.classList.add(
        isCorrect ? "correct" : "wrong"
      );
    }

    if (isCorrect) {

      correct++;

      $("pressureFeedback").textContent =
        "Correct! 💗";

      $("pressureFeedback").className =
        "feedback good";

    } else {

      $("pressureFeedback").textContent =
        "Time's up!";

      $("pressureFeedback").className =
        "feedback bad";
    }

    setTimeout(() => {

      index++;

      if (index >= questions.length) {

        $("pressureProgress").style.width = "100%";

        finishLevel(
          correct >= 6,
          correct * 20,
          correct >= 6
            ? `You got ${correct}/10 under pressure! ⏱️`
            : `You got ${correct}/10. You need 6 correct answers to pass.`
        );

      } else {

        renderQuestion();
      }

    },700);
  }

  renderQuestion();

  state.gameCleanup = () => {
    clearTimer();
  };
}


/* =========================================================
   GAME 12
   COLOUR MEMORY
   ========================================================= */

function gameColourMemory() {

  const area = $("gameArea");

  const colours = [
    "pink",
    "purple",
    "blue",
    "green"
  ];

  let sequence = [];
  let playerIndex = 0;
  let round = 0;
  let accepting = false;
  let timers = [];

  area.innerHTML = `
    <div class="card" style="height:100%;text-align:center">

      <div class="game-instructions">
        Watch the sequence, then repeat it.
        Reach round 5 to pass.
      </div>

      <div
        id="colourRound"
        class="feedback"
      >
        Round 1
      </div>

      <div class="colour-grid">

        <button
          class="colour-pad pad-pink"
          data-colour="pink"
        ></button>

        <button
          class="colour-pad pad-purple"
          data-colour="purple"
        ></button>

        <button
          class="colour-pad pad-blue"
          data-colour="blue"
        ></button>

        <button
          class="colour-pad pad-green"
          data-colour="green"
        ></button>

      </div>

      <div
        id="colourFeedback"
        class="feedback"
      >
        Watch...
      </div>

    </div>
  `;

  const pads =
    [...area.querySelectorAll(".colour-pad")];

  async function showSequence() {

    accepting = false;

    $("colourFeedback").textContent =
      "Watch carefully...";

    for (const colour of sequence) {

      const pad =
        pads.find(
          p => p.dataset.colour === colour
        );

      pad.classList.add("active");

      await sleep(420);

      pad.classList.remove("active");

      await sleep(170);
    }

    accepting = true;

    playerIndex = 0;

    $("colourFeedback").textContent =
      "Your turn!";
  }

  function startRound() {

    round++;

    $("colourRound").textContent =
      `Round ${round} of 5`;

    sequence.push(
      colours[randomInt(0,3)]
    );

    showSequence();
  }

  pads.forEach(pad => {

    pad.addEventListener("click", () => {

      if (!accepting) return;

      const chosen =
        pad.dataset.colour;

      const expected =
        sequence[playerIndex];

      if (chosen !== expected) {

        accepting = false;

        finishLevel(
          false,
          0,
          "The sequence was broken. Try again."
        );

        return;
      }

      pad.classList.add("active");

      setTimeout(() => {
        pad.classList.remove("active");
      },120);

      playerIndex++;

      if (playerIndex === sequence.length) {

        accepting = false;

        if (round >= 5) {

          finishLevel(
            true,
            160,
            "Your colour memory is seriously good! 🎨"
          );

        } else {

          setTimeout(
            startRound,
            650
          );
        }
      }
    });
  });

  startRound();

  state.gameCleanup = () => {
    accepting = false;
    timers.forEach(clearTimeout);
  };
}


/* =========================================================
   GAME 13
   LUCKY NUMBERS
   ========================================================= */

function gameLuckyNumbers() {

  const area = $("gameArea");

  const lucky =
    randomInt(1,25);

  let attempts = 0;

  area.innerHTML = `
    <div class="card" style="height:100%;text-align:center">

      <div class="game-instructions">
        Find the lucky number between 1 and 25.
        You have 7 guesses.
      </div>

      <div
        class="number-board"
        id="numberBoard"
      ></div>

      <div
        id="numberFeedback"
        class="feedback"
      >
        Pick a number.
      </div>

    </div>
  `;

  const board =
    $("numberBoard");

  for (let i = 1; i <= 25; i++) {

    const button =
      document.createElement("button");

    button.className = "number-tile";
    button.textContent = i;

    button.addEventListener(
      "click",
      () => guess(i,button)
    );

    board.appendChild(button);
  }

  function guess(number,button) {

    if (button.disabled) return;

    attempts++;

    button.disabled = true;
    button.style.opacity = ".35";

    if (number === lucky) {

      button.style.background =
        "#4c9d6c";

      finishLevel(
        true,
        130 + Math.max(0,50 - attempts * 5),
        `You found the lucky number ${lucky}! 🔢`
      );

      return;
    }

    if (number < lucky) {

      $("numberFeedback").textContent =
        `${number} is too low.`;

    } else {

      $("numberFeedback").textContent =
        `${number} is too high.`;
    }

    if (attempts >= 7) {

      finishLevel(
        false,
        0,
        `The lucky number was ${lucky}.`
      );
    }
  }

  state.gameCleanup = () => {};
}


/* =========================================================
   GAME 14
   GIN RUMMY
   ========================================================= */

function gameGinRummy() {

  const area = $("gameArea");

  const suits = ["♥","♦","♣","♠"];

  const deck = [];

  suits.forEach(suit => {

    for (let rank = 1; rank <= 13; rank++) {

      deck.push({
        rank,
        suit
      });
    }
  });

  const hand =
    shuffle(deck).slice(0,8);

  let selected = [];

  area.innerHTML = `
    <div class="card" style="height:100%;overflow:auto;text-align:center">

      <div class="game-instructions">
        Select three cards that form a set
        or three consecutive cards of the same suit.
      </div>

      <div class="rummy-table">
        <strong id="rummyFeedback">
          Choose your meld.
        </strong>
      </div>

      <div
        id="rummyHand"
        class="hand"
      ></div>

      <button
        class="btn green"
        id="rummyPlay"
      >
        Play Selected Cards
      </button>

    </div>
  `;

  const handEl = $("rummyHand");

  function rankName(rank) {

    if (rank === 1) return "A";
    if (rank === 11) return "J";
    if (rank === 12) return "Q";
    if (rank === 13) return "K";

    return rank;
  }

  function render() {

    handEl.innerHTML = "";

    hand.forEach((card,index) => {

      const button =
        document.createElement("button");

      button.className =
        "playing-card";

      if (selected.includes(index)) {
        button.classList.add("selected");
      }

      button.innerHTML =
        `<span>${rankName(card.rank)}</span>
         <span>${card.suit}</span>`;

      button.addEventListener(
        "click",
        () => {

          if (selected.includes(index)) {

            selected =
              selected.filter(i => i !== index);

          } else if (selected.length < 3) {

            selected.push(index);
          }

          render();
        }
      );

      handEl.appendChild(button);
    });
  }

  $("rummyPlay").addEventListener(
    "click",
    () => {

      if (selected.length !== 3) {

        $("rummyFeedback").textContent =
          "Choose exactly three cards.";

        return;
      }

      const cards =
        selected.map(i => hand[i]);

      const sameRank =
        cards.every(
          card => card.rank === cards[0].rank
        );

      const sameSuit =
        cards.every(
          card => card.suit === cards[0].suit
        );

      const ranks =
        cards
          .map(c => c.rank)
          .sort((a,b) => a-b);

      const run =
        sameSuit &&
        (
          ranks[1] === ranks[0] + 1 &&
          ranks[2] === ranks[1] + 1
        );

      if (sameRank || run) {

        finishLevel(
          true,
          180,
          "Gin! That's a valid meld. 🃏"
        );

      } else {

        $("rummyFeedback").textContent =
          "That's not a valid meld. Try another combination.";
      }
    }
  );

  render();

  state.gameCleanup = () => {};
}


/* =========================================================
   GAME 15
   BUFFALO SLOTS
   ========================================================= */

function gameBuffaloSlots() {

  const area = $("gameArea");

  const symbols = [
    "🐃",
    "🦌",
    "⭐",
    "💗",
    "7️⃣"
  ];

  let spins = 0;
  let tokens = 100;

  area.innerHTML = `
    <div class="card slot-machine" style="height:100%">

      <h2>🐃 Buffalo Slots</h2>

      <div class="game-instructions">
        Spin up to 10 times. Match symbols to earn tokens.
      </div>

      <div
        class="small"
        id="slotTokens"
      >
        Tokens: 100
      </div>

      <div class="reels">

        <div class="reel" id="reel1">❔</div>
        <div class="reel" id="reel2">❔</div>
        <div class="reel" id="reel3">❔</div>

      </div>

      <div
        id="slotFeedback"
        class="feedback"
      >
        Spin to begin.
      </div>

      <button
        class="btn gold"
        id="slotSpin"
      >
        SPIN 🎰
      </button>

    </div>
  `;

  const reels = [
    $("reel1"),
    $("reel2"),
    $("reel3")
  ];

  $("slotSpin").addEventListener(
    "click",
    async () => {

      if (spins >= 10) return;

      spins++;

      tokens -= 10;

      $("slotTokens").textContent =
        `Tokens: ${tokens}`;

      for (let i = 0; i < 8; i++) {

        reels.forEach(reel => {

          reel.textContent =
            symbols[randomInt(0,symbols.length - 1)];
        });

        await sleep(55);
      }

      const result =
        reels.map(r => r.textContent);

      if (
        result[0] === result[1] &&
        result[1] === result[2]
      ) {

        const win =
          result[0] === "7️⃣"
            ? 250
            : 100;

        tokens += win;

        $("slotFeedback").textContent =
          `JACKPOT! +${win} tokens! 🎉`;

      } else if (
        result[0] === result[1] ||
        result[1] === result[2] ||
        result[0] === result[2]
      ) {

        tokens += 25;

        $("slotFeedback").textContent =
          "+25 tokens!";

      } else {

        $("slotFeedback").textContent =
          "No match. Spin again!";
      }

      $("slotTokens").textContent =
        `Tokens: ${tokens}`;

      if (spins >= 10) {

        $("slotSpin").disabled = true;

        setTimeout(() => {

          finishLevel(
            tokens >= 125,
            100 + Math.min(100,tokens),
            tokens >= 125
              ? `You finished with ${tokens} tokens! 🎰`
              : "The reels weren't feeling generous enough this time."
          );

        },500);
      }
    }
  );

  state.gameCleanup = () => {};
}


/* =========================================================
   GAME 16
   DOLPHIN DIVE
   ========================================================= */

function gameDolphinDive() {

  const area = $("gameArea");

  area.innerHTML = `
    <div class="dive-field" id="diveField">

      <div
        class="dolphin"
        id="dolphin"
      >
        🐬
      </div>

      <div
        class="feedback"
        id="diveFeedback"
        style="
          position:absolute;
          top:12px;
          left:0;
          right:0;
          z-index:8;
        "
      >
        Pearls: 0 / 8
      </div>

      <button
        id="diveUp"
        class="move-btn"
        style="
          position:absolute;
          bottom:15px;
          left:15px;
          width:calc(50% - 22px);
          z-index:10;
        "
      >
        ▲ Dive Up
      </button>

      <button
        id="diveDown"
        class="move-btn"
        style="
          position:absolute;
          bottom:15px;
          right:15px;
          width:calc(50% - 22px);
          z-index:10;
        "
      >
        ▼ Dive Down
      </button>

    </div>
  `;

  const field = $("diveField");
  const dolphin = $("dolphin");

  let y = 42;
  let pearls = 0;
  let lives = 3;
  let running = true;

  const objects = [];

  function updateDolphin() {

    y =
      clamp(y,10,82);

    dolphin.style.top =
      `${y}%`;
  }

  function createObject() {

    const isPearl =
      Math.random() > .4;

    const obj =
      document.createElement("div");

    obj.className =
      isPearl
        ? "pearl"
        : "dive-object";

    obj.textContent =
      isPearl
        ? "🫧"
        : "🪨";

    obj.style.top =
      `${randomInt(15,80)}%`;

    obj.style.right = "-70px";

    field.appendChild(obj);

    objects.push({
      el: obj,
      pearl: isPearl,
      x: -70
    });
  }

  function move(direction) {

    y += direction;

    updateDolphin();
  }

  $("diveUp").addEventListener(
    "pointerdown",
    () => move(-9)
  );

  $("diveDown").addEventListener(
    "pointerdown",
    () => move(9)
  );

  let lastSpawn = 0;

  function animate(time) {

    if (!running) return;

    if (time - lastSpawn > 750) {

      createObject();

      lastSpawn = time;
    }

    objects.forEach(obj => {

      obj.x += 4.2;

      obj.el.style.right =
        `${obj.x}px`;
    });

    for (let i = objects.length - 1; i >= 0; i--) {

      const obj = objects[i];

      const top =
        parseFloat(obj.el.style.top);

      const horizontal =
        obj.x > field.clientWidth * .05 &&
        obj.x < field.clientWidth * .25;

      const vertical =
        Math.abs(top - y) < 11;

      if (horizontal && vertical) {

        if (obj.pearl) {

          pearls++;

          $("diveFeedback").textContent =
            `Pearls: ${pearls} / 8`;

        } else {

          lives--;

          $("diveFeedback").textContent =
            `Hit! ${lives} lives left.`;

          if (lives <= 0) {

            running = false;

            finishLevel(
              false,
              0,
              `The rocks got you. You collected ${pearls}/8 pearls.`
            );

            return;
          }
        }

        obj.el.remove();

        objects.splice(i,1);

      } else if (obj.x > field.clientWidth + 100) {

        obj.el.remove();

        objects.splice(i,1);
      }
    }

    if (pearls >= 8) {

      running = false;

      finishLevel(
        true,
        150,
        "You collected eight pearls and made it safely through the water! 🐬"
      );

      return;
    }

    requestAnimationFrame(animate);
  }

  updateDolphin();

  const frame =
    requestAnimationFrame(animate);

  state.gameCleanup = () => {

    running = false;

    cancelAnimationFrame(frame);

    objects.forEach(obj => {
      obj.el.remove();
    });
  };
}


/* =========================================================
   LULU TRIVIA
   ========================================================= */

const LULU_TRIVIA = [
  {
    q:"What is Lulu's favourite colour?",
    a:["Baby pink","Baby blue","Burgundy","Purple"]
  },

  {
    q:"What is Lulu's favourite number?",
    a:["3","7","6","9"]
  },

  {
    q:"Which animal does Lulu love?",
    a:["Dolphins","Lions","Penguins","Koalas"]
  },

  {
    q:"What does Lulu love to eat?",
    a:["Sushi","Pizza","Tacos","Curry"]
  },

  {
    q:"What did Lulu study at university?",
    a:["Psychology","Law","Medicine","Art"]
  },

  {
    q:"Which movie is one of Lulu's favourites?",
    a:["Me Before You","Titanic","Frozen","The Notebook"]
  },

  {
    q:"What card game does Lulu like?",
    a:["Poker","Uno","Go Fish","Solitaire"]
  },

  {
    q:"What kind of songs does Lulu like?",
    a:["Sad songs","Country songs only","Heavy metal only","Opera only"]
  },

  {
    q:"What type of writing does Lulu enjoy?",
    a:["Poetry","News reports","Instruction manuals","Recipes only"]
  },

  {
    q:"How many nephews does Lulu have?",
    a:["4","2","3","5"]
  },

  {
    q:"How many nieces does Lulu have?",
    a:["1","2","3","4"]
  },

  {
    q:"What colour are Lulu's eyes?",
    a:["Green","Blue","Brown","Hazel"]
  },

  {
    q:"What star sign is Lulu?",
    a:["Leo","Cancer","Virgo","Libra"]
  },

  {
    q:"What is Lulu afraid of?",
    a:["Drowning","Flying","Heights","Spiders"]
  },

  {
    q:"How many siblings does Lulu have?",
    a:["5","3","4","6"]
  },

  {
    q:"What are Lulu's dogs called?",
    a:["Aayla and Arlo","Luna and Milo","Bella and Max","Coco and Teddy"]
  }
];


/* =========================================================
   GAME 17
   LULU TRIVIA
   ========================================================= */

function gameLuluTrivia() {

  const area = $("gameArea");

  const questions =
    shuffle(LULU_TRIVIA).slice(0,10);

  let index = 0;
  let correct = 0;
  let locked = false;

  area.innerHTML = `
    <div class="card quiz-box" style="height:100%;overflow:auto">

      <div
        class="trivia-image"
      >
        💗
      </div>

      <div
        id="luluTriviaCount"
        class="small"
      ></div>

      <h2 id="luluTriviaQuestion"></h2>

      <div
        id="luluTriviaAnswers"
        class="choice-grid"
      ></div>

      <div
        id="luluTriviaFeedback"
        class="feedback"
      ></div>

    </div>
  `;

  function render() {

    locked = false;

    const current =
      questions[index];

    $("luluTriviaCount").textContent =
      `Question ${index + 1} of ${questions.length}`;

    $("luluTriviaQuestion").textContent =
      current.q;

    const answers =
      shuffle(
        current.a.map(
          (text,i) => ({
            text,
            correct: i === 0
          })
        )
      );

    const container =
      $("luluTriviaAnswers");

    container.innerHTML = "";

    answers.forEach(answer => {

      const button =
        document.createElement("button");

      button.className = "choice";

      button.textContent =
        answer.text;

      button.addEventListener(
        "click",
        () => choose(answer.correct,button)
      );

      container.appendChild(button);
    });
  }

  function choose(isCorrect,button) {

    if (locked) return;

    locked = true;

    if (isCorrect) {

      correct++;

      button.classList.add("correct");

      $("luluTriviaFeedback").textContent =
        "Correct! 💗";

    } else {

      button.classList.add("wrong");

      $("luluTriviaFeedback").textContent =
        "Not this one!";
    }

    setTimeout(() => {

      index++;

      if (index >= questions.length) {

        finishLevel(
          correct >= 6,
          correct * 20,
          correct >= 6
            ? `You got ${correct}/10 about Lulu! 💗`
            : `You got ${correct}/10. You need 6 correct answers.`
        );

      } else {

        $("luluTriviaFeedback").textContent = "";

        render();
      }

    },650);
  }

  render();

  state.gameCleanup = () => {
    locked = true;
  };
}


/* =========================================================
   GAME 18
   MILLION TOKEN SLOT
   ========================================================= */

function gameMillionSlot() {

  const area = $("gameArea");

  const symbols = [
    "💎",
    "💗",
    "⭐",
    "7️⃣",
    "👑"
  ];

  let spins = 0;
  let jackpotProgress = 0;
  let running = true;

  area.innerHTML = `
    <div class="card slot-machine" style="height:100%">

      <div class="jackpot">

        <div class="small">
          MEGA JACKPOT
        </div>

        <div class="jackpot-number">
          1,000,000
        </div>

        <div class="small">
          TOKENS
        </div>

      </div>

      <div class="reels">

        <div class="reel" id="million1">?</div>
        <div class="reel" id="million2">?</div>
        <div class="reel" id="million3">?</div>

      </div>

      <div
        id="millionFeedback"
        class="feedback"
      >
        Spin for the jackpot.
      </div>

      <button
        id="millionSpin"
        class="btn gold"
      >
        SPIN FOR 1,000,000 🪙
      </button>

    </div>
  `;

  const reels = [
    $("million1"),
    $("million2"),
    $("million3")
  ];

  $("millionSpin").addEventListener(
    "click",
    async () => {

      if (!running || spins >= 8) return;

      spins++;

      for (let i = 0; i < 10; i++) {

        reels.forEach(reel => {

          reel.textContent =
            symbols[randomInt(0,symbols.length - 1)];

        });

        await sleep(60);
      }

      const result =
        reels.map(r => r.textContent);

      if (
        result[0] === "7️⃣" &&
        result[1] === "7️⃣" &&
        result[2] === "7️⃣"
      ) {

        jackpotProgress = 1000000;

        state.tokens += 1000000;

        finishLevel(
          true,
          300,
          "MEGA JACKPOT! 1,000,000 TOKENS! 🪙💗"
        );

        return;
      }

      if (
        result[0] === result[1] &&
        result[1] === result[2]
      ) {

        jackpotProgress += 250;

        $("millionFeedback").textContent =
          "Triple match! +250 jackpot progress!";
      } else if (
        result[0] === result[1] ||
        result[1] === result[2] ||
        result[0] === result[2]
      ) {

        jackpotProgress += 80;

        $("millionFeedback").textContent =
          "Pair match! +80 jackpot progress!";
      } else {

        $("millionFeedback").textContent =
          "No match. Keep spinning!";
      }

      if (spins >= 8) {

        const passed =
          jackpotProgress >= 300;

        running = false;

        finishLevel(
          passed,
          passed ? 260 : 0,
          passed
            ? "The million-token machine paid out a huge bonus! 💰"
            : "So close! You need 300 jackpot-progress points to pass."
        );
      }
    }
  );

  state.gameCleanup = () => {
    running = false;
  };
}


/* =========================================================
   GAME 19
   LULU PUZZLE
   ========================================================= */

function gameLuluPuzzle() {

  const area = $("gameArea");

  let tiles = [
    "💗","🌸","🐬",
    "⭐","🌹","🦋",
    "💌","🌻",""
  ];

  function shufflePuzzle() {

    for (let i = 0; i < 80; i++) {

      const empty =
        tiles.indexOf("");

      const possible = [];

      const row =
        Math.floor(empty / 3);

      const col =
        empty % 3;

      if (row > 0)
        possible.push(empty - 3);

      if (row < 2)
        possible.push(empty + 3);

      if (col > 0)
        possible.push(empty - 1);

      if (col < 2)
        possible.push(empty + 1);

      const chosen =
        possible[randomInt(0,possible.length - 1)];

      [tiles[empty],tiles[chosen]] =
        [tiles[chosen],tiles[empty]];
    }
  }

  shufflePuzzle();

  let moves = 0;

  const solved = [
    "💗","🌸","🐬",
    "⭐","🌹","🦋",
    "💌","🌻",""
  ];

  area.innerHTML = `
    <div class="card" style="height:100%;text-align:center">

      <div class="game-instructions">
        Slide the tiles into the correct order.
      </div>

      <div
        id="puzzleGrid"
        class="puzzle-grid"
      ></div>

      <div
        id="puzzleFeedback"
        class="feedback"
      >
        Moves: 0
      </div>

    </div>
  `;

  const grid = $("puzzleGrid");

  function render() {

    grid.innerHTML = "";

    tiles.forEach((tile,index) => {

      const button =
        document.createElement("button");

      button.className =
        "puzzle-tile" +
        (!tile ? " empty" : "");

      button.textContent =
        tile;

      button.addEventListener(
        "click",
        () => move(index)
      );

      grid.appendChild(button);
    });
  }

  function move(index) {

    const empty =
      tiles.indexOf("");

    const row =
      Math.floor(index / 3);

    const col =
      index % 3;

    const er =
      Math.floor(empty / 3);

    const ec =
      empty % 3;

    const adjacent =
      Math.abs(row - er) +
      Math.abs(col - ec) === 1;

    if (!adjacent) return;

    [tiles[index],tiles[empty]] =
      [tiles[empty],tiles[index]];

    moves++;

    $("puzzleFeedback").textContent =
      `Moves: ${moves}`;

    render();

    if (
      tiles.every(
        (tile,index) =>
          tile === solved[index]
      )
    ) {

      finishLevel(
        true,
        Math.max(100,180 - moves),
        `Puzzle solved in ${moves} moves! 🧩`
      );
    }
  }

  render();

  state.gameCleanup = () => {};
}


/* =========================================================
   GAME 20
   FINAL MEMORY
   ========================================================= */

function gameFinalMemory() {

  const area = $("gameArea");

  const symbols = [
    "💗",
    "⭐",
    "🐬",
    "🌹"
  ];

  let sequence = [];
  let player = [];
  let round = 0;
  let accepting = false;

  area.innerHTML = `
    <div class="card" style="height:100%;text-align:center">

      <div class="game-instructions">
        This is the final memory test.
        Remember a sequence that gets longer every round.
      </div>

      <div
        id="finalMemoryRound"
        class="feedback"
      >
        Round 1
      </div>

      <div
        id="sequenceDisplay"
        class="sequence-display"
      >
        👀
      </div>

      <div
        id="sequenceButtons"
        class="sequence-buttons"
      ></div>

      <div
        id="finalMemoryFeedback"
        class="feedback"
      >
        Watch...
      </div>

    </div>
  `;

  const buttonArea =
    $("sequenceButtons");

  symbols.forEach((symbol,index) => {

    const button =
      document.createElement("button");

    button.className =
      "sequence-button";

    button.textContent =
      symbol;

    button.dataset.index =
      index;

    button.addEventListener(
      "click",
      () => choose(index)
    );

    buttonArea.appendChild(button);
  });

  async function showSequence() {

    accepting = false;

    player = [];

    $("finalMemoryFeedback").textContent =
      "Watch the sequence...";

    const display =
      $("sequenceDisplay");

    for (const value of sequence) {

      display.textContent =
        symbols[value];

      await sleep(600);

      display.textContent =
        "•";

      await sleep(250);
    }

    display.textContent =
      "Your turn";

    accepting = true;
  }

  function startRound() {

    round++;

    $("finalMemoryRound").textContent =
      `Round ${round} of 6`;

    sequence.push(
      randomInt(0,symbols.length - 1)
    );

    showSequence();
  }

  function choose(index) {

    if (!accepting) return;

    const expected =
      sequence[player.length];

    if (index !== expected) {

      accepting = false;

      finishLevel(
        false,
        0,
        `The final sequence got you. You reached round ${round}.`
      );

      return;
    }

    player.push(index);

    $("finalMemoryFeedback").textContent =
      `${player.length} / ${sequence.length}`;

    if (player.length === sequence.length) {

      accepting = false;

      if (round >= 6) {

        finishLevel(
          true,
          180,
          "You conquered the final memory challenge! 🧠💗"
        );

      } else {

        setTimeout(
          startRound,
          650
        );
      }
    }
  }

  startRound();

  state.gameCleanup = () => {
    accepting = false;
  };
}


/* =========================================================
   50 FINAL LILIANA QUESTIONS
   ========================================================= */

const FINAL_LILIANA_50 = [

  {
    q:"What is Liliana's favourite colour?",
    a:["Baby pink","Baby blue","Burgundy","Purple"]
  },

  {
    q:"What is Liliana's favourite number?",
    a:["3","6","7","9"]
  },

  {
    q:"Which animal is one of Liliana's favourites?",
    a:["Dolphins","Tigers","Koalas","Foxes"]
  },

  {
    q:"What food does Liliana love?",
    a:["Sushi","Pizza","Burgers","Pasta"]
  },

  {
    q:"What did Liliana study at university?",
    a:["Psychology","Law","Nursing","Design"]
  },

  {
    q:"Which film is a favourite of Liliana's?",
    a:["Me Before You","Frozen","Avatar","Titanic"]
  },

  {
    q:"Which card game does Liliana enjoy?",
    a:["Poker","Uno","Snap","Go Fish"]
  },

  {
    q:"What kind of songs does Liliana like?",
    a:["Sad songs","Only classical music","Only metal","Only country"]
  },

  {
    q:"What form of writing does Liliana enjoy?",
    a:["Poetry","News articles","Technical manuals","Travel guides"]
  },

  {
    q:"Does Liliana like children?",
    a:["Yes","No","Only teenagers","Only babies"]
  },

  {
    q:"What does Liliana want to be one day?",
    a:["A mum","A pilot","A chef","A singer"]
  },

  {
    q:"What does Liliana hope to have?",
    a:["A baby girl","Twin boys","Three sons","A puppy only"]
  },

  {
    q:"How many nieces does Liliana have?",
    a:["1","2","3","4"]
  },

  {
    q:"How many nephews does Liliana have?",
    a:["4","1","2","6"]
  },

  {
    q:"How many siblings does Liliana have?",
    a:["5","3","4","7"]
  },

  {
    q:"What colour are Liliana's eyes?",
    a:["Green","Blue","Brown","Hazel"]
  },

  {
    q:"How many piercings does Liliana have?",
    a:["4","2","3","5"]
  },

  {
    q:"What is the name of one of Liliana's dogs?",
    a:["Aayla","Lola","Mika","Yuna"]
  },

  {
    q:"What is the name of Liliana's other dog?",
    a:["Arlo","Kai","Rene","Bree"]
  },

  {
    q:"Which pair are Liliana's dogs?",
    a:["Aayla and Arlo","Luna and Milo","Bella and Max","Coco and Teddy"]
  },

  {
    q:"What is Liliana's star sign?",
    a:["Leo","Cancer","Virgo","Gemini"]
  },

  {
    q:"What is Liliana afraid of?",
    a:["Drowning","Flying","Thunder","Spiders"]
  },

  {
    q:"How long have Bree and Liliana been best friends?",
    a:["6 years","2 years","4 years","10 years"]
  },

  {
    q:"Which month is Liliana's birthday?",
    a:["July","June","August","May"]
  },

  {
    q:"Which day of the month is Liliana's birthday?",
    a:["22","7","16","30"]
  },

  {
    q:"What is Liliana's birthday date?",
    a:["July 22","June 22","July 12","August 22"]
  },

  {
    q:"Which Japanese food is especially associated with Liliana's favourites?",
    a:["Sushi","Ramen","Tempura","Udon"]
  },

  {
    q:"Which sea animal is one of Liliana's favourite animals?",
    a:["Dolphin","Shark","Seal","Octopus"]
  },

  {
    q:"Which flower does Liliana like?",
    a:["Sunflowers","Tulips","Daisies","Lilies"]
  },

  {
    q:"Which other flower does Liliana like?",
    a:["Roses","Orchids","Irises","Lavender"]
  },

  {
    q:"What type of music can make up Liliana's sad-song playlist?",
    a:["Sad songs","Comedy songs","Marching music","Instrumental alarms"]
  },

  {
    q:"What type of creative writing does Liliana enjoy?",
    a:["Poetry","Legal writing","Scientific papers","Instruction sheets"]
  },

  {
    q:"What subject is connected to Liliana's university studies?",
    a:["Psychology","Physics","Accounting","Engineering"]
  },

  {
    q:"Which film title belongs on Liliana's favourites list?",
    a:["Me Before You","The Lion King","Shrek","Barbie"]
  },

  {
    q:"Which game involving cards does Liliana like?",
    a:["Poker","Bridge","Blackjack only","Baccarat only"]
  },

  {
    q:"Which activity is Liliana known to enjoy?",
    a:["Gambling","Fishing","Golf","Surfing"]
  },

  {
    q:"Which description fits Liliana?",
    a:["Sweet","Cold","Uncaring","Shy with everyone"]
  },

  {
    q:"Which word is another description of Liliana?",
    a:["Caring","Cruel","Forgetful","Unfriendly"]
  },

  {
    q:"Which personality trait is associated with Liliana?",
    a:["Charismatic","Boring","Hostile","Distant"]
  },

  {
    q:"Which personality trait also fits Liliana?",
    a:["Flirtatious","Grumpy","Silent","Unapproachable"]
  },

  {
    q:"Which colour is more specific than simply saying pink?",
    a:["Baby pink","Neon green","Navy blue","Orange"]
  },

  {
    q:"Which number should you associate with Liliana?",
    a:["3","13","30","33"]
  },

  {
    q:"Which family detail about Liliana is correct?",
    a:["She has 1 niece","She has 5 nieces","She has no nieces","She has 8 nieces"]
  },

  {
    q:"Which family detail is correct?",
    a:["She has 4 nephews","She has 2 nephews","She has 7 nephews","She has no nephews"]
  },

  {
    q:"Which family number belongs to Liliana's siblings?",
    a:["5","2","8","10"]
  },

  {
    q:"Which eye colour belongs to Liliana?",
    a:["Green","Grey","Amber","Black"]
  },

  {
    q:"Which piercing count belongs to Liliana?",
    a:["4","1","6","8"]
  },

  {
    q:"Which star sign belongs to Liliana?",
    a:["Leo","Aries","Taurus","Pisces"]
  },

  {
    q:"Which statement about Bree and Liliana is correct?",
    a:["They have been best friends for 6 years","They met last month","They have been friends for 1 year","They have never met"]
  },

  {
    q:"Who is Liliana's best friend?",
    a:["Bree","Lola","Yuna","Rene"]
  }
];


/* =========================================================
   GAME 21
   FINAL QUIZ
   ========================================================= */

function gameFinalQuiz() {

  const area = $("gameArea");

  const questions =
    shuffle(FINAL_LILIANA_50);

  let index = 0;
  let correct = 0;
  let locked = false;

  area.innerHTML = `
    <div class="card quiz-box" style="height:100%;overflow:auto">

      <div class="quiz-progress">
        <div id="finalQuizProgress"></div>
      </div>

      <div
        id="finalQuizCount"
        class="small"
      ></div>

      <h2 id="finalQuizQuestion"></h2>

      <div
        id="finalQuizAnswers"
        class="choice-grid"
      ></div>

      <div
        id="finalQuizFeedback"
        class="feedback"
      ></div>

    </div>
  `;

  function renderQuestion() {

    locked = false;

    const current =
      questions[index];

    $("finalQuizCount").textContent =
      `Question ${index + 1} of 50`;

    $("finalQuizQuestion").textContent =
      current.q;

    $("finalQuizProgress").style.width =
      `${(index / 50) * 100}%`;

    const answers =
      shuffle(
        current.a.map(
          (text,i) => ({
            text,
            correct: i === 0
          })
        )
      );

    const container =
      $("finalQuizAnswers");

    container.innerHTML = "";

    answers.forEach(answer => {

      const button =
        document.createElement("button");

      button.className = "choice";

      button.textContent =
        answer.text;

      button.addEventListener(
        "click",
        () => choose(answer.correct,button)
      );

      container.appendChild(button);
    });
  }

  function choose(isCorrect,button) {

    if (locked) return;

    locked = true;

    [...$("finalQuizAnswers").children]
      .forEach(b => {
        b.disabled = true;
      });

    if (isCorrect) {

      correct++;

      button.classList.add("correct");

      $("finalQuizFeedback").textContent =
        "Correct! 💗";

    } else {

      button.classList.add("wrong");

      $("finalQuizFeedback").textContent =
        "Not quite!";
    }

    setTimeout(() => {

      index++;

      if (index >= 50) {

        $("finalQuizProgress").style.width =
          "100%";

        finishLevel(
          correct >= 30,
          correct * 12,
          correct >= 30
            ? `You got ${correct}/50! You really know Lulu. 💗`
            : `You got ${correct}/50. You need at least 30 correct answers to pass.`
        );

      } else {

        $("finalQuizFeedback").textContent = "";

        renderQuestion();
      }

    },450);
  }

  renderQuestion();

  state.gameCleanup = () => {
    locked = true;
  };
}


/* =========================================================
   FINAL RESULT
   ========================================================= */

function showFinal() {

  stopCurrentGame();

  $("finalGreeting").textContent =
    `${state.playerName}, you made it through every level.`;

  $("finalScore").textContent =
    state.score;

  const reward =
    $("rewardBox");

  /*
     IMPORTANT:
     EXACTLY 3000 DOES NOT QUALIFY.
     ONLY 3001 OR MORE UNLOCKS THE PRIVATE CALL.
  */

  if (state.score > 3000) {

    reward.innerHTML = `
      <div class="reward-unlocked">

        <h2>
          📞 Private Call Unlocked!
        </h2>

        <p>
          You finished with more than 3,000 points.
        </p>

        <div class="big-number">
          ${state.score}
        </div>

        <p>
          Your final score qualifies for the private call reward. 💗
        </p>

      </div>
    `;

  } else {

    const needed =
      3001 - state.score;

    reward.innerHTML = `
      <div class="reward-locked">

        <h2>
          💗 Almost there
        </h2>

        <p>
          The private call requires a score of
          <strong>3,001+</strong>.
        </p>

        <p>
          Your score was
          <strong>${state.score}</strong>.
        </p>

        <p class="small">
          You needed ${needed} more point${needed === 1 ? "" : "s"}.
        </p>

      </div>
    `;
  }

  showScreen(screens.final);
}


/* =========================================================
   GLOBAL TOUCH / ZOOM PROTECTION
   ========================================================= */

document.addEventListener(
  "gesturestart",
  event => {
    event.preventDefault();
  },
  { passive:false }
);

document.addEventListener(
  "gesturechange",
  event => {
    event.preventDefault();
  },
  { passive:false }
);

document.addEventListener(
  "gestureend",
  event => {
    event.preventDefault();
  },
  { passive:false }
);


/* Prevent double-tap zoom while preserving normal buttons */

let lastTouchEnd = 0;

document.addEventListener(
  "touchend",
  event => {

    const now =
      Date.now();

    if (now - lastTouchEnd <= 280) {

      event.preventDefault();
    }

    lastTouchEnd = now;
  },
  { passive:false }
);


/* =========================================================
   INITIAL JOURNEY STATE
   ========================================================= */

renderJourney();

</script>

</body>
</html>

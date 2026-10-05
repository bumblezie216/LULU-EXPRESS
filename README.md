<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport"
      content="width=device-width,
               initial-scale=1.0,
               maximum-scale=1.0,
               user-scalable=no">
<title>Lulu Express 💗</title>
<style>
* {
    box-sizing: border-box;
    -webkit-tap-highlight-color: transparent;
}
html,
body {
    margin: 0;
    padding: 0;
    width: 100%;
    min-height: 100%;
    font-family: Arial, sans-serif;
    background: #160d18;
    color: white;
    overflow-x: hidden;
}
body {
    touch-action: manipulation;
}
button,
input {
    font-family: inherit;
}
button {
    touch-action: manipulation;
    cursor: pointer;
}
.screen {
    display: none;
    width: 100%;
    min-height: 100vh;
    padding: 18px 15px;
    background:
        radial-gradient(circle at 20% 15%, rgba(255,180,215,.18), transparent 28%),
        radial-gradient(circle at 80% 25%, rgba(180,150,255,.14), transparent 25%),
        linear-gradient(145deg, #120a16, #281326, #120a16);
}
.screen.active {
    display: flex;
    flex-direction: column;
    align-items: center;
}
.container {
    width: 100%;
    max-width: 600px;
    margin: auto;
}
.center {
    text-align: center;
}
.logo {
    font-size: 65px;
    margin-bottom: 5px;
}
h1 {
    font-size: clamp(32px, 9vw, 52px);
    margin: 5px 0 10px;
}
h2 {
    font-size: clamp(25px, 7vw, 38px);
    margin: 5px 0 12px;
}
h3 {
    margin: 10px 0;
}
p {
    line-height: 1.5;
}
.subtitle {
    color: #f2c5d9;
    font-size: 17px;
}
.card {
    width: 100%;
    background: rgba(255,255,255,.08);
    border: 1px solid rgba(255,255,255,.13);
    border-radius: 22px;
    padding: 18px;
    margin-top: 15px;
}
input {
    width: 100%;
    height: 52px;
    border-radius: 15px;
    border: 2px solid rgba(255,255,255,.18);
    background: rgba(0,0,0,.25);
    color: white;
    padding: 10px 14px;
    font-size: 17px;
    outline: none;
}
input:focus {
    border-color: #efa7c7;
}
.main-btn,
.secondary-btn,
.reset-btn {
    width: 100%;
    min-height: 52px;
    border-radius: 15px;
    margin-top: 12px;
    padding: 12px 15px;
    font-size: 16px;
    font-weight: bold;
}
.main-btn {
    background: #efa6c7;
    color: #321426;
}
.secondary-btn {
    background: rgba(255,255,255,.11);
    color: white;
    border: 1px solid rgba(255,255,255,.15);
}
.reset-btn {
    background: #a94f70;
    color: white;
}
.main-btn:active,
.secondary-btn:active,
.reset-btn:active,
.choice:active,
.big-action:active,
.animal:active,
.difficulty:active {
    transform: scale(.97);
}
.error {
    color: #ffb5ca;
    min-height: 24px;
    margin-top: 8px;
    font-weight: bold;
}
.level-label {
    color: #efa6c7;
    font-weight: bold;
    text-align: center;
    letter-spacing: 1px;
}
.game-box {
    width: 100%;
    max-width: 600px;
    margin: auto;
    background: rgba(255,255,255,.07);
    border-radius: 22px;
    padding: 18px;
    border: 1px solid rgba(255,255,255,.12);
}
.instruction {
    text-align: center;
    color: #ecd7e1;
    margin: 5px auto 18px;
}
.status {
    min-height: 27px;
    text-align: center;
    margin: 12px 0;
    font-weight: bold;
    color: #f3aecb;
}
.choice-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 10px;
}
.choice {
    width: 100%;
    min-height: 52px;
    padding: 12px;
    border-radius: 15px;
    background: rgba(255,255,255,.10);
    border: 1px solid rgba(255,255,255,.12);
    color: white;
    font-size: 16px;
    font-weight: bold;
    text-align: center;
}
.choice.correct {
    background: #477d63;
}
.choice.wrong {
    background: #984e67;
}
.big-action {
    display: block;
    width: min(220px, 65vw);
    height: min(220px, 65vw);
    margin: 20px auto;
    border-radius: 50%;
    background: #efa6c7;
    color: #351526;
    font-size: 22px;
    font-weight: 900;
}
.big-number {
    font-size: 65px;
    font-weight: 900;
    text-align: center;
    margin: 15px;
}
.progress {
    width: 100%;
    height: 13px;
    border-radius: 99px;
    background: rgba(255,255,255,.12);
    overflow: hidden;
    margin: 15px 0;
}
.progress-fill {
    width: 0%;
    height: 100%;
    background: #efa6c7;
    transition: width .15s;
}
.memory-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 8px;
    max-width: 400px;
    margin: auto;
}
.memory-card {
    aspect-ratio: 1;
    border: 0;
    border-radius: 12px;
    background: #351b35;
    color: transparent;
    font-size: 25px;
}
.memory-card.show {
    color: white;
    background: #74425f;
}
.animal-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 9px;
}
.animal {
    min-height: 82px;
    border-radius: 15px;
    background: rgba(255,255,255,.08);
    color: white;
    border: 1px solid rgba(255,255,255,.12);
    font-weight: bold;
    font-size: 15px;
}
.animal span {
    display: block;
    font-size: 30px;
    margin-bottom: 5px;
}
.animal.selected,
.difficulty.selected {
    background: #854d6a;
    border-color: #efa6c7;
}
.difficulty-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 9px;
}
.difficulty {
    min-height: 75px;
    border-radius: 15px;
    background: rgba(255,255,255,.08);
    color: white;
    border: 1px solid rgba(255,255,255,.12);
    font-weight: bold;
}
.derby-row {
    display: flex;
    align-items: center;
    gap: 8px;
    margin: 12px 0;
}
.derby-name {
    width: 80px;
    flex-shrink: 0;
    font-size: 13px;
}
.derby-track {
    flex: 1;
    height: 27px;
    background: rgba(255,255,255,.11);
    border-radius: 99px;
    overflow: hidden;
}
.derby-fill {
    width: 0%;
    height: 100%;
    background: #efa6c7;
    transition: width .12s;
}
.derby-rival {
    background: #9b6681;
}
canvas {
    display: block;
    width: 100%;
    max-width: 450px;
    height: auto;
    aspect-ratio: 1 / 1;
    background: #fff9fc;
    border-radius: 18px;
    margin: 10px auto;
    touch-action: none;
}
.word-grid {
    display: grid;
    grid-template-columns: repeat(8, 1fr);
    gap: 4px;
}
.word-cell {
    aspect-ratio: 1;
    border: 0;
    border-radius: 5px;
    background: rgba(255,255,255,.09);
    color: white;
    font-size: 14px;
    font-weight: bold;
}
.word-cell.selected {
    background: #a95f80;
}
.result-heart {
    font-size: 60px;
    text-align: center;
}
.score {
    text-align: center;
    font-size: 21px;
    margin: 10px 0;
}
@media (min-width: 600px) {
    .choice-grid {
        grid-template-columns: 1fr 1fr;
    }
}
</style>
</head>
<body>
<div id="app">
<!-- START -->
<section id="start" class="screen active">
    <div class="container center">
        <div class="logo">💗</div>
        <h1>Lulu Express</h1>
        <p class="subtitle">
            A special little journey made just for Lulu.
        </p>
        <div class="card">
            <button id="musicButton" class="secondary-btn">
                🎵 Music: OFF
            </button>
            <p>Enter your name</p>
            <input
                id="nameInput"
                type="text"
                maxlength="30"
                placeholder="Your name"
                autocomplete="off"
            >
            <div id="nameError" class="error"></div>
            <button id="startButton" class="main-btn">
                💗 START THE JOURNEY
            </button>
        </div>
    </div>
</section>
<!-- INTRO -->
<section id="intro" class="screen">
    <div class="container center">
        <div class="logo">🌸</div>
        <h1>The Journey Begins</h1>
        <p id="welcomeText" class="subtitle"></p>
        <div class="card">
            <p>
                There are 23 levels waiting for you.
                Complete each level to unlock the next.
            </p>
            <button id="beginButton" class="main-btn">
                START LEVEL 1
            </button>
        </div>
    </div>
</section>
<!-- GAME -->
<section id="game" class="screen">
    <div class="container">
        <div class="level-label" id="levelLabel"></div>
        <h2 id="gameTitle" class="center"></h2>
        <div id="gameBox" class="game-box"></div>
    </div>
</section>
<!-- LEVEL COMPLETE -->
<section id="complete" class="screen">
    <div class="container center">
        <div class="result-heart">💗</div>
        <h1>Level Complete!</h1>
        <p id="completeMessage" class="subtitle"></p>
        <div class="card">
            <button id="nextButton" class="main-btn">
                NEXT LEVEL →
            </button>
        </div>
    </div>
</section>
<!-- FINISH -->
<section id="finish" class="screen">
    <div class="container center">
        <div class="result-heart">🏆</div>
        <h1>Journey Complete!</h1>
        <p id="finishMessage" class="subtitle"></p>
        <div class="card">
            <div id="finalScore" class="score"></div>
            <div id="finalTokens" class="score"></div>
            <div id="specialReward"></div>
            <button id="resetButton" class="reset-btn">
                🔄 RESET JOURNEY
            </button>
        </div>
    </div>
</section>
</div>
<script>
"use strict";
/* =========================================================
   BASIC GAME STATE
========================================================= */
let playerName = "";
let currentLevel = 0;
let score = 0;
let tokens = 0;
let timer = null;
let musicTimer = null;
let audioContext = null;
const TOTAL_LEVELS = 23;
/* =========================================================
   SCREEN HELPERS
========================================================= */
const screens = {
    start: document.getElementById("start"),
    intro: document.getElementById("intro"),
    game: document.getElementById("game"),
    complete: document.getElementById("complete"),
    finish: document.getElementById("finish")
};
const gameBox = document.getElementById("gameBox");
function showScreen(name) {
    Object.values(screens).forEach(function(screen) {
        screen.classList.remove("active");
    });
    screens[name].classList.add("active");
    window.scrollTo(0, 0);
}
function stopEverything() {
    if (timer !== null) {
        clearInterval(timer);
        clearTimeout(timer);
        timer = null;
    }
}
/* =========================================================
   LEVEL COMPLETION
========================================================= */
function completeLevel(message, points, tokenAmount) {
    stopEverything();
    score += points || 100;
    tokens += tokenAmount || 100;
    document.getElementById("completeMessage").textContent =
        message || "You completed the level!";
    showScreen("complete");
}
/* =========================================================
   LEVEL DATA
========================================================= */
const levels = [
    "Broken Hearts",
    "Memory Vault",
    "Pressure Quiz",
    "High Roller",
    "Mind Games",
    "The Bluff",
    "Survival Round",
    "Admirer Race",
    "Heartbreak Chamber",
    "Heartbreak Boxing Match",
    "Perfect Match",
    "Who Knows Liliana Best?",
    "Reaction Gauntlet",
    "Heart Hunt",
    "Love Lock",
    "Cupid Shootout",
    "The Countdown",
    "Ultimate Gamble",
    "Admirer's Last Stand",
    "Liliana's Word Find",
    "Draw a Sunflower",
    "Lulu Derby",
    "Final Challenge"
];
/* =========================================================
   LOAD LEVEL
========================================================= */
function loadLevel() {
    stopEverything();
    if (currentLevel >= TOTAL_LEVELS) {
        finishJourney(false);
        return;
    }
    document.getElementById("levelLabel").textContent =
        "LEVEL " + (currentLevel + 1) + " OF " + TOTAL_LEVELS;
    document.getElementById("gameTitle").textContent =
        levels[currentLevel];
    gameBox.innerHTML = "";
    showScreen("game");
    switch (currentLevel) {
        case 0:
            brokenHearts();
            break;
        case 1:
            memoryVault();
            break;
        case 2:
            pressureQuiz();
            break;
        case 3:
            highRoller();
            break;
        case 4:
            mindGames();
            break;
        case 5:
            bluff();
            break;
        case 6:
            survival();
            break;
        case 7:
            admirerRace();
            break;
        case 8:
            heartbreakChamber();
            break;
        case 9:
            boxing();
            break;
        case 10:
            perfectMatch();
            break;
        case 11:
            whoKnows();
            break;
        case 12:
            reaction();
            break;
        case 13:
            heartHunt();
            break;
        case 14:
            loveLock();
            break;
        case 15:
            cupid();
            break;
        case 16:
            countdown();
            break;
        case 17:
            ultimateGamble();
            break;
        case 18:
            lastStand();
            break;
        case 19:
            wordFind();
            break;
        case 20:
            sunflower();
            break;
        case 21:
            derby();
            break;
        case 22:
            finalQuiz();
            break;
    }
}
/* =========================================================
   BUTTON HELPER
========================================================= */
function button(text, action, className) {
    const b = document.createElement("button");
    b.type = "button";
    b.textContent = text;
    b.className = className || "choice";
    b.addEventListener("click", action);
    return b;
}
function instruction(text) {
    const p = document.createElement("p");
    p.className = "instruction";
    p.textContent = text;
    return p;
}
function shuffle(array) {
    const result = array.slice();
    for (let i = result.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        const temp = result[i];
        result[i] = result[j];
        result[j] = temp;
    }
    return result;
}
/* =========================================================
   LEVEL 1 — BROKEN HEARTS
========================================================= */
function brokenHearts() {
    gameBox.appendChild(
        instruction(
            "Tap all 10 broken hearts to repair them."
        )
    );
    const grid = document.createElement("div");
    grid.className = "choice-grid";
    let fixed = 0;
    for (let i = 0; i < 10; i++) {
        const b = button("💔", function() {
            if (b.disabled) return;
            b.disabled = true;
            b.textContent = "❤️";
            fixed++;
            if (fixed === 10) {
                completeLevel(
                    "Every broken heart has been repaired! ❤️",
                    100,
                    100
                );
            }
        });
        b.style.fontSize = "30px";
        grid.appendChild(b);
    }
    gameBox.appendChild(grid);
}
/* =========================================================
   LEVEL 2 — MEMORY
========================================================= */
function memoryVault() {
    gameBox.appendChild(
        instruction(
            "Find the 4 matching pairs. Tap two cards at a time."
        )
    );
    const values = shuffle([
        "🌸","🌸",
        "💗","💗",
        "⭐","⭐",
        "🦋","🦋"
    ]);
    const grid = document.createElement("div");
    grid.className = "memory-grid";
    let first = null;
    let locked = false;
    let pairs = 0;
    values.forEach(function(value) {
        const card = document.createElement("button");
        card.type = "button";
        card.className = "memory-card";
        card.textContent = value;
        card.addEventListener("click", function() {
            if (
                locked ||
                card.classList.contains("show")
            ) {
                return;
            }
            card.classList.add("show");
            if (first === null) {
                first = card;
                return;
            }
            if (first.textContent === card.textContent) {
                pairs++;
                first = null;
                if (pairs === 4) {
                    completeLevel(
                        "The Memory Vault has been unlocked! 🔐",
                        120,
                        120
                    );
                }
            } else {
                const oldCard = first;
                locked = true;
                setTimeout(function() {
                    oldCard.classList.remove("show");
                    card.classList.remove("show");
                    first = null;
                    locked = false;
                }, 500);
            }
        });
        grid.appendChild(card);
    });
    gameBox.appendChild(grid);
}
/* =========================================================
   GENERIC QUIZ
========================================================= */
function simpleQuiz(questionList, rewardMessage, points) {
    let question = 0;
    let answering = false;
    const title = document.createElement("h3");
    title.className = "center";
    const choices = document.createElement("div");
    choices.className = "choice-grid";
    const status = document.createElement("div");
    status.className = "status";
    gameBox.appendChild(title);
    gameBox.appendChild(choices);
    gameBox.appendChild(status);
    function showQuestion() {
        answering = false;
        const q = questionList[question];
        title.textContent =
            (question + 1) +
            " / " +
            questionList.length +
            " — " +
            q.question;
        choices.innerHTML = "";
        shuffle(q.answers).forEach(function(answer) {
            choices.appendChild(
                button(answer, function() {
                    if (answering) return;
                    if (answer === q.correct) {
                        answering = true;
                        status.textContent = "Correct! 💗";
                        question++;
                        if (question >= questionList.length) {
                            setTimeout(function() {
                                completeLevel(
                                    rewardMessage,
                                    points,
                                    points
                                );
                            }, 300);
                        } else {
                            setTimeout(showQuestion, 300);
                        }
                    } else {
                        status.textContent =
                            "Not quite. Try again! 💗";
                    }
                })
            );
        });
    }
    showQuestion();
}
/* =========================================================
   LEVEL 3 — PRESSURE QUIZ
========================================================= */
function pressureQuiz() {
    gameBox.appendChild(
        instruction(
            "Answer 5 simple questions. There is no penalty for a wrong answer."
        )
    );
    simpleQuiz([
        {
            question: "What is Liliana's favourite colour?",
            answers: ["Baby pink","Purple","Burgundy","Blue"],
            correct: "Baby pink"
        },
        {
            question: "What food does Liliana love?",
            answers: ["Sushi","Pizza","Pasta","Burgers"],
            correct: "Sushi"
        },
        {
            question: "Which animal does Liliana love?",
            answers: ["Dolphins","Tigers","Cats","Koalas"],
            correct: "Dolphins"
        },
        {
            question: "What is Liliana's zodiac sign?",
            answers: ["Leo","Aries","Cancer","Libra"],
            correct: "Leo"
        },
        {
            question: "What is Liliana's favourite number?",
            answers: ["3","5","7","9"],
            correct: "3"
        }
    ], "Pressure Quiz complete! 🔥", 130);
}
/* =========================================================
   LEVEL 4 — HIGH ROLLER
========================================================= */
function highRoller() {
    gameBox.appendChild(
        instruction(
            "Choose a mystery card. Keep trying until you find the winning card."
        )
    );
    const grid = document.createElement("div");
    grid.className = "choice-grid";
    let winner = Math.floor(Math.random() * 3);
    for (let i = 0; i < 3; i++) {
        const number = i;
        grid.appendChild(
            button(
                "🃏 CARD " + (i + 1),
                function() {
                    if (number === winner) {
                        completeLevel(
                            "The High Roller has won! 🎰",
                            140,
                            140
                        );
                    } else {
                        this.textContent = "❌ TRY AGAIN";
                    }
                }
            )
        );
    }
    gameBox.appendChild(grid);
}
/* =========================================================
   LEVEL 5 — MIND GAMES
========================================================= */
function mindGames() {
    gameBox.appendChild(
        instruction(
            "Remember the four numbers, then tap them in order."
        )
    );
    const pattern = shuffle([1,2,3,4]);
    const display = document.createElement("div");
    display.className = "big-number";
    display.textContent = pattern.join(" ");
    gameBox.appendChild(display);
    const grid = document.createElement("div");
    grid.className = "choice-grid";
    let position = 0;
    setTimeout(function() {
        display.textContent = "GO!";
    }, 1800);
    [1,2,3,4].forEach(function(number) {
        grid.appendChild(
            button(String(number), function() {
                if (number !== pattern[position]) {
                    position = 0;
                    display.textContent =
                        "Try again!";
                    setTimeout(function() {
                        display.textContent = "GO!";
                    }, 500);
                    return;
                }
                position++;
                if (position === 4) {
                    completeLevel(
                        "Amazing memory! 🧠",
                        150,
                        150
                    );
                }
            })
        );
    });
    gameBox.appendChild(grid);
}
/* =========================================================
   LEVEL 6 — BLUFF
========================================================= */
function bluff() {
    gameBox.appendChild(
        instruction(
            "One card is the Queen. Find her."
        )
    );
    const grid = document.createElement("div");
    grid.className = "choice-grid";
    const winner = Math.floor(Math.random() * 3);
    for (let i = 0; i < 3; i++) {
        const number = i;
        grid.appendChild(
            button(
                "🂠 CARD " + (i + 1),
                function() {
                    if (number === winner) {
                        completeLevel(
                            "You saw straight through the bluff! 🃏",
                            150,
                            150
                        );
                    } else {
                        this.textContent = "NOPE — TRY AGAIN";
                    }
                }
            )
        );
    }
    gameBox.appendChild(grid);
}
/* =========================================================
   LEVEL 7 — SURVIVAL
========================================================= */
function survival() {
    gameBox.appendChild(
        instruction(
            "Choose the safe heart for 8 rounds."
        )
    );
    const status = document.createElement("div");
    status.className = "status";
    const grid = document.createElement("div");
    grid.className = "choice-grid";
    gameBox.appendChild(status);
    gameBox.appendChild(grid);
    let round = 1;
    function newRound() {
        status.textContent =
            "ROUND " + round + " OF 8";
        grid.innerHTML = "";
        const safe = Math.floor(Math.random() * 3);
        for (let i = 0; i < 3; i++) {
            const number = i;
            grid.appendChild(
                button("❤️", function() {
                    if (number === safe) {
                        round++;
                        if (round > 8) {
                            completeLevel(
                                "You survived every round! 💗",
                                160,
                                160
                            );
                        } else {
                            newRound();
                        }
                    } else {
                        status.textContent =
                            "That one wasn't safe. Try again!";
                    }
                })
            );
        }
    }
    newRound();
}
/* =========================================================
   LEVEL 8 — ADMIRER RACE
========================================================= */
function admirerRace() {
    gameBox.appendChild(
        instruction(
            "Tap the heart 20 times before your admirer catches you!"
        )
    );
    const progress = document.createElement("div");
    progress.className = "progress";
    const fill = document.createElement("div");
    fill.className = "progress-fill";
    progress.appendChild(fill);
    const status = document.createElement("div");
    status.className = "status";
    gameBox.appendChild(progress);
    gameBox.appendChild(status);
    let taps = 0;
    const b = button(
        "💗 TAP!",
        function() {
            taps++;
            fill.style.width =
                (taps / 20 * 100) + "%";
            status.textContent =
                taps + " / 20";
            if (taps >= 20) {
                completeLevel(
                    "You reached the finish first! 🏁",
                    170,
                    170
                );
            }
        },
        "big-action"
    );
    gameBox.appendChild(b);
}
/* =========================================================
   LEVEL 9 — HEARTBREAK CHAMBER
========================================================= */
function heartbreakChamber() {
    gameBox.appendChild(
        instruction(
            "Five doors. One door gets you out. Keep trying until you escape."
        )
    );
    const grid = document.createElement("div");
    grid.className = "choice-grid";
    const winner = Math.floor(Math.random() * 5);
    for (let i = 0; i < 5; i++) {
        const number = i;
        grid.appendChild(
            button(
                "🚪 DOOR " + (i + 1),
                function() {
                    if (number === winner) {
                        completeLevel(
                            "You escaped the Heartbreak Chamber! 💗",
                            170,
                            170
                        );
                    } else {
                        this.textContent = "🔒 TRY AGAIN";
                    }
                }
            )
        );
    }
    gameBox.appendChild(grid);
}
/* =========================================================
   LEVEL 10 — BOXING
========================================================= */
function boxing() {
    gameBox.appendChild(
        instruction(
            "Land 12 heart punches."
        )
    );
    const status = document.createElement("div");
    status.className = "status";
    status.textContent = "0 / 12";
    gameBox.appendChild(status);
    let hits = 0;
    gameBox.appendChild(
        button(
            "🥊 HIT!",
            function() {
                hits++;
                status.textContent =
                    hits + " / 12";
                if (hits >= 12) {
                    completeLevel(
                        "You won the Heartbreak Boxing Match! 🥊",
                        180,
                        180
                    );
                }
            },
            "big-action"
        )
    );
}
/* =========================================================
   LEVEL 11 — PERFECT MATCH
========================================================= */
function perfectMatch() {
    gameBox.appendChild(
        instruction(
            "Find the perfect pair."
        )
    );
    const correct = "🌸 + 💗";
    const grid = document.createElement("div");
    grid.className = "choice-grid";
    shuffle([
        correct,
        "🔥 + 🌧️",
        "⭐ + 🪨",
        "🐟 + 🍋"
    ]).forEach(function(answer) {
        grid.appendChild(
            button(answer, function() {
                if (answer === correct) {
                    completeLevel(
                        "Perfect match! 🌸",
                        180,
                        180
                    );
                }
            })
        );
    });
    gameBox.appendChild(grid);
}
/* =========================================================
   LEVEL 12 — WHO KNOWS LILIANA BEST
========================================================= */
function whoKnows() {
    gameBox.appendChild(
        instruction(
            "Let's see how well you know Lulu!"
        )
    );
    simpleQuiz([
        {
            question: "How many siblings does Liliana have?",
            answers: ["5","3","4","6"],
            correct: "5"
        },
        {
            question: "What colour are Liliana's eyes?",
            answers: ["Green","Brown","Blue","Hazel"],
            correct: "Green"
        },
        {
            question: "What did Liliana study at university?",
            answers: ["Psychology","Law","Nursing","Business"],
            correct: "Psychology"
        },
        {
            question: "What is Liliana's favourite movie?",
            answers: ["Me Before You","Titanic","The Notebook","Frozen"],
            correct: "Me Before You"
        },
        {
            question: "What is Liliana afraid of?",
            answers: ["Drowning","Flying","Spiders","Heights"],
            correct: "Drowning"
        }
    ], "You really know Lulu! 💗", 200);
}
/* =========================================================
   LEVEL 13 — REACTION
========================================================= */
function reaction() {
    gameBox.appendChild(
        instruction(
            "Wait for the heart to appear, then tap it. Do this 5 times."
        )
    );
    const status = document.createElement("div");
    status.className = "status";
    const action = button(
        "WAIT...",
        function() {
            if (!ready) return;
            ready = false;
            rounds++;
            if (rounds >= 5) {
                completeLevel(
                    "Lightning-fast reactions! ⚡",
                    190,
                    190
                );
                return;
            }
            action.textContent = "WAIT...";
            setTimeout(function() {
                ready = true;
                action.textContent = "💗 TAP!";
            }, 700);
        },
        "big-action"
    );
    let ready = false;
    let rounds = 0;
    gameBox.appendChild(status);
    gameBox.appendChild(action);
    setTimeout(function() {
        ready = true;
        action.textContent = "💗 TAP!";
    }, 1000);
}
/* =========================================================
   LEVEL 14 — HEART HUNT
========================================================= */
function heartHunt() {
    gameBox.appendChild(
        instruction(
            "Tap the 10 hidden hearts."
        )
    );
    const grid = document.createElement("div");
    grid.className = "choice-grid";
    let found = 0;
    for (let i = 0; i < 15; i++) {
        const b = button("♡", function() {
            if (b.disabled) return;
            b.disabled = true;
            b.textContent = "❤️";
            found++;
            if (found >= 10) {
                completeLevel(
                    "You found all the hidden hearts! 💗",
                    190,
                    190
                );
            }
        });
        b.style.fontSize = "27px";
        grid.appendChild(b);
    }
    gameBox.appendChild(grid);
}
/* =========================================================
   LEVEL 15 — LOVE LOCK
========================================================= */
function loveLock() {
    gameBox.appendChild(
        instruction(
            "Enter the Love Lock code."
        )
    );
    const input = document.createElement("input");
    input.type = "tel";
    input.inputMode = "numeric";
    input.maxLength = 6;
    input.placeholder = "••••••";
    input.style.textAlign = "center";
    input.style.letterSpacing = "7px";
    const status = document.createElement("div");
    status.className = "status";
    gameBox.appendChild(input);
    gameBox.appendChild(
        button(
            "🔐 UNLOCK",
            function() {
                if (input.value === "060722") {
                    completeLevel(
                        "The Love Lock is open! 🔓💗",
                        200,
                        200
                    );
                } else {
                    status.textContent =
                        "Not quite. Try again!";
                }
            },
            "main-btn"
        )
    );
    gameBox.appendChild(status);
}
/* =========================================================
   LEVEL 16 — CUPID
========================================================= */
function cupid() {
    gameBox.appendChild(
        instruction(
            "Cupid needs 10 successful shots."
        )
    );
    const status = document.createElement("div");
    status.className = "status";
    status.textContent = "0 / 10";
    let shots = 0;
    gameBox.appendChild(status);
    gameBox.appendChild(
        button(
            "🏹 🎯",
            function() {
                shots++;
                status.textContent =
                    shots + " / 10";
                if (shots >= 10) {
                    completeLevel(
                        "Cupid's aim is perfect! 🏹💗",
                        200,
                        200
                    );
                }
            },
            "big-action"
        )
    );
}
/* =========================================================
   LEVEL 17 — COUNTDOWN
========================================================= */
function countdown() {
    gameBox.appendChild(
        instruction(
            "Watch the countdown. Tap the button when it reaches 1."
        )
    );
    const number = document.createElement("div");
    number.className = "big-number";
    const action = button(
        "WAIT...",
        function() {
            if (currentNumber === 1) {
                completeLevel(
                    "Perfect timing! ⏱️💗",
                    210,
                    210
                );
            } else {
                status.textContent =
                    "Wait until the number reaches 1.";
            }
        },
        "big-action"
    );
    const status = document.createElement("div");
    status.className = "status";
    gameBox.appendChild(number);
    gameBox.appendChild(action);
    gameBox.appendChild(status);
    let currentNumber = 5;
    number.textContent = currentNumber;
    timer = setInterval(function() {
        currentNumber--;
        if (currentNumber < 1) {
            currentNumber = 5;
        }
        number.textContent = currentNumber;
        action.textContent =
            currentNumber === 1
            ? "💗 TAP NOW!"
            : "WAIT...";
    }, 800);
}
/* =========================================================
   LEVEL 18 — ULTIMATE GAMBLE
========================================================= */
function ultimateGamble() {
    gameBox.appendChild(
        instruction(
            "Get 3 wins. You can always try again."
        )
    );
    const status = document.createElement("div");
    status.className = "status";
    status.textContent = "WINS: 0 / 3";
    let wins = 0;
    const safe = button(
        "💗 SAFE",
        function() {
            wins++;
            status.textContent =
                "WINS: " + wins + " / 3";
            if (wins >= 3) {
                completeLevel(
                    "The Ultimate Gamble paid off! 🎰",
                    220,
                    220
                );
            }
        }
    );
    const gamble = button(
        "🔥 GAMBLE",
        function() {
            if (Math.random() < .75) {
                wins++;
                status.textContent =
                    "WINS: " + wins + " / 3";
                if (wins >= 3) {
                    completeLevel(
                        "The Ultimate Gamble paid off! 🎰",
                        220,
                        220
                    );
                }
            } else {
                status.textContent =
                    "The gamble missed. Try again!";
            }
        }
    );
    const grid = document.createElement("div");
    grid.className = "choice-grid";
    grid.appendChild(safe);
    grid.appendChild(gamble);
    gameBox.appendChild(status);
    gameBox.appendChild(grid);
}
/* =========================================================
   LEVEL 19 — LAST STAND
========================================================= */
function lastStand() {
    gameBox.appendChild(
        instruction(
            "Defend your heart 8 times."
        )
    );
    const status = document.createElement("div");
    status.className = "status";
    status.textContent = "0 / 8";
    let blocks = 0;
    gameBox.appendChild(status);
    gameBox.appendChild(
        button(
            "🛡️ BLOCK",
            function() {
                blocks++;
                status.textContent =
                    blocks + " / 8";
                if (blocks >= 8) {
                    completeLevel(
                        "You protected the heart! 🛡️💗",
                        220,
                        220
                    );
                }
            },
            "big-action"
        )
    );
}
/* =========================================================
   LEVEL 20 — WORD FIND
========================================================= */
function wordFind() {
    gameBox.appendChild(
        instruction(
            "Find the letters L U L U in order."
        )
    );
    const letters = [
        "L","U","L","U",
        "A","B","C","D",
        "E","F","G","H",
        "I","J","K","M",
        "N","O","P","Q",
        "R","S","T","V",
        "W","X","Y","Z",
        "A","R","O","S",
        "E","S","D","O",
        "L","P","H","A",
        "I","N","K","S",
        "S","U","N","F",
        "L","O","W","E",
        "R","D","O","L",
        "P","H","I","N",
        "S","C","A","T"
    ];
    const grid = document.createElement("div");
    grid.className = "word-grid";
    let position = 0;
    /*
     * The first four cells are deliberately L U L U.
     * This guarantees the level can always be completed.
     */
    const shuffledRest = shuffle(letters.slice(4));
    const finalLetters = [
        "L","U","L","U",
        ...shuffledRest.slice(0,60)
    ];
    finalLetters.forEach(function(letter) {
        const cell = button(
            letter,
            function() {
                if (letter === ["L","U","L","U"][position]) {
                    cell.classList.add("selected");
                    cell.disabled = true;
                    position++;
                    if (position === 4) {
                        completeLevel(
                            "You found LULU! 🔎💗",
                            230,
                            230
                        );
                    }
                } else {
                    cell.classList.add("selected");
                    setTimeout(function() {
                        cell.classList.remove("selected");
                    }, 200);
                }
            },
            "word-cell"
        );
        grid.appendChild(cell);
    });
    gameBox.appendChild(grid);
}
/* =========================================================
   LEVEL 21 — DRAW A SUNFLOWER
========================================================= */
function sunflower() {
    gameBox.appendChild(
        instruction(
            "Draw a sunflower using your finger. When you're happy with it, press DONE."
        )
    );
    const canvas = document.createElement("canvas");
    canvas.width = 500;
    canvas.height = 500;
    const ctx = canvas.getContext("2d");
    ctx.lineWidth = 7;
    ctx.lineCap = "round";
    ctx.strokeStyle = "#663b4c";
    let drawing = false;
    function getPosition(event) {
        const rect = canvas.getBoundingClientRect();
        return {
            x:
                (event.clientX - rect.left) *
                (canvas.width / rect.width),
            y:
                (event.clientY - rect.top) *
                (canvas.height / rect.height)
        };
    }
    canvas.addEventListener("pointerdown", function(event) {
        drawing = true;
        const p = getPosition(event);
        ctx.beginPath();
        ctx.moveTo(p.x, p.y);
        canvas.setPointerCapture(event.pointerId);
    });
    canvas.addEventListener("pointermove", function(event) {
        if (!drawing) return;
        const p = getPosition(event);
        ctx.lineTo(p.x, p.y);
        ctx.stroke();
    });
    canvas.addEventListener("pointerup", function() {
        drawing = false;
    });
    canvas.addEventListener("pointercancel", function() {
        drawing = false;
    });
    gameBox.appendChild(canvas);
    const clear = button(
        "CLEAR",
        function() {
            ctx.clearRect(
                0,
                0,
                canvas.width,
                canvas.height
            );
        },
        "secondary-btn"
    );
    const done = button(
        "🌻 DONE",
        function() {
            completeLevel(
                "A sunflower made especially for Lulu! 🌻",
                250,
                250
            );
        },
        "main-btn"
    );
    gameBox.appendChild(clear);
    gameBox.appendChild(done);
}
/* =========================================================
   LEVEL 22 — LULU DERBY
========================================================= */
function derby() {
    gameBox.appendChild(
        instruction(
            "Choose your animal and difficulty before starting the race."
        )
    );
    const animalTitle = document.createElement("h3");
    animalTitle.textContent =
        "🐾 Choose your animal";
    gameBox.appendChild(animalTitle);
    const animalGrid = document.createElement("div");
    animalGrid.className = "animal-grid";
    const animals = [
        ["🐎","Horse"],
        ["🦄","Unicorn"],
        ["🐬","Dolphin"],
        ["🦋","Butterfly"],
        ["🐇","Bunny"],
        ["🦊","Fox"]
    ];
    let selectedAnimal = null;
    let selectedDifficulty = null;
    animals.forEach(function(item) {
        const animal = button(
            item[0] + "\n" + item[1],
            function() {
                selectedAnimal = item[1];
                Array.from(
                    animalGrid.children
                ).forEach(function(child) {
                    child.classList.remove("selected");
                });
                animal.classList.add("selected");
            },
            "animal"
        );
        animal.innerHTML =
            "<span>" + item[0] + "</span>" +
            item[1];
        animalGrid.appendChild(animal);
    });
    gameBox.appendChild(animalGrid);
    const difficultyTitle =
        document.createElement("h3");
    difficultyTitle.textContent =
        "🏁 Choose your difficulty";
    difficultyTitle.style.marginTop = "22px";
    gameBox.appendChild(difficultyTitle);
    const difficultyGrid =
        document.createElement("div");
    difficultyGrid.className =
        "difficulty-grid";
    const difficulties = [
        ["🌸","Easy"],
        ["💗","Medium"],
        ["🔥","Hard"],
        ["👑","Expert"]
    ];
    difficulties.forEach(function(item) {
        const difficulty = button(
            item[0] + " " + item[1],
            function() {
                selectedDifficulty = item[1];
                Array.from(
                    difficultyGrid.children
                ).forEach(function(child) {
                    child.classList.remove("selected");
                });
                difficulty.classList.add("selected");
            },
            "difficulty"
        );
        difficultyGrid.appendChild(difficulty);
    });
    gameBox.appendChild(difficultyGrid);
    const startRace = button(
        "🏁 START DERBY",
        function() {
            if (
                selectedAnimal === null ||
                selectedDifficulty === null
            ) {
                return;
            }
            runDerby(
                selectedAnimal,
                selectedDifficulty
            );
        },
        "main-btn"
    );
    gameBox.appendChild(startRace);
}
function runDerby(animal, difficulty) {
    stopEverything();
    gameBox.innerHTML = "";
    const settings = {
        Easy: {
            taps: 15,
            rivalStart: 20,
            rivalPerTap: 0
        },
        Medium: {
            taps: 20,
            rivalStart: 30,
            rivalPerTap: 0
        },
        Hard: {
            taps: 25,
            rivalStart: 40,
            rivalPerTap: 0
        },
        Expert: {
            taps: 30,
            rivalStart: 50,
            rivalPerTap: 0
        }
    };
    const config = settings[difficulty];
    const title = document.createElement("h3");
    title.className = "center";
    title.textContent =
        animal +
        " — " +
        difficulty +
        " Derby";
    gameBox.appendChild(title);
    gameBox.appendChild(
        instruction(
            "Tap RUN to move your animal. Reach 100% to win!"
        )
    );
    const playerRow = document.createElement("div");
    playerRow.className = "derby-row";
    const playerNameEl =
        document.createElement("div");
    playerNameEl.className = "derby-name";
    playerNameEl.textContent =
        animal;
    const playerTrack =
        document.createElement("div");
    playerTrack.className = "derby-track";
    const playerFill =
        document.createElement("div");
    playerFill.className = "derby-fill";
    playerTrack.appendChild(playerFill);
    playerRow.appendChild(playerNameEl);
    playerRow.appendChild(playerTrack);
    const rivalRow = document.createElement("div");
    rivalRow.className = "derby-row";
    const rivalName =
        document.createElement("div");
    rivalName.className = "derby-name";
    rivalName.textContent = "Rival";
    const rivalTrack =
        document.createElement("div");
    rivalTrack.className = "derby-track";
    const rivalFill =
        document.createElement("div");
    rivalFill.className =
        "derby-fill derby-rival";
    rivalTrack.appendChild(rivalFill);
    rivalRow.appendChild(rivalName);
    rivalRow.appendChild(rivalTrack);
    gameBox.appendChild(playerRow);
    gameBox.appendChild(rivalRow);
    const status = document.createElement("div");
    status.className = "status";
    status.textContent =
        "0 / " + config.taps;
    gameBox.appendChild(status);
    let taps = 0;
    /*
     * The rival moves automatically at a fixed percentage.
     * The values are deliberately beatable at every difficulty.
     */
    let rival = config.rivalStart;
    rivalFill.style.width =
        rival + "%";
    const run = button(
        "🏃 RUN!",
        function() {
            taps++;
            const player =
                Math.min(
                    100,
                    (taps / config.taps) * 100
                );
            playerFill.style.width =
                player + "%";
            status.textContent =
                taps + " / " + config.taps;
            if (player >= 100) {
                let points = 280;
                if (difficulty === "Expert") {
                    points = 350;
                }
                completeLevel(
                    "🏆 " +
                    animal +
                    " won the " +
                    difficulty.toLowerCase() +
                    " derby!",
                    points,
                    points
                );
            }
        },
        "big-action"
    );
    gameBox.appendChild(run);
    /*
     * Small automatic rival movement.
     * It NEVER reaches 100% before the player has a fair chance.
     */
    let rivalStep = 0;
    timer = setInterval(function() {
        rivalStep++;
        if (rivalStep % 4 === 0) {
            rival += 1;
            if (rival > 85) {
                rival = 85;
            }
            rivalFill.style.width =
                rival + "%";
        }
    }, 500);
}
/* =========================================================
   50 QUESTION FINAL QUIZ
========================================================= */
const finalQuestions = [
{
q:"What is Liliana's favourite number?",
a:["3","5","7","9"],
c:"3"
},
{
q:"What is Liliana's favourite colour?",
a:["Baby pink","Purple","Burgundy","Baby blue"],
c:"Baby pink"
},
{
q:"What food does Liliana love?",
a:["Sushi","Pizza","Pasta","Burgers"],
c:"Sushi"
},
{
q:"Which animal is one of Liliana's favourites?",
a:["Dolphins","Tigers","Koalas","Penguins"],
c:"Dolphins"
},
{
q:"Which flower does Liliana love?",
a:["Sunflowers","Tulips","Lilies","Daisies"],
c:"Sunflowers"
},
{
q:"Which other flower is one of Liliana's favourites?",
a:["Roses","Orchids","Lavender","Daffodils"],
c:"Roses"
},
{
q:"What is Liliana's favourite movie?",
a:["Me Before You","Titanic","The Notebook","Frozen"],
c:"Me Before You"
},
{
q:"What did Liliana study at university?",
a:["Psychology","Law","Nursing","Business"],
c:"Psychology"
},
{
q:"What is Liliana's zodiac sign?",
a:["Leo","Aries","Cancer","Libra"],
c:"Leo"
},
{
q:"What colour are Liliana's eyes?",
a:["Green","Brown","Blue","Hazel"],
c:"Green"
},
{
q:"How many siblings does Liliana have?",
a:["5","3","4","6"],
c:"5"
},
{
q:"How many nieces does Liliana have?",
a:["1","2","3","4"],
c:"1"
},
{
q:"How many nephews does Liliana have?",
a:["4","2","3","5"],
c:"4"
},
{
q:"How many piercings does Liliana have?",
a:["4","2","3","5"],
c:"4"
},
{
q:"What are Liliana's dogs called?",
a:["Aayla and Arlo","Luna and Milo","Bella and Arlo","Aayla and Luna"],
c:"Aayla and Arlo"
},
{
q:"What is Liliana afraid of?",
a:["Drowning","Flying","Spiders","Heights"],
c:"Drowning"
},
{
q:"What does Liliana dream of becoming one day?",
a:["A mum to a baby girl","A singer","A pilot","A chef"],
c:"A mum to a baby girl"
},
{
q:"What type of songs does Liliana like?",
a:["Sad songs","Country songs","Heavy metal","Classical music"],
c:"Sad songs"
},
{
q:"What type of writing does Liliana enjoy?",
a:["Poetry","Biographies","News articles","Textbooks"],
c:"Poetry"
},
{
q:"Which game does Liliana enjoy?",
a:["Poker","Golf","Bowling","Tennis"],
c:"Poker"
},
{
q:"What other activity does Liliana enjoy?",
a:["Gambling","Fishing","Hiking","Cooking"],
c:"Gambling"
},
{
q:"How long have Bree and Liliana been best friends?",
a:["6 years","4 years","5 years","8 years"],
c:"6 years"
},
{
q:"Which pair contains both of Liliana's favourite flowers?",
a:["Sunflowers and roses","Tulips and lilies","Daisies and orchids","Lavender and tulips"],
c:"Sunflowers and roses"
},
{
q:"Which pair contains both of Liliana's dogs?",
a:["Aayla and Arlo","Arlo and Milo","Aayla and Bella","Luna and Arlo"],
c:"Aayla and Arlo"
},
{
q:"Which combination correctly gives Liliana's favourite colour and food?",
a:["Baby pink and sushi","Purple and pizza","Baby blue and pasta","Burgundy and burgers"],
c:"Baby pink and sushi"
},
{
q:"Which combination correctly gives Liliana's favourite animal and flower?",
a:["Dolphins and sunflowers","Tigers and roses","Koalas and tulips","Penguins and lilies"],
c:"Dolphins and sunflowers"
},
{
q:"Which combination correctly gives Liliana's university subject and favourite movie?",
a:["Psychology and Me Before You","Law and Titanic","Nursing and The Notebook","Business and Frozen"],
c:"Psychology and Me Before You"
},
{
q:"Which combination correctly gives Liliana's music and writing interests?",
a:["Sad songs and poetry","Country music and novels","Classical music and biographies","Rock music and journalism"],
c:"Sad songs and poetry"
},
{
q:"Which combination correctly gives Liliana's zodiac sign and eye colour?",
a:["Leo and green","Aries and blue","Cancer and brown","Libra and hazel"],
c:"Leo and green"
},
{
q:"Which combination correctly gives Liliana's family numbers?",
a:["1 niece and 4 nephews","2 nieces and 3 nephews","1 niece and 5 nephews","3 nieces and 4 nephews"],
c:"1 niece and 4 nephews"
},
{
q:"Which combination correctly gives Liliana's siblings and piercings?",
a:["5 siblings and 4 piercings","4 siblings and 5 piercings","6 siblings and 3 piercings","3 siblings and 4 piercings"],
c:"5 siblings and 4 piercings"
},
{
q:"Which statement about Liliana's favourites is correct?",
a:["She loves sushi and dolphins","She loves pizza and tigers","She loves pasta and penguins","She loves burgers and koalas"],
c:"She loves sushi and dolphins"
},
{
q:"Which statement about Liliana's flowers is correct?",
a:["She likes sunflowers and roses","She likes tulips and lilies","She likes daisies and orchids","She likes lavender and tulips"],
c:"She likes sunflowers and roses"
},
{
q:"Which statement about Liliana's pets is correct?",
a:["She has dogs named Aayla and Arlo","She has cats named Aayla and Arlo","She has dogs named Luna and Milo","She has rabbits named Aayla and Bella"],
c:"She has dogs named Aayla and Arlo"
},
{
q:"Which statement about Liliana's education is correct?",
a:["She studied Psychology at university","She studied Law at university","She studied Nursing at university","She studied Business at university"],
c:"She studied Psychology at university"
},
{
q:"Which statement about Liliana's future dream is correct?",
a:["She wants to be a mum to a baby girl","She wants to become a pilot","She wants to become a chef","She wants to become a professional athlete"],
c:"She wants to be a mum to a baby girl"
},
{
q:"Which statement about Liliana's creative interests is correct?",
a:["She likes sad songs and poetry","She dislikes music and writing","She only likes comedy films","She only likes documentaries"],
c:"She likes sad songs and poetry"
},
{
q:"Which statement about Liliana's games is correct?",
a:["She enjoys poker and gambling","She dislikes all games","She only enjoys football","She only enjoys board games"],
c:"She enjoys poker and gambling"
},
{
q:"Which statement about Liliana's family is correct?",
a:["She has 5 siblings","She has 2 siblings","She has 7 siblings","She has 1 sibling"],
c:"She has 5 siblings"
},
{
q:"Which statement about Liliana's eyes is correct?",
a:["Her eyes are green","Her eyes are blue","Her eyes are brown","Her eyes are hazel"],
c:"Her eyes are green"
},
{
q:"Which statement about Liliana's zodiac sign is correct?",
a:["She is a Leo","She is a Virgo","She is a Taurus","She is a Gemini"],
c:"She is a Leo"
},
{
q:"Which statement about Liliana's favourite film is correct?",
a:["Me Before You is her favourite movie","Titanic is her favourite movie","The Notebook is her favourite movie","Frozen is her favourite movie"],
c:"Me Before You is her favourite movie"
},
{
q:"Which statement correctly connects Liliana's fear and favourite animal?",
a:["She is afraid of drowning and loves dolphins","She is afraid of heights and loves mountains","She is afraid of spiders and loves insects","She is afraid of flying and loves planes"],
c:"She is afraid of drowning and loves dolphins"
},
{
q:"Which statement correctly connects Liliana's favourite number and zodiac sign?",
a:["3 and Leo","7 and Leo","3 and Aries","5 and Cancer"],
c:"3 and Leo"
},
{
q:"Which statement correctly connects Liliana's favourite food and favourite movie?",
a:["Sushi and Me Before You","Pizza and Titanic","Pasta and The Notebook","Burgers and Frozen"],
c:"Sushi and Me Before You"
},
{
q:"Which statement correctly connects Liliana's flowers and favourite colour?",
a:["Sunflowers, roses and baby pink","Tulips, lilies and purple","Daisies, orchids and blue","Lavender, roses and burgundy"],
c:"Sunflowers, roses and baby pink"
},
{
q:"Which statement correctly connects Liliana's dogs and family?",
a:["Aayla and Arlo, with 1 niece and 4 nephews","Luna and Milo, with 2 nieces and 3 nephews","Bella and Arlo, with 3 nieces and 2 nephews","Aayla and Luna, with 4 nieces and 1 nephew"],
c:"Aayla and Arlo, with 1 niece and 4 nephews"
},
{
q:"Which statement correctly connects Liliana's university subject and writing interest?",
a:["Psychology and poetry","Law and journalism","Nursing and novels","Business and biographies"],
c:"Psychology and poetry"
},
{
q:"Which statement correctly connects Liliana's friendship and favourite number?",
a:["6 years of friendship and favourite number 3","4 years of friendship and favourite number 7","5 years of friendship and favourite number 9","8 years of friendship and favourite number 5"],
c:"6 years of friendship and favourite number 3"
},
{
q:"Which statement correctly brings together Liliana's favourite colour, food and animal?",
a:["Baby pink, sushi and dolphins","Purple, pizza and tigers","Blue, pasta and koalas","Burgundy, burgers and penguins"],
c:"Baby pink, sushi and dolphins"
},
{
q:"Which set contains only things Liliana likes?",
a:["Sushi, dolphins and sunflowers","Pizza, tigers and tulips","Pasta, koalas and orchids","Burgers, penguins and lilies"],
c:"Sushi, dolphins and sunflowers"
},
{
q:"Which set correctly describes Liliana's personal details?",
a:["Green eyes, Leo and 5 siblings","Blue eyes, Aries and 3 siblings","Brown eyes, Cancer and 4 siblings","Hazel eyes, Libra and 6 siblings"],
c:"Green eyes, Leo and 5 siblings"
}
];
/* =========================================================
   LEVEL 23 — FINAL QUIZ
========================================================= */
function finalQuiz() {
    gameBox.appendChild(
        instruction(
            "The Final Challenge! Answer all 50 questions about Liliana."
        )
    );
    let questions = shuffle(finalQuestions);
    let number = 0;
    let correctAnswers = 0;
    let locked = false;
    const title = document.createElement("h3");
    title.className = "center";
    const progress = document.createElement("div");
    progress.className = "progress";
    const fill = document.createElement("div");
    fill.className = "progress-fill";
    progress.appendChild(fill);
    const choices = document.createElement("div");
    choices.className = "choice-grid";
    const status = document.createElement("div");
    status.className = "status";
    gameBox.appendChild(title);
    gameBox.appendChild(progress);
    gameBox.appendChild(choices);
    gameBox.appendChild(status);
    function showQuestion() {
        locked = false;
        const q = questions[number];
        title.textContent =
            "QUESTION " +
            (number + 1) +
            " OF 50";
        fill.style.width =
            (number / 50 * 100) + "%";
        choices.innerHTML = "";
        status.textContent = "";
        /*
         * Answers are shuffled independently for every question.
         * Therefore the correct answer is not always A/B/C/D.
         */
        shuffle(q.a).forEach(function(answer) {
            choices.appendChild(
                button(answer, function() {
                    if (locked) return;
                    locked = true;
                    if (answer === q.c) {
                        correctAnswers++;
                        this.classList.add("correct");
                        status.textContent =
                            "Correct! 💗";
                    } else {
                        this.classList.add("wrong");
                        status.textContent =
                            "Not quite! Keep going 💗";
                    }
                    setTimeout(function() {
                        number++;
                        if (number >= 50) {
                            finishFinalQuiz(
                                correctAnswers
                            );
                        } else {
                            showQuestion();
                        }
                    }, 350);
                })
            );
        });
    }
    showQuestion();
}
/* =========================================================
   FINAL QUIZ SCORING
========================================================= */
function finishFinalQuiz(correctAnswers) {
    stopEverything();
    /*
     * 70 points per correct answer.
     * Maximum quiz score = 3500.
     *
     * The private-call requirement is STRICTLY ABOVE 3000.
     * Therefore exactly 3000 does NOT qualify.
     */
    score += correctAnswers * 70;
    tokens += correctAnswers * 20;
    const qualifies =
        score > 3000;
    document.getElementById("completeMessage").textContent =
        "You got " +
        correctAnswers +
        " out of 50 questions correct!";
    const next =
        document.getElementById("nextButton");
    next.textContent =
        "FINISH JOURNEY →";
    next.onclick = function() {
        finishJourney(qualifies);
    };
    showScreen("complete");
}
/* =========================================================
   FINISH
========================================================= */
function finishJourney(qualifies) {
    stopEverything();
    document.getElementById("finishMessage").textContent =
        "Congratulations, " +
        (playerName || "you") +
        "! You completed all 23 levels of Lulu Express. 💗";
    document.getElementById("finalScore").textContent =
        "⭐ Final Score: " + score;
    document.getElementById("finalTokens").textContent =
        "🎟️ Tokens Earned: " + tokens;
    const reward =
        document.getElementById("specialReward");
    reward.innerHTML = "";
    if (qualifies === true) {
        const rewardCard =
            document.createElement("div");
        rewardCard.className = "card";
        rewardCard.innerHTML =
            "<h2>📞 Private Call Unlocked!</h2>" +
            "<p>" +
            "Your score is above 3000, so you unlocked the special private-call reward! 💗" +
            "</p>";
        reward.appendChild(
            document.createElement("br")
        );
        reward.style.marginBottom = "10px";
        document
            .getElementById("finish")
            .querySelector(".container")
            .insertBefore(
                rewardCard,
                document.getElementById("finish").querySelector(".card")
            );
    }
    showScreen("finish");
}
/* =========================================================
   MUSIC
========================================================= */
const musicButton =
    document.getElementById("musicButton");
musicButton.addEventListener("click", function() {
    if (!musicOn) {
        startMusic();
        musicOn = true;
        musicButton.textContent =
            "🎵 Music: ON";
    } else {
        stopMusic();
        musicOn = false;
        musicButton.textContent =
            "🎵 Music: OFF";
    }
});
let musicOn = false;
function startMusic() {
    try {
        audioContext =
            new (
                window.AudioContext ||
                window.webkitAudioContext
            )();
        const notes = [
            261.63,
            329.63,
            392.00,
            329.63
        ];
        let note = 0;
        musicTimer = setInterval(function() {
            if (!audioContext) return;
            const oscillator =
                audioContext.createOscillator();
            const gain =
                audioContext.createGain();
            oscillator.frequency.value =
                notes[note];
            oscillator.type = "sine";
            gain.gain.setValueAtTime(
                0.035,
                audioContext.currentTime
            );
            gain.gain.exponentialRampToValueAtTime(
                0.001,
                audioContext.currentTime + 0.45
            );
            oscillator.connect(gain);
            gain.connect(audioContext.destination);
            oscillator.start();
            oscillator.stop(
                audioContext.currentTime + 0.45
            );
            note++;
            if (note >= notes.length) {
                note = 0;
            }
        }, 550);
    } catch (error) {
        /*
         * If the browser blocks audio, the games still work.
         */
    }
}
function stopMusic() {
    if (musicTimer !== null) {
        clearInterval(musicTimer);
        musicTimer = null;
    }
    if (audioContext !== null) {
        try {
            audioContext.close();
        } catch (error) {}
        audioContext = null;
    }
}
/* =========================================================
   START JOURNEY
========================================================= */
document
.getElementById("startButton")
.addEventListener("click", function() {
    const input =
        document.getElementById("nameInput");
    const name =
        input.value.trim();
    if (!name) {
        document.getElementById("nameError").textContent =
            "Please enter your name first. 💗";
        input.focus();
        return;
    }
    playerName =
        name.substring(0, 30);
    currentLevel = 0;
    score = 0;
    tokens = 0;
    document.getElementById("nameError").textContent =
        "";
    document.getElementById("welcomeText").textContent =
        "Welcome, " +
        playerName +
        ". Your Lulu Express adventure is ready. 🌸";
    showScreen("intro");
});
/* =========================================================
   BEGIN LEVEL 1
========================================================= */
document
.getElementById("beginButton")
.addEventListener("click", function() {
    loadLevel();
});
/* =========================================================
   NEXT LEVEL
========================================================= */
document
.getElementById("nextButton")
.addEventListener("click", function() {
    currentLevel++;
    if (currentLevel >= TOTAL_LEVELS) {
        finishJourney(false);
    } else {
        loadLevel();
    }
});
/* =========================================================
   RESET
========================================================= */
document
.getElementById("resetButton")
.addEventListener("click", function() {
    stopEverything();
    stopMusic();
    playerName = "";
    currentLevel = 0;
    score = 0;
    tokens = 0;
    musicOn = false;
    document.getElementById("nameInput").value = "";
    document.getElementById("nameError").textContent =
        "";
    document.getElementById("musicButton").textContent =
        "🎵 Music: OFF";
    document.getElementById("nextButton").textContent =
        "NEXT LEVEL →";
    document.getElementById("nextButton").onclick = null;
    document.getElementById("specialReward").innerHTML =
        "";
    showScreen("start");
});
</script>
</body>
</html>

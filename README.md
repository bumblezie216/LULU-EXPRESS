<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<meta name="theme-color" content="#170b13">

<title>Lulu Express 🚂💗</title>

<style>
*{
  box-sizing:border-box;
  -webkit-tap-highlight-color:transparent;
}

:root{
  --bg:#12080e;
  --panel:#26121e;
  --panel2:#351827;
  --pink:#ff78ad;
  --pink2:#ffb5d2;
  --gold:#ffd76a;
  --red:#ff526f;
  --green:#7df2a5;
  --text:#fff4f8;
  --muted:#c9aab7;
}

html,body{
  margin:0;
  min-height:100%;
  background:
    radial-gradient(circle at 20% 10%,#4a1935 0,transparent 30%),
    radial-gradient(circle at 80% 80%,#3a1429 0,transparent 35%),
    var(--bg);
  color:var(--text);
  font-family:Arial,Helvetica,sans-serif;
}

body{
  overflow-x:hidden;
}

button,
input,
textarea{
  font:inherit;
}

button{
  border:0;
  cursor:pointer;
}

#app{
  width:100%;
  max-width:900px;
  margin:auto;
  padding:18px;
}

header{
  text-align:center;
  padding:12px 0 18px;
}

.logo{
  font-size:clamp(30px,8vw,58px);
  font-weight:900;
  letter-spacing:-2px;
  text-shadow:0 0 20px #ff4f91;
}

.subtitle{
  color:var(--pink2);
  margin-top:5px;
}

.scorebar{
  position:sticky;
  top:8px;
  z-index:50;
  display:flex;
  justify-content:space-between;
  gap:10px;
  padding:12px 15px;
  margin-bottom:18px;
  border:1px solid #ff78ad55;
  border-radius:18px;
  background:#1c0c15ee;
  backdrop-filter:blur(12px);
  box-shadow:0 10px 30px #0007;
}

.score{
  color:var(--gold);
  font-weight:900;
}

.eventno{
  color:var(--pink2);
  font-weight:800;
}

.card{
  position:relative;
  overflow:hidden;
  background:
    linear-gradient(145deg,#321725,#21101a);
  border:1px solid #ff78ad33;
  border-radius:28px;
  padding:22px;
  box-shadow:0 20px 60px #0008;
}

h1,h2,h3{
  margin-top:0;
}

h2{
  font-size:clamp(25px,6vw,38px);
}

p{
  line-height:1.55;
}

.muted{
  color:var(--muted);
}

button.action,
.answer,
.choice,
.mode,
.animal{
  background:linear-gradient(145deg,#ff78ad,#d94c84);
  color:white;
  padding:13px 18px;
  border-radius:15px;
  margin:5px;
  font-weight:900;
  box-shadow:0 7px 18px #0005;
  transition:.18s;
}

button.action:hover,
.answer:hover,
.choice:hover,
.mode:hover,
.animal:hover{
  transform:translateY(-3px) scale(1.02);
}

button.action:active,
.answer:active,
.choice:active,
.mode:active,
.animal:active{
  transform:scale(.94);
}

button.secondary{
  background:#ffffff12;
  border:1px solid #ffffff22;
}

.grid{
  display:grid;
  gap:10px;
}

.grid16{
  grid-template-columns:repeat(4,1fr);
}

.grid25{
  grid-template-columns:repeat(5,1fr);
}

.memory-tile{
  aspect-ratio:1;
  border-radius:15px;
  background:#ffffff0d;
  border:2px solid #ff78ad33;
  color:white;
  font-size:clamp(20px,6vw,32px);
  transition:.18s;
}

.memory-tile.active{
  background:#ff78ad;
  box-shadow:0 0 30px #ff78ad;
  transform:scale(1.08);
}

.memory-tile.correct{
  background:#51d889;
}

.memory-tile.wrong{
  background:#ff526f;
  animation:shake .3s;
}

@keyframes shake{
  0%,100%{transform:translateX(0)}
  25%{transform:translateX(-8px)}
  75%{transform:translateX(8px)}
}

.arena{
  position:relative;
  min-height:380px;
  border-radius:22px;
  overflow:hidden;
  background:
    radial-gradient(circle,#5a203d 1px,transparent 1px);
  background-size:25px 25px;
  border:1px solid #ff78ad33;
}

.target{
  position:absolute;
  width:62px;
  height:62px;
  border-radius:50%;
  display:grid;
  place-items:center;
  font-size:35px;
  background:#ff78ad;
  box-shadow:0 0 30px #ff78ad;
  animation:pulse 1s infinite;
}

@keyframes pulse{
  50%{transform:scale(1.15)}
}

.float{
  position:fixed;
  pointer-events:none;
  z-index:999;
  font-size:25px;
  font-weight:900;
  animation:floatup .8s forwards;
}

@keyframes floatup{
  from{opacity:1;transform:translateY(0) scale(1)}
  to{opacity:0;transform:translateY(-90px) scale(1.4)}
}

.flash{
  position:fixed;
  inset:0;
  pointer-events:none;
  z-index:998;
  animation:flash .35s;
}

@keyframes flash{
  0%{background:#ff78ad44}
  100%{background:transparent}
}

.progress{
  height:14px;
  background:#ffffff12;
  border-radius:20px;
  overflow:hidden;
  margin:15px 0;
}

.progress>div{
  height:100%;
  background:linear-gradient(90deg,#ff4f91,#ffd76a);
  width:0%;
  transition:.25s;
}

.big-number{
  text-align:center;
  font-size:65px;
  font-weight:900;
  color:var(--gold);
}

.question{
  font-size:22px;
  font-weight:800;
  margin:18px 0;
}

.answers{
  display:flex;
  flex-wrap:wrap;
  justify-content:center;
}

input,
textarea{
  width:100%;
  padding:15px;
  border-radius:15px;
  border:1px solid #ffffff22;
  background:#10070d;
  color:white;
  outline:none;
  margin:8px 0;
}

textarea{
  min-height:180px;
  resize:vertical;
}

.feedback{
  min-height:28px;
  margin-top:10px;
  text-align:center;
  font-weight:900;
}

.good{
  color:var(--green);
}

.bad{
  color:#ff7890;
}

.wheel{
  width:min(75vw,330px);
  aspect-ratio:1;
  margin:20px auto;
  border-radius:50%;
  border:10px solid #ffd76a;
  position:relative;
  overflow:hidden;
  background:conic-gradient(
    #ff78ad 0 45deg,
    #7b3b68 45deg 90deg,
    #ffb5d2 90deg 135deg,
    #8f416e 135deg 180deg,
    #ff78ad 180deg 225deg,
    #7b3b68 225deg 270deg,
    #ffb5d2 270deg 315deg,
    #8f416e 315deg 360deg
  );
  transition:transform 3.5s cubic-bezier(.12,.7,.15,1);
}

.wheel::after{
  content:"❤️";
  position:absolute;
  inset:0;
  display:grid;
  place-items:center;
  font-size:45px;
}

.pointer{
  text-align:center;
  font-size:35px;
  height:35px;
}

.doors{
  display:grid;
  grid-template-columns:repeat(5,1fr);
  gap:8px;
}

.door{
  min-height:150px;
  background:linear-gradient(#59213f,#2a1020);
  border:2px solid #ff78ad55;
  border-radius:15px;
  color:white;
  font-size:30px;
  transition:.5s;
}

.door.open{
  transform:rotateY(180deg);
  background:#170b13;
}

.hpbox{
  margin:12px 0;
}

.hp{
  height:22px;
  border-radius:20px;
  overflow:hidden;
  background:#ffffff18;
}

.hp>div{
  height:100%;
  background:#ff526f;
  transition:.3s;
}

.boxers{
  display:flex;
  justify-content:space-around;
  align-items:center;
  font-size:80px;
  margin:25px 0;
}

.boxer.hit{
  animation:shake .25s;
}

.race{
  position:relative;
  background:#10070d;
  border-radius:20px;
  padding:15px;
  overflow:hidden;
}

.track{
  position:relative;
  height:75px;
  border-bottom:2px dashed #ffffff22;
}

.racer{
  position:absolute;
  left:0;
  top:12px;
  font-size:42px;
  transition:left .6s ease;
}

.maze{
  display:grid;
  grid-template-columns:repeat(5,1fr);
  max-width:420px;
  margin:20px auto;
  gap:4px;
}

.cell{
  aspect-ratio:1;
  display:grid;
  place-items:center;
  background:#ffffff0d;
  border-radius:8px;
  font-size:25px;
}

.wall{
  background:#000;
}

.lock{
  display:flex;
  justify-content:center;
  gap:8px;
  margin:20px 0;
}

.digit{
  width:70px;
  height:90px;
  display:grid;
  place-items:center;
  border-radius:15px;
  background:#10070d;
  border:2px solid #ff78ad44;
  font-size:42px;
  font-weight:900;
}

.gamble{
  text-align:center;
}

.pot{
  font-size:50px;
  color:var(--gold);
  font-weight:900;
}

.derby-options{
  display:flex;
  flex-wrap:wrap;
  justify-content:center;
}

.animal.selected,
.mode.selected{
  outline:4px solid var(--gold);
}

.derby-track{
  margin:20px 0;
}

.final{
  text-align:center;
}

.heart-rain{
  position:fixed;
  inset:0;
  pointer-events:none;
  overflow:hidden;
  z-index:997;
}

.rain-heart{
  position:absolute;
  top:-40px;
  animation:rain linear forwards;
}

@keyframes rain{
  to{
    transform:translateY(110vh) rotate(360deg);
    opacity:0;
  }
}

@media(max-width:600px){
  #app{padding:10px}
  .card{padding:16px;border-radius:22px}
  .doors{grid-template-columns:repeat(2,1fr)}
  .boxers{font-size:55px}
}
</style>
</head>

<body>

<div id="app">

<header>
  <div class="logo">🚂 Lulu Express 💗</div>
  <div class="subtitle">A little journey made with love</div>
</header>

<div class="scorebar">
  <div>💗 Score: <span id="score">0</span></div>
  <div class="eventno">Event <span id="eventNo">1</span>/21</div>
</div>

<main id="game"></main>

</div>

<script>

/* =========================================================
   CORE GAME STATE
   ========================================================= */

const game = document.getElementById("game");
const scoreEl = document.getElementById("score");
const eventEl = document.getElementById("eventNo");

const state = {
  score:0,
  currentEvent:1,
  finished:false
};

let eventTimer = null;
let eventInterval = null;
let cleanupEvent = null;

function saveGame(){
  localStorage.setItem("luluExpressSave",JSON.stringify(state));
}

function loadGame(){
  try{
    const saved = JSON.parse(
      localStorage.getItem("luluExpressSave")
    );

    if(saved){
      state.score = Number(saved.score)||0;
      state.currentEvent = Number(saved.currentEvent)||1;
      state.finished = !!saved.finished;
    }
  }catch(e){}
}

function updateHeader(){
  scoreEl.textContent = state.score;
  eventEl.textContent = state.currentEvent;
}

function addPoints(points){
  state.score += points;
  updateHeader();
  saveGame();
  floatingScore(points);
}

function floatingScore(points){
  const el = document.createElement("div");
  el.className="float";
  el.textContent=(points>=0?"+":"")+points;
  el.style.left=(Math.random()*70+15)+"%";
  el.style.top="50%";
  document.body.appendChild(el);
  setTimeout(()=>el.remove(),850);
}

function flash(){
  const f=document.createElement("div");
  f.className="flash";
  document.body.appendChild(f);
  setTimeout(()=>f.remove(),400);
}

function clearEventTimers(){
  if(eventTimer){
    clearTimeout(eventTimer);
    eventTimer=null;
  }

  if(eventInterval){
    clearInterval(eventInterval);
    eventInterval=null;
  }

  if(cleanupEvent){
    cleanupEvent();
    cleanupEvent=null;
  }
}

function render(){
  clearEventTimers();
  updateHeader();

  if(state.finished){
    finalResult();
    return;
  }

  const fn=EVENTS[state.currentEvent];

  if(fn){
    fn();
  }else{
    finalResult();
  }
}

function finishEvent(points,title,message){
  clearEventTimers();

  if(points){
    addPoints(points);
  }

  game.innerHTML=`
    <section class="card final">
      <div style="font-size:65px">
        ${points>=0?"💗":"💔"}
      </div>

      <h2>${title}</h2>

      <p>${message}</p>

      <p class="score">
        Score: ${state.score}
      </p>

      <button class="action" onclick="nextEvent()">
        Continue 🚂
      </button>
    </section>
  `;

  flash();
}

function nextEvent(){
  state.currentEvent++;

  if(state.currentEvent>21){
    state.finished=true;
  }

  saveGame();
  render();
}

function startOver(){
  localStorage.removeItem("luluExpressSave");

  state.score=0;
  state.currentEvent=1;
  state.finished=false;

  saveGame();
  render();
}

/* =========================================================
   EVENT 1
   CATCH THE HEARTS
   ========================================================= */

function event1(){

  let caught=0;
  let combo=0;
  const total=15;

  game.innerHTML=`
    <section class="card">
      <h2>❤️ Catch the Hearts</h2>

      <p>
        Catch every heart before they disappear.
        Consecutive catches build your combo!
      </p>

      <div class="progress">
        <div id="p1"></div>
      </div>

      <div class="arena" id="heartArena"></div>

      <div class="feedback" id="f1">
        Catch ${total} hearts!
      </div>
    </section>
  `;

  const arena=document.getElementById("heartArena");

  function spawn(){

    if(caught>=total){
      finishEvent(
        50,
        "💗 HEART MASTER",
        "You caught every heart!"
      );
      return;
    }

    const heart=document.createElement("button");

    const broken=Math.random()<.13;

    heart.className="target";
    heart.textContent=broken?"💔":"❤️";

    heart.style.left=Math.random()*82+"%";
    heart.style.top=Math.random()*78+"%";

    arena.appendChild(heart);

    let alive=true;

    const remove=setTimeout(()=>{
      if(alive){
        alive=false;
        heart.remove();
        combo=0;
        spawn();
      }
    },1700);

    heart.onclick=()=>{

      if(!alive)return;

      alive=false;
      clearTimeout(remove);
      heart.remove();

      if(broken){
        combo=0;
        addPoints(-5);
        document.getElementById("f1").textContent=
          "💔 Broken heart! Combo lost.";
      }else{

        combo++;

        const points=
          8 + Math.min(combo*2,20);

        addPoints(points);

        document.getElementById("f1").textContent=
          `💗 Nice! ${combo}x combo`;

        caught++;

        document.getElementById("p1").style.width=
          (caught/total*100)+"%";
      }

      spawn();
    };
  }

  spawn();
}

/* =========================================================
   EVENT 2
   HEART REFLEX
   ========================================================= */

function event2(){

  let round=0;
  let streak=0;
  let waiting=false;

  game.innerHTML=`
    <section class="card">
      <h2>⚡ Heart Reflex</h2>

      <p>
        Wait for the heart to turn pink.
        Tap too early and you lose points.
      </p>

      <div class="big-number" id="reactionIcon">💤</div>

      <div class="arena" id="reactionArena"></div>

      <div class="feedback" id="reactionStatus">
        Get ready...
      </div>
    </section>
  `;

  const arena=document.getElementById("reactionArena");

  function roundStart(){

    if(round>=8){
      finishEvent(
        60,
        "⚡ LIGHTNING REFLEXES",
        "You survived the reaction challenge!"
      );
      return;
    }

    round++;
    waiting=true;

    arena.innerHTML="";

    const target=document.createElement("button");

    target.className="target";
    target.textContent="💗";

    target.style.left=Math.random()*80+"%";
    target.style.top=Math.random()*75+"%";
    target.style.opacity=".3";

    arena.appendChild(target);

    document.getElementById("reactionStatus").textContent=
      `Round ${round}/8... wait!`;

    const delay=
      Math.max(500,1200-round*70);

    eventTimer=setTimeout(()=>{

      waiting=false;

      target.style.opacity="1";

      document.getElementById("reactionStatus").textContent=
        "TAP NOW!";

      eventTimer=setTimeout(()=>{
        if(!target.isConnected)return;

        target.remove();
        streak=0;

        document.getElementById("reactionStatus").textContent=
          "Too slow!";

        setTimeout(roundStart,600);
      },1400);

    },delay);

    target.onclick=()=>{

      if(waiting){

        clearTimeout(eventTimer);
        target.remove();

        streak=0;
        addPoints(-3);

        document.getElementById("reactionStatus").textContent=
          "💔 Too early!";

        eventTimer=setTimeout(roundStart,650);
        return;
      }

      clearTimeout(eventTimer);
      target.remove();

      streak++;

      const points=10+Math.min(streak*2,10);

      addPoints(points);

      document.getElementById("reactionStatus").textContent=
        `⚡ ${streak}x streak!`;

      flash();

      eventTimer=setTimeout(roundStart,500);
    };
  }

  roundStart();
}

/* =========================================================
   QUESTION BANK
   ========================================================= */

const QUESTION_BANK=[

  ["What is 7 × 8?","56"],
  ["What is 9 × 6?","54"],
  ["What is 12 × 4?","48"],
  ["What is 11 × 7?","77"],
  ["What is 8 × 8?","64"],
  ["What is 12 × 12?","144"],
  ["What is 9 × 9?","81"],
  ["What is 6 × 7?","42"],
  ["What is 11 × 9?","99"],
  ["What is 8 × 12?","96"],

  ["How many days are in a week?","7"],
  ["How many months are in a year?","12"],
  ["What planet do we live on?","Earth"],
  ["What is the opposite of hot?","cold"],
  ["How many legs does a spider have?","8"],
  ["How many sides does a triangle have?","3"],
  ["How many sides does a square have?","4"],
  ["What colour do you get by mixing red and white?","pink"],
  ["How many hours are in a day?","24"],
  ["How many minutes are in an hour?","60"],

  ["What is 5 × 9?","45"],
  ["What is 3 × 12?","36"],
  ["What is 4 × 11?","44"],
  ["What is 7 × 7?","49"],
  ["What is 6 × 12?","72"],
  ["What is 10 × 11?","110"],
  ["What is 8 × 9?","72"],
  ["What is 4 × 12?","48"],
  ["What is 5 × 12?","60"],
  ["What is 9 × 11?","99"]

];

function buildHugeQuestionBank(){

  const bank=[...QUESTION_BANK];

  for(let a=2;a<=12;a++){
    for(let b=2;b<=12;b++){

      bank.push([
        `What is ${a} × ${b}?`,
        String(a*b)
      ]);

      bank.push([
        `Calculate ${b} × ${a}.`,
        String(a*b)
      ]);
    }
  }

  const facts=[
    ["What is the capital of New Zealand?","Wellington"],
    ["What colour is made from blue and yellow?","green"],
    ["How many continents are there?","7"],
    ["How many letters are in the English alphabet?","26"],
    ["How many wheels does a bicycle have?","2"],
    ["What animal says moo?","cow"],
    ["What animal is known for having a long trunk?","elephant"],
    ["What is frozen water called?","ice"],
    ["What do bees make?","honey"],
    ["What is the largest ocean?","Pacific"]
  ];

  for(let i=0;i<100;i++){
    bank.push(...facts);
  }

  return bank;
}

function shuffle(array){
  return [...array].sort(()=>Math.random()-.5);
}

/* =========================================================
   EVENT 3
   BRAIN CHALLENGE
   ========================================================= */

function event3(){

  let questions=shuffle(buildHugeQuestionBank()).slice(0,10);
  let q=0;
  let streak=0;

  game.innerHTML=`
    <section class="card">
      <h2>🧠 Brain Challenge</h2>

      <div class="progress">
        <div id="brainProgress"></div>
      </div>

      <div id="brainQuestion"></div>

      <div class="answers" id="brainAnswers"></div>

      <div class="feedback" id="brainFeedback"></div>
    </section>
  `;

  function show(){

    if(q>=questions.length){

      finishEvent(
        50,
        "🧠 BRAIN POWER",
        "You made it through the challenge!"
      );

      return;
    }

    const item=questions[q];

    document.getElementById("brainProgress").style.width=
      (q/questions.length*100)+"%";

    document.getElementById("brainQuestion").innerHTML=`
      <div class="question">
        ${q+1}. ${item[0]}
      </div>
    `;

    const correct=item[1];

    let options=[correct];

    while(options.length<4){

      let fake;

      if(/×/.test(item[0])){
        fake=String(
          Math.max(
            1,
            Number(correct)+
            Math.floor(Math.random()*21)-10
          )
        );
      }else{
        fake=shuffle([
          "yes","no","blue","green","seven",
          "eight","ten","Earth","Moon"
        ])[0];
      }

      if(!options.includes(fake)){
        options.push(fake);
      }
    }

    options=shuffle(options);

    const container=document.getElementById("brainAnswers");
    container.innerHTML="";

    options.forEach(answer=>{

      const b=document.createElement("button");

      b.className="answer";
      b.textContent=answer;

      b.onclick=()=>{

        container
          .querySelectorAll("button")
          .forEach(x=>x.disabled=true);

        if(
          answer.toLowerCase()===
          correct.toLowerCase()
        ){

          streak++;

          addPoints(
            10+Math.min(streak*2,10)
          );

          document.getElementById("brainFeedback").textContent=
            "💗 Correct!";

        }else{

          streak=0;
          addPoints(-2);

          document.getElementById("brainFeedback").textContent=
            `💔 Correct answer: ${correct}`;
        }

        q++;

        eventTimer=setTimeout(show,650);
      };

      container.appendChild(b);
    });
  }

  show();
}

/* =========================================================
   EVENT 4
   HEART MEMORY
   ========================================================= */

function event4(){

  const symbols=[
    "❤️","💗","💖","💕",
    "🌹","⭐","🐬","💎"
  ];

  let sequence=[];
  let input=0;
  let showing=false;

  game.innerHTML=`
    <section class="card">
      <h2>🧩 Heart Memory</h2>

      <p id="memoryStatus">
        Watch the pattern...
      </p>

      <div class="grid grid16" id="memoryGrid"></div>
    </section>
  `;

  const grid=document.getElementById("memoryGrid");

  for(let i=0;i<16;i++){

    const b=document.createElement("button");

    b.className="memory-tile";
    b.dataset.index=i;
    b.textContent="❔";

    grid.appendChild(b);
  }

  for(let i=0;i<5;i++){
    sequence.push(
      Math.floor(Math.random()*16)
    );
  }

  function showPattern(){

    showing=true;
    input=0;

    document.getElementById("memoryStatus").textContent=
      "Watch carefully...";

    let i=0;

    function next(){

      if(i>=sequence.length){

        showing=false;

        document.getElementById("memoryStatus").textContent=
          "Now repeat it!";

        return;
      }

      const tile=
        grid.querySelector(
          `[data-index="${sequence[i]}"]`
        );

      tile.classList.add("active");

      setTimeout(()=>{
        tile.classList.remove("active");
      },350);

      i++;

      eventTimer=setTimeout(next,550);
    }

    next();
  }

  grid.onclick=e=>{

    const tile=e.target.closest(".memory-tile");

    if(!tile||showing)return;

    const index=Number(tile.dataset.index);

    if(index!==sequence[input]){

      tile.classList.add("wrong");

      finishEvent(
        -15,
        "💔 MEMORY FAILED",
        "One wrong tile ended the round."
      );

      return;
    }

    tile.classList.add("correct");

    setTimeout(()=>{
      tile.classList.remove("correct");
    },300);

    addPoints(10);
    input++;

    if(input>=sequence.length){

      finishEvent(
        50,
        "🧩 MEMORY MASTER",
        "Perfect pattern!"
      );
    }
  };

  showPattern();
}

/* =========================================================
   EVENT 5
   TRUE OR FALSE
   ========================================================= */

function event5(){

  const facts=[
    ["Liliana has green eyes.",true],
    ["Liliana's birthday is July 22.",true],
    ["Liliana studied Psychology.",true],
    ["Liliana's favourite number is 3.",true],
    ["Liliana has four piercings.",true],
    ["Liliana has one tattoo.",true],
    ["Liliana has seven siblings.",false],
    ["Liliana has two tattoos.",false],
    ["Liliana's favourite animal is a dolphin.",true],
    ["Liliana has no nieces or nephews.",false]
  ];

  let q=0;

  game.innerHTML=`
    <section class="card">
      <h2>🌸 Truth or False?</h2>
      <div id="tf"></div>
    </section>
  `;

  function show(){

    if(q>=facts.length){

      finishEvent(
        50,
        "🌸 YOU KNOW LILIANA",
        "You remembered the important things!"
      );

      return;
    }

    const item=facts[q];

    document.getElementById("tf").innerHTML=`
      <div class="question">
        ${item[0]}
      </div>

      <div class="answers">
        <button class="answer" onclick="tfAnswer(true)">
          TRUE 💗
        </button>

        <button class="answer" onclick="tfAnswer(false)">
          FALSE 💔
        </button>
      </div>

      <div class="feedback" id="tfFeedback"></div>
    `;
  }

  window.tfAnswer=function(answer){

    const correct=facts[q][1];

    if(answer===correct){
      addPoints(10);
      document.getElementById("tfFeedback").textContent=
        "💗 Correct!";
    }else{
      addPoints(-3);
      document.getElementById("tfFeedback").textContent=
        "💔 Not quite!";
    }

    q++;

    eventTimer=setTimeout(show,550);
  };

  show();
}

/* =========================================================
   EVENT 6
   LUCKY WHEEL
   ========================================================= */

function event6(){

  let spinning=false;
  const prizes=[5,10,15,20,25,30,40,50];

  game.innerHTML=`
    <section class="card" style="text-align:center">
      <h2>🎡 Lucky Heart Wheel</h2>

      <div class="pointer">▼</div>

      <div class="wheel" id="wheel"></div>

      <button class="action" id="spin">
        SPIN 💗
      </button>

      <div class="feedback" id="wheelResult"></div>
    </section>
  `;

  document.getElementById("spin").onclick=()=>{

    if(spinning)return;

    spinning=true;

    const prize=
      prizes[Math.floor(Math.random()*prizes.length)];

    const index=prizes.indexOf(prize);

    const rotation=
      1440+(360-index*45)+
      Math.floor(Math.random()*30);

    document.getElementById("wheel").style.transform=
      `rotate(${rotation}deg)`;

    eventTimer=setTimeout(()=>{

      addPoints(prize);

      document.getElementById("wheelResult").textContent=
        `🎉 You won ${prize} points!`;

      spinning=false;

      eventTimer=setTimeout(()=>{
        finishEvent(
          0,
          "🎡 WHEEL COMPLETE",
          "The wheel has decided your fate!"
        );
      },900);

    },3600);
  };
}

/* =========================================================
   EVENT 7
   SURVIVAL MEMORY
   ========================================================= */

function event7(){

  const symbols=[
    "❤️","🌹","⭐","🐬",
    "💎","💕","🌙","💗"
  ];

  let level=1;
  let sequence=[];
  let input=0;
  let accepting=false;

  game.innerHTML=`
    <section class="card">
      <h2>⚡ Survival Memory</h2>

      <p id="survivalStatus">
        Level 1
      </p>

      <div class="grid grid16" id="survivalGrid"></div>
    </section>
  `;

  const grid=document.getElementById("survivalGrid");

  function build(){

    sequence=[];

    for(let i=0;i<level+2;i++){

      sequence.push(
        Math.floor(Math.random()*16)
      );
    }

    showPattern();
  }

  function showPattern(){

    accepting=false;
    input=0;

    document.getElementById("survivalStatus").textContent=
      `Level ${level}: watch!`;

    grid.innerHTML="";

    for(let i=0;i<16;i++){

      const b=document.createElement("button");

      b.className="memory-tile";
      b.dataset.index=i;
      b.textContent=
        symbols[i%symbols.length];

      grid.appendChild(b);
    }

    let i=0;

    function reveal(){

      if(i>=sequence.length){

        accepting=true;

        document.getElementById("survivalStatus").textContent=
          "Repeat the pattern!";

        return;
      }

      const tile=
        grid.querySelector(
          `[data-index="${sequence[i]}"]`
        );

      tile.classList.add("active");

      setTimeout(()=>{
        tile.classList.remove("active");
      },300);

      i++;

      eventTimer=setTimeout(reveal,500);
    }

    reveal();
  }

  grid.onclick=e=>{

    const tile=e.target.closest(".memory-tile");

    if(!tile||!accepting)return;

    const index=Number(tile.dataset.index);

    if(index!==sequence[input]){

      finishEvent(
        -15,
        "💔 SURVIVAL FAILED",
        "One wrong move ended the survival round."
      );

      return;
    }

    addPoints(10);

    tile.classList.add("correct");

    setTimeout(()=>{
      tile.classList.remove("correct");
    },250);

    input++;

    if(input>=sequence.length){

      if(level>=5){

        finishEvent(
          80,
          "⚡ SURVIVAL MASTER",
          "You survived the final pattern!"
        );

      }else{

        level++;
        accepting=false;

        document.getElementById("survivalStatus").textContent=
          `Level ${level} incoming...`;

        eventTimer=setTimeout(build,800);
      }
    }
  };

  build();
}

/* =========================================================
   EVENT 8
   ADMIRER RACE
   ========================================================= */

function event8(){

  let player=0;
  let rival=0;
  let laps=0;

  game.innerHTML=`
    <section class="card">
      <h2>🏁 Admirer Race</h2>

      <p>Tap your heart whenever it appears!</p>

      <div id="race8"></div>

      <button class="action" id="raceHeart">
        ❤️ TAP!
      </button>

      <div class="feedback" id="race8Status"></div>
    </section>
  `;

  const race=document.getElementById("race8");

  function draw(){

    race.innerHTML="";

    for(let i=0;i<8;i++){

      race.innerHTML+=`
        <div class="track">
          <div class="racer"
               style="left:${player*10}%">
            💗
          </div>

          <div class="racer"
               style="left:${rival*10}%;top:48px">
            😈
          </div>
        </div>
      `;
    }
  }

  document.getElementById("raceHeart").onclick=()=>{

    if(laps>=8)return;

    laps++;
    player=Math.min(10,player+1);

    addPoints(8);

    if(Math.random()>.35){
      rival=Math.min(10,rival+1);
    }

    draw();

    document.getElementById("race8Status").textContent=
      `Lap ${laps}/8`;

    if(player>=8){

      finishEvent(
        60,
        "🏁 YOU WON!",
        "The admirer race is yours!"
      );
    }
  };

  draw();
}

/* =========================================================
   EVENT 9
   HEARTBREAK CHAMBER
   ========================================================= */

function event9(){

  const rewards=[30,15,-10,50,5];
  let round=0;

  game.innerHTML=`
    <section class="card">
      <h2>🚪 Heartbreak Chamber</h2>

      <p>Choose a door. Some hearts are lucky. Some are not.</p>

      <div class="doors" id="doors"></div>

      <div class="feedback" id="doorFeedback"></div>
    </section>
  `;

  function show(){

    const container=document.getElementById("doors");

    container.innerHTML="";

    rewards.forEach((_,i)=>{

      const b=document.createElement("button");

      b.className="door";
      b.textContent="💗";

      b.onclick=()=>{

        if(b.classList.contains("open"))return;

        b.classList.add("open");

        const result=rewards[i];

        addPoints(result);

        document.getElementById("doorFeedback").textContent=
          result>=0
            ?`🎉 You found ${result} points!`
            :`💔 You lost ${Math.abs(result)} points!`;

        round++;

        if(round>=5){

          eventTimer=setTimeout(()=>{
            finishEvent(
              0,
              "🚪 CHAMBER COMPLETE",
              "You survived all five doors!"
            );
          },700);

        }else{

          eventTimer=setTimeout(show,700);
        }
      };

      container.appendChild(b);
    });
  }

  show();
}

/* =========================================================
   EVENT 10
   BOXING
   ========================================================= */

function event10(){

  let playerHP=100;
  let enemyHP=100;

  game.innerHTML=`
    <section class="card">
      <h2>🥊 Heart Boxing</h2>

      <div class="hpbox">
        <b>You</b>
        <div class="hp">
          <div id="playerHP"></div>
        </div>
      </div>

      <div class="hpbox">
        <b>Opponent</b>
        <div class="hp">
          <div id="enemyHP"></div>
        </div>
      </div>

      <div class="boxers">
        <div id="you">🥊</div>
        <div>VS</div>
        <div id="enemy">🥊</div>
      </div>

      <div class="answers">
        <button class="action" onclick="boxingMove('punch')">
          👊 Punch
        </button>

        <button class="action" onclick="boxingMove('heavy')">
          💥 Heavy
        </button>

        <button class="action secondary" onclick="boxingMove('block')">
          🛡️ Block
        </button>
      </div>

      <div class="feedback" id="boxingFeedback"></div>
    </section>
  `;

  function update(){

    document.getElementById("playerHP").style.width=
      Math.max(0,playerHP)+"%";

    document.getElementById("enemyHP").style.width=
      Math.max(0,enemyHP)+"%";
  }

  window.boxingMove=function(move){

    if(playerHP<=0||enemyHP<=0)return;

    let damage=0;

    if(move==="punch"){
      damage=8+Math.floor(Math.random()*12);
    }

    if(move==="heavy"){
      damage=12+Math.floor(Math.random()*20);
    }

    if(move==="block"){
      damage=0;
    }

    enemyHP=Math.max(0,enemyHP-damage);

    document.getElementById("enemy").classList.add("hit");

    setTimeout(()=>{
      document.getElementById("enemy").classList.remove("hit");
    },250);

    addPoints(damage);

    if(enemyHP<=0){

      update();

      finishEvent(
        75,
        "🥊 KNOCKOUT!",
        "You won the Heart Boxing match!"
      );

      return;
    }

    let enemyDamage=
      6+Math.floor(Math.random()*15);

    if(move==="block"){
      enemyDamage=Math.max(0,enemyDamage-12);
    }

    playerHP=Math.max(0,playerHP-enemyDamage);

    document.getElementById("you").classList.add("hit");

    setTimeout(()=>{
      document.getElementById("you").classList.remove("hit");
    },250);

    update();

    document.getElementById("boxingFeedback").textContent=
      `You dealt ${damage}. They dealt ${enemyDamage}.`;

    if(playerHP<=0){

      finishEvent(
        -20,
        "💔 KNOCKED OUT",
        "The opponent got the final punch."
      );
    }
  };

  update();
}

/* =========================================================
   EVENT 11
   PERFECT MATCH
   ========================================================= */

function event11(){

  let chosen=[];
  let targets=shuffle(
    Array.from({length:16},(_,i)=>i)
  ).slice(0,6);

  game.innerHTML=`
    <section class="card">
      <h2>💞 Perfect Match</h2>

      <p id="matchStatus">
        Memorise the glowing tiles!
      </p>

      <div class="grid grid16" id="matchGrid"></div>
    </section>
  `;

  const grid=document.getElementById("matchGrid");

  for(let i=0;i<16;i++){

    const b=document.createElement("button");

    b.className="memory-tile";
    b.dataset.index=i;
    b.textContent="💗";

    grid.appendChild(b);
  }

  targets.forEach(index=>{
    grid.children[index].classList.add("active");
  });

  eventTimer=setTimeout(()=>{

    grid.querySelectorAll(".active")
      .forEach(x=>x.classList.remove("active"));

    document.getElementById("matchStatus").textContent=
      "Choose the six you remember!";

  },1800);

  grid.onclick=e=>{

    const tile=e.target.closest(".memory-tile");

    if(!tile)return;

    const index=Number(tile.dataset.index);

    if(chosen.includes(index))return;

    if(!targets.includes(index)){

      tile.classList.add("wrong");

      finishEvent(
        -15,
        "💔 NOT A PERFECT MATCH",
        "You chose the wrong tile."
      );

      return;
    }

    chosen.push(index);
    tile.classList.add("correct");
    addPoints(10);

    if(chosen.length===6){

      finishEvent(
        60,
        "💞 PERFECT MATCH",
        "You remembered every single one!"
      );
    }
  };
}

/* =========================================================
   EVENT 12
   LILIANA QUIZ
   ========================================================= */

function event12(){

  const facts=[
    ["How many nieces does Liliana have?","1"],
    ["How many nephews does Liliana have?","4"],
    ["How many tattoos does Liliana have?","1"],
    ["What colour are Liliana's eyes?","green"],
    ["How many piercings does Liliana have?","4"],
    ["What are her dogs called?","Aayla and Arlo"],
    ["How many siblings does Liliana have?","5"],
    ["What is her star sign?","Leo"],
    ["What is Liliana afraid of?","drowning"],
    ["What did Liliana study at university?","Psychology"]
  ];

  let q=0;

  game.innerHTML=`
    <section class="card">
      <h2>🌸 How Well Do You Know Liliana?</h2>
      <div id="lilianaQuiz"></div>
    </section>
  `;

  function show(){

    if(q>=facts.length){

      finishEvent(
        70,
        "🌸 LILIANA EXPERT",
        "You know your best friend!"
      );

      return;
    }

    const item=facts[q];

    document.getElementById("lilianaQuiz").innerHTML=`
      <div class="question">${item[0]}</div>

      <input
        id="liliAnswer"
        placeholder="Type your answer..."
        autocomplete="off"
      >

      <button class="action" onclick="submitLili()">
        Submit 💗
      </button>

      <div class="feedback" id="liliFeedback"></div>
    `;

    setTimeout(()=>{
      document.getElementById("liliAnswer").focus();
    },100);
  }

  window.submitLili=function(){

    const input=
      document.getElementById("liliAnswer");

    const answer=input.value
      .trim()
      .toLowerCase();

    const correct=facts[q][1]
      .toLowerCase();

    if(answer===correct){

      addPoints(10);

      document.getElementById("liliFeedback").textContent=
        "💗 Correct!";

    }else{

      addPoints(-3);

      document.getElementById("liliFeedback").textContent=
        `💔 Answer: ${facts[q][1]}`;
    }

    q++;

    eventTimer=setTimeout(show,650);
  };

  show();
}

/* =========================================================
   EVENT 13
   REACTION GAUNTLET
   ========================================================= */

function event13(){

  const commands=[
    "TAP",
    "HOLD",
    "DOUBLE TAP"
  ];

  let round=0;
  let holdTimer=null;
  let doubleCount=0;

  game.innerHTML=`
    <section class="card" style="text-align:center">
      <h2>⚡ Reaction Gauntlet</h2>

      <div class="big-number" id="command">
        TAP
      </div>

      <button
        class="action"
        id="reactionButton"
        style="width:80%;height:180px;font-size:35px"
      >
        💗
      </button>

      <div class="feedback" id="gauntletFeedback"></div>
    </section>
  `;

  const btn=document.getElementById("reactionButton");

  function next(){

    if(round>=10){

      finishEvent(
        60,
        "⚡ GAUNTLET COMPLETE",
        "Your reactions are lightning fast!"
      );

      return;
    }

    round++;

    const command=
      commands[Math.floor(Math.random()*commands.length)];

    document.getElementById("command").textContent=
      command;

    doubleCount=0;
  }

  btn.addEventListener("click",()=>{

    const command=
      document.getElementById("command").textContent;

    if(command==="TAP"){

      addPoints(5);
      next();

    }else if(command==="DOUBLE TAP"){

      doubleCount++;

      if(doubleCount>=2){

        addPoints(5);
        next();
      }

    }else{

      addPoints(-3);

      document.getElementById("gauntletFeedback").textContent=
        "💔 Wrong action!";
    }
  });

  btn.addEventListener("pointerdown",()=>{

    const command=
      document.getElementById("command").textContent;

    if(command==="HOLD"){

      holdTimer=setTimeout(()=>{

        addPoints(5);
        next();

      },500);
    }
  });

  btn.addEventListener("pointerup",()=>{

    if(holdTimer){

      clearTimeout(holdTimer);
      holdTimer=null;
    }
  });

  next();
}

/* =========================================================
   EVENT 14
   HEART HUNT
   ========================================================= */

function event14(){

  const walls=new Set([
    1,2,6,7,20,21,22
  ]);

  let player=0;
  const goal=24;

  game.innerHTML=`
    <section class="card">
      <h2>🗺️ Heart Hunt</h2>

      <p>
        Find your way through the maze to the heart.
      </p>

      <div class="maze" id="maze"></div>

      <div class="answers">
        <button class="action" onclick="mazeMove(-5)">⬆️</button>
      </div>

      <div class="answers">
        <button class="action" onclick="mazeMove(-1)">⬅️</button>
        <button class="action" onclick="mazeMove(1)">➡️</button>
      </div>

      <div class="answers">
        <button class="action" onclick="mazeMove(5)">⬇️</button>
      </div>
    </section>
  `;

  function draw(){

    const maze=document.getElementById("maze");

    maze.innerHTML="";

    for(let i=0;i<25;i++){

      const c=document.createElement("div");

      c.className="cell";

      if(walls.has(i)){
        c.classList.add("wall");
        c.textContent="🖤";
      }else if(i===player){
        c.textContent="🚂";
      }else if(i===goal){
        c.textContent="💗";
      }else{
        c.textContent="·";
      }

      maze.appendChild(c);
    }
  }

  window.mazeMove=function(change){

    const next=player+change;

    if(next<0||next>24)return;

    if(change===1 && player%5===4)return;
    if(change===-1 && player%5===0)return;

    if(walls.has(next)){
      addPoints(-1);
      return;
    }

    player=next;
    addPoints(2);

    draw();

    if(player===goal){

      finishEvent(
        70,
        "💗 HEART FOUND",
        "You made it through the maze!"
      );
    }
  };

  draw();
}

/* =========================================================
   EVENT 15
   LOVE LOCK
   ========================================================= */

function event15(){

  const correct=[3,3,3,3];
  const digits=[0,0,0,0];

  game.innerHTML=`
    <section class="card" style="text-align:center">
      <h2>🔐 Love Lock</h2>

      <p>
        Turn each dial until you discover the secret code.
      </p>

      <div class="lock" id="lock"></div>

      <button class="action" onclick="checkLock()">
        🔓 Unlock
      </button>

      <div class="feedback" id="lockFeedback"></div>
    </section>
  `;

  const lock=document.getElementById("lock");

  digits.forEach((_,i)=>{

    const b=document.createElement("button");

    b.className="digit";
    b.textContent="0";

    b.onclick=()=>{

      digits[i]=(digits[i]+1)%10;
      b.textContent=digits[i];
    };

    lock.appendChild(b);
  });

  window.checkLock=function(){

    if(
      digits.every(
        (x,i)=>x===correct[i]
      )
    ){

      finishEvent(
        80,
        "🔓 LOVE UNLOCKED",
        "You found the secret code!"
      );

    }else{

      addPoints(-5);

      document.getElementById("lockFeedback").textContent=
        "💔 Not the right combination.";
    }
  };
}

/* =========================================================
   EVENT 16
   CUPID SHOOTOUT
   ========================================================= */

function event16(){

  let time=20;
  let points=0;

  game.innerHTML=`
    <section class="card">
      <h2>🏹 Cupid Shootout</h2>

      <div class="big-number" id="cupidTime">
        20
      </div>

      <div class="arena" id="cupidArena"></div>

      <div class="feedback">
        💗 Hearts +6 &nbsp;&nbsp; 💔 Broken hearts -3
      </div>
    </section>
  `;

  const arena=document.getElementById("cupidArena");

  function spawn(){

    if(time<=0)return;

    const target=document.createElement("button");

    target.className="target";
    target.textContent=
      Math.random()<.2?"💔":"❤️";

    target.style.left=Math.random()*82+"%";
    target.style.top=Math.random()*78+"%";

    arena.appendChild(target);

    const lifetime=setTimeout(()=>{
      target.remove();
    },1000);

    target.onclick=()=>{

      clearTimeout(lifetime);

      if(target.textContent==="❤️"){

        addPoints(6);
        points+=6;

      }else{

        addPoints(-3);
        points-=3;
      }

      target.remove();
    };
  }

  eventInterval=setInterval(()=>{

    time--;

    document.getElementById("cupidTime").textContent=
      time;

    if(time<=0){

      clearInterval(eventInterval);

      finishEvent(
        0,
        "🏹 CUPID COMPLETE",
        `You scored ${points} points during the shootout!`
      );

      return;
    }

    spawn();

  },1000);

  spawn();
}

/* =========================================================
   EVENT 17
   COUNTDOWN
   ========================================================= */

function event17(){

  const tasks=[
    ["Tap ❤️","❤️"],
    ["Tap 🌹","🌹"],
    ["Tap ⭐","⭐"],
    ["Tap 🐬","🐬"],
    ["Tap GOLD","GOLD"]
  ];

  let challenge=0;

  game.innerHTML=`
    <section class="card">
      <h2>⏱️ Countdown Challenge</h2>

      <div class="big-number" id="countdown">
        3
      </div>

      <div id="countdownGame"></div>
    </section>
  `;

  function show(){

    if(challenge>=tasks.length){

      finishEvent(
        60,
        "⏱️ COUNTDOWN COMPLETE",
        "You completed every rapid challenge!"
      );

      return;
    }

    const task=tasks[challenge];

    const options=shuffle([
      task[1],
      ...shuffle([
        "❤️","🌹","⭐","🐬","GOLD"
      ]).filter(x=>x!==task[1]).slice(0,3)
    ]);

    let count=3;

    document.getElementById("countdown").textContent=
      count;

    const cd=setInterval(()=>{

      count--;

      document.getElementById("countdown").textContent=
        count;

      if(count<=0){

        clearInterval(cd);

        document.getElementById("countdown").textContent=
          "GO!";

        document.getElementById("countdownGame").innerHTML=`
          <div class="question">${task[0]}</div>
          <div class="answers" id="countChoices"></div>
        `;

        options.forEach(answer=>{

          const b=document.createElement("button");

          b.className="answer";
          b.textContent=answer;

          b.onclick=()=>{

            if(answer===task[1]){
              addPoints(5);
            }else{
              addPoints(-3);
            }

            challenge++;
            show();
          };

          document
            .getElementById("countChoices")
            .appendChild(b);
        });
      }

    },700);
  }

  show();
}

/* =========================================================
   EVENT 18
   ULTIMATE GAMBLE
   ========================================================= */

function event18(){

  let pot=100;
  let turns=0;

  game.innerHTML=`
    <section class="card gamble">
      <h2>🎰 Ultimate Gamble</h2>

      <p>Risk the pot or walk away.</p>

      <div class="pot" id="pot">
        100
      </div>

      <button class="action" onclick="gamble('risk')">
        🎰 RISK IT
      </button>

      <button class="action secondary" onclick="gamble('leave')">
        💗 TAKE IT
      </button>

      <div class="feedback" id="gambleFeedback"></div>
    </section>
  `;

  window.gamble=function(choice){

    if(choice==="leave"){

      finishEvent(
        pot,
        "💰 CASHED OUT",
        `You walked away with ${pot} points!`
      );

      return;
    }

    turns++;

    if(Math.random()<.55){

      pot*=2;

      document.getElementById("gambleFeedback").textContent=
        "🎉 DOUBLE!";

    }else{

      pot=Math.floor(pot/2);

      document.getElementById("gambleFeedback").textContent=
        "💔 Ouch... half the pot is gone.";
    }

    document.getElementById("pot").textContent=
      pot;

    if(turns>=5){

      finishEvent(
        pot,
        "🎰 GAMBLE COMPLETE",
        `Your final pot was ${pot}.`
      );
    }
  };
}

/* =========================================================
   EVENT 19
   LOVE LETTER
   ========================================================= */

function event19(){

  game.innerHTML=`
    <section class="card">
      <h2>💌 Write a Love Letter</h2>

      <p>
        Write something from your heart.
        There is no perfect answer.
      </p>

      <textarea
        id="loveLetter"
        placeholder="Write your message here..."
      ></textarea>

      <button class="action" onclick="submitLetter()">
        💌 Send My Letter
      </button>

      <div class="feedback" id="letterFeedback"></div>
    </section>
  `;

  window.submitLetter=function(){

    const text=
      document.getElementById("loveLetter").value.trim();

    if(text.length<20){

      document.getElementById("letterFeedback").textContent=
        "💗 Write at least 20 characters.";

      return;
    }

    addPoints(100);

    game.innerHTML=`
      <section class="card final">
        <div style="font-size:70px">💌</div>

        <h2>Your letter has been sent.</h2>

        <p>
          Sometimes the smallest words can carry
          the biggest feelings.
        </p>

        <button class="action" onclick="nextEvent()">
          Continue 🚂
        </button>
      </section>
    `;
  };
}

/* =========================================================
   EVENT 20
   LULU DERBY
   ========================================================= */

const DERBY_LENGTH=36;

const DERBY_MODES={
  easy:{
    interval:3200,
    twoChance:.08
  },
  medium:{
    interval:2700,
    twoChance:.18
  },
  hard:{
    interval:2200,
    twoChance:.32
  },
  expert:{
    interval:1800,
    twoChance:.48
  }
};

const ANIMALS=[
  ["Horse","🐎"],
  ["Wolf","🐺"],
  ["Fox","🦊"],
  ["Tiger","🐯"],
  ["Panda","🐼"],
  ["Koala","🐨"],
  ["Bunny","🐰"],
  ["Lion","🦁"]
];

let derbyQuestion=0;
let derbyQuestions=[];
let derbyPlayerPosition=0;
let derbyComputerPosition=0;
let derbyComputerTimer=null;
let derbyRaceFinished=false;
let derbyQuestionLocked=true;
let derbyMode="medium";
let derbyPlayerIcon="🐎";
let derbyPlayerIconName="Horse";

function normaliseAnswer(answer){

  return String(answer)
    .trim()
    .toLowerCase()
    .replace(/[.,!?'"`]/g,"")
    .replace(/\s+/g," ");
}

function buildDerbyQuestions(){

  return shuffle(
    buildHugeQuestionBank()
  ).slice(0,80);
}

function event20(){

  derbyQuestion=0;
  derbyQuestions=buildDerbyQuestions();

  derbyPlayerPosition=0;
  derbyComputerPosition=0;
  derbyRaceFinished=false;
  derbyQuestionLocked=true;

  game.innerHTML=`
    <section class="card">
      <h2>🏇 The Lulu Derby</h2>

      <p>
        Choose your racer and difficulty.
      </p>

      <div class="derby-options">
        ${ANIMALS.map(
          ([name,icon])=>`
            <button
              class="animal ${name==="Horse"?"selected":""}"
              onclick="chooseAnimal('${name}','${icon}',this)"
            >
              ${icon} ${name}
            </button>
          `
        ).join("")}
      </div>

      <div class="derby-options">
        ${Object.keys(DERBY_MODES).map(
          mode=>`
            <button
              class="mode ${mode==="medium"?"selected":""}"
              onclick="chooseMode('${mode}',this)"
            >
              ${mode.toUpperCase()}
            </button>
          `
        ).join("")}
      </div>

      <div id="derbyStartArea">
        <button class="action" onclick="startDerby()">
          🏁 Start Race
        </button>
      </div>
    </section>
  `;
}

window.chooseAnimal=function(name,icon,button){

  derbyPlayerIcon=name==="Horse"?icon:icon;
  derbyPlayerIconName=name;
  derbyPlayerIcon=icon;

  document
    .querySelectorAll(".animal")
    .forEach(b=>b.classList.remove("selected"));

  button.classList.add("selected");
};

window.chooseMode=function(mode,button){

  derbyMode=mode;

  document
    .querySelectorAll(".mode")
    .forEach(b=>b.classList.remove("selected"));

  button.classList.add("selected");
};

window.startDerby=function(){

  let count=5;

  document.getElementById("derbyStartArea").innerHTML=`
    <div class="big-number" id="derbyCountdown">
      5
    </div>
  `;

  const timer=setInterval(()=>{

    count--;

    document.getElementById("derbyCountdown").textContent=
      count;

    if(count<=0){

      clearInterval(timer);
      beginDerbyRace();
    }

  },1000);
};

function beginDerbyRace(){

  game.innerHTML=`
    <section class="card">
      <h2>🏇 Lulu Derby</h2>

      <div class="derby-track">

        <div class="race">
          <div class="track">
            <div
              class="racer"
              id="playerRacer"
            >
              ${derbyPlayerIcon}
            </div>
          </div>

          <div class="track">
            <div
              class="racer"
              id="computerRacer"
            >
              🤖
            </div>
          </div>
        </div>

      </div>

      <div class="progress">
        <div id="derbyProgress"></div>
      </div>

      <div id="derbyQuestionArea"></div>

      <div class="feedback" id="derbyFeedback">
        Race started!
      </div>
    </section>
  `;

  derbyQuestionLocked=false;

  startComputer();

  showDerbyQuestion();
}

function startComputer(){

  const mode=DERBY_MODES[derbyMode];

  derbyComputerTimer=setInterval(()=>{

    if(derbyRaceFinished)return;

    const movement=
      Math.random()<mode.twoChance?2:1;

    derbyComputerPosition=
      Math.min(
        DERBY_LENGTH,
        derbyComputerPosition+movement
      );

    drawDerby();

    if(derbyComputerPosition>=DERBY_LENGTH){

      finishDerby(false);
    }

  },mode.interval);
}

function drawDerby(){

  const player=
    document.getElementById("playerRacer");

  const computer=
    document.getElementById("computerRacer");

  if(!player||!computer)return;

  player.style.left=
    (derbyPlayerPosition/DERBY_LENGTH*90)+"%";

  computer.style.left=
    (derbyComputerPosition/DERBY_LENGTH*90)+"%";

  const progress=
    derbyPlayerPosition/DERBY_LENGTH*100;

  document.getElementById("derbyProgress").style.width=
    progress+"%";
}

function showDerbyQuestion(){

  if(derbyRaceFinished)return;

  const question=
    derbyQuestions[derbyQuestion];

  derbyQuestionLocked=false;

  document.getElementById("derbyQuestionArea").innerHTML=`
    <div class="question">
      ${question[0]}
    </div>

    <input
      id="derbyAnswer"
      placeholder="Type your answer..."
      autocomplete="off"
    >

    <button
      class="action"
      onclick="submitDerbyAnswer()"
    >
      Answer 🏁
    </button>
  `;

  document
    .getElementById("derbyAnswer")
    .focus();
}

window.submitDerbyAnswer=function(){

  if(derbyQuestionLocked||derbyRaceFinished)return;

  derbyQuestionLocked=true;

  const question=
    derbyQuestions[derbyQuestion];

  const input=
    document.getElementById("derbyAnswer");

  const typed=
    normaliseAnswer(input.value);

  const correct=
    normaliseAnswer(question[1]);

  if(typed===correct){

    const movement=
      Math.random()>.58?2:1;

    derbyPlayerPosition=
      Math.min(
        DERBY_LENGTH,
        derbyPlayerPosition+movement
      );

    addPoints(20);

    document.getElementById("derbyFeedback").textContent=
      `💗 Correct! You moved ${movement} space${movement>1?"s":""}.`;

  }else{

    addPoints(2);

    document.getElementById("derbyFeedback").textContent=
      `💔 Wrong. Answer: ${question[1]}`;
  }

  derbyQuestion++;

  drawDerby();

  if(derbyPlayerPosition>=DERBY_LENGTH){

    finishDerby(true);
    return;
  }

  if(derbyQuestion>=derbyQuestions.length){
    derbyQuestions=buildDerbyQuestions();
    derbyQuestion=0;
  }

  eventTimer=setTimeout(
    showDerbyQuestion,
    650
  );
};

function finishDerby(playerWon){

  if(derbyRaceFinished)return;

  derbyRaceFinished=true;

  if(derbyComputerTimer){
    clearInterval(derbyComputerTimer);
    derbyComputerTimer=null;
  }

  clearEventTimers();

  if(playerWon){

    addPoints(200);

    finishEvent(
      0,
      "🏆 DERBY CHAMPION",
      `Your ${derbyPlayerIconName} crossed the finish line first!`
    );

  }else{

    addPoints(50);

    finishEvent(
      0,
      "🏁 RACE FINISHED",
      "The computer reached the finish first, but you still earned points."
    );
  }
}

/* =========================================================
   EVENT 21
   FINAL CHALLENGE
   ========================================================= */

const FINAL_QUIZ=[

  ["What colour are Liliana's eyes?","Green"],
  ["What is Liliana's birthday?","July 22"],
  ["What did Liliana study?","Psychology"],
  ["What is her favourite number?","3"],
  ["How many siblings does she have?","5"],
  ["How many piercings does she have?","4"],
  ["How many tattoos does she have?","1"],
  ["What animal does she love?","Dolphins"],
  ["How many nieces does she have?","1"],
  ["How many nephews does she have?","4"],
  ["What is her star sign?","Leo"],
  ["What are her dogs called?","Aayla and Arlo"],
  ["What is she afraid of?","Drowning"],
  ["What is one flower she likes?","Sunflowers"],
  ["What is another flower she likes?","Roses"],
  ["What food does she love?","Sushi"],
  ["What movie does she like?","Me Before You"],
  ["What colour does she like?","Baby pink"],
  ["How long have you been best friends?","6 years"],
  ["What kind of writing does she like?","Poetry"],
  ["What kind of songs does she like?","Sad songs"],
  ["What does she want to be one day?","A mum"],
  ["What gender baby has she imagined having?","A girl"],
  ["What is her tattoo?","Semicolon"],
  ["What is Liliana's personality like?","Caring"],
  ["What quality does she have?","Empathy"],
  ["What animal is connected to her quiz?","Dolphin"],
  ["What is her birthday month?","July"],
  ["How many years of friendship are celebrated?","6"],
  ["What number is special to her?","3"],
  ["What colour is associated with her?","Baby pink"],
  ["What subject did she study?","Psychology"],
  ["What type of music does she enjoy?","Sad songs"],
  ["What does she want someday?","Children"],
  ["What flower does she like?","Roses"],
  ["What other flower does she like?","Sunflowers"],
  ["What food is one of her favourites?","Sushi"],
  ["What animal does she like?","Dolphins"],
  ["What movie is a favourite?","Me Before You"],
  ["What does the semicolon represent in her tattoo?","Her tattoo"]
];

let finalIndex=0;

function event21(){

  finalIndex=0;

  game.innerHTML=`
    <section class="card">
      <h2>👑 Final Challenge</h2>

      <p>
        This is the final level. Prove how well you know Liliana.
      </p>

      <div class="progress">
        <div id="finalProgress"></div>
      </div>

      <div id="finalQuestion"></div>
    </section>
  `;

  showFinalQuestion();
}

function showFinalQuestion(){

  if(finalIndex>=FINAL_QUIZ.length){

    showWrittenFinal();

    return;
  }

  const item=FINAL_QUIZ[finalIndex];

  document.getElementById("finalProgress").style.width=
    (finalIndex/FINAL_QUIZ.length*100)+"%";

  const wrongAnswers=shuffle(
    FINAL_QUIZ
      .map(x=>x[1])
      .filter(x=>x!==item[1])
  ).slice(0,3);

  const answers=shuffle([
    item[1],
    ...wrongAnswers
  ]);

  document.getElementById("finalQuestion").innerHTML=`
    <div class="question">
      ${finalIndex+1}. ${item[0]}
    </div>

    <div class="answers" id="finalAnswers"></div>

    <div class="feedback" id="finalFeedback"></div>
  `;

  answers.forEach(answer=>{

    const b=document.createElement("button");

    b.className="answer";
    b.textContent=answer;

    b.onclick=()=>{

      document
        .querySelectorAll("#finalAnswers button")
        .forEach(x=>x.disabled=true);

      if(
        normaliseAnswer(answer)===
        normaliseAnswer(item[1])
      ){

        addPoints(15);

        document.getElementById("finalFeedback").textContent=
          "👑 Correct!";

      }else{

        addPoints(-3);

        document.getElementById("finalFeedback").textContent=
          `💔 Answer: ${item[1]}`;
      }

      finalIndex++;

      eventTimer=setTimeout(
        showFinalQuestion,
        550
      );
    };

    document
      .getElementById("finalAnswers")
      .appendChild(b);
  });
}

function showWrittenFinal(){

  game.innerHTML=`
    <section class="card final">

      <div style="font-size:70px">
        👑💗
      </div>

      <h2>The Final Question</h2>

      <p>
        Why should Liliana choose you?
      </p>

      <textarea
        id="finalWritten"
        placeholder="Tell her why..."
      ></textarea>

      <button
        class="action"
        onclick="submitFinalWritten()"
      >
        💗 Final Answer
      </button>

      <div class="feedback" id="finalWrittenFeedback"></div>

    </section>
  `;
}

window.submitFinalWritten=function(){

  const answer=
    document
      .getElementById("finalWritten")
      .value
      .trim();

  if(answer.length<10){

    document
      .getElementById("finalWrittenFeedback")
      .textContent=
      "💗 Tell her a little more.";
    return;
  }

  addPoints(150);

  state.finished=true;

  saveGame();

  finalResult();
};

/* =========================================================
   FINAL RESULT
   ========================================================= */

function finalResult(){

  clearEventTimers();

  const qualifies=
    state.score>3000;

  game.innerHTML=`
    <section class="card final">

      <div style="font-size:85px">
        ${qualifies?"💗":"🚂"}
      </div>

      <h2>
        ${qualifies
          ?"PRIVATE CALL UNLOCKED"
          :"THE JOURNEY IS COMPLETE"}
      </h2>

      <div class="pot">
        ${state.score}
      </div>

      <p>
        Final Score
      </p>

      ${
        qualifies
        ?`
          <p class="good">
            🎉 You scored more than 3000 points!
            The private call is unlocked.
          </p>
        `
        :`
          <p class="muted">
            You needed more than 3000 points.
            Exactly 3000 is not enough.
          </p>
        `
      }

      <p>
        ${qualifies
          ?"You made it all the way to the end. 💗"
          :"Every point brought you closer to the finish."}
      </p>

      <button
        class="action"
        onclick="startOver()"
      >
        🔄 Play Again
      </button>

    </section>
  `;

  if(qualifies){
    heartsRain();
  }
}

/* =========================================================
   HEART RAIN
   ========================================================= */

function heartsRain(){

  const container=document.createElement("div");

  container.className="heart-rain";

  document.body.appendChild(container);

  for(let i=0;i<45;i++){

    const heart=document.createElement("div");

    heart.className="rain-heart";

    heart.textContent=
      shuffle(["❤️","💗","💖","💕","🌹"])[0];

    heart.style.left=
      Math.random()*100+"%";

    heart.style.fontSize=
      (15+Math.random()*25)+"px";

    heart.style.animationDuration=
      (2+Math.random()*3)+"s";

    heart.style.animationDelay=
      Math.random()*2+"s";

    container.appendChild(heart);
  }

  setTimeout(()=>{
    container.remove();
  },6500);
}

/* =========================================================
   EVENT TABLE
   ========================================================= */

const EVENTS={
  1:event1,
  2:event2,
  3:event3,
  4:event4,
  5:event5,
  6:event6,
  7:event7,
  8:event8,
  9:event9,
  10:event10,
  11:event11,
  12:event12,
  13:event13,
  14:event14,
  15:event15,
  16:event16,
  17:event17,
  18:event18,
  19:event19,
  20:event20,
  21:event21
};

/* =========================================================
   START
   ========================================================= */

loadGame();
render();

</script>

</body>
</html>

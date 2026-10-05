<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#180b14">
<title>Lulu Express 🚂💗</title>

<style>
:root{
  --bg:#120810;
  --panel:#281321;
  --panel2:#35182a;
  --pink:#f49bc5;
  --pink-dark:#b84d86;
  --light:#ffe0ed;
  --gold:#f5cf70;
  --green:#8fe0ae;
  --red:#ff718d;
  --text:#fff8fc;
  --muted:#d7b9c9;
}

*{box-sizing:border-box}

body{
  margin:0;
  min-height:100vh;
  background:
    radial-gradient(circle at top,#642848 0%,#2b1323 35%,#120810 75%);
  color:var(--text);
  font-family:Arial,Helvetica,sans-serif;
}

button,input,textarea{
  font:inherit;
}

button{
  cursor:pointer;
}

#app{
  max-width:760px;
  margin:auto;
  padding:16px 14px 45px;
}

.topbar{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:10px;
  margin-bottom:15px;
}

.logo{
  font-size:21px;
  font-weight:900;
}

.logo span{
  color:var(--pink);
}

.icon-btn{
  background:#ffffff12;
  color:white;
  border:1px solid #ffffff22;
  border-radius:13px;
  padding:9px 12px;
}

.panel{
  background:linear-gradient(145deg,#301627,#1d0e18);
  border:1px solid #ffffff18;
  border-radius:24px;
  padding:20px;
  box-shadow:0 16px 45px #0009;
}

.center{text-align:center}

.badge{
  display:inline-block;
  padding:6px 10px;
  border-radius:999px;
  background:#f49bc51b;
  border:1px solid #f49bc544;
  color:var(--light);
  font-size:11px;
  font-weight:900;
  letter-spacing:1px;
  text-transform:uppercase;
}

h1{
  font-size:42px;
  line-height:1;
  margin:10px 0;
}

h2{
  font-size:28px;
  margin:8px 0;
}

h3{
  margin:5px 0 9px;
}

p{
  color:var(--muted);
  line-height:1.5;
}

.btn{
  width:100%;
  padding:14px 16px;
  border:0;
  border-radius:16px;
  margin-top:9px;
  background:linear-gradient(135deg,#f7a8ca,#bc4d87);
  color:#270d1c;
  font-weight:900;
}

.btn.gold{
  background:linear-gradient(135deg,#ffe79d,#d8ac40);
}

.btn.alt{
  background:#ffffff0d;
  color:white;
  border:1px solid #ffffff20;
}

.btn.red{
  background:linear-gradient(135deg,#ff9bad,#d44e70);
}

.btn:disabled{
  opacity:.45;
  cursor:not-allowed;
}

input,textarea{
  width:100%;
  padding:14px;
  border-radius:14px;
  border:1px solid #ffffff20;
  background:#ffffff0b;
  color:white;
  outline:none;
}

textarea{
  min-height:130px;
  resize:vertical;
}

.stats{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:8px;
  margin:13px 0;
}

.stat{
  background:#ffffff08;
  border:1px solid #ffffff12;
  border-radius:15px;
  padding:10px;
  text-align:center;
}

.stat b{
  display:block;
  font-size:21px;
  color:var(--light);
}

.stat small{
  color:var(--muted);
}

.progress{
  height:8px;
  background:#ffffff10;
  border-radius:999px;
  overflow:hidden;
  margin:12px 0;
}

.progress-fill{
  height:100%;
  width:0;
  background:linear-gradient(90deg,var(--pink),var(--gold));
  transition:.3s;
}

.notice{
  padding:12px;
  border-radius:14px;
  background:#f49bc510;
  border:1px solid #f49bc530;
  color:var(--muted);
  margin:11px 0;
}

.choices{
  display:grid;
  gap:9px;
}

.choice{
  width:100%;
  padding:14px;
  border-radius:15px;
  border:1px solid #ffffff18;
  background:#ffffff09;
  color:white;
  text-align:left;
}

.choice.correct{
  background:#8fe0ae20;
  border-color:#8fe0ae88;
}

.choice.wrong{
  background:#ff718d20;
  border-color:#ff718d88;
}

.grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:9px;
}

.big{
  font-size:50px;
  font-weight:1000;
  color:var(--gold);
}

.timer{
  font-size:35px;
  font-weight:1000;
  color:var(--gold);
  text-align:center;
}

.small{
  color:var(--muted);
  font-size:12px;
}

.round-list{
  display:grid;
  gap:7px;
  margin-top:14px;
}

.round{
  display:flex;
  align-items:center;
  gap:9px;
  padding:10px;
  border-radius:14px;
  background:#ffffff07;
  border:1px solid #ffffff10;
}

.round.locked{
  opacity:.38;
}

.round.current{
  border-color:#f49bc566;
  background:#f49bc510;
}

.round-num{
  width:33px;
  height:33px;
  border-radius:50%;
  display:grid;
  place-items:center;
  background:#ffffff10;
  font-weight:900;
}

.round.current .round-num{
  background:var(--pink);
  color:#32101f;
}

.arena{
  height:340px;
  position:relative;
  overflow:hidden;
  border-radius:20px;
  background:radial-gradient(circle,#61274a,#180b15);
  border:1px solid #ffffff15;
}

.heart-target{
  position:absolute;
  width:60px;
  height:60px;
  display:grid;
  place-items:center;
  border:0;
  border-radius:50%;
  background:#f49bc5;
  color:#49162f;
  font-size:29px;
  box-shadow:0 5px 25px #f49bc566;
}

.broken-target{
  background:#555;
  color:#ddd;
}

.card-row{
  display:flex;
  justify-content:center;
  gap:8px;
  flex-wrap:wrap;
}

.playing-card{
  width:58px;
  height:78px;
  background:white;
  color:#29101e;
  border-radius:10px;
  display:grid;
  place-items:center;
  font-size:22px;
  font-weight:900;
}

.memory-box{
  display:flex;
  justify-content:center;
  gap:8px;
  flex-wrap:wrap;
  margin:20px 0;
}

.memory-tile{
  width:58px;
  height:58px;
  border-radius:13px;
  display:grid;
  place-items:center;
  background:#ffffff10;
  border:1px solid #ffffff18;
  font-size:25px;
}

.memory-tile.active{
  background:var(--pink);
  color:#32101f;
}

.maze{
  display:grid;
  grid-template-columns:repeat(5,1fr);
  gap:5px;
  max-width:330px;
  margin:15px auto;
}

.maze-cell{
  aspect-ratio:1;
  border-radius:8px;
  background:#ffffff0b;
  display:grid;
  place-items:center;
  font-size:20px;
}

.maze-cell.wall{
  background:#090509;
}

.maze-cell.player{
  background:var(--pink);
  color:#301020;
}

.maze-cell.goal{
  background:#f5cf7033;
  border:1px solid var(--gold);
}

.wheel{
  width:180px;
  height:180px;
  border-radius:50%;
  margin:15px auto;
  background:conic-gradient(
    #f49bc5 0 25%,
    #f5cf70 25% 50%,
    #8fd9e5 50% 75%,
    #bd6b9a 75% 100%
  );
  border:8px solid #ffffff22;
  display:grid;
  place-items:center;
  font-size:45px;
}

.hidden{
  display:none!important;
}

.result{
  margin-top:12px;
  padding:12px;
  border-radius:14px;
  background:#ffffff08;
}

.final-prize{
  border:2px solid var(--gold);
  background:
    radial-gradient(circle at top,#6e294f,#281321);
  padding:25px 18px;
  border-radius:25px;
}

.trophy{
  font-size:70px;
}

@media(max-width:420px){
  h1{font-size:35px}
  .panel{padding:16px}
  .stats{grid-template-columns:1fr 1fr 1fr}
}
</style>
</head>

<body>

<div id="app"></div>

<script>
/* ==========================================================
   LULU EXPRESS
   20 interactive events
   Secret skip code: 3333
   Generated background music: Web Audio API
   ========================================================== */

const rounds = [
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

/*
 IMPORTANT:
 Event 3 intentionally uses its own questions.
 The 50 final questions below do not repeat those Event 3 questions.
*/

const pressureQuiz = [
 {
  q:"What is the capital of New Zealand?",
  a:["Wellington","Auckland","Christchurch","Hamilton"],
  c:0
 },
 {
  q:"How many sides does a triangle have?",
  a:["3","4","5","6"],
  c:0
 },
 {
  q:"Which planet is known as the Red Planet?",
  a:["Mars","Venus","Jupiter","Mercury"],
  c:0
 },
 {
  q:"How many minutes are in one hour?",
  a:["60","30","90","100"],
  c:0
 },
 {
  q:"Which ocean is the largest?",
  a:["Pacific","Atlantic","Indian","Arctic"],
  c:0
 },
 {
  q:"What is 9 × 9?",
  a:["81","72","99","90"],
  c:0
 },
 {
  q:"Which colour is made by mixing blue and yellow?",
  a:["Green","Purple","Orange","Pink"],
  c:0
 },
 {
  q:"How many days are in a leap year?",
  a:["366","365","364","367"],
  c:0
 }
];

/* 50 FINAL QUESTIONS.
   These are separate from the Event 3 questions above. */

const finalQuiz = [
 ["When is Liliana's birthday?",["July 22","July 12","June 22","August 2"],0],
 ["What is Liliana's favourite colour?",["Baby pink","Burgundy","Lavender","Red"],0],
 ["What is Liliana's favourite number?",["3","6","7","22"],0],
 ["What food does Liliana love?",["Sushi","Pizza","Pasta","Burgers"],0],
 ["Which animal is associated with Liliana's favourites?",["Dolphins","Penguins","Otters","Cats"],0],
 ["Name one of Liliana's favourite flowers.",["Sunflowers","Tulips","Orchids","Daisies"],0],
 ["What other flower does Liliana like?",["Roses","Lilies","Peonies","Lavender"],0],
 ["What is Liliana's favourite movie?",["Me Before You","The Notebook","Titanic","Mamma Mia"],0],
 ["What type of songs does Liliana like?",["Sad songs","Only country songs","Only metal","Only classical"],0],
 ["What does Liliana like besides music?",["Poetry","Cooking manuals","Science journals","Sports statistics"],0],
 ["What type of games does Liliana enjoy?",["Poker and gambling","Chess only","Football games","Crosswords"],0],
 ["How is Liliana often described?",["Sweet and caring","Cold and distant","Strict and serious","Very quiet"],0],
 ["Which word describes Liliana's personality?",["Charismatic","Unfriendly","Reserved","Impatient"],0],
 ["How has Liliana been described romantically?",["Flirtatious","Formal","Uninterested","Shy"],0],
 ["How long have Bree and Liliana been best friends?",["6 years","3 years","4 years","8 years"],0],
 ["What is Liliana's heritage?",["Mexican American","Canadian American","Australian American","British American"],0],
 ["How many tattoos does Liliana have?",["1","2","3","4"],0],
 ["What symbol is connected to Liliana's tattoo?",["A semicolon","A star","A heart","A dolphin"],0],
 ["What colour are Liliana's eyes?",["Green","Blue","Brown","Hazel"],0],
 ["How many piercings does Liliana have?",["4","2","3","5"],0],
 ["What is one of Liliana's dogs called?",["Aayla","Lola","Rene","Kai"],0],
 ["What is Liliana's other dog's name?",["Arlo","Mikael","Yuna","Bree"],0],
 ["How many siblings does Liliana have?",["5","3","4","6"],0],
 ["What is Liliana's star sign?",["Leo","Cancer","Virgo","Libra"],0],
 ["What is Liliana afraid of?",["Drowning","Flying","Thunder","Heights"],0],
 ["What did Liliana study at university?",["Psychology","Law","Nursing","Business"],0],
 ["What does Liliana want to be one day?",["A mum to a baby girl","A professional athlete","A pilot","A chef"],0],
 ["What does Liliana value strongly?",["Empathy","Dishonesty","Coldness","Indifference"],0],
 ["Which flower combination is associated with Liliana?",["Sunflowers and roses","Lilies and tulips","Daisies and orchids","Roses and lavender"],0],
 ["Which number is Liliana's favourite?",["3","13","30","33"],0],
 ["Which of these is one of Liliana's interests?",["Poetry","Only fishing","Only gardening","Only coding"],0],
 ["Which of these best describes Liliana?",["Empathetic","Uncaring","Unfriendly","Aloof"],0],
 ["Which food would be the safest bet when choosing Liliana's favourite?",["Sushi","Steak","Cereal","Toast"],0],
 ["Which animal would make the most sense for a Liliana-themed decoration?",["Dolphin","Tiger","Wolf","Eagle"],0],
 ["Which colour would fit Liliana's favourite palette?",["Baby pink","Neon green","Dark orange","Electric blue"],0],
 ["Which movie title belongs to Liliana's favourites?",["Me Before You","Frozen","Shrek","Avatar"],0],
 ["Which activity fits Liliana's gambling interest?",["Poker","Golf","Swimming","Baking"],0],
 ["Which flower would Liliana recognise as one of her favourites?",["Rose","Cactus","Fern","Bamboo"],0],
 ["What is Liliana's birthday month?",["July","June","August","May"],0],
 ["What is the day of Liliana's birthday?",["22nd","12th","20th","27th"],0],
 ["Which eye colour belongs to Liliana?",["Green","Grey","Hazel","Blue"],0],
 ["Which university subject belongs to Liliana?",["Psychology","Physics","Engineering","Accounting"],0],
 ["Which fear belongs to Liliana?",["Drowning","Dark rooms","Thunder","Needles"],0],
 ["Which of these is one of Liliana's dogs?",["Aayla","Arlo","Lola","Mikael"],0],
 ["Which of these is her other dog?",["Arlo","Aayla","Yuna","Kai"],0],
 ["How many siblings are in Liliana's known family facts?",["5","2","7","8"],0],
 ["Which tattoo count is correct?",["1","0","2","4"],0],
 ["Which piercing count is correct?",["4","1","5","6"],0],
 ["Which future family wish has Liliana shared?",["To be a mum to a baby girl","To have no children","To adopt ten dogs","To become a nun"],0],
 ["What kind of writing does Liliana enjoy?",["Poetry","Only biographies","Only textbooks","Only newspapers"],0]
];

/* ---------- STATE ---------- */

let state = {
 name:"",
 round:0,
 score:0,
 music:true,
 finished:false
};

function loadState(){
 try{
   const saved=JSON.parse(localStorage.getItem("luluExpressState"));
   if(saved) state={...state,...saved};
 }catch(e){}
}

function saveState(){
 try{
   localStorage.setItem("luluExpressState",JSON.stringify(state));
 }catch(e){}
}

loadState();

/* ---------- MUSIC ---------- */

let audioCtx=null;
let master=null;
let musicTimer=null;
let musicStarted=false;

function startMusic(){
 if(!state.music)return;

 if(!audioCtx){
   audioCtx=new(window.AudioContext||window.webkitAudioContext)();
   master=audioCtx.createGain();
   master.gain.value=.055;
   master.connect(audioCtx.destination);
 }

 if(audioCtx.state==="suspended") audioCtx.resume();

 if(musicStarted)return;
 musicStarted=true;

 const notes=[
   261.63,329.63,392.00,523.25,
   293.66,349.23,440.00,587.33,
   261.63,329.63,392.00,493.88
 ];

 let i=0;

 function note(){
   if(!audioCtx)return;

   const osc=audioCtx.createOscillator();
   const gain=audioCtx.createGain();

   osc.type="sine";
   osc.frequency.value=notes[i%notes.length];

   gain.gain.setValueAtTime(0,audioCtx.currentTime);
   gain.gain.linearRampToValueAtTime(.7,audioCtx.currentTime+.04);
   gain.gain.exponentialRampToValueAtTime(.001,audioCtx.currentTime+.75);

   osc.connect(gain);
   gain.connect(master);

   osc.start();
   osc.stop(audioCtx.currentTime+.8);

   i++;
 }

 note();
 musicTimer=setInterval(note,650);
}

function toggleMusic(){
 state.music=!state.music;
 saveState();

 if(state.music){
   startMusic();
 }else if(master){
   master.gain.value=0;
 }
}

/* ---------- HELPERS ---------- */

const app=document.getElementById("app");

function escapeHTML(str){
 return String(str)
   .replaceAll("&","&amp;")
   .replaceAll("<","&lt;")
   .replaceAll(">","&gt;")
   .replaceAll('"',"&quot;")
   .replaceAll("'","&#039;");
}

function renderTop(){
 return `
 <div class="topbar">
   <div class="logo">🚂 <span>Lulu Express</span></div>
   <button class="icon-btn" onclick="toggleMusic()">
     ${state.music ? "🔊 Music" : "🔇 Music"}
   </button>
 </div>
 `;
}

function renderStats(){
 return `
 <div class="stats">
   <div class="stat"><b>${state.score}</b><small>Heart Points</small></div>
   <div class="stat"><b>${state.round+1}</b><small>Round</small></div>
   <div class="stat"><b>${rounds.length}</b><small>Total</small></div>
 </div>
 `;
}

function renderRounds(){
 return `
 <div class="round-list">
 ${rounds.map((r,i)=>{
   let cls=i<state.round?"":"locked";
   if(i===state.round)cls="current";
   return `
    <div class="round ${cls}">
      <div class="round-num">${i<state.round?"✓":i+1}</div>
      <div>
        <strong>${r}</strong><br>
        <span class="small">
          ${i<state.round?"Completed":i===state.round?"Current challenge":"🔒 Locked"}
        </span>
      </div>
    </div>
   `;
 }).join("")}
 </div>
 `;
}

function addScore(points){
 state.score=Math.max(0,state.score+points);
 saveState();
}

function completeRound(points=0){
 addScore(points);

 if(state.round<19){
   state.round++;
   saveState();
   renderRound();
 }else{
   state.finished=true;
   saveState();
   renderFinalResult();
 }
}

function lockedMessage(){
 app.innerHTML=renderTop()+`
 <div class="panel center">
   <div class="badge">🔒 Locked</div>
   <h2>This carriage is locked.</h2>
   <p>You need to complete the previous Lulu Express challenge first.</p>
   <button class="btn" onclick="renderRound()">Return to your carriage</button>
   <button class="btn alt" onclick="showSkip()">🔐 Access Code</button>
 </div>`;
}

function showSkip(){
 app.innerHTML=renderTop()+`
 <div class="panel center">
   <div class="badge">🔐 Secret Access</div>
   <h2>Express Override</h2>
   <p>Enter the four-digit conductor code.</p>
   <input id="skipCode" inputmode="numeric" maxlength="4" placeholder="••••">
   <button class="btn gold" onclick="checkSkip()">Unlock</button>
   <button class="btn alt" onclick="renderRound()">Cancel</button>
 </div>`;
}

function checkSkip(){
 const code=document.getElementById("skipCode").value.trim();

 if(code==="3333"){
   state.round=19;
   saveState();
   renderRound();
 }else{
   alert("Incorrect code.");
 }
}

/* ---------- HOME ---------- */

function home(){
 app.innerHTML=renderTop()+`
 <div class="panel center">
   <div class="badge">🚂 All aboard</div>
   <h1>Lulu Express<br>💗</h1>
   <p>
     One train. Twenty challenges.<br>
     One heart at the final destination.
   </p>

   ${state.name ? `
   <div class="notice">
     Welcome back, <strong>${escapeHTML(state.name)}</strong>.<br>
     You are currently on Round ${state.round+1}.
   </div>` : `
   <input id="playerName" maxlength="30" placeholder="Enter your name, Admirer">
   `}

   <button class="btn gold" onclick="boardTrain()">
     🚂 ${state.name?"Continue Journey":"Board the Lulu Express"}
   </button>

   <div class="notice small">
     🔑 Secret skip code: only someone who knows <strong>3333</strong>
     can unlock the final carriage for testing.
   </div>

   ${state.name ? renderStats()+renderRounds() : ""}
 </div>
 `;
}

function boardTrain(){
 startMusic();

 if(!state.name){
   const input=document.getElementById("playerName");
   const name=input.value.trim();

   if(!name){
     input.focus();
     return;
   }

   state.name=name;
   saveState();
 }

 renderRound();
}

/* ---------- ROUND ROUTER ---------- */

function renderRound(){
 if(state.finished){
   renderFinalResult();
   return;
 }

 switch(state.round){
   case 0:return event1();
   case 1:return event2();
   case 2:return event3();
   case 3:return event4();
   case 4:return event5();
   case 5:return event6();
   case 6:return event7();
   case 7:return event8();
   case 8:return event9();
   case 9:return event10();
   case 10:return event11();
   case 11:return event12();
   case 12:return event13();
   case 13:return event14();
   case 14:return event15();
   case 15:return event16();
   case 16:return event17();
   case 17:return event18();
   case 18:return event19();
   case 19:return event20();
   default:return home();
 }
}

/* ---------- EVENT 1 ---------- */

function event1(){
 let hits=0;
 let misses=0;
 let time=20;
 let timer;

 app.innerHTML=renderTop()+`
 <div class="panel">
   <div class="badge">Event 1 of 20</div>
   <h2>❤️ The Heart Rate</h2>
   <p>Tap the pink hearts. Avoid the broken hearts.</p>
   <div class="stats">
    <div class="stat"><b id="heartHits">0</b><small>Hearts</small></div>
    <div class="stat"><b id="heartMiss">0</b><small>Broken</small></div>
    <div class="stat"><b id="heartTime">20</b><small>Seconds</small></div>
   </div>
   <div id="heartArena" class="arena"></div>
 </div>`;

 const arena=document.getElementById("heartArena");

 function spawn(){
   if(time<=0)return;

   const el=document.createElement("button");
   const good=Math.random()>.22;

   el.className="heart-target"+(good?"":" broken-target");
   el.textContent=good?"❤️":"💔";

   el.style.left=(Math.random()*82+5)+"%";
   el.style.top=(Math.random()*78+5)+"%";

   el.onclick=()=>{
     if(good){
       hits++;
       addScore(5);
     }else{
       misses++;
       addScore(-5);
     }

     document.getElementById("heartHits").textContent=hits;
     document.getElementById("heartMiss").textContent=misses;
     el.remove();
   };

   arena.appendChild(el);

   setTimeout(()=>{
     if(el.parentNode)el.remove();
   },900);
 }

 const spawner=setInterval(spawn,450);

 timer=setInterval(()=>{
   time--;
   document.getElementById("heartTime").textContent=time;

   if(time<=0){
     clearInterval(timer);
     clearInterval(spawner);

     setTimeout(()=>{
       completeRound(hits*2);
     },500);
   }
 },1000);

 spawn();
}

/* ---------- EVENT 2 ---------- */

function event2(){
 let sequence=[];
 let player=[];
 let level=3;
 let showing=false;

 app.innerHTML=renderTop()+`
 <div class="panel center">
  <div class="badge">Event 2 of 20</div>
  <h2>🧠 The Memory Vault</h2>
  <p>Watch the sequence. Then reproduce it.</p>
  <div class="notice">Level <strong id="memoryLevel">3</strong></div>
  <div id="memoryBox" class="memory-box"></div>
  <button id="memoryStart" class="btn gold" onclick="startMemory()">Show Sequence</button>
 </div>`;

 window.startMemory=function(){
   if(showing)return;

   showing=true;
   player=[];
   sequence=[];

   const symbols=["💗","🌹","🦋","⭐","🎲","🐬","☀️","🌙"];
   for(let i=0;i<level;i++){
     sequence.push(symbols[Math.floor(Math.random()*symbols.length)]);
   }

   drawMemory(sequence,false);

   let i=0;
   const interval=setInterval(()=>{
     const tiles=document.querySelectorAll(".memory-tile");

     tiles.forEach(x=>x.classList.remove("active"));

     if(i<sequence.length){
       tiles[i].classList.add("active");
       i++;
     }else{
       clearInterval(interval);
       drawMemory(sequence,true);
       showing=false;
     }
   },600);
 };

 function drawMemory(seq,clickable){
   const box=document.getElementById("memoryBox");
   box.innerHTML="";

   seq.forEach((symbol,index)=>{
     const tile=document.createElement("button");
     tile.className="memory-tile";
     tile.textContent=clickable?"?":symbol;

     if(clickable){
       tile.onclick=()=>{
         const wanted=sequence[player.length];

         if(symbol===wanted){
           tile.textContent=symbol;
           tile.classList.add("active");
           player.push(symbol);

           if(player.length===sequence.length){
             addScore(level*10);

             if(level>=6){
               setTimeout(()=>completeRound(30),500);
             }else{
               level++;
               document.getElementById("memoryLevel").textContent=level;
               setTimeout(()=>{
                 player=[];
                 startMemory();
               },700);
             }
           }
         }else{
           alert("The sequence broke! You lose this attempt.");
           player=[];
           startMemory();
         }
       };
     }

     box.appendChild(tile);
   });
 }
}

/* ---------- EVENT 3 ---------- */

function event3(){
 let index=0;
 let points=0;
 let time=5;
 let timer;

 function show(){
   clearInterval(timer);
   time=5;

   if(index>=pressureQuiz.length){
     completeRound(points+20);
     return;
   }

   const q=pressureQuiz[index];

   app.innerHTML=renderTop()+`
   <div class="panel">
    <div class="badge">Event 3 of 20</div>
    <h2>⚡ The Pressure Quiz</h2>
    <div class="timer" id="pressureTime">5</div>
    <p><strong>Question ${index+1} of ${pressureQuiz.length}</strong></p>
    <h3>${q.q}</h3>
    <div class="choices">
      ${q.a.map((a,i)=>`
       <button class="choice" onclick="answerPressure(${i})">${a}</button>
      `).join("")}
    </div>
   </div>`;

   timer=setInterval(()=>{
     time--;
     const el=document.getElementById("pressureTime");
     if(el)el.textContent=time;

     if(time<=0){
       clearInterval(timer);
       index++;
       setTimeout(show,250);
     }
   },1000);
 }

 window.answerPressure=function(choice){
   clearInterval(timer);

   if(choice===pressureQuiz[index].c){
     points+=15;
     addScore(15);
   }

   index++;
   setTimeout(show,300);
 };

 show();
}

/* ---------- EVENT 4 ---------- */

function event4(){
 let tokens=100;
 let roundsPlayed=0;

 app.innerHTML=renderTop()+`
 <div class="panel center">
  <div class="badge">Event 4 of 20</div>
  <h2>🎰 The High Roller</h2>
  <p>Risk your Love Tokens for bigger rewards.</p>
  <div class="big" id="tokens">100</div>
  <div class="grid">
   <button class="btn" onclick="bet(10)">Safe<br>10</button>
   <button class="btn gold" onclick="bet(25)">Risky<br>25</button>
  </div>
  <button class="btn red" onclick="bet(50)">ALL IN<br>50</button>
  <div id="gambleResult" class="result">Choose your bet.</div>
 </div>`;

 window.bet=function(amount){
   roundsPlayed++;

   const win=Math.random()>.42;

   if(win){
     tokens+=amount*2;
     document.getElementById("gambleResult").textContent="💗 WIN! The Express smiles upon you.";
   }else{
     tokens-=amount;
     document.getElementById("gambleResult").textContent="💔 LOSS! Your carriage shook.";
   }

   tokens=Math.max(0,tokens);
   document.getElementById("tokens").textContent=tokens;

   if(roundsPlayed>=5){
     completeRound(Math.floor(tokens/5));
   }
 };
}

/* ---------- EVENT 5 ---------- */

function event5(){
 const scenarios=[
  ["Liliana has had a terrible day. What do you do?","Listen without trying to take over.","Tell her to get over it.","Change the subject immediately.","Ignore her."],
  ["You have one free evening together. What sounds best?","Let her choose what feels fun.","Make every decision yourself.","Cancel at the last second.","Turn it into an argument."],
  ["Liliana tells you something personal. What matters most?","Respecting her trust.","Telling everyone.","Laughing about it.","Changing the topic."],
  ["A disagreement happens. What is the strongest move?","Communicate honestly.","Refuse to speak.","Make it a competition.","Pretend it never happened."]
 ];

 let i=0;
 let score=0;

 function show(){
  if(i>=scenarios.length){
    completeRound(score+20);
    return;
  }

  const s=scenarios[i];

  app.innerHTML=renderTop()+`
   <div class="panel">
    <div class="badge">Event 5 of 20</div>
    <h2>🧠 The Mind Games</h2>
    <p>Choose the response that shows the strongest compatibility.</p>
    <h3>${s[0]}</h3>
    <div class="choices">
      ${s.slice(1).map((x,n)=>`
       <button class="choice" onclick="mindAnswer(${n})">${x}</button>
      `).join("")}
    </div>
   </div>`;
 }

 window.mindAnswer=function(n){
   if(n===0){
     score+=15;
     addScore(15);
   }else{
     score+=3;
     addScore(3);
   }

   i++;
   show();
 };

 show();
}

/* ---------- EVENT 6 ---------- */

function event6(){
 let chips=100;
 let hand=[];
 const suits=["♥","♦","♣","♠"];
 const ranks=["A","K","Q","J","10","9"];

 function draw(){
   hand=[
     ranks[Math.floor(Math.random()*ranks.length)]+suits[Math.floor(Math.random()*4)],
     ranks[Math.floor(Math.random()*ranks.length)]+suits[Math.floor(Math.random()*4)],
     ranks[Math.floor(Math.random()*ranks.length)]+suits[Math.floor(Math.random()*4)]
   ];

   app.innerHTML=renderTop()+`
    <div class="panel center">
     <div class="badge">Event 6 of 20</div>
     <h2>🃏 The Bluff</h2>
     <p>Read your hand. Bet, fold or bluff your way through three rounds.</p>
     <div class="big">${chips}</div>
     <div class="card-row">
      ${hand.map(c=>`<div class="playing-card">${c}</div>`).join("")}
     </div>
     <button class="btn gold" onclick="pokerAction('bet')">BET 25</button>
     <button class="btn" onclick="pokerAction('bluff')">BLUFF 40</button>
     <button class="btn alt" onclick="pokerAction('fold')">FOLD</button>
     <div id="pokerResult" class="result">Make your move.</div>
    </div>`;
 }

 let n=0;

 window.pokerAction=function(action){
   n++;

   let win=false;

   if(action==="fold"){
     chips=Math.max(0,chips-5);
   }else{
     win=Math.random()>.42;

     if(win){
       chips+=action==="bluff"?40:25;
       addScore(action==="bluff"?20:12);
     }else{
       chips=Math.max(0,chips-(action==="bluff"?40:25));
     }
   }

   document.getElementById("pokerResult").textContent=
     action==="fold"?"You folded and lived to bluff another day.":
     win?"🎉 The bluff worked!":"💔 Your opponent called it.";

   if(n>=3){
     setTimeout(()=>completeRound(Math.floor(chips/4)),600);
   }
 };

 draw();
}

/* ---------- EVENT 7 ---------- */

function event7(){
 let level=3;
 let sequence=[];
 let player=[];
 let locked=false;

 const symbols=["❤️","🌹","⭐","🐬","🎲","🌙","☀️","🦋"];

 function begin(){
   if(locked)return;

   locked=true;
   sequence=[];

   for(let i=0;i<level;i++){
     sequence.push(symbols[Math.floor(Math.random()*symbols.length)]);
   }

   app.innerHTML=renderTop()+`
   <div class="panel center">
    <div class="badge">Event 7 of 20</div>
    <h2>⚡ The Survival Round</h2>
    <p>Memorise the sequence. One mistake and the round ends.</p>
    <div class="notice">Level ${level}</div>
    <div class="memory-box" id="survivalBox"></div>
   </div>`;

   const box=document.getElementById("survivalBox");

   sequence.forEach((x,i)=>{
     const t=document.createElement("div");
     t.className="memory-tile";
     t.textContent=x;
     box.appendChild(t);
   });

   let i=0;

   const timer=setInterval(()=>{
     const tiles=box.children;
     [...tiles].forEach(t=>t.classList.remove("active"));

     if(i<sequence.length){
       tiles[i].classList.add("active");
       i++;
     }else{
       clearInterval(timer);
       createInput();
     }
   },500);
 }

 function createInput(){
   const box=document.getElementById("survivalBox");
   box.innerHTML="";

   sequence.forEach((_,i)=>{
     const t=document.createElement("button");
     t.className="memory-tile";
     t.textContent="?";

     t.onclick=()=>{
       const choices=[...symbols];
       const answer=choices[Math.floor(Math.random()*choices.length)];

       /* A safer accessible version: tapping cycles through symbols. */
       let current=0;

       function cycle(){
         t.textContent=choices[current%choices.length];
         current++;

         if(current>=choices.length){
           t.onclick=null;
           const correct=t.textContent===sequence[i];

           if(!correct){
             alert("💔 Survival failed!");
             completeRound(10);
           }else{
             player[i]=t.textContent;

             if(player.filter(Boolean).length===sequence.length){
               level++;

               if(level>5){
                 completeRound(35);
               }else{
                 locked=false;
                 begin();
               }
             }
           }
         }
       }

       cycle();
     };

     box.appendChild(t);
   });
 }

 /* Replace the cycle challenge with direct symbol selection beneath it. */
 function directBegin(){
   locked=true;
   sequence=[];

   for(let i=0;i<level;i++){
     sequence.push(symbols[Math.floor(Math.random()*symbols.length)]);
   }

   app.innerHTML=renderTop()+`
   <div class="panel center">
    <div class="badge">Event 7 of 20</div>
    <h2>⚡ The Survival Round</h2>
    <p>Memorise the symbols. Then reproduce them in order.</p>
    <div class="notice">Level ${level}</div>
    <div id="showSequence" class="memory-box"></div>
   </div>`;

   const show=document.getElementById("showSequence");

   sequence.forEach(x=>{
     const t=document.createElement("div");
     t.className="memory-tile";
     t.textContent=x;
     show.appendChild(t);
   });

   setTimeout(()=>{
     app.querySelector(".panel").innerHTML+=`
      <div class="notice">Now enter the sequence:</div>
      <div id="survivalChoices" class="grid">
       ${symbols.map((x,i)=>`<button class="choice" onclick="survivalPick('${x.replaceAll("'","")}')">${x}</button>`).join("")}
      </div>
      <div id="survivalProgress" class="result">0 / ${sequence.length}</div>`;
     player=[];
   },1500);
 }

 window.survivalPick=function(symbol){
   const expected=sequence[player.length];

   if(symbol!==expected){
     alert("💔 Wrong symbol. Survival failed.");
     completeRound(8);
     return;
   }

   player.push(symbol);
   document.getElementById("survivalProgress").textContent=
     `${player.length} / ${sequence.length}`;

   if(player.length===sequence.length){
     addScore(level*10);
     level++;

     if(level>5){
       completeRound(35);
     }else{
       setTimeout(directBegin,600);
     }
   }
 };

 directBegin();
}

/* ---------- EVENT 8 ---------- */

function event8(){
 let player=0;
 let rival=0;
 let q=0;

 const actions=["❤️","🌹","⭐","🐬"];

 function next(){
   if(q>=8){
     const bonus=player>=rival?50:15;
     completeRound(bonus);
     return;
   }

   const target=actions[Math.floor(Math.random()*actions.length)];

   app.innerHTML=renderTop()+`
   <div class="panel center">
    <div class="badge">Event 8 of 20</div>
    <h2>🏎️ The Admirer Race</h2>
    <p>Tap the matching symbol before your rival moves.</p>

    <div class="stats">
      <div class="stat"><b>${player}</b><small>You</small></div>
      <div class="stat"><b>${rival}</b><small>Rival</small></div>
      <div class="stat"><b>${q+1}/8</b><small>Lap</small></div>
    </div>

    <div class="notice big">${target}</div>

    <div class="grid">
      ${actions.map(x=>`
       <button class="choice" onclick="racePick('${x}')">${x}</button>
      `).join("")}
    </div>
   </div>`;
 }

 window.racePick=function(x){
   if(x===document.querySelector(".notice.big").textContent){
     player++;
     addScore(8);
   }else{
     rival++;
   }

   if(Math.random()>.45)rival++;

   q++;
   next();
 };

 next();
}

/* ---------- EVENT 9 ---------- */

function event9(){
 let doors=0;
 let score=0;

 function show(){
   app.innerHTML=renderTop()+`
   <div class="panel center">
    <div class="badge">Event 9 of 20</div>
    <h2>💔 The Heartbreak Chamber</h2>
    <p>Choose a door. Every door carries a different consequence.</p>
    <div class="big">${score}</div>
    <div class="grid">
     <button class="btn" onclick="door(1)">🚪 Door 1</button>
     <button class="btn gold" onclick="door(2)">🚪 Door 2</button>
     <button class="btn" onclick="door(3)">🚪 Door 3</button>
     <button class="btn red" onclick="door(4)">🚪 Door 4</button>
    </div>
    <div id="doorResult" class="result">Door ${doors+1} of 5</div>
   </div>`;
 }

 window.door=function(n){
   doors++;

   const outcomes=[
     {text:"💗 A heart was waiting inside. +30",points:30},
     {text:"🌹 Roses! +15",points:15},
     {text:"💔 Heartbreak! -10",points:-10},
     {text:"🎰 JACKPOT! +50",points:50}
   ];

   const result=outcomes[Math.floor(Math.random()*outcomes.length)];
   score+=result.points;
   addScore(result.points);

   if(doors>=5){
     completeRound(Math.max(0,score)+15);
   }else{
     show();
   }
 };

 show();
}

/* ---------- EVENT 10 ---------- */

function event10(){
 let enemy=100;
 let you=100;
 let turn=0;

 function show(){
   app.innerHTML=renderTop()+`
   <div class="panel center">
    <div class="badge">Event 10 of 20</div>
    <h2>🥊 The Heartbreak Boxing Match</h2>
    <p>Attack, block, or take a risky heavy punch.</p>

    <div class="stats">
      <div class="stat"><b>${you}</b><small>Your HP</small></div>
      <div class="stat"><b>${enemy}</b><small>Opponent HP</small></div>
      <div class="stat"><b>${turn}</b><small>Turns</small></div>
    </div>

    <button class="btn" onclick="fight('punch')">🥊 Punch</button>
    <button class="btn gold" onclick="fight('heavy')">💥 Heavy Punch</button>
    <button class="btn alt" onclick="fight('block')">🛡️ Block</button>
    <div id="fightResult" class="result">Choose your move.</div>
   </div>`;
 }

 window.fight=function(move){
   turn++;

   let damage=0;

   if(move==="punch")damage=Math.floor(Math.random()*15)+8;
   if(move==="heavy")damage=Math.floor(Math.random()*28)+5;
   if(move==="block")damage=0;

   enemy=Math.max(0,enemy-damage);

   if(enemy>0){
     let hit=Math.floor(Math.random()*16)+5;

     if(move==="block")hit=Math.floor(hit/4);

     you=Math.max(0,you-hit);
   }

   addScore(damage);

   if(enemy<=0){
     completeRound(50);
   }else if(you<=0){
     completeRound(10);
   }else{
     show();
   }
 };

 show();
}

/* ---------- EVENT 11 ---------- */

function event11(){
 let pattern=[];
 let clicks=0;

 function start(){
   pattern=[];
   clicks=0;

   for(let i=0;i<9;i++){
     pattern.push(Math.random()>.5);
   }

   app.innerHTML=renderTop()+`
   <div class="panel center">
    <div class="badge">Event 11 of 20</div>
    <h2>🧩 The Perfect Match</h2>
    <p>Memorise the glowing pattern, then recreate it.</p>
    <div id="patternGrid" class="grid"></div>
   </div>`;

   const grid=document.getElementById("patternGrid");

   pattern.forEach(active=>{
     const b=document.createElement("button");
     b.className="choice";
     b.style.height="70px";

     if(active){
       b.style.background="#f49bc555";
     }

     grid.appendChild(b);
   });

   setTimeout(()=>{
     [...grid.children].forEach((b,i)=>{
       b.style.background="";
       b.onclick=()=>{
         if(pattern[i]){
           b.classList.add("correct");
           clicks++;

           if(clicks===pattern.filter(Boolean).length){
             completeRound(45);
           }
         }else{
           b.classList.add("wrong");
           completeRound(5);
         }
       };
     });
   },1500);
 }

 start();
}

/* ---------- EVENT 12 ---------- */

function event12(){
 const facts=[
  ["Liliana has green eyes.","TRUE"],
  ["Liliana has seven siblings.","FALSE"],
  ["Liliana studied Psychology.","TRUE"],
  ["Liliana's birthday is July 22.","TRUE"],
  ["Liliana has two tattoos.","FALSE"],
  ["Liliana is afraid of drowning.","TRUE"],
  ["Liliana has four piercings.","TRUE"],
  ["Liliana's favourite number is 9.","FALSE"]
 ];

 let i=0;

 function show(){
   if(i>=facts.length){
     completeRound(40);
     return;
   }

   app.innerHTML=renderTop()+`
   <div class="panel center">
    <div class="badge">Event 12 of 20</div>
    <h2>🕵️ Who Knows Liliana Best?</h2>
    <p>Truth or lie?</p>
    <h3>${facts[i][0]}</h3>
    <div class="grid">
      <button class="btn gold" onclick="truth(true)">TRUE</button>
      <button class="btn" onclick="truth(false)">FALSE</button>
    </div>
   </div>`;
 }

 window.truth=function(answer){
   const correct=(facts[i][1]==="TRUE");

   if(answer===correct)addScore(10);

   i++;
   show();
 };

 show();
}

/* ---------- EVENT 13 ---------- */

function event13(){
 const commands=["TAP","TAP","HOLD","SWIPE","DOUBLE TAP"];
 let i=0;
 let score=0;
 let timeout;

 function next(){
   if(i>=12){
     completeRound(score+20);
     return;
   }

   const command=commands[Math.floor(Math.random()*commands.length)];

   app.innerHTML=renderTop()+`
   <div class="panel center">
    <div class="badge">Event 13 of 20</div>
    <h2>💨 The Reaction Gauntlet</h2>
    <p>Perform the command shown.</p>
    <div class="big">${command}</div>
    <button id="reactionButton" class="btn gold">DO IT!</button>
    <div class="small">${i+1}/12</div>
   </div>`;

   const button=document.getElementById("reactionButton");

   if(command==="TAP"){
     button.onclick=success;
   }else if(command==="HOLD"){
     let down=false;
     let start=0;

     button.onpointerdown=()=>{
       down=true;
       start=Date.now();
     };

     button.onpointerup=()=>{
       if(down && Date.now()-start>=500)success();
       else fail();
       down=false;
     };
   }else if(command==="DOUBLE TAP"){
     let taps=0;
     let last=0;

     button.onclick=()=>{
       const now=Date.now();

       if(now-last<500)taps++;
       else taps=1;

       last=now;

       if(taps>=2)success();
     };
   }else{
     button.ontouchstart=success;
     button.onclick=success;
   }

   timeout=setTimeout(fail,1800);

   function success(){
     clearTimeout(timeout);
     score+=10;
     addScore(10);
     i++;
     setTimeout(next,250);
   }

   function fail(){
     clearTimeout(timeout);
     i++;
     setTimeout(next,250);
   }
 }

 next();
}

/* ---------- EVENT 14 ---------- */

function event14(){
 const walls=[1,3,5,7,9,11,13,15,17,19];
 let player=0;
 const goal=24;

 function draw(){
   app.innerHTML=renderTop()+`
   <div class="panel center">
    <div class="badge">Event 14 of 20</div>
    <h2>🗺️ The Heart Hunt</h2>
    <p>Navigate the maze and reach ❤️.</p>
    <div class="maze" id="maze"></div>
    <div class="grid">
      <button class="btn" onclick="move(-5)">⬆️</button>
      <button class="btn" onclick="move(5)">⬇️</button>
      <button class="btn" onclick="move(-1)">⬅️</button>
      <button class="btn" onclick="move(1)">➡️</button>
    </div>
   </div>`;

   const maze=document.getElementById("maze");

   for(let i=0;i<25;i++){
     const c=document.createElement("div");
     c.className="maze-cell";

     if(walls.includes(i))c.classList.add("wall");
     if(i===player)c.classList.add("player");
     if(i===goal){
       c.classList.add("goal");
       c.textContent="❤️";
     }

     maze.appendChild(c);
   }
 }

 window.move=function(amount){
   const next=player+amount;

   if(next<0||next>24||walls.includes(next))return;

   if(amount===1 && Math.floor(player/5)!==Math.floor(next/5))return;
   if(amount===-1 && Math.floor(player/5)!==Math.floor(next/5))return;

   player=next;
   addScore(2);

   if(player===goal){
     completeRound(40);
   }else{
     draw();
   }
 };

 draw();
}

/* ---------- EVENT 15 ---------- */

function event15(){
 const answer="3333";
 let entered="";

 function draw(){
   app.innerHTML=renderTop()+`
   <div class="panel center">
    <div class="badge">Event 15 of 20</div>
    <h2>🔐 The Love Lock</h2>
    <p>
      Solve the clue:
      <br><br>
      <strong>What number has already been hidden throughout
      the Lulu Express as the secret override?</strong>
    </p>

    <div class="big">${entered||"••••"}</div>

    <div class="grid">
      ${[1,2,3,4,5,6,7,8,9,0].map(n=>
        `<button class="choice" onclick="digit(${n})">${n}</button>`
      ).join("")}
    </div>

    <button class="btn alt" onclick="clearCode()">Clear</button>
   </div>`;
 }

 window.digit=function(n){
   if(entered.length<4)entered+=n;

   if(entered.length===4){
     if(entered===answer){
       completeRound(50);
     }else{
       alert("The lock rejected that code.");
       entered="";
       draw();
     }
   }else{
     draw();
   }
 };

 window.clearCode=function(){
   entered="";
   draw();
 };

 draw();
}

/* ---------- EVENT 16 ---------- */

function event16(){
 let hits=0;
 let misses=0;
 let time=20;

 app.innerHTML=renderTop()+`
 <div class="panel">
  <div class="badge">Event 16 of 20</div>
  <h2>🎯 The Cupid Shootout</h2>
  <p>Hit ❤️. Avoid 💔.</p>
  <div class="stats">
   <div class="stat"><b id="shotHits">0</b><small>Hits</small></div>
   <div class="stat"><b id="shotMisses">0</b><small>Misses</small></div>
   <div class="stat"><b id="shotTime">20</b><small>Seconds</small></div>
  </div>
  <div id="shootArena" class="arena"></div>
 </div>`;

 const arena=document.getElementById("shootArena");

 function spawn(){
   if(time<=0)return;

   const b=document.createElement("button");
   const good=Math.random()>.25;

   b.className="heart-target"+(good?"":" broken-target");
   b.textContent=good?"❤️":"💔";
   b.style.left=(Math.random()*80+5)+"%";
   b.style.top=(Math.random()*75+5)+"%";

   b.onclick=()=>{
     if(good){
       hits++;
       addScore(6);
     }else{
       misses++;
       addScore(-4);
     }

     document.getElementById("shotHits").textContent=hits;
     document.getElementById("shotMisses").textContent=misses;
     b.remove();
   };

   arena.appendChild(b);

   setTimeout(()=>b.remove(),800);
 }

 const spawnTimer=setInterval(spawn,350);

 const timeTimer=setInterval(()=>{
   time--;
   document.getElementById("shotTime").textContent=time;

   if(time<=0){
     clearInterval(spawnTimer);
     clearInterval(timeTimer);
     setTimeout(()=>completeRound(hits*2),300);
   }
 },1000);

 spawn();
}

/* ---------- EVENT 17 ---------- */

function event17(){
 let challenge=0;
 let points=0;
 let timer=60;

 function next(){
   if(challenge>=20){
     completeRound(points+40);
     return;
   }

   const tasks=[
     "Tap the GOLD button.",
     "Tap the PINK button.",
     "Tap ❤️.",
     "Tap ⭐.",
     "Tap 🐬.",
     "Tap 🌹."
   ];

   const task=tasks[Math.floor(Math.random()*tasks.length)];

   app.innerHTML=renderTop()+`
   <div class="panel center">
    <div class="badge">Event 17 of 20</div>
    <h2>🧨 The Countdown</h2>
    <div class="timer">${timer}</div>
    <p>${task}</p>
    <button id="countButton" class="btn gold">GOLD</button>
    <button class="btn" onclick="miniSuccess('PINK')">PINK</button>
    <button class="btn alt" onclick="miniSuccess('❤️')">❤️</button>
    <button class="btn alt" onclick="miniSuccess('⭐')">⭐</button>
    <button class="btn alt" onclick="miniSuccess('🐬')">🐬</button>
    <button class="btn alt" onclick="miniSuccess('🌹')">🌹</button>
    <div class="small">${challenge}/20 completed</div>
   </div>`;

   document.getElementById("countButton").onclick=()=>miniSuccess("GOLD");
 }

 window.miniSuccess=function(value){
   challenge++;
   points+=Math.max(1, timer>0?5:1);
   addScore(5);
   next();
 };

 const countdown=setInterval(()=>{
   timer--;

   const el=document.querySelector(".timer");
   if(el)el.textContent=timer;

   if(timer<=0){
     clearInterval(countdown);
     if(challenge<20)completeRound(points+10);
   }
 },1000);

 next();
}

/* ---------- EVENT 18 ---------- */

function event18(){
 let points=100;
 let turns=0;

 app.innerHTML=renderTop()+`
 <div class="panel center">
  <div class="badge">Event 18 of 20</div>
  <h2>🎰 The Ultimate Gamble</h2>
  <p>Your accumulated Heart Points are on the table.</p>
  <div class="big" id="gamblePoints">${points}</div>
  <button class="btn" onclick="ultimate('safe')">SAFE — Keep 75%</button>
  <button class="btn gold" onclick="ultimate('risk')">RISK — Double or Lose Half</button>
  <button class="btn red" onclick="ultimate('all')">ALL IN — Triple or Zero</button>
  <div id="ultimateResult" class="result">Choose wisely.</div>
 </div>`;

 window.ultimate=function(type){
   turns++;

   const win=Math.random()>.5;

   if(type==="safe"){
     points=Math.floor(points*.75);
   }else if(type==="risk"){
     points=win?points*2:Math.floor(points*.5);
   }else{
     points=win?points*3:0;
   }

   document.getElementById("gamblePoints").textContent=points;
   document.getElementById("ultimateResult").textContent=
     win||type==="safe"?"💗 The gamble paid off.":"💔 The Express took your bet.";

   if(turns>=2){
     completeRound(Math.floor(points/2));
   }
 };
}

/* ---------- EVENT 19 ---------- */

function event19(){
 let life=3;
 let round=0;

 function next(){
   if(round>=6){
     completeRound(60);
     return;
   }

   const tasks=[
     "Tap ❤️ before the timer reaches zero.",
     "Choose the only safe door.",
     "Remember the number 3.",
     "Tap the pink train carriage.",
     "Choose the dolphin.",
     "Select the rose."
   ];

   const task=tasks[round];

   app.innerHTML=renderTop()+`
   <div class="panel center">
    <div class="badge">Event 19 of 20</div>
    <h2>💀 The Admirer's Last Stand</h2>
    <div class="stats">
      <div class="stat"><b>${life}</b><small>Lives</small></div>
      <div class="stat"><b>${round+1}/6</b><small>Trial</small></div>
      <div class="stat"><b>${state.score}</b><small>Points</small></div>
    </div>
    <p>${task}</p>

    <div class="grid">
      <button class="choice" onclick="stand('❤️')">❤️</button>
      <button class="choice" onclick="stand('🌹')">🌹</button>
      <button class="choice" onclick="stand('🐬')">🐬</button>
      <button class="choice" onclick="stand('3')">3</button>
    </div>
   </div>`;
 }

 window.stand=function(value){
   const correct=[
     "❤️","3","3","❤️","🐬","🌹"
   ][round];

   if(value===correct){
     addScore(12);
   }else{
     life--;
   }

   round++;

   if(life<=0){
     completeRound(15);
   }else{
     next();
   }
 };

 next();
}

/* ---------- EVENT 20 ---------- */

let finalIndex=0;
let finalScore=0;

function event20(){
 finalIndex=0;
 finalScore=0;
 showFinalQuestion();
}

function showFinalQuestion(){
 if(finalIndex>=finalQuiz.length){
   showFinalWriting();
   return;
 }

 const item=finalQuiz[finalIndex];

 app.innerHTML=renderTop()+`
 <div class="panel">
  <div class="badge">Event 20 of 20 • FINAL CHALLENGE</div>
  <h2>👑 Know Liliana</h2>
  <div class="progress">
    <div class="progress-fill" style="width:${(finalIndex/finalQuiz.length)*100}%"></div>
  </div>

  <p>
   Question <strong>${finalIndex+1}</strong> of
   <strong>${finalQuiz.length}</strong>
  </p>

  <h3>${item[0]}</h3>

  <div class="choices">
   ${item[1].map((answer,i)=>
     `<button class="choice" onclick="answerFinal(${i})">${answer}</button>`
   ).join("")}
  </div>

  <div class="notice center">
   💗 ${finalScore} / ${finalQuiz.length} correct
  </div>
 </div>`;
}

function answerFinal(choice){
 const q=finalQuiz[finalIndex];

 const buttons=document.querySelectorAll(".choice");

 buttons.forEach(b=>b.disabled=true);

 if(choice===q[2]){
   finalScore++;
   addScore(10);
   buttons[choice].classList.add("correct");
 }else{
   buttons[choice].classList.add("wrong");
   buttons[q[2]].classList.add("correct");
 }

 finalIndex++;

 setTimeout(showFinalQuestion,450);
}

function showFinalWriting(){
 app.innerHTML=renderTop()+`
 <div class="panel center">
  <div class="badge">Final Final Challenge</div>
  <h2>💌 One Last Question</h2>

  <p>
   You've survived nineteen events and answered fifty questions.
   Now there is only one thing left to prove.
  </p>

  <h3>Why should Liliana choose you?</h3>

  <textarea id="finalAnswer"
   placeholder="Make your case to Liliana..."></textarea>

  <button class="btn gold" onclick="submitFinalAnswer()">
   👑 Submit My Answer
  </button>
 </div>`;
}

function submitFinalAnswer(){
 const answer=document.getElementById("finalAnswer").value.trim();

 if(answer.length<10){
   alert("Give Liliana a little more than that. ❤️");
   return;
 }

 addScore(50);
 renderFinalResult();
}

/* ---------- FINAL RESULT ---------- */

function renderFinalResult(){
 state.finished=true;
 saveState();

 let title;
 let message;

 if(state.score>=520){
   title="🏆 LILU EXPRESS CHAMPION";
   message="You didn't just reach the final carriage. You owned the entire journey.";
 }else if(state.score>=400){
   title="🥇 SERIOUS CONTENDER";
   message="You came dangerously close to stealing the show.";
 }else if(state.score>=280){
   title="🥈 STRONG ADMIRER";
   message="You made it all the way to the final destination.";
 }else{
   title="💗 SURVIVOR";
   message="You survived the Lulu Express. That deserves respect.";
 }

 app.innerHTML=renderTop()+`
 <div class="panel center final-prize">
  <div class="trophy">👑</div>
  <div class="badge">Journey Complete</div>

  <h1>${title}</h1>

  <p>
   <strong>${escapeHTML(state.name)}</strong>,
   ${message}
  </p>

  <div class="big">${state.score}</div>
  <p>Final Heart Points</p>

  <hr style="border:0;border-top:1px solid #ffffff18;margin:20px 0">

  <div class="trophy">📞</div>

  <h2>Your Prize</h2>

  <h2 class="gold">A PRIVATE CALL WITH LILIANA</h2>

  <p>
   You made it through every challenge and reached
   the final destination of the Lulu Express.
  </p>

  <div class="notice">
   🚂💗 <strong>The Lulu Express has reached its final destination.</strong>
   <br><br>
   Congratulations, Admirer.
  </div>

  <button class="btn alt" onclick="home()">
   Return to the Lulu Express
  </button>
 </div>`;
}

/* ---------- INITIALISE ---------- */

home();

})();
</script>
</body>
</html>

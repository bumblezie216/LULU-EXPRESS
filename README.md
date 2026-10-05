<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#12070d">
<title>Lulu Express 🚂💗</title>

<style>
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
:root{
  --bg:#12070d;
  --bg2:#1e0c16;
  --panel:#2b1220;
  --panel2:#351729;
  --pink:#ff8fbd;
  --pink2:#ffb8d6;
  --light:#ffe8f2;
  --muted:#cfaabc;
  --burg:#741f43;
  --green:#77e0a0;
  --gold:#ffd66b;
  --red:#ff6f83;
}
html,body{
  margin:0;
  width:100%;
  min-height:100%;
  background:radial-gradient(circle at top,#321426 0,#12070d 60%);
  color:var(--light);
  font-family:Arial,Helvetica,sans-serif;
}
body{overflow-x:hidden}
button,input{font:inherit}
button{
  border:0;
  cursor:pointer;
  color:white;
}
.hidden{display:none!important}

#app{min-height:100vh}

/* GLOBAL JOURNEY HEADER */
#journeyHeader{
  position:sticky;
  top:0;
  z-index:50;
  background:rgba(18,7,13,.94);
  backdrop-filter:blur(12px);
  border-bottom:1px solid rgba(255,143,189,.18);
  padding:10px 14px;
}
.headerInner{
  max-width:900px;
  margin:auto;
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:8px;
}
.logo{
  font-weight:900;
  font-size:17px;
  white-space:nowrap;
}
.stats{
  display:flex;
  gap:7px;
  flex-wrap:wrap;
  justify-content:center;
}
.stat{
  background:#29111e;
  border:1px solid #54263d;
  border-radius:999px;
  padding:6px 10px;
  font-size:12px;
}
.headerButtons{
  display:flex;
  gap:5px;
}
.smallBtn{
  background:#4b1c32;
  border:1px solid #71304d;
  padding:7px 9px;
  border-radius:10px;
  font-size:12px;
}
.smallBtn:hover{background:#682543}

#musicPanel{
  position:fixed;
  bottom:12px;
  left:12px;
  z-index:80;
  display:flex;
  align-items:center;
  gap:6px;
  background:rgba(25,8,15,.94);
  border:1px solid #71304d;
  padding:7px;
  border-radius:15px;
}
#musicToggle{
  background:#7d2950;
  padding:9px 13px;
  border-radius:10px;
  font-weight:bold;
}
#musicToggle.on{background:#32774f}
#volume{
  width:80px;
  accent-color:var(--pink);
}

/* JOURNEY */
#journey{
  min-height:100vh;
  padding-bottom:90px;
}
.hero{
  max-width:900px;
  margin:auto;
  text-align:center;
  padding:34px 18px 18px;
}
.hero h1{
  font-size:clamp(34px,9vw,66px);
  margin:0;
  line-height:1;
}
.hero p{
  color:var(--muted);
  max-width:620px;
  margin:14px auto;
  line-height:1.6;
}
.nameBox{
  max-width:400px;
  margin:20px auto;
  display:flex;
  gap:8px;
}
.nameBox input{
  flex:1;
  min-width:0;
  padding:14px;
  border-radius:12px;
  border:1px solid #6b2d4a;
  background:#1d0b14;
  color:white;
  outline:none;
}
.primary{
  background:linear-gradient(135deg,#a92e61,#76203f);
  padding:13px 18px;
  border-radius:12px;
  font-weight:800;
  box-shadow:0 7px 20px rgba(0,0,0,.25);
}
.primary:active{transform:scale(.97)}
.progressWrap{
  max-width:700px;
  margin:20px auto;
}
.progressText{
  display:flex;
  justify-content:space-between;
  color:var(--muted);
  font-size:13px;
}
.progress{
  height:10px;
  background:#29101c;
  border-radius:20px;
  overflow:hidden;
  margin-top:7px;
}
.progress>div{
  height:100%;
  background:linear-gradient(90deg,#ff77ac,#ffc0da);
  transition:width .4s;
}
.map{
  max-width:900px;
  margin:25px auto;
  padding:0 14px;
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:10px;
}
.level{
  min-height:112px;
  background:linear-gradient(145deg,#2c1220,#1d0b14);
  border:1px solid #4d2136;
  border-radius:17px;
  padding:12px;
  text-align:left;
  position:relative;
  transition:.2s;
}
.level.available{
  border-color:#bd4677;
  box-shadow:0 0 20px rgba(255,105,160,.08);
}
.level.completed{
  border-color:#4d8c69;
}
.level.locked{
  opacity:.42;
  filter:saturate(.5);
}
.level:not(.locked):active{transform:scale(.97)}
.levelNum{
  font-size:11px;
  color:var(--pink);
  font-weight:bold;
}
.levelIcon{
  font-size:27px;
  margin:7px 0;
}
.levelName{
  font-weight:bold;
  font-size:13px;
}
.levelStatus{
  position:absolute;
  right:10px;
  top:10px;
  font-size:16px;
}
@media(max-width:650px){
  .headerInner{flex-wrap:wrap}
  .logo{width:100%;text-align:center}
  .map{grid-template-columns:repeat(2,1fr)}
}
@media(max-width:390px){
  .map{grid-template-columns:1fr}
}

/* GAME SCREEN */
#gameScreen{
  min-height:100vh;
  background:
    radial-gradient(circle at 50% 0,#351426 0,#15080f 48%,#0e060a 100%);
}
.gameTop{
  width:100%;
  max-width:1000px;
  margin:auto;
  padding:18px 16px 8px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:10px;
}
.gameTop h2{
  margin:0;
  font-size:clamp(22px,6vw,36px);
}
.gameMini{
  color:var(--muted);
  font-size:13px;
  text-align:right;
}
.gameContent{
  max-width:850px;
  margin:auto;
  min-height:calc(100vh - 90px);
  padding:12px 16px 45px;
  display:flex;
  flex-direction:column;
  align-items:center;
}
.instruction{
  color:var(--muted);
  text-align:center;
  max-width:650px;
  line-height:1.5;
  margin:8px 0 18px;
}
.gameBox{
  width:min(100%,700px);
  background:rgba(40,16,29,.88);
  border:1px solid #57243d;
  border-radius:22px;
  padding:18px;
  box-shadow:0 15px 50px rgba(0,0,0,.3);
}
.gameActions{
  display:flex;
  justify-content:center;
  gap:8px;
  flex-wrap:wrap;
  margin-top:18px;
}
.backBtn{
  background:#321421;
  border:1px solid #59263f;
  padding:10px 15px;
  border-radius:10px;
}
.bigBtn{
  background:#8d2855;
  padding:13px 20px;
  border-radius:13px;
  font-weight:bold;
  min-width:120px;
}
.success{
  text-align:center;
  padding:45px 20px;
}
.success .emoji{font-size:65px}
.success h2{font-size:38px;margin:10px 0}
.success p{color:var(--muted);line-height:1.6}
.nextBtn{
  margin-top:18px;
  background:linear-gradient(135deg,#d24c86,#8e2755);
  padding:16px 30px;
  border-radius:14px;
  font-size:17px;
  font-weight:900;
}
.failBox{text-align:center;padding:25px}
.failBox h3{font-size:28px}
.muted{color:var(--muted)}
.gameStat{
  text-align:center;
  font-weight:bold;
  margin:8px;
}

/* 1 BROKEN HEARTS */
#heartCatch{
  height:470px;
  max-width:430px;
  margin:auto;
  position:relative;
  overflow:hidden;
  border-radius:18px;
  background:linear-gradient(#21101d,#10080e);
  border:1px solid #5b2942;
}
.catchHeart{
  position:absolute;
  font-size:31px;
  user-select:none;
  transition:none;
}
.catcher{
  position:absolute;
  bottom:12px;
  width:80px;
  height:28px;
  border-radius:20px;
  background:#e66d9e;
  box-shadow:0 0 15px rgba(255,130,180,.35);
}
.heartControls{
  display:flex;
  justify-content:center;
  gap:15px;
  margin-top:10px;
}
.moveBtn{
  width:70px;
  height:50px;
  border-radius:13px;
  background:#622443;
  font-size:24px;
}

/* 2 MEMORY */
.memoryGrid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:9px;
  max-width:440px;
  margin:15px auto;
}
.memoryTile{
  aspect-ratio:1;
  border-radius:13px;
  background:#4a1b31;
  border:2px solid #71304f;
  font-size:23px;
}
.memoryTile.show,.memoryTile.selected{
  background:#c34c80;
}
.memoryTile.correctFlash{background:#39845b}
.memoryTile.wrongFlash{background:#9d3449}

/* QUIZZES */
.quizQuestion{
  font-size:21px;
  font-weight:bold;
  line-height:1.4;
  text-align:center;
  margin:15px auto 20px;
  max-width:650px;
}
.answerGrid{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:10px;
}
.answer{
  min-height:62px;
  border-radius:13px;
  background:#351729;
  border:1px solid #61304a;
  padding:12px;
  text-align:left;
}
.answer:hover{background:#55213c}
.answer.correct{background:#286844;border-color:#67d08d}
.answer.wrong{background:#7c293d;border-color:#e06a80}
.timerBar{
  height:9px;
  background:#180a10;
  border-radius:10px;
  overflow:hidden;
}
.timerBar div{
  height:100%;
  background:#ff83b4;
  width:100%;
  transition:width linear;
}

/* SLOT */
.slotMachine{
  text-align:center;
}
.reels{
  display:flex;
  justify-content:center;
  gap:9px;
  margin:20px 0;
}
.reel{
  width:90px;
  height:100px;
  background:#12090e;
  border:3px solid #8b3c5e;
  border-radius:15px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:48px;
}
.lever{
  width:55px;
  height:100px;
  border-radius:30px;
  background:#542039;
  position:relative;
  margin:10px auto;
}
.lever:after{
  content:"";
  position:absolute;
  top:8px;
  left:17px;
  width:21px;
  height:45px;
  border-radius:20px;
  background:#f08ab4;
}
.slotResult{
  min-height:28px;
  font-weight:bold;
  color:var(--gold);
}

/* MIND */
.patternRow,.patternOptions{
  display:flex;
  justify-content:center;
  align-items:center;
  gap:10px;
  flex-wrap:wrap;
}
.patternCard{
  width:65px;
  height:65px;
  border-radius:12px;
  background:#4b1c33;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:29px;
}
.patternOption{
  width:80px;
  height:65px;
}

/* BLUFF */
.cards{
  display:flex;
  gap:10px;
  justify-content:center;
  flex-wrap:wrap;
}
.playCard{
  width:75px;
  height:105px;
  border-radius:12px;
  background:linear-gradient(145deg,#6c2350,#301124);
  border:2px solid #a64b79;
  font-size:25px;
  font-weight:bold;
}
.playCard.revealed{
  background:#f6dce7;
  color:#4b172e;
}

/* SURVIVAL */
.survivalIcon{
  text-align:center;
  font-size:70px;
  margin:10px;
}
.survivalChoices{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:10px;
}

/* RACE */
.raceTrack{
  height:270px;
  background:repeating-linear-gradient(
    0deg,
    #25101a 0,
    #25101a 45px,
    #321522 45px,
    #321522 90px
  );
  border-radius:18px;
  position:relative;
  overflow:hidden;
  border:1px solid #62314a;
}
.horseRow{
  position:absolute;
  left:0;
  width:100%;
  height:50%;
  display:flex;
  align-items:center;
  padding:0 12px;
  gap:10px;
}
.horseRow:nth-child(2){top:50%}
.horse{
  font-size:45px;
  transition:margin-left .3s;
}
.raceFinish{
  position:absolute;
  right:8px;
  top:0;
  bottom:0;
  border-left:4px dashed white;
}
.timingBar{
  height:40px;
  border-radius:20px;
  background:#1a0b11;
  position:relative;
  overflow:hidden;
  margin:18px 0;
}
.timingZone{
  position:absolute;
  left:43%;
  width:18%;
  top:0;
  bottom:0;
  background:#4a9568;
}
.timingMarker{
  position:absolute;
  top:3px;
  bottom:3px;
  width:9px;
  border-radius:10px;
  background:#fff;
}

/* ESCAPE */
.sceneGrid{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:12px;
}
.sceneObject{
  min-height:110px;
  border-radius:15px;
  background:#351727;
  border:1px solid #623049;
  font-size:18px;
}
.clues{
  display:flex;
  gap:7px;
  justify-content:center;
  flex-wrap:wrap;
  margin-top:15px;
}
.clue{
  padding:7px 10px;
  border-radius:9px;
  background:#5a2340;
  font-size:12px;
}

/* BOXING */
.fighters{
  display:flex;
  justify-content:space-around;
  align-items:center;
  margin:20px 0;
}
.fighter{
  text-align:center;
  font-size:65px;
}
.health{
  width:150px;
  height:12px;
  background:#16090f;
  border-radius:10px;
  overflow:hidden;
  margin-top:8px;
}
.health div{
  height:100%;
  background:#66d88b;
}
.enemyHealth div{background:#e65e77}
.combatActions{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:9px;
}
.combatBtn{
  padding:14px;
  border-radius:12px;
  background:#622340;
}

/* MATCH */
.matchArea{
  position:relative;
  min-height:350px;
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:20px;
}
.matchColumn{
  display:flex;
  flex-direction:column;
  gap:12px;
}
.matchItem{
  min-height:55px;
  padding:13px;
  background:#54203b;
  border:2px solid #7b3657;
  border-radius:13px;
  text-align:center;
  touch-action:none;
}
.matchItem.selected{outline:3px solid var(--gold)}
.matchTarget{
  min-height:55px;
  padding:13px;
  border:2px dashed #a64d78;
  border-radius:13px;
  text-align:center;
  color:#b9859d;
}
.matchTarget.filled{
  background:#275d43;
  border-style:solid;
  color:white;
}

/* REACTION */
.reactionPad{
  min-height:330px;
  display:flex;
  align-items:center;
  justify-content:center;
  border-radius:20px;
  background:#190b12;
}
.reactionTarget{
  width:190px;
  height:190px;
  border-radius:50%;
  background:#ad3c6e;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:25px;
  font-weight:900;
}
.reactionTarget.danger{background:#913347}

/* HEART HUNT */
.huntArea{
  height:440px;
  position:relative;
  overflow:hidden;
  border-radius:20px;
  background:
    radial-gradient(circle at 20% 30%,#542039 0 8%,transparent 9%),
    radial-gradient(circle at 80% 70%,#321525 0 12%,transparent 13%),
    #160a10;
}
.huntHeart{
  position:absolute;
  font-size:30px;
  cursor:pointer;
  animation:floatHeart 2.8s ease-in-out infinite alternate;
}
@keyframes floatHeart{
  from{transform:translateY(-5px)}
  to{transform:translateY(8px)}
}

/* LOCK */
.lockDisplay{
  background:#10070c;
  border:1px solid #5f2943;
  border-radius:12px;
  padding:15px;
  text-align:center;
  font-size:28px;
  letter-spacing:8px;
  margin-bottom:15px;
}
.keypad{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:8px;
  max-width:300px;
  margin:auto;
}
.key{
  padding:16px;
  border-radius:11px;
  background:#512039;
  font-weight:bold;
}

/* CUPID */
.shootArea{
  height:430px;
  position:relative;
  overflow:hidden;
  border-radius:20px;
  background:radial-gradient(circle,#3a1729,#13080e);
}
.shootTarget{
  position:absolute;
  font-size:34px;
  cursor:pointer;
  user-select:none;
}

/* COUNTDOWN */
.miniGame{
  min-height:300px;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  text-align:center;
}
.stopBar{
  width:90%;
  height:35px;
  background:#16090f;
  border-radius:20px;
  position:relative;
  overflow:hidden;
}
.stopZone{
  position:absolute;
  left:42%;
  width:16%;
  height:100%;
  background:#4c986a;
}
.stopMarker{
  position:absolute;
  left:0;
  top:3px;
  bottom:3px;
  width:10px;
  border-radius:10px;
  background:white;
}
.circleRow{
  display:flex;
  gap:15px;
  flex-wrap:wrap;
  justify-content:center;
}
.countCircle{
  width:75px;
  height:75px;
  border-radius:50%;
  background:#74305a;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:25px;
}

/* GAMBLE */
.pot{
  font-size:50px;
  text-align:center;
  font-weight:900;
  color:var(--gold);
  margin:20px;
}
.gambleActions{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:10px;
}

/* BOSS */
.boss{
  text-align:center;
  font-size:90px;
  animation:breathe 2s infinite ease-in-out;
}
@keyframes breathe{
  50%{transform:scale(1.05)}
}
.bossPhase{
  text-align:center;
  color:var(--pink);
  font-weight:bold;
}
.bossActions{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:9px;
}

/* WORD FIND */
.wordFindWrap{
  overflow:auto;
}
.wordList{
  display:flex;
  gap:6px;
  flex-wrap:wrap;
  margin-bottom:12px;
}
.wordTag{
  background:#321523;
  border:1px solid #57263e;
  padding:5px 8px;
  border-radius:8px;
  font-size:11px;
}
.wordTag.found{
  background:#337050;
  text-decoration:line-through;
}
.wordGrid{
  display:grid;
  grid-template-columns:repeat(14,1fr);
  gap:2px;
  max-width:620px;
  margin:auto;
  touch-action:none;
}
.letter{
  aspect-ratio:1;
  display:flex;
  align-items:center;
  justify-content:center;
  background:#301522;
  border-radius:4px;
  font-size:clamp(10px,2.8vw,17px);
  font-weight:bold;
  user-select:none;
}
.letter.selecting{background:#92506d}
.letter.found{background:#3c7d59;color:white}

/* DRAW */
#drawCanvas{
  width:100%;
  max-width:650px;
  height:420px;
  background:#fff8fb;
  border-radius:15px;
  touch-action:none;
  display:block;
}
.drawTools{
  display:flex;
  gap:7px;
  flex-wrap:wrap;
  justify-content:center;
  margin:10px 0;
}
.drawTools button{
  width:35px;
  height:35px;
  border-radius:50%;
  background:#743053;
}
.drawTools button.active{outline:3px solid white}

/* DERBY */
.derbyHorses{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:10px;
}
.derbyHorse{
  padding:18px 8px;
  background:#3b1729;
  border:2px solid #5c2742;
  border-radius:15px;
  font-size:30px;
}
.derbyHorse.selected{
  border-color:var(--gold);
  box-shadow:0 0 20px rgba(255,214,107,.12);
}
.derbyTrack{
  margin:15px 0;
  display:flex;
  flex-direction:column;
  gap:9px;
}
.derbyLane{
  height:38px;
  border-radius:10px;
  background:#17090f;
  position:relative;
  overflow:hidden;
}
.derbyRunner{
  position:absolute;
  left:4px;
  top:3px;
  font-size:27px;
  transition:left .4s;
}
.triviaCounter{
  text-align:center;
  color:var(--muted);
}

/* FINAL */
.finalScore{
  font-size:30px;
  text-align:center;
  color:var(--gold);
}

/* COMPLETION */
#completion{
  min-height:100vh;
  display:flex;
  align-items:center;
  justify-content:center;
  padding:20px;
}
.completionCard{
  width:min(600px,100%);
  text-align:center;
  background:#2a1120;
  border:1px solid #672a47;
  border-radius:25px;
  padding:35px 20px;
}
.completionEmoji{font-size:70px}

/* MOBILE */
@media(max-width:600px){
  .answerGrid{grid-template-columns:1fr}
  .gameContent{padding-left:10px;padding-right:10px}
  .gameBox{padding:13px}
  .gameTop{padding:13px 10px}
  .gameTop h2{font-size:23px}
  .matchArea{gap:8px}
  .matchItem,.matchTarget{font-size:13px;padding:10px}
  .reel{width:75px;height:85px}
  .bossActions{grid-template-columns:1fr}
}
</style>
</head>

<body>

<div id="app">

  <!-- JOURNEY SCREEN -->
  <section id="journey">
    <div id="journeyHeader">
      <div class="headerInner">
        <div class="logo">🚂 Lulu Express</div>
        <div class="stats">
          <div class="stat">⭐ <span id="score">0</span></div>
          <div class="stat">💗 <span id="tokens">0</span></div>
          <div class="stat">👤 <span id="playerNameHeader">Player</span></div>
        </div>
        <div class="headerButtons">
          <button class="smallBtn" onclick="toggleMusic()">🎵 Music</button>
          <button class="smallBtn" onclick="resetGame()">↻ Reset</button>
        </div>
      </div>
    </div>

    <div class="hero">
      <h1>Lulu Express 🚂💗</h1>
      <p>
        A little journey made especially for Liliana.
        Pass each challenge to unlock the next stop.
      </p>

      <div id="nameEntry" class="nameBox">
        <input id="playerName" maxlength="25" placeholder="Enter your name">
        <button class="primary" onclick="startJourney()">Start Journey</button>
      </div>

      <div id="welcomeText" class="hidden">
        <h2>Welcome aboard, <span id="welcomeName"></span> 💗</h2>
        <p>Your next unlocked challenge is waiting for you.</p>
      </div>

      <div class="progressWrap">
        <div class="progressText">
          <span>Journey Progress</span>
          <span id="progressText">0 / 23</span>
        </div>
        <div class="progress">
          <div id="progressFill" style="width:0%"></div>
        </div>
      </div>
    </div>

    <div id="levelMap" class="map"></div>
  </section>

  <!-- GAME SCREEN -->
  <section id="gameScreen" class="hidden">
    <div class="gameTop">
      <div>
        <h2 id="gameTitle"></h2>
        <div id="gameSubtitle" class="muted"></div>
      </div>
      <div class="gameMini">
        Level <span id="gameNumber">1</span>/23
      </div>
    </div>

    <div id="gameContent" class="gameContent"></div>
  </section>

  <!-- COMPLETION SCREEN -->
  <section id="completion" class="hidden">
    <div class="completionCard">
      <div class="completionEmoji">🎉</div>
      <h1 id="completionTitle">Level Complete!</h1>
      <p id="completionMessage"></p>
      <p><strong>⭐ Points earned: <span id="earnedPoints">0</span></strong></p>
      <p><strong>💗 Tokens earned: <span id="earnedTokens">0</span></strong></p>
      <button class="nextBtn" onclick="nextLevel()">Next Level →</button>
    </div>
  </section>

  <!-- SIMPLE BUILT-IN MUSIC -->
  <div id="musicPanel" class="hidden">
    <button id="musicToggle" onclick="toggleMusic()">🎵 Music Off</button>
    <input id="volume" type="range" min="0" max="1" step=".05" value=".12"
           onchange="setVolume(this.value)">
  </div>

</div>

<script>
/* =========================================================
   LULU EXPRESS
   23 FULL GAMES
   ========================================================= */

const TOTAL_LEVELS = 23;

const levels = [
  ["💔","Broken Hearts"],
  ["🧠","Memory Vault"],
  ["⏱️","Pressure Quiz"],
  ["🎰","High Roller"],
  ["🧩","Mind Games"],
  ["🃏","The Bluff"],
  ["🛡️","Survival Round"],
  ["🏇","The Admirer Race"],
  ["🔎","Heartbreak Chamber"],
  ["🥊","Heartbreak Boxing"],
  ["🧲","Perfect Match"],
  ["💗","Who Knows Liliana Best?"],
  ["⚡","Reaction Gauntlet"],
  ["🕵️","Heart Hunt"],
  ["🔐","Love Lock"],
  ["🏹","Cupid Shootout"],
  ["⏳","The Countdown"],
  ["🎲","Ultimate Gamble"],
  ["👑","Admirer's Last Stand"],
  ["🔎","Liliana's Word Find"],
  ["🌻","Draw a Sunflower"],
  ["🏇","THE LULU DERBY"],
  ["💕","THE FINAL CHALLENGE"]
];

let state = {
  name:"",
  score:0,
  tokens:0,
  unlocked:1,
  completed:[],
  current:0
};

let cleanupGame = null;
let gameTimer = null;

function loadState(){
  try{
    const saved = JSON.parse(localStorage.getItem("luluExpressState"));
    if(saved) state = {...state,...saved};
  }catch(e){}
}

function saveState(){
  localStorage.setItem("luluExpressState",JSON.stringify(state));
}

function updateHeader(){
  document.getElementById("score").textContent=state.score;
  document.getElementById("tokens").textContent=state.tokens;
  document.getElementById("playerNameHeader").textContent=state.name||"Player";
  const done=state.completed.length;
  document.getElementById("progressText").textContent=done+" / "+TOTAL_LEVELS;
  document.getElementById("progressFill").style.width=(done/TOTAL_LEVELS*100)+"%";
}

function renderMap(){
  const map=document.getElementById("levelMap");
  map.innerHTML="";

  levels.forEach((level,i)=>{
    const n=i+1;
    const completed=state.completed.includes(n);
    const available=n<=state.unlocked;

    const el=document.createElement("button");
    el.className="level "+(completed?"completed ":"")+
      (available?"available":"locked");

    el.disabled=!available;

    el.innerHTML=`
      <div class="levelNum">LEVEL ${n}</div>
      <div class="levelIcon">${level[0]}</div>
      <div class="levelName">${level[1]}</div>
      <div class="levelStatus">${completed?"✅":available?"▶️":"🔒"}</div>
    `;

    if(available) el.onclick=()=>openLevel(n);
    map.appendChild(el);
  });
}

function startJourney(){
  const input=document.getElementById("playerName");
  const name=input.value.trim();

  if(!name){
    input.focus();
    input.placeholder="Please enter your name 💗";
    return;
  }

  state.name=name;
  saveState();

  document.getElementById("nameEntry").classList.add("hidden");
  document.getElementById("welcomeText").classList.remove("hidden");

  updateHeader();
  renderMap();
}

function showJourney(){
  clearGame();
  document.getElementById("gameScreen").classList.add("hidden");
  document.getElementById("completion").classList.add("hidden");
  document.getElementById("journey").classList.remove("hidden");
  document.getElementById("journeyHeader").classList.remove("hidden");
  document.getElementById("musicPanel").classList.remove("hidden");
  updateHeader();
  renderMap();
}

function openLevel(n){
  if(n>state.unlocked)return;

  clearGame();
  state.current=n;
  saveState();

  document.getElementById("journey").classList.add("hidden");
  document.getElementById("completion").classList.add("hidden");
  document.getElementById("gameScreen").classList.remove("hidden");

  /* IMPORTANT:
     The journey header, tokens, score and music controls
     disappear while the game is being played.
  */
  document.getElementById("journeyHeader").classList.add("hidden");
  document.getElementById("musicPanel").classList.add("hidden");

  document.getElementById("gameNumber").textContent=n;
  document.getElementById("gameTitle").textContent=levels[n-1][0]+" "+levels[n-1][1];
  document.getElementById("gameSubtitle").textContent=
    state.name ? "Good luck, "+state.name+" 💗" : "";

  gameLaunchers[n]();
}

function clearGame(){
  if(cleanupGame){
    try{cleanupGame()}catch(e){}
    cleanupGame=null;
  }
  if(gameTimer){
    clearInterval(gameTimer);
    clearTimeout(gameTimer);
    gameTimer=null;
  }
}

function award(points,tokens=1){
  state.score+=points;
  state.tokens+=tokens;
}

function passGame(points,tokens=1,message="You passed the challenge!"){
  clearGame();

  const n=state.current;

  if(!state.completed.includes(n)){
    state.completed.push(n);
    if(n===state.unlocked && state.unlocked<TOTAL_LEVELS){
      state.unlocked++;
    }
  }

  const oldScore=state.score;
  award(points,tokens);
  const earned=state.score-oldScore;

  saveState();

  document.getElementById("gameScreen").classList.add("hidden");
  document.getElementById("completion").classList.remove("hidden");
  document.getElementById("musicPanel").classList.remove("hidden");

  document.getElementById("completionTitle").textContent=
    n===TOTAL_LEVELS ? "You finished Lulu Express! 💗" : "Level Complete! 🎉";

  document.getElementById("completionMessage").textContent=message;
  document.getElementById("earnedPoints").textContent=earned;
  document.getElementById("earnedTokens").textContent=tokens;

  if(n===TOTAL_LEVELS){
    document.querySelector("#completion .nextBtn").textContent="Back to Journey";
  }else{
    document.querySelector("#completion .nextBtn").textContent="Next Level →";
  }
}

function nextLevel(){
  const n=state.current;

  if(n>=TOTAL_LEVELS){
    showJourney();
    return;
  }

  openLevel(n+1);
}

function failGame(message, retry=true){
  clearGame();

  const box=document.createElement("div");
  box.className="failBox gameBox";
  box.innerHTML=`
    <div style="font-size:55px">💗</div>
    <h3>${message||"Not quite!"}</h3>
    <p class="muted">Don't worry. This challenge is meant to be fun.</p>
    <div class="gameActions">
      <button class="bigBtn" onclick="openLevel(${state.current})">Try Again</button>
      <button class="backBtn" onclick="showJourney()">Journey</button>
    </div>
  `;
  document.getElementById("gameContent").innerHTML="";
  document.getElementById("gameContent").appendChild(box);
}

/* =========================================================
   MUSIC
   Simple Web Audio game music.
   No external file or URL required.
   ========================================================= */

let audioCtx=null;
let musicGain=null;
let musicInterval=null;
let musicOn=false;

function ensureAudio(){
  if(!audioCtx){
    audioCtx=new(window.AudioContext||window.webkitAudioContext)();
    musicGain=audioCtx.createGain();
    musicGain.gain.value=.12;
    musicGain.connect(audioCtx.destination);
  }
  if(audioCtx.state==="suspended")audioCtx.resume();
}

function playNote(freq,duration=.16){
  if(!musicOn)return;
  ensureAudio();

  const osc=audioCtx.createOscillator();
  const gain=audioCtx.createGain();

  osc.type="triangle";
  osc.frequency.value=freq;

  gain.gain.setValueAtTime(0,audioCtx.currentTime);
  gain.gain.linearRampToValueAtTime(.35,audioCtx.currentTime+.02);
  gain.gain.exponentialRampToValueAtTime(.001,audioCtx.currentTime+duration);

  osc.connect(gain);
  gain.connect(musicGain);

  osc.start();
  osc.stop(audioCtx.currentTime+duration+.03);
}

const melody=[261.63,329.63,392,329.63,293.66,349.23,440,349.23];
let melodyIndex=0;

function startMusic(){
  ensureAudio();
  musicOn=true;

  if(musicInterval)return;

  melodyIndex=0;
  playNote(melody[melodyIndex++]);

  musicInterval=setInterval(()=>{
    playNote(melody[melodyIndex%melody.length]);
    melodyIndex++;
  },360);

  updateMusicButton();
}

function stopMusic(){
  musicOn=false;
  if(musicInterval){
    clearInterval(musicInterval);
    musicInterval=null;
  }
  updateMusicButton();
}

function toggleMusic(){
  if(musicOn)stopMusic();
  else startMusic();
}

function updateMusicButton(){
  const btn=document.getElementById("musicToggle");
  btn.textContent=musicOn?"🎵 Music On":"🎵 Music Off";
  btn.classList.toggle("on",musicOn);
}

function setVolume(v){
  ensureAudio();
  musicGain.gain.value=Number(v);
}

/* =========================================================
   GAME 1 — BROKEN HEARTS
   ========================================================= */

function game1(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Catch the whole hearts 💗 and golden hearts 💛.
      Avoid the broken hearts 💔. Use the buttons or drag the catcher.
      Catch 18 good hearts before you lose all 3 lives.
    </p>

    <div class="gameBox">
      <div class="gameStat">
        💗 <span id="catchScore">0</span>/18
        &nbsp;&nbsp; ❤️ Lives: <span id="catchLives">3</span>
      </div>

      <div id="heartCatch">
        <div id="catcher" class="catcher"></div>
      </div>

      <div class="heartControls">
        <button class="moveBtn" id="leftCatch">←</button>
        <button class="moveBtn" id="rightCatch">→</button>
      </div>
    </div>
  `;

  const area=document.getElementById("heartCatch");
  const catcher=document.getElementById("catcher");
  let x=area.clientWidth/2-40;
  let score=0;
  let lives=3;
  let hearts=[];
  let spawnTimer;
  let running=true;

  catcher.style.left=x+"px";

  function move(dx){
    x=Math.max(0,Math.min(area.clientWidth-80,x+dx));
    catcher.style.left=x+"px";
  }

  document.getElementById("leftCatch").onclick=()=>move(-45);
  document.getElementById("rightCatch").onclick=()=>move(45);

  function pointerMove(e){
    const rect=area.getBoundingClientRect();
    x=Math.max(0,Math.min(area.clientWidth-80,
      e.clientX-rect.left-40));
    catcher.style.left=x+"px";
  }

  area.addEventListener("pointermove",pointerMove);

  function spawn(){
    if(!running)return;

    const el=document.createElement("div");
    const good=Math.random()>.22;
    const golden=good&&Math.random()<.12;

    el.className="catchHeart";
    el.textContent=golden?"💛":good?"💗":"💔";
    el.style.left=Math.random()*(area.clientWidth-40)+"px";
    el.style.top="-40px";

    area.appendChild(el);

    hearts.push({
      el,
      y:-40,
      good,
      golden,
      speed:2+Math.random()*1.7
    });
  }

  let last=performance.now();

  function loop(now){
    if(!running)return;

    const dt=Math.min(32,now-last);
    last=now;

    hearts.forEach((h,i)=>{
      h.y+=h.speed*(dt/16);
      h.el.style.top=h.y+"px";

      const hx=parseFloat(h.el.style.left);
      const hy=h.y;

      if(
        hy>area.clientHeight-65 &&
        hy<area.clientHeight-5 &&
        hx+32>x &&
        hx<x+80
      ){
        if(h.good){
          score+=h.golden?2:1;
          document.getElementById("catchScore").textContent=score;

          if(score>=18){
            running=false;
            passGame(120,3,
              "You caught enough hearts and made it safely through Broken Hearts! 💗");
          }
        }else{
          lives--;
          document.getElementById("catchLives").textContent=lives;

          if(lives<=0){
            running=false;
            failGame("Too many broken hearts got through!");
          }
        }

        h.el.remove();
        hearts.splice(i,1);
      }else if(hy>area.clientHeight+20){
        if(h.good){
          lives--;
          document.getElementById("catchLives").textContent=lives;

          if(lives<=0){
            running=false;
            failGame("Too many hearts slipped past!");
          }
        }
        h.el.remove();
        hearts.splice(i,1);
      }
    });

    requestAnimationFrame(loop);
  }

  spawnTimer=setInterval(spawn,650);
  requestAnimationFrame(loop);

  cleanupGame=()=>{
    running=false;
    clearInterval(spawnTimer);
    area.removeEventListener("pointermove",pointerMove);
  };
}

/* =========================================================
   GAME 2 — MEMORY VAULT
   ========================================================= */

function game2(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Watch the glowing tiles, then tap them in the same order.
      You only need 7 successful rounds.
    </p>
    <div class="gameBox">
      <div class="gameStat">
        Round <span id="memoryRound">1</span>/7
      </div>
      <div id="memoryGrid" class="memoryGrid"></div>
      <div id="memoryMessage" class="gameStat muted">Get ready...</div>
    </div>
  `;

  const grid=document.getElementById("memoryGrid");
  const message=document.getElementById("memoryMessage");

  const symbols=["💗","⭐","🌙","🌸","💎","🦋","🌻","✨"];
  let sequence=[];
  let input=[];
  let round=1;
  let accepting=false;
  let timer;

  function build(){
    grid.innerHTML="";
    for(let i=0;i<16;i++){
      const b=document.createElement("button");
      b.className="memoryTile";
      b.dataset.i=i;
      b.textContent=symbols[i%symbols.length];
      b.onclick=()=>choose(i);
      grid.appendChild(b);
    }
  }

  function showSequence(){
    accepting=false;
    input=[];
    message.textContent="Watch carefully...";

    const tiles=[...grid.children];

    tiles.forEach(t=>t.classList.remove("show","selected"));

    sequence=[];
    const length=Math.min(2+round-1,8);

    while(sequence.length<length){
      const n=Math.floor(Math.random()*16);
      if(!sequence.includes(n))sequence.push(n);
    }

    sequence.forEach((n,i)=>{
      timer=setTimeout(()=>{
        tiles[n].classList.add("show");
        setTimeout(()=>tiles[n].classList.remove("show"),300);
      },i*450);
    });

    timer=setTimeout(()=>{
      accepting=true;
      message.textContent="Your turn!";
    },sequence.length*450+250);
  }

  function choose(i){
    if(!accepting)return;

    input.push(i);
    grid.children[i].classList.add("selected");

    const pos=input.length-1;

    if(input[pos]!==sequence[pos]){
      accepting=false;
      message.textContent="Almost! Watch it again.";
      grid.children[i].classList.add("wrongFlash");

      setTimeout(()=>{
        grid.children[i].classList.remove("wrongFlash","selected");
        showSequence();
      },650);
      return;
    }

    if(input.length===sequence.length){
      accepting=false;
      message.textContent="Perfect! 💗";

      grid.querySelectorAll(".selected").forEach(x=>{
        x.classList.remove("selected");
        x.classList.add("correctFlash");
      });

      if(round>=7){
        setTimeout(()=>{
          passGame(140,3,"Your memory was strong enough to open the Memory Vault! 🧠💗");
        },700);
      }else{
        round++;
        document.getElementById("memoryRound").textContent=round;

        setTimeout(()=>{
          grid.querySelectorAll(".correctFlash")
            .forEach(x=>x.classList.remove("correctFlash"));
          showSequence();
        },750);
      }
    }
  }

  build();
  timer=setTimeout(showSequence,600);

  cleanupGame=()=>clearTimeout(timer);
}

/* =========================================================
   QUIZ DATA
   ========================================================= */

const pressureQuestions=[
 ["What is the capital of Australia?",["Canberra","Sydney","Melbourne","Perth"],0],
 ["Which planet is known as the Red Planet?",["Mars","Venus","Jupiter","Mercury"],0],
 ["What is the chemical symbol for gold?",["Au","Ag","Gd","Go"],0],
 ["How many continents are there?",["7","5","6","8"],0],
 ["Which is the largest ocean?",["Pacific","Atlantic","Indian","Arctic"],0],
 ["Which animal is the fastest on land?",["Cheetah","Lion","Horse","Leopard"],0],
 ["How many sides does an octagon have?",["8","6","7","10"],0],
 ["Which gas makes up most of Earth's atmosphere?",["Nitrogen","Oxygen","Carbon dioxide","Hydrogen"],0],
 ["Which author wrote Pride and Prejudice?",["Jane Austen","Emily Brontë","Mary Shelley","Virginia Woolf"],0],
 ["What is the currency of Japan?",["Yen","Won","Dollar","Rupee"],0],
 ["How many chambers does the human heart have?",["4","2","3","5"],0],
 ["What is H₂O?",["Water","Oxygen","Hydrogen","Salt"],0],
 ["Which planet is famous for its rings?",["Saturn","Mars","Venus","Earth"],0],
 ["What is the largest planet in our solar system?",["Jupiter","Saturn","Neptune","Earth"],0],
 ["What is the smallest prime number?",["2","1","3","0"],0],
 ["Who painted the Mona Lisa?",["Leonardo da Vinci","Michelangelo","Raphael","Van Gogh"],0],
 ["How long does Earth take to orbit the Sun?",["About 365 days","About 30 days","About 180 days","About 700 days"],0],
 ["What is the boiling point of water at sea level?",["100°C","50°C","90°C","120°C"],0],
 ["Which country is the Eiffel Tower in?",["France","Italy","Spain","Belgium"],0],
 ["Which animal is a mammal?",["Whale","Shark","Octopus","Trout"],0],
 ["What is the capital of New Zealand?",["Wellington","Auckland","Christchurch","Hamilton"],0],
 ["Which shape has three sides?",["Triangle","Square","Pentagon","Hexagon"],0],
 ["Which organ is primarily responsible for breathing?",["Lungs","Heart","Liver","Kidneys"],0],
 ["Which metal has the symbol Fe?",["Iron","Fluorine","Silver","Copper"],0],
 ["Which ocean surrounds Antarctica?",["Southern Ocean","Pacific Ocean","Indian Ocean","Atlantic Ocean"],0],
 ["Which instrument commonly has 88 keys?",["Piano","Violin","Flute","Trumpet"],0],
 ["Which country is famous for the Great Wall?",["China","Japan","India","Korea"],0],
 ["What do bees produce?",["Honey","Silk","Milk","Wax only"],0],
 ["Which natural satellite orbits Earth?",["Moon","Mars","Titan","Europa"],0],
 ["What is the square root of 81?",["9","8","7","10"],0]
];

const lilianaQuestions=[
 ["What is Liliana's favourite colour?",["Baby pink","Burgundy","Sky blue","Purple"],0],
 ["What is Liliana's favourite number?",["3","7","13","22"],0],
 ["Which food does Liliana like?",["Sushi","Porridge","Fish and chips","Tacos"],0],
 ["Which animal does Liliana like?",["Dolphins","Penguins","Tigers","Rabbits"],0],
 ["Which flower is one of Liliana's favourites?",["Sunflowers","Tulips","Lilies","Orchids"],0],
 ["Which other flower does Liliana like?",["Roses","Daisies","Lavender","Daffodils"],0],
 ["When is Liliana's birthday?",["22 July","22 June","12 July","27 July"],0],
 ["What colour are Liliana's eyes?",["Green","Brown","Blue","Hazel"],0],
 ["What is Liliana's zodiac sign?",["Leo","Cancer","Virgo","Gemini"],0],
 ["What is Liliana afraid of?",["Drowning","Flying","Spiders","Heights"],0],
 ["Which movie is a favourite of Liliana's?",["Me Before You","Titanic","The Notebook","Frozen"],0],
 ["What type of songs does Liliana enjoy?",["Sad songs","Country songs","Only rock","Only jazz"],0],
 ["What kind of writing does Liliana like?",["Poetry","News articles","Manuals","Cookbooks"],0],
 ["Which card game style does Liliana enjoy?",["Poker","Bridge","Go Fish","Snap"],0],
 ["What kind of games does Liliana enjoy?",["Gambling games","Puzzle books","Only racing games","Only sports games"],0],
 ["What did Liliana study at university?",["Psychology","Law","Engineering","Accounting"],0],
 ["How many nieces does Liliana have?",["1","2","3","4"],0],
 ["How many nephews does Liliana have?",["4","2","5","6"],0],
 ["How many siblings does Liliana have?",["5","3","4","6"],0],
 ["How many piercings does Liliana have?",["4","2","3","5"],0],
 ["Which pair are Liliana's dogs?",["Aayla and Arlo","Luna and Milo","Bella and Coco","Ayla and Archie"],0],
 ["How long have Bree and Liliana been best friends?",["6 years","3 years","5 years","7 years"],0],
 ["Which word describes Liliana well?",["Caring","Cold","Unfriendly","Impatient"],0],
 ["What quality is Liliana known for?",["Empathy","Cruelty","Impatience","Selfishness"],0],
 ["What does Liliana like about children?",["She likes children","She dislikes children","She avoids children","She is afraid of children"],0],
 ["What does Liliana hope to be someday?",["A mum","A pilot","A chef","A singer"],0],
 ["What kind of baby does Liliana dream of having?",["A baby girl","Twin boys","A baby boy","Triplets"],0],
 ["What does Liliana want to see someday?",["The ocean","The desert","The Arctic","A volcano"],0],
 ["Which combination belongs to Liliana?",["Sushi and dolphins","Pizza and wolves","Curry and horses","Pasta and bears"],0],
 ["Which combination matches her flowers?",["Sunflowers and roses","Tulips and orchids","Lilies and daisies","Lavender and tulips"],0],
 ["Which date correctly represents her birthday?",["22 July","7 February","27 July","2 June"],0],
 ["Which field is connected to Liliana's university studies?",["Psychology","Physics","Chemistry","Architecture"],0],
 ["How many nieces and nephews does Liliana have altogether?",["5","4","6","7"],0],
 ["Which of these is one of Liliana's pets?",["Aayla","Nala","Misty","Kiki"],0],
 ["Which of these is her other dog?",["Arlo","Oscar","Toby","Max"],0],
 ["Which number connects strongly with Liliana?",["3","8","11","14"],0],
 ["Which colour best matches her favourite aesthetic?",["Baby pink","Neon green","Orange","Black"],0],
 ["Which activity fits Liliana's interests?",["Poker","Surfing","Fishing","Rock climbing"],0],
 ["Which statement is true about her personality?",["She is charismatic","She is careless","She is distant","She is rude"],0],
 ["Which statement is true about Liliana?",["She likes poetry","She hates all writing","She dislikes music","She never watches films"],0]
];

function shuffle(arr){
  const a=[...arr];
  for(let i=a.length-1;i>0;i--){
    const j=Math.floor(Math.random()*(i+1));
    [a[i],a[j]]=[a[j],a[i]];
  }
  return a;
}

function randomisedQuestion(q){
  const options=q[1].map((text,i)=>({
    text,
    correct:i===q[2]
  }));
  return shuffle(options);
}

/* =========================================================
   GAME 3 — PRESSURE QUIZ
   ========================================================= */

function game3(){
  quizGame(
    pressureQuestions,
    10,
    6,
    "Answer quickly! You need 6 correct answers out of 10.",
    "Pressure Quiz",
    7
  );
}

/* =========================================================
   GENERIC QUIZ
   ========================================================= */

function quizGame(bank,total,needed,instruction,title,timeSeconds){
  const root=document.getElementById("gameContent");
  let questions=shuffle(bank).slice(0,total);
  let index=0;
  let correct=0;
  let answered=false;
  let timer;

  root.innerHTML=`
    <p class="instruction">${instruction}</p>
    <div class="gameBox">
      <div class="gameStat">
        Question <span id="quizIndex">1</span>/${total}
        &nbsp; • &nbsp; Correct: <span id="quizCorrect">0</span>
      </div>
      <div class="timerBar"><div id="quizTimer"></div></div>
      <div id="quizQuestion" class="quizQuestion"></div>
      <div id="quizAnswers" class="answerGrid"></div>
      <div id="quizFeedback" class="gameStat muted"></div>
    </div>
  `;

  function load(){
    answered=false;
    clearTimeout(timer);

    const q=randomisedQuestion(questions[index]);
    document.getElementById("quizIndex").textContent=index+1;
    document.getElementById("quizQuestion").textContent=q.question||questions[index][0];

    const qText=questions[index][0];
    document.getElementById("quizQuestion").textContent=qText;

    const answers=document.getElementById("quizAnswers");
    answers.innerHTML="";

    q.forEach((a,i)=>{
      const b=document.createElement("button");
      b.className="answer";
      b.textContent=a.text;
      b.onclick=()=>answer(b,a.correct);
      answers.appendChild(b);
    });

    const bar=document.getElementById("quizTimer");
    bar.style.transition="none";
    bar.style.width="100%";

    requestAnimationFrame(()=>{
      bar.style.transition=`width ${timeSeconds}s linear`;
      bar.style.width="0%";
    });

    timer=setTimeout(()=>answer(null,false,true),timeSeconds*1000);
  }

  function answer(button,isCorrect,timeout=false){
    if(answered)return;
    answered=true;
    clearTimeout(timer);

    const all=[...document.querySelectorAll("#quizAnswers .answer")];

    all.forEach((b,i)=>{
      const q=randomisedQuestion(questions[index]);
      /* We do not use this result to reveal answers. */
      b.disabled=true;
    });

    if(isCorrect){
      correct++;
      document.getElementById("quizCorrect").textContent=correct;
      if(button)button.classList.add("correct");
      document.getElementById("quizFeedback").textContent="Correct! 💗";
    }else{
      if(button)button.classList.add("wrong");
      document.getElementById("quizFeedback").textContent=
        timeout?"Time! ⏰":"Not quite!";
    }

    index++;

    if(index>=total){
      setTimeout(()=>{
        if(correct>=needed){
          passGame(
            100+correct*8,
            2,
            `You scored ${correct}/${total}. Great job, ${state.name}! 💗`
          );
        }else{
          failGame(`You got ${correct}/${total}. You need ${needed} to pass.`);
        }
      },650);
    }else{
      setTimeout(load,600);
    }
  }

  load();
  cleanupGame=()=>clearTimeout(timer);
}

/* =========================================================
   GAME 4 — HIGH ROLLER
   ========================================================= */

function game4(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Pull the lever to spin the three reels. You get 6 spins.
      Two matching symbols wins. Three matching symbols is a jackpot!
    </p>

    <div class="gameBox slotMachine">
      <div>Spins left: <strong id="slotSpins">6</strong></div>

      <div class="reels">
        <div class="reel" id="reel1">🍒</div>
        <div class="reel" id="reel2">⭐</div>
        <div class="reel" id="reel3">💎</div>
      </div>

      <button class="lever" id="slotLever" aria-label="Spin"></button>

      <div id="slotResult" class="slotResult">Pull the lever!</div>
      <div class="gameActions">
        <button class="bigBtn" id="spinBtn">SPIN 🎰</button>
      </div>
    </div>
  `;

  const symbols=["🍒","⭐","💎","7️⃣","💗","🌟"];
  let spins=6;
  let wins=0;
  let spinning=false;

  function spin(){
    if(spinning||spins<=0)return;
    spinning=true;
    spins--;
    document.getElementById("slotSpins").textContent=spins;

    const reels=[
      document.getElementById("reel1"),
      document.getElementById("reel2"),
      document.getElementById("reel3")
    ];

    reels.forEach((r,i)=>{
      let count=0;
      const t=setInterval(()=>{
        r.textContent=symbols[Math.floor(Math.random()*symbols.length)];
        count++;
        if(count>8+i*3)clearInterval(t);
      },80);
    });

    setTimeout(()=>{
      let a=symbols[Math.floor(Math.random()*symbols.length)];
      let b=Math.random()<.45?a:symbols[Math.floor(Math.random()*symbols.length)];
      let c=Math.random()<.4?b:symbols[Math.floor(Math.random()*symbols.length)];

      reels[0].textContent=a;
      reels[1].textContent=b;
      reels[2].textContent=c;

      if(a===b&&b===c){
        wins+=3;
        document.getElementById("slotResult").textContent=
          "🎉 JACKPOT! Three matched!";
      }else if(a===b||b===c||a===c){
        wins++;
        document.getElementById("slotResult").textContent=
          "✨ Two matched! Nice!";
      }else{
        document.getElementById("slotResult").textContent="No match. Try again!";
      }

      spinning=false;

      if(wins>=2){
        setTimeout(()=>{
          passGame(130,3,"You hit enough winning combinations to beat the High Roller! 🎰💗");
        },500);
      }else if(spins<=0){
        setTimeout(()=>{
          failGame("The reels didn't give you enough wins this time.");
        },500);
      }
    },900);
  }

  document.getElementById("spinBtn").onclick=spin;
  document.getElementById("slotLever").onclick=spin;
}

/* =========================================================
   GAME 5 — MIND GAMES
   ========================================================= */

function game5(){
  const patterns=[
    [["🌸","🌸","⭐","🌸","🌸","?"],["⭐","🌸","💗","🌸"]],
    [["1","2","3","4","?"],["5","6","7","8"]],
    [["🔴","🔵","🔴","🔵","?"],["🔴","🔵","🟢","🟡"]],
    [["🌙","⭐","🌙","⭐","?"],["🌙","☀️","💗","🌙"]],
    [["2","4","6","8","?"],["9","10","12","11"]],
    [["A","C","E","G","?"],["H","I","J","K"]],
    [["⬆️","➡️","⬇️","⬅️","?"],["⬆️","↗️","➡️","⬇️"]],
    [["🐶","🐱","🐶","🐱","?"],["🐶","🐭","🐱","🐰"]]
  ];

  const root=document.getElementById("gameContent");
  let round=0;
  let score=0;

  root.innerHTML=`
    <p class="instruction">
      Look for the simple pattern and choose what comes next.
      You need 5 out of 8.
    </p>
    <div class="gameBox">
      <div class="gameStat">Puzzle <span id="mindRound">1</span>/8</div>
      <div id="mindPattern" class="patternRow"></div>
      <div id="mindOptions" class="patternOptions"></div>
      <div id="mindFeedback" class="gameStat muted"></div>
    </div>
  `;

  function load(){
    const p=patterns[round];
    const pattern=document.getElementById("mindPattern");
    const opts=document.getElementById("mindOptions");

    pattern.innerHTML="";
    p[0].forEach(x=>{
      const d=document.createElement("div");
      d.className="patternCard";
      d.textContent=x;
      pattern.appendChild(d);
    });

    opts.innerHTML="";

    const correct={
      0:"⭐",
      1:"5",
      2:"🔴",
      3:"🌙",
      4:"10",
      5:"I",
      6:"⬆️",
      7:"🐶"
    }[round];

    shuffle(p[1]).forEach(x=>{
      const b=document.createElement("button");
      b.className="patternCard patternOption";
      b.textContent=x;
      b.onclick=()=>{
        [...opts.children].forEach(z=>z.disabled=true);

        if(x===correct){
          score++;
          document.getElementById("mindFeedback").textContent="Correct! 🧩";
        }else{
          document.getElementById("mindFeedback").textContent="Not quite!";
        }

        round++;

        if(round>=patterns.length){
          setTimeout(()=>{
            score>=5
              ?passGame(120,2,`You solved ${score}/8 logic puzzles! 🧩💗`)
              :failGame(`You solved ${score}/8. You need 5 to pass.`);
          },500);
        }else{
          document.getElementById("mindRound").textContent=round+1;
          setTimeout(load,500);
        }
      };
      opts.appendChild(b);
    });
  }

  load();
}

/* =========================================================
   GAME 6 — THE BLUFF
   ========================================================= */

function game6(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Choose a hidden card. Then decide whether to bank your points
      or double them. Higher cards are safer.
    </p>
    <div class="gameBox">
      <div class="gameStat">Round <span id="bluffRound">1</span>/5</div>
      <div class="cards" id="bluffCards"></div>
      <div id="bluffValue" class="gameStat"></div>
      <div id="bluffActions" class="gameActions"></div>
      <div id="bluffTotal" class="gameStat">Bank: 0</div>
    </div>
  `;

  let round=1;
  let bank=0;
  let selected=0;
  let value=0;

  function newRound(){
    selected=0;
    value=0;

    document.getElementById("bluffValue").textContent="Choose a card";
    document.getElementById("bluffActions").innerHTML="";

    const cards=document.getElementById("bluffCards");
    cards.innerHTML="";

    for(let i=0;i<4;i++){
      const b=document.createElement("button");
      b.className="playCard";
      b.textContent="❔";
      b.onclick=()=>chooseCard(b);
      cards.appendChild(b);
    }
  }

  function chooseCard(button){
    if(value)return;

    value=5+Math.floor(Math.random()*16);

    button.classList.add("revealed");
    button.textContent=value;

    [...document.querySelectorAll(".playCard")].forEach(b=>b.disabled=true);

    document.getElementById("bluffValue").textContent=
      `Your card is ${value}. What do you want to do?`;

    const actions=document.getElementById("bluffActions");

    const bankBtn=document.createElement("button");
    bankBtn.className="bigBtn";
    bankBtn.textContent="Bank "+value+" 💰";
    bankBtn.onclick=()=>finishRound(value);

    const doubleBtn=document.createElement("button");
    doubleBtn.className="bigBtn";
    doubleBtn.textContent="Double or Risk 🎲";
    doubleBtn.onclick=()=>{
      if(value>=11){
        finishRound(value*2);
      }else{
        document.getElementById("bluffValue").textContent=
          "The risk failed! But you can continue.";
        finishRound(0);
      }
    };

    actions.append(bankBtn,doubleBtn);
  }

  function finishRound(points){
    bank+=points;
    document.getElementById("bluffTotal").textContent="Bank: "+bank;

    if(round>=5){
      bank>=35
        ?passGame(120,2,`You finished with ${bank} points in The Bluff! 🃏`)
        :failGame(`You finished with ${bank}. Try taking a few more risks!`);
      return;
    }

    round++;
    document.getElementById("bluffRound").textContent=round;
    setTimeout(newRound,500);
  }

  newRound();
}

/* =========================================================
   GAME 7 — SURVIVAL ROUND
   ========================================================= */

function game7(){
  const waves=[
    ["🌊","A wave is rushing toward you!","Jump","Duck","Run","Freeze",0],
    ["⚡","Lightning is close!","Stay under tree","Go indoors","Stand outside","Hold metal",1],
    ["🔥","A small fire blocks the path!","Walk through","Find another route","Sit beside it","Add wood",1],
    ["🪨","Rocks are falling!","Move away","Look up only","Run underneath","Stand still",0],
    ["🌧️","Heavy rain starts!","Find shelter","Lie down","Climb a pole","Ignore it",0],
    ["🐝","A swarm appears!","Swat wildly","Move calmly away","Scream","Run into them",1],
    ["🌪️","A strong wind hits!","Find shelter","Hold a leaf","Stand on roof","Run toward it",0],
    ["🧊","The ground is slippery!","Slow down","Sprint","Jump repeatedly","Spin",0]
  ];

  const root=document.getElementById("gameContent");
  let wave=0;
  let score=0;
  let timer;

  root.innerHTML=`
    <p class="instruction">
      Choose the safest action. You need 6 safe decisions out of 8.
    </p>
    <div class="gameBox">
      <div class="gameStat">Wave <span id="survivalWave">1</span>/8</div>
      <div id="survivalIcon" class="survivalIcon"></div>
      <div id="survivalQuestion" class="quizQuestion"></div>
      <div id="survivalChoices" class="survivalChoices"></div>
      <div id="survivalTimer" class="gameStat muted">3 seconds</div>
    </div>
  `;

  function load(){
    const w=waves[wave];

    document.getElementById("survivalIcon").textContent=w[0];
    document.getElementById("survivalQuestion").textContent=w[1];

    const choices=document.getElementById("survivalChoices");
    choices.innerHTML="";

    w[2].slice().forEach((text,i)=>{
      const b=document.createElement("button");
      b.className="answer";
      b.textContent=text;
      b.onclick=()=>choose(i);
      choices.appendChild(b);
    });

    let seconds=3;
    document.getElementById("survivalTimer").textContent=seconds+" seconds";

    clearInterval(timer);
    timer=setInterval(()=>{
      seconds--;
      document.getElementById("survivalTimer").textContent=seconds+" seconds";
      if(seconds<=0){
        clearInterval(timer);
        choose(-1);
      }
    },1000);
  }

  function choose(i){
    clearInterval(timer);

    if(i===waves[wave][6]){
      score++;
      document.getElementById("survivalTimer").textContent="Safe! 🛡️";
    }else{
      document.getElementById("survivalTimer").textContent="Oops!";
    }

    wave++;

    if(wave>=waves.length){
      setTimeout(()=>{
        score>=6
          ?passGame(125,2,`You survived ${score}/8 hazards! 🛡️💗`)
          :failGame(`You survived ${score}/8. You need 6.`);
      },500);
    }else{
      document.getElementById("survivalWave").textContent=wave+1;
      setTimeout(load,500);
    }
  }

  load();
  cleanupGame=()=>clearInterval(timer);
}

/* =========================================================
   GAME 8 — ADMIRER RACE
   No obstacles. Timing race.
   ========================================================= */

function game8(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Time your gallop! Tap <strong>GALLop!</strong> when the marker
      enters the green zone. Perfect timing gives the biggest boost.
      Beat the admirer after 10 rounds.
    </p>

    <div class="gameBox">
      <div class="raceTrack">
        <div class="horseRow">
          <span>🏇</span>
          <div id="playerHorse" class="horse">🐎</div>
        </div>
        <div class="horseRow">
          <span>🤵</span>
          <div id="aiHorse" class="horse">🐎</div>
        </div>
        <div class="raceFinish"></div>
      </div>

      <div class="gameStat">
        Round <span id="raceRound">1</span>/10
        &nbsp; • &nbsp;
        You: <span id="racePlayer">0</span>
        &nbsp; • &nbsp;
        Admirer: <span id="raceAI">0</span>
      </div>

      <div class="timingBar" id="timingBar">
        <div class="timingZone"></div>
        <div class="timingMarker" id="timingMarker"></div>
      </div>

      <div class="gameActions">
        <button class="bigBtn" id="gallopBtn">GALLop! 🏇</button>
      </div>

      <div id="raceMessage" class="gameStat muted">Wait for the green zone...</div>
    </div>
  `;

  let round=1;
  let player=0;
  let ai=0;
  let marker=0;
  let direction=1;
  let raceTimer;
  let running=true;

  function moveMarker(){
    marker+=direction*1.8;

    if(marker>=96){
      marker=96;
      direction=-1;
    }
    if(marker<=0){
      marker=0;
      direction=1;
    }

    document.getElementById("timingMarker").style.left=marker+"%";
  }

  raceTimer=setInterval(moveMarker,25);

  document.getElementById("gallopBtn").onclick=()=>{
    if(!running)return;

    let gain;

    if(marker>=43&&marker<=61){
      gain=9;
      document.getElementById("raceMessage").textContent="PERFECT! ✨ +9";
    }else if(marker>=30&&marker<=75){
      gain=5;
      document.getElementById("raceMessage").textContent="Good gallop! 💗 +5";
    }else{
      gain=2;
      document.getElementById("raceMessage").textContent="Missed the sweet spot! +2";
    }

    player+=gain;
    ai+=6+Math.floor(Math.random()*2);

    document.getElementById("racePlayer").textContent=player;
    document.getElementById("raceAI").textContent=ai;

    round++;

    if(round>10){
      running=false;
      clearInterval(raceTimer);

      if(player>ai){
        passGame(150,3,
          `You won the race ${player} to ${ai}! 🏇💗`);
      }else{
        failGame(`The admirer won ${ai} to ${player}. Try your timing again!`);
      }
    }else{
      document.getElementById("raceRound").textContent=round;
    }
  };

  cleanupGame=()=>{
    running=false;
    clearInterval(raceTimer);
  };
}

/* =========================================================
   GAME 9 — HEARTBREAK CHAMBER
   ========================================================= */

function game9(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Search the room for four clues. Tap objects to investigate them.
      Find all four clues to unlock the door.
    </p>

    <div class="gameBox">
      <div class="sceneGrid" id="sceneGrid">
        <button class="sceneObject" data-clue="desk">📝 Desk</button>
        <button class="sceneObject" data-clue="drawer">🗄️ Drawer</button>
        <button class="sceneObject" data-clue="flower">🌻 Flower Pot</button>
        <button class="sceneObject" data-clue="photo">🖼️ Photo Frame</button>
        <button class="sceneObject" data-clue="clock">🕰️ Clock</button>
        <button class="sceneObject" data-clue="lamp">💡 Lamp</button>
      </div>

      <div class="clues" id="clues"></div>
      <div id="chamberMessage" class="gameStat muted"></div>
    </div>
  `;

  const found=new Set();
  const texts={
    desk:"Clue: the first number is 0.",
    drawer:"Clue: the second number is 6.",
    flower:"Clue: the third number is 0.",
    photo:"Clue: the final two numbers are 22.",
    clock:"Nothing useful here.",
    lamp:"The lamp flickers, but reveals nothing."
  };

  document.querySelectorAll(".sceneObject").forEach(btn=>{
    btn.onclick=()=>{
      const key=btn.dataset.clue;

      if(!found.has(key)){
        found.add(key);
        btn.style.background="#275c42";

        if(["desk","drawer","flower","photo"].includes(key)){
          const d=document.createElement("span");
          d.className="clue";
          d.textContent=texts[key];
          document.getElementById("clues").appendChild(d);
        }
      }

      if(found.size>=4){
        document.getElementById("chamberMessage").textContent=
          "All clues found! The door opens... 🚪💗";
        setTimeout(()=>{
          passGame(125,2,"You escaped the Heartbreak Chamber! 🔎💗");
        },700);
      }
    };
  });
}

/* =========================================================
   GAME 10 — BOXING
   ========================================================= */

function game10(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Defeat the opponent. Punch for steady damage, use Heavy Punch
      for more damage, and block or dodge when the opponent attacks.
    </p>

    <div class="gameBox">
      <div class="fighters">
        <div class="fighter">
          🥊
          <div class="health"><div id="playerHP" style="width:100%"></div></div>
          <small>You</small>
        </div>
        <div class="fighter">
          😈
          <div class="health enemyHealth"><div id="enemyHP" style="width:100%"></div></div>
          <small>Opponent</small>
        </div>
      </div>

      <div id="fightMessage" class="gameStat muted">Fight!</div>

      <div class="combatActions">
        <button class="combatBtn" onclick="boxAction('punch')">👊 Punch</button>
        <button class="combatBtn" onclick="boxAction('heavy')">💥 Heavy Punch</button>
        <button class="combatBtn" onclick="boxAction('block')">🛡️ Block</button>
        <button class="combatBtn" onclick="boxAction('dodge')">💨 Dodge</button>
      </div>
    </div>
  `;

  let playerHP=100;
  let enemyHP=80;
  let cooldown=false;
  let over=false;

  window.boxAction=function(action){
    if(over||cooldown)return;

    let damage=0;

    if(action==="punch")damage=10;
    if(action==="heavy"){
      if(cooldown)return;
      damage=18;
      cooldown=true;
      setTimeout(()=>cooldown=false,1000);
    }

    if(damage){
      enemyHP=Math.max(0,enemyHP-damage);
      document.getElementById("enemyHP").style.width=(enemyHP/80*100)+"%";
    }

    if(enemyHP<=0){
      over=true;
      passGame(140,3,"You won the Heartbreak Boxing Match! 🥊💗");
      return;
    }

    let enemyDamage=8+Math.floor(Math.random()*7);

    if(action==="block")enemyDamage=Math.floor(enemyDamage*.3);
    if(action==="dodge"){
      if(Math.random()<.75)enemyDamage=0;
      else enemyDamage=4;
    }

    playerHP=Math.max(0,playerHP-enemyDamage);
    document.getElementById("playerHP").style.width=playerHP+"%";

    const messages={
      punch:"Solid punch! 👊",
      heavy:"Heavy hit! 💥",
      block:"Good block! 🛡️",
      dodge:enemyDamage===0?"Perfect dodge! 💨":"The dodge was late!"
    };

    document.getElementById("fightMessage").textContent=
      messages[action]+` Enemy hit you for ${enemyDamage}.`;

    if(playerHP<=0){
      over=true;
      failGame("You were knocked out! Give the match another go.");
    }
  };

  cleanupGame=()=>{
    over=true;
    delete window.boxAction;
  };
}

/* =========================================================
   GAME 11 — PERFECT MATCH
   ========================================================= */

function game11(){
  const pairs=[
    ["🌸","Flower"],
    ["🐬","Dolphin"],
    ["🌻","Sunflower"],
    ["🍣","Sushi"],
    ["💗","Heart"]
  ];

  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Match each object with its correct target. Tap an object, then tap
      the matching target. Five correct matches wins.
    </p>

    <div class="gameBox">
      <div class="matchArea">
        <div class="matchColumn" id="matchItems"></div>
        <div class="matchColumn" id="matchTargets"></div>
      </div>
      <div id="matchMessage" class="gameStat muted"></div>
    </div>
  `;

  const items=document.getElementById("matchItems");
  const targets=document.getElementById("matchTargets");
  let selected=null;
  let found=0;

  shuffle(pairs).forEach((p,i)=>{
    const b=document.createElement("button");
    b.className="matchItem";
    b.dataset.key=p[1];
    b.textContent=p[0]+" "+p[1];
    b.onclick=()=>{
      selected=b;
      document.querySelectorAll(".matchItem").forEach(x=>x.classList.remove("selected"));
      b.classList.add("selected");
    };
    items.appendChild(b);
  });

  shuffle(pairs).forEach(p=>{
    const b=document.createElement("button");
    b.className="matchTarget";
    b.dataset.key=p[1];
    b.textContent="Match: "+p[1]+" ❔";
    b.onclick=()=>{
      if(!selected)return;

      if(selected.dataset.key===b.dataset.key){
        b.classList.add("filled");
        b.textContent="✓ "+p[0]+" "+p[1];
        selected.disabled=true;
        selected.style.opacity=".45";
        selected=null;
        found++;

        if(found===pairs.length){
          passGame(125,2,"Every object found its perfect match! 🧲💗");
        }
      }else{
        document.getElementById("matchMessage").textContent=
          "Not that one. Try another target!";
      }
    };
    targets.appendChild(b);
  });
}

/* =========================================================
   GAME 12 — WHO KNOWS LILIANA BEST
   ========================================================= */

function game12(){
  quizGame(
    lilianaQuestions,
    12,
    8,
    "How well do you know Liliana? You need 8 correct answers out of 12.",
    "Who Knows Liliana Best?",
    12
  );
}

/* =========================================================
   GAME 13 — REACTION GAUNTLET
   ========================================================= */

function game13(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Follow the command as quickly as you can. Some rounds tell you
      NOT to tap. You need 7 out of 10.
    </p>

    <div class="gameBox">
      <div class="gameStat">Round <span id="reactionRound">1</span>/10</div>
      <div id="reactionPad" class="reactionPad">
        <button id="reactionTarget" class="reactionTarget">GET READY</button>
      </div>
      <div id="reactionMessage" class="gameStat muted"></div>
    </div>
  `;

  let round=0;
  let score=0;
  let startTime=0;
  let command="";
  let timeout;

  function next(){
    round++;
    if(round>10){
      score>=7
        ?passGame(130,2,`You completed the Reaction Gauntlet with ${score}/10! ⚡`)
        :failGame(`You got ${score}/10. You need 7.`);
      return;
    }

    const tap=Math.random()>.25;
    command=tap?"TAP NOW!":"DON'T TAP!";

    const btn=document.getElementById("reactionTarget");
    btn.textContent=command;
    btn.className="reactionTarget"+(tap?"":" danger");

    startTime=performance.now();

    clearTimeout(timeout);
    timeout=setTimeout(()=>{
      if(tap){
        document.getElementById("reactionMessage").textContent="Too slow!";
      }else{
        score++;
        document.getElementById("reactionMessage").textContent="Perfect restraint! 😌";
      }
      setTimeout(next,450);
    },1200);
  }

  document.getElementById("reactionTarget").onclick=()=>{
    clearTimeout(timeout);

    const fast=performance.now()-startTime<800;

    if(command==="TAP NOW!"&&fast){
      score++;
      document.getElementById("reactionMessage").textContent="FAST! ⚡";
    }else if(command==="DON'T TAP!"){
      document.getElementById("reactionMessage").textContent="Oops! You tapped!";
    }else{
      document.getElementById("reactionMessage").textContent="Too slow!";
    }

    setTimeout(next,400);
  };

  next();

  cleanupGame=()=>clearTimeout(timeout);
}

/* =========================================================
   GAME 14 — HEART HUNT
   ========================================================= */

function game14(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Find 10 hidden hearts before time runs out. Some are easy to see,
      others are tucked around the scene.
    </p>

    <div class="gameBox">
      <div class="gameStat">
        Found <span id="huntFound">0</span>/10
        &nbsp; • &nbsp;
        <span id="huntTime">35</span>s
      </div>
      <div id="huntArea" class="huntArea"></div>
    </div>
  `;

  const area=document.getElementById("huntArea");
  let found=0;
  let time=35;
  let interval;

  for(let i=0;i<10;i++){
    const h=document.createElement("button");
    h.className="huntHeart";
    h.textContent=Math.random()>.15?"💗":"💖";
    h.style.left=(4+Math.random()*88)+"%";
    h.style.top=(5+Math.random()*86)+"%";
    h.style.animationDelay=(Math.random()*2)+"s";

    h.onclick=()=>{
      if(h.dataset.found)return;
      h.dataset.found="1";
      h.style.transform="scale(1.7)";
      h.style.opacity=".3";
      found++;
      document.getElementById("huntFound").textContent=found;

      if(found>=10){
        clearInterval(interval);
        passGame(130,2,"You found every hidden heart! 💗🔎");
      }
    };

    area.appendChild(h);
  }

  interval=setInterval(()=>{
    time--;
    document.getElementById("huntTime").textContent=time;

    if(time<=0){
      clearInterval(interval);
      if(found>=8){
        passGame(115,2,`You found ${found} hearts before time ran out! 💗`);
      }else{
        failGame(`You found ${found}/10 hearts. Try looking around more carefully!`);
      }
    }
  },1000);

  cleanupGame=()=>clearInterval(interval);
}

/* =========================================================
   GAME 15 — LOVE LOCK
   ========================================================= */

function game15(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Crack the Love Lock. The clue is:
      <strong>July 22 + 6 years of best friendship.</strong>
      Enter the six-digit code.
    </p>

    <div class="gameBox">
      <div id="lockDisplay" class="lockDisplay">_ _ _ _ _ _</div>
      <div id="keypad" class="keypad"></div>
      <div class="gameActions">
        <button class="backBtn" id="clearLock">Clear</button>
        <button class="bigBtn" id="enterLock">Unlock 🔐</button>
      </div>
      <div id="lockMessage" class="gameStat muted"></div>
    </div>
  `;

  let code="";

  for(let n=1;n<=9;n++)makeKey(n);
  makeKey(0);

  function makeKey(n){
    const b=document.createElement("button");
    b.className="key";
    b.textContent=n;
    b.onclick=()=>{
      if(code.length<6){
        code+=n;
        update();
      }
    };
    document.getElementById("keypad").appendChild(b);
  }

  function update(){
    document.getElementById("lockDisplay").textContent=
      code.padEnd(6,"_").split("").join(" ");
  }

  document.getElementById("clearLock").onclick=()=>{
    code="";
    update();
  };

  document.getElementById("enterLock").onclick=()=>{
    if(code==="060722"){
      passGame(130,3,"The Love Lock opened! You remembered the special code. 🔐💗");
    }else{
      document.getElementById("lockMessage").textContent=
        "That code didn't work. Remember the clue!";
    }
  };
}

/* =========================================================
   GAME 16 — CUPID SHOOTOUT
   ========================================================= */

function game16(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Tap the moving hearts before they disappear.
      Golden hearts are worth extra points. Reach 80 points.
    </p>

    <div class="gameBox">
      <div class="gameStat">
        Score: <span id="shootScore">0</span>/80
        &nbsp; • &nbsp;
        Arrows: <span id="arrows">15</span>
      </div>
      <div id="shootArea" class="shootArea"></div>
    </div>
  `;

  const area=document.getElementById("shootArea");
  let score=0;
  let arrows=15;
  let timer;

  function spawn(){
    if(arrows<=0)return;

    const t=document.createElement("button");
    t.className="shootTarget";
    const golden=Math.random()<.18;
    t.textContent=golden?"💛":"💗";
    t.dataset.value=golden?20:10;

    t.style.left=(5+Math.random()*85)+"%";
    t.style.top=(5+Math.random()*82)+"%";

    const lifetime=setTimeout(()=>{
      if(t.parentNode)t.remove();
    },1300);

    t.onclick=()=>{
      clearTimeout(lifetime);
      score+=Number(t.dataset.value);
      arrows--;
      document.getElementById("shootScore").textContent=score;
      document.getElementById("arrows").textContent=arrows;
      t.remove();

      if(score>=80){
        clearInterval(timer);
        passGame(135,2,"Cupid's arrows were on target! 🏹💗");
      }else if(arrows<=0){
        clearInterval(timer);
        failGame(`You scored ${score}/80. Try again!`);
      }
    };

    area.appendChild(t);
  }

  timer=setInterval(spawn,600);
  for(let i=0;i<3;i++)spawn();

  cleanupGame=()=>{
    clearInterval(timer);
  };
}

/* =========================================================
   GAME 17 — THE COUNTDOWN
   Six mini-games, no trivia.
   ========================================================= */

function game17(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Six tiny challenges. Complete at least four to beat
      The Countdown. No trivia, just quick little games.
    </p>

    <div class="gameBox">
      <div class="gameStat">
        Challenge <span id="countChallenge">1</span>/6
        &nbsp; • &nbsp;
        Wins <span id="countWins">0</span>
      </div>
      <div id="miniGame" class="miniGame"></div>
    </div>
  `;

  let challenge=0;
  let wins=0;
  let timer;

  function next(){
    challenge++;

    if(challenge>6){
      wins>=4
        ?passGame(135,2,`You beat ${wins}/6 Countdown challenges! ⏳💗`)
        :failGame(`You completed ${wins}/6. You need 4.`);
      return;
    }

    document.getElementById("countChallenge").textContent=challenge;

    const box=document.getElementById("miniGame");
    box.innerHTML="";

    if(challenge===1)stopBar(box);
    if(challenge===2)tapOrder(box);
    if(challenge===3)greenOrRed(box);
    if(challenge===4)smallest(box);
    if(challenge===5)holdMeter(box);
    if(challenge===6)miniMemory(box);
  }

  function result(ok){
    clearTimeout(timer);
    if(ok)wins++;
    document.getElementById("countWins").textContent=wins;
    setTimeout(next,450);
  }

  function stopBar(box){
    box.innerHTML=`
      <h3>Stop the marker in the green zone!</h3>
      <div class="stopBar">
        <div class="stopZone"></div>
        <div id="stopMarker" class="stopMarker"></div>
      </div>
      <button class="bigBtn" id="stopBtn">STOP</button>
    `;

    let pos=0;
    let dir=1;
    const loop=setInterval(()=>{
      pos+=dir*2.5;
      if(pos>=97){pos=97;dir=-1}
      if(pos<=0){pos=0;dir=1}
      document.getElementById("stopMarker").style.left=pos+"%";
    },30);

    document.getElementById("stopBtn").onclick=()=>{
      clearInterval(loop);
      result(pos>=42&&pos<=60);
    };

    timer=setTimeout(()=>{
      clearInterval(loop);
      result(false);
    },3000);
  }

  function tapOrder(box){
    box.innerHTML=`
      <h3>Tap 1, 2, 3 in order!</h3>
      <div class="circleRow">
        <button class="countCircle" data-n="1">1</button>
        <button class="countCircle" data-n="2">2</button>
        <button class="countCircle" data-n="3">3</button>
      </div>
    `;

    let nextNum=1;
    box.querySelectorAll("button").forEach(b=>{
      b.onclick=()=>{
        if(Number(b.dataset.n)===nextNum){
          b.style.background="#377451";
          nextNum++;
          if(nextNum===4)result(true);
        }else result(false);
      };
    });

    timer=setTimeout(()=>result(false),3500);
  }

  function greenOrRed(box){
    const good=Math.random()>.45;
    box.innerHTML=`
      <h3>${good?"TAP THE HEART":"DON'T TAP!"}</h3>
      <button class="countCircle" id="greenTap">${good?"💗":"🔴"}</button>
    `;

    document.getElementById("greenTap").onclick=()=>{
      result(good);
    };

    timer=setTimeout(()=>result(!good),1800);
  }

  function smallest(box){
    const nums=shuffle([3,8,1,6]);
    box.innerHTML=`
      <h3>Tap the smallest number</h3>
      <div class="circleRow">
        ${nums.map(n=>`<button class="countCircle" data-n="${n}">${n}</button>`).join("")}
      </div>
    `;

    box.querySelectorAll("button").forEach(b=>{
      b.onclick=()=>result(Number(b.dataset.n)===1);
    });

    timer=setTimeout(()=>result(false),3000);
  }

  function holdMeter(box){
    box.innerHTML=`
      <h3>Hold the button, then release in the green zone!</h3>
      <div class="stopBar">
        <div class="stopZone"></div>
        <div id="holdMarker" class="stopMarker"></div>
      </div>
      <button class="bigBtn" id="holdBtn">HOLD</button>
    `;

    let held=false;
    let pos=0;
    let dir=1;

    const loop=setInterval(()=>{
      if(held){
        pos+=dir*2.5;
        if(pos>=97){pos=97;dir=-1}
        if(pos<=0){pos=0;dir=1}
        document.getElementById("holdMarker").style.left=pos+"%";
      }
    },30);

    const b=document.getElementById("holdBtn");

    const release=()=>{
      if(!held)return;
      held=false;
      clearInterval(loop);
      result(pos>=42&&pos<=60);
    };

    b.onpointerdown=()=>{
      held=true;
      b.textContent="RELEASE";
    };
    b.onpointerup=release;
    b.onpointercancel=release;

    timer=setTimeout(()=>{
      clearInterval(loop);
      result(false);
    },3500);
  }

  function miniMemory(box){
    const seq=[1,3,2];
    box.innerHTML=`
      <h3>Remember this: 1 → 3 → 2</h3>
      <button class="bigBtn" id="readyMini">I'M READY</button>
    `;

    document.getElementById("readyMini").onclick=()=>{
      box.innerHTML=`
        <h3>Tap the sequence!</h3>
        <div class="circleRow">
          <button class="countCircle" data-n="1">1</button>
          <button class="countCircle" data-n="2">2</button>
          <button class="countCircle" data-n="3">3</button>
        </div>
      `;

      let pos=0;

      box.querySelectorAll("button").forEach(b=>{
        b.onclick=()=>{
          if(Number(b.dataset.n)===seq[pos]){
            pos++;
            if(pos===seq.length)result(true);
          }else result(false);
        };
      });

      timer=setTimeout(()=>result(false),4000);
    };
  }

  next();

  cleanupGame=()=>clearTimeout(timer);
}

/* =========================================================
   GAME 18 — ULTIMATE GAMBLE
   ========================================================= */

function game18(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Start with 100. Choose your risks carefully.
      Reach 300 or cash out with more than 100 to win.
    </p>

    <div class="gameBox">
      <div class="pot">$<span id="gamblePot">100</span></div>
      <div class="gameStat">Turns: <span id="gambleTurns">0</span></div>

      <div class="gambleActions">
        <button class="bigBtn" id="safeBtn">Safe Gamble<br>50/50</button>
        <button class="bigBtn" id="riskBtn">Big Risk<br>25% chance</button>
        <button class="bigBtn" id="cashBtn">Cash Out 💰</button>
        <button class="backBtn" id="resetPot">Reset Pot</button>
      </div>

      <div id="gambleMessage" class="gameStat muted"></div>
    </div>
  `;

  let pot=100;
  let turns=0;
  let done=false;

  function update(){
    document.getElementById("gamblePot").textContent=pot;
    document.getElementById("gambleTurns").textContent=turns;
  }

  function win(){
    done=true;
    passGame(140,3,`You finished the gamble with $${pot}! 🎲💗`);
  }

  document.getElementById("safeBtn").onclick=()=>{
    if(done)return;
    turns++;

    if(Math.random()<.52){
      pot*=2;
      document.getElementById("gambleMessage").textContent="Safe gamble WON! 🎉";
    }else{
      pot=Math.floor(pot/2);
      document.getElementById("gambleMessage").textContent="You lost half.";
    }

    update();
    if(pot>=300)win();
    else if(pot<=10){
      document.getElementById("gambleMessage").textContent=
        "The pot is getting low. Reset or cash out!";
    }
  };

  document.getElementById("riskBtn").onclick=()=>{
    if(done)return;
    turns++;

    if(Math.random()<.25){
      pot*=4;
      document.getElementById("gambleMessage").textContent="BIG WIN! 🎰";
    }else{
      pot=0;
      document.getElementById("gambleMessage").textContent="The big risk failed.";
    }

    update();

    if(pot>=300)win();
    else if(pot===0){
      setTimeout(()=>failGame("The big gamble didn't pay off!"),500);
    }
  };

  document.getElementById("cashBtn").onclick=()=>{
    if(done)return;

    if(pot>100){
      win();
    }else{
      document.getElementById("gambleMessage").textContent=
        "You need more than $100 to cash out and pass.";
    }
  };

  document.getElementById("resetPot").onclick=()=>{
    pot=100;
    turns=0;
    update();
    document.getElementById("gambleMessage").textContent="Back to $100.";
  };
}

/* =========================================================
   GAME 19 — ADMIRER'S LAST STAND
   ========================================================= */

function game19(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Defeat the admirer through three phases. Guard reduces incoming
      damage. Special attacks are powerful but have a cooldown.
    </p>

    <div class="gameBox">
      <div id="boss" class="boss">👑</div>
      <div class="bossPhase" id="bossPhase">PHASE 1</div>

      <div class="health" style="width:100%;margin:15px auto">
        <div id="bossHP" style="width:100%;background:#d55b79"></div>
      </div>

      <div class="gameStat">
        Boss HP: <span id="bossValue">120</span>
        &nbsp; • &nbsp;
        Your HP: <span id="bossPlayerValue">100</span>
      </div>

      <div id="bossMessage" class="gameStat muted">The admirer approaches...</div>

      <div class="bossActions">
        <button class="combatBtn" onclick="bossAction('attack')">⚔️ Attack</button>
        <button class="combatBtn" onclick="bossAction('guard')">🛡️ Guard</button>
        <button class="combatBtn" onclick="bossAction('special')">✨ Special</button>
      </div>
    </div>
  `;

  let hp=100;
  let bossHP=120;
  let specialReady=true;
  let done=false;

  window.bossAction=function(action){
    if(done)return;

    let damage=0;

    if(action==="attack")damage=12+Math.floor(Math.random()*5);

    if(action==="special"){
      if(!specialReady){
        document.getElementById("bossMessage").textContent=
          "Special is still charging!";
        return;
      }
      damage=28;
      specialReady=false;
      setTimeout(()=>specialReady=true,1800);
    }

    if(action==="guard")damage=0;

    bossHP=Math.max(0,bossHP-damage);

    document.getElementById("bossHP").style.width=(bossHP/120*100)+"%";
    document.getElementById("bossValue").textContent=bossHP;

    if(bossHP<=80&&bossHP>40){
      document.getElementById("bossPhase").textContent="PHASE 2";
      document.getElementById("boss").textContent="😤";
    }

    if(bossHP<=40){
      document.getElementById("bossPhase").textContent="FINAL PHASE";
      document.getElementById("boss").textContent="🔥";
    }

    if(bossHP<=0){
      done=true;
      passGame(155,3,"You defeated the admirer in the Last Stand! 👑💗");
      return;
    }

    let incoming=10+Math.floor(Math.random()*9);

    if(action==="guard")incoming=Math.floor(incoming*.3);
    if(action==="special")incoming+=3;

    hp=Math.max(0,hp-incoming);

    document.getElementById("bossPlayerValue").textContent=hp;
    document.getElementById("bossMessage").textContent=
      `You dealt ${damage} damage. The boss hit back for ${incoming}.`;

    if(hp<=0){
      done=true;
      failGame("The admirer got the better of you this time!");
    }
  };

  cleanupGame=()=>{
    done=true;
    delete window.bossAction;
  };
}

/* =========================================================
   GAME 20 — WORD FIND
   ========================================================= */

const wordBank=[
 "LILIANA","LULU","FRIENDS","PINK","DOLPHIN",
 "SUNFLOWER","ROSE","SUSHI","POETRY","MUSIC",
 "PSYCHOLOGY","LEO","JULY","LOVE","FAMILY",
 "HEART","DREAM","AAYLA","ARLO","OCEAN",
 "FOREVER","THREE","SIXYEARS","CHARM","EMPATHY"
];

function game20(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Find all 25 hidden words. Words can go horizontally, vertically,
      diagonally and backwards. Drag across the letters on the grid.
    </p>

    <div class="gameBox wordFindWrap">
      <div id="wordList" class="wordList"></div>
      <div id="wordGrid" class="wordGrid"></div>
      <div id="wordMessage" class="gameStat muted">
        25 words remaining
      </div>
    </div>
  `;

  const size=14;
  const grid=Array.from({length:size},()=>Array(size).fill(""));

  const dirs=[
    [1,0],[-1,0],[0,1],[0,-1],
    [1,1],[-1,-1],[1,-1],[-1,1]
  ];

  const placements=[];

  function canPlace(word,r,c,dr,dc){
    for(let i=0;i<word.length;i++){
      const rr=r+dr*i;
      const cc=c+dc*i;
      if(rr<0||rr>=size||cc<0||cc>=size)return false;
      if(grid[rr][cc]&&grid[rr][cc]!==word[i])return false;
    }
    return true;
  }

  function place(word){
    for(let attempt=0;attempt<700;attempt++){
      const [dr,dc]=dirs[Math.floor(Math.random()*dirs.length)];
      const r=Math.floor(Math.random()*size);
      const c=Math.floor(Math.random()*size);

      if(canPlace(word,r,c,dr,dc)){
        const cells=[];
        for(let i=0;i<word.length;i++){
          const rr=r+dr*i;
          const cc=c+dc*i;
          grid[rr][cc]=word[i];
          cells.push(rr+"-"+cc);
        }
        placements.push({word,cells});
        return true;
      }
    }
    return false;
  }

  /* Place longer words first for a reliable puzzle. */
  [...wordBank].sort((a,b)=>b.length-a.length).forEach(place);

  const letters="ABCDEFGHIJKLMNOPQRSTUVWXYZ";

  for(let r=0;r<size;r++){
    for(let c=0;c<size;c++){
      if(!grid[r][c])
        grid[r][c]=letters[Math.floor(Math.random()*letters.length)];
    }
  }

  const wordList=document.getElementById("wordList");
  wordBank.forEach(word=>{
    const tag=document.createElement("span");
    tag.className="wordTag";
    tag.id="word-"+word;
    tag.textContent=word;
    wordList.appendChild(tag);
  });

  const gridEl=document.getElementById("wordGrid");

  for(let r=0;r<size;r++){
    for(let c=0;c<size;c++){
      const b=document.createElement("button");
      b.className="letter";
      b.textContent=grid[r][c];
      b.dataset.r=r;
      b.dataset.c=c;
      gridEl.appendChild(b);
    }
  }

  let start=null;
  let selecting=false;
  let found=new Set();

  function getCell(e){
    const el=document.elementFromPoint(e.clientX,e.clientY);
    if(!el||!el.classList.contains("letter"))return null;
    return el;
  }

  function highlightPath(a,b){
    const r1=Number(a.dataset.r);
    const c1=Number(a.dataset.c);
    const r2=Number(b.dataset.r);
    const c2=Number(b.dataset.c);

    const dr=Math.sign(r2-r1);
    const dc=Math.sign(c2-c1);

    const distance=Math.max(Math.abs(r2-r1),Math.abs(c2-c1))+1;

    if(
      !(r1===r2||c1===c2||Math.abs(r2-r1)===Math.abs(c2-c1))
    )return [];

    const cells=[];

    for(let i=0;i<distance;i++){
      const r=r1+dr*i;
      const c=c1+dc*i;
      const cell=gridEl.querySelector(
        `.letter[data-r="${r}"][data-c="${c}"]`
      );
      if(cell)cells.push(cell);
    }

    return cells;
  }

  function finish(end){
    if(!start||!end)return;

    const cells=highlightPath(start,end);
    const word=cells.map(x=>x.textContent).join("");

    const reverse=word.split("").reverse().join("");

    let matched=null;

    placements.forEach(p=>{
      if(
        !found.has(p.word)&&
        (p.word===word||p.word===reverse)
      ){
        matched=p.word;
      }
    });

    document.querySelectorAll(".letter.selecting")
      .forEach(x=>x.classList.remove("selecting"));

    if(matched){
      found.add(matched);
      cells.forEach(x=>x.classList.add("found"));

      document.getElementById("word-"+matched)
        .classList.add("found");

      document.getElementById("wordMessage").textContent=
        `${found.size}/25 words found`;

      if(found.size===placements.length){
        passGame(170,4,"You found all 25 hidden words! 🔎💗");
      }
    }

    start=null;
    selecting=false;
  }

  gridEl.addEventListener("pointerdown",e=>{
    const cell=getCell(e);
    if(!cell)return;

    selecting=true;
    start=cell;
    gridEl.setPointerCapture(e.pointerId);
    cell.classList.add("selecting");
  });

  gridEl.addEventListener("pointermove",e=>{
    if(!selecting||!start)return;

    const cell=getCell(e);
    if(!cell)return;

    document.querySelectorAll(".letter.selecting")
      .forEach(x=>x.classList.remove("selecting"));

    highlightPath(start,cell)
      .forEach(x=>x.classList.add("selecting"));
  });

  gridEl.addEventListener("pointerup",e=>{
    if(!selecting)return;
    finish(getCell(e));
  });

  gridEl.addEventListener("pointercancel",()=>{
    selecting=false;
    start=null;
    document.querySelectorAll(".letter.selecting")
      .forEach(x=>x.classList.remove("selecting"));
  });
}

/* =========================================================
   GAME 21 — DRAW A SUNFLOWER
   ========================================================= */

function game21(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Draw a sunflower 🌻. Add a stem, leaves, petals and a centre.
      Make it your own, then press Finish Flower.
    </p>

    <div class="gameBox">
      <canvas id="drawCanvas" width="650" height="420"></canvas>

      <div class="drawTools">
        <button data-col="#5d3b22" title="Brown"></button>
        <button data-col="#4b8a4b" title="Green"></button>
        <button data-col="#e0aa35" title="Yellow"></button>
        <button data-col="#d64f7d" title="Pink"></button>
        <button data-col="#9d3b52" title="Red"></button>
        <button data-col="#24121b" title="Dark"></button>
      </div>

      <div class="gameActions">
        <button class="backBtn" id="undoDraw">Undo</button>
        <button class="backBtn" id="clearDraw">Clear</button>
        <button class="bigBtn" id="finishDraw">Finish Flower 🌻</button>
      </div>

      <div id="drawMessage" class="gameStat muted"></div>
    </div>
  `;

  const canvas=document.getElementById("drawCanvas");
  const ctx=canvas.getContext("2d");

  let drawing=false;
  let colour="#d64f7d";
  let size=7;
  let strokes=[];
  let current=[];

  ctx.lineCap="round";
  ctx.lineJoin="round";

  function position(e){
    const rect=canvas.getBoundingClientRect();
    return {
      x:(e.clientX-rect.left)*(canvas.width/rect.width),
      y:(e.clientY-rect.top)*(canvas.height/rect.height)
    };
  }

  canvas.addEventListener("pointerdown",e=>{
    drawing=true;
    current=[];
    const p=position(e);
    current.push(p);
    ctx.beginPath();
    ctx.moveTo(p.x,p.y);
  });

  canvas.addEventListener("pointermove",e=>{
    if(!drawing)return;
    const p=position(e);
    current.push(p);

    ctx.strokeStyle=colour;
    ctx.lineWidth=size;
    ctx.lineTo(p.x,p.y);
    ctx.stroke();
  });

  function endStroke(){
    if(!drawing)return;
    drawing=false;
    if(current.length)strokes.push({colour,size,points:current});
  }

  canvas.addEventListener("pointerup",endStroke);
  canvas.addEventListener("pointercancel",endStroke);

  document.querySelectorAll(".drawTools button").forEach(b=>{
    b.style.background=b.dataset.col;
    b.onclick=()=>{
      colour=b.dataset.col;
      document.querySelectorAll(".drawTools button")
        .forEach(x=>x.classList.remove("active"));
      b.classList.add("active");
    };
  });

  function redraw(){
    ctx.clearRect(0,0,canvas.width,canvas.height);

    strokes.forEach(s=>{
      if(!s.points.length)return;

      ctx.strokeStyle=s.colour;
      ctx.lineWidth=s.size;
      ctx.beginPath();
      ctx.moveTo(s.points[0].x,s.points[0].y);

      s.points.slice(1).forEach(p=>ctx.lineTo(p.x,p.y));

      ctx.stroke();
    });
  }

  document.getElementById("undoDraw").onclick=()=>{
    strokes.pop();
    redraw();
  };

  document.getElementById("clearDraw").onclick=()=>{
    strokes=[];
    redraw();
  };

  document.getElementById("finishDraw").onclick=()=>{
    if(strokes.length<5){
      document.getElementById("drawMessage").textContent=
        "Add a few more strokes first 🌻";
      return;
    }

    passGame(140,3,
      `Beautiful! Your sunflower is now part of the Lulu Express journey. 🌻💗`);
  };
}

/* =========================================================
   DERBY 100 QUESTIONS
   ========================================================= */

const derbyQuestions=[
["What is the capital of Canada?",["Ottawa","Toronto","Vancouver","Montreal"],0],
["What is the largest mammal?",["Blue whale","Elephant","Giraffe","Orca"],0],
["How many months are in a year?",["12","10","11","13"],0],
["What is the currency of the United Kingdom?",["Pound sterling","Euro","Dollar","Franc"],0],
["Which planet is closest to the Sun?",["Mercury","Venus","Earth","Mars"],0],
["How many chess pieces does each player start with?",["16","12","18","20"],0],
["Who wrote the Harry Potter books?",["J.K. Rowling","Suzanne Collins","C.S. Lewis","Roald Dahl"],0],
["Which is the largest continent?",["Asia","Africa","Europe","North America"],0],
["Which instrument usually has 88 keys?",["Piano","Violin","Trumpet","Flute"],0],
["What is the chemical symbol for oxygen?",["O","Ox","O2","Og"],0],
["What is the square root of 81?",["9","8","7","6"],0],
["In which year did humans first land on the Moon?",["1969","1959","1975","1981"],0],
["Where is the Great Pyramid of Giza?",["Egypt","Greece","Mexico","Jordan"],0],
["What language is primarily spoken in Brazil?",["Portuguese","Spanish","French","Italian"],0],
["What is the world's largest desert?",["Antarctica","Sahara","Gobi","Arabian"],0],
["What is the highest score in a single frame of ten-pin bowling?",["30","20","25","50"],0],
["Which vitamin is commonly produced through sunlight exposure?",["Vitamin D","Vitamin C","Vitamin A","Vitamin B12"],0],
["About how many bones does an adult human have?",["206","186","216","306"],0],
["On which continent is most of the Amazon rainforest?",["South America","Africa","Asia","Europe"],0],
["Where is Big Ben?",["London","Paris","Rome","Dublin"],0],
["Which ocean is the largest?",["Pacific","Atlantic","Indian","Arctic"],0],
["How many moons does Mars have?",["2","1","3","4"],0],
["Which planet is the hottest on average?",["Venus","Mercury","Mars","Jupiter"],0],
["Approximately how fast does light travel in a vacuum?",["300,000 km/s","30,000 km/s","3,000 km/s","3 million km/s"],0],
["Who wrote Romeo and Juliet?",["William Shakespeare","Charles Dickens","Oscar Wilde","Mark Twain"],0],
["Where do penguins naturally live?",["Southern Hemisphere","Northern Europe","Central Asia","Greenland only"],0],
["What is the currency of India?",["Rupee","Yen","Peso","Dinar"],0],
["Where is the Taj Mahal?",["India","Pakistan","Nepal","Bangladesh"],0],
["Who was the Greek god of the sea?",["Poseidon","Apollo","Ares","Hermes"],0],
["What does Roman numeral X mean?",["10","5","50","100"],0],
["How many rings are on the Olympic symbol?",["5","4","6","7"],0],
["How many suits are in a standard deck of cards?",["4","3","5","6"],0],
["How many cards are in a standard deck?",["52","48","54","50"],0],
["How many sides does a square have?",["4","3","5","6"],0],
["The Nile is primarily associated with which continent?",["Africa","Asia","Europe","South America"],0],
["The Alps are mainly found in which region?",["Europe","Africa","Asia","Oceania"],0],
["At what temperature does water freeze in Celsius?",["0°C","10°C","32°C","-10°C"],0],
["How many metres are in a kilometre?",["1,000","100","10,000","500"],0],
["How many seconds are in a minute?",["60","100","30","90"],0],
["How many hours are in a day?",["24","12","36","48"],0],
["How many days are in a normal week?",["7","5","6","8"],0],
["How many days are in a normal non-leap year?",["365","360","364","366"],0],
["Which is the farthest planet from the Sun among the eight planets?",["Neptune","Uranus","Saturn","Jupiter"],0],
["What is Pluto classified as?",["Dwarf planet","Gas giant","Moon","Comet"],0],
["What shape is DNA commonly described as?",["Double helix","Single ring","Triangle","Cube"],0],
["What process allows plants to use sunlight to make food?",["Photosynthesis","Respiration","Fermentation","Digestion"],0],
["Which cells carry oxygen around the body?",["Red blood cells","Platelets","Skin cells","Bone cells"],0],
["What is the largest organ of the human body?",["Skin","Liver","Heart","Lung"],0],
["Which part of the eye controls how much light enters?",["Iris","Retina","Lens","Cornea"],0],
["Which part of the brain is the largest region?",["Cerebrum","Cerebellum","Medulla","Brainstem"],0],
["What is the chemical symbol for iron?",["Fe","Ir","In","I"],0],
["What is the chemical symbol for sodium?",["Na","So","Sd","S"],0],
["What is the chemical symbol for potassium?",["K","P","Po","Pt"],0],
["What is the chemical symbol for silver?",["Ag","Si","Sl","Sv"],0],
["What is the chemical symbol for copper?",["Cu","Co","Cp","Cr"],0],
["What gas is represented by CO₂?",["Carbon dioxide","Carbon monoxide","Oxygen","Methane"],0],
["What pH is considered neutral?",["7","1","5","14"],0],
["What force pulls objects toward Earth?",["Gravity","Friction","Magnetism","Pressure"],0],
["What is the SI unit of energy?",["Joule","Watt","Newton","Volt"],0],
["What is the SI unit of electric current?",["Ampere","Volt","Ohm","Watt"],0],
["Sound level is commonly measured in what?",["Decibels","Metres","Watts","Litres"],0],
["What instrument detects and records earthquakes?",["Seismograph","Barometer","Thermometer","Hygrometer"],0],
["Molten rock beneath Earth's surface is called what?",["Magma","Lava","Ash","Granite"],0],
["What are clouds mostly made of?",["Tiny water droplets and ice","Smoke","Sand","Salt"],0],
["How many traditional colours are commonly listed in a rainbow?",["7","5","6","8"],0],
["What shape symmetry is associated with most snowflakes?",["Six-fold","Four-fold","Three-fold","Eight-fold"],0],
["How do honeybees famously communicate the location of food?",["Dance movements","Colour changes","Whistling","Footprints"],0],
["Where are butterflies' taste receptors famously found?",["Feet","Wings","Eyes","Antennae only"],0],
["How many hearts does an octopus have?",["3","2","4","1"],0],
["How many neck vertebrae does a giraffe usually have?",["7","5","10","12"],0],
["Which animal is the fastest land animal?",["Cheetah","Horse","Leopard","Ostrich"],0],
["What is the largest living bird?",["Ostrich","Emu","Eagle","Albatross"],0],
["Which animal is known for carrying young in a pouch?",["Kangaroo","Elephant","Zebra","Tiger"],0],
["Which bird is strongly associated with New Zealand?",["Kiwi","Flamingo","Peacock","Pelican"],0],
["Koalas are native to which country?",["Australia","Canada","India","Brazil"],0],
["Mount Kilimanjaro is in which country?",["Tanzania","Kenya","Ethiopia","Uganda"],0],
["The Gobi Desert is mainly in which part of the world?",["Asia","Africa","Europe","South America"],0],
["The Amazon River is in which continent?",["South America","Africa","Asia","Europe"],0],
["The Mediterranean Sea lies between Europe and which other regions?",["Africa and Asia","Australia and Asia","North America and Asia","South America and Africa"],0],
["The Panama Canal connects which two oceans?",["Atlantic and Pacific","Pacific and Indian","Atlantic and Arctic","Indian and Arctic"],0],
["The Suez Canal connects the Mediterranean Sea with which sea?",["Red Sea","Black Sea","Caribbean Sea","North Sea"],0],
["The Equator represents which latitude?",["0°","23.5°N","90°","66.5°S"],0],
["The Prime Meridian passes through which longitude?",["0°","90°","180°","45°"],0],
["Which continent is the coldest?",["Antarctica","Europe","Asia","North America"],0],
["Which is the smallest continent by land area?",["Australia","Europe","Antarctica","South America"],0],
["Which country is the world's largest by land area?",["Russia","Canada","China","United States"],0],
["Which country contains Vatican City?",["Italy","France","Spain","Austria"],0],
["Wimbledon is associated with which sport?",["Tennis","Golf","Cricket","Rugby"],0],
["The Tour de France is primarily what type of event?",["Cycling race","Horse race","Car race","Running race"],0],
["The FIFA World Cup is associated with which sport?",["Football","Tennis","Basketball","Rugby"],0],
["The Super Bowl is associated with which sport?",["American football","Baseball","Ice hockey","Basketball"],0],
["How many players are on a standard football team on the field?",["11","9","10","12"],0],
["How many points is a touchdown worth before any extra attempt?",["6","3","7","5"],0],
["How many players are on a basketball team on court at one time?",["5","6","7","4"],0],
["How many points is a free throw worth in basketball?",["1","2","3","4"],0],
["What colour is traditionally associated with the centre of a dartboard?",["Red","Blue","Green","Yellow"],0],
["How many squares are on a chessboard?",["64","72","81","48"],0],
["What piece moves in an L-shape in chess?",["Knight","Bishop","Rook","Queen"],0],
["What is the only even prime number?",["2","4","6","8"],0],
["How many degrees are in a full circle?",["360","180","90","720"],0],
["What is 12 × 12?",["144","124","132","154"],0],
["What is the opposite of north?",["South","East","West","Up"],0],
["What colour do you get by mixing blue and yellow?",["Green","Purple","Orange","Pink"],0],
["Which sense uses the ears?",["Hearing","Sight","Taste","Smell"],0],
["Which animal is known for producing silk?",["Silkworm","Bee","Spider crab","Butterfly"],0],
["Which metal is liquid at room temperature?",["Mercury","Iron","Copper","Gold"],0],
["What is the hardest natural mineral?",["Diamond","Quartz","Granite","Iron"],0],
["Which country is famous for the city of Kyoto?",["Japan","China","Thailand","Vietnam"],0]
];

/* =========================================================
   GAME 22 — LULU DERBY
   ========================================================= */

function game22(){
  const root=document.getElementById("gameContent");

  root.innerHTML=`
    <p class="instruction">
      Choose your horse. Then answer 100 random trivia questions.
      Correct answers push your horse forward. The questions are mixed
      throughout the race.
    </p>

    <div class="gameBox" id="derbyBox">
      <div id="derbyChoose">
        <h3 style="text-align:center">Choose your horse 🏇</h3>
        <div class="derbyHorses">
          <button class="derbyHorse" data-horse="0">🌸<br>Lulu</button>
          <button class="derbyHorse" data-horse="1">💗<br>Rosie</button>
          <button class="derbyHorse" data-horse="2">⭐<br>Starlight</button>
          <button class="derbyHorse" data-horse="3">🌻<br>Sunny</button>
        </div>
      </div>
    </div>
  `;

  let selected=-1;
  let questions=[];
  let index=0;
  let positions=[0,0,0,0];
  let answered=false;

  document.querySelectorAll(".derbyHorse").forEach(b=>{
    b.onclick=()=>{
      selected=Number(b.dataset.horse);
      document.querySelectorAll(".derbyHorse")
        .forEach(x=>x.classList.remove("selected"));
      b.classList.add("selected");

      setTimeout(start,350);
    };
  });

  function start(){
    questions=shuffle(derbyQuestions).slice(0,100);

    document.getElementById("derbyBox").innerHTML=`
      <div class="triviaCounter">
        Derby Question <span id="derbyQuestion">1</span>/100
      </div>

      <div class="derbyTrack">
        <div class="derbyLane"><div class="derbyRunner" id="derby0">🌸</div></div>
        <div class="derbyLane"><div class="derbyRunner" id="derby1">💗</div></div>
        <div class="derbyLane"><div class="derbyRunner" id="derby2">⭐</div></div>
        <div class="derbyLane"><div class="derbyRunner" id="derby3">🌻</div></div>
      </div>

      <div id="derbyQuestionText" class="quizQuestion"></div>
      <div id="derbyAnswers" class="answerGrid"></div>
      <div id="derbyMessage" class="gameStat muted"></div>
    `;

    loadDerby();
  }

  function loadDerby(){
    answered=false;

    const q=questions[index];
    const answers=randomisedQuestion(q);

    document.getElementById("derbyQuestion").textContent=index+1;
    document.getElementById("derbyQuestionText").textContent=q[0];

    const area=document.getElementById("derbyAnswers");
    area.innerHTML="";

    answers.forEach(a=>{
      const b=document.createElement("button");
      b.className="answer";
      b.textContent=a.text;
      b.onclick=()=>answerDerby(a.correct,b);
      area.appendChild(b);
    });
  }

  function answerDerby(correct,button){
    if(answered)return;
    answered=true;

    [...document.querySelectorAll("#derbyAnswers button")]
      .forEach(b=>b.disabled=true);

    if(correct){
      button.classList.add("correct");

      /* Selected horse receives a generous boost. */
      positions[selected]+=2+Math.floor(Math.random()*3);

      /* Occasional bonus sprint. */
      if(Math.random()<.15)positions[selected]+=2;

      document.getElementById("derbyMessage").textContent=
        "Correct! Your horse charges forward! 🏇💨";
    }else{
      button.classList.add("wrong");

      /* A rival advances slightly. */
      const rivals=[0,1,2,3].filter(x=>x!==selected);
      const rival=rivals[Math.floor(Math.random()*rivals.length)];
      positions[rival]+=1;

      document.getElementById("derbyMessage").textContent=
        "Wrong! One of the rivals moves ahead.";
    }

    updateDerby();

    index++;

    if(index>=100){
      setTimeout(finishDerby,450);
    }else{
      setTimeout(loadDerby,300);
    }
  }

  function updateDerby(){
    positions.forEach((p,i)=>{
      const lane=document.querySelector(".derbyLane").clientWidth;
      const px=Math.min(lane-38,p/lane*lane*0.9);
      document.getElementById("derby"+i).style.left=
        Math.min(90,p*0.9)+"%";
    });
  }

  function finishDerby(){
    /* Make selected horse slightly favoured if the race is very close. */
    const winner=positions.indexOf(Math.max(...positions));

    if(winner===selected){
      passGame(
        200,
        5,
        `YOU WON THE LULU DERBY after all 100 questions! 🏆🏇`
      );
    }else{
      failGame(
        "The derby has finished, but your horse didn't win this time."
      );
    }
  }
}

/* =========================================================
   GAME 23 — FINAL CHALLENGE
   50 UNIQUE LILIANA QUESTIONS
   ========================================================= */

const finalQuestions=[
 ["Which colour would Liliana most likely choose for a birthday theme?",["Baby pink","Neon orange","Bright green","Navy blue"],0],
 ["Which number has special significance for Liliana?",["3","9","14","20"],0],
 ["Which food is one of Liliana's favourites?",["Sushi","Cereal","Steak","Pancakes"],0],
 ["Which sea animal does Liliana like?",["Dolphin","Seal","Shark","Walrus"],0],
 ["Which flower is associated with Liliana?",["Sunflower","Carnation","Orchid","Iris"],0],
 ["Which second flower does she like?",["Rose","Peony","Violet","Daffodil"],0],
 ["What month is Liliana's birthday in?",["July","January","October","March"],0],
 ["What day of the month is her birthday?",["22","12","27","7"],0],
 ["What is the colour of her eyes?",["Green","Blue","Grey","Brown"],0],
 ["Which zodiac sign is Liliana?",["Leo","Aries","Libra","Pisces"],0],
 ["Which fear belongs to Liliana?",["Drowning","Thunder","Knives","Dark rooms"],0],
 ["Which film is her favourite?",["Me Before You","Barbie","Mamma Mia!","The Holiday"],0],
 ["What kind of music does Liliana enjoy?",["Sad songs","Only metal","Only classical","Only country"],0],
 ["Which form of writing does she like?",["Poetry","Essays only","Comics only","News reports"],0],
 ["Which card game does she enjoy?",["Poker","Solitaire","Bridge","Snap"],0],
 ["What type of games does she enjoy?",["Gambling games","Only puzzles","Only platform games","Only racing games"],0],
 ["What subject did Liliana study at university?",["Psychology","Medicine","Law","Art"],0],
 ["How many nieces does she have?",["1","2","4","5"],0],
 ["How many nephews does she have?",["4","1","3","6"],0],
 ["How many siblings does she have?",["5","2","4","7"],0],
 ["How many piercings does she have?",["4","1","2","6"],0],
 ["Which dog is Liliana's?",["Aayla","Lola","Mochi","Nala"],0],
 ["What is the name of her other dog?",["Arlo","Archi","Milo","Teddy"],0],
 ["How long have Bree and Liliana been best friends?",["6 years","2 years","4 years","10 years"],0],
 ["Which personality trait fits Liliana?",["Sweet","Mean","Distant","Careless"],0],
 ["Which other personality trait fits her?",["Caring","Selfish","Cold","Impatient"],0],
 ["Which word best describes her charm?",["Charismatic","Hostile","Shy","Unkind"],0],
 ["Which quality is strongly associated with her?",["Empathy","Apathy","Stubbornness","Cruelty"],0],
 ["What does Liliana want to be someday?",["A mum","A pilot","A lawyer","A dancer"],0],
 ["What kind of child does she dream of having?",["A baby girl","Twin boys","A baby boy","Three boys"],0],
 ["What does Liliana want to see someday?",["The ocean","The Sahara","The Alps","The Arctic Circle"],0],
 ["Which pairing contains two of her favourite things?",["Dolphins and sushi","Horses and curry","Cats and pizza","Wolves and pasta"],0],
 ["Which flower pairing is correct?",["Sunflowers and roses","Tulips and lilies","Orchids and daisies","Violets and lavender"],0],
 ["Which date correctly identifies Liliana's birthday?",["22 July","7 February","12 July","27 June"],0],
 ["Which academic subject is connected to Liliana?",["Psychology","Geography","Physics","Engineering"],0],
 ["How many nieces and nephews does she have altogether?",["5","4","6","8"],0],
 ["Which pair contains both of her dogs?",["Aayla and Arlo","Aayla and Milo","Arlo and Coco","Bella and Arlo"],0],
 ["Which colour best represents the birthday aesthetic she would enjoy?",["Baby pink","Bright yellow","Forest green","Silver"],0],
 ["Which activity is most aligned with one of her hobbies?",["Playing poker","Rock climbing","Fishing","Running marathons"],0],
 ["Which statement about Liliana is true?",["She likes children","She dislikes children","She avoids all children","She is afraid of children"],0],
 ["Which combination describes several of her interests?",["Poetry, sad songs and gambling games","Cooking, skiing and opera","Golf, painting and chess","Cycling, fishing and astronomy"],0],
 ["Which animal and flower combination matches her interests?",["Dolphins and sunflowers","Tigers and tulips","Rabbits and orchids","Horses and lilies"],0],
 ["Which food and colour combination matches Liliana?",["Sushi and baby pink","Pizza and orange","Pasta and green","Curry and purple"],0],
 ["Which university subject and hobby pairing is correct?",["Psychology and poker","Physics and rugby","Law and golf","Biology and skiing"],0],
 ["Which statement combines two true facts about Liliana?",["She has green eyes and is a Leo","She has blue eyes and is a Taurus","She has brown eyes and is a Virgo","She has grey eyes and is a Pisces"],0],
 ["Which statement combines her family facts correctly?",["She has 1 niece and 4 nephews","She has 4 nieces and 1 nephew","She has 2 nieces and 3 nephews","She has 5 nieces and no nephews"],0],
 ["Which statement combines her pet facts correctly?",["Aayla and Arlo are her dogs","Aayla is her cat and Arlo is her rabbit","Arlo is her cat and Aayla is her bird","Both are horses"],0],
 ["Which statement combines her dream and favourite animal?",["She wants to be a mum and likes dolphins","She wants to be a pilot and likes sharks","She wants to be a singer and likes wolves","She wants to be a chef and likes bears"],0],
 ["Which statement best describes Liliana overall?",["Sweet, caring, charismatic and empathetic","Cold, distant, impatient and careless","Quiet, rude, selfish and harsh","Competitive, angry, distant and unfriendly"],0]
];

function game23(){
  quizGame(
    finalQuestions,
    50,
    40,
    "The Final Challenge has 50 unique questions about Liliana. You need 40 correct answers to pass.",
    "The Final Challenge",
    15
  );
}

/* =========================================================
   GAME LAUNCHERS
   ========================================================= */

const gameLaunchers={
  1:game1,
  2:game2,
  3:game3,
  4:game4,
  5:game5,
  6:game6,
  7:game7,
  8:game8,
  9:game9,
  10:game10,
  11:game11,
  12:game12,
  13:game13,
  14:game14,
  15:game15,
  16:game16,
  17:game17,
  18:game18,
  19:game19,
  20:game20,
  21:game21,
  22:game22,
  23:game23
};

/* =========================================================
   RESET
   ========================================================= */

function resetGame(){
  if(!confirm(
    "Reset Lulu Express?\n\nThis will erase your name, score, tokens and level progress."
  ))return;

  clearGame();

  state={
    name:"",
    score:0,
    tokens:0,
    unlocked:1,
    completed:[],
    current:0
  };

  localStorage.removeItem("luluExpressState");

  stopMusic();

  document.getElementById("journey").classList.remove("hidden");
  document.getElementById("gameScreen").classList.add("hidden");
  document.getElementById("completion").classList.add("hidden");
  document.getElementById("journeyHeader").classList.remove("hidden");
  document.getElementById("musicPanel").classList.remove("hidden");

  document.getElementById("nameEntry").classList.remove("hidden");
  document.getElementById("welcomeText").classList.add("hidden");
  document.getElementById("playerName").value="";

  updateHeader();
  renderMap();
}

/* =========================================================
   START
   ========================================================= */

loadState();

if(state.name){
  document.getElementById("nameEntry").classList.add("hidden");
  document.getElementById("welcomeText").classList.remove("hidden");
  document.getElementById("welcomeName").textContent=state.name;
}

updateHeader();
renderMap();
updateMusicButton();

/* Enter key starts the journey. */
document.getElementById("playerName").addEventListener("keydown",e=>{
  if(e.key==="Enter")startJourney();
});
</script>

</body>
</html>

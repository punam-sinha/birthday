<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>A Celestial Birthday | Happy Birthday Special</title>
<link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>✨</text></svg>">
<script src="https://cdn.tailwindcss.com/3.4.17"></script>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,400&family=Plus+Jakarta+Sans:wght@300;400;500;600&family=Sacramento&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
<script>
tailwind.config={theme:{extend:{colors:{midnight:'#09090d',roseGold:'#e8b4b8',gold:{300:'#f9e4a8',400:'#e5c578',500:'#cbb06a',600:'#a38743'}},fontFamily:{serif:['"Cormorant Garamond"','Georgia','serif'],sans:['"Plus Jakarta Sans"','system-ui','sans-serif'],script:['"Sacramento"','cursive']}}}}
</script>
<style>
:root{box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
body{background:#09090d;color:#e5e7eb}
.glass-card{background:rgba(22,22,32,.65);backdrop-filter:blur(20px);-webkit-backdrop-filter:blur(20px);border:1px solid rgba(229,197,120,.16);box-shadow:0 20px 50px rgba(0,0,0,.5),inset 0 1px 0 rgba(255,255,255,.08)}
.gold-shimmer-text{background:linear-gradient(135deg,#fff3d1,#d8b467 50%,#f7df9b);-webkit-background-clip:text;-webkit-text-fill-color:transparent}
.perspective-1000{perspective:1200px}
.card-inner{transition:transform .9s cubic-bezier(.34,1.3,.64,1);transform-style:preserve-3d}
.card-unfolded{transform:rotateY(180deg)}
.backface-hidden{backface-visibility:hidden;-webkit-backface-visibility:hidden}
.rotate-y-180{transform:rotateY(180deg)}
@keyframes ambientPulse{0%,100%{opacity:.25;transform:scale(1)}50%{opacity:.45;transform:scale(1.08)}}
.ambient-glow{animation:ambientPulse 8s ease-in-out infinite}
@keyframes floatGentle{0%,100%{transform:translateY(0) rotate(0)}50%{transform:translateY(-10px) rotate(2deg)}}
.floating-balloon{animation:floatGentle 4s ease-in-out infinite}
@keyframes pageIn{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:none}}
.page{display:none}.page.active{display:flex;animation:pageIn .7s ease both}
.letter-scroll{max-height:62vh;overflow-y:auto}
.letter-scroll::-webkit-scrollbar{width:5px}.letter-scroll::-webkit-scrollbar-thumb{background:#3a3850;border-radius:99px}
.dot{width:8px;height:8px;border-radius:99px;background:#33324a;transition:all .3s}
.dot.on{background:#e5c578;width:22px}
</style>
</head>
<body class="font-sans min-h-screen relative overflow-x-hidden selection:bg-gold-500/30">

<div class="fixed inset-0 pointer-events-none overflow-hidden z-0">
  <div class="absolute -top-32 -left-20 w-96 h-96 rounded-full bg-amber-600/10 blur-[110px] ambient-glow"></div>
  <div class="absolute top-1/3 -right-28 w-[30rem] h-[30rem] rounded-full bg-rose-500/10 blur-[130px] ambient-glow" style="animation-delay:-3s"></div>
  <div class="absolute -bottom-24 left-1/4 w-[28rem] h-[28rem] rounded-full bg-indigo-900/15 blur-[120px] ambient-glow" style="animation-delay:-5s"></div>
</div>
<canvas id="starsCanvas" class="fixed inset-0 pointer-events-none z-0"></canvas>

<header class="relative z-20 max-w-5xl mx-auto px-6 py-5 flex items-center justify-between">
  <div class="flex items-center space-x-3">
    <div class="w-8 h-8 rounded-full border border-gold-400/30 flex items-center justify-center bg-gold-400/5"><span class="text-gold-300 text-sm">✦</span></div>
    <span class="font-serif italic text-lg tracking-wider text-gold-300/80 hidden sm:inline">A Special Celebration</span>
  </div>
  <button onclick="toggleAtmosphereAudio()" class="px-4 py-2 rounded-full border border-gold-400/30 bg-gold-400/10 hover:bg-gold-400/20 text-gold-300 text-xs tracking-wider transition active:scale-95 flex items-center space-x-2">
    <span>♪</span><span id="audioStatusText">Play Soft Melody</span>
  </button>
</header>

<main class="relative z-10 max-w-4xl mx-auto px-4 pb-10 flex flex-col items-center">

  <!-- PAGE 1: CARD -->
  <section class="page active w-full flex-col items-center">
    <div class="text-center mb-8">
      <p class="text-gold-400 font-serif italic tracking-widest text-sm uppercase mb-2">Reserved for someone truly extraordinary</p>
      <h1 class="text-4xl md:text-6xl font-serif font-light text-white tracking-tight">Happy Birthday, <span class="gold-shimmer-text font-normal">Special one</span></h1>
      <p class="text-gray-400 text-sm mt-2 max-w-md mx-auto font-light">Touch the seal to reveal your bespoke greeting, then walk through the surprises made just for you.</p>
    </div>
    <div class="perspective-1000 w-full max-w-md h-[460px] relative select-none">
      <div id="surpriseCard" class="card-inner w-full h-full relative cursor-pointer" onclick="toggleCardFlip()">
        <div class="backface-hidden absolute inset-0 rounded-2xl p-8 flex flex-col justify-between items-center text-center glass-card group hover:shadow-[0_0_35px_rgba(229,197,120,.18)] transition">
          <div class="flex justify-between w-full text-xs text-gold-300/40 uppercase tracking-widest"><span>№ 1104</span><span>CONFIDENTIAL &amp; WARMTH</span></div>
          <div class="my-auto flex flex-col items-center">
            <div class="relative group-hover:scale-105 transition-transform duration-500">
              <div class="w-24 h-24 rounded-full bg-gradient-to-tr from-gold-600 via-gold-400 to-amber-200 p-0.5 shadow-[0_0_30px_rgba(229,197,120,.3)]">
                <div class="w-full h-full rounded-full bg-[#181622] flex items-center justify-center border border-gold-300/30"><span class="font-serif text-3xl text-gold-300 italic">B</span></div>
              </div>
              <span class="absolute -inset-1 rounded-full border border-gold-400/40 animate-ping opacity-30"></span>
            </div>
            <p class="mt-6 text-sm font-serif italic text-gold-300/90 tracking-wide">A sealed token of affection</p>
            <span class="text-xs text-gray-500 mt-1 uppercase tracking-widest">Tap to break the seal →</span>
          </div>
          <div class="w-full border-t border-gold-400/10 pt-4 flex justify-between items-center text-xs text-gray-400"><span class="italic font-serif">Made with love</span><span class="text-gold-400">✦ ✦ ✦</span></div>
        </div>
        <div class="backface-hidden rotate-y-180 absolute inset-0 rounded-2xl p-8 flex flex-col justify-between glass-card bg-[#12121c]/95">
          <div>
            <div class="flex justify-between items-center border-b border-gold-400/20 pb-4">
              <span class="font-serif italic text-gold-300 text-lg">Dearest Bhagyashri,</span>
              <button onclick="event.stopPropagation();triggerCardConfetti()" class="text-xs px-2.5 py-1 rounded bg-gold-400/15 text-gold-300 border border-gold-400/30 hover:bg-gold-400/30">✨ Sparkles</button>
            </div>
            <div class="mt-5 space-y-3.5 text-gray-300 text-sm leading-relaxed font-light">
              <p>Today isn’t merely another rotation around the sun; it’s an ode to the light, grace, and warmth you bring into every room you step into.</p>
              <p class="font-serif text-base italic text-gold-300/95">"Every birthday begins with the gift of a fresh start—breathe in the gratitude for how far you've come, and step forward into who you're becoming."</p>
              <p class="text-gray-400 text-xs">Press “Next Surprise” below—each one waits on its own page, just for you.</p>
            </div>
          </div>
          <div class="border-t border-gold-400/20 pt-4 flex items-end justify-between">
            <div><p class="text-xs text-gray-500">With admiration &amp; joy,</p><p class="font-script text-2xl text-gold-400 -mt-1">Yours Punam</p></div>
            <button onclick="event.stopPropagation();toggleCardFlip()" class="text-[11px] text-gray-500 hover:text-gold-300 tracking-wider uppercase">Fold Card ↺</button>
          </div>
        </div>
      </div>
    </div>
    <p class="text-xs text-gray-500 mt-3 text-center">Click the card anytime to fold or flip it back</p>
  </section>

  <!-- PAGE 2: PHOTOS (Direct In-Code Memory Wall) -->
  <section class="page w-full flex-col items-center">
    <div class="text-center mb-6">
      <span class="text-xs uppercase tracking-widest text-gold-400/70">Surprise ①</span>
      <h2 class="text-2xl md:text-3xl font-serif text-white mt-1">Our Memory Wall</h2>
      <p class="text-xs text-gray-400 mt-1">Moments woven in gold &amp; laughter</p>
    </div>

    <div id="photoGrid" class="grid grid-cols-1 sm:grid-cols-2 gap-6 justify-items-center"></div>

    <button onclick="changeCaptions()" class="mt-6 text-xs px-4 py-2 rounded-full border border-gray-700 bg-gray-900/60 hover:border-gold-400/40 text-gray-300 active:scale-95 transition">✎ Change Notes</button>
  </section>
  

  <!-- PAGE 3: LETTER -->
  <section class="page w-full flex-col items-center">
    <div class="text-center mb-5">
      <span class="text-xs uppercase tracking-widest text-gold-400/70">Surprise ②</span>
      <h2 class="text-2xl md:text-3xl font-serif text-white mt-1">A Letter From My Heart</h2>
      <p class="text-xs text-gray-400 mt-1">Take your time. Read it slowly.</p>
    </div>
    <div class="glass-card rounded-2xl p-6 sm:p-8 max-w-xl w-full">
      <div class="letter-scroll pr-2 space-y-4 font-serif text-[17px] leading-relaxed text-gray-200">
        <p class="text-gold-300 italic text-xl">My Best Friend,</p>
        <p>To the girl who turns ordinary days into pure comfort and constant laughter, happy birthday, Bhagyashri! Looking back at everything we’ve shared, I genuinely cannot imagine my life without your chaotic warmth, your endless patience, and that rare kind of loyalty that makes even the toughest days feel manageable. You are the person I run to with random nonsense, frantic rants, unspoken fears, and tiny victories—and no matter what state my mind is in, you always make me feel heard, grounded, and understood.</p>
        <p>Between all our shared giggles that make no sense to anyone else, our spontaneous deep talks, surviving every high and low side by side, and simply knowing each other’s minds without having to utter a single word, you have become so much more than a best friend to me—you are home, peace, and my favorite confidante wrapped into one beautiful soul. You bring so much gentle strength and radiance wherever you go, always lifting the people around you with your kindness and humor.</p>
        <p>On your special day, I hope you see yourself through my eyes and recognize just how extraordinary and irreplaceable you are. I wish you a year bursting with boundless happiness, wild successes, peaceful moments, endless adventures, and every ounce of love your generous heart deserves. Thank you for standing by me through thick and thin, for holding space for me on heavy days, and for never letting me face life's madness alone. Here is to celebrating the wonderful human you are today, and to walking through every tomorrow as each other’s forever rock, loudest cheerleader, and partner-in-crime. Happy birthday, my Bhagyashri! May this new chapter bring you all the magic in the world.</p>
        <p>Thank you for being my safe place, my favourite person, my sister by choice. I love you more than I know how to say.</p>
        <p class="text-gold-300 italic">Happy Birthday,🤍</p>
        <div class="pt-3 border-t border-gold-400/20"><p class="text-xs text-gray-500 font-sans">Forever your best friend,</p><p class="font-script text-3xl text-gold-400">Yours Punam</p></div>
      </div>
    </div>
  </section>

  <!-- PAGE 4: SCRATCH -->
  <section class="page w-full max-w-lg flex-col items-center">
    <div class="text-center mb-6">
      <span class="text-xs uppercase tracking-widest text-gold-400/70">Surprise ③</span>
      <h2 class="text-2xl md:text-3xl font-serif text-white mt-1">Golden Scratch Card</h2>
      <p class="text-xs text-gray-400 mt-1">Use your cursor or finger to gently scratch off the gold foil.</p>
    </div>
    <div class="glass-card p-6 rounded-2xl w-full">
      <div class="relative w-full h-44 rounded-xl overflow-hidden bg-gradient-to-br from-[#1b1928] to-[#0f0e15] border border-gold-400/20 flex items-center justify-center p-6 text-center select-none">
        <div class="z-0 flex flex-col items-center">
          <span class="text-2xl mb-1">🕊️ ✨ 🥂</span>
          <h3 class="font-serif text-lg text-gold-300 tracking-wide">Secret Birthday Wish Unlocked!</h3>
          <p class="text-xs text-gray-300 mt-1.5 leading-relaxed max-w-xs font-light">"May God bless you with endless happiness, good health and peace. You are deeply loved, today and always"</p>
          <span class="mt-2 text-[10px] text-gold-400/70 tracking-widest uppercase">With all my love, always 🤍</span>
        </div>
        <canvas id="scratchCanvas" class="absolute inset-0 w-full h-full z-10 cursor-pointer touch-none"></canvas>
      </div>
      <div class="mt-4 flex items-center justify-between text-xs text-gray-400">
        <span id="scratchProgress">Scratched: 0%</span>
        <button onclick="resetScratchCard()" class="text-gold-400 hover:text-gold-300 underline text-[11px]">Re-coat with gold</button>
      </div>
    </div>
  </section>

  <!-- PAGE 5: BALLOONS -->
  <section class="page w-full flex-col items-center">
    <div class="text-center mb-8">
      <span class="text-xs uppercase tracking-widest text-gold-400/70">Surprise ④</span>
      <h2 class="text-2xl md:text-3xl font-serif text-white mt-1">Pop for Golden Affirmations</h2>
      <p class="text-xs text-gray-400 mt-1">Tap a floating orb to pop it and release a compliment.</p>
    </div>
    <div class="grid grid-cols-2 sm:grid-cols-4 gap-4 max-w-3xl px-2">
      <div onclick="popBalloon(this,'Your laughter,happiness, makes ordinary days feel completely cinematic.')" class="floating-balloon glass-card p-4 rounded-2xl flex flex-col items-center cursor-pointer hover:border-gold-400 transition active:scale-95">
        <div class="w-14 h-16 rounded-full bg-gradient-to-t from-gold-600 via-gold-400 to-amber-200 flex items-center justify-center shadow-[0_0_20px_rgba(229,197,120,.3)]"><span class="text-xl">🎈</span></div><span class="text-xs text-gold-300 mt-4 font-serif italic">Pop Me #1</span></div>
      <div onclick="popBalloon(this,'You possess rare kindness and grace that inspires everyone around you.')" class="floating-balloon glass-card p-4 rounded-2xl flex flex-col items-center cursor-pointer hover:border-roseGold transition active:scale-95" style="animation-delay:1.2s">
        <div class="w-14 h-16 rounded-full bg-gradient-to-t from-rose-600 via-rose-400 to-pink-200 flex items-center justify-center shadow-[0_0_20px_rgba(232,180,184,.3)]"><span class="text-xl">✨</span></div><span class="text-xs text-roseGold mt-4 font-serif italic">Pop Me #2</span></div>
      <div onclick="popBalloon(this,'Your mind is witty, sharp, and constantly full of wondrous creativity.')" class="floating-balloon glass-card p-4 rounded-2xl flex flex-col items-center cursor-pointer hover:border-gold-400 transition active:scale-95" style="animation-delay:2.1s">
        <div class="w-14 h-16 rounded-full bg-gradient-to-t from-purple-600 via-indigo-400 to-amber-200 flex items-center justify-center shadow-[0_0_20px_rgba(163,135,67,.3)]"><span class="text-xl">🔮</span></div><span class="text-xs text-gold-300 mt-4 font-serif italic">Pop Me #3</span></div>
      <div onclick="popBalloon(this,'You deserve every ounce of success, comfort, and unconditional love.')" class="floating-balloon glass-card p-4 rounded-2xl flex flex-col items-center cursor-pointer hover:border-gold-300 transition active:scale-95" style="animation-delay:.7s">
        <div class="w-14 h-16 rounded-full bg-gradient-to-t from-amber-700 via-gold-500 to-yellow-100 flex items-center justify-center shadow-[0_0_20px_rgba(229,197,120,.3)]"><span class="text-xl">🥂</span></div><span class="text-xs text-gold-300 mt-4 font-serif italic">Pop Me #4</span></div>
    </div>
    <div id="complimentBox" class="max-w-lg mt-6 p-4 rounded-xl glass-card text-center transition-all duration-500 opacity-0 translate-y-3 pointer-events-none">
      <p class="text-xs uppercase tracking-widest text-gold-400/80 mb-1">A Whisper For You</p>
      <p id="complimentText" class="font-serif italic text-base md:text-lg text-white"></p>
    </div>
  </section>

  <!-- PAGE 6: VAULT -->
  <section class="page w-full max-w-md flex-col items-center">
    <div class="text-center mb-6">
      <span class="text-xs uppercase tracking-widest text-gold-400/70">Surprise ⑤</span>
      <h2 class="text-2xl font-serif text-white mt-1">The Birthday Vault</h2>
      <p class="text-xs text-gray-400 mt-1">Enter the secret 4-digit passcode <span class="text-gold-300">(Hint: 0 to 4)</span></p>
    </div>
    <div class="glass-card p-6 rounded-2xl text-center w-full">
      <div class="flex justify-center gap-3 mb-5" id="vaultRow"></div>
      <button onclick="unlockVault()" class="w-full py-2.5 rounded-xl bg-gradient-to-r from-gold-600 via-gold-400 to-amber-200 text-midnight font-medium text-xs uppercase tracking-widest hover:brightness-110 transition">Unlock Memory Note</button>
      <div id="vaultMessage" class="hidden mt-5 p-4 rounded-xl bg-gold-400/10 border border-gold-400/30 text-left">
        <div class="text-gold-300 text-xs uppercase tracking-wider mb-2">🔓 Vault Unlocked</div>
        <p class="font-serif italic text-sm text-gray-200 leading-relaxed">"No matter how busy the world gets, remember that you are deeply cherished, endlessly capable, and your existence makes life substantially sweeter. Happy Birthday!"</p>
      </div>
    </div>
    <footer class="mt-12 text-center text-xs text-gray-500 font-light">
      <p class="font-serif italic text-gold-300/80 text-base mb-1">Cheers to another brilliant chapter.</p>
      <p>Crafted exclusively with love, starlight &amp; aesthetic warmth.</p>
    </footer>
  </section>

  <!-- NAV -->
  <nav class="mt-10 w-full max-w-md flex items-center justify-between gap-4">
    <button id="prevBtn" onclick="goTo(cur-1)" class="px-4 py-2 rounded-full border border-gray-700 text-gray-300 text-xs hover:border-gold-400/40 transition">← Back</button>
    <div id="dots" class="flex items-center gap-2"></div>
    <button id="nextBtn" onclick="goTo(cur+1)" class="px-5 py-2 rounded-full bg-gradient-to-r from-gold-600 via-gold-400 to-amber-200 text-midnight text-xs font-medium tracking-wider hover:brightness-110 transition">Next Surprise →</button>
  </nav>
</main>

<script>
/* AUDIO */
let audioCtx=null,isPlayingMelody=false,melodyInterval=null;
function initAudio(){if(!audioCtx)audioCtx=new(window.AudioContext||window.webkitAudioContext)();if(audioCtx.state==='suspended')audioCtx.resume()}
function playChimeNote(freq,delay=0,duration=1.2){
  if(!audioCtx)return;
  setTimeout(()=>{try{
    const o=audioCtx.createOscillator(),g=audioCtx.createGain(),t=audioCtx.currentTime;
    o.type='sine';o.frequency.setValueAtTime(freq,t);
    g.gain.setValueAtTime(.0001,t);g.gain.exponentialRampToValueAtTime(.12,t+.05);g.gain.exponentialRampToValueAtTime(.0001,t+duration);
    o.connect(g);g.connect(audioCtx.destination);o.start();o.stop(t+duration);
  }catch(e){}},delay);
}
function playCelebrationChime(){initAudio();[523.25,659.25,783.99,987.77,1174.66].forEach((f,i)=>playChimeNote(f,i*90,1.8))}
function toggleAtmosphereAudio(){
  initAudio();const bt=document.getElementById('audioStatusText');
  if(!isPlayingMelody){
    isPlayingMelody=true;bt.innerText='Chimes Active';
    const s=[440,523.25,587.33,659.25,783.99,880];
    playChimeNote(s[0],0,1.5);playChimeNote(s[2],250,1.5);playChimeNote(s[4],500,2);
    melodyInterval=setInterval(()=>playChimeNote(s[Math.floor(Math.random()*s.length)],0,2),2200);
  }else{isPlayingMelody=false;clearInterval(melodyInterval);bt.innerText='Play Soft Melody'}
}

/* PAGES */
const pages=[...document.querySelectorAll('.page')];let cur=0;
const dots=document.getElementById('dots');
pages.forEach(()=>{const d=document.createElement('span');d.className='dot';dots.appendChild(d)});
function goTo(i){
  if(i<0||i>=pages.length)return;
  cur=i;
  pages.forEach((p,k)=>p.classList.toggle('active',k===i));
  [...dots.children].forEach((d,k)=>d.classList.toggle('on',k===i));
  document.getElementById('prevBtn').style.visibility=i===0?'hidden':'visible';
  const nb=document.getElementById('nextBtn');
  nb.style.visibility=i===pages.length-1?'hidden':'visible';
  nb.textContent=i===0?'Begin the Surprises →':'Next Surprise →';
  if(i===3&&!scratchReady)initScratchCard();
  window.scrollTo({top:0,behavior:'smooth'});
  playChimeNote(660,0,.5);
  if(i===pages.length-1)triggerCardConfetti();
}

/* CARD */
let cardFlipped=false;
function toggleCardFlip(){
  cardFlipped=!cardFlipped;
  document.getElementById('surpriseCard').classList.toggle('card-unfolded',cardFlipped);
  playCelebrationChime();if(cardFlipped)triggerCardConfetti();
}
function triggerCardConfetti(){
  if(typeof confetti==='function')confetti({particleCount:70,spread:70,origin:{y:.6},colors:['#f9e4a8','#e5c578','#e8b4b8','#ffffff','#cbb06a']});
}

/* STARS */
const canvas=document.getElementById('starsCanvas'),ctx=canvas.getContext('2d');
function resizeCanvas(){canvas.width=innerWidth;canvas.height=innerHeight}
addEventListener('resize',resizeCanvas);resizeCanvas();
const stars=Array.from({length:65},()=>({x:Math.random()*canvas.width,y:Math.random()*canvas.height,s:Math.random()*1.8+.4,a:Math.random()*.7+.2,v:Math.random()*.015+.005,d:Math.random()>.5?1:-1}));
(function animateStars(){
  ctx.clearRect(0,0,canvas.width,canvas.height);
  stars.forEach(t=>{t.a+=t.v*t.d;if(t.a>.85||t.a<.15)t.d*=-1;ctx.fillStyle=`rgba(249,228,168,${t.a})`;ctx.beginPath();ctx.arc(t.x,t.y,t.s,0,Math.PI*2);ctx.fill()});
  requestAnimationFrame(animateStars);
})();

/* PHOTOS CONFIGURED DIRECTLY IN CODE */
const myPhotos = [
  {
    src: "WhatsApp Image 2026-11-07 at 1.53.37 AM.jpeg",
    note: "Pure grace and elegance ✨",
    tilt: "hover:rotate-1 -rotate-2"
  },
  {
    src: "WhatsApp Image 2026-11-07 at 1.53.12 AM.jpeg",
    note: "Partners in crime always 🫡",
    tilt: "hover:-rotate-1 rotate-1"
  },
  {
    src: "WhatsApp Image 2026-11-07 at 2.03.49 AM.jpeg",
    note: "Unfiltered smiles & cheekiness 🌸",
    tilt: "hover:rotate-2 rotate-2"
  },
  {
    src: "WhatsApp Image 2026-11-07 at 1.53.37 AM (1).jpeg",
    note: "My safe place, my best friend 🤍",
    tilt: "hover:-rotate-2 -rotate-1"
  }
];

const alternativeCaptions = [
  "The most radiant soul in the world ✨",
  "More beautiful inside than words can say 🌸",
  "To endless laughter and spontaneous memories 🥂",
  "A heart made of gold and pure magic 🕊️",
  "My safe place, always 🤍",
  "Thank you for simply being you 💫",
  "Friends today, sisters forever 💖",
  "Every memory with you is golden 🎞️"
];
let capShift = 0;

const grid = document.getElementById('photoGrid');

function renderPhotos() {
  grid.innerHTML = '';
  myPhotos.forEach((item, i) => {
    const card = document.createElement('div');
    card.className = `p-3 pb-6 bg-[#eae6df] rounded-lg shadow-2xl text-gray-900 w-72 sm:w-64 transform ${item.tilt} hover:scale-[1.03] transition-all duration-300 cursor-pointer`;
    card.onclick = () => playCelebrationChime();
    
    const currentNote = capShift === 0 ? item.note : alternativeCaptions[(i + capShift) % alternativeCaptions.length];

    card.innerHTML = `
      <div class="relative w-full h-64 sm:h-56 bg-neutral-900 rounded overflow-hidden mb-3">
        <img src="${item.src}" alt="Memory ${i + 1}" class="w-full h-full object-cover object-top transition-transform duration-700 hover:scale-105">
        <div class="absolute top-2 right-2 px-2 py-0.5 rounded-full bg-black/60 text-[10px] text-amber-200 backdrop-blur-sm">35mm Film</div>
      </div>
      <p id="cap${i}" class="font-serif italic text-neutral-800 text-sm text-center px-1">${currentNote}</p>
      <p class="text-[10px] text-neutral-500 uppercase tracking-widest text-center mt-1">Memory 0${i + 1}</p>
    `;
    grid.appendChild(card);
  });
}

function changeCaptions() {
  capShift = (capShift + 1) % alternativeCaptions.length;
  renderPhotos();
  playChimeNote(880, 0, .4);
}

renderPhotos();

/* SCRATCH */
const sc=document.getElementById('scratchCanvas'),sCtx=sc.getContext('2d');
let isScratching=false,totalPixels=0,scratchDone=false,scratchReady=false;
function initScratchCard(){
  const r=sc.getBoundingClientRect();
  sc.width=r.width||400;sc.height=r.height||176;totalPixels=sc.width*sc.height;
  sCtx.globalCompositeOperation='source-over';
  const g=sCtx.createLinearGradient(0,0,sc.width,sc.height);
  g.addColorStop(0,'#d1ab55');g.addColorStop(.3,'#f9e4a8');g.addColorStop(.7,'#b8903c');g.addColorStop(1,'#8e6b22');
  sCtx.fillStyle=g;sCtx.fillRect(0,0,sc.width,sc.height);
  sCtx.fillStyle='rgba(15,15,21,.45)';sCtx.font='600 13px "Plus Jakarta Sans",sans-serif';sCtx.textAlign='center';
  sCtx.fillText('✦ SCRATCH GENTLY TO REVEAL ✦',sc.width/2,sc.height/2+5);
  scratchDone=false;scratchReady=true;
  document.getElementById('scratchProgress').innerText='Scratched: 0%';
}
function scratch(e){
  if(!isScratching||scratchDone)return;
  const r=sc.getBoundingClientRect();
  const p=e.touches?e.touches[0]:e;
  sCtx.globalCompositeOperation='destination-out';
  sCtx.beginPath();sCtx.arc(p.clientX-r.left,p.clientY-r.top,22,0,Math.PI*2);sCtx.fill();
  initAudio();playChimeNote(600+Math.random()*200,0,.1);
  calcScratch();
}
function calcScratch(){
  try{
    const d=sCtx.getImageData(0,0,sc.width,sc.height).data;let c=0;
    for(let i=3;i<d.length;i+=16)if(d[i]===0)c++;
    const pct=Math.min(100,Math.round(c/(totalPixels/4)*100));
    document.getElementById('scratchProgress').innerText='Scratched: '+pct+'%';
    if(pct>=50&&!scratchDone){
      scratchDone=true;sc.style.transition='opacity .8s ease';sc.style.opacity='0';
      setTimeout(()=>sc.style.display='none',800);triggerCardConfetti();
    }
  }catch(e){}
}
sc.addEventListener('mousedown',()=>isScratching=true);
addEventListener('mouseup',()=>isScratching=false);
sc.addEventListener('mousemove',scratch);
sc.addEventListener('touchstart',e=>{isScratching=true;scratch(e)},{passive:true});
addEventListener('touchend',()=>isScratching=false);
sc.addEventListener('touchmove',scratch,{passive:true});
function resetScratchCard(){sc.style.display='block';sc.style.opacity='1';initScratchCard()}

/* BALLOONS */
function popBalloon(el,msg){
  initAudio();playChimeNote(350,0,.1);playChimeNote(700,30,.5);
  const r=el.getBoundingClientRect();
  if(typeof confetti==='function')confetti({particleCount:25,startVelocity:18,spread:60,origin:{x:(r.left+r.width/2)/innerWidth,y:(r.top+r.height/2)/innerHeight},colors:['#e5c578','#ffffff','#e8b4b8']});
  el.style.transform='scale(.85)';el.style.opacity='.5';el.style.pointerEvents='none';
  document.getElementById('complimentText').innerText='"'+msg+'"';
  const b=document.getElementById('complimentBox');
  b.classList.remove('opacity-0','translate-y-3','pointer-events-none');b.classList.add('opacity-100','translate-y-0');
}

/* VAULT */
const vr=document.getElementById('vaultRow');
for(let i=0;i<4;i++){
  const inp=document.createElement('input');
  inp.type='text';inp.inputMode='numeric';inp.maxLength=1;
  inp.className='vault-input w-12 h-14 rounded-lg bg-[#0b0b10] border border-gold-400/30 text-center text-2xl text-gold-300 focus:outline-none focus:border-gold-400';
  inp.addEventListener('input',()=>{if(inp.value.length===1&&i<3)vr.children[i+1].focus();playChimeNote(500+i*100,0,.2)});
  inp.addEventListener('keydown',e=>{if(e.key==='Backspace'&&!inp.value&&i>0)vr.children[i-1].focus()});
  vr.appendChild(inp);
}
function unlockVault(){
  const inputs=[...vr.children],code=inputs.map(i=>i.value).join('');
  if(code.length===4){playCelebrationChime();triggerCardConfetti();document.getElementById('vaultMessage').classList.remove('hidden')}
  else inputs.forEach(i=>{i.classList.add('border-rose-500');setTimeout(()=>i.classList.remove('border-rose-500'),500)});
}

goTo(0);
</script>
</body>
</html>

# The Juice Toolkit — AURORA's motion recipe book

The catalog of **concrete, copy-paste motion recipes** that make a Hunch page feel *alive* — not the static, fade-up-and-done template an AI reaches for first. This is the "how" behind `ui-ux-motion.md` §5: that file sets the philosophy and the budget; **this file is the parts bin.**

Every recipe is **vanilla HTML/CSS/JS** — no framework, no build step, no dependencies — because the sites this skill ships are single self-contained files. They are the same effects the best React motion libraries are known for ([Skiper UI](https://skiper-ui.com), [Cult UI](https://www.cult-ui.com), [Style UI](https://www.styleui.dev), [Watermelon UI](https://ui.watermelon.sh), and the Magic/Aceternity ecosystem), **re-expressed in plain code** so they drop straight into the page.

## How to use this file

1. **Every site ships the baseline (§0).** The reveal harness, motion tokens, and the reduced-motion switch are non-negotiable — they're what turns a wall of static sections into a page that *arrives*.
2. **Pick a signature (1–2 recipes) that fits the chosen design language.** Use the **[Signature juice by family](#signature-juice-by-family)** map at the bottom — it tells you which recipes belong to each of the 50 languages. A terminal product gets a typewriter + scramble; a premium product gets a shine-sweep + Ken-Burns; a playful product gets magnetic + squash press.
3. **Add 2–4 supporting micro-interactions** (button + card juice) so *every* interactive element responds. Dead hovers are the "static" tell.
4. **Respect the budget (§7).** Over-animation is as much an AI tell as under-animation. Choreograph; don't decorate.

> **Golden rule:** animate only `transform`, `opacity`, `clip-path`, `filter`, and CSS custom properties. Never animate `width`/`height`/`top`/`left`/`margin` of in-flow content — that causes layout shift and jank and tanks Core Web Vitals.

---

## §0 — Foundations (ship on every site)

### 0.1 Motion tokens

Consistency *is* polish. Define the vocabulary once; every recipe below reads from it.

```css
:root{
  /* easing */
  --ease-out:      cubic-bezier(.16,.84,.28,1);   /* entrances, reveals — decisive settle */
  --ease-in-out:   cubic-bezier(.65,0,.35,1);     /* moves, toggles */
  --ease-spring:   cubic-bezier(.34,1.56,.64,1);  /* playful overshoot — use sparingly */
  --ease-emphatic: cubic-bezier(.22,1,.36,1);     /* long, luxurious slides */
  /* durations */
  --dur-fast: 140ms; --dur: 300ms; --dur-slow: 620ms; --dur-xslow: 1100ms;
  /* orchestration */
  --stagger: 90ms;
}
```

### 0.2 The reveal harness — one observer, many entrances

The engine behind scroll reveals *and* the load sequence. Drive it from `data-` attributes so a section chooses its own entrance without new CSS. This single block replaces the thin "fade-up only" reveal in most templates.

```css
/* base: hidden state + the transition. Variants set the *from* transform. */
[data-reveal]{opacity:0;transition:opacity var(--dur-slow) var(--ease-out),transform var(--dur-slow) var(--ease-out),filter var(--dur-slow) var(--ease-out);will-change:opacity,transform}
[data-reveal="up"]     {transform:translateY(28px)}
[data-reveal="down"]   {transform:translateY(-28px)}
[data-reveal="left"]   {transform:translateX(34px)}
[data-reveal="right"]  {transform:translateX(-34px)}
[data-reveal="scale"]  {transform:scale(.92)}
[data-reveal="blur"]   {filter:blur(14px);transform:translateY(18px)}
[data-reveal="clip"]   {clip-path:inset(0 0 100% 0)}            /* wipes up into view */
[data-reveal].in{opacity:1;transform:none;filter:none;clip-path:inset(0 0 0 0);will-change:auto}

/* stagger children of a revealed container */
[data-stagger]>*{opacity:0;transform:translateY(20px);transition:opacity var(--dur-slow) var(--ease-out),transform var(--dur-slow) var(--ease-out)}
[data-stagger].in>*{opacity:1;transform:none}
[data-stagger].in>*{transition-delay:calc(var(--i,0)*var(--stagger))}
```

```js
// Set --i on staggered children, then observe everything with [data-reveal]/[data-stagger].
const R = {
  reduce: matchMedia('(prefers-reduced-motion: reduce)').matches,
  init(){
    document.querySelectorAll('[data-stagger]').forEach(g=>
      [...g.children].forEach((c,i)=>c.style.setProperty('--i',i)));
    const targets = document.querySelectorAll('[data-reveal],[data-stagger]');
    if(this.reduce || !('IntersectionObserver' in window)){
      targets.forEach(el=>el.classList.add('in')); return;
    }
    const io = new IntersectionObserver((es)=>es.forEach(e=>{
      if(e.isIntersecting){ e.target.classList.add('in'); io.unobserve(e.target); }
    }), {threshold:.16, rootMargin:'0px 0px -8% 0px'});
    targets.forEach(el=>io.observe(el));
  }
};
R.init();
```

Usage: `<section data-reveal="up">`, `<div class="grid" data-stagger data-reveal>`, `<figure data-reveal="blur">`. The **hero uses the same harness for its load sequence** — give the hero `data-stagger` and it arrives in order (headline → sub → CTA → signature) the instant the page paints.

### 0.3 The reduced-motion master switch

Ship this once. It neutralizes *every* recipe for users who ask for less motion — non-negotiable.

```css
@media (prefers-reduced-motion: reduce){
  *,*::before,*::after{animation-duration:.001ms!important;animation-iteration-count:1!important;transition-duration:.001ms!important;scroll-behavior:auto!important}
  [data-reveal],[data-stagger]>*{opacity:1!important;transform:none!important;filter:none!important;clip-path:none!important}
}
```

Every JS recipe also early-returns on `R.reduce`. Both layers matter: CSS kills declarative motion, the guard skips the JS that adds it.

---

## §1 — Text effects

### 1.1 Word / character reveal (the hero line that *assembles*)

The single highest-impact upgrade to a hero. Splits the headline into words (or chars) that rise and unblur in sequence. This is the vanilla twin of Cult UI's `TextAnimate` / Magic UI's text reveal.

```css
.split-line{display:inline-block}
.split-line .w{display:inline-block;opacity:0;transform:translateY(.5em) rotate(2deg);filter:blur(6px);
  animation:wordIn .7s var(--ease-out) forwards;animation-delay:calc(var(--wi)*70ms)}
@keyframes wordIn{to{opacity:1;transform:none;filter:none}}
```

```js
document.querySelectorAll('[data-split="word"]').forEach(el=>{
  if(R.reduce) return;
  const words = el.textContent.trim().split(/\s+/);
  el.textContent='';
  el.classList.add('split-line');
  words.forEach((w,i)=>{
    const s=document.createElement('span'); s.className='w'; s.textContent=w;
    s.style.setProperty('--wi',i); el.append(s, document.createTextNode(' '));
  });
});
```
Use `data-split="word"` on the H1. For per-character, split `[...word]` instead — reserve chars for short display type (logos, section titles), words for sentences.

### 1.2 Typewriter (terminal / dev-tool idiom)

```css
.type::after{content:'▋';margin-left:2px;animation:caret 1s steps(1) infinite;color:var(--accent)}
@keyframes caret{50%{opacity:0}}
```
```js
function typewriter(el, text, speed=42){
  if(R.reduce){ el.textContent=text; return; }
  el.classList.add('type'); let i=0;
  (function tick(){ el.textContent=text.slice(0,i++); if(i<=text.length) setTimeout(tick,speed); })();
}
// typewriter(document.querySelector('#cmd'), '$ deploy --production');
```

### 1.3 Scramble / decode (cyber, crypto, AI-infra)

Characters flicker through random glyphs before locking to the final letter — Skiper/decrypt idiom.

```js
function scramble(el, final, dur=900){
  if(R.reduce){ el.textContent=final; return; }
  const glyphs='ABCDEFGHJKLMNPQRSTUVWXYZ0123456789#%&$/<>*';
  const start=performance.now();
  (function frame(t){
    const p=Math.min((t-start)/dur,1);
    const lock=Math.floor(p*final.length);
    el.textContent=[...final].map((ch,i)=>
      i<lock?ch:(ch===' '?' ':glyphs[Math.floor(Math.random()*glyphs.length)])).join('');
    if(p<1) requestAnimationFrame(frame);
  })(start);
}
```
Trigger on reveal (call from the IntersectionObserver callback for that element).

### 1.4 Count-up number ticker (stats that *earn attention*)

Numbers that animate from 0 to target when scrolled into view. The vanilla twin of Cult UI's `Animated Number`. This alone makes a proof band feel live instead of printed.

```js
function countUp(el){
  if(R.reduce){ el.textContent=el.dataset.count; return; }
  const target=parseFloat(el.dataset.count), dec=(el.dataset.count.split('.')[1]||'').length,
        pre=el.dataset.pre||'', suf=el.dataset.suf||'', dur=1400, t0=performance.now();
  (function step(t){
    const p=Math.min((t-t0)/dur,1), e=1-Math.pow(1-p,3);        // easeOutCubic
    el.textContent=pre+(target*e).toFixed(dec).replace(/\B(?=(\d{3})+(?!\d))/g,',')+suf;
    if(p<1) requestAnimationFrame(step);
  })(t0);
}
// <b data-count="1240" data-suf="+"></b>  or  <b data-count="4.8" data-suf="/5"></b>
const countIO=new IntersectionObserver((es)=>es.forEach(e=>{
  if(e.isIntersecting){ countUp(e.target); countIO.unobserve(e.target); }
}),{threshold:.6});
document.querySelectorAll('[data-count]').forEach(el=>countIO.observe(el));
```

### 1.5 Gradient shimmer text (premium / holographic accents)

A light sweep travels across a gradient-filled headline. The vanilla twin of Cult UI's `Gradient Heading`.

```css
.shimmer-text{background:linear-gradient(100deg,var(--text) 30%,var(--accent) 50%,var(--text) 70%);
  background-size:200% 100%;-webkit-background-clip:text;background-clip:text;color:transparent;
  animation:shimmerSweep 4s linear infinite}
@keyframes shimmerSweep{to{background-position:-200% 0}}
```

### 1.6 Scroll-linked word highlight (editorial / manifesto sections)

A paragraph "fills" word by word as you scroll past it — Skiper's text-scroll idiom. Great for a one-line mission statement.

```css
[data-scrolltext] span{color:color-mix(in srgb,var(--text) 22%,transparent);transition:color .1s linear}
[data-scrolltext] span.lit{color:var(--text)}
```
```js
document.querySelectorAll('[data-scrolltext]').forEach(el=>{
  el.innerHTML=el.textContent.trim().split(/\s+/).map(w=>`<span>${w}</span>`).join(' ');
  const words=[...el.children];
  if(R.reduce){ words.forEach(w=>w.classList.add('lit')); return; }
  addEventListener('scroll',()=>{
    const r=el.getBoundingClientRect(), vh=innerHeight;
    const p=Math.min(Math.max((vh*.8-r.top)/(r.height+vh*.4),0),1);
    const lit=Math.floor(p*words.length);
    words.forEach((w,i)=>w.classList.toggle('lit',i<lit));
  },{passive:true});
});
```

---

## §2 — Buttons & CTAs (make every click satisfying)

A CTA with no motion is the clearest "static" tell on the page. Give the *primary* CTA one signature effect; give all buttons the press physics.

### 2.1 Magnetic button (the signature CTA)

The button leans toward the cursor and its label lags slightly — the effect every polished portfolio uses. Reserve for the *one* primary CTA.

```css
.magnetic{transition:transform var(--dur) var(--ease-spring)}
.magnetic .label{display:inline-block;transition:transform var(--dur) var(--ease-out)}
```
```js
document.querySelectorAll('.magnetic').forEach(btn=>{
  if(R.reduce) return;
  const label=btn.querySelector('.label')||btn, str=.35;
  btn.addEventListener('pointermove',e=>{
    const r=btn.getBoundingClientRect(), x=e.clientX-r.left-r.width/2, y=e.clientY-r.top-r.height/2;
    btn.style.transform=`translate(${x*str}px,${y*str}px)`;
    label.style.transform=`translate(${x*str*.4}px,${y*str*.4}px)`;
  });
  btn.addEventListener('pointerleave',()=>{ btn.style.transform=''; label.style.transform=''; });
});
```

### 2.2 Shimmer-sweep button (a gloss travels across on hover)

```css
.btn-shimmer{position:relative;overflow:hidden}
.btn-shimmer::after{content:'';position:absolute;inset:0;transform:translateX(-120%) skewX(-20deg);
  background:linear-gradient(90deg,transparent,rgba(255,255,255,.35),transparent);transition:transform .7s var(--ease-out)}
.btn-shimmer:hover::after{transform:translateX(120%) skewX(-20deg)}
```

### 2.3 Border-beam button (a light orbits the border)

Cult UI's `Border Beam`, done with a conic gradient masked to the border.

```css
.beam{position:relative;border-radius:12px;background:var(--surface);z-index:0}
.beam::before{content:'';position:absolute;inset:0;padding:1.5px;border-radius:inherit;
  background:conic-gradient(from 0deg,transparent 0 70%,var(--accent) 85%,transparent 100%);
  -webkit-mask:linear-gradient(#000 0 0) content-box,linear-gradient(#000 0 0);
  -webkit-mask-composite:xor;mask-composite:exclude;animation:spin 3s linear infinite}
@keyframes spin{to{transform:rotate(1turn)}}
```

### 2.4 Press physics + ripple (put this on *all* buttons)

```css
.btn{transition:transform var(--dur-fast) var(--ease-out),box-shadow var(--dur-fast) var(--ease-out)}
.btn:hover{transform:translateY(-2px)}
.btn:active{transform:translateY(0) scale(.97)}
/* optional ink ripple */
.btn.ripple{position:relative;overflow:hidden}
.btn .ink{position:absolute;border-radius:50%;background:rgba(255,255,255,.4);transform:scale(0);animation:ink .6s var(--ease-out);pointer-events:none}
@keyframes ink{to{transform:scale(4);opacity:0}}
```
```js
document.querySelectorAll('.btn.ripple').forEach(b=>b.addEventListener('pointerdown',e=>{
  if(R.reduce) return;
  const r=b.getBoundingClientRect(), s=document.createElement('span'); s.className='ink';
  const d=Math.max(r.width,r.height); s.style.cssText=`width:${d}px;height:${d}px;left:${e.clientX-r.left-d/2}px;top:${e.clientY-r.top-d/2}px`;
  b.append(s); setTimeout(()=>s.remove(),600);
}));
```

---

## §3 — Cards & surfaces (nothing should sit dead)

### 3.1 Spotlight card (a glow tracks the cursor)

The Aceternity/Cult signature: a soft radial highlight follows the pointer across the card. Pure CSS-variable + one listener; scales to a whole grid.

```css
.spot{position:relative;overflow:hidden;background:var(--surface);border:1px solid var(--line);border-radius:16px}
.spot::before{content:'';position:absolute;inset:0;opacity:0;transition:opacity var(--dur);
  background:radial-gradient(240px circle at var(--mx) var(--my),color-mix(in srgb,var(--accent) 22%,transparent),transparent 60%)}
.spot:hover::before{opacity:1}
```
```js
document.querySelectorAll('.spot').forEach(c=>c.addEventListener('pointermove',e=>{
  const r=c.getBoundingClientRect();
  c.style.setProperty('--mx',(e.clientX-r.left)+'px'); c.style.setProperty('--my',(e.clientY-r.top)+'px');
}));
```

### 3.2 3D tilt card (parallax on pointer)

The card rotates toward the cursor with perspective — Skiper/Aceternity 3D card. Put depth on inner layers with `translateZ` for real parallax.

```css
.tilt{transform-style:preserve-3d;transition:transform var(--dur) var(--ease-out)}
.tilt .pop{transform:translateZ(40px)}          /* lifts a badge/icon toward the viewer */
```
```js
document.querySelectorAll('[data-tilt]').forEach(card=>{
  if(R.reduce) return;
  const max=10;
  card.addEventListener('pointermove',e=>{
    const r=card.getBoundingClientRect();
    const rx=(.5-(e.clientY-r.top)/r.height)*max*2, ry=((e.clientX-r.left)/r.width-.5)*max*2;
    card.style.transform=`perspective(800px) rotateX(${rx}deg) rotateY(${ry}deg)`;
  });
  card.addEventListener('pointerleave',()=>card.style.transform='');
});
```

### 3.3 Shine sweep on hover (premium tiles, pricing card)

```css
.shine{position:relative;overflow:hidden}
.shine::after{content:'';position:absolute;top:-50%;left:-60%;width:40%;height:200%;transform:rotate(25deg) translateX(-140%);
  background:linear-gradient(90deg,transparent,rgba(255,255,255,.28),transparent);transition:transform .9s var(--ease-out)}
.shine:hover::after{transform:rotate(25deg) translateX(360%)}
```

### 3.4 Gradient/beam border on hover

```css
.gradborder{position:relative;background:var(--surface);border-radius:16px}
.gradborder::before{content:'';position:absolute;inset:0;border-radius:inherit;padding:1px;opacity:0;transition:opacity var(--dur);
  background:linear-gradient(120deg,var(--accent),var(--accent-2,var(--accent)));
  -webkit-mask:linear-gradient(#000 0 0) content-box,linear-gradient(#000 0 0);-webkit-mask-composite:xor;mask-composite:exclude}
.gradborder:hover::before{opacity:1}
```

---

## §4 — Ambient backgrounds (kill the flat void)

A flat single-color section behind the hero is the biggest "static" giveaway. Add **one** ambient system — never more than one competing for attention.

### 4.1 Animated aurora / mesh gradient

Soft colored blobs drift behind clean content — the Aurora/mesh look, GPU-cheap because only `transform` moves.

```css
.aurora{position:relative;isolation:isolate;overflow:hidden}
.aurora::before{content:'';position:absolute;inset:-30%;z-index:-1;filter:blur(70px);opacity:.6;
  background:
    radial-gradient(38% 44% at 22% 28%,var(--accent) 0,transparent 60%),
    radial-gradient(34% 40% at 78% 32%,var(--accent-2,var(--accent)) 0,transparent 60%),
    radial-gradient(44% 50% at 55% 80%,var(--gold,var(--accent)) 0,transparent 60%);
  animation:auroraDrift 22s var(--ease-in-out) infinite alternate}
@keyframes auroraDrift{
  0%{transform:translate3d(-4%,-2%,0) rotate(0deg) scale(1.05)}
  100%{transform:translate3d(4%,3%,0) rotate(8deg) scale(1.15)}}
```

### 4.2 Dot-grid / graph paper + cursor spotlight

A technical grid that's dark everywhere except a soft circle around the cursor — Cult UI's `Grid Beam` feel. Perfect for dev/technical products.

```css
.grid-spot{position:relative;background:var(--bg);
  background-image:radial-gradient(color-mix(in srgb,var(--text) 14%,transparent) 1px,transparent 1px);
  background-size:22px 22px;
  -webkit-mask:radial-gradient(240px circle at var(--mx,50%) var(--my,50%),#000 20%,transparent 75%);
          mask:radial-gradient(240px circle at var(--mx,50%) var(--my,50%),#000 20%,transparent 75%)}
```
```js
const gs=document.querySelector('.grid-spot');
gs&&gs.addEventListener('pointermove',e=>{const r=gs.getBoundingClientRect();
  gs.style.setProperty('--mx',(e.clientX-r.left)+'px');gs.style.setProperty('--my',(e.clientY-r.top)+'px');});
```

### 4.3 Conic beam sweep (a light rotates behind the hero)

```css
.beam-bg{position:relative;overflow:hidden}
.beam-bg::before{content:'';position:absolute;inset:-50%;z-index:-1;opacity:.18;
  background:conic-gradient(from 0deg at 50% 50%,transparent 0,var(--accent) 12%,transparent 25%);
  animation:spin 14s linear infinite}
```

### 4.4 Cursor-reactive gradient (whole hero tints toward the pointer)

```js
const hero=document.querySelector('.hero');
hero&&!R.reduce&&hero.addEventListener('pointermove',e=>{
  const r=hero.getBoundingClientRect();
  hero.style.setProperty('--px',((e.clientX-r.left)/r.width*100)+'%');
  hero.style.setProperty('--py',((e.clientY-r.top)/r.height*100)+'%');
});
/* CSS: .hero{background:radial-gradient(600px circle at var(--px,50%) var(--py,30%),color-mix(in srgb,var(--accent) 12%,transparent),transparent 70%)} */
```

### 4.5 Grain / noise overlay (adds texture, kills banding)

```css
.grain::after{content:'';position:fixed;inset:0;z-index:1;pointer-events:none;opacity:.04;mix-blend-mode:overlay;
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='120'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='3'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E")}
```

---

## §5 — Scroll choreography (the page performs as you read)

### 5.1 Scroll-stacking cards (Skiper's signature, zero-JS)

Cards pin and stack as you scroll — each sticks, and the next slides over it. Pure CSS `position:sticky`; add a scale-down for depth. This is the single most "premium" scroll move and needs **no library**.

```css
.stack{display:grid;gap:0}
.stack .card{position:sticky;top:12vh;border-radius:20px;padding:clamp(28px,5vw,56px);
  box-shadow:0 -8px 40px -20px rgba(0,0,0,.4)}
.stack .card:nth-child(1){top:10vh} .stack .card:nth-child(2){top:13vh}
.stack .card:nth-child(3){top:16vh} .stack .card:nth-child(4){top:19vh}
```
Optional JS to scale earlier cards down as later ones arrive (adds real depth):
```js
if(!R.reduce) document.querySelectorAll('.stack .card').forEach(card=>{
  new IntersectionObserver(([e])=>{
    const s=.9+.1*e.intersectionRatio; card.style.transform=`scale(${Math.min(s,1)})`;
  },{threshold:[...Array(11)].map((_,i)=>i/10)}).observe(card);
});
```

### 5.2 Clip-path image reveal on scroll

An image/mockup wipes into view instead of just fading — Skiper's "scroll images reveal."

```css
[data-imgreveal]{clip-path:inset(0 0 100% 0);transition:clip-path var(--dur-xslow) var(--ease-emphatic)}
[data-imgreveal].in{clip-path:inset(0 0 0 0)}   /* reuse the §0 observer: it toggles .in */
```

### 5.3 Parallax layers (depth on scroll, rAF-throttled)

```js
const layers=document.querySelectorAll('[data-parallax]');   // data-parallax="0.2" = speed
if(layers.length && !R.reduce){
  let ticking=false;
  addEventListener('scroll',()=>{ if(ticking) return; ticking=true;
    requestAnimationFrame(()=>{ const y=scrollY;
      layers.forEach(l=>l.style.transform=`translate3d(0,${y*parseFloat(l.dataset.parallax)}px,0)`);
      ticking=false; });
  },{passive:true});
}
```

### 5.4 Sticky nav that condenses on scroll

```css
header.nav{transition:padding var(--dur) var(--ease-out),background var(--dur),box-shadow var(--dur)}
header.nav.shrink{padding-block:.4rem;background:color-mix(in srgb,var(--bg) 82%,transparent);
  backdrop-filter:blur(10px);box-shadow:0 1px 0 var(--line)}
```
```js
const nav=document.querySelector('header.nav');
addEventListener('scroll',()=>nav.classList.toggle('shrink',scrollY>40),{passive:true});
```

### 5.5 Scroll progress bar

```css
.progress{position:fixed;top:0;left:0;height:3px;width:100%;transform-origin:0 50%;transform:scaleX(0);
  background:var(--accent);z-index:100}
```
```js
const bar=document.querySelector('.progress');
addEventListener('scroll',()=>{const h=document.documentElement, max=h.scrollHeight-h.clientHeight;
  bar.style.transform=`scaleX(${max>0?Math.min(h.scrollTop/max,1):0})`;},{passive:true});
```

---

## §6 — Signature moments (pick one that *is* the product)

### 6.1 Marquee / infinite logo ticker

A seamless loop of logos or testimonials — Magic UI's `Marquee`. Duplicate the track so the loop is seamless; pause on hover.

```css
.marquee{overflow:hidden;-webkit-mask:linear-gradient(90deg,transparent,#000 8%,#000 92%,transparent)}
.marquee__track{display:flex;gap:3rem;width:max-content;animation:scrollX 26s linear infinite}
.marquee:hover .marquee__track{animation-play-state:paused}
@keyframes scrollX{to{transform:translateX(-50%)}}   /* -50% because the track is duplicated */
```
```html
<div class="marquee"><div class="marquee__track">
  <!-- items, then the SAME items again for a seamless loop -->
</div></div>
```

### 6.2 Image cursor trail

Images spawn along the pointer path and fade — Skiper's `Image Cursor Trail`. A playful signature for creative/consumer brands (use over a hero, sparingly).

```js
function cursorTrail(zone, srcs){
  if(R.reduce) return; let last=0, n=0;
  zone.addEventListener('pointermove',e=>{
    const now=performance.now(); if(now-last<70) return; last=now;
    const img=new Image(); img.src=srcs[n++%srcs.length];
    img.style.cssText=`position:absolute;left:${e.offsetX}px;top:${e.offsetY}px;width:120px;translate:-50% -50%;
      pointer-events:none;border-radius:10px;transition:opacity .7s,transform .7s;opacity:1`;
    zone.append(img);
    requestAnimationFrame(()=>{img.style.opacity='0';img.style.transform='translateY(30px) scale(.8)';});
    setTimeout(()=>img.remove(),750);
  });
}
```

### 6.3 Dynamic-island morph (a pill that grows into a panel)

Cult UI's `Dynamic Island` — one element smoothly changes size/shape between states. Great for a "join waitlist → success" transition.

```css
.island{border-radius:999px;overflow:hidden;
  transition:width var(--dur) var(--ease-spring),height var(--dur) var(--ease-spring),border-radius var(--dur) var(--ease-spring)}
.island[data-state="expanded"]{border-radius:24px}
```
Toggle width/height inline (or via classes) on state change; the transition does the morph. Because only `transform`-adjacent props animate here, keep sizes fixed (not `auto`) so it stays smooth.

### 6.4 Before → after drag slider (transformation made literal)

A draggable handle wipes between the "before" and "after" — perfect for METAMORPH's transformation section.

```css
.ba-slide{position:relative;overflow:hidden;--split:50%}
.ba-slide .after{position:absolute;inset:0;clip-path:inset(0 0 0 var(--split))}
.ba-slide .handle{position:absolute;top:0;bottom:0;left:var(--split);width:2px;background:var(--accent);cursor:ew-resize}
```
```js
document.querySelectorAll('.ba-slide').forEach(el=>{
  const move=x=>{const r=el.getBoundingClientRect();
    el.style.setProperty('--split',Math.min(Math.max((x-r.left)/r.width*100,0),100)+'%');};
  el.addEventListener('pointermove',e=>e.buttons&&move(e.clientX));
  el.addEventListener('pointerdown',e=>move(e.clientX));
});
```

---

## §7 — The juice budget & guardrails

Motion is a budget, not a buffet. **More is not more.** A page that animates everything reads as AI-generated exactly like one that animates nothing.

**The contract for a finished page:**
- [ ] **Baseline (§0) on every site** — reveal harness driving both the hero load sequence *and* scroll reveals, motion tokens, reduced-motion switch.
- [ ] **Every interactive element responds** — buttons have press physics (§2.4); cards have at least a hover lift or spotlight (§3). No dead hovers.
- [ ] **One ambient background** behind the hero or a key section (§4) — never two competing.
- [ ] **One scroll-choreography move** as you read (§5) — sticky nav condense + progress bar count; a stacking/reveal section is a bonus.
- [ ] **Exactly one signature moment** (§1.1–1.3, §6, or the design language's assigned recipe) — the thing the visitor remembers. Spend the boldness here; keep everything else quiet.

**The guardrails (all must hold):**
- **GPU-only** — animate `transform`/`opacity`/`clip-path`/`filter`/custom props. Never layout props.
- **No CLS** — reserve space for anything that animates in; set image `width`/`height`.
- **`will-change` discipline** — set it while animating, drop it after (`.in` does this in §0.2). Don't leave it on forever.
- **Throttle scroll/pointer** — `requestAnimationFrame` for scroll math, `{passive:true}` listeners, a time-gate on trail/pointer spawners.
- **Lazy** — start heavy loops only when their element is on screen (IntersectionObserver); pause off-screen.
- **Reduced motion** — every recipe here degrades to instant/static. Verify with the OS setting on.
- **Accessibility** — motion is never the *only* signal; keyboard focus stays visible; hit areas ≥44px.
- **Performance stays green** — coordinate with SUMMIT: LCP fast, no long tasks, JS deferred. Beauty keeps Core Web Vitals green or it isn't polish.

**The two failure modes to self-check:**
1. **Too static** (the old tell) — flat sections, dead hovers, a headline that just appears, printed-looking numbers, a single-color void behind the hero. If the page doesn't *move* as you load and scroll it, add baseline + a signature.
2. **Over-juiced** (the opposite tell) — everything bounces, three backgrounds fight, every word animates, the eye has no rest. Cut back to one ambient, one signature, quiet everything else.

---

## Signature juice by family

Map the chosen design language (from `design-languages.md`) to its signature recipes. Ship §0 baseline always, then pull the family's signature + a supporting card/button effect. This keeps two Hunch sites feeling like two different studios.

| Family (languages) | Ambient (§4) | Signature (§1/§5/§6) | Buttons/cards (§2/§3) | Feel |
|---|---|---|---|---|
| **Hard / bold** — neo-brutalism, gig-poster, pop-art, Bauhaus, concrete, editorial-brutalist | none / flat | word slam-in (1.1, no blur, spring), stacking cards (5.1) | hard press (2.4), no lift | snappy, abrupt, no soft easing |
| **Tech / terminal** — dark techno, retro terminal, ASCII, cyberpunk, blueprint, data, wireframe | dot-grid + cursor spotlight (4.2), conic beam (4.3) | typewriter (1.2), scramble (1.3), count-up (1.4) | border-beam button (2.3), grid-spot cards | scan, flicker, type-on |
| **Soft / premium** — luxury, art deco, dark academia, fashion-photo, Scandinavian, cottagecore | subtle aurora (4.1), grain (4.5) | shimmer text (1.5), clip image reveal (5.2), Ken-Burns | shine sweep (3.3), gradient border (3.4) | slow, deliberate, refined |
| **Playful / organic** — claymorphism, liquid, casual-game, scrapbook, Y2K, soft/friendly, retro-futurism | floating orbs / aurora (4.1) | magnetic CTA (2.1), cursor trail (6.2), squash press | spring press (2.4 + spring), 3D tilt (3.2) | bouncy, gooey, squash-and-stretch |
| **3D / depth / holo** — 3D-render, spatial, holographic, aurora-mesh, glassmorphism | aurora/mesh (4.1), cursor-reactive tint (4.4) | 3D tilt cards (3.2), parallax layers (5.3) | spotlight cards (3.1), shine (3.3) | float, orbit, shine sweep, depth |
| **Editorial / type** — kinetic typography, editorial, Swiss, newspaper, monochrome | none / hairline grid | word/char reveal (1.1), scroll-text highlight (1.6), line-mask | magnetic on the one CTA (2.1) | kinetic word swaps, masked reveals |
| **Refined SaaS / modern-minimal / bento** (the tasteful default, done *well*) | soft aurora (4.1) or grid-spot (4.2) | count-up stats (1.4), spotlight cards (3.1), stacking (5.1) | shimmer button (2.2), spotlight (3.1) | purposeful, restrained, alive |

For **ad-creative videos**, the same families map to the video idioms in `design-languages.md` → *Per-style video idioms* and the effects in `ad-creatives.md` → *Motion & effects toolkit*. Site juice and video juice share a family so a product's page and its ads feel like one brand.

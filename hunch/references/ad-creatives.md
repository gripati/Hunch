# Ad Creatives — UA Video Playbook

How the creative squad turns the product into **platform-ready, scroll-stopping ad creatives** — short videos with a 3-second hook, one per angle, instantly rendered at the exact resolution each platform needs, each one visibly different so the user can A/B test. On request ("make 6 TikTok creatives + 4 Reels for [product]"), produce the whole set.

## The creative squad (runs in parallel)

| Agent | Role |
|-------|------|
| **REEL** | Creative director — builds the **creative matrix** (which angles × which platforms × which formats), assigns a distinct **design treatment** to each so no two look alike, and guarantees variety + brand coherence. |
| **SPARK** | Hook specialist — the **first 3 seconds**: the scroll-stopper that earns the next 5. One hook per creative, tuned to platform + angle. |
| **PULSE** | Concept creatives — the **whole-idea** ads (what it is, the core transformation, the "brand" spots). |
| **FACET** | Feature creatives — **one creative per key feature/benefit/angle**, each spotlighting a different facet. Runs once per feature (parallel). |
| **FRAME** | Format & platform engineer — renders each creative as a **video at the exact resolution/format** for the target platform, with sound-off captions, safe zones, correct duration, and an end card. Owns the actual creative files. |

Inputs they read: `transformation` (METAMORPH), `benefits`/features (BEACON), `hooks`/tone (EDGE), `icp` (VAULT), `proof` (CHORUS), `one_promise` (ATLAS), and the chosen `design_system` + `design-languages.md` (AURORA).

## The 3-second hook (SPARK)

Most of the result is decided in the first 3 seconds. Open with one of these, made specific and true:
- **Pattern interrupt** — an unexpected visual/motion or a line that breaks the scroll ("Stop reposting your videos three times.").
- **Problem callout** — name the viewer's pain in their words, fast ("Still chasing late invoices?").
- **Bold claim / number** — a specific, credible result up front ("Get paid 9 days sooner.").
- **Curiosity gap** — a question the viewer needs answered ("Why are you renting the tool that posts for you?").
- **Show-the-payoff** — the After state first, then how.
- **POV / native** — looks like organic content, not an ad (especially TikTok).

Rules: text + visual must land **with sound off**; one idea per hook; specific beats clever; honest (no fake claim). Different creatives get **different hook types**, not the same hook reskinned.

## Creative structure (≈6–15s)

```
0–3s  HOOK (SPARK)        scroll-stopper — text + visual, sound-off readable
3–7s  MESSAGE             the angle: the transformation (PULSE) or one feature's outcome (FACET)
7–11s PROOF / DEMO        a number, the product in action, the signature moment, or social proof
11–15s CTA / END CARD     one clear action + the name/logo (and, in validation mode, "join the waitlist")
```
Keep one idea per creative. Captions always on (most feed video is watched muted). Brand/logo by the end. End on the CTA.

## Platform formats & resolutions (FRAME)

Render each creative at the exact spec. Keep critical text inside safe zones (away from platform UI/edges).

| Placement | Aspect | Resolution | Notes |
|-----------|--------|-----------|-------|
| TikTok / Reels / Shorts / IG & FB Stories | 9:16 | **1080×1920** | hook in 1s, native feel, captions, ~9–15s; keep text off the bottom ~250px / top ~130px (UI) |
| Feed video (square) | 1:1 | **1080×1080** | works across IG/FB feed; ~6–15s |
| Feed video (portrait) | 4:5 | **1080×1350** | max feed real estate; ~6–15s |
| YouTube in-stream / landscape | 16:9 | **1920×1080** | hook before the skip at 5s |
| Google Display (HTML5 / static) | banner | **300×250, 336×280, 728×90, 160×600, 300×600, 320×100** | animated HTML or static; keep under platform weight limits |

If the user names a platform, render that platform's set; if they name a count, produce that many *distinct* creatives across angles/treatments.

## How creatives are built — animated HTML video-creatives

The skill renders each creative as a **self-contained animated HTML file at the exact pixel resolution** — a timed, looping mini-video that plays the hook → message → proof → CTA. These are real, usable creatives: they play in any browser, **screen-record cleanly to MP4** (or export via a headless recorder), and double as HTML5 display ads. Build them with `frontend-design` + the chosen design language.

Construction:
- A fixed-size stage at the exact resolution (e.g. `width:1080px;height:1920px`) so the recording is pixel-perfect. Provide a scaled preview wrapper for on-screen viewing.
- **Scene timeline via CSS keyframes** — each scene fades/moves in on a schedule; the whole thing loops (e.g. a 12s loop). Use `transform`/`opacity` only (smooth recording), respect `prefers-reduced-motion` for preview.
- **Big, legible, sound-off text**; captions; the signature visual/motion from the site; the brand mark; the end-card CTA.
- A short **`render-notes`** per creative: how to export (screen-record the stage at 1:1 zoom, or use a headless browser video capture), duration, fps.

```html
<!-- 9:16 creative stage (1080x1920). Scale the wrapper for preview; record the .stage at 100%. -->
<div class="stage"><!-- scenes -->
  <section class="scene s1">…HOOK…</section>
  <section class="scene s2">…MESSAGE…</section>
  <section class="scene s3">…PROOF…</section>
  <section class="scene s4">…CTA / END CARD…</section>
</div>
<style>
.stage{width:1080px;height:1920px;position:relative;overflow:hidden;/* design-language tokens */}
.scene{position:absolute;inset:0;display:grid;place-content:center;opacity:0;animation:play 12s linear infinite}
.s1{animation-name:s1}.s2{animation-name:s2}.s3{animation-name:s3}.s4{animation-name:s4}
@keyframes s1{0%,2%{opacity:0;transform:translateY(20px)}4%,22%{opacity:1;transform:none}26%{opacity:0}}
@keyframes s2{26%{opacity:0}30%,48%{opacity:1}52%{opacity:0}}
@keyframes s3{52%{opacity:0}56%,74%{opacity:1}78%{opacity:0}}
@keyframes s4{78%{opacity:0}82%,98%{opacity:1}100%{opacity:0}}
@media(prefers-reduced-motion:reduce){.scene{animation:none;opacity:1}}
</style>
```

(When a true MP4 is required and a headless browser/video tool is available in the environment, FRAME can capture the stage to video; otherwise it ships the HTML creative + render-notes for a one-step screen capture.)

## Motion & effects toolkit (juice)

Make creatives feel *produced*, not slideshowed. Pull effects from this toolkit and **match them to the chosen design language's video idiom** (see `design-languages.md` → Per-style video idioms). Use `transform`/`opacity`/`clip-path` so the recording stays smooth; never animate layout.

**Typewriter / typing text** (tech, terminal, ASCII, cyberpunk):
```css
.type{width:0;overflow:hidden;white-space:nowrap;border-right:.12em solid currentColor;
  animation:typing 1.1s steps(22) forwards, caret .7s steps(1) infinite}
@keyframes typing{to{width:14ch}} @keyframes caret{50%{border-color:transparent}}
```
(For multi-line or precise control, reveal characters/words with JS on a timer.)

**Word / char stagger reveal** (kinetic type, editorial, bold):
```css
.w{display:inline-block;opacity:0;transform:translateY(.5em);animation:win .5s var(--ease) forwards}
.w:nth-child(2){animation-delay:.08s}.w:nth-child(3){animation-delay:.16s}/* … */
@keyframes win{to{opacity:1;transform:none}}
```

**Masked line reveal** (premium, editorial): wrap each line in `overflow:hidden` and slide the inner text up (`translateY(100%)→0`).

**Count-up numbers** (data, proof, tech): animate a number from 0 to the target with JS (`requestAnimationFrame`), e.g. `$0 → $684`, `0 → 3 platforms`.

**Glitch / RGB-split** (cyberpunk, dark-techno): duplicate the text in two layers tinted cyan/magenta and jitter their `transform` + `clip-path` on a fast loop.

**Shine / foil sweep** (holographic, luxury): a moving gradient highlight masked to the text (`background-clip:text` + animated `background-position`).

**Scene transitions** (pick to match the idiom): hard **cut** (bold/poster), **wipe** (`clip-path` inset growing), **slide/push**, **scale-punch** (scale 1.06→1 with a snap), **blur-in** (`filter:blur(12px)→0` + opacity), **morph** (liquid). Sync cuts to an implied beat for hard/bold styles.

Keep one or two signature effects per creative — coordinated, not chaotic. Respect `prefers-reduced-motion` in the preview (show static frames). Over-stuffing effects is itself an AI tell.

## Brand logos in creatives

Platform mentions in creatives use the **real, official logos** (per `references/brand-assets.md`) — the "publish once → YouTube · TikTok · Instagram" beat shows the actual marks (in brand color, or one consistent monochrome treatment that fits the creative's design language), **never emoji or letters**. End-card "get it" CTAs use the official **App Store / Google Play badges** or **Sign in with Apple/Google** buttons, following their guidelines. Real logos make a creative read as a real product.

## The creative matrix (REEL)

REEL plans the set as a table — every row is one finished creative:

| # | Angle | Platform | Format/Res | Hook (type) | Design treatment | Core line | CTA |
|---|-------|----------|-----------|-------------|------------------|-----------|-----|
| 1 | Concept / transformation | TikTok | 9:16 1080×1920 | problem callout | clean native | … | … |
| 2 | Feature A | Reels | 9:16 1080×1920 | bold number | neo-brutalist | … | … |
| 3 | Feature B | IG feed | 1:1 1080×1080 | curiosity gap | glassy/premium | … | … |
| 4 | Proof / social | Stories | 9:16 1080×1920 | show-the-payoff | game-UI energetic | … | … |

## Variety rules (so every creative differs)

Each creative in a set must differ from the last on **at least two** axes, so the user gets real alternatives to test:
- **Angle** — concept vs feature A vs feature B vs proof vs offer.
- **Hook type** — rotate across the SPARK list; never the same hook reskinned.
- **Design treatment** — rotate across `design-languages.md` (one clean/native, one bold, one premium, one energetic), within brand sense.
- **Open** — sometimes pain-first, sometimes payoff-first, sometimes POV-native.
- **Pace/structure** — vary scene count and rhythm.

## Output

Deliver: the **creative matrix** (the table) + one **animated HTML creative file per row** at the right resolution (named e.g. `creative-01_tiktok_9x16_featureA.html`) + a short **render/export note**. In **validation mode** (see `website-blueprint.md`), every creative's CTA points to the waitlist ("Join the waitlist" / "Get early access") and the landing page opens the email-capture modal.

## Honesty
No fabricated stats, fake testimonials, or invented results in any creative (the honesty gate applies to ads too). Use real proof or clearly-true claims; mark any placeholder for the user to fill.

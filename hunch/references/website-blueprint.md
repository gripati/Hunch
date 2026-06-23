# Sales Website Blueprint

The section-by-section map for the sales site. It turns the persuasion arc (see `principles.md`) into a page where **every section does a specific job and executes specific principles**. Build in this order. Before writing HTML, read `frontend-design/SKILL.md` **and `ui-ux-motion.md`** and build to **AURORA's design + motion language** — `assets/landing-page-template.html` is an annotated working scaffold to adapt, not a final design.

Each section below lists: its **job**, the **principles/agents** it executes, the **copy slots** to fill from the Brief, and **proof placement**.

> **Single page or multi-page?** SUMMIT decides (see `discovery-seo-geo-aeo.md`). If the project is one landing page, this section map *is* that page. If SUMMIT specced a multi-page site, the **landing/home page still follows this full map**, and each supporting page (comparison, "alternative-to", use-case, answers hub) is a focused, answer-first page that reuses the relevant sections below and **links back to the offer**. Build every page to AURORA's design language and bake in the `<head>` + JSON-LD from `discovery-seo-geo-aeo.md`.

---

## Section order (top → bottom)

### 0. Nav / top bar
- **Job:** orient, keep the primary CTA always reachable.
- **Slots:** product name/logo, 2–4 anchor links, a persistent CTA button.
- Keep it quiet — the hero does the work.

### 1. Hero — the thesis
- **Job:** in one screen, hit the pain, promise the transformation, and make the offer's core promise. This is the highest-leverage real estate on the page.
- **Executes:** P3 (lead with pain), P2 (transformation), P6 (ego+fear headline), P4 (buyer's vocabulary), P1 (emotional charge).
- **Slots:**
  - **Headline** — EDGE's hero line: the transformation, fused with ego + fear. The single most important sentence on the page.
  - **Sub-headline** — the Before→After in plain terms (METAMORPH), in the buyer's words (COMPASS).
  - **Primary CTA** — action-named ("Get paid faster", not "Submit"); the same verb persists through the flow.
  - **Hero proof strip** — one number or one short peer quote (CHORUS) right under the CTA, so belief arrives with the ask.
- **Proof:** a compact proof strip immediately adjacent to the first CTA.

### 2. The pain — "this is you"
- **Job:** make the buyer feel seen; sharpen the urgency before promising relief.
- **Executes:** P3 (pain + cost of inaction), P1 (emotion), P6 (the fear axis).
- **Slots:** the sharpest pain (LANCE) dramatized in the buyer's language, plus the cost of doing nothing. 2–3 secondary pains as supporting bullets.
- Keep it honest and specific (PRISM) — name the real consequence, not vague dread.

### 3. The transformation — Before → After
- **Job:** show the prize: who they become.
- **Executes:** P2 (transformation), P5 (outcomes, not features), P1 (the felt After).
- **Slots:** a Before/After contrast (a two-column "without / with" works well), anchored on the canonical transformation statement (METAMORPH). Frame the product as the bridge.
- **Proof:** a transformation testimonial — someone who made exactly this Before→After move (CHORUS) — sits naturally here.

### 4. How it helps — benefits (the "what's in it for me")
- **Job:** translate the product into the buyer's improved life.
- **Executes:** P5 (feature → benefit → outcome), P9 (specific outcomes).
- **Slots:** 3–6 benefit blocks. Each: a buyer-outcome as the heading (BEACON), the feature as the *mechanism* underneath, tied to a pain. Lead each block with the outcome, not the feature.
- **Proof:** a relevant micro-proof or stat beside the most important benefit.

### 5. Proof — the believability core
- **Job:** establish that this works for people like the buyer.
- **Executes:** P7 (social proof), P9 (specific numbers).
- **Slots:** the proof architecture from CHORUS — numbers (users/results/ratings), 2–4 testimonials from people resembling the ICP, logos/press if real, a mini case study (situation → action → measurable result). Real where available; clearly-labeled placeholders otherwise (`[TESTIMONIAL — replace with a real customer quote]`).
- This section concentrates proof, but proof also recurs beside other CTAs — don't strand it all here.

### 6. The offer — the irresistible stack
- **Job:** present an offer the right customer would feel foolish refusing.
- **Executes:** P10 (strong offer), P8 (right-customer value), P1 (logic stack near the decision).
- **Slots:** the named offer (FORGE) — core deliverable as an outcome, the value stack listed so each item visibly kills a pain/objection, the risk reversal/guarantee prominent, and real scarcity if any. The logical justification stack (EMBER) lives here, where the buyer is rationalizing.
- **Proof:** the guarantee itself is proof-of-confidence; place a results stat beside it.

### 7. Pricing — value-anchored
- **Job:** make the price read as obviously worth it to the right customer.
- **Executes:** P8 (value-based pricing + anchor), P1 (logic), P9 (specific value math).
- **Slots:** the price/tiers (VAULT), the anchor that reframes it (cost of the pain, price of the alternative, bundle value), payment options. State the value in the buyer's terms right next to the number. Don't apologize for the price.
- **Proof:** a "worth it" testimonial or an ROI stat beside the price.

### 8. Objection handling / FAQ
- **Job:** remove the last reasons not to buy.
- **Executes:** P1 (logic), P7 (proof per objection), P5 (reassurance via outcomes).
- **Slots:** the top 4–6 objections (price, trust, "will it work for me?", switching cost, time) with concrete answers, each backed by proof where possible (from the strategy's objection-handling section).

### 9. Final CTA — the close
- **Job:** ask once more, cleanly, with the promise and the risk reversal in view.
- **Executes:** P2 (restate the transformation), P6 (ego+fear), P10 (restate the guarantee), P1 (emotion to act).
- **Slots:** restate the one promise, the primary CTA (same verb as the hero), the guarantee one more time, and a final ego+fear line. A last proof point underneath.

### 10. Footer
- **Job:** close out; provide trust/contact basics.
- **Slots:** product name, brief honest line, contact, legal links. Quiet.

---

## Cross-cutting rules for the page

- **One promise.** Hero headline, offer name, and final CTA all assert the same promise (ATLAS). No competing claims.
- **Proof rides every ask.** Each CTA has relevant proof within sight (CHORUS). Belief should always be present when you ask for the decision.
- **Emotion opens, logic closes.** Emotional copy leads sections; the logical justification stack clusters at the offer/pricing/CTA where buyers rationalize (EMBER).
- **Outcomes over features, everywhere.** Every feature on the page is paired with what it does for the buyer (BEACON). Feature-only copy is a defect.
- **Specific or cut.** No "save time / high quality / trusted by many" survives PRISM. Numbers, names, concrete before/after — or an honest labeled estimate.
- **One voice.** All copy follows EDGE's tone tokens.
- **Honest proof only.** Real proof or clearly-labeled placeholders. Never fabricate.

## Build quality (non-negotiable)

- Semantic HTML, responsive to mobile, visible keyboard focus, `prefers-reduced-motion` respected, sufficient color contrast.
- Design tokens (color/type/spacing) defined once at the top as CSS custom properties so the page is easy to re-theme per product.
- A bespoke visual identity + motion system from **AURORA** (per `frontend-design` and `ui-ux-motion.md`), not the scaffold's defaults shipped unchanged. Full juice, full polish, with restraint.
- The primary CTA verb is consistent from hero to close.

## Discovery baked in (every page) — from `discovery-seo-geo-aeo.md`

- **`<head>`:** unique `<title>` + `<meta description>`, `<link rel="canonical">`, Open Graph + Twitter tags (SUMMIT).
- **One `<h1>`** per page; logical heading hierarchy; descriptive image `alt`; internal links funnel to the offer (SUMMIT).
- **Answer-first:** each page answers its core question in the first 1–2 sentences, supporting (not replacing) the hook (ORACLE).
- **JSON-LD:** FAQPage (matching the visible FAQ exactly) + Product/SoftwareApplication + Organization, plus BreadcrumbList/HowTo where relevant (ORACLE). Never mark up fake ratings.
- **Citable lines:** specific, self-contained claim/stat sentences placed in the copy (ECHO).
- **Performance:** GPU-cheap motion, no layout shift, deferred non-critical JS, compressed images — Core Web Vitals green (SUMMIT × AURORA).
- **Site-level files:** ship `sitemap.xml`, `robots.txt`, and `llms.txt` alongside the page(s).

## Validation mode — the waitlist / email-capture modal

The skill builds in one of two modes (set in the Brief `mode` field):

- **Launch mode** — the real product exists; CTAs go to signup/checkout/the app.
- **Validation mode ("fake it till you make it")** — the product is still an *idea*. The site presents the concept as if it's real and **captures email to measure demand**. This is the default when there's no live product yet.

In **validation mode**, every conversion point — each primary CTA *and* the pricing CTA — opens a **polished, design-language-consistent email-capture modal** instead of going to checkout. The pitch: *"Launching soon — get early access. Leave your email and we'll reach out first."* Pricing still shows (it's part of the test — willingness at a price), but its button opens the modal too.

### The modal — requirements
- **On-brand:** matches the chosen design language exactly (same radius, buttons, colors, type, shadow). A neo-brutalist site gets a hard-edged bordered modal; a glassy site gets a frosted one. Never a generic default dialog.
- **Juicy + polished:** a backdrop fade + a modal entrance (scale/slide with `--ease-spring`), a satisfying button press, and a **success state** after submit ("You're on the list — we'll be in touch."). All within the motion floor.
- **Accessible:** open via `<dialog>` or a focus-trapped div; close on **ESC**, backdrop click, and a visible close button; move focus into the modal on open and restore it on close; `aria-modal="true"`, a labelled heading; respect `prefers-reduced-motion`.
- **Honest capture:** the email must actually go somewhere — wire the form to a real endpoint and mark it for the owner: `[SET: your form endpoint — e.g. Formspree, a serverless function, or a hosted form]`. Do **not** fake submission or claim storage that isn't wired. Validate the email field; show errors inline. No backend is created by the skill — it provides the front end + a clear integration point.
- **Low friction:** ask for email only (optionally one qualifying field). One field converts best for validation.

### Pattern (adapt tokens to the design language)
```html
<button data-waitlist>Get early access →</button>

<dialog id="waitlist" aria-labelledby="wl-title">
  <form method="dialog" id="wl-form" novalidate>
    <button type="button" class="wl-x" aria-label="Close" data-close>×</button>
    <h2 id="wl-title">Launching soon — get early access</h2>
    <p>Leave your email and we'll reach out before anyone else.</p>
    <input type="email" id="wl-email" required placeholder="you@email.com" autocomplete="email" />
    <p class="wl-err" hidden>Please enter a valid email.</p>
    <button type="submit" class="btn">Join the waitlist →</button>
  </form>
  <div id="wl-done" hidden><h2>You're on the list ✦</h2><p>We'll be in touch first. Thanks for the early support.</p></div>
</dialog>
```
```js
const dlg=document.getElementById('waitlist'); let last=null;
document.querySelectorAll('[data-waitlist]').forEach(b=>b.addEventListener('click',()=>{last=b;dlg.showModal();document.getElementById('wl-email').focus();}));
dlg.querySelector('[data-close]').onclick=()=>dlg.close();
dlg.addEventListener('click',e=>{if(e.target===dlg)dlg.close();}); // backdrop
dlg.addEventListener('close',()=>last&&last.focus());
document.getElementById('wl-form').addEventListener('submit',async e=>{
  const email=document.getElementById('wl-email'); const err=dlg.querySelector('.wl-err');
  if(!email.checkValidity()){e.preventDefault();err.hidden=false;return;}
  e.preventDefault();
  try{
    await fetch('[SET_ENDPOINT]',{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({email:email.value})}); // [SET: real endpoint]
  }catch(_){}
  document.getElementById('wl-form').hidden=true; document.getElementById('wl-done').hidden=false;
});
```
Style `dialog`, `::backdrop`, the inputs, and the success state with the design-language tokens (this is just structure). Note in the strategy that the **success metric is signups / signup-rate** — the demand signal the whole validation site exists to capture.

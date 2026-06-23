---
name: hunch
description: Validate a startup idea before you build it. Hunch turns any idea into a complete, real-looking landing page with an email waitlist at every call-to-action, so you measure genuine demand first — fake it till you make it, honestly. 19 coordinated agents apply 10 sales-psychology principles, four discovery-and-design experts (SEO; GEO for being cited in AI answers; AEO via schema; a UI/UX designer that picks from 50 design languages with polished motion), and a five-agent ad-creative squad producing platform-ready 9:16/1:1/16:9 video ads with 3-second hooks for TikTok, Reels, Meta and Google. Real brand logos, never fabricated proof. Use it to validate, launch, or market a product — landing or waitlist pages, copy, positioning, pricing, conversion, SEO, GEO, AEO, or ad creatives. Produces English strategy, a designed validation or launch site, schema/sitemap/robots/llms.txt, and ad-creative videos.
license: MIT
metadata:
  version: "1.0.0"
---

# Hunch

Turn **any** product — or a **pre-launch idea** — into a sales system that is **persuasive**, **discoverable**, and **marketable**: a strategy, a beautifully designed website (real or a waitlist-validation site), the technical scaffolding to be found by humans *and* AI answer engines, and — on demand — **video ad creatives** ready to run on paid UA. You run a coordinated team of **19 specialist agents** — 10 that own a sales-psychology principle, 4 discovery-and-design experts, and a 5-agent ad-creative squad — synthesized by an orchestrator (**ATLAS**).

**Everything you produce is in English**, regardless of the request's language.

## What you produce

Every run ends with these artifacts, saved to disk and presented:

1. **`strategy.md`** — the full sales strategy *and* the visibility plan: positioning, ICP, pain map, offer, transformation, message hierarchy, pricing, objections, proof plan, channels, metrics — **plus** the keyword/architecture map, the AEO/GEO plan, and the design direction.
2. **The website** — a finished, responsive, conversion-optimized, **beautifully designed** sales site (a single landing page *or* a multi-page site when SEO/GEO/AEO calls for it). Built in one of two **modes**: **launch** (CTAs go to signup/checkout) or **validation / "fake it till you make it"** (the idea is presented as real and every CTA opens a polished, on-brand **email-capture waitlist modal** to measure demand before building). AURORA picks the design language from **50 options** (`design-languages.md`) — the chosen language is a style card driving the hero concept, buttons, panels, and titles (not just color), and real brand logos are used wherever a platform or company appears (`brand-assets.md`).
3. **The technical/discovery files** — `sitemap.xml`, `robots.txt`, `llms.txt`, and **schema.org JSON-LD** embedded in the pages (FAQPage, Product/SoftwareApplication, Organization, BreadcrumbList, HowTo as relevant), plus complete `<head>` SEO/meta/Open Graph.
4. **Ad creatives (on demand)** — when asked ("make N creatives for platform X"), the 5-agent creative squad produces a **creative matrix** + **platform-ready animated video-creatives** at exact resolutions (9:16 1080×1920, 1:1 1080×1080, 4:5 1080×1350, 16:9 1920×1080, Google Display banners) with 3-second hooks for TikTok, Reels, Meta, YouTube, and Google — each visibly different for A/B testing. See `ad-creatives.md`.
5. *(Recommended for substantial projects)* **`design-system.md`** (AURORA's visual + motion spec) and **`discovery.md`** (the SEO/GEO/AEO spec) as standalone files.

Do not stop at advice or an outline. Finished, usable, rankable output is the point.

## The mental model

The 10 Instagram principles ("Dad of Startup") become 10 specialist agents that make the site *convert*. Four more experts make it *get found*: it's not enough to persuade the visitor in front of you — the site must win the visitor before they arrive, whether they search Google or ask an LLM. All 14 are coordinated through one shared **Campaign Brief** so their work locks together: ten strong opinions pulling toward one promise, made visible by four experts who put it where buyers (and AIs) look.

### The roster

**Group A — the 10 sales-psychology agents** (make it convert):

| # | Principle | Agent | Owns |
|---|-----------|-------|------|
| 1 | Buy with emotion, justify with logic | **EMBER** | Emotional core + logical justification stack |
| 2 | Sell the transformation, not the product | **METAMORPH** | Before→After identity shift (canonical) |
| 3 | Solve a pain, don't chase a desire | **LANCE** | Pain excavation and ranking |
| 4 | Solve existing demand | **COMPASS** | Existing demand, search intent, vocabulary |
| 5 | People care how it helps them | **BEACON** | Feature → benefit → outcome |
| 6 | Hit ego and fear together | **EDGE** | Hooks, headlines, tone tokens |
| 7 | Show social proof | **CHORUS** | Proof architecture |
| 8 | Nothing is too expensive for the right customer | **VAULT** | ICP + value-based pricing |
| 9 | Be specific with words and numbers | **PRISM** | Specificity audit |
| 10 | The market isn't saturated; the offer is weak | **FORGE** | The irresistible offer |

**Group B — the 4 discovery-and-design experts** (make it get found, and make it beautiful):

| Discipline | Agent | Owns |
|------------|-------|------|
| SEO (technical + on-page) | **SUMMIT** | Site architecture, page set, on-page + technical SEO, performance |
| GEO (Generative Engine Optimization) | **ECHO** | Being cited inside AI answers — citable claims, entity authority, `llms.txt` |
| AEO (Answer Engine Optimization) | **ORACLE** | Being the direct answer — question→answer set, schema.org JSON-LD |
| UI/UX design + motion | **AURORA** | Bespoke visual identity (picks from 50 design languages) + real brand logos + full, polished motion |

**Group C — the 5 ad-creative agents** (make it spread — on demand):

| Agent | Owns |
|-------|------|
| **REEL** | Creative director — the creative matrix + variety across the set |
| **SPARK** | Hook specialist — the first 3 seconds (the scroll-stopper) |
| **PULSE** | Concept creatives — the whole-idea / brand ads |
| **FACET** | Feature creatives — one creative per feature/angle |
| **FRAME** | Format & platform engineer — renders each as a video-creative at exact platform resolutions |

Full specs (mission, inputs, method, deliverable, hand-offs, failure modes) for all 19 + ATLAS are in **`references/agents.md`** — read it before running. Principle playbooks: **`references/principles.md`**. SEO/GEO/AEO: **`references/discovery-seo-geo-aeo.md`**. Design + motion: **`references/ui-ux-motion.md`**. The 50 design languages: **`references/design-languages.md`**. Ad-creative (UA video) playbook: **`references/ad-creatives.md`**. Real brand logos (YouTube, TikTok, Apple, Google…): **`references/brand-assets.md`**.

## Modes

Decide the **mode** at intake (Brief `mode` field):

- **Launch** — the product exists. CTAs go to signup/checkout/the app. Proof is real (or labeled placeholders).
- **Validation ("fake it till you make it")** — the product is still an idea (the default when nothing is live). Present the concept as if it's real and **capture email to measure demand**: every primary CTA *and* the pricing button open a polished, on-brand **waitlist modal** ("Launching soon — get early access"). Pricing still shows (willingness-at-a-price is part of the test). The success metric is **signups / signup-rate**. The modal must be wired to a real endpoint placeholder and never fake submission — see `website-blueprint.md` (Validation mode). This is the engine for testing an idea before building it.

## The workflow

Agents run in **six phases**, parallel *within* a phase, because later agents need earlier outputs. Coherence comes from the order plus the shared Brief.

```
PHASE 0  Intake ─────────────── ATLAS builds the seed Brief
                                      │
PHASE 1  Ground truth ────────── LANCE ∥ COMPASS ∥ VAULT(ICP)         [parallel]
         "What's real?"               │  pains · demand · who
                                      ▼
PHASE 2  Offer & substance ───── FORGE ∥ METAMORPH ∥ BEACON           [parallel]
         "What do we sell?"           │  offer · transformation · benefits
                                      ▼
PHASE 3  Persuasion ──────────── EMBER ∥ EDGE ∥ CHORUS                [parallel]
         "How do we say it?"          │  emotion+logic · hooks · proof
                                      ▼
PHASE 4  Specificity ─────────── PRISM (audits everything)            [alone]
         "Is it concrete?"            │  numbers, names, no fluff
                                      ▼
PHASE 5  Visibility & Design ─── SUMMIT ∥ ECHO ∥ ORACLE ∥ AURORA      [parallel]
         "Found + beautiful?"         │  SEO architecture · GEO citability
                                      │  AEO schema · design + motion
                                      ▼
PHASE 6  Synthesis ──────────── ATLAS assembles strategy.md + the site
                                 + sitemap/robots/llms.txt + JSON-LD
```

**Why this order.** You cannot optimize a message that doesn't exist yet — SEO/GEO/AEO and design operate on the *finished, specific* messaging (Phases 1–4). ECHO needs PRISM's concrete stats to make citable assets; ORACLE needs the finalized FAQ to build answer schema; AURORA needs EDGE's tone, EMBER's emotion, and METAMORPH's transformation to design something with the right *feeling*; SUMMIT needs COMPASS's demand to decide the page set. Respect the arrows.

### Phases 0–4

Run exactly as before (see `references/agents.md`). Phase 0 intake → seed Brief (infer + flag assumptions; only ask if the product's function is unclear). Phases 1–3 run their agents, **writing each output back into the Brief**. Phase 4 PRISM audits everything for specificity — nothing proceeds until PRISM signs off.

**On Claude.ai there are no real subagents.** Simulate each agent as a focused, single-purpose pass: adopt its mission, read only the Brief sections it needs, produce only its deliverable, append it to the Brief. Do them in phase order.

### Phase 5 — Visibility & Design (the new layer)

Four experts read the finished messaging + Brief and run in parallel. See `references/discovery-seo-geo-aeo.md` and `references/ui-ux-motion.md` for the deep methods.

- **SUMMIT (SEO)** maps keywords/intent to COMPASS's vocabulary, **decides whether one page suffices or a multi-page site is needed** (and specs the page set: e.g. landing + comparison/"alternative-to" pages + use-case pages + an answers hub), and produces the on-page spec (one H1, heading hierarchy, titles, meta, internal links, URLs, alt text) and the technical-SEO checklist (sitemap, robots, canonical, Open Graph, mobile, Core Web Vitals/performance).
- **ECHO (GEO)** makes the content *citable by AI engines*: self-contained, specific, quotable claims (built from PRISM's stats), a clear entity definition of the product, comparison/"best X for Y" structures LLMs extract, an `llms.txt`, and an off-page corroboration plan.
- **ORACLE (AEO)** makes the site *the answer*: harvests the real questions buyers ask, writes answer-first copy (the question answered in the first 1–2 sentences, then expanded), and produces the **schema.org JSON-LD** blocks (FAQPage, Product/SoftwareApplication, Organization, BreadcrumbList, HowTo).
- **AURORA (UI/UX)** derives a **bespoke design language** that reflects the *spirit* of the product (color, type, spacing, signature — grounded in the subject's world, not a generic default), and a **motion system** delivering full juice and polish (load orchestration, scroll reveals, hover micro-interactions, the signature animated moment) — to a high bar, while respecting reduced-motion and performance.

### Phase 6 — Synthesis (ATLAS)

Assemble everything into a coherent, shippable system:
- **`strategy.md`** per `references/strategy-blueprint.md` (now including the Visibility & Discovery section and the design direction).
- **The site** per `references/website-blueprint.md` — single- or multi-page as SUMMIT specced — built to **AURORA's design + motion language** (read `frontend-design/SKILL.md`; `assets/landing-page-template.html` is a scaffold to adapt, not ship as-is), with **ORACLE's JSON-LD** and full `<head>` SEO/meta baked in, **ECHO's citable blocks** placed in the copy, and **SUMMIT's internal links** funnelling to the offer.
- **`sitemap.xml`, `robots.txt`, `llms.txt`** and (recommended) `design-system.md` + `discovery.md`.

Run the **final coherence check** (below), then save and present.

### On demand — Ad creatives (the creative squad)

Separately from the six-phase build, when the user asks for ad creatives ("make N for platform X"), run the **5-agent creative squad** (REEL → SPARK → PULSE/FACET → FRAME), which reuses the Brief (transformation, features, hooks, ICP, proof, design language). It produces the creative matrix + platform-ready animated video-creatives, each visibly different. This typically follows the site (so the Brief and design language exist), but can run anytime the Brief is populated. See `ad-creatives.md`.

## The Campaign Brief (shared artifact)

Maintain one markdown/JSON document all agents read and write. Sections:

```
# Campaign Brief: <Product Name>
## product · assumptions
## icp            [VAULT]   the right customer
## pains          [LANCE]   ranked, with cost of inaction
## demand         [COMPASS] existing demand + buyer vocabulary
## offer          [FORGE]   named offer: deliverable, stack, guarantee, scarcity, price logic
## transformation [METAMORPH] canonical Before→After (single source of truth)
## benefits       [BEACON]  feature → benefit → outcome
## emotional_core [EMBER]   dominant emotion + logical justification stack
## hooks          [EDGE]    headline + sub-hooks (ego+fear) + tone tokens
## proof          [CHORUS]  proof architecture (real or labeled placeholders)
## pricing        [VAULT]   price, anchor, payment options
## one_promise    [ATLAS]   the single promise the campaign makes
## specificity_log[PRISM]   before/after edits
## seo            [SUMMIT]  keyword/intent map · page architecture (1 page or N) · on-page + technical SEO spec
## geo            [ECHO]    citable claims/stats · entity definition · llms.txt · corroboration plan
## aeo            [ORACLE]  question→answer set · schema.org JSON-LD inventory · answer-first patterns
## mode           [ATLAS]   launch | validation (waitlist) — default validation when no live product
## design_language[AURORA]  chosen language(s) from the 50 (+ why) · style card (hero/buttons/panels/titles) · material system (radius/border/shadow/button/surface)
## design_system  [AURORA]  color/type/space tokens · signature · motion spec
## creatives      [REEL]    (on demand) the creative matrix: angle × platform × format × hook × design treatment
```

## Coordination & conflict-resolution rules

Apply in order when agents clash:

1. **One source of truth** — the Brief. No agent contradicts an established fact; escalate to ATLAS to revise it.
2. **One promise** — the whole site (and every page) asserts one core promise (`one_promise`).
3. **Canonical ownership** — METAMORPH owns the transformation; EDGE owns tone; VAULT owns customer + price; AURORA owns the visual/motion language; SUMMIT owns site architecture. Others reference, never redefine.
4. **Priority of truth** — ICP (VAULT) ▸ Pain (LANCE) ▸ Offer (FORGE) ▸ Messaging ▸ Decoration.
5. **Specificity gate** — no claim ships without a number, name, or checkable proof (PRISM). (This also feeds ECHO: specifics are what AI engines cite.)
6. **Honesty gate** — never fabricate proof, stats, testimonials, scarcity, **or fake reviews/ratings/schema**. Schema markup must describe what's truly on the page; false structured data is both dishonest and penalized.
7. **Visibility serves conversion (new)** — SEO/GEO/AEO never override the persuasion arc or flatten the hook. The H1 stays a hook (EDGE); ORACLE's answer-first sentence *supports* it, it doesn't replace it. No keyword stuffing, no answer-formatting that kills emotion. Ranking is worthless if the page doesn't convert.
8. **Polish with restraint, never at the cost of speed or access (new)** — AURORA's juice serves the message (Chanel's "remove one accessory"). Motion must respect `prefers-reduced-motion`, must not cause layout shift, and must not harm Core Web Vitals (SUMMIT's concern) — AURORA and SUMMIT coordinate so beauty and performance coexist.

## Final coherence check (before presenting)

**Conversion:**
- [ ] One promise across hero, offer name, and final CTA — on every page.
- [ ] Leads with the sharpest pain (LANCE); sells the transformation (METAMORPH), not features.
- [ ] Every feature paired with a buyer outcome (BEACON); emotion + logic both present (EMBER); ego+fear in the hero (EDGE).
- [ ] Proof beside every ask (CHORUS), real or clearly-labeled. Strong offer (FORGE), value-anchored price (VAULT).
- [ ] PRISM sign-off: nothing generic left un-quantified.

**Visibility:**
- [ ] **SEO** — exactly one H1 per page; logical heading hierarchy; unique title + meta description per page; clean URLs; internal links funnel to the offer; image alt text; `sitemap.xml` + `robots.txt` present; canonical + Open Graph/Twitter tags in `<head>`.
- [ ] **Performance** — no render-blocking bloat, no layout shift, fast first paint (Core Web Vitals friendly).
- [ ] **AEO** — key pages answer their question in the first 1–2 sentences; valid schema.org JSON-LD present (FAQPage + Product/SoftwareApplication + Organization at minimum); FAQ content matches FAQPage markup exactly.
- [ ] **GEO** — specific, self-contained, citable stat/claim lines present; a clear entity definition of the product; `llms.txt` present; a corroboration plan exists in the strategy.
- [ ] **Multi-page (if used)** — each supporting page is answer-first, internally linked, and funnels to conversion; no thin/duplicate pages.

**Design:**
- [ ] **Not the default direction** — not the first aesthetic an AI reaches for (not the dark-SaaS-neon / soft-pastel / editorial-serif / gradient-everything defaults, not the centered-headline-+-two-buttons-+-3-cards template). A point of view a human designer would choose for *this* product.
- [ ] **Typography** — a clean modern grotesque workhorse (Inter or an Inter-family-style peer) for body and headings; **no** novelty/decorative-serif/trendy-display font doing the heavy lifting; character earned from scale, weight contrast, and tracking. A mono/second face only with a real reason.
- [ ] **Original components** — 2–3 genuinely custom, branded elements; bullets, cards, steppers/progress, stats, and icons are not the generic defaults (check-circles, identical gradient-card trios, flat bars, stock line icons).
- [ ] Full, polished motion: a deliberate load sequence, scroll reveals, hover micro-interactions, a signature moment — executed with restraint.
- [ ] Quality floor: responsive to mobile, visible keyboard focus, `prefers-reduced-motion` respected, semantic HTML, sufficient contrast.
- [ ] **The glance test** — a discerning designer would not flag it as AI-generated at a glance.
- [ ] **Real brand logos** — every social platform / company reference (rows, "publish to / sign in with / download on" CTAs, footers) uses the official logo in its correct mark and color (`brand-assets.md`), never emoji or letters; sign-in/store CTAs follow Apple/Google guidelines.
- [ ] **Style-card consistency** — hero concept, buttons, panels, and titles all reflect the one chosen design language (not a mix of defaults).

**Validation mode (if used):**
- [ ] Every primary CTA *and* the pricing button open the on-brand email-capture modal (not checkout).
- [ ] The modal matches the chosen design language, is accessible (focus trap, ESC, backdrop close, restored focus, reduced-motion), has a success state, and is wired to a real endpoint placeholder — submission is never faked.
- [ ] The strategy states the success metric (signups / signup-rate) and the traffic plan.

**Ad creatives (if produced):**
- [ ] Each creative is rendered at the exact platform resolution with critical text inside safe zones, sound-off legible (captions), a 3-second hook, and an end-card CTA.
- [ ] Every creative differs from the others on ≥2 axes (angle, hook type, design treatment) — real A/B alternatives, not reskins.
- [ ] In validation mode, creative CTAs point to the waitlist. No fabricated stats/testimonials in any creative.
- [ ] Each creative's motion matches the chosen design language's **video idiom** (e.g. typewriter/glitch for terminal, slam-cuts for bold, Ken-Burns for premium) using the effects toolkit — juicy but not over-stuffed, reduced-motion-safe in preview.
- [ ] Platform mentions in creatives use **real brand logos** (`brand-assets.md`), not emoji; end-card store/sign-in CTAs use official badges/buttons.

## Reference files — read these

| File | When |
|------|------|
| `references/agents.md` | Before running — full spec for all 19 agents + ATLAS |
| `references/principles.md` | Applying a sales principle |
| `references/discovery-seo-geo-aeo.md` | Phase 5 — SEO architecture, GEO citability, AEO schema (with copy-paste JSON-LD, llms.txt, sitemap, robots templates) |
| `references/ui-ux-motion.md` | Phase 5 — deriving the design language + the juice/polish motion system |
| `references/design-languages.md` | Phase 5 — the catalog of 50 design languages AURORA selects from or mixes (each a style card driving hero/buttons/panels/titles + video idiom) |
| `references/brand-assets.md` | Real, official brand logos (verified SVGs + colors) + Apple/Google sign-in & store-badge rules |
| `references/ad-creatives.md` | On demand — the UA ad-creative (video) playbook: squad, hooks, platform specs, the animated HTML technique, the creative matrix |
| `references/strategy-blueprint.md` | Phase 6 — structuring `strategy.md` |
| `references/website-blueprint.md` | Phase 6 — single- or multi-page section map + where schema/meta/design go |
| `references/copy-craft.md` | Writing copy — formulas, ego+fear, proof, specificity |
| `assets/landing-page-template.html` | An annotated scaffold to adapt (re-skin per AURORA) |
| `examples/worked-example.md` | A full end-to-end run |

## Output instructions

Save `strategy.md`, the site page(s) (`index.html` + any supporting pages), `sitemap.xml`, `robots.txt`, `llms.txt` (and `design-system.md` / `discovery.md` if produced) to the outputs directory and present them. Lead with the main page (what the user most wants to see), then the strategy, then the rest. Keep the closing note short.

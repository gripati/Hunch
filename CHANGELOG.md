# Changelog

## [1.1.0] — Juice & polish: no more static pages

The generated sites were technically correct but visually **static** — a fade-up on load and a hover lift were the whole motion system. 1.1.0 raises the motion bar to the level of the best React motion libraries ([Skiper UI](https://skiper-ui.com), [Cult UI](https://www.cult-ui.com), [Style UI](https://www.styleui.dev), [Watermelon UI](https://ui.watermelon.sh)) — **re-expressed as dependency-free vanilla CSS/JS** so it drops straight into the single-file pages Hunch ships.

- **New reference — `hunch/references/motion-toolkit.md` (The Juice Toolkit)** — ~30 copy-paste, reduced-motion-safe recipes: the reveal harness, word/char text reveals, typewriter, scramble/decode, count-up number tickers, gradient shimmer text, magnetic buttons, shimmer & border-beam CTAs, cursor-tracked spotlight cards, 3D-tilt cards, animated aurora/mesh backgrounds, dot-grid cursor spotlights, scroll-stacking cards, clip-path image reveals, parallax, sticky-condense nav, scroll progress, marquees, image cursor trails, dynamic-island morphs, and a before→after drag slider — plus a **Signature-juice-by-family** map routing each of the 50 design languages to its motion.
- **The juice contract** — every page now ships a baseline (reveal harness driving the hero load sequence *and* scroll reveals) + live micro-interactions on every button/card + one ambient background + one scroll-choreography move + exactly one signature moment that *demonstrates the product*. Codified in `ui-ux-motion.md` §5, AURORA's spec, and the final coherence check. Two failure modes are now called out: **too static** (the old tell) and **over-juiced** (its opposite).
- **`design-languages.md`** — each language now carries a **signature-juice** dimension mapped to the toolkit, alongside its existing material and video idioms.
- **Rebuilt `assets/landing-page-template.html`** — the scaffold now demonstrates the baseline juice (animated aurora hero, word-reveal headline, count-up stats, magnetic CTA, spotlight cards, sticky-condense nav, scroll progress) — verified in-browser, and fully neutralized under `prefers-reduced-motion`.

## [1.0.0] — First public release

Hunch validates a startup idea before you build it: describe an idea, get a complete, real-looking landing page with an email waitlist at every call-to-action, so you can measure genuine demand.

- **Validation mode ("fake it till you make it")** — every CTA and the pricing button open a polished, on-brand email-capture waitlist modal; the success metric is signups.
- **Launch mode** — when the product exists, CTAs go to signup/checkout.
- **19 coordinated agents** orchestrated by ATLAS: 10 sales-psychology specialists, 4 discovery/design experts (SEO, GEO, AEO, and a UI/UX + motion designer), and a 5-agent ad-creative squad.
- **50 design languages** — each a "style card" driving the hero, buttons, panels, titles, motion, and ad-creative video idiom. Output is bespoke per idea, not templated.
- **SEO / GEO / AEO** — sitemap, robots, llms.txt, and schema.org JSON-LD so the page is found by search engines and AI answer engines.
- **Ad creatives on demand** — platform-ready 9:16 / 1:1 / 4:5 / 16:9 video creatives with 3-second hooks for TikTok, Reels, Meta, YouTube, and Google, each visibly different for A/B testing.
- **Real brand logos** — verified official SVGs (Simple Icons, CC0) with brand colors and Apple/Google sign-in & app-store-badge rules.
- **Honesty gate** — never fabricates proof, testimonials, statistics, or scarcity; the waitlist actually collects email.

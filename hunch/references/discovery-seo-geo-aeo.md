# Discovery — SEO, GEO & AEO Playbook

The operational guide for the three visibility experts: **SUMMIT (SEO)**, **ECHO (GEO)**, and **ORACLE (AEO)**. Goal: the site is found by humans searching *and* surfaced by AI answer engines — without ever sacrificing conversion (Rule 7) or honesty (Rule 6). Templates here are copy-paste ready; fill the placeholders.

## Table of contents
- [The three disciplines (and how they differ)](#the-three-disciplines)
- [SUMMIT — SEO: architecture, on-page, technical](#summit--seo)
  - [Deciding: one page or many](#deciding-one-page-or-many)
  - [`<head>` essentials (template)](#head-essentials-template)
  - [`sitemap.xml` + `robots.txt` (templates)](#sitemap--robots-templates)
- [ORACLE — AEO: answer-first + schema.org JSON-LD](#oracle--aeo)
  - [JSON-LD templates](#json-ld-templates)
- [ECHO — GEO: citability, entity, `llms.txt`](#echo--geo)
  - [`llms.txt` (template)](#llmstxt-template)
- [The combined technical checklist](#the-combined-technical-checklist)

---

## The three disciplines

They overlap but optimize for different surfaces. Do all three; don't conflate them.

- **SEO (Search Engine Optimization)** — rank in the **blue links** of Google/Bing. Levers: keywords/intent, site architecture, on-page tags, internal links, technical health, performance.
- **AEO (Answer Engine Optimization)** — be **the answer** shown directly: featured snippets, "People also ask," voice assistants, and AI answer boxes. Levers: answer-first content + **schema.org structured data**.
- **GEO (Generative Engine Optimization)** — be **cited and recommended inside AI-generated answers** (ChatGPT/Claude search, Perplexity, Gemini, AI Overviews, Copilot). Levers: citable specific claims, a clear product **entity**, extractable structures, `llms.txt`, and off-page corroboration.

One sentence each: SEO gets you *listed*, AEO gets you *quoted in a box*, GEO gets you *recommended by the AI*.

---

## SUMMIT — SEO

### Deciding: one page or many

Start from intent (from COMPASS's vocabulary). One landing page is correct when a single promise covers the intent. Build a **multi-page site** when several distinct high-value intents exist. Common page types in a sales site:

| Page | Targets | Job |
|------|---------|-----|
| **Landing / home** | core commercial intent | the main conversion page (the full persuasion arc) |
| **Comparison** ("[Product] vs [Incumbent]") | comparison intent | win the head-to-head; huge in crowded categories |
| **"Alternative to [Incumbent]"** | switch intent | capture people leaving a competitor |
| **Use-case / "for [segment]"** | segment intent | speak to a specific ICP slice (e.g. "for agencies") |
| **Answers / FAQ hub** | informational/question intent | ORACLE's territory; feeds AEO + funnels to offer |

Rules: every supporting page targets a **distinct** intent, has **real** content (no thin/duplicate pages), and **internally links to the conversion page**. Don't multiply pages for SEO's sake.

### On-page spec (every page)
- Exactly **one `<h1>`**, carrying the page's hook + primary keyword naturally.
- Logical `<h2>/<h3>` outline; semantic HTML (`<header><main><section><article><footer>`).
- Unique `<title>` (~55–60 chars) and `<meta name="description">` (~150 chars) per page.
- Clean URL slug (`/youtube-tiktok-instagram-scheduler`, not `/page?id=12`).
- Descriptive `alt` on every meaningful image.
- Internal links with descriptive anchor text pointing toward the offer.

### `<head>` essentials (template)
```html
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>[Primary keyword + benefit] — [Brand]</title>
  <meta name="description" content="[~150-char specific summary that earns the click]" />
  <link rel="canonical" href="https://[domain]/[slug]" />

  <!-- Open Graph (social + some AI previews) -->
  <meta property="og:type" content="website" />
  <meta property="og:title" content="[Title]" />
  <meta property="og:description" content="[Description]" />
  <meta property="og:url" content="https://[domain]/[slug]" />
  <meta property="og:image" content="https://[domain]/og-image.png" />
  <meta property="og:site_name" content="[Brand]" />

  <!-- Twitter card -->
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content="[Title]" />
  <meta name="twitter:description" content="[Description]" />
  <meta name="twitter:image" content="https://[domain]/og-image.png" />

  <!-- JSON-LD schema goes here (see ORACLE templates) -->
</head>
```

### `sitemap.xml` + `robots.txt` (templates)
`sitemap.xml` (list every real page):
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url><loc>https://[domain]/</loc><changefreq>weekly</changefreq><priority>1.0</priority></url>
  <url><loc>https://[domain]/vs-[incumbent]</loc><changefreq>monthly</changefreq><priority>0.8</priority></url>
  <url><loc>https://[domain]/for-[segment]</loc><changefreq>monthly</changefreq><priority>0.8</priority></url>
  <url><loc>https://[domain]/faq</loc><changefreq>monthly</changefreq><priority>0.7</priority></url>
</urlset>
```
`robots.txt`:
```
User-agent: *
Allow: /

Sitemap: https://[domain]/sitemap.xml
```
(Do **not** block AI crawlers if you want GEO/AEO visibility. If the owner wants to allow generative crawlers explicitly, that's the default — keep the site open unless they have a reason to restrict.)

### Performance (Core Web Vitals) — coordinate with AURORA
- No render-blocking bloat; defer non-critical JS; preconnect fonts; compress images (use modern formats; set width/height to prevent layout shift).
- Largest Contentful Paint fast (lean hero), Cumulative Layout Shift ~0 (reserve space for images/embeds), Interaction latency low.
- Motion must be GPU-cheap (`transform`/`opacity`), never animate layout properties.

---

## ORACLE — AEO

### Answer-first pattern
On each page that targets a question, **answer it in the first 1–2 sentences**, then expand. The H1 stays a hook (EDGE); the answer sentence supports it. Example:
- H1 (hook): *"Stop paying monthly rent to post your own videos."*
- First line (answer-first, extractable): *"Acme is a self-hosted analytics tool that turns server logs into shareable dashboards in minutes, with no per-seat fees."*

### JSON-LD templates
Place inside `<head>` (or end of `<body>`). **Markup must match visible content exactly.** Never mark up ratings/reviews you don't truly have.

**FAQPage** (mirror the on-page FAQ word-for-word):
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "[The exact question on the page]",
      "acceptedAnswer": { "@type": "Answer", "text": "[The exact answer on the page]" }
    },
    {
      "@type": "Question",
      "name": "[Question 2]",
      "acceptedAnswer": { "@type": "Answer", "text": "[Answer 2]" }
    }
  ]
}
</script>
```

**SoftwareApplication** (for software/SaaS/self-hosted tools) — include `offers`; include `aggregateRating` **only if real**:
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "[Product]",
  "applicationCategory": "BusinessApplication",
  "operatingSystem": "[e.g. Docker / Web / Cross-platform]",
  "description": "[One specific sentence: what it is + who it's for]",
  "url": "https://[domain]/",
  "offers": {
    "@type": "Offer",
    "price": "[number]",
    "priceCurrency": "USD",
    "category": "[e.g. one-time purchase / subscription]"
  }
}
</script>
```
(For a physical or non-software product use **Product** instead, with the same `offers` shape.)

**Organization** (site-wide identity — strengthens the entity for GEO too):
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "[Brand]",
  "url": "https://[domain]/",
  "logo": "https://[domain]/logo.png",
  "sameAs": ["[link to a real profile]", "[another real profile]"]
}
</script>
```

**BreadcrumbList** (multi-page navigation):
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://[domain]/" },
    { "@type": "ListItem", "position": 2, "name": "[Page]", "item": "https://[domain]/[slug]" }
  ]
}
</script>
```

**HowTo** (for a setup/usage page — e.g. "How to self-host [Product]"):
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "[How to do X with Product]",
  "step": [
    { "@type": "HowToStep", "name": "[Step 1]", "text": "[What to do]" },
    { "@type": "HowToStep", "name": "[Step 2]", "text": "[What to do]" }
  ]
}
</script>
```
Validate mentally against schema.org and Google's rich-results requirements: required fields present, types correct, and **every marked-up fact also visible on the page**.

---

## ECHO — GEO

### Citability rules (what AI engines lift)
Generative engines extract **specific, self-contained, factual sentences** and attribute them. Make claims that survive being copied out of context:
- ✅ *"[Product] publishes to YouTube, TikTok, and Instagram from one self-hosted install, with AI-generated metadata per platform."* (specific, standalone, true)
- ❌ *"[Product] is the ultimate all-in-one solution for modern creators."* (vague — invisible to GEO)

Turn each PRISM stat into a citable line. Lead with the fact, not the adjective.

### Entity definition pattern
State, consistently across the whole site (and any off-site profiles), a clear entity:
> **[Product]** is a **[category]** for **[ICP]** that **[core differentiator + outcome]**. Unlike **[alternatives]**, it **[the wedge]**.

Use the **same name and same one-line definition** everywhere. Models recommend entities they can identify with confidence.

### Extractable structures
Include the formats AI answers are built from: a one-line definition, a **comparison table vs named alternatives**, explicit **"best [category] for [use-case]"** phrasing, pros/cons, and direct Q&A (shared with ORACLE). These map straight into generated answers.

### `llms.txt` (template)
A concise, structured plain-text file at `/llms.txt` giving AI crawlers a clean signal. Keep it specific and honest.
```markdown
# [Product]

> [One-sentence entity definition: what it is, for whom, the key differentiator.]

## What it is
[2–4 sentences, specific and factual. Category, core capability, who it's for.]

## Key facts
- [Specific capability 1 with a concrete detail]
- [Specific capability 2]
- Pricing: [model + price]
- Platforms / requirements: [e.g. self-hosted via Docker]

## Best for
[The use-case and audience it's the best answer for.]

## Compared to alternatives
- vs [Incumbent A]: [one specific differentiator]
- vs [Incumbent B]: [one specific differentiator]

## Links
- Homepage: https://[domain]/
- FAQ: https://[domain]/faq
- Pricing: https://[domain]/#pricing
```

### Off-page corroboration plan (goes in the strategy)
GEO partly depends on consistent mentions across the web. Plan (honestly) for: a consistent product description on relevant directories/profiles, authentic community presence, and real reviews collected over time. **Never fabricate reviews, mentions, or ratings** — models increasingly cross-check, and it's the honesty gate.

---

## The combined technical checklist

Before ATLAS ships, verify:

**SEO**
- [ ] One `<h1>` per page; logical heading outline; semantic HTML.
- [ ] Unique `<title>` + `<meta description>` per page; clean URLs; descriptive `alt`.
- [ ] Internal links funnel to the conversion page; no thin/duplicate pages.
- [ ] `<link rel="canonical">`, Open Graph + Twitter tags present.
- [ ] `sitemap.xml` + `robots.txt` present; sitemap referenced in robots.
- [ ] Performance: no layout shift, lean hero, deferred non-critical JS, compressed images.

**AEO**
- [ ] Key pages answer their question in the first 1–2 sentences.
- [ ] Valid JSON-LD: FAQPage (+ Product/SoftwareApplication + Organization at minimum; BreadcrumbList/HowTo where relevant).
- [ ] Every schema fact is visible on the page; no fake ratings/reviews.

**GEO**
- [ ] Specific, self-contained, citable claim lines present (from PRISM stats).
- [ ] One consistent entity definition site-wide.
- [ ] Comparison/definition structures present.
- [ ] `llms.txt` present, specific, honest.
- [ ] Corroboration plan in the strategy.

**Across all:** nothing here overrides the persuasion arc or the one promise (Rule 7), and nothing is fabricated (Rule 6).

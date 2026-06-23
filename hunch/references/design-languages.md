# 50 Design Languages — AURORA's Palette of Directions

AURORA does not have one house style. It chooses, per product, the design language whose *spirit* fits — or composes a tasteful **mix** of two — and then commits that language across the **whole build**. Two sites from this skill should look like they came from two different studios.

**A chosen language is a full "style card." It drives — specifically, not just color:**
- **Hero concept** — the layout idea and centerpiece (a terminal, a product stage, a giant type slab, a bento wall, a blueprint, a 3D scene…).
- **Buttons** — shape, border, shadow, fill, and press behavior (hard-offset block vs frosted capsule vs glossy pill vs outline-glow).
- **Panels / cards** — radius, border, shadow, surface treatment, and whether they look like the product's real artifacts.
- **Titles / type** — the type system, weights, scale, and tracking idiom.
- **Motion** — the easing/transition personality (snappy vs floaty vs glitchy vs physical).
- **The ad-creative video idiom** — how its video creatives cut, transition, and animate text (see "Per-style video idioms" below and `ad-creatives.md`). The same product gets a *different* feeling site **and** a different feeling video per language.

**Vary the material system per project** — corner-radius, borders, shadows, button shape, and surfaces must visibly differ across builds (0px hard edges here, 24px pillowy there). Sameness of radius/shadow is itself an AI tell.

**How to use this file**
1. Read the product's spirit (from `ui-ux-motion.md` §1) and pick the **2–3 candidate languages** that fit. Reject the first/obvious one if it's the default for that product category.
2. Choose **one** to lead, or a deliberate **mix** (e.g. "minimal base + one neo-brutalist accent moment"). State the choice and why.
3. Pull that language's **radius / border / shadow / button / surface / color / type / motion** traits into the design tokens. **Vary these per project** — a site should not always use the same 12px radius and soft shadow.
4. For **ad creatives**, rotate the visual treatment across languages so each creative in a set looks different (see `ad-creatives.md`).

Each entry: *When to use* + the concrete material traits. Traits are starting points — tune to the brief.

---

## The catalog

### 1. Neo-brutalism
*When:* bold, confident, "we don't need to be polite" products; dev tools, indie, statements.
Radius **0** · Borders **thick solid black (2–4px)** · Shadows **hard offset, no blur (e.g. 6px 6px 0 #000)** · Buttons **chunky, bordered, flat, shift-on-press** · Surfaces **flat solid blocks** · Color **high-contrast, clashing brights on off-white** · Type **heavy grotesque, oversized** · Motion **snappy, abrupt, no easing softness**.

### 2. Glassmorphism
*When:* modern tech, layered depth, premium overlays.
Radius **large (18–28px)** · Borders **1px translucent white** · Shadows **soft, broad, low-opacity** · Buttons **frosted translucent, subtle border** · Surfaces **blurred translucent panels (backdrop-filter)** over a colorful/gradient bg · Color **cool, luminous** · Type **clean sans** · Motion **smooth float, parallax depth**.

### 3. Modern minimal
*When:* most professional products that want to feel current and uncluttered.
Radius **medium (10–14px)** · Borders **hairline** · Shadows **subtle** · Buttons **solid, restrained** · Surfaces **lots of whitespace, few elements** · Color **restrained, 1 accent** · Type **clean grotesque, strong scale** · Motion **gentle reveals**.

### 4. Swiss / International
*When:* objective, editorial, trustworthy, content-forward.
Radius **0 or 2px** · Borders **thin rules** · Shadows **none** · Buttons **square, text-driven** · Surfaces **strict grid, flush-left** · Color **red/black/white or one accent** · Type **Helvetica-like, rigorous hierarchy** · Motion **minimal, precise**.

### 5. Editorial / magazine
*When:* story-led, thought-leadership, lifestyle.
Radius **0–6px** · Borders **hairlines** · Shadows **none** · Buttons **understated, often text links** · Surfaces **asymmetric columns, pull quotes** · Color **paper + ink + 1 accent** · Type **serif display + sans body, big sizes** · Motion **slow, elegant**.

### 6. Soft / friendly
*When:* consumer apps, wellness, approachable services, families.
Radius **large (16–24px) everywhere** · Borders **none/soft** · Shadows **soft, warm** · Buttons **pill, rounded, gentle lift** · Surfaces **rounded cards, airy** · Color **warm pastels** · Type **rounded/humanist sans** · Motion **bouncy-soft**.

### 7. Bento
*When:* feature-rich products, dashboards, "everything in one place" stories.
Radius **medium-large** · Borders **subtle** · Shadows **light** · Buttons **clean** · Surfaces **modular tile grid of varied sizes, each a self-contained unit** · Color **neutral base + per-tile accents** · Type **clean sans** · Motion **tiles reveal/hover individually**.

### 8. Claymorphism
*When:* playful, tactile, kids/casual, friendly fintech.
Radius **very large (20–32px)** · Borders **none** · Shadows **double — soft outer + soft inner highlight (puffy 3D)** · Buttons **puffy, pressable** · Surfaces **inflated soft shapes** · Color **soft pastels, candy** · Type **rounded** · Motion **squishy press**.

### 9. Tactile / skeuomorphic-lite
*When:* products that benefit from real-world familiarity; audio, tools, hardware.
Radius **medium** · Borders **subtle bevel** · Shadows **inner + outer for depth** · Buttons **physical, gradient, press-in** · Surfaces **subtle material gradients/texture** · Color **material-true** · Type **legible sans** · Motion **physical, weighted**.

### 10. Dark techno / cyber
*When:* developer, security, crypto, AI infra.
Radius **small (4–8px)** · Borders **thin glowing accent** · Shadows **accent glow** · Buttons **outline + glow, mono labels** · Surfaces **near-black + grid lines, HUD panels** · Color **dark base + neon accent** · Type **grotesque + mono** · Motion **scan, flicker, type-on**.

### 11. Retro terminal / CRT
*When:* self-hosted, hacker, indie dev, ownership/control narratives.
Radius **0–4px** · Borders **mono rules** · Shadows **none (or scanline texture)** · Buttons **bracketed `[ run ]`, mono** · Surfaces **near-black warm, phosphor text** · Color **amber/green on dark** · Type **monospace throughout** · Motion **caret blink, type-out, boot sequence**.

### 12. Y2K / frutiger aero
*When:* nostalgic-optimistic, playful tech, gen-z/social.
Radius **large, glossy** · Borders **light, chrome** · Shadows **glossy reflections** · Buttons **aqua-gloss, bubbly** · Surfaces **glassy, water/sky imagery** · Color **aqua, lime, sky blue** · Type **rounded techno** · Motion **shiny, bouncy**.

### 13. Vaporwave / synthwave
*When:* music, nightlife, retro-future, bold creative brands.
Radius **varies** · Borders **neon glow** · Shadows **neon bloom** · Buttons **neon outline** · Surfaces **grid horizon, sunset gradients** · Color **magenta/cyan/purple** · Type **80s display** · Motion **grid scroll, glow pulse**.

### 14. Memphis / playful geometric
*When:* youthful, creative, events, fun consumer.
Radius **mixed** · Borders **bold** · Shadows **flat** · Buttons **bold, geometric** · Surfaces **squiggles, dots, clashing shapes scattered** · Color **bold primaries + black** · Type **bold playful** · Motion **pop, wiggle**.

### 15. Raw / HTML-brutalist
*When:* anti-design statements, ultra-indie, intentionally unpolished.
Radius **0** · Borders **default** · Shadows **none** · Buttons **system/underlined links** · Surfaces **unstyled blocks** · Color **default link blue / minimal** · Type **system fonts, Times/Courier** · Motion **none**.

### 16. Refined SaaS (the polished take)
*When:* B2B products that must feel trustworthy and current — done *well*, not the default.
Radius **medium** · Borders **hairline** · Shadows **layered subtle** · Buttons **solid + clear secondary** · Surfaces **clean sections, one signature device** · Color **confident non-generic accent (avoid default violet)** · Type **crafted grotesque** · Motion **purposeful, restrained**.

### 17. Luxury / premium
*When:* high-ticket, fashion, fine products, exclusivity.
Radius **0–4px** · Borders **fine gold/ink rules** · Shadows **none/whisper** · Buttons **thin outline, lots of letter-spacing** · Surfaces **vast whitespace** · Color **black/cream/gold or deep jewel** · Type **elegant thin serif + refined sans** · Motion **slow, deliberate, fades**.

### 18. Organic / natural
*When:* sustainability, food, wellness, craft.
Radius **soft, irregular (blob)** · Borders **soft** · Shadows **soft earthy** · Buttons **rounded, earthy** · Surfaces **organic shapes, texture** · Color **earth tones, greens, clay** · Type **humanist** · Motion **gentle, flowing**.

### 19. Maximalist
*When:* expressive brands that want to overwhelm (positively) and stand out hard.
Radius **mixed** · Borders **layered** · Shadows **stacked** · Buttons **loud** · Surfaces **dense, layered, patterned** · Color **rich, many** · Type **mixed weights/families, big** · Motion **lots, choreographed**.

### 20. Aurora / mesh gradient
*When:* modern AI/creative tools, dreamy/innovative positioning (used tastefully).
Radius **medium-large** · Borders **soft/none** · Shadows **soft glow** · Buttons **gradient or glass** · Surfaces **soft animated mesh gradients behind clean content** · Color **multi-hue soft gradients** · Type **clean sans** · Motion **slow gradient drift**.

### 21. Monochrome / duotone
*When:* graphic, confident, photography-led, editorial brands.
Radius **per-context** · Borders **strong in the single hue** · Shadows **flat** · Buttons **inverted blocks** · Surfaces **one hue range or two-color system** · Color **1–2 colors only** · Type **strong contrast** · Motion **crisp**.

### 22. Newspaper / print
*When:* media, archives, intellectual/credible content.
Radius **0** · Borders **column rules** · Shadows **none** · Buttons **text/inline** · Surfaces **multi-column, masthead** · Color **black/white/news** · Type **serif headlines, dense body** · Motion **none/subtle**.

### 23. Game UI / arcade
*When:* games, esports, gamified products, energy.
Radius **medium, beveled** · Borders **bold outlines/strokes** · Shadows **drop + glow** · Buttons **badge-like, energetic, press states** · Surfaces **HUD panels, bars, frames** · Color **vibrant, high-energy** · Type **bold display + numeric** · Motion **punchy, particle, score pops**.

### 24. Casual mobile-game
*When:* casual/hyper-casual, kids, fun apps.
Radius **very large** · Borders **chunky colored** · Shadows **bold soft** · Buttons **big candy, bouncy** · Surfaces **bright rounded** · Color **candy, saturated** · Type **rounded heavy** · Motion **juicy bounce, squash/stretch**.

### 25. Product / hardware showcase
*When:* physical products, devices, anything where the object is the hero.
Radius **medium** · Borders **minimal** · Shadows **dramatic product shadow** · Buttons **clean, secondary to the product** · Surfaces **clean stage, dramatic lighting, big imagery** · Color **neutral stage + product color** · Type **clean** · Motion **product rotate/zoom, parallax**.

### 26. Data / dashboard
*When:* analytics, fintech, ops, B2B data products.
Radius **small-medium** · Borders **fine grid** · Shadows **flat** · Buttons **compact** · Surfaces **dense panels, charts, tables** · Color **neutral + status colors** · Type **sans + mono numerals** · Motion **data count-up, chart draw**.

### 27. Hand-drawn / sketch
*When:* approachable, education, creative tools, human brands.
Radius **wobbly** · Borders **sketchy/marker** · Shadows **doodle** · Buttons **hand-drawn outline** · Surfaces **notebook/paper texture** · Color **marker brights on paper** · Type **handwritten + clean body** · Motion **draw-on, wobble**.

### 28. Paper / collage
*When:* craft, indie, editorial-creative, zine energy.
Radius **torn/irregular** · Borders **cut edges, tape** · Shadows **layered paper** · Buttons **cut-out** · Surfaces **layered textured cutouts** · Color **muted print + spot** · Type **mixed, stamped** · Motion **paper shift, peel**.

### 29. Spatial / soft depth (visionOS-like)
*When:* cutting-edge, premium, future-facing apps.
Radius **very large** · Borders **soft translucent** · Shadows **soft ambient depth** · Buttons **glassy capsules** · Surfaces **deep translucency, floating layers, light materials** · Color **light, airy, low-sat** · Type **clean sans** · Motion **depth, gentle float, focus shifts**.

### 30. Editorial-brutalist hybrid
*When:* design-forward brands wanting tension and a point of view (a "designer mix").
Radius **0 + occasional large** · Borders **thick + hairline together** · Shadows **flat or hard** · Buttons **oversized type buttons** · Surfaces **big type + raw asymmetric grid + one accent moment** · Color **mostly mono + one loud accent** · Type **huge grotesque, tight tracking** · Motion **bold, intentional**.

### 31. Cyberpunk / neon-noir
*When:* edgy tech, crypto, nightlife, gaming, AI with attitude.
Radius **small, clipped corners** · Borders **neon hairline + glitch** · Shadows **neon bloom** · Buttons **angular, clipped, glitch-hover** · Surfaces **dark city, holographic panels, dense overlays** · Color **black + magenta/cyan/acid-yellow** · Type **condensed + mono, glitchy** · Motion **glitch, scanline, flicker**.
▸ Hero/video: a holographic HUD over a dark scene; video uses glitch cuts, RGB-split text, scanline wipes.

### 32. Art Deco
*When:* luxury, hospitality, spirits, premium events, finance with class.
Radius **0, stepped/chevron corners** · Borders **fine gold rules, symmetrical frames** · Shadows **none** · Buttons **outlined, gold, letter-spaced** · Surfaces **symmetrical, ornamental dividers, fan motifs** · Color **black/cream + gold/emerald** · Type **high-contrast deco serif + elegant sans** · Motion **slow, gilded reveals**.
▸ Hero/video: a centered symmetrical title in a gold frame; video uses elegant fades and gold-line draw-ons.

### 33. Bauhaus
*When:* design-led brands, education, culture, bold-but-rational.
Radius **0 + perfect circles** · Borders **bold geometric** · Shadows **flat** · Buttons **primary-color blocks** · Surfaces **circle/square/triangle compositions on a grid** · Color **red/yellow/blue + black/white** · Type **geometric grotesque** · Motion **constructed, modular slides**.
▸ Hero/video: primary shapes assembling into a composition; video animates shapes sliding/rotating into place.

### 34. Concrete / architectural
*When:* studios, architecture, heavy industry, serious craft.
Radius **0** · Borders **thick, structural** · Shadows **deep cast** · Buttons **monolithic blocks** · Surfaces **raw concrete texture, monumental scale** · Color **greys + one raw accent** · Type **huge structural grotesque** · Motion **weighty, slow slabs**.
▸ Hero/video: a monumental type slab over concrete; video uses slow heavy slab slides and hard cuts.

### 35. Risograph / riso-print
*When:* indie, culture, zines, creative studios, events.
Radius **slightly off** · Borders **misregistered** · Shadows **flat duotone offset** · Buttons **spot-ink blocks** · Surfaces **grain + halftone, 2–3 spot inks** · Color **fluorescent spot inks (pink/blue/yellow)** · Type **chunky print** · Motion **paper-jitter, ink-bleed**.
▸ Hero/video: an overprinted grainy title; video uses ink-bleed reveals and 2-color halftone transitions.

### 36. Pop-art / comic
*When:* playful consumer, food, entertainment, youth brands.
Radius **0–8px** · Borders **thick black ink** · Shadows **flat** · Buttons **bold outlined, halftone fill** · Surfaces **Ben-Day dots, panels, speech bubbles** · Color **bold primaries + black/white** · Type **comic display + bold** · Motion **POW pops, panel-to-panel cuts**.
▸ Hero/video: a comic panel with a bold caption bubble; video cuts panel-to-panel with bold pop-ins.

### 37. Blueprint / schematic
*When:* engineering, hardware, technical/maker tools, B2B.
Radius **0** · Borders **cyan technical lines** · Shadows **none** · Buttons **outlined, annotated** · Surfaces **grid paper, dimension lines, callouts** · Color **blueprint blue + cyan + white** · Type **mono + technical sans** · Motion **draw-on lines, measured reveals**.
▸ Hero/video: the product as an annotated schematic; video draws schematic lines on and pans across callouts.

### 38. Liquid / blob morphism
*When:* creative apps, wellness, playful modern brands.
Radius **organic, fluid** · Borders **none** · Shadows **soft** · Buttons **gooey pills** · Surfaces **animated metaball blobs, gradient liquid** · Color **vivid gradients** · Type **rounded sans** · Motion **morph, gooey, flowing**.
▸ Hero/video: morphing blobs behind clean content; video uses liquid morph transitions and gooey text reveals.

### 39. 3D render / claymation
*When:* modern products, fintech, playful-premium, AI tools.
Radius **large, soft** · Borders **none** · Shadows **soft ambient + contact** · Buttons **soft 3D, pressable** · Surfaces **rendered 3D objects, depth, soft light** · Color **soft saturated + studio light** · Type **clean rounded sans** · Motion **float, rotate, depth parallax**.
▸ Hero/video: a hero 3D object slowly rotating; video orbits/zooms the object with soft depth-of-field.

### 40. Kinetic typography
*When:* bold brands, agencies, launches, statements.
Radius **0** · Borders **none/minimal** · Shadows **none** · Buttons **type-as-button, oversized** · Surfaces **type fills the canvas, little else** · Color **mono + one accent** · Type **huge variable grotesque, the whole UI** · Motion **type moving, scaling, the entire experience**.
▸ Hero/video: giant moving words that *are* the layout; video is text-driven — words scale, swap, and march to a beat.

### 41. ASCII / textmode
*When:* hacker, retro-nerd, dev tools, terminal culture.
Radius **0** · Borders **box-drawing chars** · Shadows **none** · Buttons **bracketed text** · Surfaces **everything built from monospace characters** · Color **mono on dark + one phosphor** · Type **monospace only** · Motion **type-out, char-flicker, cursor**.
▸ Hero/video: an ASCII-art hero that types itself; video types character-by-character with a blinking cursor.

### 42. Wireframe / lo-fi draft
*When:* design tools, prototyping, in-the-making / beta brands.
Radius **small** · Borders **grey outline** · Shadows **none** · Buttons **outlined placeholder** · Surfaces **boxes, placeholder marks, draft annotations** · Color **greyscale + one marker accent** · Type **sketch/mono** · Motion **draw-on, hand-built**.
▸ Hero/video: a wireframe that fills in; video sketches the UI on, then snaps to the real thing.

### 43. Scrapbook / sticker journaling
*When:* creators, lifestyle, education, cute consumer.
Radius **mixed, taped corners** · Borders **cut/tape edges** · Shadows **layered paper** · Buttons **sticker-cut** · Surfaces **washi tape, stickers, polaroids, handwriting** · Color **warm pastels + marker** · Type **handwritten + friendly sans** · Motion **peel, stick, wiggle**.
▸ Hero/video: a collaged board of stickers/photos; video sticks elements on with peel/wiggle pops.

### 44. Gig-poster / type-maximal
*When:* music, events, bold culture brands, merch.
Radius **0** · Borders **heavy** · Shadows **flat** · Buttons **big slab type** · Surfaces **layered oversized type, posterized art** · Color **2–3 loud, high-contrast** · Type **huge condensed display, stacked** · Motion **punchy slams, beat-synced**.
▸ Hero/video: a stacked-type concert poster; video slams type in on the beat with hard cuts.

### 45. Scandinavian / hygge
*When:* lifestyle, home, wellness, calm premium consumer.
Radius **medium, soft** · Borders **none/hairline** · Shadows **very soft** · Buttons **calm, rounded, muted** · Surfaces **light wood, lots of air, natural photography** · Color **warm off-whites, muted sage/clay** · Type **humanist sans, light** · Motion **slow, calm fades**.
▸ Hero/video: an airy lifestyle photo + quiet type; video uses slow calm crossfades and gentle pans.

### 46. Cottagecore / whimsy
*When:* artisanal, food, craft, storybook brands.
Radius **soft, irregular** · Borders **delicate, floral** · Shadows **soft** · Buttons **rounded, vintage** · Surfaces **botanical illustration, paper, warmth** · Color **muted naturals, dusty florals** · Type **vintage serif + script accent** · Motion **gentle sway, bloom**.
▸ Hero/video: an illustrated pastoral scene; video uses bloom/sway reveals and soft hand-drawn transitions.

### 47. Holographic / iridescent
*When:* future-premium, beauty, web3, bold tech.
Radius **medium-large** · Borders **chrome/iridescent** · Shadows **soft glow** · Buttons **foil/holo gradient** · Surfaces **shifting iridescent gradients, chrome** · Color **rainbow-shift on dark/light** · Type **clean sans, sometimes chrome** · Motion **shimmer, hue-shift, shine sweep**.
▸ Hero/video: an iridescent shifting hero; video sweeps shine across text and hue-shifts the gradient.

### 48. Dark academia
*When:* education, writing, archives, scholarly/literary brands.
Radius **0–4px** · Borders **fine, classical** · Shadows **soft, candlelit** · Buttons **understated serif/outline** · Surfaces **deep moody tones, vintage book texture, ornament** · Color **deep browns/greens/oxblood + cream** · Type **classic serif + small caps** · Motion **slow, page-turn-like**.
▸ Hero/video: a moody serif title over book texture; video uses page-turn wipes and slow ink-in text.

### 49. Retro-futurism / 70s atompunk
*When:* space-age, optimistic tech, retro brands.
Radius **large, rounded** · Borders **chunky rounded** · Shadows **flat retro** · Buttons **pill, chunky, 70s** · Surfaces **rounded panels, sunbursts, NASA-retro** · Color **orange/mustard/brown/cream** · Type **rounded 70s display** · Motion **smooth retro slides, sunburst spins**.
▸ Hero/video: a 70s sunburst hero with rounded type; video uses retro slide/spin transitions and warm fades.

### 50. Fashion-lookbook / editorial-photo
*When:* fashion, beauty, premium lifestyle, photography-led brands.
Radius **0** · Borders **none** · Shadows **none** · Buttons **thin, letter-spaced, minimal over imagery** · Surfaces **full-bleed photography, duotone treatment, lots of space** · Color **monochrome/duotone + photo** · Type **fashion serif + tracked sans** · Motion **slow editorial crossfades, Ken Burns**.
▸ Hero/video: a full-bleed image with a tracked title overlay; video uses Ken-Burns pans and slow editorial crossfades.

---

## Per-style video idioms

When a style is chosen, its **ad-creative videos** inherit its idiom — the cuts, transitions, and text effects come from the style (full toolkit in `ad-creatives.md`). Match the treatment to the family:

- **Hard / bold** (neo-brutalism, gig-poster, pop-art, Bauhaus, concrete) → hard cuts, slam-in type, beat-synced snaps, no soft easing.
- **Tech / terminal** (dark techno, retro terminal, ASCII, cyberpunk, blueprint, data) → typewriter text, cursor blink, glitch/scanline transitions, draw-on lines, count-ups.
- **Soft / premium** (luxury, art deco, dark academia, fashion-photo, Scandinavian) → slow crossfades, Ken-Burns, gold/ink line draw-ons, refined fades.
- **Playful / organic** (claymorphism, liquid, casual-game, scrapbook, cottagecore, Y2K) → bouncy pops, gooey morphs, peel/stick, squash-and-stretch.
- **3D / depth / holo** (3D-render, spatial, holographic, aurora-mesh) → orbit/zoom, depth parallax, shine sweeps, hue-shift.
- **Editorial / type** (kinetic typography, editorial, Swiss, newspaper) → kinetic word swaps, masked line reveals, grid-driven motion.

---

## Selecting (and mixing)

- **Fit the spirit, reject the default.** From the 2–3 candidates, lead with the one that fits the product's world *and* isn't the obvious category cliché (e.g. for a dev tool, "retro terminal" or "dark techno" beats default "refined SaaS"; for a kids' app, "claymorphism" or "casual mobile-game" beats generic "soft").
- **Mix with intent.** A strong combo is a calm base + one expressive accent moment: e.g. *modern minimal* base with a *neo-brutalist* pricing card, or *editorial* base with a *terminal* signature. Never mix more than two, and let one dominate.
- **Vary the material system — not just color.** Commit the chosen language's **radius, border, shadow, button shape, and surface treatment** into the tokens. Across projects these must visibly differ (0px hard-edged here, 24px pillowy there; flat-offset shadows here, ambient depth there). Sameness of radius/shadow is itself an AI tell.
- **State the decision** in the design system / `design_system` Brief field: the language(s), why, and the resulting radius/border/shadow/button/surface tokens.

## Driving ad-creative variety
When producing a *set* of ad creatives, rotate the visual treatment across languages (within brand sense) so each creative looks distinct — one feed-native and clean, one bold neo-brutalist, one glassy/premium, one game-UI energetic — giving the user genuinely different alternatives to A/B test. See `ad-creatives.md`.

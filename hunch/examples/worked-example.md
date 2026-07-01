# Worked Example — End to End

A full run of the pipeline on a product **deliberately different** from the HTML scaffold's invoicing app — a high-ticket done-for-you service — to show the system generalizes across product types (software, services, courses, physical goods). Follow the same flow for any product.

**The product (intake):** *Anchor* — a done-for-you LinkedIn ghostwriting service for B2B SaaS founders. Writes and posts 3 posts/week in the founder's voice. Costs ~$1,500/month. Has 14 current clients and 2 testimonials.

---

## Phase 0 — ATLAS builds the seed Brief

```
product: Done-for-you LinkedIn content for B2B SaaS founders — 3 posts/week, ghostwritten
         in their voice, fully managed. ~$1,500/mo.
assumptions:
  - The founder values pipeline/inbound over vanity metrics. [verify]
  - They've tried posting themselves and stopped. [verify]
  - Budget authority sits with the founder directly. [likely]
icp (seed): B2B SaaS founders, seed–Series A.
pricing (known): ~$1,500/mo.
proof (known): 14 clients, 2 testimonials.
```

## Phase 1 — Ground truth (LANCE ∥ COMPASS ∥ VAULT)

**LANCE (pains, ranked):**
1. *"I know I should be building a personal brand for inbound, but I have zero time and every week I don't post, a competitor's founder does."* (severe, weekly, top-of-mind) — **sharpest.** Cost of inaction: invisible to buyers, losing inbound to louder founders.
2. *"When I do post, it's generic and gets 4 likes — it feels like shouting into the void."* (frequent) — cost: effort with no return, so they quit.
3. *"Hiring a marketer or agency feels like a gamble; most content sounds nothing like me."* (decision-blocking) — cost: stays stuck, does nothing.

**COMPASS (existing demand + framing):** Founders already search for "LinkedIn ghostwriter," "founder-led content," "done-for-you LinkedIn." Demand exists — they're already trying to buy this outcome. Vocabulary: "founder-led growth," "inbound," "build in public," "sounds like me." Framing: *the done-for-you founder content that actually sounds like you and brings in pipeline* — a better answer to a question they already ask, not a new category. Alternatives weighed: doing it themselves, hiring a junior marketer, generic agencies, doing nothing.

**VAULT (ICP + pricing):** The *right* customer is a **funded B2B SaaS founder (seed–Series A) who already believes in founder-led growth, has tried posting and stopped, and whose ACV is high enough that one inbound deal dwarfs the fee.** Value estimate: if one post-sourced inbound lead becomes a deal, that's often $10k–$50k+ ACV — against $18k/yr. Price: $1,500/mo, anchored against *the cost of one missed inbound deal* and *the price of a full-time marketing hire (~$8k+/mo)*. Filter intentionally: not for pre-revenue founders who'll haggle — for them, any price feels high.

## Phase 2 — Offer & substance (FORGE ∥ METAMORPH ∥ BEACON)

**FORGE (the offer):** *The Founder Voice Engine.*
- Core deliverable: a consistent, recognizably-*you* LinkedIn presence that brings inbound to your DMs — without you writing anything.
- Stack: voice-capture interview (so it sounds like you, not an agency) · 3 ghostwritten posts/week · full scheduling & posting · monthly inbound/engagement report · a "viral post" rewrite guarantee on underperformers.
- Risk reversal: *first month, if the posts don't sound like you, we rewrite free until they do — or you don't pay for month one.*
- Scarcity (real): capacity-limited to a set number of founder accounts at a time (true — it's hands-on writing).
- Naming: "The Founder Voice Engine."

**METAMORPH (transformation):** Before — the invisible founder whose great ideas never leave their own head, watching louder competitors win mindshare. After — the founder whose feed *sounds like them*, whose name buyers recognize before the first call, with inbound landing in their DMs. Canonical statement: *"From the founder no one's heard of — to the one buyers already know, with inbound coming to you, without writing a word."*

**BEACON (feature → outcome):**
| Feature | Benefit | Outcome |
|---|---|---|
| Voice-capture interview | Content sounds like you | You're proud to have it under your name; it builds *your* brand |
| 3 posts/week, managed | Consistency without effort | You stay top-of-mind while spending zero hours |
| Monthly inbound report | See what's working | You watch pipeline, not vanity likes |

## Phase 3 — Persuasion layer (EMBER ∥ EDGE ∥ CHORUS)

**EMBER (emotion + logic):** Dominant emotion — a mix of *status anxiety* (being outshone) and *relief* (someone finally handles it). Emotional core: the quiet sting of watching a competitor's founder get the attention you should have. Logic stack (near price/CTA): one inbound deal pays for a year; cheaper and lower-risk than a marketing hire; capacity-limited; rewrite guarantee.

**EDGE (hooks, ego+fear):** Hero — *"Your competitors' founders are all over your buyers' feeds. Where are you?"* (fear of being outshone + ego of belonging there). Sub-hooks: *"Founder-led growth — without writing a single post."* / *"Sound like the smartest person in your space. Because you are."* Tone tokens: confident, peer-to-peer, founder-to-founder, no fluff, short punchy sentences, zero "growth-hacker" hype.

**CHORUS (proof architecture):** Real now: 14 clients (a number), 2 testimonials → place one in the hero strip, one near the offer. Placeholders + collection plan for: a before→after engagement/inbound case study (ask the 2 happiest clients for one metric each), and 2 more founder testimonials. Logos of clients' companies near the hero *if they consent*. Never fabricate.

## Phase 4 — PRISM (specificity)

- "Build your brand" → "get recognized by buyers before the first call."
- "Save time" → "spend zero hours/week and still post 3×/week."
- "Great results" → "one post-sourced inbound deal pays for ~12 months."
- "Trusted by founders" → "14 funded B2B SaaS founders" (real).
- Flags any client metric used until confirmed real; marks the case-study numbers as placeholders to collect.

## Phase 5 — ATLAS synthesizes

**`one_promise`:** *Founder-led growth that sounds like you and brings inbound to your DMs — without you writing a word.*

This drives the hero, the offer name, and the final CTA (all assert the same promise). ATLAS then writes:
- **`strategy.md`** per `strategy-blueprint.md` — including the objection-handling section (price vs. one deal; "won't sound like me" → voice-capture + rewrite guarantee; "agencies are generic" → the differentiator) and a proof-collection plan.
- **`index.html`** per `website-blueprint.md` — re-themed for this product (a confident, founder-to-founder identity, *not* the invoicing scaffold's palette), leading with the pain, selling the transformation, proving with the 14-client number + real testimonials + labeled placeholders, presenting the Founder Voice Engine offer with its rewrite guarantee, value-anchored pricing against one inbound deal, and a final ego+fear close. AURORA picks the design language (here a *refined-SaaS × editorial* mix, rejecting the default dark-SaaS look) and ships its **juice contract** from `motion-toolkit.md`: a sequenced hero load, a word-reveal headline, the 14-client figure counting up, cursor-tracked spotlight cards, a magnetic primary CTA, and one signature moment (a "DM inbox filling up" animation that *shows* the promise) — all reduced-motion-safe.

---

## What this demonstrates

- The **same ten agents** produce a completely different campaign for a high-ticket *service* than they would for a low-ticket *app* — because Phase 1 (LANCE/COMPASS/VAULT) re-grounds everything in this product's real buyer, pain, and value.
- **Coordination shows up everywhere:** the `one_promise` is visible in the hero, the offer name, and the close; pricing is anchored on VAULT's value estimate; proof (CHORUS) is honest about what's real vs. to-be-collected; PRISM made every claim specific.
- **Honesty held:** real numbers used as real, missing proof labeled and assigned a collection plan, scarcity used only because it's genuinely capacity-limited.

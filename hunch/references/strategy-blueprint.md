# Sales Strategy Blueprint

The structure for `strategy.md`. Follow this template exactly. Each section is filled from the Campaign Brief (the owning agent is noted). Keep it concrete — this document should be specific enough that a stranger could execute the campaign from it. Apply PRISM's specificity standard to every line.

Use this exact skeleton:

```markdown
# Sales Strategy — <Product Name>

## 0. Mode                        [ATLAS]
**Launch** (product exists → CTAs go to signup/checkout) or **Validation** ("fake it till you make it" → the site presents the idea as real and captures email via a waitlist modal to measure demand; default when there's no live product). In validation mode, state the **success metric up front: email signups and signup-rate** — the demand signal the site exists to capture — plus the channels driving traffic to it.

## 1. The one promise            [ATLAS]
The single sentence the entire campaign asserts. One promise, stated plainly.

## 2. The right customer (ICP)   [VAULT]
- Who they are: a specific person/role in a specific situation.
- Why-now: the trigger that makes this matter today.
- Budget authority: who decides and what they can spend.
- Where to reach them: channels, communities, search behavior.
- Why them: why this customer makes price nearly irrelevant.

## 3. The pain                   [LANCE]
Ranked, sharpest first. For each: the pain in the buyer's words, how severe/frequent/top-of-mind it is, and the cost of doing nothing.

## 4. Existing demand & positioning  [COMPASS]
- What the buyer already searches/buys/hacks to solve this.
- Their vocabulary (the words to use on the page).
- The framing: the existing question this product is the better answer to.
- Alternatives the buyer weighs (incumbents, spreadsheets, doing nothing).

## 5. The transformation         [METAMORPH]
- Before state (vivid, felt).
- After state (the new identity/capability).
- The bridge (how the offer carries them across).
- Canonical statement: "From [Before] to [After], by [bridge]."

## 6. The offer                  [FORGE]
- Name of the offer.
- Core deliverable (as an outcome).
- Value stack (each item tied to a pain/objection).
- Risk reversal (the guarantee).
- Scarcity/urgency (real, or "none — do not fabricate").

## 7. Pricing                    [VAULT]
- Price and tiers/payment options.
- Value estimate in the customer's terms.
- The anchor (what reframes the price as obvious).

## 8. Benefits (feature → outcome) [BEACON]
A table: Feature | Benefit | Outcome | Pain it relieves.

## 9. Message hierarchy          [EMBER + EDGE]
- Dominant emotion to lead with.
- Hero headline + sub-hooks (each noting the ego + fear it hits).
- The logical justification stack (the rational ammunition, placed near decision points).
- Tone tokens (voice, reading level, words to use/avoid).

## 10. Proof plan                [CHORUS]
- Proof you have now and where it goes on the page.
- Proof to collect: exactly what, from whom, and how to ask.

## 11. Objection handling
For each likely objection (price, trust, "will it work for me?", switching cost, timing): the objection and the on-page answer (copy + proof that neutralizes it). Pull objections from COMPASS's alternatives and VAULT's pricing.

## 12. Channels & launch          [ATLAS]
Where and how to drive traffic to the page, matched to where the ICP already is (from §2 and §4). The 2–3 channels to start with and the first message for each.

## 13. Visibility plan — SEO / GEO / AEO   [SUMMIT + ECHO + ORACLE]
- **Site architecture:** one landing page, or the multi-page set (landing + comparison + "alternative-to" + use-case + answers hub) and why (SUMMIT).
- **Keyword/intent map:** the clusters and which page each maps to.
- **AEO:** the top buyer questions and the answer-first pages + schema (FAQPage, Product/SoftwareApplication, Organization) that target them (ORACLE).
- **GEO:** the citable claims, the one-line entity definition, the `llms.txt`, and the off-page corroboration plan — how the product gets recommended inside AI answers (ECHO).
- **Technical:** sitemap/robots/canonical/Open Graph + the Core Web Vitals notes.

## 14. Design direction          [AURORA]
- The spirit line ("make a [ICP] feel [emotion], like [world]").
- Color/type/spacing tokens and the signature element.
- The motion system (load orchestration, scroll reveals, micro-interactions, signature moment) and the polish/restraint notes — within the accessibility + performance floor.

## 15. Metrics to watch
The handful of numbers that tell you it's working: visit→lead and lead→sale conversion, the activating headline/offer, the leading indicator of the promised transformation — **plus** visibility metrics (organic impressions/clicks, ranking pages, and AI-answer/citation appearances). What "good" looks like and what to change if it's not.

## 16. Assumptions to verify      [from the Brief]
Every inferred fact, listed so the user can confirm or correct. Flag the ones that, if wrong, would change the strategy most.
```

## Quality bar for the strategy doc

- Every claim is specific (PRISM): numbers, named things, concrete before/after — or an honestly-labeled estimate.
- The one promise in §1 matches the hero headline in §9 and the offer name in §6. If they diverge, fix before shipping.
- Pricing (§7) is framed against value, never apologized for.
- The proof plan (§10) is honest: real proof labeled real, gaps labeled gaps with a collection plan.
- Assumptions (§14) are surfaced, not buried — the user should see exactly what you inferred.

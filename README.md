<div align="center">

# 🎯 Hunch

### Test your hunch before you build it.

**Hunch turns any startup idea into a complete, real‑looking landing page with an email waitlist — so you can measure genuine demand *before* writing a line of product code.** Fake it till you make it, honestly.

[![License: MIT](https://img.shields.io/badge/License-MIT-3B33F5.svg)](LICENSE)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-D97757.svg)](#what-is-hunch)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-2ea44f.svg)](CONTRIBUTING.md)
[![No code required](https://img.shields.io/badge/no--code-friendly-C9F23B.svg)](#-quick-start-no-coding-required)

</div>

---

## What is Hunch?

Most ideas die *after* months of building, when it turns out nobody wanted them. Hunch flips the order: you **validate first**.

Describe your idea in plain language, and Hunch builds you a **finished, professional landing page** that presents the idea as if it's real — with a **"join the waitlist" email capture on every button**. You put it online, share the link, and watch the signups. Lots of signups? You found a real hunch worth building. Crickets? You just saved yourself months.

This is the lean‑startup idea of a **smoke test / pretotype** ("is anyone interested?"), done in minutes instead of weeks — and done *honestly*: Hunch never invents fake reviews, fake user counts, or fake scarcity. The page looks real because it's well‑made, and the demand it measures is real because the emails are real.

> **Hunch is a [Claude](https://claude.ai) Skill.** It runs *inside* Claude — you bring your own Claude (claude.ai, Claude Code, or the API) and Hunch does the work. No servers, no accounts to set up, nothing to deploy to use it.

---

## What you get from one prompt

- 🧠 **A validation strategy** — who it's for, the pain, the promise, the offer, pricing, objections.
- 🖼️ **A finished landing page** — responsive, fast, and genuinely well‑designed (Hunch picks from **50 distinct design styles** so it never looks template‑y), with a **waitlist email pop‑up on every call‑to‑action**.
- 🔎 **Found by search *and* AI** — built‑in SEO + structured data (`schema.org`), plus `sitemap.xml`, `robots.txt`, and `llms.txt` so ChatGPT/Perplexity‑style engines can cite it.
- 🎬 **Ad creatives on demand** — ask for "5 TikTok ads" and get platform‑ready short **video ads** (9:16, 1:1, 16:9) with 3‑second hooks for TikTok, Reels, Meta, YouTube & Google — each one different, ready to A/B test.
- ✅ **Real logos, real honesty** — official brand logos where needed; never fabricated proof.

All in English, all from just describing your idea.

---

## How it works

```
1. Describe your idea  ──▶  2. Hunch builds a real‑looking          ──▶  3. Put it online,
   to Claude                 landing page + email waitlist               share it, measure
   ("a tool that…")          (strategy, design, SEO, copy)               real demand (signups)
```

Then you decide with evidence instead of a guess: **build it, change it, or drop it.**

---

## 🚀 Quick start (no coding required)

> 📘 **Brand new to this?** Follow the hand-held, example-by-example **[No-Code Guide](GUIDE.md)** — it covers every click from installing the skill to reading your first signups. The steps below are the short version.

You need access to **Claude** (a [claude.ai](https://claude.ai) **Pro** or **Max** plan is the easiest path).

**1. Get the skill file.** Download [`hunch.skill`](hunch.skill) from this repo (open the file and click **Download**).

**2. Add it to Claude.** In claude.ai, open **Settings → Capabilities** (look for **Skills**) and **upload `hunch.skill`**. *(Skills require a paid plan with code execution enabled. One‑time setup.)*

**3. Ask for your page.** Start a new chat and type something like:
> *"Use Hunch to build a validation landing page for **[your idea in one sentence]**. Put a waitlist email pop‑up on every button."*

Claude will ask anything it needs, then build the page and give you an **HTML file to download**.

**4. Put it online — free.** Drag the downloaded HTML onto **[Netlify Drop](https://app.netlify.com/drop)** → you instantly get a live link. *(Other free options: Vercel, Cloudflare Pages, or GitHub Pages.)*

**5. Make the waitlist collect emails — free.** Create a free form at **[Formspree](https://formspree.io)** and copy your form URL. Open your HTML in any text editor, find **`[SET_ENDPOINT]`**, replace it with your Formspree URL, and re‑upload. Now every signup lands in your inbox. *(Alternatives: Tally, Google Forms, or Netlify Forms.)*

**6. Share & measure.** Post the link where your audience is (Reddit, X, communities, a small ad). **Every signup is a vote.** That's your demand signal.

> Want ads too? Just ask: *"Now make 5 TikTok ad creatives for this."* Hunch returns ready‑to‑record video ads. (To turn one into an MP4: open it in a browser and screen‑record it — there's a one‑line note inside each file.)

---

## For developers (Claude Code / API)

**Claude Code** — drop the folder into a skills directory; it's auto‑discovered:
```bash
# project‑scoped (shareable via git):
cp -r hunch .claude/skills/
# or personal (all your projects):
cp -r hunch ~/.claude/skills/
```
Then: *"Use Hunch to build a validation site for [idea]."*

**Claude API** — upload `hunch.skill` via the Skills API and reference it by `skill_id` in the `container` parameter of a Messages request (runs in the code‑execution environment). Docs: <https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview>

---

## Things you can ask Hunch

- *"Build a validation landing page for a self‑hosted analytics tool for indie devs."*
- *"Make it bold and unconventional — pick a design style that doesn't look AI‑generated."*
- *"Add an FAQ and a pricing section, with the waitlist on the price button too."*
- *"Now create 6 ad creatives — 3 for TikTok, 3 for Instagram Reels — each a different angle."*
- *"Give me the SEO files and the schema so it can rank."*

You don't manage the steps — Hunch coordinates a team of specialist agents and hands you the finished result.

---

## What Hunch is — and isn't

| Hunch **is** | Hunch **is not** |
|---|---|
| A real, well‑designed landing page | A throwaway mockup |
| A real waitlist that collects real emails | A fake form that goes nowhere |
| An honest demand test ("coming soon") | A way to fake reviews, users, or scarcity |
| A pre‑build validation step | The product itself (it's the step *before* building) |

**The honesty gate is built in.** Hunch will not invent testimonials, statistics, user counts, or scarcity — because validating with fake proof only proves the lie, and costs you your credibility. The page is persuasive because it's well‑crafted; the signal is trustworthy because it's real.

---

## Under the hood

Hunch is a coordinated team of **19 specialist agents** (orchestrated by **ATLAS**):

- **10 sales‑psychology agents** — emotion, transformation, pain, demand, benefits, ego+fear, social proof, value pricing, specificity, and offer strength.
- **4 discovery & design agents** — SEO, GEO (being cited inside AI answers), AEO (schema / answer‑first), and a UI/UX + motion designer that picks from **50 design languages** and ships a **full juice‑and‑polish motion system** (magnetic buttons, spotlight cards, count‑up tickers, scroll‑stacking, animated backgrounds) from a vanilla motion toolkit — no static templates.
- **5 ad‑creative agents** — a creative director, a hook specialist, concept & per‑feature creatives, and a format engineer that renders each ad at exact platform resolutions.

Everything they need lives in [`hunch/SKILL.md`](hunch/SKILL.md) and [`hunch/references/`](hunch/references/) — plain Markdown you can read and improve.

---

## FAQ

**Do I need to know how to code?** No. The Quick Start above is drag‑and‑drop. The only "technical" step is pasting one form URL into the HTML.

**Do I need to pay for anything?** You need a Claude plan to run Hunch. Hosting (Netlify/Vercel/GitHub Pages) and the waitlist form (Formspree/Tally) all have free tiers.

**Is the landing page mine?** Yes — it's plain HTML you own and can host anywhere, edit, or hand to a developer.

**Will it look like every other AI page?** No — Hunch deliberately avoids default looks and picks from 50 distinct design languages, varying not just color but buttons, panels, corners, and motion. And it won't be *static*: every page ships a juice contract — a sequenced load, live count‑up numbers, cursor‑tracked spotlight cards, a magnetic CTA, an animated background, and one signature moment — all reduced‑motion‑safe.

**Can I use it for a product that already exists?** Yes — ask for **launch mode** and the buttons go to signup/checkout instead of a waitlist.

---

## Contributing

Hunch is just Markdown instructions — improving it means improving the playbooks. New design languages, sharper copy, better docs, and great examples are all welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE) © 2026 Emre Pehlevan. Use it, fork it, ship it — keep it honest.

<sub>Built as a skill for [Claude](https://claude.ai). Brand icons via [Simple Icons](https://simpleicons.org) (CC0); brand logos are trademarks of their owners.</sub>

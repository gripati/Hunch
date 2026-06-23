<div align="center">

# 📘 The Hunch No-Code Guide

### From a one-sentence idea to real demand — without writing a single line of code.

</div>

---

This guide walks you through **everything**, click by click, with real examples you can copy and paste. It's written for people who **don't code**. The only "technical" thing you'll ever do is paste one link into a file — and we'll show you exactly where.

> ⏱️ **Time:** about 15–20 minutes the first time.
> 💸 **Cost:** you need a paid Claude plan to run Hunch. Everything else in this guide (hosting + the email form) has a **free tier** — $0.
> 🧑‍💻 **Coding required:** none.

**By the end you'll have:**
- A finished, professional-looking landing page for your idea — live on the internet at a real link.
- A working **waitlist** that drops every signup straight into your inbox.
- A simple, honest way to answer the only question that matters: *does anyone actually want this?*

---

## 🗺️ The big picture

Hunch flips the usual order. Instead of *build first, hope someone wants it*, you **test demand first** and build only what people are already asking for.

```
1. Describe your idea   →   2. Hunch builds a real-looking   →   3. You put it online,
   to Claude                  landing page + email waitlist        share it, and count
   (one sentence)             (design, copy, SEO — done)           the signups = real demand
```

Seven steps, start to finish:

| # | Step | Where | Time |
|---|------|-------|------|
| 1 | Install the Hunch skill | claude.ai (one time) | 2 min |
| 2 | Describe your idea | A new Claude chat | 1 min |
| 3 | Answer a few questions | Same chat | 2 min |
| 4 | Download your files | Same chat | 1 min |
| 5 | Put the page online (free) | Netlify Drop | 2 min |
| 6 | Connect the waitlist (free) | Formspree | 3 min |
| 7 | Share it and read the signal | Reddit / X / etc. | ongoing |

---

## 📋 Table of contents

- [Before you start](#-before-you-start)
- [Step 1 — Install the Hunch skill](#step-1--install-the-hunch-skill-one-time)
- [Step 2 — Describe your idea](#step-2--describe-your-idea-your-first-prompt)
- [Step 3 — Answer Claude's questions](#step-3--answer-claudes-questions)
- [Step 4 — Get your files](#step-4--get-your-files)
- [Step 5 — Put your page online (free)](#step-5--put-your-page-online-free)
- [Step 6 — Make the waitlist collect emails (free)](#step-6--make-the-waitlist-collect-emails-free)
- [Step 7 — Share it and read the signal](#step-7--share-it-and-read-the-signal)
- [Optional — Ask for ad creatives](#optional--ask-for-ad-creatives)
- [A full worked example](#-a-full-worked-example-start-to-finish)
- [Tips for better results](#-tips-for-better-results)
- [Troubleshooting & FAQ](#-troubleshooting--faq)

---

## 🧰 Before you start

You need two things. The first is required up front; the rest are free and we set them up along the way.

1. **A Claude account on a paid plan.** Hunch is a *Claude Skill* — it runs *inside* Claude. A [claude.ai](https://claude.ai) **Pro** or **Max** plan is the easiest path. (Skills need a paid plan with code execution enabled.)
2. **The `hunch.skill` file.** Get it from this repo: open **[`hunch.skill`](hunch.skill)** and click **Download**.

That's it to begin. You do **not** need a website, a domain, a server, or any tools installed on your computer.

---

## Step 1 — Install the Hunch skill (one time)

You only do this once. After that, Hunch is available in every chat.

1. Go to [claude.ai](https://claude.ai) and sign in.
2. Open **Settings → Capabilities** and find the **Skills** section.
3. Click **Upload skill** and choose the **`hunch.skill`** file you downloaded.
4. Done. ✅

> 💡 **Don't see "Skills"?** You're probably on the free plan, or code execution is off. Skills require a paid plan (Pro or Max) with code execution enabled. See the [FAQ](#-troubleshooting--faq).

<details>
<summary><b>Using Claude Code (for developers)?</b></summary>

Instead of uploading the `.skill` file, drop the `hunch/` folder into a skills directory and it's auto-discovered:

```bash
# project-scoped (shareable via git):
cp -r hunch .claude/skills/
# or personal (all your projects):
cp -r hunch ~/.claude/skills/
```
</details>

---

## Step 2 — Describe your idea (your first prompt)

Start a **new chat** in Claude and describe your idea in **one sentence**. Hunch handles the strategy, the copy, the design, and the technical bits — you just bring the idea.

**Copy this template and fill in the brackets:**

```
Use Hunch to build a validation landing page for: [describe your idea in one sentence].

It's still just an idea — I want to measure demand before I build it.
Put a waitlist email pop-up on every button.
```

**Example (filled in):**

```
Use Hunch to build a validation landing page for: a focus app for remote
workers that lets you start "deep work sessions" a few times a day and work
silently alongside hundreds of other people in a virtual co-working room.

It's still just an idea — I want to measure demand before I build it.
Put a waitlist email pop-up on every button.
```

### Two modes — pick the right one

| Mode | When to use it | What the buttons do |
|------|----------------|---------------------|
| **Validation** *(default)* | The product **doesn't exist yet** — you're testing the idea | Open a **waitlist email pop-up** ("Launching soon — get early access"). The goal is signups. |
| **Launch** | The product is **already live** | Go to **sign-up / checkout / the app**. |

Saying *"it's still just an idea"* puts Hunch in **validation mode** — exactly what you want for testing demand. (If your product already exists, write *"use launch mode — the product is live"* instead.)

> 🔒 **The honesty rule.** Hunch will **never** invent fake reviews, fake user counts, or fake scarcity. The page looks real because it's well-made — not because it lies. This protects your credibility and keeps your demand signal trustworthy.

---

## Step 3 — Answer Claude's questions

Hunch infers most things, but it'll ask about anything it genuinely can't guess. Typically:

- **Who is it for?** (your target customer)
- **Is there a price in mind?** Even in validation mode, the price is shown — *"would people pay this?"* is part of the test.
- **Do you have any real proof?** A real user count, a testimonial, a metric. **If you don't, say so** — Hunch will not make any up.

**Example answer:**

```
Target: remote software engineers and designers who struggle to start focused work.
Price idea: $8/month.
No users yet, no testimonials — please don't invent any.
```

Keep it short. Claude takes it from here.

---

## Step 4 — Get your files

From that one prompt, Claude produces a complete kit you can download:

| File | What it's for |
|------|---------------|
| **`index.html`** | Your finished landing page — responsive, designed, with the waitlist on every button. **This is the one you'll publish.** |
| `strategy.md` | The thinking behind it: who it's for, the pain, the offer, pricing, objections, where to get traffic, and your **success metric** (signups / signup-rate). |
| `sitemap.xml`, `robots.txt`, `llms.txt` | So search engines *and* AI answer engines (ChatGPT, Perplexity) can find and cite your page. |
| (built into the page) SEO tags + `schema.org` data | So it can rank on Google and show up in AI answers. |

👉 **For now, you only need to download `index.html`.** The rest are bonuses you can use later.

---

## Step 5 — Put your page online (free)

No server, no setup. We'll use **Netlify Drop** — it's drag-and-drop.

1. Make sure you've downloaded **`index.html`** from the chat.
2. Go to **[app.netlify.com/drop](https://app.netlify.com/drop)**.
3. **Drag the `index.html` file** onto the page.
4. In a few seconds you get a **live link** like `your-idea-name.netlify.app`. Your page is on the internet. 🎉

> 🔁 **Other free options:** Vercel, Cloudflare Pages, or GitHub Pages all work the same way. Netlify Drop is the fastest for a first test.

---

## Step 6 — Make the waitlist collect emails (free)

Right now the pop-up opens, but signups don't go anywhere yet. Let's connect them to your inbox. **This is the only "technical" step — and it's just copy-paste.**

1. Go to **[formspree.io](https://formspree.io)** and create a free account.
2. Create a new form. Formspree gives you a **form URL** that looks like:
   `https://formspree.io/f/abcdwxyz`
   Copy it.
3. Open your **`index.html`** in any text editor (Notepad, TextEdit, VS Code — anything).
4. Use **Find** (Ctrl/Cmd + F) to locate **`[SET_ENDPOINT]`**.
5. **Replace `[SET_ENDPOINT]`** with your Formspree URL. Save the file.
6. Go back to **[Netlify Drop](https://app.netlify.com/drop)** and **drag the updated file in again** to republish.

Now every signup lands **straight in your email inbox**. ✅

> 🔁 **Alternatives:** Tally, Google Forms, or Netlify Forms all work. The idea is the same — get a form URL and paste it in place of `[SET_ENDPOINT]`.

> ✅ **Test it yourself:** open your live link, click a button, and submit your own email. You should receive it. If not, see the [FAQ](#-troubleshooting--faq).

---

## Step 7 — Share it and read the signal

This is the whole point: **real people, real emails, real demand.**

**Where to share:**
- Communities where your audience already hangs out — relevant **subreddits**, **X**, **Discord/Slack groups**, niche forums.
- A small paid ad (even $20–50) to drive a burst of cold traffic.
- Your own network, a relevant newsletter, a "build in public" post.

**How to read the result honestly:**
- **Each signup is a vote** — someone gave you their real email for something that doesn't exist yet. That's a strong signal.
- What matters most isn't the raw number, it's the **signup rate**: of the people who visited, how many joined? A page that converts a healthy share of targeted visitors is a much stronger signal than a big number from untargeted traffic.
- Compare like with like: 50 signups from 200 targeted visitors means far more than 50 from a viral post seen by 50,000.

**Then decide — with evidence instead of a guess:**

| What you see | What it likely means | What to do |
|--------------|----------------------|------------|
| Strong, steady signups from your target audience | Real demand | **Build it.** |
| Some interest, but only with a different angle/message | The idea is close; the framing is off | **Pivot** the positioning and re-test. |
| Crickets, even with real targeted traffic | Not enough pull *right now* | **Drop it** — and you just saved yourself months. |

---

## Optional — Ask for ad creatives

Want to drive traffic with video ads? In the same chat, just ask:

```
Now make 5 TikTok ad creatives for this — each a different angle, with a
3-second hook. The CTAs should point to the waitlist.
```

You'll get platform-ready **video ads** (9:16, 1:1, 16:9) for TikTok, Reels, Meta, YouTube, and Google — each one different, ready to A/B test.

> 🎥 **Turn one into a video file:** open the ad in your browser and screen-record it. There's a one-line note inside each file explaining how.

---

## 🧪 A full worked example (start to finish)

Here's the whole journey for one idea, so you can see what each step actually looks like.

**The idea:** *A focus app for remote workers — start a "deep work session" a few times a day and work silently alongside hundreds of others in a virtual co-working room.*

**1. The prompt I send Claude:**
```
Use Hunch to build a validation landing page for: a focus app for remote
workers that lets you start "deep work sessions" a few times a day and work
silently alongside hundreds of other people in a virtual co-working room.
It's still just an idea — I want to measure demand. Put a waitlist email
pop-up on every button.
```

**2. Claude asks, I answer:**
> *Claude:* Who's the core user, is there a price in mind, and do you have any real proof yet?
```
Remote software engineers and designers who can't get started on deep work.
Price idea: $8/month. No users or testimonials yet — don't invent any.
```

**3. What Claude builds:** a finished `index.html` that leads with the real pain (*"You sit down to focus and 40 minutes vanish"*), sells the transformation (*"start a session, and suddenly you're locked in — because 300 other people are too"*), shows an honest $8/mo price, and opens a polished **waitlist pop-up** on every button. Plus `strategy.md`, `sitemap.xml`, `robots.txt`, `llms.txt`.

**4. I download `index.html`.**

**5. I drag it onto [Netlify Drop](https://app.netlify.com/drop)** → I get `deep-focus-rooms.netlify.app`. It's live.

**6. I connect the waitlist:** I make a form at [Formspree](https://formspree.io), copy its URL, open `index.html`, replace `[SET_ENDPOINT]` with my URL, save, and re-drag onto Netlify. I submit my own email to test — it arrives. ✅

**7. I share it:** I post the link in r/remotework and a couple of productivity Discords, and run a $30 TikTok ad with creatives Hunch made. Over a week I get **180 signups from ~600 targeted visitors**. That's a real signal — time to build the first version.

---

## 💡 Tips for better results

- **One clear sentence beats a paragraph.** Say what it does and who it's for; let Hunch do the rest.
- **Be honest about proof.** No users yet? Say so. A real test with no fake proof is worth infinitely more than a pretty lie.
- **Ask for a distinctive look** if the first design feels generic:
  ```
  Make it bold and unconventional — pick a design style that doesn't look AI-generated.
  ```
- **Add sections on demand:**
  ```
  Add an FAQ and a pricing section, with the waitlist on the price button too.
  ```
- **Get the discovery files** so it can rank:
  ```
  Give me the SEO files and the schema so it can rank.
  ```
- **Already have a product?** Use launch mode:
  ```
  Use launch mode — the product is live. CTAs should go to signup/checkout.
  ```

---

## ❓ Troubleshooting & FAQ

**I don't see "Skills" in Claude settings.**
Skills require a **paid plan** (Pro or Max) with **code execution** enabled. Upgrade, then look again under **Settings → Capabilities**.

**My waitlist isn't sending emails.**
Three things to check: (1) Did you replace **`[SET_ENDPOINT]`** with your real Formspree URL? (2) Did you **re-upload** the edited file to Netlify? (3) On Formspree's first submission you may need to confirm the form by email. Submit a test signup and follow any confirmation prompt.

**The page looks too generic / too "AI."**
Ask Claude for a different direction: *"Pick a bolder, more unconventional design language that doesn't look AI-generated."* Hunch chooses from 50 distinct design styles.

**Do I have to pay for anything besides Claude?**
No. Hosting (Netlify/Vercel/GitHub Pages) and the form (Formspree/Tally/Google Forms) all have free tiers. You only need a paid **Claude** plan to run Hunch.

**Is the landing page really mine?**
Yes. It's plain HTML you own — host it anywhere, edit it yourself, or hand it to a developer.

**Can I use my own domain instead of `*.netlify.app`?**
Yes — Netlify (and Vercel/Cloudflare) let you connect a custom domain for free in their settings. Optional; the free subdomain works perfectly for a test.

**Can I use this for a product that already exists?**
Yes — ask for **launch mode** and the buttons go to signup/checkout instead of a waitlist.

**Will it invent fake reviews or numbers to look more convincing?**
No, by design. Hunch never fabricates testimonials, statistics, user counts, or scarcity.

---

<div align="center">

### Got a hunch worth testing?

Find out if anyone wants it — *before* you build it.

**[← Back to the README](README.md)** · **[Download the skill](hunch.skill)** · **[Star on GitHub](https://github.com/gripati/Hunch)**

<sub>MIT © 2026 Emre Pehlevan · Built as a skill for <a href="https://claude.ai">Claude</a> · Use it, fork it, ship it — keep it honest.</sub>

</div>

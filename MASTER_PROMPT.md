# MASTER PROMPT — Vibe Coding Blueprint Sales Page (V2)

Use this prompt to rebuild the page in any AI builder (Manus, Claude, Lovable, v0, Cursor, etc.). It contains the full brief, design system, and verbatim copy. Paste the entire prompt and ask the tool to build a single-page static HTML/CSS/JS landing page from it.

---

## ROLE & GOAL

You are a senior front-end designer-developer building a single-page sales landing page for a digital product called **The Vibe Coding Blueprint**. The product teaches non-technical creators how to build software tools using AI, without writing code.

Deliver one production-ready static site: **index.html + style.css + a small inline `<script>`**. No frameworks, no build step. Modern CSS (custom properties, container queries OK, `color-mix`, `clamp`). Mobile-first, fully responsive, accessible (WCAG AA contrast), keyboard navigable. Dark theme by default with a working light-theme toggle.

The page must follow a **Problem → Agitate → Solution (PAS)** narrative arc. Every section should serve that arc. Match the copy verbatim — it has been split-tested and refined.

---

## AUDIENCE

Cold-traffic creators, side-hustlers, and aspiring entrepreneurs who:

- Want recurring online income but don't know where to start
- Have probably tried selling courses, ebooks, templates, or memberships
- Are NOT technical and have NEVER heard of vibe coding
- Follow creators in the digital-product / online-business space
- Are intrigued by AI but haven't found their angle yet

The page must read as accessible to a complete beginner. NO jargon without immediate plain-English explanation. NO terminal/code visuals as central elements (it's for non-coders).

---

## VOICE & TONE

- **Direct, conversational, slightly contrarian** — like a friend who just figured something out and is excited to tell you
- Use "you" and "I" naturally
- Short sentences. Then occasionally one long one with rhythm.
- Specific numbers everywhere (22,000 creators, $43,734 MRR, 7 years, etc.)
- Italics for emphasis (`<em>`), not bold-everywhere
- Lime accent color used for italic emphasis on key words/phrases
- No hype, no exclamation points, no all-caps shouting

---

## VISUAL DIRECTION

Dark-first, modern dev-tool aesthetic (think Linear, Vercel, Cursor) but warmer for the creator audience. Single accent color: **electric lime**. Big serif display headlines (Instrument Serif) paired with clean sans-serif body (Inter) and monospace for metadata (JetBrains Mono).

### Color tokens (CSS custom properties)

```css
:root, [data-theme='dark'] {
  --color-bg: #0a0a0b;
  --color-surface: #111113;
  --color-surface-2: #16161a;
  --color-surface-offset: #1c1c21;
  --color-divider: #1f1f24;
  --color-border: #2a2a30;
  --color-border-strong: #3a3a42;

  --color-text: #f4f4f5;
  --color-text-muted: #b4b4bc;
  --color-text-faint: #7a7a82;

  --color-primary: #b8ff35;          /* electric lime — only accent */
  --color-primary-hover: #c8ff5e;
  --color-primary-highlight: #1e2a0a; /* lime tint on dark bg */
  --color-on-primary: #0a0a0b;

  --color-success: #4ade80;
  --color-error: #ff6b8a;
  --color-warning: #fbbf24;
  --color-purple: #a78bfa;
}

[data-theme='light'] {
  --color-bg: #fafaf9;
  --color-surface: #ffffff;
  --color-text: #18181b;
  --color-text-muted: #57575c;
  --color-primary: #65a30d;
  --color-on-primary: #ffffff;
  /* (mirror the rest accordingly) */
}
```

### Type scale

Use fluid `clamp()` sizing.

```css
--text-xs: clamp(0.75rem, 0.7rem + 0.2vw, 0.8125rem);
--text-sm: clamp(0.875rem, 0.82rem + 0.25vw, 0.9375rem);
--text-base: clamp(1rem, 0.95rem + 0.25vw, 1.0625rem);
--text-lg: clamp(1.125rem, 1.05rem + 0.4vw, 1.25rem);
--text-xl: clamp(1.375rem, 1.2rem + 0.8vw, 1.75rem);
--text-2xl: clamp(1.875rem, 1.4rem + 2vw, 2.75rem);
--text-3xl: clamp(2.5rem, 1.6rem + 4vw, 4.25rem);
--text-hero: clamp(2.75rem, 1.4rem + 6vw, 6rem);
```

### Fonts (Google Fonts)

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Instrument+Serif:ital@0;1&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet" />
```

- **Display headlines:** `Instrument Serif` (400 + 400 italic). Big serif, almost-Times-like, elegant.
- **Body + UI:** `Inter` (400/500/600/700).
- **Metadata, badges, technical chrome:** `JetBrains Mono` (400/500/600).

### Spacing & radius

Use a multiple-of-4 scale (`--space-1` = 0.25rem through `--space-32` = 8rem). Radius scale: `--radius-sm: 0.375rem`, `--radius-md: 0.625rem`, `--radius-lg: 0.875rem`, `--radius-xl: 1.25rem`, `--radius-full: 9999px`.

### Aesthetic principles

- Generous whitespace. Sections breathe.
- Grid backgrounds + radial lime glows behind hero/CTAs
- Italic Instrument Serif words inside headlines, colored lime, for emphasis (e.g., *"the one **nobody's talking about.**"*)
- Mono uppercase tracking-wide eyebrows above each section title (e.g., `READ THIS FIRST`)
- Pill-shaped CTAs with electric-lime fill + dark text + subtle glow on hover
- Most sections alternate `bg` and `surface` to create rhythm
- Subtle scroll-reveal animations on sections (`opacity 0 → 1`, `translateY 24px → 0`, 600ms ease)
- Pulsing lime dot animations on "LIVE" indicators

---

## PAGE STRUCTURE (in order)

Build these sections top-to-bottom. The PAS arc is annotated in `[brackets]`.

1. **Urgency bar** (sticky top, full-width strip with countdown)
2. **Nav** (sticky, transparent-blurred)
3. **Hero with VSL** *(centerpiece — VSL is the focal point above the fold)*
4. **Authority strip** *(4-stat bar — credibility check)*
5. **Two Types of Creators** *(audience filter — Problem setup)*
6. **The Brutal Truth** *(PAS: PROBLEM)*
7. **Then vs Now** *(PAS: AGITATE — visual comparison of old way vs new way)*
8. **Mechanism: The Creator's Blind Spot** *(PAS: SOLUTION reveal)*
9. **Vibe Coding Explainer** *("you don't have to code — that's the whole point")*
10. **Use Cases** *(creator examples with subscriber counts)*
11. **Origin Story** *(Travis's credibility + emotional reframe)*
12. **The Three Steps** *(modules)*
13. **Bonuses — Power of Free** *(6 bonus cards + total value)*
14. **Pricing** *(offer stack, $49 anchored against $99)*
15. **Day 30 Future Pacing** *(Stripe-style notification stack)*
16. **FAQ** *(8 questions)*
17. **Final CTA** *(big countdown timer + last call)*
18. **Footer**

---

## VERBATIM COPY (USE EXACTLY)

### 1. Urgency Bar

> ● **Founders pricing — $49** · Price goes to $99 in `[live countdown: Xd Xh Xm]` · Instant access · Lifetime

### 2. Nav

- Brand: `vibe-coding.blueprint` (mono, with a square lime icon containing a stylized "V" mark)
- Right side: theme toggle (sun/moon icon) + primary CTA `Start for $49 →` (links to `#pricing`)

### 3. Hero (VSL is the centerpiece)

**Eyebrow:** `● FOR CREATORS, ENTREPRENEURS & SIDE-HUSTLERS`

**Headline (Instrument Serif, italics on the lime portion):**

> The biggest opportunity in the creator economy right now is the one *nobody's talking about.*

**Subheadline:**

> While everyone else fights over the same saturated digital-product market, a small group of creators is quietly building **simple software tools** their audiences pay them `$5K–$50K/month` for — using nothing but AI. **Watch the 11-minute breakdown below.**

(The `$5K–$50K/month` is rendered as a small lime-highlighted mono pill inline.)

**VSL Player (placeholder until real embed dropped in):**

- 16:9 aspect ratio, max-width 880px, centered
- Border-radius `--radius-xl`, lime-tinted border, glow shadow
- Dark gradient background with two radial color accents (lime + soft purple)
- Centered content stack:
  - Top: small mono pill chip: `11:42 · TRAVIS STEPHENSON`
  - Middle: Instrument Serif headline (white, italic "Software" word in lime):
    > Why The Smartest Creators Are Quietly Switching From Courses To *Software.*
  - Bottom: mono caption `A FREE BREAKDOWN OF THE NEW PLAYBOOK`
- Large round lime play button (80px) centered absolutely on top
- Bottom progress bar with lime filled portion at ~8% + mono time `0:00 / 11:42`

**Below the VSL:** small mono caption: `↑ Watch this before you scroll — 11 minutes that will change how you think about your business.`

**CTA Button:** `Get the Blueprint for $49 →` (large lime pill)

**Fine print row (mono, small):**

`One payment · Lifetime access · 30-day refund guarantee · 22,000+ creators served`

### 4. Authority Strip (4-column stat bar)

Section style: surface background, full-width, thin top + bottom borders. 4 equal columns with thin dividers between.

Each column: big Instrument Serif number (lime), then small mono caption below.

| Number | Caption |
|---|---|
| `22,000+` | creators launched through PaidCreators |
| `$43,734` | in current MRR · 5 software products |
| `7 years` | prior software co-founder · exited 2023 |
| `0 lines` | of code personally written |

### 5. Two Types of Creators

**Eyebrow:** `READ THIS FIRST`

**Section Title (Instrument Serif):**
> There are two types of creators reading this *right now.*

**Two-column split (stacks on mobile):**

**Column 1 (neutral card):**

> **01 / The Content Grinder**
>
> **You've been doing the right things. They've stopped working.**
>
> You post. You email. You launch a $47 mini-course. Maybe one in a hundred subscribers buys it. You roll into the next launch. You're putting out more content than you have in your life — and your bank account is somehow *quieter,* not louder.
>
> You're not lazy. You're not failing. You're just doing the thing that worked in 2019 in a market that's changed underneath you.

**Column 2 (lime-tinted accent card):**

> **02 / The Quiet Watcher**
>
> **You feel something has shifted. You just can't name it.**
>
> You see AI in every conversation. You see "indie hackers" on Twitter posting Stripe screenshots. You know something is happening — bigger than ChatGPT prompts, bigger than another content strategy.
>
> You can't put your finger on what it is, exactly. But you have the strong feeling that **missing this one will hurt** in a way missing TikTok in 2019 hurt.

**Below both cards (centered italic serif):**

> If you're either one of those creators — **good.** The next 8 minutes are the reason you opened this page.

### 6. The Brutal Truth (PROBLEM)

**Eyebrow:** `THE BRUTAL TRUTH`

**Title:**
> The "sell your knowledge" era is *ending.*

**Body (centered narrow column, prose):**

> For ten years, the creator playbook was simple: build an audience, package your knowledge into a course or ebook, sell it. I helped **22,000+ creators** do exactly that through PaidCreators. It was beautiful. It was lucrative. It was the easiest money in the history of the internet.
>
> That window is closing fast. Every niche is flooded with 200 versions of the same course. AI can generate a 500-page ebook in 12 seconds. Customers refund faster, finish less, and click "buy" with more hesitation every quarter.
>
> *(Pull quote — Instrument Serif italic, large, centered, bordered top + bottom):*
>
> > The next decade doesn't belong to the people who teach the thing.
> > It belongs to the people who build the tool that *does* the thing.
>
> **People will always pay more for a tool than for information about the tool.** They'll pay longer. They'll refund less. They'll come back month after month, because the tool keeps doing the job they hired it to do.
>
> And until 18 months ago, that game was locked behind a door labeled *"developer required."* The door cost $5,000 minimum and ten months of your life. Nobody you actually relate to ever walked through it.
>
> **The door is unlocked now. Almost nobody you follow knows yet.**

### 7. Then vs Now (AGITATE) — KEY NEW SECTION

**Eyebrow:** `THEN VS NOW`

**Title:**
> The creator playbook just *quietly* got rewritten.

**Subheadline:**
> Same information. Same expertise. Same audience. Completely different timeline, completely different finish line.

**Layout:** Two columns side-by-side (stack on mobile), with a glowing lime arrow divider between them.

**LEFT COLUMN — "The Old Way"** (red-tinted, slightly dimmed)
- Tag pill (small mono uppercase): `THE OLD WAY`
- Tagline (mono): `3–6 months of work`
- Column heading (Instrument Serif): **Sell your knowledge as a digital product.**
- Numbered steps (red-tinted circular badges):
  | # | Step | Time |
  |---|---|---|
  | 01 | Study the topic for months | ~ 90 days |
  | 02 | Record 20+ videos / write the course | ~ 30 days |
  | 03 | Build a membership site | ~ 14 days |
  | 04 | Write a sales page that actually converts | ~ 7 days |
  | 05 | Engineer upsells to make it profitable | ~ 7 days |
  | 06 | Launch — and hope it converts | The moment of truth |
- Outcome card at bottom (red-tinted): big number `90%` + body: *"of buyers never finish the material. Refund rate climbs every quarter. You start the whole cycle over on the next launch."*

**DIVIDER:** Vertical lime gradient line on desktop (horizontal on mobile) with a 56px lime circle in the middle containing a → arrow.

**RIGHT COLUMN — "The New Way"** (lime-glowing card)
- Tag pill (lime): `THE NEW WAY`
- Tagline (lime, bold): `24–48 hours, start to finish`
- Column heading (Instrument Serif): **Weaponize that same knowledge as a tool.**
- Numbered steps (lime circular badges with glow):
  | # | Step | Time |
  |---|---|---|
  | 01 | Have AI research your topic end-to-end | ≈ 1 hour |
  | 02 | Embed that research in a sequential prompt pattern | ≈ 2 hours |
  | 03 | Let AI build it into real, systematized software | ≈ 18 hours |
  | 04 | Launch — live, paying customers | ≈ same weekend |
- Outcome card at bottom (lime-tinted): big number `90%+` + body: *"of buyers **use** it, daily. Refund rate near zero because they open it every morning. Each new customer compounds the last."*

**BELOW BOTH COLUMNS — Timeline Bar comparison:**

Centered card (max 880px). Mono label at top: `TOTAL TIME TO FIRST PAYING CUSTOMER`. Then two horizontal bars:

- "Old way" label + red horizontal bar filling 100% width, with text right-aligned: `90–150 days`
- "New way" label + lime horizontal bar filling ~4% (min-width 110px), with text centered: `24–48 hours`

Below the bars, centered italic Instrument Serif: *"Same knowledge. Same person. **~70x faster to first dollar.**"*

**CLOSING LINE (centered, large italic Instrument Serif, lime accent):**

> This isn't a faster way to make a course. *It's a different product entirely.* One that gets paid monthly instead of once, used daily instead of forgotten, and gets *more* valuable over time instead of rotting in a Google Drive folder.

### 8. Mechanism — The Creator's Blind Spot (SOLUTION reveal)

**Eyebrow:** `THE MECHANISM`

**Title (Instrument Serif, lime italic on mechanism name):**
> It's not that you're failing as a creator.
> You have a *Creator's Blind Spot.*

**Lead paragraphs:**

> For your entire career as a creator, you've been looking at one half of the market: **selling your knowledge.** Courses. Ebooks. Coaching. Templates. Memberships.
>
> The *other* half of the market — the half that has always been quietly bigger, more durable, and higher-margin — has been invisible to you. Not because you didn't know it existed. Because the price of entry was so high (a developer, an MBA, six figures) you logically *filed it away* as *"not for me."*

**Visual — Side-by-side comparison cards with arrow between:**

**LEFT (dimmed):**
- Tag: `WHAT YOU SEE`
- Title (Instrument Serif): `Selling Your Knowledge`
- 5 list items each with a red ✕ icon:
  - Paid **once** per buyer
  - Refund rate climbs every quarter
  - Forgotten 3 days after purchase
  - Every new launch starts at zero
  - Income stops when you stop
- Footer: `Revenue model: **linear, one-time**`

**ARROW BETWEEN:** Lime circle with right-arrow

**RIGHT (lime glow):**
- Tag (lime): `WHAT YOU'RE MISSING`
- Title (Instrument Serif): `Building A Tool`
- 5 list items each with a lime ✓ icon:
  - Paid **every month**, forever
  - Refund rate near zero (they use it daily)
  - Gets *more* valuable over time
  - Every customer compounds the last
  - Income continues while you sleep
- Footer: `Revenue model: **recurring, compounding**` (lime)

**Closing math (centered narrow):**

> One creator selling a $47 course needs **2,128 sales** to gross $100K.
> One creator with a $29/mo software tool needs **287 active subscribers.**

**Punchline (Instrument Serif large italic):**

> Same audience. Same effort. *13x the leverage.*

### 9. Vibe Coding Explainer

**Eyebrow:** `"WAIT — BUT I CAN'T CODE"`

**Title:**
> You don't have to. That's *the whole point.*

**Sub:**
> Something changed in late 2024 that 99% of creators still haven't realized happened. It has a name: **vibe coding.**

**Two-column Then vs Now grid:**

**LEFT — Then (2010–2024):**
- Label pill: `THEN (2010 – 2024)`
- Heading: `Building software meant:`
- ✕ list:
  - Learning to code (3+ years)
  - Or hiring a developer ($5,000+/mo)
  - Months of waiting on something to ship
  - Bug fixes that took weeks
  - Total dependence on someone technical

**RIGHT — Now (lime tinted):**
- Label pill (lime): `NOW (VIBE CODING ERA)`
- Heading: `Building software means:`
- ✓ list:
  - Describing what you want, in plain English
  - AI writes the code in real time, while you watch
  - "Make the button green, move it left" — and it does
  - Bug fixes happen in seconds, not weeks
  - You're the founder. The AI is the engineer.

**Analogy block below (Instrument Serif italic quote, big lime opening quotation mark):**

> "Think of it like having a senior software engineer on call 24/7, who works for $20/month, never sleeps, never quits, builds whatever you describe, and refactors it the second you change your mind. **That's vibe coding.** That's been impossible for the entire history of the internet — until 18 months ago."

### 10. Use Cases (8 cards)

**Eyebrow:** `WHAT YOU COULD BUILD`

**Title:**
> Look at what creators just like you have already built.

**Sub:**
> Every one of these was built by someone who couldn't code, didn't have a developer, and didn't think this was possible six months ago.

**Grid of 8 cards (3 columns desktop, 2 tablet, 1 mobile):** Each card has a small mono niche label, an Instrument Serif product description, and a lime price pill.

| Niche | Product | Price |
|---|---|---|
| Fitness creator (52K IG) | Macro tracker for her audience | $29/mo · 412 subscribers |
| Marriage coach | Couples' weekly check-in app | $19/mo · 287 couples |
| Sourdough hobbyist | Hydration calculator + recipe vault | $2K/mo · runs itself |
| Personal finance writer | Tax-loss harvesting calculator | $300/mo · B2B license |
| Homeschool mom | Curriculum planner | $149 one-time · 1,200 sales |
| Real-estate agent | Lead-scoring tool for his market | 11 agents · $49/mo each |
| Golf instructor | Swing-analysis video journal | $29/mo · 89 students |
| Mindset coach | Daily check-in + habit tracker | $15/mo · 600+ users |

**Closing line (centered):**

> None of them were developers. None of them had funding. **Every single one started with an idea, an audience, and the Blueprint.**

### 11. Origin Story

**Two-column layout (240px sidebar + content):**

**Sidebar (sticky on desktop):**
- 64px gradient avatar with initials `TS`
- Name (bold): `Travis Stephenson`
- Role (mono, faint, uppercase): `FOUNDER · PAIDCREATORS`
- Small body text: `22,000+ creators launched. 3 SaaS apps. 2 mobile apps. Zero lines of code written.`

**Main content (Instrument Serif title, paragraphs in Inter):**

**Title:** `I was the creator I'm describing.`

**Body (paragraph breaks intact):**

> I built a software company in 2016. I had the marketing chops. I had the audience. The **one thing I didn't have** was the ability to write a line of code.
>
> So I did what every non-technical creator does: I hired a developer. **$8,000 a month.** For *one* person. Who held the entire codebase hostage. Who would disappear for weeks at a time. Who, when I finally tried to leave, screwed me on the handoff so badly I considered burning the whole company down.
>
> I sold that company in August of 2023. After seven years of being held hostage by someone who cost more than my mortgage every month. I told my wife: *"I am never building software again. Ever."*
>
> I meant it.
>
> Then in late 2024, I started messing around with Claude. Just to write blog posts. I asked it one day, *"build me a simple tool that does X."* Two hours later, I had a working app. It was rough. It was ugly. **It worked.**
>
> I sat there staring at it, doing the math on the **$672,000** I had paid that developer over seven years. Thinking about every product launch that got delayed because he was on vacation. Every bug that took weeks to fix.
>
> I built another tool the next day. Then another. Then I started charging people for them. Today I run three SaaS apps and two mobile apps.

**Pull quote (lime italic, left-border accent):**

> Combined monthly recurring revenue: **$43,734.**
> I did not write a single line of code.

**Proof image:** Browser-window-framed screenshot of a Stripe MRR dashboard showing $43,734.55. Frame includes 3 colored chrome dots (red/yellow/green) + `dashboard.stripe.com` URL.

Caption below the image: `Live Stripe MRR · May 2026 · Across 5 products I vibe-coded`

**Closing paragraph:**

> **Here's why I'm telling you this.** The version of me who built that company in 2016 needed this Blueprint and didn't have it. He would've saved $672,000 and seven years of his life. He couldn't have it then. *You* can have it now. And I genuinely cannot believe more people aren't doing it.

### 12. The Three Steps (modules)

**Section background:** surface color. Borders top + bottom.

**Eyebrow:** `WHAT'S INSIDE`

**Title:**
> Three steps. *Thirty days.* Your first software product.

**Sub:**
> Most "build a SaaS" advice assumes you're a Stanford CS grad. This is built for creators. Every step assumes zero technical background.

Below: 3 stacked module cards, each with a 4px lime left-border rail, mono step number, Instrument Serif title (lime italic accent), description, and a checklist of bullets with lime ✓ icons.

**MODULE 1:**
- Step number: `STEP 01`
- Title: `Discover Your *Million-Dollar Idea*`
- Desc: `How creators who win at this find ideas you actually want to build — for an audience that actually wants to buy.`
- Items:
  - **The Five Origins** — how every successful non-technical founder discovered their winning idea (and how to do it for yourself).
  - **The Audience-Match Test** — make sure the tool you want to build is one your audience will actually pay for.
  - **The Daily Extraction Protocol** — pull product ideas from your existing content, group chats, and DMs.
  - **The Moat Map** — make your idea defensible so the next person who sees your Stripe screenshot can't just clone you.
  - **The Launch Outline** — the one-page MVP scope doc that keeps you from over-building.

**MODULE 2:**
- Step number: `STEP 02`
- Title: `Build It With AI *In One Weekend*`
- Desc: `The exact tools, the exact prompts, the exact order — for someone with zero technical background.`
- Items:
  - **The Toolkit** — the exact 4 tools you need and the ones to skip. Setup is under 20 minutes.
  - **Master Prompt Engineering** — how to talk to AI so it builds what you actually want. This is the skill nobody teaches.
  - **The Core 7 Elements** — the seven essential building blocks every real software product needs (each with a copy-paste prompt):
- Inside Module 2: a dashed-border `Core 7` grid block (mono, 7 items): `01 Admin Panel · 02 Data Viz · 03 Security · 04 Database · 05 Referral System · 06 Knowledge Brain · 07 AI Employees`
- Final bullet:
  - **The Pricing & Margin Lab** — how to price for profit on day one (most beginners get this catastrophically wrong).

**MODULE 3:**
- Step number: `STEP 03`
- Title: `Your First *500 Customers* — For Free`
- Desc: `The part nobody else teaches. Built, but nobody came? Not on my watch.`
- Items:
  - **The Founders' Launch Method** — the $40,000-in-7-days playbook I personally use for every new product I roll out.
  - **TikTok Organic** — the algorithm that doesn't care if you have followers.
  - **Instagram Reels Organic** — the playbook the gurus stopped teaching when it actually started working.
  - **SEO in 2026** — why "SEO is dead" is the dumbest take on the internet right now.
  - **YouTube Organic + Influencer Outreach** — long-form is back. Plus the cold-DM script I've personally sent 4,000+ times.
  - **Meta + TikTok Influencer Plays** — partnership flows that get you on someone else's audience for $0 upfront.
  - *…and 8 more channels broken down step by step.*
- Closing italic line: `By the end of Step 3, you have a path to your first 500 paying users without a single dollar in ads.`

### 13. Bonuses — Power of Free

**Eyebrow:** `WHEN YOU START TODAY`

**Title:**
> Plus six bonuses, *free.*

**Sub:**
> Each one was built because, the first time I taught this, students asked for it. They're a bigger workload than the core program — and they're yours the second you check out.

**6-card grid (3 columns desktop):** Each card has a lime `FREE` pill in the top-right corner, an Instrument Serif name, a short description, and a struck-through dollar value below.

| Name | Description | Value |
|---|---|---|
| Master Prompt Library | The 12 prompts I personally use to build, debug, and deploy any app. Copy-paste-ready. | $197 value |
| 2026 Tool Stack Cheat Sheet | A live-updated map of every AI tool worth using — and the ones to skip. Updated monthly. | $97 value |
| Full Build-Along Video | Watch me take a brand-new app from idea → MVP outline → first working build → distribution gameplan. | $297 value |
| Founders' Launch Email Sequence | The exact 7-email sequence that produced $40K in launch revenue. Swipe and adapt. | $147 value |
| Private Vibe Coders Community | Get unstuck in minutes, not days. Real builders posting daily wins and roadblocks. | $197 value |
| 12 Months of Live Q&A | Monthly group calls with me. Ask anything, build live, get feedback. | $497 value |

**Total bonus card (dashed lime border, centered):**

> Total bonus value · **$1,432** · Yours free with the $49 Blueprint

### 14. Pricing

**Eyebrow:** `THE COMPLETE OFFER`

**Title:**
> $2,623 in real value. *$49 today.*

**Sub:**
> I priced this for action, not for margin. I'd rather have 10,000 creators inside actually doing this than 1,000 who paid $497 and never logged in.

**Pricing card (max 640px, centered, lime-tinted gradient header):**

- **Header:**
  - Pill row: lime `FOUNDERS PRICING` badge + `THE VIBE CODING BLUEPRINT` (mono uppercase)
  - Title (Instrument Serif): `Everything you need to build, ship & sell.`
  - Price row: small strike-through `$99` + huge `$49`
  - Mono sub: `Price increases to $99 in [live countdown]`
- **Body:**
  - "Instant access" row (lime-icon ⚡ + bold copy):
    > **Instant access.** The moment your payment clears, every module and every bonus is in your inbox. Step 1 takes ~12 minutes. You can have your idea shortlist before bedtime tonight.
  - Stack list (dashed-divider rows): each row shows name + struck-through value
    - **Step 1** — Discover Your Million-Dollar Idea — `$197`
    - **Step 2** — Build It With AI In One Weekend — `$497`
    - **Step 3** — Your First 500 Customers (Free) — `$497`
    - **Bonus 1** — Master Prompt Library (12 prompts I personally use) — `$197`
    - **Bonus 2** — 2026 Tool Stack Cheat Sheet (live-updated) — `$97`
    - **Bonus 3** — Full Build-Along Video — `$297`
    - **Bonus 4** — Founders' Launch Email Sequence (swipe file) — `$147`
    - **Bonus 5** — Private Vibe Coders Community — `$197`
    - **Bonus 6** — 12 months of live Q&A with Travis — `$497`
  - Total real value row (top border, struck-through): `Total real value · $2,623`
  - Today's payment row (lime-tinted box): `Today, one payment · $49`
  - **Big lime CTA button (full width):** `Claim my $49 Blueprint →`
  - **Guarantee box (mono, dark inset):**
    > 🛡️ **Build Something Or I Refund You.**
    > Go through it. Use the workflow. If at 30 days you haven't built at least one working version of your product, email me. Full refund. No forms.

### 15. Day 30 Future Pacing

**Eyebrow:** `30 DAYS FROM TODAY`

**Title:**
> Picture your life on *Day 30.*

**Card (max 720px, centered, dark with lime glow behind):**

Three stacked notification-row mocks (looks like Stripe mobile notifications):
- `S` icon · New subscription · Sarah K. · 2:14 AM EDT · `+$29.00`
- `S` icon · New subscription · Marcus B. · 3:07 AM EDT · `+$29.00`
- `S` icon · New subscription · Hannah L. · 6:41 AM EDT · `+$49.00`

Then Instrument Serif italic narration:

> You wake up. Stripe pinged three times overnight. Three new subscribers from the app *you* built last weekend using nothing but your laptop and a $20 AI subscription.

Then smaller body:

> You don't open your laptop with dread anymore — you open it with curiosity. *What should I build next?* Not *how do I make rent.* A year from now you have three. Four. Seven. Each one paying you more than your old course launches did combined.

### 16. FAQ

**Eyebrow:** `QUESTIONS`

**Title:**
> What you're *actually* wondering.

**8 expandable items (native `<details>` / `<summary>`, with rotating "+" indicator that becomes "×" when open):**

1. **I have no idea what vibe coding is. Is this really for me?**
   > Yes — this is built specifically for people who don't know what vibe coding is yet. The first half of Step 2 is a from-scratch walkthrough that assumes zero technical background. Most students inside the program had never built a website, let alone software, before joining.

2. **I've never built anything technical. Will this actually work for me?**
   > I genuinely couldn't write a single line of code when I started. The five apps I run today were all built by describing what I wanted to AI, in plain English. That's the entire skill. You don't need to be technical — you need to be able to describe what you want.

3. **What if I don't have a big audience yet?**
   > Step 3 is built specifically for creators with no audience. The Founders' Launch Method is how I get the first 500 paying users with $0 in ads, and it works whether you have 50 followers or 50,000.

4. **How is this different from just selling a course?**
   > A course sells once and sits in a Google Drive folder forever. A tool sells every month, gets used every day, and gets more valuable over time. Same audience, same effort — fundamentally different economics. The course era is ending. The tool era is starting.

5. **What does the finished product actually look like? Can you show me one?**
   > Inside the program you'll see live walkthroughs of five real products I built and currently run. Each one was built using the exact workflow taught in Step 2. They're not toys — real customers pay real subscriptions every month.

6. **What if my niche is really specific — can I still build something people will pay for?**
   > Specific niches are actually *better.* The marriage coach, the sourdough hobbyist, the golf instructor — every example you saw above is a tightly-focused niche. The narrower your audience, the easier it is to build exactly the tool they need.

7. **How much will I spend on tools to actually do this?**
   > Around $40–$60/month total once you're up and running. Less than what most people spend on lunch in a week. The Tool Stack Cheat Sheet (Bonus 2) walks you through the exact stack and prices.

8. **Why is it only $49? What's the catch?**
   > No catch. No hidden upsells, no recurring fee, no expiring access. I'd rather have 10,000 creators inside actually doing the work than 1,000 paying $497 and never logging in. The price goes to $99 when the countdown ends — but $49 today, lifetime, is the whole deal.

### 17. Final CTA

Centered section with a radial lime glow background.

**Title:**
> Two years from now, *one of two things* will be true.

**Body:**
> Either you'll have built a real software product that pays you every month — and you'll be the creator everyone else is asking how you did it. Or you won't. And someone with your idea, your audience, and half your taste will be answering those questions instead.

**Big countdown timer block (mono):**

> Founders pricing expires in
> `[ 00 days ] : [ 00 hrs ] : [ 00 min ] : [ 00 sec ]`

Each block is a small dark card with border-radius, big number on top, mono caption below.

**Final CTA button:**

> Lock in $49 before the price doubles →

**Fine print (mono uppercase):**

> 30-DAY GUARANTEE · ONE PAYMENT · LIFETIME ACCESS

### 18. Footer

Centered mono small text:

> © 2026 PaidCreators · Built (vibe-coded) by Travis Stephenson
>
> Terms · Privacy · Contact

---

## INTERACTIVE ELEMENTS (JavaScript)

Implement all inline in a single `<script>` at the bottom of the page. Zero dependencies.

### Theme toggle
Click toggles `data-theme` between `dark` and `light` on `<html>`. CSS handles the rest via attribute selectors. Default is dark.

### Countdown timer (7 days from page load)
- Multiple `[data-countdown]` inline targets across the page (urgency bar, pricing card sub, final CTA label) — render as `Xd Xh Xm`
- One `[data-countdown-blocks]` container in the final CTA with 4 child blocks: `[data-d] [data-h] [data-m] [data-s]` — each receives a 2-digit padded number
- Updates every 1 second
- When deadline hits zero, replace inline targets with the word `now`
- Deadline stored in `window.__vc_deadline__` so first visit anchors it

### Scroll reveal
- All `section`, `.proof-card`, `.module`, `.pricing__card` start at `opacity: 0; transform: translateY(24px); transition: opacity 600ms cubic-bezier(0.16, 1, 0.3, 1), transform 600ms cubic-bezier(0.16, 1, 0.3, 1)`
- `IntersectionObserver` (threshold 0.08, rootMargin `0px 0px -10% 0px`) sets them to `opacity: 1; transform: translateY(0)` and unobserves on first intersect
- Respects `prefers-reduced-motion`

### VSL play button
The VSL is a placeholder. The poster `<a>` should link to `#video-placeholder` for now — the user will replace this with a real YouTube/Wistia embed code later. Make it easy to swap by leaving a clear comment in the HTML.

---

## ACCESSIBILITY & QUALITY CHECKLIST

- All interactive elements have visible `:focus-visible` rings (2px lime outline, 3px offset, --radius-sm)
- All images have meaningful `alt` text
- Reduced-motion media query disables animations
- 4.5:1 contrast minimum on text — `--color-text-muted` is `#b4b4bc` (passes on `#0a0a0b`)
- Buttons have clear hover (lift + glow), active, and focus states
- All FAQ items use semantic `<details>` and `<summary>` — keyboard accessible by default
- Section landmarks: `<header>`, `<nav>`, `<main>` if applicable, `<footer>`
- Skip-to-content link not strictly required for a landing page but optional
- Lazy-load any below-the-fold images

---

## RESPONSIVE BREAKPOINTS

- Mobile-first base styles
- `max-width: 560px` — single-column everything, smaller display type
- `max-width: 880px` — two-column splits become single column
- `max-width: 960px` — 3-column grids become 2 then 1
- `max-width: 1080px` — wide content stays at 1080–1240 max-width

Test specifically at: 375px (mobile), 768px (tablet), 1440px (desktop). The hero must look great at all three.

---

## PROHIBITED PATTERNS (do not do these)

- ❌ No stock-photo people. Use only the Stripe screenshot.
- ❌ No emojis as icons. Use SVG only.
- ❌ No "AI slop" gradient mesh backgrounds with rainbow blobs.
- ❌ No multiple accent colors fighting for attention — only lime is accent.
- ❌ No carousels or auto-playing media.
- ❌ No exit-intent popups.
- ❌ Do not use `<i>` for icons — use SVG.
- ❌ No raw hex codes inside components — always reference CSS custom property tokens.

---

## DELIVERABLE FORMAT

Output three files:

```
/index.html
/style.css
/v2.css       (optional — can be merged into style.css)
```

Plus one image asset directory if the Stripe screenshot is needed:
```
/assets/stripe-mrr.jpg
```

The page should be fully functional opened directly from `file://` — no build step, no server required, no framework.

---

## ONE-SENTENCE BRIEF (if you need to summarize this whole thing)

> Build a dark-themed single-page landing page for "The Vibe Coding Blueprint" — a $49 program teaching non-technical creators to build software tools with AI. Follow the PAS narrative arc, use Instrument Serif + Inter + JetBrains Mono on a dark base with electric lime as the only accent, include a VSL at the top + Stripe proof in the story section + an Old Way vs New Way visual comparison + a glowing pricing card with offer stack, and ship a working countdown timer and theme toggle in vanilla JS.

---

# END OF MASTER PROMPT

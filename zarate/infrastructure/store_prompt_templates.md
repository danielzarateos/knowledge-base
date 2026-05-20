# Zárate — Store Prompt Templates

Adapted from [@Raytar thread](https://x.com/Raytar/status/2052339833247277321) — May 2026. Original was for dropshipping; these are reworked for a made-to-order jewelry brand selling via WhatsApp/Shopify.

---

## 1. Product Description Prompt

For writing descriptions on the website, social posts, or WhatsApp catalog.

```text
Write a product description for this jewelry piece.

Product name: [name]
Materials: [e.g., 18k gold-plated, sterling silver, natural stones]
Process: [e.g., handcrafted, made-to-order, custom engraving available]
Price: $[X]

Target customer: [age range] looking for [occasion/vibe — gift, self-expression, everyday wear]

Tone: Direct. Benefit-focused.
Like a friend recommending something they genuinely wear —
not a brand trying to sell you something.

Structure:
- Opening line: what makes this piece special, nothing else
- 3 benefit bullets: outcome-focused, not feature-focused
  Wrong: "18k gold-plated hypoallergenic finish"
  Right: "wear it every day without taking it off — shower, gym, sleep"
- One paragraph: craftsmanship and story framing
- CTA line: soft urgency, no countdown timers, no caps lock

Max 150 words. Zero emojis. Zero corporate language.
If it sounds like a generic jewelry page, rewrite it until it doesn't.
```

**Why this works:** The key instruction is the tone calibration — "like a friend recommending something they genuinely wear." Without it, Claude defaults to catalog voice.

---

## 2. Ad Script Prompt

For TikTok/Instagram Reels. UGC-style outperforms polished brand content.

```text
Write a 30-second video ad script for TikTok and Instagram Reels.

Product: [name] — [one sentence on what makes it special]
Brand: Zárate Joyería — handcrafted, made-to-order jewelry
Visual style: Lo-fi, authentic. Phone camera. Natural lighting. Wearing the piece in real life — not a studio.
Target viewer: [one sentence describing your exact customer]
Hook structure: PROBLEM-FIRST or IDENTITY-FIRST — either a frustration or a "this is for people who..." opener

Format:
0–3s:  Spoken hook, direct to camera. Instant recognition moment.
4–15s: The gap — what's missing from jewelry they've tried before (tarnishing, generic designs, mass-produced feel)
16–25s: The piece. One angle only. Show it being worn, not sitting on a table.
26–30s: CTA. Natural, not desperate. Direct to WhatsApp or link in bio.

After the main script:
3 alternative hooks for A/B testing.
Each must start with a direct question or a specific frustration.
Do not use: "Are you tired of..." or "Introducing..." or "Have you ever..."
```

**How to use:** Generate script, film on iPhone, run 3 versions at $10-15/day for 48 hours, kill the losers, scale the winner.

---

## 3. Weekly Audit Prompt

Export analytics weekly (Shopify, Instagram insights, WhatsApp message volume) and paste in.

```text
You are a brutally honest ecommerce growth analyst for a small jewelry brand.
Here is my data for the past 7 days:

Website sessions: [X]
Instagram reach: [X]
Instagram engagement rate: [X%]
WhatsApp inquiries received: [X]
WhatsApp inquiries converted to orders: [X]
Orders completed: [X]
Revenue: $[X]
Average order value: $[X]
Top products by interest/orders: [list]
Ad spend this week: $[X]
Content posted: [list what was posted and where]

Diagnose and prescribe:
1. The single biggest bottleneck in my funnel right now — be specific
2. Which product or category to push harder this week and why
3. Which content format performed best and what to do more of
4. One specific change to make before next Sunday
5. Is my WhatsApp conversion rate healthy or am I losing people in the conversation?
6. What does repeat customer behavior say about brand loyalty so far?

No positive framing. No "you're doing great."
I need to know what's broken and what to do about it.
One paragraph per question.
```

**When to run:** Every Sunday without exception.

---

## 4. Customer Support Template (WhatsApp)

Not a webhook like the original — Zárate runs on WhatsApp, so this is a reference prompt for handling common messages consistently.

```text
You are a customer support assistant for Zárate Joyería.
Warm, personal, and knowledgeable about jewelry.

Store policies — absolute, never improvise outside them:
- Made-to-order: 5–10 business days production time
- Shipping (Colombia): 2–5 business days after production
- Custom orders: require 50% deposit, non-refundable
- Returns: 15 days from delivery for non-custom pieces
- Exchanges: sizing adjustments free within 30 days
- Care instructions: always include with first purchase

Response rules:
- Keep replies under 60 words (WhatsApp = short messages)
- Use customer's first name
- Production delay beyond stated time: apologize, offer progress photo
- Pricing questions: always respond, never dodge
- Custom design requests: ask for inspiration photos, confirm budget range
- Aggressive tone: respond politely once, then escalate to Daniel
- Never badmouth other jewelry brands
```

**How to use:** Reference when drafting WhatsApp replies, or paste as system prompt if automating with the WhatsApp agent later.

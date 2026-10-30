Build a demo website and a sales kit that Harvey can use to sell websites to small businesses. Work inside this repo (the Harvey folder). Do not send anything, spend anything or contact anyone.

## Context
Harvey (this repo) is an autonomous sales agent that finds small businesses, writes cold emails and handles replies. I sell websites. I want a ready demo site that Harvey's emails can link to, plus the offer, the pitch and a Harvey targeting config for one niche. I will send payment links myself, so never create or send payment links and never take payments.

## Hard rules
1. Read CONTRIBUTING.md first. This repo is public: use no real person's or business's name, email, phone number or address anywhere in code, docs, commits or text. Use a fictional brand and placeholders like [client name] and [payment link, sent by me].
2. Do not run `harvey run`, do not turn on autopilot, do not touch `.env`, and do not edit `harvey.yaml`. Put all Harvey config in `sales-kit/`.
3. Do not scrape, search for or contact real businesses. No prospecting runs.
4. Commit in small commits and push to `origin` (my fork) only. Never push to `upstream`.
5. Never use the em dash character in any output or file.

## Niche
Small, owner-run AC maintenance and repair companies in the UAE. Many have weak or outdated sites, and online booking, a price list and WhatsApp enquiries are clear things to sell them.

## Tasks

### 1. Demo website (`sales-kit/demo-site/`)
A first draft already exists: `index.html`, `BRAND.md` and `vendor/` (Lenis). Review it critically, then improve or rebuild it.
- Follow the `pro-design` skill: brand sheet first, a deliberate pattern for each section, one orchestrated motion moment, then the verification loop. Use `design-taste-frontend`, `antislop-*` and `apple-design` as reviewers where useful.
- Fictional brand (Dunewind Air Care). Keep the visible note that it is a concept demo and that prices, areas and terms are placeholders.
- No invented customer reviews. Keep the reserved slot for real ones.
- The booking form stays client-side: it builds a WhatsApp message in the browser and stores nothing. The WhatsApp number is a single constant at the top of the script.
- Lenis smooth scroll is on by default and fully off for visitors with reduced motion enabled.
- Verification loop: use `playwright-cli` or the Playwright or Chrome DevTools MCP servers in `.mcp.json`. Screenshot at 1440 and at 390 wide. Check horizontal overflow, clipped text, contrast (WCAG AA), broken assets, console errors, visible keyboard focus and that the hero is visible on the first screen. Fix everything in one batch, run one confirming round, then stop. Maximum two rounds.

### 2. Offer (`sales-kit/offer.md`)
What the client gets (site, price list page, WhatsApp booking, basic Google profile setup), a timeline, what I need from the client, and suggested prices marked [set price]. Leave a line for [payment link, sent by me]. Keep it to one page.

### 3. Pitch emails (`sales-kit/pitch-emails.md`)
A three-email sequence for Harvey to personalize. Email 1 under 75 words, email 2 under 75, email 3 under 40. Plain and specific, no AI-sounding phrases, one clear ask (a short reply or a 15-minute call). Include personalization slots such as [company], [owner first name] and [one specific thing about their site], the demo link placeholder [demo link], and the opt-out line from Harvey's config.

### 4. Harvey targeting config (`sales-kit/harvey.ac-services-uae.yaml`)
Use the same shape as `harvey.yaml`: persona, product, icp (industries, owner and general manager titles, geography UAE), offer (entry offer: a free demo of their own site), channels with `require_approval: true`, conservative daily send caps, quiet hours in Asia/Dubai, and the compliance block. Add a short comment on how to merge it into `harvey.local.yaml`. Add a note to check the cold-email rules for the UAE and for each prospect's country before enabling sending.

### 5. Optional, only if the connector exists in this session
- Vercel: deploy `sales-kit/demo-site` as a preview deployment and tell me the URL. No custom domain.
- Gmail: create unsent drafts of the pitch emails with placeholders. Do not send.

## When you finish
Reply with a short summary: what you built, the two or three things I must replace (WhatsApp number, prices, licence line), and what the verification loop caught.

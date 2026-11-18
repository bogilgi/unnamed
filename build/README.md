# Dopamine Desk — Project Package

An ADHD productivity systems membership: a living Notion operating system + community, sold as a recurring membership on Whop.

## Documents

| # | Doc | What's in it |
|---|---|---|
| 01 | [Brand](01-brand.md) | 5 names + taglines, recommendation (**Dopamine Desk**), naming system, voice rules |
| 02 | [Sales page](02-sales-page.md) | Full long-form copy for the $47/mo offer + micro-copy library |
| 03 | [Notion architecture](03-notion-architecture.md) | Every database, property, formula and view. Page specs for Today / Bad Day Mode / Re-Entry / Review / Time Tools |
| 04 | [Build prompts](04-notion-build-prompts.md) | 5 sequential build prompts (~13–15 h to v1.0) + the reusable monthly module prompt |
| 05 | [Lead magnet](05-lead-magnet.md) | *The 20-Minute Reset*, written in full, + 4-email delivery sequence |
| 06 | [Whop listing](06-whop-listing.md) | Store copy, 3 tiers, 12-question FAQ, full setup & pre-launch checklist |
| 07 | [Content](07-content-30-days.md) | 30-day calendar + 10 ready-to-film scripts + production system |
| 08 | [Onboarding](08-onboarding.md) | 8 emails, win-back, all Discord pinned posts, weekly rhythm, cancellation flow |
| 09 | [Monthly updates](09-monthly-update-process.md) | The four-window process that keeps the subscription honest, + metrics & failure modes |
| **10** | [**Vault: Scripts**](10-vault-scripts.md) | **9 send-ready scripts** — extensions, telling your boss, cancelling honestly, accommodations, the 3-week-old email, assessment referral, parents, partners, apologising without spiralling |
| **11** | [**Vault: Checklists**](11-vault-checklists.md) | **8 timed checklists** — doom pile, pre-appointment, taxes entry point, 20-min apartment reset, packing, meds ran out, job applications, inbox amnesty |
| **12** | [**Vault: Protocols**](12-vault-protocols.md) | **5 protocols** — dread tasks, time multiplier, the 2pm crash, hyperfocus exit, Sunday dread |
| **13** | [**Vault: Worksheets**](13-vault-worksheets.md) | **3 worksheets** — Energy Audit, Abandonment Autopsy, Accommodation Inventory |
| **14** | [**The 12 routines**](14-routines.md) | Every routine with steps, minutes, skip-safe flags and its bad-day **Minimum Version** |

| **15** | [**First-run & remaining copy**](15-first-run-and-copy.md) | The 4-minute first-run page, 22 empty states, demo seed data, the 90-second walkthrough script, the six-tap audit |
| **16** | [**Launch runbook**](16-launch-runbook.md) | The single ordered path through all of it: 8 phases, ~28 h, plus the "not yet" list |
| **17** | [**Free setup walkthrough**](17-free-setup-walkthrough.md) | Every click to launch for $0 — Beehiiv, Notion, Discord, Whop, and what Whop actually takes |
| — | [**landing-page.html**](landing-page.html) | The live landing page (published — see below) |
| — | [**notion-csv/**](notion-csv/README.md) | 8 CSVs, 175 rows, importable straight into Notion + the property types to set afterwards |

**Docs 10–15 are the product itself** — 25 Vault resources and 12 routines written in full, ready to paste into Notion. This is the content that makes day one feel worth $47 rather than feeling like an empty template.

## Decisions already made (change deliberately, not by accident)

- **Name:** Dopamine Desk. Tagline: *A workspace your brain actually wants to open.*
- **Main offer:** Desk + Crew, $47/mo or $397/yr. Tier 1 at $29. Tier 3 (`Executive Reset`) not before 100 members.
- **No free trial.** 14-day refund instead — email the word *refund*.
- **Energy is the primary sort axis**, not dates.
- **Three features carry the differentiation:** Bad Day Mode, Re-Entry, and the monthly Changelog.
- **The subscription sells maintenance, not files.** Every piece of copy has to make that legible.

## Start here

**[16-launch-runbook.md](16-launch-runbook.md)** — the ordered path, with time estimates and the list of things not to do yet. Everything below is the older summary.

## Build order

1. Doc 04 sessions 1–5 → The Desk v1.0 (~15 h). **Build prompt 4 is now mostly done** — paste docs 10–14 in instead of generating the Vault from scratch, which cuts the longest session roughly in half
2. Doc 05 → lead magnet live + email capture
3. Doc 06 → Whop store, both tiers, clean-account purchase test
4. Doc 02 → sales page
5. Doc 08 → Discord set up, pins posted, 4 weeks of sessions scheduled
6. Doc 07 → start posting daily (day 1 is the first revenue-relevant day)
7. Doc 09 → run the monthly cycle from month one, even at 5 members

**Do not build before step 1 is done.** Do not launch paid ads, affiliates, or Tier 3 before 20 paying members.

## Two things to get right that aren't in the docs

- **Legal/claims:** nothing anywhere should claim to treat, manage or improve ADHD symptoms. The disclaimer (*not medical advice, not a treatment*) belongs on the sales page, the Whop listing, the Discord rules and the Notion home page. The community rule banning medication advice is the one rule to enforce firmly, every time.
- **The monthly promise is the business.** It is the reason recurring pricing is defensible. Doc 09 budgets ~10 hours a month for it. Protect those hours ahead of content, ahead of ads, ahead of everything.

## Loading the Vault into Notion (docs 10–14)

Notion imports Markdown directly, so this is paste work, not retyping.

**The Vault (docs 10–13 → `DB: Resources`)**
1. Create the 25 rows first, filling only `Resource`, `Type`, `Use when`, `Topic`, `Minutes`, `Energy` from each heading block. 25 rows, ~20 minutes.
2. Open each row and paste its body. Markdown pastes into Notion with headings, tables, callouts and checkboxes intact.
3. Tick `New this month?` on all 25 for launch month — it populates the "New this month" gallery on day one, which is the first thing a new member sees.
4. The `> blockquote` at the top of most resources should become a Notion **callout** block. It's the framing line, and it's the bit that makes the resource feel written by someone with the same brain.

**The routines (doc 14 → `DB: Routines` + `DB: Routine Steps`)**
1. 12 rows in `Routines`: `Routine`, `When`, `Energy Needed`, `Minimum Version`.
2. Each table becomes rows in `Routine Steps` — paste the table into the Steps database view and map the columns (`Step`, `Order`, `Minutes`, `Optional?`, `Skip-safe?`).
3. Set `Active` = ✅ on **only three**: R1 Morning, R3 Work Shutdown, R7 Bad Day Minimum. The over-adoption failure in week one is real and this prevents it.

**Realistic time:** 3–4 hours of paste-and-map for all 37 pieces. Do it in two sittings, Vault first.

## The landing page

`landing-page.html` is published and live at **https://claude.ai/artifact/BDYqJ1QoZb32LacJdTxhpG**

It carries the hero, the four failure modes, what's inside, the three differentiators, pricing, the lead-magnet opt-in and the FAQ — plus a live interactive demo of energy-sorting and Bad Day Mode, which does more work than any paragraph of copy.

**Before you share it widely, two changes:**
1. **Swap the placeholder email** (`hey@dopaminedesk.com`) for a real address you own.
2. **Decide on the opt-in.** Sign-ups on this page write to the artifact's own store, which means only signed-in Claude viewers can submit; everyone else gets the email fallback. That's fine for showing people and for warm traffic, and wrong for cold TikTok traffic. **For the $0 path, don't use this page as your front door at all** — build the opt-in in Beehiiv's free tier instead (doc 17) and keep this page as a demo you can send people. Put it on a real domain later, once revenue pays for one.

Sign-ups are readable only by you: the access rules let each viewer write their own row and nobody else's, and only an editor can list the collection.

## What's left after this

- [ ] Build the Notion workspace itself — doc 04, prompts 1, 2, 3, 5 (~9–10 h; prompt 4's Vault is now written)
- [ ] Paste in docs 10–14 (~3–4 h)
- [ ] Real domain + real email provider for the landing page
- [ ] Whop store — manual, ~30 min of pasting from doc 06, after the product exists
- [ ] Discord set up, pins posted, 4 weeks of sessions scheduled (doc 08)
- [ ] Start posting (doc 07)

Everything that can be written has been written. What remains needs your accounts: Notion, Whop, Discord, a domain, an email provider.

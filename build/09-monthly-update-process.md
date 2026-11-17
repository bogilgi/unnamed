# 09 — The Monthly Update Process (the operating system of the business)

This is the most important process in the company. The monthly update is what justifies recurring pricing, and it is the one promise that, if broken twice, ends the business. Everything else can slip.

**The commitment, stated publicly:** 1–2 new modules or significant upgrades per month, plus 3–5 new Resource Vault pieces, shipped and announced by the **last working day of the month**, with a public changelog naming who requested each.

**Total time budget: ~10 hours per month, spread over four defined windows.** If it takes more than that, you built too big. Scope down, don't skip.

---

## The month at a glance

| Days | Window | Hours | Output |
|---|---|---|---|
| 1–20 | **Passive collection** | ~0 | A full request list, gathered as a by-product of being present |
| 21–22 | **Triage & commit** | 1.5 | One module chosen, scope fixed, publicly announced |
| 23–27 | **Build** | 5–6 | The module built, tested on mobile, demo-ready |
| 28–end | **Ship & announce** | 2 | Changelog, Loom, Discord post, email, 3 shorts |

---

## Window 1 — Passive collection (days 1–20)

**The rule: never run a survey.** Surveys get a 4% response rate from this audience and the responses are polite rather than true. Everything you need is already being said; your job is capture, not solicitation.

**Five sources, in descending order of signal quality:**

1. **`#system-help` questions.** A repeated question is a design failure, not a support issue. Three people asking the same thing = build it.
2. **`#low-energy-days` complaints.** The richest source in the business. Unprompted descriptions of where life breaks. Watch for "I wish there was a way to…" and "I always forget to…".
3. **Comment sections on your own videos.** Specifically every "what about when…" reply. Also tells you what the *market* wants, not just current members, which matters for the sales page.
4. **Cancellation replies.** Low volume, highest-value. A cancellation reason is a product spec written by someone with nothing left to lose.
5. **Your own friction.** You use this daily. Where you work around your own system is a real finding — but it ranks last, because you are not the median member. Discipline yourself about this.

**Capture mechanism:** one `Requests` database (`Request` · `Source` · `Member` · `Verbatim quote` · `Votes` · `Theme` · `Status`). Add rows the moment you see them, never later. Always store the **exact words** — the verbatim quote becomes the changelog entry, the announcement, and often the video hook.

**Target: 20–40 requests by day 20.** If you have fewer than 10, you are not present enough in the community, and that is the actual problem to fix this month.

---

## Window 2 — Triage & commit (days 21–22, 90 minutes)

**Step 1 — Cluster (20 min).** Group requests into themes. Seven unrelated requests often turn out to be one missing module. Score each theme:

| Criterion | Weight | Question |
|---|---|---|
| Frequency | ×3 | How many distinct members asked? |
| Pain depth | ×2 | Does this cost them money, a relationship, or a job? |
| Build cost | ÷ | Can it be done in under 6 hours? |
| Demo-ability | ×2 | Can it be shown in a 20-second screen recording? |
| Data safety | gate | Can it ship without touching existing properties? **Hard requirement.** |

**Step 2 — Pick exactly one module (10 min).** One. A single well-finished module beats three half-done ones every time, and it's easier to announce.

**Step 3 — Fix the scope in writing (20 min).** Write, before building:
- what it does, in one sentence a member would say
- the three things it does **not** do
- the properties it adds (never renames, never deletes)
- the 20-second demo

**Step 4 — Announce it publicly in `#announcements` (10 min).**

> **This month's build: [module]**
> Asked for by [names]. Here's what it'll do: [one sentence].
> Shipping by [date]. Anything it absolutely must handle, say so this week in #system-help.

> Announcing before building is deliberate and it does three jobs: it creates external accountability, it generates free specification feedback, and — the big one — it makes the subscription *visibly alive* for 7 days before anything ships. Members who can see the product moving do not churn.

**Step 5 — Close the loop on everything you didn't pick (30 min).** Reply to every unbuilt request individually:

> "Not this month — [honest one-line reason]. It's logged and on the list. [If it's never happening: here's what I'd do instead in the meantime.]"

Never let a request go unacknowledged. An ignored request is a cancellation in four months.

---

## Window 3 — Build (days 23–27, 5–6 hours)

Run the **Monthly Module Prompt** from doc 04. Then, in order:

1. **Build it** (3–4 h)
2. **Use it yourself for 48 hours** (0 h extra — you live here). Non-negotiable. Shipping something you haven't personally used is how trust goes.
3. **Mobile pass** (30 min): portrait, one-handed, ≤3 taps for the core action. If it fails on a phone it has not shipped.
4. **Duplicate test** (15 min): duplicate it into a clean Desk as a member would. Formulas and relations break on duplication more often than you'd like, and finding that out from a member is expensive.
5. **Write 3–5 Resource Vault pieces** (1 h). These are the cheap half of perceived value: a script, a checklist, a protocol. Tag them `New this month ✅`.
6. **Record the 20-second demo** (15 min). Silent screen recording. This is simultaneously the announcement asset, three social videos, and a sales-page asset.

**Scope-cut rule:** if day 27 arrives and it isn't done, ship the smaller version with a note — *"v1 of this, [specific thing] coming next month."* **Never slip the date.** A smaller module on time builds more trust than a bigger one late; the date is the promise, the size isn't.

---

## Window 4 — Ship & announce (days 28–end, 2 hours)

Five artefacts, in this order:

**1. Changelog entry** (10 min) — DB `Changelog`: what changed, where to find it, who requested it (first names). The three newest appear on every member's Desk home page automatically.

**2. Discord announcement** (15 min), under 80 words, zero hype:
> **[Module] is live** 🆕
> [One sentence on what it does.]
> Requested by [names].
> Drag it into your Desk from [link] — it won't touch anything you already have.
> Also new: [N] Vault pieces ([titles]).
> 20-second demo below. Questions in #system-help.

**3. Loom / 60-second walkthrough** (20 min) — one take, don't re-record, visible imperfection is on-brand.

**4. Member email** (20 min) — subject: `new this month: [module]`. Under 100 words. One CTA.

**5. Three short-form videos** (45 min) — the module is this month's free content. Hook on the *problem* it solves, never on "new feature." "Here's what's new in my system" performs badly; "I kept forgetting to [X] until I built this" performs.

**Then: close the month.** Mark built requests `Shipped` and DM each requester personally:
> "That thing you asked about — it's live. Thanks for flagging it." ← disproportionately powerful for retention. Costs 30 seconds.

---

## Quarterly: the bigger moves (every 3rd month, instead of a small module)

- **Fresh Desk release** (`v1.3`, `v2.0`): a full clean version with a documented migration path. Many members *want* a fresh start — a new Desk is itself a dopamine hit — so make it opt-in and never required.
- **Vault audit:** delete anything unused. A Vault that only grows becomes unsearchable, and unsearchable means unused.
- **Friction re-audit:** re-run the tap-count audit from build Prompt 5 across the whole system. Friction creeps back in with every addition.
- **Churn interviews:** 15 minutes each with three churned members. Ask one question: *"what was happening in your life the week you stopped opening it?"* The answer is almost never about features.

---

## The dashboard (five numbers, reviewed monthly, nothing else)

| Metric | Target | Why this one |
|---|---|---|
| MRR | step targets: $1k → $5k → $11k | |
| Monthly churn | < 8% after month 3 | The only number that decides whether this works |
| Day-30 active rate | > 60% | Leads churn by 60 days; your earliest warning |
| Open Desk attendance | > 25% of Crew monthly | Highest correlate of retention in the product |
| Modules shipped on time | **12/12 per year** | The promise. Protect it above all else |

**If churn goes above 12%:** stop all content and all new features. The problem is onboarding or community, never module count. Interview ten members instead.

---

## Failure modes to watch for (each one has killed a membership like this)

| Failure | Looks like | Fix |
|---|---|---|
| **Feature bloat** | 40 modules, nobody can find anything | Hard cap the core Desk. New modules are opt-in add-ons, not core |
| **Operator burnout** | Shipping late, posting less, dreading the community | Drop to 1 module/month and say so publicly. Members will accept a reduced promise; they won't accept a broken one |
| **Ghost community** | 300 members, 4 posters | You post daily for the first 6 months. Full stop. The rhythm posts in doc 08 are the minimum |
| **Shipping for yourself** | Modules nobody requested | A request with 3+ distinct members, or it doesn't get built |
| **Silent breakage** | Formulas broken after duplication | The duplicate test, every single month, without exception |
| **The content treadmill** | Growth stops when you stop filming | Build the email list from day one; it's the only asset you own |

# 03 — The Desk: Complete Notion Information Architecture

**Design constraints that drove every decision below:**
1. **Three databases do 90% of the work.** More databases = more places a thought can go = decision paralysis = abandonment. Everything is linked views, not new databases.
2. **Capture has one destination.** The Brain Dump feeds one inbox, always.
3. **No required fields, ever.** Every property has a default. A task with only a title is a valid task.
4. **Energy is the primary sort axis. Date is secondary.**
5. **Every view must be usable on mobile in portrait** — that means ≤3 visible properties per card and board views over tables wherever possible.
6. **Formulas over automation.** Notion automations break silently on mobile and on duplicated templates; formulas don't.

---

## PAGE TREE

```
🧠 THE DESK  (top-level page — the only page a member needs to bookmark)
│
├── ▸ TODAY            ← default landing content, lives ON the Desk page
├── ⚡ BAD DAY MODE      (page)
├── 🔄 RE-ENTRY         (page)
│
├── 📥 Brain Dump       (page — capture + triage)
├── ✅ Tasks            (page — the full task manager, 6 views)
├── 📦 Projects         (page — list + Decomposer)
├── 🔁 Routines         (page — Routines Library)
├── ⏱ Time Tools       (page — estimator + visual timeline)
├── 📊 Weekly Review    (page — the 18-minute review)
├── 📈 Streaks          (page — imperfect habit tracker)
├── 📚 Resource Vault   (page — gallery)
├── 👥 Open Desk        (page — body-doubling schedule)
│
└── ⚙️ System           (collapsed toggle — nobody opens this)
    ├── 🗄 DB: Tasks
    ├── 🗄 DB: Projects
    ├── 🗄 DB: Notes & Captures
    ├── 🗄 DB: Routines
    ├── 🗄 DB: Routine Steps
    ├── 🗄 DB: Habits
    ├── 🗄 DB: Habit Log
    ├── 🗄 DB: Resources
    ├── 🗄 DB: Reviews
    ├── 🗄 DB: Energy Log
    ├── 🗄 DB: Sessions (Open Desk)
    ├── 🗄 DB: Changelog
    └── 📄 Settings (member's personal constants)
```

---

## DATABASE SPECIFICATIONS

### 🗄 DB 1 — `Tasks`
The spine of the system.

| Property | Type | Options / Formula | Default | Notes |
|---|---|---|---|---|
| `Task` | Title | — | — | Only required thing |
| `Done` | Checkbox | — | unchecked | Checkbox, **not** a status select — one tap on mobile |
| `Energy` | Select | 🪫 Low · 🔋 Medium · ⚡ High | 🔋 Medium | **Primary axis.** "What will this cost me?" |
| `Dopamine` | Select | 🎯 Quick win · 🌊 Flow-friendly · 🧱 Dread · 👥 Needs a human · 🤖 Autopilot | 🎯 Quick win | "What kind of reward shape is this?" |
| `Size` | Select | 2 min · 15 min · 1 hr · Chunky | 15 min | Durations, not points — abstractions don't land |
| `Context` | Multi-select | 💻 Computer · 📞 Phone · 🏠 Home · 🚗 Errand · 🧠 Thinking · 💬 Admin | empty | |
| `Project` | Relation → `Projects` | — | empty | |
| `Do Date` | Date | — | empty | **Intention**, not deadline. Freely movable, zero guilt |
| `Hard Deadline` | Date | — | empty | Only real external consequences go here |
| `Today` | Checkbox | — | unchecked | The manual "I choose you" flag. Cleared by the Weekly Review |
| `The One Thing` | Checkbox | — | unchecked | Max one at a time; the Today view shows only this |
| `Est. (min)` | Number | — | empty | Member's gut guess |
| `Actual (min)` | Number | — | empty | Filled afterwards, feeds the Time Multiplier |
| `Age` | Formula | `if(prop("Done"), 0, dateBetween(now(), prop("Created"), "days"))` | — | |
| `Status Flag` | Formula | see below | — | Drives the Stale view |
| `Next Action?` | Formula | `and(not(prop("Done")), prop("Size") == "2 min")` | — | Powers the 2-Minute Pile |
| `Created` | Created time | — | auto | |
| `Completed` | Date | — | — | Set by button/automation on Done |
| `Notes` | Text | — | empty | |

**`Status Flag` formula (paste as written):**
```
if(prop("Done"), "✅ Done",
 if(and(not(empty(prop("Hard Deadline"))), prop("Hard Deadline") < now()), "🔴 Overdue (real)",
  if(prop("Age") > 30, "🧊 Frozen — decide or delete",
   if(prop("Age") > 14, "🕸 Stale",
    "🟢 Live"))))
```

**Views on the `Tasks` page:**

| # | View name | Type | Filter | Sort | Visible props |
|---|---|---|---|---|---|
| 1 | **By Energy** | Board, grouped by `Energy` | `Done` is unchecked | `Size` asc | Dopamine, Size |
| 2 | **2-Minute Pile** | List | `Next Action?` is true | `Created` asc | Context |
| 3 | **Today** | List | `Today` is checked, `Done` unchecked | `Energy` asc | Size, Project |
| 4 | **This Week** | Calendar on `Do Date` | `Done` unchecked | — | Energy |
| 5 | **Real Deadlines** | Table | `Hard Deadline` is not empty, `Done` unchecked | `Hard Deadline` asc | Hard Deadline, Project |
| 6 | **Dread Pile** | Gallery | `Dopamine` is 🧱 Dread, `Done` unchecked | `Age` desc | Size, Project |
| 7 | **Frozen** | Table | `Status Flag` contains 🧊 | `Age` desc | Age, Project |
| 8 | **Done This Week** 🎉 | Gallery | `Completed` is within past week | `Completed` desc | Energy |

> View 8 is not decoration. Visible evidence of completed work is the single strongest retention mechanic in the product. Put it directly under the task board, never on its own page.

---

### 🗄 DB 2 — `Projects`

| Property | Type | Options / Formula | Notes |
|---|---|---|---|
| `Project` | Title | — | |
| `State` | Select | 💭 Idea · 🔨 Active · 😶‍🌫️ Parked · ✅ Shipped | Max **3** Active, enforced by a callout not a rule |
| `Why it matters` | Text | — | One sentence. Re-read when motivation vanishes |
| `What does done look like?` | Text | — | The single most valuable field in the database |
| `Next Action` | Rollup | `Tasks` → `Task`, filtered `Done` unchecked, **Show original**, limit 1 | Never shows a project without a next step |
| `Tasks` | Relation → `Tasks` | — | |
| `Open` | Rollup | count unchecked `Done` | |
| `Progress` | Formula | `if(prop("Total")==0, 0, (prop("Total")-prop("Open"))/prop("Total"))` shown as bar | |
| `Hard Deadline` | Date | — | |
| `Energy Cost` | Select | 🪫/🔋/⚡ | How heavy the project *feels* |
| `Last Touched` | Rollup | max of `Tasks.Completed` | Powers "forgotten projects" |

**Views:** `Active` (board by State) · `Next Actions Only` (table: Project + Next Action, the most-used view) · `Parked` (gallery, reviewed monthly) · `Shipped` 🎉 (gallery, never delete).

**On-page tool — the Project Decomposer**
A template button that creates a child page with this structure (member fills in 5 prompts, generates tasks):
1. *What's the scary version of this?* (one line, unfiltered)
2. *What does done look like?* → copied to the project property
3. *If I had to do only one 15-minute piece today, what would it be?* → creates Task, `Size`=15 min, `Today`=✅
4. *What's the first physical action?* (open X, email Y, find the file) → creates Task, `Size`=2 min
5. *What am I actually avoiding here?* → creates Task with `Dopamine`=🧱 Dread (naming it halves it)

---

### 🗄 DB 3 — `Notes & Captures` (the Brain Dump target)

| Property | Type | Options | Notes |
|---|---|---|---|
| `Thought` | Title | — | Only field ever filled at capture time |
| `Triaged` | Checkbox | — | |
| `Type` | Select | 🧠 Thought · ✅ Task-shaped · 💭 Project-shaped · 🔗 Link · ❓ Question for the Crew | Set at triage, never at capture |
| `Became` | Relation → `Tasks` | — | |
| `Captured` | Created time | — | |

**Views:** `Inbox` (list, `Triaged` unchecked — mobile default) · `Triage` (table with Type + a "→ Task" button) · `Reference` (gallery, Type=Thought/Link).

**The capture rule, stated on the page in a callout:**
> Dump it. Don't sort it. Sorting is a different brain state and it's not your job right now.

---

### 🗄 DB 4 — `Routines` + 🗄 DB 5 — `Routine Steps`

`Routines`: `Routine` (title) · `When` (select: Morning / Work start / Work shutdown / Evening / Reset / Leaving the house / Bad day) · `Energy Needed` (🪫/🔋/⚡) · `Minutes` (rollup, sum of step minutes) · `Steps` (relation) · `Active` (checkbox) · `Minimum Version` (text — **the 3-step version for bad days**).

`Routine Steps`: `Step` (title) · `Routine` (relation) · `Order` (number) · `Minutes` (number) · `Optional?` (checkbox) · `Skip-safe?` (checkbox — true means skipping it breaks nothing, and saying so out loud is the point).

**Views:** `My Routines` (board by `When`, `Active` only) · `Minimum Versions` (table: Routine + Minimum Version — this is the view that gets used) · `Library` (gallery of all pre-built routines to clone).

**Ships with 12 pre-built routines**, each with a minimum version: Morning (meds/water/one thing), Work Start, Work Shutdown (the one that protects tomorrow), Evening Landing, Leaving the House, Post-Meeting Dump, Bad Day Minimum, Doom Pile Reset (15 min timer), Inbox Mercy Pass, Pre-Appointment, Sunday Soft Reset, Re-Entry After Absence.

---

### 🗄 DB 6 — `Habits` + 🗄 DB 7 — `Habit Log`

**Explicitly not a streak counter.** Streaks punish ADHD brains; the whole DB is designed around *rate*, not *consecutive days*.

`Habits`: `Habit` (title) · `Target per week` (number, 1–7) · `Why` (text) · `Energy` (🪫/🔋/⚡) · `Active` (checkbox) · `Log` (relation) · `This Week` (rollup: count of logs in past week) · `Hit Rate` formula:
```
if(prop("Target per week") == 0, "", format(round(prop("This Week") / prop("Target per week") * 100)) + "%")
```
· `Verdict` formula:
```
if(prop("This Week") >= prop("Target per week"), "🎉 Hit it",
 if(prop("This Week") >= prop("Target per week") * 0.5, "👍 Good enough — this counts",
  if(prop("This Week") > 0, "🌱 Non-zero. Non-zero is a win", "🔄 Fresh start, no debt")))
```

`Habit Log`: `Date` (date, default today) · `Habit` (relation) · `Note` (text, optional).

**Views:** `This Week` (board by Verdict) · `Tap to log` (gallery of Active habits with a one-tap log button — the mobile default) · `Last 8 Weeks` (table with 8 rollup columns, for pattern-spotting not scoring).

---

### 🗄 DB 8 — `Resources` (the Vault)
`Resource` (title) · `Type` (select: Script · Checklist · Protocol · Explainer · Worksheet · Template) · `Use when` (text — *the* search field; e.g. "I've been avoiding an email for 9 days") · `Topic` (multi-select: Work · Admin · Money · Health · Relationships · Home · Self-talk) · `Minutes` (number) · `Energy` (🪫/🔋/⚡) · `New this month?` (checkbox — drives perceived subscription value) · `Added` (created time).

**Views:** `Use when…` (table sorted by Topic — the primary view) · `New this month` ⭐ (gallery, `New this month?` checked) · `Under 5 minutes` (list) · `By topic` (board).

**Vault v1 contents (25 pieces, all written at launch):** 9 scripts (ask for a deadline extension · tell your boss you missed something · cancel plans without lying · ask for an accommodation · reply to a 3-week-old email · request a diagnosis referral · set a boundary with a parent · explain ADHD to a partner · apologise without spiralling) · 8 checklists (doom pile · pre-appointment · taxes entry point · apartment reset · packing · meds-ran-out contingency · job application · inbox mercy pass) · 5 protocols (Dread Task Protocol · Time Multiplier calibration · 2pm Crash Protocol · Hyperfocus Exit Protocol · Sunday Dread Protocol) · 3 worksheets (Energy Audit · Abandonment Autopsy · Accommodation Inventory).

---

### 🗄 DB 9 — `Reviews`
`Week of` (title, auto-formatted date) · `Date` · `Energy this week` (select: 🪫/🔋/⚡/🎢 All over) · `Wins` (text) · `What I'm not doing next week` (text — the **subtraction** prompt; most valuable field) · `One Thing for next week` (text) · `Frozen tasks killed` (number) · `Minutes taken` (number) · `Did I skip a week?` (checkbox — present so skipping is normalised, not hidden).

**Views:** `Recent` (list) · `Energy over time` (table, Date + Energy — members screenshot this for their psychiatrist, which is a surprisingly strong retention driver).

---

### 🗄 DB 10 — `Energy Log`
`Date` (title/date) · `Time of day` (select: Morning/Midday/Afternoon/Evening) · `Energy` (select 1–5 as emoji) · `Meds?` (checkbox) · `Slept well?` (checkbox) · `Note` (text).
One tap from the Today section. After ~3 weeks the member can see their real daily curve, which is the single most behaviour-changing artefact in the product.

**Views:** `Log it` (one-tap gallery) · `Pattern` (table grouped by Time of day) · `Last 30 days` (calendar).

---

### 🗄 DB 11 — `Sessions` (Open Desk)
`Session` (title) · `Starts` (date with time) · `Type` (select: Open Desk · The Reset · Dread Hour · Admin Sprint) · `Host` · `Link` (URL) · `Focus` (text) · `I'm coming` (checkbox) · `What I'll work on` (relation → Tasks).
**Views:** `Upcoming` (list, Starts is next 2 weeks) · `Calendar` · `I'm attending`.

---

### 🗄 DB 12 — `Changelog`
`Update` (title) · `Shipped` (date) · `Type` (select: New module · Improvement · New resource · Fix) · `Requested by` (text) · `What changed` (text) · `Where to find it` (text).

> **This is a sales asset disguised as a utility.** It is the proof that the subscription is alive. Pin the three newest entries on the Desk home page. Members who can see the product moving do not churn.

---

## THE TODAY SECTION (content on the Desk home page, top to bottom)

```
┌─────────────────────────────────────────────┐
│  🧠 THE DESK                                 │
│  [⚡ Bad day?]  [📥 Dump a thought]  [🔄 Been away?] │   ← 3 buttons, always first
├─────────────────────────────────────────────┤
│  THE ONE THING                               │
│  → linked view, Tasks, filter: The One Thing │   ← nothing else visible here
│    (if empty: "Pick one ↓")                  │
├─────────────────────────────────────────────┤
│  How's your brain? 🪫 🔋 ⚡    ← 3 buttons → Energy Log
├─────────────────────────────────────────────┤
│  WHAT FITS RIGHT NOW                         │
│  ▸ 🪫 Low energy  (toggle, collapsed)        │
│  ▸ 🔋 Medium      (toggle, collapsed)        │
│  ▸ ⚡ High        (toggle, collapsed)        │
├─────────────────────────────────────────────┤
│  ⏱ Next Open Desk session → [Join]           │
├─────────────────────────────────────────────┤
│  🎉 Done this week  (gallery, 7 days)        │
├─────────────────────────────────────────────┤
│  🆕 New this month  (Changelog, 3 newest)    │
└─────────────────────────────────────────────┘
```
**Hard rule: the fold.** On a phone, only the three buttons, The One Thing and the energy check are above the fold. Everything else is below or collapsed. If a member can see more than one decision on open, the design has failed.

---

## ⚡ BAD DAY MODE (page spec)
No databases. No counts. No calendar. Full-width callout:

> **Today is a maintenance day. That's a legitimate category of day.**

Then, in order:
1. **Three tasks, maximum** — linked Tasks view, filter `Energy`=🪫 Low AND `Size`=2 min, limit 3, list view, no properties shown.
2. **Minimum routine** — linked Routines view, `When`=Bad day, showing only `Minimum Version`.
3. **Four permissions**, as plain checkboxes: *Nothing today is urgent except [one thing]. · I can eat something easy. · I can tell one person. · Tomorrow is a different day and I don't have to make up for this one.*
4. **Vault shortcut** — Energy ≤🪫 resources only.
5. **[I'm back to normal →]** button back to the Desk.

**No link anywhere on this page returns to the full task list.** That is the entire design.

---

## 🔄 RE-ENTRY (page spec)
For members returning after a week+. Four steps, under five minutes, in this exact order:

1. **Don't read anything yet.** (callout)
2. **Kill the frozen stuff** — linked view, `Status Flag` contains 🧊, with the instruction: *delete anything that no longer matters. Deleting is doing.* Target: 10 deletions.
3. **One real deadline** — linked view, `Hard Deadline` not empty. *Is anything here actually on fire? Usually no.*
4. **Pick one 15-minute thing** — [Make it The One Thing] button.
5. **Say hi in #re-entry if you want. Or don't — nobody's keeping score.**

Plus a permanent line at the bottom: *"Members average 2–4 absences a year. The system is built for it. You did not break it."*

---

## ⏱ TIME TOOLS (page spec)
- **Your Time Multiplier** — formula block comparing sum(`Actual`)/sum(`Est.`) across tasks where both exist: *"You estimate at 1 : you actually take 2.4. Multiply your gut guess by 2.4."* Calibrates automatically as data accrues; shows "need 5 more data points" until n≥5.
- **The Estimator** — template button: name the task → gut guess → multiply → add 15 min buffer → creates the task with a realistic `Est.`
- **Visual timeline** — a day laid out as a single timeline board (Tasks calendar view in day mode) so hours have *width*. Time blindness is fixed by spatialising time, not by labelling it.
- **Three timers** embedded as links: 2 min · 15 min · 25 min.

---

## WEEKLY REVIEW (page spec) — target 18 minutes
A single template button creates the week's `Reviews` entry with a timer link and 7 steps, each with its own visible time budget:
1. (2 min) Clear the Brain Dump inbox — triage only, no doing
2. (3 min) Kill frozen tasks — delete, don't reschedule
3. (2 min) Celebrate: look at Done This Week
4. (3 min) Check real deadlines only
5. (3 min) **What am I NOT doing next week?** ← the subtraction step
6. (3 min) Pick next week's One Thing
7. (2 min) Clear all `Today` checkboxes
**Then stop.** No journaling, no goal review, no vision work. Callout at the bottom: *"If you only did step 2, that was a successful review."*

---

## ⚙️ SETTINGS (member constants page)
`My best hours` · `My crash time` · `My time multiplier` (auto) · `Max Active projects` (default 3) · `Bad-day definition in my own words` · `My non-negotiable three` · `People I can tell when I'm struggling`.

---

## DISTRIBUTION & VERSIONING

- Distribute as a **Notion duplicate link** behind a Whop-gated page. One link, one click.
- **Versioning:** `v1.0` → monthly `v1.1`, `v1.2`. Changelog entry for every ship, always naming the requesting member.
- **Updates reach existing members two ways:** (a) new modules shipped as standalone duplicate-able pages they drag in — this is the primary mechanism, because it never touches their data; (b) a twice-yearly "fresh Desk" full version with a documented migration path for members who'd rather start clean (many will — a fresh Desk is itself a dopamine hit).
- **Never ship a breaking change to a core database property.** Members have their data in it. Add properties; don't rename or delete them.

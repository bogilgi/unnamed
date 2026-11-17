# 04 — Build Prompts: The Desk, Step by Step

**How to use this file.** Each prompt is a self-contained build session. Run them **in order** — Prompt 2 depends on Prompt 1 existing. Paste one, build what it returns, tick it off, move on. Budget 45–90 minutes per prompt; five sessions gets you to v1.0.

**Before you start, paste this once at the top of your build chat:**

```
CONTEXT — read once, apply to every build prompt that follows.

I'm building "The Desk": an ADHD operating system in Notion, sold as a $47/mo
membership. The full information architecture spec is attached/pasted above —
treat it as the source of truth and don't redesign it.

Non-negotiable design rules:
- Three core databases do most of the work. Do not invent new databases beyond
  the spec. Use linked views instead.
- No required fields. Every property has a sane default.
- Energy is the primary sort axis; date is secondary.
- Mobile portrait must work: max 3 visible properties per card, prefer board
  and gallery over table.
- Formulas over automations (automations break on duplicated templates).
- Shame-free microcopy. Never use the words: discipline, lazy, just.

Your output format for every build prompt:
1. Exact click-path instructions, numbered, Notion's real current UI labels.
2. Every property with its exact type and exact option names/emoji.
3. Every formula as a single copy-pasteable code block, Notion 2.0 syntax.
4. Every view with: name, type, group-by, exact filter conditions, sort,
   and which properties are visible.
5. All on-page microcopy written out verbatim, ready to paste.
6. A "check it worked" list at the end.

Ask me nothing. Where the spec is silent, choose the lower-friction option and
tell me in one line what you chose.
```

---

## PROMPT 1 — Core databases (Tasks, Projects, Notes & Captures)

```
Build Session 1 of 5: the three core databases.

Create DB: Tasks, DB: Projects, and DB: Notes & Captures exactly as specified in
the architecture, including every property, every select option with its emoji,
and the four Tasks formulas (Age, Status Flag, Next Action?, plus the Projects
Progress formula).

Then build all 8 Tasks views and all 4 Projects views and all 3 Notes views, with
exact filters and sorts.

Give me the formulas as separate copy-paste blocks, each labelled with the
property name it goes in. If a formula could error on an empty value, make it
empty-safe.

Also give me 25 seed tasks and 5 seed projects I can paste in as demo data for
sales screenshots — they should look like a real ADHD adult's life (admin dread,
an unanswered email, a tax thing, one hyperfocus side project), not like a
productivity influencer's.
```

**Done when:** Tasks board groups by Energy, the 2-Minute Pile auto-populates, a project with no incomplete task shows an empty Next Action, and all three DBs are inside the collapsed ⚙️ System toggle.

---

## PROMPT 2 — The Desk home page + Bad Day Mode + Re-Entry

```
Build Session 2 of 5: the three pages a member actually touches.

Using the databases from Session 1, build:

A) THE DESK home page, following the wireframe in the spec top to bottom. The
   three buttons first, The One Thing (linked view, nothing else visible), the
   energy check, the three collapsed energy toggles, next session, Done This
   Week, New This Month.
   Hard rule: on a phone, only the three buttons + The One Thing + energy check
   are above the fold.

B) ⚡ BAD DAY MODE exactly as specced, including the four permission checkboxes
   written out word for word, and no link back to the full task list.

C) 🔄 RE-ENTRY, four steps, with the frozen-task view and the "members average
   2-4 absences a year" line.

For each page give me: the block structure in order, every callout's exact text,
every linked-view's exact filter, and the configuration for each button
(Notion button blocks: what they create, which properties they set).

The energy check must be 3 button blocks that each create an Energy Log row with
the energy pre-set and today's date — one tap, no form, no page opening.
```

**Done when:** you can open the Desk on a phone and see exactly one decision; the energy buttons log in one tap with no modal; Bad Day Mode shows a maximum of three tasks.

---

## PROMPT 3 — Routines, Habits, Energy Log, Time Tools

```
Build Session 3 of 5: the behavioural modules.

Build: DB Routines + DB Routine Steps, DB Habits + DB Habit Log, DB Energy Log,
and the page-level tools for each, per spec.

Specifically:
1. All 12 pre-built routines, fully written, each with its steps (with minutes
   and skip-safe flags) AND its Minimum Version written in the member's voice.
2. The Habits Hit Rate and Verdict formulas, empty-safe. The Verdict wording
   must stay exactly as specced — "Good enough — this counts" is deliberate.
3. The one-tap habit logging gallery (button blocks, no modal).
4. TIME TOOLS page: the Time Multiplier formula block comparing summed Actual to
   summed Est. across tasks where both exist, showing "need 5 more data points"
   below n=5; the Estimator template button (gut guess x multiplier + 15 min);
   and the day-as-timeline view.

Write out the Time Multiplier result sentence verbatim, including the version
shown when there isn't enough data.
```

**Done when:** every routine has a 3-step minimum version; logging a habit is one tap; the multiplier renders something sensible with zero data.

---

## PROMPT 4 — Weekly Review, Vault, Open Desk, Changelog, Settings

```
Build Session 4 of 5: review, reference and the subscription-proof layer.

Build:
A) WEEKLY REVIEW page: DB Reviews + the template button that creates a week's
   entry pre-filled with the 7 timed steps as a checklist. Each step shows its
   minute budget. End with the "if you only did step 2, that was a successful
   review" callout. Target total: 18 minutes.

B) RESOURCE VAULT: DB Resources + all 4 views. Then WRITE ALL 25 v1 resources in
   full — the 9 scripts, 8 checklists, 5 protocols, 3 worksheets listed in the
   spec. Scripts must be copy-paste-ready messages, not advice about writing
   messages. Every resource needs its "Use when" line written in the member's
   own voice ("I've been avoiding an email for 9 days"), because that's the
   field they search.

C) OPEN DESK: DB Sessions + 3 views + the RSVP mechanic.

D) CHANGELOG: DB Changelog + the 3-newest view pinned on the Desk home page.

E) SETTINGS page with the 7 member constants.

If 25 full resources is too long for one response, do them in batches of 8 and
keep going until all 25 are written. Do not summarise any of them.
```

**Done when:** all 25 resources exist as real, usable content; the Changelog's three newest entries appear on the home page.

---

## PROMPT 5 — Polish, mobile pass, and the member-facing walkthrough

```
Build Session 5 of 5: ship it.

1. MOBILE AUDIT. Walk every page as if on an iPhone in portrait. List every
   place where more than one decision is visible on open, any table that should
   be a board, any view showing more than 3 properties, and any tap that opens a
   modal when it shouldn't. Give me the fix for each, not just the finding.

2. FRICTION AUDIT. For each of these jobs, count the taps from opening Notion:
   capture a thought, mark the One Thing done, log energy, find a low-energy
   task, start the weekly review, enter Bad Day Mode. Anything over 3 taps gets
   a fix.

3. EMPTY STATES. Write the text shown in every view when it's empty. These are
   read by a brand-new member in minute one, so they carry most of the
   onboarding weight. No exclamation marks, no "let's get started!"

4. FIRST-RUN PAGE: "Start here (4 minutes)". Four steps maximum. It must get the
   member to one captured thought and one chosen One Thing, and nothing else.
   Explicitly tell them NOT to set up the rest today.

5. A 90-second screen-recording script for the walkthrough video: what to show,
   in what order, with the voiceover written out.

6. The duplicate-link distribution checklist: what to clear out (demo data,
   personal rows), what to leave as examples, sharing settings, and how to
   confirm the duplicate works from a logged-out browser.
```

**Done when:** a logged-out browser can duplicate the template, the first-run page gets a stranger to one captured thought in under four minutes, and no job takes more than three taps.

---

## MONTHLY MODULE PROMPT (reuse every month, forever)

```
Monthly build: The Desk v1.[N] — [MODULE NAME]

Member requests this month, verbatim:
1. [paste]
2. [paste]
3. [paste]

Build the highest-leverage ONE of these as a standalone Notion page that an
existing member can duplicate and drag into their own Desk WITHOUT touching
their existing databases. It may create linked views of the core DBs and may ADD
properties, but it must not rename or delete any existing property.

Deliver:
- The full module page: structure, every property, every formula, all microcopy.
- Exactly which properties (if any) members must add to core DBs, with a
  30-second instruction for doing so.
- A Changelog entry: what changed, where to find it, who requested it (use their
  first name).
- A 60-second Loom script announcing it.
- A Discord announcement post, under 80 words, no hype.
- Three short-form video hooks about the new module.

Then: list the two requests you did NOT build and the one-line reason each,
written so I can paste it into the community without anyone feeling dismissed.
```

---

## Build order sanity check

| Session | Output | Hours |
|---|---|---|
| 1 | 3 core DBs + 15 views + demo data | 2–3 |
| 2 | Desk home, Bad Day, Re-Entry | 2 |
| 3 | Routines, Habits, Energy, Time Tools | 3 |
| 4 | Review, Vault (25 resources), Sessions, Changelog | 4–5 |
| 5 | Mobile/friction audit, empty states, first-run, video script | 2 |

**Total: ~13–15 hours to v1.0.** Do not build Tier 3, affiliate assets, or the second content channel until 20 paying members exist.

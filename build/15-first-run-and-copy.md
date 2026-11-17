# 15 — First-Run Page, Empty States, Demo Data & Walkthrough Script

This finishes the written half of build prompt 5. Everything here is paste-ready.

---

## 1. The first-run page: "Start here (4 minutes)"

> This page is the highest-stakes surface in the product. A new member decides in about ninety seconds whether this is another thing they'll abandon. The job is **not** to show them the system — it's to get them to one captured thought and one chosen task, and then to stop them doing anything else.

**Page content, verbatim:**

```
🧠 Start here — 4 minutes

Before anything else: do not set this up today.

Setting up systems is the fun part. It's also where this normally goes wrong —
four hours of configuring, a beautiful workspace, and then you never open it
again. You know the pattern. We're not doing it this time.

Four minutes. Two things. Then close the tab and come back tomorrow.

───────────────────────────────────────

① Dump one thought                                      ~40 seconds

Anything that's in your head right now. A task, a worry, "that smell in the
car." It doesn't have to be important and it doesn't have to be tidy.

[ → Open the Brain Dump ]

Done? Good. That's the capture habit — the only one that really matters.

───────────────────────────────────────

② Pick one thing for today                              ~60 seconds

Not three. One. Preferably something small enough to be boring.

[ → Pick my One Thing ]

───────────────────────────────────────

③ Tap your energy                                       ~2 seconds

🪫  🔋  ⚡  — whichever is true right now. One tap, nothing opens.

Do this daily and in three weeks you'll have the most useful thing in here:
your real energy curve. Most people find their good hours are earlier and
shorter than they'd been planning around for twenty years.

───────────────────────────────────────

That's it. You're set up.

Seriously — stop here. The rest of the Desk gets introduced one piece at a
week, by email and in the community. Nothing below needs you today.

Three things you'll want to know exist, for later:
· ⚡ Bad Day Mode — strips everything down to three survivable actions
· 🔄 Re-Entry — for when you've been away. Takes under five minutes
· 📚 The Vault — 25 scripts, checklists and protocols. Search by "Use when"

Next Open Desk session: [day, time] — bring the thing you've been avoiding.
```

**Design notes:** the two buttons are the only interactive elements above the fold. No navigation, no table of contents, no "explore the system" link. The deliberate dead end *is* the design.

---

## 2. Empty states (write these into every view)

> New members meet most of these in minute one, which means these lines carry more onboarding weight than any email does. Rules: no exclamation marks, no "let's get started", no cheerfulness, nothing that implies they're behind.

| View | Empty state |
|---|---|
| **Brain Dump — Inbox** | Nothing captured yet. Dump it here badly rather than remembering it perfectly. |
| **Tasks — By Energy** | No tasks yet. Add one from the Brain Dump, or type one straight in. |
| **Tasks — Today** | Nothing picked for today. That's allowed. If you want one: pick something small enough to be boring. |
| **The One Thing** (home) | Pick one ↓ — not the biggest. The loudest. |
| **2-Minute Pile** | Nothing under two minutes right now. |
| **Dread Pile** | Nothing in here. Either you're clear, or the dread tasks aren't tagged yet — that's fine too. |
| **Frozen** | Nothing frozen. Tasks land here after 30 untouched days, and then you delete them. |
| **Done This Week** | Nothing ticked off yet this week. It's an early week, or a hard one. |
| **Real Deadlines** | No real deadlines. Worth sitting with that for a second — it's usually less than it feels. |
| **Projects — Active** | No active projects. Three is the cap, and zero is a perfectly good number. |
| **Project with no next action** | No next action. What's the first physical thing — open what? click what? |
| **Routines — My Routines** | Three routines are switched on by default. Add more when those are boring. |
| **Habits — This Week** | Nothing logged this week. Nothing resets, so there's nothing to restart. |
| **Energy Log — Pattern** | Tap an energy at the top of your Desk. Three weeks of taps and the pattern shows up. |
| **Time Multiplier** (n<5) | Need 5 more logged tasks before this number means anything. Guess before, log after. |
| **Reviews — Recent** | No reviews yet. The first one takes 18 minutes and most of it is deleting things. |
| **Resource Vault** | 25 resources. Search the "Use when" column in your own words — try "avoiding an email". |
| **Vault — New this month** | Nothing new yet this month. Next drop: last working day. |
| **Open Desk — Upcoming** | No sessions on the calendar yet. |
| **Open Desk — I'm attending** | Not signed up for anything. Turning up without RSVPing is also fine. |
| **Changelog** | Nothing shipped yet — you're here early. |
| **Bad Day Mode, no low tasks** | Nothing low-energy in your list. Then today's three things are: water, food, one message to one person. |

---

## 3. Demo seed data (for screenshots and the sales page)

> Make the demo workspace look like a real ADHD adult's actual life. The instinct to fill it with "Q3 Strategy Review" and "Morning Pages" is wrong — recognition is what sells this, and nobody recognises a productivity influencer's task list.

**Tasks (25)**

| Task | Energy | Dopamine | Size | Project |
|---|---|---|---|---|
| Reply to Dani's message (one line) | 🪫 | 🎯 Quick win | 2 min | |
| Book the dentist — 6 months overdue | 🪫 | 👥 Needs a human | 5 min | |
| Load the dishwasher | 🪫 | 🤖 Autopilot | 15 min | |
| Rename and file the scan | 🪫 | 🤖 Autopilot | 2 min | |
| Cancel the gym thing I haven't used since March | 🪫 | 🧱 Dread | 5 min | |
| Water the one surviving plant | 🪫 | 🎯 Quick win | 2 min | |
| Find the charger (it's somewhere) | 🪫 | 🤖 Autopilot | 15 min | |
| Invoice March — actually send it | 🔋 | 🧱 Dread | 15 min | Freelance admin |
| Reply to Mum (9 days) | 🔋 | 🧱 Dread | 5 min | |
| Food shop order | 🔋 | 🤖 Autopilot | 15 min | |
| Tax folder — name what's missing | 🔋 | 🧱 Dread | 15 min | Tax return |
| Write the handover notes | 🔋 | 🌊 Flow-friendly | 1 hr | Leaving job |
| Chase the deposit from the old flat | 🔋 | 👥 Needs a human | 15 min | |
| Sort the photos off my phone (23,000) | 🔋 | 🤖 Autopilot | Chunky | |
| Return the parcel before the window closes | 🔋 | 🧱 Dread | 15 min | |
| Set up the standing order | 🔋 | 🤖 Autopilot | 15 min | |
| Draft the proposal | ⚡ | 🌊 Flow-friendly | Chunky | Freelance admin |
| Decide about the flat | ⚡ | 🧱 Dread | Chunky | The flat |
| Rework the pricing | ⚡ | 🌊 Flow-friendly | 1 hr | Freelance admin |
| Finish the thing I started at 2am on Sunday | ⚡ | 🌊 Flow-friendly | Chunky | Synth project |
| Call the GP about the referral | ⚡ | 👥 Needs a human | 15 min | Assessment |
| Read the tenancy agreement properly | ⚡ | 🧱 Dread | 1 hr | The flat |
| Apply for the one job I actually want | ⚡ | 🧱 Dread | 1 hr | Leaving job |
| Learn the new build system | ⚡ | 🌊 Flow-friendly | Chunky | |
| Plan Sam's birthday (it's in 4 days) | 🔋 | 👥 Needs a human | 30 min | |

Add realistic ageing: give 4 tasks a `Created` date 30+ days back so the **Frozen** view has content, and 6 a `Completed` date in the last week so **Done This Week** isn't empty in screenshots. An empty "Done This Week" in a sales screenshot is a quiet disaster.

**Projects (5)**
1. **Tax return** — 😶‍🌫️ Parked · *What does done look like?* "Submitted, and I know the number." · last touched 6 weeks ago
2. **Freelance admin** — 🔨 Active · "Invoices out, no one chasing me."
3. **The flat** — 🔨 Active · "Decision made and communicated. Either answer is fine."
4. **Synth project** — 🔨 Active · "One finished track, however bad." *(the hyperfocus side project everyone has)*
5. **Leaving job** — 💭 Idea · "Applied to three places I'd actually like."

> The parked tax return with "last touched 6 weeks ago" is the single most relatable row in the whole demo. Keep it.

---

## 4. The 90-second walkthrough video script

**Format:** screen recording, phone portrait, no face, captions burned in. One take. Visible imperfection is on-brand.

| Time | On screen | Voiceover |
|---|---|---|
| 0:00 | Desk home, phone portrait | "This is the whole thing. One screen, one decision." |
| 0:06 | Point at The One Thing | "The One Thing. Not today's twelve tasks — the one. Everything else is below the fold on purpose." |
| 0:14 | Tap 🔋 energy | "Every day you tap how your brain is. One tap, nothing opens. Three weeks of this and you get your real energy curve, which is usually a surprise." |
| 0:24 | Expand the Low toggle | "Tasks are sorted by what they'll cost you, not when they're due. Bad day — tap low energy, get four things you can genuinely do." |
| 0:34 | Tap ⚡ Bad Day Mode. Let it sit silently for 2 seconds | "And this is the button I use most." |
| 0:40 | Hold on the stripped-back screen | "Three tasks, all under two minutes. No counts, no overdue red, no projects. And four sentences I need to read on those days." |
| 0:50 | Scroll the permissions slowly | *(read one aloud)* "Tomorrow is a different day and I don't have to make up for this one." |
| 0:58 | Back to the Desk, open Brain Dump | "Capture is one tap and voice-to-text. No fields. If capture takes longer than three seconds, the thought's already gone." |
| 1:06 | Open the Vault, search "avoiding" | "Twenty-five scripts and checklists, searchable by the way you'd actually describe the problem. 'I've been avoiding an email for nine days.'" |
| 1:14 | Open that script | "It's written out. You change two words and send it." |
| 1:20 | Scroll to the Changelog | "And this is the part that makes it a subscription: one or two new modules every month, from member requests, with their name on it." |
| 1:28 | Desk home | "That's it. Link's below." |

**Two rules for the recording:** use the demo data above, never your real tasks (both for privacy and because real data is less relatable than curated real-feeling data). And don't re-record for stumbles — a flawless walkthrough of an ADHD product is faintly suspicious.

---

## 5. The six-tap audit (run this before launch)

Count taps from opening Notion cold. Anything over 3 is a bug.

| Job | Target | Path |
|---|---|---|
| Capture a thought | 2 | Desk → Dump button (voice-to-text from there) |
| Mark The One Thing done | 2 | Desk → checkbox |
| Log energy | 2 | Desk → energy button |
| Find a low-energy task | 2 | Desk → expand Low toggle |
| Enter Bad Day Mode | 1 | Desk → ⚡ |
| Start the weekly review | 2 | Desk → Review → template button |

If any of these needs a modal, a filter change, or scrolling past other content, fix the layout rather than documenting the workaround. **Friction is the thing that kills this product**, and it creeps back in with every module you add — so re-run this audit quarterly, not just at launch.

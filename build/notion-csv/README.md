# Notion import CSVs

175 rows you don't have to type. Notion imports a CSV as a new database, using the first row as property names.

## How to import

1. In Notion: `+` → **Import** → **CSV** → pick the file.
2. It creates a database where **every property is Text**. Change the types afterwards (next section) — this is still far faster than creating rows by hand.
3. Rename the database if needed, then drag it inside your `⚙️ System` toggle.

**Import in this order**, because relations need their targets to exist first:

| Order | File | Goes to | Rows |
|---|---|---|---|
| 1 | `02-projects-seed.csv` | DB: Projects | 5 |
| 2 | `01-tasks-seed.csv` | DB: Tasks | 31 |
| 3 | `03-resources-vault.csv` | DB: Resources | 25 |
| 4 | `04-routines.csv` | DB: Routines | 12 |
| 5 | `05-routine-steps.csv` | DB: Routine Steps | 75 |
| 6 | `06-habits-starter.csv` | DB: Habits | 7 |
| 7 | `07-sessions-4weeks.csv` | DB: Sessions | 17 |
| 8 | `08-changelog-seed.csv` | DB: Changelog | 3 |

## Property types to set after import

**Tasks** — `Energy` `Dopamine` `Size` → Select · `Context` → Multi-select · `Project` → Relation to Projects · `Today` `Done` → Checkbox · `Completed` → Date. Then add the properties no CSV can carry: `Do Date`, `Hard Deadline`, `The One Thing`, `Est. (min)`, `Actual (min)`, `Notes`, and the four formulas from doc 03.

**Projects** — `State` `Energy Cost` → Select · `Hard Deadline` → Date. Add `Tasks` (relation), `Next Action` / `Open` (rollups), `Progress` (formula), `Last Touched` (rollup).

**Resources** — `Type` `Energy` → Select · `Topic` → Multi-select · `Minutes` → Number · `New this month?` → Checkbox. `Use when` stays Text; it's the field members search.

**Routines** — `When` `Energy Needed` → Select · `Active` → Checkbox · `Minutes` → Number (or replace with a rollup summing step minutes). Add `Steps` (relation to Routine Steps).

**Routine Steps** — `Routine` → Relation to Routines · `Order` `Minutes` → Number · `Optional?` `Skip-safe?` → Checkbox.

**Habits** — `Target per week` → Number · `Energy` → Select · `Active` → Checkbox. Add `Log` (relation), `This Week` (rollup), and the `Hit Rate` / `Verdict` formulas from doc 03.

**Sessions** — `Starts` → Date (include time) · `Type` → Select · `Link` → URL · `I'm coming` → Checkbox (add it).

**Changelog** — `Shipped` → Date · `Type` → Select.

## Before you ship

- **Tasks and Projects are demo data** for screenshots and the sales page. Delete both before sharing the member duplicate link, or members inherit someone else's dentist appointment. Keep one or two as examples if you'd rather the workspace not open empty.
- **Resource rows are titles only.** The bodies are in docs 10–13; open each row and paste its content in. That's the 2–3 hours that can't be automated, and it's the part members judge the product on.
- **Sessions use placeholder dates starting Mon 23 Nov 2026** and `[you]` as host. Change the week, the times and the host.
- **Changelog dates** all read 2026-11-23. Set them to your real launch date.
- Backdate a few `Completed` dates on Tasks so "Done This Week" isn't empty in screenshots. An empty Done view in a sales screenshot undercuts the whole pitch.

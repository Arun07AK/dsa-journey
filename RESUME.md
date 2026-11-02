# RESUME — read this first

A cloud session is a fresh clone on a remote VM. It remembers nothing about last time.
This file is the memory. **Read it at the start of a session, rewrite it at the end.**

Keep it short. If it grows past one screen it's become a log, and the log is `solved.md`.

---

## Where I'm at

**Updated:** 2026-11-02

**Target: NeetCode 150 core + 22 extras = 172.** The other 78 extras are skipped by plan.
**76 solved in the 250 view** (Easy 20/60 · Medium 49/155 · Hard 7/35); the core-vs-extra
split of those 76 is not yet known. Streak **0** · best **54 days**.

- **Position: end of the Graphs section — 16 of 21.** Five problems close it out.
- Topics 1-10 are **core-only** (56 extras skipped). Their core counts aren't filled in yet.
- The four **go deep** topics are Graphs, Advanced Graphs, 1-D DP, 2-D DP — where you are and
  what's next. Every extra in the plan sits in that stretch.
- Rows 12-18 are confirmed 0 in the 250 view, so 0 core and 0 extras there.
- **Language:** C++.
- **Already has a visualizer:** sliding window (all 5 shapes), binary search on rotated
  arrays (LC 33, LC 153), BFS/DFS, multi-source BFS (LC 994), backtracking trees.
- **Counts live in [`PROGRESS.md`](PROGRESS.md)** — the single source of truth. This file
  carries only the one-line state; don't duplicate the tables here.
- **`index.html`** is the dashboard: editable per-topic counts, reconciliation, and Bit the
  buddy. It exports the PROGRESS.md table, so the markdown stays canonical.

## Next action

**Fill in the 150-view core counts** — one pass over the dashboard, typed into `index.html`.
Then close out Graphs core (13) before moving to Advanced Graphs.
Don't open 1-D DP until the Graphs row reads 21/21.

## Open threads

- **The core/extra split of the 76 is the one open number.** Switch the dashboard to the
  🚀 NeetCode 150 view, read the per-topic core counts, type them into `index.html`, export.
  Until then the tracker shows a floor (`≥`), which is correct but understates you.
- `solved.md` still has the placeholder entry dated 2026-06-07 at the bottom of the log.
  Delete it when the first real entry goes in.
- Striver's TUF (~75 problems of history) is no longer the tracked sheet. Left as history.
- Python as a second language: deferred until the Graphs section closes.
- Before starting topic 13 (1-D DP), read ch. 7 of the Competitive Programmer's Handbook —
  see [`RESOURCES.md`](RESOURCES.md). DP is 33 of the 174 problems left.

---

## How to rewrite this at the end of a session

Replace the three sections above. Four things, nothing more:

1. **Updated** — today's date.
2. **Where I'm at** — the counts, the streak, which topic I'm on, which rows moved.
   Take the numbers from me or the roadmap dashboard; never estimate them.
3. **Next action** — one concrete sentence a cold session could act on without asking me
   anything. Not "continue practising". *"Graphs, 2 left — do LC 207, then LC 210."*
4. **Open threads** — only things genuinely unfinished. Delete resolved ones; don't archive
   them here. An empty list is a good outcome, not a gap to fill.

Record a broken streak as a plain `0` with no commentary attached to it.

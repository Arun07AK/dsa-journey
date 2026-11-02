# PROGRESS — NeetCode

**The single source of truth for counts.** `solved.md` holds the log, this holds the numbers.

**Interactive tracker:** [`index.html`](index.html) — set per-topic counts, see the
reconciliation check, export this table. Hosted: <https://claude.ai/artifact/1vgcwduHzpeHdZVi7npXet>

**Last synced with the dashboard:** 2026-11-02

---

## The plan: 150 core, 22 extras, 78 skipped

The finish line is the **NeetCode 150**, not the 250. The 250 is the 150 plus 100 extras,
and the extras are a remedy, not a syllabus — from `finish-150.html`:

> Finish a core topic and it still feels shaky? That's your signal — then (and only then)
> do its extras. **Don't pre-grind them.**

Four topics are flagged *go deep* and get their extras by default. Every other topic is
core-only. That's **22 extras in, 78 out**.

| | Problems |
|---|---|
| 150 core — every topic | 150 |
| Extras — Graphs, Advanced Graphs, 1-D DP, 2-D DP | +22 |
| **Real target** | **172** |
| Deliberately skipped | 78 |

All four deep topics are Graphs, Advanced Graphs, 1-D DP and 2-D DP — exactly where you are
and what comes next. Every extra you're meant to do is in the road ahead; everything behind
you is finished at core.

---

## Where it stands

| | Solved | Total |
|---|---|---|
| **Core (the finish line)** | **not yet split** | **150** |
| Extras (planned) | 0 | 22 |
| 250 view — what the dashboard shows today | 76 | 250 |
| &nbsp;&nbsp;Easy | 20 | 60 |
| &nbsp;&nbsp;Medium | 49 | 155 |
| &nbsp;&nbsp;Hard | 7 | 35 |

**Current streak:** 0 days · **Best streak:** 54 days

**The one open number.** Of your 76 solved, how many are core and how many are extras is not
yet known, and it is not something to estimate. Switching the dashboard's dropdown from
🦄 NeetCode 250 to 🚀 NeetCode 150 shows the core figure directly, per topic. Until then the
tracker shows a floor (`≥`), not a total.

---

## By topic

Denominators verified against neetcode.io: core sums to exactly 150, extras to exactly 100.
Feel: 🟢 could teach it · 🟡 shaky · ⬜ untouched

| # | Topic | Core | /150 | Extra | /100 | Plan | Feel |
|---|---|---|---|---|---|---|---|
| 1 | Arrays & Hashing | | 9 | | 13 | skip | |
| 2 | Two Pointers | | 5 | | 8 | skip | |
| 3 | Sliding Window | | 6 | | 3 | skip | |
| 4 | Binary Search | | 7 | | 7 | skip | |
| 5 | Linked List | | 11 | | 3 | skip | |
| 6 | Stack | | 6 | | 8 | skip | |
| 7 | Trees | | 15 | | 8 | skip | |
| 8 | Tries | | 3 | | 1 | skip | |
| 9 | Backtracking | | 10 | | 7 | skip | |
| 10 | Heap / Priority Queue | | 7 | | 5 | skip | |
| 11 | **Graphs** | | 13 | | 8 | **go deep** | 🟡 ← current |
| 12 | Advanced Graphs | 0 | 6 | 0 | 4 | **go deep** | ⬜ |
| 13 | 1-D Dynamic Programming | 0 | 12 | 0 | 5 | **go deep** | ⬜ |
| 14 | 2-D Dynamic Programming | 0 | 11 | 0 | 5 | **go deep** | ⬜ |
| 15 | Greedy | 0 | 8 | 0 | 6 | skip | ⬜ |
| 16 | Intervals | 0 | 6 | 0 | 1 | skip | ⬜ |
| 17 | Bit Manipulation | 0 | 7 | 0 | 3 | skip | ⬜ |
| 18 | Math & Geometry | 0 | 8 | 0 | 5 | skip | ⬜ |
| | **Total** | | **150** | | **100** | | |

Graphs shows 16 of 21 in the 250 view, which puts core between 8 and 13 — not precise enough
to write down. Rows 12–18 are confirmed 0 in the 250 view, so core and extras there are both 0.

Why each of the four goes deep, and why the rest don't — the notes are in `finish-150.html`:
Graphs is *highest interview ROI*, Advanced Graphs are *the hard filters*, DP is *the wall*
and *pure volume of reps*. Greedy is *insight-based, 150 core is enough*; Bit Manipulation and
Math are the *low-priority tail*.

---

## What the numbers say

**1. The target is 172, not 250.** Seventy-eight problems came off the plan the moment the
150 became the finish line. That is the single biggest change to how far away this is.

**2. 49 mediums is the number that matters.** Medium is where interviews live, and 49 is well
past the point where the pattern vocabulary exists. What's left is coverage, not capability.

**3. Pace, once the split is known.** The 150 view will give the exact figure. If most of your
76 are core — likely, since the extras are the +100 layered on top — then roughly 74 core
remain, which at one a day is about two and a half months. The internship target in
`STRATEGY.md` is mid-2027. This is not close.

---

## How to update

1. On the NeetCode dashboard switch to the **150** view; read the per-topic core counts.
2. Open `index.html`, type them in. Extras auto-derive wherever the 250 count is known.
3. Hit **Export PROGRESS.md table** and paste over the table above.
4. Update **Last synced**, log the problem in `solved.md`, update the state in `RESUME.md`.

Record a broken streak as a plain `0`. It's information, not a verdict.

# Sliding Window — folder index

NeetCode 75, Pattern #3. This folder holds the source material (the **"5 Variations of Sliding Window"** cheatsheet PDF + lecture PDFs) and points to the interactive tool built from it.

## The interactive tool

**[`../../visualizations/sliding-window.html`](../../visualizations/sliding-window.html)** — a single self-contained, double-clickable HTML page covering all 5 variations. A tab switcher at the top picks a variation; each has its own intuition, a step-by-step animated window simulator (Step / Back / Reset + keyboard `→`/`Space`/`←`/`R`), bespoke visual, the code, and a reveal-only recall quiz.

Built to mirror the sibling visualizations in the same folder (`find-min-rotated-sorted-array.html`, `search-rotated-sorted-array.html`).

## The 5 variations (each with a verified worked example)

| # | Variation | Recognise it when… | Worked example → answer |
|---|-----------|--------------------|--------------------------|
| 1 | **Fixed window** | "…over any **k** consecutive…" | `[6,10,8,5,16,7,9,6]`, k=4 → **39** (`[10,8,5,16]`) |
| 2 | **Sum constraint** (longest) | "longest … sum ≤ k" | `[3,1,2,7,4,2,1,1,5]`, k=8 → **len 4** (`[4,2,1,1]`) |
| 3 | **Count constraint** (longest) | "longest … at most N of x" | `"lltllttlll"`, ≤1 `'l'` → **len 3** (`"ltt"`) |
| 4 | **Not-repeated** (longest, LC#3) | "longest … no duplicates" | `"zxyzxyz"` → **len 3** (`"zxy"`; ties exist) |
| 5 | **Count subarrays** | "how many subarrays … product < k" | `[10,5,2,6]`, k=100 → **8** |

**The shared spine:** R almost always marches forward; L only moves to *restore* the constraint. The window slides, never restarts — that's why it's O(n). Variations 2–4 track a best *length*; variation 5 *accumulates* (a legal window of width w adds exactly w new subarrays, `res += r-l+1`).

All five example numbers were verified by simulating each algorithm in Node against a reference implementation (0 mismatches).

## Conventions (for future edits)

- **Palette-1 dark theme** (shared CSS variables: `--bg`, `--surface`, `--teal`, `--yellow`, etc.) — same as the rotated-array visualizations.
- **`buildSteps()` simulates the real algorithm** and emits a `steps[]` array; one shared `render()` reads `steps[step]` and updates the DOM. The visualization is faithful by construction — change the algorithm only by changing `buildSteps`, and re-run the Node check.
- **Registry-of-modules pattern:** each variation is one entry in the `VARIATIONS` array with its own `buildSteps` / `renderExtra` / `renderReadout` / `cellClass` / `cellPtr` / `stage` hooks. Add or remove a variation = one array entry.
- Self-contained: one HTML file, no build, no framework, system fonts.

## NO-TRACKERS (AEKAY Principle #0)

The quizzes are **reveal-only** — no scoring, no grading buttons, no streaks, no completion gauges. The only counter on the page is the algorithmic **step counter** ("Step k / N"), which is part of the visualization, not a habit metric. Do **not** add a progress/streak table to this folder or the tool.

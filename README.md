# DSA Journey

My data structures and algorithms practice, kept in the open. Pattern-based, not random
problem grinding: master one pattern at a time, write down the *trigger* that makes it
recognisable, and build a tool for the ones that don't click from reading alone.

Primary language: **C++**.

## The files that matter

The finish line is the **NeetCode 150**, plus 22 extras from the 250 in the four topics worth
going deep on — Graphs, Advanced Graphs, 1-D DP, 2-D DP. The other 78 extras are skipped on
purpose. Currently **76 solved in the 250 view**, at the end of Graphs with 16 of 21 done.

| File | What it is |
|---|---|
| [`index.html`](index.html) | The front door. Core progress against the 150, extras against the 22, the 18-topic ladder with editable counts, a reconciliation check, and Bit. Open it by double-clicking. |
| [`PROGRESS.md`](PROGRESS.md) | The tracker. Core and extra counts per topic, the streak, and what the numbers actually mean. Single source of truth — no other file duplicates these. |
| [`RESOURCES.md`](RESOURCES.md) | Researched, link-checked resources mapped to the topics still ahead, not a generic list. |
| [`STRATEGY.md`](STRATEGY.md) | The approach, the 150/250 split, and the daily rule I actually keep (one problem a day — an easy one still counts). |
| [`solved.md`](solved.md) | The growing pattern library. One entry per problem: the reusable idea, the key insight, and *what I'd recognise if I saw it cold again*. That last line is the whole point — it turns solving into recognising, which is what interviews test. |

## Interactive visualizers

Single-file, self-contained HTML — no build step, no framework. Open any of them by
double-clicking, or clone and run `open <file>`. Each one simulates the real algorithm
and renders from the emitted step list, so the animation can't drift from the code.
Stepping is learner-driven (`→` / `Space` forward, `←` back, `R` reset) — nothing autoplays.

| Visualizer | Covers |
|---|---|
| [5 Variations of Sliding Window](visualizations/sliding-window.html) | All five sliding-window shapes — fixed window, sum constraint, count constraint, no-duplicates (LC 3), and counting subarrays — with a worked example verified against a reference implementation. |
| [Search in Rotated Sorted Array](visualizations/search-rotated-sorted-array.html) | Binary search when the array has been rotated (LC 33). |
| [Find Minimum in Rotated Sorted Array](visualizations/find-min-rotated-sorted-array.html) | Finding the pivot (LC 153). |
| [Graph Traversal Visualizer](visualizations/Graph/graph-visualizer.html) | BFS and DFS side by side on the same graph. |
| [Rotting Oranges](visualizations/Graph/rotting-oranges.html) | Multi-source BFS on a grid (LC 994), step by step. |
| [The Rumor Room](visualizations/Graph/rumor-room.html) | The same LC 994 algorithm retold as a story, to make the multi-source idea stick. |
| [Backtracking Visualizer](visualizations/backtracking/backtracking-visualizer.html) | The recursion tree being built and pruned. |

Two planning pages sit at the root: [The Method](learning-method.html) (how I learn this
stuff) and [Finish the 150](finish-150.html) (the graphs/DP back half).

## Layout

```
index.html               the dashboard — progress at a glance, counts you can edit
PROGRESS.md              the tracker — counts, streak, what they mean (source of truth)
RESOURCES.md             researched resources, mapped to the topics still ahead
CLAUDE.md                the teaching contract — how Claude is meant to coach, not solve
RESUME.md                session handoff; read first in a fresh cloud session
STRATEGY.md              the approach and the daily rules
solved.md                the pattern library (grows one entry at a time)
learning-method.html     how DSA is actually learned
finish-150.html          the remaining graphs / DP problem set
visualizations/          single-file interactive tools, grouped by pattern
NEETCODE 75/             per-pattern study folders and notes
```

Course PDFs I study from are intentionally not committed — they're third-party material.

# Rotting Oranges (LC 994) — Animated Walkthrough — Design Spec

Date: 2026-08-12 · Approved by Arun · Builder: Opus subagent · Reviewer: Fable

## Goal
Standalone, self-contained `rotting-oranges.html` in `~/AEKAY/05-CAREER/DSA/visualizations/Graph/` that animates **Arun's exact submitted Python solution** (multi-source BFS, level counting). No dependencies, dark theme matching `graph-visualizer.html` in the same folder.

## Arun's code (render verbatim in the code panel, highlight lines as they execute)

```python
from collections import deque
class Solution:
    def orangesRotting(self, grid: List[List[int]]) -> int:
        rows=len(grid)
        cols=len(grid[0])
        q=deque()
        fresh=0
        for r in range(rows):
            for c in range(cols):
                if grid[r][c]==2:
                    q.append((r,c))
                elif grid[r][c]==1:
                    fresh+=1

        if fresh ==0:
            return 0

        def addfruit(r,c):
            nonlocal fresh
            if(min(r,c)<0 or r>=rows or c>=cols ):
                return
            if grid[r][c]!=1:
                return
            grid[r][c]=2
            q.append((r,c))
            fresh-=1
        level=0
        while q and fresh>0:
            for _ in range(len(q)):
                r,c=q.popleft()
                for dr,dc in [(1,0),(0,1),(-1,0),(0,-1)]:
                    addfruit(r+dr,c+dc)
            level+=1
        return level if fresh ==0 else -1
```

## Page structure (top to bottom)

1. **WHY section** (short, first-principles): all rotten oranges spread *simultaneously* → multi-source BFS; 1 minute = 1 BFS level; fire-spreading-from-multiple-ignition-points analogy. Why DFS can't answer "how many minutes" (it explores one path deep, not in synchronized waves).
2. **Main visualization** — three synced panels side by side (stack on narrow screens):
   - **Grid panel**: cells are clickable, cycling empty(0) → fresh(1) → rotten(2) when animation is at step 0. Fresh = orange, rotten = dark brown/green, empty = grey. Cells rotted during the current minute get a highlighted ring ("this wave"). Newly rotted cell pulses.
   - **Code panel**: the Python above, verbatim, current line highlighted each micro-step. When `addfruit` bails, highlight the specific guard line that fired (bounds vs `!=1`).
   - **State panel**: deque rendered as (r,c) chips with a divider between "this minute's ring" and "next minute's ring"; live `fresh` counter; `level` (minutes) counter; `for _ in range(len(q))` remaining-pops countdown; final verdict banner (returns 0 / level / -1).
3. **Controls**: Prev / Next micro-step, Play/Pause with speed slider, Reset. Preset dropdown: (a) classic spread `[[2,1,1],[1,1,0],[0,1,1]]` → 4, (b) unreachable `[[2,1,1],[0,1,1],[1,0,1]]` → -1, (c) no fresh `[[0,2]]` → 0, (d) single source line.

## Engine (correctness-critical)

- One JS function `simulate(grid)` mirrors the Python **line for line** (including seeding order row-major, neighbor order `[(1,0),(0,1),(-1,0),(0,-1)]`, `while q and fresh>0` guard, `return level if fresh==0 else -1`). It emits an **event log**: `init-scan`, `seed`, `count-fresh`, `early-return-0`, `pop`, `guard-oob`, `guard-notfresh`, `rot`, `level-inc`, `verdict`.
- UI is a pure replayer over the event log (forward + backward: each event stores enough to undo). Animation can never diverge from the algorithm.
- **Visible teaching moment**: with the `fresh>0` guard, once fresh hits 0 the loop exits even with items still in the queue — animation must show the queue non-empty but the loop stopping, with a callout explaining why that's safe and saves work.

## Verification (builder must do before returning)

Run a Node script that executes `simulate()` for all 4 presets **plus ≥20 random grids (≤5×6)** and compares the returned minutes against an independent straightforward BFS reference implementation (written separately, not shared code). Also verify against the known LeetCode answers for presets. Report the comparison output verbatim.

## Out of scope (YAGNI)
DFS comparison mode, gamification/XP, editable grid sizes beyond preset dimensions (grid resize buttons optional, max 8×8 if trivial), localStorage.

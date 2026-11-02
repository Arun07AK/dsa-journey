# Rumor Room — Cinematic Metaphor Animation for Rotting Oranges (LC 994)

Date: 2026-08-12 · Approved by Arun · Builder: Opus subagent · Reviewer: Fable

## Goal
Standalone `rumor-room.html` in `~/AEKAY/05-CAREER/DSA/visualizations/Graph/` — a **visualization-only** cinematic page (NO code panel, NO micro-stepping) that acts out the rumor-in-a-room metaphor for Arun's Rotting Oranges solution. Companion to `rotting-oranges.html` (the step-through/code page). Self-contained, no external deps, dark theme matching the folder's other pages. Link between the two pages (small "see the code version →" / "see the story version →" nav link).

## The metaphor (from Arun, drive everything from this)
- Grid cell 2 = person who KNOWS the rumor (gossiper). Cell 1 = person who HASN'T heard. Cell 0 = empty chair.
- Minute 0 setup: everyone who knows stands up into a single LINE (the queue); count of un-informed people is written down (fresh).
- Every minute: whistle blows; everyone currently in line tells their 4 neighbors (up/down/left/right).
- Neighbor is wall/empty chair/already-knows → ignored (bubble bounces off). Neighbor hasn't heard → they learn it, fresh−1, status flips (can't be told twice), they join the BACK of the line for next minute.
- Stop the whistle the moment fresh == 0 (even with people still in line — call this out). If line empties with people still un-informed → unreachable → −1.

## Scene layout (single screen)
1. **Header strip**: title + two big counters — "Minute: N" and "Haven't heard yet: N" (ticks down live) — plus a whistle badge that animates each minute ("🔔 Minute N!").
2. **The room** (main area): grid of chairs. People = simple SVG/CSS figures (head + body), NOT bare emoji: knower = warm red/orange glow, subtle talking animation; unaware = calm blue, idle; empty chair = grey outline chair shape. Cells keep small r,c labels off in this page (story mode) — optional tiny coordinates on hover only.
3. **The line** (bottom strip): a literal horizontal row of standing figures — the queue, rendered in order. A divider marks "talking this minute" vs "joined this minute (talks next)".
4. **Ending banners**: (a) success — whistle stops, leftover line highlighted with callout "Everyone knows! No point whistling again — that's `while q and fresh>0`", confetti burst, "Answer: N minutes"; (b) failure — room dims, spotlight on the still-blue isolated people, banner "They can never hear it → return −1".

## Choreography per minute (one smooth wave, ~2–4s at default speed)
1. Whistle badge pulses, minute counter increments label ("Minute N begins").
2. For each person in this minute's ring (staggered ~150ms apart): their room figure highlights; 4 speech bubbles fly toward neighbors. Bubble outcomes visually distinct: bounces off wall edge (bubble pops at grid edge), fades on empty chair ("empty chair"), shrugs off already-knower ("already knows"), LANDS on unaware person → shocked flash (😮-style eyes/color flash) → figure flips blue→red → fresh counter ticks down → a clone figure slides from the room into the back of the line.
3. When ring drains: divider in the line advances; if fresh hit 0 mid-wave, remaining bubbles/tellers still finish their current teller but the NEXT loop-check stops (mirror the engine exactly — the engine already models this).
4. Minute-0 intro choreography before the loop: scan sweep across the room, knowers stand up one by one and slide into the line, counter counts the blues.

## Controls (minimal, story mode)
- Play / Pause / Replay button (one primary button that morphs).
- Speed slider (0.5×–3×).
- Scenario dropdown: same 4 presets as rotting-oranges.html (classic → 4, walled-off → −1, no fresh → 0, single line → 4). No grid editing on this page (YAGNI — the code page has it).
- Auto-plays on load? No — show the assembled room at Minute 0 with a big centered Play button.

## Engine (correctness-critical)
- Copy the verified engine block from `rotting-oranges.html` VERBATIM (`/* ===== ENGINE-START/END ===== */`, simulate/initState/applyEvent/undoEvent/PRESETS/DIRS). Do not modify it. The animation layer groups the event log into waves: `init-scan`/`seed`/`count-fresh` = intro; `ring-start`..`level-inc` = one minute; `loop-check` with freshExit/exit = ending selection; `early-return-0` = instant "0 minutes" ending; `verdict` = final banner.
- Animation timing may be cosmetic but state shown (counters, line order, who flips when) must come from the event log only.

## Verification (builder must do before returning)
1. Diff the copied engine block against the source in rotting-oranges.html — must be byte-identical (`diff` of extracted blocks).
2. Re-run the existing scratchpad verify script (or equivalent) against the new file's engine block — all grids pass.
3. `node --check` all script blocks.
4. Wave-grouping unit check in Node: for each preset, group events into waves and assert: number of whistle waves == returned level for successes; every `rot` event lands inside exactly one wave; for the classic preset the freshExit loop-check occurs with a non-empty queue.

## Out of scope
Code panel, micro-stepping, grid editing, sound/audio, gamification.

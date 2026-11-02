# Working agreement for this repo

This repo is a **learning journal**, not a software project. Code here exists to teach me
something, not to ship. Optimise every answer for *what I'll be able to do cold next month*,
not for getting me unstuck today.

Primary language: **C++**. Write C++ unless I ask otherwise.

---

## Rule 0: don't hand me the answer

When I bring a problem, do **not** open with a solution and do **not** write the full function
unprompted. Climb this ladder one rung per message, then stop and wait for me:

1. **Ask what I've tried.** If I haven't tried, tell me to go try for ten minutes.
2. **Nudge the observation** — point at the structure, never the technique.
   *"What's true about every element left of the pivot?"* — not *"use binary search."*
3. **Name the pattern**, only if the nudge didn't land. *"This is a sliding window."*
4. **Sketch the invariant** in words or pseudocode. Still no C++.
5. **Full solution** — only when I ask for it outright, or when the 45 minutes are up.

If I say *"just give me the answer"*, give it. Then immediately ask me to recode it from
scratch without looking. The recode is the part that teaches (Daily Rule #4).

**The 45-minute rule.** I don't stay stuck past 45 minutes. If I tell you I'm past it, skip
to the solution without making me ask twice. A hint is not cheating — hints teach the
*trigger*, and the trigger is the thing I'm actually training.

---

## What a good session produces

Every solved problem ends with an entry appended to the **top** of the log in `solved.md`,
in exactly the template that file defines. Four lines, and the fourth is load-bearing:

- **Pattern** — the reusable idea, phrased so it applies to problems I haven't seen.
- **Key insight** — the one thing that unlocked it.
- **If I saw it cold again** — the recognisable *trigger*. This line is the whole point of
  the file. It turns solving into recognising, which is what interviews actually test.
  If this line could be copy-pasted onto a different problem, it's too vague — rewrite it.
- **Did I need a hint?** — honest. Yes is a fine answer and I want it recorded.

Then update the pattern-coverage table in the same file if the feel genuinely changed
(⬜ → 🟡 → 🟢). Don't inflate it. 🟢 means *I could teach this*, not *I solved one*.

---

## Never do these

- **No guilt framing.** Never "you missed yesterday" or "you're behind." If I've been away a
  month, the correct response is to pick a problem and start. Nothing else. This is the rule
  that matters most, and it is *not* the same as hiding the numbers — see below.
- **No sandbagging the numbers.** I track this deliberately (see *Tracking*). Record what's
  true, including a broken streak, and don't soften it or editorialise around it.
- **No rewriting my log entries into your voice.** Tighten my wording if it's unclear, but
  the entry stays mine.
- **No committing PDFs.** Course material is third-party; `.gitignore` already blocks `*.pdf`.
  Don't work around it.

---

## Tracking

I keep counts and streaks. I tried it without them and I want them back — the 54-day streak
was real and it worked. So: surface the numbers, don't bury them.

- **`PROGRESS.md` is the single source of truth for counts.** Per-topic, difficulty split,
  streak. Do not duplicate those tables into any other file — that's how trackers go stale
  and stop being believed.
- The upstream source is the **NeetCode 250** dashboard, which you can't reach from the
  sandbox. Take numbers from me or from `PROGRESS.md`. **Never estimate or infer a count.**
  The official per-topic denominators are fixed and sum to exactly 250 — if a column doesn't
  add up, something is wrong, so say so rather than papering over it.
- `solved.md` carries the log. `RESUME.md` carries the one-line state.

**When a streak breaks**, write the zero down and move on in the same breath. No commentary,
no recovery plan, no "let's get back on track." The number is information, not a verdict —
that distinction is the entire reason tracking is safe to keep.

---

## Repo map

```
PROGRESS.md              the tracker — counts, streak, derived read (source of truth)
RESOURCES.md             researched resources mapped to the topics still ahead
STRATEGY.md              the approach + the daily rules
solved.md                the pattern library — the real artifact, grows one entry at a time
RESUME.md                session handoff: read this FIRST in a fresh cloud session
learning-method.html     how DSA is actually learned
finish-150.html          the remaining graphs / DP set
visualizations/          single-file interactive tools, grouped by pattern
NEETCODE 75/             per-pattern study folders and notes
```

### Building a visualizer

Only when a pattern won't click from reading — a visualizer is a last resort, not a reward.
The house style, which every existing one in `visualizations/` follows:

- **One self-contained `.html` file.** No build step, no framework, no CDN. It has to open
  by double-click in five years.
- **Simulate, then render.** Run the real algorithm first, emit a list of step objects, and
  draw purely from that list. Never animate by hand alongside the code — hand-drawn
  animation drifts from the algorithm and then teaches the wrong thing.
- **Learner-driven stepping.** `→`/`Space` forward, `←` back, `R` reset. Nothing autoplays.
- **Verify the worked example** against a reference implementation before committing.

---

## Cloud session notes

This repo gets used from Claude Code cloud sessions, which are **fresh clones on a remote
VM**. Consequences worth remembering:

- Nothing from my laptop is here. Only what's committed exists. If it matters, commit it.
- `RESUME.md` is the continuity mechanism — read it at the start, update it at the end.
- `leetcode.com` is **not reachable** from the sandbox by default. Don't try to fetch a
  problem; ask me to paste the statement, or work from the name if you know the problem.
- `g++` is available. Compile and actually run test cases rather than eyeballing code —
  `g++ -std=c++20 -fsanitize=address,undefined -g scratch.cpp && ./a.out` catches the
  off-by-ones that reading never does. Keep scratch files out of commits.

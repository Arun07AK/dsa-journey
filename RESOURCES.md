# RESOURCES

Researched and link-checked **2026-11-02**. Opinionated on purpose — a list of forty links is
not a resource, it's a way to avoid starting. Everything here is something to actually use,
tied to where you are on the roadmap.

**A warning about searching for this yourself:** most "Best DSA Resources 2026" pages are SEO
content marketing for a paid course, including several that rank on page one. The ranked
listicles are not research. What's below is either free, or paid and named as such.

---

## The spine

| Resource | Cost | What it's for |
|---|---|---|
| [NeetCode 150](https://neetcode.io/practice/practice/neetcode150) | Free | **The finish line.** Every problem has a video. This is the plan; everything else is support. |
| [NeetCode 250](https://neetcode.io/practice/practice/neetcode250) | Free | The same 150 plus 100 extras. Used only as a remedy — 22 of them, in Graphs, Advanced Graphs and DP. |
| [NeetCode — Advanced Algorithms](https://neetcode.io/courses/advanced-algorithms/0) | Free | Dijkstra, union-find, MST, topological sort. Watch this **before** topic 12, not during. |
| [CP-Algorithms](https://cp-algorithms.com/) | Free | The reference for *how an algorithm actually works*, with correct C++ already written. When NeetCode shows you the idea and you want the rigorous version, it's here. |
| [VisuAlgo](https://visualgo.net/en) | Free | Watch a structure move. Built by Steven Halim (author of *Competitive Programming*), not a toy. Good for heaps, tries, union-find, and the graph algorithms. |

---

## Mapped to what's left

### Now — close out Graphs (5 problems)

Nothing new to pick up. You already have the visualizers for BFS/DFS and multi-source BFS in
`visualizations/Graph/`, which is exactly the right tooling for this. Finish the five.

### Next — Advanced Graphs (10 problems)

This is the first genuine step up on the roadmap: Dijkstra, union-find, MST, topological sort.
Watching the NeetCode *Advanced Algorithms* course end-to-end first is worth the time, because
these are algorithms you implement rather than derive.

- [CP-Algorithms — graph section](https://cp-algorithms.com/#graphs) for correct C++ you can
  read and then rewrite from memory.
- [VisuAlgo](https://visualgo.net/en) for union-find and MST specifically — they're much
  easier watched than read.

### The big one — Dynamic Programming (23 core + 10 extras, both halves)

**This is the single largest block ahead of you, and the only place outside graphs where the
plan says go deep.** It's also the
topic most people bounce off, and the reason is almost always the same: trying to pattern-match
DP problems the way you pattern-match two-pointer problems. It doesn't work. DP is a method —
define the state, define the transition, decide the order — and the method is what transfers.

- [CSES Problem Set — Dynamic Programming](https://cses.fi/problemset/) — 19 problems that
  teach the *method* rather than the trick. Free, no account friction, and the difficulty ramp
  is better designed than LeetCode's. Widely considered the best DP set that exists.
- [Errichto's CSES DP editorial](https://codeforces.com/blog/entry/70018) — walkthroughs for
  that whole section by a Codeforces grandmaster. *(Open in a normal browser; Codeforces
  blocks automated fetches.)*
- [Competitive Programmer's Handbook](https://cses.fi/book/book.pdf) — free PDF, same author
  as CSES. **Chapter 7 is the best short treatment of DP in print.** Read it once before
  starting topic 13; it's about ten pages and it reframes the whole thing.

If DP is still not landing after a dozen problems, that's the signal to build a visualizer —
the DP table filling in, cell by cell, with the recurrence shown. It's the one topic in the
back half where the tool would genuinely pay for itself.

### Later — Greedy, Intervals, Bit Manipulation, Math & Geometry (44 problems)

Shorter topics, less conceptual lift. NeetCode's videos are sufficient; no extra resource
needed. Intervals is only 7 problems and is mostly one idea (sort by start, then sweep).

---

## Worth knowing about, not needed now

- [MIT 6.006 — Introduction to Algorithms](https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/)
  *(free)*. A real university course with proofs. This builds the understanding that makes
  hard problems tractable, but it's a semester, not a supplement — worth it after the 250, or
  alongside it if you want depth more than coverage.
- [AlgoMonster](https://algo.monster/) *(paid)*. Its selling point is a flowchart from problem
  statement to pattern. You're building the same thing yourself in `solved.md`, one
  "if I saw it cold again" line at a time — and the version you write will stick better than
  the version you buy.
- **Striver's TUF** — ~75 problems of history, no longer the tracked sheet. Don't restart it;
  running two lists at once is how both stall.

---

## C++ specifics

You're in C++, which the pattern courses mostly treat as a second-class citizen behind Python.
Two things that matter in practice:

- **Compile with sanitizers while learning.** This catches the off-by-one and the
  read-past-the-end that silently pass on small test cases:
  ```
  g++ -std=c++20 -fsanitize=address,undefined -g sol.cpp && ./a.out
  ```
- **`cp-algorithms` is a C++ reference first.** Its snippets are production-correct C++, which
  makes it a better fit for you than the Python-centric pattern sites.

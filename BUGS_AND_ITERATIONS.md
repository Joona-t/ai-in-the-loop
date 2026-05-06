# Bugs & Iterations

A log of bug fixes and iterations on this repo. Newest entries at the top.

---

## 2026-05-07 — Schedule drift across prompt and README

**Problem.** The routine prompt and README both claimed the routine "runs every 4 hours," and the prompt instructed Claude to scope searches to "the last 4 hours." The actual cron is `0 5,9,13,17,21 * * *` Helsinki time — five runs a day with one 8-hour overnight gap (21:00 → 05:00). With the old instructions, the 05:00 run would have missed everything published between 01:00 and 05:00.

**Root cause.** The prompt and README were drafted assuming a uniform 4-hour cadence and never reconciled when the schedule landed as 5x/day with one wider window. The README repeated the wrong framing in three places (tagline, "How it works", V2 roadmap line). A third 4-hour reference was hidden inside the prompt body itself ("1-3 papers/posts/talks from this 4-hour window," section 5) and only surfaced on a careful re-read.

**Fix.**
- Prompt opening states the five clock times explicitly and instructs scoping "since the previous scheduled run" (~8 hours for the 05:00 run, ~4 hours otherwise).
- README "How it works" mirrors the schedule and lookback rules.
- README tagline says "fires five times a day"; V2 roadmap line says "5x/day scheduled run."
- Prompt section 5 reads "from this run's window" — self-describing language so future cadence changes don't reintroduce the bug.
- Header note in `routine-prompt.md` upgraded to a dated "Last synced" block so future drift between this file and the live cloud routine is visible at a glance.

The live cloud routine prompt is updated separately in the Anthropic UI; that surface is not version-controlled here.

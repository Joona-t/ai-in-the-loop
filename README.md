# ai-in-the-loop

A small automation experiment: a Claude Code cloud routine that fires five times a day and outputs a structured AI/dev intelligence brief.

## Why this exists

Social media is a poor signal source for AI and developer news. The signal is buried in noise, the noise is engineered to be addictive, and stepping away — which I want to do more of — means missing things that matter.

This repo documents an alternative: a scheduled loop instead of an algorithmic feed, with a significance threshold that lets it stay quiet when nothing important happened.

It is not a product. It is how I am trying to stay current without being terminally online.

## How it works

The routine fires five times daily at 05:00, 09:00, 13:00, 17:00, and 21:00 Helsinki time. Each run scopes its web search to items published since the previous run — usually a 4-hour window, with one 8-hour overnight window covering 21:00 → 05:00. Runs that find nothing meeting the significance threshold output a single line and stop, deferring to the next loop instead of padding.

Sections, when there is signal:

1. Items relevant to my projects
2. Anthropic ships
3. Competitor moves
4. Open source & local ML
5. Worth reading

Each item carries a citation. The brief is capped at ~400 words unless the cycle genuinely warrants more.

## The prompt

The prompt is in [`routine-prompt.md`](./routine-prompt.md).

The live version lives on Anthropic's side; this file is the source of truth I edit against. Source-controlling it gets me three things: transparency about what the loop is told, version history when I tune it, and reproducibility if I want the setup elsewhere.

## Roadmap

**V2 — near-realtime trigger.** A small Cloudflare Worker polls a curated list of RSS/Atom feeds (Anthropic news, docs, model release pages) every 15 minutes. When a new item appears, the Worker fires the routine via API trigger. KV-backed dedupe so the same item never triggers twice. The 5x/day scheduled run stays as the fallback floor.

The point is to not miss a same-day Anthropic release while keeping the rest of the brief on its calmer cadence.

## Philosophy

Understand the problem before automating it. The loop is short, the threshold is high, and the default output is silence — because the goal is to stay informed, not to manufacture content. Signal over noise. That is the difference between staying current and being terminally online.

## Stack

- Claude Code cloud routines (Claude Opus 4.7)
- Web search
- Future: Cloudflare Workers + KV

## Notes

- `briefs/` is reserved for an eventual archive of notable briefs. Not auto-populated yet.
- No secrets, API keys, or routine tokens live in this repo. The routine itself is configured on Anthropic's side.

---

Vibed with Claude

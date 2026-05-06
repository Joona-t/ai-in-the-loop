# routine-prompt

> This is the prompt as of 2026-05-07. The live version may drift; this file is the source of truth I edit against.

---

```text
AI/dev intelligence brief. Runs every 4 hours.

Scope every search to items published or materially updated in the
last 4 hours. If nothing meets the significance threshold below,
output only:

  "No significant updates this cycle."

and stop. Do not pad, do not recap older items, do not include
"worth reading" filler — defer to the next loop.

When there IS signal, output a single markdown digest, ranked by
importance (not chronology). Omit any section with no items.

1. RELEVANT TO MY PROJECTS — News materially affecting:
   - Sparky (macOS SwiftUI, GRDB, claude -p subprocess, on-device
     inference target)
   - TONGUE (iOS Mandarin, Azure TTS, CoreML CREPE, CF Worker)
   - LoveSpark Reads (Cloudflare D1/Workers/R2)
   - Blitz-Swarm (multi-agent consensus, Redis blackboard)
   - glyph-grid (p5.js ASCII renderer)
   - Chrome/Edge/Firefox extension portfolio
   Each item: headline, link, one-sentence "→ relevant because."
   No fake relevance.

2. ANTHROPIC SHIPS — Claude models, Claude Code, Agent SDK, MCP,
   pricing, docs. Sources: anthropic.com/news, docs.claude.com,
   code.claude.com, @AnthropicAI.

3. COMPETITOR MOVES — OpenAI, Google DeepMind, Meta, Mistral, xAI,
   DeepSeek, Qwen, Alibaba. Ship-confirmed only — no rumors, no leaks.

4. OPEN SOURCE & LOCAL ML — Consumer-GPU inference (RTX 5060 Ti
   class), Gemma family, llama.cpp, vLLM, MLX, on-device tooling.
   Privacy-first / local-first especially.

5. WORTH READING — 1-3 papers/posts/talks from this 4-hour window,
   one sentence why each.

SIGNIFICANCE THRESHOLD (only these qualify):
- New model release or model update
- New SDK / framework / API release or breaking change
- New product or major feature ship
- Pricing or access policy change
- Security disclosure or notable policy/legal development
- Paper with a genuinely novel result, not incremental
Skip: recaps, opinion pieces, tutorials, incremental docs polish,
hype threads, speculation about unreleased products.

Rules:
- No hype words: no "game-changing," "revolutionary," "AGI moment."
- Cite every claim with a link.
- Under 400 words unless the cycle genuinely warrants more.
```

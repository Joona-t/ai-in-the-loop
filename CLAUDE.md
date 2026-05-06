# CLAUDE.md

Repo-level context for Claude Code sessions on this project.

## Purpose

This repo holds the prompt source and supporting docs for an AI/dev intelligence brief — a Claude Code cloud routine that runs every 4 hours. The live routine is configured on Anthropic's side; this repo is the version-controlled source of truth I edit against. The README explains the project in full.

## How I work

- **Specs first.** Plan before code. For non-trivial changes, write `plan.md` before touching files. Implement only when I say "implement it all."
- **Carmack-style architecture.** Map full data flow before writing code. Data-oriented. Explicit over implicit. No premature abstraction.
- **No magic.** Every effect should be traceable to its cause from a cold read.
- **Ask before destructive or external operations.** Confirm before `gh` commands, force pushes, history rewrites, or anything that touches a remote. Local edits are fine without asking.

## Conventions

- **Repo.** kebab-case names. Branch: `main`. GitHub user: `Joona-t`.
- **Commits.** No `Co-Authored-By` lines, ever. Sole-authored.
- **Secrets.** None. The routine lives on Anthropic's side; nothing here reads from environment, API keys, or token files.
- **Public copy.** Plainspoken. No hype. The 🜂 sign-off is the one allowed motif.

## Files

- `README.md` — public-facing description.
- `routine-prompt.md` — the prompt as committed to source.
- `briefs/` — reserved for an eventual archive of notable briefs. Empty for now.

## Related

Full LoveSpark conventions (broader fleet of extensions, iOS apps, tools) live in my main CLAUDE.md at `~/CLAUDE.md`. Not part of this repo.

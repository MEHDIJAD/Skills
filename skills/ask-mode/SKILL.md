---
name: "ask-mode"
description: "Read-only question mode for Mehdi: turned on with /ask on (or /ask-mode), stays on until /ask off. Claude only answers questions — it reads and explains, and never changes files, runs changing commands, or touches git/Docker/services."
---

# /ask on — ask-only mode (no changes)

Mehdi typed `/ask on` (or `/ask-mode`). From now until he types `/ask off`, Claude **only answers
questions**. Nothing on his machine, repo or services changes.

## Allowed

- Reading: open files, search the code, `git status` / `log` / `diff` / `show`, `ls`, `cat`, `grep`.
- Read-only checks: `docker ps`, `docker logs`, `docker compose config`, `curl` GET requests to local
  services, `--help` / `--version` / `man`.
- Explaining: concepts, code, errors, logs, commands — with the usual simple English + technical
  labels and the C++ analogy when a new concept appears.
- Suggesting: describe what to change and where, show a command or a code idea **in the answer** for
  Mehdi to run or write himself.

## Not allowed (even if it looks small)

- Creating, editing, renaming or deleting any file (code, config, `.env`, docs, memory files).
- Commands that change state: installs, builds, `make up/down/clean`, `docker compose up/restart/rm`,
  `git add/commit/push/merge/checkout/switch/stash/reset`, migrations, `npm/pnpm install`, `rm`, `mv`.
- POST / PUT / PATCH / DELETE requests, creating test users, sending messages, opening PRs or issues.
- Spawning agents that could make changes.

If answering truly needs a change, say so in one line ("this needs a change — turn off `/ask` or tell
me to do it") and stop. A direct request like "do it", "fix it", "change it" still does **not** change
anything while the mode is on: remind him to type `/ask off` first.

## Answer shape

- Answer the question asked, nothing more; end with one concrete next action he can do himself.
- Other modes (`/short`, `/hint on`, `/learn`, `/strict`, ADHD format) still apply on top.

## Turning it off

`/ask off` ends the mode: confirm in one line, then normal behaviour (changes allowed again).

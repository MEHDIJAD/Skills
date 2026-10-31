---
name: commit
description: "Inspect the current repo's staged/unstaged changes and suggest a commit message matching the repo's own convention. Never runs git add/commit/push itself — Mehdi does those. Trigger: /commit."
---

# Commit Message Suggestion — `/commit`

Mehdi runs `git add` / `git commit` / `git push` himself, always — this
skill (and Claude generally, per the global "Git" rule in
`~/.claude/CLAUDE.md`) never runs those commands, no exceptions.

## What it does

1. Run read-only git commands to see the real situation:
   - `git status` — what's staged, unstaged, untracked
   - `git diff` and `git diff --staged` — the actual content that changed
   - `git log --oneline -10` — the repo's own commit message style/convention
     (prefixes like `FEAT:`/`FIX:`, imperative mood, emoji, length, etc.)
2. Write **one suggested commit message** that:
   - Describes what actually changed, not what the task was about in the
     abstract
   - Matches the tone/format already used in this repo's `git log`, not a
     generic template
   - Is a single suggestion, not a menu of options, unless the changes are
     genuinely two unrelated things (then say so and suggest splitting)
3. Hand it back as text Mehdi can copy — in a fenced block so it's easy to
   grab exactly, including the body if the diff warrants one (not just a
   one-liner for a multi-concern change).
4. Do **not** stage, commit, or push anything. If nothing is staged yet,
   say so and suggest what looks ready to `git add`, but don't run it.

## When to trigger without `/commit`

Per the global Git rule, don't wait to be asked at all — if work in the
current task looks complete and push-ready, proactively offer a suggested
commit message the same way, without needing `/commit` typed.

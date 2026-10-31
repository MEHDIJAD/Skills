---
name: hint
description: Give Mehdi one hint instead of the answer, for something he needs to build or understand himself in the current chat/project context. Activated only when he types /hint.
---

# /hint

Mehdi typed `/hint`. He wants a nudge, not the answer. Figure out what he's currently stuck on from context — the last thing he asked about, or whatever he names right after `/hint` (e.g. `/hint how do I parse this header`) — and give him **one hint**, not a solution.

## What counts as "the thing"

- If he wrote text after `/hint`, that's the target.
- Otherwise, use the most recent unresolved question/problem in the conversation — what he was just asking about or trying to build.
- If it's genuinely unclear what he's stuck on, ask him in one line rather than guessing.

## Rules for the hint itself

1. **One hint, smallest useful size.** Point at the next thing to think about or look up — not the mechanism, not the steps, not code.
2. **No solution code.** Not pseudocode either. If a function/concept name is enough to unblock him, name it — don't explain how to use it.
3. **Point at where to look**, when relevant: which man page, which doc section, which part of the project's own subject/README, which existing function in his own codebase.
4. **Prefer a question over a statement** when it would make him find the gap himself ("what happens if the list is empty?").
5. **Don't ask if he wants more** — give the one hint and stop. He can type `/hint` again for the next nudge.

## Boundaries

- This is a single nudge, not a mode — it doesn't change how you answer anything else, and it doesn't persist. Compare `/learn` and `/strict`, which are full modes; `/hint` is a one-off.
- If `/strict` is already active, `/hint` just gives one hint in strict's Socratic style — no direct answers or code either way.
- Keep it short: 1-3 lines. This is a nudge, not a lecture.

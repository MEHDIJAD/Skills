---
name: "pseudo-mode"
description: "Persistent pseudo-code mode for Mehdi: turned on with /pseudo on (or /pseudo-mode), stays on until /pseudo off. Each step is given as plain-English pseudo-code plus one hint; Mehdi writes the code; the review comes back in the same form (what is wrong, what to fix), not as corrected code."
---

# /pseudo on — pseudo-code mode

Mehdi typed `/pseudo on` (or `/pseudo-mode`). From now until he types
`/pseudo off`, he writes every block of code himself. Claude's job is to
describe the block in plain English, then review what he wrote.

The mode has two kinds of reply: a **step** and a **review**.

## 1. Giving a step

When he asks for the next step (or a review just passed), give **one block
only** — one function, one route, one method, or one clear part of one.

The reply has exactly these parts:

1. **Goal** — one line: what this block does and where it goes (file, and
   which function or class).
2. **Pseudo-code** — numbered steps in plain English, one action per step,
   in the order the code will run. Describe *what* happens, not the syntax:
   "if the two ids are different, stop with a 404", not
   `if (id !== userOrgId) throw ...`.
3. **Hint** — one line that points at where to look: the name of a function,
   decorator or method to use, an earlier block of his own code that has the
   same shape, or the doc page to open. Name it; do not show how to call it.

Rules for a step:

- **No real code.** No code blocks, no snippets, not even one line. Names of
  functions, files, fields and types are fine in backticks.
- Keep the pseudo-code to about 3–7 steps. If the block needs more, split it
  and give the first part.
- Say which values come in and what goes out, in words.
- End with one line telling him to write it and say when it is ready.

## 2. Reviewing his code

When he says he is done ("look", "check", "is it good", pasting code, or a
screenshot), **read the real file first**, then review in the same form as
the step — directions in English, not a corrected version.

The reply has these parts:

1. **Verdict** — one line: correct, or how many things to fix.
2. **What is right** — one short line, so he knows what to keep.
3. **What to fix** — a numbered list. For each item:
   - where it is (line number or the name of the statement),
   - what is wrong, in plain words,
   - what it causes when the code runs,
   - what to change, described in English (which name, which value, which
     order) — not the fixed line itself.
4. **Next** — one line: fix and show again, or the next step if it passed.

Rules for a review:

- **Do not rewrite his code.** No corrected snippet. If a fix is a single
  misspelled name, naming the right spelling is fine.
- Order the fixes by importance: things that break the code first, style last.
- Check what a compiler would not catch: wrong field names against the
  schema, wrong status code against the contract, missing `await`, missing
  checks, security gaps.
- If the code is correct, say so plainly and move to the next step. Do not
  invent problems.
- Run the type-check or tests when it helps, and report the result in one line.

## Exceptions while the mode is on

- If he explicitly asks for the code ("show me the code", "write it", "fix
  it", "do it"), give it for that one block, then stay in pseudo-mode for
  the next message.
- Setup and tooling (install a package, run a command, edit a config or env
  file, Docker, git) get a normal direct answer with the real command. The
  mode is for the code he is learning to write, not for unblocking tools.
- Questions about a concept ("what does this do", "why") get a normal
  explanation, then the mode continues.
- Brand-new syntax he has never seen (a new library's config call, a new
  decorator) may be shown once as a tiny generic example that is **not** his
  block, so he can adapt it.

## What it does not change

- It stacks with the always-on rules in `~/.claude/CLAUDE.md` (ADHD shaping,
  Simple English / Technical, C++ analogy for new concepts) and with
  `/short` and `/brainstorming`: when a length cap is on, compress the
  pseudo-code steps rather than dropping the hint or the review items.
- It does not replace `/hint on` (one small nudge, no step list) or `/learn`
  (the 7-step workflow). Pseudo-mode always gives the full step list for one
  block and always reviews in the same form.
- It is a per-conversation toggle. A new chat starts with it off.

## Turning it off

`/pseudo off` (or "stop pseudo mode", "normal mode") ends the mode. Confirm
in one line and answer normally from then on.

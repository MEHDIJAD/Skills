---
name: short
description: "Short mode — every response capped at 5 lines, plain simple wording, no extra explanation. Activated only when Mehdi types /short. Stays on until he types /short off. Trigger: /short."
---

# Short Mode — `/short`

A blunt override on response length and wording. Nothing about *what* gets
answered changes — only how much gets said and how plainly it's said.

## What it does

- **Every response, while this mode is on, is capped at 5 lines maximum.**
  Not 5 bullet points that each wrap to 5 lines — 5 actual lines of text,
  full stop.
- Plain, simple wording. Short sentences. No jargon unless the word itself
  is the answer (and even then, no aside defining it — that's what normal
  mode is for).
- No preamble, no recap, no "let me know if...", no closing line. The 5
  lines ARE the answer, nothing padding it.
- No headers, no bullet lists, no code blocks, no bold/formatting flourish
  — just plain lines of prose. If a command genuinely has to be shown,
  it counts as one of the 5 lines, not extra.
- If the honest answer needs more than 5 lines to not be misleading,
  compress harder before adding a 6th line — cut detail, not accuracy.
  Only if compressing would make the answer actually wrong (not just
  less thorough) is going over acceptable, and only by the minimum
  needed.

## What it does NOT do

- Does not turn off ADHD mode, Simple English/Technical labeling, or any
  other always-on formatting rule from the global CLAUDE.md — it stacks
  on top of them, and where they conflict (e.g. the Simple/Technical
  two-line habit), the 5-line cap wins; fold both lenses into the same
  5 lines rather than doubling the line count.
- Does not change depth of *investigation* — still read the file, still
  check the real bug, still get the right answer. Only the reported
  answer gets compressed, not the work behind it.
- Does not persist across sessions — like `/learn` and `/strict`, this is
  a per-conversation toggle. A new chat starts with it off.

## Usage

Mehdi types `/short` — confirm in one short line, then every response
after that stays at 5 lines until he types `/short off` (or "normal
mode", "stop short mode").

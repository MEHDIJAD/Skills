---
name: brainstorming
description: "Brainstorming mode — Mehdi throws out raw, half-formed thoughts and Claude fixes/refines them along the way, every response capped short. Activated only when Mehdi types /brainstorming. Stays on until he types /brainstorming off. Trigger: /brainstorming."
---

# Brainstorming Mode — `/brainstorming`

A back-and-forth mode for thinking out loud. Mehdi drops a raw idea,
half-formed or wrong in places — not a polished question — and each
response nudges it forward instead of answering it as a one-shot task.

## What it does

- Treat each message as **an idea in progress**, not a finished spec. Do
  not wait for a "final version" before responding.
- **Fix/correct along the way** — if a piece of what he said is wrong,
  imprecise, or would break later, say so plainly and give the corrected
  version right there, in the same short reply. Don't silently agree just
  to keep momentum.
- **Every response capped at 5 lines maximum** — same hard cap as
  `/short`: plain wording, no headers, no bullet-point padding, no
  preamble/recap/closing line. If a fix needs more room, compress harder,
  don't spill past 5 lines.
- End most replies with a short nudge forward (a question, a fork, a next
  angle) so the brainstorm keeps moving — but that nudge is inside the
  5-line cap, not an extra line tacked on.
- Push back on ideas that don't hold up, in the same breath as fixing
  them — brainstorming means catching problems early, not stacking more
  ideas on a shaky base.

## What it does NOT do

- Does not turn into a deep-dive lecture — if a topic needs real
  explanation, say so in one line and offer to switch out of brainstorming
  for it, rather than blowing the cap.
- Does not replace `/checkme` — `/checkme` is a one-time check of a
  finished explanation; `/brainstorming` is an ongoing loop of raw ideas
  getting refined turn by turn.
- Does not turn off ADHD mode or Simple English/Technical labeling — it
  stacks with them the same way `/short` does: fold both lenses into the
  same 5 lines instead of doubling length.
- Does not persist across sessions — like `/short`/`/learn`/`/strict`,
  it's a per-conversation toggle; a new chat starts with it off.

## Usage

Mehdi types `/brainstorming` — confirm in one short line, then every
response after that follows the rules above until he types
`/brainstorming off` (or "stop brainstorming", "normal mode").

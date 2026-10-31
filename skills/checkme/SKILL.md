---
name: checkme
description: Mehdi writes his own understanding of a concept, in his own rough wording, and Claude checks it — confirms what's right, corrects logic mistakes, fills real gaps — to sharpen his understanding rather than just answering the original question for him. Activated only when Mehdi types /checkme. Trigger: /checkme.
---

# Check My Understanding — /checkme

`/checkme` is a one-time check, not a mode toggle. Mehdi types `/checkme`
followed by his own explanation of something (a concept, a mechanism, how a
piece of the project works), written in his own rough wording — not asking
a fresh question, but testing an understanding he already has.

## What it does

- Read his explanation as a claim to verify, not a question to answer from
  scratch.
- Go through it piece by piece (a numbered list matching his own points
  works well) and mark each part: correct, correct-but-needs-sharpening,
  or wrong.
- **Correct logic mistakes directly** — don't just say "not quite," say
  what's actually true and why the intuition that led him wrong seemed
  reasonable in the first place. Wrong beliefs left uncorrected calcify.
- **Add real depth he didn't cover**, but keep it short and clearly marked
  as an addition, not folded into "grading" his existing points.
- **End with a "Fixed version" block** — his own explanation rewritten
  clean: correct logic, correct technical wording, correct English/grammar
  (his raw writing is often rushed/typo'd), but still in his own voice and
  structure, not padded into a mini-essay. This is the piece he keeps —
  the point-by-point correction above is how he sees *why* it changed.
- **If a real gap was found in step "Add real depth," fold it into the
  Fixed version too** — append the missing piece as its own sentence/point
  in his structure, don't leave it stranded only in the point-by-point
  section above. The Fixed version should be the complete, correct
  explanation on its own, readable without needing the corrections above
  it — not just his original sentences with typos cleaned up.

## Fixed version — plain English, without losing the technical terms

- The Fixed version block is written in **the simplest English that still
  states the real mechanism correctly** — short sentences, common words,
  no filler ("essentially," "leverages," "in order to") — but it does
  **not** water down or drop the actual technical terms themselves
  (`bind mount`, `tmpfs`, `PID 1`, `FastCGI`, whatever the concept
  actually is called). Simplify the *sentences around* a term, never the
  term.
- The rule of thumb: a term stays exactly as-is the first time it's used,
  with a short plain-English clarifier right next to it if it's not
  already been explained earlier in the conversation — not replaced by a
  vaguer synonym that loses precision (e.g. keep "bind mount," don't
  soften it to "connected the file somehow").
- This applies only to the Fixed version block — the point-by-point
  correction section above it can still use the fuller Simple
  English / Technical two-line format from his global preferences as
  normal.

## What it does NOT do

- Does not answer a new question — if his message isn't him explaining
  something back but is actually a fresh ask, treat it as one, not as a
  `/checkme`.
- Does not turn into a full lesson unless he asks a follow-up — a `/checkme`
  response should be scoped to what he actually wrote, not a chance to
  teach the whole topic over again.
- Does not stay active — it applies to that one message only; no toggle
  state to track, no "on/off."
- The "Fixed version" is a corrected-and-completed rewrite of *his*
  explanation, not an unrelated, more thorough one written from scratch —
  it should still look recognizably like what he wrote, in his structure,
  just with wrong parts fixed and missing parts appended in-place.

## Usage

Mehdi types `/checkme` plus his own explanation of something, e.g.
`/checkme so a docker volume is just...`. Respond in two parts:

1. Point-by-point check of what he wrote (correct / needs sharpening /
   wrong, with the fix and why), in the standing Simple English / Technical
   format from his global preferences.
2. A closing **"Fixed version"** block — his explanation rewritten clean,
   logic and wording both corrected, still in his own words/structure.

Then stop — don't continue into unrelated new material unless he asks.

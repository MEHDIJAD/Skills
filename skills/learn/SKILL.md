---
name: learn
description: Enter Learning Mode — the 7-step guided learning workflow (understanding → structure → brainstorming → pseudocode → hard-coded version → Mehdi's own code → review). Activated only when Mehdi types /learn; stays active until he types /learn off or asks to exit.
---

# Learning Mode — 7-Step Process

Learning Mode is now **ON**. It applies to every task from this point in the conversation until Mehdi turns it off.

## Entering and exiting

- **Enter**: Mehdi typed `/learn`. Confirm the mode is on and ask what he wants to work on (or apply it to the task he provided with the command).
- **Exit**: When Mehdi types `/learn off` or clearly asks to leave the mode (e.g. "exit learn mode"), confirm it is off and return to normal behavior.
- While the mode is on, show `🎓 Learning Mode — Step N: <name>` at the top of every response.

## The 7 Steps (strict order)

1. **Understanding Concepts** — Explain the underlying concepts and what we're trying to solve.
2. **Structure** — Outline the high-level structure / architecture / approach.
3. **Brainstorming** — Explore possible solutions, trade-offs, and edge cases.
4. **Pseudocode** — Write the logic in plain pseudocode (no real syntax).
5. **Hard-coded Version** — A simple, hard-coded implementation to prove the idea works.
6. **My Own Code** — Mehdi writes the real code himself.
7. **Discussion & Final Code** — Review the code together, discuss improvements, produce the final version.

## Rules

- **Guide, don't do it for him.** At each step, coach and ask questions so Mehdi figures it out on his own. Do **not** give the answer or write the code (except where the step explicitly calls for it — step 5).
- **One step at a time.** Never move to the next step until Mehdi explicitly says so.
- **The keyword is `JAD`.** Only when Mehdi types `JAD` does the workflow advance to the next step. Without `JAD`, stay on the current step no matter what.
- If Mehdi asks a question that would skip ahead, redirect back to the current step.
- When a task finishes (step 7 done), the mode stays on — start the next task at step 1 unless Mehdi exits.

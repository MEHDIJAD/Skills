# Skills
My collection of Claude skills: reusable instructions and workflows I've built while learning at 1337

## Skills

| Skill | Command | What it does |
|-------|---------|--------------|
| `learn` | `/learn` · `/learn off` | 7-step guided learning: understand → structure → brainstorm → pseudocode → hard-coded → my code → review |
| `hint` | `/hint` | One small hint instead of the answer (one time) |
| `hint-mode` | `/hint on` · `/hint off` | Every answer becomes a small nudge until turned off |
| `pseudo-mode` | `/pseudo on` · `/pseudo off` | Steps given as plain-English pseudo-code + one hint; I write the real code |
| `checkme` | `/checkme` | I explain a concept in my own words, Claude corrects and fills gaps |
| `teach` | `/teach` | Teaches a new skill or concept step by step |
| `ask-mode` | `/ask on` · `/ask off` | Read-only: Claude answers questions but never edits files or runs changing commands |
| `scaffold-exercises` | `/scaffold-exercises` | Builds exercise folders (problems, solutions, explainers) |
| `i-have-adhd` | always on | Short, action-first answers: numbered steps, one clear next action |
| `short` | `/short` · `/short off` | Every reply capped at a few lines, plain words |
| `brainstorming` | `/brainstorming` · `/brainstorming off` | Fast back-and-forth on raw ideas, Claude refines them |
| `commit` | `/commit` | Reads git changes and suggests a commit message (never commits/pushes) |
| `grilling` | `/grilling` | Relentless questions to stress-test a plan or idea |
| `grill-me` | `/grill-me` | Shortcut that starts a `/grilling` session |

## Install on another PC

```bash
git clone git@github.com:MEHDIJAD/Skills.git
mkdir -p ~/.claude/skills
cp -R Skills/skills/* ~/.claude/skills/
```

Restart Claude Code, then type `/` to see the skills.

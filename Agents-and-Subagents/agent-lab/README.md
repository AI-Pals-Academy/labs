# Agent Lab — learn agents & subagents in one afternoon

## The scenario
You're asked: *"Which note-taking app should our 5-person team use?"*
Instead of one Claude doing everything, you build a small team:

```
                 YOU
                  │
          ORCHESTRATOR  (main Claude, guided by CLAUDE.md)
                  │
   ┌──────────────┼──────────────┐      Phase 1: PARALLEL
researcher    researcher    researcher
 (Notion)     (Obsidian)    (OneNote)
   └──────────────┼──────────────┘
                  ▼
               analyst                 Phase 2: SEQUENTIAL
                  ▼
               writer  ◄── uses skill: report-format
                  ▼
              reviewer ──FIX──► back to writer (max 2x)
                  │ PASS
                  ▼
        output/final-report.md
```

## What each file teaches you

| File | What it is | Lesson |
|---|---|---|
| `CLAUDE.md` | Instructions the main agent reads automatically every session | How to give the orchestrator a plan & rules |
| `brief.md` | The goal/input | Keep the *task* separate from the *process* so you can reuse it |
| `.claude/agents/*.md` | One file = one subagent (name, description, tools, model + instructions) | How to define specialists |
| `.claude/skills/report-format/SKILL.md` | Reusable know-how any agent can load | How to share standards across agents |
| `output/` | Where agents hand work to each other | Files are how agents pass results along |

Key ideas:
- **`description`** decides *when* Claude picks a subagent. Write it like a job title + when to use it.
- **`tools`** limits what a subagent can do (the reviewer can only read — it can't "fix" things itself).
- **Each subagent has its own fresh context** — it only knows what you tell it plus the files it reads.
- **Parallel** = independent tasks (3 products). **Sequential** = one needs the previous output.

## How to run it (Claude desktop)
1. Unzip this folder somewhere, e.g. `Documents/agent-lab`.
   (The `.claude` folder is hidden — on Mac press Cmd+Shift+. in Finder to see it.)
2. Open Claude desktop → **Code** tab → choose this folder as the project.
3. Type `/agents` to confirm you see: researcher, analyst, writer, reviewer.
4. Type: **"Run the workflow in CLAUDE.md for brief.md."**
5. Approve the plan with "go", and watch the 3 researchers start at once.
6. Open `output/final-report.md` when it's done.

## Exercises (do them in order)
1. **Change the brief** — swap in 3 laptops, CRMs or cities. Run again. Nothing else changes.
2. **Add a 4th product** — notice a 4th researcher runs in parallel automatically.
3. **Add a new agent** — ask Claude: *"Create a `fact-checker` subagent in .claude/agents that re-verifies prices only."* Then add it to CLAUDE.md between Phase 1 and 2.
4. **Change a model** — set `model: haiku` on the researcher. Compare speed vs quality.
5. **Break it on purpose** — remove `WebSearch` from the researcher's tools. See what happens.
6. **Make your own skill** — e.g. `tone-of-voice/SKILL.md`, and add it to the writer's `skills:` list.
7. **Your real project** — keep the pattern: *parallel gatherers → one combiner → one writer → one checker.*

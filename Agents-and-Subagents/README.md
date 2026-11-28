<p align="center">
  <img src="../assets/logo.png" alt="AI Pals Academy" width="160">
</p>

# WB01 · Agents & Subagents, Step by Step

Learn how to build a small **AI team** in the Claude desktop app. One "manager" agent hands work to specialist subagents, some running **in parallel** and some **in sequence**.

**The scenario:** a 5-person team needs to choose a note-taking app (Notion, Obsidian or OneNote). Three researcher agents each look into one app at the same time. An analyst compares them, a writer produces a one-page recommendation, and a reviewer checks it.

▶️ **Video:** [Watch on YouTube](https://youtu.be/YXF2EWgt7VQ)

## What's here

| File | What it is |
|---|---|
| [`WB01-Agents-and-Subagents.pdf`](WB01-Agents-and-Subagents.pdf) | The workbook: 6 concept chapters with diagrams, 9 practices, cheat sheet, and a 5-question quiz with answers |
| [`agent-lab.zip`](agent-lab.zip) | The starter project. Download, unzip and open it in Claude desktop |
| [`agent-lab/`](agent-lab/) | The same starter files, to browse online |

## Quick start

1. Download **`WB01-Agents-and-Subagents.pdf`** and **`agent-lab.zip`** (click the file, then the ↓ download button).
2. Unzip `agent-lab.zip`, for example into your *Documents* folder.
3. Open the Claude desktop app, go to the **Code** tab, and choose the `agent-lab` folder.
4. Follow **Practice 0** in the PDF.

> **Can't see the `.claude` folder after unzipping?** It's hidden.
> Mac: press **Cmd + Shift + .** in Finder. Windows: File Explorer → View → Show → **Hidden items**.

## What you need

- The Claude desktop app, on a paid plan that includes the **Code** tab
- About 2–3 hours for all practices (you can stop after any practice)

## What's inside the starter project

```
agent-lab/
├─ CLAUDE.md                 ← the workflow rules the main agent follows
├─ brief.md                  ← the goal (change this to reuse the team)
├─ .claude/
│  ├─ agents/                ← researcher, analyst, writer, reviewer
│  └─ skills/report-format/  ← shared report style
└─ output/                   ← where the agents save their work
```

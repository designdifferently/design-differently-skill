# Design Differently, free skill

Removes the signs of an AI-built frontend and fixes basic UX, in one prompt.

The agent reads your code, lists what looks generated (overused fonts, emoji, AI copy, glass, fade-ins, blinking dots, tinted icon boxes, accent-bar callouts, browser-default controls, drifting tooltips, jumping dialogs, missing favicon), lets you pick what to fix, applies it, checks the result and gives you a report with before and after screenshots.

At the end it writes `DESIGN_RULES.md` into your project and links it from your agent instruction files (`CLAUDE.md`, `AGENTS.md`, Cursor rules and others). Every agent that touches the project later reads those rules first, so further vibecoding keeps the fixes instead of undoing them.

## What is inside

| File | What it is |
|------|------------|
| `SKILL.md` | The skill: rules, detection patterns and workflow for the agent |
| `PROMPT.md` | The prompt you paste into the chat to run it |
| `README.md` | This file |

## Built for

The skill is plain Markdown, so any agent that reads files or accepts instructions can use it. It was written and tuned for these:

**Coding agents with access to your files and terminal**, where it runs the full workflow including searches, checks and screenshots:

| Tool | Where to put `SKILL.md` |
|------|-------------------------|
| Claude Code | `.claude/skills/design-differently/SKILL.md` in the project, or `~/.claude/skills/design-differently/SKILL.md` for every project |
| Claude (app) | Settings, Capabilities, Skills: upload the `design-differently` folder as a zip |
| Codex | `.codex/skills/design-differently/SKILL.md`, or reference it from `AGENTS.md` |
| Cursor | `.cursor/rules/design-differently.mdc` (paste the content), or keep `SKILL.md` in the repo and mention it in the prompt |
| Windsurf, Cline, Zed, Copilot agent | Keep `SKILL.md` in the repo and mention its path in the prompt |

**Hosted app builders**, where it works from the files the builder can read and skips terminal steps:

| Tool | Where to put `SKILL.md` |
|------|-------------------------|
| Lovable | Project knowledge, or attach the file in chat |
| v0 | Project instructions, or attach the file in chat |
| Bolt | Project prompt, or attach the file in chat |
| Replit Agent | Upload to the project and mention its path in the prompt |

Then paste the content of `PROMPT.md` into the chat.

## Best results with

Use the strongest coding model your tool offers. The skill asks the agent to read a whole codebase, hold many rules at once and check its own work, which smaller models tend to cut short.

If your tool lets you set reasoning effort or thinking level, set it to high or extra high for this run. You apply the skill once per project and the rules then stay in the repo, so it is worth spending more tokens one time to get a better looking result.

| Works best | Works, with less thorough checks | Not recommended |
|------------|----------------------------------|-----------------|
| Claude Opus and Sonnet, latest versions | Claude Haiku | Small local models |
| GPT-5 class models, Codex models | Fast or mini variants of the models on the left | Models without tool use |
| Gemini Pro, latest version | Gemini Flash | |

## What it does not do

- It does not touch business logic, data, routing or backend.
- It does not install libraries, except font files, which it stores in your repo instead of loading them from Google Fonts or other hosts.
- It does not build a new design system or brand. It cleans what you have.

## Want the full version

The full Design Differently skill adds visual hierarchy, copywriting, color harmony, typography, icons and SVG, motion and speed, with library setup and UI tests. It comes with a step-by-step course.

https://designdifferently.co/

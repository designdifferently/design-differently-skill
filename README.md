# Design Differently (free version)

A quick cure for vibecoded apps and sites. One prompt scans your frontend, removes AI artifacts, fixes UX and leaves rules in your repo so the next prompts keep it clean. Your logo and brand stay. Works in Claude Code, Codex, Cursor, Lovable, v0, Bolt, Replit and more.

## What it does

The agent reads your code and lists what gives it away as AI-built: overused fonts, emoji, em dashes and AI phrasing, glass headers, fade-in animations, blinking live dots, icons in tinted boxes, accent-bar callouts, browser-default controls and scrollbars, tooltips that hang in the air, dialogs that jump in size, a missing favicon.

You reply `all` or pick the numbers you want. The agent applies only those, checks the result, and posts a report with before and after screenshots.

## What you will notice

Most of the change shows up when you use the product. Dialogs keep their size. Save and Close stay in reach. Tooltips appear on hover and go away when they should. Focus rings show up for the keyboard only. Images don't get dragged by accident. Copy reads like a person wrote it.

The site looks more professional, and still looks like yours.

## Your brand stays

The skill works from what you already built. It keeps your logo, the font set in your logo, and the color your logo and main button use. It replaces what an AI tool picked by default, and leaves what you chose on purpose.

If your logo turns out to be generated in code, the skill does not redraw it. It tells you in the report, so you can decide what to do with it.

## What happens to your repo

Commit your work before you run the skill, so you can review every change as one diff.

| | What |
|---|---|
| Changed | Styles, design tokens, shared components (buttons, dialogs, tooltips, dropdowns, badges), visible copy, page titles |
| Added | Font files in your repo (for example `public/fonts/`), a favicon if you had none, `DESIGN_RULES.md` |
| Added one line to | `CLAUDE.md`, `AGENTS.md`, Cursor rules, Windsurf rules, Copilot instructions, `replit.md`, whichever exist. If none exist, it creates `CLAUDE.md` and `AGENTS.md` |
| Removed | Google Fonts and other external font links, unused font packages, decorative fade-in and blur-in code, emoji in the UI |
| Temporary | `.design-differently/` with the screenshots. Do not commit it; delete it when you have looked at them |
| Not touched | Business logic, data, routing, backend, environment variables |

## The rules stay in your repo

Vibecoding tends to undo design work. The next prompt brings back the fade-in, the em dash, the second button component.

So at the end the skill writes `DESIGN_RULES.md` with the rules it applied to your project: your fonts and where they live, your color tokens, your shared components, and everything that is now banned. It links that file from your agent instruction files. Every agent that edits the project later reads those rules before it writes UI code, and your next prompts build on the fixes instead of breaking them.

You can edit `DESIGN_RULES.md` by hand. If you run the skill again, it updates the file and keeps your edits.

## Updates

The skill is updated as new vibecoding patterns show up. The latest version is always in this repo.

To update, replace your copy of `SKILL.md` with the one from this repo, in the same folder. Do not keep the old and new versions side by side, because agents would see two skills with the same name. Watch the repo or check Releases to see what changed.

## What is inside

| File | What it is |
|------|------------|
| `SKILL.md` | The skill: rules, detection patterns and workflow for the agent |
| `PROMPT.md` | The prompt you paste into the chat to run it |
| `README.md` | This file |

## Built for

The skill is plain Markdown, so any agent that reads files or accepts instructions can use it. It was written and tuned for these.

**Coding agents with access to your files and terminal.** The skill runs its full workflow here, including searches, checks and screenshots.

| Tool | Where to put `SKILL.md` |
|------|-------------------------|
| Claude Code | `.claude/skills/design-differently/SKILL.md` in the project, or `~/.claude/skills/design-differently/SKILL.md` for every project |
| Claude (app) | Settings, Capabilities, Skills: upload the `design-differently` folder as a zip |
| Codex | `.codex/skills/design-differently/SKILL.md`, or reference it from `AGENTS.md` |
| Cursor | `.cursor/rules/design-differently.mdc` (paste the content), or keep `SKILL.md` in the repo and mention it in the prompt |
| Windsurf, Cline, Zed, Copilot agent | Keep `SKILL.md` in the repo and mention its path in the prompt |

**Hosted app builders.** The skill works from the files the builder can read and skips the terminal steps.

| Tool | Where to put `SKILL.md` |
|------|-------------------------|
| Lovable | Project knowledge, or attach the file in chat |
| v0 | Project instructions, or attach the file in chat |
| Bolt | Project prompt, or attach the file in chat |
| Replit Agent | Upload to the project and mention its path in the prompt |

Then paste the content of `PROMPT.md` into the chat.

## Best results with

Use the strongest coding model your tool offers. The skill asks the agent to read a whole codebase, hold many rules at once and check its own work, which smaller models tend to cut short.

If your tool lets you set reasoning effort or thinking level, set it to high or extra high for this run. You apply the skill once per project and the rules then stay in the repo, so it is worth spending more tokens one time for a better result.

| Works best | Works, with less thorough checks | Not recommended |
|------------|----------------------------------|-----------------|
| Claude Opus and Sonnet, latest versions | Claude Haiku | Small local models |
| GPT-5 class models, Codex models | Fast or mini variants of the models on the left | Models without tool use |
| Gemini Pro, latest version | Gemini Flash | |

## What it does not do

- It does not touch business logic, data, routing or backend.
- It does not install libraries. Font files are the one exception, and they go into your repo.
- It does not create a new brand, logo or design system. It works with the one you have.

If you correct one of the agent's fixes during the run, it adds a short note to the Gotchas section of its own `SKILL.md`, so the next run avoids the same mistake.

## Want the full version

The full Design Differently skill adds visual hierarchy, copywriting, color harmony, typography, icons and SVG, motion and speed, with library setup and UI tests. It comes with a step-by-step course.

https://designdifferently.co/

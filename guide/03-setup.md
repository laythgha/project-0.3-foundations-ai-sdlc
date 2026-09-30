# 3. Get Set Up

## Before You Start

1. Click **Use this template** to create your own copy of this repository. Make it private.
2. Add the reviewer account named on your assignment as a read-only collaborator.
3. Clone your copy to your own machine.

## Your Client

Palmstone Living, a small online homewares store. Their sales, stock, advertising and returns are spread across six Google Sheets kept by four people, and management cannot see the business in one place. You build them a dashboard with centralised reporting. The full brief is in [guide/05-build.md](05-build.md); everything the client gave you is in `discovery/`.

## Stack

Use whatever you already know. If you have no preference, a JavaScript or TypeScript web app (for example Next.js) with a small database (for example SQLite) and a chart library (for example Chart.js or Recharts) works well.

The client's sheets are given to you as CSV exports, which is how Sam would download them from Google Sheets. Importing CSV files is enough. Reading straight from Google Sheets is an optional extra, only once everything else is done.

## Folder Structure

```
CLAUDE.md                  your AI project context (you write it)
README.md                  start here (add your run instructions at the bottom on Day 5)
SUCCESS.md                 what you are scored against
SUBMISSION.md              your submission form
LEARNING_LOG.md            skills learned, with confidence scores
project.yaml               project settings, read by the platform (do not edit)
guide/                     these instructions
.claude/skills/            teach-me and troubleshoot
discovery/                 what the client gave you (do not edit)
maintenance/               for Stage 7 only (do not open before then)
docs/01-requirements.md    one document per stage, headings already in place
docs/02-plan.md
docs/03-design.md
docs/04-build.md
docs/05-testing.md
docs/06-deployment.md
docs/07-maintenance.md
docs/ai-pipeline.md        your AI pipeline, context and token use
docs/reflection.md         looking back at the week
design/                    Claude Design screenshots
src/                       your application code
tests/                     your tests
.env.example               variable names only, never real values (you create it)
.github/workflows/         your automatic check (you create it)
```

If your framework wants a different layout for `src/` and `tests/`, follow the framework and say so in `docs/03-design.md`.

## Standards

- **No secrets anywhere, ever.** Real values go in `.env`, which is already ignored by Git.
- **Made-up data only.** Use the files in `discovery/`. Never add real personal data.
- **Diagrams display inline.** Any tool is fine: text that renders inline (such as Mermaid) or an image saved in the repository and embedded with a markdown image link.
- **Commit as you go.** Commit after each task, with a clear message. One big commit at the end is flagged.
- **Keep code you can explain.** If you cannot explain a piece of code in your live review, it counts against you, whoever wrote it.
- **AI use is expected and visible.** Your stage documents and `docs/ai-pipeline.md` show how you directed it.
- **Short and honest beats long.** A few clear lines per heading is enough. Your reviewer should be able to check everything without asking you anything extra.

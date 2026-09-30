# 5. What You Will Build

## The Brief

> We sell homewares on our website, a marketplace and Instagram. Everything lives in separate Google Sheets and our Monday numbers take half a day and never match. We want one place where we can see how the business is doing, in time to act on it.
>
> Dana, owner, Palmstone Living

That is all the brief says. Everything else is in `discovery/`: the call transcript, a follow-up email, a note from the warehouse, and six sheet exports. The sheets are messy on purpose. Finding out what the client really needs, and what is wrong with their data, is part of the work.

You build a dashboard that brings all six sheets into one place and gives management the reporting they need. Work through the seven stages below in order. Each stage has a document in `docs/` with its headings already in place. Fill it in as you go, not at the end, and end each one with **AI did / I decided**.

---

## Stage 1: Discovery and Requirements

1. **Read every source.** The transcript, the email, the warehouse note, and all six sheets.
2. **Audit the sheets.** For each file: what it holds, who keeps it, and every problem you find (formats, duplicates, missing values, names that do not match across files).
3. **State the problem** in one or two sentences.
4. **Name the users** and what each one needs from the dashboard.
5. **List the must-haves and the qualities.**
6. **Resolve the gaps.** List every open question. Answer it from the sources where you can, and note which source. Where the sources disagree or say nothing, write down your assumption and mark it as one.
7. **Write acceptance criteria** for every must-have.
8. **Say what is out of scope.**

**Done when:** the audit covers all six sheets; every must-have has an acceptance criterion; every assumption is marked.

## Stage 2: Planning

1. **Write user stories,** at least one per user.
2. **Break them into tasks** of an hour or two, as a checklist. No board or other tool is needed.
3. **Order the tasks** and note what depends on what.
4. **Mark the first visible slice,** for example one channel's sales on screen by the end of Day 3.
5. **Guess the time** for each task.
6. **Name the risks,** for example a sheet format you are not sure you can clean.

**Done when:** every must-have maps to a task, and the plan fits Days 3 and 4.

## Stage 3: Design

1. **Architecture.** One diagram: sheets in, import and cleaning, storage, dashboard.
2. **Data model.** How six messy sheets become a few clean tables, as a diagram or a table.
3. **Cleaning rules.** How you handle each problem from your audit: matching product names to one code, reading every date format, stripping currency symbols, removing duplicates, and what you do with rows you cannot clean.
4. **Folder structure.** The one you chose, the option you did not, and why.
5. **User interface.** Design the dashboard in Claude Design, working from your requirements. Save at least two screenshots in `design/`, including one before and one after a change you asked for.
6. **Feedback.** Show the design to someone else and ask them to look at it as Dana or Sam would. Write down three things they said and what you changed.

**Done when:** `docs/03-design.md` has both diagrams, the cleaning rules, the folder choice, the Claude Design link and the feedback notes.

## Stage 4: Build

1. **Set up.** Fill in `CLAUDE.md`, create the project, and get it running.
2. **Import.** Load the six sheet exports.
3. **Clean.** Apply your cleaning rules, and show Sam which rows were skipped and why.
4. **Store.** Save the clean data in your data model.
5. **Show.** Build the dashboard screens from your design, one task at a time.
6. **Review every change.** Ask the agent for a plan, approve it, then let it write the code. Run the app after every task, and ask the agent to explain anything you do not understand.
7. **Commit after every task,** and tick it in `docs/02-plan.md`.

**Done when:** the dashboard shows real numbers from all six sheets, and `docs/04-build.md` records at least one time you corrected the agent.

## Stage 5: Testing

1. **Test plan.** Each acceptance criterion, and the type of test that covers it.
2. **Unit tests** (at least 3) for your cleaning rules, for example reading a date or a price.
3. **Integration test** (at least 1) that imports a sheet and checks the stored totals.
4. **UI tests with Playwright** (at least 2) that open the dashboard and check what appears.
5. **Edge cases** (at least 3), for example a duplicate order, an unknown product name, or an empty file.
6. **Prove the tests are real.** Break your code once on purpose, show a test fails, then put it back.
7. **Regression run.** Run the whole suite and record the result.
8. **UAT.** Use the dashboard yourself as Dana, then as Sam. Mark every acceptance criterion pass or fail.

Write tests as you build, not only at the end. Have AI draft them, then read what each one actually checks.

**Done when:** all tests pass with one command, and the UAT table is complete.

## Stage 6: Deployment

1. **Configuration and secrets.** Add `.env.example` with names only, and check no secret is anywhere in the repository.
2. **Automatic check.** A GitHub Actions workflow that installs, runs your tests and builds on every push. Get it green. Running Playwright in the workflow is optional.
3. **Run instructions.** Add them to the bottom of `README.md`, so anyone can run and test the dashboard in a few commands.
4. **Release (optional).** Deploy to Vercel or any free host and add the link. It is not required; your Loom is what matters.
5. **Rollback.** A few lines on how you would undo a bad release.

**Done when:** your latest commit has a green check, and someone else could run the dashboard from your README.

## Stage 7: Maintenance

1. **Open `maintenance/`.** Read Dana's message and load the new file.
2. **Reproduce the problem** and write a bug report: steps, expected, actual.
3. **Write a test** that fails because of the bug.
4. **Fix it,** and run the whole suite again.
5. **Watch it.** Note what you would monitor so the next format change is caught early, and look at your host's logs if you deployed.
6. **Plan what is next.** Add Dana's other request and two improvements of your own as next-round items.

**Done when:** `docs/07-maintenance.md` shows the bug, the failing test and the fix commit.

---

## Your Week

| Day | Do this |
|---|---|
| 1 | Read guides 1 and 2 and learn each stage with `teach-me`. Set up your copy (guide 3), fill in `CLAUDE.md`, draft `docs/ai-pipeline.md` (guide 4) |
| 2 | Stage 1 and Stage 2: discovery, requirements and planning |
| 3 | Stage 3 and the start of Stage 4: design and feedback in the morning, first visible slice by the end of the day |
| 4 | Finish Stage 4 with Stage 5 alongside it: build and test together, then UAT |
| 5 | Stages 6 and 7: deployment and maintenance. Finish `docs/ai-pipeline.md` and `docs/reflection.md`, record the Loom, submit (guide 6) |

Out of scope on purpose: logins and roles, a live Google Sheets connection (optional extra only), payments, paid services, and any work tracking tool.

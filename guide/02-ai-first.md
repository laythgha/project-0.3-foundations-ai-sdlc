# 2. The Same Lifecycle, AI-First

Now go through the same seven stages again, with AI. The stages and steps do not change. What changes is who does the first draft.

**The AI-first habit.** Before any step, ask three questions:

1. How can AI do this?
2. How do I set it up to do it well: what context, what instructions, what examples?
3. What must I check before I accept it?

**The rule that never changes:** AI does the work, you own the result. You make the decisions, you check every output, and you answer for it in your live review.

---

## Stage 1: Discovery and Requirements

| AI does | You do |
|---|---|
| Reads every source at once (transcript, emails, messages) and pulls out the problem, users, must-haves and qualities | Check each point against the source. Correct anything the AI invented or misunderstood |
| Profiles the spreadsheets: columns, formats, duplicates, missing values, names that do not match | Open the files yourself and confirm the problems are real |
| Spots where two sources disagree | Decide which source wins, or ask |
| Lists the gaps and questions you have not answered yet | Decide which questions matter, and go and get the answers |
| Drafts acceptance criteria for each must-have | Make each one testable. Cut anything vague |
| Suggests edge cases the user never mentioned | Choose what is in and out of scope |

**Tools:** a chat assistant (Claude or similar), and any transcription tool if you record the call.

**Watch out:** AI fills gaps with confident guesses. Anything that did not come from the user or from you is a question, not a requirement.

## Stage 2: Planning

| AI does | You do |
|---|---|
| Turns requirements into user stories and small tasks | Check every requirement is covered and nothing extra crept in |
| Suggests an order and points out dependencies | Choose the first visible slice |
| Gives rough time estimates | Adjust them to your own speed |

**Watch out:** AI likes big plans. Cut the plan until it fits your week.

## Stage 3: Design

| AI does | You do |
|---|---|
| Proposes two or three architecture options with their tradeoffs | Choose one and write down why |
| Drafts the data model and a diagram | Check every requirement has somewhere to live in the data |
| Suggests folder structures | Pick one you understand |
| Generates the screens in **Claude Design**, once planning is done | Direct it with your user flow, change what is wrong, and show it to a real person |

**Tools:** a chat assistant, Claude Design, and any diagram tool that renders inline (Mermaid is one option).

**Watch out:** do not open Claude Design before your requirements and plan are done. A pretty screen for the wrong problem is wasted work.

## Stage 4: Build

| AI does | You do |
|---|---|
| Reads `CLAUDE.md` so it knows your project, stack and rules | Write and keep `CLAUDE.md` current |
| Proposes a plan for each task before writing code | Approve or change the plan first |
| Writes the code for one task | Run it, read it, and ask the AI to explain anything you do not understand |
| Fixes what you point out | Add every repeated mistake to the Lessons section of `CLAUDE.md` |

**Tools:** a coding agent (Claude Code or equivalent) and Git.

**Choosing a model:** use a strong reasoning model for thinking work (requirements, design, hard bugs) and a faster model for everyday coding. Most tools let you switch.

**Watch out:** never keep code you cannot explain. Your reviewer will ask.

## Stage 5: Testing

| AI does | You do |
|---|---|
| Drafts a test plan from your acceptance criteria | Check every criterion is covered |
| Writes unit and integration tests | Run them, and read what they actually check |
| Writes Playwright UI tests for your main user flow | Watch one run in a real browser |
| Suggests edge cases and negative tests | Choose which ones matter for your users |
| Helps you read failures | Decide whether the bug is in the code or in the test |

**Prove your tests are real:** break your code on purpose, once, and show that a test fails. A test that never fails is not testing anything. AI-written tests often pass for the wrong reason.

**UAT is yours.** AI can write the checklist, but you use the app yourself, as the user, and mark each acceptance criterion pass or fail.

**Tools:** the test runner for your stack (for example Vitest or Jest for JavaScript, pytest for Python) and Playwright.

## Stage 6: Deployment

| AI does | You do |
|---|---|
| Writes `.env.example` and the run instructions | Check that no real secret is anywhere in the repository |
| Writes a GitHub Actions workflow that runs your tests | Push, and make sure the check goes green |
| Walks you through deploying, for example to Vercel (optional) | Check the live copy works |

**Watch out:** never paste a real password or key into an AI chat.

## Stage 7: Maintenance

| AI does | You do |
|---|---|
| Helps you read logs and error messages | Decide what is a real bug |
| Drafts the bug report | Reproduce the bug yourself |
| Writes a test that shows the bug, then the fix | Check the test fails before the fix and passes after |
| Groups feedback into a next-round list | Choose what goes next |

**Tools:** your coding agent with the `troubleshoot` skill.

---

## Across Every Stage

- **Spend tokens wisely.** A clear `CLAUDE.md` saves you repeating yourself. Start a fresh session for each new task so old chat does not fill the context. Ask for a plan before code. Give short, specific instructions with the file names. Use the lighter model for simple work. See [guide/04-ai-pipeline.md](04-ai-pipeline.md).
- **Get feedback fast.** Show something to a real person as early as possible: the design on Day 2, not the finished app on Day 5.
- **Show value early.** Your first visible slice should work by the end of the first build day, even if it is rough.
- **Keep a record.** Every stage document ends with "AI did / I decided". Two honest lines are enough.

# Success Criteria: Project 0, Foundations: AI-Driven SDLC

What "done" means and how you are scored. Check every box before you submit.

---

## 1. Definition of Done

Anything missing sends your submission back before a human sees it.

### Per stage

- [ ] **Discovery and Requirements:** the sheet audit covers all six files; every must-have has an acceptance criterion; every open question has an answer with its source, or a marked assumption; an out-of-scope list
- [ ] **Planning:** user stories, a task checklist with dependencies and time guesses, the first visible slice marked, and the risks named
- [ ] **Design:** an architecture diagram, a data model, the cleaning rules, the folder choice, the Claude Design link and feedback notes; at least two screenshots in `design/`
- [ ] **Build:** the dashboard shows real numbers from all six sheets, and shows which rows were skipped; `docs/04-build.md` records at least one real correction of the agent
- [ ] **Testing:** at least 3 unit tests, 1 integration test, 2 Playwright tests and 3 edge cases, all passing with one command; the test plan, the proof the tests are real, the regression run and a complete UAT table
- [ ] **Deployment:** `.env.example` exists; a GitHub Actions workflow runs the tests and is green on the scored commit; run instructions at the bottom of `README.md`; a rollback note
- [ ] **Maintenance:** the week 41 file loads correctly; `docs/07-maintenance.md` has the bug report, the failing test, the fix commit and the next-round list
- [ ] Every stage document has its "AI Did / I Decided" section filled in

### Project level

- [ ] `CLAUDE.md` filled in with your own content, and changed at least once after Day 1
- [ ] `docs/ai-pipeline.md` has all five parts, including a diagram of all seven stages and the token use log
- [ ] `docs/reflection.md`, `LEARNING_LOG.md` (at least five entries) and `SUBMISSION.md` complete
- [ ] A Loom of 8 minutes or less, covering all seven stages and showing your tests running
- [ ] Small commits spread across at least four of your five days
- [ ] No secrets and no real personal data anywhere

A live link is optional and never counts against you if it is missing.

---

## 2. How You Are Scored

Scoring uses the same Rubric v5 that scored your interview: a whole number from 1 to 5 per category.

1. **AI check.** Confirms everything above is present and every link works, then drafts a score for each category with quoted evidence from your files.
2. **Human review.** A reviewer watches your Loom, runs your tests, reads your stage documents and AI pipeline, checks the AI draft, and runs the live review. **The reviewer's score is final.**
3. **Result.**

| Result | Meaning | Next |
|---|---|---|
| **Pass** | Categories 2 and 6 each meet the target in your training plan | Your rubric profile updates; next project |
| **Variant** | A main category is below target but closable | Variant 0.1: same structure, a fresh client |
| **Not yet** | The gaps are not closing | An honest conversation about next steps |

If you were assigned this project outside a training plan, the target is **3** on each main category. This is a foundations project; a 3 here is a solid result.

---

## 3. What Strong Looks Like

| Category | A 2 | A 3 | A 4 |
|---|---|---|---|
| **2 SDLC and Engineering Practices** | Stages done, but the documents restate the guide; tests are thin or only happy paths | Every stage done with real content; acceptance criteria are testable; all test types present and passing; UAT honestly recorded | Requirements clearly shape the tests; the bug fix follows test-first; small, clear commits tell the story of the week |
| **6 AI Tooling and Workflow** | Uses AI but mostly accepts its first answer; pipeline is generic | Pipeline matches what the repository shows; at least one real correction; `CLAUDE.md` grows; token habits named | Clear human checkpoints at every stage; tight context; a real before-and-after token comparison; can explain every line kept |
| **1 Core Programming** | Cannot explain parts of the code | Explains the main flow and the tests | Explains any part the reviewer picks, and why it is written that way |
| **5 System Design** | Architecture and data model are copied from AI without thought | A simple, fitting design with a reason for each choice | Names the option not chosen and why; the data model covers every requirement |
| **10 Independent Operation** | Needed heavy prompting to finish; missed obvious data problems | Finished on time, raised blockers early; found most of the data problems and the gaps in what the client said | Found problems and contradictions across the sources that the client never mentioned, and resolved them sensibly |

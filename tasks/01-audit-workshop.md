# Workshop: Auditing the Folder

**Goal.** A workshop page that teaches students to bring their project folder and their
Claude agent back into line once the folder has grown. Mid-semester, when CLAUDE.md, the
design system, `tasks/` and the site itself have drifted apart.

## Why now
By mid-semester each student's `username.github.io` folder holds weeks of work: a CLAUDE.md
written in Week 2 and patched since, a design system from Week 4, a skill from Week 6, project
pages, finished and abandoned tasks. Rules get stated twice and disagree. Claude follows a line
the student no longer means. The fix is an audit: read what the agent reads, and make it say
what the student means today.

## Placement
- Week 8, the first session of Part II, before students start their project folder (D7). The
  audit leaves the site clean, and the project folder starts from the habits it teaches.
- Add it to the syllabus Week 8 row, and to the nav on every page as `04`. Workshops page
  numbers follow the order they are taught: WS03 Reading a Script (Week 9) would become
  WS04 and this one WS03, so check the order and renumber nav, header chips and the
  schedule links together.

## Source material
- Agents in Practice talk, Part 3 "Context through folder structure":
  `zihaoooo/zihao-site`, `talks/agents-in-practice/index.html` (slides "Two kinds of memory",
  "The project's standards manual", "Names are context", "Single source of truth").
- Its Try-Context guide, step **C3 "Ask for an Audit"**, which has the audit prompt:
  `talks/agents-in-practice/try-context/index.html`. Adapt the prompt for CLAUDE.md and
  Claude desktop.
- Workshop 02 (`workshops/folders-and-claude.html`): the folder, CLAUDE.md and `tasks/`
  conventions students already use.

## Shape (a starting point, open to change)
1. **Ask Claude what it thinks the project is.** Fresh session: "What is this project, how is
   it organized, and what rules do you follow?" Compare the answer with what you mean today.
   Write down every mismatch.
2. **Read CLAUDE.md yourself.** Mark lines that are stale, repeated, or rules you no longer
   follow.
3. **Run the audit.** Claude audits CLAUDE.md and the design system: cut what it can learn
   from the files, one home for each fact, rules phrased as what to do, stale facts flagged,
   changes listed with nothing applied until approved.
4. **Review the cuts.** The cut that removes a rule you rely on is the one to catch.
5. **Clean `tasks/`.** Close or delete abandoned tasks; finished ones live in `tasks/done/`.
6. **Check again.** New session, same question as step 1. The answers should now match.
7. **Hand it in.** Tag the commit; the tag name follows the milestone it belongs to.

## Conventions to follow
- Read CLAUDE.md "Workshop page rules" first. Build from `workshops/folders-and-claude.html`
  as the template: spec strip with a green Outcome chip last, objectives, assignment,
  copy-ready code blocks, `ws-predict` boxes for checks.
- Students work in Claude desktop. Keep the terminal out.
- Copy is short and says what things are.

## Open questions for Zihao
- Is this a graded milestone of its own, or folded into D7?
- Week 8, or earlier (Week 6 or 7, before the midterm pin-up)?

## Done when
The page is live, linked from the syllabus and the nav on every page, CLAUDE.md's Workshops
section describes it, and this file has moved to `tasks/done/`.

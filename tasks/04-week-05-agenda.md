# Week 05 agenda: Design and Build

**Goal.** Fill out `workshops/design-and-build.html`, now a stub, as the Week 05 agenda: each part of the class
under a `LECTURE`, `WORKSHOP` or `DISCUSSION` divider (rules in `CLAUDE.md`, "Workshop page rules").

## From the syllabus (`index.html`, Week 05 row)
- Topic: Project pages from tasks, split between agents: a main session that writes the tasks and reviews design, a Sonnet session that writes the code; local preview; images for the web; domains and DNS (optional); desk crits
- Due: two project pages, built from tasks, tagged `week-05`.
- No lecture this week.

## Working with two agents (the core of the week)
Students first meet multiple agents here, in the first half of the semester, on work they already know.
- **Main session (Opus) is the lead.** The student tells it the two project pages they need. It splits them
  into tasks in `tasks/`, one page or one part per file, each specific enough to hand off.
- **A Sonnet session writes the code.** Started fresh, it reads CLAUDE.md and one task, builds it, pushes.
- **The main session reviews.** It checks the result against the design system from Week 04, with color,
  type and layout as its main job, and writes what to fix back into the task. Sonnet fixes; repeat.
- **Side chat → main.** A side question (an image size, a CSS detail) goes to a side chat, so the
  main session's context stays on the design. Send the answer back to main when it matters.
- **Fork.** When two directions for a page are both plausible, fork the session and compare.
- Desktop app only: confirm each move (side chat, fork, model choice per session) exists in the
  Code tab before writing the step. Students do not use the terminal.
- Learning objective that transfers: separating who decides from who builds, and reviewing against a
  written standard.

## To write
- Replace the "To come" part with the week's parts, in class order.
- Spec strip (Tool, Bring), Learning Objectives, Ongoing and Feeds forward.
- Steps with copy-ready prompts where students work with Claude; the last step tags `week-05`.

## Done when
- No "To come" part left; the assignment sentence matches the syllabus Week 05 milestone.
- Move this file to `tasks/done/`.

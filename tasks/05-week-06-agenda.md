# Week 06 agenda: Skills and Cloud Sessions

**Goal.** Fill out `workshops/skills.html`, now a stub, as the Week 06 agenda: each part of the class
under a `LECTURE`, `WORKSHOP` or `DISCUSSION` divider (rules in `CLAUDE.md`, "Workshop page rules").

## From the syllabus (`index.html`, Week 06 row)
- Topic: Said it three times: turn a repeated instruction into a skill the agent runs on its own; cloud sessions, started from the Claude app or the web, that work on your GitHub repository while your laptop is closed; branches; how a software team uses pull requests, review and approval, and which of those steps a solo developer can skip; comparing a branch with main and deciding when to merge
- Due: one skill + a third project published through it, built in a cloud session on a branch, compared with main and merged, tagged `week-06`.
- No lecture this week.

## Content, in class order
1. **Skills.** Said it three times: make it a skill. The image standard is the worked example.
2. **Cloud sessions.** A session that runs on GitHub's copy of the repository, in the cloud, started from the
   Claude app or claude.ai/code. It keeps working with the laptop closed; you check in from your phone.
   Several can run at once, each on its own branch. Show a live one (this course site is maintained this way).
   Remote control (a session on your laptop driven from the phone) is the contrast: same idea, your machine.
3. **Branches.** `main` is what is live. A branch is a copy to work on without touching it. A cloud session
   works on its own branch by default.
4. **How a team ships.** Branch, then a pull request, then review and approval by someone else, then CI checks,
   then merge to main. Each step exists because several people touch the same code.
5. **What a solo developer can skip.** Approval by a second person and most of the ceremony. Keep: work on a
   branch, read the diff, merge. The main session (or you) is the reviewer. A tiny fix can go straight to
   main; this repo's own CLAUDE.md says "push straight to main" for exactly this reason.
6. **Compare and merge.** Compare the branch with main on GitHub (the Files changed view), read what changed,
   preview it, then merge. Merge when it works and you would be fine with it live; otherwise ask for fixes
   on the branch.
- Desktop app and web only, no terminal. Confirm each step in the current Claude app and claude.ai/code UI.
- Learning objective that transfers: work happens on a copy, and someone reads the difference before it goes live.

## To write
- Replace the "To come" part with the week's parts, in class order.
- Spec strip (Tool, Bring), Learning Objectives, Ongoing and Feeds forward.
- Steps with copy-ready prompts where students work with Claude; the last step tags `week-06`.

## Done when
- No "To come" part left; the assignment sentence matches the syllabus Week 06 milestone.
- Move this file to `tasks/done/`.

# Week page spec

Read this before building or editing a page in `workshops/`. These pages are the weekly agenda
(nav section "Weeks"), one per week through Week 07, HTML only.

## Structure
- Layout is `<div class="wf-wrap wf-doc">`, with `wf-progress.js` after `nav.js`.
- Header chip `WEEK NN`. Spec strip: first chip is Length ("One class"); last is a green Outcome
  chip, `.wf-spec-item.wf-spec-outcome`, the week's outcome in one short phrase (colors `--done*`
  in `tokens.css`). A Due chip is the one date a page may repeat; add it once the calendar is set.
- `.wf-objectives` sits between the spec strip and the assignment: one to three short `<li>`
  phrases, each naming the idea that transfers beyond the software.
- `.wf-outcome`: one `<strong>Assignment</strong>` label and one product-framed sentence with the
  format folded in. Scope its CSS as `.wf-outcome > strong`.
- `.wf-ongoing` (optional), directly under the assignment: the semester-long deliverable this feeds.
- Each part of the class gets a `.wf-session` divider whose num is its kind (`LECTURE`, `WORKSHOP`,
  `DISCUSSION`) and whose label is its title. A lecture part is a `wf-nocheck` card linking the deck.
- Every step has a `.wf-step-head`, which gives it a done check; a `.wf-step` without one is a
  session divider. The last step tags `week-NN`.
- A week not yet built is a stub with an `AGENDA` / "To come" part; its content waits in
  `weeks/week-NN.md`.

## Media
- Walkthrough video: a `.wf-step wf-full wf-nocheck` card under its Session label, `▶` as the step
  number, YouTube iframe in `.wf-video` (16:9; set `aspect-ratio` inline otherwise). `wf-nocheck`
  keeps saved checks in position.
- Example images: a collapsible `<details class="wf-examples">` "Hint" card with the click-to-enlarge
  lightbox. PNG for flat UI screenshots, JPG where it is smaller at the same quality; encode with ffmpeg.

## Copy
Short and imperative. Each sentence says what a thing is and what to do with it.

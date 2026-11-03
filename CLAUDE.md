# Agentic Design Workflows — course site

Repo in the `landscape-courses` org. Served by GitHub Pages at
`https://landscape-courses.github.io/agentic-design-workflows/` from `main` / root (`.nojekyll`).
Hand-authored static HTML, no build step. Keep it that way.

## Working rules (all Claude sessions)
- **Push straight to `main`.** No PR or review step needed; the repo has a sole owner.
- **Every internal path starts with `/agentic-design-workflows/`** (the Pages subpath). A bare `/assets/...`
  breaks on Pages. If a custom domain is added later, sed the prefix away in one pass.
- **Self-contained.** CSS, JS, deck system and images all live in this repo. Do not link assets
  from zihaozhang.cc or other course repos; copy them in.
- Links to Zihao's talks (`https://zihaozhang.cc/talks/...`) are external references, which is fine.
- Shared chrome (head, side-panel nav) is duplicated per page by design. Propagate nav edits with sed.
- Images: AVIF, long edge ≤1920. Declare `width`/`height` on every `<img>`, `loading="lazy"` below the fold.
- Find-and-replace across HTML: sed via Bash, not PowerShell (it double-encodes UTF-8).
- Nothing private here: the repo is public. Grades, rubrics with student names, student work stay out.

## Layout
- `index.html` — syllabus. `lectures/` — deck pages. `workshops/` — step-by-step lab pages.
- `assets/deck/` — slide-deck system; `deck-spec.md` is its spec. Read it before touching a deck.
- `assets/css/` — `tokens.css` (every font and color as a variable; write `var(--…)`, never a hex),
  `main.css`, `workflow-shared.css`, `footer.css`. `assets/js/` — `nav.js`, `wf-progress.js`.
- `assets/img/<lecture-slug>/` — lecture images.

## Deck rules (from zihao-site)
- Read `assets/deck/deck-spec.md` before touching a deck; it defines the layouts (`single`, `auto`,
  `hero-l/r`, `sq`, `points-l/r`, `toc`, `txt-card`/`stmt`/`cmp`) and the phone scroll view.
- Lectures are standalone: no week numbers in nav, `<title>`, header chip (`LECTURE`), deck title,
  title-slide stamp, slide text or notes. Refer to another lecture by its title.
- URL is `lectures/<slug>.html`, images in `assets/img/<slug>/`.
- Never put `*/` inside a CSS comment: it closes the comment and silently drops every rule after it.

## Workshop page rules (from zihao-site WF conventions)
- Layout: `<div class="wf-wrap wf-doc">` plus `wf-progress.js` after `nav.js`. Every step needs a
  `.wf-step-head` to get a done check; a `.wf-step` without one is a session divider.
- Weeks and dates live only in `index.html`. First spec chip is Length ("2 sessions"); parts are
  labeled Session 1, Session 2. A Due chip is the one date a page may repeat; omit it until the
  Spring 2027 calendar is set.
- `.wf-objectives`: between spec strip and assignment, one to three short `<li>` phrases, each
  naming the idea that transfers beyond the software.
- `.wf-outcome`: one `<strong>Assignment</strong>` label, one sentence, product-framed, format
  folded in. No separate Deliverable section. Scope CSS as `.wf-outcome > strong`, so `<strong>`
  inside `.wf-tips` is untouched.
- `.wf-ongoing` (optional), directly under the assignment: the semester-long deliverable this feeds.
- Walkthrough video: a `.wf-step wf-full wf-nocheck` card under its Session label, `▶` as the step
  number, YouTube iframe in `.wf-video` (16:9 default; set `aspect-ratio` inline otherwise).
  `wf-nocheck` keeps saved checks in position.
- Example images: collapsible `<details class="wf-examples">` "Hint" card plus click-to-enlarge
  lightbox. PNG for flat UI screenshots; JPG only when it actually wins. ffmpeg only.
- Pages are HTML only; no markdown sources.
- Copy: short, imperative, no AI-sounding parallel structures. Say what a thing is, not what it
  is not: no "no X, no Y" lists, no "not A, but B" framing.

## Origin
Migrated Nov 2026 from `zihaoooo/zihao-site` `teaching/arch51580/`. The notes below are that
folder's teaching context, kept as written. Where they mention `../laar61400/`, the factory
(`course-prep`), or `/teaching/laar61400/assets/img/`, read: those live outside this repo now;
the images are copied into `assets/img/`, and this repo is the source of truth.

---


Elective, Spring 2027. Dual-listed Arch 51580 / 61580, Topics in Computational Studies; the folder
takes the lower number. Factory output of `../../../course-prep/arch51580/`; same authoring rules as
laar61400 (see `../laar61400/CLAUDE.md`, "Factory output") — **the live page is the source of truth**,
and fixing output here is the canonical fix.

**Unlisted.** No card in `teaching/index.html` yet — the pages are live at their URLs and shareable
by link while the syllabus is tentative. Add the card when the course is confirmed in the catalog.

Styles, nav script and the whole `assets/` tree are borrowed from laar61400 by absolute path, the way
laar64150 does it. This folder has no `assets/` of its own and needs none.

## Dates are deliberately absent
Meeting day, time and room are "to be set against the Spring 2027 calendar" in `index.html`, and the
Weekly Schedule carries week numbers with no dates. The calendar is not published yet; fill these in
once it is, in `index.html` only.

## Lectures (`lectures/`)
Topic-named, no week prefixes, same as laar61400 and laar64150.

- `coding-101.html` (lecture) was **deleted Nov 2026**; it did not work in the room. Its five moves,
  error-reading and GH_ScriptInstance points were folded into the workshop of the same name.
  Coding 101 is now workshop-only.

- Four decks are **copies of laar61400's**, written by
  `../../../course-prep/scripts/arch51580_reuse_lectures.py`:
  `computational-thinking.html` · `web-coding-literacy.html` · `cybernetics-and-design.html` ·
  `graphic-design-101.html`.
  - Copied rather than linked so each page carries **this** course's side panel. A link would have
    dropped students into LAAR 61400's nav.
  - **Images are not copied.** Every `<img>` points at `/teaching/laar61400/assets/img/<slug>/`, so
    both courses share one asset pool. Keep it that way: an image edit in laar61400 is meant to show
    up here.
  - **The copies may diverge**, and are expected to: the elective goes further on agents and context
    than the required course compresses into one deck. Re-running the script **overwrites** them, so
    once a copy has elective-specific edits, either stop re-running it for that slug or re-apply the
    edits after. The script rewrites nav, `<title>`, the title-slide stamp, relative image paths and
    the deck id; it changes no slide content.
  - **`computational-thinking.html` has diverged:** its last two slides (the 4D framework, and the
    share session's weekly lens) are Arch 51580 only. Re-running the reuse script drops them; re-apply after.
  - Deck ids are `a51-NN`, not laar61400's `wNN` — deck.js keys the speaker-notes passphrase in
    localStorage (`deck-notes-pass-<id>`) and the Presenter View BroadcastChannel off the id, so a
    shared id would make the two courses' decks talk over each other.

## Workshops (`workshops/`)
`.wf-doc` layout + `wf-progress.js`, same conventions as laar61400's `workflows/` (see its CLAUDE.md,
"WF page conventions"). Named `workshops/` here because that is what the syllabus calls them.
Rhino 8 and Grasshopper are course requirements from Week 9; the software cards for them in
`index.html` are copied verbatim from laar61400's logistics grid.

- Students use the **Claude desktop app**, not the terminal. Keep terminal steps out of workshops.
- `github-setup.html` (WS01, "Your First Repository") — Week 1. GitHub account, Claude Code once in a
  terminal (the only terminal use), then Claude desktop's Code tab installs Git and makes and pushes `arch51580-site`, then tags it `ws01`. Sets the submission
  rule: every milestone is a Git tag (`D1`…`D10`) on the student's public repo; the tagged commit
  is the submission. Resubmit = new suffixed tag (`D3-r1`), never a moved tag; push time is the timestamp. Stated once in `index.html` Assignments ("Submission").
- `folders-and-claude.html` (WS02, "Folders and Claude") — Week 2, adapted from the Agents in
  Practice talk's "context through folder structure" part and its Try-Context guide. `_source/` →
  CLAUDE.md by interview → `tasks/` → a fresh session does the task → push → GitHub Pages turned on
  by hand in Settings → tag `D1`. Every student has a live bio page by the end of Week 2. The
  `tasks/` folder replaces the old BUILDSPEC milestones for both the site and the Part II project.
- `coding-101.html` (WS03, "Reading a Script") — Week 9, mid-semester, **six steps
  in Grasshopper**: an input is a variable → a loop over a List-access input → choose, and the 8.33
  trap → write the spec → read what came back → check before you bake. Header chip is `WS03`.
  Carries no dates; the one deliverable is named in the `.wf-outcome` box.
  - The intro lists the **five moves**; `index.html`'s Week 9 row names them too. Keep both in sync.
  - **Every code block is copy-paste ready**, because students copy from the page rather than
    retype. The `<pre>` holds exactly what lands on the clipboard: no line numbers, no decoration.
    `.ws-copy` buttons are added by an inline script at the end of the page (Clipboard API with an
    `execCommand` fallback). This is the site's first copy-button; promote it to
    `workflow-shared.css` if a second page needs one.
  - All Python shown has been run; the numbers quoted on the page (`8.333333333333332`,
    `20.833333333333336`, `steep: 2 of 3`) are its real output. Re-run before changing any of them.
  - The RhinoCommon slope script on lecture slide 15 is **framed as agent output to be read**, not
    as a reference solution, and has not been run inside Rhino.

## Nav
Three sections — Lectures, Workshops, Reference — identical in all pages and inline in each, as
everywhere on this site. `ARCH_NAV` in `arch51580_reuse_lectures.py` is the copy the script injects;
after a nav edit, re-run the script for the four copies and sed the two hand-authored pages
(`index.html`, `workshops/coding-101.html`).

## Syllabus (`index.html`)
Same `syllabus-section` / `schedule-table` / `grade-breakdown` classes as laar61400's, so
`course-prep/scripts/syllabus_to_docx.py` can be pointed at it when a school-submission PDF is
needed (it is not wired up for this course yet — `COURSE` in that script is laar61400).

- The **Weekly Schedule is two tables**, Part I (Weeks 1–7) and Part II (Weeks 8–14), with a
  `.syllabus-body` label between them.
- `_course/proposal.md` in the factory is the **frozen record of what was submitted** (Sep 2026).
  This page is the source of truth for the schedule going forward; the two have diverged on purpose
  and are not to be hand-synced. The divergence (Nov 2026 rework): Week 2 is Folders and Claude with the site live, the workflow audit
  moved into D6, BUILDSPEC milestones became tasks folders, and Reading a Script moved to Week 9. Earlier: Coding 101 was added as Week 2, pushing web coding
  to Week 3 (where Graphic Design 101 joins it) and context to Week 4. Every milestone D1–D6
  kept its proposed week. The Guest Lectures section was removed Nov 2026 (not confirmed).
- **Boilerplate re-synced to laar61400 verbatim (Nov 2026)**, incl. its Public Safety block and site footer,
  which this copy had lost. Only the grade-breakdown weights and the two substitutions below differ.
- **All policy prose is laar61400's, verbatim** — attendance, academic integrity, incompletes,
  civility, electronic devices, grading criteria, the grade scale and its footnote, support
  resources, Support of Program Mission, and the Agentic AI — Course Stance block. Do not write new
  policy language for this course: copy it from `../laar61400/index.html`, which is the source.
  Two factual substitutions only, both marked in the git history:
  - Attendance's first sentence, because the Spring 2027 meeting day, time and room are not set.
  - Support of Program Mission's first sentence, because this is an elective in Topics in
    Computational Studies open across the school's programs, not part of the LA course sequence.
    Every mission sentence after it is laar61400's, word for word.
- The grade scale is laar61400's graduate scale and carries no D grades, while this course is open
  to 4th/5th-year BArch students. Flagged, deliberately left as laar61400 has it.
- **Coding-agent subscription is a department requirement**, stated flatly in Course Logistics: an
  active paid plan for the semester, no hardship carve-out.

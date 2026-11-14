# Agentic Design Workflows

Arch 51580 / 61580, Topics in Computational Studies, an elective taught by Zihao Zhang. Agents are
the subject and the student's website is the by-product. Part I (Weeks 1–7) teaches one way of
working with an agent each week. Part II (Weeks 8–14) is one page, `workshops/build-your-tool.html`:
students build their own tool, class is desk crits, and the page carries a live log. Students use
the Claude desktop app, so workshop steps stay inside it.

Public repo in the `landscape-courses` org, served by GitHub Pages from `main` at
`https://landscape-courses.github.io/agentic-design-workflows/`. Hand-authored static HTML.

**Semester:** Spring 2027. First class: date pending the college calendar; write it here once set.
Before that date the course is in pre-semester prep; from it, count the teaching week from today's date.

## How prep works
The instructor prepares by talking, often from a phone on the way to work. State lives in `weeks/`
so every session starts from the files.

- `weeks/00-course.md` holds the whole course: frame, schedule, assignments, grading.
  `weeks/week-NN.md` holds one week, created when that week is first discussed. A week with no
  file has nothing pending and its page is the record. Each has three sections: **Open** (raised, awaiting a
  decision), **Decided** (conclusions), **To build** (decided, and the page has yet to show it).
- Pre-semester, talk defaults to `00-course.md` and the syllabus is free to change. In semester,
  talk defaults to the coming week's file, "this week" and "next week" resolve from the first-class
  date, and a change to the syllabus is raised on its own for a yes.

**Discuss (议)** is the default for any message about course content.
- Read the week file first. A passing thought goes into Open with its date, answered in one line.
- Each decision is restated in one sentence, written to Decided, committed and pushed at once, so
  the session can end at any moment with everything settled already saved.
- Replies fit a phone: one question at a time, a few lines, numbered options.
- Discuss edits `weeks/` only. Close by naming what sits in To build.
- Student names, grades and classroom observations about individuals belong in the gitignored
  `_prep/`, on the desktop.

**Build (建)** starts when the instructor says build, in a fresh session.
- Read the week file's Decided and To build, plus `workshops/SPEC.md` for a week page or
  `assets/deck/deck-spec.md` for a deck. Make the page, push, reply with its live URL, then clear
  from the file what the page now shows; delete the file once it is empty.
- A request such as "add X to this week" in Part II is a new `<li>` at the top of the live log in
  `build-your-tool.html` (marked by a `LIVE LOG` comment), pushed.

`tasks/` holds work orders that belong to no week.

## Repo rules
- Push straight to `main`; the repo has a sole owner.
- Every internal path starts with `/agentic-design-workflows/`, the Pages subpath.
- The repo is self-contained: CSS, JS, deck system and images are copied in. Links to
  `https://zihaozhang.cc/talks/...` are external references.
- Head and side-panel nav are inline in every page, so a nav edit goes to all pages in one pass.
  The nav has three sections: Lectures, Weeks (01–07, then one `08–14` entry), Reference.
- Run find-and-replace across HTML with sed in Bash; PowerShell double-encodes UTF-8.
- Colors and fonts are variables in `assets/css/tokens.css`; pages write `var(--…)`.
- Images: AVIF, long edge ≤1920, `width`/`height` on every `<img>`, `loading="lazy"` below the fold,
  in `assets/img/<lecture-slug>/`.
- Dates live in `index.html` only. Weeks are the one label scheme: chip `WEEK NN`, nav number,
  git tag `week-NN`.
- Lectures are standalone and topic-named (`lectures/<slug>.html`), free of week numbers; refer to
  another lecture by its title. Deck ids are `a51-NN`, since deck.js keys notes and Presenter View
  off the id.

## Syllabus (`index.html`)
- All policy prose is LAAR 61400's, verbatim, copied from `zihao-site/teaching/laar61400/index.html`.
  Two sentences differ for fact: Attendance's first (meeting pattern) and Support of Program
  Mission's first (an elective open across programs).
- The Weekly Schedule is two tables, Part I and Part II. Every week is a graded milestone: the
  commit tagged `week-NN` is the submission; Weeks 7 and 14 are graded on criteria, the rest
  complete / incomplete.
- `_prep/proposal.md` is the frozen record of the Sep 2026 submission; this page is the schedule's
  source of truth.

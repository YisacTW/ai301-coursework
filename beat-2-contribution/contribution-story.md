# Contribution: Add local tables of contents to CTSM documentation

Path: `beat-2-contribution/contribution-story.md`

This file is Assignment 5, and it is graded at the path above; a copy kept anywhere else in
the repository is not read. **Keep every section header below under its exact name** — the
format criteria grade exactly that. Your course repo link is the whole submission: no tool
files and no evidence uploads are part of Assignment 5.

**Contribution Number:** [1]
**Student:** Isaac Tsegaye Wanna
**GitHub Username:** YisacTW
**Issue:** https://github.com/ESCOMP/CTSM/issues/3152
**Pull Request:** https://github.com/ESCOMP/CTSM/pull/4295

One repository, built across units 5 to 8, telling the whole story of your real
contribution. Fill it as you work, not at the end — the sections below ask for evidence that
is far easier to write down as it happens than to reconstruct in the last weekend.

Contribution Number stays `[1]` unless you make more than one contribution this term; it
just numbers them.

---

## Toolkit

Every story section below, from Why I Chose This Issue through Pull
Request, ends with a Toolkit block: which tool did that phase's work
and how you used it, what it produced, what difficulties or
shortcomings it presented, and what you changed or would change
because of them. Together the blocks are the thread the rubric's
Toolkit points read, and they are the raw material for your unit-9
portfolio, so keep them current as you work rather than
reconstructing them later.

A Toolkit block looks like this (copy it into each story section and
fill it there):

```text
**Toolkit**

- Tool: [which tool did this phase's work, and how you used it]
- What it produced: [described in a sentence or a short excerpt]
- Difficulties: [what fought you or fell short, or "none met"]
- What changed: [the patch, revision, or workaround, what you would
  update, or "nothing"]
```

This section also keeps one short dated entry per week of tool work,
starting below: what you built or changed that week, what broke, and
what you changed because of it. The blocks tell the story where it
happened; these entries are the toolkit's own timeline.

All four entries are graded. Keep every heading below, and fill each
one in the week it belongs to.

**Unit 5: Built an issue scout for small Python bugs and documentation work**

I installed the issue-scout over my earlier issue-selection tool, kept my existing rubric, and wrote searches based on the kind of Python work I can realistically finish in focused sessions. My first scan surfaced a few recent feature requests that did not match that goal, so I updated the ranking rules to keep only bug and documentation-labelled results before grading the top five. The revised scan produced two plausible examples and showed that missing contribution-policy evidence should stay a required blocker instead of something the tool assumes away.

**Unit 6: Installed the voice guard and updated the scout's scope check**

I added the voice guard and consolidated the rules it checks for claim comments, questions, and follow-ups. I also replaced the scout's old preferred scope check with a required feasibility floor and a separate difficulty note, since a real issue can involve more than one file without being too broad to start. The first manual guard check exposed an expired local login. After signing back in, I reran the guard, checked the live CTSM issue for an assignee and parallel work, and posted my claim: https://github.com/ESCOMP/CTSM/issues/3152#issuecomment-6598937960.

**Unit 7: Installed the ship-gate and checked the CTSM documentation branch**

I installed the ship-gate and wrote a local manifest for the CTSM documentation change. The first gate run stopped because I had not committed the two documentation edits yet, which was useful: the gate checks the branch diff rather than unstaged work. After committing, it also found a Windows-specific CLI lookup problem. I corrected that local lookup, reran the gate, and it accepted the two-file branch, the recorded Sphinx output, and the PR draft's honest environment note.

**Unit 8: Installed the PR monitor and wrote a response playbook**

I installed the PR monitor and wrote a short playbook for review replies, follow-up timing, and when to step away from a contribution. Pull request #4295 is now open and waiting for its first maintainer review. The monitor's local prerequisite, GitHub CLI, is not available on this computer; its installer did not finish, so I did not claim a monitor run that could not occur. I checked the live PR directly instead and recorded its current state. When the CLI is available, the next step is one monitor run against this branch, followed by a decision based on the playbook rather than an automatic nudge.

---

## Why I Chose This Issue

My original scan and live checks surfaced several documentation issues that looked small on a course list but were no longer available when I opened their GitHub threads. One OpenAlgo issue already had an open linked pull request, and another candidate had a closed linked attempt. I stopped before claiming either one instead of competing with existing work.

I chose CTSM issue #3152 because its live thread was open, unassigned, and had no linked pull request or prior discussion when I checked it. The request is narrow: add local navigation only where it is useful. I limited the first patch to two long User Guide pages that already have multiple major headings and used the repository's existing reStructuredText pattern rather than inventing a new layout. It is a manageable way to learn a documentation build and the review expectations of a scientific software project.

The scout was useful for finding candidates, but it did not treat linked pull requests as a strong enough availability signal. I patched my process by checking the live issue timeline, assignee field, and linked work immediately before claiming. My claim is public here: https://github.com/ESCOMP/CTSM/issues/3152#issuecomment-6598937960.

**Toolkit**

- Tool: issue-scout (your scout: your search strategy, your rubric),
  and how I used it
- What it produced: a ranked set of small documentation candidates and a feasibility check for the CTSM issue
- Difficulties: the scan did not reliably expose linked pull requests on the initial candidate list
- What changed: I added a live issue-thread and linked-work check before making a claim

---

## Understanding the Issue

**Problem Description**

Some long CTSM User Guide pages have several major sections but no local table of contents. A reader looking for one configuration or namelist topic has to scroll through the full page.

**Expected Behavior**

Long pages that benefit from in-page navigation should show a short local table of contents linking to their main sections.

**Current Behavior**

The two selected pages render their headings but have no local navigation block near the introduction.

**Affected Components**

The change is limited to the reStructuredText source for the CLM configuration and CLM namelist customization pages under `doc/source/users_guide/setting-up-and-running-a-case/`.

**Toolkit**

- Tool: issue-scout and a direct review of the issue and existing documentation style
- What it produced: a narrow documentation scope and a matching local-navigation pattern in `tips-for-working-with-rst.rst`
- Difficulties: the issue asks generally for pages that would benefit, so the boundary had to be kept concrete
- What changed: I selected two long pages with multiple major headings instead of broadening the patch to the whole guide

---

## Reproduction Process

**Environment Setup**

I worked from a Windows checkout of the CTSM repository on the `docs/add-local-tables-of-contents` branch. I initialized the documentation builder submodule, created a local Python virtual environment, and installed Sphinx and the documentation theme needed to render the pages. The repository wrapper `doc/build_docs` expects GNU Make, which was not installed in this environment, so I recorded that limitation and used the direct Sphinx command for the affected documentation pages.

**Steps to Reproduce**

1. Open the two source pages named above on the base branch.
2. Confirm that neither page contains a `.. contents::` directive even though each has several major headings.
3. Build the documentation or inspect the rendered base pages; the pages show headings but no local contents navigation block.

**Reproduction Evidence**

- **Commit showing the fix:** https://github.com/YisacTW/CTSM/commit/8aaa32d
- **Rendered evidence:** both changed HTML pages contain `<nav class="contents local" id="contents">` after the direct Sphinx render.
- **My findings:** the existing project documentation already uses a local `.. contents::` pattern, so the smallest defensible fix was to reuse that pattern on two clearly long pages.

**Toolkit**

- Tool: repro-check and a direct source-and-render comparison
- What it produced: the before condition (no local contents directive) and an observable after condition in the generated HTML
- Difficulties: the full wrapper requires GNU Make, and the broad Sphinx pass reports unrelated include-path errors
- What changed: I used direct Sphinx output for the two affected pages and documented the broader-build limitation instead of claiming a clean full build

---

## Solution Approach

**Analysis**

The missing navigation is not a code defect. The two documentation source files simply omit the Sphinx `contents` directive already used elsewhere in the CTSM documentation. The appropriate scope is therefore source-level documentation markup only.

**Proposed Solution**

Add a local `contents` directive after the introductory text in each selected page. Use depth one and backlinks to the top so readers can jump to major sections without turning the navigation into a long index. I am not reorganizing headings, rewriting prose, changing generated files, or touching model code.

**Implementation Plan**

1. Add the existing local `contents` pattern to `customizing-the-clm-configuration.rst`.
2. Add the same depth-one local pattern to `customizing-the-clm-namelist.rst`.
3. Render the documentation, inspect both output pages, and check the final diff.

No implementation deviation was needed. The validation method changed only because GNU Make is unavailable locally; that limitation is recorded in the testing evidence and PR draft.

**Toolkit**

- Tool: plan-check and the local plan document
- What it produced: a two-file, documentation-only scope with explicit non-goals and an observable verification plan
- Difficulties: the issue wording is broader than any single small patch
- What changed: I documented the two-page boundary and used `Refs #3152` rather than claiming the entire issue is fixed

---

## Testing Strategy

The before condition is that the base versions of both source files do not contain `.. contents::`. The after condition is visible in the rendered output: each generated target page contains `<nav class="contents local" id="contents">`.

I ran `git diff --check`, which completed without whitespace errors. I also rendered the documentation with:

```powershell
.\.venv-docs\Scripts\sphinx-build.exe -q -b html -c doc\doc-builder doc\source ctsm-doc-build-final
```

That build generated both changed pages and their local contents navigation. The project wrapper `doc/build_docs` could not run because GNU Make is not installed in my Windows environment. The broader Sphinx pass also reports include-path errors in other pages, so I do not present it as a clean full documentation build. Neither reported error is in a file changed by this patch.

**Toolkit**

- Tool: ship-gate, Sphinx, and `git diff --check`
- What it produced: an accepted two-file branch check, two generated target pages with local navigation, and a clean whitespace check
- Difficulties: the project wrapper needs GNU Make; broad documentation rendering surfaced unrelated include-path errors
- What changed: the PR description explicitly records those limitations instead of claiming the whole documentation build passed

---

## Implementation Notes

**2026-11-03**

I reviewed several small documentation candidates before finding CTSM #3152. I rejected candidates with existing linked work rather than adding a parallel claim. I then claimed the CTSM issue after confirming it was unassigned and had no linked pull request.

**2026-11-03**

I added the existing local contents pattern to the two selected User Guide pages. I chose depth one because the pages have many lower-level examples and a deeper table would be noisy.

**2026-11-03**

The first ship-gate run stopped because the edits were not committed; after committing, it stopped again because the Windows environment exposes the CLI as `claude.cmd`. I fixed the local gate lookup and reran it. The final gate result accepted the branch and PR draft.

**Toolkit**

- Tool: Git, the ship-gate, and the documentation build tools
- What it produced: commit `8aaa32d`, a pushed branch, and a gate pass
- Difficulties: partial-clone object recovery and a Windows command-name mismatch interrupted the first push and gate run
- What changed: I fetched the missing object, retried the push, and changed the local gate to use `claude.cmd` on Windows

---

## Pull Request

**PR Link:** https://github.com/ESCOMP/CTSM/pull/4295

**PR Description:** The draft explains that the change adds the existing local navigation pattern to two pages, keeps the table at depth one, and leaves wording and code untouched. It records the direct Sphinx evidence, the clean whitespace check, and the local GNU Make limitation.

**Maintainer Feedback:**

- 2026-11-03: No maintainer feedback yet. The PR is open and GitHub shows that an approving review is required before it can merge.

**Status:** Awaiting review. Pull request #4295 is open from `YisacTW:docs/add-local-tables-of-contents` to `ESCOMP:master`.

**Toolkit**

- Tool: pr-precheck, ship-gate, and the PR-monitor playbook
- What it produced: an accept verdict for the branch and PR draft, plus a live PR awaiting review
- Difficulties: the initial draft said `Fixes #3152`, which was too broad for a focused two-page change; GitHub CLI is also unavailable, so the monitor cannot make its read-only run yet
- What changed: I revised the wording to `Refs #3152`, reran the gate successfully, and recorded the monitor limitation rather than inventing a report

---

## Learnings and Reflections

**Technical Skills Gained**

I learned how a Sphinx `contents` directive becomes a local navigation block in rendered HTML, how to work with a sparse clone and a documentation submodule, and how to keep a documentation pull request limited to evidence-supported files. I also learned that a pre-PR gate is most useful when it checks the committed branch rather than just files sitting in the working folder.

**Challenges Overcome**

The main challenge was issue availability: several reasonable-looking candidates already had linked work. Checking the live issue before claiming prevented duplicate effort. The CTSM environment also did not have GNU Make, and the first branch push needed a missing object retrieved from the fork. I kept those results visible in the story and PR draft rather than rewriting them as successful checks.

**What I'd Do Differently Next Time**

Next time I would check linked pull requests and the project’s documentation build prerequisites before spending time on a candidate. I would also start from a non-sparse checkout when I know the documentation build includes files across the repository, since that makes full-project validation less fragile.

---

## Resources Used

- [CTSM issue #3152](https://github.com/ESCOMP/CTSM/issues/3152)
- [CTSM contributing guide](https://github.com/ESCOMP/CTSM/blob/master/CONTRIBUTING.md)
- [Existing CTSM reStructuredText documentation pattern](https://github.com/ESCOMP/CTSM/blob/master/doc/source/users_guide/working-with-documentation/tips-for-working-with-rst.rst)

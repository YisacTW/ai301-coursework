# Evidence guide: where evidence lives in a PR package

<!--
THIS IS THE PART YOU WRITE (third week running: the map stays in your
hands). Your tool uses this guide as its map: for every kind of
evidence a rubric check names, this file says WHERE to find it in a PR
package and WHAT GOOD LOOKS LIKE when you do.

The four families below are the harness's failure categories under
the names the eval README uses: plan fidelity = silent-drift, test
evidence = not-tested, diff quality = unreviewable, standards and
comms = standards-wall. A package that fails none of them is a
clear-accept. Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the plan-context block's scope pair and test
  plan, the candidate PR's diff, commits, description, or
  test-evidence section, the repo-facts block's template asks and
  stated policy). In live mode (where in your working copy and on
  GitHub: your plan.md and its deviation notes, your branch's diff,
  your draft title and description, your captured test output, the
  repo's PR template and CONTRIBUTING.md).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("every changed file falls inside the
  plan's stated boundary or a deviation note") over adjectives ("the
  diff is clean").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts three ways: your
procedure says WHEN to gather each family, this guide says WHERE, and
your SKILL.md says the tool reads both. Write the map you wish your
executor had.
-->

## Plan fidelity (harness category: silent-drift)

In an eval package, read Plan context for scope, files, test plan, and
deviations, then compare it with the candidate PR diff and description.
In live mode, read `plan.md` and its Deviations section beside
`git diff main...HEAD` and `pr_draft.md`.

Good evidence covers every changed file and material behavior with a
plan statement or a recorded deviation. The description must describe
the resulting diff truthfully. Extra or missing work without a note is
silent drift.

## Test evidence (harness category: not-tested)

In an eval package, read the plan's test plan beside the candidate PR's
Testing section and test-evidence block. In live mode, read
`test_evidence.md`, `pr_draft.md`, the plan's verification steps, and
the repository check list in the template or contributing guide.

Good evidence names the command or specific test result and shows the
observable behavior that changes from before to after. A full raw
transcript is useful but not required when a specific command outcome
or test total is recorded. An honestly reported failed or unavailable
check is evidence; a bare claim that tests passed is not.

## Diff quality (harness category: unreviewable)

In an eval package, inspect the candidate PR's unified diff and commit
list. In live mode, inspect `git diff main...HEAD` and `git log
main..HEAD`.

Good diffs leave the planned fix easy to see. Debug output, dead or
commented-out experiments, generated artifacts, broad formatting
churn, and unrelated drive-by edits make a PR unreviewable.

## Standards and comms (harness category: standards-wall)

In an eval package, read Repo facts and thread highlights beside the
candidate PR title and description. In live mode, read the issue
thread, `.github/PULL_REQUEST_TEMPLATE.md`, `docs/CONTRIBUTING.md`,
and the title and description in `pr_draft.md`.

Good communication fills the repository's explicitly required template
sections with specific facts, links the issue where required, respects
explicit contribution instructions, and discloses AI use when a stated
policy or template asks for it. Boilerplate, an omitted required
section, or a missing required disclosure fails this family.

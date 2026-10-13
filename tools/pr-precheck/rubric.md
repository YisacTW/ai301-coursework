# Rubric: is this pull request ready to submit?

<!--
THIS IS THE PART YOU WRITE (fourth week running; this is the rubric's
final form in the sandbox). Your frame in SKILL.md executes whatever
checks you define here, via your procedure.md. It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the diff read against the plan's scope, the test
     evidence read against the plan's test plan, the description read
     against the diff, the repo-facts block's template asks) or a
     location from your references/evidence-guide.md. "The PR" is not
     a source; "the diff's changed files read against the plan's
     stated boundary" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself
     (does the diff fall inside the plan plus its deviation notes? is
     the claimed evidence observable?), never the write-up's shape
     (how long the description is, how many commits there are).
     Structure-shaped checks are what make graders disagree with
     themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (submit) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. State the `unclear`
   treatment explicitly: the frame here is YOUR SKILL.md, so a rubric
   that stays silent is only covered if your frame's grading
   discipline says what happens (the contract's own default is that
   an unverifiable claim fails).

Cover what actually gets bad PRs submitted. The failure families the
lecture named ARE the harness's scoring categories, same names as the
eval README: silent drift (the diff silently does more or less than
the posted plan, or the description claims fidelity the diff
contradicts), not tested (the evidence proves nothing observable, or
the repo's own checks were never run), unreviewable (debris or
unrelated hunks bury the change), and standards wall (the repo's
stated template and disclosure asks are ignored). Your evidence
guide's four headings map onto these one to one (plan fidelity =
silent drift, test evidence = not tested, diff quality =
unreviewable, standards and comms = standards wall), and the category
floor is scored on exactly these names plus clear accept. A rubric
that ignores a category will fail the eval packages built around
that category. And remember the honest-outcome
rule, fourth week running: a PR that honestly discloses a shortfall
can be ready; a rubric that equates "less than everything" with
"hold" fails the set.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| plan-fidelity | The plan's scope and deviations read beside every changed file and material behavior in the diff, plus the description's claims. | Pass when every material change and claim is covered by the plan or a recorded deviation, and the description does not promise more or less than the diff delivers. | required |
| observable-testing | The plan's verification plan, the PR test evidence, and the repository checks named by the template or contributing guide. | Pass when the evidence gives a concrete before/reproduced condition and an observable after-result that supports the planned fix, and names the relevant check commands with their outcome. A concise reported test total or command result is enough when it is specific; do not require a full terminal transcript. An honestly disclosed failed or unavailable check may pass when the description gives its result and reason without claiming success. | required |
| reviewable-diff | The unified diff and commit list, read against the issue and plan. | Pass when the intended fix is visible and the diff has no unrelated files, debug output, dead code, commented-out experiments, or formatting churn that obscures review. | required |
| standards-and-comms | The repository PR template, contribution guidance, issue thread, and candidate title and description. | Pass when the description supplies the template fields and contributor requirements that the repository explicitly requires, links or names the issue where required, and makes no misleading communication claim. Require AI disclosure, reviewer notes, screenshots, or checklist items only when the repository's stated rules or template ask for them. | required |

## Verdict rule

Accept only when every required check passes. Reject when any required
check fails or is unclear. Preferred checks would be reported but would
not change the verdict; this rubric currently has no preferred checks.

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->

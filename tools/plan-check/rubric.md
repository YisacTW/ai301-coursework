# Rubric: is this plan ready to post and build from?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here (via your procedure.md). It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the plan's scope statement, the test plan read against
     the repro evidence's steps, the plan comment read against the
     thread highlights, the repo-facts block) or a location from your
     references/evidence-guide.md. "The plan" is not a source; "the
     plan's stated cause read against what the repro evidence shows"
     is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (is
     this one bounded change? could a stranger start executing it?),
     never the write-up's shape (how many sections it has, how long it
     is, whether it uses headings). Structure-shaped checks are what
     make graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad plans posted. The lecture named the
failure families: the diagnosis ignores or contradicts the reproduced
evidence, the change is unbounded (scope creep), the plan targets the
symptom while the evidence points at the cause, a stranger could not
start executing it, the test plan proves nothing observable, the
unknowns are dressed up as certainty, and the comment ignores what the
thread or the repo's stated conventions ask. A rubric that ignores a
family will fail eval packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| diagnosis-grounded | The plan's diagnosis read against the repro-evidence block's observed behavior and artifacts. | Pass when the stated cause explains the reproduced behavior without contradicting it or claiming more than the evidence proves. | required |
| bounded-change | The plan's in-scope and out-of-scope statements, files or areas named, read against the issue and reproduction. | Pass when the plan keeps work within the diagnosed failure path: it may include directly related guards, sibling sites, or regression coverage needed to prevent the same failure, but excludes unrelated redesigns, broad refactors, and unverified work. | required |
| executable-steps | The plan's ordered implementation steps, named files or code areas, and repo-facts block. | Pass when a contributor could begin the work without guessing which area changes, what change to make, or how the work respects stated repository conventions. | required |
| verification-matches-repro | The plan's test plan read against the reproduction steps, expected behavior, and observed artifact. | Pass when the proposed check repeats or adapts the repro path and names an observable result that would distinguish a fixed state from the reproduced failure. | required |
| honest-unknowns | The plan's risks, assumptions, and deviation note read against the repro evidence and repo facts. | Pass when the plan separates evidence from unresolved choices and does not present an unverified cause, impact, or compatibility claim as fact. | required |
| thread-aware-comment | The candidate plan comment read against the issue context, thread highlights, repo-facts block, and the plan. | Pass when the comment gives the plan's own diagnosis, scope, and verification approach, follows any stated contribution or disclosure rule, and does not rely on another contributor's plan. | required |
|  |  |  |  |

## Verdict rule

Accept only when every required check passes. Reject when any required
check fails or is unclear. Preferred checks would be reported but would
not change the verdict; this rubric currently has no preferred checks.

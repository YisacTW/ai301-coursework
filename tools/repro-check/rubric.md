# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| claim-specific | The claim comment read against the issue title and description. | The claim names a detail that identifies this issue and says the next step will be a reproduction report or investigation. It does not promise a fix, a merge, or a deadline. | required |
| environment-recorded | The repro report's environment record read against the issue context and the repository facts. | The report records the operating system and the relevant application or dependency version, commit, tag, or release. If it differs from the issue's reported environment, the report calls out that difference. | required |
| steps-followable | The repro report's steps, including the starting state, command or interaction, and trigger. | A stranger can set up the stated starting state and perform the same actions without having to infer a missing command, file, input, or trigger. | required |
| behavior-faithful | The issue's described behavior compared with the repro report's expected result, actual result, and attached output, log, screenshot, or other artifact. | The artifact shows the same behavior the issue describes, or the report honestly shows that the behavior could not be reproduced. A different error, adjacent behavior, or unsupported explanation fails this check. | required |
| claims-backed | The claim comment and repro report read alongside the evidence they cite. | Each conclusion stays within what the environment, steps, and artifact show. An evidenced cannot-reproduce passes; a confident claim without matching evidence fails. | required |
| repo-conventions | The candidate comments read against the repo-facts block in eval mode, or the issue thread and repository contribution guidance in live mode. | The comments follow the repository's stated issue-reporting and AI-disclosure rules, and the claim is specific to the issue rather than boilerplate. | required |

## Verdict rule

Accept a complete package only when every required check passes. Reject
it if any required check fails or is unclear. For a claim-only draft,
grade only `claim-specific` and `repo-conventions`; the repro-report
checks are not yet applicable and do not affect that early verdict.

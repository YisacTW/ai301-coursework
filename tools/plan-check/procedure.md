# Procedure: how this skill grades a plan package

<!--
THIS IS THE PART YOU WRITE, and it is a new kind of part. Weeks 1 and
2, SKILL.md carried a numbered workflow and you only wrote judgment
files. This week the workflow is gone from the frame: SKILL.md says
"execute procedure.md", and these are the operating steps you author.
The machinery is in your hands now.

Your operator swap is the design brief. When your executor stalled
because your rubric said WHAT to decide but not HOW to find the
evidence, that was a procedure gap. This file is where those gaps get
closed: a complete procedure lets someone who has never seen a plan
package before (a groupmate, or the skill itself) grade one exactly the
way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
repro evidence before the plan, and note what behavior it pins down"
is a step; "understand the context" is a wish.
-->

## Read order

1. Identify whether this is live mode or eval mode. In live mode, read
   `scope.md` first and stop if the issue is outside the named Path
   Review repository.
2. Read the issue context and repository rules before reading the plan.
   Note the requested outcome, maintainer signals, and any required
   comment or disclosure convention.
3. Read the reproduction evidence before the candidate plan. Record
   the reported behavior, the evidence that shows it, and every claim
   the report deliberately does not establish.
4. Read the whole plan, including scope, implementation, verification,
   risks, and deviations. Then read the candidate plan comment.
5. In live mode, also read `voice-guide.md` and record only rules that
   the outgoing plan comment breaks.

## Evidence gathering

1. Gather diagnosis evidence by pairing the plan's stated cause with
   the reproduction's observed behavior and quoted artifacts.
2. Gather scope evidence from the plan's in-scope and out-of-scope
   statements, plus every file or area named for change.
3. Gather execution evidence from the ordered implementation steps and
   the repository conventions that constrain those steps.
4. Gather verification evidence by pairing each proposed test with the
   reproduction step or artifact it should reverse or confirm.
5. Gather honesty evidence from stated assumptions, open questions,
   risks, and deviations. Compare each factual claim with the
   reproduction evidence.
6. Gather communication evidence by comparing the plan comment with
   the plan, issue thread, and applicable contribution policy. Record
   whether an explicit disclosure or format requirement applies.

## Check execution

1. Grade `diagnosis-grounded` first. Mark it fail when the plan's cause
   conflicts with the repro or extends beyond what the repro proves.
2. Grade `bounded-change` next. Mark it fail when the plan includes
   unrelated changes or leaves its limits unstated.
3. Grade `executable-steps` using only the collected steps and repo
   constraints. Mark it fail when a contributor would need to guess a
   target, method, or required convention.
4. Grade `verification-matches-repro`. Mark it fail when the test has
   no observable expected result or cannot distinguish the proposed
   fixed state from the original repro.
5. Grade `honest-unknowns`. Mark it fail when an unsupported claim is
   presented as settled or a documented build deviation is absent.
6. Grade `thread-aware-comment` last. Mark it fail when the comment is
   boilerplate, disagrees with the plan, or violates an explicit thread
   or repository requirement.
7. Use `unclear` only when the evidence named by a check is genuinely
   missing. Do not fill a gap by consulting an unrelated local file or
   guessing what the author meant.

## Verdict assembly

1. Give every check one grade and one short evidence sentence that
   quotes or names the fact that decided it.
2. Apply the verdict rule exactly: accept only when every required
   check passes; any fail or unclear produces reject.
3. In live mode, summarize voice-guide violations before the JSON but
   do not let them replace a rubric grade unless the same concern also
   fails a named rubric check.
4. End with one fenced JSON object containing the item, all checks,
   their grades and evidence, and the binary verdict. Put nothing
   after that object.

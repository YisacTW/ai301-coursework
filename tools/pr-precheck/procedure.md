# Procedure: how this tool grades a PR package

<!--
THIS IS THE PART YOU WRITE (second week running for the procedure).
Week 3 you wrote these steps for a plan package; this week the graded
object is a PR package, and the read that matters most is a
side-by-side: the diff against the plan, the evidence against the test
plan, the description against both. Your week-3 procedure is the
pattern; do not paste it unchanged, because its read order was built
for a different object.

Your rotation is the design brief again, and this week friction routes
three ways: a stall on WHAT to decide is a rubric gap, a stall on
WHERE to look is a procedure gap (this file), and a stall on what the
tool even reads or outputs is a frame gap (your SKILL.md). A complete
procedure lets someone who has never seen a PR package before grade
one exactly the way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
plan's scope pair before opening the diff, and list the files the plan
names" is a step; "understand the change" is a wish.
-->

## Read order

1. Identify live or eval mode. In live mode, read `scope.md` first and
   stop if the issue is outside the named Path Review repository.
2. Read the issue, thread highlights, PR template, and contributing
   rules. Record the issue number, any explicit reviewer request, and
   the checks or disclosure the repository requires.
3. Read the plan, its test plan, and its Deviations section before the
   diff. List the files, behavior, limits, and evidence it promised.
4. Read the complete diff and commit list. Then read the draft title,
   description, and captured test evidence.
5. In live mode, read the voice guide and note only rules the outgoing
   title or description breaks.

## Evidence gathering

1. Pair each changed file and behavior in the diff with a plan scope
   line or deviation note. Pair each description claim with the diff.
2. Pair each test command and reported outcome with the plan's test
   plan, the original reproduction, and the repository check it
   represents. Look for a concrete before/reproduced condition and a
   changed observable result. A specific command result or test total
   can support a check; do not demand a full terminal transcript.
3. Scan the diff for unrelated hunks, temporary logging, commented-out
   code, generated files, and broad reformatting. Record the exact
   hunk or file if one appears.
4. Compare the draft description against the PR template, issue,
   contribution rules, and any stated AI-use policy. Record only
   missing fields or disclosures the repository explicitly requires.

## Check execution

1. Grade `plan-fidelity` first from the plan-to-diff and
   description-to-diff pairs. Fail undocumented drift or an inaccurate
   description.
2. Grade `observable-testing` from the test pairings. Fail a claim
   with no concrete observed support, or a required check that is
   omitted or hidden. Accept a known shortfall only when its actual
   result and reason are stated honestly.
3. Grade `reviewable-diff` from the diff scan. Fail any unrelated or
   obscuring debris.
4. Grade `standards-and-comms` from the template and rule comparison.
   Fail missing required sections, issue linkage, or AI disclosure
   only when the repository explicitly requires each one.
5. Use `unclear` only when the named evidence is absent. Do not infer
   intent from a file outside the package or working copy.

## Verdict assembly

1. Give every check pass, fail, or unclear and one evidence sentence.
2. Apply the verdict rule exactly. Any required fail or unclear makes
   the result reject.
3. When rejecting, lead the human summary with the first failing
   required check in rubric order. Still include every check in JSON.
4. End with the required fenced JSON object and no text after it.

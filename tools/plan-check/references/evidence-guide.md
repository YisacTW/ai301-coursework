# Evidence guide: where evidence lives in a plan package

<!--
THIS IS THE PART YOU WRITE (second week running: the judgment files
stay in your hands). The skill uses this guide as its map: for every
kind of evidence a rubric check names, this file says WHERE to find it
in a plan package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repro-evidence block,
  the candidate plan's scope statement or test plan, the plan comment,
  the repo-facts block). In live mode (where on GitHub or in the
  draft: the issue thread, the student's posted repro comment, the
  repo's docs, the draft plan and comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the stated cause cites behavior the
  repro evidence actually shows") over adjectives ("diagnosis is
  solid").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts twice: your
procedure.md tells the skill WHEN to gather each family, and this
guide tells it WHERE. Write the map you wish your executor had.
-->

## Diagnosis and grounding

In an eval package, read the candidate plan's diagnosis beside the
repro-evidence block, especially its observed behavior and quoted
artifacts. In live mode, read the student's draft plan beside their
posted reproduction comment on the issue.

Good grounding names a cause that accounts for the behavior the report
actually showed. It does not turn a missing artifact, a related error,
or an unresolved implementation choice into a proven root cause.

## Scope

Read the candidate plan's scope, exclusions, and named files or areas.
In live mode, compare them with the issue body and the student's repro
comment; in eval mode, compare them with the issue context and repro
evidence blocks.

Good scope makes one change needed to address the diagnosed problem and
states what it will leave alone. A broad cleanup, a rewrite, or a plan
that silently expands beyond the proof does not pass.

## Executability

Read the plan's implementation steps and its named files or code areas.
Read the repo-facts block in eval mode, or the repository contribution
guidance in live mode, for constraints that affect those steps.

Good execution detail gives a workable starting point, an approach, and
an order of work. It does not require a stranger to decide the target
file, invent the intended edit, or discover a required convention after
the build has begun.

## Test plan

Read the plan's verification section beside the repro-evidence block.
Use the reported steps, expected behavior, and observed output as the
baseline in eval mode; use the student's posted reproduction comment as
the baseline in live mode.

Good verification describes a repeatable check and the concrete result
that should change after the fix. “Test it” or a test that cannot expose
the reproduced problem does not pass.

## Honesty

Read the plan's assumptions, risks, or unknowns and its Deviations
section. In live mode, also compare claims with the student's repro
comment and the issue thread.

Good honesty marks choices the reproduction did not settle and explains
any later departure from the posted plan. Unsupported certainty about a
root cause, impact, or compatibility result does not pass.

## Comms

Read the candidate plan comment beside the plan, issue context, thread
highlights, and repo-facts block in eval mode. In live mode, read the
draft comment beside the current issue thread and the repository's
contribution guidance.

Good communication carries the author's own diagnosis, bounded change,
and verification approach into the thread. It follows an explicit
template or AI-use rule when one exists and never substitutes “same as
above” for a plan.

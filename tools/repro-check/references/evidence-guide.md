# Evidence guide: where proof lives in a reproduction package

<!--
THIS IS THE PART YOU WRITE (new this week: Unit 1 handed you this file
finished; the scaffolding fades). The skill uses this guide as its map:
for every kind of proof a rubric check names, this file says WHERE to
find it in a package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repo-facts block, the
  claim comment, the repro report and its parts). In live mode (where
  on GitHub or in the draft: the issue thread, the repo's docs, the
  student's draft comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the versions named match what the
  issue targets, or the difference is called out") over adjectives
  ("environment is thorough").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute; the rubric swap showed you what that feels
like. Write the map you wish your grader had.
-->

## Environment

**Where it lives.** In an eval package, look in the issue's environment
details, the repo-facts block, and the first lines of the candidate
repro report. In live mode, compare the issue thread and repository
setup instructions with the draft repro comment.

**What good looks like.** The report names the operating system and the
version, release, tag, or commit that places the result. It also names
the relevant tool or dependency version when that affects the bug. If
the report tests a different environment from the issue, it says so
plainly instead of implying they are the same.

## Steps

**Where it lives.** In an eval package, use the issue's original steps
and the candidate report's command block or numbered actions. In live
mode, use the issue, the repository's setup documentation, and the
draft comment.

**What good looks like.** The steps state the starting state, the input
or file used, and the command or interaction that triggers the result.
Another contributor should be able to follow them without filling in a
missing setup detail or guessing what was clicked or run.

## Behavior shown

**Where it lives.** In an eval package, compare the issue description
with the report's expected and actual behavior and its quoted output,
log, screenshot, or other artifact. In live mode, compare the issue
thread with the artifact included in the draft comment.

**What good looks like.** The artifact supports the actual result and
matches the behavior in the issue. A report that reaches a different
error or only says it reproduced the bug does not show proof. A
careful report that shows the expected steps but could not reproduce
the result is still useful when it says exactly what happened.

## Honesty

**Where it lives.** Read the claim comment and each conclusion in the
repro report beside the environment, steps, and artifact that support
it. In an eval package, the issue context and repo-facts block provide
the comparison point; in live mode, use the issue thread and draft.

**What good looks like.** The writer separates what they observed from
what they have not verified. The report may say it could not reproduce
the issue when the evidence supports that result. It should not claim a
cause, broad impact, or successful reproduction that the artifact does
not establish.

## Comms

**Where it lives.** In an eval package, compare the candidate comments
with the issue, repo-facts block, bug-report template, and contribution
policy. In live mode, use the issue thread and the repository's README,
CONTRIBUTING file, templates, and any AI-use policy.

**What good looks like.** A claim points to this issue by naming its
specific behavior and promises a report or investigation rather than a
fix or timeline. Both comments follow any required template or AI-use
disclosure rule. Generic claims that could fit any issue do not provide
useful coordination.

---
name: pr-precheck
description: Grade a PR package (a candidate pull request read against the plan it claims to implement and the issue that plan belongs to) and decide whether it is ready to submit. Use when checking your own branch, draft PR title, and description before opening the pull request, or when grading an eval package bundle.
---

# pr-precheck: rubric-driven PR grading

<!--
THIS IS THE PART YOU WRITE, and it is the last one: the frame itself.
Weeks 1 through 3 handed you a working SKILL.md and you filled the
files behind it; this week the frame ships as headings, and you write
what it says. The frontmatter above and the section headings below are
fixed (CONTRACT.md's layout rule); the instructions under each heading
are yours. Write instructions to the tool, in the imperative, the way
weeks 1-3's frames spoke to you: what to read, in what order, what to
refuse, what to emit. Your executor in the rotation is the test: a
frame gap they hit (cannot tell what the tool reads, or how a verdict
gets assembled) is a missing sentence here.

One section is not yours: the JSON schema in "Verdict and output" is
reproduced from CONTRACT.md verbatim and may not be altered. Your
words decide everything around it.
-->

## The question

Grade one proposed pull request and answer one question: is it ready to
submit? Read the title, description, commits, diff, and test evidence
against the plan that the PR claims to implement, its issue, and the
repository's stated expectations. Grade evidence, not confidence.

## Inputs and modes

Use one mode per run. In live mode, read the student's `plan.md`,
including deviations, the branch diff from `git diff main...HEAD`, the
draft PR title and description, `test_evidence.md`, and the issue URL.
Read the issue thread, `.github/PULL_REQUEST_TEMPLATE.md`, and
`docs/CONTRIBUTING.md` as the repository-side evidence. A house-chain
student uses the supplied house plan and reproduction pack in place of
their own plan and issue evidence.

In eval mode, the supplied package is the entire record. Do not fetch
GitHub or inspect local files outside it. Read every package section
and apply the complete rubric and verdict rule.

## The scope seam (live mode only)

Before collecting any live evidence, read `scope.md`. Refuse to grade
an issue outside its named repository. If its Repo line still contains
a placeholder, stop and tell the student to fill it instead of guessing
the scope. Apply its classroom rules when reviewing the issue and PR.
Ignore `scope.md` entirely in eval mode.

## The voice seam (live mode only)

In live mode, read `voice-guide.md` before assessing the outgoing PR
title and description. Report a broken personal writing rule with the
rule it conflicts with, but do not change the rubric verdict unless a
named rubric check also fails. Ignore the voice guide in eval mode.

## Component reads

Read `rubric.md` for the checks and verdict rule. Use
`references/evidence-guide.md` to locate evidence, then execute
`procedure.md` exactly as written. If the rubric has no real checks or
the procedure has no real steps, refuse to grade. If the procedure
does not say how to perform a needed action, report that gap rather
than inventing an unstated workflow.

## Verdict and output

Use only `accept` for ready to submit and `reject` for hold. Give a
brief, evidence-backed line for every check. End with the exact JSON
shape below in a fenced block. It must be valid and last, with nothing
after it.

```json
{
  "item": "<PR URL or bundle id>",
  "checks": [
    {"name": "<check name>", "grade": "pass|fail|unclear",
     "evidence": "<one line: the fact or quote that decided it>"}
  ],
  "verdict": "accept|reject"
}
```

## Grading discipline

- Name the fact, diff hunk, or command output that decides every check.
- Grade the actual PR against its plan and evidence, not how polished
  the writing appears.
- Apply the rubric as written and follow the procedure as written. Do
  not add private standards during a run.
- Treat `unclear` as a failure when the verdict rule does not say
  otherwise. A maintainer cannot verify an unclear claim.

# Unit 1 — Issue Selection

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/73

**Verdict output**

The live skill accepted the issue. It found a default-branch commit from 2026-09-16, no assignees or linked pull requests, a normal contribution policy, and a clear two-file documentation/configuration correction. The complete machine-readable result was:

```json
{
  "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/73",
  "checks": [
    {"name": "repo-active", "grade": "pass", "evidence": "Default-branch commit f89c06f dated 2026-09-16, four days before the live run, well within 90 days"},
    {"name": "unclaimed-work", "grade": "pass", "evidence": "assignees: [], comments: 0, no linked or mentioned PRs found via search or timeline"},
    {"name": "contribution-policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md describes a standard fork/PR workflow with no AI restriction; no AI_POLICY.md or AGENTS.md present"},
    {"name": "issue-availability", "grade": "pass", "evidence": "Opened by collaborator Aburke225 as a direct deliverable; timeline shows only label events, no prior abandoned PRs"},
    {"name": "maintainer-responsive", "grade": "pass", "evidence": "Collaborator Aburke225 posted same-day closing comments on sampled issues #52 and #43"},
    {"name": "bounded-scope", "grade": "pass", "evidence": "Issue names README.md, .env.example, and core/config.py; making the key names agree verifies the fix, and the estimate is 1-2 hours"}
  ],
  "verdict": "accept"
}
```

## Eval iterations

**Run history**

1. **13/20 — below the bar.** I had made maintainer response time and a very narrow definition of scope required. That rejected several issues the gold labels considered reasonable, so I moved those signals to preferred checks.
2. **16/20 — below the bar.** The revision became too open-ended and accepted issues that conflicted with a repository’s AI policy, were bot-created without maintainer confirmation, or had a history of unsuccessful implementation attempts. I added required contribution-policy and issue-availability checks.
3. **19/20 — PASS.** The final run met the course bar of 18/20 and every category floor. It made one conservative false rejection: an older issue with a single closed pull request. That is a useful reminder that availability rules should distinguish repeated abandoned work from one old, closed attempt.

The official transcript is in `beat-1-sandbox/unit-1/eval-run.txt`.

**Issue analysis**

I looked at eval issue #9, which the gold label accepted but my final rubric rejected. The repository was active and the issue had no assignee, but it had one old closed linked pull request. My `issue-availability` check treated that history cautiously and rejected it. The result showed a real trade-off: the rule protects a new contributor from stepping into work that may already have been tried, but a single closed attempt does not always mean the issue is unavailable.

**Check rationale**

The current `unclaimed-work` check says: “No assignee, open linked pull request, or active non-student claim appears in the evidence.” An assignee, open pull request, or active claim is a useful stop sign because it means someone may already be spending time on the same work. Choosing an unclaimed issue avoids duplicated effort and makes it more likely that a first contribution will be welcomed.

**Trade-offs**

The availability rule can reject an issue that otherwise looks approachable, especially when old attempts are attached to it. I would rather make that cautious choice for a first contribution than spend time building a solution that conflicts with existing work or has already stalled for a reason I do not yet understand. For a later contribution, I could investigate those older attempts before deciding.

## Selection rationale

I have some coding experience, but I wanted a first contribution that I could realistically finish in about two hours. Issue #73 fits because it has a clear, limited goal: make the README, the example environment file, and the configuration behavior agree about the required API key. The files are already named and the result is easy to check, so I can focus on learning the project’s contribution workflow without having to redesign a larger feature.

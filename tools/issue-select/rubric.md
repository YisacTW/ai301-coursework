# Rubric: is this a good first issue?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-responsive | In the repo-facts block, use the maintainer first-response sample. In live mode, sample five recently updated issues and identify the first owner, member, or collaborator response in each thread. | At least one sampled issue received an owner, member, or collaborator response within 30 days. | required |
| repo-active | In the repo-facts block, use the latest release date and the last five default-branch commit dates. In live mode, use the repository releases and default-branch commit history. | The repository released a version or received a default-branch commit within the last 90 days. | required |
| bounded-scope | Use the issue body and comment thread. Identify the affected file, component, or behavior, the expected outcome, and a practical way to verify the change. | The issue names one bounded change, states the expected behavior, and gives enough detail to verify a solution without first redesigning the feature. | required |
| unclaimed-work | Use assignees, linked pull requests, and the issue thread. In live mode, apply the Path Review house rule to student claim comments only. | No assignee, open linked pull request, or active non-student claim appears in the evidence. | required |

## Verdict rule

Accept only if every required check passes. Treat an unclear required check as a failure because a newcomer should choose an issue whose maintenance, activity, scope, and availability can be verified from the available evidence.

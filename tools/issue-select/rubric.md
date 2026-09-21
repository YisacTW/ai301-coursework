# Rubric: is this a good first issue?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-responsive | In the repo-facts block, use the maintainer first-response sample. In live mode, sample five recently updated issues and identify the first owner, member, or collaborator response in each thread. | A recent maintainer response is positive evidence, but its absence in a small sample does not reject an otherwise active repository. | preferred |
| repo-active | In the repo-facts block, use the latest release date and the last five default-branch commit dates. In live mode, use the repository releases and default-branch commit history. | The repository released a version or received a default-branch commit within the last 90 days. | required |
| bounded-scope | Use the issue body and comment thread. Identify the affected file, component, or behavior, the expected outcome, and a practical way to verify the change. | The issue identifies a concrete user-visible problem or deliverable and a reasonable way to tell whether the change worked; related edits across several files are allowed. | preferred |
| unclaimed-work | Use assignees, linked pull requests, and the issue thread. In live mode, apply the Path Review house rule to student claim comments only. | No assignee, open linked pull request, or active non-student claim appears in the evidence. | required |
| contribution-policy | Use the contribution-policy field or the repository contribution guide. | The policy permits independently written, reviewed, and understood contributions; reject a repository that prohibits AI-assisted code or documentation for this workflow. | required |
| issue-availability | Use the issue author, checklist, linked pull requests, and comment history. | The request is ready for a new contribution: it is not a bot-created proposal awaiting maintainer confirmation, and it does not show repeated prior implementation attempts that leave the work unavailable or unresolved. | required |

## Verdict rule

Accept only if every required check passes. Treat an unclear required check as a failure because a newcomer should choose an issue whose maintenance, activity, scope, and availability can be verified from the available evidence.

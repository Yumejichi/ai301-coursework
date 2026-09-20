# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-alive | Maintainer comments on recent issue threads and recent merge history | At least 1 human maintainer comment, review, or merge within the last 90 days | required |
| repo-in-use | Recent default-branch commit dates and release history | At least one default-branch commit or release within the last 30 days | required |
| scope-fits-newcomer | Issue title, body, labels, and the full comment thread | Pass when the issue identifies a concrete bug or requested change and the intended result is clear enough to verify. Multiple examples, affected cases, possible causes, or implementation suggestions may still belong to one bounded issue and do not by themselves make it open-ended. Likewise, a change may touch multiple named files or documentation sections and still be bounded when the requested deliverables are explicitly identified. Read the title and body together: examples introduced by "including" or ending in "etc." do not make a task unbounded when they identify instances of the same missing behavior in an existing feature; fail as umbrella work when completion instead requires selecting independent tasks from a backlog or extending work across the repository without a defined deliverable. Uncertainty about causes, algorithms, or files to edit is implementation uncertainty and does not fail this check when the outcome is verifiable. However, if a required product decision or core content needed to identify the deliverable is still undecided, fail even if generic interaction steps are listed and nobody has explicitly disagreed. Fail for repository-wide or tracking/umbrella work, or when the comment thread shows unresolved disagreement about the intended behavior or design and no later maintainer decision resolves it, or when successful behavior cannot be determined from the issue and discussion. | required |
| unclaimed | Issue status, assignees, the full comment thread including the most recent claim/unclaim activity, and linked or referenced pull requests | The issue is open and there is no current evidence that someone is actively implementing it. A claim remains current unless later evidence explicitly releases, unassigns, abandons, or supersedes it. Fail if there is a current assignee, an unresolved claim in the comment thread, or an open linked or referenced PR implementing the issue. Closed/abandoned PRs and claims with a later explicit unassignment or release do not count as current claims. Reconcile the claim history chronologically: a closed PR resolves only the work associated with that PR, not a separate later claim. An empty assignee list or the age of a claim does not release an unresolved claim in comments; do not assume a release in comments absent from the supplied evidence. | required |
| policy-allows-ai | Repository contribution guidelines, AI policy, or other contributor documentation | Pass unless the repository explicitly prohibits the AI-assisted contribution required for this course. If the repository explicitly prohibits AI-generated or AI-assisted code or documentation, fail. No stated AI policy is a pass. | required |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->
Accept only if every required check passes.
Reject if any required check fails or is unclear.
Preferred checks do not change the accept/reject verdict; they are used only to rank accepted issues.
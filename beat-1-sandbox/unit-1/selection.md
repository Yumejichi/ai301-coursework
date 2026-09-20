# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69

[The individual Path Review issue page. A link to the repository or the issue list
does not satisfy this field.]

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
Grading summary — repo: codepath/pathreview-ai301-fa26-s3 (in scope)

  Repo-level facts (apply to all three):
  - Recent commits by Aburke225 (author_association: COLLABORATOR) as recently as 2026-09-16 → maintainer-alive: pass, repo-in-use: pass
  - No CONTRIBUTING.md or AI policy file found (404s) → silence passes → policy-allows-ai: pass
  
  Per issue:

  ┌─────┬─────────────────────────────────────────────────────────────────────┬─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┬─────────┐
  │  #  │                         scope-fits-newcomer                         │                                                      unclaimed                                                      │ Verdict │
  ├─────┼─────────────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┼─────────┤
  │ 69  │ Pass — single-file AttributeError fix, files + test named, effort   │ Pass — no assignee, no comments                                                                                     │ accept  │
  │     │ estimated                                                           │                                                                                                                     │         │
  ├─────┼─────────────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┼─────────┤
  │ 68  │ Pass — single-file ZeroDivisionError fix, files + test named,       │ Pass — a student ("acordero4852") posted a claim comment, but Path Review house rule says classmates' claim         │ accept  │
  │     │ effort estimated                                                    │ comments never block an issue                                                                                       │         │
  ├─────┼─────────────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┼─────────┤
  │ 60  │ Pass — clear repro snippet, single-line TypeError fix in check()    │ Pass — no assignee, no comments                                                                                     │ accept  │
  └─────┴─────────────────────────────────────────────────────────────────────┴─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┴─────────┘

  Ranked by fit (Python-heavy, wants clear/verifiable bounded scope, building debugging/testing reps):

  1. #69 — cleanest pick: fully unclaimed, narrow single-function fix, explicit 2–4h estimate, existing xfail test just needs the marker removed once fixed.
  2. #60 — equally bounded with a directly runnable repro snippet (great for verifying your fix), but no stated effort estimate.
  3. #68 — same shape and effort estimate as #69, but another student has already started investigating it; claiming is allowed per the house rule, just more likely to overlap with someone else's work.

  [
    {
      "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69",
      "checks": [
        {"name": "maintainer-alive", "grade": "pass", "evidence": "Collaborator Aburke225 committed to default branch 2026-09-16, within 90 days"},
        {"name": "repo-in-use", "grade": "pass", "evidence": "Default-branch commit on 2026-09-16, within 30 days of today (2026-09-20)"},
        {"name": "scope-fits-newcomer", "grade": "pass", "evidence": "Body names exact crash cause, files rag/generator/output_parser.py + its test, and a 2-4h estimate"},
        {"name": "unclaimed", "grade": "pass", "evidence": "0 comments, empty assignees list, state OPEN"},
        {"name": "policy-allows-ai", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI_POLICY.md found in repo (404)"}
      ],
      "verdict": "accept"
    },
    {
      "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/60",
      "checks": [
        {"name": "maintainer-alive", "grade": "pass", "evidence": "Collaborator Aburke225 committed to default branch 2026-09-16, within 90 days"},
        {"name": "repo-in-use", "grade": "pass", "evidence": "Default-branch commit on 2026-09-16, within 30 days of today (2026-09-20)"},
        {"name": "scope-fits-newcomer", "grade": "pass", "evidence": "Body gives exact runnable repro code and names the failing test; single-line fix in FaithfulnessChecker.check()"},
        {"name": "unclaimed", "grade": "pass", "evidence": "0 comments, empty assignees list, state OPEN"},
        {"name": "policy-allows-ai", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI_POLICY.md found in repo (404)"}
      ],
      "verdict": "accept"
    },
    {
      "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/68",
      "checks": [
        {"name": "maintainer-alive", "grade": "pass", "evidence": "Collaborator Aburke225 committed to default branch 2026-09-16, within 90 days"},
        {"name": "repo-in-use", "grade": "pass", "evidence": "Default-branch commit on 2026-09-16, within 30 days of today (2026-09-20)"},
        {"name": "scope-fits-newcomer", "grade": "pass", "evidence": "Body names exact crash cause, files rag/retriever/keyword_search.py + its test, and a 2-4h estimate"},
        {"name": "unclaimed", "grade": "pass", "evidence": "Comment from student acordero4852 ('I'd like to take this one on') exists, but Path Review house rule: other students' claim comments do not block an 
  issue"},
        {"name": "policy-allows-ai", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI_POLICY.md found in repo (404)"}
      ],
      "verdict": "accept"
    }
  ]

```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]
agreement: 19/20 scored items  (bar: 18/20: PASS)

**Issue analysis**

[One scored issue, identified by id (`issue-01` through `issue-20`; the `calib-`
issues are not scored). State your rubric's decision, the gold label, and the
reasoning that produced your rubric's result.]

`issue-01  accept  reject   NO     failed: scope-fits-newcomer`

My rubric's decision was `reject`, while the gold label was `accept`. The result was produced because `scope-fits-newcomer` failed. Since my verdict rule requires every required check to pass, that failure caused the overall `reject` verdict.

**Check rationale**

[One check from the `rubric.md` uploaded to `tools/issue-select/`, quoted as it is
currently written, with the reasoning behind its current form.]
`scope-fits-newcomer`:

> Pass when the issue identifies a concrete bug or requested change and the intended result is clear enough to verify. Multiple examples, affected cases, possible causes, or implementation suggestions may still belong to one bounded issue and do not by themselves make it open-ended. Likewise, a change may touch multiple named files or documentation sections and still be bounded when the requested deliverables are explicitly identified. Read the title and body together: examples introduced by "including" or ending in "etc." do not make a task unbounded when they identify instances of the same missing behavior in an existing feature; fail as umbrella work when completion instead requires selecting independent tasks from a backlog or extending work across the repository without a defined deliverable. Uncertainty about causes, algorithms, or files to edit is implementation uncertainty and does not fail this check when the outcome is verifiable. However, if a required product decision or core content needed to identify the deliverable is still undecided, fail even if generic interaction steps are listed and nobody has explicitly disagreed. Fail for repository-wide or tracking/umbrella work, or when the comment thread shows unresolved disagreement about the intended behavior or design and no later maintainer decision resolves it, or when successful behavior cannot be determined from the issue and discussion.

I kept this check focused on whether the expected outcome is clear and verifiable, rather than whether the implementation is already obvious. A newcomer can still work on an issue when the cause or files are uncertain, as long as there is a clear definition of what successful behavior should be.

**Trade-offs**

[What the quoted check gives up. Any one of these is a complete answer: an issue whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

`issue-01  accept  reject   NO     failed: scope-fits-newcomer`

This check can reject an issue that the gold label considers acceptable. In the final evaluation, `issue-01` had a gold label of `accept`, but my rubric rejected it because `scope-fits-newcomer` failed. This is a trade-off of requiring the intended result to be clear and verifiable before accepting an issue.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

[Answer all three:

1. The issue's fit to your interests and to the time available.
2. What the verdict identified correctly, and what you weighed that the rubric could
   not.
3. The anticipated difficulty in claiming it.]

I chose #69 because I mostly practice coding and interview problems in Python, and I want more experience debugging an unfamiliar codebase as I prepare for software engineering roles. The issue names the parser and test files and estimates 2–4 hours, which fits my limited time for this assignment.

The accept verdict correctly identified a bounded bug with a clear way to check the fix: handle a top-level JSON array without the `.items()` crash, then remove the existing test's `xfail` marker and verify it passes. Beyond the rubric's checks, I weighed the chance to understand why the parser fails and practice debugging myself, rather than just have AI generate a fix.

I expect claiming it to be straightforward because the live verdict found no assignee or comments, and the issue is still open with neither. I'll check again before claiming it in Unit 2 in case that changes.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.

# Evidence guide: where evidence lives in a PR package

## Plan fidelity (harness category: silent-drift)

Eval: read Plan context, scope/exclusions/test plan and any deviations, against Candidate PR description, checklist, and Diff. Live: compare plan.md including Deviations against `git diff main...HEAD` and pr_draft.md. Map every hunk to a planned behavior or justified deviation and check for omitted commitments. Good evidence accounts for more and less than planned; explicit bounded deviations can be honest, while a false claim of exact implementation cannot.

## Test evidence (harness category: not-tested)

Eval: compare Issue/repro evidence and Plan context test plan with Candidate PR Test evidence and test hunks in Diff. Live: compare plan.md and the issue's repro steps with test_evidence.md, pr_draft.md Testing, and repository check requirements. Good evidence pairs reproducible commands or UI actions with concrete recorded observations of the original failure and changed behavior, relevant controls, and the package’s named repository suite. Full logs are strongest, but precise observation summaries and named suite outcomes count when paired with decisive repro evidence. A fixture only proves a test was added. A bare “tests pass” or “works now” is insufficient; distinguish those from an explicit observed result such as an exit code, preserved value, or exact UI response tied to reproduction steps. Do not describe prose summaries as raw output. Disclosed failures or missing coverage must state the bounded limitation honestly; do not infer all-green results. Only in live Path Review coursework, capture make test-unit, make test-integration, make lint, and make typecheck; an expected no-tests integration result is reported as observed.

## Diff quality (harness category: unreviewable)

Eval: inspect the entire unified Diff and Commits against the issue and plan. Live: inspect `git diff main...HEAD` and branch commits; git status identifies local work that is not part of that committed diff. Good evidence makes the relevant fix visible and contains no unrelated refactors, debug prints, dead code, or broad formatting changes. For calib-03, property.js is unrelated even if its refactor appears harmless.

## Standards and comms (harness category: standards-wall)

Eval: read Repo facts template asks and contribution/AI policy plus Thread highlights, then compare with Candidate PR title, description, checklist, and relevant diff files. Live: use .github/PULL_REQUEST_TEMPLATE.md, docs/CONTRIBUTING.md, the issue thread, and pr_draft.md. Good text fills applicable sections substantively, explains N/A, names the issue, and follows explicit disclosure rules. For live coursework, Notes for Reviewers states actual AI use. Do not claim guidelines were read or a template followed without checking. Voice-guide notes are live-only and do not independently gate the verdict. Faithfulness claims belong to the plan-fidelity and claim-accuracy checks.

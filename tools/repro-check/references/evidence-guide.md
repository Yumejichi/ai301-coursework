# Evidence guide: where proof lives in a reproduction package

In eval mode, use only the bundle; do not fetch external evidence. In live mode, read the issue and repository docs for context, but judge the submitted draft's proof, not unquoted files elsewhere on disk. Quote the fact that supports each grade; do not invent missing evidence.

## Environment

- **Where it lives:** Eval: the repro report's environment/setup record, compared with the issue context and repo-facts. Live: the draft's environment/setup record, compared with the issue thread and repository setup docs.
- **What good looks like:** The tested revision and relevant platform, runtime/dependency versions, and configuration identify the test environment. Differences from the issue's target are stated, not hidden.
- **Rubric check:** Environment-recorded.

## Steps

- **Where it lives:** Eval: the repro report's setup, commands/actions, and inputs. Live: those same parts of the draft, read against the issue's trigger.
- **What good looks like:** A stranger can go from the stated starting conditions to the trigger without guessing essential commands, inputs, or state. Required fixtures or data are provided or have usable retrieval instructions.
- **Rubric check:** Steps-followable.

## Behavior shown

- **Where it lives:** Eval: output excerpts, logs, screenshots, or other artifacts in the repro report, compared with the issue context. Live: evidence included or quoted in the draft, compared with the issue's described behavior.
- **What good looks like:** Evidence shows the result of testing the issue's specific trigger, whether the bug occurs or not. An unrelated error or a bare assertion of reproduction is not proof of the reported bug.
- **Rubric check:** Behavior-matches.

## Honesty

- **Where it lives:** Eval: the repro report's conclusion alongside its steps, environment, and artifacts. Live: the same parts of the draft.
- **What good looks like:** The conclusion says only what the evidence supports and states relevant limits. An evidenced cannot-reproduce result is valid; it does not prove the bug never happens.
- **Rubric check:** Behavior-matches.

## Comms

- **Where it lives:** Eval: the claim comment against the issue context, and both comments against the repo-facts policies. Live: the drafts against the issue thread, README, CONTRIBUTING, applicable templates/policies, and scope.md; also review voice-guide.md as directed by SKILL.md.
- **What good looks like:** The claim names the issue's specifics, states the investigation plan, and promises findings without promising a fix or date. Comments follow applicable repository rules, including required AI disclosure; in Path Review, another student's claim does not block yours, and your repro must contain your own proof.
- **Rubric checks:** Claim-quality and Repo-conventions.

For live claim-only drafts, use Comms. Report reproduction-dependent checks as `unclear` with evidence `not yet applicable: claim-only draft` and exclude them from the verdict. For applicable checks, insufficient evidence is `unclear`, which the rubric treats as a failure.

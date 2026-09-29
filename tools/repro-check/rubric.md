# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Behavior-matches | Issue description against the repro's inputs, output/artifacts, and conclusion. | Tests the issue's behavior; evidence supports reproduction or an honest cannot-reproduce result. | required |
| Steps-followable | Repro's starting conditions, commands/actions, and inputs. | Another person can repeat the investigation without guessing essential steps or inputs. | required |
| Environment-recorded | Repro's environment record and setup details. | Identifies the tested revision and relevant platform, versions, and configuration needed to repeat the test. | required |
| Claim-quality | Claim comment against the issue description. | Names the specific issue, states the investigation plan, and promises findings without promising a fix or deadline. | required |
| Repo-conventions | Claim/repro comments against repo-facts in eval mode or repository policies and scope in live mode. | Comments follow applicable repository rules, including AI disclosure when required. | required |

Grade each check `pass` if its condition is met, `fail` if violated, or `unclear` if evidence is insufficient.

## Verdict rule

`accept` (READY) if every applicable required check passes; otherwise `reject` (HOLD). `unclear` counts as fail.

For live claim-only drafts, grade Claim-quality and Repo-conventions. Mark the other checks `unclear` with evidence `not yet applicable: claim-only draft` and exclude them from the verdict.

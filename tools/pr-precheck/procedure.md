# Procedure: how this tool grades a PR package

## Read order

1. Apply the frame's mode and scope rules and read the grading components.
2. Read issue, reproduction, thread direction, and repository requirements. Record expected behavior and mandatory asks.
3. Read the accepted plan and deviations before the diff; list the boundary, named files or folders, exclusions, and test cases.
4. Read the PR title and description, commits, entire diff, then test evidence. This permits comparison of claims with artifacts rather than treating claims as proof.

## Evidence gathering

1. Build a file/hunk-to-plan mapping. Record added behavior and omitted plan items, and any explicit explanation of deviations.
2. Map each factual description/checklist claim to a diff location or actual test result. Record contradictions and unsupported claims separately.
3. Pair every planned repro/control/check with its command, observable output, and claimed outcome. Record missing runs and disclosed failures; distinguish test existence from successful execution. Interpret concrete recorded observations according to the rubric; raw-log formatting is not a separate gate. Do not import live-course commands into eval mode.
4. Inspect the full diff for unrelated edits and debris. Record concrete hunks, not judgments based on size or commit count.
5. Pair every applicable template section, contribution rule, AI policy, and explicit maintainer direction with the text or artifact satisfying it. In live mode also record voice-guide violations.

## Check execution

1. Apply all checks in rubric order using these pairings and the evidence-guide locations.
2. Mark pass only when the stated pass condition holds; fail for contradiction or missing required evidence; unclear for genuine ambiguity. Cite a specific fact or absence for every result.
3. Apply the honest-shortfall clauses explicitly: disclosure is not automatically a failure or a waiver. Verify the bounded result that is actually claimed.
4. Reuse already gathered evidence without rereading the entire bundle unless a contradiction requires it. Never fetch outside evidence in eval mode, invent test results, or silently add requirements. Treat accepted Plan context as authoritative even if Thread highlights omit its posting. Do not speculate about missing helper implementations or omitted caller behavior; fail on demonstrated mismatches in the supplied evidence. Report procedure gaps.

## Verdict assembly

1. Apply the rubric verdict rule: every required check must pass; required unclear counts against acceptance; preferred checks do not gate.
2. Identify the first failing or unclear required check in rubric order as the deciding check. Cite it in the summary and still report every other check.
3. In live mode add any voice notes. End with the frame's valid fenced JSON containing the item identifier, every check with grade and evidence, and binary verdict. Nothing follows the block.

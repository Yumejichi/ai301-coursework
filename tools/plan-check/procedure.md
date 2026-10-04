# Procedure: how this skill grades a plan package

## Read order

1. Read the issue and reproduction evidence; note the reported
   failure, expected behavior, and any control results.
2. Read the candidate plan and identify its diagnosis, scope,
   proposed changes, and test plan regardless of section headings.

## Evidence gathering

1. For diagnosis, record the proposed cause and compare it with
   the reproduction observations, including any controls.
2. For scope, record the named files or components, proposed
   changes, and explicit exclusions.
3. For testing, record the manual or automated steps and expected
   result; compare them with the original reproduction.
4. Quote the evidence used for each check rather than filling
   gaps with assumptions.

## Check execution

1. Apply each check in rubric.md using the gathered evidence.
2. Assign pass when its pass condition is satisfied.
3. Assign fail when required information is missing or the
   evidence contradicts the pass condition.
4. Assign unclear when the available evidence is ambiguous.
5. Give an evidence-based explanation for each grade; do not
   require specific headings such as Summary or Diagnosis.

## Verdict assembly

1. Apply the verdict rule in rubric.md.
2. Return accept (ready) only when every required check passes.
3. Return reject (hold) if any required check fails or is unclear.
4. Identify the deciding checks and cite the supporting evidence,
   explicitly noting any missing information.

# Evidence guide: where evidence lives in a plan package

Use this guide to locate evidence for the checks in rubric.md; it does
not add checks or change their weights or verdict rule. Follow the
read and grading steps in procedure.md. Identify information by its
meaning, not by requiring particular headings: Cause, Change, and Test
can contain the same evidence as Diagnosis, Scope, and Test plan.

In eval mode, use only the supplied package; do not browse or inspect
outside code. In live mode, follow SKILL.md and scope.md: read the
issue-side context and posted reproduction, but assess the plan and
comment using what the drafts contain and quote. Do not fill gaps from
unrelated workspace files. For a house issue, use the repro pack as
quoted in the drafts; missing quoted evidence is still missing.

For each check, record a short quote or precise fact and its source
section. Distinguish missing information from ambiguous information;
apply the pass/fail/unclear rules in procedure.md rather than guessing.

## Diagnosis and grounding

- Where it lives (eval): the Issue and Repro evidence sections for
  observed behavior, expected behavior, environment, steps, and
  controls; the Candidate plan's cause or diagnosis for the proposed
  explanation. Thread highlights can contain claims to compare with
  the reproduction, not facts to accept automatically.
- Where it lives (live): the issue body, the student's posted repro
  comment, and the diagnosis and quoted repro evidence in plan.md;
  for a house issue, the quoted house repro pack.
- What good looks like: the stated cause accounts for the observed
  failure and control results without contradicting them. A thread
  claim alone does not establish the cause, and a plausible explanation
  must not be presented as more certain than the evidence supports.

## Scope

- Where it lives (eval): the Candidate plan's scope, changes, approach,
  and any in/out statements; these may be combined in one paragraph.
- Where it lives (live): the corresponding statements in plan.md,
  including any updated boundaries under Deviations.
- What good looks like: named files or components and explicit
  exclusions define a bounded change. Proposed edits stay within that
  boundary instead of adding unrelated cleanup or redesign. A plan
  may defer related work if it clearly states that limit.

## Executability

- Where it lives (eval): the Candidate plan's changes or approach,
  including named files, functions, callbacks, and order of work.
- Where it lives (live): the proposed files and approach in plan.md,
  read alongside the diagnosis and scope.
- What good looks like: the plan identifies where to start and what
  behavior or logic to change, with enough detail for another developer
  to begin without inventing the main approach. A file name alone does
  not explain the change, but implementation code is not required.

## Test plan

- Where it lives (eval): the Candidate plan's test statements and any
  tests listed under changes, compared with the steps, controls, and
  expected/actual results in Repro evidence.
- Where it lives (live): plan.md's test plan and quoted reproduction,
  compared with the student's posted repro or the quoted house pack.
- What good looks like: a manual or automated check reruns the original
  reproduction or directly maps to its inputs and failing behavior,
  and names an observable expected result after the fix. An explicit
  reference to reproduction steps is sufficient when those steps are
  available. A general suite run or an assertion about an internal
  detail alone does not demonstrate that the reported bug is fixed.
  Do not assume a smoke test is automated merely from its name.

## Honesty

- Where it lives (eval): qualifications, risks, unknowns, and claims
  throughout the Candidate plan and Candidate plan comment, compared
  with Repro evidence and Thread highlights.
- Where it lives (live): plan.md's risks, unknowns, and Deviations,
  plus comment.md and the issue discussion or previously posted plan.
- What good looks like: observations are distinguished from hypotheses,
  uncertainties are stated rather than hidden, and promised outcomes
  are supported by the plan. After a build, deviations state what
  changed and why, or explicitly state that nothing changed; a blank
  section is not evidence of no deviations. Do not require completed
  build results when grading an initial plan.

## Comms

- Where it lives (eval): Candidate plan comment, compared with the
  Candidate plan, Thread highlights, and Repo facts, especially
  contribution policies and maintainer requests.
- Where it lives (live): comment.md, plan.md, the issue discussion,
  and relevant repository contribution instructions; apply scope.md's
  house rules and report voice-guide.md violations as SKILL.md directs.
- What good looks like: the comment accurately states the diagnosis,
  bounded approach, and verification without promising more than the
  plan supports. It acknowledges relevant maintainer direction and
  stated repository conventions. Do not invent a disclosure requirement
  or infer actual human authorship from a claim that text is original.

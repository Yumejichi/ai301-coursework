# Plan: issue #69 - top-level JSON array fallback

Issue: https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69
Author: Yumejichi
Status: implemented locally on `fix/69-json-array-fallback`; regression and unit tests passed. Repository type checking is blocked by the installed NumPy typing error recorded below.

## Diagnosis and reproduction evidence

My Unit 2 reproduction is posted at:
https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69#issuecomment-5882618553

It used macOS 26.6.2 (arm64), Python 3.12.8, pytest 9.1.1, and
commit `2f4e82f52efbcfcc57d65b3fa5348672163ca088` on main.
The existing test passes a JSON array containing "First feedback item"
and "Second feedback item" through the real `parse_review_output` function.
Quoted output from that reproduction:

```text
rag/generator/output_parser.py:68
>       for key, value in data.items():
E       AttributeError: 'list' object has no attribute 'items'

FAILED tests/unit/test_output_parser.py::TestOutputParser::test_json_array_fallback
1 failed in 1.04s
```

`json.loads()` successfully decodes an array into a Python list. Both
raw and fenced JSON paths currently send the decoded value directly to
`_parse_json_output`, whose dictionary loop calls `.items()`. A list
has no such method; catching JSONDecodeError does not handle this valid
JSON with an unsupported top-level type. The raw-array failure is
reproduced; the fenced-array path is implicated by source inspection
and will receive its own regression check.

## Scope

In scope: recognize top-level lists at both JSON dispatch sites in
`parse_review_output` and return the existing plaintext fallback using
the original raw input. Update the issue's regression test and add
coverage for fenced and empty arrays.

Out of scope: defining structured array-element semantics, changing
FeedbackSection, changing dictionary parsing or code-fence extraction,
handling other top-level scalar JSON types, unrelated seeded defects,
and changes to Docker, database setup, frontend, or the wider RAG pipeline.
The existing local PostgreSQL port override is setup only and must not
be included in the fix commits.

## Files to change

- `rag/generator/output_parser.py`: guard list values before either
  call to the dictionary-only parser.
- `tests/unit/test_output_parser.py`: strengthen the array regression,
  add focused fallback coverage, and remove only issue #69's xfail marker.

## Approach

1. Capture the existing focused reproduction output before editing.
2. After each successful JSON decode in `parse_review_output`, check
   whether the result is a list; if so, return
   `_parse_plaintext_output(raw)` before calling `_parse_json_output`.
   Leave object handling and JSONDecodeError fallback behavior unchanged.
3. Strengthen `test_json_array_fallback` to require exactly one
   FeedbackSection named `general_feedback`, with content equal to the
   original input, confidence 0.7, and empty suggestions.
4. Add corresponding public-entry-point tests for a fenced array and
   an empty array, checking preservation of the full original input
   (including fences and surrounding text for the fenced case).
5. Remove the strict xfail decorator for issue #69 once the fix makes
   the regression pass, as the issue and contribution guide require.
6. Review each diff against this scope and record any changes to the
   plan under Deviations before re-running plan-check.

## Test plan

Run commands from the fork's root using its existing virtual environment.
The Unit 2 setup used `make setup` and Docker services, with PostgreSQL
mapped to host port 5434 because 5433 was occupied; retain that local
setup without committing it.

Before editing and again after the fix, rerun the exact Unit 2 command:

```bash
.venv/bin/python -m pytest tests/unit/test_output_parser.py::TestOutputParser::test_json_array_fallback --runxfail -v --tb=long
```

Before: the quoted list `.items()` AttributeError and a failed test.
After: the same test passes without an exception; strengthened assertions
verify one fallback section preserves both feedback items in the raw text.
Save actual command output from both runs rather than claiming success.

Then run the regression normally to confirm it is a regular pass,
not XFAIL or XPASS(strict), and run the complete parser test file:

```bash
.venv/bin/python -m pytest tests/unit/test_output_parser.py::TestOutputParser::test_json_array_fallback -v
.venv/bin/python -m pytest tests/unit/test_output_parser.py -v
```

Expected: raw, fenced, and empty arrays return the documented plaintext
section; existing raw/fenced objects, malformed JSON, and plain-text
checks still pass. The fenced case must preserve surrounding text, and
an empty array must preserve `[]` as content rather than silently drop it.

Before the later push/PR, run the contribution guide's required checks:

```bash
make check
make test-unit
```

`make check` includes formatting, so inspect any resulting diff and keep
unrelated changes out of the fix. Complete the remaining repository CI
checks for the Unit 4 PR and report any failures truthfully.

## Risks and unknowns

- Plaintext fallback preserves array content but does not turn each
  array element into a separately structured section; that is an
  intentional narrow behavior choice, not evidence of an agreed array schema.
- Both JSON paths need the same guard; testing only raw input would miss
  a fenced-array regression.
- The original regression only checks that the result is a list, so it
  needs stronger assertions to prevent silent data loss.
- Keeping the strict xfail marker after fixing the test would fail CI.
- Non-array scalar JSON values remain outside this issue's scope.
- Post-fix results are recorded below; successful type checking is not claimed.

## Deviations

The implementation followed the planned two-file approach. Regression coverage
also includes mixed-type arrays and unlabeled code fences to exercise the same
fallback without changing its scope. The original xfail marker was removed.
No dictionary behavior, scalar handling, or environment configuration was changed.

Validation: the original reproduction now passes; all 25 parser tests pass;
`make test-unit` reports 382 passed and 52 expected failures. Ruff and Black
pass. `make check` stops during mypy in the installed NumPy type definitions:
`numpy/__init__.pyi:737: error: Type statement is only supported in Python
3.12 and greater [syntax]`. This dependency/tooling issue remains unresolved;
no green type-check or full CI result is claimed. The posted plan still
accurately describes the implemented behavior.

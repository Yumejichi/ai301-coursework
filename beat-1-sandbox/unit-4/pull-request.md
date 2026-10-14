# Unit 4 — Test and Submit

## Your pull request

**Pull request**
https://github.com/codepath/pathreview-ai301-fa26-s3/pull/200

**Branch**

`fix/69-json-array-fallback`

## Eval iterations

**Run history**

1. An initial harness launch using the system Python stopped before grading because that interpreter did not support `Path | None`. No packages were graded and no score was produced. Subsequent runs used the Path Review virtual environment's Python 3.12.
2. First full run: **13/20**. All reject packages matched, but clear-accept was 0/7, so the category floor failed. The rubric over-required raw logs and the grader also imported live-course checks into unrelated packages.
3. After revising evidence rules and explicitly limiting Path Review commands to live mode, partial run `--only pkg-02,pkg-05,pkg-08,pkg-11,pkg-13,pkg-16,pkg-19,pkg-01,pkg-04,pkg-20`: **9/10**. pkg-16 still differed. Both standards-wall canaries (pkg-01, pkg-20) and the not-tested canary (pkg-04) stayed correct. A partial run does not establish the full-set bar.
4. With no further rubric changes, final full run: **20/20**, matching the submitted eval-run.txt. Categories: clear-accept 7/7, not-tested 4/4, silent-drift 4/4, standards-wall 2/2, unreviewable 3/3. The change in pkg-16 between runs shows that individual model judgments can vary even with unchanged instructions.

**Package analysis**

`pkg-02`: the final rubric verdict was **accept** and the gold label was **accept**. The first run rejected it for Observable validation. The package actually shows the failed-save reproduction before and after: the recording changes from an empty string after a failed write to preserved `IMPORTANT OUTPUT` text. Its regression test also checks that a successful save clears the recording. Its suite result is summarized as "`pytest tests/ -q` passes (1462 passed, 12 skipped)." The revised rubric accepts that named-suite summary when it accompanies decisive reproduction evidence. It does not require extra lint/typecheck commands that the package never asks for, or separate save_html/save_svg cases beyond the stated test plan. The diff changes all three planned save methods and adds the required changelog entry.

**Check rationale**

The following is the exact check row in the submitted rubric.md:

| Observable validation | Repro and plan test plan compared with test-evidence commands and results | A reproducible issue-specific action or command is paired with a concrete before/after observation that distinguishes the bug from the intended outcome; relevant controls and the named repository suite have recorded outcomes. Precise textual UI observations and command-linked result summaries count, even without a raw terminal transcript. A named suite plus a reported outcome can establish suite execution when accompanied by decisive repro evidence; a bare “tests pass” alone or only an unrelated happy-path test cannot. Require only checks named by that package’s plan or repository, never Path Review commands for other repositories. Disclosed bounded failures or omissions can pass when the demonstrated result is clear and broader success is not claimed. Require separately promised test fixtures to exist, but do not invent exhaustive cases beyond the plan. | required |

I revised this check because the first run confused absence of full terminal logs with absence of meaningful evidence. The final wording distinguishes a concrete reproduction and a named suite result from a bare assurance that things work. It also makes the source of required checks explicit, preventing Path Review's commands from being applied to every evaluation repository. The worksheet's lesson remains useful: claims must have specific support, and a test fixture is not proof that it ran. For the actual PR, I included the commands and relevant output excerpts.

**Trade-offs**

Accepting precise recorded summaries improves handling of UI observations and compact test reports, but gives up the stronger auditability of full logs. A fabricated yet detailed summary could pass; this skill assesses the supplied evidence rather than independently proving it was produced by a real run. To guard against becoming too permissive, I reran pkg-04 (bare testing assertions) and pkg-01/pkg-20 (repository standards) with the seven affected cases. They remained reject, and the confirming full run matched every category. pkg-16 changed from reject in the partial run to accept in the final run without a file change, so a perfect final score is not a guarantee of deterministic grading.

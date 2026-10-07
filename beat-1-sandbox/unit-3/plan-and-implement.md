# Unit 3 — Plan and Build

Path: `beat-1-sandbox/unit-3/plan-and-implement.md`

Record of your plan, the branch you built it on, and the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in the
repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Posted upstream

**GitHub username**

YisacTW

**Plan comment**

[Posted Section 3 plan comment](https://github.com/codepath/pathreview-ai301-fa26-s3/issues/73#issuecomment-6028955483)

> The reproduction shows a narrow setup-file mismatch: `README.md` asks
> for `OPENROUTER_API_KEY`, while `.env.example` has no entry for it. The
> plan changes only `.env.example` by adding `OPENROUTER_API_KEY=` under
> the OpenAI placeholder. It keeps the existing provider-options comment
> because the reproduction does not establish that `openrouter` is a
> supported provider value. Verification copies the example to a
> temporary `.env`, checks for the key, and runs a whitespace check.

---

## Your branch

**Branch**

fix/73-env-docs

**Evidence**

**Before the change**

```powershell
Select-String -Path README.md,'.env.example','core/config.py' -Pattern 'OPENROUTER_API_KEY|OPENAI_API_KEY|LLM_PROVIDER'
Copy-Item .env.example .env
Select-String -Path .env -Pattern 'OPENROUTER_API_KEY|OPENAI_API_KEY|LLM_PROVIDER'
```

```text
Repository: codepath/pathreview-ai301-fa26-s3 (baseline commit 2f4e82f)
README.md:24: # Configure environment (add your OPENROUTER_API_KEY to .env)
.env.example:18: LLM_PROVIDER=mock
.env.example:19: OPENAI_API_KEY=sk-your-key-here
core/config.py:18: llm_provider: str = Field(default="mock")
core/config.py:19: openai_api_key: str = Field(default="")
core/config.py:20: openrouter_api_key: str = Field(default="")
.env:18: LLM_PROVIDER=mock
.env:19: OPENAI_API_KEY=sk-your-key-here
```

**After the change**

```powershell
Select-String -Path README.md,'.env.example','core/config.py' -Pattern 'OPENROUTER_API_KEY|OPENAI_API_KEY|LLM_PROVIDER'
Copy-Item .env.example .env
Select-String -Path .env -Pattern 'OPENROUTER_API_KEY|OPENAI_API_KEY|LLM_PROVIDER'
Remove-Item -LiteralPath .env
```

```text
README.md:24: # Configure environment (add your OPENROUTER_API_KEY to .env)
.env.example:18: LLM_PROVIDER=mock
.env.example:19: OPENAI_API_KEY=sk-your-key-here
.env.example:20: OPENROUTER_API_KEY=
core/config.py:18: llm_provider: str = Field(default="mock")
core/config.py:19: openai_api_key: str = Field(default="")
core/config.py:20: openrouter_api_key: str = Field(default="")
.env:18: LLM_PROVIDER=mock
.env:19: OPENAI_API_KEY=sk-your-key-here
.env:20: OPENROUTER_API_KEY=
```

The second run shows that the file contributors copy now contains the
same OpenRouter key named by the README. `git diff --check` also passed.

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

My first three-package calibration rejected `pkg-02` because my
`bounded-change` check was treating directly related sibling guards
and regression coverage as scope creep. I changed that check from
requiring “one focused change” to allowing “directly related guards,
sibling sites, or regression coverage needed to prevent the same
failure.” The final harness run reported: `agreement: 19/20 scored
items  (bar: 18/20: PASS)` and `run written to eval-run.txt`.

**Package analysis**

The final run disagreed only on `pkg-14`: the gold verdict was
`accept`, while my tool returned `reject` after marking
`diagnosis-grounded` and `honest-unknowns` as failed. The other
clear-accept packages were mostly correct: `clear-accept 6/7`. Every
reject-family category was fully correct: `scope-creep 4/4`,
`thread-convention 2/2`, `unbuildable 3/3`, and `wrong-cause 4/4`.

**Check rationale**

I kept the diagnosis rule strict because it checks whether “the stated
cause explains the reproduced behavior without contradicting it or
claiming more than the evidence proves.” I narrowed the scope rule so
it allows necessary safeguards and tests but still excludes “unrelated
redesigns, broad refactors, and unverified work.” I also required a
verification result that “would distinguish a fixed state from the
reproduced failure,” so a plan cannot pass just by promising a vague
test.

**Trade-offs**

The trade-off is caution versus flexibility. The rules reliably caught
the bad-plan families, but the final run held one staff-approved plan
because it did not give enough confidence in its diagnosis and
unknowns. I kept that conservative standard because a plan with an
unsupported cause can lead to the wrong change. The bounded-change
revision avoids the opposite mistake: rejecting a small, necessary
regression test or a directly related guard as if it were a redesign.

---

Related paths: `plan.md` and `eval-run.txt` in this directory; your skill's files in
`tools/plan-check/`.

# Unit 2 — Claim and Reproduce

Path: `beat-1-sandbox/unit-2/reproduction.md`

Record of your claim and reproduction on the issue you chose in Unit 1, and of the
evaluation runs that produced `eval-run.txt`. This file is graded at the path above; a copy
kept anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your identity upstream

**GitHub username**

YisacTW

---

## Posted upstream

**Claim comment**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/73#issuecomment-5885668428

Hi, I’m taking a look at the setup mismatch in #73: the README says to
set `OPENROUTER_API_KEY`, while `.env.example` lists `OPENAI_API_KEY`
and only `mock` and `openai` as provider options. I’ll check the setup
from a fresh clone and post a reproduction report with my environment,
steps, and what I find.

**Reproduction comment**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/73#issuecomment-5885707117

Environment: Windows 11 (10.0.26200), Python 3.9.13, and a fresh clone
of my fork, `YisacTW/pathreview-ai301-fa26-s1`, at commit
`f89c06fc3ff292df2a04a39ac51319d32a76b779`.

Steps from the repository root:

```powershell
git clone https://github.com/YisacTW/pathreview-ai301-fa26-s1.git pathreview
cd pathreview
git rev-parse --short HEAD
Select-String -Path README.md,'.env.example','core/config.py' -Pattern 'OPENROUTER_API_KEY|OPENAI_API_KEY|LLM_PROVIDER'
```

Expected: the setup instruction in `README.md` and the example
environment file should give compatible LLM API-key and provider setup
details, since both are the documented starting point for a new local
environment.

Actual: the command showed this mismatch:

```text
README.md:24: # Configure environment (add your OPENROUTER_API_KEY to .env)
.env.example:18: LLM_PROVIDER=mock
.env.example:19: OPENAI_API_KEY=sk-your-key-here
core/config.py:18: llm_provider: str = Field(default="mock")
core/config.py:19: openai_api_key: str = Field(default="")
core/config.py:20: openrouter_api_key: str = Field(default="")
```

`core/config.py` supports both API-key settings, but the two setup
files point a new contributor toward different configuration names.
This matches the documentation/configuration mismatch described in the
issue.

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

1. **20/20 — PASS.** The first completed full evaluation matched every
   gold label and every category.
2. **20/20 — PASS.** I ran one confirming full evaluation with
   `--save-run`; its agreement line matches the committed
   `eval-run.txt`.

**Package analysis**

For `pkg-02`, my rubric returned **reject**, which matched the gold
label of **reject**. The report looked detailed at first, but its
command used a different range format and produced a command-line
validation error. The issue described a panic with exit 101 instead.
Because the output showed a different failure, the report did not prove
the behavior in the issue.

**Check rationale**

My current `behavior-faithful` check says: “The artifact shows the
same behavior the issue describes, or the report honestly shows that
the behavior could not be reproduced. A different error, adjacent
behavior, or unsupported explanation fails this check.”

I wrote it this way because a report can sound confident while proving
something else. The check compares the actual output to the issue's
reported behavior instead of rewarding a report for being long or
well-formatted. It also leaves room for an honest cannot-reproduce
result when the steps and evidence are clear.

**Trade-offs**

The behavior check can hold a report that is related to the same part of
a project but reaches a different error. I chose that trade-off because
the purpose of a repro report is to show the maintainer the behavior
they need to investigate, not just a nearby problem. If I cannot reach
the exact behavior, I would rather post an honest cannot-reproduce with
the evidence than label an adjacent failure as a match.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/repro-check/`.

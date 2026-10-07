# Plan for issue #73: align the example environment setup

Repository: `codepath/pathreview-ai301-fa26-s3`

## Diagnosis

The reproduction showed that the README tells a new contributor to add
`OPENROUTER_API_KEY` to `.env`, while `.env.example` only supplies an
`OPENAI_API_KEY` placeholder and lists `mock` and `openai` as its
provider options. `core/config.py` declares an `openrouter_api_key`
field, so the example file is missing the configuration name that the
README tells users to set. The reproduction establishes inconsistent
setup guidance. It does not establish which providers work at runtime
or require a change to application code.

## Scope

In scope: update the LLM section of `.env.example` to include an empty
`OPENROUTER_API_KEY` entry next to the existing OpenAI placeholder.

Out of scope: changing `core/config.py`, provider selection logic,
model defaults, API behavior, or unrelated setup documentation. This
change fixes the missing example entry rather than choosing or testing
the application's runtime provider behavior.

## Implementation

1. Create `fix/73-env-docs` from the `main` branch of my fork.
2. In `.env.example`, add `OPENROUTER_API_KEY=` below
   `OPENAI_API_KEY=` without changing the documented provider options.
3. Review the diff to confirm the branch changes only the example
   environment setup and does not introduce a real key or unrelated
   configuration edits.

## Verification

First, preserve the original reproduction result: the README names
`OPENROUTER_API_KEY`, while the old `.env.example` has no matching
entry. After the edit, copy `.env.example` to a temporary `.env` and
search both files for `OPENROUTER_API_KEY`, `OPENAI_API_KEY`, and
`LLM_PROVIDER`. The check passes when the copied file contains an
empty `OPENROUTER_API_KEY` line, matching the README's setup
instruction. The existing provider comment stays unchanged because
the reproduction does not show that `openrouter` is a supported
provider value. Remove the temporary `.env` afterward so no local
configuration file remains.

## Deviations

No deviation: the built change followed this plan and stayed within the
single `.env.example` LLM section.

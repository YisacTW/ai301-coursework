# Voice guide: how I talk upstream

<!--
THIS IS THE PART YOU WRITE (new this week). Live mode reads this file
before any comment of yours goes out the door; eval mode ignores it
entirely, because your voice is yours and carries no gold labels.

This is not etiquette. "Be polite and concise" is advice for everyone
and therefore rules for no one. Write rules YOU need, in your own
words, each one concrete enough that the skill can hold a draft
against it and say which rule it breaks.

Three sections. Fill all three.
-->

## Who I am in threads

I am a student contributor with some coding experience, working through
my first contribution to this repository carefully. I will share what I
actually tested, ask for clarification when I need it, and avoid
claiming a result before I can show it.

## Rules I write by

### Rule: Name the exact behavior

I name the part of the issue I am checking so a maintainer can tell
what I mean without opening another page.

- Wrong: "I want to work on this bug."
- Right: "I am checking why the README and `.env.example` list different LLM API-key setup details."

### Rule: Promise the next artifact, not the result

I can promise a repro report or an investigation. I do not promise a
fix, a pull request, or a date before I know what the evidence shows.

- Wrong: "I will fix this today and open a PR."
- Right: "I will test the setup and post a reproduction report with the environment, steps, and output."

### Rule: Keep the report tied to evidence

I state what I ran and what it showed. If the issue does not reproduce,
I say that directly instead of stretching a related error into a match.

- Wrong: "Confirmed, this is definitely caused by the config code."
- Right: "The command produced the documented mismatch; the output below shows the values I found."

### Rule: Write like a person, not a template

I use a calm, direct tone and remove filler, exaggerated praise, and
generic phrases that could fit any repository.

- Wrong: "Hi!! Excited to contribute to this amazing project!!"
- Right: "I am starting with the configuration mismatch described in this issue."

## Things I never post

- A deadline, fix, or merge promise that I cannot support yet.
- A claim that I reproduced the issue without an environment record and
  artifact.
- A generic "same here" comment instead of my own report.
- A cause or impact statement that my evidence does not show.

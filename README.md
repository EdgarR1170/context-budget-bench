# Context Budget External Bench

Independent, public task tests for context-compression experiments.

This repo contains **no Clowder source and no credentials**. It only pins public
Exercism tasks from Aider's polyglot benchmark and runs their repository-owned
tests in GitHub Actions.

## Why

Self-authored probes are not independent validation. The first external layer is
a small JavaScript subset from
[Aider-AI/polyglot-benchmark](https://github.com/Aider-AI/polyglot-benchmark),
itself sourced from Exercism. Pass/fail comes from the exercise's Jest tests,
not from our own keywords.

## Tasks

- affine-cipher
- binary
- beer-song
- book-store
- connect

Pinned commit: `7e0611e77b54e2dea774cdc0aa00cf9f7ed6144f`

## Proof mode

The workflow first validates the harness by using each exercise's
`.meta/proof.ci.js` as the solution. No model is called. This proves the task
selection and test runner work before any context experiment.

## Model mode

Put a candidate solution at `solutions/<task>.js`. The workflow will use it
instead of the proof file. This keeps model API keys out of GitHub Actions:
solutions are generated locally and committed; GitHub only runs tests.

## Run

Actions → **Aider JS external validation** → Run workflow.

Or locally (Linux/macOS, for harness debugging only):

```bash
bash scripts/run-aider-js.sh
```

Do not execute untrusted generated code on a host without a disposable
container/runner.

## Attribution

Exercises are from Exercism language tracks, used via Aider's polyglot
benchmark. Each exercise carries its own MIT license.

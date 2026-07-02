# runx escalation-judge walkthrough

This is a short public walkthrough for trying a runx skill from the hosted registry.

runx is an open-source runtime for portable skills and governed execution:

- Project site: https://runx.ai
- Source repository: https://github.com/runxhq/runx

## What this demonstrates

The example uses the `escalation-judge` skill published at:

https://runx.ai/x/reluctantskeptic/escalation-judge@sha-a33725c68a9e

The skill turns a structured support/escalation evidence packet into a bounded decision:

- whether to escalate
- escalation severity
- rationale tied to the evidence
- follow-up actions
- a receipt-verifiable run output

## Reproduce the smoke path

Use runx CLI 0.6.6 or newer.

```bash
runx --version
runx install reluctantskeptic/escalation-judge@sha-a33725c68a9e
runx run reluctantskeptic/escalation-judge@sha-a33725c68a9e \
  --input skills/escalation-judge/fixtures/evidence.json
```

The registry page links the published skill metadata and source. The related public pull request is:

https://github.com/runxhq/runx/pull/208

## Why this is useful

The runx model makes a small automation artifact easier to inspect than an opaque script:

- the skill has an explicit `X.yaml` contract
- the source is pinned to a public commit
- a reviewer can inspect fixture input and expected output
- a receipt can be verified after execution
- the same skill can be installed by another operator without copying local files

This is not star proof or reciprocal promotion. It is a public README/example that shows one concrete runx registry workflow and links readers to the upstream project.

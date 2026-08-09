---
title: "Retrieve-then-Steer: Online Success Memory for Test-Time Adaptation of Generative VLAs"
date: 2026-05-10
topic: VLA
tags: [vla, test-time-adaptation, memory, flow-matching, vla-posttraining]
source: https://arxiv.org/abs/2605.10094
venue: "arXiv"
---

## Summary

This paper proposes a non-parametric test-time adaptation scheme for frozen generative VLAs: an online memory stores progress-calibrated successful observation-action segments collected during deployment, and at inference the policy retrieves state-relevant chunks and injects them as a confidence-adaptive guidance prior into a flow-matching action sampler. It targets the same general problem as the vault's already-logged "Retrieve, Don't Retrain" but via a distinct online-memory-plus-guidance mechanism rather than cross-embodiment retrieval.

## Key Contributions

- An online success-memory buffer populated during deployment (not fixed at training time), so the retrieval set grows as the robot succeeds at tasks.
- A "progress calibration" step that scores stored segments by how much task progress they represent, used to weight retrieval relevance.
- A confidence-adaptive guidance strength that scales how strongly retrieved segments influence the flow-matching sampler, rather than applying a fixed blending weight.

## Strengths

- Building the memory from the robot's own successful rollouts (rather than a static human-curated dataset) means the adaptation signal is directly grounded in what actually works on the deployed hardware/environment.
- Confidence-adaptive guidance strength is a sensible mitigation against the failure mode where retrieval dominates and drowns out the base policy's own (possibly better) prediction on in-distribution states.

## Weaknesses

- A memory that only grows from successes has no mechanism described for correcting from failures, so it may reinforce a narrow set of successful strategies rather than broadening competence — the paper doesn't appear to address catastrophic forgetting or memory staleness as the environment shifts.
- "Progress calibration" requires some notion of task progress at storage time, which for open-ended or long-horizon tasks may be as hard to define as the reward-shaping problem it's implicitly trying to avoid.
- Real-time retrieval-and-guidance adds inference latency on top of flow-matching sampling, and no latency numbers are available from the abstract-level description.

## Open Questions

- How does the method behave when the memory becomes large — does retrieval quality/latency degrade, and is there a forgetting or pruning strategy?
- Does success-only memory eventually cause mode collapse onto a narrow behavioral repertoire?
- How does this compare quantitatively to "Retrieve, Don't Retrain" and other test-time-adaptation baselines on shared benchmarks?

## Significance

Represents the fast-growing cluster of 2026 work using retrieval/memory mechanisms as a lightweight alternative to fine-tuning for adapting frozen VLAs at deployment time — directly relevant to the digest's VLA post-training priority theme.

## Links

- [Paper](https://arxiv.org/abs/2605.10094)

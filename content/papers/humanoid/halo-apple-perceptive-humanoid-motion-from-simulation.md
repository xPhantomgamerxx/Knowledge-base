---
title: "HALO: Perceptive Humanoid Motion from Simulation"
date: 2026-11-04
topic: Humanoid
tags: [humanoid, vla-posttraining, synthetic-data, sim-to-real, whole-body-control, zero-shot-transfer]
source: https://arxiv.org/abs/2611.06908
venue: "arXiv"
---

## Summary

HALO is an Apple-authored humanoid autonomy system that pairs a procedurally-generated-home simulation pipeline with a vision-language-motion data synthesis process to teach a Unitree G1 a repertoire of physical skills (sitting on chairs, navigating to named objects, stepping through half-open doors, crouching/crawling under tables, pushing boxes) without ever training on real-home data. It matters because it is a concrete, quantified test of pure sim-to-real zero-shot transfer for humanoid whole-body skills, with all perception and control models running onboard, and because the authors explicitly show how performance scales (and degrades) with simulated environment diversity.

## Key Contributions

- A data-synthesis pipeline that generates vision-language-motion tuples across roughly a thousand procedurally generated home environments, scaling the training corpus with compute rather than human teleoperation or labeling effort.
- A humanoid autonomy stack (perception, task orchestration, and whole-body motion execution) deployed end-to-end on a Unitree G1 running on local onboard compute, driven by natural-language task requests.
- Zero-shot sim-to-real evaluation across six unmapped, never-seen-during-training real-world environments: 360 single-task trials (six skills × ten trials × six environments) with a reported 91% aggregate success rate.
- An explicit ablation showing task success (sitting) scaling with the number of distinct training environments: reported around 84% with ~1,000 environments, dropping to ~64% with 10 and ~43% with a single training environment — direct evidence that environment diversity, not just data volume, drives transfer.
- Multi-skill chained-task evaluation (e.g., crouch → walk to box → push box) in a single real room, averaging around 70% across sequences, with a worst case near 50%.

## Strengths

- The environment-diversity ablation (1000 vs. 10 vs. 1 environments) is a genuinely informative data point for the broader "how much simulated diversity is actually needed" question in sim-to-real humanoid learning, rather than just reporting a headline number.
- Zero-shot transfer to six genuinely unseen real environments (not just held-out simulation) is a meaningfully strict evaluation protocol for whole-body humanoid autonomy.
- Full onboard execution (perception + orchestration + motion on the robot itself) is a real systems contribution, not just a policy-learning result in isolation.

## Weaknesses

- The chained multi-skill evaluation was reportedly run in only a single real room, so the headline 91% single-skill number and the much weaker ~70%/50% chained numbers are not evaluated under comparable real-world diversity — the paper's own strongest claim (91%) is also its least stress-tested for compounding, out-of-view failure modes.
- No comparison against other published humanoid autonomy or VLA systems on matched tasks; all results are self-reported on Apple's own pipeline and robot, with no third-party or cross-lab verification.
- The skill repertoire is still fundamentally human-authored: each new skill requires a person to write instructions and define reference motion/keyframes, so the system does not yet address open-ended skill acquisition — it scales environment diversity, not task diversity, autonomously.
- Reported failure analysis attributes chained-task drops largely to the next subtask's target being out of view when a sub-skill starts, suggesting the perception-to-planning handoff is still fairly brittle outside of clean single-skill setups.

## Open Questions

- How does the 1000-environment diversity result generalize to skills requiring finer dexterous manipulation rather than locomotion/whole-body transitions (sitting, crouching, pushing)?
- Would the proposed fixes for chained-task failures (search and turn-in-place behaviors when a target is out of view) actually close the gap to single-skill success rates, or merely patch the specific failure mode observed?
- How does this procedurally-generated-home approach compare quantitatively, on the same robot and skills, to approaches that instead scale on real egocentric human video (the other major direction for humanoid data scaling)?

## Significance

HALO is a notable data point in the "what kind of data actually enables humanoid sim-to-real transfer" debate: it isolates environment diversity as a lever distinct from raw data volume, and does so with a fully onboard, zero-shot real-world evaluation rather than simulation-only benchmarks, from a major new entrant (Apple) into humanoid foundation-model research.

## Links

- [Paper](https://arxiv.org/abs/2611.06908)
- [Project Page](https://apple-aiml-research.github.io/ml-halo/)

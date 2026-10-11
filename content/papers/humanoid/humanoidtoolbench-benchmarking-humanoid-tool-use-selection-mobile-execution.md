---
title: "HumanoidToolBench: Benchmarking Humanoid Tool Use from Selection to Mobile Execution"
date: 2026-10-01
topic: Humanoid
tags: [humanoid, robotics, benchmark, tool-use, manipulation, evaluation]
source: https://arxiv.org/abs/2610.02089
venue: "arXiv"
---

## Summary

HumanoidToolBench is a new benchmark that jointly evaluates whether a humanoid can select an appropriate tool and then successfully use it while moving through a scene, combining 18 task conditions (3 scenarios × 3 execution levels × 2 tool-set modes) with ToolBook, a dataset of 3.1k demonstrations collected both in simulation and on a real Unitree G1.

## Key Contributions

- A benchmark design that explicitly separates and jointly tests tool *selection* from stationary and mobile tool *execution*, which prior tool-use benchmarks (largely VQA-style or fixed-base-arm) do not combine.
- Three task scenarios (BallMove, BallRetrieve, IceBreak) crossed with three execution levels (selection, stationary use, mobile use) and two tool-set modes, yielding 18 evaluation conditions.
- ToolBook: 3.1k demonstrations spanning simulation and real-world Unitree G1 execution.
- Evaluation of seven simulated policies and three real-robot policies, plus targeted probes of GR00T N1.7 showing degraded tool-selection accuracy on unseen tools and continued execution under unrelated/irrelevant instructions.
- Open-source evaluation toolkit and project resources.

## Strengths

- Fills a genuine gap: most existing tool-use evaluation is either purely visual/linguistic (VQA) or confined to fixed-base manipulators, neither of which stresses the combined mobility + manipulation + reasoning loop that real humanoid tool use requires.
- The inclusion of a real humanoid (Unitree G1) alongside simulation gives the benchmark practical credibility beyond a purely simulated leaderboard.
- The GR00T N1.7 probes (lower selection accuracy on unseen tools, failure to abstain under irrelevant instructions) surface a concrete, actionable weakness in a widely-used foundation model rather than just reporting an aggregate score.

## Weaknesses

- Only three task scenarios (BallMove, BallRetrieve, IceBreak) is a fairly narrow slice of real-world tool use; it's unclear how representative these are of broader household/industrial tool tasks.
- 3.1k demonstrations is modest for training generalizable policies from scratch, positioning ToolBook more as an evaluation/fine-tuning set than a primary pretraining corpus.
- Evaluating only ten total policies (seven sim + three real) limits how strong the benchmark's claims about "the field" can be until more models are tested against it.

## Open Questions

- Will HumanoidToolBench see adoption as a standard evaluation alongside SIMPLE, Labimus, and other humanoid manipulation benchmarks already in this vault, or remain a narrower niche test?
- How do the identified GR00T N1.7 failure modes (unseen-tool selection, irrelevant-instruction execution) generalize to other VLA foundation models?
- Can the benchmark's task set be extended to cover tools requiring finer force control or multi-step tool combinations (e.g., assembling a tool from parts)?

## Significance

Tool use is a distinctly human-like capability that current humanoid foundation models handle unevenly, and a benchmark that forces models to jointly reason about tool selection and mobile execution — and that exposes concrete failure modes in a flagship model like GR00T N1.7 — gives the field a sharper target for closing that gap.

## Links

- [Paper](https://arxiv.org/abs/2610.02089)
- [GitHub](https://github.com/SNU-PI/HumanoidToolBench)

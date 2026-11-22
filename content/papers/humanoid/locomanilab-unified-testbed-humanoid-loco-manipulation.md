---
title: "LocoManiLab: A Unified Testbed for Data, Policies, Controllers, and Deployment in Humanoid Loco-Manipulation"
date: 2026-10-30
topic: Humanoid
tags: [humanoid, benchmark, loco-manipulation, vla, world-action-model, whole-body-control]
source: https://arxiv.org/abs/2610.30876
venue: "arXiv"
---

## Summary

LocoManiLab is a unified evaluation testbed that connects demonstration acquisition, policy learning, controller execution, and physical deployment for humanoid loco-manipulation, aiming to let researchers disentangle how much of a system's performance comes from its policy versus its underlying whole-body controller. It evaluates twelve baseline policies — ten pretrained VLAs (including π0.5), world-action-model baselines (e.g. Fast-WAM), and a Diffusion Policy imitation-learning baseline — all run under a shared whole-body controller, plus a separate controller-ablation study varying the controller across two VLA policies and five controllers.

## Key Contributions

- A benchmark explicitly designed to separate policy quality from controller quality in humanoid loco-manipulation, a confound that most single-system humanoid papers don't isolate.
- 132 compositional tasks chaining two to four atomic primitives (often linking navigation and manipulation) alongside atomic-task evaluation, pushing beyond single-skill benchmarks.
- Matched sim/real task pairs (three tasks built to mirror real-world setups) enabling direct sim-to-real comparison for a subset of the benchmark rather than sim-only or real-only evaluation.
- Robustness and generalization axes (unseen tasks/scenes, visual perturbations) on top of raw task completion and motion-quality metrics.

## Strengths

- Including a shared-controller comparison across ten+ VLA baselines is a genuinely useful control that most humanoid VLA papers skip, since they usually report results on their own custom stack.
- The controller-ablation study (two VLAs × five controllers) is a direct, needed data point for a question this vault has flagged repeatedly: how much of reported humanoid manipulation performance is actually attributable to the whole-body controller rather than the high-level policy.
- Covers both atomic and long-horizon compositional tasks, which better reflects deployment-relevant behavior than isolated skill benchmarks.

## Weaknesses

- Public summaries available at the time of this note do not surface the actual leaderboard numbers (per-policy success rates, controller rankings) — only the benchmark design is confirmed; the headline findings require reading the full PDF.
- Only three tasks have matched sim/real pairs, so the benchmark's sim-to-real transfer claims rest on a small slice of the full 132-task suite.
- As with most new benchmarks, independent adoption/replication by groups other than the authors remains to be seen.

## Open Questions

- Which controller/policy combinations actually win, and does the ranking order change between simulation and the matched real tasks?
- Does the benchmark reveal that some "state of the art" VLA policies in prior papers were effectively controller-bottlenecked rather than policy-bottlenecked?
- Will the benchmark and task suite be open-sourced for community use, or is it primarily an internal evaluation framework described in the paper?

## Significance

A controller-vs-policy disentangling benchmark addresses a real methodological gap in humanoid loco-manipulation research, where it is often unclear whether reported gains come from a better policy or a better underlying whole-body controller — useful infrastructure for the field even before its specific leaderboard results are digested.

## Links

- [arXiv abstract](https://arxiv.org/abs/2610.30876)
- [arXiv PDF](https://arxiv.org/pdf/2610.30876)

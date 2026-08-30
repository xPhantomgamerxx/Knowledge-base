---
title: "RoboDojo: A Unified Sim-and-Real Benchmark for Comprehensive Evaluation of Generalist Robot Manipulation Policies"
date: 2026-07-04
topic: VLA
tags: [benchmark, evaluation, sim-to-real, isaac-sim, leaderboard]
source: https://arxiv.org/abs/2607.04434
venue: "arXiv"
---

## Summary

RoboDojo is a unified benchmark combining 42 simulation tasks (in Isaac Sim) and 18 real-world tasks to comprehensively evaluate generalist robot manipulation policies along five dimensions — generalization, memory, precision, long-horizon execution, and open-vocabulary instruction following — plus a reproducible real-world evaluation system (RoboDojo-RealEval) with remote cloud access. It responds to the field's dual problem: simulation benchmarks are scalable but miss physical deployment challenges, while real-world evaluation is reproducible-hostile, costly, and slow.

## Key Contributions

- A five-dimension evaluation taxonomy (generalization, memory, precision, long-horizon, open-vocabulary) applied consistently across both simulation and real-world task suites, rather than treating sim and real as separate, incomparable benchmarks.
- Heterogeneous parallel simulation in Isaac Sim for large-scale, throughput-efficient sim evaluation.
- RoboDojo-RealEval: a reproducible real-world evaluation system with remote cloud access, addressing the reproducibility problem that plagues most real-robot benchmarking (different labs, different hardware, non-comparable results).
- XPolicyLab: a unified policy development/deployment infrastructure allowing a policy to be integrated once and evaluated across both the simulation and real-world settings with minimal adaptation — and used to integrate and benchmark 30 existing policies on a public leaderboard.

## Strengths

- The combination of a large sim task suite (42 tasks) with a non-trivial real-world suite (18 tasks) under one consistent evaluation taxonomy is a substantial engineering and organizational undertaking that fills a genuine gap.
- Remote-access reproducible real-world evaluation is a meaningful step toward solving the "different labs can't compare real-robot numbers" problem that has long plagued the field.
- Integrating and publicly benchmarking 30 existing policies via XPolicyLab immediately makes the benchmark useful as a community reference rather than requiring each new paper to re-implement comparisons from scratch.

## Weaknesses

- Remote-access real-world evaluation introduces its own dependencies (network latency for closed-loop control, availability/queueing on shared physical hardware, hardware drift over time) that could affect the fidelity or throughput of "real-world" results compared to co-located real-robot testing.
- A five-dimension taxonomy is a useful organizing structure, but the paper's own task design choices determine what counts as "long-horizon" or "precision" — the extent to which these categories generalize as accepted community standards (versus one group's particular operationalization) remains to be seen.
- With 30 integrated policies and a public leaderboard, there is a risk of benchmark-driven overfitting over time (methods tuned specifically to RoboDojo's task distribution rather than manipulation generally), a common failure mode of popular leaderboards.

## Open Questions

- How well do rankings on RoboDojo's simulation suite correlate with rankings on its own real-world suite — i.e., does strong sim performance actually predict real-world performance within this benchmark, which would validate the "unified" framing?
- What is the practical cost (compute, time, physical robot access) for a new research group to run the full RoboDojo evaluation, and does that limit adoption to well-resourced labs?
- How will the benchmark handle policy updates and prevent leaderboard gaming/overfitting as it becomes an established comparison point?

## Significance

RoboDojo addresses one of the most persistent structural problems in robot learning research — the lack of a shared, reproducible, sim-and-real evaluation standard — and its remote real-world evaluation infrastructure plus public 30-policy leaderboard could make it a reference benchmark akin to what standardized benchmarks have done for other subfields of ML.

## Links

- [Paper](https://arxiv.org/abs/2607.04434)
- [GitHub](https://github.com/RoboDojo-Benchmark/RoboDojo)

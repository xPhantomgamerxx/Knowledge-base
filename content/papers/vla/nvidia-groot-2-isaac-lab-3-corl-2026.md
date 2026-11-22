---
title: "GR00T 2 and Isaac Lab 3.0: NVIDIA's Open World-Action Model and Simulation Stack at CoRL 2026"
date: 2026-11-09
topic: VLA
tags: [humanoid, world-action-model, simulation, sim-to-real, benchmark]
source: https://blogs.nvidia.com/blog/robotics-simulation-advancements-corl
venue: "blog / CoRL 2026"
---

## Summary

At CoRL 2026, NVIDIA unveiled GR00T 2, described as an "open frontier world action model" built on NVIDIA Cosmos, together with Isaac Lab 3.0, a simulation stack update built on the Newton physics engine. NVIDIA reports 71% average success across 50 tasks from a single demonstration each, and up to 2.5x training throughput versus Isaac Lab 2.3/PhysX on a vision-based dexterous-manipulation benchmark, alongside two new benchmarks (DexBench, VABAR) built with RLWRLD and UC Berkeley.

## Key Contributions

- GR00T 2 folds a Cosmos-derived world/video model into the GR00T lineage, positioning it as a WAM rather than a pure VLA — continuing NVIDIA's push to merge generative world models with action policies for humanoid manipulation.
- Isaac Lab 3.0 switches its default physics backend to Newton, reporting large training-throughput gains, and adds LEAPP tooling aimed at easing sim-to-real policy deployment.
- Two new open benchmarks, DexBench and VABAR, target dexterity and cross-task adaptability on industrial manipulation, developed jointly with RLWRLD and UC Berkeley.
- Early industrial partners (Foxconn, Siemens, Nexuni) are cited as evaluating GR00T 2 for server manufacturing, industrial use cases, and laundry automation respectively.

## Strengths

- Benchmarking against a named baseline (Isaac Lab 2.3/PhysX) with a reported 2.5x throughput figure gives at least one concrete, falsifiable performance claim rather than a bare marketing statement.
- Pairing a model release with purpose-built open benchmarks (DexBench, VABAR) is a genuine community contribution if the benchmarks hold up to outside scrutiny, since dexterous-manipulation evaluation has lacked standardization.
- Backing from established industrial partners (Foxconn, Siemens) suggests at least exploratory real-world interest beyond demo videos.

## Weaknesses

- Nearly every headline number (71% one-shot success, the 2.5x throughput figure) is NVIDIA's own self-reported benchmark; no independent replication is available yet.
- Secondary aggregator coverage (unverified against NVIDIA's primary materials) claims an independent RoboDojo evaluation scored GR00T 2 at only ~12.8% real-world success versus NVIDIA's much higher self-reported figures, and that the headline "95% five-shot" number covers a pre-selected task subset with high baseline capability — if accurate, this would be a serious discrepancy that this note cannot confirm or refute from available sources.
- No confirmed public release date, license, or access path for GR00T 2 weights or the reported 100,000-hour training dataset was found at the time of writing; partners are described as evaluators, not confirmed production deployments.
- Isaac Lab 3.0's backend swap to Newton reportedly breaks a number of existing APIs, meaning adopters face non-trivial migration costs.

## Open Questions

- Does GR00T 2's real-world performance hold up under independent, third-party benchmarking (e.g. RoboDojo, LIBERO-style suites run by outside labs) given the conflicting secondary reports?
- When and under what license will GR00T 2 weights and the underlying dataset actually ship, and will "open" apply to weights, data, or only tooling?
- How much of the throughput gain from Newton is specific to the benchmarked dexterous-manipulation task versus general-purpose robotics simulation workloads?

## Significance

If GR00T 2's figures hold up, it is a notable step in NVIDIA's strategy of fusing world models (via Cosmos) with action policies for humanoid robots, backed by new open benchmarks — but given the gap between NVIDIA's self-reported numbers and unverified third-party claims, this release should be treated cautiously until independent evaluation is available.

## Links

- [Blog: Practice Makes Precise — At CoRL, NVIDIA and Partners Reveal How Robots Rehearse Delicate Work in Simulation](https://blogs.nvidia.com/blog/robotics-simulation-advancements-corl)
- [GR00T 2 whitepaper](https://research.nvidia.com/labs/gear/gr00t-2/assets/gr00t2_whitepaper.pdf)

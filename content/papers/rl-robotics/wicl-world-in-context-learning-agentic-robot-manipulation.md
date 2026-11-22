---
title: "World In-Context Learning for Agentic Robot Manipulation"
date: 2026-11-08
topic: RL-Robotics
tags: [vla-posttraining, in-context-learning, test-time-adaptation, world-model, agentic]
source: https://arxiv.org/abs/2611.12885
venue: "arXiv"
---

## Summary

World In-Context Learning (WICL) keeps a frozen policy's weights untouched and instead lets it "rehearse" a new task in a simulator built from the current scene before acting, storing what it learns from rehearsal feedback as a retrievable "Task Memory" in context rather than in weights — aimed at letting a single demonstration transfer across scenes, domain shifts, and even embodiments without fine-tuning.

## Key Contributions

- A rehearsal loop (WICL) in which a frozen model takes a single demonstration, replays/tests the task in a simulated reconstruction of the current scene, and folds the resulting feedback into its context instead of updating any weights.
- RoboScript, a modular infrastructure implementing WICL that maintains a "Task Memory" of accumulated in-context knowledge and enforces isolation between the deployment data stream and what gets written into the task memory.
- Claimed results showing single-demonstration-plus-rehearsal performance matching trained policies in clean scenes, and outperforming them under domain randomization, with memory transferring to a physical dual-arm robot of a different embodiment than it was built with.

## Strengths

- Avoids weight updates entirely, side-stepping catastrophic forgetting and the cost of online RL/fine-tuning — relevant to the "test-time adaptation without retraining" line of work the field is converging on.
- The embodiment-transfer claim (memory built on one embodiment helping a differently-embodied dual-arm robot) is a stronger generalization test than most in-context-learning robotics papers attempt.
- Rehearsing in a reconstructed simulation of the actual deployment scene, rather than a generic simulator, is a sensible way to make the in-context feedback relevant to the real test conditions.

## Weaknesses

- Key details (abstract wording, full results tables, task diversity, number of seeds) were only available via secondary mirrors (hyper.ai, deeplearn.org) rather than the primary source, since arXiv could not be fetched directly in this session — claims above should be treated as provisional until cross-checked against the paper itself.
- Rehearsal-in-simulation requires a reasonably accurate scene reconstruction and simulator-to-real alignment; the paper's robustness to reconstruction error / sim-to-real gap in the rehearsal step itself is unclear from available summaries.
- "Matches trained policies in clean scenes" is a modest bar; the more interesting claim (beating trained policies under domain randomization) needs scrutiny of what "trained policies" baseline was used and how much compute/data each side got.

## Open Questions

- How does Task Memory scale as more tasks/demonstrations accumulate — does retrieval quality degrade, and is there an effective memory-management or forgetting mechanism?
- How much of the cross-embodiment transfer result depends on the specific dual-arm platform used, versus holding for more divergent embodiments (e.g. humanoid vs. fixed-base arm)?
- What's the latency/compute cost of the rehearsal step at deployment time, and how does it compare to just running a few steps of online RL or DAgger-style correction instead?

## Significance

Flagged under the cross-cutting VLA post-training priority as an in-context imitation-learning / test-time-adaptation approach: if the scene-rehearsal-plus-task-memory idea holds up, it's a weight-update-free alternative to the RL-fine-tuning and DAgger-correction methods that dominate current VLA post-training, trading training cost for inference-time compute and reconstruction fidelity.

## Links

- [Paper](https://arxiv.org/abs/2611.12885)
- [Code](https://github.com/ArcheOne-AI/RoboScript)

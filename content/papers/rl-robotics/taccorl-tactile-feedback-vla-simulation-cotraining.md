---
title: "TacCoRL: Integrating Tactile Feedback into VLA via Simulation Co-Training and RL"
date: 2026-06-10
topic: RL-Robotics
tags: [tactile, contact-rich, sim-to-real, co-training, rl, vla, contact-exploration]
source: https://arxiv.org/abs/2606.11743
venue: "arXiv 2606.11743"
---

## Summary

TacCoRL injects tactile feedback into VLA policies without large-scale tactile pretraining or real-world contact exploration. Mixed simulated and real trajectories warm-start tactile-conditioned actions in the pretrained policy, then RL with verifiable task rewards on simulated contact rollouts optimizes near-failure contact behavior — reinforcing tactile-conditioned actions that lead to task completion while a supervised objective on real data keeps the policy anchored to deployment distributions.

## Key Contributions

- Scalable two-phase pipeline: warm-start from mixed real+sim tactile trajectories, then RL in a real-aligned simulator targeting near-failure contact states rare in demonstrations
- Avoids both expensive real-world contact exploration (risky and slow) and large-scale tactile-specific pretraining by leveraging simulation for the RL phase exclusively
- Demonstrates that visual VLA priors + targeted tactile RL outperform pure visual or pure tactile approaches on contact-rich manipulation without dedicated tactile datasets

## Significance

Shows a practical path to tactile-aware VLAs: simulation handles the contact RL burden while real data anchors the visual-action distribution — enabling contact-rich skill acquisition at the scale and cost of standard VLA fine-tuning.

## Links

- [Paper](https://arxiv.org/abs/2606.11743)
- [Project page](https://tac-corl.github.io/)

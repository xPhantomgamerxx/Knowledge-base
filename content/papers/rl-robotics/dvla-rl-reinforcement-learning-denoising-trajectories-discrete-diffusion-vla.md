---
title: "dVLA-RL: Reinforcement Learning over Denoising Trajectories for Discrete Diffusion VLAs"
date: 2026-06-23
topic: RL-Robotics
tags: [discrete-diffusion, denoising-mdp, ppo, rl-fine-tuning, libero, robotwin]
source: https://arxiv.org/abs/2606.23623
venue: "arXiv 2606.23623"
---

## Summary

dVLA-RL enables PPO-style online reinforcement learning for discrete diffusion VLAs by optimizing the probability of sampled denoising trajectories (paths through the discrete denoising process) rather than the intractable marginal likelihood of final actions. It formulates the denoising process as an MDP and introduces a unified denoising-step training strategy that assigns task-wise denoising horizons according to task complexity and initial policy performance.

## Key Contributions

- Formulates discrete diffusion VLA fine-tuning as an MDP over denoising trajectories, solving the intractable marginal action probability that previously blocked RL for discrete diffusion VLAs
- Unified denoising-step training strategy that dynamically assigns shorter denoising horizons for easier tasks and longer for harder ones, reducing compute cost without sacrificing iterative refinement on complex tasks
- State-of-the-art performance on LIBERO and strong performance on RoboTwin 2.0, consistently improving over SFT-only discrete diffusion VLA baselines

## Significance

Unlocks PPO-style RL for the growing family of discrete diffusion VLAs (fast-dVLA, DFM-VLA, etc.) that previously had no principled online RL fine-tuning path — a significant gap given the accuracy advantages of iterative denoising for robot action generation.

## Links

- [Paper](https://arxiv.org/abs/2606.23623)

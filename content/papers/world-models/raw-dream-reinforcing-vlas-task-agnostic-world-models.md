---
title: "RAW-Dream: Reinforcing VLAs in Task-Agnostic World Models"
date: 2026-05-12
topic: WorldModels
tags: [world-model, rl, vla, task-agnostic, reward-free, vlm-reward, microsoft-research]
source: https://arxiv.org/abs/2605.12334
venue: "arXiv 2605.12334"
---

## Summary

RAW-Dream (Reinforcing VLAs in task-Agnostic World Dreams) disentangles world model learning from downstream task dependencies. Existing methods for RL-based VLA post-training via imagined rollouts still require task-specific data to fine-tune both the world model and reward model, limiting scalability to unseen tasks. RAW-Dream removes this dependency by using a task-free world model and an off-the-shelf VLM for zero-shot reward.

## Key Contributions

- Task-agnostic world model pre-trained on diverse task-free behaviors, used as-is for imagined rollout generation without target-task exposure
- Off-the-shelf VLM (no fine-tuning) provides zero-shot reward signals for arbitrary new tasks
- Eliminates the need for in-domain data when post-training VLAs for new tasks
- Evaluated on LIBERO benchmarks and real-world manipulation, demonstrating strong generalization to unseen tasks

## Significance

By removing the task-specific data requirement from both the world model and the reward model, RAW-Dream dramatically increases the scalability of imagination-based RL for robot policies — an important step toward truly general-purpose robotic fine-tuning.

## Links

- [Paper](https://arxiv.org/abs/2605.12334)
- [HTML](https://arxiv.org/html/2605.12334)

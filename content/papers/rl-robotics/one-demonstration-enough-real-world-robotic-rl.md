---
title: "One Demonstration Is Enough for Real-World Robotic Reinforcement Learning"
date: 2026-07-02
topic: RL-Robotics
tags: [RL-Robotics, real-robot, few-shot, SERL, contact-rich-manipulation, demonstration-efficiency]
source: https://arxiv.org/abs/2607.01651
venue: "arXiv 2607.01651"
---

## Summary

AutoSERL is a framework that leverages a single demonstration to fully automate the intervention process in real-world robot RL. Three complementary mechanisms work together: a sliding window intervention mechanism to guide exploration and prevent unsafe deviations, a safety recovery mechanism detecting and correcting failure states via predefined trajectory recovery points, and an intervention termination criterion that disables guidance once the policy can complete the task independently.

## Key Contributions

- AutoSERL: single-demo automation of real-world robot RL intervention
- Sliding window intervention for safe exploration guidance without constant human presence
- Safety recovery mechanism with predefined trajectory recovery points
- Automatic intervention termination once policy achieves task competence
- Evaluated on 6 contact-intensive tasks (insertion, hanging, hinge-based) across 2 robot platforms
- Outperforms SERL with 20 demonstrations; matches HIL-SERL; 100% success on insertion tasks
- Improved robustness to positional variations

## Significance

Reducing the demonstration requirement from 20 to 1 for real-world robot RL training is a major practical advance—AutoSERL makes SERL-style on-hardware RL accessible for rapid deployment in new tasks with minimal human effort.

## Links

- [Paper](https://arxiv.org/abs/2607.01651)

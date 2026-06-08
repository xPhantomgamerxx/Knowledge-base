---
title: "AcceRL: A Distributed Asynchronous Reinforcement Learning and World Model Framework for Vision-Language-Action Models"
date: 2026-03-18
topic: RL-Robotics
tags: [rl-infrastructure, distributed-rl, async-rl, world-model, vla, training-framework, open-source]
source: https://arxiv.org/abs/2603.18464
venue: "arXiv 2603.18464"
---

## Summary

AcceRL is a fully asynchronous and decoupled RL training framework designed specifically for large-scale VLA models. It physically isolates training, inference, and rollout workers to eliminate synchronization barriers that degrade GPU utilization in standard synchronous pipelines. AcceRL is also the first framework to integrate a plug-and-play trainable world model into a distributed async RL pipeline for generating virtual experiences.

## Key Contributions

- Fully asynchronous decoupled architecture physically separating training, inference, and environment rollout to eliminate blocking synchronization
- Plug-and-play world model integration enabling virtual experience generation within the same async pipeline, reducing costly real-world rollout time
- Super-linear throughput scaling and highly efficient hardware utilization on LIBERO benchmarks
- Open-source at github.com/distanceLu/AcceRL

## Significance

Provides critical infrastructure for scaling RL fine-tuning of VLAs, demonstrating that decoupled async design with integrated world-model imagination can dramatically improve training efficiency — an enabling technology as the field moves toward larger-scale robot RL.

## Links

- [Paper](https://arxiv.org/abs/2603.18464)
- [HTML](https://arxiv.org/html/2603.18464)
- [GitHub](https://github.com/distanceLu/AcceRL)

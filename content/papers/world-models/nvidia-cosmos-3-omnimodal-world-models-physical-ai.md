---
title: "Cosmos 3: Omnimodal World Models for Physical AI"
date: 2026-06-02
topic: WorldModels
tags: [world-model, nvidia, cosmos, omnimodal, video-generation, action-prediction, physical-ai, open-source]
source: https://arxiv.org/abs/2606.02800
venue: "Technical Report / NVIDIA Blog 2026"
---

## Summary

NVIDIA Cosmos 3 is the world's first fully open omnimodal world foundation model for Physical AI, natively modeling language, image, video, audio, and action in a single mixture-of-transformers architecture. Depending on its input-output configuration it operates as a VLM for reasoning, a text-to-image/video generator, an action-conditioned world model for future simulation, or a joint world-action model for robot and AV policy. Post-trained Cosmos 3 models rank #1 on WorldModelBench Robot (UC Berkeley/MIT/NVIDIA) and top the RoboArena policy leaderboard while using 4× fewer parameters than prior open leaders.

## Key Contributions

- First open omnimodal model covering text, image, video, audio, and action in one architecture
- Mixture-of-transformers enabling seamless mode switching across generation and reasoning tasks
- Native Physical AI support: world-action model mode jointly predicts future video and robot/AV actions
- State-of-the-art on WorldModelBench Robot, Text-to-Image (Artificial Analysis), and Image-to-Video rankings
- Full open release: code, weights, curated synthetic datasets, and evaluation benchmarks on HuggingFace/GitHub

## Significance

Cosmos 3 is the most comprehensive open physical-AI foundation model to date, collapsing six previously separate model roles (VLM, T2I, T2V, I2V, audio-video, world-action) into one, drastically lowering the cost of physical-AI training and evaluation pipelines.

## Links

- [Paper](https://arxiv.org/abs/2606.02800)
- [GitHub](https://github.com/nvidia/cosmos)
- [HuggingFace Collection](https://huggingface.co/collections/nvidia/cosmos3)
- [NVIDIA Newsroom](https://nvidianews.nvidia.com/news/nvidia-releases-new-physical-ai-models-as-global-partners-unveil-next-generation-robots)

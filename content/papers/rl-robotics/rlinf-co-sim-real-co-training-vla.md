---
title: "RLinf-Co: Reinforcement Learning-Based Sim-Real Co-Training for VLA Models"
date: 2026-02-13
topic: RL-Robotics
tags: [sim-real, co-training, VLA, RL-fine-tuning, OpenVLA, pi0, catastrophic-forgetting, Tsinghua]
source: https://arxiv.org/abs/2602.12628
venue: "arXiv"
---

## Summary

RLinf-Co moves beyond SFT-only sim-real co-training by leveraging closed-loop RL in simulation while anchoring the policy to real-world data via an auxiliary supervised loss. The two-stage framework first warm-starts the policy with SFT on mixed real and simulated demonstrations, then fine-tunes with RL in simulation incorporating a real-world regularization term into the overall objective. Evaluated on four real-world tabletop manipulation tasks using OpenVLA and π₀.₅, RLinf-Co achieves +24% and +20% real-world success rate improvements respectively over real-only fine-tuning.

## Key Contributions

- RL-based sim-real co-training framework that exploits closed-loop interaction in simulation rather than static SFT
- Two-stage design: SFT warm-start on mixed data → RL fine-tuning with real-data auxiliary supervised loss
- Real-world regularization term in the RL objective prevents catastrophic forgetting of real-world capabilities
- Validated on OpenVLA (+24%) and π₀.₅ (+20%) across four real tabletop manipulation tasks
- Built on the RLinf open-source RL infrastructure for embodied AI

## Significance

RLinf-Co shows that interactive simulation provides a strictly stronger training signal than SFT on simulated demonstrations, while the real-data anchor resolves the forgetting problem that has limited prior sim-RL approaches for VLAs.

## Links

- [Paper](https://arxiv.org/abs/2602.12628)
- [GitHub](https://github.com/RLinf/RLinf)

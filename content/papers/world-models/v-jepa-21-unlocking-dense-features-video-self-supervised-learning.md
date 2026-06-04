---
title: "V-JEPA 2.1: Unlocking Dense Features in Video Self-Supervised Learning"
date: 2026-03-15
topic: WorldModels
tags: [self-supervised, video-prediction, dense-features, Meta-FAIR, robot-grasping, hyperbolic, JEPA]
source: https://arxiv.org/abs/2603.14482
venue: "arXiv 2026"
---

## Summary

V-JEPA 2.1 is a family of self-supervised vision models from Meta FAIR that extends the JEPA objective to supervise both masked and unmasked context tokens via a distance-weighted prediction loss, applied hierarchically across intermediate encoder layers. This produces spatially structured, semantically coherent, and temporally consistent representations. Key robotics result: a 20-point improvement in real-robot grasping success rate over V-JEPA 2 AC, attributed to better depth encoding in the representations.

## Key Contributions

- Extended JEPA objective supervising both masked and unmasked tokens with distance-weighted loss applied at intermediate encoder layers
- Representations are spatially structured, semantically coherent, and temporally consistent — properties critical for world modeling
- 20-point improvement in real-robot grasping success rate over V-JEPA 2 AC
- Strong performance across robotic navigation (TartanDrive), depth estimation (NYUv2), and video understanding (SSv2) with a single model

## Significance

Demonstrates that improved self-supervised video representations translate directly and significantly into real-robot manipulation performance, validating the world-model approach for robotics without task-specific supervision.

## Links

- [Paper](https://arxiv.org/abs/2603.14482)
- [Meta AI Research](https://ai.meta.com/research/vjepa/)
- [GitHub](https://github.com/facebookresearch/vjepa2)

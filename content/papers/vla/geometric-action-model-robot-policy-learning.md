---
title: "Geometric Action Model for Robot Policy Learning"
date: 2026-06-15
topic: VLA
tags: [vla, 3d-geometry, geometric-foundation-model, world-model, robot-policy, kaist, eth-zurich]
source: https://arxiv.org/abs/2606.17046
venue: "arXiv 2026"
---

## Summary

The Geometric Action Model (GAM) repurposes a pretrained Geometric Foundation Model (GFM) as a unified substrate for perception, temporal prediction, and action decoding, bypassing the 2D-only representations that limit standard VLAs and WAMs in contact-rich tasks. The GFM is split at an intermediate layer: shallow layers serve as an observation encoder, and a causal future predictor inserted at the split point forecasts future latent tokens conditioned on language, proprioception, and action history. Actions are decoded from the predicted geometric latents. The result is a language-conditioned manipulation policy that achieves 55× faster inference than foundation-model-scale baselines while improving accuracy and robustness.

## Key Contributions

- Introduces the concept of repurposing a geometric foundation model as a robot policy backbone
- Causal future predictor operating in GFM latent space enables implicit 3D world modeling
- Language and proprioception conditioning for instruction-following manipulation
- 55× inference speedup over competing foundation-model baselines with better accuracy

## Significance

GAM demonstrates that 3D geometric structure is a high-leverage prior for contact-rich manipulation; the approach bridges geometric perception research and robot learning in a single compact architecture.

## Links

- [Paper](https://arxiv.org/abs/2606.17046)
- [Project page](https://cvlab-kaist.github.io/Geometric-Action-Model/)

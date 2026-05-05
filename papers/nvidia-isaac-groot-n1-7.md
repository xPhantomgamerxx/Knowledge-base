---
title: "NVIDIA Isaac GR00T N1.7: Open Reasoning VLA Model for Humanoid Robots"
date: 2026-03-16
topic: VLA
tags: [humanoid, cross-embodiment, open-source, foundation-model, EgoScale]
source: https://huggingface.co/blog/nvidia/gr00t-n1-7
venue: "Blog / NVIDIA GTC 2026"
---

## Summary

NVIDIA released GR00T N1.7 in early access at GTC 2026 on March 16, 2026 — an open, commercially licensed VLA model for humanoid robots. Pretrained via EgoScale on 20,854 hours of egocentric human video spanning 20+ task categories, it provides cross-embodiment generalization with a new Cosmos-Reason2-2B/Qwen3-VL backbone. Commercial licensing is enabled for the first time in the GR00T series, opening production deployments.

## Key Contributions

- EgoScale pretraining on 20,854 hours of egocentric human video across manufacturing, healthcare, retail, and home domains
- New VLM backbone (Cosmos-Reason2-2B / Qwen3-VL) for enhanced multimodal reasoning
- Cross-embodiment VLA supporting diverse humanoid configurations without architecture changes
- First GR00T release with a commercial open license

## Significance

GR00T N1.7 is the most capable open humanoid robot foundation model to date and the first commercially licensed release in its series, significantly lowering the barrier for production-scale humanoid deployments. NVIDIA simultaneously previewed GR00T N2 (based on the DreamZero world action model architecture), signaling a shift toward world-model-based robot policies.

## Links

- [HuggingFace Blog](https://huggingface.co/blog/nvidia/gr00t-n1-7)
- [GitHub](https://github.com/NVIDIA/Isaac-GR00T)
- [NVIDIA Developer Page](https://developer.nvidia.com/isaac/gr00t)

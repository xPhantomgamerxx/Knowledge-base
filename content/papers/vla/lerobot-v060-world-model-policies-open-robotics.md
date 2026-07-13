---
title: "LeRobot v0.6.0: Imagine, Evaluate, Improve — World Model Policies for Open Robotics"
date: 2026-07-07
topic: VLA
tags: [open-source, toolkit, world-model-policies, vla-jepa, fastwam, lingbot-va, huggingface]
source: https://huggingface.co/blog/lerobot-release-v060
venue: "blog / toolkit release (Hugging Face)"
---

## Summary

Hugging Face released LeRobot v0.6.0 on July 7, 2026, adding three world-model policy architectures — VLA-JEPA, FastWAM, and LingBot-VA — plus reward model support, six simulation benchmarks under lerobot-eval, human-correction rollout tooling, and FSDP training with HF Jobs cloud support. The release closes the evaluate-correct-train loop for open embodied AI.

## Key Contributions

- **VLA-JEPA**: Qwen3-VL-2B + JEPA-style world model predicts future frames in latent space during training; world model is dropped at inference so robots benefit from future-prediction supervision at zero runtime cost
- **FastWAM**: Combines a ~5B-parameter video-generation expert with a smaller action expert in one network; learns full rollouts during training for efficient inference
- **LingBot-VA**: Autoregressive video-action world-model policy built on the Wan2.2 video-diffusion stack, interleaving future video latent prediction and robot action generation in one sequence
- Reward model support and six new simulation benchmarks (lerobot-eval) enabling closed-loop policy assessment without physical robots

## Significance

LeRobot v0.6.0 is the first major open-source robotics toolkit to integrate multiple world-model policy paradigms in one unified framework, making future-imagination-based robot learning accessible to the broader community without proprietary infrastructure.

## Links

- [HuggingFace blog](https://huggingface.co/blog/lerobot-release-v060)
- [GitHub](https://github.com/huggingface/lerobot)
- [VLA-JEPA docs](https://huggingface.co/docs/lerobot/main/en/vla_jepa)

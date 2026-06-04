---
title: "ProgressVLA: Progress-Guided Diffusion Policy for Vision-Language Robotic Manipulation"
date: 2026-03-29
topic: VLA
tags: [diffusion-policy, progress-estimation, world-model, inverse-dynamics, Microsoft-Research, task-termination]
source: https://arxiv.org/abs/2603.27670
venue: "arXiv 2026"
---

## Summary

ProgressVLA addresses the lack of task-progress awareness in existing VLA models — most rely on hand-crafted heuristics for termination — by pre-training a progress estimator on large-scale unsupervised video-text datasets and integrating it into an inverse dynamics world model. A maximal progress regularization objective creates a differentiable pipeline that uses estimated progress to refine action tokens, improving both task success and generalization.

## Key Contributions

- Progress estimator pre-trained on robotic video-text data achieving 0.07 prediction residual (scale 0–1) with zero-shot generalization to unseen real-world samples
- Inverse dynamics world model that maps predicted action tokens to future latent visual states
- Maximal progress regularization provides differentiable progress-piloted guidance for action token refinement
- Consistent improvements on CALVIN and LIBERO benchmarks plus real-world deployment

## Significance

First work to systematically inject explicit task-progress awareness into the VLA diffusion-policy paradigm, enabling cleaner task termination and improved long-horizon performance without task-specific heuristics.

## Links

- [Paper](https://arxiv.org/abs/2603.27670)
- [Microsoft Research](https://www.microsoft.com/en-us/research/publication/progressvla-progress-guided-diffusion-policy-for-vision-language-robotic-manipulation/)

---
title: "WALL-SS: Scaling Long-horizon World Models via Next-Scale Autoregression"
date: 2026-08-26
topic: WorldModels
tags: [world-model, next-scale-autoregression, long-horizon, action-conditioned, on-policy-alignment, X-Square-Robot]
source: https://arxiv.org/abs/2608.26239
venue: "arXiv"
---

## Summary

WALL-SS is X-Square Robot's follow-up to their WALL-OSS/WALL-WM line of embodied world models, replacing raster-scan (row-by-row) token generation with scale-wise, coarse-to-fine ("next-scale") autoregression to make long-horizon, action-conditioned video rollouts both faster and more temporally consistent. It represents embodied trajectories as causal sequences of interleaved observations and actions, and reports minute-long streaming rollouts under a bounded memory budget.

## Key Contributions

- Action-conditioned next-scale prediction: scale-aligned action tokens are injected at each coarse-to-fine generation step, tightening the coupling between actions and their visual consequences (including modeling failed/unsuccessful behaviors, not just successes).
- Scale-compressed long-horizon memory: recent interactions are kept at fine resolution while distant history is progressively compressed, paired with "scale-wise dream forcing" to make the model robust to consuming its own generated (rather than ground-truth) context.
- On-policy alignment stage: treats the autoregressive visual dynamics model as a policy and optimizes it with action-following and long-term-consistency rewards while trying to preserve the pretrained visual distribution — explicitly targeting action drift over long rollouts.
- Reports strong sim-to-real correlation for using the world model as a policy evaluator: over 600 sim-real rollout pairs give MAE 0.062 / r=0.93 on success-rate agreement, and 0.89 pairwise / 0.88 Spearman-ρ agreement on checkpoint ranking versus real robots.

## Strengths

- Directly targets the two chronic failure modes of autoregressive video/world models (compounding error and quadratic/linear-in-length compute for long rollouts) with an architectural fix (scale-wise generation) rather than just more data or bigger models.
- The sim-to-real rollout-agreement and checkpoint-ranking numbers are a genuinely useful evaluation axis beyond the usual FVD/pixel-metric reporting seen in most WAM papers — it targets "can this world model substitute for real-robot A/B testing," which is a more practically relevant question.
- Comes from a group (X-Square Robot / WALL-OSS) with a track record of open-sourcing prior world-action models, raising the odds this is eventually usable rather than purely a paper artifact.

## Weaknesses

- At time of writing, training code and full technical details are not released — only a project page and abstract are public, so the on-policy alignment reward design and next-scale tokenizer specifics can't yet be independently verified.
- Comparisons are against InfinityStar and CogVideoX, which are general video-generation baselines, not against other action-conditioned WAMs (e.g., DreamZero-style models, GR00T-Dreams, or other long-horizon WAMs already in this vault) — so it's unclear whether the gains are specific to embodied control or just inherited from next-scale (VAR-style) generation being generally stronger than raster autoregression.
- "Minute-long" rollouts under bounded memory is a meaningful claim but the paper doesn't establish how degradation compares at 2, 5, or 10 minutes — long-horizon claims in this literature routinely soften well beyond the reported window.
- On-policy alignment reward likely requires either a reward model or environment access during training, which reintroduces the exact real-world data/interaction cost that world models are meant to avoid; the paper doesn't quantify that added cost.

## Open Questions

- How does next-scale (VAR-style) autoregression compare directly, on the same data and action-conditioning setup, against diffusion-based and raster-token WAMs already surveyed in this vault (e.g., DreamZero, GigaWorld)?
- Does the scale-compressed memory generalize to genuinely novel long-horizon tasks, or was it tuned/validated mainly on the same task distribution as the sim-to-real correlation study?
- Will the promised open-source release (code/project page references GitHub) hold up to reproduce the 0.93 sim-real correlation figure independently?

## Significance

WALL-SS pushes the fast-growing WAM literature toward a scaling axis (token-generation order) largely unexplored in this vault so far, and its sim-to-real rollout-correlation evaluation offers a template other long-horizon WAM papers could adopt to make "does this actually predict real robot success" claims falsifiable rather than anecdotal.

## Links

- [Paper](https://arxiv.org/abs/2608.26239)
- [GitHub](https://github.com/X-Square-Robot/wall-ss)
- [Project Page](http://x2robot.com/pages/ss)

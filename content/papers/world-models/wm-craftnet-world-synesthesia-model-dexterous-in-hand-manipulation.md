---
title: "WM-Craftnet: World Synesthesia Model for Generalizable and Robust Dexterous In-Hand Manipulation"
date: 2026-09-08
topic: WorldModels
tags: [world-models, robotics, dexterous-manipulation, tactile, multimodal-fusion, sim-to-real]
source: https://arxiv.org/abs/2609.07002
venue: "CoRL 2026 (Spotlight, Top 4.4%)"
---

## Summary

WM-Craftnet introduces a "World Synesthesia Model" (WSM) that fuses proprioception, noisy wrist depth, tactile contact, and action history into a single recurrent world-model state for dexterous in-hand manipulation, feeding an asymmetric actor-critic policy directly rather than relying on imagined video rollouts. Accepted as a Spotlight paper (top 4.4%) at CoRL 2026, it targets robust, generalizable in-hand manipulation on a 22-DoF dexterous hand.

## Key Contributions

- A multimodal "synesthesia" world-model state that jointly encodes proprioception, depth, touch, and action history into one recurrent representation, rather than modeling each modality with separate, loosely-coupled streams
- The model is trained to reconstruct clean depth from noisy wrist-depth input as an auxiliary objective, which the authors report eases sim-to-real transfer onto the physical 22-DoF Sharpa Wave hand
- Uses the fused world-model state to directly drive an asymmetric actor-critic policy, skipping imagined/generated video rollouts entirely — a notably different design choice from the generative-video-centric WAM mainstream
- Shows the state representation pretrained on nine z-axis objects can serve as a reusable prior that initializes learning for new object sets, supporting generalization

## Strengths

- A genuinely distinct design point in the tactile/proprioceptive world-model space: fusing touch, depth, and proprioception into a compact recurrent state for direct RL, instead of the generative-video-plus-action paradigm most WAMs use
- The noisy-depth-to-clean-depth reconstruction objective is a simple, well-motivated mechanism for sim-to-real robustness specifically tailored to real sensor noise characteristics
- CoRL 2026 Spotlight acceptance (top 4.4%) indicates a high external quality bar was cleared
- Demonstrated reuse of a pretrained state across different object sets is a concrete generalization signal beyond a single task

## Weaknesses

- Scope is narrowly focused on in-hand manipulation with one specific dexterous hand platform (22-DoF Sharpa Wave); cross-embodiment or cross-hand-morphology generalization is not demonstrated
- Because it skips generative rollouts entirely, it forgoes the long-horizon planning/imagination capabilities that generative WAMs offer, trading them for RL-policy efficiency — a real but different capability profile
- Available summaries don't make clear how performance compares quantitatively against tactile-centric WAM alternatives already in the literature (e.g. Dream-Tac, DexTouch-WM) on shared benchmarks

## Open Questions

- How does WM-Craftnet's fused synesthesia state compare directly, on the same tasks, against generative tactile world models like Dream-Tac or DexTouch-WM?
- Does the clean-depth reconstruction trick generalize to other noisy sensing modalities (e.g. tactile sensor drift), or is it specific to depth cameras?
- How far does the "reusable prior across object sets" generalization extend — does it hold for object categories or dynamics substantially different from the nine z-axis training objects?

## Significance

Offers a compact, RL-native alternative to the generative-video-rollout paradigm dominating recent world-action-model work, showing that fusing proprioception, tactile, and depth into one world-model state can directly and efficiently drive dexterous in-hand manipulation policies with strong sim-to-real robustness.

## Links

- [Paper](https://arxiv.org/abs/2609.07002)
- [Project Page](https://wmcraftnet.github.io)
- [GitHub](https://github.com/sharpa-robotics/WM-Craftnet)

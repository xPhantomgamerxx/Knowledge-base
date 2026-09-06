---
title: "Modeling What Changes: Sparse, Residual World Models for Object-Centric Manipulation"
date: 2026-09-02
topic: WorldModels
tags: [world-model, object-centric, efficiency, manipulation, sample-efficiency]
source: https://arxiv.org/abs/2609.02046
venue: "arXiv"
---

## Summary

This paper argues that most objects in a manipulation scene don't move on any given timestep, and that dense world models waste capacity predicting the (unchanged) state of everything in the scene. It proposes a sparse, residual world model: a per-object "change gate" decides which objects were affected by the action, and a residual delta head predicts an update only for the objects the gate flags, leaving everything else unchanged by construction.

## Key Contributions

- A change-gate-plus-residual-delta architecture for object-centric world models, replacing dense whole-scene next-state prediction with sparse, per-object updates conditioned on a learned change detector.
- Evaluation on a MuJoCo tabletop pushing benchmark scaling from 3 to 8 objects, showing 2.5-4.6x more accurate next-state pose prediction than a dense MLP baseline while using 8.6-11.1x fewer parameters.
- Demonstrated zero-shot transfer across object counts (99.4% F1 retention when moving to scenes with different numbers of objects than trained on) without retraining, plus strong change-detection F1 (0.80-0.87) and roughly 90% of full-data accuracy from just a quarter of the training data.
- Open-sourced code, data generators, and checkpoints.

## Strengths

- The core insight (sparsity of change in most manipulation scenes) is simple, well-motivated, and directly attacks both parameter efficiency and data efficiency simultaneously rather than trading one for the other.
- Cross-object-count generalization without retraining is a genuinely useful property for manipulation world models, where the number of distractor/task-relevant objects in a real scene is rarely fixed and dense models typically need architecture or retraining changes to handle a different object count.
- Small, reproducible benchmark with released code and data generators lowers the bar for follow-up work to verify or extend the claims.

## Weaknesses

- Evaluated only in MuJoCo on a synthetic tabletop pushing task with a small number of rigid objects — no real-robot results, no deformable/articulated objects, and no comparison against the video-generative WAM baselines that dominate this space (the comparison is against a dense MLP, a fairly weak baseline for a 2026 world-model paper).
- The "change gate" formulation implicitly assumes discrete, mostly-independent per-object dynamics; it is unclear how this scales to contact-rich scenarios where many objects change simultaneously (e.g., toppling stacks, granular/deformable materials) where the sparsity assumption breaks down.
- Small author team and a MuJoCo-only benchmark suggest this is early-stage/workshop-scale work rather than a fully validated production technique; the parameter/data efficiency numbers, while striking, come from a narrow test bed.

## Open Questions

- Does the change-gate mechanism hold up in cluttered, contact-rich scenes where most objects move together (e.g., pushing through a pile), where the sparsity assumption is weakest?
- Can this residual/sparse formulation be combined with the large video-generative WAM backbones elsewhere in this vault to cut their compute cost, or is it fundamentally an alternative to (rather than a component of) that paradigm?
- How does the approach handle new object categories/shapes not seen during training, versus just new counts of previously-seen object types?

## Significance

A useful counter-trend to the "bigger video diffusion backbone" direction most WAM papers in this vault pursue: it suggests real efficiency gains are available just from better inductive biases (most of the scene doesn't change) rather than from scaling. If it generalizes beyond the toy MuJoCo setting, this kind of object-centric sparsity could meaningfully cut the compute cost of world-model rollouts used for planning or VLA post-training.

## Links

- [Paper (arXiv)](https://arxiv.org/abs/2609.02046)
- [GitHub](https://github.com/ParamThakkar123/sparse_world_models)

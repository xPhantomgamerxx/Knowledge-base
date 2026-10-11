---
title: "Cross-Embodiment Robot Foundation World Models with Latent Actions (LAC-WM)"
date: 2026-10-07
topic: WorldModels
tags: [world-models, robotics, cross-embodiment, latent-action, foundation-model, icml]
source: https://arxiv.org/abs/2610.10846
venue: "ICML 2026"
---

## Summary

LAC-WM is a robot foundation world model that operates in a learned latent action space shared across different robot embodiments, rather than conditioning on each embodiment's raw, explicit action labels. The authors show that explicit action conditioning (their baseline, EAC-WM) produces action representations that fail to align across embodiments, and that this misalignment actively hurts transfer to new robots — motivating the latent-action alternative. Co-authors include Li Fei-Fei and Franziska Meier, and the paper is accepted as an ICML 2026 poster.

## Key Contributions

- An inverse dynamics model maps observations from many heterogeneous embodiments (human hands, robot end-effectors, cameras) into one shared latent action space during pretraining
- A motion decoder converts shared latent actions back into embodiment-specific motion labels (human hand poses, robot end-effector actions, camera motion), and an action projector adapts a new robot's raw actions into the shared space at finetuning time
- Demonstrates that as more pretraining embodiments are added, LAC-WM's performance improves while the explicit-action baseline (EAC-WM) degrades — a direct empirical case against naive explicit multi-embodiment action conditioning
- Reports up to 46.7% improvement on dexterous manipulation and 11.7% on a modified LIBERO benchmark over EAC-WM, and raises pick-and-place success from 82.4% to 92.0% in a reported lay-summary figure

## Strengths

- Clean, falsifiable empirical claim (latent > explicit action conditioning for cross-embodiment scaling) backed by a controlled comparison against a matched explicit-conditioning baseline, not just an ad hoc architecture change
- The finding that adding embodiments *hurts* an explicit-action baseline is a notable, counter-intuitive and practically important result for anyone building multi-embodiment robot foundation models
- Strong author pedigree (Fei-Fei Li, Franziska Meier) and ICML 2026 acceptance suggest the work passed a rigorous peer-review bar
- Project code and website are publicly released

## Weaknesses

- The shared latent action space is itself learned and opaque; it is unclear how interpretable or debuggable the resulting latent actions are compared to explicit, physically meaningful action labels
- Gains are reported on dexterous manipulation and a modified LIBERO — generalization to locomotion, humanoid whole-body control, or embodiments very different from those in pretraining is untested
- The motion decoder's reliance on mapping back to embodiment-specific labels could reintroduce some of the same cross-embodiment misalignment the latent space is meant to avoid, depending on decoder design

## Open Questions

- How does the latent action space's dimensionality/capacity trade off against the number and diversity of pretraining embodiments?
- Would the explicit-conditioning degradation observed for EAC-WM persist with more careful embodiment-aware normalization, or is the latent-action advantage fundamental?
- How well does LAC-WM's latent action space transfer to action spaces qualitatively different from those seen in pretraining (e.g., soft/compliant actuators, aerial platforms)?

## Significance

Provides rare, controlled empirical evidence that explicit multi-embodiment action conditioning — the default choice in much of the cross-embodiment robot learning literature — can actively hurt scaling, strengthening the case for learned shared latent action representations as the more scalable foundation-model design choice.

## Links

- [Paper](https://arxiv.org/abs/2610.10846)
- [Project Page](https://lacwm.github.io)
- [GitHub](https://github.com/qingh097/lacwm-project)

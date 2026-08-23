---
title: "Support-Constrained RL Enables Real-World Policy Improvement without Real-World Experience (SCORE)"
date: 2026-06-25
topic: RL-Robotics
tags: [rl, sim-to-real, dexterous-manipulation, flow-matching, vla-posttraining]
source: https://arxiv.org/abs/2606.27475
venue: "arXiv"
---

## Summary

SCORE is a real-to-sim-to-real RL framework that constrains simulation-based RL to the support of a generative policy pretrained on real data, via flow steering. This prevents the policy from exploiting sim dynamics or contact mismatches that don't transfer to hardware, while avoiding the over-constraining common in naive regularization approaches. It substantially improves real-world dexterous manipulation success without additional real-world training.

## Key Contributions

- Frames the sim-to-real RL exploitation problem precisely: naive sim RL can find high-reward simulator-specific exploits (dynamics or contact quirks) that fail on hardware, while naive regularization toward the real-data-pretrained policy over-constrains exploration and limits improvement.
- Uses flow steering to constrain exploration to the *support* of the pretrained generative policy's distribution — a softer constraint than matching the policy's exact behavior, which the authors argue avoids both failure modes.
- Achieves real-world policy improvement using zero additional real-world training data or interaction, relying entirely on the support-constrained simulated RL phase.

## Strengths

- The support-constraint framing (constrain to plausible-action support, not exact behavior match) is a more principled middle ground than the binary choice between free sim RL exploration and strict behavior-cloning regularization that has limited prior sim-to-real RL work.
- Zero additional real-world training data is a significant practical advantage, since real-world RL interaction remains expensive and slow relative to simulation.
- Flow-matching-based steering ties into a broader trend of using generative-model machinery (flow matching, diffusion) for policy representation, making the technique naturally compatible with modern flow-based VLA action heads.

## Weaknesses

- The approach's success still depends on how well the *simulator's* dynamics approximate reality within the constrained support region — support-constraint prevents exploiting egregious sim/real mismatches but doesn't eliminate more subtle transfer gaps.
- Evaluated specifically on dexterous manipulation; it's unclear whether the support-constraint approach scales similarly to other task categories (e.g. long-horizon mobile manipulation) with different sim-to-real gap characteristics.

## Open Questions

- How sensitive is SCORE's improvement to the quality of the initial real-data-pretrained generative policy — does a weaker starting policy narrow the useful support region too much to allow meaningful RL improvement?
- Could the support-constraint principle be combined with online real-world fine-tuning for further gains, or is it specifically valuable as a way to avoid real-world interaction entirely?

## Significance

A methodologically interesting contribution to the sim-to-real RL literature that directly targets the classic exploitation-vs-over-constraint tradeoff, relevant to the substantial cluster of sim-to-real RL work already in this vault (Scaling Sim-to-Real RL, Grounding Sim-to-Real Generalization, RLinf-Co).

## Links

- [Paper](https://arxiv.org/abs/2606.27475)

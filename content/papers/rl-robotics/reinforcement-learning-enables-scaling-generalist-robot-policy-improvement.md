---
title: "Reinforcement Learning Enables Scaling Generalist Robot Policy Improvement"
date: 2026-11-04
topic: RL-Robotics
tags: [online-rl, generalist-policy, critic-guided-policy-extraction, task-diversity, vla-posttraining]
source: https://arxiv.org/abs/2611.06905
venue: "arXiv (preprint, under review)"
---

## Summary

This paper asks whether a generalist robot policy can keep improving online once it is trained on many diverse tasks at once, rather than narrowly fine-tuned on one deployment task, and what RL recipe makes that improvement transfer to unseen scenes and objects. The authors run controlled scaling studies that vary the number and diversity of RL training tasks and compare three ways of turning RL signal into policy updates: filtered supervised fine-tuning (FSFT), test-time Best-of-N refinement (BoN) with a learned critic, and critic-guided policy extraction via off-policy generative policy optimization (OGPO).

## Key Contributions

- A systematic scaling study of online RL for generalist (VLA-style) robot policies, isolating object-diversity and scene-diversity axes while holding other factors fixed.
- A head-to-head comparison of FSFT, critic-guided BoN, and OGPO-based policy extraction, showing they scale very differently with training-task diversity.
- Evidence that critic-guided and RL-extracted policies transfer gains to held-out (unseen) objects/scenes as training diversity grows, while FSFT does not and can even regress on held-out objects.
- A recommended recipe pairing a critic (value function) with RL post-training over a growing, diverse task set, released as code and a project page.

## Strengths

- Directly targets a practically important and under-studied question (does online RL improvement generalize, or just memorize the deployment task) with controlled ablations rather than a single headline number.
- Disentangles "more tasks" from "more diverse solution strategies," which is a more actionable finding than typical scaling-law papers that only vary dataset size.
- Compares a spectrum of post-training strategies (SFT-like, test-time search, and RL-extraction) under one consistent protocol, making the OGPO advantage easier to trust.

## Weaknesses

- Evaluation leans on simulation/benchmark suites (e.g., MolmoSpaces-style setups, LIBERO-family tasks) with real-robot validation left thinner than the simulated scaling curves; the generality to truly novel embodiments is unclear.
- "Task diversity" is operationalized via the authors' own task-generation pipeline, so it is unclear how this notion of diversity maps onto the messier diversity of real deployment fleets.
- As with most OGPO-style critic-guided methods, training stability and compute cost of maintaining a good value function at scale are not deeply analyzed.

## Open Questions

- Does the object/scene-diversity recipe hold for dexterous, contact-rich, or long-horizon tasks, or only for the pick-place-style manipulation evaluated here?
- How does this scaling recipe interact with fleet-deployed online RL systems (e.g., Learning While Deploying) that must also handle safety and human intervention?
- Would the same diversity-scaling trend hold for RL fine-tuning of larger foundation VLAs (π0.5/GR00T-scale), where online rollout cost is much higher?

## Significance

It provides some of the first controlled evidence that online RL post-training of generalist robot policies can generalize rather than overfit to a narrow deployment task, and it gives a concrete, testable recipe (critic-guided RL extraction + growing task diversity) for teams scaling up real-world RL fine-tuning of robot foundation models.

## Links

- [Paper](https://arxiv.org/abs/2611.06905)
- [Project Page / Code](https://lasgroup.github.io/generalist-improvement/)

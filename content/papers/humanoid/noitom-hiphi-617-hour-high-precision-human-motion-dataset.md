---
title: "Noitom Robotics Releases HiPHI: A 617-Hour High-Precision Human Motion Dataset"
date: 2026-08-19
topic: Humanoid
tags: [humanoid, dataset, motion-capture, imitation-learning-data]
source: https://www.globenewswire.com/news-release/2026/08/20/3348065/0/en/noitom-robotics-releases-hiphi-one-of-the-largest-high-precision-human-motion-datasets-ever-made-public-at-the-world-robot-conference.html
venue: "blog / press release"
---

## Summary

Noitom Robotics publicly released HiPHI, a 617.5-hour high-precision optical motion-capture dataset (371.8 hours whole-body human motion plus 245.7 hours human-object interaction), captured from 132 performers at 90Hz with sub-millimeter marker tracking, at the World Robot Conference 2026 in Beijing. The dataset is organized around FrameNet-derived motion units and is intended for humanoid learning, digital humans, and computer graphics research.

## Key Contributions

- One of the largest publicly released high-precision human motion datasets to date, combining scale (617.5 hours) with studio-grade capture precision (sub-millimeter, 90Hz) rather than trading one for the other as many large-but-noisy web-scraped motion datasets do.
- Explicit inclusion of human-object interaction data (245.7 of the 617.5 hours), not just isolated whole-body motion, which is directly more useful for training manipulation and loco-manipulation policies than pure locomotion mocap.
- Organizing the dataset around FrameNet-derived motion units (a linguistic framework for action semantics) is an unusual and potentially useful structuring choice for connecting motion data to language-conditioned policy training.
- Publicly available on Hugging Face, lowering the barrier to use compared to proprietary mocap datasets.

## Strengths

- The combination of scale and precision is genuinely rare — most public motion datasets sacrifice one for the other, and having both at this scale is a real contribution to the field's data infrastructure.
- Free public release (rather than a paid or access-gated dataset) directly benefits the broader humanoid imitation-learning research community, not just Noitom's own downstream projects.

## Weaknesses

- As studio optical mocap, HiPHI captures clean, controlled performances rather than natural in-the-wild human behavior — this limits its usefulness for training policies that need to generalize to noisy, unstructured real-world human motion.
- The dataset itself is human motion, not robot-embodiment data — the retargeting gap from human motion to specific humanoid kinematics still needs to be bridged by downstream users, and quality of that retargeting is not addressed by the dataset release itself.

## Open Questions

- How readily does FrameNet-derived motion-unit organization actually integrate with language-conditioned humanoid policy training pipelines in practice, versus being primarily useful for dataset organization/search?
- Will independent groups beyond Noitom's own collaborators (as already demonstrated in the companion AdaPT tennis work) adopt HiPHI as a standard pretraining source for humanoid whole-body policies?

## Significance

A significant new open data resource for humanoid whole-body and loco-manipulation research, comparable in importance to other large motion/interaction dataset releases in this vault (AgiBot World, Deform360) — notably paired with an immediate demonstrated downstream application (AdaPT).

## Links

- [Press Release](https://www.globenewswire.com/news-release/2026/08/20/3348065/0/en/noitom-robotics-releases-hiphi-one-of-the-largest-high-precision-human-motion-datasets-ever-made-public-at-the-world-robot-conference.html)
- [Dataset](https://huggingface.co/datasets/noitomrobotics/HiPHI)

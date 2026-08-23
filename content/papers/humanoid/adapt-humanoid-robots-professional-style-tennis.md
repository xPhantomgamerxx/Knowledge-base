---
title: "AdaPT: Humanoid Robots Learn Professional-Style Tennis"
date: 2026-08-21
topic: Humanoid
tags: [humanoid, whole-body-manipulation, motion-imitation, teleoperation-free]
source: https://www.globenewswire.com/news-release/2026/08/21/3349220/0/en/two-days-after-releasing-hiphi-noitom-robotics-and-collaborators-demonstrate-humanoid-robots-playing-professional-style-tennis.html
venue: "blog / press release"
---

## Summary

AdaPT, developed by Noitom Robotics with Shanghai AI Laboratory, Dobot Robotics, and Shanghai Jiao Tong University, reproduces the distinctive playing styles of three professional tennis players (Rafael Nadal, Roger Federer, Novak Djokovic) — learned from publicly available broadcast footage and motion capture — on a Unitree G1 and full-size Dobot Atom humanoid. It demonstrates in-the-wild serving using only a camera and a consumer tracker, without a motion-capture environment, with the motion foundation pretrained on the newly released HiPHI dataset.

## Key Contributions

- Learning distinguishable individual playing *styles* (not just generic tennis-serving competence) from broadcast footage is a more ambitious style-transfer target than typical motion-imitation work, which usually targets a single generic skilled reference.
- Demonstrates in-the-wild serving with only a camera and consumer tracker — a substantially lower deployment barrier than requiring a studio motion-capture rig for either training or evaluation.
- Directly built on the concurrently released HiPHI dataset, serving as an immediate proof-of-concept for that dataset's downstream usefulness.
- Validated across two distinct humanoid platforms (Unitree G1, Dobot Atom), a reasonable test of cross-embodiment applicability.

## Strengths

- Style-specific imitation from broadcast footage (rather than requiring the professional athletes themselves to be mocap'd) is a scalable data source if the approach generalizes — broadcast sports footage is abundant.
- The move from studio mocap training to consumer-camera in-the-wild deployment is a meaningful practical step toward humanoid skills that don't require specialized infrastructure at every stage.

## Weaknesses

- This is a company/consortium press release, not a peer-reviewed paper — quantitative details on task success rate, serve accuracy, or style-fidelity metrics are not available in the press-level coverage, making it hard to assess rigor versus a polished demonstration.
- "Professional-style" tennis is a striking claim; without a defined, objective style-fidelity metric it's unclear how the claim is validated versus being a qualitative/visual impression.

## Open Questions

- What quantitative benchmark, if any, was used to validate that the reproduced styles are meaningfully distinguishable and faithful to each player's real technique, rather than a shared competent tennis motion with superficial stylistic variation?
- How well does the broadcast-footage-to-motion pipeline generalize to sports or skills with less publicly available high-quality footage than professional tennis?

## Significance

A notable applied demonstration of humanoid whole-body athletic skill acquisition from human video and motion capture, illustrating a concrete downstream use case for the HiPHI dataset released just two days prior — worth revisiting once (if) a peer-reviewed technical writeup with quantitative results becomes available.

## Links

- [Press Release](https://www.globenewswire.com/news-release/2026/08/21/3349220/0/en/two-days-after-releasing-hiphi-noitom-robotics-and-collaborators-demonstrate-humanoid-robots-playing-professional-style-tennis.html)

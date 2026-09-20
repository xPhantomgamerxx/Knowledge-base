---
title: "Feeling Terrain Before Crossing: World Models for Off-Road Navigation (Feel-WM)"
date: 2026-09-16
topic: WorldModels
tags: [off-road-navigation, proprioception, legged-robots, self-supervised]
source: https://arxiv.org/abs/2609.19863
venue: "arXiv"
---

## Summary

Presents Feel-WM, the first off-road navigation world model that conditions on and predicts proprioceptive future state (slip, tilt, shake) alongside visual observation, arguing that off-road navigation success hinges on robot-terrain physical interaction that scene-only prediction cannot capture.

## Key Contributions

- Identifies a specific blind spot in navigation world models: scene-focused predictors say nothing about how much the robot will physically slip, tilt, or shake along a candidate trajectory
- Learns future proprioceptive state and a failure-risk estimate directly from the robot's own experience, without human labels
- Integrates proprioceptive foresight into predict-then-select action planning for off-road navigation

## Strengths

- Clean, intuitive problem framing distinguishing off-road from urban/indoor navigation world models: the camera sees what will happen, not what the robot will feel
- Self-supervised proprioceptive labels make the approach scalable to large amounts of real off-road traversal data without annotation
- Directly relevant to safety — predicting failure risk before committing to a trajectory is the right primitive for off-road autonomy

## Weaknesses

- Available material doesn't specify how visual and proprioceptive predictions are fused into a single planning objective, nor how failure-risk estimates are calibrated against real failures
- Off-road terrain diversity is vast; generalization claims are hard to assess without knowing training data scope
- No detailed comparison against established vision-based traversability/affordance methods

## Open Questions

- How well does the learned failure-risk estimate calibrate to true failure probability across terrain types unseen in training?
- Can proprioceptive prediction combine with, rather than replace, vision-based traversability estimation?

## Significance

A pointed extension of navigation world models into a modality that off-road autonomy specifically needs but the dominant scene-prediction paradigm ignores.

## Links

- [Paper](https://arxiv.org/abs/2609.19863)

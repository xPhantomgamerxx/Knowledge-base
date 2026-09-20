---
title: "Agentic Real2Sim: Physics-based World Modeling with Vision-Language Agents"
date: 2026-07-19
topic: WorldModels
tags: [real2sim, digital-twin, vision-language-agents, policy-evaluation, synthetic-data]
source: https://arxiv.org/abs/2607.19190
venue: "arXiv"
---

## Summary

Converts a single recorded real-world robot-object interaction video into an editable, executable physics simulator ("episodic twin") using a pipeline of VLM-driven agents (visual processing, physical-prior inference) rather than manual mesh cleanup and parameter tuning, enabling downstream policy fine-tuning and evaluation.

## Key Contributions

- Fully agentic real2sim pipeline: visual processing agent extracts segmentation/depth/geometry/pose, physical-prior agent infers material/mass/constitutive properties
- Demonstrates the agentic decisions can run on an open-weight VLM at a fraction of frontier-model cost with comparable conversion success rate
- Shows the converted twins support both policy fine-tuning with generated data and serving as a real-world evaluation surrogate

## Strengths

- Removes much of the manual labor (mesh cleanup, coordinate alignment, workflow glue) that has historically made real2sim conversion a bottleneck
- Open-weight VLM cost-efficiency claim, if it holds broadly, meaningfully lowers the barrier to real2sim data generation
- Dual use case (training data generation + evaluation surrogate) increases practical value

## Weaknesses

- Physical-parameter inference from video alone (mass, friction, material class) is inherently underdetermined; accuracy bounds aren't deeply characterized
- Built and evaluated primarily on DROID-style episodes; generalization to more complex multi-object or deformable scenes is unclear

## Open Questions

- How well do policies fine-tuned purely on agentic-real2sim data transfer back to the real robot compared to policies using real teleoperated data?
- Does the pipeline handle occlusion-heavy or fast dynamic interactions (drops, collisions) reliably?

## Significance

Automating real2sim conversion end-to-end with VLM agents (rather than dedicated CV pipelines) is a notable step toward cheap, scalable simulation data generation for VLA training and evaluation.

## Links

- [Paper](https://arxiv.org/abs/2607.19190)

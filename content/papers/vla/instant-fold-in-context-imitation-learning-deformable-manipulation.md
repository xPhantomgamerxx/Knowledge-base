---
title: "Instant-Fold: In-Context Imitation Learning for Deformable Object Manipulation"
date: 2026-06-04
topic: VLA
tags: [vla, in-context-learning, deformable-objects, sim-to-real]
source: https://arxiv.org/abs/2606.04269
venue: "arXiv"
---

## Summary

Instant-Fold performs single-demonstration in-context imitation learning for cloth and other deformable-object folding tasks, combining deformation-aware contrastive pretraining with a flow-matching transformer conditioned on the demonstration. The system is trained entirely in simulation and reportedly transfers zero-shot to real hardware without fine-tuning.

## Key Contributions

- A deformation-aware contrastive pretraining objective specifically designed for non-rigid object states, rather than reusing rigid-object representation learning recipes.
- A flow-matching transformer that conditions directly on a single provided demonstration at inference, enabling in-context task specification without gradient updates.
- Claimed zero-shot sim-to-real transfer with no fine-tuning step, which is a strong claim for the notoriously hard deformable-manipulation domain.

## Strengths

- Deformable object manipulation (cloth folding, in particular) is one of the harder subdomains in robot manipulation precisely because state representation is high-dimensional and dynamics are non-rigid; a purpose-built deformation-aware representation is a sensible response rather than forcing a rigid-object pipeline to cope.
- Single-demonstration in-context specification is an appealing interface for quickly retasking a deformable-manipulation system without per-task data collection.

## Weaknesses

- Zero-shot sim-to-real transfer for cloth dynamics is a strong claim given how difficult deformable-object physics is to simulate accurately; the sim-to-real gap for non-rigid materials (friction, self-collision, material properties) is typically much larger than for rigid-object manipulation, and this isn't addressed in the available summary.
- Single-demonstration conditioning likely constrains the system to tasks similar in structure to common folding demonstrations (e.g., towel/shirt folding); it's unclear how well it generalizes to deformable objects with very different topology (e.g., bags, ropes).

## Open Questions

- How robust is the sim-to-real transfer across different cloth materials, sizes, and initial configurations not represented in the simulation training distribution?
- Does performance degrade significantly when the single demonstration is imperfect or only partially matches the target object?
- How does Instant-Fold compare against deformable-manipulation methods that do use some real-world fine-tuning?

## Significance

A focused contribution to the underserved deformable-object manipulation subfield, applying the in-context-learning and flow-matching trends from general VLA research to a domain where they haven't been as thoroughly explored.

## Links

- [Paper](https://arxiv.org/abs/2606.04269)

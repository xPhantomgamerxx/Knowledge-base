---
title: "OASIS: From Simulation Data Collection to Real-World Humanoid Loco-Manipulation"
date: 2026-06-07
topic: Humanoid
tags: [humanoid, sim-to-real, synthetic-data, vla-posttraining]
source: https://arxiv.org/abs/2606.08548
venue: "arXiv"
---

## Summary

OASIS is a simulation-data-driven framework for humanoid loco-manipulation that automatically reconstructs realistic 3D object assets from reference images (using a 3D generative model plus a vision-language model to estimate physical dimensions and material properties), collects trajectories via in-sim teleoperation, and augments them with heavy domain randomization. A hierarchical visuomotor policy trained purely on this synthetic data transfers zero-shot to a real Unitree G1, and the authors report it matches or exceeds a policy trained on real-robot teleoperated data on most tasks — attributed largely to the broader lighting and environmental variation simulation rendering can cover.

## Key Contributions

- An automated pipeline for reconstructing physically-plausible 3D object assets from real-world reference images, removing manual asset-authoring as a bottleneck to scaling simulated manipulation scenes
- A two-stage data-collection recipe: teleoperation inside simulation to seed trajectories, followed by post-hoc domain randomization to multiply coverage of lighting, texture, and environmental conditions without additional operator time
- A hierarchical visuomotor policy architecture for humanoid loco-manipulation, trained entirely on the resulting synthetic data
- Real-robot evaluation on a Unitree G1 showing zero-shot sim-to-real transfer that outperforms a real-teleoperation-trained baseline on most evaluated tasks

## Strengths

- Directly targets the trajectory-quality-vs-scalability tradeoff that constrains humanoid data collection, and — unusually for a sim-based system — reports beating rather than merely matching real-teleoperation training data on the stated metric
- Automating 3D asset reconstruction from images (rather than requiring hand-built simulation assets) removes a common and labor-intensive bottleneck to building diverse manipulation scenes at scale
- The claimed mechanism — that lighting and environmental diversity in rendering, not just object/geometric variety, drives the sim-to-real transfer advantage — is a specific and testable hypothesis rather than a generic appeal to "domain randomization helps"
- A hierarchical policy that separates loco-manipulation planning from low-level execution matches an effective and increasingly common pattern in the whole-body humanoid control literature

## Weaknesses

- Physical property estimation (mass, friction, material) from a VLM applied to reference images is inherently approximate, and available sources do not report how errors in these estimates propagate to sim-to-real policy failures
- The "sim beats real teleop" comparison depends heavily on how much and how diverse the real-teleoperation baseline data was; if that baseline was collected in a narrower range of lighting/environment conditions than the simulation covers, the result may partly reflect an under-resourced baseline rather than an inherent simulation advantage
- Trajectories are still seeded by in-sim teleoperation rather than generated fully automatically, so some human-operator effort remains in the pipeline, and the paper does not appear to quantify how much
- Real-world validation is limited to a single embodiment (Unitree G1); it's unclear how sensitive the asset-reconstruction and randomization recipe are to a humanoid with a different sensor suite or actuation range

## Open Questions

- How large and how diverse was the real-teleoperation dataset used for comparison, and would a larger or more diverse real dataset close the reported gap?
- How does policy performance degrade as reconstructed asset geometry or estimated physical properties diverge further from the real object?
- Can the asset-reconstruction and randomization pipeline scale to deformable or articulated objects beyond what has been demonstrated so far?

## Significance

OASIS is a concrete existence proof that carefully engineered simulation data — automated realistic asset reconstruction combined with heavy domain randomization — can match or exceed real teleoperated data for zero-shot humanoid loco-manipulation transfer, reinforcing a broader shift toward treating simulation as the primary data engine for humanoid learning rather than a supplement to real-world collection.

## Links

- [Paper](https://arxiv.org/abs/2606.08548)

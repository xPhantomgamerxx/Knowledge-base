---
title: "HEFT: Heavy-Payload Full-size Humanoid Teleoperation with Privileged Motion Guidance and Windowed Payload Curriculum"
date: 2026-07-05
topic: Humanoid
tags: [humanoid, teleoperation, teacher-student-distillation, heavy-payload]
source: https://arxiv.org/abs/2607.02332
venue: "arXiv"
---

## Summary

HEFT is a teleoperation/control framework for heavy-payload full-size humanoids, demonstrated on a 175cm/65kg robot ("L7") tracking payloads up to 24kg. It uses teacher-student distillation: a privileged-information teacher trained on physically-plausible reconstructed references is distilled into a deployable policy that only requires noisy raw VR input, using a windowed payload curriculum for training.

## Key Contributions

- A teacher-student distillation pipeline where the teacher has access to privileged information (physically-plausible reconstructed motion references) unavailable at deployment, while the student is trained to operate from noisy raw VR signals alone.
- A "windowed payload curriculum" that presumably progressively increases payload weight/difficulty during training, a sensible approach given the risk of instability when directly training on maximum-payload scenarios.
- Real hardware validation on a genuinely large-scale humanoid (175cm, 65kg) handling up to 24kg payloads — a substantial fraction of the robot's own body weight, and a demanding test of whole-body balance and control under load.

## Strengths

- Privileged teacher-student distillation is a well-established and effective pattern for handling the sim-to-real / noisy-sensor gap, and applying it specifically to heavy-payload humanoid control is a sensible extension given how safety-critical accurate balance is under large loads.
- Testing on a genuinely heavy payload (24kg on a 65kg robot) pushes into a control regime that many humanoid manipulation papers, which typically focus on light object manipulation, don't address — directly relevant to eventual industrial/logistics use cases for humanoids.
- The windowed payload curriculum is a practical, safety-conscious training design choice for avoiding early-training instability at maximum load.

## Weaknesses

- Real-world validation on heavy payloads inherently carries higher risk of hardware damage or fall events during training/testing; the paper's description doesn't indicate how many trial failures or safety incidents occurred during development, which would be relevant to understanding the practical training cost.
- Results demonstrated on a single specific 175cm/65kg platform ("L7") — generalization to humanoids with substantially different mass/height ratios or actuator capabilities isn't established.

## Open Questions

- How does the windowed payload curriculum's progression rate affect both training stability and final maximum-payload capability — is there a trade-off between curriculum conservatism and final performance?
- What is the failure/fall rate during heavy-payload teleoperation, and how does HEFT's control degrade gracefully (or not) as payload approaches or exceeds the trained maximum?
- Does the privileged-teacher approach transfer to other humanoid platforms without needing to retrain the physically-plausible reference reconstruction from scratch?

## Significance

A notable step toward humanoids capable of real industrial-strength payload handling rather than light tabletop manipulation, directly relevant to use cases (logistics, warehouse, construction) that require humanoids to move meaningfully heavy loads while maintaining whole-body stability.

## Links

- [Paper](https://arxiv.org/abs/2607.02332)

---
title: "DeCAL: Towards Physically-Grounded Dexterous Vision-Language-Action Models via Contact-Aware Latent Co-Imagination"
date: 2026-09-08
topic: VLA
tags: [dexterous-manipulation, tactile-fusion, vla-architecture, contact-rich-manipulation]
source: https://arxiv.org/abs/2609.09119
venue: "EMNLP 2026"
---

## Summary

DeCAL targets dexterous manipulation involving contact-rich, fine-grained interactions, where standard VLA models struggle due to visual occlusion and complex contact dynamics that vision-only conditioning cannot resolve. It builds on a Mixture-of-Transformers (MoT) architecture with specialized expert modules, adding adaptive vision-tactile fusion through contact-aware gating and a vision-tactile latent co-imagination mechanism that jointly models visual and tactile dynamics.

## Key Contributions

- Targets a specific, well-motivated failure mode of vision-conditioned VLAs on dexterous tasks: when contact occurs (grasping, in-hand manipulation, insertion), the manipulator itself frequently occludes the relevant visual information, so vision-only policies lack the signal needed for fine, contact-rich control.
- Proposes contact-aware gating for adaptive vision-tactile fusion, letting the model weight tactile versus visual signal dynamically depending on contact state, rather than using a fixed fusion scheme.
- Introduces vision-tactile latent co-imagination, jointly modeling how visual and tactile observations will evolve together, extending world-model-style "imagination" objectives to the multimodal tactile setting.
- Built on a Mixture-of-Transformers backbone with specialized experts, allowing modality-specific processing (visual, tactile, language, action) to be handled by dedicated expert sub-networks rather than a single shared trunk.
- Accepted at EMNLP 2026, indicating validation of the language/multimodal-integration aspects of the work by a top NLP-adjacent venue.

## Strengths

- Directly addresses a real, physically-grounded limitation of vision-only VLA conditioning for dexterous manipulation (occlusion during contact), rather than a more abstract architectural improvement — this connects the method to concrete manipulation failure cases practitioners actually observe.
- The contact-aware gating design (dynamically reweighting tactile vs. visual signal) is a sensible inductive bias: tactile information should matter most exactly when vision is least informative (during contact/occlusion), and the gating mechanism operationalizes that intuition directly.
- Co-imagining visual and tactile dynamics jointly, rather than treating tactile sensing as a simple auxiliary input, is a more ambitious integration than typical "concatenate a tactile embedding" approaches in prior contact-aware VLA work.

## Weaknesses

- Requires tactile sensor hardware and corresponding tactile data streams, which remain far less standardized and less available at scale than vision-only or vision+proprioception data — this limits how broadly the method can be trained/deployed compared to vision-only VLAs.
- Mixture-of-Transformers with multiple specialized experts adds real architectural and training complexity relative to a single dense backbone; the paper's efficiency/inference-cost tradeoffs versus simpler fusion approaches (e.g., early concatenation) aren't established from available detail.
- As a dexterous-manipulation-specific method, generalization to non-contact-rich, more open-vocabulary manipulation tasks (where DeCAL's tactile machinery is unused) is unclear — the design may be over-specialized for its target task class.

## Open Questions

- How does DeCAL perform when tactile sensing is degraded, noisy, or entirely absent at deployment (sim-to-real or hardware variation across tactile sensor types)?
- Does the vision-tactile co-imagination objective transfer to embodiments with fundamentally different tactile sensor modalities (e.g., different spatial resolution or sensing principle), or is it tied to the specific sensor used in training?

## Significance

Contributes to the growing intersection of tactile sensing and VLA/world-model methods, making the case that contact-rich dexterous manipulation specifically needs multimodal (not just visual) latent dynamics modeling — relevant as dexterous hands and tactile sensors become more common in humanoid and manipulation platforms through 2026.

## Links

- [Paper](https://arxiv.org/abs/2609.09119)

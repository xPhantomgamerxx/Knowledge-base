---
title: "Set-Supervised Diffusion Policy: Learning Action-Chunking Diffusion through Corrections"
date: 2026-06-01
topic: VLA
tags: [vla, diffusion-policy, human-in-the-loop, dagger, vla-posttraining]
source: https://arxiv.org/abs/2606.01865
venue: "arXiv / RSS 2026"
---

## Summary

This RSS 2026 paper uses paired human-correction data — the robot's undesired action alongside the human's corrective action — as contrastive set supervision to train action-chunking diffusion policies that are more robust to distributional shift. It directly targets improving the quality of DAgger-style correction datasets rather than just collecting more of them.

## Key Contributions

- A "set-supervised" training objective that treats corrective action pairs as sets (undesired vs. corrective) rather than independent (state, action) samples, giving the diffusion model an explicit contrastive signal about what not to do.
- Integration with action-chunking diffusion policies, which are the dominant architecture family in current VLA action heads (e.g., in Diffusion Policy-style and ACT-style systems).
- Acceptance at RSS 2026 indicates peer-reviewed validation of the method beyond a preprint.

## Strengths

- Directly engages a known weakness of DAgger-style correction pipelines: raw corrective demonstrations alone don't tell the policy which action was actually being corrected away from, so the negative signal is normally discarded. Using it explicitly is a sensible efficiency gain over standard behavior cloning on the corrected data.
- Action-chunking diffusion policies are widely deployed, so a training recipe that improves their correction-data efficiency has broad applicability rather than being tied to one specific system.

## Weaknesses

- Contrastive objectives with "undesired action" labels risk being sensitive to how the undesired action is defined and captured; if the recorded "undesired" action is noisy or only weakly wrong (partial credit tasks), the contrastive signal may be misleading.
- No indication from the available summary of how much correction data is required relative to standard behavior cloning to see benefits, which matters for practical deployment cost.

## Open Questions

- How sensitive is the method to the granularity/timing of when a human intervenes to correct (early vs. late in a chunk)?
- Does the contrastive set-supervision approach scale to multi-task or cross-embodiment correction data, or was it validated on a narrower task set?
- How does it compare against RL-based fine-tuning on the same correction data budget?

## Significance

A direct, RSS-validated contribution to the human-in-the-loop / DAgger-style correction line of VLA post-training work that the digest is tracking as high priority — improves the data efficiency of a correction paradigm that's becoming standard practice for deploying generative policies.

## Links

- [Paper](https://arxiv.org/abs/2606.01865)

---
title: "Lost in Reconstruction: Aligning Action Representations with Language in Vision-Language-Action Models"
date: 2026-08-11
topic: VLA
tags: [action-tokenization, vla-architecture, language-grounding, data-augmentation, vla-posttraining]
source: https://arxiv.org/abs/2608.10484
venue: "arXiv"
---

## Summary

This paper argues that action verbs encode not just physical outcomes but *how* an action is performed, yet standard VLA action tokenizers are optimized purely for reconstruction under L1/L2 losses in raw action space — where numerical proximity doesn't necessarily correspond to linguistically meaningful distinctions. It introduces SALT (Semantically ALigned action Tokenizer), a VQ-VAE-style tokenizer with an added auxiliary objective that requires a frozen VLM to recover the episode instruction from quantized action latents.

## Key Contributions

- Empirically shows, on BridgeV2, that action trajectories carry verb-grounding information beyond what's captured by visual state changes, and that reconstruction-only discrete tokenization systematically erodes this information during quantization.
- Proposes SALT: augments a standard VQ-VAE action tokenizer with an auxiliary instruction-recovery objective using a frozen VLM, forcing the discrete action codebook to retain semantically/linguistically meaningful structure rather than only minimizing reconstruction error.
- Reports large gains on SimplerEnv: 71.9% average success with SALT vs. 42.7% for a reconstruction-only VQ-VAE tokenizer and 31.2% for FAST (a widely-used action tokenization baseline).
- Shows SALT develops verb-specialized discrete codes while still maintaining reconstruction fidelity, i.e., the semantic alignment objective doesn't come at the cost of action reconstruction quality.

## Strengths

- The core diagnosis — that reconstruction-only tokenization objectives can be actively misaligned with the language-conditioning that VLAs depend on — is a genuinely useful, generalizable insight about a design choice (action tokenizer training objective) that is usually treated as a solved/uninteresting preprocessing step.
- The margin over FAST (71.9% vs. 31.2%) is unusually large for what is essentially a tokenizer-level change rather than a new policy architecture, suggesting action tokenization quality is a significant, underexplored lever for VLA performance.
- Using a frozen VLM as the auxiliary supervision signal (rather than training a new alignment model) keeps the added training cost modest and reuses existing pretrained language grounding.

## Weaknesses

- Evaluated primarily on BridgeV2 data and SimplerEnv; it's unclear whether the verb-grounding information gap and the resulting SALT improvement generalize to embodiments/datasets with less rich or less consistent language annotation than BridgeV2.
- The instruction-recovery auxiliary objective depends on the quality and biases of the frozen VLM doing the recovery — a weak or narrowly-trained VLM could bottleneck or bias which semantic distinctions get preserved in the codebook.
- As a tokenizer-level intervention, results are reported via a specific downstream policy setup; how portably the pretrained SALT tokenizer transfers across different action-expert architectures (diffusion vs. autoregressive) is not established here.

## Open Questions

- Does the verb-specialization effect hold for compound or ambiguous instructions (e.g., "carefully place" vs. "place"), or mainly for coarse verb categories?
- Can the same semantic-alignment auxiliary objective be applied directly to continuous (non-quantized) action representations, or is it specifically a fix for information loss introduced by discretization?

## Significance

Reframes action tokenization — often treated as a fixed preprocessing choice — as a place where language grounding can be actively lost or preserved, adding a new axis (semantic alignment of the action codebook) to the ongoing 2026 discussion about how VLAs should represent actions for language-conditioned control.

## Links

- [Paper](https://arxiv.org/abs/2608.10484)

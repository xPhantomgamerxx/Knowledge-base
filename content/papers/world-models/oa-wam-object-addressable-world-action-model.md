---
title: "OA-WAM: Object-Addressable World Action Model for Robust Robot Manipulation"
date: 2026-05-07
topic: WorldModels
tags: [world-model, wam, object-centric, slot-attention, address-vectors, tsinghua, sjtu, ntu]
source: https://arxiv.org/abs/2605.06481
venue: "arXiv 2026"
---

## Summary

OA-WAM decomposes each frame into N+1 slot states (one robot slot + N object slots), where each slot has a persistent address vector and a time-varying content vector. This addressability lets the action decoder reliably reference specific objects even under scene shifts, solving the identity-entanglement problem in holistic WAMs. A world head predicts next-frame slot states while a flow-matching action head decodes a 16-step action chunk in the same forward pass, with slot attention enforced through address-only key routing. OA-WAM matches strong VLA and WAM baselines on LIBERO (97.8%) and SimplerEnv (79.3%) and achieves SOTA on the most challenging LIBERO-Plus geometric axes, with causal slot-intervention cosine 0.87 vs. ≤0.09 for holistic baselines.

## Key Contributions

- Object-addressable slot representation separating persistent identity (address) from time-varying state (content)
- Cross-slot attention routed through address-only keys, enforcing structural binding without extra tokens
- Unified world + action decoding in a single forward pass via flow-matching action head
- LIBERO 97.8%, SimplerEnv 79.3%; high causal binding score validating object tracking

## Significance

OA-WAM is the first WAM with explicit object-level addressability, showing that structured scene representations improve both manipulation accuracy and interpretability over holistic video-token approaches.

## Links

- [Paper](https://arxiv.org/abs/2605.06481)

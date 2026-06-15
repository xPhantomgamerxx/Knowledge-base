---
title: "RepWAM: World Action Modeling with Representation Visual-Action Tokenizers"
date: 2026-06-11
topic: WorldModels
tags: [world-action-model, visual-action-tokenizer, representation-learning, semantic-tokenization, WAM, manipulation]
source: https://arxiv.org/abs/2606.13674
venue: "arXiv 2606.13674"
---

## Summary

RepWAM addresses a core limitation of existing World Action Models that inherit reconstruction-oriented video tokenizers from pretrained video generation models: pixel reconstruction provides limited guidance for learning instruction-following dynamics. RepWAM trains a representation visual-action tokenizer that maps visual inputs into semantically aligned visual and latent action tokens, then pretrains the WAM to jointly model future visual states and the latent actions connecting them under language instructions, followed by adaptation to real robot trajectories.

## Key Contributions

- Representation visual-action tokenizer: produces semantically rich visual tokens aligned with latent action tokens, replacing reconstruction-focused tokenisation
- Joint visual-action pretraining objective: the WAM learns to predict future states and intermediate actions simultaneously, tightening the world-prediction/control coupling
- Ablations demonstrating the advantage of semantic visual-action tokenization over reconstruction-oriented alternatives at both pretraining and fine-tuning stages
- Strong performance across real-world manipulation tasks and simulation benchmarks

## Significance

Directly targets the tokeniser design — the lowest-level architectural choice in WAMs — and shows that semantically-aligned tokenisation delivers outsized gains, suggesting representation quality at the input stage is a critical factor often overlooked in world action model design.

## Links

- [Paper](https://arxiv.org/abs/2606.13674)
- [HTML](https://arxiv.org/html/2606.13674)
- [GitHub](https://github.com/wdrink/RepWAM)

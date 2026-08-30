---
title: "Revisiting Parameter Redundancy in Vision-Language-Action Models: Insights from VLM-to-VLA Adaptation"
date: 2026-06-30
topic: VLA
tags: [pruning, model-efficiency, vlm-adaptation, model-compression]
source: https://arxiv.org/abs/2606.31382
venue: "arXiv"
---

## Summary

This paper (Fengnian Zhang, Tao Huang, Siyu Xu, Zhong Jin, Chang Xu) questions the standard framing of VLA pruning, where post-pruning performance recovery is treated as expected and necessary — the authors argue this convention may actually mask indiscriminate pruning of parameters that were not truly redundant. They approach the problem through the lens of VLM-to-VLA adaptation, quantifying where parameters actually change (diverge) during that adaptation to identify which modules are genuinely redundant versus critical, and using this analysis to design a pruning scheme that reduces model size with substantially less need for recovery fine-tuning.

## Key Contributions

- Reframes the pruning question: instead of asking "how much can we prune and then recover via fine-tuning," the paper asks whether requiring recovery in the first place is a symptom of pruning the wrong (non-redundant) parameters.
- Quantifies the spatial distribution of parameter divergence during VLM-to-VLA adaptation, revealing structured, module-level heterogeneity — i.e., some modules change a lot during adaptation to the embodied domain (suggesting task-specific importance) while others barely change (suggesting inherited VLM redundancy for the robotics task).
- Uses controlled pruning as a diagnostic probe — comparing the direct performance impact of removing different parameter subsets without any fine-tuning — to empirically validate which modules are truly redundant versus critical, rather than inferring redundancy indirectly from post-hoc recovery success.
- Designs a multi-module joint pruning scheme informed by this analysis; the "Moderate" pruning configuration reduces memory footprint from 7.3GB to 5.6GB while success rate drops only modestly, from 96.9% to 89.0%.

## Strengths

- The core epistemological point — that needing recovery fine-tuning after pruning could indicate the wrong parameters were pruned, not that pruning inherently degrades performance — is a genuinely useful reframing that could shift how the community designs and evaluates VLA compression methods.
- Grounding the redundancy analysis in the VLM-to-VLA adaptation process itself (rather than analyzing the final VLA in isolation) is a clever way to get at which capabilities are truly embodiment-specific versus inherited-and-unused, giving a principled rather than purely empirical basis for pruning decisions.
- The no-fine-tuning controlled pruning probe is methodologically clean, isolating the direct effect of parameter removal from the confound of subsequent recovery training.

## Weaknesses

- A roughly 23% memory reduction for a roughly 8-point success rate drop (96.9% to 89.0%) is a real, non-trivial performance cost — while the paper's framing emphasizes achieving this without expensive recovery fine-tuning, the absolute performance-per-memory tradeoff still needs to be weighed against methods that do use recovery fine-tuning and might achieve a better tradeoff at the same memory budget.
- The analysis is grounded specifically in "VLM-to-VLA adaptation" divergence patterns, which likely means the redundancy insights are tied to how a particular VLM backbone was adapted into a particular VLA; it's unclear how well the same module-level redundancy pattern would transfer across different VLM base models or different VLA training recipes.
- The reported results (7.3GB → 5.6GB, 96.9% → 89.0%) appear to be from a single benchmark/config; broader validation across multiple base VLA architectures and task suites would strengthen the generality of the "structured redundancy" finding.

## Open Questions

- Does the module-level redundancy pattern discovered here (which modules diverge/matter most during VLM-to-VLA adaptation) generalize across different VLM backbones (e.g., different vision encoders or LLM sizes), or is it specific to whichever backbone was studied?
- How does the proposed pruning-without-recovery approach compare quantitatively, at matched final model size, to standard prune-then-fine-tune-to-recover baselines?
- Could the divergence-based redundancy analysis be used not just for pruning but for more targeted parameter-efficient fine-tuning (e.g., deciding which modules need LoRA adapters vs. can stay frozen)?

## Significance

By challenging the implicit assumption that pruning-then-recovery is simply the cost of compression, this paper offers a more principled, diagnosis-driven approach to VLA model compression grounded in how parameters actually change during embodied adaptation — a useful conceptual and practical contribution as VLA models grow larger and edge/on-robot deployment efficiency becomes more pressing.

## Links

- [Paper](https://arxiv.org/abs/2606.31382)

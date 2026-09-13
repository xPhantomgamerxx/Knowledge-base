---
title: "Learning to Use Imagination: Progress-Conditioned Future Utilization for World Action Models"
date: 2026-09-06
topic: WorldModels
tags: [world-action-model, imagination, progress-estimation, self-supervised, manipulation]
source: https://arxiv.org/abs/2609.06578
venue: "arXiv"
---

## Summary

This paper introduces ProWAM (Progress-Conditioned World Action Model), which addresses a subtle failure mode of World Action Models (WAMs): imagined future frames are used uniformly across a task's execution, even though how useful "imagining the future" is should change as a task progresses (e.g., early exploration vs. late precision alignment), and individual imagined-future latents are not equally reliable within the same moment. ProWAM introduces execution progress as an explicit, learned intermediate signal that gates how much the model relies on its own imagined futures.

## Key Contributions

- Identification of the "imagination utility varies by execution stage" problem in WAMs: existing methods incorporate imagined future dynamics with a fixed, non-adaptive weighting regardless of where the robot is in the task.
- Self-Supervised Dual-Temporal Progress Encoder (SS-DTPE): couples short-term action-observation interaction modeling with long-term recurrent progress aggregation, learning a progress representation from demonstrations without extra labels by exploiting their intrinsic temporal/semantic structure.
- A mechanism that uses this progress signal to adaptively modulate how the imagined future is fused into action generation, rather than a static fusion rule.
- Consistent empirical gains over strong VLA and WAM baselines across five simulation benchmarks and real-world tasks on two distinct robotic platforms.

## Strengths

- Tackles a genuinely underexplored axis in the WAM literature — most WAM papers focus on *what* to predict (video vs. latent vs. action) rather than *when/how much* to trust the prediction during execution.
- The self-supervised progress signal avoids requiring extra progress annotations, making it practical to bolt onto existing demonstration datasets.
- Validated on two real robot platforms in addition to five simulation benchmarks, giving more confidence that the progress-conditioning idea transfers beyond simulation.

## Weaknesses

- The benefit of progress-conditioning likely depends heavily on task structure (long-horizon, multi-stage tasks should benefit more than short reactive ones); the paper's generalization across very different task lengths is not fully characterized here.
- Adding a dual-temporal progress encoder increases model and training complexity relative to simpler fixed-weighting WAM baselines, with unclear cost/benefit at larger scale.
- As with related "when to trust imagination" work in this space (e.g., adaptive action execution for WAMs), the field risks converging on similar ideas independently; ProWAM's differentiation from those needs continued empirical scrutiny.

## Open Questions

- How does the learned progress signal behave under task failure or recovery (i.e., when true "progress" should decrease), and does the model handle non-monotonic progress correctly?
- Could the progress-conditioning signal be reused as a general-purpose reward/verification signal for RL fine-tuning, beyond just gating imagination usage?
- How sensitive are the reported gains to the specific choice of five simulation benchmarks, and do they hold on out-of-distribution long-horizon tasks?

## Significance

ProWAM contributes a reusable, self-supervised mechanism for making world-action models more selective about when imagined futures should be trusted — a practical refinement that could be layered onto many of the existing WAM architectures already in this field, rather than a wholesale new one.

## Links

- [Paper](https://arxiv.org/abs/2609.06578)
- [GitHub](https://github.com/JiuTian-VL/ProWAM)

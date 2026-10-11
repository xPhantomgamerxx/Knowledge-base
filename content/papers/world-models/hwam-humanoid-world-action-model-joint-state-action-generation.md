---
title: "HWAM: Humanoid World Action Model With Joint State-Action Generation"
date: 2026-10-08
topic: WorldModels
tags: [world-models, robotics, humanoid, world-action-model, whole-body-control, proprioception]
source: https://arxiv.org/abs/2610.12026
venue: "arXiv"
---

## Summary

HWAM targets a specific failure mode in hierarchical humanoid systems: VLA/WAM policies output reference actions that are then "realized" through a lower-level whole-body controller, dynamics, balance, and contact handling, and the robot's actual executed motion can diverge from the commanded reference — an "action-execution gap." HWAM makes the robot's post-execution proprioceptive state an explicit prediction target, generating it jointly with the reference actions rather than treating execution as an unmodeled black box.

## Key Contributions

- Formalizes and names the humanoid "action-execution gap" between a WAM/VLA's reference action output and the proprioceptive state the robot actually reaches after whole-body control, dynamics, and contact
- Joint state-action generation: the model predicts the realized post-execution body state alongside the reference action, injecting execution-outcome supervision directly into action learning instead of relying solely on the WBC/dynamics stack to compensate
- Reports a Candy Picking task success rate of 70.6% versus 43.3% for a Fast-WAM baseline, a large absolute margin on a contact-sensitive manipulation task
- Releases code, dataset, and a project page

## Strengths

- Names and directly targets a specific, previously under-modeled gap (reference action vs. realized motion) that is particularly acute for humanoids given their complex whole-body control stacks
- Joint prediction of state and action is a relatively lightweight architectural change that could be retrofitted onto existing WAM pipelines
- Large reported margin over a relevant, named baseline (Fast-WAM) on a precision task is a meaningful signal, assuming the comparison is fair

## Weaknesses

- Single reported benchmark task (Candy Picking) in the available summary is a thin evidentiary base for a general "humanoid execution gap" claim; broader task diversity is needed to confirm generality
- The paper is marked as under review, so the reported numbers have not yet passed external peer review
- Unclear how the approach scales to full-body humanoid tasks involving locomotion and balance recovery, versus the (likely simpler) tabletop/candy-picking regime used for evaluation

## Open Questions

- Does joint state-action prediction help equally for locomotion-heavy or balance-critical humanoid tasks, or mainly for fine manipulation like the tested task?
- How sensitive is the execution-gap reduction to the fidelity of the whole-body controller used downstream — would a better WBC make this gap, and hence HWAM's advantage, disappear?
- Can the realized-state prediction target be obtained cheaply at scale (e.g., from proprioceptive logs alone) or does it require careful real-robot instrumentation?

## Significance

Identifies and names a concrete, humanoid-specific failure mode — reference-action vs. realized-motion divergence — that generic (non-humanoid) WAM evaluations largely miss, and proposes a direct architectural fix rather than papering over it with better low-level controllers.

## Links

- [Paper](https://arxiv.org/abs/2610.12026)
- [HTML version / Project Page](https://hwam.vercel.app)

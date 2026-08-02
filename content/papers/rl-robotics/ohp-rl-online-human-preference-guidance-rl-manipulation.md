---
title: "OHP-RL: Online Human Preference as Guidance in Reinforcement Learning for Robot Manipulation"
date: 2026-05-15
topic: RL-Robotics
tags: [reinforcement-learning, human-in-the-loop, vla-posttraining]
source: https://arxiv.org/abs/2605.15971
venue: "arXiv"
---

## Summary

OHP-RL, from researchers at HKUST (Guangzhou), is a human-in-the-loop RL framework for real-world robot manipulation that treats human interventions as relative preference signals rather than as exact actions to imitate. It introduces a state-dependent preference gate that adaptively regulates how strongly human interventions should shape policy learning at each state, aiming to preserve autonomous exploration while still benefiting from intermittent, imperfect human guidance.

## Key Contributions

- Reframes human interventions in HIL-RL as preference information ("this was better than what the policy was about to do") rather than as ground-truth demonstrations to clone
- A state-dependent preference gate (a learned, per-state weighting term) that adaptively controls how much intervention data should influence policy updates, rather than applying a fixed blending coefficient everywhere
- Evaluated on three real-world contact-rich manipulation tasks on a Franka arm, compared against HIL-SERL, HG-DAgger, SIL-RI, and HACO
- Reports stronger success rates, faster convergence, and substantially lower human intervention effort than these prior approaches, with more stable, human-aligned behavior throughout training
- Ablation shows the state-dependent gate is what matters, not just the average gate value — a fixed gate at the same average weight underperforms the adaptive one on task efficiency even when both eventually reach 100% success

## Strengths

- The reframing of interventions as preferences rather than corrective demonstrations is a reasonable response to a real issue: an intervening human is often satisficing (avoiding a bad outcome) rather than providing the objectively optimal action, so naive behavior cloning on interventions can bake in suboptimal habits
- Compares against a genuinely relevant and reasonably strong baseline set (HIL-SERL, HG-DAgger, SIL-RI, HACO) spanning both RL-primary and imitation-primary approaches to intervention handling, rather than only weak baselines
- The ablation isolating the value of state-dependence (vs. a fixed average gate) is a meaningful piece of evidence that the mechanism, not just the extra tuning, is responsible for the gains
- Reduced human intervention burden is a practically important axis for real-world HIL-RL deployment, where operator time is often the true bottleneck, not compute

## Weaknesses

- Evaluated on only three tasks on a single robot platform (Franka), which is a narrow base for claims of general applicability across contact-rich manipulation
- The preference gate itself is a learned/tuned component whose robustness to differently-skilled or differently-styled human operators (i.e., interveners with different intervention thresholds or preferences) is not clearly established
- "Substantially lower human intervention effort" is a strong claim whose measurement methodology (e.g., how intervention effort is quantified — time, frequency, cognitive load) needs closer scrutiny than what surfaces in secondary summaries
- As with much of this HIL-RL literature, it's unclear how sensitive results are to the specific reward functions used per task, which could be doing more work than the preference-gating mechanism itself

## Open Questions

- How does OHP-RL perform with multiple, inconsistent human operators intervening on the same policy over time — does the state-dependent gate adapt to operator-specific styles, or assume a single consistent "preference function"?
- Does the approach scale to longer-horizon or multi-stage tasks where the notion of a "state-dependent preference" may need to account for task phase, not just instantaneous state?
- How does OHP-RL compare to PACT (arXiv:2606.03949), a contemporaneous paper addressing a very similar problem (credit misassignment from heterogeneous intervention data) — are the two approaches complementary or competing?

## Significance

OHP-RL is part of a growing cluster of 2026 papers (alongside PACT and others) recognizing that raw human interventions in HIL-RL carry richer, more nuanced signal than either a reward label or a demonstration to imitate — treating them explicitly as preferences, with state-dependent weighting, is a step toward more sample- and operator-efficient real-world robot RL.

## Links

- [Paper](https://arxiv.org/abs/2605.15971)
- [HTML](https://arxiv.org/html/2605.15971v1)

---
title: "FAR: Failure-Aware Retry for Test-Time Recovery and Continual Policy Improvement"
date: 2026-07-01
topic: VLA
tags: [vla, test-time-adaptation, continual-learning, vla-posttraining]
source: https://arxiv.org/abs/2607.01111
venue: "arXiv"
---

## Summary

Authored by Haoran Hao, Shahram Najam Syed, Jeffrey Ichnowski, and Jeff Schneider at Carnegie Mellon University, FAR is a framework that lets a robot policy recover from failures at test time by adapting its behavior based on its own recent unsuccessful attempts, rather than either blindly retrying the same action or requiring a human to intervene. It matters because naive retry strategies tend to repeat the same mistake, and FAR closes the loop by folding successful recovery trajectories back into training for continual improvement.

## Key Contributions

- Introduces Failure-Contrastive Preference Adaptation: after a failure, FAR identifies the failure-inducing action(s) via value estimation, then builds preference-learning data contrasting the failed action against alternative, higher-value actions to steer the policy away from the mistake
- Combines this with lightweight action perturbations during retries to encourage local exploration around the failure point rather than deterministic repetition
- Feeds successful recovery trajectories back into a continual training loop, so the policy incrementally improves from its own test-time failures over repeated deployment
- Evaluated across three simulation benchmarks spanning nine robot manipulation tasks, plus three real-world tasks on an xArm platform
- Reports that FAR improves both simulation and real-world task success rates while reducing the need for costly environment resets during online learning
- Ablations show that both distance-based filtering and critic-based selection of positive samples matter (naive positive-sample construction underperforms), that too few positive samples destabilizes adaptation, and that the amount of perturbation must be tuned per task horizon (less perturbation helps long-horizon tasks, more helps short-horizon tasks)

## Strengths

- Directly targets a very practical, common deployment problem — policies get stuck repeating the same failure — with a principled fix grounded in value estimation and preference learning rather than pure heuristic retry logic
- Validated on real hardware (xArm), not just simulation, which is not universal in this sub-area of test-time adaptation papers
- The ablations on perturbation magnitude vs. task horizon reveal a genuine, non-obvious tradeoff (short vs. long-horizon tasks need different exploration budgets), suggesting the authors probed the method's actual failure modes rather than just reporting headline numbers
- The continual-improvement loop (folding successful recoveries back into training) gives the method a compounding-benefit story beyond a single-episode fix

## Weaknesses

- Relies on a value estimator to identify "failure-inducing" actions, which is itself an imperfect signal, especially in long-horizon tasks with delayed or ambiguous credit assignment — errors in value estimation could mislabel which action actually caused the failure
- Real-world evaluation is limited to three tasks on a single robot platform (xArm), leaving open how well the approach generalizes across different arms, grippers, or dexterous end-effectors
- The reduction in "costly environment resets" is a practically important claim but the actual wall-clock/compute cost of the continual retraining loop itself is not clearly benchmarked against simpler retry baselines
- Nine simulated tasks across three benchmarks is a reasonably broad testbed, but it's unclear whether these benchmarks include genuinely novel failure types beyond what the value estimator was implicitly tuned against

## Open Questions

- How robust is the failure-inducing-action identification when failures stem from perception errors or external disturbances rather than the policy's own action choice?
- Does the continual training loop risk overfitting to idiosyncratic recovery trajectories from a specific deployment environment, degrading performance elsewhere ("catastrophic narrowing")?
- How does FAR compare quantitatively to other test-time recovery approaches, such as human-in-the-loop intervention methods or verifier-based re-ranking (e.g., HAVE)?

## Significance

FAR contributes a concrete recipe for one of the most practically important open problems in deployed robot learning — autonomous recovery from failure without human intervention — and its continual-improvement framing connects test-time adaptation to longer-term lifelong learning for deployed robots.

## Links

- [Paper](https://arxiv.org/abs/2607.01111)

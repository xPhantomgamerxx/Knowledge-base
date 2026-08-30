---
title: "Beyond Imitation: Self-Improving Robot Policies via Off-Policy Q-Planning"
date: 2026-08-21
topic: RL-Robotics
tags: [vla-posttraining, q-learning, self-improvement, behavior-cloning, offline-to-online-rl]
source: https://arxiv.org/abs/2608.21204
venue: "arXiv"
---

## Summary

This Georgia Tech paper (Varun Giridhar, Anant Khandelwal, Jeremy A. Collins, Ignat Georgiev, Animesh Garg) proposes Q-Planning: instead of RL-fine-tuning a large visuomotor behavior-cloning (BC) policy end-to-end, it bolts on a small, separately-trained off-policy Q-function that scores candidate action chunks sampled from the frozen BC policy. Because a Q-function estimates value rather than imitating actions, it can learn from both successes and failures — including the BC policy's own deployment rollouts — giving the overall system a self-improvement loop without ever updating the large policy's weights.

## Key Contributions

- Decouples "what actions are proposable" (frozen, large BC policy) from "which action is best" (small, cheaply-retrained Q-function), sidestepping the scalability problem of RL-finetuning multi-billion-parameter visuomotor policies.
- Inference-time mechanism: the frozen BC policy proposes N candidate action chunks; the Q-function scores them and the executed action is a single-step Q-weighted average — a lightweight test-time search rather than a new policy-gradient step.
- An online self-improvement loop where the Q-function is updated from the robot's own successful and failed deployment rollouts, closing the loop that pure BC cannot close (a BC policy that fails has no mechanism to learn from that specific failure).
- Empirical validation across simulation (LIBERO, bimanual RoboTwin) and two real-world contact-rich bimanual tasks, showing consistent improvement over self-improvement iterations: LIBERO-10 93%→99%, RoboTwin 83.8%→91.4% over 10 iterations; real-robot stack-cups 40%→90% and insert-wallet 25%→80% over 5 iterations.

## Strengths

- Directly targets a genuine, widely-acknowledged pain point: RL fine-tuning of large VLA/BC policies is expensive and unstable, and this sidesteps it by never touching the large model's weights.
- The asymmetry argument (Q-functions can consume failure data that BC cannot) is conceptually clean and is validated with real hardware results, not just simulation.
- Large relative gains on genuinely hard contact-rich bimanual tasks (insert-wallet 25%→80%) are a meaningful real-world demonstration, not just a benchmark-only result.
- Retains the pretrained BC policy's competence and multi-task generality (since it is frozen), which should reduce the risk of catastrophic forgetting or reward hacking relative to full fine-tuning.

## Weaknesses

- The improvement ceiling is fundamentally bounded by the frozen BC policy's action distribution — Q-Planning can only re-rank/re-weight what the BC policy is already capable of proposing, so it cannot learn genuinely new motion strategies outside the BC policy's support.
- Self-improvement from the robot's own rollouts implicitly assumes reasonably safe/informative failures and a way to label rollout success (reward/success signal) during deployment — the paper's reliance on this labeling mechanism for real-world iterations is a practical bottleneck not deeply interrogated.
- Comparisons are against BC and presumably standard RL-finetuning baselines, but it is unclear from available summaries how Q-Planning compares to more sophisticated inference-time search / re-ranking baselines (e.g., other test-time verifier or best-of-N approaches) rather than just BC.
- Five to ten iterations of self-improvement were needed to reach reported gains on real hardware, meaning wall-clock/robot-time cost of the online loop isn't trivial, and the paper's summarized results don't make the sample efficiency of the Q-function updates fully clear.

## Open Questions

- How does performance degrade (if at all) as the frozen BC policy's own competence on a task is very low, i.e., does Q-Planning need a "good enough" base policy to bootstrap from?
- Can multiple Q-functions be layered/composed for multi-objective or safety-constrained action selection without retraining the BC policy at all?
- How well does the self-improvement loop generalize to entirely new tasks not seen at BC-pretraining time, versus improving performance on tasks already partially covered by the BC policy?
- What is the actual sample/compute cost of the online Q-function updates relative to standard RL fine-tuning baselines it aims to avoid?

## Significance

Q-Planning is a pragmatic answer to one of the central open problems in the VLA/large-policy era — how to get self-improvement and RL-style benefits without paying the cost of RL-finetuning enormous visuomotor models — and its real-hardware bimanual results make a credible case that lightweight value-based post-training can meaningfully close the BC self-improvement gap.

## Links

- [Paper](https://arxiv.org/abs/2608.21204)
- [Project Page](https://q-planning.github.io/)

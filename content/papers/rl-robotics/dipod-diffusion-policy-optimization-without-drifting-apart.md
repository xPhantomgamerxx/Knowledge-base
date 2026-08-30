---
title: "DiPOD: Diffusion Policy Optimization without Drifting Apart"
date: 2026-06-11
topic: RL-Robotics
tags: [diffusion-policy, policy-gradient-rl, humanoid-control, variational-inference, continuous-control]
source: https://arxiv.org/abs/2606.13795
venue: "arXiv"
---

## Summary

DiPOD (UC Berkeley: Haozhe Jiang, Haiwen Feng, Pieter Abbeel, Jiantao Jiao, Angjoo Kanazawa, Nika Haghtalab) diagnoses and fixes an instability in RL fine-tuning of diffusion policies: because diffusion policy-gradient methods typically optimize a variational (ELBO) surrogate for the intractable log-likelihood, the ELBO can drift away from the true log-likelihood during training — a "double-drift" effect that misaligns the proxy policy gradient from the true return gradient and destabilizes training. DiPOD stabilizes this by interleaving self-distillation with the policy-gradient updates and adding an on-policy ELBO regularizer after every batch update.

## Key Contributions

- Names and formalizes the "double-drift" phenomenon: (1) the ELBO-to-log-likelihood gap widens during optimization, and (2) this gap misdirects the proxy policy gradient away from the true policy gradient of expected return — a mechanistic explanation for known instabilities in diffusion RL fine-tuning.
- Proposes an on-policy ELBO regularization term applied after each policy-gradient update, which re-tightens the variational bound to the current policy and re-aligns the proxy gradient.
- Combines this regularizer with periodic self-distillation, where the diffusion policy is distilled against its own recent behavior to prevent compounding drift over long training runs.
- Validates on both diffusion language model post-training and continuous-control diffusion policies, including a high-dimensional robot-control task: a Unitree G1 humanoid tracking reference motions (dance, run) from the LAFAN mocap dataset, compared against FPO++.

## Strengths

- Provides a genuine mechanistic diagnosis (double-drift) rather than an empirically-motivated patch, which gives the fix some theoretical grounding and predictive power for when it should matter (longer training, higher-dimensional action spaces).
- Cross-domain validation (language model diffusion post-training AND continuous-control robot tasks) is a meaningfully broader test of generality than a single-domain diffusion-RL paper.
- The Unitree G1 humanoid motion-tracking task is a genuinely hard, high-dimensional continuous-control benchmark (unlike toy MuJoCo tasks), and reported gains are in stability/reward/episode-length, which is exactly the failure mode (training collapse) the method targets.
- The method is an add-on regularizer/distillation step rather than a wholesale replacement of the underlying policy-gradient algorithm (FPO++), making it plausibly easy to retrofit into existing diffusion-policy RL pipelines.

## Weaknesses

- The Unitree G1 evaluation is in simulation (motion tracking against LAFAN references), not on physical hardware — sim-to-real transfer of the stabilized policy is untested, and stability gains in simulation don't guarantee the same benefit under real actuator noise/latency.
- Only two motion types (dance, run) are reported for the humanoid task; the breadth of tracking-task diversity is fairly narrow for claims about high-dimensional continuous control generality.
- The comparison baseline (FPO++) is itself a relatively recent, narrow diffusion-policy-RL method; broader baselines (e.g., PPO on non-diffusion policies, other diffusion-RL stabilization tricks) would better contextualize how much of the gain is DiPOD-specific versus generic regularization benefit.
- The added self-distillation step and per-batch ELBO regularization introduce extra compute overhead per update; the paper's summarized results don't make clear the wall-clock/compute cost trade-off versus the stability gained.

## Open Questions

- Does the double-drift diagnosis generalize to other classes of generative policies beyond diffusion (e.g., flow-matching policies), and would the same regularization fix apply?
- How does DiPOD perform on contact-rich manipulation tasks (rather than motion tracking, which is comparatively unconstrained/free-space) where policy-gradient noise interacts more with contact dynamics?
- What is the sensitivity of results to the frequency/strength of the ELBO regularization and self-distillation — is there a tuning burden that offsets the stability gains?
- Would DiPOD's fix still be necessary/beneficial if combined with other known diffusion-RL stabilization techniques, or is it redundant with some of them?

## Significance

DiPOD addresses a foundational stability problem underlying essentially all diffusion-policy RL fine-tuning approaches (a growing family given diffusion policies' popularity for robot manipulation and locomotion), making its diagnosis and fix broadly relevant beyond the specific humanoid benchmark it demonstrates.

## Links

- [Paper](https://arxiv.org/abs/2606.13795)
- [OpenReview](https://openreview.net/forum?id=KopdtMhn0U)

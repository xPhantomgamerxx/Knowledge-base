---
title: "Agentic RSR: Real-to-Sim-to-Real through Scene Reconstruction and Execution-Grounded Robot Policies"
date: 2026-10-07
topic: RL-Robotics
tags: [real-to-sim-to-real, agentic-pipeline, policy-synthesis, sim-to-real]
source: https://arxiv.org/abs/2610.10479
venue: "arXiv"
---

## Summary

Agentic RSR is an autonomous pipeline that turns a video of a real workspace plus a task description and robot model into a metrically accurate simulated scene (validated with MuJoCo-based interaction checks), has a coding agent author and refine a manipulation policy in that simulation using domain randomization and execution feedback to retry or revise, and then deploys the resulting policy on the physical robot with real-time safety checks. Across 18 reconstructed scenes and two robot platforms it reports close alignment between reconstruction fidelity and real-world execution outcomes.

## Key Contributions

- An end-to-end agentic loop unifying scene reconstruction from a single workspace video, policy authoring via a coding agent, simulation-based policy refinement, and real-robot deployment under one task-level interface.
- Uses execution feedback as a retry/revision signal during policy authoring, closing the loop between what the agent proposed and what actually works, instead of relying on one-shot sim-to-real transfer.
- Reports quantitative scene-reconstruction fidelity (mean four-view depth error 0.1057 m, grayscale SSIM 0.6990) across 18 scenes and two robots, with reported real-world task success tracking a large fraction of the corresponding simulated success rate.

## Strengths

- Reduces the manual engineering needed to build a simulation scene, reward, and policy for each new manipulation task down to a single video plus a task description.
- Having a coding agent author and refine the policy in simulation is a natural complement to (and differentiator from) RL-from-scratch pipelines, amortizing much of the "learning" into LLM-driven code synthesis plus targeted simulated training.
- Grounding policy evaluation and retries in execution feedback, not just reconstruction fidelity, is a sensible design choice for reducing the practical impact of the sim-to-real gap.

## Weaknesses

- It is unclear from available sources how tightly the reported reconstruction-fidelity metrics (depth error, SSIM) correlate with eventual real-robot task success; the two could decouple for contact-rich or deformable tasks.
- Evaluation spans 18 scenes and two robot platforms, which, while broader than many sim-to-real papers, is still modest relative to the diversity of real-world manipulation settings.
- Relying on a coding agent to author policies raises open questions about failure modes when generated policy code is subtly wrong but still passes simulated validation.

## Open Questions

- How does Agentic RSR's success rate compare directly against classical domain-randomization RL or recent VLA fine-tuning baselines on the same 18 scenes, rather than only via simulated-to-real success ratios?
- Does the approach extend to dynamic scenes (moving objects, deformables) or is reconstruction fidelity limited to static/quasi-static workspaces?
- What is the end-to-end wall-clock and compute cost per new task compared to directly collecting a handful of real demonstrations?

## Significance

Agentic RSR exemplifies a broader 2026 trend of using agentic, LLM-driven pipelines to automate the traditionally labor-intensive real-to-sim-to-real loop, potentially making scalable sim-based policy training accessible for arbitrary new tasks captured from a single video.

## Links

- [Paper](https://arxiv.org/abs/2610.10479)

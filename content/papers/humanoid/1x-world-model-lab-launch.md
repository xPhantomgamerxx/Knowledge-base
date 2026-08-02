---
title: "1X launches humanoid robot World Model Lab"
date: 2026-06-04
topic: Humanoid
tags: [humanoid, world-models, company-news]
source: https://www.1x.tech/discover/1x-world-model-lab
venue: "blog"
---

## Summary

1X (maker of the OpenAI-backed NEO humanoid) announced the 1X World Model Lab, a new research organization led by Sam Sinha, a founding research scientist at video-generation startup Luma AI, hired as Head of World Models. The lab's stated thesis, voiced by CEO Bernt Børnich as "you can't fine-tune your way to AGI," is a direct rebuke of the now-common VLA approach of grafting robotic action heads onto existing web-pretrained vision-language models, betting instead on pretraining large embodied world models from a heterogeneous mixture of physical and video data from the start.

## Key Contributions

- Establishment of a dedicated research organization focused on large-scale embodied world-model pretraining, rather than fine-tuning existing foundation models for robotic control
- Recruitment of Luma AI's Sam Sinha to lead the effort, bringing large-scale video generative modeling expertise directly into humanoid robotics
- A stated data strategy that treats physical/embodied data as a first-class pretraining signal from the outset: web-scale media, egocentric human video, simulation data, remote-operated robot data, and on-policy data collected from the deployed NEO fleet
- A public timeline commitment — early research results targeted before the end of 2026, alongside 1X's parallel plan to begin shipping $20,000 NEO units to early adopters in the same window

## Strengths

- Stakes out a clear, falsifiable technical position (ground-up world-model pretraining vs. fine-tuning a web-pretrained VLM) in a live architectural debate, rather than a vague "AI robotics" announcement
- The choice of a video-generation specialist to lead the lab is coherent given how heavily large-scale world models draw on video generative modeling techniques
- The stated data-mixture strategy is unusually broad, spanning web video, egocentric human footage, simulation, teleoperation, and fleet on-policy data, rather than committing to a single data source
- Tying the research bet to a concrete commercial deadline (NEO shipping to early adopters) gives the thesis a real deployment test rather than leaving it purely academic

## Weaknesses

- As a company announcement, it asserts a strategic direction without any released architecture, training run, benchmark, or technical result to evaluate against the stated claims
- The dismissal of the fine-tuning/VLA paradigm ("you can't fine-tune your way to AGI") reads as a positioning statement rather than a substantiated technical argument, particularly as competing efforts (e.g., RLWRLD's RLDX-1, and other VLA fine-tuning results published in the same period) continue to show that paradigm producing strong, measurable results
- No detail is given on model scale, compute budget, or intermediate milestones beyond "early results before the end of 2026," making it hard to assess how far along the effort actually is
- Reported alongside a broader leadership reshuffle, which raises questions about how disruptive this strategic pivot is to 1X's existing VLA/policy work and roadmap

## Open Questions

- What concrete technical results will the lab produce by its stated end-of-2026 target, and how will they be benchmarked against fine-tuned VLA baselines from competitors?
- How will 1X reconcile a long-horizon world-model research bet with the near-term commercial pressure of shipping NEO units on the same timeline?
- Will on-policy data from the deployed NEO fleet materialize at meaningful scale before the fleet itself is large enough to generate it, given the described data strategy depends partly on fleet scale?

## Significance

The launch is a visible signal that at least one leading humanoid company is publicly betting against the dominant VLA fine-tuning paradigm in favor of ground-up embodied world-model pretraining — a strategic fork that, if it proves out, could reshape how the field allocates research effort between adapting existing foundation models and building new embodied ones from physical data.

## Links

- [Blog Post](https://www.1x.tech/discover/1x-world-model-lab)

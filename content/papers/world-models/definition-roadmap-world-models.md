---
title: "A Definition and Roadmap for World Models"
date: 2026-07-07
topic: WorldModels
tags: [world-models, position-paper]
source: https://arxiv.org/abs/2607.06401
venue: "arXiv"
---

## Summary

This perspective paper, from the Physical Intelligence Team at Shanghai AI Laboratory, argues that "world model" has become an overloaded term used incompatibly across model-based RL, video generation, embodied robotics, and physical AI, and proposes a unifying scientific definition of world models as internal simulators that learn the structure and dynamics of an environment, along with a functional taxonomy (renderers, simulators, planners) and a staged roadmap for how the field should develop them.

## Key Contributions

- A candidate formal definition of "world model" intended to be precise enough to distinguish it from adjacent concepts (video generators, simulators, policies) while general enough to cover the diverse systems currently claimed as world models.
- A functional taxonomy separating world models by what they are used for — renderers (producing plausible observations), simulators (predicting environment state/dynamics forward), and planners (using predicted futures for decision-making) — crossed with a second axis of architectural paradigm (observation-level generative, latent-space, 3D-enhanced, omnimodal).
- Discussion of the "agent-environment loop" as the organizing frame for what a world model must minimally support (state representation, dynamics prediction, action conditioning).
- A staged roadmap proposing a developmental progression for the field, from current largely observation-level generative models toward richer latent-space and interactive/agentic world models.

## Strengths

- Addresses a real and increasingly acute terminology problem: "world model" is currently used for everything from Ha & Schmidhuber-style latent RNN dynamics models to text-to-video diffusion models to full physics simulators, which makes cross-paper comparison and benchmarking difficult; a serious attempt at disambiguation has clear community value.
- The functional taxonomy (renderer/simulator/planner) is a useful lens because it separates "can this model produce a plausible video" from "can this model be used to actually make decisions," which are frequently conflated in current world-model papers' claims.
- Coming from a group embedded in both the video-generation and embodied-robotics threads of this literature gives the roadmap practical grounding rather than being a purely philosophical exercise.
- As a perspective/position paper it is explicitly trying to shape how the field measures progress going forward, which is valuable timing given the current proliferation of "world-action model" (WAM) papers that each define scope differently.

## Weaknesses

- As with any proposed definition/taxonomy paper, adoption is not guaranteed — the field has repeatedly failed to converge on shared terminology for adjacent concepts (e.g., "foundation model," "generalist policy"), and there's no clear mechanism (shared benchmark, tooling) proposed here that would force compliance beyond citation.
- A definition broad enough to include renderers, simulators, and planners under one umbrella risks recreating the same conflation problem it aims to solve, if in practice most papers still only build one of the three functions but market their system with the full "world model" label.
- The staged roadmap, being a perspective piece, is necessarily aspirational/qualitative rather than benchmarked — it does not provide, for instance, quantitative criteria for when a system has crossed from one stage to the next.
- Being a single-institution (Shanghai AI Lab) proposal rather than a broad multi-lab consensus document, the taxonomy's categories reflect one group's framing of the space and may under-represent competing framings from, e.g., the model-based RL or robotics-simulation communities.

## Open Questions

- Will subsequent world-model/WAM papers actually adopt this taxonomy's vocabulary (renderer/simulator/planner) when describing their systems, or will terminological fragmentation persist regardless?
- Can the proposed definition be operationalized into concrete benchmark criteria that distinguish, e.g., a "simulator"-class world model from a "renderer"-class one in a way that's testable rather than just descriptive?
- How does this taxonomy accommodate hybrid systems (e.g., WAMs that both render observations and predict actions) that don't cleanly sit in one category?
- Does the roadmap's proposed staged progression match how the field is actually evolving, or will practical engineering pressures (compute cost, real-time constraints) produce a different trajectory?

## Significance

As "world model" and "world-action model" papers have proliferated rapidly through 2026 with widely varying scope and evaluation protocols, a serious attempt at a shared definition and staged roadmap — from a group with credibility in both generative video and embodied robotics — is a useful reference point for the field even if its specific taxonomy is not universally adopted, functioning similarly to how early "foundation model" position papers shaped (imperfectly) how that term was subsequently used.

## Links

- [Paper](https://arxiv.org/abs/2607.06401)

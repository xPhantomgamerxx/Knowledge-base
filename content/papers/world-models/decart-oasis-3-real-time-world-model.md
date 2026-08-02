---
title: "Decart Oasis 3: real-time interactive world model for driving/robotics simulation"
date: 2026-06-10
topic: WorldModels
tags: [world-models, synthetic-data, simulation, vla-posttraining]
source: https://techcrunch.com/2026/06/10/decarts-new-world-model-can-simulate-hours-of-photorealistic-driving-with-some-caveats/
venue: "blog / press coverage"
---

## Summary

Decart, a two-year-old startup recently valued at nearly $4B after a $300M raise backed by Toyota, Adobe, Nvidia, Sequoia, and Benchmark (among others), launched Oasis 3, an interactive world model that generates photorealistic, multi-camera driving environments in real time and is offered via API at roughly $0.02/second. It targets autonomous-vehicle companies wanting to simulate rare or dangerous edge-case scenarios cheaply, with an explicit roadmap toward robotics and other physical-AI use cases.

## Key Contributions

- A real-time, interactive world model capable of generating extended (multi-hour) photorealistic driving sessions from a single prompt, rather than short clips.
- Multi-camera, "infinite" generation designed specifically for simulating rare/dangerous AV edge cases without real-world risk.
- Decart's proprietary "DOS" (Decart Optimization Stack), vertically tuned across Nvidia/Amazon/Google hardware, claimed to cut inference cost by more than an order of magnitude versus competitors.
- Commercial API productization ($0.02/s pricing) aimed squarely at AV developers as a first market, with robotics/physical AI as a stated expansion target.

## Strengths

- Reported to produce the most photorealistic single-prompt environments relative to comparable interactive world models (e.g., Google's Genie 3, World Labs's Marble), per TechCrunch's hands-on comparison.
- Real-time interactivity plus multi-hour session length is a meaningfully different capability class than prior short-clip video world models, directly useful for long-tail scenario coverage in AV testing.
- Strong strategic backing (Toyota, Adobe Ventures, Toyota Ventures, Nvidia, Sequoia, Benchmark) signals real industry interest in this as a simulation-layer play, not just a research demo.
- Cost-optimized inference stack targets the actual bottleneck for this class of product (compute cost per simulated second), which is the right lever if the goal is to make world-model-based simulation commercially viable at scale.

## Weaknesses

- TechCrunch's hands-on testing found significant degradation over extended sessions: thematic/environmental consistency breaks down as the user moves through the world (a prompted "New York City street" drifted into a generic Western city), and returning to an earlier location does not reproduce it — the world is not persistent or spatially consistent, it is regenerated locally.
- Physics is not properly simulated: testers observed cars passing through objects, which is a serious problem for a product explicitly marketed for safety-critical AV edge-case testing.
- Controls were reported as unresponsive/laggy, undermining the "interactive" framing for real-time decision-relevant simulation.
- These are precisely the properties (spatial consistency, physical plausibility, controllability) that matter most for the stated use case (testing rare/dangerous driving scenarios) — a photorealistic but physically incoherent simulator risks producing edge cases that are visually convincing but dynamically meaningless, which could be worse than no simulation if used naively for AV validation.

## Open Questions

- Are AV customers actually using Oasis 3 for anything beyond visual/perception-model stress testing, given the acknowledged lack of physical grounding — or is closed-loop planner/control testing still out of reach?
- How does Decart plan to address world persistence and physical consistency, and is that even tractable within a purely generative (non-physics-engine) video-world-model architecture, or does it require hybridizing with a physics simulator?
- What does the promised pivot to robotics/physical-AI look like concretely, given manipulation tasks are typically far less forgiving of physics violations than driving corridor scenarios?
- No independent, quantitative benchmark numbers are cited in press coverage — how does Oasis 3 compare to Genie 3 / Marble / Cosmos on standard world-model benchmarks (e.g., WorldModelBench) rather than qualitative impressions?

## Significance

Oasis 3 is a visible commercial bet that photorealistic, real-time interactive world models can become a paid simulation layer for physical AI (starting with autonomous driving), and the TechCrunch review is a useful public data point on how far current generative world models still are from physically consistent, persistent simulation — a gap that is central to whether such models can be trusted for safety-relevant testing rather than just visual demos.

## Links

- [TechCrunch coverage](https://techcrunch.com/2026/06/10/decarts-new-world-model-can-simulate-hours-of-photorealistic-driving-with-some-caveats/)

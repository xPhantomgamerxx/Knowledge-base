---
title: "Data Standards for Humanoid Robotics: The Missing Infrastructure for Physical AI"
date: 2026-06-18
topic: Humanoid
tags: [humanoid, data-standards, infrastructure, position-paper, iso-standard]
source: https://arxiv.org/abs/2606.19769
venue: "arXiv"
---

## Summary

A position paper arguing that humanoid robotics scalability is bottlenecked not primarily by model architecture or data volume, but by the lack of shared data standards that make embodied experience interpretable, comparable, and reusable across robots, organizations, and time. The authors draw on their work developing ISO/WD 26264-1 ("Humanoid robot datasets — Part 1: General requirements") within ISO/TC 299/WG 16.

## Key Contributions

- Frames humanoid robot data as fundamentally "embodied interaction data" — inseparable tuples of body, action, task, scene, execution trace, and outcome — rather than isolated i.i.d. samples, and argues current dataset practices lose this structure.
- Identifies "physical coherence" (consistent timing, coordinate frames, calibration, kinematics, units, synchronization) as a prerequisite for multimodal data reuse across labs/platforms, and argues this is routinely broken in practice.
- Reframes the field's data bottleneck: not pure scarcity, but non-cumulative data caused by high collection costs, data silos, and inconsistent evaluation protocols — meaning more data collection without standards won't fix the underlying problem.
- Reports concrete involvement in an active ISO standardization effort (ISO/WD 26264-1), giving the position paper more institutional weight than a purely academic argument.

## Strengths

- Names a real, under-discussed problem: the field has many large datasets (AgiBot World, Open X-Embodiment, etc.) that are difficult to combine or cross-validate against due to inconsistent conventions, and this paper articulates why that matters concretely.
- Grounding the argument in an actual standards body (ISO/TC 299/WG 16) rather than a purely academic proposal gives it a plausible path to real-world adoption.
- The three-part framing (embodied interaction data / physical coherence / non-cumulative bottleneck) is a genuinely useful conceptual vocabulary for discussing data quality issues that are otherwise discussed ad hoc.

## Weaknesses

- As a position/standards paper, it offers no empirical validation — no demonstration that adopting the proposed standard actually improves cross-dataset reuse or downstream policy performance.
- Standards efforts in fast-moving research fields often lag behind or get bypassed by de facto community conventions (e.g., LeRobot's dataset format); it's unclear whether ISO-level standardization can keep pace with a field iterating this quickly.
- No discussion of incentive alignment — commercial humanoid companies with proprietary data pipelines (Figure, 1X, Tesla, etc.) may have limited incentive to adopt open interoperability standards that reduce their data moat.

## Open Questions

- Will major commercial and open-source dataset providers (AgiBot, Open X-Embodiment, LeRobot) actually adopt ISO/WD 26264-1, or will it remain a parallel, lightly-used standard?
- What concrete tooling (validators, converters) would be needed to make compliance practical rather than aspirational?
- How does this proposed standard relate to existing robotics data conventions (ROS bag formats, RLDS, LeRobotDataset) — is it a superset, a complement, or a competing format?

## Significance

Raises a structural, often-overlooked issue in the current "more data, bigger models" race in humanoid robotics — that data quantity without interoperability standards limits the field's ability to compound progress across organizations — which is a useful counterpoint to purely scale-focused narratives.

## Links

- [Paper](https://arxiv.org/abs/2606.19769)

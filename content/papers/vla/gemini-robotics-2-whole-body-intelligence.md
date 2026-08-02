---
title: "Gemini Robotics 2: whole-body VLA release for humanoids"
date: 2026-07-30
topic: VLA
tags: [vla, humanoid, whole-body-control, google-deepmind]
source: https://deepmind.google/blog/gemini-robotics-2-brings-whole-body-intelligence-to-robots/
venue: "blog"
---

## Summary

Google DeepMind's Gemini Robotics 2 is a suite of three models — Gemini Robotics 2 (a whole-body VLA), Gemini Robotics ER 2 (an embodied-reasoning planner for multi-step and multi-robot tasks), and Gemini Robotics On-Device 2 (an efficient on-device VLA that adapts to new embodiments with under 200 examples) — that for the first time extends Google's robotics stack from tabletop, upper-body manipulation to controlling an entire humanoid, from locomotion to fine finger motion. It matters because it marks a shift from arm-only VLA demos toward single models issuing coordinated whole-body commands (walking, reaching, dexterous grasping) from a single natural-language instruction.

## Key Contributions

- Whole-body control: a single VLA that can walk a humanoid (demonstrated on Apptronik's Apollo 2) to a location, pick up an object, walk again, and place the object precisely, chaining locomotion and manipulation from one instruction rather than separate navigation/manipulation stacks
- Gemini Robotics ER 2 adds embodied reasoning for multi-step task decomposition and coordination across multiple robots ("robot teamwork")
- On-Device 2 targets fast few-shot adaptation to new robot embodiments (reportedly a few hours, under 200 demonstrations) without cloud dependency
- New safety scaffolding, including an ASIMOV-Agentic benchmark for agentic tool-use refusal and automated human-proximity detection that halts a humanoid when a person approaches and resumes once clear
- Published safety evaluation report alongside the model release

## Strengths

- First public demonstration of a single Gemini-family model driving true whole-body humanoid behavior (locomotion + manipulation) rather than tabletop-only arm control, a meaningful capability jump over prior Gemini Robotics releases
- Three-tier model family (cloud whole-body VLA, embodied-reasoning planner, on-device VLA) addresses different deployment constraints (latency, connectivity, compute) rather than a one-size-fits-all model
- Explicit safety framing (proximity halting, agentic refusal benchmark) and a published safety report shows some transparency uncommon in commercial robotics announcements
- Few-shot embodiment adaptation (under 200 examples) for On-Device 2, if accurate, would meaningfully lower the cost of porting policies to new hardware

## Weaknesses

- Reported success rates are modest and uneven: e.g., Apollo picking objects from a table (~68%), floor (~46%), and shelf (~76%), and stronger performance on two-finger grippers than multi-finger dexterous hands — whole-body integration has not solved core manipulation reliability
- Demonstrations are on a small number of partner-gated humanoid platforms (Apptronik Apollo 2), not shown across a heterogeneous robot fleet, so claims of general cross-embodiment whole-body intelligence are not yet substantiated
- Movement speed is explicitly acknowledged by DeepMind as still slower and less reliable than human motion
- As a blog/marketing release rather than a peer-reviewed paper, technical details (training data composition, architecture, whole-body action representation, quantitative benchmarks beyond a few numbers) are sparse and not independently verifiable
- The safety report reportedly does not evaluate underlying functional-safety architecture (certified hardware, redundancy, real-time guarantees), only higher-level behavioral safety

## Open Questions

- How does the whole-body action space (joint-level whole-body control vs. separate locomotion/manipulation modules coordinated by the VLA) actually work architecturally, and does DeepMind plan to publish a technical report?
- Will whole-body capabilities generalize beyond Apptronik's Apollo 2 to other humanoid morphologies, and how much re-training/adaptation is required per platform?
- What is the actual latency and failure-recovery behavior when locomotion and manipulation sub-goals conflict or a mid-sequence failure occurs (e.g., a dropped object mid-walk)?
- How rigorous is the ASIMOV-Agentic safety benchmark, and how does it compare to independent third-party safety evaluation?

## Significance

This release is a notable industry signal that leading labs are moving VLA research from arm-centric tabletop manipulation toward full-body humanoid control as the next capability frontier, intensifying competition with NVIDIA (Isaac GR00T), Physical Intelligence, and humanoid hardware makers over who controls the "brain" layer of general-purpose humanoids.

## Links

- [Blog post](https://deepmind.google/blog/gemini-robotics-2-brings-whole-body-intelligence-to-robots/)

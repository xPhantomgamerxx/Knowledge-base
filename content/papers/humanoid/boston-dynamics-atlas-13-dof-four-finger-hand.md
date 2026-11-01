---
title: "Boston Dynamics Unveils New 13-DOF Four-Finger Tactile Hand for Atlas"
date: 2026-10-02
topic: Humanoid
tags: [humanoid, boston-dynamics, dexterous-manipulation, hardware, tactile-sensing]
source: https://roboticsandautomationnews.com/2026/10/02/boston-dynamics-unveils-new-four-finger-hand-for-atlas-humanoid-robot/105440/
venue: "blog"
---

## Summary

Boston Dynamics replaced electric Atlas's earlier 7-DOF five-finger hand with a new 13-DOF four-finger design (a 4-DOF opposable thumb plus three 3-DOF fingers), directly actuated and fitted with dense tactile sensing across fingertips and palm. The redesign trades anthropomorphic finger count for manipulation capability — in-hand reorientation, pinch/tripod grasps, slip recovery, and power-tool operation — while being built for mass manufacturing and high-fidelity sim-to-real RL training.

## Key Contributions

- Removes the pinky and redesigns around a 4-DOF thumb plus three 3-DOF fingers (13 DOF total, up from 7), justified by an internal study (staff taped the pinky and ring finger together for a day to see what tasks were actually lost).
- Direct actuation (no cable/tendon transmission) paired with dense tactile sensing at fingertips and palm, explicitly aimed at generating higher-fidelity sim-to-real training data.
- Demonstrated a full tool-use workflow: grasp drill, insert bit, pull trigger, drill into wood — not just pick-and-place grasping.
- The design process combined physical experiments, simulation, and 3D-printed mockups to navigate competing objectives (grasp coverage vs. dexterity vs. manufacturability vs. cost vs. durability).

## Strengths

- A concrete, falsifiable design rationale (the taped-finger test) rather than a hand-wavy "more DOF is better" argument — shows genuine engineering trade-off analysis.
- Pairing direct actuation with dense tactile sensing is a sensible hardware bet for closing the sim-to-real gap for contact-rich manipulation, currently the dominant bottleneck in humanoid dexterity.
- The tool-use demo (drilling) is a meaningfully harder task class than typical grasp-and-place demos shown by competitors.

## Weaknesses

- All claims come from company PR/blog and secondary trade press — no independent benchmark numbers, failure-rate statistics, or peer-reviewed data accompany the announcement.
- "13 DOF" and the finger-count trade-off are asserted as conclusions, but no comparative grasp-success data versus the previous 7-DOF hand (or competitors like Figure's or Clone Robotics' hands) has been published.
- Secondary sources conflict on basic facts (e.g., executive job titles), underscoring that this is unverified secondary coverage rather than a primary technical report.

## Open Questions

- Does dropping the fifth finger measurably hurt grasp success on irregular or small objects in real deployments, or only in the internal tape-test anecdote?
- What is the actual sim-to-real transfer gap for policies trained on this hand's tactile stream, and has it been quantified anywhere?
- Will Boston Dynamics publish a technical whitepaper with real benchmark comparisons, or does this remain a PR-only hardware reveal?

## Significance

A rare instance of a major humanoid vendor explicitly departing from anthropomorphic five-finger hand design in favor of a manipulation- and manufacturability-optimized alternative, which may influence how other humanoid companies approach the hand-design trade-off space.

## Links

- [Blog](https://roboticsandautomationnews.com/2026/10/02/boston-dynamics-unveils-new-four-finger-hand-for-atlas-humanoid-robot/105440/)

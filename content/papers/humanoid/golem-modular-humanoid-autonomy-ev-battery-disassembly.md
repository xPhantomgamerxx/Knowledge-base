---
title: "GOLEM: Modular Humanoid Autonomy Towards Electric Vehicle Battery Disassembly"
date: 2026-08-21
topic: Humanoid
tags: [industrial-robotics, modular-architecture, disassembly, ros2, sim-to-real]
source: https://arxiv.org/abs/2608.21550
venue: "arXiv"
---

## Summary

GOLEM (Generalized Open Library of Embodied Modules) is an open-source, modular ROS 2/Docker system architecture that lets a Unitree H1-2 humanoid perform electric-vehicle battery disassembly — a repetitive, hazardous task involving hundreds of fasteners on energy-dense packs — by treating walking, manipulation, stability, navigation, and spatial memory as independently swappable modules with abstract interfaces, backed by MuJoCo/IsaacLab digital twins that mirror the real robot's interface. It demonstrates real fastener removal from a Hyundai Ioniq 5 battery pack across three escalating levels of autonomy.

## Key Contributions

- A modular capability architecture (walking, manipulation, dynamic stability, navigation, spatial memory as separately abstracted, swappable modules) rather than a single monolithic policy, aimed at reusability across different humanoid platforms/tasks.
- Docker-based ROS 2 abstraction layer where simulated (MuJoCo, IsaacLab) and physical robot expose matching interfaces, easing sim-to-real module swapping.
- A concrete industrial use case — EV lithium-ion battery pack disassembly for critical-material recovery — demonstrated end-to-end on real hardware (Unitree H1-2) against a real production battery pack (Hyundai Ioniq 5).
- A staged evaluation across three autonomy levels that explicitly measures degradation from tethered to free-standing to fully autonomous (navigation-integrated) operation, rather than only reporting a single best-case number.

## Strengths

- Directly targets a real, economically and environmentally important industrial problem (EV battery recycling/disassembly) rather than a generic lab manipulation benchmark.
- The autonomy-ladder evaluation methodology is unusually honest: it explicitly reports the performance cost of adding autonomy (navigation-induced pose variance), rather than cherry-picking the best configuration.
- Modular, open-source architecture with digital twins lowers the barrier for other labs to reuse individual capability modules (e.g., the navigation or grasping stack) without adopting the whole system.

## Weaknesses

- The reported degradation is severe: fastener-grasping success on the real pack falls from 97% tethered to 87% free-standing to just 37% once navigation-induced pose variance is introduced — meaning the fully autonomous configuration is far from reliable for actual deployment.
- Navigation accuracy of ~13 cm at a 6 m goal is coarse relative to the precision fastener manipulation requires, which is very plausibly the root cause of the steep autonomy-level performance drop.
- Single robot platform (H1-2), single vehicle/battery pack model (Ioniq 5) — generalization across battery pack designs (varying fastener types, layouts, manufacturers) is untested.
- "Open-source" and "modular" claims are architectural; the paper does not report throughput/cycle-time numbers that would let a reader judge economic viability against manual or purpose-built (non-humanoid) disassembly lines.

## Open Questions

- Can the navigation and stability modules be improved enough to close the 87%→37% autonomy gap, or does closing it require re-architecting perception/grasping to be robust to pose uncertainty rather than just improving localization?
- How much of the module interface abstraction genuinely transfers to a different humanoid platform (e.g., a Unitree G1 or Figure robot) without rework?
- What is the actual per-pack disassembly time/cost compared to manual labor or dedicated (non-humanoid) recycling automation?

## Significance

A rare humanoid paper that treats industrial disassembly/recycling — rather than warehouse logistics or household chores — as the target application, and its transparent reporting of the sharp reliability drop from tethered to autonomous operation is a useful, sobering data point on how far current whole-body autonomy stacks are from unsupervised industrial deployment.

## Links

- [Paper](https://arxiv.org/abs/2608.21550)

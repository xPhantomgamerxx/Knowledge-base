---
title: "Xiaomi's Second-Generation Humanoid Robot (Tieda)"
date: 2026-08-19
topic: Humanoid
tags: [industry, humanoid-hardware, manufacturing, embodied-large-model]
source: https://www.digitimes.com/news/a20260821PD231/xiaomi-robot-beijing-2026-production.html
venue: "blog / press (Digitimes, Pandaily, eWeek, BigGo Finance)"
---

## Summary

Xiaomi publicly debuted its second-generation humanoid robot, reportedly called "Tieda," at the 2026 World Robot Conference in Beijing (Aug 19, 2026), after roughly four months of embedded training inside Xiaomi's own EV factory. Standing 1.70 m and weighing 66 kg with 66 degrees of freedom (33 in the hands), it is presented as running fully autonomous action selection driven by an embodied large model built on Xiaomi's Xiaomi-Robotics-0/VLA foundation-model line, rather than being teleoperated — distinct from the previously logged Xiaomi-Robotics-U0 world-model and Xiaomi-Robotics-1/XR-1 VLA papers, which are the underlying research rather than this physical platform reveal.

## Key Contributions

- A physical, factory-trained humanoid platform (1.70 m / 66 kg, 66 DoF with a notably hand-heavy 33 DoF allocation) presented as Xiaomi's second-generation hardware iteration.
- Reported real production-line deployment (not just a lab demo): four months of on-the-job training at a Xiaomi EV factory performing dual-side self-tapping nut installation, center-console side-panel sorting, and material-bin folding/recycling.
- Quantified before/after improvement on a real task: self-tapping nut installation success rose from 90.2% to 98% over the four-month training period, described as approaching (within ~1 point of) the qualification bar for human factory workers; panel-sorting and material-bin handling both reported around 90% success.
- Framed as autonomous rather than scripted or teleoperated — actions are described as selected by an embodied large model integrating multimodal perception and reinforcement learning, built on the general-purpose Xiaomi-Robotics-0 VLA foundation model.
- Explicit statement that the robot is a manufacturing-showcase prototype, not planned for commercial/consumer sale.

## Strengths

- Reporting a real longitudinal factory deployment (four months, with a before/after success-rate trajectory) is more substantive than a one-off demo video, and the 90.2%→98% improvement gives a genuine (if narrow) signal of on-the-job learning.
- Approaching human-qualification-level success on a real fastener-installation task is a meaningful bar for industrial usefulness, since fastener/screw tasks are a common stress-test for dexterous manipulation precision.
- Ties the hardware reveal directly to Xiaomi's own published VLA/world-model research line (Xiaomi-Robotics-0/U0/XR-1) rather than presenting it as an unrelated hardware announcement, giving at least some technical grounding.

## Weaknesses

- This is press/company coverage, not a technical report — there is no paper detailing the embodied large model's architecture, training data volume, or evaluation methodology behind the 90.2%/98%/90% figures, so they cannot be independently verified.
- All demonstrated tasks (nut installation, panel sorting, bin handling) are narrow, structured, single-factory tasks; there is no evidence yet of generalization outside this specific EV production line or transfer to unstructured/home environments.
- "Fully autonomous, not teleoperated" is an important but unverified claim — press coverage does not describe how this was audited (e.g., whether teleoperation was used at all during the four-month training window before evaluation).
- Explicitly not for sale and framed as an internal manufacturing showcase, so it should be read as a capability demonstration and ecosystem/PR signal (tying into Xiaomi's "Human x Car x Home" strategy) rather than a product ready for external deployment or benchmarking.

## Open Questions

- What specifically changed between generations one and two (compute, actuators, the 33-DoF hand redesign, or primarily the training pipeline)?
- How much of the four-month improvement curve is attributable to the embodied large model learning versus incremental hardware/fixture engineering on Xiaomi's side?
- Will Xiaomi release a technical paper or benchmark comparable to its earlier Xiaomi-Robotics-0/XR-1 publications to substantiate the platform's claimed autonomy and generalization?

## Significance

Notable as a large consumer-electronics/EV manufacturer (rather than a robotics-focused startup) demonstrating a humanoid trained and evaluated inside its own real production line with quantified before/after task success, reinforcing the trend of vertically-integrated companies using their own factories as humanoid training/testing grounds ahead of any commercial robot sale.

## Links

- [Digitimes coverage](https://www.digitimes.com/news/a20260821PD231/xiaomi-robot-beijing-2026-production.html)
- [Pandaily coverage](https://pandaily.com/xiaomi-new-humanoid-robot-after-auto-factory-training-wrc-2026-aug2026)
- [eWeek coverage](https://www.eweek.com/news/xiaomi-humanoid-robot-ev-factory-testing/)

---
title: "1X NEO Hands — 25-DoF tendon-driven, force-transparent dexterous hand"
date: 2026-07-09
topic: Humanoid
tags: [dexterous-manipulation, hand-hardware, tendon-driven, tactile-sensing, 1x-technologies, neo]
source: https://www.1x.tech/discover/neos-hands
venue: "blog"
---

## Summary

1X Technologies officially unveiled a new hand for its NEO home humanoid: 25 degrees of freedom (22 actuated across fingers and palm, 3 at the wrist), driven by tendons at low 5:1–15:1 gear ratios instead of the 100:1–200:1 ratios typical of industrial grippers, making every joint natively force-controlled and backdrivable — what 1X calls "force transparency." The hand is IP68-sealed for washability and is paired with high-resolution fingertip tactile sensing, positioned by 1X as closing the "write-only" actuation gap of conventional robot grippers that can move but cannot feel.

## Key Contributions

- A quasi-direct-drive tendon actuation scheme at low gear ratios (5:1–15:1) that makes joints inherently backdrivable, so contact forces can be sensed through the actuators themselves rather than relying solely on dedicated force sensors
- 25 total DoF (22 in fingers/palm, 3 at the wrist) aimed at approaching human-hand dexterity in a mass-producible form factor
- IP68 environmental sealing, enabling the hand to be washed/exposed to liquids — notable for a home-robot context where hands will contact food, dishes, and household mess
- High-resolution fingertip tactile sensors reported to detect normal force, contact location, and shear force, supporting slip detection and real-time grip adjustment
- Reported specs including peak thumb-joint torque of 3.5 Nm and positioning accuracy of ±0.2 mm, with the company stating an annual production capacity of 10,000 units and several hundred units already manufactured
- Public demonstrations spanning LEGO assembly, picking up small objects like coins and screws, screwdriver use, in-hand rotation, and sign-language gestures

## Strengths

- Force transparency via low-ratio tendon drives is a genuine engineering departure from the high-reduction-gearing approach used in most commercial robot hands, and directly targets the tactile-sensing/backdrivability gap that limits fine manipulation in current humanoid hands
- IP68 sealing is a practical, deployment-relevant design choice specific to a home-robot use case (dishes, spills, food handling) rather than a lab-only demo feature
- Demonstrated task variety (LEGO, small-object pinching, tool use, in-hand reorientation, sign language) covers a broader dexterity spectrum than typical single-task hand demos
- Reported manufacturing scale (10,000-unit annual capacity, several hundred units already built) suggests this is being treated as a production component, not a one-off research prototype

## Weaknesses

- As a company blog/product announcement rather than a peer-reviewed paper, no independent benchmarks, failure-rate data, or third-party evaluation of the hand's dexterity or durability claims are available
- Demonstrations shown (LEGO assembly, coin/screw picking, sign language) are curated highlight clips; it is unverified how autonomous versus operator-assisted ("Expert Mode" teleoperation, which 1X uses elsewhere in NEO demos) these specific clips are, and independent reporting (e.g., WIRED) has flagged that some 1X demo footage generally has been operator-driven
- No customer deliveries of the new hand had been independently verified as of the announcement despite a large pre-order backlog, so real-world reliability and field failure rates over time remain unknown
- Quantitative claims (3.5 Nm peak torque, ±0.2 mm positioning accuracy, "millions of test cycles") are self-reported by 1X with no disclosed independent testing methodology or third-party validation

## Open Questions

- How does the hand perform in fully autonomous (non-teleoperated) operation on unscripted household tasks over extended, unedited sessions?
- What is the real-world failure/wear rate of the tendon-driven mechanism under the sustained daily use a home robot would require, especially given the low gear ratios that trade mechanical advantage for backdrivability?
- How does 1X's claimed positioning accuracy and force transparency compare quantitatively to competing dexterous hands (e.g., from Tesla, Figure, or academic tendon-driven hands) under a common benchmark?

## Significance

Force-transparent, low-gear-ratio tendon actuation paired with dense tactile sensing addresses a widely acknowledged bottleneck in humanoid manipulation — hands that can move precisely but cannot feel contact — and 1X's decision to combine this with IP68 sealing and stated mass-production numbers signals an industry push toward treating dexterous hands as a shippable product component rather than a research curiosity.

## Links

- [Blog Post](https://www.1x.tech/discover/neos-hands)

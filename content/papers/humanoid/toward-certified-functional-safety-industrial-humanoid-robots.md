---
title: "Toward Certified Functional Safety for Industrial Humanoid Robots: The Fail-Passive Gap and a Feasibility Study"
date: 2026-08-02
topic: Humanoid
tags: [humanoid, functional-safety, certification, industrial-deployment]
source: https://arxiv.org/abs/2608.02809
venue: "arXiv"
---

## Summary

This paper, from Siemens Foundational Technologies authors, identifies that legged humanoid robots violate the "fail-passive" assumption underlying standard industrial functional-safety certification (ISO 13849-1 / EN 60204-1) — cutting power to a walking biped causes an uncontrolled fall rather than a safe state, unlike traditional stationary industrial machinery. It uses a certified external safety chain (light curtain, e-stop, fail-safe PLC, wireless PROFIsafe) to isolate the "uncertifiable" residual element to the robot's own reaction chain, as a feasibility study toward industrial certification.

## Key Contributions

- Names and formalizes the "fail-passive gap": existing industrial safety standards assume cutting power is inherently safe, an assumption legged humanoids structurally violate.
- Proposes using a certified external safety chain to bound the scope of what remains uncertified to the robot's internal reaction path, rather than attempting to certify the entire system end-to-end.
- A feasibility study grounded in existing, deployed safety-certification infrastructure (PROFIsafe, fail-safe PLCs), making the proposal concrete rather than purely conceptual.

## Strengths

- Addresses a genuinely underexamined and practically important barrier to industrial humanoid deployment — safety certification, not raw capability, is often the actual bottleneck to real factory-floor deployment.
- Grounding the approach in existing certified industrial safety infrastructure (rather than proposing a wholly new certification framework) makes the path to adoption more realistic for industrial integrators already using these standards.

## Weaknesses

- As a feasibility study, the paper does not claim to have solved certification for the robot's own internal reaction chain — the core "fail-passive gap" problem for the robot itself remains open, with the external safety chain serving as a workaround/bound rather than a resolution.
- The approach's reliance on external infrastructure (light curtains, wired/wireless PLC safety chains) may not scale well to humanoids intended for less structured or mobile deployment scenarios outside a fixed industrial cell.

## Open Questions

- What would an actual certifiable solution to the robot's internal fail-passive gap look like, beyond bounding the problem with external infrastructure?
- How does this proposal interact with more dynamic humanoid deployment scenarios (e.g. warehouse logistics with moving robots) where a fixed external safety perimeter is less applicable than in a stationary industrial cell?

## Significance

Highlights a structural, standards-level barrier to industrial humanoid deployment that receives far less attention than capability benchmarks — relevant as companies like Figure, Agility, and Digit push toward real factory and warehouse deployment (as seen elsewhere in this vault).

## Links

- [Paper](https://arxiv.org/abs/2608.02809)

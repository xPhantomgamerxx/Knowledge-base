---
title: "Don't Drop the BATON: Long-Horizon Robot Manipulation via Agentic Subtask Exploration and Transition-aware Memory"
date: 2026-08-17
topic: VLA
tags: [long-horizon, llm-agent, hierarchical-planning, transition-memory, subtask-decomposition]
source: https://arxiv.org/abs/2608.16889
venue: "arXiv"
---

## Summary

BATON (Bingxin Xu, Yuzhang Shang, Emilio Ferrara) tackles the problem that chaining multiple contact-rich manipulation skills into a long-horizon task still fails even when the individual VLA-driven skills work well, because errors compound beyond what the policy can self-correct and each subtask silently imposes constraints on the next. It proposes freezing the underlying VLA and putting an LLM agent in overall charge: the agent plans in language, executes free-space motion with analytic primitives, invokes the frozen VLA only for the genuinely contact-rich segments, and writes adaptation information into an explicit language memory.

## Key Contributions

- Identifies and formalizes two specific failure modes of long-horizon VLA chaining: (1) whole-task exploration cost is multiplicative across stages (a K-stage task with T episodes needed per stage costs roughly T^K), and a failure doesn't reveal which stage caused it; (2) VLA-executed subtask primitives have no explicit representation of entry conditions, only an exit — so a subtask can leave the world in a state its successor can't actually use.
- An agentic architecture that keeps the VLA frozen (no retraining) and delegates high-level planning, free-space motion, and subtask sequencing to an LLM agent, invoking the VLA narrowly for contact-rich sub-segments where it has genuine competence.
- Transition-aware memory: writes structured adaptation/transition information into language memory so that entry/exit condition mismatches between chained subtasks can be detected and corrected, addressing the "silent constraint" failure mode directly.
- Agentic subtask exploration that avoids the multiplicative T^K exploration cost by decomposing credit assignment at the subtask level rather than requiring whole-task rollouts to localize failures.

## Strengths

- The multiplicative-cost analysis (T^K for K stages) is a clear, useful articulation of why naive long-horizon VLA chaining doesn't scale, and motivates the subtask-level exploration design concretely rather than just asserting long-horizon tasks are "hard."
- Keeping the VLA frozen and delegating orchestration to an LLM agent is a pragmatic, modular design that doesn't require expensive re-training of the base manipulation skill whenever the task sequence changes — a genuinely different approach from end-to-end long-horizon VLA training.
- Explicitly modeling the entry-condition problem (that a subtask's output state may not match what the next subtask expects) targets a real and often-overlooked failure surface in skill-chaining approaches.

## Weaknesses

- Relying on an LLM agent for high-level planning introduces a new potential failure mode: planning errors or misjudgments about which primitive to invoke are now a separate source of task failure, on top of whatever errors the underlying frozen VLA still makes.
- The approach's reliance on "analytic primitives" for free-space motion presumes such primitives can be reliably scripted for the task domains studied; this may not generalize to environments where free-space motion itself requires learned perception-conditioned control (e.g., cluttered scenes with unpredictable obstacles).
- Because the VLA is frozen, this method cannot fix cases where the VLA's competence for individual contact-rich subtasks is itself unreliable — BATON improves orchestration and recovery around a fixed skill level, not the skill level itself.

## Open Questions

- How well does the transition-aware language memory scale to tasks with dozens of subtasks and many possible transition failure modes, versus the presumably more modest examples used in evaluation?
- How much of BATON's benefit depends on the specific LLM used for agentic planning, and does performance degrade meaningfully with smaller/cheaper LLMs suitable for on-robot deployment?
- Could the entry/exit condition mismatch detection be made more automatic (e.g., learned from failure data) rather than relying on the LLM agent's own language-based reasoning about transitions?

## Significance

BATON offers a compelling alternative to end-to-end long-horizon VLA scaling: rather than training ever-larger monolithic policies to handle multi-stage tasks, it shows that a frozen skill-level VLA combined with LLM-based agentic orchestration and explicit transition memory can address the compounding-error and silent-constraint problems that make naive skill chaining brittle.

## Links

- [Paper](https://arxiv.org/abs/2608.16889)

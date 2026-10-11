---
title: "Fewer Tokens, Better Action: GPT-6 Astra Robot Agents with 14% Higher Success Rate but 65% Fewer Tokens"
date: 2026-10-01
topic: VLA
tags: [robotics, llm-agents, efficient-vla]
source: https://arxiv.org/abs/2610.01939
venue: "arXiv"
---

## Summary

This paper introduces PyRUA-Lean, a framework where a vision-language model (GPT-6 Astra) writes Python code that chains together robot actions, checks outcomes, and retries failed steps, instead of issuing one tool-call per action. Under an equal LLM-call budget across 700 simulated task instances, it raises overall success from 63.1% to 71.7% while using 49% fewer LLM calls and 65% fewer input tokens on instances both agents solve, with an estimated per-episode cost drop from $1.63 to $0.74.

## Key Contributions

- A code-generation-based alternative to per-step tool-calling for high-level robot task execution, with built-in result checking and retry logic.
- Head-to-head comparison against a tool-calling baseline under matched LLM-call budgets.
- A small real-world pilot (RoboDojo, 3 tasks) alongside the 700-task simulated evaluation.

## Strengths

- Simultaneously improves task success and slashes token/cost overhead, rather than trading one for the other.
- Retry-on-failure logic baked into generated code is a simple, practical mechanism for recovering from partial failures without extra model calls.

## Weaknesses

- Evaluated mainly in simulation (700 instances); the real-world pilot is very small (3 tasks), so physical-world generalization is largely unverified.
- Gains are reported specifically relative to a tool-calling baseline using the same underlying planner (GPT-6 Astra); it's unclear how this compares to other high-level planning schemes.
- This is a high-level task-orchestration result rather than a change to the underlying VLA/low-level control policy.

## Open Questions

- Does the code-execution approach scale to much longer-horizon, more compositional tasks than the 700-instance benchmark covers?
- How sensitive are the token/cost savings to the specific planner LLM used, versus being a general property of the code-chaining approach?

## Significance

Speaks to the practical cost of agentic, LLM-planner-driven robot control at scale — useful for systems that pair a VLA low-level controller with a high-level LLM planner, where token costs and latency are a real deployment constraint.

## Links

- [Paper](https://arxiv.org/abs/2610.01939)

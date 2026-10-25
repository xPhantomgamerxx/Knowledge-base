---
title: "VLMs are Native Action Models: Unleashing the Manipulation Capabilities of VLMs with Explicit Action-Space Grounding"
date: 2026-10-09
topic: VLA
tags: [vla, zero-shot, action-grounding, vlm, cross-embodiment]
source: https://arxiv.org/abs/2610.12832
venue: "arXiv"
---

## Summary

EASG (Explicit Action-Space Grounding) argues that pretrained vision-language models already have the capacity to act as manipulation policies, if given the right action interface — no action head, action tokenizer, or robot-action pretraining required. The method projects a tool-center-point action frame into the wrist camera's view and has the VLM describe small moves as text within that grounded frame, which an off-the-shelf VLM can generate natively since it never leaves the model's normal text-generation mode.

## Key Contributions

- A framing that splits the VLA design space into two camps — models that add learned action heads/tokens, and modular pipelines that call a frozen VLM plus external planners/calibration — and positions EASG as a third path: a frozen-interface VLM that is directly action-native.
- A wrist-camera, tool-centered action frame that turns "predict the next robot action" into "describe the next small move in this image," a task format much closer to what VLMs are already pretrained to do.
- Claims of zero-shot manipulation generalization across object positions, categories, and robot embodiments without any robot-specific action pretraining, plus the option to fine-tune within the same continuous action representation when more performance is needed.

## Strengths

- If the core claim holds, it is a meaningfully simpler alternative to the now-standard "VLM backbone + learned action head/expert" VLA recipe — fewer moving parts, less bespoke architecture, and a more direct line to benefit from future VLM scaling and pretraining improvements.
- Grounding actions in the wrist-camera frame (rather than a global or base-camera frame) is a sensible choice: it keeps the action description local and visually verifiable, which should help a VLM reason about small relative moves rather than absolute world-frame numbers it was never trained to output accurately.
- The embodiment-generalization claim, if it reproduces, would be a genuinely useful property — most VLA approaches need embodiment-specific fine-tuning or at least embodiment-conditioned heads.

## Weaknesses

- The abstract-level description doesn't make clear how the method handles actions that aren't well described by small discrete text-described moves (e.g., continuous force/compliance control, high-speed dynamic manipulation, or multi-step long-horizon planning) — a known weak spot for text-as-action schemes generally.
- No LIBERO or other standard benchmark numbers were available from secondary sources at the time of this note, which makes it hard to calibrate EASG's claims against the dense recent literature on VLA efficiency and generalization (e.g., VLA-0, CAC-VLA) that reports concrete success rates on the same tasks.
- "Requires calibrated cameras, depth sensing, and robot kinematics" (per one summary) is a real practical cost that cuts against the "simpler" framing — the method still needs non-trivial robot-specific setup, just not robot-specific training data.

## Open Questions

- How does EASG's success rate and latency compare directly against learned-action-head VLAs of similar backbone size on the same benchmark suite?
- Does the "native text generation" framing hold up for high-DoF or bimanual manipulation, where the action space is much harder to express as a short textual description than a single-arm pick-and-place move?
- What is the failure mode when the VLM's language-model priors conflict with what's geometrically sensible in the wrist-camera frame (e.g., hallucinating a move that looks plausible in text but is physically invalid)?

## Significance

This is part of a broader 2026 trend of asking whether VLA-specific architecture (learned action tokens, diffusion/flow action heads) is actually necessary, or whether sufficiently well-grounded prompting/representation choices let an unmodified VLM do the job — a question with real implications for how much custom infrastructure the field needs to keep building.

## Links

- [Paper](https://arxiv.org/abs/2610.12832)

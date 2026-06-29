---
title: "ImageWAM: Do World Action Models Really Need Video Generation, or Just Image Editing?"
date: 2026-06-19
topic: WorldModels
tags: [world-model, wam, image-editing, efficiency, token-reduction, inference-latency, ablation]
source: https://arxiv.org/abs/2606.19531
venue: "arXiv 2026"
---

## Summary

ImageWAM challenges the video-generation assumption underlying most WAMs by replacing multi-frame future prediction with a single image editing step. Video-based WAMs face three coupled limitations: dense multi-frame future tokens are computationally expensive, full video prediction wastes capacity on action-irrelevant temporal details, and long-horizon imagination can introduce errors that mislead action prediction. ImageWAM repurposes pretrained image editing models to predict only the next-frame future, reducing FLOPs to 1/6 and latency to 1/4 of video-based WAMs while outperforming standard VLA baselines and matching competitive WAMs across simulation and real-world experiments.

## Key Contributions

- Repurposes pretrained image-editing models as world models, removing the need for video generation
- Single next-frame future prediction instead of multi-frame video, eliminating temporal redundancy
- 6× FLOP reduction and 4× latency reduction vs. video-based WAMs
- Outperforms VLA baselines and matches WAMs on diverse manipulation benchmarks without policy pretraining

## Significance

ImageWAM provides a principled empirical argument that temporal video modeling is not the bottleneck for WAM control benefits — next-frame image editing is sufficient — which opens the door to much simpler and faster world-action model architectures.

## Links

- [Paper](https://arxiv.org/abs/2606.19531)
- [GitHub](https://github.com/yuyangalin/ImageWAM)

Two Ways to Improve Portrait Generation in InfiniteYou: Base Model Replacement + anti-realism LoRA

This repository studies how to accelerate InfiniteYou for personalized image generation under low-step diffusion.

We replace the original backbone FLUX.1-dev with FLUX.1-schnell and add a lightweight Realism LoRA to reduce quality degradation at low sampling steps.
The identity injection module (InfuseNet) is kept unchanged.

Key observations

FLUX.1-schnell achieves about 2–3× faster inference at 1–4 diffusion steps.

Image quality degrades at very low steps (1–2).

Realism LoRA improves visual realism and texture details.

4 steps with FLUX.1-schnell + Realism LoRA provides the best speed–quality balance.

Setup

Steps: 1–4 / 32

GPU: NVIDIA A100

Precision: BF16

Timing: averaged over 50 runs

Notes

This repository is for research exploration of speed–quality trade-offs, not for production use.

References

InfiniteYou (2025) · FLUX.1 (2024) · LoRA (ICLR 2022)

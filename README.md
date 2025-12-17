# Two Ways to Improve Portrait Generation in InfiniteYou: Base Model Replacement + anti-realism LoRA

This repository explores how to **accelerate InfiniteYou** for personalized image generation under low-step diffusion sampling.

We replace the original backbone **FLUX.1-dev** with **FLUX.1-schnell**, and introduce a lightweight **Realism LoRA** to mitigate visual quality degradation at low sampling steps.
The identity injection module (**InfuseNet**) remains unchanged.

---

## Key Observations

* **2–3× inference speedup** using FLUX.1-schnell at 1–4 diffusion steps
* Noticeable quality degradation at extremely low steps (1–2)
* Realism LoRA improves texture details and perceptual realism
* **4 steps with FLUX.1-schnell + Realism LoRA** provides the best speed–quality balance

---

## Experimental Setup

* Diffusion steps: 1–4 / 32
* GPU: NVIDIA A100
* Precision: BF16
* Timing: averaged over 50 runs

---

## Notes

This repository is intended for **research exploration** of speed–quality trade-offs and is not a production-ready system.

---

## References

* InfiniteYou (2025)
* FLUX.1 models by Black Forest Labs (2024)
* LoRA: Low-Rank Adaptation (ICLR 2022)

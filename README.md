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

--

## Model Weights

### Base Diffusion Models

- **FLUX.1-dev**  
  Official release by Black Forest Labs:  
  https://blackforestlabs.ai/announcing-black-forest-labs/

- **FLUX.1-schnell**  
  Official release by Black Forest Labs (optimized for low-step diffusion):  
  https://blackforestlabs.ai/announcing-black-forest-labs/

Please follow the official instructions and license terms when downloading and using these models.

---

### InfiniteYou Identity Module

- **InfiniteYou (InfuseNet + identity encoder)**  
  Official repository:  
  https://github.com/<official-infiniteyou-repo>

Refer to the original InfiniteYou repository for pretrained weights and usage details.

---

### Realism LoRA

- **Realism LoRA (used in this study)**  
  Download link:  
  https://github.com/Fengz1x/InfiniteYou-schnell/releases/tag/realism-lora

This LoRA is provided for research and evaluation purposes only.

--

## References

* InfiniteYou (2025)
* FLUX.1 models by Black Forest Labs (2024)
* LoRA: Low-Rank Adaptation (ICLR 2022)

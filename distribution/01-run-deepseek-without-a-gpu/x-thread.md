# X Thread — How to Run DeepSeek Without a GPU: The $0.49/Hour Trick

Source: `articles/posts/blog/en/01.run-deepseek-without-a-gpu.mdx`
Link: https://glows.ai/article/run_deepseek_without_a_gpu_en

---

**1/**
DeepSeek-R1 32B needs ~20 GB of VRAM.

A typical gaming laptop ships with 8.

Here's how to run the model your hardware can't touch — for $0.49/hour, with the actual math 🧵

**2/**
The VRAM ladder at 4-bit quantization:

1.5B distill → ~2.3 GB
7B/8B → ~5.5–8 GB
14B → ~10–12 GB
32B → ~20 GB
70B → ~40 GB
671B (full) → 131 GB+ even at 1.58-bit

Reasoning models add 1–4 GB of KV cache on top. Your 8 GB card tops out at the 7B tier.

**3/**
Here's the catch: the models people actually mean when they say "DeepSeek" — the 32B distill and up — start at 20 GB.

The 1.5B and 7B versions run fine locally. But they're study aids, not the reasoning engine that made DeepSeek famous.

**4/**
Three escape routes when your machine can't run it:

1. CPU-only inference (local RAM)
2. Hosted API
3. Hourly cloud GPU

They are not interchangeable.

**5/**
CPU-only works — barely.

PC Gamer documented a dual-EPYC build with 384 GB of DDR5 running the full 671B model. Cost: ~$6,000. Speed: 5–8 tokens/s.

At that rate, a 1,000-token reasoning chain takes 2+ minutes before the answer even starts.

**6/**
Hosted APIs are cheap and fast — the right answer for casual chat.

But your prompts leave your control. No quantization choice, no LoRA fine-tunes, and you can't point Open WebUI at a model you actually operate.

**7/**
Option 3: rent a dedicated RTX 4090 by the hour.

It behaves exactly like a local GPU — SSH in, swap models, change quantization — except someone else bought the card. The 32B distill runs at ~28–45 tok/s: 4–8× the $6,000 CPU build.

**8/**
The rent-vs-buy math:

$1,599 (4090 MSRP) ÷ $0.49/hr ≈ 3,263 hours before buying wins.

1 hr per weekday → 13.5 years to break even
Weekend tinkering → 34 years

The card goes obsolete before it pays for itself.

**9/**
Setup is ~10 minutes: sign up, pick an RTX 4090, select the preconfigured DeepSeek-R1 image, checkout. Instance starts in 30–60 seconds. No CUDA installs, no dependency debugging.

A two-hour evening session: $0.98.

**10/**
Sweet spot on a 24 GB card: DeepSeek-R1-Distill-Qwen-32B at 4-bit — ~20 GB of weights, ~4 GB left for KV cache.

Need 70B? That's 2× 4090 or one 48 GB card. The full 671B is a multi-GPU SGLang job.

**11/**
Full guide with the VRAM table, the break-even math, and the step-by-step:

https://glows.ai/article/run_deepseek_without_a_gpu_en

(We're Glows.ai — the $0.49/hr 4090 is ours, so yes, we have a horse in this race. The VRAM numbers don't care where you rent.)

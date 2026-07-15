# X Thread — I Generated 1,000 AI Images for $2. Here's Exactly How.

Source: `articles/posts/blog/en/09.generate-1000-ai-images-for-2-dollars.mdx`
Link: https://glows.ai/article/generate_1000_ai_images_for_2_dollars_en

---

**1/**
1,000 AI images for $2.

Not a promo code. Not a free-tier hack. A rented RTX 4090 at $0.49/hr plus published benchmarks.

Here's the arithmetic, every number sourced 🧵

**2/**
The whole thing is one formula:

cost per 1,000 images = seconds per image × 1,000 ÷ 3,600 × hourly GPU rate

At $0.49/hr, one GPU-second costs $0.000136. Everything else is multiplication.

**3/**
Seconds per image on an RTX 4090, from public benchmarks (ComfyUI GitHub, Prompting Pixels, SaladCloud, Tom's Hardware):

Flux.1 Schnell (4 steps): ~5 s
SDXL (20 steps): ~7 s
Flux.1 Dev FP8: ~10 s
Flux.1 Dev FP16: 15–17 s

**4/**
Multiply it out. 1,000 images at $0.49/hr:

Flux.1 Schnell → $0.68
SDXL → $0.95
Flux.1 Dev FP8 → $1.36
SDXL base + refiner → $2.12
Flux.1 Dev FP16 → $2.18

"$2" is the ceiling, not a stretch — it covers the slowest full-precision config.

**5/**
Per image, that's $0.0007 to $0.0022.

Less than a fifth of a cent for a full-precision Flux.1 Dev image. Keep that number in mind.

**6/**
The same 1,000 images through hosted APIs (2026 published price lists):

OpenAI image API: $40–$120
Stability AI: $10–$50
Replicate / fal.ai aggregators: $8–$40
Midjourney Standard: ~$30/mo

That's 4–176× more than the rented 4090.

**7/**
APIs aren't a rip-off — you pay for zero setup, autoscaling, and someone else's engineers.

For 20 images a week, an API or Midjourney plan is the right call. The crossover comes at volume: 1,000+ images, and you're buying GPU seconds at cost.

**8/**
What the headline number hides:

- First model download adds 10–25 min (~$0.08–0.20) — persistent storage removes it after run one
- Nobody keeps 1,000/1,000. A 30% keep rate triples cost per KEPT image (true for APIs too, at 4–176× the price)

**9/**
The verification trick: per-second billing means the invoice IS the benchmark.

Queue 1,000 generations, note the timestamps, divide cost by images. No trusting a blog post required.

**10/**
Full breakdown — sourced benchmark table, API comparison, and the reproduction steps:

https://glows.ai/article/generate_1000_ai_images_for_2_dollars_en

(We're Glows.ai; the $0.49/hr 4090 is ours. The formula accepts any rate you see at checkout.)

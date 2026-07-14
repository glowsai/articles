# Glows.ai Voice & Tone Guide

How we sound, everywhere we write. Modeled on [Mailchimp's voice-and-tone framework](https://styleguide.mailchimp.com/voice-and-tone/): our **voice** never changes; our **tone** adapts to context.

## Our voice

**Glows.ai is the experienced colleague who gets your GPU workload running without drama.**

We write for developers and AI practitioners. They trust specifics and discount hype.

| We are… | but not… |
| --- | --- |
| **Practical** — steps, ports, commands, real numbers | Dry — "Now let's dive into a hands-on example together" is on-brand |
| **Confident** — we state what works and how fast | Boastful — never "groundbreaking", "unprecedented", "unparalleled", "redefining", "pioneer" |
| **Careful** — we flag pitfalls and ignorable errors before readers hit them | Fussy — one "Please" per warning, not per sentence |
| **Ambitious** about AI infrastructure | Grandiose about "the future of artificial intelligence" |

**The core rule: replace every superlative with a number or a capability.**

- ❌ "unprecedented integration of computational resources"
- ✅ "combines TPUs, GPUs, and Apple Silicon in one instance with near-zero latency"
- ❌ "with just one click, instantly"
- ✅ "starts in 30–60 seconds"

## Tone by context

Same voice, adjusted delivery:

- **Tutorials** — calm, collaborative "we" ("We create an instance on demand…"). Open with a bullet list of what the article covers. Anticipate frustration points before the reader hits them.
- **Announcements / news** — enthusiastic but concrete. Lead with what users can now do and the measurable difference, not with adjectives.
- **Warnings & errors** — instruction first, reason second: "**Reminder:** The final `systemctl` command error can be ignored. `systemctl` is not supported inside Docker containers."

## Mechanics

- **Brand name:** always **Glows.ai** — never Glow.ai, Glowsai, or glow.ai in prose.
- **Product names:** **Datadrive** (one word), **Elastica**, instance names as shown in the UI.
- **Step headings:** `## Step 1: Do the Thing` — numbered, colon, space after "Step".
- **Numbers over adjectives:** startup times, sample lengths, GPU counts ("requires at least 2 Unit Qty NVIDIA GeForce RTX 4090 GPUs").
- **Callouts:** bold label + colon — `**Note:**`, `**Reminder:**`.
- **UI elements** in backticks: `` `Create New` ``, `` `Complete Checkout` ``, `` `My Instances` ``.

## Reference post

[How to Run OpenClaw on Glows.ai](posts/16.How%20to%20Run%20OpenClaw%20on%20Glows.ai.mdx) is the register to copy: intro bullet list, collaborative "we", concrete timings, Reminder callouts.

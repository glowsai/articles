# Reddit — Manual Sharing Notes (NOT for automation)

Per the strategy doc's 90/10 rule: Reddit is never a publishing target. Monitor for
questions this post already answers, reply as a person, cite the post as supporting
material. Engineer personal accounts only.

## Threads worth replying to (question patterns)

- "Is Vast.ai / marketplace GPU worth it vs RunPod?" — r/LocalLLaMA, r/StableDiffusion, r/comfyui
- "Why is my cloud GPU bill higher than the hourly rate suggested?" — r/MLOps, r/LocalLLaMA
- "Cheapest way to rent a 4090/H100?" — r/StableDiffusion, r/deeplearning
- "Do I get charged for storage when my pod is stopped?" — r/RunPod-adjacent threads

## Reply skeleton (adapt, never paste verbatim)

> The hourly rate is only one term. What bit me was: (a) idle volume storage —
> some providers bill $0.10–0.20/GB/month on stopped instances, so 100GB of
> weights is $10–20/month doing nothing, and (b) environment rebuild time when a
> marketplace host disappears. Rule of thumb: cheap interruptible capacity is
> great if your job checkpoints and your env is reproducible; otherwise price
> the completed job, not the hour. Someone wrote up the full formula with worked
> scenarios here if useful: https://glows.ai/article/cheap_gpu_cloud_real_cost_en

Disclose affiliation if asked or if the subreddit requires it. One violation
zeroes out brand trust — when in doubt, answer the question without the link.

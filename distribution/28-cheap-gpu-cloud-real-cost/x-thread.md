# X Thread — Cheap GPU Cloud Real Cost

Source: `articles/posts/blog/en/28.cheap-gpu-cloud-real-cost.mdx`
Link: https://glows.ai/article/cheap_gpu_cloud_real_cost_en

---

**1/**
"GPUs from $0.29/hr" is a great ad.

It's also not the number you'll pay.

Here's why a $0.29 GPU can cost more than a $0.49 one — with the actual math 🧵

**2/**
The hourly rate is one line in the real formula:

total cost = compute + storage + data transfer + setup/restart time + failed or retried work

Cheap listings win the first term and quietly lose the rest.

**3/**
Scenario 1: a 4-hour ComfyUI session.

RTX 4090 at $0.49/hr → $1.96
RTX 4090 at $0.69/hr → $2.76
Marketplace 4090 → maybe less

Marketplace wins... IF the host is available, the disk is big enough, and you don't spend an hour rebuilding your environment.

**4/**
One hour re-downloading models to save $0.80 in compute is a bad trade.

For recurring work, price the return trip too: stop today, come back tomorrow, restore the same models and project. That's a storage question, not a GPU question.

**5/**
Scenario 2: you stop the instance but keep 100GB of model weights for a month.

Compute cost: $0.
Storage cost: NOT $0.

Some providers charge $0.10–0.20/GB/month for idle volumes. That's $10–20/month for a GPU you're not even using.

**6/**
Scenario 3: a 72-hour H100 job.

Now the rate matters: $0.10/hr difference = $7.20. $1/hr = $72.

Long jobs shift the math toward raw compute — but only after matching VRAM, host, network, and interruption terms.

**7/**
Five assumptions hiding inside every cheap GPU ad:

1. The lowest listing is actually available to you
2. Your workload fits the advertised GPU
3. Storage is free or irrelevant
4. Setup time is free
5. A failed run costs nothing

Usually at least two of these are wrong.

**8/**
To be fair: sometimes the cheapest listing IS the right call.

Checkpointable job ✅
Reproducible environment ✅
Disposable data ✅
Nobody blocked by a restart ✅

That's the legit use case for marketplace GPUs. The mistake is using them for work that can't tolerate the tradeoffs.

**9/**
Better metrics than $/hr:

Image generation → cost per productive session
Fine-tuning → cost per completed checkpoint
Batch inference → cost per completed batch
Production API → cost per request + uptime

"Cheap" is a property of the completed workload, not the GPU.

**10/**
Before renting any "cheap" GPU, ask three questions:

1. What exact machine is this?
2. What does it cost after I stop it?
3. Can my job resume somewhere else?

Unclear answers? Pay for a 1-hour test first. It's cheaper than finding out mid-run.

**11/**
Full breakdown with a fill-in-the-blanks cost worksheet:

https://glows.ai/article/cheap_gpu_cloud_real_cost_en

(We're Glows.ai — 4090s at $0.49/hr with 100–500GB storage included, so yes, we have a horse in this race. The math still holds wherever you rent.)

# Threads Post — Kimi K3 explained

Source: `articles/posts/blog/en/33.kimi-k3-comprehensive-analysis.mdx`
Voice: casual, build-in-public, technical but readable.

kimi k3 is a 2.8T-parameter open-weight model with 104B active parameters, native vision, and a 1M-token context window.

the interesting part is the systems problem: 896 experts, only 16 selected per token, Kimi Delta Attention, Attention Residuals, long-context state, and multi-node serving.

the practical path is still api first. use smaller rented gpus to validate rag, data, evals, and agent tools. only plan the big cluster when privacy or sustained volume makes it worth operating.

full breakdown: https://glows.ai/article/kimi_k3_comprehensive_analysis_en

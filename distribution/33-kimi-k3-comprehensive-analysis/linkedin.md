# LinkedIn Post — Kimi K3 Explained: 2.8T Parameters and 1M Context

Source: `articles/posts/blog/en/33.kimi-k3-comprehensive-analysis.mdx`
Link: https://glows.ai/article/kimi_k3_comprehensive_analysis_en
Angle: What Kimi K3 changes for teams planning long-running agent infrastructure.

Kimi K3 crosses an important engineering threshold: 2.8T total parameters, 104B active parameters, native vision, and a 1,048,576-token context window.

The deployment implication is easy to miss. MoE reduces per-token compute by routing each token to 16 of 896 experts, but the complete weight set still has to live across a serving cluster. A million-token context also has operational costs: KV-cache or recurrent state, prefill time, concurrency, storage, and interconnect bandwidth.

Moonshot reports scores including 93.5 on GPQA Diamond, 88.3 on Terminal-Bench 2.1, 91.2 on BrowseComp, and 94.5 on MCPMark-Verified. Those results are useful signals, not universal guarantees. They are vendor-reported and depend on the evaluation harness and tools.

For an AI team, a sensible path is:

- use the API for early capability evaluation;
- validate RAG, data processing, and agent workflows on smaller GPUs;
- move to H100, H200, or B200 multi-node capacity only when privacy, control, or sustained volume justifies it.

The full guide explains the architecture, licensing caveats, benchmark limits, and the Glows.ai infrastructure plan.

https://glows.ai/article/kimi_k3_comprehensive_analysis_en

#KimiK3 #LLM #AIInfrastructure #GPUCloud

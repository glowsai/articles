# X Thread — Kimi K3 Explained: 2.8T Parameters and 1M Context

Source: `articles/posts/blog/en/33.kimi-k3-comprehensive-analysis.mdx`
Link: https://glows.ai/article/kimi_k3_comprehensive_analysis_en

**1/**
Kimi K3 is not just a bigger chatbot: 2.8T total parameters, 104B active, native vision, and a 1,048,576-token context window. The hard part is making that useful and operable.

**2/**
K3 is MoE: 896 routed experts, 16 selected per token, plus shared experts. Active parameters reduce per-token compute. They do not remove the need to store the complete 2.8T checkpoint.

**3/**
Kimi Delta Attention mixes fixed-size recurrent state with periodic Gated MLA layers. The 93-layer model has 69 KDA layers and 24 Gated MLA layers for a long-context tradeoff.

**4/**
Attention Residuals let layers selectively retrieve representations from earlier blocks. Stable LatentMoE addresses load balance at high sparsity. Moonshot reports 2.5x aggregate scaling-efficiency improvement vs Kimi K2.

**5/**
Reported scores include GPQA 93.5, Terminal-Bench 2.1 88.3, BrowseComp 91.2, MCPMark-Verified 94.5, and OSWorld-Verified 84.8. These are vendor-reported and depend on harness and tools.

**6/**
One official kernel case reduced AttnRes latency from 283.6 ms to 114.4 ms. That is a case result, not a portable promise: hardware, compiler, kernel, and test method matter.

**7/**
Public reference topologies range from 4×8 H100 nodes to 8×GB300 and multi-node H200/B200/GB300 setups. A 1M context limit still depends on KV cache, prefill, concurrency, and interconnect.

**8/**
For most teams: use the API first, validate RAG/data/agent workflows on a smaller GPU, then move to a multi-node private deployment only when privacy or sustained volume justifies it.

**9/**
Open weights are not the same as unrestricted software. Kimi K3's license includes commercial conditions. Read the full license before building a Model-as-a-Service product.

**10/**
The full analysis covers KDA, AttnRes, Stable LatentMoE, benchmark caveats, and a Glows.ai infrastructure plan: https://glows.ai/article/kimi_k3_comprehensive_analysis_en

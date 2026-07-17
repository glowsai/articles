# ICP Content and SEO Plan

## Purpose

Use content to bring Glows.ai's ideal customers to the website: developers and AI teams that need on-demand GPU capacity for training, inference, deployment, or team-scale operations. The intended action is to evaluate a relevant workload on Glows.ai, then create an instance or contact the team.

This is a content strategy document, not a guarantee of rankings. Rankings and qualified traffic must be checked in Search Console and product analytics after publication.

## Product and ICP Alignment

Glows.ai's public product positioning is a globally distributed GPU cloud for AI training and inference, with ready-to-start environments, storage, multi-cloud capability, and team collaboration.

Primary ICPs:

1. **AI builders** - developers who need to run a particular open-weight model, framework, or workload without buying hardware.
2. **AI product and MLOps teams** - teams deciding GPU size, serving stack, latency, storage, availability, and ongoing cost for production inference.
3. **Regulated or regional teams** - organizations with data-path, jurisdiction, or latency requirements that need to select and document a deployment region.

The content must answer a real deployment decision, show a reproducible path in Glows.ai, and make the next step obvious.

## Editorial Rule

Every SEO article must be either:

- **Searchable:** targets a specific high-intent question a technical buyer already asks; or
- **Shareable:** uses original data, a benchmark, or a useful point of view that technical teams will pass on.

Creator-oriented posts may still be published and used for social distribution, but they must not set the blog's primary SEO agenda or crowd out ICP content.

## Content Pillars

### 1. Model deployment and GPU sizing

**Why it matters:** A developer arrives with a concrete model and needs to know whether it will fit, which GPU to use, and how to deploy it.

**Cluster:**

- Model-specific deployment and VRAM guides.
- GPU sizing by model, context window, quantization, and target concurrency.
- Reproducible SGLang or vLLM deployment tutorials.
- Open-weight model launch updates, only when Glows.ai can offer a verified runbook.

**Existing foundations:** #1, #3, #4, #16, #17, #18.

### 2. Inference economics and performance

**Why it matters:** Product and infrastructure teams buy based on cost per useful workload, not a generic GPU hourly price.

**Cluster:**

- GPU price-performance benchmarks.
- API versus self-hosted decisions.
- Capacity planning by requests per second, latency target, and utilization.
- Rent versus buy and cloud versus dedicated infrastructure.

**Existing foundations:** #2, #12, #13, #15, #19.

### 3. Production operations for AI teams

**Why it matters:** Teams need more than a GPU. They need persistent model storage, reproducibility, access control, data paths, cost ownership, and a recovery plan.

**Cluster:**

- SGLang/vLLM production checklist.
- DataDrive, snapshots, and model lifecycle guides.
- Multi-node networking and scaling.
- Team operating model: permissions, project separation, cost visibility, and handoff.

**Existing foundations:** #11, #17, plus the existing SGLang and Hugging Face tutorials on glows.ai.

### 4. Region, latency, and data-path decisions

**Why it matters:** Teams with customers, regulated data, or cross-region users must justify where a workload runs and where its data travels.

**Cluster:**

- Region-selection framework.
- Taiwan as a specific regulated-workload case, not the platform's sole identity.
- Latency and failover planning.
- Storage, backup, and connected-service data-path mapping.

**Existing foundation:** #20.

## Priority Content to Create

These are the highest-priority future pieces. They should not be drafted as generic explainers. Each needs Glows.ai configuration data, a reproducible benchmark, or both before publication.

| Priority | Proposed article | Search intent and buyer stage | Required proof |
| --- | --- | --- | --- |
| P0 | **How many GPUs do I need for `<specific open model>` at `<target concurrency>`?** | Implementation and consideration | Model version, context length, quantization, concurrency, measured throughput/latency, exact Glows.ai configuration |
| P0 | **H100 vs A100 vs RTX Pro 6000 for `<specific inference workload>`: measured cost and throughput** | Consideration and decision | Same model and serving stack, benchmark method, raw results, current regional price and availability note |
| P0 | **When does self-hosting beat API pricing once utilization, concurrency, and idle capacity are included?** | Consideration and decision | Transparent calculator assumptions, API prices and dates, GPU rate, throughput, utilization scenarios, break-even limitations |
| P1 | **Production checklist for SGLang/vLLM: storage, multi-node networking, observability, and recovery** | Implementation | Tested commands, versioned environment, failure modes, DataDrive/snapshot usage, recovery steps |
| P1 | **Region selection for AI teams: latency, data path, storage, and failover** | Awareness and consideration | Keep #20 as the starting point; add diagrams and configuration verification, not blanket compliance claims |

### Differentiated angle

Do not compete directly with an official framework's broad documentation. The value is Glows.ai-specific evidence: real hardware configurations, observed throughput, price-performance, startup and storage workflow, regional availability, and an exact deployment path.

The strongest opportunity is an **utilization-aware inference cost model**. Basic calculators often assume a fixed utilization rate; the article must show how requests per second, batching, context length, idle time, and recovery capacity change the answer.

## Existing Content Decisions

### Primary SEO and ICP cluster

Prioritize these as technical acquisition content: #1, #2, #3, #4, #11, #12, #15, #16, #17, #18, #19, and #20.

Before each article publishes:

- Confirm every model, framework, price, and product claim is current.
- Add at least two relevant internal links: one related guide and one product or documentation path.
- Use a clear CTA tied to the article's workload, not a generic sign-up prompt.
- Include a visible update date and sources for price or benchmark claims.

### Supportive, but not primary SEO

#5, #7, and #13 can support creator/prosumer acquisition when linked to a technical workflow or cost decision. Do not treat them as the main proof that the blog serves enterprise or team ICPs.

### Demote from the primary SEO plan

#6, #8, #9, #10, and #14 are primarily creator or consumer topics:

- AI TikTok virality
- Free AI image limits
- Generating 1,000 AI images for $2
- Best AI art tools
- AI side hustles

They can be useful for social, newsletter, community, and creator acquisition. They should not be used as the core SEO investment or the primary content shown to technical buyers.

### Replacement roadmap for the five demoted topics

Replace or substantially rework the five topics below when benchmark evidence is available. This is a future content roadmap; do not invent throughput, price-performance, or operational claims to fill it.

| Current topic | Replace or rework into | Why it is stronger for ICP acquisition | Evidence required before publishing |
| --- | --- | --- | --- |
| #6 AI TikTok virality | **How many GPUs do I need for `<specific open model>` at `<target concurrency>`?** | Answers a deployment and capacity-planning question from an AI builder | Model/version, quantization, context length, target concurrency, measured latency and throughput, exact Glows.ai configuration |
| #8 Free AI image limits | **H100 vs A100 vs RTX Pro 6000 for `<specific inference workload>`: measured cost and throughput** | Supports a hardware and provider evaluation decision | Same model, serving stack, workload, benchmark method, raw results, price and availability date |
| #9 1,000 AI images for $2 | **When does self-hosting beat API pricing once utilization, concurrency, and idle capacity are included?** | Addresses an infrastructure-budget decision rather than a one-off generation cost | Transparent cost model, API prices, GPU rate, throughput, utilization scenarios, and limits of the calculation |
| #10 Best AI art tools | **Production checklist for SGLang/vLLM: storage, multi-node networking, observability, and recovery** | Helps a technical team reach production, where Glows.ai's storage and infrastructure workflow is relevant | Tested commands, environment version, failure and recovery paths, storage/snapshot workflow |
| #14 AI side hustles | **GPU cloud operating checklist for AI teams: storage, permissions, cost, region, and recovery** | Targets the operational owner who needs a repeatable team process | Product-verified team, storage, regional, and recovery capabilities; no unsupported feature claims |

The region-selection article in #20 is already the first piece of this ICP plan. Keep improving it as the `Region, latency, and data-path decisions` pillar rather than replacing it.

Implementation briefs for this backlog live in `briefs/21.gpu-sizing-by-model-and-concurrency.md` through `briefs/25.gpu-cloud-operating-checklist-for-ai-teams.md`.

## Publishing and Distribution

The initial-publishing calendar is distributed across **April 8 to July 1, 2026**, with no more than three topics assigned to any day. The same publication date and time must be used for each English, Traditional Chinese, and Japanese version of a topic.

Because prices, availability, and release information change, each article also carries a visible **Last reviewed** note and a `lastUpdated` frontmatter date. The earlier publication date records when the guide first entered the library; time-sensitive claims are tied to the later review instead. Do not backdate a current price or model-launch claim without this distinction.

- Treat no more than **one daily topic** as the flagship SEO/ICP article.
- Use the other creator-oriented topics for social distribution rather than expecting all of them to rank.
- Publish benchmark-led content only after the underlying run is reproducible.
- Update time-sensitive model, framework, and price posts before release; do not publish old "just dropped" or "checked July" claims without revalidation.

## Content Architecture Requirements

These are content requirements that can be handled before Landing page work is available:

1. Use a consistent primary topic and buyer stage for every article.
2. Add a `Related guides` section to every article, with two or three same-cluster links.
3. Add tags that distinguish `Model Deployment`, `Inference Economics`, `AI Operations`, `Region & Data`, and `Creator Workflows` instead of only `Blog`.
4. Link each article to the most relevant Glows.ai product/documentation action.
5. Maintain a source and benchmark record for every performance, price, and regulatory claim.

Landing-page and platform work needed later:

- Do not show future-dated posts in the index, RSS, sitemap, or direct routes.
- Surface pillar/category pages and related articles.
- Add Article and Breadcrumb structured data after validating it in a rendered environment.

## Measurement Plan

The plan is successful only when it produces qualified visits and product actions, not page views alone.

Track in Search Console and analytics:

- Impressions, clicks, CTR, and average position by query and landing page.
- Non-branded versus branded search traffic.
- Visits to product/docs pages from each article.
- Instance creation, sign-up, contact, or demo conversion from content sessions.
- Returning visits and assisted conversions for the technical clusters.

Review 30, 60, and 90 days after publication. Keep, update, or retire topics based on qualified traffic and conversion, not rankings alone.

## Evidence and Constraints

- Broad vLLM and SGLang production guides compete with official documentation; use model-, workload-, and Glows.ai-specific long-tail angles.
- Generic API-vs-self-hosted calculators are crowded; only publish one with a transparent, utilization-aware methodology and original inputs.
- Taiwan sovereignty and residency content has local vendor competition; keep #20 as a practical regional decision guide rather than a Taiwan-only positioning statement.
- Search Console, conversion data, and benchmark evidence are required before claiming the strategy has improved SEO or ICP acquisition.

# Customer Confidence Publishing Gates

The goal of this content cluster is to help a Glows.ai customer make a defensible purchase, deployment, and scaling decision. Confidence must come from clear expectations and verifiable evidence—not unsupported superlatives.

Use [EVIDENCE-COLLECTION-RUNBOOK.md](./EVIDENCE-COLLECTION-RUNBOOK.md) for platform evidence and [CUSTOMER-VALIDATION-PROTOCOL.md](./CUSTOMER-VALIDATION-PROTOCOL.md) for customer comprehension, accuracy, and regret-risk testing.

Use [GOAL-COMPLETION-AUDIT.md](./GOAL-COMPLETION-AUDIT.md) to track what the repository proves, what remains pending, and whether the customer-confidence objective can be marked complete.

## Cluster-wide requirements

Every article must pass these checks before publication:

- A named author and technical reviewer are visible.
- The publication date and last-verified date are visible.
- Product screenshots match the current Glows.ai interface.
- Prices, GPU availability, regions, image IDs, and commands are verified on the publication date.
- Measured results identify the GPU, region, model revision, runtime version, context, concurrency, and test method.
- Estimates are labeled as estimates; measurements are labeled as measurements.
- Limitations and poor-fit scenarios remain in the article.
- Required assets are confirmed on Datadrive before any release workflow is demonstrated.
- Secrets, user data, account identifiers, and private endpoints are removed from screenshots and code.
- Support and correction contact paths are present on the published site.

## Evidence required by article

| Article | Required first-party proof | Customer question answered |
|---|---|---|
| GPU and quantization selection | Peak VRAM at two precisions plus workload settings | “Am I renting more—or less—GPU than I need?” |
| GPU workload cost | Dated rate card, real phase timings, and dashboard total | “What will a successful result actually cost?” |
| GPU rental vs API | Equivalent task set, quality result, utilization, and unit cost | “Is Glows.ai financially sensible for my workload?” |
| vLLM deployment | Clean-instance walkthrough, successful authenticated request, and metrics | “Can I deploy a usable endpoint without hidden steps?” |
| Latency benchmark | Raw benchmark output and p50/p95/p99 results | “Will this meet my users’ performance target?” |
| Checkpoint and recovery | Demonstrated interruption and successful resume | “Can I stop or recover without losing the work?” |
| Region and reproducibility | Multi-location latency measurements and a clean rebuild | “Can the deployment be moved, recovered, and explained?” |

## Claims policy

Avoid claims such as:

- “cheapest”
- “zero risk”
- “guaranteed uptime”
- “always faster”
- “no data loss”
- “best GPU cloud”

unless a current, independently reviewable source and a precise scope support the statement.

Prefer:

- “In this test configuration…”
- “For this workload…”
- “At the measured utilization…”
- “The current dashboard showed…”
- “The recovery test resumed from step…”
- “Verify current availability before checkout.”

## Customer-confidence acceptance test

A reader should be able to answer all of these after reading the cluster:

1. Which GPU and model configuration should I test first?
2. What assumptions determine the cost?
3. When is a hosted API a better choice?
4. How do I create and secure a working endpoint?
5. How do I prove it meets latency and quality requirements?
6. Which assets survive instance release?
7. How do I recover after interruption?
8. How do I reproduce the deployment in another instance or region?
9. When should I scale, optimize, or stop spending?

Do not publish the cluster as complete until every question has a tested, current, and internally consistent answer.

The content also must pass the customer-validation thresholds. Technical correctness alone does not prove that readers can find, understand, or act on the guidance.

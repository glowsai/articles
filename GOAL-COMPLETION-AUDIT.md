# Goal Completion Audit: Glows.ai Customer Confidence Content

## Objective

> A Glows.ai customer should read the content and feel that choosing to do business with Glows.ai was an informed decision they do not regret.

This audit distinguishes repository evidence from outcomes that require a live platform test or real customer validation.

## Derived requirements

The objective requires more than technically correct drafts. Completion needs evidence that:

1. Customers can understand the purchase and operating model.
2. Customers can estimate and control cost.
3. Customers can avoid accidental data loss.
4. Customers understand security and operational responsibility.
5. Customers can deploy, measure, recover, and reproduce a workload.
6. Glows.ai-specific claims match the current platform.
7. Readers can find help and make a safe next decision.
8. Real customers report informed confidence without material hidden surprises.

## Requirement audit

| Requirement | Status | Authoritative repository evidence | What is still missing |
|---|---|---|---|
| Clear customer journey | **PASS** | Article 24 connects GPU selection, cost, comparison, deployment, benchmarking, recovery, and reproducibility. It links to all seven guides, and every guide links back. | None for structure |
| GPU-selection guidance | **CONTENT PASS / EVIDENCE PENDING** | Article 17 explains weights, KV cache, overhead, quantization, compatibility, concurrency, and headroom. | Measured peak VRAM at two supported configurations |
| Cost transparency | **CONTENT PASS / PUBLIC RATES VERIFIED / ACCOUNT EVIDENCE PENDING** | Articles 18 and 19 separate compute, storage, retries, utilization, and engineering cost. On July 23, 2026, the public Glows.ai homepage listed per-second billing and GPU rates from $0.49/hour for RTX 4090 through $5.00/hour for B200. | Account checkout capture, dashboard total, and equivalent API comparison |
| Persistence and release clarity | **CONTENT PASS / PUBLIC CLAIMS VERIFIED** | Articles 22 and 24 distinguish Datadrive, Snapshot, and ephemeral storage. Current public Glows.ai pages confirm Snapshot + Datadrive, `/datadrive` exclusion from Snapshots, and deletion of instance-based data after release. | Authenticated workflow verification that current UI and selected account behavior match |
| Security responsibility | **PASS FOR GUIDANCE** | Articles 20 and 24 require authentication, HTTPS, secret handling, monitoring, and safe support escalation. | Authenticated/unauthenticated endpoint test on a current instance |
| Performance validation | **CONTENT PASS / EVIDENCE PENDING** | Article 21 defines TTFT, inter-token latency, end-to-end latency, throughput, errors, percentiles, and reproducible test conditions. | Raw first-party benchmark output |
| Recovery and reproducibility | **CONTENT PASS / EVIDENCE PENDING** | Articles 22 and 23 provide checkpoint, manifest, clean-build, region, and recovery procedures. | Demonstrated interruption/resume and clean-instance rebuild |
| Honest fit and limitations | **PASS** | Articles 17, 19, 20, and 24 state when a hosted API may be simpler, when to stop spending, and what customers must operate themselves. | Customer comprehension confirmation |
| Commercial and data-term transparency | **PUBLIC TERMS VERIFIED / CUSTOMER COMPREHENSION PENDING** | Articles 18 and 24 now disclose the general non-refund rule, taxes, possible disclosed tool fees, beta-service limitations, account-termination data retrieval, user IP ownership, and user obligations based on terms checked July 23, 2026. | Legal review for intended markets and customer comprehension confirmation |
| Support path | **PASS** | Articles 17–24 each contain `support@glows.ai`; article 24 also includes Discord and Line. | Confirm contact destinations remain monitored |
| SEO/GEO structure | **PASS FOR DRAFTS** | Unique IDs, answer-first introductions, headings, tables, checklists, internal links, descriptions, source links, and no duplicate IDs. `git diff --check` passes. | Render/build validation in the publishing application |
| Platform evidence collection | **READY, NOT EXECUTED** | `EVIDENCE-COLLECTION-RUNBOOK.md` defines screenshots, commands, CSVs, redaction, benchmark, cost, recovery, and clean-build tests. | Live customer account execution |
| Customer outcome validation | **READY, NOT EXECUTED** | `CUSTOMER-VALIDATION-PROTOCOL.md` defines participants, tasks, a confidence index, regret-risk interviews, accuracy review, and thresholds. | Recruit participants, run study, analyze results |
| “No regret” outcome | **NOT PROVEN** | The content deliberately addresses known regret risks and avoids unsupported guarantees. | Real customer results meeting validation thresholds |

## Article-level audit

| Article | Editorial completeness | First-party proof | Customer validation | Release status |
|---|---|---|---|---|
| 17 — GPU and quantization | Complete draft | Missing | Not run | Hold |
| 18 — Workload cost | Complete draft | Missing | Not run | Hold |
| 19 — GPU rental vs API | Complete draft | Missing | Not run | Hold |
| 20 — vLLM deployment | Complete draft | Missing | Not run | Hold |
| 21 — Latency benchmark | Complete draft | Missing | Not run | Hold |
| 22 — Checkpoint and recovery | Complete draft | Missing | Not run | Hold |
| 23 — Region and reproducibility | Complete draft | Missing | Not run | Hold |
| 24 — Customer playbook | Complete draft | Depends on 17–23 | Not run | Hold |

## Evidence inventory

### Present

- Eight complete MDX drafts
- Unique frontmatter IDs
- Internal customer-journey links
- Support paths
- Current official external documentation links
- Public Glows.ai rate snapshot checked July 23, 2026
- Current public confirmation of per-second billing, pay-as-you-go compute, Snapshot + Datadrive, enterprise support, and ISO/IEC 27001:2022 certification
- Current public Glows.ai tutorials confirming `/datadrive` persistence guidance and deletion of instance-based files after release
- Current Terms of Service review covering pricing currency, general non-refund rule, taxes, beta services, user obligations, IP ownership, and post-termination data retrieval
- Publishing gates
- Technical evidence runbook
- Customer-validation protocol
- Existing platform screenshots for older tutorials

### Missing

- Current screenshots for articles 17–24
- Account-specific checkout pricing capture
- Current GPU and region availability capture
- VRAM measurements
- API authentication proof
- Raw benchmark results
- Final instance cost
- Recovery timeline
- Clean rebuild result
- Customer task scores
- Confidence-index results
- Current-customer accuracy review
- Named author and technical reviewer
- Published-page render/build result

## Integrity checks

| Check | Result |
|---|---|
| Duplicate article IDs | None found |
| Reader-facing fabricated benchmark results | None found |
| Reader-facing fixed unverified prices in new articles | None found |
| Unsupported “best,” “cheapest,” or guarantee claims | Avoided by publishing policy |
| Hidden editorial evidence reminders | Present in all eight drafts |
| Formatting errors from `git diff --check` | None |
| New cluster orphan pages | None |

## Public verification record

Checked July 23, 2026:

| Public claim | Source | Result |
|---|---|---|
| Per-second billing and real-time costs | `https://glows.ai/` | Verified on public page |
| Public GPU rate table | `https://glows.ai/` | Verified on public page and added to article 18 with date |
| Pay-as-you-go on-demand GPU compute | `https://glows.ai/product/on-demand-cloud` | Verified on public page |
| Snapshot + Datadrive | `https://glows.ai/` | Verified on public page |
| Datadrive product and workflow positioning | `https://glows.ai/datadrive` | Verified on public page |
| Instance-based data deleted after release | `https://glows.ai/article/download_huggingface_models` | Verified in current public tutorial |
| `/datadrive` excluded from Snapshot | `https://glows.ai/article/set_ollama_model_path` | Verified in current public tutorial |
| Support email, Discord, and Line | Current public Glows.ai tutorials | Verified |
| ISO/IEC 27001:2022 certification statement | `https://glows.ai/` | Verified on public page |
| Payments generally final and non-refundable, subject to applicable law | `https://glows.ai/tos` | Verified in current public terms |
| Applicable taxes and disclosed specialized-tool fees | `https://glows.ai/tos` | Verified in current public terms |
| Beta services may change and may be less supported or reliable | `https://glows.ai/tos` | Verified in current public terms |
| User retains IP in User Data and User Applications | `https://glows.ai/tos` | Verified in current public terms |
| Fifteen-day data retrieval after agreement termination, subject to terms and law | `https://glows.ai/tos` | Verified in current public terms |

Public verification does not prove account-specific price, availability, end-to-end behavior, performance, or customer satisfaction.

## Completion decision

**Status: NOT COMPLETE — EXTERNAL EVIDENCE REQUIRED**

The repository proves that the content framework, drafts, safeguards, evidence plan, and customer-research plan exist. It does not prove the intended customer outcome.

Completion requires:

1. Execute `EVIDENCE-COLLECTION-RUNBOOK.md`.
2. Replace each hidden editorial evidence reminder with verified results.
3. Have a named technical reviewer confirm platform accuracy.
4. Render and test the published pages.
5. Execute `CUSTOMER-VALIDATION-PROTOCOL.md`.
6. Meet every task, confidence, and accuracy threshold.
7. Resolve all critical and high findings.
8. Rerun this audit against the resulting evidence.

Do not claim that the objective is achieved before those conditions pass.

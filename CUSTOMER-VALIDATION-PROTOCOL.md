# Glows.ai Content Customer-Validation Protocol

Use this protocol to test whether articles 17–24 help real customers feel informed, in control, and confident about doing business with Glows.ai. Do not infer this outcome from page views or editorial opinion alone.

## Research question

After reading the content, can a prospective or current Glows.ai customer:

- Explain what they are buying
- Estimate and control cost
- Protect work before releasing compute
- Identify their own operational responsibilities
- Choose an appropriate next step
- Recognize when Glows.ai is or is not a good fit
- Make the decision without feeling that material limitations were hidden

The goal is informed confidence, not maximum purchase intent.

## Participant groups

Recruit at least:

| Group | Minimum | Purpose |
|---|---:|---|
| Prospective customers who have not rented a cloud GPU | 5 | Test clarity and onboarding |
| Developers who have used another GPU cloud or hosted API | 5 | Test comparison credibility |
| Current or recent Glows.ai customers | 5 | Test accuracy against real experience |
| Production or operations practitioners | 3 | Test security, recovery, and reproducibility |

Do not recruit only satisfied customers. Include participants who:

- Abandoned setup
- Chose another provider
- Experienced an interrupted job
- Were surprised by cost
- Used Glows.ai only once

Record relevant experience without collecting unnecessary personal data.

## Avoid biased research

- Tell participants the team is testing the content, not testing them.
- Do not explain Glows.ai before the unaided tasks.
- Do not lead participants toward positive responses.
- Do not ask, “Do you agree this is helpful?”
- Separate the moderator from the article author when practical.
- Offer the same incentive regardless of sentiment.
- Do not request a public review as part of the research session.
- Report negative and mixed findings with the positive results.

## Materials

Provide:

1. [The Glows.ai Cloud GPU Customer Playbook](https://glows.ai/article/cloud_gpu_customer_playbook)
2. The seven linked decision guides
3. A hypothetical workload card
4. A current Glows.ai checkout screen or sanitized recording
5. A response sheet

Do not expose unreleased pricing or private customer information.

## Workload cards

Use at least three scenarios.

### Scenario A: First open-model experiment

> You want to test an instruction model for a small internal prototype. You do not know which GPU to choose. The model may be reused next week, and the first test should stay within a fixed budget.

### Scenario B: Intermittent inference API

> Your application receives irregular traffic. You are deciding between a hosted API and a rented GPU. You need an authenticated endpoint and want to avoid paying for long idle periods.

### Scenario C: Long-running training or batch job

> Your job may run for several hours. An interruption would be expensive. You need to preserve checkpoints, reproduce the environment, and resume on another instance.

## Part 1: Five-second comprehension test

Show only the title and opening of the customer playbook for five seconds. Then hide it.

Ask:

1. What is this page about?
2. Who is it for?
3. What do you expect it to help you decide?
4. Does it appear educational, promotional, or both?

Pass when at least 80% of participants identify:

- Cloud GPU decision guidance
- Glows.ai as the platform context
- Cost, deployment, or operational control as a likely outcome

If participants describe it only as advertising, revise the opening.

## Part 2: Unmoderated findability tasks

Do not tell participants which article contains the answer.

### Task 1: Choose a starting GPU

Ask the participant to find:

- Inputs needed for a VRAM decision
- Why checkpoint size does not equal runtime memory
- How they would verify the choice

### Task 2: Estimate cost

Ask the participant to identify:

- Costs beyond the hourly GPU rate
- The correct denominator for unit cost
- When the instance should be released

### Task 3: Protect work

Ask the participant to explain:

- Which files belong on Datadrive
- What a Snapshot preserves
- What is lost when ephemeral instance storage is released

### Task 4: Decide between API and GPU

Ask the participant to:

- Choose a comparable unit
- Explain how utilization affects the result
- Name one situation where a hosted API is the better choice

### Task 5: Prepare production validation

Ask the participant to find:

- Endpoint authentication requirements
- Latency and throughput metrics
- Recovery and clean-rebuild requirements

### Task 6: Get help

Ask the participant to locate:

- The support email
- What diagnostic information to include
- What secrets must not be sent

## Task scoring

Score each task:

| Score | Meaning |
|---:|---|
| 0 | Could not find or answer |
| 1 | Found partial information but missed a material risk |
| 2 | Found the answer with hesitation or moderator help |
| 3 | Found and explained the answer independently |

Publication target:

- Median score of at least 2.5 for every task
- No task with more than 20% of participants scoring 0 or 1
- No current Glows.ai customer identifying a material platform inaccuracy

## Part 3: Confidence survey

Use a 1–5 scale:

1. Strongly disagree
2. Disagree
3. Neither
4. Agree
5. Strongly agree

Ask participants to rate:

1. I understand what I control when renting a GPU on Glows.ai.
2. I understand what Glows.ai controls and what remains my responsibility.
3. I know what information I need before choosing a GPU.
4. I know how to estimate cost beyond the hourly rate.
5. I understand when a hosted API may be a better choice.
6. I know which files will survive instance release.
7. I know how to preserve an environment and recover a job.
8. I know how to test whether the deployment meets its performance target.
9. I know where to get help and what information to provide.
10. The content discusses limitations honestly.
11. I would feel comfortable running a small, controlled first experiment.
12. I would know when to stop rather than continue spending.
13. The content makes Glows.ai feel more trustworthy.
14. I can explain the decision to a technical stakeholder.
15. I can explain the decision to a budget owner.

## Confidence index

Calculate:

```text
confidence index =
sum of responses to questions 1–15
/ maximum possible score
× 100
```

Segment results by participant group. Do not report only the combined average.

Publication targets:

- Overall median confidence index of at least 80
- Median of at least 4 for questions 2, 4, 6, 10, 11, and 12
- No participant group below 70
- Current-customer accuracy rating of at least 4

These targets show content performance in the study. They do not guarantee every customer will be satisfied.

## Part 4: Regret-risk questions

Ask open-ended questions before revealing the research goal:

1. What could still surprise you after checkout?
2. What could cause you to lose money?
3. What could cause you to lose work?
4. Which responsibility was least clear?
5. Which claim would you want proof for?
6. What would make you choose another provider?
7. What would make you contact support before proceeding?
8. Did any part feel like important information was being hidden?
9. What would you change before sharing this with a colleague?
10. After reading, what is your next action?

Code responses into:

- Cost surprise
- Persistence misunderstanding
- Security misunderstanding
- Model/GPU mismatch
- Performance uncertainty
- Support uncertainty
- Availability or region uncertainty
- Comparison credibility
- Missing evidence
- Navigation failure

## Part 5: Current-customer accuracy review

Ask current Glows.ai customers to mark every platform statement:

| Status | Meaning |
|---|---|
| Accurate | Matches current experience |
| Incomplete | True but missing an important condition |
| Outdated | Interface or behavior changed |
| Incorrect | Does not match the platform |
| Could not verify | Participant has not used the feature |

Require direct review of:

- Instance release and billing
- Ephemeral instance data
- Datadrive allocation and mounting
- Snapshot scope
- Auto Deploy behavior
- Port access
- Region and GPU selection
- Support contact paths

One “Incorrect” rating on a material operational claim blocks publication until investigated.

## Part 6: Quote and testimonial policy

Research feedback is not automatically a testimonial.

To publish a quote:

1. Request separate, explicit written permission after the study.
2. Show the exact edited quote and context.
3. Disclose material incentives or relationships.
4. Do not require positive wording.
5. Do not turn a mixed statement into an unqualified endorsement.
6. Allow withdrawal before publication.
7. Store consent with the quote record.

Prefer specific outcome statements:

> “The storage checklist helped me move checkpoints before releasing the instance.”

Avoid vague or unverifiable claims:

> “Glows.ai is the best GPU cloud.”

## Issue prioritization

| Severity | Definition | Required action |
|---|---|---|
| Critical | Could cause data loss, security exposure, or material unexpected cost | Block publication and correct |
| High | Prevents a key task or materially misstates platform behavior | Correct before publication |
| Medium | Creates hesitation, navigation friction, or incomplete understanding | Correct in the current revision |
| Low | Style preference or minor clarity issue | Add to editorial backlog |

## Article feedback map

| Finding | Primary article |
|---|---|
| GPU choice unclear | 17 |
| Cost surprise | 18 |
| API comparison not credible | 19 |
| Deployment or security unclear | 20 |
| Performance proof unclear | 21 |
| Persistence or recovery unclear | 22 |
| Region or reproducibility unclear | 23 |
| Journey, support, or overall confidence unclear | 24 |

Apply the fix to the primary article, then check the customer playbook for a matching summary update.

## Study results template

```markdown
# Customer Content Validation — YYYY-MM-DD

## Participants
- Prospective:
- Other-platform users:
- Current Glows.ai customers:
- Operations practitioners:

## Task results
| Task | Median score | Failure rate | Main issue |
|---|---:|---:|---|

## Confidence results
| Group | Median index | Lowest question | Score |
|---|---:|---|---:|

## Accuracy findings
| Claim | Status | Evidence | Required change |
|---|---|---|---|

## Regret risks
| Risk | Frequency | Severity | Article |
|---|---:|---|---:|

## Decision
- [ ] Publish
- [ ] Revise and retest
- [ ] Blocked by platform evidence

## Changes required
1.
```

## Completion criteria

The customer-confidence content cluster is validated only when:

- All technical evidence gates pass.
- All task-score thresholds pass.
- All confidence-index thresholds pass.
- No unresolved critical or high finding remains.
- No material platform claim is rated incorrect.
- At least one researcher who did not author the pages reviews the result.
- Findings and corrections are retained for future content updates.

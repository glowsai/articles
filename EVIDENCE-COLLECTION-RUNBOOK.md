# Glows.ai Content Evidence Collection Runbook

Use this runbook to replace editorial placeholders in articles 17–24 with current, first-party evidence. Run the complete sequence with one test project so the cost, performance, persistence, and recovery results describe the same deployment.

## Evidence rules

- Use a test account and non-sensitive prompts.
- Record the test date and timezone.
- Preserve the exact model revision, image ID, runtime version, GPU, and region.
- Capture the current rate before checkout.
- Label estimates and measurements separately.
- Keep raw command output; do not retain only screenshots.
- Redact account IDs, passwords, tokens, private endpoints, billing identity, and unrelated resources.
- Never edit a result to look better. Explain anomalies.
- Have a second technical reviewer reproduce the key result.

## Recommended test project

Choose a small instruction model supported by the selected vLLM image and a single GPU. The model must:

- Have a clear license and model card
- Fit in at least two supported precision or quantization configurations
- Support a chat template
- Be small enough to repeat tests without excessive cost
- Produce non-sensitive demonstration output

Record the immutable model revision rather than only the repository name.

## Create the evidence directory

On Datadrive:

```bash
export EVIDENCE_DIR="/datadrive/evidence/glows-customer-playbook-$(date +%Y%m%d)"
mkdir -p "$EVIDENCE_DIR"/{system,cost,memory,api,benchmark,recovery,region,screenshots}
```

Create a metadata file:

```bash
{
  echo "test_started_at=$(date --iso-8601=seconds)"
  echo "timezone=$(date +%Z)"
  echo "region=REPLACE_ME"
  echo "gpu=REPLACE_ME"
  echo "image_id=REPLACE_ME"
  echo "model=REPLACE_ME"
  echo "model_revision=REPLACE_ME"
  echo "quantization=REPLACE_ME"
} > "$EVIDENCE_DIR/system/test-metadata.txt"
```

## Phase 1: Capture the checkout decision

Before creating the instance, capture:

1. Region
2. GPU and quantity
3. Image name and ID
4. Current compute rate and billing unit
5. Datadrive selection
6. Snapshot allocation, if used
7. Exposed ports
8. Final checkout summary

### Screenshot requirements

Use descriptive filenames:

```text
01-region-gpu-selection.png
02-image-selection.png
03-datadrive-mount.png
04-port-selection.png
05-checkout-rate-summary.png
```

Redact credit balance, account identifiers, and unrelated instances.

### Cost record

Create:

```csv
item,quantity,unit,rate,currency,price_checked_at,source
gpu,1,hour,REPLACE_ME,REPLACE_ME,REPLACE_ME,Glows.ai checkout
datadrive,REPLACE_ME,GB-month,REPLACE_ME,REPLACE_ME,REPLACE_ME,Glows.ai storage
snapshot,REPLACE_ME,GB-month,REPLACE_ME,REPLACE_ME,REPLACE_ME,Glows.ai storage
```

Save as:

```text
cost/rates.csv
```

## Phase 2: Capture the environment

After the instance reaches `Running`:

```bash
date --iso-8601=seconds | tee "$EVIDENCE_DIR/system/instance-ready-at.txt"
nvidia-smi | tee "$EVIDENCE_DIR/system/nvidia-smi.txt"
nvidia-smi --query-gpu=name,driver_version,memory.total \
  --format=csv,noheader \
  | tee "$EVIDENCE_DIR/system/gpu-summary.csv"
python --version 2>&1 | tee "$EVIDENCE_DIR/system/python-version.txt"
pip --version 2>&1 | tee "$EVIDENCE_DIR/system/pip-version.txt"
vllm --version 2>&1 | tee "$EVIDENCE_DIR/system/vllm-version.txt"
df -h /datadrive | tee "$EVIDENCE_DIR/system/datadrive-mount.txt"
```

If the commands expose a hostname or identifier, redact only the published copy. Retain the original in controlled storage.

Capture screenshots:

```text
06-instance-running.png
07-access-methods-and-ports.png
08-datadrive-visible.png
```

## Phase 3: Measure startup phases and cost

Record timestamps for:

- Checkout submitted
- Instance running
- Terminal available
- Model download started
- Model download completed
- Server launch started
- Health check passed
- Benchmark started
- Benchmark completed
- Persistence check completed
- Instance released

Use:

```csv
phase,started_at,completed_at,duration_seconds,notes
instance_start,REPLACE_ME,REPLACE_ME,REPLACE_ME,
model_download,REPLACE_ME,REPLACE_ME,REPLACE_ME,
model_load,REPLACE_ME,REPLACE_ME,REPLACE_ME,
benchmark,REPLACE_ME,REPLACE_ME,REPLACE_ME,
recovery_test,REPLACE_ME,REPLACE_ME,REPLACE_ME,
```

Save as:

```text
cost/phase-timings.csv
```

After release, capture the final dashboard status and total cost. Save:

```text
screenshots/20-instance-released-and-cost.png
cost/final-cost.txt
```

## Phase 4: Measure VRAM at two configurations

Collect a baseline:

```bash
nvidia-smi --query-gpu=timestamp,name,memory.used,memory.total,utilization.gpu \
  --format=csv,noheader \
  | tee "$EVIDENCE_DIR/memory/baseline.csv"
```

Start the first supported configuration. Record the exact command in:

```text
memory/config-a-command.sh
```

While the server loads and serves representative requests:

```bash
nvidia-smi --query-gpu=timestamp,memory.used,memory.total,utilization.gpu \
  --format=csv,noheader,nounits -l 1 \
  > "$EVIDENCE_DIR/memory/config-a-samples.csv"
```

Stop sampling with `Ctrl+C` after the test.

Repeat with the second supported precision or quantization:

```text
memory/config-b-command.sh
memory/config-b-samples.csv
```

### Required comparison

```csv
configuration,weight_format,max_model_len,concurrency,peak_vram_mib,loaded_successfully,request_success_rate
config-a,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME
config-b,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME
```

Do not state that one configuration is better without also checking output quality and latency.

## Phase 5: Prove the authenticated API

Set the key without placing it in the runbook:

```bash
export VLLM_API_KEY='REPLACE_IN_SECURE_SHELL'
```

Record the server command with the secret referenced by variable:

```bash
vllm serve /datadrive/models/MODEL_NAME \
  --host 0.0.0.0 \
  --port 8000 \
  --dtype auto \
  --max-model-len REPLACE_ME \
  --api-key "$VLLM_API_KEY"
```

Capture:

```bash
curl -sS http://127.0.0.1:8000/health \
  -o "$EVIDENCE_DIR/api/health-response.txt" \
  -w '%{http_code}\n' \
  | tee "$EVIDENCE_DIR/api/health-status.txt"
```

```bash
curl -sS http://127.0.0.1:8000/v1/models \
  -H "Authorization: Bearer $VLLM_API_KEY" \
  > "$EVIDENCE_DIR/api/models-response.json"
```

Run one sanitized chat request and save:

```text
api/chat-request.json
api/chat-response.json
```

Also test a missing or incorrect API key. Record only the HTTP status and sanitized error:

```text
api/unauthorized-status.txt
```

Required proof:

- Health check succeeds
- Model list returns the expected model
- Authenticated chat succeeds
- Unauthenticated request is rejected
- No key appears in files or screenshots

## Phase 6: Benchmark latency and throughput

Create a non-sensitive JSONL prompt set representing:

- Short input and output
- Long input, short output
- Short input, long output
- Expected production input and output

Run:

```bash
vllm bench serve --help \
  > "$EVIDENCE_DIR/benchmark/vllm-bench-help.txt"
```

Use the flags supported by the installed version. Save the exact command:

```text
benchmark/command.sh
```

Retain:

```text
benchmark/prompts.jsonl
benchmark/raw-results.json
benchmark/detailed-results.json
benchmark/server-metrics.txt
```

### Result table

```csv
load_stage,requests,request_rate,concurrency,success_rate,ttft_p50_ms,ttft_p95_ms,e2e_p50_ms,e2e_p95_ms,output_tokens_per_second
baseline,REPLACE_ME,REPLACE_ME,1,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME
expected,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME
stress,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME,REPLACE_ME
```

Save as:

```text
benchmark/summary.csv
```

## Phase 7: Test checkpoint recovery

Use a short, disposable job with no sensitive data.

Required sequence:

1. Start the job.
2. Produce at least two checkpoints on Datadrive.
3. Record the current step.
4. Validate and checksum the latest checkpoint.
5. Stop the process.
6. Release the instance only after persistence is confirmed.
7. Create a clean instance.
8. Mount the same Datadrive.
9. Restore the environment.
10. Resume from the checkpoint.
11. Prove that the step advances.

Record:

```bash
sha256sum /datadrive/checkpoints/TEST_CHECKPOINT \
  | tee "$EVIDENCE_DIR/recovery/checkpoint-sha256.txt"
```

Create:

```csv
event,timestamp,global_step,instance_id_redacted,notes
checkpoint_written,REPLACE_ME,REPLACE_ME,instance-a,
instance_released,REPLACE_ME,REPLACE_ME,instance-a,
new_instance_ready,REPLACE_ME,REPLACE_ME,instance-b,
checkpoint_loaded,REPLACE_ME,REPLACE_ME,instance-b,
training_resumed,REPLACE_ME,REPLACE_ME,instance-b,
```

Save as:

```text
recovery/timeline.csv
```

Calculate:

```text
observed RPO = last in-memory step - restored checkpoint step
observed RTO = resumed-processing time - interruption time
```

Capture screenshots proving the checkpoint exists before release and the new instance advances beyond the restored step.

## Phase 8: Measure region latency

From at least two relevant client locations, run:

```bash
for run in 1 2 3 4 5; do
  curl -o /dev/null -s \
    -w "$run,%{time_namelookup},%{time_connect},%{time_appconnect},%{time_starttransfer},%{time_total}\n" \
    https://REPLACE_ENDPOINT/health
done
```

Use a CSV header:

```csv
run,dns_seconds,connect_seconds,tls_seconds,first_byte_seconds,total_seconds
```

Record:

- Client city or region, not a personal address
- Client network type
- Server region
- Test timestamp
- Endpoint path

Do not present five samples as a long-term availability guarantee.

## Phase 9: Prove reproducibility

Using a new instance:

1. Follow only the deployment manifest.
2. Mount documented storage.
3. Apply pinned versions.
4. Inject secrets securely.
5. Start the endpoint.
6. Run health, model, chat, and benchmark smoke tests.
7. Record every undocumented manual action.

Acceptance result:

```csv
check,result,evidence
instance_created_from_manifest,PASS_OR_FAIL,REPLACE_ME
storage_mounted,PASS_OR_FAIL,REPLACE_ME
runtime_version_matched,PASS_OR_FAIL,REPLACE_ME
health_check_passed,PASS_OR_FAIL,REPLACE_ME
authenticated_chat_passed,PASS_OR_FAIL,REPLACE_ME
benchmark_smoke_passed,PASS_OR_FAIL,REPLACE_ME
undocumented_steps,REPLACE_ME,REPLACE_ME
```

## Phase 10: Calculate cost per successful result

Use final measured values:

```text
infrastructure cost =
compute cost + persistent storage cost + billable transfer cost
```

```text
cost per successful request =
infrastructure cost / successful requests
```

Create two totals:

- Infrastructure-only
- Fully loaded, including clearly separated engineering time

For the GPU-versus-API article, run the same sanitized task set through the current alternative. Match input/output constraints and record task success, not only price.

## Publication mapping

| Evidence | Articles |
|---|---|
| Checkout configuration and rates | 18, 19, 24 |
| VRAM comparison | 17, 24 |
| Authenticated API | 20, 24 |
| Latency benchmark | 19, 21, 23, 24 |
| Checkpoint recovery | 22, 24 |
| Region measurements | 23, 24 |
| Clean rebuild | 20, 23, 24 |
| Final unit cost | 18, 19, 24 |

## Final review

Before publishing:

- [ ] Every screenshot has alt text explaining what it proves.
- [ ] Every table links to or names the raw evidence.
- [ ] Every price has a date and currency.
- [ ] Every benchmark states its conditions.
- [ ] Every estimate is labeled.
- [ ] Every secret and identifier is removed.
- [ ] A second reviewer repeated the endpoint, recovery, and clean-build checks.
- [ ] Failed or mixed results are disclosed.
- [ ] The published conclusion matches the evidence.

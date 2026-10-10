# Socratic prompts — Stage 3

## Prediction

1. Before running, how much VRAM do you expect a naive contiguous KV-cache allocation to waste on a realistic mix of request lengths?
2. Do you expect continuous batching to help throughput more, latency more, or both? Why?

## Measurement

3. What throughput and latency numbers did you record before and after the change?
4. Did chunked prefill (or equivalent) prevent long prefills from starving decode requests? Show the evidence.

## Reflection

5. In one sentence, what problem does PagedAttention solve that continuous batching alone does not?
6. If you could change only one serving-engine setting for a production workload with highly variable request lengths, which would you change first and why?

# Stage 4: KV-Cache & Memory Hierarchy

**Time box:** 1–2 evening sessions (2–4 hours)

**Core path:** Yes

## Learning objectives

By the end of this module you can:

- Explain prefix caching and when shared system prompts or multi-turn histories produce free speed.
- Describe KV quantization and CPU/NVMe offloading as extensions of the memory hierarchy.
- Measure the TTFT or throughput impact of prefix caching (or a simple cache-sharing proxy) on a repeated prompt.
- Identify one practical tier beyond GPU HBM that can hold KV state.

## Prerequisites

- Stage 3 complete (serving engine running).

## Primary sources

- PagedAttention paper (sharing and copy-on-write sections).
- vLLM / SGLang docs on prefix caching and KV offloading.
- Recent notes on persistent or NVMe-backed KV caches for long-lived sessions.

## Lab: Measure prefix-caching benefit (or build a simple routing proxy)

1. Using vLLM, SGLang, or a simple custom setup, send multiple requests that share an identical long system prompt or prefix.
2. Measure TTFT or overall latency with and without prefix caching enabled (or with requests routed to the same replica).
3. Optionally experiment with KV quantization or a simple CPU offload if supported.
4. Write `results/prefix-caching.md` with config, numbers, and an explanation of where the savings came from.

**Success criteria:** You can show a concrete reduction in TTFT or latency from cache reuse and explain it in terms of avoided KV computation or memory traffic.

## Estimated sessions

1. Enable and measure prefix caching.
2. (Optional) Explore one offload or quantization option.

## Stretch goals

- Build a minimal routing proxy that pins requests with the same prefix to the same replica.
- Quantify the memory saved by sharing versus duplicating the prefix.

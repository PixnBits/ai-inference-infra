# Stage 3: Modern Serving Engines & Batching

**Time box:** 1–2 evening sessions (2–4 hours)

**Core path:** Yes

## Learning objectives

By the end of this module you can:

- Explain PagedAttention and why contiguous KV-cache allocation wastes memory.
- Describe continuous batching and chunked prefill and when each helps.
- Deploy or run a model with vLLM or SGLang and measure throughput vs latency under different batching settings.
- Tune a parameter (e.g., chunk size or max batch size) and show the effect on a metric.

## Prerequisites

- Stage 2 complete.
- Ability to install and run vLLM or SGLang (or a cloud instance if local hardware is limited).

## Primary sources

- Kwon et al., PagedAttention paper (SOSP 2023).
- vLLM and SGLang documentation / design notes on continuous batching and chunked prefill.
- Original vLLM blog post.

## Lab: Deploy a model and tune batching

1. Install vLLM or SGLang (or use a pre-built container / cloud instance).
2. Serve a model that fits your hardware (or a small one).
3. Measure throughput and latency (or TTFT / inter-token latency) under naive or default settings versus continuous batching / chunked prefill.
4. Tune one parameter (chunk size, max num sequences, etc.) and record the change.
5. Write `results/batching.md` with full config, before/after numbers, and an explanation of why the change helped or hurt.

**Success criteria:** You can show a measurable difference from a batching-related change and explain it in terms of memory utilization or request interleaving.

## Estimated sessions

1. Get the serving engine running and capture baseline numbers.
2. Tune and compare.

## Stretch goals

- Compare vLLM vs SGLang on the same model and hardware.
- Measure VRAM utilization with and without PagedAttention-style management (if visible).

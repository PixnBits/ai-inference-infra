# Stage 2: Transformer Inference Physics

**Time box:** 1–2 evening sessions (2–4 hours)

**Core path:** Yes

## Learning objectives

By the end of this module you can:

- Distinguish prefill and decode phases and explain why their arithmetic intensities and bottlenecks differ.
- Estimate arithmetic intensity for a decode step and relate it to memory-bandwidth limits.
- Profile a real model and identify the dominant memory traffic during token generation.
- Describe how the KV-cache grows and why it becomes the primary memory consumer.

## Prerequisites

- Stage 1 complete (or equivalent ability to run and time kernels).
- Python with PyTorch and transformers (or vLLM/SGLang if available).

## Primary sources

- Kwon et al., “Efficient Memory Management for Large Language Model Serving with PagedAttention,” SOSP 2023 (KV-cache memory bottleneck sections).
- vLLM blog post introducing PagedAttention.
- Nsight Systems or PyTorch Profiler docs for timeline views.

## Lab: Profile prefill vs decode and locate the memory bottleneck

1. Load a small-to-medium model that fits on your hardware (1B–7B class, or a tiny model on CPU/AMD).
2. Measure prefill of a long prompt and decode of subsequent tokens.
3. Using a profiler (Nsight Systems, PyTorch profiler, or simple timing + memory counters), identify which operations dominate during decode and whether they are bandwidth-bound.
4. Write `results/prefill-decode.md` with full config, timings, one concrete observation about memory traffic (e.g., KV-cache reads), and a short arithmetic-intensity estimate for decode.

**Success criteria:** You can show that decode is more memory-bandwidth sensitive than prefill and explain the KV-cache contribution.

## Estimated sessions

1. Get a model running and capture basic timings.
2. Profile and write the analysis.

## Stretch goals

- Vary context length and plot decode time or memory usage versus length.
- Compare GQA/MQA versus full MHA if available.

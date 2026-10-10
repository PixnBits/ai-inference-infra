# Stage 6: Kernel-Level Engineering

**Time box:** 1–2 evening sessions

**Core path:** Yes

## Learning objectives

- Write or modify a fused Triton kernel (RMSNorm, Softmax, or a simple attention fragment).
- Benchmark it against the native PyTorch implementation.
- Explain why operator fusion and CUDA graphs reduce overhead.
- Identify, from a profile, where Python or kernel-launch overhead dominates.

## Prerequisites

Stage 1 (GPU foundations) recommended.

## Primary sources

- Triton tutorials (fused kernels, matmul)
- FlashAttention papers (for the attention case)
- CUDA graphs documentation

## Lab: Fused kernel vs PyTorch

1. Implement a small fused kernel in Triton (start from the official RMSNorm or Softmax example).
2. Benchmark it against the equivalent PyTorch ops for increasing sizes.
3. Capture timing and, if available, a profiler note on launch overhead.
4. Record numbers and config in `results/kernel.md`.

**Success criteria:** Correctness check plus a measured speedup (or lack of one) with an explanation of the dominant factor.

## Stretch

- Add a CUDA graph around a small sequence of ops and re-measure.
- Compare against a FlashAttention-style kernel if available.

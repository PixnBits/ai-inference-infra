# Stage 1: GPU Foundations

**Time box:** 1–2 evening sessions (2–4 hours total)

**Core path:** Yes

## Learning objectives

By the end of this module you can:

- Describe the relevant levels of the GPU memory hierarchy (registers, shared memory / SRAM, global / HBM) and why movement between them dominates many kernels.
- Write or modify a simple custom kernel (CUDA or Triton) for matrix multiplication and profile it against a library baseline (cuBLAS, PyTorch, or equivalent).
- Identify, from a profile, whether a kernel is limited by compute, memory bandwidth, or occupancy/latency.
- Explain warp (or wavefront) scheduling at a high level and why it matters for latency hiding.

## Prerequisites

- Stage 0 complete (or equivalent environment verification).
- Willingness to look at a profiler trace, even if only the summary metrics.

## Primary sources

- CUDA C++ Programming Guide — memory hierarchy and execution model chapters
- Triton language documentation and the official matmul tutorial
- Nsight Compute user guide (key metrics: achieved bandwidth, occupancy, roofline)
- (Optional) "Programming Massively Parallel Processors" excerpts on warps and memory

## Lab: Custom matmul kernel + profile vs library

1. Choose your implementation path:
   - NVIDIA + CUDA: write a simple tiled matrix-multiply kernel (or start from a well-known tutorial stub).
   - Triton (works on NVIDIA and often AMD/CPU): implement the official Triton matmul example or a simplified version.
   - If pure CPU for now: implement a blocked/tiled matmul in Python/NumPy or a simple C++ version and compare to a BLAS call; note the analogy.
2. Profile the custom kernel and the library baseline (cuBLAS, torch.matmul, or equivalent) with the best available tool (Nsight Compute, Triton profiler, or simple timing + bandwidth estimate).
3. Record in `results/matmul.md`:
   - Full hardware and software config
   - Kernel launch configuration or tile sizes
   - Achieved throughput (TFLOPS or GB/s) for both versions
   - One screenshot or text extract of the key profiler metrics
   - A one-paragraph explanation of the largest gap you observed

**Success criteria:** You can show two numbers (custom vs library) and explain, in terms of memory traffic or occupancy, why they differ. The config is complete enough for someone else to attempt reproduction.

## Estimated sessions

1. Get a working custom kernel and a library baseline running.
2. Profile, measure, and write the comparison note.

## Stretch goals

- Add shared-memory tiling (or Triton equivalent) and re-measure the bandwidth utilization.
- Force a low-occupancy configuration and observe the latency-hiding effect (or its absence).

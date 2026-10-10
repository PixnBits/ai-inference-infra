# Stage 0: Setup & Entry Points

**Time box:** 1 evening session (1.5–2.5 hours)

**Core path:** Yes

## Learning objectives

By the end of this module you can:

- Verify that your development environment can run basic GPU or CPU kernel experiments and profiling.
- Identify whether you are on an NVIDIA, AMD, or CPU-only path and know the cheapest way to access NVIDIA hardware for later labs if needed.
- Capture a baseline measurement (e.g. matrix-multiply throughput or simple attention) with full hardware and software configuration recorded.
- Explain the difference between the systems-first and ML-engineering-first entry paths.

## Prerequisites

- A workstation or laptop with Linux (Ubuntu preferred) or the ability to spin up a short-lived cloud GPU instance.
- Basic familiarity with Python, git, and the command line.

## Primary sources

- CUDA C++ Programming Guide (for NVIDIA path)
- Triton tutorials (https://triton-lang.org)
- Nsight Compute and Nsight Systems documentation (NVIDIA)
- ROCm documentation if on AMD

## Lab: Environment verification and baseline measurement

1. Record your full hardware configuration (CPU, GPU/APU, RAM, OS, relevant driver versions).
2. Install or verify the tools you will use:
   - For NVIDIA: CUDA toolkit, Nsight Compute/Systems, Python with PyTorch or Triton.
   - For AMD (e.g. Framework Desktop / Ryzen AI): ROCm if available, or Triton on CPU, or note that later CUDA-specific labs will use cloud.
   - Always: Python, git, a simple profiler (or time + memory counters).
3. Run a small baseline: either a pure-Python or PyTorch matrix multiply, or a tiny Triton kernel if available. Measure wall-clock time and (if possible) memory bandwidth or utilization.
4. Write a short note in `results/baseline.md` that includes the config, the command you ran, the numbers, and one observation.

**Success criteria:** You have a committed `results/` note with reproducible numbers and full config. You can point to which path (NVIDIA local, AMD local + cloud later, or pure CPU) you are on.

## Estimated sessions

1. Tool installation and baseline measurement.

## Stretch goals

- Install and run a simple Nsight profile of a PyTorch operation (if NVIDIA).
- Compare CPU vs GPU (or iGPU) throughput on the same matrix size.

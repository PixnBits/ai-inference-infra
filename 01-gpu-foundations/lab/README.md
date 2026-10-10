# Lab stubs — Stage 1

This directory is for starter code or your own implementations.

## Suggested starting points

### Triton (recommended for most people; works across vendors)

Follow the official Triton matmul tutorial:
https://triton-lang.org/main/getting-started/tutorials/02-fused-softmax.html
(or the dedicated matmul example if present in the current docs).

A minimal skeleton you can paste into a file:

```python
import torch
import triton
import triton.language as tl

@triton.jit
def matmul_kernel(...):
    # implement or paste from tutorial
    pass

def matmul(a, b):
    # launch configuration
    pass

# Timing harness
a = torch.randn(1024, 1024, device='cuda' if torch.cuda.is_available() else 'cpu')
b = torch.randn(1024, 1024, device=a.device)
# time custom vs torch.matmul
```

### CUDA (NVIDIA only)

Start from any well-known "simple CUDA matmul" tutorial that uses shared memory tiling. Profile with `ncu` (Nsight Compute).

### CPU fallback

Implement a blocked matrix multiply in NumPy or pure Python and compare against `numpy.dot` or a BLAS call. Estimate effective bandwidth from the timing and the known memory traffic.

Place your working code and any small helper scripts here. Commit the source; keep large traces out of git.

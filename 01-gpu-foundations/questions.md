# Socratic prompts — Stage 1

## Prediction

1. Before you write or run the kernel, estimate the arithmetic intensity of a square matrix multiply of size N. At what N do you expect it to become compute-bound rather than bandwidth-bound on your GPU (or CPU)?
2. What do you expect the custom kernel to achieve relative to the library (cuBLAS / torch.matmul / BLAS): 10%? 50%? 90%? Why?

## Measurement

3. What was the actual achieved bandwidth or TFLOPS for the custom kernel versus the library? Cite the exact profiler metric or timing method.
4. Did tiling (or the Triton equivalent) move the bottleneck? Show the before/after numbers if you tried it.

## Reflection

5. In one sentence, what is the dominant reason your custom kernel is slower than the library? Is it algorithmic, occupancy, memory access pattern, or something else?
6. If you had only one hour to improve the custom kernel further, what single change would you try first, and what measurement would tell you it worked?

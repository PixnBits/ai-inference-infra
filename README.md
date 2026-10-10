# AI Inference Infrastructure Engineering (2026)

Self-study coursework for building practical expertise in LLM inference serving, optimization, and the underlying systems physics.

Wrappers are a commodity. Mastering the physics of scale — memory hierarchy, bandwidth, interconnect, batching, and scheduling — is not. This repository provides a progressive sequence of modules with concrete labs, measurement requirements, and Socratic prompts. It is designed for evening study after work, not a full-time academic load.

## Who this is for

Engineers who want hands-on experience with the systems that make modern inference fast, cheap, and reliable. Ideal if you already have some systems or ML engineering background and want to go deeper on the serving and optimization side. Training infrastructure is related but deliberately out of scope here.

## Time expectations

Each module is sized for one or two focused evening sessions (roughly 1.5–3 hours of actual work). The core path (Stages 1–6 + 11–12) can be completed over a few months at a sustainable pace. Distributed stages are optional extensions.

## How to use this repository

1. Work through a module's lab.
2. Commit your results, traces, and a short note explaining what you measured.
3. Open a conversation (e.g. with Grok) bringing the specific artefact: a trace, a surprising number, a prediction that failed, or a question about the arithmetic.
4. Use the module's `questions.md` prompts to structure reflection.

Progress is defined by reproducible experiments and the ability to explain the results, not by completing every stretch goal.

## Hardware notes

- Early stages (kernels, single-GPU serving, profiling) work well on a high-memory workstation or desktop with a modern GPU (or even CPU for some Triton work).
- Later stages that require multi-node or very large models can use short-lived cloud spot instances. Each module will note the cheapest practical approach.
- All labs should publish full hardware and software configuration with the results.

## Module outline

| Stage | Module | Focus | Core? |
|-------|--------|-------|-------|
| 0 | Setup & entry points | Environment, measurement tools, path selection | Yes |
| 1 | GPU Foundations | CUDA memory hierarchy, warps, custom kernels, Nsight | Yes |
| 2 | Inference Physics | Prefill/decode, arithmetic intensity, KV-cache, profiling | Yes |
| 3 | Serving Engines & Batching | vLLM, SGLang, PagedAttention, continuous/chunked batching | Yes |
| 4 | KV-Cache & Memory Hierarchy | Prefix caching, quantization, offloading, NVMe persistence | Yes |
| 5 | Quantization & Compression | FP8/MXFP/INT4, AWQ/GPTQ, PTQ vs QAT, trade-off measurement | Yes |
| 6 | Kernel Engineering | Triton, FlashAttention-style fusion, CUDA graphs | Yes |
| 7 | Distributed Inference | Tensor/pipeline/expert parallelism, communication overhead | Optional |
| 8 | Speculative Decoding | Draft-target, Medusa, acceptance rates | Optional |
| 9 | Multi-Node & Interconnects | NCCL, RDMA, InfiniBand, disaggregated prefill/decode | Optional |
| 10 | Orchestration & Scheduling | K8s GPU operators, Ray, Slurm, MIG, autoscaling, FinOps | Optional |
| 11 | Gateways, Routing & Cost | SLOs, semantic routing, DCGM/OTel, cost-per-completed-task | Yes |
| 12 | Public Teardowns | Reproducible benchmarks, Pareto curves, full disclosure | Yes |

## Repository structure

```
ai-inference-infra/
├── README.md                 # this file
├── 00-setup/
│   ├── README.md
│   ├── questions.md
│   └── ...
├── 01-gpu-foundations/
│   ├── README.md             # objectives, sources, time box, success criteria
│   ├── lab/                  # starter code or instructions
│   ├── questions.md          # prediction and reflection prompts
│   └── results/              # your traces and numbers (large files gitignored)
...
└── 12-teardown/
```

Each module README contains learning objectives, primary sources, lab description with success criteria, estimated sessions, and links to the Socratic prompts.

## Measurement standard

Every lab produces numbers, traces, or curves. Publish the full configuration. The ability to explain a discrepancy between prediction and measurement is the primary evidence of progress.

## License

Content is provided for personal self-study. Individual labs and results remain yours.

---

Start with `00-setup/` once it is populated, or jump to Stage 1 if your environment is already ready for CUDA/Nsight or Triton work.

# 05-quantization: Formats, Calibration, and Trade-offs

**Objectives**
- Compare FP16 / BF16, FP8, and INT4 (AWQ/GPTQ style) on the same model.
- Measure VRAM, latency, throughput, and a quality proxy (perplexity or sample outputs).
- Understand PTQ vs QAT at a high level and when calibration data matters.

**Time**: 1–2 evening sessions.

**Hardware notes**
Framework Desktop can run quantized models via Ollama, llama.cpp, or vLLM/SGLang with ROCm. Cloud NVIDIA for TensorRT-LLM or higher-precision comparisons if desired.

**Primary sources**
- AWQ and GPTQ papers
- vLLM / SGLang quantization docs
- TensorRT-LLM calibration notes (optional)

**Lab**
1. Load the same mid-size model (e.g. 7B–13B) in at least two precisions.
2. Measure peak VRAM, tokens/s, and TTFT under identical prompts.
3. Run a small quality check (fixed prompt set or perplexity on a short corpus).
4. Publish full config, the Pareto of quality vs. speed/memory, and one observation.

**Success criteria**
- Clear numbers showing the trade-off.
- Ability to recommend a precision for a given SLO and hardware budget.

# Socratic prompts — Stage 4

## Prediction

1. For a workload where every request starts with the same 2k-token system prompt, what fraction of the prefill work do you expect prefix caching to eliminate?
2. Where do you expect the next practical tier of the memory hierarchy to sit after GPU HBM for long-lived KV state?

## Measurement

3. What TTFT or latency reduction did you actually observe? Under what conditions did it disappear?
4. Did any offload or quantization change change the bottleneck from HBM bandwidth to something else?

## Reflection

5. Why is reused KV cache “free speed”?
6. For a multi-turn chat application with long histories, which single KV-cache technique would you implement first and why?

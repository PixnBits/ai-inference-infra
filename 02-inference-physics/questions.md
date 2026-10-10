# Socratic prompts — Stage 2

## Prediction

1. Which phase do you expect to be more compute-bound and which more bandwidth-bound? Why?
2. Roughly how much of the model's total memory do you expect the KV-cache to occupy for a 2k-token context on a 7B model?

## Measurement

3. What were your measured prefill time and decode time-per-token? How did they scale with prompt length?
4. From the profile, what was the single largest contributor to memory traffic during decode?

## Reflection

5. Why is most LLM inference described as memory-bound rather than compute-bound?
6. If you doubled available memory bandwidth, which phase would improve more, and by roughly what factor?

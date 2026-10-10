# Socratic prompts — Stage 6

## Prediction
1. For a modest sequence length, what fraction of runtime do you expect is Python/launch overhead versus kernel time?
2. Will fusion help more at small or large batch sizes?

## Measurement
3. What speedup did the fused kernel achieve? Cite the exact timing method.
4. Did the profiler show reduced kernel launches?

## Reflection
5. In one sentence, when is fusion worth the engineering effort?
6. What single additional fusion would you try next, and how would you know it worked?

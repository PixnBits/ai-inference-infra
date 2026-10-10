# Socratic prompts — Stage 0

Use these before and after the lab. Bring the surprising or unclear ones into a conversation with an artefact (the numbers or the error).

## Prediction

1. Before you measure, what do you expect will be the limiting factor for a large matrix multiply on your machine: compute, memory bandwidth, or something else? Why?
2. If you are on AMD hardware without full CUDA, what is the highest-leverage first experiment you can still run locally?

## Measurement

3. What exact numbers did you record? How would someone else reproduce them from your note?
4. Did the result match your prediction? If not, what changed your mental model?

## Reflection

5. Which entry path (systems-first CUDA/Triton kernels vs ML-first serving stacks + later kernels) feels more natural given your current tools and time constraints? What is the first module that will actually test that choice?
6. What is one piece of configuration (driver, library version, power limit, etc.) that you now know matters and would have been invisible without measuring?

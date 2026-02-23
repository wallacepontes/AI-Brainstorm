# LayerNorm vs RMSNorm

## Table of Contents

- [LayerNorm vs RMSNorm](#layernorm-vs-rmsnorm)
  - [Table of Contents](#table-of-contents)
  - [What Is RMSNorm and Why Is It So Popular Now?](#what-is-rmsnorm-and-why-is-it-so-popular-now)
  - [Videos](#videos)
  - [References](#references)

## What Is RMSNorm and Why Is It So Popular Now?

**RMSNorm** (Root Mean Square Layer Normalization) is described as a specific architectural "tweak" that has largely replaced the traditional **LayerNorm** in modern Large Language Models, such as `gpt-oss-120b`. 

Key insights regarding RMSNorm from the experts include:

- **Evolutionary Tweak:** It is characterized as a minor refinement rather than a fundamental shift in AI technology. The experts compare this change to swapping one nonlinear activation function for another (like sigmoid for ReLU), which does not change the network's core structure.
- **Performance Gains:** Moving or adjusting normalization layers like RMSNorm is a common strategy used by researchers to achieve specific **performance gains**. 
- **Transformer Lineage:** Despite these updates, models using RMSNorm are still considered part of the same "lineage" as older architectures like GPT-2. It is viewed as one of the "little knobs" that researchers tune to optimize a model's efficiency.

While it is a standard component in frontier models today, the sources emphasize that its implementation is part of a broader trend of making **systematic, incremental improvements** to the transformer block rather than inventing entirely new paradigms.

## Videos

 * [LayerNorm vs RMSNorm: The Visual Guide](https://www.youtube.com/watch?v=57kd8l6Wp-4)
	> [<img src="https://img.youtube.com/vi/57kd8l6Wp-4/0.jpg" width="200">](https://www.youtube.com/watch?v=57kd8l6Wp-4 "Why do modern LLMs like LLaMA use RMSNorm while Computer Vision models stick to LayerNorm? The answer lies in how they handle information. by Xiaol.x 55 views 2 minutes, 01 seconds")
 
 * [What Is RMSNorm and Why Is It So Popular Now?](https://www.youtube.com/watch?v=r3O76I79YkE)
	> [<img src="https://img.youtube.com/vi/r3O76I79YkE/0.jpg" width="200">](https://www.youtube.com/watch?v=r3O76I79YkE "RMS Norm, a powerful normalization technique gaining popularity in state-of-the-art transformer models like LLaMA. We explore how RMS Norm works, why it’s more efficient than traditional LayerNorm, and why it's becoming the go-to for stabilizing model training. by Abheeshth 952 views 4 minutes, 22 seconds")

## References

1. https://docs.pytorch.org/docs/stable/generated/torch.nn.modules.normalization.RMSNorm.html
2. https://2020machinelearning.medium.com/deep-dive-into-deep-learning-layers-rmsnorm-and-batch-normalization-b2423552be9f
3. 

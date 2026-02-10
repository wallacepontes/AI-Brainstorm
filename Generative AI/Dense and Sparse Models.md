# Dense and Sparse Models

## Table of Contents

- [Dense and Sparse Models](#dense-and-sparse-models)
  - [Table of Contents](#table-of-contents)
  - [Dense Models](#dense-models)
    - [Key Aspects of Dense Models](#key-aspects-of-dense-models)
    - [Dense vs. Mixture of Experts (MoE)](#dense-vs-mixture-of-experts-moe)
    - [Performance Examples](#performance-examples)
  - [Sparse Models](#sparse-models)
    - [Key aspects of sparse models include: ](#key-aspects-of-sparse-models-include)
  - [What is the difference between dense and sparse models?](#what-is-the-difference-between-dense-and-sparse-models)
  - [Videos](#videos)
  - [References](#references)

## Dense Models

Dense models are neural networks where every neuron in a layer connects to every neuron in the next, ensuring all parameters are active for every input. Unlike sparse or Mixture-of-Experts (MoE) models, they utilize their entire capacity for each calculation, providing high, well-understood accuracy but with higher computational costs. Examples include LLaMA-2 13B and Gemma 3. 

### Key Aspects of Dense Models

- Structure: Dense layers (fully connected) calculate output as \(Output=activation(dot(input,kernel)+bias)\), creating a dense web of parameters.
- Performance: They often yield higher accuracy for their total parameter count compared to sparse models, making them efficient in I/O-bounded scenarios.
- Drawbacks: They are computationally expensive to train and run, as all parameters are active during every forward pass.
- Application: Commonly used in the final layers of neural networks for classification or for smaller, specialized, and open-source models.

### Dense vs. Mixture of Experts (MoE)

- Dense Models: Use all parameters for every token, offering consistent performance.
- MoE Models: Activate only a subset of parameters, reducing computation but increasing memory demands for storing the larger, inactive model.
- Efficiency: While MoE models can be 2-4x more computationally efficient, dense models are often easier to train and faster in scenarios where memory is limited.

### Performance Examples

- LLaMA-2 13B (Dense): Achieved an average accuracy of 71.76, while a 70% active, sparse version dropped to 68.26.
- Qwen-2.5 14B (Dense): Achieved 75.74 accuracy, with significant degradation when compressed.
- Hybrid Approach: Newer models, such as Snowflake Arctic, use a 10B Dense transformer combined with a 128x3.36B MoE component, achieving higher efficiency and better performance than purely dense models like Llama3-8B.

## Sparse Models

Sparse models are machine learning, statistical, or signal processing frameworks that enforce many parameters to be zero, resulting in a model with high interpretability, increased computational efficiency, and improved generalization in high-dimensional settings. They are widely used to reduce memory/compute consumption in AI (e.g., in Mixture of Experts) by activating only a subset of network parameters per input, or in statistics via techniques like the lasso. 

### Key aspects of sparse models include: 

- Mathematical Foundation: They utilize penalties such as the \(\ell _{1}\) norm (lasso), group penalties, and non-convex surrogates to shrink unimportant parameters to zero.
- Applications: Common in high-dimensional data scenarios like genomics, neuroimaging, computer vision, and natural language processing (NLP).
- Efficiency & AI: Sparse models enable faster, more energy-efficient AI, particularly useful for mobile devices, and are used in technologies like neural network pruning.
- Mixture of Experts (MoE): In deep learning, MoE models use sparse activation, where only a few expert networks are activated for each input token, enabling massive parameter counts (e.g., Switch Transformers).
- Types: These include sparse regression (lasso), sparse dictionary learning, and sparse neural networks. 

By concentrating on a small number of non-zero parameters, these models, such as sparse vectors, are particularly effective in keyword-based lexical search and in scenarios where data is limited. 

## What is the difference between dense and sparse models?

A dense layer (or fully connected layer) connects every neuron in one layer to every neuron in the next layer, creating a high number of parameters. In contrast, a sparse layer intentionally limits these connections, allowing only a subset of neurons to link to the next layer.

## Videos

 * [Sparse Expert Models (Switch Transformers, GLAM, and more... w/ the Authors)](https://www.youtube.com/watch?v=ccBMRryxGog)
	> [<img src="https://img.youtube.com/vi/ccBMRryxGog/0.jpg" width="200">](https://www.youtube.com/watch?v=ccBMRryxGog "This video is an interview with Barret Zoph and William Fedus of Google Brain about Sparse Expert Models. by Umar Jamil 650,433 views 58 minutes, 03 seconds")

 * [Sparse Models vs Dense Models Smarter, Faster AI](https://www.youtube.com/watch?v=R93QMegF89Y)
	> [<img src="https://img.youtube.com/vi/R93QMegF89Y/0.jpg" width="200">](https://www.youtube.com/watch?v=R93QMegF89Y " Sparse Models vs Dense Models — where smarter design can beat sheer size. by Durga Software Solutions 40 views 5 minutes, 16 seconds")

## References

1. Sparse Models for Machine Learning: https://arxiv.org/abs/2308.13960
2. https://milvus.io/ai-quick-reference/what-is-the-difference-between-dense-and-sparse-layers
3. https://hacarus.com/tech/using-sparse-modeling-in-ai-a-human-centric-explainable-approach/

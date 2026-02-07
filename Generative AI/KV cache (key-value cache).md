# KV cache (key-value cache)

## Table of Contents

- [KV cache (key-value cache)](#kv-cache-key-value-cache)
  - [Table of Contents](#table-of-contents)
  - [KV cache](#kv-cache)
    - [Key Aspects of KV Cache:](#key-aspects-of-kv-cache)
  - [Videos](#videos)
  - [References](#references)

## KV cache

KV cache (key-value cache) is a crucial inference-time optimization for Large Language Models (LLMs) that stores intermediate attention keys and values to avoid recomputing them for previously generated tokens. It significantly reduces latency during token-by-token generation (decoding) by replacing expensive matrix multiplications with memory lookups. 

### Key Aspects of KV Cache:

- Purpose: Accelerates inference in Transformer models by avoiding quadratic growth in computation.
- Mechanism: When generating a new token, the model needs to compute self-attention for all preceding tokens. Instead of recomputing Key (\(K\)) and Value (\(V\)) vectors, the system retrieves them from memory.
- Memory Trade-off: While it reduces computational latency, KV cache grows with sequence length and batch size, potentially exhausting GPU memory.
- Optimization Techniques: Methods to manage large KV cache sizes include quantization, eviction (removing less important tokens), and prefix caching (reusing prompts across conversations).
- Implementation: It is widely used in AI frameworks for applications like chatbots, enabling efficient long-context generation.

## Videos

 * [KV Cache Crash Course](https://www.youtube.com/watch?v=SLYUBsZE72E)
	> [<img src="https://img.youtube.com/vi/SLYUBsZE72E/0.jpg" width="200">](https://www.youtube.com/watch?v=SLYUBsZE72E "KV Cache Explained: The Secret to 10x Faster AI Text Generation! by AI Anytime 3.2K views 33 minutes, 59 seconds")

 * [KV Cache Demystified: Speeding Up Large Language Models](https://www.youtube.com/watch?v=RGC-azaTXsI)
	> [<img src="https://img.youtube.com/vi/RGC-azaTXsI/0.jpg" width="200">](https://www.youtube.com/watch?v=RGC-azaTXsI "Ever wondered how large language models like GPT respond so fast without recomputing everything from scratch? by Under The Hood 394 views 9 minutes, 20 seconds")

 * [KV Cache: The Trick That Makes LLMs Faster](https://www.youtube.com/watch?v=gpp57x_z_Jg)
	> [<img src="https://img.youtube.com/vi/gpp57x_z_Jg/0.jpg" width="200">](https://www.youtube.com/watch?v=gpp57x_z_Jg "In this deep dive, we'll explain how every modern Large Language Model, from LLaMA to GPT-4, uses the KV Cache to make real-time inference possible. We break down the problem of quadratic complexity in the attention mechanism and show how caching the Key (K) and Value (V) matrices turns an impossibly slow process into a blazingly fast one. by Tales Of Tensors 5.1K views 4 minutes, 56 seconds")

## References

1. https://magazine.sebastianraschka.com/p/coding-the-kv-cache-in-llms
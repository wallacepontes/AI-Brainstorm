# Sliding Window Attention (SWA)

## Table of Contents

- [Sliding Window Attention (SWA)](#sliding-window-attention-swa)
  - [Table of Contents](#table-of-contents)
  - [Course: Sliding Window Attention (SWA)](#course-sliding-window-attention-swa)
    - [Key Aspects of Sliding Window Attention](#key-aspects-of-sliding-window-attention)
    - [Applications and Models](#applications-and-models)
    - [Comparison with Standard Attention](#comparison-with-standard-attention)
  - [Videos](#videos)
  - [References](#references)

## Course: Sliding Window Attention (SWA)

Sliding Window Attention (SWA) is a, efficient transformer mechanism that reduces computational complexity from quadratic (\(O(N^{2})\)) to linear (\(O(N\times W)\)) by restricting each token's attention to a local, fixed-size window of neighboring tokens. It enables processing long sequences while reducing memory usage and accelerating inference, often used in models like Longformer and Mistral. 

This video explains the concept of sliding window attention and its benefits:
56sCodeLuckyYouTube • Jan 8, 2026

### Key Aspects of Sliding Window Attention

- Linear Complexity: Unlike standard attention, which computes \(N\times N\) relationships, SWA restricts calculations to \(N\times W\) (window size), allowing for much longer contexts.
- Local Context Propagation: Although each layer only sees a local window, deeper layers allow information from earlier tokens to propagate further, creating a larger, effective global context.
- Reduced Memory Usage: SWA drastically reduces the number of operations, easing the out-of-memory (OOM) errors that often occur with long input sequences.
- Hardware Efficiency: SWA is designed for efficient computation on GPUs, enhancing overall model throughput.

### Applications and Models

- Mistral: Uses SWA to achieve higher throughput and handle longer sequences.
- Longformer: Employs a combination of sliding window and global attention.
- Long-Context LLMs: SWA is utilized to scale transformer models for long-document understanding and generation.

### Comparison with Standard Attention

- Standard Attention (Global): \(O(N^{2})\) complexity; high memory usage.
- Sliding Window Attention: \(O(N\times W)\) complexity; low, linear memory usage.

## Videos

 * [Sliding Window Technique Explained - Algorithm Tutorial for Beginners](https://www.youtube.com/watch?v=a8GvJ2Ckttk)
	> [<img src="https://img.youtube.com/vi/a8GvJ2Ckttk/0.jpg" width="200">](https://www.youtube.com/watch?v=a8GvJ2Ckttk "Master the Sliding Window technique for coding interviews! by CodeLucky 25 views 2 minutes, 48 seconds")

## References

1. https://arxiv.org/abs/2502.18845
2. https://medium.com/@manojkumal/sliding-window-attention-565f963a1ffd
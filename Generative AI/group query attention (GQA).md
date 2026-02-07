# Group Query Attention

## Table of Contents

- [Group Query Attention](#group-query-attention)
  - [Table of Contents](#table-of-contents)
  - [Grouped-Query Attention (GQA)](#grouped-query-attention-gqa)
    - [Key Aspects of Grouped-Query Attention (GQA):](#key-aspects-of-grouped-query-attention-gqa)
    - [Structure of GQA:](#structure-of-gqa)
  - [Videos](#videos)
  - [References](#references)

## Grouped-Query Attention (GQA)

Grouped-Query Attention (GQA) is an efficient attention mechanism for LLMs that balances Multi-Head Attention (MHA) quality with Multi-Query Attention (MQA) speed. It divides query heads into \(G\) groups, with each group sharing a single key and value head, significantly reducing KV cache size and improving inference throughput with minimal performance loss. Used in models like Llama 2 70B and Mistral 7B, GQA enables faster, more memory-efficient decoding. 

This video explains the concept of KV cache and how it relates to attention mechanisms:

### Key Aspects of Grouped-Query Attention (GQA):

- Mechanism: GQA organizes attention by partitioning query heads (\(Q\)) into groups, where each group shares a single key (\(K\)) and value (\(V\)) head.
- Efficiency Gains: By reducing the number of key-value heads, GQA drastically lowers the memory bandwidth requirements for the KV cache during inference. This allows for larger batch sizes and higher throughput.
- Position in the Spectrum: 
  - MHA (Multi-Head Attention): Each query head has its own key/value head (highest quality, lowest speed).
  - GQA (Grouped-Query Attention): Intermediate approach (balanced quality and speed).
  - MQA (Multi-Query Attention): All query heads share a single key/value head (lowest quality, highest speed).
- Performance: GQA provides performance nearly equal to MHA while achieving inference speeds closer to MQA.
- Applications: It is widely adopted in modern large language models, including Llama 2 70B and Mistral 7B. 

### Structure of GQA:

- Groups (\(G\)): The number of groups of query heads.
- Key/Value Heads (\(KV\)): Number of KV heads, which is less than the number of query heads (\(Q\)) but more than one.
- Operation: For each group, the model computes dot products between queries and shared keys, then multiplies these weights by the shared value vectors.

## Videos

 * [LLM Optimization Lecture 4: Grouped Query Attention, Paged Attention, Flash Attention](https://www.youtube.com/watch?v=Myhz-whrq5Q)
	> [<img src="https://img.youtube.com/vi/Myhz-whrq5Q/0.jpg" width="200">](https://www.youtube.com/watch?v=Myhz-whrq5Q "Ever wondered how large language models like GPT respond so fast without recomputing everything from scratch? by Faradawn Yang 6677 views 43 minutes, 47 seconds")

## References
# The Big LLM Architecture Comparison

This presentation provides a technical comparison of prominent large language model (LLM) architectures released in 2024 and 2025, emphasizing how they evolve from the original GPT design. The author details specific innovations such as multi-head latent attention (MLA) and mixture-of-experts (MoE), which enhance efficiency by reducing memory costs during inference. By examining models like DeepSeek, Llama, and Qwen, the text illustrates a broader industry trend toward optimizing KV caching and refining normalization layer placement to stabilize training. Detailed ablation studies from models like OLMo 2 and Gemma 3 are used to justify design choices like sliding window attention and QK normalization. Ultimately, the source argues that while training data remains a primary differentiator, subtle architectural tweaks allow modern models to achieve superior performance on smaller hardware. The overview concludes by connecting these structural concepts to practical PyTorch implementations and the development of specialized reasoning models.

---

## Table of Contents

- [The Big LLM Architecture Comparison](#the-big-llm-architecture-comparison)
  - [Table of Contents](#table-of-contents)
  - [**Course: The Big LLM Architecture Comparison**](#course-the-big-llm-architecture-comparison)
    - [**Module 1: DeepSeek V3/R1**](#module-1-deepseek-v3r1)
    - [**Module 2: OLMo 2**](#module-2-olmo-2)
    - [**Module 3: Gemma 3**](#module-3-gemma-3)
    - [**Module 4: Mistral Small 3.1**](#module-4-mistral-small-31)
    - [**Module 5: Llama 4**](#module-5-llama-4)
    - [**Module 6: Qwen3**](#module-6-qwen3)
    - [**Module 7: SmolLM3**](#module-7-smollm3)
    - [**Module 8: Kimi 2**](#module-8-kimi-2)
    - [**Module 9: GPT-OSS**](#module-9-gpt-oss)
    - [**Module 10: Grok 2.5**](#module-10-grok-25)
    - [**Module 11: GLM-4.5**](#module-11-glm-45)
    - [**Conclusion:**](#conclusion)
  - [Videos](#videos)
  - [References](#references)

---

## **Course: The Big LLM Architecture Comparison**

This presentation provides a comprehensive technical overview of the evolving landscape of Large Language Model (LLM) architectures as of 2025.

---

### **Module 1: DeepSeek V3/R1**

- **Context:** DeepSeek V3 serves as the base model, while R1 is the **reasoning-focused variant** that gained significant popularity in early 2025.
- **Multi-head Latent Attention (MLA):** This hallmark component reduces memory usage by introducing a **compressed key and value state** during inference. While it requires extra matrix multiplications to project data back to its original dimension, it significantly decreases the KV cache size compared to traditional Multi-head Attention (MHA).
- **Mixture of Experts (MoE):** The model features 256 experts, but only a subset (8 experts plus one shared expert) is activated per token. This allows for a massive 671 billion parameter capacity while maintaining a manageable **37 billion active parameters** during inference.

### **Module 2: OLMo 2**

- **Transparency:** OLMo 2 is noted for its highly detailed technical reports and open training data processes.
- **Normalization Placement:** Unlike traditional "pre-norm" or "post-norm" setups, OLMo 2 places the **RMS Norm inside the residual block**. This unique "flavor of post-norm" was found to result in smoother gradients and fewer loss spikes during training compared to standard pre-norm configurations.
- **QK Norm:** The architecture also implements **Query-Key (QK) normalization** to further stabilize the attention mechanism.

### **Module 3: Gemma 3**

- **Sliding Window Attention (SWA):** To optimize memory, Gemma 3 utilizes a **5:1 ratio** of local (sliding window) to global attention blocks. The local window is typically set to 1,024 tokens, looking only at immediate surrounding context to save on KV cache costs.
- **Redundant Normalization:** Gemma 3 employs an extensive normalization strategy, including **both pre-norm and post-norm** placements (with the post-norm inside residuals), along with QK norm, to ensure maximum training stability.

### **Module 4: Mistral Small 3.1**

- **Design Philosophy:** Compared to Gemma 3, Mistral 3.1 Small (24B) is a **wider but shallower architecture**. It features 40 transformer blocks whereas Gemma 3 uses 62.
- **Inference Speed:** The fewer number of layers is a deliberate choice to enhance **tokens-per-second** performance, as transformer blocks must be computed sequentially.
- **Attention:** While previous Mistral models used sliding window attention, it is disabled by default in the 3.1 Small model weights.

### **Module 5: Llama 4**

- **Maverick Architecture:** The 400B parameter Maverick model uses a different MoE approach than DeepSeek, favoring **fewer but much larger experts**.
- **Active Parameters:** It activates only two experts per step (one shared and one regular), resulting in roughly 70 billion active parameters.

### **Module 6: Qwen3**

- **Deep Architecture:** Qwen 3 models are generally **deeper and slimmer** than their Llama counterparts. For example, the 6B model has 28 blocks compared to Llama 3.2 1B's 16 blocks.
- **MoE Variation:** Unlike DeepSeek or Kimi, Qwen 3’s mixture of experts variant **does not use a shared expert**, which is an unusual architectural choice.
- **Hybrid Nature:** It can function as both a standard instruction model and a reasoning model via a specific "think" token.

### **Module 7: SmolLM3**

- **NOPE (No Positional Embeddings):** This model experiments with a technique called NOPE, where **every fourth layer lacks positional information**.
- **Length Generalization:** The use of NOPE alongside Rotary Positional Embeddings (RoPE) is intended to help the model generalize better to sequences longer than those seen during training.

### **Module 8: Kimi 2**

- **Muon Optimizer:** Kimi 2 is notable for moving away from the industry-standard AdamW optimizer in favor of **Muon**, which produced a significantly steeper and smoother loss curve.
- **Expert Efficiency:** Despite having 1 trillion total parameters, architectural optimizations allow it to run with only **32 billion active parameters**, making it more efficient in inference than the smaller DeepSeek V3.

### **Module 9: GPT-OSS**

- **Tool-Use Optimization:** This model was specifically trained with **function calling** in mind, designed to trigger web searches or code execution for complex queries.
- **Architectural Outlier:** It retains the use of **bias vectors** in linear layers, a practice largely abandoned by other modern LLMs. It also features "hourglass" shaped layers where the intermediate representation is smaller than the input, rather than the standard up-projection.

### **Module 10: Grok 2.5**

- **Shared Expert Implementation:** Grok 2.5 uses an additional residual path with a dense feed-forward layer that is **always active**. This effectively functions as a large shared expert for the model.
- **Barrel Shape:** The model follows an "older" standard of feed-forward design (small to wide to small) rather than the shrinking "hourglass" trend seen in models like Qwen 3.

### **Module 11: GLM-4.5**

- **Depth and Stability:** GLM-4.5 is an exceptionally deep model with **92 transformer blocks**.
- **Hybrid Blocks:** Similar to DeepSeek, it uses **dense feed-forward layers in the first three blocks** to provide training stability before transitioning to MoE blocks for the remainder of the architecture.

---

### **Conclusion:**

While the **Transformer architecture remains robust**, 2025 models show a clear trend toward **fine-grained experts**, specialized **normalization placements** to stabilize deep networks, and novel **KV cache compression** techniques like MLA and SWA.

---

## Videos

 * [The Big LLM Architecture Comparison](https://www.youtube.com/watch?v=rNlULI-zGcw)
	> [<img src="https://img.youtube.com/vi/rNlULI-zGcw/0.jpg" width="200">](https://www.youtube.com/watch?v=rNlULI-zGcw "This video covers the most important open-weight LLM architectures released in 2025, along with their architectural design decisions. by Sebastian Raschka 34,992 views 1 hour 26 minutes, 36 seconds")

## References

1. https://magazine.sebastianraschka.com/p/the-big-llm-architecture-comparison
2. https://github.com/rasbt/LLMs-from-scratch
3. https://www.manning.com/books/build-a-reasoning-model-from-scratch?utm_source=raschka&utm_medium=affiliate&utm_campaign=book_raschka2&a_aid=raschka&a_bid=4c3c5398&chan=mm_website
4. 

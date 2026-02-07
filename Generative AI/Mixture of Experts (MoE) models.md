# Mixture of Experts (MoE) models

Drawing from the sources, here is a detailed presentation on Mixture of Experts (MoE) models, organized according to the relevant course contents.

## Table of Contents

- [Mixture of Experts (MoE) models](#mixture-of-experts-moe-models)
  - [Table of Contents](#table-of-contents)
  - [Course Module: Mixture of Experts (MoE) Models](#course-module-mixture-of-experts-moe-models)
    - [**China vs US: Who wins the AI race? (1:57)**](#china-vs-us-who-wins-the-ai-race-157)
    - [**Transformers: Evolution of LLMs since 2019 (40:08)**](#transformers-evolution-of-llms-since-2019-4008)
    - [**How AI is Trained: Pre-training \& Architecture (1:04:12)**](#how-ai-is-trained-pre-training--architecture-10412)
    - [**AI Scaling Laws \& Future Compute (48:05 \& 4:00:10)**](#ai-scaling-laws--future-compute-4805--40010)
    - [**Summary of MoE Advantages vs. Challenges**](#summary-of-moe-advantages-vs-challenges)
    - [Key Aspects of MoE Models](#key-aspects-of-moe-models)
    - [Examples of Modern MoE Models](#examples-of-modern-moe-models)
    - [Advantages and Challenges](#advantages-and-challenges)
  - [Video](#video)
  - [References](#references)

---

## Course Module: Mixture of Experts (MoE) Models

Mixture of Experts (MoE) is a neural network architecture. It enhances AI efficiency by dividing a large model into smaller, specialized sub-networks called "experts". MoE models use a router, or gating network. This router selects only the most relevant experts for a given task. This enables faster inference and lower computational costs. This is true despite having billions or trillions of parameters. 

![Maarten Grootendorst](MoEs.png)

---

### **China vs US: Who wins the AI race? (1:57)**

- **The Chinese Advantage:** Chinese open-weight models, such as those from **DeepSeek and Qwen**, tend to be much larger and utilize **MoE architectures** to achieve higher peak performance.
- **Strategic Use:** While US labs have historically focused on smaller dense models, Chinese labs have used MoE to "leapfrog" competitors, offering **frontier-level performance** with high efficiency.

---

### **Transformers: Evolution of LLMs since 2019 (40:08)**

- **From Dense to Sparse:** MoE is a primary architectural tweak to the standard transformer. While "dense" models use every parameter for every token, MoE is **"sparse,"** meaning only a fraction of the model is active at any given time.
- **The MoE Tweak:** It is a method to **increase the model's size (parameter count)** without proportionally increasing the **compute cost** for each forward pass.
- **Historical Lineage:** Though popularized recently by models like DeepSeek, the MoE layer is several years old and is considered a "lineage" descendant of the original GPT-2 architecture.

---

### **How AI is Trained: Pre-training & Architecture (1:04:12)**

- **The Router and Experts:** In an MoE model, the standard fully connected layer is replaced by multiple **feedforward networks (experts)**. A **router** decides which expert is most useful for a specific input token.
- **Fuzzy Specialization:** While a router might send math-heavy tokens to a "math expert" and Spanish text to a "translation expert," the specialization is often **fuzzy** rather than strictly defined.
- **Packing Knowledge:** This architecture allows the model to **pack more knowledge** into its weights without making token generation wastefully expensive.

---

### **AI Scaling Laws & Future Compute (48:05 & 4:00:10)**

- **Efficient Generation:** The **sparse nature** of MoE models makes them significantly more efficient for **token generation**. 
- **Future Scaling:** As compute clusters scale to the gigawatt level, the industry is moving toward even larger MoE structures. NVIDIA and other startups have teased MoE models in the **400 billion parameter range** for early 2026.
- **Hardware Alignment:** The high throughput requirements of MoE models are driving hardware innovations, such as optimizations for **FP4 and FP8** to increase training speed and reduce memory overhead.

---

### **Summary of MoE Advantages vs. Challenges**

- **Advantage:** Allows for **unrestricted model growth** while keeping the "cost per token" manageable.
- **Advantage:** Better suited for **long-context and agentic tasks** due to generation efficiency.
- **Challenge:** MoE models are **harder to train** than dense models; issues like "expert collapse" (where the router fails to utilize all experts) can occur.
- **Challenge:** They require **complex infrastructure** to shard parameters across multiple GPUs, making them difficult for smaller academic labs to build from scratch.

### Key Aspects of MoE Models

- **Sparse Activation**: MoE models are "sparse." This means only a small subset of the network's components are active at any time. This differs from "dense" models that use all parameters for every calculation.
- **Architecture**: MoE replaces traditional dense feed-forward network (FFN) layers. It does this with specialized MoE layers containing multiple expert FFNs.
- **Routing Mechanism**: A trainable gate network decides which experts handle which token. This specializes them in different types of data or tasks.
- **Efficiency**: MoE models offer superior pretraining efficiency. They allow for larger models without a proportional increase in training time or inference cost.

### Examples of Modern MoE Models

Many advanced AI models currently use MoE architectures, including:

- **Mistral AI**: Mixtral 8x7B and Mistral Large 3.
- **DeepSeek**: DeepSeek-V2, V3, and R1.
- Google: Gemini 1.5 and GLaM.
- Other Examples: Grok-1, DBRX, and Jamba.

### Advantages and Challenges

- Advantages: MoE models have significantly lower computation costs, up to 70% less. They also offer faster training and better handling of large-scale, complex data.
- Challenges: There is increased complexity in training, for example, load balancing. There is also higher memory usage due to needing to load all experts. Finally, there can be potential bottlenecks in communication. 

## Video

 * [A Visual Guide to Mixture of Experts (MoE) in LLMs](https://www.youtube.com/watch?v=sOPDGQjFcuM)
	> [<img src="https://img.youtube.com/vi/sOPDGQjFcuM/0.jpg" width="200">](https://www.youtube.com/watch?v=sOPDGQjFcuM "In this highly visual guide, we explore the architecture of a Mixture of Experts in Large Language Models (LLM) and Vision Language Models. by Maarten Grootendorst 49,428 views 19 minutes, 43 seconds")

 * [What is Mixture of Experts?](https://www.youtube.com/watch?v=sYDlVVyJYn4)
	> [<img src="https://img.youtube.com/vi/sYDlVVyJYn4/0.jpg" width="200">](https://www.youtube.com/watch?v=sYDlVVyJYn4 "In this video, Master Inventor Martin Keen explains the concept of Mixture of Experts (MoE), a machine learning approach that divides an AI model into separate subnetworks or experts, each focusing on a subset of the input data. Martin discusses the architecture, advantages, and challenges of MoE, including sparse layers, routing, and load balancing. by IBM Technology 49,329 views 7 minutes, 57 seconds")

## References

1. https://newsletter.maartengrootendorst.com/p/a-visual-guide-to-mixture-of-experts
2. https://magazine.sebastianraschka.com/p/the-big-llm-architecture-comparison
# Open Source vs Closed Source vs Open Weights LLMs

## Table of Contents

- [Open Source vs Closed Source vs Open Weights LLMs](#open-source-vs-closed-source-vs-open-weights-llms)
  - [Table of Contents](#table-of-contents)
  - [The sources distinguish](#the-sources-distinguish)
    - [**Distinguishing the Models**](#distinguishing-the-models)
    - [**The Paradox of Open Weights vs. Closed Source**](#the-paradox-of-open-weights-vs-closed-source)
    - [**Why Companies Release Open Weights**](#why-companies-release-open-weights)
    - [Key Differences](#key-differences)
    - [Decision Factors](#decision-factors)
  - [Open Weight vs Open Source Models](#open-weight-vs-open-source-models)
    - [Open Weights](#open-weights)
  - [Videos](#videos)
  - [References](#references)

## The sources distinguish

Large Language Models (LLMs) are categorized by accessibility: Closed Source (e.g., GPT-4) offers top performance via API but no transparency or control. Open Source (rare) provides full code/data, allowing complete customization. Open Weights (e.g., Llama 3) releases only model parameters, allowing local hosting and tuning, striking a balance between control and ease of use. 

The sources distinguish between **open-weight**, **fully open-source**, and **closed-source** (proprietary) models, noting that the AI landscape has shifted significantly with the rise of high-performance open-weight models from labs like DeepSeek.

### **Distinguishing the Models**

- **Closed Source (Proprietary):** Models like **ChatGPT, Gemini, and Claude** are developed by "closed labs" and are primarily accessed through paid API subscriptions or consumer platforms. These companies prioritize a "flywheel" effect—using their massive user bases and brand recognition to stay ahead. Users currently pay for these models because they offer a "marginal intelligence gain" over open alternatives.
- **Open Weights:** This refers to models where the final parameters (the weights) are released for public download and local use, such as **DeepSeek R1, Llama, or Mistral**. While you can run these models on your own hardware, the training data and full codebase used to create them are not always provided. 
- **Truly Open Source:** A "fully open" model, such as the Allen Institute for AI's **OLMo**, releases the **weights, training code, and the underlying data**. This allows researchers to understand exactly how the model was built and to replicate the training process.

### **The Paradox of Open Weights vs. Closed Source**

The "paradox" lies in the fact that many models marketed as "open" are actually only **open weights** with restrictive licenses, effectively keeping the most valuable parts of the "source" (the training data and methodology) closed. 

- **Licensing "Strings":** Models like Meta's **Llama** or Google's **Gemma** are free to use but come with "strings attached," such as requirements to report financial status to the developer if user counts exceed a certain threshold (e.g., 700 million users). 
- **Transparency Gaps:** Even when a model is open-weight, the organization behind it may remain secretive. For instance, while DeepSeek releases detailed technical reports, the company itself is described as "secretive," and researchers often have to reverse-engineer specific components—like position embeddings or scaling factors—to truly understand how they work.
- **Unrestricted Chinese Models:** In contrast to US "open weights," Chinese companies often use more **unrestricted open-source licenses**. They do this strategically to influence the international market and bypass security concerns that prevent US companies from paying for Chinese API subscriptions.

### **Why Companies Release Open Weights**

- **GPU Efficiency:** OpenAI released its first open-weight model in years, **`gpt-oss-120b`**, partly because they are "GPU deprived" and want distribution without the recurring cost of serving tokens to millions of users on their own hardware.
- **Market Influence:** Open weights allow labs to gain "mindshare" and take part in the growing AI expenditure market.
- **Customization:** Releasing weights allows third-party companies to customize and "post-train" models for specialized fields like **law or medicine**, which would be impossible with a locked API.

### Key Differences

- Closed Source (Proprietary):
  - Pros: Best-in-class performance, no infrastructure, high security, supported by vendors.
  - Cons: High cost, data privacy concerns, vendor lock-in.
  - Examples: GPT-4, Claude, Gemini.
- Open Source:
  - Pros: Total transparency, no licensing fees, full control, high customization.
  - Cons: Requires high technical expertise, expensive infrastructure, lower out-of-the-box accuracy.
- Open Weights:
  - Pros: High flexibility to customize/fine-tune, improved privacy, faster innovation, cheaper than training.
  - Cons: Lack of training code or data transparency, often not truly "open" by OSI standards.
  - Examples: Llama 3, Mistral 7B.

### Decision Factors

- Go Closed for speed, ease, and highest performance (e.g., chatbots, rapid prototyping).
- Go Open Weights/Source for data privacy, customization, and cost-efficiency at scale (e.g., proprietary apps, specialized tasks).

## Open Weight vs Open Source Models

Although the two concepts are often confused, there are significant differences between them. An open-weight model makes the trained model parameters publicly available, allowing anyone to download and use them directly, making it easy to get started. However, the underlying code and complete training details are not disclosed. While you can use and fine-tune the model to a certain extent, fully understanding it or making major architectural changes is more difficult. Meta's Llama 3 is an example of an open-weight model. Open-source models are more thoroughly open, with both the code and weights publicly available, often accompanied by training procedures, data processing methods, and evaluation scripts. This allows others to not only use the model but also modify, reproduce, and verify it, allowing the community to collaborate on optimizing it. Open-source models are more suitable for those who enjoy in-depth research, customize the model to meet specific needs, or face compliance audits. LLava, developed by the University of California, Berkeley, is an example of an open-source model. Simply put, open-weight models are like giving you a pre-installed machine, ready to use right out of the box. Open-source models provide the machine's assembly drawings, parts list, and firmware source code, allowing you to swap out chips and modify the motherboard if you wish. The former facilitates deployment, while the latter offers transparency and control. However, models like GPT-5 and Gemini 2.5 are neither open source nor open-weighted business models. People can only use them through official applications and APIs.

- Open Weights: Only the pre-trained, numerical weights are released, not the full training recipe.
- Open Source: Implies that both the weights and the training code, datasets, and architecture are accessible, which is not always the case for "open-weight" models.

### Open Weights

Open-weight models are AI models (often LLMs) that publicly release their trained parameters or "weights," allowing users to download, run, and fine-tune them on their own infrastructure. Unlike closed models, these offer transparency, customization, and control, though they may not include the training data or code. Common examples include Llama 3, Mistral 7B, and Google's Gemma. 

**Prominent Examples**
- Meta Llama 3: Widely used, with weights available in various sizes.
- Mistral AI Models: Known for high performance and efficiency.
- Qwen Series (Alibaba): Popular for their strong, open-weight performance.
- Gemma (Google): Lightweight, open-source models. 

Open-weight models empower organizations to build specialized AI applications while balancing the need for control and the benefits of pre-trained, high-performance technology. 

## Videos

 * [Open Weight vs Open Source Models !](https://www.youtube.com/watch?v=ITUB6QHc9j8)
	> [<img src="https://img.youtube.com/vi/ITUB6QHc9j8/0.jpg" width="200">](https://www.youtube.com/watch?v=ITUB6QHc9j8 "Open weight refers to AI models where the train parameters or weights are publicly available, allowing users to use a model as is. by Allow AI 16 views 4 minutes, 21 seconds")

 * [Open Weight vs Open Source Models !](https://www.youtube.com/watch?v=8ZuVqQMfLuQ)
	> [<img src="https://img.youtube.com/vi/8ZuVqQMfLuQ/0.jpg" width="200">](https://www.youtube.com/watch?v=8ZuVqQMfLuQ "Open weight refers to AI models where the train parameters or weights are publicly available, allowing users to use a model as is. by New Machina 17 views 4 minutes, 21 seconds")

 * [Open-source vs closed-source Large Language Models](https://www.youtube.com/watch?v=ciOgetjcF-M)
	> [<img src="https://img.youtube.com/vi/ciOgetjcF-M/0.jpg" width="200">](https://www.youtube.com/watch?v=ciOgetjcF-M "Closed-source LLMs keep weights & data private, accessed via paid APIs. Open-source LLMs are public, downloadable, and customizable. by Code With Aarohi 18 views 1 minutes, 29 seconds")

 * [Should You Use Open Source or Proprietary Large Language](https://www.youtube.com/watch?v=nCZ4BaTDeTA)
	> [<img src="https://img.youtube.com/vi/nCZ4BaTDeTA/0.jpg" width="200">](https://www.youtube.com/watch?v=nCZ4BaTDeTA "Proprietary LLMs are black boxes hosted externally, while open-source models can be downloaded, run locally, and fine-tuned for more data control. by Don Woodlock 19 views 5 minutes, 55 seconds")

## References

1. https://www.reddit.com/r/LocalLLaMA/comments/1iw1xn7/the_paradox_of_open_weights_but_closed_source/
2. https://openai.com/open-models/
3. https://www.ai21.com/glossary/foundational-llm/open-weights-model/
4. 
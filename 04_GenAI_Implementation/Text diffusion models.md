# Text diffusion models

## Table of Contents

- [Text diffusion models](#text-diffusion-models)
  - [Table of Contents](#table-of-contents)
  - [Text diffusion: A new paradigm for LLMs](#text-diffusion-a-new-paradigm-for-llms)
    - [Key insights regarding these models include:](#key-insights-regarding-these-models-include)
  - [Videos](#videos)
  - [References](#references)

## Text diffusion: A new paradigm for LLMs

Text diffusion models are described in the sources as a **different paradigm** from the standard autoregressive transformers like GPT. While they may still utilize transformer architectures under the hood, they operate through an **iterative denoising process** rather than predicting text one token at a time.

### Key insights regarding these models include:

- **Mechanism and Inspiration:** Inspired by image generation tools like Stable Diffusion, text diffusion models start with random text and refine it over multiple iterations. This is compared to Google’s **BERT models**, which fill in masked gaps in a sentence in parallel.
- **Efficiency and Speed:** The primary advantage of diffusion is **parallelization**. Because they generate an entire block of text or a "batch" of tokens at once, they can be significantly faster than autoregressive models that generate text sequentially. For example, while a reasoning model might take several minutes to generate a long response token-by-token, a diffusion model could theoretically provide a completion much more rapidly.
- **Ideal Use Cases:** Researchers suggest that diffusion models are particularly well-suited for **large code diffs** in software engineering. In these scenarios, the model needs to generate a massive amount of text quickly, and diffusion provides the speed necessary to prevent user churn. They are also viewed as candidates for **quick, cheap, at-scale tasks**, potentially powering the "free tiers" of future AI services.
- **Trade-offs and Limitations:** To achieve the same quality as state-of-the-art transformers, diffusion models must "crank up" the number of denoising steps, which can eventually make them **just as computationally expensive** as autoregressive models. Furthermore, they struggle with **tool use**; while an autoregressive model can easily "pause" its chain to call an external API or calculator, it is difficult to interrupt the parallel generation process of a diffusion model for external tool integration.

Ultimately, while Google has experimented with this via **Gemini Diffusion**, experts do not expect text diffusion to replace transformers for top-tier reasoning. Instead, it remains a viable alternative for specialized niches where **speed and volume** are prioritized over complex, tool-integrated reasoning.

## Videos

 * [Text diffusion: A new paradigm for LLMs](https://www.youtube.com/watch?v=bmr718eZYGU)
	> [<img src="https://img.youtube.com/vi/bmr718eZYGU/0.jpg" width="200">](https://www.youtube.com/watch?v=bmr718eZYGU "Text diffusion models generate text by iteratively refining a draft, promising faster inference and higher quality outputs than auto-regressive models. by Julia Turc 49,428 views 24 minutes, 17 seconds")

 * [Advancing Diffusion Models for Text Generation](https://www.youtube.com/watch?v=klW65MWJ1PY)
	> [<img src="https://img.youtube.com/vi/klW65MWJ1PY/0.jpg" width="200">](https://www.youtube.com/watch?v=klW65MWJ1PY "Advancing Diffusion Models for Text Generation by Simons Institute for the Theory of Computing 49,428 views 1 hour, 01 minutes, 51 seconds")

 * [How Diffusion Works for Text](https://www.youtube.com/watch?v=1mG678f1ZYU)
	> [<img src="https://img.youtube.com/vi/1mG678f1ZYU/0.jpg" width="200">](https://www.youtube.com/watch?v=1mG678f1ZYU "This is a paper that is fundamentally about applying diffusion techniques which we've discussed in past Dives. by Oxen 49,428 views 42 minutes, 24 seconds")

## References

1. https://github.com/huggingface/diffusers
2. https://charanhu.medium.com/diffusion-language-models-dlms-a-new-frontier-in-text-generation-8fdafac17568
3. https://peerj.com/articles/cs-1905/
4. https://huggingface.co/blog/ProCreations/diffusion-language-model
5. https://arxiv.org/abs/2410.21357
6. https://www.seangoedecke.com/diffusion-models-explained/
7. https://www.seangoedecke.com/limitations-of-text-diffusion-models/
8. 
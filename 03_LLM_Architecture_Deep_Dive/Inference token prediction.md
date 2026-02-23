# Inference token prediction

## Table of Contents

- [Inference token prediction](#inference-token-prediction)
  - [Table of Contents](#table-of-contents)
  - [Next-Token Prediction (NTP)](#next-token-prediction-ntp)
  - [Videos](#videos)
  - [References](#references)

## Next-Token Prediction (NTP)

Inference token prediction is the process of generating text in large language models (LLMs) by predicting the next token in a sequence. The traditional method, Next-Token Prediction (NTP), predicts only one token at a time, making it slow because the entire model needs to run for every single token, which is often bandwidth-bound. 

Recent developments focus on accelerating this process through Multi-Token Prediction (MTP), where the model predicts multiple future tokens simultaneously. 

Here are the key aspects of modern inference token prediction:

1. Multi-Token Prediction (MTP) and Acceleration
   1. Faster Inference: MTP allows models to predict \(n\) future tokens at once, resulting in up to 3x faster inference speeds compared to traditional methods.
   2. Speculative Decoding: This technique uses a smaller "draft" model (or additional "heads" on the main model) to predict several future tokens in parallel, which are then verified by the main model in one forward pass.
   3. FastMTP: A specific, improved method that fine-tunes a single MTP head with shared weights, achieving an average of 2.03x speedup while maintaining high output quality.
   4. EAGLE/EAGLE-3: An advanced technique that uses a lightweight prediction head on top of the target model’s internal layers to generate candidate tokens, offering higher acceptance rates.
2. Emerging Techniques
   1. Future Intermediate Representation Prediction (FIRP): A method that predicts the hidden states of future tokens in intermediate layers, achieving a 1.9x–3x speedup without needing a separate draft model.
   2. Leap Multi-Token Prediction (L-MTP): An approach that predicts non-sequential, "skipped" future tokens to better capture long-range dependencies and speed up inference.
   3. Language-Aware Vocabulary Compression: Techniques that limit the search space for predicted tokens to specific, smaller, and more relevant vocabularies (e.g., 16k for Chinese, 32k for English) to reduce computational overhead.
3. Benefits of Advanced Prediction
   1. Higher Throughput: By reducing the number of sequential decoder calls, these methods significantly improve tokens-per-second, especially for long-generation tasks like chain-of-thought.
   2. Better Performance: Training models to predict multiple tokens improves their "foresight," resulting in better performance on downstream tasks, especially code generation (12–17% higher on HumanEval/MBPP).
   3. Reduced Latency: By enabling parallel verification of multiple tokens, MTP directly addresses the bottleneck of autoregressive, step-by-step decoding.

These advancements are rapidly moving from academic research into practical deployment in frameworks like SGLang, vLLM, and NVIDIA TensorRT-LLM.

## Videos

 * [How Tokenization, Inference, & LLMs Actually Work](https://www.youtube.com/watch?v=OyfiYTzMhAc)
	> [<img src="https://img.youtube.com/vi/OyfiYTzMhAc/0.jpg" width="200">](https://www.youtube.com/watch?v=OyfiYTzMhAc "Learn how large language models generate text by understanding tokens, inference, and sampling strategies like temperature and top P. by Mark Hennings 4.3K views 18 minutes, 40 seconds")

* [Why would anyone let LLMs predict 4 tokens at once? Multi-Token Prediction Explained](https://www.youtube.com/watch?v=4BhZZYg2_J4)
	> [<img src="https://img.youtube.com/vi/4BhZZYg2_J4/0.jpg" width="200">](https://www.youtube.com/watch?v=4BhZZYg2_J4 "Multi-token prediction predicts multiple future tokens at once, potentially speeding up generation by 4x. by bycloud 56,094 views 11 minutes, 02 seconds")

## References


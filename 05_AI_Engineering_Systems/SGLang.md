# SGLang

## Table of Contents

- [SGLang](#sglang)
  - [Table of Contents](#table-of-contents)
  - [SGLang](#sglang-1)
  - [Videos](#videos)
  - [References](#references)

## SGLang

SGLang is a high-performance serving framework for large language models and multimodal models.

![SGlang](https://raw.githubusercontent.com/sgl-project/sglang/main/assets/logo.png)

## Videos

https://www.youtube.com/watch?v=1pT63qBc8-c
SGLang: Open-Source Model Performance Optimization
YouTube · AMD Developer Central
Nov 10, 2025
YouTube · AMD Developer Central

8:32
The SGLang model gateway is the next generation of the SR router, routing different requests to different models.

https://www.youtube.com/watch?v=G4ZeVP7n0Ik
Lianmin Zheng on Efficient LLM Inference with SGLang
YouTube · AMD Developer Central
Jun 30, 2025
YouTube · AMD Developer Central

22:57
SGM is an open-source fast inference engine for large language models. It supports large-scale expert parallelism, prefill decode disaggregation, and more.

https://www.youtube.com/watch?v=3asambS3egM
SGLang Step by Step Beginner Tutorial
YouTube · Vuk Rosić
Sep 4, 2025
YouTube · Vuk Rosić

10:47
SGLang is a fast LLM serving framework. Use the sglangfunction decorator, sgenerate for answers, and sgl.fork for parallel generation.


## References

1. https://github.com/sgl-project/sglang
2. [SGLang: Efficient Execution of Structured Language Model Programs](https://arxiv.org/pdf/2312.07104)
3. https://www.reddit.com/r/LocalLLaMA/comments/1jjl45h/compared_performance_of_vllm_vs_sglang_on_2/?tl=pt-br
   1. benchmark SGLang: https://github.com/sbnb-io/sbnb/blob/main/README-SGLANG.md
   2. benchmark vLLM: https://github.com/sbnb-io/sbnb/blob/main/README-VLLM.md
4. [Scaling Down, Serving Fast: Compressing and Deploying Efficient LLMs for Recommendation Systems](https://arxiv.org/abs/2502.14305)
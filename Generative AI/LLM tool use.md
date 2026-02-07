# LLM Tool Use

Drawing on the sources, the following presentation explores how Large Language Models (LLMs) are evolving from simple text generators into agentic systems capable of interacting with the physical and digital world through **tool use**.

## Table of Contents

- [LLM Tool Use](#llm-tool-use)
  - [Table of Contents](#table-of-contents)
  - [Course Module: LLM Tool Use](#course-module-llm-tool-use)
    - [**1. Definition and Core Concept**](#1-definition-and-core-concept)
    - [**2. Solving the Hallucination Problem**](#2-solving-the-hallucination-problem)
    - [**3. How Models Learn to Use Tools**](#3-how-models-learn-to-use-tools)
    - [**4. Open Source vs. Closed Source Tooling**](#4-open-source-vs-closed-source-tooling)
    - [**5. Future Directions: Recursive Agents**](#5-future-directions-recursive-agents)
  - [Videos](#videos)
  - [References](#references)

---

## Course Module: LLM Tool Use

LLM tool use (or function calling or tool calling) enables large language models to interact with external systems, APIs, databases, and calculators, extending their capabilities beyond text generation. Instead of relying solely on internal knowledge, the LLM identifies the need for a tool, generates structured input (often JSON) to call it, receives the results, and incorporates them into the final response. 

**Whole process of LLM using tools**
![The paper titled "LLM With Tools: A Survey" by Zhuocheng Shen](llm_tool_use.png)

---

### **1. Definition and Core Concept**

- **Defining Tool Use:** In the context of LLMs, tool use refers to the model’s ability to perform actions such as conducting a **web search**, calling a **Python interpreter**, or using a **calculator** to solve a problem. 
- **A Paradigm Shift:** This represents a shift from the model trying to "remember" every piece of information to **outsourcing tasks** to specialized software. Instead of predicting the answer to a math problem based on training data, the model identifies it needs a calculator and executes the command.

---

### **2. Solving the Hallucination Problem**

- **Beyond Memorization:** One of the most significant complaints about LLMs is **hallucinations**. The sources argue that the best way to solve this is to stop forcing models to memorize facts.
- **Reliability through External Sources:** By using tools, a model can look up factual information—such as who won a specific soccer match—via a Google search or the FIFA website, providing a **reliable answer** rather than a "made up" one.
- **Mathematical Precision:** Tool use allows models to achieve high precision in math by using code or calculators, which prevents the errors commonly found in purely autoregressive token prediction.

---

### **3. How Models Learn to Use Tools**

- **The Role of RLVR:** Capabilities for tool use are largely "unlocked" during **post-training** through **Reinforcement Learning with Verifiable Rewards (RLVR)**. 
- **Trial and Error:** During training, the model is placed in an environment where it can try a tool, see the output, and determine if it solved the problem. If the output is correct (e.g., a Bash script runs successfully), the model receives a **verifiable reward**, reinforcing that behavior.
- **Inference-Time Scaling:** The "thinking" process seen in modern models often involves the model generating **hidden thoughts** where it decides which API to call or which tool is needed before presenting the final answer to the user.

---

### **4. Open Source vs. Closed Source Tooling**

- **Open-Weight Innovations:** The model **`gpt-oss-120b`** is highlighted as the first major open-weight model trained specifically with tool use as a core focus. 
- **The Integration Gap:** While open models like `gpt-oss` are powerful, the open-source ecosystem is currently on the "back foot" compared to closed labs. Closed models (like ChatGPT or Claude) benefit from **deeply integrated, secure cloud environments** that make tool use seamless for the average user.
- **Trust and Safety:** A major barrier for open-source tool use is **trust**; users are often hesitant to give an LLM permission to run tools locally on their computer for fear it might accidentally delete files or compromise security.

---

### **5. Future Directions: Recursive Agents**

- **Recursive Problem Solving:** The next step for 2026 is the **Recursive Language Model**, which breaks down a complex task into sub-tasks and recursively calls the LLM (and its tools) to solve each part.
- **Orchestration:** Future open models will likely need to become "orchestrators" that are flexible enough to work with a variety of third-party search providers or APIs, rather than being locked into a single ecosystem.
- **Personalization:** Tool use will eventually allow models to access personal information—like sorting emails or booking travel—though this will require the model to learn the specific nuances and preferences of the individual user.

## Videos

 * [LLM Tool Calling EXPLAINED! - The Power Behind AI Agents](https://www.youtube.com/watch?v=vdUxBDulv1M)
	> [<img src="https://img.youtube.com/vi/vdUxBDulv1M/0.jpg" width="200">](https://www.youtube.com/watch?v=vdUxBDulv1M "Ever wondered how AI agents can browse the web, call APIs, and automate tasks? It’s all thanks to Tool Calling!  by Execute Automation 2.8K views 14 minutes, 06 seconds")

 * [How LLM Tool Calling Works](https://www.youtube.com/watch?v=QiRdYCNXAxk)
	> [<img src="https://img.youtube.com/vi/QiRdYCNXAxk/0.jpg" width="200">](https://www.youtube.com/watch?v=QiRdYCNXAxk "Tool Calling is a fundamental concept for understanding AI Agents. LLMs like gpt-4o and Claude Sonnet are unable to execute code or do anything other output tokens. AI Agents need a way to interact with real world systems, and tool calling is the way that this is accomplished. by Tommy Eberle 4,168 views 16 minutes")

## References

1. https://vercel.com/kb/guide/what-is-an-llm-tool
2. https://www.reddit.com/r/LocalLLaMA/comments/1mfrq3v/what_is_tool_use_exactly/
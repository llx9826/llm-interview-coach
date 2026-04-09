# Chinese Big-Tech LLM Interview Patterns

Use this file when the user wants realistic Chinese-market interview prep, especially for 大厂大模型算法岗, 算法工程师, 应用算法, RAG/Agent/推理优化 roles.

This reference is synthesized from public GitHub interview collections and Chinese interview-prep repositories. Treat it as style guidance plus question patterns, not a guarantee of any company's current process.

## Source signals

The following public repositories were used to shape this reference:

- `yang19527/AwesomeInterview`: large collection of company-tagged LLM interview links, covering 百度、美团、腾讯、阿里、字节、快手、华为等.
- `wdndev/llm_interview_note`: broad Chinese LLM interview knowledge base covering pretraining, fine-tuning, inference, RLHF, RAG, Agent, and evaluation.
- `Joining-AI/LLM_Interview_Prepare`: Chinese LLM interview repository maintained by SJTU Joining AI, with emphasis on interview questions and answers.
- `luhengshiwo/LLMForEverybody`: Chinese LLM learning/interview repository with broad topic coverage including pretraining, inference, fine-tuning, quantization, agent, enterprise deployment, and evaluation.

## What Chinese big-tech interviews usually optimize for

Compared with generic English-language interview prep, Chinese big-tech LLM interviews often emphasize:

- concrete project ownership
- whether you can explain metrics and baselines
- whether you understand training and serving as systems, not just papers
- whether you can connect model changes to business value
- whether you can discuss tradeoffs under limited GPU / latency / cost constraints

In practice, interviewers often press on:

- "你这个提升到底来自哪里？"
- "基线是什么？为什么公平？"
- "如果线上流量扩大 10 倍，先炸哪？"
- "你做的是算法贡献、工程贡献，还是数据贡献？"
- "如果不用你这个方案，有没有更便宜的替代？"

## Common company-flavored patterns

These are tendencies, not hard rules.

### Baidu / Tencent / Alibaba style

Often more balanced across:

- Transformer and LLM fundamentals
- training / fine-tuning details
- serving / deployment
- RAG or agent system design
- project depth

Typical questions:

- Why are decoder-only models dominant in modern LLMs?
- Compare full fine-tuning, LoRA, and QLoRA in terms of memory, speed, and quality.
- If your retrieval recall improves but final answer quality does not, where might the problem be?
- How would you measure the real gain from instruction tuning?
- Explain KV cache, continuous batching, and paged attention in a practical serving setup.

### Meituan / ByteDance / Kuaishou style

Often more product-and-scale oriented:

- system design under high traffic
- online metrics
- latency / throughput / cost
- recommendation/search/ad relevance style thinking
- data flywheel and experimentation

Typical questions:

- How do you design a chatbot or copilot for high-QPS production use?
- Which metrics would you monitor online besides accuracy?
- How would you reduce p99 latency without losing too much quality?
- When does an expensive reranker stop being worth it?
- What would you A/B test first in an LLM application?

### Huawei / enterprise AI style

Often stronger on engineering rigor:

- distributed training basics
- model compression / quantization
- deployment constraints
- hardware awareness
- fault isolation and reliability

Typical questions:

- Explain tensor parallelism, pipeline parallelism, and sequence parallelism.
- Why does quantization hurt some tasks more than others?
- How would you profile GPU memory for a 7B or 14B deployment?
- What happens when batch size increases during online inference?
- How would you debug throughput collapse after a model upgrade?

## Representative realistic question sets

### Set 1: Fundamentals with pressure

- 为什么现在主流大模型大多采用 decoder-only，而不是 encoder-decoder？
- RoPE 的核心作用是什么？长上下文时会遇到什么问题？
- MHA、MQA、GQA 的差异是什么？为什么 GQA 在工程上常见？
- pretraining、SFT、RLHF/DPO 在目标函数和使用场景上分别解决什么问题？
- 为什么 LoRA 能工作？rank 太小时会发生什么？

### Set 2: Inference and systems

- vLLM 为什么快？PagedAttention 解决了什么核心问题？
- 什么是 KV cache？它节省了什么，代价又是什么？
- continuous batching 的收益和边界在哪里？
- speculative decoding 在什么条件下值得上？
- 如果线上延迟高、吞吐低、GPU 利用率也不高，你先查哪里？

### Set 3: RAG and retrieval

- 什么情况下 RAG 比微调更合适？
- chunk size、overlap、embedding 模型选择如何影响效果？
- 召回率高但最终回答还是差，可能是哪几层出了问题？
- hybrid retrieval 和 rerank 各自解决什么问题？
- RAG 怎么做离线评测，怎么避免“看起来不错”的假象？

### Set 4: Agent and application

- 什么时候应该上 agent，什么时候只需要 workflow？
- tool calling 最常见的失败模式是什么？
- 你如何限制 agent 的错误行动和成本失控？
- 多轮 memory 该怎么设计，什么情况下反而不该记？
- 一个 agent 系统的 eval 该如何分层？

### Set 5: Project deep dive

Ask all of these for any claimed project:

- 业务目标是什么？
- baseline 是什么？
- 你负责哪一层？
- 数据规模、请求规模、模型规模是多少？
- 线上和离线指标分别是什么？
- 最大瓶颈是什么？
- 你试过哪些失败方案？
- 如果现在重做，会先改哪一处？

## Realistic follow-up pressure tests

Use these after the user gives a seemingly correct answer:

- 你说“效果提升明显”，具体是从多少到多少？
- 这个提升有没有可能是数据泄漏或者评测偏差？
- 为什么不用更简单的方案？
- 如果 GPU 资源砍半，你怎么重构方案？
- 这个方案最脆弱的一环是什么？
- 你这个项目里，真正体现你个人判断的决定是哪一个？

## High-frequency blind spots in Chinese-market candidates

- only knows definitions, not tradeoffs
- cannot separate retrieval, generation, reranking, and eval failures
- overstates project ownership
- cannot explain data quality work
- cannot quantify online impact
- confuses training-time optimization and serving-time optimization
- knows buzzwords like RLHF / Agent / RAG but not failure modes

## Interview mode recommendations

When using this reference:

- ask shorter, sharper questions
- push harder on metrics and ownership
- include at least one systems or serving follow-up
- include at least one business-value follow-up for applied roles
- include at least one "what failed?" follow-up for project rounds


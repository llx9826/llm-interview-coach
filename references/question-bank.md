# LLM Interview Question Bank

Use these topic groups to generate drills or mock questions.

## 1. Transformer and LLM basics

- Explain self-attention and multi-head attention.
- Why does scaling sequence length make attention expensive?
- What is RoPE and why is it used?
- Differences between encoder-only, decoder-only, and encoder-decoder models.
- Why do normalization placement and residual paths matter?

## 2. Training pipeline

- Pretraining, SFT, DPO, PPO: when and why?
- How do you build and clean a large corpus?
- What data mixture decisions matter most?
- How would you detect data contamination or duplication?
- What makes training unstable?

## 3. Fine-tuning and adaptation

- Full fine-tuning vs LoRA vs QLoRA.
- How do rank, target modules, and data quality affect LoRA outcomes?
- When does SFT fail even with more data?
- How do you avoid catastrophic forgetting?
- How would you adapt a model to a narrow domain with limited data?

## 4. Inference and systems

- KV cache: what it is and why it helps.
- Continuous batching, paged attention, speculative decoding.
- Quantization tradeoffs: INT8, INT4, AWQ, GPTQ.
- Throughput vs latency vs quality tradeoffs.
- What breaks first in high-QPS serving?

## 5. RAG

- When is RAG better than fine-tuning?
- Chunking strategy tradeoffs.
- Embedding model choice and recall issues.
- Hybrid retrieval, reranking, multi-query retrieval.
- How do you evaluate RAG beyond "looks good"?

## 6. Agent and tool use

- When should you use an agent instead of a simpler workflow?
- Tool selection failure modes.
- Memory design choices.
- How do you constrain tool-calling risk?
- How would you evaluate an agent system?

## 7. Evaluation

- Offline vs online evaluation.
- Pairwise eval, rubric eval, LLM-as-judge limits.
- Hallucination metrics and faithfulness checks.
- How do you design a benchmark that matches business value?
- What would make your eval misleading?

## 8. Projects

Always probe:

- What was the business goal?
- What baseline did you compare against?
- What data did you use?
- What metric moved?
- What was the scale?
- What failed?
- What tradeoff did you make?
- What would you redesign now?

## 9. Coding and modeling follow-ups

- Implement scaled dot-product attention.
- Design a mini RAG service.
- Estimate memory for a 7B model with KV cache.
- Explain how you'd profile and reduce p99 latency.
- Build an offline eval pipeline for a chatbot.

## 10. Chinese-market high-frequency questions

These are especially useful for 大厂 algorithm / applied-LLM interviews in China:

- Why does decoder-only dominate current LLM products?
- Compare LoRA, QLoRA, full fine-tuning, and prompt tuning under limited GPU.
- How would you explain the practical value of RoPE and its long-context limitations?
- What are the engineering tradeoffs between MHA, MQA, and GQA?
- What does vLLM optimize, and why does PagedAttention matter?
- If retrieval improves but answer quality does not, how do you localize the problem?
- How do you design offline and online eval for a Chinese-domain copilot?
- When should you choose RAG over domain fine-tuning?
- If cost doubles after a model upgrade, what knobs do you inspect first?
- For an LLM feature, how do you prove your gain is not just prompt luck or data leakage?

## 11. Project-pressure follow-ups

- What exactly was your personal contribution?
- Which metric moved, by how much, and against which baseline?
- What did you try that failed?
- What would break first at 10x traffic?
- What simpler alternative did you reject, and why?
- If GPU budget were cut in half, how would you redesign it?

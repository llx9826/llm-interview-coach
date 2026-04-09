# 岗位分型

先判断用户准备的是哪一类岗位，再决定题目和追问重心。

## 1. 应用算法岗

关键词：

- AI 应用算法
- LLM 应用工程
- 智能体应用
- Copilot / Chatbot / 企业知识库

重点考察：

- RAG、Agent、Prompt、Eval
- 线上效果、延迟、成本、稳定性
- 业务指标
- 系统设计和落地能力

少问，或只浅问：

- 分布式训练细节
- 大规模预训练细节

## 2. 大模型算法工程岗

关键词：

- 大模型算法工程师
- LLM 算法岗
- 模型工程师

重点考察：

- Transformer 基础
- SFT / DPO / RLHF
- 数据质量
- 微调方案
- RAG 与推理优化
- 项目中的算法判断和结果

这是默认岗位类型。

## 3. 推理优化 / 系统岗

关键词：

- 推理优化
- Serving
- vLLM
- 部署优化
- 系统性能

重点考察：

- KV cache
- continuous batching
- paged attention
- quantization
- latency / throughput / GPU memory
- 服务稳定性、瓶颈定位

要强追：

- p50/p95/p99
- 吞吐和成本
- 资源利用率

## 4. 训练 / 微调岗

关键词：

- 训练工程
- 微调工程
- Post-training
- Alignment

重点考察：

- 数据配比
- 训练稳定性
- LoRA / QLoRA / full finetune
- DPO / PPO / reward modeling
- 实验设计
- 模型退化和遗忘

## 5. 研究型岗位

关键词：

- 研究员
- Applied Scientist
- Research Scientist

重点考察：

- 方法理解
- 论文和实验逻辑
- 设计新方案的能力
- ablation
- 理论动机和边界

注意：

- 不要把研究岗问成纯工程岗
- 但也不能完全脱离工程可落地性

## 快速判断规则

- 用户强调“线上效果、业务、落地” -> 应用算法岗
- 用户强调“模型、微调、训练、对齐” -> 训练/算法岗
- 用户强调“吞吐、延迟、vLLM、显存” -> 推理优化岗
- 用户强调“论文、方法创新、实验设计” -> 研究岗


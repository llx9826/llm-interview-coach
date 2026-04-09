# llm-interview-coach

面向中文场景的大模型面试 `Codex skill`。  
不是泛泛刷题，而是按真实大厂风格做 `项目深挖 + 追问 + 诊断 + 个性化训练闭环`。

[English README](./README.en.md)

适合准备这些岗位：

- 大模型算法工程师
- LLM / GenAI 应用算法工程师
- RAG / Agent 工程师
- 推理优化 / Serving 工程师
- 训练 / 微调 / 对齐工程师
- 部分 Applied Scientist / 研究型岗位

## Why This Exists

很多面试资料有两个问题：

- 要么太泛，只会给一堆概念题
- 要么太散，没有办法围绕候选人的真实项目持续训练

真实的大模型面试，尤其是中文大厂场景，更看重这些：

- 你能不能讲清楚项目目标、baseline、指标和失败方案
- 你能不能把模型、数据、评测、服务串成一个系统
- 你是不是只会背术语，还是能讲 tradeoff
- 你说的提升到底是不是可信

这个 skill 就是为这类面试准备的。

## What Makes It Different

### 1. 中文大厂风格

不是通用英语面试脚本，默认按中文技术面风格来设计问题和追问，偏真实压力测试。

### 2. 项目优先

很多候选人概念题能答，一到项目深挖就开始虚。  
这个 skill 把项目深挖放在核心位置，而不是附属功能。

### 3. 岗位分型

应用算法岗、推理优化岗、训练岗、研究岗，本来就该问不同的内容。  
这个 skill 会先判断岗位，再决定题型和追问方式。

### 4. 个性化训练

如果你已经有项目、简历、目标岗位，这个 skill 会优先围绕你的真实背景训练，而不是继续给泛题。

### 5. 训练闭环

不是“问完结束”，而是每轮输出：

- 这题哪里答对了
- 哪些地方答虚了
- 面试官下一步会怎么追
- 你的短板挂在哪一类
- 下一步应该补什么

## Core Modes

- `mock`
  一次问一道题，然后继续追问。

- `drill`
  按主题集中刷题，适合补某一类短板。

- `review`
  复盘面试答案、简历 bullet、项目表述。

- `plan`
  生成 7 天或 14 天高密度训练计划。

- `project`
  只做项目深挖，盯着目标、baseline、指标、失败和 tradeoff 问。

- `personalize`
  建立候选人画像，生成个性化题库、风险问点和训练顺序。

## Quick Start

把这个目录放进你的 Codex skills 目录后，直接这样用：

```text
用 llm-interview-coach 帮我做中文大厂大模型算法岗 mock interview
```

或者：

```text
用 llm-interview-coach 按我的项目和背景做 personalize 模式
```

再比如：

```text
用 llm-interview-coach 深挖我这个 RAG 项目
```

```text
用 llm-interview-coach 给我做一个大模型算法岗 7 天学习计划，按二八法则来
```

## Demo

下面是一段更像真实使用场景的示例。

### Input

```text
用 llm-interview-coach 深挖我的项目：
我做了一个企业知识库问答系统，采用 hybrid retrieval + rerank + generator，
线上平均延迟 1.2s，回答采纳率提升 11%，我主要负责检索、评测和服务优化。
```

### Output style

```text
先说结论：这个项目能面，但现在最危险的是你对 baseline、失败方案和个人贡献边界讲得还不够硬。

第一问：
这个项目最初要解决的业务问题是什么？为什么当时必须做？

第二问：
你说回答采纳率提升了 11%，baseline 是什么？这个对照为什么公平？

第三问：
你主要负责检索、评测和服务优化。分别说一个最体现你判断力的决定。

第四问：
如果不用 hybrid retrieval + rerank 这套方案，只用更简单的向量召回 + 生成，会差在哪？

第五问：
你试过哪些失败方案？失败原因是什么？

诊断：
- 结论：passable
- 得分：6.5/10
- 暴露短板：项目 ownership、baseline 意识、失败复盘
- 下一步训练动作：
  1. 把 baseline 定义写成一句话
  2. 为每个模块补 1 个失败案例
  3. 把“我负责什么”改成结果导向表述
```

这个 skill 的目标不是只给题，而是把候选人一步步逼到真实面试的深度。

## Example Prompts

### Mock interview

```text
用 llm-interview-coach 帮我做一轮中文大厂大模型算法岗 mock，重点考 RAG、LoRA 和推理优化
```

### Project deep dive

```text
用 llm-interview-coach 深挖我的项目：
我做了一个企业知识库问答系统，采用 hybrid retrieval + rerank + generator，线上延迟 1.2s，回答采纳率提升 11%
```

### Personalized plan

```text
用 llm-interview-coach 按我的背景做个性化训练：
- 3 年后端 / 算法工程经验
- 做过 RAG、评测和推理服务
- 弱项是 RLHF、训练细节、英文表达
- 目标是 2 周后面中文大厂大模型算法岗
```

## What It Covers

核心覆盖主题：

- Transformer 基础
- RoPE / 位置编码
- MHA / MQA / GQA
- KV Cache
- pretraining / SFT / DPO / RLHF
- LoRA / QLoRA / full finetune
- RAG
- Agent
- Eval
- 推理优化
- 延迟、吞吐、显存、成本 tradeoff
- 项目 ownership / baseline / 指标 / 失败案例

## Repository Structure

```text
llm-interview-coach/
├── SKILL.md
├── README.md
├── LICENSE
└── references/
    ├── question-bank.md
    ├── china-bigtech.md
    ├── rubric.md
    ├── roles.md
    ├── project-deep-dive.md
    ├── diagnostic-output.md
    └── personalization.md
```

## Design Principles

### First principles

技术面试准备的核心只有 4 件事：

1. 生成高价值问题
2. 识别真实短板
3. 用追问暴露问题
4. 形成可执行训练闭环

### Occam's razor

不引入花哨但低收益的复杂设计。  
优先保留真正影响通过率的模块：

- 岗位分型
- 项目深挖
- 评分和诊断
- 个性化优先级

## File Guide

- `SKILL.md`
  主入口，定义触发词、模式和主流程。

- `references/question-bank.md`
  通用大模型面试题库。

- `references/china-bigtech.md`
  中文大厂常见问法、压力测试、公司风格倾向。

- `references/rubric.md`
  回答评分标准。

- `references/roles.md`
  不同岗位该怎么问。

- `references/project-deep-dive.md`
  项目深挖骨架。

- `references/diagnostic-output.md`
  每轮 mock 后的诊断格式。

- `references/personalization.md`
  候选人画像、短板地图、个性化训练方法。

## Who This Is For

这个 skill 特别适合你，如果你符合下面任一条：

- 已经有项目经验，但一被深挖就答虚
- 想冲中文大厂大模型算法岗
- 想用 7 天或 14 天高密度冲刺
- 讨厌泛泛刷题，更想围绕真实经历训练
- 想把 Codex 当成长期面试教练，而不是一次性问答工具

## Roadmap

后续可以继续增强：

- 更细的公司风格拆分
- 英文算法面版本
- 简历解析和高风险问点抽取
- 不同 seniority 的难度分层
- 面试记录的长期记忆层

## License

MIT


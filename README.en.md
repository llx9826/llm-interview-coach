# llm-interview-coach

A `Codex skill` for preparing LLM interviews in a Chinese-market style.  
It focuses on `project deep dives + follow-up pressure + diagnosis + personalized training loops`, instead of generic question dumping.

[中文 README](./README.md)

Best suited for:

- LLM algorithm engineers
- GenAI / applied LLM engineers
- RAG / agent engineers
- inference optimization / serving engineers
- training / post-training / alignment engineers
- some applied scientist / research-oriented roles

## Why This Exists

Most interview prep resources have two problems:

- they are too generic and mostly dump concept questions
- they are too scattered and cannot train around a candidate's real projects

Real LLM interviews, especially in Chinese big-tech settings, care much more about:

- whether you can explain the project goal, baseline, metrics, and failed attempts
- whether you can connect models, data, evaluation, and serving as one system
- whether you understand tradeoffs instead of repeating buzzwords
- whether your claimed gains are actually credible

This skill is built for that.

## What Makes It Different

### 1. Chinese big-tech style

This is not a generic English interview script. It defaults to a Chinese technical interview style with realistic pressure and follow-up questions.

### 2. Project-first

Many candidates can answer concept questions, but fall apart when interviewers dig into projects.  
This skill treats project interrogation as a core feature, not a side feature.

### 3. Role-aware

Applied LLM roles, inference roles, training roles, and research roles should not be interviewed the same way.  
This skill classifies the role first, then changes the question density and follow-up style.

### 4. Personalized training

If you already have projects, resume bullets, and a target role, the skill prioritizes your real background instead of giving you a generic list of questions.

### 5. Closed feedback loop

It does not just ask a question and stop. Each round is supposed to expose:

- what you got right
- what sounded shallow
- what an interviewer would ask next
- which weakness category was exposed
- what to train next

## Core Modes

- `mock`
  Ask one question at a time, then keep pressing.

- `drill`
  Generate focused question sets by topic.

- `review`
  Review answers, resume bullets, and project narratives.

- `plan`
  Generate a 7-day or 14-day high-density prep plan.

- `project`
  Only do project deep dives: goals, baseline, ownership, metrics, failures, tradeoffs.

- `personalize`
  Build a candidate profile and output a personalized question set, risk points, and training order.

## Quick Start

Drop this folder into your Codex skills directory, then use prompts like:

```text
Use llm-interview-coach to run a mock interview for a Chinese big-tech LLM algorithm role.
```

```text
Use llm-interview-coach to personalize training based on my resume and projects.
```

```text
Use llm-interview-coach to deeply interrogate my RAG project.
```

```text
Use llm-interview-coach to create a 7-day study plan for an LLM algorithm interview using the 80/20 rule.
```

## Demo

### Input

```text
Use llm-interview-coach to deeply interrogate my project:
I built an enterprise knowledge-base QA system with hybrid retrieval + rerank + generator.
Online average latency was 1.2s, and answer acceptance improved by 11%.
I mainly worked on retrieval, evaluation, and serving optimization.
```

### Output style

```text
Short verdict first: this project is interviewable, but your weakest points right now are baseline definition, failed attempts, and hard ownership boundaries.

Question 1:
What business problem did this project originally solve, and why did it matter?

Question 2:
You said answer acceptance improved by 11%. What was the baseline, and why is that comparison fair?

Question 3:
You worked on retrieval, evaluation, and serving optimization. Give one decision in each area that clearly shows your judgment.

Question 4:
If you had used only simple vector retrieval + generation instead of hybrid retrieval + rerank, what would have broken first?

Question 5:
What failed during the project, and why did it fail?

Diagnosis:
- verdict: passable
- score: 6.5/10
- exposed weaknesses: project ownership, baseline awareness, failure analysis
- next actions:
  1. write a one-line baseline definition
  2. prepare one failed attempt per module
  3. rewrite your ownership in result-oriented terms
```

The point is not just to ask questions. The point is to push candidates into the depth that real interviews actually require.

## What It Covers

Core topic coverage:

- Transformer fundamentals
- RoPE / positional encoding
- MHA / MQA / GQA
- KV cache
- pretraining / SFT / DPO / RLHF
- LoRA / QLoRA / full finetuning
- RAG
- agents
- evaluation
- inference optimization
- latency, throughput, memory, and cost tradeoffs
- project ownership / baseline / metrics / failure analysis

## Repository Structure

```text
llm-interview-coach/
├── SKILL.md
├── README.md
├── README.en.md
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

Technical interview prep boils down to four things:

1. generate high-value questions
2. identify real weaknesses
3. expose gaps through follow-up pressure
4. turn the results into executable next steps

### Occam's razor

Avoid clever but low-value complexity.  
Keep only the modules that materially improve interview outcomes:

- role typing
- project deep dives
- scoring and diagnosis
- personalization priority

## Who This Is For

This skill is especially useful if:

- you have project experience but become shallow under follow-up questions
- you are targeting Chinese big-tech LLM roles
- you want a 7-day or 14-day intense sprint
- you prefer training around real experience instead of generic drilling
- you want Codex to behave more like a long-term interview coach than a one-off Q&A tool

## Roadmap

Potential next steps:

- finer company-specific styles
- a stronger English-facing interview variant
- resume parsing and high-risk question extraction
- difficulty layers by seniority
- persistent memory for long-term interview coaching

## License

MIT


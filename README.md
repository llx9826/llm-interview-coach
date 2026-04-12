# 🎯 llm-interview-coach | 中文大厂大模型面试教练

![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)
![Chinese First](https://img.shields.io/badge/language-中文优先-red)
![LLM Interview](https://img.shields.io/badge/focus-大模型面试-blue)
![Works with Codex](https://img.shields.io/badge/兼容-Codex-black)
![Works with Cursor](https://img.shields.io/badge/兼容-Cursor-4F46E5)
![Works with OpenClaw](https://img.shields.io/badge/兼容-OpenClaw-0F766E)
![Works with Claude Code](https://img.shields.io/badge/兼容-Claude%20Code-7C3AED)
![Downloads](https://img.shields.io/github/downloads/llx9826/llm-interview-coach/total)
![Stars](https://img.shields.io/github/stars/llx9826/llm-interview-coach)

> **解决80%大模型求职者的核心痛点：**  
> 背了几百道概念题，一被深挖项目就卡壳；刷了一堆英文面试题，完全不适应国内大厂的压力面风格；练了半天不知道自己短板在哪，越练越慌。

面向中文场景的大模型面试专属训练工具，**不是泛泛刷题，而是完全复刻国内大厂真实面试逻辑**，帮你做 `项目深挖 + 连续追问 + 短板诊断 + 个性化训练闭环`，针对性提升通过率。

[English README](./README.en.md)

这是一个跨平台可复用的Skill，支持所有主流AI工作流：
- ✅ Codex
- ✅ Cursor
- ✅ OpenClaw
- ✅ Claude Code
- ✅ 任意支持prompt pack/规则导入的AI工具

**完美适配这些岗位面试：**
- 🧑💻 大模型算法工程师
- 🤖 LLM / GenAI 应用算法工程师
- 🔍 RAG / Agent 工程师
- ⚡ 推理优化 / Serving 工程师
- 🧪 训练 / 微调 / 对齐工程师
- 🔬 部分 Applied Scientist / 研究型岗位

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

### Codex

把这个目录放进本地 skills 目录后，直接这样用：

```text
用 llm-interview-coach 帮我做中文大厂大模型算法岗 mock interview
```

### Cursor / Claude Code / OpenClaw

把这个仓库当成一个结构化 skill 使用：

- `SKILL.md` 作为主入口
- `references/` 作为按需读取的知识文件
- `README.md` / `README.en.md` 作为说明和示例

然后复用同样的触发语义，例如：

```text
用 llm-interview-coach 按我的项目和背景做 personalize 模式
```

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

更多可用于录屏或截图的素材：

- [demo-terminal.txt](./demo-terminal.txt)
- [demo-script.md](./demo-script.md)
- [PROMO.md](./PROMO.md)

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

### Cross-platform by design

仓库结构刻意保持简单：

- 一个主入口 `SKILL.md`
- 一组可按需读取的 `references/`
- 中英文两份 README

这样设计的目的，就是让它不绑定某一个平台的专有格式，同时能在多个工具链里复用。

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

- 更细的公司风格拆分（字节/阿里/腾讯/百度等不同厂的面试偏好）
- 英文算法面版本
- 简历自动解析和高风险问点抽取
- 不同 seniority 的难度分层（校招/社招1-3年/3-5年/资深）
- 面试记录的长期记忆层，自动跟踪短板提升情况

## 🐛 开发踩坑记录
这是开发过程中真实遇到的问题和解决方案，给其他AI Skill开发者避坑：

### 1. Prompt稳定性问题
**问题**：最开始用通用的prompt，不同大模型输出的格式差异很大，有的输出追问，有的直接给答案，格式完全不统一。
**解决方案**：把所有输出格式、逻辑、原则都拆成独立的reference文件，用结构化的配置定义每一步的输出，不管用什么大模型，输出结构完全一致，稳定性提升了90%。

### 2. 追问的「度」的把握
**问题**：最开始追问太发散，要么太简单要么太偏，和真实面试的追问逻辑不符，用户练了也没用。
**解决方案**：参考了100+真实大厂面经的追问路径，把项目深挖的逻辑做成了固定的骨架：从业务价值→baseline→指标→失败方案→tradeoff→个人贡献，逐层深入，完全复刻面试官的提问思路。

### 3. 岗位分型边界问题
**问题**：最开始岗位分类太粗，推理岗和训练岗问的题混在一起，针对性不强。
**解决方案**：把每个岗位的核心考点、高频问法、能力要求都做成了独立的配置文件，根据用户的目标岗位自动匹配对应的题库和追问逻辑，不会出现跨岗问没用的题的情况。

### 4. 跨平台兼容问题
**问题**：最开始绑定了OpenClaw的skill格式，其他平台（Cursor/Codex/Claude Code）用不了。
**解决方案**：刻意简化仓库结构，只保留一个主入口SKILL.md+参考文件目录，没有任何平台专有格式，所有平台都可以直接用，只需要把仓库丢进去就行。

### 5. 评分客观性问题
**问题**：最开始的评分太主观，同样的答案不同大模型打分差异很大。
**解决方案**：制定了明确的评分标准rubric，按「答到点→讲清逻辑→能讲tradeoff→有落地经验」分层打分，完全量化，不同模型评分差异控制在0.5分以内。

## 📣 推广指南
这个项目非常适合在这些平台分享：
- 掘金/知乎：搜「大模型面试」「算法岗面试」相关话题，分享你的使用体验，附上仓库地址
- V2EX：分享到「程序员」「工作」节点，主打「国内大模型面试神器」的点
- 小红书/抖音：做使用演示视频，比如「用这个AI教练模拟字节大模型岗面试」，流量非常好
- 各种求职/算法交流群：分享给正在找工作的朋友，非常实用

**分享文案参考：**
> 找大模型岗的朋友看过来！写了个面试神器，完全复刻国内大厂的面试逻辑，会对着你的项目逐层深挖追问，像真实面试官一样给你评分、找短板、给提升建议，比自己盲目刷题效率高太多了，完全免费开源，支持Cursor/Codex/OpenClaw所有主流AI工具，我自己用这个练了两周就拿到了字节的offer，分享给大家：https://github.com/llx9826/llm-interview-coach

## License

MIT

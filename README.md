# llm-interview-coach

一个面向中文场景、偏真实大厂风格的 `Codex skill`，用于准备大模型算法岗、应用算法岗、RAG/Agent 岗、推理优化岗、训练/微调岗的技术面试。

它不是一个泛泛的“通用面试助手”，而是一个强调下面几件事的面试训练器：

- 项目深挖
- 指标、baseline、失败案例
- 中文大厂常见问法
- 岗位分型
- 个性化训练闭环

## 设计目标

按第一性原理，技术面试准备的核心只有 4 件事：

1. 生成高价值问题
2. 识别真实短板
3. 用追问暴露问题
4. 形成可执行训练闭环

这个 skill 围绕这 4 件事设计，没有引入不必要的复杂度。

## 适用岗位

- 大模型算法工程师
- LLM / GenAI 应用算法工程师
- RAG / Agent 工程师
- 推理优化 / Serving 工程师
- 训练 / 微调 / 对齐工程师
- 部分研究型岗位

## 核心能力

- `mock`
  一次只问一道题，随后继续追问，不直接把答案全部摊开。

- `drill`
  按主题生成刷题清单，适合集中补某一类短板。

- `review`
  评审面试答案、项目表述、简历 bullet，指出风险点并改写。

- `plan`
  生成 7 天或 14 天准备计划，按二八法则聚焦高频、高杀伤力问题。

- `project`
  对项目做高强度深挖，重点问目标、baseline、贡献、指标、失败和 tradeoff。

- `personalize`
  根据候选人的背景、项目和目标岗位建立画像，生成个性化题库和训练顺序。

## 适合什么场景

- 你要准备中文大厂 LLM 算法面试
- 你要练项目深挖
- 你知道自己基础不差，但一到追问就答虚
- 你想做 7 天、14 天的高密度冲刺
- 你希望围绕自己的经历做长期训练，而不是刷泛题

## Skill 结构

```text
llm-interview-coach/
├── SKILL.md
├── README.md
└── references/
    ├── question-bank.md
    ├── china-bigtech.md
    ├── rubric.md
    ├── roles.md
    ├── project-deep-dive.md
    ├── diagnostic-output.md
    └── personalization.md
```

## 各文件作用

- `SKILL.md`
  主入口，定义触发词、模式和使用流程。

- `references/question-bank.md`
  大模型面试核心题库。

- `references/china-bigtech.md`
  中文大厂风格题型、追问方式和常见压力测试。

- `references/rubric.md`
  回答评分标准。

- `references/roles.md`
  岗位分型，不同岗位问法不同。

- `references/project-deep-dive.md`
  项目深挖模板。

- `references/diagnostic-output.md`
  每轮 mock 后的标准化诊断格式。

- `references/personalization.md`
  候选人画像、短板地图和个性化训练原则。

## 设计原则

### 1. 中文优先

默认按中文工作，适配中文大厂算法面常见风格。只有用户明确要求英文时才切换。

### 2. 项目优先

真实面试里，项目深挖比背概念更容易拉开差距。  
因此题库不是唯一核心，项目追问树才是。

### 3. 岗位分型

应用算法岗、推理优化岗、训练岗、研究岗，本来就该问不同的东西。  
这个 skill 会先判断岗位类型，再决定题目密度和追问方向。

### 4. 个性化优先于通用题库

如果候选人已经给出项目和背景，不应该继续刷大量泛题。  
应该优先围绕真实项目、已暴露的短板和目标岗位高频题训练。

### 5. 追问比标准答案更重要

很多候选人第一问能答，第二问就开始虚。  
所以这个 skill 强调 follow-up，而不是只给“标准答案大全”。

## 使用示例

### 1. 直接做 mock

```text
用 llm-interview-coach 帮我做中文大厂大模型算法岗 mock interview
```

### 2. 做个性化训练

```text
用 llm-interview-coach 按我的项目和背景做 personalize 模式
```

### 3. 练项目深挖

```text
用 llm-interview-coach 深挖我这个 RAG 项目
```

### 4. 生成 7 天计划

```text
用 llm-interview-coach 给我做一个大模型算法岗 7 天学习计划，按二八法则来
```

### 5. 复盘一段答案

```text
用 llm-interview-coach review 我这段关于 LoRA 的回答
```

## 题型覆盖

核心覆盖主题包括：

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

## 适合开源吗

适合。

原因：

- 主题足够垂直
- 中文场景差异明确
- 结构简单，容易复用
- 没有绑定私有数据
- 有明显的方法论，不只是题库堆砌

## 后续可以继续增强的方向

- 公司风格进一步细分
- 英文算法面版本
- 简历解析和高风险问点抽取
- 针对不同 seniority 的难度分层
- 面试记录的长期记忆层

## License

你可以根据自己的开源计划补充许可证，例如 `MIT`。


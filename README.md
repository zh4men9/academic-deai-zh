# Academic De-AI 中文版

这是 `academic-deai` 的中文镜像版本，用于帮助中文用户理解和维护这个开源 skill。  
它的目标不是处理中文学术写作，而是以中文说明的方式，驱动对**英文**学术文本进行安全、克制、可追踪的去 AI 味处理。

## 对应仓库

- 英文主版本仓库：[zh4men9/academic-deai](https://github.com/zh4men9/academic-deai)

## 定位

这个 skill 适用于以下英文文本：

- journal / conference manuscript
- abstract
- introduction
- related work
- discussion / conclusion
- cover letter
- rebuttal / response letter

它要解决的是：

- 模板化 academic prose
- 空泛褒义与过度 significance claim
- 机械转折和自我宣告式 scaffolding
- 低风险表面残留，如缺空格、图号空格、全角编号

它**不**追求：

- 让文本更像聊天
- 增加 personality / warmth / humor
- 为了更顺口而牺牲技术精度
- 悄悄改事实、引文关系、结果力度

## 目录结构

```text
academic-deai-zh/
├── SKILL.md
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
├── agents/
│   └── openai.yaml
├── benchmark-demo/
│   ├── README.md
│   ├── cases.md
│   └── results.md
├── examples/
│   ├── README.md
│   └── prompts.md
└── references/
    ├── claim-calibration.md
    ├── core-rules.md
    ├── diagnostic-checklist.md
    ├── manual-check-items.md
    ├── non-goals.md
    ├── rewrite-patterns.md
    ├── section-guidance.md
    ├── surface-hygiene.md
    ├── transparent-reporting.md
    ├── validation-rubric.md
    └── workflow.md
```

## 默认 v3 行为

当前默认策略：

- `Claim Mode = balanced`
- 允许的 edit level 为 `No-op` / `Micro-edit only` / `Full safe rewrite`
- 默认启用透明报告
- 非平凡改写前必须做 `Detail Preservation Guard`
- 改写后必须做 `Residual Scan`

对于整篇论文，默认必须分章节处理，而不是全文一次性重写。

## 标准输出块

为保持英文版与中文版一致，输出块名称保留英文原名：

- `Diagnosis`
- `Edit Level`
- `Claim Mode`
- `Priority Fixes`
- `Revised Text`
- `Risk Check`
- `Manual Check Items`
- `Skipped High-Risk Items`
- `Unchanged Suspicious Items`
- `Verdict`

这三个风险块必须分开：

- `Manual Check Items`：已经改了，但改动仍有解释风险
- `Skipped High-Risk Items`：因为风险过高而故意不改
- `Unchanged Suspicious Items`：没改，但仍残留低风险可疑表达或表面问题

## Claim Mode

该 skill 保留与英文版完全一致的三档 claim mode：

- `closer to source`
- `balanced`
- `conservative`

其中：

- `closer to source`：更贴近原文强调力度
- `balanced`：默认档，既去 AI 味，也不过度收窄
- `conservative`：仅在用户明确要求更保守时使用

## 版本迭代

### v1

v1 建立了最初的 academic-safe 去 AI 味框架：

- diagnosis-first
- conservative rewrite
- section-aware editing
- 明确禁止 casual humanization
- 默认保护 technical meaning、citation intent 和 scholarly tone

这一版证明了 skill 在低风险 prose 上可用，但高风险场景还比较依赖人工判断。

### v2

v2 加入了“受控自动化 + 独立风险清单”：

- 引入 `No-op` / `Micro-edit only` / `Full safe rewrite`
- 引入 `Manual Check Items`
- 加强 related work、citation-sensitive prose、高风险 technical text 的约束
- 使整篇论文处理更容易落地

这一版的主要进步是降低了人工重读全文的负担，但报告仍可能偏乐观。

### v3

v3 把此前靠人工 QA 收敛出来的经验正式写成能力：

- `balanced` 成为默认 claim mode
- 引入 `Detail Preservation Guard`
- 引入 `Residual Scan`
- 引入透明报告三分法
- 引入 `Surface Hygiene`
- 强化 related work 的 citation-sensitive compression
- 强化高风险段落的 symbol-safe micro-edit

这一版是面向开源整理后的稳定结构版本。

## 维护策略

- **英文版是主版本**
- 中文版以翻译同步为主，尽量不独立发散
- 英文版变更时，建议按以下顺序同步：
  1. 更新英文 `SKILL.md`
  2. 更新英文 `references/`
  3. 更新英文 `README.md`
  4. 翻译并同步中文版
  5. 重新验证两版 skill

## 对应英文版

英文主版本单独维护于：

- [zh4men9/academic-deai](https://github.com/zh4men9/academic-deai)

如果后续要继续维护，优先改英文版，再同步中文版。

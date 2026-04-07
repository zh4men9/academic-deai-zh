# Workflow

## 1. Triage

改写前必须识别以下五项：

- genre：manuscript、cover letter、rebuttal 或 review response
- section：abstract、introduction、related work、methods、results、discussion、conclusion 或其他
- risk level：low、medium 或 high
- sensitivity：ordinary、citation-sensitive 或 symbol-bearing
- claim mode：`closer to source`、`balanced` 或 `conservative`

默认 claim mode 为 `balanced`。

## 2. Diagnostic Pass

改写前先使用 diagnostic checklist。

需要看：

- AI-like prose signals
- citation-sensitive comparison structure
- 不可丢失的 concrete detail
- deterministic surface residue，例如断句、缺空格、图号空格、全角编号

## 3. Risk Classification

默认按以下方式分类：

### Low-risk text

- abstract wording
- introduction framing
- conclusion inflation
- cover-letter stiffness
- 不含 citation-sensitive comparison 的 general background prose

### Medium-risk text

- related work synthesis
- citation-heavy synthesis
- attribution-bearing contrast sentences
- discussion claims
- reviewer-response tone

### High-risk text

- methods
- experimental setup
- exact numerical result interpretation
- theorem-like language
- statistical wording
- symbol-bearing technical paragraphs

## 4. Detail Preservation Guard

在接受任何非平凡 rewrite 前，检查 revision 是否删除或削弱了：

- named algorithms
- datasets 或 environments
- enumerations
- scoped qualifiers
- comparison bases
- evidence-linked conditions

如果 concrete detail 丢失，执行以下之一：

- 退回 `Micro-edit only`
- 保留原文
- 在 `Risk Check` 中显式说明该问题

不要把具体列表直接压没。更安全的做法通常是压缩列表周围，而不是压缩列表本身。

## 5. Edit Decision

必须显式选择一个 edit level。

### No-op

- 当文本已经 specific、proportionate、non-templated 时使用
- 优先于不必要的 smoothing

### Micro-edit only

- high-risk 文本默认使用
- citation-sensitive 文本默认使用
- symbol-bearing 文本默认使用
- 仅允许改动：空转折、重复 novelty framing、夸张副词、reminder phrases、不必要重复、过宽 scope language、deterministic surface cleanup
- 不要实质性重构句子
- 不要改动 inline math、variable-bearing spans、embedded objects 或 definition skeletons

### Full safe rewrite

- 仅用于 low-risk 文本
- medium-risk 文本只有在 attribution、evidence linkage 和 claim calibration 仍然清楚时才可使用

## 6. Manual Check Items

只有 changed sentence 仍然存在实质风险时，才生成单独的 `Manual Check Items` 块。

常见触发条件：

- claim strength 的变化影响了解释
- exact quantitative result 周围的 wording 改了
- attribution-bearing 或 citation-bearing sentence 被重写
- methods、procedure 或 assumptions sentence 被重写
- causal explanation 被重写
- generality scope 被缩窄或扩大
- definition-like sentence 被改成了更描述性的句子
- edit 需要在 precision 和 fluency 之间做 tradeoff

不要用 `Manual Check Items` 去装 skipped high-risk candidates 或 unchanged suspicious residue。

## 7. Transparent Reporting

改写后，必须把 residual uncertainty 分成三类：

- `Manual Check Items`：已经改了，但仍需 review 的 changed text
- `Skipped High-Risk Items`：因为安全改写会越界，所以故意不改的文本
- `Unchanged Suspicious Items`：改写后仍存在的 low-risk 或 surface-level residue

不要把所有不确定性都压进 `Manual Check Items`。

## 8. Residual Scan

在任何 rewrite pass 之后，都要扫描 unchanged text 中是否还存在：

- residual low-risk AI-like prose
- broken sentence boundaries
- missing sentence 或 label spacing
- figure/table label formatting residue
- full-width numbering 或其他明显的 surface-style mismatch

把这些写入 `Unchanged Suspicious Items`。

## 9. Post-Edit Audit

任何 rewrite 之后，都要检查：

- meaning preservation
- detail preservation
- claim calibration consistency
- citation anchoring
- tone consistency
- 是否引入了比原文更 generic 的 prose
- changed / skipped / unchanged reporting 是否真实透明，而不是过度乐观

## 10. Whole-Document Rule

绝不要把整篇 manuscript 当成一段文本一次性重写。必须 section by section 处理。

推荐顺序：

1. abstract
2. introduction
3. related work
4. discussion
5. conclusion
6. methods 或 results，仅在用户明确要求时处理
7. 最后执行 residual scan 和 transparent reporting

## 11. Escalation Rule

如果文本存在严重的 factual、citation、logic 或 formatting 问题，而这些问题不属于 stylistic editing，应单独 flag 出来，并把 de-AI edits 保持最小。

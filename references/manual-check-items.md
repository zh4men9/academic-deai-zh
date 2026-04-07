# Manual Check Items

只有当**已经改过的文本**仍存在实质解释风险时，才把它放进 `Manual Check Items`。

## 这个块负责什么

用于：

- 已经改写，但解释上仍可能影响判断的句子
- 有风险的 claim recalibration
- 有风险的 citation-bearing rewrites
- 有风险的 methods 或 result wording changes
- 有风险的 causal 或 scope changes

不要用于：

- 因高风险而故意不改的文本
- 没改但仍可疑的低风险残留
- harmless 的低风险清理

这些分别属于 `Skipped High-Risk Items` 或 `Unchanged Suspicious Items`。

## 何时生成

若 edit 满足以下任一条件，就生成 checklist item：

- 改变了会影响解释的 claim strength
- 改变了 exact quantitative result 周围的措辞
- 重写了 citation-bearing 或 attribution-bearing sentence
- 重写了 methods、procedure 或 assumptions sentence
- 重写了 causal explanation
- 缩窄或扩大了 generality scope
- 把 definition-like sentence 改成了更描述性的句子
- 为了兼顾 precision 和 fluency 做了明显 tradeoff

对于 deterministic surface cleanup 或无解释风险的轻微模板清理，不要生成 checklist item。

## 必填字段

每个 checklist item 必须包含：

- `Location`
- `Original fragment`
- `Revised fragment`
- `Risk type`
- `Why it needs review`
- `Suggested reviewer question`

## 质量标准

好的 checklist 应当：

- specific
- short
- 一条只对应一个真实 changed risk
- 让人一眼就能 review

坏的 checklist 通常会：

- generic
- repetitive
- 讨论 unchanged text
- 讨论 skipped text
- 长到相当于重新做一遍全文人工编辑

## 示例

- `Location`: sentence 2
- `Original fragment`: "clearly demonstrating remarkable superiority and strong generalizability across all settings"
- `Revised fragment`: "in the evaluated setting"
- `Risk type`: result-scope narrowing
- `Why it needs review`: 改写改变了结论听起来有多宽
- `Suggested reviewer question`: Does the revised scope still match what the experiment was intended to claim?

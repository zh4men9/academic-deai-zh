# Section Guidance

## Title / Keywords

- Intervention level: very low
- Default edit level: `No-op` 或 `Micro-edit only`
- Goal: 只去掉明显 generic 或冗余的词
- Avoid: creative rebranding 或修辞性 embellishment

## Abstract

- Intervention level: medium
- Default edit level: `Full safe rewrite`
- Goal: 提高 density、specificity、restraint 和 sentence economy
- Remove: generic setup、空 motivation、夸张 contribution wording
- Keep: exact task、method、evidence、scope 和 concrete detail
- 默认使用 `balanced` claim mode，除非用户明确另选

## Introduction

- Intervention level: low to medium
- Default edit level: `Micro-edit only` 或 `Full safe rewrite`
- Goal: 降低 thesis-template rhetoric 和空泛的 field-level motivation
- Remove: 不能推进本文实际设定的 broad claims
- Keep: problem framing、gap statement、contribution logic 和 named constraints

## Related Work

- Intervention level: low
- Default edit level: `Micro-edit only`
- Goal: 在减少重复 scaffolding 的同时保留 comparison logic 和 citation structure
- Remove: 仅当比较关系仍清楚时，才压缩重复的 "X proposed" pattern
- Keep: cited works 之间的 attribution 和 distinction
- 在压缩语言前，先保住 attribution skeleton
- 保持每篇 cited method 与其描述之间的一一对应
- 如果 substantively 重写了 citation-bearing comparison、contrast sentence 或 multi-citation synthesis line，加入 `Manual Check Items`

## Methods

- Intervention level: very low
- Default edit level: `Micro-edit only`
- Goal: 保留 precision
- Remove: 只删不触及 technical content 的明显公式化措辞
- Avoid: 可能改变 definitions、procedure、assumptions 或 symbol-bearing clauses 的 paraphrase
- 不要改动 inline variables、equation-bearing spans 或 definition skeletons
- 如果 methods、procedure 或 assumptions sentence 的改写超出 micro-edit 范围，加入 `Manual Check Items`
- 如果安全清理必须重构 technical skeleton，则写入 `Skipped High-Risk Items`

## Experiments / Results

- Intervention level: very low
- Default edit level: `Micro-edit only`
- Goal: 让 findings 保持 exact 和 proportionate
- Remove: findings 周围的 formulaic narration
- Avoid: 让 uncertainty、magnitude、comparison basis、datasets 或 environments 变模糊的 smoothing
- 保留 named algorithms、datasets、environments 和 comparison bases
- 对 exact quantitative wording、causal explanations、scope changes，加入 `Manual Check Items`
- 如果 symbol-bearing technical prose 无法通过 micro-edit 安全改进，则写入 `Skipped High-Risk Items`

## Discussion

- Intervention level: low
- Default edit level: `Micro-edit only` 或 `Full safe rewrite`
- Goal: 收紧 interpretation，让 implications 保持成比例
- Remove: 夸大的 significance 和 generic impact language
- Keep: evidence-linked interpretation 和已写出的 limitations
- 如果 edit 改变了 causal explanation 或 generality scope，加入 `Manual Check Items`

## Conclusion

- Intervention level: medium
- Default edit level: `Full safe rewrite`
- Goal: 去掉 recap clichés 和无支撑的 future-impact claims
- Remove: generic 的 "in summary" 式结尾，以及结果不支持的 broad claims
- Keep: 论文真实 takeaways 和合理 future work
- 默认使用 `balanced` claim mode
- 如果 rewrite 改变了解释层面的 claim strength、cause 或 scope，加入 `Manual Check Items`

## Cover Letter

- Intervention level: medium
- Default edit level: `Full safe rewrite`
- Goal: direct、professional、non-robotic
- Remove: stiff templates 和 exaggerated self-praise
- Keep: venue fit、contribution summary 和 procedural politeness

## Rebuttal / Response Letter

- Intervention level: low to medium
- Default edit level: `Micro-edit only` 或 `Full safe rewrite`
- Goal: respectful、evidence-based、steady
- Remove: canned gratitude、defensive phrasing 或公式化过度平滑
- Keep: exact reviewer-response mapping 和 concrete changes

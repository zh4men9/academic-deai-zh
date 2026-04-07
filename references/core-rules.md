# Core Rules

这些规则优先于一切风格偏好。若某个可能的 edit 与以下任一规则冲突，则不要做该 edit。

## Hard Constraints

- 不要新增 facts、data、citations、methods 或 claims
- 不要增强 novelty、significance 或 generality claims
- 不要为了“更自然”而削弱本来合理的技术精度
- 当技术措辞是必须的时，不要用 generic prose 替换 discipline-specific wording
- 不要改变 citation relationships、attribution 或 evidential anchoring
- 除非用户明确要求，否则不要重写 equations、variable definitions、theorem statements 或 exact result claims
- 默认不要注入 first person、contractions、idioms、humor 或 conversational markers
- 不要在未被要求时悄悄修 factual 或 bibliographic 问题
- 如果原文已经足够自然，应建议 minimal edits 或 no edits
- 当某个 edit 改变了 claim strength、exact quantitative wording、citation-bearing prose、methods wording、causal explanation、generality scope 或 definition-like sentence 时，应输出 `Manual Check Item`

## Positive Goal

目标不是“更像真人聊天”，而是让 scholarly prose 变得：

- less templated
- more specific
- more proportionate
- more natural in sentence rhythm
- 同时仍然 formal、objective、evidence-disciplined

## Safety Preference Order

当两个 edit 互相冲突时，优先级如下：

1. meaning preservation
2. citation 和 evidence preservation
3. claim proportionality
4. precision
5. stylistic naturalness

## Practical Rule of Thumb

如果一个 edit 让文本更顺，但同时也变得更 generic、更不精确、更强势，或更难追溯到证据，就拒绝这个 edit。

## Manual Check Principle

并非每个 rewrite 都需要人工复核。只有在以下情况下才使用 `Manual Check Items`：

- 改动在解释层面确实有风险
- 人工确认能明显降低不确定性
- 为保护 precision 不得不牺牲 fluency，或反之

不要为了 harmless 的低风险清理而制造 checklist 噪声。

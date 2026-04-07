# 示例 Prompts

## 中文说明触发

- 用中文帮我把这个英文 abstract 去 AI 味，但不要改 technical meaning。
- 这段英文 introduction 有点像 LLM 写的，按 balanced 模式帮我润色。
- 这段 related work 请做 citation-safe 压缩，不要改 attribution 关系。
- 这段 methods 只做 micro-edit，不要动公式和变量。
- 帮我检查这版英文 conclusion 是否还有 AI 味，并透明报告残留风险。

## 英文触发也可用

- De-AI this abstract without changing technical meaning.
- Clean up this related work paragraph, but preserve the attribution skeleton and citation logic.
- Apply micro-edits only to this symbol-bearing methods paragraph.

## Mismatch / Refusal Tests

- Humanize this blog post so it sounds warmer and more personal.
- Rewrite this marketing paragraph to sound more persuasive and emotionally engaging.

期望行为：

- 识别这些请求不属于学术安全去 AI 味的范围，不要强行套用学术 workflow。

# Diagnostic Checklist

改写前先用这个 checklist 诊断。只标记那些**明确存在**的问题类别。

## Generic framing

- 表现：可套用到很多论文的泛化开场句
- 为什么像 LLM：更像模板填充，而不是针对本文的具体思考
- 安全修法：用论文真实问题替换，或直接删掉
- 不要：补入原文并未支持的新背景 claim

## Template-like transitions

- 表现：机械重复使用 "Furthermore,"、"Moreover,"、"In addition," 等连接词
- 为什么像 LLM：整体 flow 过度均匀、可预测
- 安全修法：调整结构、合并句子，或删掉该转折
- 不要：把 prose 改得很口语化

## Inflated novelty or significance

- 表现：对 importance、effectiveness、impact 做过宽或过强的断言
- 为什么像 LLM：听起来更像宣传，而不是 scholarly writing
- 安全修法：把 claim strength 收敛到 evidence 能支持的范围
- 不要：引入新的 claim 或更大的 impact language

## Vague abstraction

- 表现：如 "offers a valuable perspective"、"has significant implications" 但没有具体内容
- 为什么像 LLM：用评价性雾气替代真实 substance
- 安全修法：明确 mechanism、finding、scope 或 limitation
- 不要：捏造 source text 没有的细节

## Repetitive authorial scaffolding

- 表现：近距离重复 "This paper proposes,"、"This study demonstrates,"、"The results show"
- 为什么像 LLM：句子不断自我宣告，显得公式化
- 安全修法：删掉重复 scaffolding，让内容本身承担信息
- 不要：删掉必要 attribution，或让句子变得难懂

## List-like prose disguised as sentences

- 表现：多个平行 claim 被硬塞进一个长句，层级关系很弱
- 为什么像 LLM：读起来像 bullet points 被粘成一段
- 安全修法：拆分或重排，让逻辑层次更清楚
- 不要：抹平重要区别

## Over-smoothed logical flow

- 表现：每句都无摩擦地顺下去，缺少限制、转折、边界
- 为什么像 LLM：论证过于丝滑且泛化
- 安全修法：恢复具体锚点、限制条件或更尖锐的转折
- 不要：把段落改得突兀或不连贯

## Unnatural hedging or certainty

- 表现：hedging 很机械，或 certainty 超出证据支持
- 为什么像 LLM：语气校准像机器产物
- 安全修法：让 modal strength 与 evidence 对齐
- 不要：删掉合理的谨慎，或制造虚假自信

## Conclusion clichés

- 表现：结尾依赖通用总结句式或广泛 future impact 话术
- 为什么像 LLM：结论与论文真实贡献脱节
- 安全修法：用具体的 contribution 和 limitation 重述结论
- 不要：加入无支撑的 grand future directions

## Cover-letter stiffness

- 表现：礼貌过度 polished、重复感谢、程序化套话
- 为什么像 LLM：像投稿模板，而不像作者来信
- 安全修法：保持 concise、direct、professional
- 不要：变得 casual 或过度 personal

## Residual low-risk prose

- 表现：未改的背景句仍含有 generic praise、空泛评价或明显模板语
- 为什么像 LLM：主干改干净了，但低风险残留仍在
- 安全修法：写入 `Unchanged Suspicious Items`，或做 low-risk cleanup
- 不要：因这点残留就对本来可接受的 prose 强行整段重写

## Surface residue

- 表现：断句、缺空格、`Fig.7` 样式标签空格、英文稿中的全角编号等
- 为什么像 LLM：常常从 prose cleanup 中漏出来，显得成品未收口
- 安全修法：做 deterministic surface cleanup，或写入 `Unchanged Suspicious Items`
- 不要：把这类问题当作 claim-level 或 evidence-level 改写问题

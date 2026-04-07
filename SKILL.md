---
name: academic-deai-zh
description: 当用户希望在不改变 technical meaning、citation intent、evidential strength 和 scholarly tone 的前提下，降低英文学术写作中的 AI 痕迹时使用。适用于 de-AI abstract、让 introduction 少一点 LLM 味、在不改内容的情况下润色 manuscript 段落，或将 cover letter / response letter 改得更自然但仍然专业。默认使用 balanced claim calibration，限制高风险改动，并透明报告 changed risks、skipped high-risk items 和 unchanged suspicious residue。
metadata:
  short-description: 面向英文论文的平衡型去AI味与透明复核技能
---

# Academic De-AI 中文版

## Overview

当你需要对**英文**学术写作做 academic-safe 的去 AI 味处理时使用本 skill。目标是减少模板化、空泛化、夸张化或过于平滑的 LLM 痕迹，同时保留 meaning、evidence、citations 和学科语域下应有的正式性。

默认采用 diagnosis first、balanced claim calibration 和 transparent reporting。若文本已经足够自然，优先选择 minimal edits 或 no-op，而不是为了“更像真人”去硬改。若风险真实存在，则要么保持改动克制、要么写入 `Manual Check Items`、要么明确说明该处保持不改。

## When to Use

适用于以下场景：

- abstract
- introduction
- related work
- discussion 和 conclusion
- journal / conference cover letter
- rebuttal letter 和 reviewer response letter
- 明确要求“减少 AI 味但不改变技术内容”的段落级学术润色

典型触发语：

- “帮我把这个 abstract 去 AI 味。”
- “让这个 introduction 少一点 LLM 腔。”
- “不改 technical meaning，润色这段 manuscript prose。”
- “把这封 response letter 改得更自然但仍然专业。”

## When Not to Use

不要把本 skill 作为以下任务的主流程：

- equations、proofs、theorem statements、variable definitions
- references 和 citation formatting
- 原始 quantitative result statements，除非用户明确只要 style cleanup
- tables、figure captions、labels，除非用户明确要求
- 博客式 humanization
- marketing / promotional tone transformation
- creative writing
- 追求 personality、warmth、humor 或 chatty naturalness 的请求

如果请求更接近普通 humanization 而不是 scholarly editing，应明确指出不匹配，而不是硬套本 workflow。

## Default Workflow

1. 识别 genre、section、risk level，以及文本是否 citation-sensitive 或 symbol-bearing。
2. 先诊断 AI-like signals，再决定是否改写。
3. 对任何非平凡 rewrite，先执行 `Detail Preservation Guard`。
4. 明确选择一种 `Edit Level`：`No-op`、`Micro-edit only`、`Full safe rewrite`。
5. 只有在确有必要时才输出 revised text，随后执行 `Residual Scan`。
6. 最后用透明报告输出 changed risks、skipped high-risk items 和 unchanged suspicious residue。

如果处理整篇论文，必须 section by section，而不是全文一次性改写。默认顺序是 abstract、introduction、related work、discussion、conclusion；methods 和 results 只有在用户明确要求时再处理。

## Claim Calibration

必须显式选择一个 claim mode：

- `closer to source`
- `balanced`
- `conservative`

默认使用 `balanced`。只有当用户明确要求更贴近原文强调力度时才使用 `closer to source`；只有当用户明确想更保守时才使用 `conservative`。

## Edit Levels

必须显式使用以下 edit level 之一：

- `No-op`
  - 当 prose 已经足够具体、克制、非模板化时使用
  - 可以直接建议不做实质改写

- `Micro-edit only`
  - 当最安全的做法只是删除空转折、重复 novelty framing、夸张副词、轻微 scaffolding 或表面残留时使用
  - 这是 high-risk、citation-sensitive、symbol-bearing 文本的默认档

- `Full safe rewrite`
  - 仅用于 low-risk academic prose
  - 可以重组句子，但 meaning、evidence、claim calibration 和具体细节必须保留

## Mode Selection

必须显式使用以下 mode 之一：

- `Diagnostic mode`
  - 当用户先问“这段是不是像 AI 写的”或要求先看问题时使用
  - 输出：`Diagnosis`、`Priority Fixes`，以及必要的透明报告块

- `Conservative rewrite mode`
  - 当用户明确要求改写时使用
  - 输出：`Diagnosis`、`Edit Level`、`Claim Mode`、`Revised Text`、`Risk Check`，以及必要的透明报告块

- `Final audit mode`
  - 当用户给出改写后文本，或要求做 final check 时使用
  - 输出：`Verdict`、`Diagnosis`、`Risk Check`，以及必要的透明报告块

默认路由：

- “这段像 AI 写的吗？” -> `Diagnostic mode`
- “把这段改得少一点 AI 味。” -> `Conservative rewrite mode`
- “帮我检查现在这个版本是否安全。” -> `Final audit mode`

## Output Blocks

统一使用以下块名：

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

`Manual Check Items`、`Skipped High-Risk Items` 和 `Unchanged Suspicious Items` 必须保持独立，不要埋在普通说明文字中。

## Risk Rules

- methods、experimental setup、exact result interpretation、theorem-like language、symbol-bearing paragraphs 这类高风险文本，默认先诊断，且默认 `Micro-edit only`
- citation-heavy related work、multi-citation comparisons 和 attribution-bearing contrast sentences 即使不属于高风险，也属于 citation-sensitive
- 对 named algorithms、datasets、environments、enumerations、scoped qualifiers、comparison bases 的压缩，必须先过 `Detail Preservation Guard`
- 改写后必须执行 `Residual Scan`，把 unchanged low-risk residue 和 deterministic surface hygiene issues 显式报出来
- 绝不增强 claims、捏造 evidence、改变 citation relationships
- 绝不用 fluency 交换 precision
- 如果文本已经足够自然，应建议不再修改
- 如果某个高风险改进必须重构 technical skeleton，保持不改，并写入 `Skipped High-Risk Items`

## Reference Routing

只读取需要的文件：

- `references/core-rules.md`：不可违背的安全约束
- `references/workflow.md`：triage、guards 和 full-document 流程
- `references/section-guidance.md`：按章节的编辑策略
- `references/diagnostic-checklist.md`：识别 AI-like signals 与 residual surface issues
- `references/rewrite-patterns.md`：安全改写模式
- `references/claim-calibration.md`：`closer to source` / `balanced` / `conservative`
- `references/manual-check-items.md`：checklist 触发条件和字段结构
- `references/transparent-reporting.md`：changed / skipped / unchanged 的报告规则
- `references/surface-hygiene.md`：确定性的非语义表面清理
- `references/non-goals.md`：决定哪些任务必须拒绝或避免
- `references/validation-rubric.md`：final audit 和验收标准

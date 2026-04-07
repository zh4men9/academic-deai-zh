# Claim Calibration

对于 results、discussion 和 conclusion 文本，必须显式使用一个 claim mode。

## 默认档

- 默认 mode：`balanced`

## 三种模式

### closer to source

- 当用户希望更贴近原文的强调力度时使用
- 只要原文的论证压力并非明显失据，就尽量保留
- 优先做轻度清理，而不是明显削弱 claim

### balanced

- 默认使用
- 降低明显夸张、空泛褒义和过宽 generality
- 在原文表述可辩护时，尽量保留作者的原始方向和强调重点
- 优先做成比例的清理，而不是过度保守

### conservative

- 仅当用户明确要求更保守时使用
- 更积极地收紧 scope 和 interpretive language
- 当支撑不确定时，优先改成更贴近 evaluated setting 的表述

## 决策顺序

不确定时，按以下顺序决策：

1. 保留 meaning
2. 保留 evidence linkage
3. 保留 concrete detail
4. 应用所选 claim mode
5. 优先选择侵入性更小的 rewrite

## 升级处理

如果两个可行 rewrite 在 claim pressure 上差异明显，则：

- 要么退回 `Micro-edit only`
- 要么把该改动写入 `Manual Check Items`

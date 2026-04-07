# Transparent Reporting

默认启用 transparent reporting。不要因为给出了一版“干净”的 rewrite，就把 residual risk 隐藏起来。

## 三类报告对象

### Manual Check Items

用于：已经改过，但改后仍存在实质风险的文本。

### Skipped High-Risk Items

用于：因为安全改写会触碰以下边界而故意保持不改的文本：

- 改动 inline math 或 symbol-bearing spans
- 重构 technical skeletons
- 削弱 precision
- 改变 attribution 或 evidence linkage

### Unchanged Suspicious Items

用于：没有改，但仍残留以下问题的文本：

- low-risk AI-like residue
- broken sentence boundaries
- missing spaces
- figure / table label spacing residue
- numbering-style mismatch

## 标准输出块

必须使用以下块名：

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

## 质量规则

- 三个 residual-risk buckets 必须分开
- 不要把 unchanged residue 报成 changed risky edit
- 不要把 skipped text 报成 revised text
- 若某一类为空，简短说明为空即可，不要静默省略
- 宁可给出一个简短但诚实的报告，也不要给一个过度干净、掩盖不确定性的报告

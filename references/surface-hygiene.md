# Surface Hygiene

这个 reference 用于处理确定性的低风险表面清理，不应把它误当成 claim-level rewrite。

## 覆盖的问题

- broken sentence-boundary spacing
- period 后缺空格
- `Fig. 7` / `Table 2` 这类标签空格
- 英文稿中的全角编号，如 `（1）` / `（2）`

## 原则

- 把它们当作 surface cleanup，而不是 semantic rewriting
- 只有在目标表面形式明确时，才应用 deterministic fix
- 如果问题看得见，但正确修法不明确，则写入 `Unchanged Suspicious Items`

## 安全示例

- `state.Different` -> `state. Different`
- `Fig.7` -> `Fig. 7`
- `（1）` -> `(1)`

## 不要做的事

- 不要借表面清理之名改写附近 technical content
- 不要悄悄改变 citation formatting 或 bibliographic style
- 当简单修 surrounding prose 就足够时，不要去动 inline equations 或 embedded objects

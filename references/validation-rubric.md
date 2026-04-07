# Validation Rubric

在任何 rewrite 之后，进入 final audit mode 时使用本 rubric。

## 1. Meaning preserved

- Pass: revised text 保留了原始技术意义和论证意义
- Borderline: meaning 基本保留，但有一句措辞可能轻微缩窄或放大了 scope
- Fail: rewrite 改变了文本真正表达的 claim

## 2. Claim strength preserved or properly softened

- Pass: claim 与原有 evidence 匹配，或在所选 claim mode 下被适当收敛
- Borderline: 有一句听起来比预期略强或略弱
- Fail: novelty、significance 或 generality 被实质改变

## 3. Citation and evidence relationships preserved

- Pass: attribution 和 evidence anchors 保持完整
- Borderline: 有一句可能让“哪条证据支撑哪项 claim”略微模糊
- Fail: rewrite 改变了 attribution、scope 或 evidential linkage

## 4. Detail preserved

- Pass: 重要的 named algorithms、datasets、environments、enumerations 和 scoped qualifiers 都保留了
- Borderline: 有一个具体细节被压缩了，但从上下文仍可恢复
- Fail: 有意义的 detail 被删除或模糊化

## 5. Academic tone naturalized without becoming informal

- Pass: 文本减少模板感，同时仍 formal 且 scholarly
- Borderline: 文本更干净了，但仍略机械，或稍微太顺
- Fail: 文本变得 casual、promotional、chatty 或过度会话化

## 6. Sentence rhythm improved without introducing generic prose

- Pass: prose 更自然，也更具体
- Borderline: rhythm 变好了，但有一处 edit 更 generic
- Fail: rewrite 为了更顺而牺牲了 specificity 或 discipline fit

## 7. Manual Check coverage

- Pass: 所有需要人工复核的 changed high-risk 或 citation-sensitive edits 都准确进入 `Manual Check Items`，且 checklist 有用不过噪
- Borderline: checklist 略吵，或漏了一个低严重度项
- Fail: checklist 漏掉了实质 changed review item，或被低价值项淹没

## 8. Transparent reporting coverage

- Pass: `Manual Check Items`、`Skipped High-Risk Items`、`Unchanged Suspicious Items` 三类分得正确
- Borderline: 有一个 residual item 被放错桶，但仍然可见
- Fail: residual uncertainty 被隐藏、压平或误报

## 9. Claim mode consistency

- Pass: 所选 claim mode 在类似句子上应用一致
- Borderline: 有一句轻微偏离所选 mode
- Fail: 输出混用了互相冲突的 calibration style，且未解释

## Audit Decision

- Safe: 九项全部 pass，或仅有轻微 borderline
- Needs revision: 存在一个或多个重要 borderline
- Unsafe: 任一项出现 fail

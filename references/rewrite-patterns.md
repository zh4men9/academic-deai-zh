# Rewrite Patterns

这些模式是 guide，不是可以盲套的公式。

## Abstract compression

**Before**  
This study aims to explore an effective framework for addressing the problem and provides valuable insights into how the proposed approach can improve performance in complex scenarios.

**Better**  
This study evaluates a framework for the task and shows how the proposed approach improves performance under the tested conditions.

**Why**  
改写去掉了 generic value language，只保留文本能支持的内容。

## Introduction de-templating

**Before**  
In recent years, this topic has attracted significant attention due to its broad applicability and considerable importance in many real-world settings.

**Better**  
This topic has received attention because it affects applications where the stated constraint directly limits performance.

**Why**  
改写用与论文设定直接相关的具体理由，替代了泛化的 field-level praise。

## Conclusion de-inflation

**Before**  
In summary, the results of this study highlight the substantial potential of the proposed method and provide important guidance for future research and practical deployment.

**Better**  
Overall, the results support the proposed method under the evaluated setting and suggest a limited set of directions for follow-up work.

**Why**  
改写让结论与 evidence 保持比例关系，避免了 grand impact language。

## Removing empty transitions

**Before**  
Moreover, it is worth noting that the model also shows improved robustness in several cases.

**Better**  
The model also shows improved robustness in several cases.

**Why**  
原本的转折只增加 polished 感，没有增加信息。删掉后节奏更自然、模板感更弱。

## Making claims more proportionate

**Before**  
These findings demonstrate that the proposed approach is highly effective and broadly applicable.

**Better**  
These findings suggest that the proposed approach is effective in the evaluated setting.

**Why**  
改写保留了积极结果，但去掉了无支撑的 scope 扩张。

## Preserving cautious academic hedging

**Before**  
This may potentially indicate that the method could possibly be useful in other domains.

**Better**  
This suggests that the method may be useful in related domains.

**Why**  
改写去掉了堆叠 hedges，但保留了合理的谨慎度。

## Detail-preserving compression

**Before**  
We selected six representative methods for evaluation, including Method A, Method B, Method C, Method D, Method E, and Method F, because each represents a different family of approaches.

**Better**  
We selected six representative methods for evaluation: Method A, Method B, Method C, Method D, Method E, and Method F, each representing a different family of approaches.

**Why**  
改写压缩的是列表周围的冗余，而不是把具体列表本身压没。

## Citation-sensitive compression

**Before**  
Smith et al. propose a density-based method, while Lee et al. introduce a contrastive alternative. By contrast, Chen et al. focus on reward shaping rather than state novelty.

**Better**  
Smith et al. propose a density-based method, Lee et al. a contrastive alternative, and Chen et al. a reward-shaping approach rather than a state-novelty method.

**Why**  
改写减少了 scaffolding，但保留了 attribution skeleton 和 comparison logic。

## Symbol-safe micro-edit

**Before**  
It is important to note that the optimal x values may vary depending on the specific characteristics of the environment and the algorithm being used.

**Better**  
The optimal x values may vary with the environment and algorithm.

**Why**  
改写删掉的是 reminder-style framing，而不是带变量的结构本身。

## Cover-letter naturalization

**Before**  
We sincerely believe that our manuscript will be of great interest to the readership of the journal and would be highly suitable for publication in your esteemed venue.

**Better**  
We believe the manuscript fits the journal because it addresses the stated topic and may be relevant to its readership.

**Why**  
改写保留了专业的 venue-fit 语言，但去掉了夸张的尊称和自我推销。

## Rebuttal naturalization

**Before**  
We greatly appreciate the reviewer's insightful and valuable comments, which have significantly helped us improve the quality and clarity of the manuscript.

**Better**  
We thank the reviewer for the comment. We clarified this point in the revised manuscript and now state the assumption explicitly.

**Why**  
改写把 canned politeness 转成了具体回应内容，同时不显得无礼。

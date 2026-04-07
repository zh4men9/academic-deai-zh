# Sample Results

下面是一些紧凑的 synthetic 演示，不是完整 benchmark 输出。

## B01 Abstract compression

**Before**  
This study aims to explore an effective framework for addressing the problem and provides valuable insights into how the proposed approach can improve performance in complex scenarios.

**Expected output style**  
This study evaluates a framework for the task and shows how the proposed approach improves performance under the tested conditions.

**Why**  
改写去掉了 generic value language，只保留有支撑的内容。

## B03 Related-work compression

**Before**  
Smith et al. propose a density-based method, while Lee et al. introduce a contrastive alternative. By contrast, Chen et al. focus on reward shaping rather than state novelty.

**Expected output style**  
Smith et al. propose a density-based method, Lee et al. a contrastive alternative, and Chen et al. a reward-shaping approach rather than a state-novelty method.

**Why**  
改写缩短了 prose，但没有打乱 attribution mapping。

## B04 Detail preservation

**Before**  
We selected six representative methods for evaluation, including Method A, Method B, Method C, Method D, Method E, and Method F, because each represents a different family of approaches.

**Expected output style**  
We selected six representative methods for evaluation: Method A, Method B, Method C, Method D, Method E, and Method F, each representing a different family of approaches.

**Why**  
压缩的是列表周围的冗余，而不是把具体列表压掉。

## B05 Symbol-safe micro-edit

**Before**  
It is important to note that the optimal x values may vary depending on the specific characteristics of the environment and the algorithm being used.

**Expected output style**  
The optimal x values may vary with the environment and algorithm.

**Why**  
改写删掉了 reminder-style phrasing，但保留了带变量的结构。

## B06 Surface hygiene

**Before**  
state.Different settings are shown in Fig.7. The two groups are denoted by （1） and （2）.

**Expected output style**  
state. Different settings are shown in Fig. 7. The two groups are denoted by (1) and (2).

**Why**  
这属于 deterministic cleanup，不是 semantic rewriting。

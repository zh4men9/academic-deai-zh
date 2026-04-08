# Academic De-AI 中文版

一个开源的 Codex skill，用于在**不改变技术含义、引文关系、证据力度和学术语气**的前提下，降低中文学术写作中的 AI 痕迹。

这个 skill 面向中文论文和中文学术沟通文本，而不是普通“润色得更像真人聊天”的 humanizer。它的目标是让中文学术 prose **更少模板味、更少空泛套话、更成比例、更具体**，同时保持正式、可追溯、可复核。

## 对应英文母版

- 英文能力母版仓库：[zh4men9/academic-deai](https://github.com/zh4men9/academic-deai)

中文版不是镜像说明层，而是**中文论文场景的强同步双生版**：

- 同步英文版的 workflow、guards、edit levels 和 reporting structure
- 本地化中文论文的触发语、诊断信号、章节指导、示例和 benchmark

## 安装方式

### Codex

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/zh4men9/academic-deai-zh.git ~/.codex/skills/academic-deai-zh
```

### Claude Code

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/zh4men9/academic-deai-zh.git ~/.claude/skills/academic-deai-zh
```

### 更新

如果你把 skill 装在 Codex：

```bash
git -C ~/.codex/skills/academic-deai-zh pull
```

如果你把 skill 装在 Claude Code：

```bash
git -C ~/.claude/skills/academic-deai-zh pull
```

### 验证

可以直接对 agent 说：

- `帮我把这段中文摘要去 AI 味，但不要改技术含义。`
- `这段中文引言有点像 AI 写的，按平衡档位帮我润色。`
- `这段相关工作请保留归因关系，只做压缩和去模板化。`

## 这个 skill 做什么

- 处理中文论文摘要、引言、相关工作、方法、实验结果、讨论和结论
- 处理中文投稿附信和中文回复信
- 默认使用**平衡**论断档位，而不是一味收窄
- 使用**章节感知**与**风险感知**的编辑规则
- 用 `仅微调` 约束高风险段落
- 用透明报告区分已改风险、跳过风险和未改残留

最适合的请求包括：

- “帮我把这段中文摘要去 AI 味。”
- “让这段引言少一点模板感，但不要改问题设定。”
- “把这段结论改得更自然，但不要过度收窄论断。”
- “检查这段方法是否还有 AI 味，只允许做微调。”

## 这个 skill 不做什么

- 它不是博客或营销文案 humanizer
- 它不是参考文献修复工具
- 它不是事实修正器
- 它不是期刊格式化工具
- 它不是以牺牲精确性为代价的流畅度最大化器
- 它不能替代真正高风险学术修改的人审

## 目录结构

```text
academic-deai-zh/
├── SKILL.md
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
├── agents/
│   └── openai.yaml
├── benchmark-demo/
│   ├── README.md
│   ├── cases.md
│   └── results.md
├── examples/
│   ├── README.md
│   └── prompts.md
└── references/
    ├── claim-calibration.md
    ├── core-rules.md
    ├── diagnostic-checklist.md
    ├── manual-check-items.md
    ├── non-goals.md
    ├── rewrite-patterns.md
    ├── section-guidance.md
    ├── surface-hygiene.md
    ├── transparent-reporting.md
    ├── validation-rubric.md
    └── workflow.md
```

## 当前默认行为（v3）

当前默认策略：

- `论断档位 = 平衡`
- `编辑级别` 从 `不改` / `仅微调` / `安全重写` 中选择
- 默认启用透明报告
- 非平凡改写前必须做 `细节保留检查`
- 改写后必须做 `残留扫描`

对于整篇论文，默认必须按章节处理，而不是全文一次性重写。

## 标准输出块

本 skill 默认使用以下中文输出块：

- `诊断`
- `编辑级别`
- `论断档位`
- `优先修复项`
- `修订文本`
- `风险检查`
- `人工复核项`
- `跳过的高风险项`
- `未修改但可疑项`
- `结论`

三类残余风险必须分开：

- `人工复核项`：已经改了，但改后仍需人工判断
- `跳过的高风险项`：因为安全边界而故意不改
- `未修改但可疑项`：没改，但仍残留低风险套话或表层问题

## 论断档位

本 skill 支持三档论断校准：

- `贴近原文`
  - 当用户明确要求更忠实于原文强调力度时使用
- `平衡`
  - 默认档；在去 AI 味的同时尽量保留作者原始重点
- `保守`
  - 仅当用户明确要求更收敛、更谨慎时使用

## 安全模型

本 skill 围绕以下优先级设计：

1. 保留技术含义
2. 保留引文与证据关系
3. 保留具体细节
4. 让论断力度与证据匹配
5. 只在前四项不受损时提升自然度

高风险文本，如方法、精确结果、统计表述、符号密集段落，默认使用 `仅微调`。如果安全改进必须改动技术骨架，本 skill 会显式报告，而不是假装已经安全重写。

## 版本迭代

### v1

v1 建立了最初的中文学术安全去 AI 味框架：

- diagnosis-first
- conservative rewrite
- section-aware editing
- 明确禁止 casual humanization
- 默认保护技术含义、引文关系和学术语气

这一版证明了低风险中文 prose 可以安全改善，但高风险场景仍较依赖人工判断。

### v2

v2 引入了“受控自动化 + 独立风险清单”：

- 引入 `不改` / `仅微调` / `安全重写`
- 引入 `人工复核项`
- 强化相关工作、引文敏感 prose 和高风险技术段的约束
- 改善整篇论文的处理纪律

这一版降低了人工通读全文的负担，但报告仍可能偏乐观。

### v3

v3 正式把之前依赖人工 QA 的经验固化成能力，并把仓库重定义为**中文论文场景的双生版**：

- `平衡` 成为默认论断档位
- 引入 `细节保留检查`
- 引入 `残留扫描`
- 引入透明报告三分法
- 引入 `表层卫生`
- 强化相关工作的归因骨架保护
- 强化高风险段落的符号安全微调
- 不再把中文仓库定位为“帮助处理英文论文”的镜像说明层

## 维护策略

- **英文版是能力架构母版**
- **中文版是中文论文场景的强同步双生版**
- 同步的是：
  - workflow
  - guards
  - edit levels
  - transparent reporting structure
  - benchmark categories
- 本地化的是：
  - 中文论文的套话信号
  - 中文章节表达
  - 中文输出块
  - 中文示例与 benchmark

英文版更新后，建议按以下顺序同步中文版：

1. 更新英文 `SKILL.md`
2. 更新英文 `references/`
3. 判断哪些规则属于结构同步，哪些需要中文语料本地化
4. 更新中文版 `SKILL.md` 和 `references/`
5. 更新中文版 `README.md`
6. 更新 `examples/` 与 `benchmark-demo/`
7. 重新运行校验

## 对应英文版

- [zh4men9/academic-deai](https://github.com/zh4men9/academic-deai)

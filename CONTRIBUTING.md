# 贡献指南

感谢你为 `academic-deai-zh` 做贡献。

## 仓库定位

这是 `academic-deai` 的**中文镜像版**，用于帮助中文用户理解和维护这个 skill。  
它处理的目标仍是**英文**学术文本，而不是中文学术写作。

## 维护原则

- 英文仓库是 source of truth：
  - [zh4men9/academic-deai](https://github.com/zh4men9/academic-deai)
- 中文仓库以翻译同步为主
- 除非有非常明确的理由，否则不要让中文版行为独立发散

## 欢迎的贡献

- 提高清晰度的中文翻译改进
- 修复中英结构不一致
- 同步英文版新增规则
- 改进中文示例和 benchmark/demo 说明
- 修复术语前后不一致问题

## 请避免

- 把中文版改造成独立于英文版的另一套 skill
- 引入与英文版不一致的默认行为
- 为了中文表达流畅而改变原本的风险边界
- 不更新 `CHANGELOG.md` 就修改关键行为

## 更新清单

当行为或文档发生变化时，建议按以下顺序处理：

1. 若涉及行为，先确认英文版是否已同步更新
2. 更新中文版 `SKILL.md`
3. 更新对应的 `references/`
4. 更新 `README.md`
5. 更新 `CHANGELOG.md`
6. 如有必要，更新 `examples/` 与 `benchmark-demo/`
7. 运行 `quick_validate.py`

## 最低验证要求

至少确认：

- skill 结构仍然合法
- 输出块名称仍保持一致
- 风险报告仍明确区分：
  - `Manual Check Items`
  - `Skipped High-Risk Items`
  - `Unchanged Suspicious Items`

## 发布说明

如果本次变更会影响用户行为，请在 `CHANGELOG.md` 中补一条简明记录。

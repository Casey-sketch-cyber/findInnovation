# findInnovation

找创新点、判断创新点的共用方法，给所有研究项目和所有 AI（Claude、Codex、Gemini、GPT）以及人使用。

**Skill：** [`skills/research-innovation-points/SKILL.md`](skills/research-innovation-points/SKILL.md)

## 包含什么

- **建立领域视野（文献树）**：找里程碑论文，向前向后追引用，按时间线整理每条脉络，回答“领域视野六问”，按里程碑任务归类 pipeline。
- **难点—解法树**：每个难点有哪些解法、还空着什么、别的数据域有没有同内核的解法。
- **找课题的五个来源**：视野六问、failure case、新锤子用到自己的领域、从工程问题提炼科学问题、从用户需求出发。
- **四种情况判断选题**：按彭思达选题课件的原文定义，并注明课件没有给四种情况排序。
- **判断与排序**：实用价值、技术创新、影响范围、发展空间与竞争、通用性、当下可解、与条件匹配、区别类型；检查三个常见误区和贡献不足风险。
- **发散与选择**：从稳到激进的多个方案、方法设计循环、创新层级，最后定一个核心贡献加一个有时间上限的大胆尝试，以及第一个实验。
- **价值优先的判断原则**：看增量价值和与已有工作的区别，不因“有人做过类似的”就否定方向；只有已被简单方法解决、做不了、或不改变任何决定时才换题。

## 文件

| 文件 | 作用 |
| --- | --- |
| [`skills/research-innovation-points/SKILL.md`](skills/research-innovation-points/SKILL.md) | 方法本身 |
| [`templates/LITERATURE_TREE_TEMPLATE.md`](templates/LITERATURE_TREE_TEMPLATE.md) | 文献树模板，产出放在项目仓库的 `docs/literature-tree/literature-tree-vN.md` |
| [`templates/INNOVATION_ASSESSMENT_TEMPLATE.md`](templates/INNOVATION_ASSESSMENT_TEMPLATE.md) | 创新点评估模板，产出放在项目仓库的 `docs/INNOVATION.md` |

## 怎么用

**Claude：** 作者的 Claude 账号里装有同名 skill（research-innovation-points），本仓库是参考副本。两边任何一边改了，另一边也要同步。

**Codex / Gemini / GPT，在别的项目仓库里：** 在该仓库的 `AGENTS.md` 或 `GEMINI.md` 里加一行：

```
When choosing a topic, building a literature tree or judging innovation points, first read and follow
https://github.com/Casey-sketch-cyber/findInnovation/blob/main/skills/research-innovation-points/SKILL.md
and use the templates in https://github.com/Casey-sketch-cyber/findInnovation/tree/main/templates
```

项目自己的内容（文献树、检索记录、创新点评估）放在项目仓库里，不放在这里。

**和写论文的 skill 怎么衔接：** 定下核心贡献以后，用 [Casey-sketch-cyber/paperwrite](https://github.com/Casey-sketch-cyber/paperwrite) 里的 research-paper-story-writing 写论文故事。

**实际用例：** [Casey-sketch-cyber/gnn2gsnn](https://github.com/Casey-sketch-cyber/gnn2gsnn) 的 `docs/literature-tree/`，是本方法整理成 skill 之前的一次应用。注意它的草稿里写了“前两种换题、第三种适合新手、第四种适合高手”，课件原文没有这个说法，以本仓库为准。

## 来源与致谢

方法改编自彭思达公开的科研经验材料。引用或改编本仓库内容时，请注明这些来源：

- 彭思达，learning_research：https://github.com/pengsida/learning_research
- 彭思达，《如何建立领域视野和选择科研课题》课件（2025-08-12）：https://pengsida.net/files/research_topic_selection.pdf
- 彭思达，learning research 课件 v4：https://pengsida.net/files/learning_research_v4.pdf
- GAMES003《图形视觉科研基本素养》第 1 讲（科研流程与领域视野）、第 3 讲（技术方案的设计方法）：https://pengsida.net/games003/

价值优先的判断原则来自作者自己的研究偏好。

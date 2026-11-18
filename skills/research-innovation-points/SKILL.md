---
name: research-innovation-points
description: Use when choosing a research topic, building a literature tree for a field, generating research ideas or innovation points, or judging and positioning novelty and value, including after a literature search finds similar prior work.
---

# Finding and judging research innovation points

This skill combines two things:

1. **Peng Sida's method** for building domain vision (a literature tree), finding topics and ideas, and judging topics (the "four situations", "Aim high", common traps, method-design steps).
2. **A value-first way of judging ideas**: an idea is worth doing when it adds clear, incremental value with a meaningful distinction from prior work, not only when it is absolutely original.

Use the whole workflow when a topic is still open. When the topic is fixed and the question is only "how do we differ from paper X", jump to Stage 5 and Stage 7.

Write all outputs in the user's language. Quote Peng's definitions in the original Chinese where this file does.

Reference copy and templates: https://github.com/Casey-sketch-cyber/findInnovation. Keep the Claude account copy of this skill and that repository in sync.

## Core principles

1. **Value over originality.** Judge an idea by its value to a named user or field and by its room to advance. Never end a discussion with "someone has already done it".
2. **Similar work is not a verdict; solved work is.** Drop or change a topic only when (a) a simple method or a plain combination of existing methods (A+B) already solves it well, (b) it cannot be done with the available time, data, compute or people, or (c) it would not change anyone's decision. Peng's rule: if A+B or a simple method already solves the problem well, change the topic decisively.
3. **Aim high within reach.** Peng: "Aim high: 选择个人能力范围内最重要的科研课题。" Importance first, then feasibility.
4. **Evidence before claims.** Every paper placed in the tree, and every "no one has done X", rests on sources actually opened, with a search date. Unverified items are marked as such.
5. **Divergence is welcome.** Generate ideas from the problem and from what a decision-maker (designer, user, practitioner, policymaker) needs; use the literature to position ideas, not to generate or veto them. Not every published paper is good: build on or contrast explicitly with large, validated or replicated studies; cite single cases, conceptual analyses or weak venues briefly and don't let them shape the study design.
6. **Immature ideas get a development path, not a rejection.** Say concretely how the idea could be developed further.
7. **One point per paper.** A paper should make one coherent point well. Prefer one solid core contribution plus at most one bold bet.

## Stage 0. Frame the search

Write down, in a few lines:

- **Long-term goal and who needs it.** Peng distinguishes goal-driven research (set a long-term goal, plan a roadmap of milestone tasks) from idea-driven research (start from a SOTA paper and its failure cases; easy to start, but limited room and easy to collide with others). Prefer goal-driven framing even for a single paper.
- **Constraints.** Time to submission, compute (GPU type and memory), data access and licences, code skills, whether human participants or raters are available, target venue level.
- **Contribution types acceptable at that venue.** Top venues usually expect a new method. Applied or journal papers can also rest on a new setting or benchmark with ground truth, a failure analysis, a practical guideline, a dataset, or a cheaper or more robust pipeline.

## Stage 1. Build the literature tree (领域视野)

Domain vision has two sides: how the technology evolved (技术演变) and which problems matter (重要问题). Peng's steps:

1. **Find milestone papers.** Take the most-cited papers of the field and sort them by date; ask experienced researchers.
2. **Trace backward and forward.** Backward: what each milestone builds on. Forward: who cites it. Tools: Connected Papers, Semantic Scholar, OpenAlex, Google Scholar, arXiv listings.
3. **Read each paper for three things:** the problem it solves, its pipeline, its technical insight.
4. **Place papers on a timeline per strand** and label each as milestone or follow-up, judged by how new the method is.
5. **Summarize the paradigm of each milestone** and what the follow-ups improved.
6. **Track the problems year by year** and name the current hot topics.
7. **Answer the six vision questions:** milestone papers; how the technology evolved; the field's ultimate goal; the level it has reached; the important unsolved problems; the current hot topics.

Also group papers by **milestone task**, and for each task record the representative pipelines (Peng's 文献树: list most papers of the direction, group them by milestone task, then group the pipelines within each task).

Breadth: match the vision to the ability and time available. A newcomer or a short project needs two to four tightly chosen strands, not the whole field.

For an applied or cross-disciplinary topic, use one strand per side, for example "the AI technique", "the application domain's current practice", "how results in this area are evaluated".

**Output:** `docs/literature-tree/literature-tree-vN.md` in the project repository, using `templates/LITERATURE_TREE_TEMPLATE.md` from the findInnovation repository. Keep each version; never overwrite a reviewed version.

## Stage 2. Build the challenge–insight tree (难点—解法树, the "weapon store")

For each milestone task, list:

- the **technical challenges** that made earlier methods fail;
- the **techniques or insights** that addressed each challenge, with the paper;
- what is **still unsolved**, and in which data domain or setting.

Note where the same technical core appears in a different data domain. This feeds the third of the four situations below.

## Stage 3. List candidate topics and ideas

Use several generators, and record which one produced each candidate:

1. **The vision questions.** Each important unsolved problem from Stage 1 is a candidate.
2. **Failure cases.** Push the current SOTA to harder data, settings or users ("探索算法的上限，尝试更具有挑战性的cases"). Peng notes that finding new failure cases on new data and publishing the new findings can itself be a large contribution. Then separate surface symptoms from the real technical challenge ("抽离表面问题得到真正的technical challenge").
3. **A new hammer for your field (新技术 应用 你的领域).** List what a new technique can do, list the essential technical difficulties of your field's important problems, and connect the two. Peng calls this the simplest and most efficient route, provided the technique is understood deeply rather than bolted on.
4. **From engineering problem to scientific problem.** Is there still large room for improvement in practice? Which important problems remain? What is their root cause from first principles?
5. **From the user's need.** Start from the product or decision a practitioner wants, and measure the gap between current research and that need.

Define each candidate by its **setting (input and output)** and its **technical problem or failure case**.

## Stage 4. Classify each candidate by the four situations

Peng classifies topics by how much of the problem is already solved, and whether the same technical core is solved in other data domains. Definitions, quoted from his topic-selection slides:

1. "同样输入输出的任务，已经有了不错的解决方案，只是有些地方做得还不够好。"（例：如何煮熟猪肉）
2. "输入或输出有所变化的任务，已经有了不错的解决方案。或者在多个完全不同data domain、技术问题内核相同的任务中，都有了不错的类似解决方案。"（例：如何煮熟某种肉）
3. "只有少数一两个完全不同data domain、技术问题内核相同的任务，有不错的解决方案。"（例：如何煮熟并且不煮老某种肉）
4. "在各个不同领域的任务中，虽然有类似的技术问题，但都没有较好的解决方案。"（例：如何快速地煮熟并且不煮老某种肉）

The slides say only that "不同问题的创新空间区别很大"; they do not rank the four situations or assign them to beginners or experts. Do not attribute such a ranking to Peng. This skill's reading, to use with care:

- **Situation 1**: room is in doing something better; crowded; watch for the "obvious answer" trap. Worth doing only with a clear, measurable distinction.
- **Situation 2**: transfer to a new input, output or domain. Common for applied and journal papers. The contribution must show what actually changes in the new setting (new failure modes, new constraints, new users), not just that the method still runs.
- **Situation 3**: borrow a solution from one or two distant domains that share the technical core. Often good room with manageable risk.
- **Situation 4**: an open problem everywhere. Largest room and highest risk; needs a fallback.

Also note the task type: well-defined tasks (lower risk, less competition, less room) suit beginners and short projects; ill-defined tasks (higher risk, more room, more competition) suit experienced researchers.

## Stage 5. Judge and rank

Score each candidate in a table. Ratings are judgements, so write one line of reasoning for each.

| Criterion | Question to answer |
| --- | --- |
| Practical value | Who needs this, and how urgently? Peng: industry needs drive practical value; ask practitioners. |
| Technical innovation | Is there no good answer yet? Peng: problems without good answers drive technical innovation. |
| Scope of impact | How many subfields or users need it solved? |
| Room and competition | Peng's ideal topic: "发展空间大、竞争程度小". |
| Generality | Is the failure case or problem general, with few qualifiers? |
| Solvability now | Can current techniques plausibly solve it this year (technology readiness)? |
| Fit | Does the difficulty match the people, time, compute and data? |
| Distinction | Which kind of distinction from prior work (list below)? |

**Kinds of distinction** (any one, stated in one concrete sentence per prior strand): overcomes a limitation of current solutions; improves the user experience; meets a new need (new users, contexts or conditions); reframes the problem; offers a more effective method (more accurate, robust, scalable, cheaper or faster); tests or generalizes an existing claim at larger scale or in a new setting.

**Check Peng's three common traps** for each top candidate:

1. Choosing a topic with an obvious answer ("倾向于去做有明显答案的课题"). Typical outcome: the paper gets done, then rejected repeatedly or accepted and rarely read.
2. Starting the first doable topic without ranking topics by importance.
3. Choosing an important problem that is not ready this year, because the technology or the team is not ready.

**Check the reasons Peng gives for "insufficient contribution":** the failure case addressed is too rare; the technique used is already well explored, so the gain is predictable.

**Sort** by importance first, then keep only what fits the constraints.

## Stage 6. Diverge, then design the idea

Propose three to five options, ordered from incremental to radical. For each give the distinctive value, the feasibility and cost, and the decision it would change.

For method ideas, follow Peng's method-design loop:

1. **Analyse causes** from first principles: why is the current SOTA not good enough? Run its code, collect failure cases, use ablations or bisection to localize the cause.
2. **List the causes, then all techniques that could address them**, then prefer a recent technique that is not yet well explored and leaves room for imagination (未被 well-explored、有想象空间).
3. **Design at the pipeline level**, not as small patches.
4. **Check plausibility** by discussion and by reading analyses of the technique.
5. **Iterate** like gradient descent: evaluate the idea, compare experiment and target, change the idea, many variants.

Place the idea on Peng's innovation levels, from highest to lowest: a new paradigm; a very novel module in an existing pipeline; a new pipeline combining existing modules; an existing pipeline with a simply improved module; an existing pipeline with an existing module. Lower levels can still be publishable in applied venues when the distinction and value are clear; say so explicitly rather than overselling.

## Stage 7. Choose, plan the first experiment, and state the value

- **Core contribution**: the defensible point that holds even if the bet fails.
- **Bold bet**: one more ambitious element with a fixed time box and a fallback, and a note on how it connects to the person's own expertise.
- **First experiment**: the smallest experiment that would confirm or kill the core. Peng: reduce the number of exploration points in each experiment; start from controllable parts and simple settings, add one exploratory element at a time.
- **Development path** for anything immature: next step, evidence needed, what would make it publishable.
- **Value proposition** in one sentence: what is turned into what, for whom.

Then hand over to the paper-writing skill (research-paper-story-writing, repository Casey-sketch-cyber/paperwrite) for the story.

**Output:** `docs/INNOVATION.md` in the project repository, using `templates/INNOVATION_ASSESSMENT_TEMPLATE.md`.

## Compact output (when there is no project repository or the question is quick)

**Value proposition:** one sentence.

**Positioning table**

| Strand / prior work | What it established | Limitation for our question | Evidence strength | What we add (kind of distinction) |
|---|---|---|---|---|

**Four-situation call** for the chosen topic, with one line of reasoning.

**Divergent options** (incremental to radical): name, distinctive value, feasibility and cost, decision it changes.

**Recommendation:** core contribution; bold bet with a time box and fallback; first experiment.

**Development path** for immature parts.

## Evidence and wording rules

- Search with dated queries and keep a search log (query, source, date, what was found).
- Open each paper before placing it in the tree or citing it. A search snippet is not a source. Record title, authors, year, venue and link.
- Mark anything not verified as "unverified" and list it under open items.
- Avoid "first", "novel" and "never done before" unless a documented search supports it and it matters. State contributions relative to named prior work.
- When close work turns up, describe the remaining difference precisely, adjust the study to add value, and keep going.
- Keep claims proportional to the evidence, for both the related paper and this work.
- When web search is not available, say so and label anything from memory as unverified.

## Sources and credit

The workflow adapts Peng Sida's public research guidance. Credit it when quoting or adapting this material:

- Peng Sida, learning_research: https://github.com/pengsida/learning_research
- Peng Sida, research topic selection slides (2025-08-12): https://pengsida.net/files/research_topic_selection.pdf
- Peng Sida, learning research slides v4: https://pengsida.net/files/learning_research_v4.pdf
- GAMES003 course slides, week 1 (research workflow and domain vision) and week 3 (designing technical solutions): https://pengsida.net/games003/

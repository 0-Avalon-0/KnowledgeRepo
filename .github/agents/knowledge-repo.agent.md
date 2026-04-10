---
name: knowledge-repo
description: "Use when: compiling sources into 来源笔记, extracting 概念/主题, maintaining 索引, or checking whether 来源笔记 have explicit candidate and compiled links back to the knowledge base."
---

# Knowledge Repo Agent

这个 agent 适用于当前仓库中的知识整理任务，重点不是直接生成长答案，而是维护知识库结构的一致性。

## 工作重点

1. 先从 `原始资料/` 或 `知识库/来源笔记/` 读取上下文。
2. 在来源笔记中区分“候选概念 / 候选主题”和“已编入条目”。
3. 对已经存在的概念页和主题页，优先使用显式 Markdown 链接回写到来源笔记。
4. 在新增或重编译条目时，优先复用已有概念页和主题页，避免重复造页。
5. 当知识库结构发生变化时，同步检查 `知识库/索引/`、`AGENTS.md` 与 workflow skill 是否仍然匹配。

## 输出约束

1. 不把一次性问答直接混入 `知识库/`。
2. 不把单一二手来源中的判断直接写成概念页或主题页的确定性结论。
3. 对尚未正式沉淀的条目，保留在来源笔记的候选区，而不是伪造链接。
4. 如果来源之间存在冲突，优先记录冲突与边界，而不是强行统一。
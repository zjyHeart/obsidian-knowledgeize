# obsidian-knowledgeize

英文版说明: [README.md](./README.md)

`obsidian-knowledgeize` 是一个 Codex skill，用来把普通 Markdown 笔记转换成更适合 Obsidian 知识库管理的笔记。

它的设计重点是: 在控制 token 消耗的前提下，对整个仓库中的笔记建立高质量链接关系。

- 先读取目标笔记
- 再扫描整个仓库中的笔记标题和路径
- 先筛出少量相关候选笔记
- 只在必要时读取最相关候选笔记的正文
- 保守地补充 frontmatter、标签、双向链接和导航区块

## 这个 Skill 做什么

这个 skill 可以帮助 Codex:

- 补充 Obsidian 风格的 YAML frontmatter
- 补充标签和别名
- 增加双向 `[[wikilinks]]`
- 增加导航区块, 比如总览入口、相关笔记、主题导航
- 在默认情况下优化笔记结构, 但不重写整篇正文

默认策略是“标题优先检索”。除非用户明确要求更深度的整理, 否则不会把整个仓库的正文全部读入上下文。

## 仓库结构

```text
obsidian-knowledgeize/
├── SKILL.md
├── README.md
├── README.zh-CN.md
├── agents/
│   └── openai.yaml
└── references/
    └── linking-strategy.md
```

## 使用方式

把这个 skill 放到 Codex 的 skills 目录下, 让系统自动发现。

典型提示词:

```text
Use $obsidian-knowledgeize to convert this Markdown note into an Obsidian knowledge-base note with tags and bidirectional links.
```

典型使用场景:

- 把单篇 Markdown 笔记知识化
- 为一篇笔记补充同仓库内的相关链接
- 在不全库读正文的前提下优化 Obsidian 导航
- 批量处理多篇笔记, 同时复用一次标题/路径索引

## 设计原则

- 优先做结构增强, 而不是全文重写
- 优先少量高价值链接, 而不是密集打链
- 优先复用已有笔记, 而不是大量新建占位页
- 优先扫描标题和路径, 再决定是否读取正文

## 说明

- skill 主体说明位于 `SKILL.md`
- 更细的链接策略位于 `references/linking-strategy.md`
- 这个仓库刻意保持最小结构, 便于后续维护

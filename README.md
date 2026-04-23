# obsidian-knowledgeize

Chinese version: [README.zh-CN.md](./README.zh-CN.md)

`obsidian-knowledgeize` is a Codex skill for turning ordinary Markdown notes into Obsidian-friendly knowledge-base notes.

It is designed for vault-scale note enhancement with controlled token usage:

- read the target note first
- scan note titles and paths across the vault
- choose a small candidate set of related notes
- read only the most relevant candidate bodies when needed
- add frontmatter, tags, wiki links, and navigation blocks conservatively

## What It Does

This skill helps Codex:

- add Obsidian-style YAML frontmatter
- add tags and aliases
- add bidirectional wiki links
- add navigation sections such as hub links and related-note links
- improve note structure without rewriting the whole document by default

The default strategy is title-first retrieval. It avoids reading the whole vault into context unless the user explicitly asks for deeper curation.

## Repository Structure

```text
obsidian-knowledgeize/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    └── linking-strategy.md
```

## Usage

Place this skill under your Codex skills directory so it can be discovered automatically.

Typical prompt:

```text
Use $obsidian-knowledgeize to convert this Markdown note into an Obsidian knowledge-base note with tags and bidirectional links.
```

Typical use cases:

- knowledgeize a single Markdown note
- add links from one note to related notes in the same vault
- improve Obsidian navigation without full-vault loading
- batch-process several notes while reusing a title/path index

## Design Principles

- Prefer structure-preserving enhancement over full rewriting
- Prefer sparse, high-value links over dense linking
- Prefer existing notes over creating many placeholder notes
- Prefer title/path discovery before reading note bodies

## Notes

- The skill body lives in `SKILL.md`
- Detailed linking heuristics live in `references/linking-strategy.md`
- This repository is intentionally minimal so the skill remains easy to maintain

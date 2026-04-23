---
name: obsidian-knowledgeize
description: Convert ordinary Markdown notes into Obsidian knowledge-base notes with frontmatter, tags, bidirectional links, navigation blocks, and knowledge-oriented structure. Use when Codex needs to knowledgeize one or more .md notes, add wiki links to related notes in the same vault, improve note discoverability, or turn linear notes into reusable knowledge cards without reading the entire vault into context.
---

# Obsidian Knowledgeize

Convert a plain Markdown note into an Obsidian-friendly knowledge note while keeping token use under control.

Prefer repository-aware linking over generic rewriting. Improve structure and retrieval value first; rewrite prose only when the user explicitly asks.

## Core Rule

Never read the full vault by default.

Use this retrieval order:

1. Read the target note.
2. Read only note titles and relative paths across the vault.
3. Select a small candidate set of potentially related notes.
4. Read only the top candidate notes whose titles suggest real relevance.
5. Add links only when the relation is defensible from the target note plus the inspected candidates.

If the vault is large, title-only discovery is the default behavior, not an optimization.

## Default Output

When knowledgeizing a note, prefer these upgrades:

- Add YAML frontmatter with concise tags and aliases when justified.
- Add a short `Knowledge Position` or `Note Position` section near the top.
- Add `Related Notes and Navigation` or an equivalent navigation section near the bottom.
- Add a small set of high-value `[[wikilinks]]` to related concepts, tasks, models, projects, or hub pages.
- Add a short `Further Split Ideas` section when the note is long and contains multiple separable ideas.

Do not force all sections if the note type does not need them.

## Workflow

### 1. Classify the target note

Decide what kind of note it is before linking:

- concept note
- summary note
- project or practice note
- task note
- paper note
- tutorial note
- index or MOC note

This determines what metadata and links are appropriate.

### 2. Build a cheap vault index

Discover only titles and paths first. Prefer fast file listing commands such as `rg --files -g "*.md"` or equivalent.

From paths and filenames, infer:

- note titles
- folder themes
- likely hub pages
- obvious siblings

Do not open note bodies yet.

### 3. Choose candidate notes

Select candidates using cheap signals:

- title token overlap
- shared entities or acronyms
- same model or task family
- same folder or neighboring folder
- likely parent-child relation such as overview vs detail
- likely theory-practice relation such as `RNN` vs `RNN Practice`

Keep the candidate set small. A good default is 3 to 8 notes.

If a relationship is obvious from title alone, linking without reading the candidate body is acceptable. Example: a note named `NLP-KB-Overview.md` is clearly a hub page.

### 4. Read only the candidates that matter

Open candidate bodies only when title evidence is insufficient to justify linking.

Prioritize candidates that may answer one of these questions:

- Is this really the same concept?
- Is this note a parent, child, sibling, or hub?
- Should the link be conceptual, navigational, or comparative?

Stop reading once the link set is good enough. Do not keep exploring for completeness.

### 5. Edit conservatively

Default to structure-preserving enhancement:

- keep the original body
- add metadata and navigation
- insert a small number of high-value links
- avoid turning every noun phrase into a wikilink

Prefer precision over density. Too many links reduce note quality.

## Link Selection Rules

Add links when at least one of these is true:

- the linked note is a direct prerequisite
- the linked note is a direct follow-up
- the linked note is the same topic at a different granularity
- the linked note is the theory behind the current practice note
- the linked note is a hub, map, or overview page
- the linked note is repeatedly referenced by the target note

Avoid links when:

- the relation is generic and weak
- the title match is accidental
- the concept is too broad to help navigation
- the vault does not already have a defensible target note

Prefer existing notes over creating many new placeholder notes unless the user asked for expansion.

## Link Density Rules

For a normal note, aim for a sparse, useful link set:

- 1 hub or navigation link
- 2 to 6 strong related-note links
- 0 to 5 concept links inside the body, only for central terms

Do not link the same term repeatedly in every paragraph.

## Metadata Rules

Keep frontmatter small and stable. Good defaults:

- `tags`
- `aliases`

Optional fields only when clearly useful:

- `source_type`
- `knowledge_type`
- `status`

Do not invent large metadata schemas unless the vault already uses one.

## Body Rewrite Rules

By default:

- do not rewrite the full note
- do not aggressively paraphrase
- do not reorganize every section

You may lightly normalize headings, add short framing blocks, and fix obvious structure issues.

Only do substantial rewriting when the user explicitly asks for summarization, polishing, or refactoring.

## Batch Mode

When the user asks to knowledgeize multiple notes:

- build the title/path index once
- process notes one by one
- reuse the same title index
- read additional note bodies only for each note's top local candidates

Do not preload the whole vault.

## References

Read [references/linking-strategy.md](references/linking-strategy.md) when you need the detailed candidate-selection and stop-reading heuristics.

# Markdown Cleanup

Use this file when the source text appears to come from GPT or another chat model and renders poorly in Obsidian.

## Goal

Normalize the note into Markdown that Obsidian renders reliably before adding knowledge links.

## Common Problems

### 1. Empty lines inside lists

Chat output often inserts empty lines between list items or between the marker and the continuation text.

Example:

```text
- item one

- item two
```

Preferred cleanup:

```text
- item one
- item two
```

For numbered lists:

```text
1. first

2. second
```

Preferred cleanup:

```text
1. first
2. second
```

## 2. GPT-style math delimiters

Obsidian usually works best with:

- inline math: `$...$`
- display math: `$$...$$`

Chat output often uses LaTeX delimiters:

- `\(...\)` for inline math
- `\[...\]` for display math

Convert them when they are clearly math delimiters.

Examples:

```text
\(x_1, x_2, \dots, x_n\)
```

becomes

```text
$x_1, x_2, \dots, x_n$
```

and

```text
\[
\mathbf{h}_t = f(\mathbf{x}_t, \mathbf{h}_{t-1})
\]
```

becomes

```text
$$
\mathbf{h}_t = f(\mathbf{x}_t, \mathbf{h}_{t-1})
$$
```

## 3. Do not damage code

Never apply math-delimiter conversion inside:

- fenced code blocks
- inline code spans
- literal examples that are clearly teaching syntax

## 4. Minimal cleanup principle

Only fix rendering problems that are clearly harmful:

- broken lists
- broken math delimiters
- unnecessary blank lines around headings or callouts

Do not perform broad reformatting just because the text looks slightly uneven.

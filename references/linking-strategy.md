# Linking Strategy

Use this file when the vault has many notes and you need a disciplined way to add links without reading everything.

## Objective

Find the smallest set of high-value related notes for the target note.

## Cheap Signals First

Use cheap signals before opening note bodies:

- exact title match
- shared acronym or model name
- same folder
- shared task family
- same chapter or course block
- overview/detail naming pattern
- theory/practice naming pattern

Examples:

- `RNN` and `RNN-Practice`
- `Transformer` and `Transformer-Project`
- `NLP-KB-Overview` and any topic note
- `Sequence-Labeling` and `BiLSTM-CRF`

## Candidate Ranking

Rank candidate notes roughly in this order:

1. Hub or overview pages
2. Same-topic notes with different granularity
3. Direct prerequisite notes
4. Direct follow-up notes
5. Same-folder siblings
6. Broad background notes

Stop after you have enough good links. Do not optimize for coverage.

## When Title Is Enough

You can link without reading the candidate body when the title/path relationship is obvious, such as:

- target note to a known vault index page
- theory note to matching practice note
- chapter summary to a named chapter note
- folder MOC to notes inside that folder

## When to Read the Candidate Body

Open the candidate note only if one of these is true:

- the title is ambiguous
- multiple notes compete for the same concept
- the link direction is unclear
- you need to know whether the note is conceptual or practical
- you need to confirm whether it is a hub or just a passing mention

## Stop Conditions

Stop exploring when all are true:

- the target note has one clear navigation path
- the strongest related notes are already linked
- extra links would be weak or repetitive
- you would need to read many more notes for little gain

## Practical Limits

Reasonable defaults for one target note:

- title scan: full vault
- candidate list: 3 to 8
- candidate bodies opened: 0 to 4

Exceed these limits only when the user explicitly asks for deep curation.

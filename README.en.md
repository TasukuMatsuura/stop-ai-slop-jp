English | [日本語](README.md)

# Stop AI Slop (Japanese Edition)

A Claude Skill for removing AI tells from Japanese prose. Japanese-language port of [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop).

> The skill content (`SKILL.md`, `references/*.md`) is written in Japanese. This English README exists for discoverability. If you write in Japanese with the help of an LLM, this is for you.

## What this is

AI-written Japanese has predictable patterns. Vocabulary, structure, rhythm. This skill teaches Claude (or any LLM) to catch and remove them. It covers Japanese-specific tells: false agency, 必殺技造語 (grandiose Sino-Japanese compounds used to inflate small stories), 命題型H2 (proposition-style headings borrowed from English SEO blogs), 両論併記 (both-sides-ism), and 書き手の不在 (the absence of a real writer behind the prose).

## Skill structure

```
stop-ai-slop-jp/
├── SKILL.md              # Core rules + quick checks + scoring
├── references/
│   ├── phrases.md        # Phrases to remove
│   ├── structures.md     # Structural patterns to avoid
│   └── examples.md       # AI / human transformation pairs
├── CHANGELOG.md
├── README.md
└── LICENSE
```

## Quick start

**Claude Code (personal)**
```bash
git clone https://github.com/iKora128/stop-ai-slop-jp ~/.claude/skills/stop-ai-slop-jp
```

**Claude Code (project)**
```bash
git clone https://github.com/iKora128/stop-ai-slop-jp <project>/.claude/skills/stop-ai-slop-jp
```

**Claude Projects**: Upload `SKILL.md` and `references/` to project knowledge.

**API**: Include `SKILL.md` in the system prompt. References load on demand.

## How to use

Before drafting, answer SKILL.md's three opening questions: what are you committing to, is there a falsifiable claim, how does this differ from the average article on this topic. After drafting, work the priority list top-down: stance → false agency → structure → vocabulary → symbols. For review, run the quick check.

Reading aloud catches the most. Patterns the eye misses surface immediately when spoken: uniform rhythm, breath-killing long sentences, monotone endings.

## What it catches

**Banned phrases** — old-style templates, throat-clearing openers, AI-favored abstract nouns (本質, 解像度, 文脈, …), grandiose Sino-Japanese compounds (真理, 虚飾, 禁欲的, …), IT-as-metaphor borrowings (思考のOSをアップデート, 人生をハック, …), hedges, conclusion avoidance, decorative emoji sprinkling. See `references/phrases.md`.

**Structural clichés** — false agency, proposition-style headings, hook-and-reversal openers, Wikipedia-style sentence compression, lack of variance, template repetition (体験 → quote → abstraction), binary contrasts (Not X. It's Y.), negative listing, dramatic fragmentation, both-sides-ism, missing edge. See `references/structures.md`.

**Symbol- and sentence-level** — full-width dashes (──), gratuitous Japanese corner brackets 「」, three-item parallelism, adverb stacking, `**` residue, decorative emoji.

## Scoring

Rate 1–10 on each dimension. Below 35/50: revise.

| Dimension | Question |
|---|---|
| Stance | Is there a falsifiable, specific claim? |
| Rhythm | Varied length, tone, conclusion? |
| Agency | Is "who did what" explicit? (no false agency) |
| Specificity | Descends from abstractions to the actual context? |
| Reduction | Anything cuttable? |

## Credits

- Inspired by: [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)
- Japanese pattern catalog and worked examples: [note article "その文章、AIに書かせただろ"](https://note.com/ikora/n/n0bbb2828b91e) (だいち | GENSHI AI)

## Author

Daichi Nagashima

## License

MIT. See `LICENSE`.

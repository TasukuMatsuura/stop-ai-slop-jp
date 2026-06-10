English | [日本語](README.md)

# Stop AI Slop (Japanese Edition)

A Claude Skill for removing AI tells from Japanese prose.

This is the Japanese-language port of [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop).

> The skill content (`SKILL.md`, `references/*.md`) is written in Japanese. This English README exists for discoverability. If you write in Japanese with the help of an LLM, this is for you.

## What it is for

Use this before publishing Japanese text drafted with an LLM.

It catches things like:

- Missing human agency: 課題が浮き彫りになる, 文化が醸成される
- Overbuilt headings: ○○が私たちに教えてくれること
- Small personal stories inflated into 真理, 美学, 境地
- Repeated structures: AではなくBだ, 3つの観点から
- Paragraphs with the same length, tone, and landing
- Full-width dashes, gratuitous 「」, leftover `**`, decorative emoji

The core problem is not the vocabulary list. It is prose with no visible writer. The skill pushes the model back toward who saw what, what bothered them, and what they are willing to say.

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

Before drafting, answer three questions:

- What are you willing to say plainly?
- Is the claim concrete enough to argue against?
- How is this different from the average article on the same topic?

After drafting, revise in this order:

1. Stance: what does the piece actually claim?
2. Agency: who did what?
3. Structure: headings, paragraphs, reversals, three-item lists
4. Vocabulary: AI-favored nouns, grandiose compounds, IT metaphors
5. Symbols: dashes, stray brackets, emoji, Markdown residue

Reading aloud catches the most. Patterns the eye misses surface immediately when spoken: uniform rhythm, breath-killing long sentences, monotone endings.

## What's inside

**SKILL.md**  
Principles, core rules, quick checks, and scoring.

**references/phrases.md**  
Words and phrases to consider removing: AI-favored nouns, translationese, hedges, IT metaphors, emoji.

**references/structures.md**  
Deeper patterns: false agency, proposition-style H2s, hook-and-reversal openings, uniform rhythm, both-sides-ism.

**references/examples.md**  
Before/after examples showing how to rewrite actual passages.

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
- Japanese pattern catalog and worked examples: [note "その文章、AIに書かせただろ"](https://note.com/ikora/n/n0bbb2828b91e) (だいち | GENSHI AI)

## Author

Daichi Nagashima

## License

MIT. See `LICENSE`.

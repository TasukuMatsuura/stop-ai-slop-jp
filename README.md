# Stop AI Slop(日本語版)

日本語の文章からAI臭を取り除く Claude Skill。

[hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop) の日本語版。日本語に固有のクセ(false agency、必殺技造語、命題型H2、両論併記、書き手の不在、など)を扱う。

## 構成

```
stop-ai-slop-jp/
├── SKILL.md
├── references/
│   ├── phrases.md
│   ├── structures.md
│   └── examples.md
├── CHANGELOG.md
├── LICENSE
└── README.md
```

## インストール

Claude Code(個人用):
```bash
git clone https://github.com/iKora128/stop-ai-slop-jp ~/.claude/skills/stop-ai-slop-jp
```

プロジェクト用:
```bash
git clone https://github.com/iKora128/stop-ai-slop-jp <project>/.claude/skills/stop-ai-slop-jp
```

Claude Projects: `SKILL.md` と `references/` をプロジェクトナレッジにアップロード。

API: `SKILL.md` をシステムプロンプトに含める。

## クレジット

- 着想元: [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)
- 日本語パターンの整理と実例: [noteの記事「その文章、AIに書かせただろ」](https://note.com/ikora/n/n0bbb2828b91e) (だいち | GENSHI AI)

## ライセンス

MIT。`LICENSE` を参照。

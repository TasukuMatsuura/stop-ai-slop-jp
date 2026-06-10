[English](README.en.md) | 日本語

# Stop AI Slop(日本語版)

日本語の文章からAI臭を取り除く Claude Skill。[hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop) の日本語版。

## これは何か

AI が書いた日本語には予測可能なパターンがある。語彙、構造、リズム。このスキルは Claude(あるいは任意の LLM)に、それらを検出して直すことを教える。日本語に固有のクセ(false agency、必殺技造語、命題型H2、両論併記、書き手の不在 など)を扱う。

## 構成

```
stop-ai-slop-jp/
├── SKILL.md              # コアルール + クイックチェック + 採点
├── references/
│   ├── phrases.md        # 撲滅すべき語彙
│   ├── structures.md     # 避けるべき構造パターン
│   └── examples.md       # AI版/人間版の対比
├── CHANGELOG.md
├── README.md
└── LICENSE
```

## インストール

**Claude Code(個人用)**
```bash
git clone https://github.com/iKora128/stop-ai-slop-jp ~/.claude/skills/stop-ai-slop-jp
```

**Claude Code(プロジェクト単位)**
```bash
git clone https://github.com/iKora128/stop-ai-slop-jp <project>/.claude/skills/stop-ai-slop-jp
```

**Claude Projects**: `SKILL.md` と `references/` をプロジェクトナレッジにアップロード。

**API**: `SKILL.md` をシステムプロンプトに含める。参照ファイルは必要に応じてロード。

## 使い方

下書きするときは SKILL.md 大原則の3問(何を引き受けているか / 反証可能か / 平均的な記事とどこが違うか)に答えてから書く。書いた後は修正の優先順位(立場 → false agency → 構造 → 語彙 → 記号)を上から潰す。レビューはクイックチェックを流す。

検出には音読が一番効く。目で読むと気づかない違和感が、口に出すと一気に出てくる。

## 何を捕まえるか

**禁止フレーズ** — 旧型の定型句、咳払いの前置き、AI偏愛語、必殺技造語、横文字メタファー、ヘッジ、結論回避、絵文字撒布など。`references/phrases.md` を参照。

**構造のクセ** — false agency、命題型H2、フック→反転、一文圧縮、ムラの欠如、テンプレ反復、二項対比、否定的列挙、劇的断片化、全方位肯定、毒の不在など。`references/structures.md` を参照。

**文・記号レベル** — 全角ダッシュ、不要なカギ括弧、3項目並列、副詞スタッキング、`**`残骸、装飾絵文字。

## 採点

5軸を1〜10で採点。35/50を下回ったら書き直す。

| 軸 | 質問 |
|---|---|
| 立場 | 反証可能な具体的主張があるか? |
| リズム | 長さ・トーン・結論にムラがあるか? |
| 主体性 | 誰が何をしたかが明示されているか? |
| 具体性 | 抽象語で終わらず、固有の文脈に降りているか? |
| 削減 | 削れる箇所はないか? |

## クレジット

- 着想元: [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)
- 日本語パターンの整理と実例: [noteの記事「その文章、AIに書かせただろ」](https://note.com/ikora/n/n0bbb2828b91e) (だいち | GENSHI AI)

## 作者

Daichi Nagashima

## ライセンス

MIT。詳細は `LICENSE` を参照。

[English](README.en.md) | 日本語

# Stop AI Slop(日本語版)

日本語の文章からAI臭を抜くための Claude Skill。

[hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop) の日本語版です。

## 何に使うか

AIで下書きした文章を、そのまま出す前に直すためのものです。

たとえば、こういう文章を捕まえます。

- 誰がやったのか分からない。「課題が浮き彫りになる」「文化が醸成される」
- 見出しだけ妙に大げさ。「○○が私たちに教えてくれること」
- 小さい体験を、急に「真理」「美学」「境地」まで膨らませる
- 「AではなくBだ」「3つの観点から」の型が続く
- 全段落が同じ長さ、同じ温度、同じ着地になる
- 全角ダッシュ、不要な「」、`**`の残骸、装飾絵文字が残る

中心にあるのは「書き手がいない感じ」です。語彙リストだけでは直りません。誰が何を見て、何に引っかかって、どこまで言い切るのかを戻す必要があります。

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

下書き前に、まず3つだけ決めます。

- 自分は何を「そうだ」と言うのか
- 反論できるくらい具体的な主張になっているか
- 同じテーマのよくある記事と、どこが違うのか

書いた後は、次の順で直します。

1. 立場: 何を言い切るのか
2. 主体: 誰が何をしたのか
3. 構造: 見出し、段落、反転構文、3項目並列
4. 語彙: 偏愛語、必殺技造語、横文字メタファー
5. 記号: ダッシュ、不要な「」、絵文字、Markdown残骸

検出には音読が一番効く。目で読むと気づかない違和感が、口に出すと一気に出てくる。

## 中身

**SKILL.md**  
大原則、コアルール、クイックチェック、採点表。

**references/phrases.md**  
消す候補の語彙。偏愛語、翻訳調、ヘッジ、横文字メタファー、絵文字など。

**references/structures.md**  
語彙より深いクセ。false agency、命題型H2、フックからの反転、ムラの欠如、両論併記など。

**references/examples.md**  
AI版と修正版の対比。実際にどう直すかを見るためのファイル。

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
- 日本語パターンの整理と実例: [note「その文章、AIに書かせただろ」](https://note.com/ikora/n/n0bbb2828b91e) (だいち | GENSHI AI)

## 作者

Daichi Nagashima

## ライセンス

MIT。詳細は `LICENSE` を参照。

# Changelog

## [0.1.2] - 2026-06-24

[iKora128/stop-ai-slop-jp](https://github.com/iKora128/stop-ai-slop-jp) (Daichi Nagashima, MIT) をフォークし、TasukuMatsuura/stop-ai-slop-jp で管理する版。元のMITライセンス・著作権表示・クレジットは保持。

### 追加

- 構造の系統7「構成を設計しない」を新設(structures.md): 総論→各論の崩れ、初出語の未説明、単語の羅列による散文の代替、DRY違反の散在
- SKILL.md コアルールに「D. 構成と情報設計」(ルール15〜18)を追加
- クイックチェック「構造レベル」に構成の4項目を追加
- リファレンス説明を「6系統」→「7系統」に更新
- frontmatter に `disable-model-invocation: true`(手動実行のみ)

### 方針

- このフォークは汎用の文章作法のみを扱う。社内固有の例・用語・機密情報は入れない(公開リポのため)

## [0.1.1] - 2026-06-10

READMEの書きぶりを整理。

### 変更

- 日本語READMEを、説明先行から使い方先行に変更
- 英語READMEも同じ構成に更新
- READMEの使い方を、実際にClaudeへ投げるプロンプト例中心に変更
- SKILL.mdのdescriptionと冒頭を少し短くした
- note本文と照合し、一人称の消失・一般論化・黙読時のリズム確認を補強

### 修正

- structures.md に残っていた「family 5/6」表記を「系統5/6」に統一
- SKILL.mdのチェックリストにだけあった「熱量」を phrases.md の偏愛語リストにも追加
- このファイルの日付区切りを em-dash からハイフンに変更

## [0.1.0] - 2026-06-01

初版。

### 含まれるもの

- 日本語のAI臭パターンを構造6系統と語彙8系統に整理
- AI版/人間版の対比例17本
- false agency、必殺技造語、無害さチューニング、英語ネイティブ思考の漏れなど、日本語特有の症状を反映

### 元ネタ

- [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop): 構造とフロントマター形式
- [noteの記事「その文章、AIに書かせただろ」](https://note.com/ikora/n/n0bbb2828b91e) (だいち | GENSHI AI): 日本語パターンの分類と実例

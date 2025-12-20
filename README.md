# ¡Hola México! 毎日わくわく冒険ノート

> 子ども向けメキシコ旅行情報ブログ - AI アシストによる教育コンテンツ制作プロジェクト

![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-active-brightgreen)
![Jekyll](https://img.shields.io/badge/Jekyll-Minima-red)

**ライブサイト**: [https://hfujikawa77.github.io/mexico-articles/](https://hfujikawa77.github.io/mexico-articles/)

---

## 概要

このプロジェクトは、子どもたちがメキシコの文化・歴史・自然を楽しく学べる教育ブログです。

AI を活用したコンテンツ制作により、以下の特徴を持つ高品質な記事を定期的に公開しています。

### 主な特徴

- **毎日更新される記事** - メキシコの様々なテーマを網羅的に紹介
- **4コママンガ風イラスト** - ChatGPT o3 で生成した視覚的に楽しいコンテンツ
- **音声解説** - NotebookLM による記事の読み上げ音声
- **スペイン語学習コーナー** - 発音リンク付きの実用的なフレーズ集
- **インタラクティブなクイズ** - 記事の理解度を確認できるクイズ
- **厳選された YouTube 動画** - 各記事に3本の関連動画を掲載
- **体験ミッション** - 子どもたちが実際に取り組める課題

---

## 技術スタック

| カテゴリ | 技術 |
|---------|------|
| **ホスティング** | GitHub Pages |
| **静的サイトジェネレーター** | Jekyll (Minima テーマ) |
| **コンテンツ生成** | Claude Code |
| **イラスト生成** | ChatGPT o3 |
| **音声生成** | NotebookLM |
| **スペイン語発音** | SpanishDict API |
| **バージョン管理** | Git / GitHub |

---

## セットアップ方法

### 前提条件

以下のツールをインストールしておいてください。

- **Git**: バージョン管理システム
- **GitHub アカウント**: リポジトリのホスティング用
- **テキストエディタ**: VS Code を推奨

### GitHub Pages の設定手順

1. **リポジトリのフォークまたはクローン**
   ```bash
   git clone https://github.com/YOUR_USERNAME/mexico-articles.git
   cd mexico-articles
   ```

2. **GitHub リポジトリの Pages 設定**
   - GitHub リポジトリページにアクセス
   - `Settings` → `Pages` を選択
   - `Source` を `main` ブランチに設定
   - 保存すると自動でデプロイが開始されます

3. **`_config.yml` の編集**
   ```yaml
   title: ¡Hola México! 毎日わくわく冒険ノート
   theme: minima
   timezone: Asia/Tokyo
   future: true
   ```

4. **変更をコミット&プッシュ**
   ```bash
   git add _config.yml
   git commit -m "Update configuration"
   git push origin main
   ```

5. **GitHub Actions で自動デプロイ**
   - プッシュ後、数分で自動的にサイトが公開されます
   - `https://YOUR_USERNAME.github.io/mexico-articles/` でアクセス可能

### ローカル環境での動作確認（オプション）

Jekyll をローカルで実行して、プッシュ前にプレビューできます。

```bash
# Ruby と Jekyll のインストール（詳細は Jekyll 公式サイト参照）
gem install bundler jekyll

# リポジトリのルートディレクトリで実行
jekyll serve

# ブラウザで以下にアクセス
# http://localhost:4000/mexico-articles/
```

---

## プロジェクト構成

```
mexico-articles/
├── _config.yml           # Jekyll 設定ファイル
├── _posts/               # 記事の Markdown ファイル（26+ 記事）
│   ├── 2025-07-09-title.md
│   ├── 2025-07-10-title.md
│   └── ...
├── assets/               # 画像・音声ファイル
│   ├── 2025-07-09-comic.png
│   ├── 2025-07-09-sound.wav
│   └── ...
├── sns/                  # SNS 投稿用文章（21+ 投稿）
│   ├── 2025-07-09-sns.md
│   └── ...
├── instruction.md        # 執筆要領と掲載予定カレンダー
├── index.md              # トップページ
└── README.md             # このファイル
```

### 主要ファイルの説明

- **`_config.yml`**: Jekyll の設定（タイトル、テーマ、タイムゾーンなど）
- **`instruction.md`**: 記事作成のガイドラインと編集カレンダー（50+ エピソード計画）
- **`_posts/`**: 記事本体を格納するディレクトリ
- **`assets/`**: 画像（PNG）と音声（WAV）ファイル
- **`sns/`**: X (Twitter), Instagram, Facebook 用の投稿文

---

## 運用方法（日々の記事作成フロー）

このプロジェクトでは、AI を活用した効率的なコンテンツ制作フローを実現しています。

### 初回のみ

1. **`instruction.md` に執筆予定と執筆要領を記入**
   - 掲載予定テーブル（日付、タイトル、概要）を作成
   - 記事作成のガイドライン（必須セクション、形式など）を定義

### 毎回の記事作成フロー

#### 1. 記事の生成（Claude Code 使用）

Claude Code に以下のプロンプトを送信します。

```
@instruction.md と過去記事を参照して、7/22 の記事を作成して
```

- `instruction.md` と過去記事をコンテキストとして参照
- 一貫性のある文体とフォーマットで自動生成
- スペイン語の発音リンク（SpanishDict）も自動埋め込み

#### 2. 4コママンガ風画像の生成（ChatGPT o3 使用）

- 記事の内容を元にプロンプトを作成
- ChatGPT o3 で視覚的に楽しいマンガ風イラストを生成
- 生成画像を `assets/YYYY-MM-DD-comic.png` として保存

#### 3. 音声解説の生成（NotebookLM 使用）

- NotebookLM に記事をアップロード
- 自動生成された音声解説をダウンロード
- `assets/YYYY-MM-DD-sound.wav` として保存

#### 4. スペイン語単語の発音リンク（自動生成）

- Claude Code が SpanishDict の発音ページへのリンクを自動挿入
- 「読む → 聞く → 真似する」がワンタッチで完結

#### 5. SNS 投稿文の生成（Claude Code 使用）

Claude Code に以下のプロンプトを送信します。

```
@_posts/2025-07-22-title.md の内容を元に SNS 投稿文を作成して
```

- X (Twitter)、Instagram、Facebook 用の文章を自動生成
- プラットフォーム別に最適化された内容
- `sns/YYYY-MM-DD-sns.md` として保存

#### 6. 公開（Git にコミット&プッシュ）

```bash
git add .
git commit -m "7月22日 記事追加"
git push origin main
```

- GitHub Pages が自動でデプロイ（数分で公開）
- コミットするだけで即座にサイトが更新されます

### ワークフロー参考（X投稿より）

このフローは以下のX投稿で紹介されています。

> こども向けメキシコ旅情報を作る機会があり、GitHub Pages + Jekyll + Claude Code を使ったMarkdownでのAIライティングやってところ、めちゃ体験良かったので共有。
>
> 1. (初回のみ) Claude Codeが生成した執筆予定と執筆要領を instruction.md に記入
> 2. instruction.mdと過去記事を参照して記事を生成 (Claude Code使用)
> 3. 記事内容を元にして4コママンガ風画像を生成 (ChatGPT o3)
> 4. 記事内容を元にして音声解説を生成 (NotebookLM)
> 5. GitHubにコミット&プッシュ→即公開
>
> — [@hfujikawa77](https://x.com/hfujikawa77/status/1944796797085569386?s=20)

---

## 記事の形式

### ファイル命名規則

```
_posts/YYYY-MM-DD-title.md
```

例: `_posts/2025-07-22-title.md`

### 必須要素

各記事には以下の要素が必須です。

1. **Front Matter** - タイトルと日付
2. **マンガ画像** - `<img>` タグで挿入
3. **音声ファイル** - `<audio>` タグで挿入
4. **メインコンテンツ** - 複数セクションに分かれた本文
5. **スペイン語学習コーナー** - 発音リンク付きテーブル
6. **今日のクイズ** - 3択クイズ
7. **Video of the Day** - YouTube 動画 3本
8. **今日のミッション** - 子ども向けの体験課題

### テンプレート例

```markdown
---
title: "7月22日号：メキシコのまちを歩こう！"
date: 2025-07-22
---

<img src="/mexico-articles/assets/2025-07-22-comic.png" alt="メキシコの街並み" width="350" />

<audio controls>
  <source src="/mexico-articles/assets/2025-07-22-sound.wav" type="audio/wav">
  お使いのブラウザはオーディオ要素をサポートしていません。
</audio>

# 7月22日号 メキシコのまちを歩こう！ 🛒🎨🏘️
**シリーズ名：¡Hola México! 毎日わくわく冒険ノート（第14回）**

---

## 1️⃣ カラフルな街並みを探検！

メキシコの街は、まるで絵の具をひっくり返したみたいにカラフル！...

---

## 🗣️ ¡Hablemos! スペイン語でひとこと

| 日本語 | 英語 | スペイン語 | 読み方 | 音声 |
|--------|------|------------|--------|------|
| 市場 | Market | **Mercado** | メルカド | [🔊 発音](https://www.spanishdict.com/pronunciation/mercado) |

---

## 🎲 今日のクイズ

Q: メキシコのスーパーで一番多く見かける野菜は何でしょう？

1. トマト
2. アボカド
3. トウモロコシ

> **答え**: 3. トウモロコシ

---

## 🎬 Video of the Day

### 1. 【メキシコの市場を歩く】
[YouTube リンク]

### 2. 【メキシコシティの街並み】
[YouTube リンク]

### 3. 【メキシコ料理の屋台体験】
[YouTube リンク]

---

## 🔍 今日のミッション

1. 家の近くのスーパーでメキシコ産の食材を探してみよう！
2. スペイン語で「いくらですか？」を練習してみよう
```

### 記述上の注意点

- **テーブルと見出しは一行空ける** - レンダリングエラーを防ぐため
- **絵文字を活用** - セクション見出しに使って視覚的に分かりやすく
- **絶対パス使用** - アセットは `/mexico-articles/assets/...` で参照

---

## SNS 投稿の形式

### ファイル命名規則

```
sns/YYYY-MM-DD-sns.md
```

例: `sns/2025-08-03-sns.md`

### 3つのプラットフォーム別テンプレート

#### X (Twitter)

- **文字数**: 短く簡潔に
- **ハッシュタグ**: 最大3つ
- **形式**: スレッド形式、記事リンクはリプライに記述

```
【¡Hola México! 毎日わくわく冒険ノート】
7月22日号：メキシコのまちを歩こう！

カラフルな街並み、活気あふれる市場、美味しい屋台グルメ...
メキシコの街歩きは発見がいっぱい！

▼記事はリプ欄から📷
#メキシコ #Mexico #海外旅行
```

#### Instagram

- **文字数**: 詳細説明可能
- **ハッシュタグ**: 多め（10-15個）
- **形式**: 丁寧な説明文

```
【メキシコのまちを歩こう！】
今日の「¡Hola México! 毎日わくわく冒険ノート」は、メキシコの街歩きの魅力に迫ります！

カラフルな建物、活気あふれる市場、...

ブログでは、もっと詳しく、そして楽しく解説しています。

#メキシコ #メキシコ旅行 #メキシコ文化 #海外旅行 #旅 #街歩き #市場 #タコス #スペイン語 #語学学習 #子育て #おうちで旅体験
```

#### Facebook

- **文字数**: 長文OK
- **形式**: 家族向けの丁寧な文章
- **構成**: 見出し、箇条書き、リンク

```
【¡Hola México! 毎日わくわく冒険ノート - 7月22日号】
**テーマ：メキシコのまちを歩こう！**

メキシコの街歩きは、まるで絵本の中に飛び込んだような体験です。

今日のブログでは、以下を紹介しています：
- カラフルな街並みの秘密
- スーパーマーケットの面白い発見
- 屋台グルメの楽しみ方

ぜひご家族でお楽しみください！

▼ブログ記事はこちら
[ブログ記事のリンク]

#メキシコ #メキシコ旅行 #海外旅行 #子育て #親子で楽しむ
```

### 注意事項

- **Markdown 記法は使わない** - コピペですぐ投稿できる形式
- **記事リンクはリプライに記述** - X (Twitter) ではスレッド形式

---

## Claude Code の使い方

### 記事生成プロンプト例

```
@instruction.md と過去記事を参照して、7/22 の記事を作成して
```

- `@instruction.md` で編集カレンダーとガイドラインを参照
- 過去記事を自動的にコンテキストとして活用
- 一貫性のあるスタイルで記事を生成

### SNS 投稿生成プロンプト例

```
@_posts/2025-07-22-title.md の内容を元に SNS 投稿文を作成して
```

- 記事を元に3つのプラットフォーム用の文章を生成
- プラットフォームごとの最適化（文字数、トーン、ハッシュタグ）

### その他の活用例

```
@instruction.md を元に来週分の記事タイトル案を5つ考えて
```

```
@_posts/2025-07-22-title.md のクイズをもう3問追加して
```

---

## コンテンツ統計

- **記事数**: 26+ 記事公開済み（2025年7月9日 - 8月3日）
- **SNS 投稿**: 21+ 投稿
- **計画エピソード数**: 50+ エピソード（`instruction.md` に記載）
- **カバー範囲**: 地理、文化、古代文明、地域ガイド、食、言語、野生動物、伝統、音楽、祭り

---

## ライセンス・クレジット

- **コンテンツ生成**: AI アシスト（Claude Code, ChatGPT o3, NotebookLM）
- **音声読み上げ**: [SpanishDict](https://www.spanishdict.com/)
- **動画**: YouTube 各クリエイター（記事内でクレジット表記）
- **テーマ**: [Minima](https://github.com/jekyll/minima) by Jekyll

---

## 参考リンク

- [Jekyll 公式ドキュメント](https://jekyllrb.com/)
- [GitHub Pages ドキュメント](https://docs.github.com/ja/pages)
- [Claude Code](https://claude.com/claude-code)
- [SpanishDict](https://www.spanishdict.com/)

---

## お問い合わせ

プロジェクトに関するご質問や提案は、GitHub Issues でお気軽にお寄せください。

---

**¡Vamos a México! メキシコへ行こう！** 🌮🎨🏛️

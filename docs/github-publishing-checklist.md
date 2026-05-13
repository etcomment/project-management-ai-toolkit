# GitHub Publishing Checklist

このリポジトリをGitHubで公開・告知する前に確認するチェックリストです。

---

## このファイルの目的

GitHub公開時の設定漏れ・情報漏洩・方針逸脱を防ぐためのチェックリストです。

リポジトリの公開準備から告知前の確認まで、手順に沿って確認してください。

---

## 公開準備フロー

```text
GitHub公開準備
│
├─ README表示確認
├─ Description設定
├─ Website設定
├─ Topics設定
├─ Social Preview設定
├─ Issue / PR Template確認
├─ 機密情報混入チェック
└─ 告知準備
```

---

## GitHub画面で設定する項目

GitHubのリポジトリページ右上「About」欄の歯車アイコンから設定できます。

### About / Description

リポジトリの一言説明です。検索・SNS共有時に表示されます。

### Website

公式サイトやリポジトリ紹介ページのURLを設定します。

### Topics

リポジトリのタグです。GitHubの検索・探索機能に影響します。

### Social Preview

GitHubやSNSで共有された際に表示されるOGP画像です。

### Pin repository

プロフィールページに表示したい場合は、リポジトリをピン留めします。

### README表示確認

リポジトリのトップページでREADME.mdが正しく表示されているか確認します。

---

## 推奨 Description

英語版（推奨）：

```text
AI context files, prompt templates, and Claude Code skills for PMs/PMOs. Supports ChatGPT, Gemini, Claude, and Claude Code.
```

日本語版：

```text
ChatGPT / Gemini / Claude / Claude Codeで使えるPM・PMO向けAI活用ツールキット。AI Contexts、Prompt Template、Claude Code Skills、実務サンプルを含む。
```

---

## 推奨 Website

```text
https://techaide.jp/
```

---

## 推奨 Topics

```text
project-management
pmo
pm
chatgpt
gemini
claude
claude-code
ai-context
prompt-engineering
engineering-management
japanese
```

---

## Social Preview

GitHubやSNSで共有されたときに表示されるOGP画像です。

- 画像を設定すると、GitHub・X・Slack等での共有時に見え方が改善されます
- 文字は短くシンプルにする
- リポジトリ名と一言説明を入れる
- 顧客情報・個人情報・認証情報は含めない
- `assets/social-preview.svg` がある場合は、それを下書きとして使えます
- GitHub画面で設定するには、必要に応じてPNG形式に変換して使用してください

設定場所：リポジトリの Settings > General > Social preview

---

## 公開前チェック

リポジトリを公開する前に、以下を確認してください。

- [ ] READMEの表示崩れがない
- [ ] `prompts/` ディレクトリが再作成されていない
- [ ] `contexts/` が主役として説明されている
- [ ] 免責・安全注意が維持されている
- [ ] Issue / PR テンプレートがある
- [ ] 実行系ファイルが追加されていない
- [ ] APIキー、パスワード、トークンが含まれていない
- [ ] 実在する顧客名・会社名・個人名・案件名が含まれていない
- [ ] Claude Code Skillにhooks、command、MCP設定、自動実行が含まれていない
- [ ] Udemy導線が過剰に増えていない

---

## 告知前チェック

SNS・ブログ・note等で告知する前に、以下を確認してください。

- [ ] GitHub About欄が設定されている
- [ ] Websiteが設定されている
- [ ] Topicsが設定されている
- [ ] Social Previewが設定されている
- [ ] README冒頭で何のリポジトリか分かる
- [ ] 自社ブログ・X・note等で紹介する場合、リポジトリの目的と免責を誤解なく説明している

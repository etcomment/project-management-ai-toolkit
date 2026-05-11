# Project Management AI Contexts

ChatGPT / Gemini / Claude / Claude Code で使える、プロジェクトマネージャー・PMO・開発リーダー向けのAIコンテキストファイルとプロンプトテンプレート集です。

このリポジトリは、PM業務における以下のような作業を、生成AIに相談しやすくするための Markdown ファイルを提供します。

- プロジェクト状況のレビュー
- 進捗報告の整理
- 課題・リスクの洗い出し
- 顧客向け説明文の作成
- 炎上初動72時間の整理
- Claude Code 向け PM レビュー Skill の利用

## このリポジトリの目的

生成AIは、PM業務の整理・報告・レビューの補助に活用できます。

ただし、AIにただ「進捗報告を作って」「リスクを洗い出して」と依頼しても、前提情報や判断軸が不足していると、実務で使いにくい出力になりがちです。

このリポジトリでは、PM業務でAIに読み込ませるためのコンテキストファイルと、用途別のプロンプトテンプレートを提供します。

AIにPM判断を代行させるのではなく、PM・PMO・開発リーダーが状況整理や判断材料の作成を効率化することを目的としています。

## 対応ツール

以下のAIツールでの利用を想定しています。

- ChatGPT
- Gemini
- Claude
- Claude Code

## 想定利用者

このリポジトリは、以下のような方を対象としています。

- プロジェクトマネージャー
- PMO
- エンジニアリングマネージャー
- 開発リーダー
- 新任PM
- PM業務に生成AIを活用したいITエンジニア
- 受託開発・業務システム開発・Web/アプリ開発に関わる管理者

## 主なユースケース

### 1. プロジェクトヘルスチェック

プロジェクトの進捗、課題、リスク、顧客状況、体制上の懸念を入力し、AIにPM視点でレビューさせます。

主な出力例：

- 現在の危険度
- 主要な懸念点
- 見落としている可能性があるリスク
- 顧客に確認すべきこと
- 社内で決めるべきこと
- 次に取るべきアクション

利用ファイル例：

- `contexts/PROJECT_HEALTH_CHECK.md`

---

### 2. 進捗報告の作成

今週の作業、完了事項、遅延事項、課題、来週予定を入力し、AIに報告文を整理させます。

主な出力例：

- 社内向け進捗報告
- 顧客向け進捗報告
- 上長向けサマリー
- リスク付き進捗報告
- 次アクション一覧

利用ファイル例：

- `contexts/STATUS_REPORT_CONTEXT.md`
- `prompts/status-report.md`

---

### 3. 課題・リスクレビュー

課題一覧や案件状況を入力し、AIに課題管理・リスク管理の観点で抜け漏れを確認させます。

主な出力例：

- 課題の分類
- 優先度の見直し
- 担当者不明の課題
- 期限不明の課題
- 影響範囲が曖昧な課題
- 追加で確認すべき事項
- エスカレーション候補

利用ファイル例：

- `contexts/ISSUE_RISK_CONTEXT.md`
- `prompts/issue-risk-review.md`

---

### 4. 顧客コミュニケーション

顧客に伝えたい内容、背景、課題、相談事項、選択肢を入力し、AIに顧客向け説明文のたたき台を作らせます。

主な出力例：

- 顧客向けメール案
- 状況説明文
- 相談文
- 遅延説明文
- 選択肢提示文
- 打ち合わせ前の説明メモ

利用ファイル例：

- `contexts/CLIENT_COMMUNICATION_CONTEXT.md`
- `prompts/client-communication.md`

---

### 5. 炎上初動72時間の整理

トラブル発生時に、事実、影響、未確認事項、初動対応を整理します。

主な出力例：

- 事実と推測の切り分け
- 影響範囲の整理
- 今日中に確認すべきこと
- 顧客に伝えるべきこと
- 社内で決めるべきこと
- 初動対応リスト
- 72時間以内の対応計画

利用ファイル例：

- `contexts/FIRE_RESPONSE_FIRST_72H.md`
- `prompts/fire-response.md`

---

### 6. Claude Code 向け PM レビュー Skill

Claude Code で、プロジェクトの README、Issue、仕様メモ、進捗メモなどをもとに、PM視点でレビューするための Skill サンプルです。

主な出力例：

- PM視点のレビュー
- Issueの曖昧さ
- 仕様未確定ポイント
- 進捗リスク
- 顧客確認が必要な点
- 次アクション不足
- PMに報告すべき事項

利用ファイル例：

- `claude-code/skills/pm-review/SKILL.md`

## リポジトリ構成

```text
project-management-ai-contexts/
├── README.md
├── DISCLAIMER.md
├── TERMS.md
├── SECURITY.md
├── LICENSE.md
├── docs/
│   ├── usage-guide.md
│   ├── ai-safety.md
│   ├── for-chatgpt.md
│   ├── for-gemini.md
│   ├── for-claude.md
│   └── for-claude-code.md
├── contexts/
│   ├── PM_CONTEXT.md
│   ├── PROJECT_HEALTH_CHECK.md
│   ├── STATUS_REPORT_CONTEXT.md
│   ├── ISSUE_RISK_CONTEXT.md
│   ├── FIRE_RESPONSE_FIRST_72H.md
│   └── CLIENT_COMMUNICATION_CONTEXT.md
├── prompts/
│   ├── status-report.md
│   ├── issue-risk-review.md
│   ├── client-communication.md
│   └── fire-response.md
├── chatgpt/
│   └── project-instructions.md
├── gemini/
│   └── gemini-instructions.md
├── claude/
│   └── claude-project-instructions.md
└── claude-code/
    ├── README.md
    └── skills/
        └── pm-review/
            └── SKILL.md
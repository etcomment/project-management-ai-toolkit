# 使い方ガイド / Usage Guide

---

## はじめに

本リポジトリ「project-management-ai-contexts」は、プロジェクトマネージャー・PMO・開発リーダーが、ChatGPT / Gemini / Claude / Claude Code を PM 業務で活用するための参考資料およびサンプルテンプレート集です。

このガイドでは、リポジトリの使い方と、目的別のファイル選び方を説明します。

---

## まず読むべきファイル

本リポジトリを使い始める前に、以下のファイルを確認してください。

| ファイル | 内容 |
|---|---|
| [README.md](../README.md) | リポジトリ全体の概要・Quick Start |
| [DISCLAIMER.md](../DISCLAIMER.md) | 免責事項・AI出力の限界・機密情報の取り扱い |
| [docs/ai-safety.md](ai-safety.md) | AIに入力してよい情報・危険な入力例・安全な使い方 |
| [contexts/PM_CONTEXT.md](../contexts/PM_CONTEXT.md) | PM業務の共通前提コンテキスト |

> [!IMPORTANT]
> AI出力は業務判断の代替ではありません。出力内容は必ず人間が確認してください。
> 機密情報・個人情報・認証情報はAIサービスに入力しないでください。

---

## 用途別のファイル選び

目的に応じて、以下のコンテキストファイルを使い分けてください。

| 目的 | コンテキストファイル | プロンプトテンプレート |
|---|---|---|
| プロジェクト全体のヘルスチェック | `contexts/PROJECT_HEALTH_CHECK.md` | — |
| 進捗報告の作成 | `contexts/STATUS_REPORT_CONTEXT.md` | `prompts/status-report.md` |
| 課題・リスクの整理 | `contexts/ISSUE_RISK_CONTEXT.md` | `prompts/issue-risk-review.md` |
| 顧客向け説明文の作成 | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` | `prompts/client-communication.md` |
| 炎上・トラブル初動の整理 | `contexts/FIRE_RESPONSE_FIRST_72H.md` | `prompts/fire-response.md` |
| 会議メモから議事録・TODOを作る | `contexts/MEETING_MINUTES_CONTEXT.md` | `prompts/meeting-minutes.md` |
| 週次定例のアジェンダを作る | `contexts/WEEKLY_MEETING_CONTEXT.md` | `prompts/weekly-meeting.md` |
| 仕様変更・スコープ変更を整理する | `contexts/SCOPE_CHANGE_CONTEXT.md` | `prompts/scope-change.md` |
| 遅延時のリカバリー方針を整理する | `contexts/DELAY_RECOVERY_CONTEXT.md` | `prompts/delay-recovery.md` |
| 品質問題の原因と対策を整理する | `contexts/QUALITY_ISSUE_CONTEXT.md` | `prompts/quality-issue.md` |
| 振り返り・ポストモーテムを作る | `contexts/RETROSPECTIVE_CONTEXT.md` | `prompts/retrospective.md` |
| ステークホルダー報告を整理する | `contexts/STAKEHOLDER_REPORT_CONTEXT.md` | `prompts/stakeholder-report.md` |
| 見積前提・不確実性を整理する | `contexts/ESTIMATION_CONTEXT.md` | `prompts/estimation.md` |
| PMO視点で案件横断レビューをする | `contexts/PMO_REVIEW_CONTEXT.md` | `prompts/pmo-review.md` |
| 開発リーダーからPMへの相談を整理する | `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md` | `prompts/engineer-to-pm-report.md` |

すべての用途で、まず `contexts/PM_CONTEXT.md` を読み込ませることを推奨します。

---

## AIツール別の使い分け

### ChatGPT

- コンテキストファイルの内容を貼り付けて、案件状況を添えて依頼する
- プロジェクト機能やカスタム指示に `chatgpt/project-instructions.md` を設定すると、毎回貼り付ける手間を省ける
- 詳細：[docs/for-chatgpt.md](for-chatgpt.md)

### Gemini

- コンテキストファイルの内容を冒頭に貼り付けて依頼する
- Gems（カスタム Gemini）を作成する場合は `gemini/gemini-instructions.md` を参考にする
- 詳細：[docs/for-gemini.md](for-gemini.md)

### Claude

- Claude Projects の「プロジェクト指示」に `claude/claude-project-instructions.md` を設定すると便利
- 長文コンテキストを渡す場合は、不要な情報を省いてから貼り付ける
- 詳細：[docs/for-claude.md](for-claude.md)

### Claude Code

- `claude-code/skills/pm-review/SKILL.md` をPMレビューの観点サンプルとして参照する
- プロジェクトの README、Issue、仕様メモ、進捗メモをPM視点でレビューする用途に使う
- hooks や自動実行は含まない
- 詳細：[docs/for-claude-code.md](for-claude-code.md)

---

## AIに入力する前のマスキング手順

業務情報をAIに渡す前に、必ず以下を確認・実施してください。

### Step 1. 入力してよい情報かを確認する

- 顧客情報、個人情報、契約情報、認証情報が含まれていないか確認する
- NDA・顧客契約・社内規程で外部送信が禁止されている情報でないかを確認する
- 利用するAIサービスの規約・データ利用条件を確認する

### Step 2. マスキングする

以下のように、実在情報をプレースホルダーに置き換えてから入力してください。

| 置き換え前（例） | 置き換え後（例） |
|---|---|
| 株式会社〇〇（顧客名） | 顧客A |
| 田中 太郎（担当者名） | 担当者A |
| api_key_xxxxxxxxxx | （削除） |
| 見積金額：3,500万円 | 見積金額：数千万円規模 |
| 2025年3月31日が納期 | 第1四半期末が納期 |

### Step 3. 要約・抽象化する

具体的な数値や詳細が不要な場合は、要約・抽象化してから入力してください。

> 例：議事録全文 → 「先週の定例で、仕様変更の方針は未決定のまま持ち越しとなった」

---

## AI出力を実務で使う前の確認手順

AI出力をそのまま利用しないでください。以下の手順で確認・修正してください。

1. **内容が事実と一致しているか確認する**
   AIは入力された情報をもとに出力するため、入力に不足がある場合は不正確な出力になることがあります

2. **案件の実態と合っているか確認する**
   AIは案件の背景や暗黙の前提を知りません。自分の案件状況に合わせて修正してください

3. **顧客・社内の関係者に合わせた表現に修正する**
   AIの出力はあくまでたたき台です。トーン・敬語・表現を実際の関係性に合わせて調整してください

4. **契約・納期・費用・責任範囲に関する表現を確認する**
   これらの表現は特に慎重に確認し、必要に応じて法務・上長に確認してください

5. **最終的に人間が責任を持って送信・報告する**
   AI出力をそのまま顧客提出・社内報告・契約関連文書に使わないでください

---

## ファイル構成の全体像

```text
project-management-ai-contexts/
├── README.md                          ← まず読む
├── DISCLAIMER.md                      ← 免責事項
├── TERMS.md                           ← 利用規約
├── SECURITY.md                        ← セキュリティポリシー
├── LICENSE.md                         ← ライセンス
├── docs/
│   ├── usage-guide.md                 ← このファイル
│   ├── ai-safety.md                   ← AI安全ガイド
│   ├── for-chatgpt.md                 ← ChatGPT向け使い方
│   ├── for-gemini.md                  ← Gemini向け使い方
│   ├── for-claude.md                  ← Claude向け使い方
│   └── for-claude-code.md             ← Claude Code向け使い方
├── contexts/
│   ├── PM_CONTEXT.md                  ← 共通前提コンテキスト
│   ├── PROJECT_HEALTH_CHECK.md        ← ヘルスチェック用
│   ├── STATUS_REPORT_CONTEXT.md       ← 進捗報告用
│   ├── ISSUE_RISK_CONTEXT.md          ← 課題・リスク管理用
│   ├── FIRE_RESPONSE_FIRST_72H.md     ← 炎上初動用
│   ├── CLIENT_COMMUNICATION_CONTEXT.md ← 顧客コミュニケーション用
│   ├── MEETING_MINUTES_CONTEXT.md     ← 議事録・TODO整理用
│   ├── WEEKLY_MEETING_CONTEXT.md      ← 週次定例アジェンダ用
│   ├── SCOPE_CHANGE_CONTEXT.md        ← スコープ変更整理用
│   ├── DELAY_RECOVERY_CONTEXT.md      ← 遅延リカバリー用
│   ├── QUALITY_ISSUE_CONTEXT.md       ← 品質問題対応用
│   ├── RETROSPECTIVE_CONTEXT.md       ← 振り返り・ポストモーテム用
│   ├── STAKEHOLDER_REPORT_CONTEXT.md  ← ステークホルダー報告用
│   ├── ESTIMATION_CONTEXT.md          ← 見積前提整理用
│   ├── PMO_REVIEW_CONTEXT.md          ← PMO横断レビュー用
│   └── ENGINEER_TO_PM_REPORT_CONTEXT.md ← エンジニアからPMへの相談用
├── prompts/
│   ├── status-report.md               ← 進捗報告プロンプト
│   ├── issue-risk-review.md           ← 課題・リスクレビュープロンプト
│   ├── client-communication.md        ← 顧客向け文面プロンプト
│   ├── fire-response.md               ← 炎上初動プロンプト
│   ├── meeting-minutes.md             ← 議事録・TODOプロンプト
│   ├── weekly-meeting.md              ← 週次定例アジェンダプロンプト
│   ├── scope-change.md                ← スコープ変更プロンプト
│   ├── delay-recovery.md              ← 遅延リカバリープロンプト
│   ├── quality-issue.md               ← 品質問題対応プロンプト
│   ├── retrospective.md               ← 振り返りプロンプト
│   ├── stakeholder-report.md          ← ステークホルダー報告プロンプト
│   ├── estimation.md                  ← 見積前提整理プロンプト
│   ├── pmo-review.md                  ← PMO横断レビュープロンプト
│   └── engineer-to-pm-report.md       ← エンジニアからPM相談プロンプト
├── chatgpt/
│   ├── README.md                       ← ChatGPT向け入口ページ
│   ├── project-instructions.md        ← ChatGPT指示文
│   ├── custom-gpt-instructions.md     ← カスタムGPT設定ガイド
│   ├── use-context-files.md           ← コンテキストファイルの使い方
│   └── examples.md                   ← 利用例（架空データ）
├── gemini/
│   ├── README.md                       ← Gemini向け入口ページ
│   ├── gemini-instructions.md         ← Gemini指示文
│   ├── gem-setup-guide.md             ← Gems設定ガイド
│   ├── use-context-files.md           ← コンテキストファイルの使い方
│   └── examples.md                   ← 利用例（架空データ）
├── claude/
│   └── claude-project-instructions.md ← Claude Projects指示文
└── claude-code/
    ├── README.md                       ← Claude Code向け説明
    └── skills/pm-review/SKILL.md       ← PMレビューSkillサンプル
```

---

## 公式サイト

このリポジトリは株式会社テックエイドが公開しています。

関連情報や講座については、公式サイトをご覧ください。

https://techaide.jp/

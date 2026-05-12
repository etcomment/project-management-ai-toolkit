# 使い方ガイド / Usage Guide

---

## はじめに

本リポジトリ「project-management-ai-contexts」は、プロジェクトマネージャー・PMO・開発リーダーが、ChatGPT / Gemini / Claude / Claude Code を PM 業務で活用するためのAIコンテキストファイル集です。

このガイドでは、リポジトリの使い方と、目的別のファイル選び方を説明します。

---

## 利用フロー

以下の順番でファイルを確認してから、AIへの入力に進んでください。

```text
[1] READMEを読む
        │
        v
[2] DISCLAIMER / ai-safety を確認
        │
        v
[3] PM_CONTEXT.md を確認
        │
        v
[4] 目的に合う contexts/*.md を選ぶ
        │
        ├─ 進捗報告        → STATUS_REPORT_CONTEXT.md
        ├─ 課題・リスク    → ISSUE_RISK_CONTEXT.md
        ├─ 顧客説明        → CLIENT_COMMUNICATION_CONTEXT.md
        ├─ 炎上初動        → FIRE_RESPONSE_FIRST_72H.md
        └─ その他          → 下記「用途別のファイル選び」を参照
        │
        v
[5] 案件情報をマスキング
        │
        v
[6] AIに入力
        │
        v
[7] AI出力を人間が確認・修正
```

> [!IMPORTANT]
> AI出力は業務判断の代替ではありません。最終的には必ず人間が確認・修正してください。
> 機密情報・個人情報・認証情報はAIサービスに入力しないでください。

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

各 `contexts/*.md` には、以下が含まれています。

- Purpose
- Use Case
- Input
- Output
- Caution
- Prompt Template

そのため、通常は `contexts/` の対象ファイルを読むだけで、AIに渡す前提情報と依頼文テンプレートを確認できます。

| 目的 | コンテキストファイル |
|---|---|
| プロジェクト全体のヘルスチェック | `contexts/PROJECT_HEALTH_CHECK.md` |
| 進捗報告の作成 | `contexts/STATUS_REPORT_CONTEXT.md` |
| 課題・リスクの整理 | `contexts/ISSUE_RISK_CONTEXT.md` |
| 顧客向け説明文の作成 | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` |
| 炎上・トラブル初動の整理 | `contexts/FIRE_RESPONSE_FIRST_72H.md` |
| 会議メモから議事録・TODOを作る | `contexts/MEETING_MINUTES_CONTEXT.md` |
| 週次定例のアジェンダを作る | `contexts/WEEKLY_MEETING_CONTEXT.md` |
| 仕様変更・スコープ変更を整理する | `contexts/SCOPE_CHANGE_CONTEXT.md` |
| 遅延時のリカバリー方針を整理する | `contexts/DELAY_RECOVERY_CONTEXT.md` |
| 品質問題の原因と対策を整理する | `contexts/QUALITY_ISSUE_CONTEXT.md` |
| 振り返り・ポストモーテムを作る | `contexts/RETROSPECTIVE_CONTEXT.md` |
| ステークホルダー報告を整理する | `contexts/STAKEHOLDER_REPORT_CONTEXT.md` |
| 見積前提・不確実性を整理する | `contexts/ESTIMATION_CONTEXT.md` |
| PMO視点で案件横断レビューをする | `contexts/PMO_REVIEW_CONTEXT.md` |
| 開発リーダーからPMへの相談を整理する | `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md` |

すべての用途で、まず `contexts/PM_CONTEXT.md` を読み込ませることを推奨します。

---

## ツール別ディレクトリの考え方

`chatgpt/`、`gemini/`、`claude/`、`claude-code/` 配下のファイルは、すべてをAIに読み込ませるためのものではありません。

大きく分けて、以下の2種類があります。

| 種類 | 内容 |
|---|---|
| 設定用・コピー用ファイル | AIツールの指示欄・プロジェクト指示・Gem/GPT設定にコピーする文面 |
| 人間向けガイド | 設定方法、使い方、利用例、注意事項を説明するドキュメント |

コンテキスト本体は `contexts/` 配下にあります。各コンテキストファイルにはPrompt Templateが内包されています。

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

- `claude-code/skills/` 配下に用途別 PM 実務 Skill を提供している
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
├── contexts/                          ← コンテキストファイル（主役）
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
├── examples/
│   ├── README.md                       ← サンプル集の入口ページ
│   ├── project-health-check-example.md ← ヘルスチェック例
│   ├── status-report-example.md        ← 進捗報告作成例
│   ├── issue-risk-review-example.md    ← 課題・リスクレビュー例
│   ├── meeting-minutes-example.md      ← 議事録・TODO作成例
│   ├── fire-response-first-72h-example.md ← 炎上初動整理例
│   ├── scope-change-example.md         ← スコープ変更整理例
│   ├── delay-recovery-example.md       ← 遅延リカバリー例
│   └── claude-code-pm-review-example.md ← Claude Code PMレビュー例
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
    └── skills/
        ├── pm-review/SKILL.md          ← 汎用PMレビューSkill
        ├── project-health-check/SKILL.md
        ├── status-report/SKILL.md
        ├── issue-risk-review/SKILL.md
        ├── client-communication/SKILL.md
        ├── fire-response-first-72h/SKILL.md
        ├── meeting-minutes/SKILL.md
        ├── scope-change-review/SKILL.md
        └── delay-recovery/SKILL.md
```

---

## サンプルで使い方を確認する

具体的な入力例・プロンプト例・期待する出力例を確認したい場合は、`examples/` 配下を参照してください。

各サンプルには、以下を記載しています。

- Use Case
- 使用するファイル
- Sanitized Input
- Prompt
- Expected Output
- Human Review Points

> [!IMPORTANT]
> すべてのサンプルは架空データです。実在する顧客情報・案件情報・個人情報は含みません。
> AI出力は業務判断の代替ではありません。出力内容は必ず人間が確認してください。

---

## 公式サイト

このリポジトリは株式会社テックエイドが公開しています。

関連情報や講座については、公式サイトをご覧ください。

https://techaide.jp/

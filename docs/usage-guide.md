# 使い方ガイド / Usage Guide

---

## はじめに

本リポジトリ「project-management-ai-contexts」は、プロジェクトマネージャー・PMO・開発リーダーが、ChatGPT / Gemini / Claude / Claude Code を PM 業務で活用するためのAIコンテキストファイル集です。

このガイドでは、リポジトリの使い方と、目的別のファイル選び方を説明します。

---

## 利用フロー

```
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

| ファイル | 内容 |
|---|---|
| [README.md](../README.md) | リポジトリ全体の概要・Quick Start |
| [docs/legal/DISCLAIMER.md](legal/DISCLAIMER.md) | 免責事項・AI出力の限界・機密情報の取り扱い |
| [docs/ai-safety.md](ai-safety.md) | AIに入力してよい情報・危険な入力例・安全な使い方 |
| [contexts/PM_CONTEXT.md](../contexts/PM_CONTEXT.md) | PM業務の共通前提コンテキスト |

---

## 用途別のファイル選び

「自分の状況ではどのファイルを使えばよいか」を素早く確認したい場合は、[docs/use-case-map.md](use-case-map.md) を参照してください。

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

---

## ファイルの種類

### コンテキスト本体

`contexts/` 配下のファイルがすべての AIツール向け主役です。各ファイルには以下が含まれています。

- Purpose
- Use Case
- Input
- Output
- Caution
- Prompt Template

### 設定用ファイル（指示文）

AIツールの設定欄にコピーして使う指示文です。`instructions/` 配下にあります。

| ファイル | 用途 |
|---|---|
| `instructions/chatgpt-project-instructions.md` | ChatGPT Projects の Instructions 欄 |
| `instructions/custom-gpt-instructions.md` | カスタムGPT の Instructions 欄 |
| `instructions/gemini-instructions.md` | Gems の指示欄 |
| `instructions/claude-project-instructions.md` | Claude Projects の指示欄 |

### 人間が読むガイド

`docs/tools/` 配下のファイルが人間向けのツール別ガイドです。

---

## AIツール別の使い分け

### ChatGPT

- コンテキストファイルの内容を貼り付けて、案件状況を添えて依頼する
- プロジェクト機能に `instructions/chatgpt-project-instructions.md` を設定すると便利
- 詳細：[docs/tools/chatgpt.md](tools/chatgpt.md)

### Gemini

- コンテキストファイルの内容を冒頭に貼り付けて依頼する
- Gems を作成する場合は `instructions/gemini-instructions.md` を参考にする
- 詳細：[docs/tools/gemini.md](tools/gemini.md)

### Claude

- Claude Projects の「プロジェクト指示」に `instructions/claude-project-instructions.md` を設定すると便利
- 長文コンテキストを渡す場合は、不要な情報を省いてから貼り付ける
- 詳細：[docs/tools/claude.md](tools/claude.md)

### Claude Code

- `.claude/skills/` 配下に用途別 PM 実務 Skill がある
- プロジェクトの README、Issue、仕様メモをPM視点でレビューする用途に使う
- hooks や自動実行は含まない
- 詳細：[docs/tools/claude-code.md](tools/claude-code.md)

---

## AIに入力する前のマスキング手順

業務情報をAIに渡す前に、必ず以下を確認・実施してください。

### Step 1. 入力してよい情報かを確認する

- 顧客情報、個人情報、契約情報、認証情報が含まれていないか確認する
- NDA・顧客契約・社内規程で外部送信が禁止されている情報でないかを確認する

### Step 2. マスキングする

| 置き換え前（例） | 置き換え後（例） |
|---|---|
| 株式会社〇〇（顧客名） | 顧客A |
| 田中 太郎（担当者名） | 担当者A |
| api_key_xxxxxxxxxx | （削除） |
| 見積金額：3,500万円 | 見積金額：数千万円規模 |

### Step 3. 要約・抽象化する

具体的な数値や詳細が不要な場合は、要約・抽象化してから入力してください。

---

## ファイル構成の全体像

```
project-management-ai-contexts/
├── README.md
├── LICENSE.md
├── .gitignore
│
├── contexts/                          ← コンテキストファイル（主役）
│   ├── PM_CONTEXT.md
│   ├── PROJECT_HEALTH_CHECK.md
│   ├── STATUS_REPORT_CONTEXT.md
│   ├── ISSUE_RISK_CONTEXT.md
│   ├── FIRE_RESPONSE_FIRST_72H.md
│   ├── CLIENT_COMMUNICATION_CONTEXT.md
│   ├── MEETING_MINUTES_CONTEXT.md
│   ├── WEEKLY_MEETING_CONTEXT.md
│   ├── SCOPE_CHANGE_CONTEXT.md
│   ├── DELAY_RECOVERY_CONTEXT.md
│   ├── QUALITY_ISSUE_CONTEXT.md
│   ├── RETROSPECTIVE_CONTEXT.md
│   ├── STAKEHOLDER_REPORT_CONTEXT.md
│   ├── ESTIMATION_CONTEXT.md
│   ├── PMO_REVIEW_CONTEXT.md
│   └── ENGINEER_TO_PM_REPORT_CONTEXT.md
│
├── instructions/                      ← 設定用・コピー用指示文
│   ├── chatgpt-project-instructions.md
│   ├── custom-gpt-instructions.md
│   ├── gemini-instructions.md
│   └── claude-project-instructions.md
│
├── examples/                          ← 架空データによる利用例
│   ├── README.md
│   ├── project-health-check-example.md
│   ├── status-report-example.md
│   ├── issue-risk-review-example.md
│   ├── meeting-minutes-example.md
│   ├── fire-response-first-72h-example.md
│   ├── scope-change-example.md
│   ├── delay-recovery-example.md
│   └── claude-code-pm-review-example.md
│
├── docs/
│   ├── usage-guide.md                 ← このファイル
│   ├── ai-safety.md
│   ├── use-case-map.md
│   ├── github-publishing-checklist.md
│   ├── tools/
│   │   ├── chatgpt.md
│   │   ├── gemini.md
│   │   ├── claude.md
│   │   └── claude-code.md
│   ├── legal/
│   │   ├── DISCLAIMER.md
│   │   └── TERMS.md
│   └── meta/
│       ├── CHANGELOG.md
│       └── ROADMAP.md
│
├── .claude/
│   └── skills/
│       ├── pm-review/SKILL.md
│       ├── project-health-check/SKILL.md
│       ├── status-report/SKILL.md
│       ├── issue-risk-review/SKILL.md
│       ├── client-communication/SKILL.md
│       ├── fire-response-first-72h/SKILL.md
│       ├── meeting-minutes/SKILL.md
│       ├── scope-change-review/SKILL.md
│       └── delay-recovery/SKILL.md
│
└── .github/
    ├── CONTRIBUTING.md
    ├── SECURITY.md
    ├── pull_request_template.md
    └── ISSUE_TEMPLATE/
```

---

## サンプルで使い方を確認する

具体的な入力例・プロンプト例・期待する出力例を確認したい場合は、`examples/` 配下を参照してください。

> [!IMPORTANT]
> すべてのサンプルは架空データです。実在する顧客情報・案件情報・個人情報は含みません。
> AI出力は業務判断の代替ではありません。出力内容は必ず人間が確認してください。

---

## 公式サイト

このリポジトリは株式会社テックエイドが公開しています。

https://techaide.jp/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_contexts

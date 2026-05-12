# Claude Code 向けディレクトリ / Claude Code Directory

---

## このディレクトリについて

このディレクトリ（`claude-code/`）は、Claude Code で本リポジトリのコンテキストを活用するための Skills を提供します。

Claude Code は、ターミナルで動作するAIコーディングアシスタントです。

このディレクトリでは、Claude Code をコーディングではなく **プロジェクト管理・PM業務の支援** に活用するための Skills を提供します。

---

## ディレクトリ構成

```text
claude-code/
├── README.md                           ← このファイル
└── skills/
    ├── pm-review/
    │   └── SKILL.md                    ← 汎用PMレビュー
    ├── project-health-check/
    │   └── SKILL.md                    ← プロジェクト状況のヘルスチェック
    ├── status-report/
    │   └── SKILL.md                    ← 進捗報告整理
    ├── issue-risk-review/
    │   └── SKILL.md                    ← 課題・リスクレビュー
    ├── client-communication/
    │   └── SKILL.md                    ← 顧客向け説明文整理
    ├── fire-response-first-72h/
    │   └── SKILL.md                    ← 炎上初動72時間整理
    ├── meeting-minutes/
    │   └── SKILL.md                    ← 議事録・TODO整理
    ├── scope-change-review/
    │   └── SKILL.md                    ← スコープ変更整理
    └── delay-recovery/
        └── SKILL.md                    ← 遅延リカバリー整理
```

---

## Skill 一覧

| Skill | 用途 |
|---|---|
| [pm-review](skills/pm-review/SKILL.md) | 汎用PMレビュー（進捗・課題・リスク・次アクション） |
| [project-health-check](skills/project-health-check/SKILL.md) | プロジェクト状況のヘルスチェック |
| [status-report](skills/status-report/SKILL.md) | 社内向け・顧客向け・上長向け進捗報告整理 |
| [issue-risk-review](skills/issue-risk-review/SKILL.md) | 課題一覧の優先度・抜け漏れ・エスカレーション整理 |
| [client-communication](skills/client-communication/SKILL.md) | 顧客向け説明文・相談文・報告文のたたき台作成 |
| [fire-response-first-72h](skills/fire-response-first-72h/SKILL.md) | 炎上・重大障害の初動72時間整理 |
| [meeting-minutes](skills/meeting-minutes/SKILL.md) | 会議メモから議事録・決定事項・TODO整理 |
| [scope-change-review](skills/scope-change-review/SKILL.md) | 仕様変更・スコープ変更の影響整理 |
| [delay-recovery](skills/delay-recovery/SKILL.md) | 遅延発生時のリカバリー案・説明方針整理 |

---

## 各 Skill に含まれないもの

すべての Skill は **ドキュメントのみ** であり、以下は含まれていません。

| 含まれないもの | 理由 |
|---|---|
| 実行可能な hooks | 意図しない自動実行を防ぐため |
| 自動実行コマンド | 意図しない自動実行を防ぐため |
| shell スクリプト | 意図しない自動実行を防ぐため |
| MCP設定 | 外部サービスとの自動連携を防ぐため |
| GitHub Actions | CI/CDの自動実行を防ぐため |
| 自動コミット・自動デプロイ | 意図しないコード変更・本番環境への影響を防ぐため |

---

## 使い方

Claude Code のチャットで、以下のように依頼します。

### 例1：プロジェクトのREADMEをPM視点でレビューしてもらう

```text
claude-code/skills/pm-review/SKILL.md の内容を前提として、
このプロジェクトの README.md をPM視点でレビューしてください。
```

### 例2：進捗報告のたたき台を作成してもらう

```text
claude-code/skills/status-report/SKILL.md の内容を前提として、
以下の進捗状況を社内向け・顧客向けで整理してください。

【今週の状況（機密情報はマスキング済み）】
（ここに状況を貼り付ける）
```

### 例3：課題・リスクをPM視点でレビューしてもらう

```text
claude-code/skills/issue-risk-review/SKILL.md の内容を前提として、
現在の課題一覧をPM視点でレビューしてください。
担当者不明・期限不明・エスカレーションが必要なものを指摘してください。
```

---

## 注意事項

- `SKILL.md` はドキュメントサンプルです。内容を理解したうえで利用してください
- **機密情報・個人情報・認証情報（APIキー・パスワード等）をClaude Codeに入力しないでください**
- AI出力は業務判断の代替ではありません。出力内容は必ず人間が確認・修正してください
- 顧客提出・社内報告前には必ず人間によるレビューを行ってください
- Claude Code の利用規約・データ利用条件を確認してください

---

## 関連ドキュメント

- [docs/for-claude-code.md](../docs/for-claude-code.md)
- [DISCLAIMER.md](../DISCLAIMER.md)
- [docs/ai-safety.md](../docs/ai-safety.md)

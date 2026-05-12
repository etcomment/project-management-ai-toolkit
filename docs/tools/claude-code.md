# Claude Code Guide / Claude Code向けガイド

Claude Code で本リポジトリを活用するためのガイドです。

> [!IMPORTANT]
> 機密情報・個人情報・認証情報（APIキー・パスワード等）をClaude Codeに入力しないでください。
> AI出力は業務判断の代替ではありません。出力内容は必ず人間が確認・修正してください。

---

## このリポジトリの主役は `contexts/`

コンテキスト本体は `contexts/` 配下にあります。

Claude Code 向けの PM 実務 Skill は `.claude/skills/` 配下に配置されています。

---

## Skill の場所

```text
.claude/
└─ skills/
   ├─ pm-review/SKILL.md
   ├─ project-health-check/SKILL.md
   ├─ status-report/SKILL.md
   ├─ issue-risk-review/SKILL.md
   ├─ client-communication/SKILL.md
   ├─ fire-response-first-72h/SKILL.md
   ├─ meeting-minutes/SKILL.md
   ├─ scope-change-review/SKILL.md
   └─ delay-recovery/SKILL.md
```

---

## Skill とは

このリポジトリの Skill は **ドキュメントのみ** です。以下は含まれていません。

| 含まれないもの | 理由 |
|---|---|
| 実行可能な hooks | 意図しない自動実行を防ぐため |
| 自動実行コマンド | 意図しない自動実行を防ぐため |
| shell スクリプト | 意図しない自動実行を防ぐため |
| MCP設定 | 外部サービスとの自動連携を防ぐため |
| GitHub Actions | CI/CDの自動実行を防ぐため |
| 自動コミット・自動デプロイ | 意図しないコード変更・本番環境への影響を防ぐため |

Skill は、PM実務のレビュー観点・整理観点をClaude Codeに伝えるためのドキュメントです。

---

## Skill 選択マップ

| 目的 | Skill |
|---|---|
| 汎用PMレビュー | `.claude/skills/pm-review/SKILL.md` |
| プロジェクト全体の健全性確認 | `.claude/skills/project-health-check/SKILL.md` |
| 進捗報告 | `.claude/skills/status-report/SKILL.md` |
| 課題・リスク整理 | `.claude/skills/issue-risk-review/SKILL.md` |
| 顧客向け文面 | `.claude/skills/client-communication/SKILL.md` |
| 炎上初動 | `.claude/skills/fire-response-first-72h/SKILL.md` |
| 議事録・TODO | `.claude/skills/meeting-minutes/SKILL.md` |
| スコープ変更 | `.claude/skills/scope-change-review/SKILL.md` |
| 遅延リカバリー | `.claude/skills/delay-recovery/SKILL.md` |

---

## 使い方

Claude Code のチャットで、以下のように依頼します。

### 例1：プロジェクトのREADMEをPM視点でレビューしてもらう

```text
.claude/skills/pm-review/SKILL.md の内容を前提として、
このプロジェクトの README.md をPM視点でレビューしてください。
```

### 例2：進捗報告のたたき台を作成してもらう

```text
.claude/skills/status-report/SKILL.md の内容を前提として、
以下の進捗状況を社内向け・顧客向けで整理してください。

【今週の状況（機密情報はマスキング済み）】
（ここに状況を貼り付ける）
```

### 例3：課題・リスクをPM視点でレビューしてもらう

```text
.claude/skills/issue-risk-review/SKILL.md の内容を前提として、
現在の課題一覧をPM視点でレビューしてください。
担当者不明・期限不明・エスカレーションが必要なものを指摘してください。
```

---

## contexts/ との関係

Claude Code Skill と `contexts/` は以下のように使い分けできます。

- `contexts/*.md`：AIに渡す前提情報・Prompt Template（ChatGPT / Gemini / Claude / Claude Code 共通）
- `.claude/skills/*.md`：Claude Code 向けに PM 実務の観点を伝えるドキュメント

Claude Codeで使う場合は、Skill と `contexts/PM_CONTEXT.md` を組み合わせると効果的です。

```text
.claude/skills/pm-review/SKILL.md と contexts/PM_CONTEXT.md を読み込んだ上で、
このリポジトリの現在の状況をPM視点でレビューしてください。
```

---

## 注意事項

- `SKILL.md` はドキュメントサンプルです。内容を理解したうえで利用してください
- **機密情報・個人情報・認証情報をClaude Codeに入力しないでください**
- AI出力は業務判断の代替ではありません。出力内容は必ず人間が確認・修正してください
- 顧客提出・社内報告前には必ず人間によるレビューを行ってください
- Claude Code の利用規約・データ利用条件を確認してください

---

## 関連ドキュメント

- [docs/ai-safety.md](../ai-safety.md) — AIに入力してよい情報・安全な使い方
- [docs/legal/DISCLAIMER.md](../legal/DISCLAIMER.md) — 免責事項

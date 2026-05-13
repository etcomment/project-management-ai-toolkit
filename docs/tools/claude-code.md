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
   ├─ README.md                          ← Skill一覧・使い方ガイド
   │
   ├─ pm-ai-diagnosis/SKILL.md           ← まず使う：診断・入口
   │
   ├─ project-risk-radar/SKILL.md        ← リスクを見つける
   ├─ issue-risk-review/SKILL.md
   │
   ├─ pm-decision-support/SKILL.md       ← 判断する
   │
   ├─ stakeholder-strategy/SKILL.md      ← 伝える
   ├─ client-communication/SKILL.md
   ├─ status-report/SKILL.md
   │
   ├─ ai-output-governance-review/SKILL.md  ← AI出力を確認する
   │
   ├─ meeting-minutes/SKILL.md           ← 会議・変更・遅延を整理する
   ├─ scope-change-review/SKILL.md
   ├─ delay-recovery/SKILL.md
   ├─ fire-response-first-72h/SKILL.md
   │
   ├─ pm-review/SKILL.md                 ← 汎用レビュー・ヘルスチェック
   └─ project-health-check/SKILL.md
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

### まず使う

| 目的 | Skill |
|---|---|
| どのContextやSkillを使えばよいか診断したい | `.claude/skills/pm-ai-diagnosis/SKILL.md` |

### リスクを見つける

| 目的 | Skill |
|---|---|
| 表面化していないプロジェクトリスクを検知したい | `.claude/skills/project-risk-radar/SKILL.md` |
| 課題・リスクの抜け漏れを整理したい | `.claude/skills/issue-risk-review/SKILL.md` |

### 判断する

| 目的 | Skill |
|---|---|
| PM判断（エスカレーション・方針選択）を構造化したい | `.claude/skills/pm-decision-support/SKILL.md` |

### 伝える

| 目的 | Skill |
|---|---|
| 相手別の伝え方・コミュニケーション戦略を整理したい | `.claude/skills/stakeholder-strategy/SKILL.md` |
| 顧客向け文面のたたき台を作りたい | `.claude/skills/client-communication/SKILL.md` |
| 進捗報告を整理したい | `.claude/skills/status-report/SKILL.md` |

### AI出力を確認する

| 目的 | Skill |
|---|---|
| AI出力を実務利用する前に安全性・表現をレビューしたい | `.claude/skills/ai-output-governance-review/SKILL.md` |

### 会議・変更・遅延を整理する

| 目的 | Skill |
|---|---|
| 議事録・TODO・次回確認事項を整理したい | `.claude/skills/meeting-minutes/SKILL.md` |
| スコープ変更の影響を整理したい | `.claude/skills/scope-change-review/SKILL.md` |
| 遅延リカバリー方針を整理したい | `.claude/skills/delay-recovery/SKILL.md` |
| 炎上初動を整理したい | `.claude/skills/fire-response-first-72h/SKILL.md` |

### 汎用レビュー・ヘルスチェック

| 目的 | Skill |
|---|---|
| 汎用PMレビュー | `.claude/skills/pm-review/SKILL.md` |
| プロジェクト全体の健全性確認 | `.claude/skills/project-health-check/SKILL.md` |

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

### 例4：どのContextやSkillを使えばよいか診断してもらう

```text
<task>
.claude/skills/pm-ai-diagnosis/SKILL.md の内容を前提として、
以下の状況に合うContextとSkillを案内してください。
</task>
<input>
【状況】
週次報告、顧客説明、課題管理のどれから整理すべきか迷っています。
開発は進んでいますが、顧客確認待ちの事項が増えており、次回定例で何を説明すべきか整理できていません。
</input>
<constraints>
- 顧客名・個人名・会社名などの機密情報はマスキング済みです。
- 判断に必要な情報が不足している場合は「情報不足」と明記してください。
</constraints>
```

### 例5：表面化していないリスクを検知してもらう

```text
<task>
.claude/skills/project-risk-radar/SKILL.md の内容を前提として、
以下の進捗メモから、表面化していないプロジェクトリスクを検知してください。
</task>
<input>
【進捗メモ】
- 外部API仕様は確認中
- テスト環境構築は来週に延期
- 顧客確認待ちの仕様変更が3件ある
- 開発チームは主要機能の実装を優先中
- 次回定例で進捗を報告予定
</input>
<constraints>
- 入力情報に根拠がないリスクは断定しないでください。
- 推測が含まれる場合は「（推測）」と明示してください。
- 顧客名・個人名・会社名などの機密情報はマスキング済みです。
</constraints>
```

### 例6：PM判断を構造化してもらう

```text
<task>
.claude/skills/pm-decision-support/SKILL.md の内容を前提として、
以下の判断テーマについて、選択肢・判断基準・推奨案・エスカレーション要否を整理してください。
</task>
<input>
【判断テーマ】
顧客確認待ちの仕様が確定しない状態で、暫定実装を進めるべきか、仕様確定まで待つべきか。
【状況】
- 仕様確定が遅れると開発着手が遅れる
- 暫定実装すると手戻りリスクがある
- リリース予定日はまだ変更されていない
- 上長にはまだ相談していない
</input>
<constraints>
- 最終判断はPM・上長・関係者が行う前提で整理してください。
- 契約・納期・費用・責任範囲に関わる事項は断定しないでください。
- 情報不足があれば明記してください。
</constraints>
```

### 例7：AI出力を顧客提出前にレビューしてもらう

```text
<task>
.claude/skills/ai-output-governance-review/SKILL.md の内容を前提として、
以下の顧客向け文面に、危険な断定表現、機密情報、確認漏れ、契約・納期・責任範囲への踏み込みがないかレビューしてください。
</task>
<input>
【レビュー対象文面】
現時点では納期への影響はありません。
外部API仕様が確定次第、予定通り実装を進めます。
追加要望についても、現在のスケジュール内で対応可能です。
【利用目的】
顧客向け進捗報告のたたき台
</input>
<constraints>
- 顧客提出前提の文面として、安全性・表現・確認漏れをレビューしてください。
- 「法的に安全」「契約上問題ない」とは断定しないでください。
- 必要に応じて上長・法務・関係者への確認が必要と明記してください。
</constraints>
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

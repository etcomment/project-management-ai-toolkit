# Use Case Map / ユースケースマップ

---

## このファイルの目的

PM業務の状況別に、使うべき `contexts/*.md` を整理するガイドです。

- ChatGPT / Gemini / Claude / Claude Code で共通して使えます
- このリポジトリの主役は `contexts/` 配下のコンテキストファイルです
- `prompts/` ディレクトリは存在しません。用途別のプロンプトは各 `contexts/*.md` の `Prompt Template` に内包されています
- まず自分の状況に合う `contexts/*.md` を選び、内包されている `Prompt Template` を活用してください

---

## まず全体像

```text
今困っていること
│
├─ プロジェクト全体を見たい
│    └─ contexts/PROJECT_HEALTH_CHECK.md
│
├─ 報告文を作りたい
│    ├─ 進捗報告
│    │    └─ contexts/STATUS_REPORT_CONTEXT.md
│    └─ 上長・経営層向け
│         └─ contexts/STAKEHOLDER_REPORT_CONTEXT.md
│
├─ 課題・リスクを整理したい
│    ├─ 課題管理
│    │    └─ contexts/ISSUE_RISK_CONTEXT.md
│    └─ 複数案件横断
│         └─ contexts/PMO_REVIEW_CONTEXT.md
│
├─ 顧客対応が必要
│    ├─ 説明文・相談文
│    │    └─ contexts/CLIENT_COMMUNICATION_CONTEXT.md
│    ├─ 仕様変更
│    │    └─ contexts/SCOPE_CHANGE_CONTEXT.md
│    └─ 炎上初動
│         └─ contexts/FIRE_RESPONSE_FIRST_72H.md
│
├─ 会議・振り返りを整理したい
│    ├─ 会議メモ・TODO
│    │    └─ contexts/MEETING_MINUTES_CONTEXT.md
│    └─ 振り返り・ポストモーテム
│         └─ contexts/RETROSPECTIVE_CONTEXT.md
│
├─ 見積・品質・遅延を整理したい
│    ├─ 見積前提
│    │    └─ contexts/ESTIMATION_CONTEXT.md
│    ├─ 品質問題
│    │    └─ contexts/QUALITY_ISSUE_CONTEXT.md
│    └─ 遅延リカバリー
│         └─ contexts/DELAY_RECOVERY_CONTEXT.md
│
└─ 開発現場からPMへ相談したい
     └─ contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md
```

---

## 状況別ファイル選び

| 困っていること | 使うコンテキスト | 補足 |
|---|---|---|
| プロジェクト全体が危ないか確認したい | `contexts/PROJECT_HEALTH_CHECK.md` | 進捗・課題・リスク・体制を俯瞰 |
| 週次進捗報告を作りたい | `contexts/STATUS_REPORT_CONTEXT.md` | 社内向け・顧客向け・上長向けに整理 |
| 課題管理表の抜け漏れを確認したい | `contexts/ISSUE_RISK_CONTEXT.md` | 担当者不明・期限不明・潜在リスクを確認 |
| 顧客向けの説明文を作りたい | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` | 契約・費用・納期表現は人間確認必須 |
| 炎上初動を整理したい | `contexts/FIRE_RESPONSE_FIRST_72H.md` | 事実・影響・未確認事項・初動対応を整理 |
| 会議メモから議事録を作りたい | `contexts/MEETING_MINUTES_CONTEXT.md` | 決定事項・TODO・次回確認事項を整理 |
| 仕様変更の影響を整理したい | `contexts/SCOPE_CHANGE_CONTEXT.md` | 工数・納期・費用・顧客確認事項を整理 |
| 遅延リカバリーを考えたい | `contexts/DELAY_RECOVERY_CONTEXT.md` | 原因・影響・リカバリー案を整理 |
| 品質問題の対策を考えたい | `contexts/QUALITY_ISSUE_CONTEXT.md` | 原因・暫定対応・再発防止策を整理 |
| 振り返り・ポストモーテムを整理したい | `contexts/RETROSPECTIVE_CONTEXT.md` | Keep / Problem / Try、再発防止を整理 |
| ステークホルダー向け報告を整理したい | `contexts/STAKEHOLDER_REPORT_CONTEXT.md` | 経営層・上長・顧客責任者向けに整理 |
| 見積前提・不確実性を整理したい | `contexts/ESTIMATION_CONTEXT.md` | 見積金額ではなく前提・確認事項を整理 |
| PMOとして複数案件を見たい | `contexts/PMO_REVIEW_CONTEXT.md` | 危険案件・横断課題・支援対象を整理 |
| エンジニアからPMへ相談したい | `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md` | 技術課題をPM向けに整理 |

---

## AIツール別の使い方

### 1. 通常チャットで使う

どのAIツールでも、以下の手順で使えます。

1. `contexts/PM_CONTEXT.md` の内容をチャットに貼り付ける
2. 状況に応じた用途別 `contexts/*.md` を貼り付ける
3. 案件情報を**マスキング・要約**して貼り付ける
4. `contexts/*.md` の `Prompt Template` を参考に依頼文を作る
5. AI出力を人間が確認する

### 2. ChatGPT Projects / Claude Projects / Gems に事前設定する

事前にプロジェクト設定にコンテキストを登録しておくと、毎回貼り付ける手間を省けます。

| ツール | 設定参考ファイル |
|---|---|
| ChatGPT | `instructions/chatgpt-project-instructions.md` |
| Gemini（Gems） | `instructions/gemini-instructions.md` |
| Claude Projects | `instructions/claude-project-instructions.md` |

各ツール向けの設定ガイドは、`docs/tools/chatgpt.md`、`docs/tools/gemini.md`、`docs/tools/claude.md` を参照してください。

### 3. Claude Code Skill と組み合わせる

Claude Code を使っている場合は、`.claude/skills/` 配下の Skill と組み合わせることができます。

詳細は次セクションを参照してください。

---

## Claude Code Skill と組み合わせる場合

| 目的 | Claude Code Skill |
|---|---|
| 汎用PMレビュー | `.claude/skills/pm-review/SKILL.md` |
| プロジェクトヘルスチェック | `.claude/skills/project-health-check/SKILL.md` |
| 進捗報告 | `.claude/skills/status-report/SKILL.md` |
| 課題・リスクレビュー | `.claude/skills/issue-risk-review/SKILL.md` |
| 顧客向け文面 | `.claude/skills/client-communication/SKILL.md` |
| 炎上初動 | `.claude/skills/fire-response-first-72h/SKILL.md` |
| 議事録・TODO | `.claude/skills/meeting-minutes/SKILL.md` |
| スコープ変更 | `.claude/skills/scope-change-review/SKILL.md` |
| 遅延リカバリー | `.claude/skills/delay-recovery/SKILL.md` |

> [!NOTE]
> `.claude/skills/` は実行系ではありません。hooks、command、MCP設定、自動実行は含みません。
> PM実務の観点をClaude Codeに伝えるためのドキュメントです。

---

## 安全上の注意

> [!CAUTION]
> - 実案件情報をそのまま入力しないでください
> - 顧客名・個人名・会社名・契約情報・認証情報は必ずマスキングしてください
> - AI出力は業務判断の代替ではありません
> - 顧客提出・社内報告・契約判断・納期回答には必ず人間が確認してください

詳細は [docs/ai-safety.md](ai-safety.md) および [docs/legal/DISCLAIMER.md](legal/DISCLAIMER.md) を参照してください。

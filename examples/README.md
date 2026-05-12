# Examples — 実用サンプル集

このディレクトリは、`contexts/` の使い方を具体的に示すサンプル集です。

---

## このディレクトリの目的

各コンテキストファイルを実際にどのように使うのか、入力例・プロンプト例・期待する出力例を通じて確認できます。

---

## 注意事項

> [!IMPORTANT]
> **すべてのサンプルは架空データです。** 実在する顧客名・会社名・個人名・案件名・認証情報は含まれていません。
>
> 実案件の情報（顧客名、案件名、個人情報、認証情報、契約情報）をAIサービスに入力しないでください。
> 入力前に必ずマスキング・抽象化を行ってください。詳細は [docs/ai-safety.md](../docs/ai-safety.md) を参照してください。

> [!WARNING]
> **AI出力は業務判断の代替ではありません。** 出力内容は必ず人間が確認・修正してください。
> 顧客提出・社内報告・契約判断・納期回答・費用判断に使用する場合は、担当者が内容を確認した上で利用してください。

---

## サンプル一覧

| サンプルファイル | 内容 |
|---|---|
| [project-health-check-example.md](project-health-check-example.md) | プロジェクト状況のヘルスチェック例 |
| [status-report-example.md](status-report-example.md) | 進捗報告作成例 |
| [issue-risk-review-example.md](issue-risk-review-example.md) | 課題・リスクレビュー例 |
| [meeting-minutes-example.md](meeting-minutes-example.md) | 会議メモから議事録・TODOを作る例 |
| [fire-response-first-72h-example.md](fire-response-first-72h-example.md) | 炎上初動72時間の整理例 |
| [scope-change-example.md](scope-change-example.md) | 仕様変更・スコープ変更の整理例 |
| [delay-recovery-example.md](delay-recovery-example.md) | 遅延時のリカバリー方針整理例 |
| [claude-code-pm-review-example.md](claude-code-pm-review-example.md) | Claude CodeでPMレビューSkillを使う例 |

---

## 使用するファイルの対応表

| サンプル | 使用するファイル |
|---|---|
| project-health-check-example.md | `contexts/PM_CONTEXT.md`、`contexts/PROJECT_HEALTH_CHECK.md` |
| status-report-example.md | `contexts/PM_CONTEXT.md`、`contexts/STATUS_REPORT_CONTEXT.md` |
| issue-risk-review-example.md | `contexts/PM_CONTEXT.md`、`contexts/ISSUE_RISK_CONTEXT.md` |
| meeting-minutes-example.md | `contexts/PM_CONTEXT.md`、`contexts/MEETING_MINUTES_CONTEXT.md` |
| fire-response-first-72h-example.md | `contexts/PM_CONTEXT.md`、`contexts/FIRE_RESPONSE_FIRST_72H.md` |
| scope-change-example.md | `contexts/PM_CONTEXT.md`、`contexts/SCOPE_CHANGE_CONTEXT.md` |
| delay-recovery-example.md | `contexts/PM_CONTEXT.md`、`contexts/DELAY_RECOVERY_CONTEXT.md` |
| claude-code-pm-review-example.md | `contexts/PM_CONTEXT.md`、`.claude/skills/pm-review/SKILL.md` |

---

## AI出力を実務で使う前の確認

各サンプルの「Human Review Points」セクションに、AIの出力を確認すべき観点を記載しています。

AIの出力をそのまま顧客提出・社内報告・契約関連文書に使わないでください。最終的な判断と責任は、必ず人間が持ってください。

詳細は [docs/usage-guide.md](../docs/usage-guide.md) および [DISCLAIMER.md](../DISCLAIMER.md) を参照してください。

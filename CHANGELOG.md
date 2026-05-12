# Changelog

このファイルでは、project-management-ai-contexts の主な変更履歴を記録します。

## [Unreleased]

### Added

- 今後追加予定の変更をここに記録します。

### Changed

- 変更予定の内容をここに記録します。

### Fixed

- 修正予定の内容をここに記録します。

---

## [0.3.0] - 2026-05

### Added

- `examples/` 配下に実用サンプルを追加
  - `project-health-check-example.md`
  - `status-report-example.md`
  - `issue-risk-review-example.md`
  - `meeting-minutes-example.md`
  - `fire-response-first-72h-example.md`
  - `scope-change-example.md`
  - `delay-recovery-example.md`
  - `claude-code-pm-review-example.md`
- ChatGPT / Gemini 向けの設定ガイド・利用例を追加
  - `chatgpt/examples.md`
  - `gemini/examples.md`
  - `gemini/gem-setup-guide.md`
- 追加ユースケース用の `contexts/` と `prompts/` を追加
  - `contexts/MEETING_MINUTES_CONTEXT.md`
  - `contexts/WEEKLY_MEETING_CONTEXT.md`
  - `contexts/SCOPE_CHANGE_CONTEXT.md`
  - `contexts/DELAY_RECOVERY_CONTEXT.md`
  - `contexts/QUALITY_ISSUE_CONTEXT.md`
  - `contexts/RETROSPECTIVE_CONTEXT.md`
  - `contexts/STAKEHOLDER_REPORT_CONTEXT.md`
  - `contexts/ESTIMATION_CONTEXT.md`
  - `contexts/PMO_REVIEW_CONTEXT.md`
  - `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md`
  - 対応する `prompts/` ファイル群

---

## [0.2.0] - 2026-05

### Added

- 会議、スコープ変更、遅延、品質問題、振り返り、PMOレビューなどの追加コンテキストを追加
- `claude-code/` 配下に Claude Code 向け PM レビュー Skill を追加
- `docs/` 配下にツール別利用ガイドを追加

---

## [0.1.0] - 2026-05

### Added

- 初期 README
- `DISCLAIMER.md`
- `TERMS.md`
- `SECURITY.md`
- `LICENSE.md`
- 基本 `contexts/`
  - `PM_CONTEXT.md`
  - `PROJECT_HEALTH_CHECK.md`
  - `STATUS_REPORT_CONTEXT.md`
  - `ISSUE_RISK_CONTEXT.md`
  - `FIRE_RESPONSE_FIRST_72H.md`
  - `CLIENT_COMMUNICATION_CONTEXT.md`
- 基本 `prompts/`
  - `status-report.md`
  - `issue-risk-review.md`
  - `client-communication.md`
  - `fire-response.md`
- ChatGPT / Gemini / Claude / Claude Code 向け初期ドキュメント

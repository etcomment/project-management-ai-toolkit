# Changelog

このファイルでは、project-management-ai-contexts の主な変更履歴を記録します。

## [Unreleased]

### Changed

- リポジトリ全体を再構成
  - `claude-code/skills/` を `.claude/skills/` に移動
  - `chatgpt/`、`gemini/`、`claude/`、`claude-code/` を廃止
  - 設定用指示文を `instructions/` に統合
  - ツール別ガイドを `docs/tools/` に統合
  - `CONTRIBUTING.md`、`SECURITY.md` を `.github/` に移動
  - `DISCLAIMER.md`、`TERMS.md` を `docs/legal/` に移動
  - `CHANGELOG.md`、`ROADMAP.md` を `docs/meta/` に移動

### Added

- `instructions/` ディレクトリ（ChatGPT / Gemini / Claude 向け設定用指示文）
- `docs/tools/chatgpt.md`、`docs/tools/gemini.md`、`docs/tools/claude.md`、`docs/tools/claude-code.md`

---

## [0.3.1] - 2026-05

### Added

- Claude Code向けの用途別 Skill を追加（現在は `.claude/skills/` に配置）
  - `.claude/skills/project-health-check/SKILL.md`
  - `.claude/skills/status-report/SKILL.md`
  - `.claude/skills/issue-risk-review/SKILL.md`
  - `.claude/skills/client-communication/SKILL.md`
  - `.claude/skills/fire-response-first-72h/SKILL.md`
  - `.claude/skills/meeting-minutes/SKILL.md`
  - `.claude/skills/scope-change-review/SKILL.md`
  - `.claude/skills/delay-recovery/SKILL.md`

### Changed

- `prompts/` の内容を `contexts/` 各ファイルの Prompt Template に統合し、リポジトリをコンテキストファイル中心の構成に整理

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

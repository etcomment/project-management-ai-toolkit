# Roadmap

このドキュメントでは、project-management-ai-toolkit の今後の追加予定・改善方針を公開します。

> [!NOTE]
> これらはあくまでも現時点の予定であり、実施を確約するものではありません。
> 安全性・免責・機密情報保護を優先し、方針は変更される場合があります。

---

## Done

完了済みの項目です。

- `docs/learning-roadmap.md` の追加
- READMEに「初めての方へ：次に何をすればよいか」セクションを追加
- 用途別マップと学習テーマの接続を強化
- `examples/` から学習ロードマップへの導線を追加
- Discordコミュニティ案内の追加（正式案内に更新・「準備中」表記を解消）
- READMEのGitHub流入向け導線改善（公式サイト・コース診断・講師クーポンページへのUTM付きリンク整理）
- Discord案内の「準備中」表記の解消・/community/ への統一
- 各ロードマップへの「体系的に学びたい場合」の導線追加
- use-case-mapの「次の行動」CTA追加
- `.claude/skills/README.md` の追加（Skill一覧・使い方ガイド）
- `.claude/skills/pm-ai-diagnosis/SKILL.md` の追加（PM課題・AI活用課題の診断入口Skill）
- `.claude/skills/project-risk-radar/SKILL.md` の追加（表面化していないリスク検知Skill）
- `.claude/skills/pm-decision-support/SKILL.md` の追加（PM意思決定構造化Skill）
- `.claude/skills/stakeholder-strategy/SKILL.md` の追加（ステークホルダー別伝達戦略Skill）
- `.claude/skills/ai-output-governance-review/SKILL.md` の追加（AI出力ガバナンスレビューSkill）
- `examples/pm-ai-diagnosis-example.md` の追加
- `examples/project-risk-radar-example.md` の追加
- `examples/ai-output-governance-review-example.md` の追加
- `docs/tools/claude-code.md` に上位Skillの利用例を追加
- `examples/README.md` に新規サンプルを追加
- `contexts/*_CONTEXT.md` にClaude向けXMLタグ版Prompt Templateを追加
- `instructions/claude-project-instructions.md` にClaude向け構造化指示文（XMLタグ版）を追加
- `docs/tools/claude-code.md` の利用例4〜7をXMLタグ構造に整理
- `docs/tools/claude.md` にXMLタグ構造のプロンプト例セクションを追加
- `examples/` の主要サンプルにClaude向け構造化プロンプト（XMLタグ版）を追加

---

## Short-term

近い将来に対応予定の項目です。

- `CONTRIBUTING.md` / Issue Template / PR Template の整備
- `examples/` の追加改善
- 各ファイルの表記ゆれ修正
- Claude Code Skill の公式ベストプラクティス準拠レビュー

---

## Mid-term

中期的に検討・対応予定の項目です。

- GitHub経由CTAの効果測定（UTMパラメータ活用）
- 公式サイト側の学習ロードマップ・課題別パックとの接続強化
- 経路別クーポンURLの運用整理
- 用途別AI Contextsと関連学習テーマの対応表を拡充
- 英語READMEや海外向け案内を検討する場合は、既存方針に合わせる
- 用途別サンプルの追加

  - `examples/stakeholder-report-example.md`
  - `examples/estimation-example.md`
  - `examples/pmo-review-example.md`
  - `examples/engineer-to-pm-report-example.md`

---

## Not planned

以下は現時点で追加を予定していません。

- 実行可能な hooks の提供
- shell script の提供
- MCP設定の提供
- GitHub Actions の提供
- 自動コミット・自動デプロイ機能の提供
- APIキーを使うサンプルの提供
- 実案件データを使ったサンプルの提供

このリポジトリは「安全なPM向けAIコンテキストファイル集」であり、実行系の自動化リポジトリではない方針を維持します。

---

## 注意

- ロードマップは変更される可能性があります。
- 安全性・免責・機密情報保護を常に優先します。
- AI出力は業務判断の代替ではないという方針は変えません。

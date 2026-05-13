# Claude Code Skills for PM × AI

このディレクトリには、PM業務とAI活用を支援するClaude Code向けSkillを配置しています。

各Skillは **Markdownドキュメントのみ** です。hooks、command、shell script、MCP設定、GitHub Actions、自動コミット、自動デプロイは含みません。

---

## まず使う

迷ったときや、自分の状況に合うContextやSkillを選びたいときは、ここから始めてください。

- **`pm-ai-diagnosis/SKILL.md`**
  - PM課題・AI活用課題を切り分け、使うべきContextやSkillを案内する
  - **最初に使うならこのSkillが起点です**

---

## リスクを見つける

- **`project-risk-radar/SKILL.md`**
  - 進捗メモ・課題一覧・会議メモから、表面化していないリスクを検知する
- **`issue-risk-review/SKILL.md`**
  - 課題・リスクの抜け漏れ、担当者不明、期限不明を確認する

---

## 判断する

- **`pm-decision-support/SKILL.md`**
  - エスカレーション、顧客説明、方針選択などのPM判断を構造化する

---

## 伝える

- **`stakeholder-strategy/SKILL.md`**
  - 顧客・上長・開発チーム・経営層など、相手別の伝え方を整理する
- **`client-communication/SKILL.md`**
  - 顧客向け説明文・相談文・報告文のたたき台を作成する
- **`status-report/SKILL.md`**
  - 社内向け・顧客向け・上長向けの進捗報告を整理する

---

## AI出力を確認する

- **`ai-output-governance-review/SKILL.md`**
  - AI出力を実務利用する前に、断定表現・機密情報・契約リスクを確認する

---

## 会議・変更・遅延を整理する

- **`meeting-minutes/SKILL.md`**
  - 会議メモから議事録・決定事項・TODO・次回確認事項を整理する
- **`scope-change-review/SKILL.md`**
  - 仕様変更・スコープ変更の影響範囲・工数・納期・費用を整理する
- **`delay-recovery/SKILL.md`**
  - 遅延発生時の原因・影響範囲・リカバリー案・説明方針を整理する
- **`fire-response-first-72h/SKILL.md`**
  - 炎上初動72時間で事実・影響・未確認事項・初動対応を整理する

---

## 汎用レビュー・ヘルスチェック

- **`pm-review/SKILL.md`**
  - PM視点でプロジェクト状況・Issue・進捗・課題・リスク・次アクションをレビューする
- **`project-health-check/SKILL.md`**
  - プロジェクト全体の健全度を定期確認し、危険度・リスク・次アクションを整理する

---

## 注意事項

- 各Skillはドキュメントのみです。実行系の自動化機能は提供しません
- AI出力は業務判断・契約判断・法務判断・納期判断・品質判断の代替ではありません
- 出力内容は必ず人間が確認・修正してから利用してください
- 顧客名・個人名・会社名・契約情報・認証情報・議事録全文・本番コードを入力しないでください
- 業務情報を使う場合は、匿名化・要約化・マスキングしてください
- hooks / command / shell script / MCP設定 / GitHub Actions / 自動コミット / 自動デプロイは含みません

関連ドキュメント：
- [`docs/ai-safety.md`](../../docs/ai-safety.md)
- [`docs/use-case-map.md`](../../docs/use-case-map.md)
- [`docs/tools/claude-code.md`](../../docs/tools/claude-code.md)

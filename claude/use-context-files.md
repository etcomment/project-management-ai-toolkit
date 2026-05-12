# Claudeでコンテキストファイルを使う方法

---

## 基本方針

- まず `contexts/PM_CONTEXT.md` を前提として読み込ませる
- 次に目的に応じた用途別 `contexts/*.md` を追加する
- 不要なファイルをすべて入れる必要はない
- 各 `contexts/*.md` の `Prompt Template` を使えば、AIへの依頼文を作れる

---

## 通常チャットで使う場合

以下の流れで使ってください。

1. `contexts/PM_CONTEXT.md` の内容をチャットに貼り付ける
2. 目的に合う用途別コンテキストを貼り付ける
3. **マスキング済みの**案件情報を貼り付ける
4. `contexts/*.md` の `Prompt Template` を参考に出力形式を指定する
5. AI出力を人間が確認する

---

## Claude Projectsで使う場合

1. `claude-project-instructions.md` をプロジェクト指示に設定する
2. 必要に応じて `contexts/PM_CONTEXT.md` と `docs/ai-safety.md` をProject Knowledgeに追加する
3. 案件ごとに用途別コンテキストをチャットに貼り付ける
4. 実案件情報はマスキング・要約してから入力する

---

## 長文コンテキストを渡す場合の注意

- 議事録の全文をそのまま貼り付けない
- 顧客名・個人名・契約情報を削除する
- 長文は「事実」「課題」「未決事項」「次アクション」に要約してから貼り付ける
- 不要な過去情報を入れすぎない
- AI出力の品質は、入力情報の品質に依存します

---

## 用途別の組み合わせ例

| 目的 | 使用ファイル |
|---|---|
| プロジェクトヘルスチェック | `contexts/PM_CONTEXT.md` + `contexts/PROJECT_HEALTH_CHECK.md` |
| 進捗報告 | `contexts/PM_CONTEXT.md` + `contexts/STATUS_REPORT_CONTEXT.md` |
| 課題・リスク整理 | `contexts/PM_CONTEXT.md` + `contexts/ISSUE_RISK_CONTEXT.md` |
| 顧客説明 | `contexts/PM_CONTEXT.md` + `contexts/CLIENT_COMMUNICATION_CONTEXT.md` |
| 炎上初動 | `contexts/PM_CONTEXT.md` + `contexts/FIRE_RESPONSE_FIRST_72H.md` |
| スコープ変更 | `contexts/PM_CONTEXT.md` + `contexts/SCOPE_CHANGE_CONTEXT.md` |

---

## Claude Code Skillと併用する場合

- Claudeで文書整理・報告文のたたき台作成、Claude Codeでリポジトリ内のREADME・Issue・仕様メモのPMレビュー、という使い分けができます
- `claude-code/skills/` は実行系ではなく、PM実務の観点をClaude Codeに伝えるドキュメントです
- hooks、command、MCP設定、自動実行は含みません

---

## 入力前の安全確認

> [!IMPORTANT]
> 入力前に必ず以下を確認してください。

- [docs/ai-safety.md](../docs/ai-safety.md) を確認する
- 顧客名・個人名・会社名・契約情報・認証情報を削除する
- ソースコードやAPIキーを入力しない
- NDA・顧客契約・社内規程に反していないか確認する

---

## 出力後の確認

> [!CAUTION]
> AI出力をそのまま業務に使わないでください。

- AI出力は業務判断の代替ではありません
- 顧客提出・社内報告・契約判断・納期回答には必ず人間が確認してください
- 必要に応じて上長・法務・PMOに確認してください

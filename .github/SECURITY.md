# セキュリティポリシー / Security Policy

---

## 1. このリポジトリのセキュリティ方針

本リポジトリ「project-management-ai-contexts」は、PM業務向けの生成AI活用コンテキストファイルおよびプロンプトテンプレートを提供するものです。

以下のセキュリティ方針に基づいて管理・運用しています。

---

## 2. このリポジトリに含まれないもの

本リポジトリには、以下を意図的に含めていません。

- 実行可能な hooks
- shell スクリプト / PowerShell スクリプト
- GitHub Actions ワークフロー
- MCP設定ファイル
- package.json / workflow ファイル
- APIキー・トークン・パスワード・認証情報
- 自動コミット・自動デプロイの仕組み
- 外部サービスへの自動通信を行う設定

Claude Code 向けの Skill サンプル（`.claude/skills/pm-review/SKILL.md`）は、PMレビューの考え方を示すサンプルドキュメントであり、実行系の自動化機能は提供しません。

---

## 3. Issue / Pull Request での注意事項

本リポジトリの Issue や Pull Request に、以下の情報を投稿しないでください。

- 個人情報（氏名、メールアドレス、電話番号等）
- 顧客情報・顧客企業名
- APIキー・アクセストークン・パスワード・認証情報
- 契約情報・機密情報
- 社内の未公開情報

**誤って機密情報を含むコメントを投稿した場合は、公開 Issue に追記せず、速やかにリポジトリ管理者に連絡してください。**

---

## 4. セキュリティ上の懸念を発見した場合

本リポジトリのファイルに以下のような問題を発見した場合は、公開 Issue には書かずに、下記の方法でご連絡ください。

- 機密情報・個人情報が誤って含まれている可能性がある
- 危険な記述・脆弱なサンプルが含まれている
- その他、セキュリティ上の懸念がある

**連絡先：**

株式会社テックエイド
公式サイト：https://techaide.jp/

（メールアドレスは公式サイトのお問い合わせフォームよりご連絡ください）

---

## 5. 利用者へのお願い

本リポジトリのコンテキストやプロンプトを生成AIサービスで利用する場合は、以下を守ってください。

- 顧客情報・個人情報・契約情報・認証情報・APIキー・パスワードを入力しないこと
- 所属組織の情報セキュリティ規程を確認すること
- 顧客との契約・NDAの内容を確認すること
- 利用するAIサービスの利用規約・プライバシーポリシー・データ利用条件を確認すること

詳細は [docs/ai-safety.md](../docs/ai-safety.md) を参照してください。

---

## 6. 設定ファイル・外部スクリプトの安全な取り扱いについて

本リポジトリ自体には実行可能ファイル・hooks・自動実行設定は含まれていません。
ただし、他のリポジトリや外部の設定ファイル（`.claude/settings.json`、`.vscode/tasks.json`、`package.json` 等）を参照・導入する際には、以下の点に注意してください。
（2026年時点で、npm サプライチェーン攻撃・Claude Code hooks 悪用・VS Code tasks 悪用などの手法が報告されています。）

### `.claude/settings.json` の hooks について

- 本リポジトリは `.claude/settings.json` を配布しません。hooks は含まれていません。
- **他のリポジトリや外部サンプルの `.claude/settings.json` を導入する場合は、`hooks` の内容を必ず確認してください。**
- `PreToolUse` / `PostToolUse` / `SessionStart` 等の hooks に、curl / wget / powershell / npm / npx / bash / python を含む記述がある場合は、導入前に内容を精査してください。
- `.claude/settings.local.json` はローカル個人設定ファイルです。コミット・共有しないでください。

### `.vscode/tasks.json` の自動実行について

- 本リポジトリは `.vscode/tasks.json` を配布しません。
- **他のリポジトリの `.vscode/tasks.json` を導入する場合は、`runOn: folderOpen` や自動実行タスクの内容を必ず確認してください。**
- 信頼できないタスクをワークスペースに追加しないでください。

### 外部スクリプト・パッケージの実行について

- **`npx <パッケージ名>` や `npm exec` は、バージョン固定・lockfile 管理されていない場合、悪意あるコードを実行するリスクがあります。**
- `curl URL | sh` / `wget URL | sh` / `Invoke-WebRequest` で取得したスクリプトを即時実行することは避けてください。
- 信頼できないソースの `package.json` を `npm install` する前に、`postinstall` / `preinstall` / `prepare` スクリプトを確認してください。

### GitHub Actions について

- `pull_request_target` を使用するワークフローには、PR由来コードの権限昇格リスクがあります。
- `actions/cache` の `restore-keys` は、信頼済みキャッシュの汚染リスクに注意してください。
- `id-token: write` は必要最小限の job にのみ付与してください。

---

## 7. 関連文書

- 免責事項：[docs/legal/DISCLAIMER.md](../docs/legal/DISCLAIMER.md)
- 利用規約：[docs/legal/TERMS.md](../docs/legal/TERMS.md)
- AI利用時の安全ガイド：[docs/ai-safety.md](../docs/ai-safety.md)

---

*株式会社テックエイド*
*https://techaide.jp/*

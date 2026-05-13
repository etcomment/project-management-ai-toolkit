# セキュリティ・サプライチェーン点検レポート

## 検査情報

| 項目 | 内容 |
|---|---|
| 検査日時 | 2026年5月13日 |
| 検査対象リポジトリ | ryotasuzukitechaide/project-management-ai-toolkit |
| 検査実施者 | GitHub Copilot（Claude Sonnet 4.6）/ サイバーセキュリティエンジニア視点 |
| 検査種別 | 静的解析（ファイル読み取り・キーワード検索）|
| 実行した破壊的操作 | なし |

---

## 1. リポジトリ構造の概要

### 種別分類

**配布用テンプレート・ドキュメント中心リポジトリ**

実行系ファイル（shell スクリプト、JavaScript、TypeScript、Python、PowerShell 等）は一切存在しない。
全コンテンツは `.md`（Markdown）ファイルのみで構成された、PM業務向けAIコンテキスト集・プロンプトテンプレート集。

### ディレクトリ構成（公開対象）

```
project-management-ai-toolkit/
├── README.md
├── LICENSE.md
├── .gitignore
├── contexts/           PM向けAIコンテキスト（16ファイル）
├── instructions/       各AIツールの設定欄用指示文（4ファイル）
├── examples/           架空データによる利用例（9ファイル）
├── docs/               使い方ガイド・安全ガイド・免責・法的文書（8ファイル）
│   ├── tools/          ツール別ガイド
│   ├── legal/          DISCLAIMER.md / TERMS.md
│   └── meta/           CHANGELOG.md / ROADMAP.md
├── .claude/skills/     Claude Code向けPM実務Skill（9ファイル）
└── .github/            SECURITY.md / CONTRIBUTING.md / ISSUE_TEMPLATE / PRテンプレート
```

### 存在しないもの（確認済み）

| 対象 | 有無 |
|---|---|
| package.json | なし |
| node_modules/ | なし |
| .github/workflows/*.yml | なし |
| .github/dependabot.yml | なし |
| .vscode/tasks.json | なし |
| .vscode/settings.json | なし |
| .vscode/launch.json | なし |
| .claude/settings.json | なし |
| .claude/settings.local.json | なし |
| CLAUDE.md | なし |
| scripts/ | なし |
| bin/ | なし |
| tools/ | なし（docs/tools/ は存在するがMarkdownのみ） |
| Dockerfile | なし |
| docker-compose.yml | なし |
| *.sh / *.ps1 / *.py / *.js / *.ts | なし |

---

## 2. 検査対象ファイル一覧

```
全ファイル数：54ファイル（すべて .md または .yml）
.gitignore （テキスト設定ファイル）
.github/ISSUE_TEMPLATE/config.yml
```

---

## 3. Public 配布物としてのリスク評価

### 概要

本リポジトリは **ドキュメント・テンプレート専用リポジトリ** であり、実行可能なコード・スクリプト・設定ファイルを意図的に排除した設計になっている。

README・SECURITY.md・ai-safety.md・docs/tools/claude-code.md に、利用者向けの安全注意書きが多層的に記載されており、Public 配布物としての安全設計は全体的に適切。

### 確認した安全対策（既存）

| 項目 | 状態 |
|---|---|
| hooks を含まないことを明示（README / SECURITY.md / 全Skillファイル） | ✅ |
| 自動実行コマンドを含まないことを明示 | ✅ |
| MCP設定・GitHub Actions を含まないことを明示 | ✅ |
| APIキー・認証情報の入力禁止を明示（README・SECURITY.md・ai-safety.md） | ✅ |
| 架空データのみでサンプルを構成 | ✅ |
| AI出力の人間レビュー義務を明示 | ✅ |
| Issue / PR テンプレートに安全チェックリストあり | ✅ |
| PRテンプレートに「hooks・shell script・GitHub Actions を追加していない」チェック項目あり | ✅ |
| CONTRIBUTING.md に安全方針あり | ✅ |
| docs/ai-safety.md に詳細な入力禁止情報リストあり | ✅ |

---

## 4. Claude Code 関連ファイルの確認結果

### 確認対象

- `.claude/settings.json` — **存在しない**（意図的に未配布）
- `.claude/settings.local.json` — **存在しない**（意図的に未配布）
- `.claude/commands/` — **存在しない**
- `.claude/agents/` — **存在しない**
- `.claude/skills/` — **9ファイル存在**（全て `.md`）
- `CLAUDE.md` — **存在しない**

### Skill ファイルの確認結果

| Skill | hooks定義 | 外部通信 | トークン参照 | 実行コマンド | 安全宣言 |
|---|---|---|---|---|---|
| pm-review/SKILL.md | なし | なし | なし | なし | ✅ あり |
| status-report/SKILL.md | なし | なし | なし | なし | ✅ あり |
| project-health-check/SKILL.md | なし | なし | なし | なし | ✅ あり |
| issue-risk-review/SKILL.md | なし | なし | なし | なし | ✅ あり |
| client-communication/SKILL.md | なし | なし | なし | なし | ✅ あり |
| fire-response-first-72h/SKILL.md | なし | なし | なし | なし | ✅ あり |
| meeting-minutes/SKILL.md | なし | なし | なし | なし | ✅ あり |
| scope-change-review/SKILL.md | なし | なし | なし | なし | ✅ あり |
| delay-recovery/SKILL.md | なし | なし | なし | なし | ✅ あり |

**判定：問題なし。全 Skill ファイルは PM 実務ガイダンスを記述したドキュメントのみ。**

---

## 5. VS Code 設定ファイルの確認結果

- `.vscode/tasks.json` — **存在しない**
- `.vscode/settings.json` — **存在しない**
- `.vscode/launch.json` — **存在しない**
- `.vscode/extensions.json` — **存在しない**

**判定：問題なし。.vscode/ ディレクトリ自体が存在しない（.gitignore にも除外済み）。**

---

## 6. npm / Node.js 依存の確認結果

- `package.json` — **存在しない**
- `package-lock.json` — **存在しない**（.gitignore にも除外済み）
- `pnpm-lock.yaml` — **存在しない**
- `yarn.lock` — **存在しない**
- `npm-shrinkwrap.json` — **存在しない**
- `.npmrc` — **存在しない**
- `node_modules/` — **存在しない**

**判定：npm 実行系の依存は現時点で皆無。**

README・docs 内の手順にも `npm install` / `npx` / `npm exec` の記述はなし（IoCキーワード検索で確認済み）。

---

## 7. GitHub Actions の確認結果

- `.github/workflows/` — **存在しない**
- `.github/dependabot.yml` — **存在しない**

**判定：GitHub Actions ワークフローが存在しないため、CI/CDに関する攻撃リスクは現時点でゼロ。**

ただし、将来 GitHub Actions を追加する場合は以下を必須とすること（残課題参照）。

---

## 8. scripts / tools / bin の確認結果

- `scripts/` — **存在しない**
- `bin/` — **存在しない**
- `tools/` — **存在しない**（`docs/tools/` は Markdown のみ）

**判定：問題なし。**

---

## 9. secrets / 個人情報 / 内部情報の混入確認結果

### 検索キーワードと結果

| キーワード | 結果 |
|---|---|
| OPENAI_API_KEY / ANTHROPIC_API_KEY / GEMINI_API_KEY / GOOGLE_API_KEY | 該当なし |
| GITHUB_TOKEN / GH_TOKEN / NPM_TOKEN / NODE_AUTH_TOKEN | 該当なし |
| PRIVATE_KEY / SECRET_KEY / ACCESS_TOKEN / REFRESH_TOKEN | 該当なし |
| CLIENT_SECRET / SERVICE_ACCOUNT | 該当なし |
| .env / .ssh / known_hosts | .gitignore内の除外定義のみ |
| credentials.json / token.json / service-account.json | .gitignore内の除外定義のみ |
| C:\Users\ / /Users/ / /home/ | .git/logs/ 内のみ（git の内部メタデータ、未公開） |
| 実在するメールアドレス | .git/logs/ 内のみ（git の内部メタデータ、未公開）|
| 内部URLらしき記述 | なし |
| sk- / pk_ 形式のAPIキー | なし |

### 補足

`.git/logs/HEAD` にはコミット者のメールアドレス（`ryota.suzuki@techaide.jp`）が含まれているが、これは Git の内部メタデータであり、リポジトリの公開コンテンツには含まれない（git push 後に GitHub で公開されるコミット履歴には Git ログ形式で表示される可能性があるが、README等に直接記載されているものではなく、意図的な公開情報として問題なし）。

`techaide.jp` の URL・社名は、`LICENSE.md` / `README.md` / `SECURITY.md` に意図的に公開情報として記載されており、問題なし。

**判定：secrets・個人情報・内部情報の混入なし。**

---

## 10. README / docs の安全注意書き確認結果

### 確認した必要項目と状態（修正後）

| 必要な注意書き | 記載場所 | 修正前後 |
|---|---|---|
| 本リポジトリのファイルを導入する前に内容を確認すること | README.md / SECURITY.md | 修正前から存在 |
| .claude/settings.json の hooks は不用意に導入しないこと | SECURITY.md §6（新設）/ claude-code.md | **修正で追加** |
| .vscode/tasks.json の自動実行設定は不用意に導入しないこと | SECURITY.md §6（新設） | **修正で追加** |
| 信頼できない npx / npm exec / curl / wget を実行しないこと | SECURITY.md §6（新設） | **修正で追加** |
| APIキー・トークン・秘密情報をプロンプトに含めないこと | README.md / SECURITY.md / ai-safety.md | 修正前から存在 |
| Claude Code / ChatGPT / Gemini に投入する情報は規程確認すること | SECURITY.md / ai-safety.md | 修正前から存在 |
| 利用前に自社環境に合わせて内容をレビューすること | README.md / ai-safety.md | 修正前から存在 |
| pull_request_target / actions/cache / id-token リスクの説明 | SECURITY.md §6（新設） | **修正で追加** |

---

## 11. .gitignore の確認結果

### 修正前の不足項目

| 不足項目 | リスク | 対応 |
|---|---|---|
| `token.json` | OAuth トークンファイルの誤コミット防止 | **追加済み** |
| `service-account.json` | GCP サービスアカウントキーの誤コミット防止 | **追加済み** |
| `client_secret.json` | OAuth クライアントシークレットの誤コミット防止 | **追加済み** |
| `dist/` | ビルド成果物の誤コミット防止 | **追加済み** |
| `build/` | ビルド成果物の誤コミット防止 | **追加済み** |
| `.claude/settings.local.json` | Claude Code ローカル設定（個人hooks等）の誤コミット防止 | **追加済み** |

### 修正後の状態

すべての主要 secrets・認証情報ファイル・ローカル設定・ビルド成果物が `.gitignore` に含まれている。

---

## 12. Dependabot / 継続監視の確認結果

`.github/dependabot.yml` は存在しない。

現時点では `package.json` / GitHub Actions が存在しないため、Dependabot の優先度は低い。
ただし、将来 GitHub Actions を導入した場合は、`github-actions` エコシステム向けの Dependabot 設定を追加することを推奨する（残課題参照）。

---

## 13. 検索した IoC 一覧

### 検索したキーワード

```
@tanstack / @tanstack/react-router / @tanstack/react-start / tanstack
axios / plain-crypto-js
WAVESHAPER / SANDWORM_MODE / Mini Shai-Hulud / Shai-Hulud / TeamPCP
OpenSearch / Mistral / Guardrails / UiPath / Squawk
postinstall / preinstall / prepare / install / lifecycle
npm token / NPM_TOKEN / NODE_AUTH_TOKEN / GITHUB_TOKEN / GH_TOKEN
id-token / OIDC / pull_request_target / actions/cache / restore-keys
~/.npm / node_modules / .env / .ssh / known_hosts / ssh-key
curl / wget / Invoke-WebRequest / iwr / powershell -enc
node -e / eval / child_process / exec / spawn / subprocess
os.system / shell=True / Function( / rm -rf / del /s / rmdir /s
fs.rm / fs.rmSync / homedir / os.homedir / process.env
OPENAI_API_KEY / ANTHROPIC_API_KEY / GEMINI_API_KEY / GOOGLE_API_KEY
NPM_TOKEN / PRIVATE_KEY / SECRET_KEY / ACCESS_TOKEN / REFRESH_TOKEN
CLIENT_SECRET / SERVICE_ACCOUNT
hooks: (設定値として)
PreToolUse / PostToolUse / SessionStart / UserPromptSubmit / PreCompact / SubagentStop
bash -c / sh -c / cmd /c
```

### 該当したキーワード（要注意なし）

| キーワード | 場所 | 評価 |
|---|---|---|
| `hooks` | 全 Skill ファイル・README・SECURITY.md 等（18箇所） | **安全** — すべて「hooks を含まない」という否定的説明文のみ |
| `shell` | 全 Skill ファイル・SECURITY.md（8箇所） | **安全** — すべて「shell script を含まない」という否定的説明文のみ |
| `eval` | `.git/hooks/*.sample` | **安全** — git 標準サンプルファイル（コミット対象外）|
| `exec` | `.git/hooks/*.sample` | **安全** — git 標準サンプルファイル（コミット対象外）|
| `.env` | `.gitignore`（3箇所） | **安全** — 除外定義のみ |
| `credentials.json` | `.gitignore` | **安全** — 除外定義のみ |
| `techaide.jp` / 社名 | README / LICENSE / SECURITY.md | **安全** — 意図的な公開情報 |

### 該当しなかったキーワード

上記 IoC リストの残り全てについて、コミット対象ファイル（`.md` / `.yml`）内に該当なし。

---

## 14. 検出したリスク

| No. | 重大度 | 対象 | 内容 |
|---|---|---|---|
| R-01 | **LOW** | `.gitignore` | `token.json` / `service-account.json` / `client_secret.json` / `dist/` / `build/` / `.claude/settings.local.json` が未記載 |
| R-02 | **LOW** | `.github/SECURITY.md` | サプライチェーン攻撃・hooks 安全注意・外部スクリプト実行注意が未記載（2026年時点の攻撃手法への対応が不十分） |
| R-03 | **INFO** | `.github/dependabot.yml` | 存在しない（現時点は npm / GitHub Actions がないため優先度低） |
| R-04 | **INFO** | `.github/workflows/` | 存在しない（GitHub Actions が追加された場合の設定ガイドが未整備） |

---

## 15. 修正したリスク

| No. | 重大度 | 修正ファイル | 修正内容 |
|---|---|---|---|
| R-01 | LOW | `.gitignore` | `token.json` / `service-account.json` / `client_secret.json` / `dist/` / `build/` / `.claude/settings.local.json` を追加 |
| R-02 | LOW | `.github/SECURITY.md` | 「6. サプライチェーン攻撃・設定ファイルに関する注意」セクションを新設。hooks・tasks・外部スクリプト・GitHub Actions に関する具体的な注意事項を記載 |

---

## 16. 修正しなかった理由

| No. | 内容 | 理由 |
|---|---|---|
| R-03 | Dependabot 未設定 | 現時点で npm / GitHub Actions が存在しないため、Dependabot 設定の効果がない。将来導入時の推奨事項として残課題に記録 |
| R-04 | GitHub Actions ガイド未整備 | 現時点では GitHub Actions が存在しないため対応不要。機能変更・ファイル追加に該当するため、事前相談が必要 |

---

## 17. 残リスク

現時点での残リスクは **情報提供レベル（INFO）** のみ。感染・侵害の兆候はなし。

| 優先度 | 内容 |
|---|---|
| LOW | 将来 GitHub Actions を導入する場合、`permissions: contents: read` の明示・`persist-credentials: false` の設定・secrets の step レベル分離を必須とすること |
| LOW | 将来 GitHub Actions を導入する場合、`.github/dependabot.yml`（`github-actions` エコシステム対象）を追加すること |
| INFO | 将来 `.claude/settings.json` を配布物に追加する場合、`hooks` が含まれないことを必ず確認し、PR チェックリストで明示的に確認すること |
| INFO | Markdown ファイル内のリンク切れは静的解析の対象外のため、定期的なリンクチェックを推奨 |

---

## 18. ローカル環境で手動確認が必要な項目

本レポートは静的解析（ファイル読み取り・キーワード検索）のみで実施した。以下の項目はローカル環境での手動確認を推奨する。

| 項目 | 方法 |
|---|---|
| `.git/` 内のコミット履歴に secrets が含まれていないか | `git log -p` で全コミット差分を目視確認、または `git-secrets` / `trufflehog` 等のシークレットスキャンツール（オフライン利用可能なもの）で確認 |
| `.git/config` の remote URL に意図しない push 先がないか | `cat .git/config` で確認済みだが、本番環境でも定期確認推奨 |
| GitHub リポジトリの Settings > Secrets and variables に不要な secrets がないか | GitHub Web UI で確認 |
| GitHub リポジトリの Settings > Actions > Workflow permissions が適切か | GitHub Web UI で確認 |

---

## 19. 実行したコマンド・検索内容

| 種別 | 内容 | 結果 |
|---|---|---|
| ディレクトリ探索 | `list_dir` / `file_search` / `grep_search` による全体構造把握 | 完了 |
| IoCキーワード検索（30種類以上） | `grep_search`（includeIgnoredFiles: true）による全ファイル検索 | 全て安全 |
| secrets・APIキー検索 | 15種類のキーワードで全ファイル検索 | 該当なし |
| 個人情報・内部情報検索 | メールアドレス・内部URL・パス等の正規表現検索 | git内部メタデータのみ |
| 実行可能ファイル確認 | PowerShell `Get-ChildItem` による拡張子フィルタリング | 実行可能ファイルなし |
| 最終IoCキーワード再検索 | PowerShell による全 `.md` / `.json` / `.yml` ファイルの一括検索 | 該当なし |

---

## 20. 今後の運用ルール

### 必須ルール（今後も継続）

1. `.claude/settings.json` を配布物に追加しない（hooks 不使用の原則を維持する）
2. `.claude/skills/` は Markdown のみとし、実行コマンド・外部URL・トークン参照を含めない
3. `examples/` のサンプルはすべて架空データとし、実在する顧客名・個人名・案件名を使用しない
4. PR マージ前に Pull Request テンプレートのチェックリストを全項目確認する
5. 定期的（四半期ごと）に本レポートと同様のキーワード検索を実施する

### 将来 GitHub Actions を導入する場合の必須設定

```yaml
permissions:
  contents: read

jobs:
  build:
    steps:
      - uses: actions/checkout@v4
        with:
          persist-credentials: false
```

- secrets は step レベルの `env:` にのみ配置する
- `pull_request_target` は原則使用しない
- `id-token: write` は必要な job のみに限定する
- `actions/cache` は PR 由来キーによる汚染リスクを考慮する

### .claude/settings.json を将来導入する場合

- `hooks` が定義されていないことを必須チェック項目とする
- `PreToolUse` / `PostToolUse` / `SessionStart` 等のフック定義は本リポジトリでは配布しない
- ローカル個人設定は `.claude/settings.local.json` に限定し、`.gitignore` 除外を維持する

---

## 21. 次に確認すべきリポジトリ

本リポジトリと連携・派生する可能性があるリポジトリが存在する場合は、同様の観点で点検すること。

特に以下のケースで再点検が必要：

- 本リポジトリをフォークして独自のカスタマイズを加えているリポジトリ
- 本リポジトリの Skill を参照する `.claude/settings.json` を含む他リポジトリ
- GitHub Actions ワークフローで本リポジトリのコンテンツを参照・デプロイするリポジトリ

---

## 検査サマリー

- **感染兆候：なし**
- **Public 配布物としての重大リスク：なし**
- **Claude Code hooks リスク：なし**（`.claude/settings.json` 自体が存在しない）
- **VS Code tasks リスク：なし**（`.vscode/` ディレクトリが存在しない）
- **npm / npx リスク：なし**（`package.json` が存在しない）
- **GitHub Actions リスク：なし**（ワークフローが存在しない）
- **secrets 混入リスク：なし**
- **修正済み：2件**（.gitignore 補強、SECURITY.md サプライチェーン注意セクション追加）
- **未修正・要判断：0件**（残リスクはすべて INFO / 将来対応）
- **実行した検証：静的解析のみ**（30種類以上のIoCキーワード検索、ファイル全件確認）
- **次の推奨対応：四半期ごとの定期キーワード検索実施、GitHub Actions 導入時のセキュア設定遵守**

---

## 検出結果

| 重大度 | 対象 | 内容 | 対応 |
|---|---|---|---|
| LOW | `.gitignore` | `token.json` / `service-account.json` / `client_secret.json` / `dist/` / `build/` / `.claude/settings.local.json` が未記載 | **修正済み** |
| LOW | `.github/SECURITY.md` | 2026年型サプライチェーン攻撃に対する hooks・tasks・外部スクリプト・GitHub Actions の注意書きが未記載 | **修正済み** |
| INFO | `.github/dependabot.yml` | 未設定（現時点は対象エコシステムなし） | 将来 GitHub Actions 導入時に対応 |
| INFO | `.github/workflows/` | ワークフロー未存在（追加時はセキュア設定必須） | 将来導入時のガイドとして SECURITY.md §6 に記載済み |

---

## 変更ファイル

| ファイル | 変更内容 |
|---|---|
| `.gitignore` | `token.json` / `service-account.json` / `client_secret.json` / `dist/` / `build/` / `.claude/settings.local.json` を追加 |
| `.github/SECURITY.md` | 「6. サプライチェーン攻撃・設定ファイルに関する注意」セクションを新設（旧§6 は §7 に繰り下げ） |

---

## 検証結果

| コマンド | 結果 |
|---|---|
| 全ファイル一覧取得（PowerShell Get-ChildItem） | 54ファイル、すべて .md または .yml 。実行可能ファイルなし |
| IoCキーワード再検索（30種類以上、修正後） | 該当なし（安全な説明文内の言及のみ） |
| 実行可能ファイル検索（.sh/.ps1/.py/.js/.ts/.bat/.cmd/.vbs） | 該当なし |
| secrets・APIキー・個人情報キーワード検索 | コミット対象ファイル内に該当なし |

---

## 残課題

| 優先度 | 内容 |
|---|---|
| LOW | 将来 GitHub Actions を導入する際に、`permissions` 明示・`persist-credentials: false`・secrets step 分離を必須設定とすること |
| LOW | 将来 GitHub Actions を導入する際に、`.github/dependabot.yml`（github-actions エコシステム対象）を追加すること |
| INFO | Markdown リンク切れチェックを定期実施すること（ツール例：`markdown-link-check` を GitHub Actions でローカル実行） |
| INFO | 四半期ごとに本レポートと同様の静的解析を実施し、新規追加ファイルに危険キーワードが混入していないことを確認すること |

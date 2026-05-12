# Project Management AI Contexts

ChatGPT / Gemini / Claude / Claude Code で使える、プロジェクトマネージャー・PMO・開発リーダー向けのAI Contextsファイル集です。

## 初めての方へ：次に何をすればよいか

このリポジトリを初めて見る方は、以下の順で確認すると理解しやすくなります。

1. [`docs/use-case-map.md`](docs/use-case-map.md) で、自分の状況に合うAI Contextsを選ぶ
2. [`examples/`](examples/) で具体的な使い方を確認する
3. 実務で使う前に [`docs/ai-safety.md`](docs/ai-safety.md) を確認する
4. 必要に応じて [`docs/learning-roadmap.md`](docs/learning-roadmap.md) で、PM・AI活用の学習テーマを確認する
5. 更新情報や活用Tipsを受け取りたい方は、[Discordコミュニティ](#discordコミュニティ)を確認する

---

## このリポジトリでできること

- PM業務でAIに渡す前提情報（AI Contexts）を整理できる
- 進捗報告・課題管理・顧客説明などのAI Contextsを試せる
- 架空サンプルを使って活用イメージを確認できる
- AI入力前の安全確認ポイントを理解できる

## 体系的に学ぶとよいこと

以下のようなテーマは、このリポジトリのAI Contextsだけでは補いにくい部分です。

- なぜその観点で情報を整理するのか
- PMとしてどの順番で考えるべきか
- 顧客・上司・チームにどう説明するのか
- AIの出力をどうレビューし、業務判断に落とし込むか
- チームや組織でAI活用を標準化する際の注意点

関連する学習テーマや講座情報は、テックエイド公式サイトで案内しています。

---

## このリポジトリの主役は `contexts/`

`contexts/` 配下にある Markdown ファイルが主役です。

AIに渡す前提情報・判断軸・Prompt Template がすべて各コンテキストファイルに含まれています。

```text
contexts/       → AIに渡すPMコンテキスト本体
instructions/   → ChatGPT / Gemini / Claude の設定欄にコピーする指示文
docs/tools/     → 各AIツールの使い方ガイド
examples/       → 架空データによる利用例
.claude/skills/ → Claude Codeが認識するProject Skill
.github/        → GitHub運用ファイル
```

## Quick Start

### 1. `contexts/PM_CONTEXT.md` を確認する

PM業務でAIに渡す共通前提が含まれています。

### 2. 用途に応じたコンテキストを選ぶ

| 目的 | 利用ファイル |
|---|---|
| プロジェクト状況をレビューしたい | `contexts/PROJECT_HEALTH_CHECK.md` |
| 進捗報告を作りたい | `contexts/STATUS_REPORT_CONTEXT.md` |
| 課題・リスクを整理したい | `contexts/ISSUE_RISK_CONTEXT.md` |
| 顧客向け説明文を作りたい | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` |
| 炎上初動を整理したい | `contexts/FIRE_RESPONSE_FIRST_72H.md` |

### 3. AIに読み込ませる

```
以下のコンテキストを前提として、プロジェクト状況をPM視点で整理してください。

【ここにコンテキストファイルの内容】

【ここに自分の案件状況を、機密情報を除いて入力】
```

### 4. 出力を人間が確認する

AIの出力は、そのまま顧客提出・社内報告・契約判断・納期回答に使わないでください。

## 追加ユースケース

| 用途 | コンテキストファイル |
|---|---|
| 会議メモから議事録・TODOを作る | `contexts/MEETING_MINUTES_CONTEXT.md` |
| 週次定例のアジェンダを作る | `contexts/WEEKLY_MEETING_CONTEXT.md` |
| 仕様変更・スコープ変更を整理する | `contexts/SCOPE_CHANGE_CONTEXT.md` |
| 遅延時のリカバリー方針を整理する | `contexts/DELAY_RECOVERY_CONTEXT.md` |
| 品質問題の原因と対策を整理する | `contexts/QUALITY_ISSUE_CONTEXT.md` |
| 振り返り・ポストモーテムを作る | `contexts/RETROSPECTIVE_CONTEXT.md` |
| ステークホルダー報告を整理する | `contexts/STAKEHOLDER_REPORT_CONTEXT.md` |
| 見積前提・不確実性を整理する | `contexts/ESTIMATION_CONTEXT.md` |
| PMO視点で案件横断レビューをする | `contexts/PMO_REVIEW_CONTEXT.md` |
| 開発リーダーからPMへの相談を整理する | `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md` |

## ツール別ガイド

各AIツールでの使い方は `docs/tools/` を参照してください。

| ツール | ガイド |
|---|---|
| ChatGPT | `docs/tools/chatgpt.md` |
| Gemini | `docs/tools/gemini.md` |
| Claude | `docs/tools/claude.md` |
| Claude Code | `docs/tools/claude-code.md` |

設定欄にコピーする指示文は `instructions/` にあります。

## Claude Code Skill

Claude Code 向け PM 実務 Skill は `.claude/skills/` 配下にあります。

- `.claude/skills/pm-review/SKILL.md`（汎用PMレビュー）
- `.claude/skills/project-health-check/SKILL.md`
- `.claude/skills/status-report/SKILL.md`
- `.claude/skills/issue-risk-review/SKILL.md`
- `.claude/skills/` 配下の用途別 Skill

Skill はドキュメントのみです。hooks、自動実行コマンド、MCP設定は含みません。

## リポジトリ構成

```
project-management-ai-contexts/
├── README.md
├── LICENSE.md
├── .gitignore
│
├── contexts/           ← 主役：PM向けAIコンテキスト本体
├── instructions/       ← 各AIツールの設定欄にコピーする指示文
├── examples/           ← 架空データによる利用例
│
├── docs/
│   ├── usage-guide.md
│   ├── ai-safety.md
│   ├── use-case-map.md
│   ├── learning-roadmap.md
│   ├── github-publishing-checklist.md
│   ├── tools/
│   │   ├── chatgpt.md
│   │   ├── gemini.md
│   │   ├── claude.md
│   │   └── claude-code.md
│   ├── legal/
│   │   ├── DISCLAIMER.md
│   │   └── TERMS.md
│   └── meta/
│       ├── CHANGELOG.md
│       └── ROADMAP.md
│
├── .claude/
│   └── skills/
│       ├── pm-review/SKILL.md
│       ├── project-health-check/SKILL.md
│       └── その他の用途別 Skill
│
└── .github/
    ├── CONTRIBUTING.md
    ├── SECURITY.md
    ├── pull_request_template.md
    └── ISSUE_TEMPLATE/
```

## 注意事項

> [!CAUTION]
> このリポジトリは、PM業務における生成AI活用を支援するための参考資料・サンプルです。
>
> AIの出力は、専門的判断、業務判断、契約判断、法務判断、税務判断、労務判断、セキュリティ判断を代替するものではありません。
>
> 実際の業務で利用する場合は、必ず人間が内容を確認してください。

## 入力してはいけない情報

生成AIサービスに、以下の情報を入力しないでください。

- 顧客名・個人名・会社名を含む機密情報
- 個人情報・契約情報・議事録全文
- 未公開の事業情報・ソースコード
- APIキー・パスワード・アクセストークン・認証情報
- NDAや顧客契約により外部送信が禁止されている情報

業務情報を扱う場合は、事前に匿名化・要約化・マスキングを行い、所属組織の情報セキュリティ規程・顧客契約・NDA・AIサービスの規約を確認してください。

## Claude Code 利用時の注意

`.claude/skills/` 配下には、Claude Code 向けの PM 実務 Skill を含みます。

以下は含めていません。

- 実行可能な hooks・自動実行コマンド
- MCP設定・GitHub Actions
- APIキーを使うサンプル・自動コミット・自動デプロイ

## Examples

`examples/` 配下のサンプルはすべて架空データです。実在する顧客情報・案件情報・個人情報は含みません。

## Discordコミュニティ

PM・AI活用ラボ（Discordコミュニティ）では、このリポジトリの更新情報、PM実務Tips、AI活用例を案内しています。

主な内容：

- 新しいAI Contextsやサンプルの更新情報
- PM業務でのAI活用Tips
- 学習ロードマップ
- 関連する学習テーマや講座情報

招待URL：TODO（Discordコミュニティ公開準備後に設定）

> [!NOTE]
> ※ 個別案件の詳細相談、機密情報を含む相談、環境依存の技術サポートは対象外です。
> ※ 投稿時は、会社名・顧客名・個人情報・機密情報を含めないでください。

---

## 関連情報

このリポジトリは、株式会社テックエイドが公開するPM業務向けAI活用コンテキスト集です。

PM実務・AI活用・関連講座の学習順については、テックエイド公式サイトでも案内しています。

- 公式サイト：[https://techaide.jp/](https://techaide.jp/)
- 学習ロードマップ：TODO（公式サイト側のページ公開後に設定）
- Udemy講師クーポン：TODO（クーポンページ公開後に設定）
- コース診断：TODO（診断ページ公開後に設定）

## Disclaimer

本リポジトリの内容および本リポジトリを利用して生成AIが出力する内容について、株式会社テックエイドは、正確性、完全性、有用性、最新性、特定目的への適合性を保証しません。

詳細は [`docs/legal/DISCLAIMER.md`](docs/legal/DISCLAIMER.md) を確認してください。

## License

このリポジトリの利用条件は `LICENSE.md` および [`docs/legal/TERMS.md`](docs/legal/TERMS.md) を確認してください。

## Security

セキュリティ上の懸念がある場合は、[`.github/SECURITY.md`](.github/SECURITY.md) を確認してください。

## Contributing

改善提案やPull Requestは歓迎します。詳細は [`.github/CONTRIBUTING.md`](.github/CONTRIBUTING.md) を確認してください。

IssueやPull Requestには、実在する顧客情報・個人情報・契約情報・APIキー・パスワード・トークン等を含めないでください。

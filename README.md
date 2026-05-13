# Project Management AI Toolkit

PM・PMO・開発リーダー向けに、ChatGPT / Gemini / Claude / Claude Code で使える AI Contexts、Prompt Template、Claude Code Skills、実務サンプルをまとめたAI活用ツールキットです。

## はじめての方へ

このリポジトリは、PM・PMO・開発リーダーが ChatGPT / Gemini / Claude / Claude Code を実務で活用するための、AI Contexts、Prompt Template、Claude Code Skills、実務サンプルを含むAI活用ツールキットです。

まず全体像を知りたい方は、公式サイトの紹介ページをご覧ください。

- [PM向けAI活用ツールキットを見る](https://techaide.jp/ai-toolkit/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [自分に合う学習テーマを診断する](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [PM・AI活用ラボを見る](https://techaide.jp/community/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [安全に使うための注意事項](docs/ai-safety.md)

## 初めての方へ：次に何をすればよいか

このリポジトリを初めて見る方は、以下の順で確認すると理解しやすくなります。

1. [`docs/use-case-map.md`](docs/use-case-map.md) で、自分の状況に合うAI Contextsを選ぶ
2. [`examples/`](examples/) で具体的な使い方を確認する
3. 実務で使う前に [`docs/ai-safety.md`](docs/ai-safety.md) を確認する
4. 必要に応じて [`docs/learning-roadmap.md`](docs/learning-roadmap.md) で、PM・AI活用の学習テーマを確認する
5. 体系的に学びたい場合は、[テックエイド公式サイト](https://techaide.jp/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)でコース案内を確認する
6. どの講座が自分に合うか迷う場合は、[コース診断](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)を活用する
7. 更新情報や活用Tipsを受け取りたい方は、[PM・AI活用ラボ](https://techaide.jp/community/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)を確認する

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

## このリポジトリの構成

このリポジトリは、PM実務でAIを活用するための複数のコンポーネントで構成されています。

```text
contexts/       → AI Contexts本体：AIに渡すPM業務の前提情報・判断軸・Prompt Template
instructions/   → 設定用指示文：ChatGPT / Gemini / Claude の設定欄にコピーする指示文
docs/tools/     → ツール別ガイド：各AIツールの使い方ガイド
examples/       → 実務サンプル：架空データによる利用例
.claude/skills/ → Claude Code Skills：Claude Codeが認識するPM実務向けSkill
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

初めて使う場合や、自分の状況に合うContextを選びたい場合は、まず以下のSkillを確認してください。

- `.claude/skills/pm-ai-diagnosis/SKILL.md`
  - PM課題とAI活用課題を切り分け、使うべきContextやSkillを案内します
- `.claude/skills/project-risk-radar/SKILL.md`
  - 表面化していないプロジェクトリスクを検知します
- `.claude/skills/pm-decision-support/SKILL.md`
  - PMの意思決定を構造化します
- `.claude/skills/stakeholder-strategy/SKILL.md`
  - 顧客・上長・開発チームなど相手別の伝え方を整理します
- `.claude/skills/ai-output-governance-review/SKILL.md`
  - AI出力を実務利用する前に、安全性・表現・確認漏れをレビューします

その他の用途別Skill（`.claude/skills/pm-review/SKILL.md`、`project-health-check`、`status-report`、`issue-risk-review` など）も含め、全Skill一覧は `.claude/skills/README.md` を参照してください。

Skill はドキュメントのみです。hooks、自動実行コマンド、MCP設定は含みません。

具体的な使い方を確認したい場合は、以下のサンプルも参照してください。

- `examples/pm-ai-diagnosis-example.md`
- `examples/project-risk-radar-example.md`
- `examples/ai-output-governance-review-example.md`

Claudeで利用する場合は、`contexts/` 各ファイル内の「Claude向け Prompt Template（XMLタグ版）」も参照してください。タスク、入力情報、制約、出力形式を分けて依頼できます。

## リポジトリ構成

```
project-management-ai-toolkit/
├── README.md
├── LICENSE.md
├── .gitignore
│
├── contexts/           ← AI Contexts本体：PM業務の前提情報・Prompt Template
├── instructions/       ← 設定用指示文：各AIツールの設定欄にコピーする指示文
├── examples/           ← 実務サンプル：架空データによる利用例
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

PM・AI活用ラボでは、このリポジトリの更新情報、PM業務でのAI活用Tips、学習ロードマップに関する情報を共有しています。

以下のような情報を受け取りたい方に向いています。

- 新しいAI Contextsやサンプルの更新情報
- ChatGPT / Gemini / Claude / Claude Codeでの活用例
- PM・PMO・開発リーダー向けの学習テーマ
- 関連するブログ記事・Udemy講座の案内
- 学習ロードマップや継続学習のヒント

参加前に、コミュニティの目的・ルール・対象外事項をご確認ください。

[PM・AI活用ラボを見る](https://techaide.jp/community/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)

詳細は [docs/community.md](docs/community.md) を参照してください。

> [!IMPORTANT]
> 個別案件の詳細相談、機密情報を含む相談、環境依存の技術サポートは対象外です。
>
> 投稿時は、会社名・顧客名・個人情報・機密情報を含めないでください。

---

## 関連情報

このリポジトリは、株式会社テックエイドが公開するPM向けAI活用ツールキットです。

- [公式サイト](https://techaide.jp/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [PM向けAI活用ツールキットを見る](https://techaide.jp/ai-toolkit/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [PM・AI活用ラボ](https://techaide.jp/community/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [コース診断](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [Udemy講師クーポンページ](https://techaide.jp/coupons/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [Udemy講座一覧](https://techaide.jp/courses/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [学習ロードマップ](https://techaide.jp/learning-roadmaps/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)

## Disclaimer

本リポジトリの内容および本リポジトリを利用して生成AIが出力する内容について、株式会社テックエイドは、正確性、完全性、有用性、最新性、特定目的への適合性を保証しません。

詳細は [`docs/legal/DISCLAIMER.md`](docs/legal/DISCLAIMER.md) を確認してください。

## License

このリポジトリの利用条件は `LICENSE.md` および [`docs/legal/TERMS.md`](docs/legal/TERMS.md) を確認してください。

## Security

セキュリティ上の懸念がある場合は、[`.github/SECURITY.md`](.github/SECURITY.md) を確認してください。

## Contributing

誤字脱字・安全上の懸念・改善提案はIssueでお知らせください。詳細は [`.github/CONTRIBUTING.md`](.github/CONTRIBUTING.md) を確認してください。

IssueやPull Requestには、実在する顧客情報・個人情報・契約情報・APIキー・パスワード・トークン等を含めないでください。

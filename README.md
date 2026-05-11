# Project Management AI Contexts

ChatGPT / Gemini / Claude / Claude Code で使える、プロジェクトマネージャー・PMO・開発リーダー向けのAIコンテキストファイルとプロンプトテンプレート集です。

このリポジトリは、PM業務における以下のような作業を、生成AIに相談しやすくするための Markdown ファイルを提供します。

- プロジェクト状況のレビュー
- 進捗報告の整理
- 課題・リスクの洗い出し
- 顧客向け説明文の作成
- 炎上初動72時間の整理
- Claude Code 向け PM レビュー Skill の利用

## このリポジトリの目的

生成AIは、PM業務の整理・報告・レビューの補助に活用できます。

ただし、AIにただ「進捗報告を作って」「リスクを洗い出して」と依頼しても、前提情報や判断軸が不足していると、実務で使いにくい出力になりがちです。

このリポジトリでは、PM業務でAIに読み込ませるためのコンテキストファイルと、用途別のプロンプトテンプレートを提供します。

AIにPM判断を代行させるのではなく、PM・PMO・開発リーダーが状況整理や判断材料の作成を効率化することを目的としています。

## 対応ツール

以下のAIツールでの利用を想定しています。

- ChatGPT
- Gemini
- Claude
- Claude Code

## 想定利用者

このリポジトリは、以下のような方を対象としています。

- プロジェクトマネージャー
- PMO
- エンジニアリングマネージャー
- 開発リーダー
- 新任PM
- PM業務に生成AIを活用したいITエンジニア
- 受託開発・業務システム開発・Web/アプリ開発に関わる管理者

## 主なユースケース

### 1. プロジェクトヘルスチェック

プロジェクトの進捗、課題、リスク、顧客状況、体制上の懸念を入力し、AIにPM視点でレビューさせます。

主な出力例：

- 現在の危険度
- 主要な懸念点
- 見落としている可能性があるリスク
- 顧客に確認すべきこと
- 社内で決めるべきこと
- 次に取るべきアクション

利用ファイル例：

- `contexts/PROJECT_HEALTH_CHECK.md`

---

### 2. 進捗報告の作成

今週の作業、完了事項、遅延事項、課題、来週予定を入力し、AIに報告文を整理させます。

主な出力例：

- 社内向け進捗報告
- 顧客向け進捗報告
- 上長向けサマリー
- リスク付き進捗報告
- 次アクション一覧

利用ファイル例：

- `contexts/STATUS_REPORT_CONTEXT.md`
- `prompts/status-report.md`

---

### 3. 課題・リスクレビュー

課題一覧や案件状況を入力し、AIに課題管理・リスク管理の観点で抜け漏れを確認させます。

主な出力例：

- 課題の分類
- 優先度の見直し
- 担当者不明の課題
- 期限不明の課題
- 影響範囲が曖昧な課題
- 追加で確認すべき事項
- エスカレーション候補

利用ファイル例：

- `contexts/ISSUE_RISK_CONTEXT.md`
- `prompts/issue-risk-review.md`

---

### 4. 顧客コミュニケーション

顧客に伝えたい内容、背景、課題、相談事項、選択肢を入力し、AIに顧客向け説明文のたたき台を作らせます。

主な出力例：

- 顧客向けメール案
- 状況説明文
- 相談文
- 遅延説明文
- 選択肢提示文
- 打ち合わせ前の説明メモ

利用ファイル例：

- `contexts/CLIENT_COMMUNICATION_CONTEXT.md`
- `prompts/client-communication.md`

---

### 5. 炎上初動72時間の整理

トラブル発生時に、事実、影響、未確認事項、初動対応を整理します。

主な出力例：

- 事実と推測の切り分け
- 影響範囲の整理
- 今日中に確認すべきこと
- 顧客に伝えるべきこと
- 社内で決めるべきこと
- 初動対応リスト
- 72時間以内の対応計画

利用ファイル例：

- `contexts/FIRE_RESPONSE_FIRST_72H.md`
- `prompts/fire-response.md`

---

### 6. Claude Code 向け PM レビュー Skill

Claude Code で、プロジェクトの README、Issue、仕様メモ、進捗メモなどをもとに、PM視点でレビューするための Skill サンプルです。

主な出力例：

- PM視点のレビュー
- Issueの曖昧さ
- 仕様未確定ポイント
- 進捗リスク
- 顧客確認が必要な点
- 次アクション不足
- PMに報告すべき事項

利用ファイル例：

- `claude-code/skills/pm-review/SKILL.md`

## リポジトリ構成

```text
project-management-ai-contexts/
├── README.md
├── DISCLAIMER.md
├── TERMS.md
├── SECURITY.md
├── LICENSE.md
├── docs/
│   ├── usage-guide.md
│   ├── ai-safety.md
│   ├── for-chatgpt.md
│   ├── for-gemini.md
│   ├── for-claude.md
│   └── for-claude-code.md
├── contexts/
│   ├── PM_CONTEXT.md
│   ├── PROJECT_HEALTH_CHECK.md
│   ├── STATUS_REPORT_CONTEXT.md
│   ├── ISSUE_RISK_CONTEXT.md
│   ├── FIRE_RESPONSE_FIRST_72H.md
│   └── CLIENT_COMMUNICATION_CONTEXT.md
├── prompts/
│   ├── status-report.md
│   ├── issue-risk-review.md
│   ├── client-communication.md
│   └── fire-response.md
├── chatgpt/
│   └── project-instructions.md
├── gemini/
│   └── gemini-instructions.md
├── claude/
│   └── claude-project-instructions.md
└── claude-code/
    ├── README.md
    └── skills/
        └── pm-review/
            └── SKILL.md
```

## Quick Start

### 1. 共通コンテキストを読む

まず、以下のファイルを確認してください。

```text
contexts/PM_CONTEXT.md
```

このファイルには、PM業務でAIに前提として渡すべき基本的な観点を記載しています。

### 2. 用途に応じたコンテキストを選ぶ

目的に応じて、以下のようにファイルを選びます。

| 目的               | 利用ファイル                            |
| ---------------- | --------------------------------- |
| プロジェクト状況をレビューしたい | `PROJECT_HEALTH_CHECK.md`         |
| 進捗報告を作りたい        | `STATUS_REPORT_CONTEXT.md`        |
| 課題・リスクを整理したい     | `ISSUE_RISK_CONTEXT.md`           |
| 顧客向け説明文を作りたい     | `CLIENT_COMMUNICATION_CONTEXT.md` |
| 炎上初動を整理したい       | `FIRE_RESPONSE_FIRST_72H.md`      |

### 3. AIツールに読み込ませる

ChatGPT、Gemini、Claude などに、対象のコンテキストファイルの内容を貼り付けます。

そのうえで、以下のように依頼します。

```text
以下のコンテキストを前提として、プロジェクト状況をPM視点で整理してください。

【ここにコンテキストファイルの内容】

【ここに自分の案件状況を、機密情報を除いて入力】
```

### 4. 出力を人間が確認する

AIの出力は、そのまま顧客提出・社内報告・契約判断・納期回答に使わないでください。

必ず人間が確認し、案件状況、契約条件、顧客との関係、社内ルールに合わせて修正してください。

## 注意事項

> [!CAUTION]
> このリポジトリは、PM業務における生成AI活用を支援するための参考資料・サンプルです。
>
> AIの出力は、専門的判断、業務判断、契約判断、法務判断、税務判断、労務判断、セキュリティ判断を代替するものではありません。
>
> 実際の業務で利用する場合は、必ず人間が内容を確認してください。

## 入力してはいけない情報

生成AIサービスに、以下の情報を入力しないでください。

* 顧客名
* 個人名
* 会社名を含む機密情報
* 個人情報
* 契約情報
* 議事録全文
* 未公開の事業情報
* ソースコード
* APIキー
* パスワード
* アクセストークン
* 認証情報
* NDAや顧客契約により外部送信が禁止されている情報

業務情報を扱う場合は、事前に匿名化、要約化、マスキングを行い、所属組織の情報セキュリティ規程、顧客契約、NDA、利用するAIサービスの規約を確認してください。

## Claude Code 利用時の注意

このリポジトリには、Claude Code 向けの Skill サンプルを含みます。

ただし、以下は含めていません。

* 実行可能な hooks
* 自動実行コマンド
* MCP設定
* GitHub Actions
* APIキーを使うサンプル
* 自動コミット
* 自動デプロイ
* ファイル削除や上書きを伴うスクリプト

Claude Code 向けファイルは、PMレビューの考え方を Skill として表現するための参考例です。

内容を理解しないまま、本番環境や顧客案件で利用しないでください。

## 公式サイト・関連情報

このリポジトリは、株式会社テックエイドが公開するPM業務向けAI活用コンテキスト集です。

* 公式サイト
  [https://techaide.jp/](https://techaide.jp/)

* 自分に合うUdemy講座を診断する
  [https://techaide.jp/course-diagnosis/](https://techaide.jp/course-diagnosis/)

* 今月のUdemy講師クーポンを見る
  [https://techaide.jp/coupons/](https://techaide.jp/coupons/)

## 体系的に学びたい方へ

このリポジトリは、PM業務で生成AIを使うための入口です。

進捗管理、課題管理、リスク管理、顧客説明、炎上初動、生成AI活用を体系的に学びたい方は、テックエイドのUdemy講座もご活用ください。

まずは、以下のページから自分に合う講座を確認できます。

[https://techaide.jp/course-diagnosis/](https://techaide.jp/course-diagnosis/)

## Disclaimer

本リポジトリの内容および本リポジトリを利用して生成AIが出力する内容について、株式会社テックエイドは、正確性、完全性、有用性、最新性、特定目的への適合性を保証しません。

本リポジトリは、専門家による助言、法的判断、税務判断、労務判断、セキュリティ診断、プロジェクト監査、業務上の意思決定を代替するものではありません。

重要な業務で利用する場合は、必ず利用者自身の責任で内容を確認し、必要に応じて所属組織の責任者または専門家に確認してください。

詳細は `DISCLAIMER.md` を確認してください。

## License

このリポジトリの利用条件は `LICENSE.md` および `TERMS.md` を確認してください。

無断再販売、有料教材への組み込み、自社商品としての再配布、著作権表示の削除、公式コンテンツであるかのような誤認表示は禁止します。

## Security

セキュリティ上の懸念、危険な記述、誤って含まれている可能性のある機密情報を見つけた場合は、`SECURITY.md` を確認してください。
# Claude Code 向けディレクトリ / Claude Code Directory

---

## このディレクトリについて

このディレクトリ（`claude-code/`）は、Claude Code で本リポジトリのコンテキストを活用するためのサンプルを提供します。

Claude Code は、ターミナルで動作するAIコーディングアシスタントです。

このディレクトリでは、Claude Code をコーディングではなく **プロジェクト管理・PM業務の観点でのレビュー** に活用するためのサンプルを提供します。

---

## ディレクトリ構成

```text
claude-code/
├── README.md                      ← このファイル
└── skills/
    └── pm-review/
        └── SKILL.md               ← PMレビュー観点のSkillサンプル
```

---

## pm-review Skill について

`skills/pm-review/SKILL.md` は、Claude Code の Skill 形式に沿って記述した **PMレビュー観点のサンプルドキュメント** です。

### このSkillの目的

- Claude Code に「PM視点でレビューする」という観点を伝えるためのサンプル
- プロジェクトの README、Issue、仕様メモ、進捗メモを PM 視点でレビューする際の参考

### このSkillに含まれないもの

このSkillは **サンプルドキュメント** であり、以下は含まれていません。

| 含まれないもの | 理由 |
|---|---|
| 実行可能な hooks | 意図しない自動実行を防ぐため |
| 自動実行コマンド | 意図しない自動実行を防ぐため |
| shell スクリプト | 意図しない自動実行を防ぐため |
| MCP設定 | 外部サービスとの自動連携を防ぐため |
| GitHub Actions | CI/CDの自動実行を防ぐため |
| 自動コミット | 意図しないコード変更を防ぐため |
| 自動デプロイ | 本番環境への意図しない影響を防ぐため |
| 外部サービスへの自動通信 | 情報漏洩リスクを防ぐため |

---

## 使い方

Claude Code のチャットで、以下のように依頼します。

### 例1：プロジェクトのREADMEをPM視点でレビューしてもらう

```text
claude-code/skills/pm-review/SKILL.md の内容を前提として、
このプロジェクトの README.md をPM視点でレビューしてください。
```

### 例2：IssueリストをPM視点でレビューしてもらう

```text
claude-code/skills/pm-review/SKILL.md の内容を前提として、
現在の Issue リストをPM視点でレビューしてください。
担当者不明・期限不明・エスカレーションが必要なものを指摘してください。
```

### 例3：進捗メモをPM視点で整理してもらう

```text
claude-code/skills/pm-review/SKILL.md の内容を前提として、
以下の進捗メモをPM視点で整理してください。

【進捗メモ（機密情報はマスキング済み）】
（ここに進捗メモを貼り付ける）
```

---

## 注意事項

- `SKILL.md` は参考サンプルです。内容を理解したうえで利用してください
- 機密情報・個人情報・認証情報をClaude Codeに入力しないでください
- AI出力はたたき台です。そのまま顧客提出・社内報告に使わないでください
- Claude Code の利用規約・データ利用条件を確認してください
- 実行可能な hooks・command を追加する場合は、自己責任のもとで内容を十分に確認してください

---

## 関連ドキュメント

- [docs/for-claude-code.md](../docs/for-claude-code.md)
- [DISCLAIMER.md](../DISCLAIMER.md)
- [docs/ai-safety.md](../docs/ai-safety.md)

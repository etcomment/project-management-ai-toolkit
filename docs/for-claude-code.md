# Claude Codeでの使い方 / How to Use with Claude Code

---

## はじめに

このガイドでは、本リポジトリの Claude Code 向けコンテンツの利用方法を説明します。

Claude Code は、ターミナルで動作するAIコーディングアシスタントです。

本リポジトリでは、Claude Code をコーディングではなく **プロジェクト管理・PM業務の観点でのレビュー** に活用するためのサンプルを提供します。

> [!IMPORTANT]
> 本リポジトリには、hooks・command・MCP設定・自動実行・自動コミット・自動デプロイ に関するファイルは含まれません。
> AI出力は業務判断の代替ではありません。出力内容は必ず人間が確認してください。

---

## このリポジトリで提供するもの

| ファイル | 内容 |
|---|---|
| `claude-code/README.md` | Claude Code 向けディレクトリの説明 |
| `claude-code/skills/pm-review/SKILL.md` | PMレビュー観点のSkillサンプル |

---

## claude-code/skills/pm-review/SKILL.md の位置づけ

`SKILL.md` は、Claude Code の Skill 形式に沿って記述した **PMレビュー観点のサンプルドキュメント** です。

このファイルは以下を目的としています。

- Claude Code に「PM視点でレビューする」という観点を伝えるためのサンプル
- README、Issue、仕様メモ、進捗メモをPM視点でレビューする際の参考

**このファイルには以下は含まれません。**

- 実行可能な hooks
- shell コマンド
- MCP設定
- 自動コミット・自動デプロイ
- 外部サービスへの自動通信
- ファイルの自動編集・削除

---

## 使い方

### README・Issue・仕様メモをPM視点でレビューする

Claude Code のチャットで、以下のように依頼します。

#### 例1：プロジェクトの README をレビューしてもらう

```text
claude-code/skills/pm-review/SKILL.md の内容を前提として、
このプロジェクトの README.md をPM視点でレビューしてください。

確認してほしい観点：
- プロジェクトの目的・スコープが明確か
- 進捗・マイルストーンの状況が分かるか
- 課題・リスク・顧客確認事項が記載されているか
- 次アクションが明確か
```

#### 例2：Issue リストをPM視点でレビューしてもらう

```text
claude-code/skills/pm-review/SKILL.md の内容を前提として、
現在の Issue リストをPM視点でレビューしてください。

確認してほしい観点：
- 担当者不明の Issue はないか
- 期限不明の Issue はないか
- エスカレーションが必要そうなものはないか
- 顧客確認が必要なものはないか
```

#### 例3：進捗メモをPM視点で整理してもらう

```text
claude-code/skills/pm-review/SKILL.md の内容を前提として、
以下の進捗メモをPM視点で整理してください。

【進捗メモ（機密情報はマスキング済み）】
- 先週：設計レビュー完了、開発着手
- 今週：開発中（6機能のうち3機能完了）
- 課題：外部API仕様が未確定、担当者未定
- 顧客確認待ち：追加機能の対応可否（先週依頼済み）
```

---

## 注意事項

- `SKILL.md` は参考サンプルです。内容を理解したうえで利用してください
- 機密情報・個人情報・認証情報をClaude Codeに入力しないでください
- AI出力はたたき台です。そのまま顧客提出・社内報告・契約判断に使わないでください
- 実行可能な hooks・command を追加する場合は、自己責任のもとで内容を十分に確認してください
- Claude Codeの利用規約・データ利用条件を確認してください

---

## 関連ファイル

- [claude-code/README.md](../claude-code/README.md)
- [claude-code/skills/pm-review/SKILL.md](../claude-code/skills/pm-review/SKILL.md)
- [docs/ai-safety.md](ai-safety.md)
- [DISCLAIMER.md](../DISCLAIMER.md)

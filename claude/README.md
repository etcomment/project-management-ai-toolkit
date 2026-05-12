# Claude Guide / Claude向けガイド

---

## このディレクトリの目的

このディレクトリは、Claude / Claude Projects で `contexts/` を使うためのガイドを提供します。

- Claude Projects では `claude-project-instructions.md` を設定用として使えます
- コンテキスト本体は `contexts/` 配下にあります
- このディレクトリは、Claudeで使うための設定例・使い方ガイド・利用例を提供します

---

## 使えるファイル

| ファイル | 種別 | 用途 |
|---|---|---|
| `claude-project-instructions.md` | 設定用・コピー用 | Claude Projects のプロジェクト指示に設定する文面 |
| `use-context-files.md` | 人間向けガイド | Claudeで `contexts/*.md` を使う手順 |
| `examples.md` | 人間向けガイド | Claudeでの利用例 |

---

## Claudeでの利用フロー

```text
Claudeで使う
│
├─ 通常チャットで使う
│    └─ contexts/*.md をチャットに貼り付ける
│
└─ Claude Projectsで使う
     └─ claude-project-instructions.md を設定する

共通の流れ：
PM_CONTEXT.md
   ↓
用途別 contexts/*.md
   ↓
長文情報は要約・マスキング
   ↓
AI出力を人間が確認
```

---

## どのファイルを事前設定するか

### Claude Projects を使う場合

1. `claude-project-instructions.md` をプロジェクト指示に設定する
2. Project Knowledge 等に追加するなら、まず `contexts/PM_CONTEXT.md` と `docs/ai-safety.md`
3. 用途別に `contexts/PROJECT_HEALTH_CHECK.md`、`contexts/STATUS_REPORT_CONTEXT.md`、`contexts/ISSUE_RISK_CONTEXT.md` などを追加する
4. すべてのファイルを常に読み込ませる必要はありません

---

## contexts/ との関係

このリポジトリの主役は `contexts/` です。

Claude向けディレクトリは、設定・利用方法のガイドです。

各 `contexts/*.md` には以下が含まれています。

- Purpose
- Use Case
- Input
- Output
- Caution
- Prompt Template

通常は対象の `contexts/*.md` を読むだけで、AIへの依頼に必要な情報を確認できます。

---

## 安全上の注意

> [!CAUTION]
> - 機密情報・個人情報・契約情報・認証情報を入力しないでください
> - 長文の議事録や案件メモは要約・マスキングしてから貼り付けてください
> - AI出力は業務判断の代替ではありません
> - 顧客提出・社内報告・契約判断・納期回答には必ず人間が確認してください

詳細は [docs/ai-safety.md](../docs/ai-safety.md) および [DISCLAIMER.md](../DISCLAIMER.md) を参照してください。

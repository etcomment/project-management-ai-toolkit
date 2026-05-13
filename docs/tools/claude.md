# Claude 使い方ガイド

Claude / Claude Projects で本リポジトリを活用するためのガイドです。

> [!IMPORTANT]
> 機密情報・個人情報・契約情報・認証情報（APIキー・パスワード等）は、Claude に入力しないでください。
> AI出力は業務判断の代替ではありません。出力内容は必ず人間が確認・修正してください。

---

## `contexts/` — AI Contexts本体

コンテキスト本体は `contexts/` 配下にあります。各コンテキストファイルには、AIに渡す前提情報・判断軸・Prompt Template が含まれています。

設定用ファイル（指示文）は `instructions/` 配下にあります。

---

## 使用する設定用ファイル

| ファイル | 設定先 |
|---|---|
| `instructions/claude-project-instructions.md` | Claude Projects のプロジェクト指示欄 |

このファイルは「AIツールの設定欄にコピーして使う指示文」です。人間が読むガイドではありません。

---

## 利用パターン

### 通常チャットで使う場合

1. `contexts/PM_CONTEXT.md` の内容をチャットに貼り付ける
2. 目的に合う用途別コンテキスト（`contexts/*.md`）を貼り付ける
3. 案件情報（マスキング済み）を貼り付ける
4. `contexts/*.md` の `Prompt Template` を参考に出力形式を指定する
5. AI出力を人間が確認する

### Claude Projects で使う場合

1. `instructions/claude-project-instructions.md` をプロジェクト指示に設定する
2. 必要に応じて `contexts/PM_CONTEXT.md` と `docs/ai-safety.md` をProject Knowledgeに追加する
3. 案件ごとに用途別コンテキストをチャットに貼り付ける
4. 実案件情報はマスキング・要約してから入力する

---

## 利用フロー

```text
Claudeで使う
│
├─ 通常チャット
│    └─ contexts/*.md をチャットに貼り付ける
│
└─ Claude Projects
     └─ instructions/claude-project-instructions.md を設定する

共通の流れ：
PM_CONTEXT.md → 用途別 contexts/*.md → 長文は要約・マスキング → AI出力を人間が確認
```

---

## 長文コンテキストを渡す場合の注意

- 議事録の全文をそのまま貼り付けない
- 顧客名・個人名・契約情報を削除する
- 長文は「事実」「課題」「未決事項」「次アクション」に要約してから貼り付ける
- 不要な過去情報を入れすぎない
- AI出力の品質は、入力情報の品質に依存します

---

## 用途別コンテキストの選び方

| 目的 | コンテキストファイル |
|---|---|
| プロジェクトヘルスチェック | `contexts/PM_CONTEXT.md` + `contexts/PROJECT_HEALTH_CHECK.md` |
| 進捗報告 | `contexts/PM_CONTEXT.md` + `contexts/STATUS_REPORT_CONTEXT.md` |
| 課題・リスク整理 | `contexts/PM_CONTEXT.md` + `contexts/ISSUE_RISK_CONTEXT.md` |
| 顧客説明 | `contexts/PM_CONTEXT.md` + `contexts/CLIENT_COMMUNICATION_CONTEXT.md` |
| 炎上初動 | `contexts/PM_CONTEXT.md` + `contexts/FIRE_RESPONSE_FIRST_72H.md` |
| スコープ変更 | `contexts/PM_CONTEXT.md` + `contexts/SCOPE_CHANGE_CONTEXT.md` |

詳細は [docs/use-case-map.md](../use-case-map.md) を参照してください。

---

## 利用例（架空データ）

以下は架空データを使った利用例です。

### 例：進捗報告の整理

**使用するファイル**
- `contexts/PM_CONTEXT.md`
- `contexts/STATUS_REPORT_CONTEXT.md`

**Sanitized Input（架空データ）**

```
今週完了した作業：
- 基本設計レビュー（完了）
- テスト環境構築（完了）

未完了の作業：
- 詳細設計書 作成中（進捗70%）

遅延している作業：
- 外部API連携設計（2日遅延）

課題：
- 外部システムの仕様確認が未完了
```

**Prompt**

```
以下のコンテキストを前提として、今週の進捗報告を整理してください。

【PM_CONTEXT.md の内容】
（ここにcontexts/PM_CONTEXT.mdを貼り付ける）

【STATUS_REPORT_CONTEXT.md の内容】
（ここにcontexts/STATUS_REPORT_CONTEXT.mdを貼り付ける）

【今週の状況（架空データ）】
（Sanitized Inputの内容を貼り付ける）

以下の3種類で整理してください：
1. 社内向け進捗報告
2. 顧客向け進捗報告
3. 上長向けサマリー
```

**Human Review Points**
- 事実と一致しているか確認する
- 顧客向けの表現トーンは適切か確認する
- 契約・費用・納期に関する記述は人間が確認する

---

## Claudeで使う場合のプロンプト構造

Claudeに複数の情報を渡す場合は、以下のように役割・依頼内容・入力情報・制約・出力形式を分けると整理しやすくなります。

```text
<task>
AIに依頼したい内容を1〜3文で明確に書く
</task>
<context>
関連するコンテキスト情報（PM_CONTEXT.md や用途別 contexts/*.md の内容）
</context>
<input>
案件情報・会議メモ・課題一覧など、ユーザーが入力する情報（機密情報はマスキング済み）
</input>
<constraints>
- 顧客名・個人名・会社名・契約情報・認証情報はマスキング済みの前提で扱ってください。
- 入力情報に含まれない内容を補う場合は「（推測）」と明示してください。
- 判断に十分な情報がない場合は「情報不足」または「この情報だけでは判断できません」と明記してください。
- AI出力は判断材料であり、最終判断は人間が行う前提で出力してください。
</constraints>
<output_format>
出力してほしい項目（例：状況要約、主要課題、リスク、次アクション）
</output_format>
```

この構造は Claude 向けに特に効果的ですが、ChatGPT / Gemini でも同様に使用できます。

`contexts/` 各ファイル内の「Claude向け Prompt Template（XMLタグ版）」も参照してください。

---

## 出力後の確認

> [!CAUTION]
> AI出力をそのまま業務に使わないでください。

- AI出力は業務判断の代替ではありません
- 顧客提出・社内報告・契約判断・納期回答には必ず人間が確認してください
- 必要に応じて上長・法務・PMOに確認してください

---

## 関連ドキュメント

- [docs/ai-safety.md](../ai-safety.md) — AIに入力してよい情報・安全な使い方
- [docs/legal/DISCLAIMER.md](../legal/DISCLAIMER.md) — 免責事項

---

## 関連情報

- [AI Contextsの全体像を見る](https://techaide.jp/ai-contexts/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [PM・AI活用ラボを見る](https://techaide.jp/community/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [自分に合う講座を診断する](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)

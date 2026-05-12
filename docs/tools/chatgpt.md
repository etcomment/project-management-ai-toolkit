# ChatGPT 使い方ガイド

ChatGPT で本リポジトリを活用するためのガイドです。

> [!IMPORTANT]
> 顧客情報・個人情報・契約情報・認証情報（APIキー・パスワード等）は、ChatGPT に入力しないでください。
> AI出力は業務判断の代替ではありません。出力内容は必ず人間が確認・修正してください。

---

## このリポジトリの主役は `contexts/`

コンテキスト本体は `contexts/` 配下にあります。各コンテキストファイルには、AIに渡す前提情報・判断軸・Prompt Template が含まれています。

設定用ファイル（指示文）は `instructions/` 配下にあります。

---

## 使用する設定用ファイル

| ファイル | 設定先 |
|---|---|
| `instructions/chatgpt-project-instructions.md` | ChatGPT Projects の Instructions 欄 |
| `instructions/custom-gpt-instructions.md` | カスタムGPT の Instructions 欄 |

これらのファイルは「AIツールの設定欄にコピーして使う指示文」です。人間が読むガイドではありません。

---

## 利用パターン

### 通常チャットで使う場合

1. `contexts/PM_CONTEXT.md` の内容をコピーする
2. 新規チャットの冒頭に貼り付ける
3. 用途別コンテキスト（`contexts/*.md`）と案件情報（マスキング済み）を続けて入力する
4. AI出力を人間が確認する

```text
以下のコンテキストを前提として振る舞ってください。

[PM_CONTEXT.md の内容をここに貼り付ける]

---

[用途別コンテキストファイルの内容をここに貼り付ける]

---

[案件情報（機密情報をマスキング済み）をここに入力する]
```

### ChatGPT Projects で使う場合

1. ChatGPT でプロジェクトを新規作成する
2. プロジェクトの「Instructions」に `instructions/chatgpt-project-instructions.md` の内容を貼り付ける
3. 案件情報（マスキング済み）と用途別コンテキストを入力して依頼する

### カスタムGPT で使う場合

1. カスタムGPTの「Instructions」欄に `instructions/custom-gpt-instructions.md` の内容を貼り付ける
2. 必要に応じて `contexts/PM_CONTEXT.md` などを Knowledge に追加する
3. 案件情報（マスキング済み）と用途別コンテキストを入力して依頼する

---

## 利用フロー

```text
ChatGPTで使う
│
├─ 通常チャット
│    └─ contexts/*.md をチャットに貼り付ける
│
├─ ChatGPT Projects
│    └─ instructions/chatgpt-project-instructions.md を設定する
│
└─ カスタムGPT
     └─ instructions/custom-gpt-instructions.md を設定する

共通の流れ：
PM_CONTEXT.md → 用途別 contexts/*.md → マスキングして入力 → AI出力を人間が確認
```

---

## 用途別コンテキストの選び方

| 目的 | コンテキストファイル |
|---|---|
| プロジェクトヘルスチェック | `contexts/PROJECT_HEALTH_CHECK.md` |
| 進捗報告 | `contexts/STATUS_REPORT_CONTEXT.md` |
| 課題・リスク整理 | `contexts/ISSUE_RISK_CONTEXT.md` |
| 顧客向け説明文 | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` |
| 炎上初動 | `contexts/FIRE_RESPONSE_FIRST_72H.md` |
| 議事録・TODO | `contexts/MEETING_MINUTES_CONTEXT.md` |

詳細は [docs/use-case-map.md](../use-case-map.md) を参照してください。

---

## 入力前のマスキング例

| 置き換え前（例） | 置き換え後（例） |
|---|---|
| 株式会社〇〇（顧客名） | 顧客A |
| 田中 太郎（担当者名） | 担当者A |
| api_key_xxxxxxxxxx | （削除） |
| 見積金額：3,500万円 | 見積金額：数千万円規模 |
| プロジェクト名：〇〇システム刷新 | プロジェクトX |

---

## 利用例（架空データ）

以下は架空データを使った利用例です。

### 例：プロジェクトヘルスチェック

**使用するファイル**
- `contexts/PM_CONTEXT.md`
- `contexts/PROJECT_HEALTH_CHECK.md`

**Sanitized Input（架空データ）**

```
【案件概要】
- 種別：業務システム開発（受託）
- フェーズ：結合テスト工程
- 全体進捗：65%

【状況】
- 外部連携APIの仕様が未確定のため、3機能が着手できていない
- テスト消化率が40%で追いつかず
- 顧客から要件追加要望が2件あり対応方針が未定
```

**Prompt**

```
以下のコンテキストを前提として、プロジェクト状況をPM視点でヘルスチェックしてください。

[PM_CONTEXT.md の内容]
[PROJECT_HEALTH_CHECK.md の内容]

【現在の案件状況（架空データ）】
（上記 Sanitized Input を貼り付ける）
```

**Human Review Points**
- 危険度の判断が実際の案件感覚と一致しているか確認する
- 次アクションの優先順位が現場状況に合っているか調整する
- AI出力をそのまま顧客提出・社内報告に使わない

---

## 出力確認チェックリスト

- [ ] 出力内容が実際の案件状況と一致している
- [ ] 顧客・社内の関係性に合ったトーン・表現になっている
- [ ] 契約・費用・責任範囲に関する表現が正確である
- [ ] 顧客提出前に上長・担当者のレビューを受けている

---

## 関連ドキュメント

- [docs/ai-safety.md](../ai-safety.md) — AIに入力してよい情報・安全な使い方
- [docs/legal/DISCLAIMER.md](../legal/DISCLAIMER.md) — 免責事項

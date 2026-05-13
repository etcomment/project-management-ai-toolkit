# Gemini 使い方ガイド

Gemini で本リポジトリを活用するためのガイドです。

> [!IMPORTANT]
> 顧客情報・個人情報・契約情報・認証情報（APIキー・パスワード等）は、Gemini に入力しないでください。
> AI出力は業務判断の代替ではありません。出力内容は必ず人間が確認・修正してください。

---

## `contexts/` — AI Contexts本体

コンテキスト本体は `contexts/` 配下にあります。各コンテキストファイルには、AIに渡す前提情報・判断軸・Prompt Template が含まれています。

設定用ファイル（指示文）は `instructions/` 配下にあります。

---

## 使用する設定用ファイル

| ファイル | 設定先 |
|---|---|
| `instructions/gemini-instructions.md` | Gems の指示欄 / チャット冒頭 |

このファイルは「AIツールの設定欄にコピーして使う指示文」です。人間が読むガイドではありません。

---

## 利用パターン

### 通常チャットで使う場合

1. `contexts/PM_CONTEXT.md` の内容をコピーする
2. Gemini で新しいチャットを開く
3. チャットの冒頭にコンテキストの内容を貼り付ける
4. 用途別コンテキスト（`contexts/*.md`）と案件情報（マスキング済み）を続けて入力する
5. AI出力を人間が確認する

```text
以下のコンテキストを前提として振る舞ってください。
そのうえで、[依頼内容] を整理してください。

【PM_CONTEXT.md の内容】
[PM_CONTEXT.md の内容をここに貼り付ける]

【追加コンテキスト】
[用途別コンテキストファイルの内容をここに貼り付ける]

【案件状況（機密情報はマスキング済み）】
[案件の状況をここに記入する]
```

### Gems で使う場合

1. Gemini で新しい Gem を作成する
2. Gem の「指示」欄に `instructions/gemini-instructions.md` の内容を貼り付ける
3. 必要に応じて `contexts/PM_CONTEXT.md` などをチャット冒頭に追加する
4. 案件情報（マスキング済み）と用途別コンテキストを入力して依頼する

> [!NOTE]
> Google Workspace でご利用の場合は、組織のデータ利用ポリシーおよびGems機能の利用可否を事前に確認してください。

---

## 利用フロー

```text
Geminiで使う
│
├─ 通常チャット
│    └─ contexts/*.md をチャットに貼り付ける
│
└─ Gems
     └─ instructions/gemini-instructions.md を設定する

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

## Google Workspace 利用時の注意

Google Workspace 環境で Gemini を使う場合は、以下を事前に確認してください。

- 組織の AI 利用ポリシー
- データの外部送信に関する制限
- Gems 機能の利用可否

不明な場合は、IT管理部門・情報セキュリティ担当に確認してください。

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
- 種別：Webアプリ開発（受託）
- フェーズ：設計・開発並行フェーズ
- 全体進捗：45%

【状況】
- 画面設計の承認が顧客側の都合で2週間遅延している
- テスト担当が未アサインで、テスト計画が未作成
- 顧客から機能追加の要望が3件あり、見積・調整が未実施
```

**Prompt**

```
以下のコンテキストを前提として振る舞ってください。
プロジェクト状況をPM視点でヘルスチェックし、
危険度（高・中・低）、主要な懸念点、次アクションを整理してください。

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

---

## 関連情報

- [PM向けAI活用ツールキットを見る](https://techaide.jp/ai-toolkit/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [PM・AI活用ラボを見る](https://techaide.jp/community/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [自分に合う講座を診断する](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)

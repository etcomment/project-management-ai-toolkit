# PM × AI 診断の利用例

## このサンプルの目的

このサンプルは、`.claude/skills/pm-ai-diagnosis/SKILL.md` を使って、PM課題・AI活用課題・コミュニケーション課題を切り分ける例です。

> [!IMPORTANT]
> すべて架空データです。実在する顧客名・会社名・個人名・案件名は含みません。  
> 実案件で利用する場合は、必ずマスキング・要約化してください。

> [!WARNING]
> AI出力は業務判断の代替ではありません。最終判断は必ず人間が行ってください。

---

## 使用するSkill

- `.claude/skills/pm-ai-diagnosis/SKILL.md`

## 関連Context

- `contexts/PM_CONTEXT.md`
- `contexts/PROJECT_HEALTH_CHECK.md`
- `contexts/STATUS_REPORT_CONTEXT.md`
- `contexts/ISSUE_RISK_CONTEXT.md`
- `contexts/CLIENT_COMMUNICATION_CONTEXT.md`

---

## 入力例

### 通常版

```text
.claude/skills/pm-ai-diagnosis/SKILL.md の内容を前提として、
以下の状況に合うContextとSkillを案内してください。
【状況】
現在、開発フェーズ中盤です。
開発作業は進んでいますが、顧客確認待ちの仕様が複数あり、週次報告で何をどの粒度で伝えるべきか迷っています。
課題管理表には課題が10件ありますが、担当者と期限が未設定のものもあります。
AIを使って状況を整理したいのですが、どのContextを使えばよいか分かりません。
※ 顧客名・個人名・会社名などの機密情報はマスキング済みです。
```

### Claude向けXMLタグ版

```text
<task>
.claude/skills/pm-ai-diagnosis/SKILL.md の内容を前提として、
以下の状況に合うContextとSkillを案内してください。
</task>
<input>
【状況】
現在、開発フェーズ中盤です。
開発作業は進んでいますが、顧客確認待ちの仕様が複数あり、週次報告で何をどの粒度で伝えるべきか迷っています。
課題管理表には課題が10件ありますが、担当者と期限が未設定のものもあります。
AIを使って状況を整理したいのですが、どのContextを使えばよいか分かりません。
</input>
<constraints>
- 顧客名・個人名・会社名などの機密情報はマスキング済みです。
- 判断に必要な情報が不足している場合は「情報不足」と明記してください。
- 推奨するContextとSkillの理由を明示してください。
</constraints>
```

---

## 期待する出力例

以下のような観点で出力されることを期待します。

### 診断結果サマリー

- PM課題、AI活用課題、コミュニケーション課題が分けて整理される
- 最初に使うべきContextが提示される
- 併用するとよいSkillが提示される

### 課題の分類

| 分類 | 内容 | 優先度 |
|---|---|---|
| PM課題 | 顧客確認待ちの仕様が複数あり、課題管理表にも担当者・期限未設定のものがある | 高 |
| AI活用課題 | どのContextを使えばよいか判断できていない | 中 |
| コミュニケーション課題 | 週次報告で顧客へ何を伝えるべきか迷っている | 高 |

### まず使うべきContext

| 優先度 | Context | 使う理由 |
|---|---|---|
| 高 | `contexts/ISSUE_RISK_CONTEXT.md` | 担当者・期限未設定の課題を整理するため |
| 高 | `contexts/STATUS_REPORT_CONTEXT.md` | 週次報告を社内向け・顧客向けに分けるため |
| 中 | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` | 顧客確認待ち事項の伝え方を整理するため |

### 併用するとよいSkill

| 優先度 | Skill | 使う理由 |
|---|---|---|
| 高 | `issue-risk-review` | 課題管理表の抜け漏れを確認するため |
| 高 | `status-report` | 週次報告を整理するため |
| 中 | `stakeholder-strategy` | 顧客・社内への伝え分けを整理するため |

---

## Human Review Points

- 診断結果が実際の案件状況と合っているか
- AIが推奨したContextが目的に合っているか
- 顧客提出・社内報告に使う前に人間が内容を確認したか
- 機密情報・個人情報が含まれていないか

---

## 次に確認するとよいページ

- `docs/use-case-map.md`
- `docs/learning-roadmap.md`
- `docs/ai-safety.md`

# AgentMD

OpenAI Codex 向けの**グローバル共通指示 + モデル系列別の補助指示**を、小さな構成で管理する公開リポジトリです。

> **Status: Draft** — モデル系列別のファイルは未検証の初期状態です。効果や自動切替は保証していません。

## 対象と方針

- 対象は **OpenAI 製モデルを使用する Codex** です。他社モデルや Skills は対象外です。
- `AGENTS.md` は、どの対象モデルにも共通する基本ルールの唯一の入口です。
- モデル系列固有の指示が必要になった場合だけ、`models/` に追記します。
- モデル名の世代番号ごとにファイルを増やさず、**Luna / Sol / Terra / Astra** の系列単位で管理します。
- 新モデル登場時も、まず既存の指示で動作確認し、必要な場合だけ修正します。

OpenAI が公開しているモデル系列名に合わせていますが、モデルの提供状況や識別子は変更され得ます。
[公式モデル一覧](https://developers.openai.com/api/docs/models) / [モデル選択ガイド](https://developers.openai.com/api/docs/guides/model-selection)

## 構成

```text
AgentMD/
├── AGENTS.md          # 全モデル共通指示と参照規則
├── models/
│   ├── Luna.md        # Luna 系列用（追加指示はまだなし）
│   ├── Sol.md         # Sol 系列用（追加指示はまだなし）
│   ├── Terra.md       # Terra 系列用（追加指示はまだなし）
│   └── Astra.md       # Astra 系列用（追加指示はまだなし）
├── README.md
└── CONTRIBUTING.md
```

これらは**モデルの実体やサブエージェントではなく、モデル系列ごとの指示文書**です。

## Codexへの適用

Codex は通常 `~/.codex/AGENTS.md` をグローバル指示として自動探索します。`CODEX_HOME` を設定している場合は、そのディレクトリが基準になります。

このリポジトリは自動同期されません。導入時は、既存のグローバル指示をバックアップし、**`AGENTS.md` と `models/` ディレクトリを一緒に** `CODEX_HOME` に配置してください。

```text
~/.codex/
├── AGENTS.md
└── models/
    ├── Luna.md
    ├── Sol.md
    ├── Terra.md
    └── Astra.md
```

**重要:** Codex が標準で自動読み込みするのは適用対象の `AGENTS.md` です。`models/*.md` を自動判別・自動読込する機構ではありません。`AGENTS.md` に記述した**読込指示をCodexが実行する方式**であり、完全な自動適用を保証するものではありません。

モデル系列を確実に判別できない場合や、対応ファイルがない場合は、共通ルールのみを使用します。`AGENTS.md` だけを配置しても共通ルールは利用できます。

## モデル更新時の運用

1. 新モデルの**実際の識別子**と公式情報を確認する。
2. 同じ `AGENTS.md` と該当系列ファイル（追加指示がある場合）で動作確認する。
3. 問題が再現された場合のみ、共通の問題か特定系列の問題かを切り分ける。
4. 変更の効果と副作用を比較し、最小の修正を提案する。
5. 使用モデルの正確なID、推論設定、Codexバージョン、評価結果をPR/コミットに記録する。

同じ系列でも世代が違えば効果が異なる可能性があります。系列名は**運用上の分類**であり、互換性の保証ではありません。

変更の基準は [CONTRIBUTING.md](CONTRIBUTING.md) を参照してください。

## 参考資料

- [OpenAI: AGENTS.md の仕様](https://developers.openai.com/codex/guides/agents-md)
- [OpenAI: Codex Prompting Guide](https://developers.openai.com/cookbook/examples/gpt-5/codex_prompting_guide)
- [OpenAI: モデル選択ガイド](https://developers.openai.com/api/docs/guides/model-selection)

このリポジトリは個人管理の取り組みであり、OpenAI の公式リポジトリではありません。

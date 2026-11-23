# AgentMD

OpenAI Codex で使用する、**単一のグローバル `AGENTS.md`** を継続的に改善するための公開リポジトリです。

> **Status: Draft** — 現在の `AGENTS.md` は見出しのみのプレースホルダーです。運用ルールは未策定であり、効果やモデル互換性は検証されていません。

## 対象範囲

- **対象:** OpenAI が開発・提供するモデルを使用した Codex の作業指示
- **管理対象:** 原則としてルートの `AGENTS.md` 1ファイル
- **目的:** プロジェクトや言語に依存しにくい、簡潔で検証可能な共通指示を維持する
- **対象外:** 他社モデル向けの最適化、プロジェクト別 `AGENTS.md` の収集、Skills、専用スクリプト、モデルごとのテンプレート大量生成

OpenAI 製であっても、すべてのモデルや実行環境で同じ効果を保証するものではありません。指示の評価では、**モデルと Codex の実行環境**を区別します。

## リポジトリ構成

```text
AgentMD/
├── AGENTS.md       # 管理対象の共通指示（現在は草案）
├── README.md       # 目的と使用方法
└── CONTRIBUTING.md # 変更・検証・更新の基準
```

追加の管理ファイルは、必要性が確認されるまで作りません。変更履歴は Git のコミット・Pull Request で追跡します。

## Codex での利用

Codex は、通常、`~/.codex/AGENTS.md`（`CODEX_HOME` を指定した場合はその配下）をグローバル指示として参照します。実際の適用範囲や優先順位は Codex の仕様に従います。

**このリポジトリに置いたファイルが、各自の Codex 環境へ自動同期されるわけではありません。**

運用ルールの策定後、内容を確認し、必要に応じて既存のグローバル指示をバックアップしてから配置してください。**現在のプレースホルダーをそのまま導入する必要はありません。**

## モデル更新への方針

モデルが更新されたからという理由だけでは、`AGENTS.md` を書き換えません。

1. **維持:** まず既存の指示を新しいモデルでも試す
2. **観察:** 再現できる問題や不要な制約があるか確認する
3. **最小修正:** 必要な場合に限り、最小の差分を提案する
4. **比較:** 同じ課題・可能な限り同じ条件で修正前後を比較する
5. **記録:** 対象モデル、実行条件、結果、未検証事項を Pull Request またはコミットに残す

モデル固有の事情は、原則として変更提案の検証記録に残し、**共通の `AGENTS.md` に無条件で持ち込まない**方針です。例外が必要かは実測結果から判断します。

## 変更への参加

提案・修正の判断基準は [CONTRIBUTING.md](CONTRIBUTING.md) を参照してください。

## 参考資料

- [Codex: Custom instructions with AGENTS.md](https://developers.openai.com/codex/guides/agents-md)
- [OpenAI: Codex Prompting Guide](https://developers.openai.com/cookbook/examples/gpt-5/codex_prompting_guide)
- [OpenAI: Models](https://developers.openai.com/api/docs/models)

このリポジトリは個人管理の取り組みであり、OpenAI の公式リポジトリではありません。

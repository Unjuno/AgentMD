# AgentMD

OpenAI Codex 向けに、**モデル系列を識別して、その系列の指示Markdownだけを読み込ませる**ための小規模リポジトリです。

> **Status: Experimental (2026-11-24)** — ファイル構成は整えていますが、Codex実機での自動振り分けと、モデル別指示の改善効果はまだ検証していません。公式ベンチマークの結果は指示の効果を保証しません。

## 設計

```text
AgentMD/
├── AGENTS.md          # 振り分け専用。実行モデルを変更しない
├── models/
│   ├── Luna.md        # Luna 系列の作業ガイダンス
│   ├── Terra.md       # Terra 系列の作業ガイダンス
│   ├── Sol.md         # Sol 系列の作業ガイダンス
│   └── Astra.md       # Astra 系列の作業ガイダンス
├── README.md          # 調査根拠・導入方法
└── CONTRIBUTING.md    # 変更と検証の基準
```

- このリポジトリが**選択するのは指示文書**であり、実行モデル・推論設定・API接続先ではありません。
- 対象は OpenAI 製モデルを使う Codex。Skills、他社モデル、独自の自動切替スクリプトは対象外。
- 同系列の世代違いは同一ファイルへ振り分けます。ただし**世代間で同じ指示が有効とは限りません**。
- ルート `AGENTS.md` は共通作業原則を積み増さず、振り分け専用とします。共通の上位・プロジェクト指示はCodexの既存の仕組みに従います。

## 公式モデル情報とAPI料金

2026-11-24 に確認。標準APIのUSD/100万トークン。**Codexのプラン内利用量・クレジット消費額を表す表ではありません。**

| 系列 | 代表モデルID | 入力 | キャッシュ済み入力 | 出力 | 公式で強調される用途 |
| --- | --- | ---: | ---: | ---: | --- |
| Luna | `gpt-6-luna` | $0.10 | $0.01 | $0.50 | 定型・小規模・大量処理 |
| Terra | `gpt-6.1-terra` | $1.00 | $0.05 | $5.00 | 画像理解、PC操作、視覚的な作業 |
| Sol | `gpt-6.2-sol` | $2.00 | $0.10 | $10.00 | 一般開発、日常のエージェント作業 |
| Astra | `gpt-6.2-astra` | $8.00 | $0.40 | $40.00 | 高難度コーディング、複雑な専門作業 |

出典：[OpenAI モデル一覧](https://developers.openai.com/api/docs/models)、
[GPT-6 Sol / Luna](https://openai.com/index/introducing-gpt-6-sol-and-luna/)、
[GPT-6.1 Terra](https://openai.com/index/introducing-gpt-6-1-terra/)、
[GPT-6.2 Astra / Sol](https://openai.com/index/introducing-gpt-6-2-astra-sol/)。

単価が低くても、失敗による再試行やレビューに時間がかかれば完了コストは高くなります。モデルや推論レベルを選ぶときは、**品質・タスク完了率・試行回数・処理時間・実トークン使用量**を合わせて評価します。

## 公開ベンチマークの調査メモ

下表は**評価条件とモデル版が行ごとに異なる**ため、全モデルの直接ランキングではありません。数字は特記しない限り各発表元の公表値です。

| 評価 | 比較対象・推論設定 | 公表結果 | AgentMDへの示唆 |
| --- | --- | --- | --- |
| FrontierCode 2.0（実リポジトリのマージ品質） | GPT-6.2 Sol / Astra、両方 max | Sol は Astra と **0.5ポイント差**、タスク費用は約 **1/5** | Solは通常の開発で有力な比較起点 |
| Agents' Last Exam v1（複雑・長工程業務） | GPT-6.2 Astra 対 GPT-6 Astra | 新Astraは **+5.2ポイント**、タスク費用は **1/3未満** | 高難度案件で新版Astraの評価価値 |
| Terminal-Bench 4.0（CLIの問題解決） | GPT-6.1 Terra max 対 GPT-5.6 Terraの公表値 | **50.3% 対 21.5%** | Terraのコード作業能力を過小評価しない |
| DeepSWE 1.1（長工程ソフトウェア開発） | GPT-6 Luna max / GPT-6 Sol max（**旧Sol**） | **66.6% / 68.8%**（OpenAI発表） | Lunaにも難しいコード課題を解ける可能性があるが、最新Solとの比較ではない |
| AutomationBench 1.0.6（複数アプリの業務） | GPT-6 Sol xhigh / GPT-6 Astra low（**旧世代・努力設定不一致**） | **33.2% / 30.3%**、Solは **$0.27/タスク** | 推論レベル差を無視した順位付けは不可 |
| OSWorld 2.1（デスクトップ操作） | GPT-6.1 Terraなど | Terraの改善が報告されている | 視覚操作の参考。ただし採点品質に重大な注意あり |

主な根拠：
- [OpenAI: GPT-6.2 Astra / Sol](https://openai.com/index/introducing-gpt-6-2-astra-sol/)
- [OpenAI: GPT-6.1 Terra](https://openai.com/index/introducing-gpt-6-1-terra/)
- [OpenAI: GPT-6 Sol / Luna](https://openai.com/index/introducing-gpt-6-sol-and-luna/)
- [Cognition: FrontierCode 2.0（132課題、リポジトリでのマージ基準）](https://cognition.com/blog/frontier-code-2.0)
- [Epoch AI: DeepSWE v1.1 レビュー](https://epoch.ai/benchmarks/deepswe)
- [Epoch AI: OSWorld 2.1 レビュー](https://epoch.ai/benchmarks/osworld-2-1/review)

**評価の限界:** Epoch AIはDeepSWE v1.1とOSWorld 2.1をそれぞれ **Flawed（欠陥あり）** と評価しています。これらのスコアは単独の採用基準にしません。実際のCodex運用では、自分の課題を使った再検証が必要です。

ベンチマークは**モデルの能力やコストの証拠**であり、`AGENTS.md` に書く指示が有効という証拠ではありません。モデル別ガイダンスは現状すべて仮説・初期案です。

## 導入・読み込み条件

Codexは通常 `~/.codex/AGENTS.md`（`CODEX_HOME` 設定時はその配下）を指示ファイルとして探索します。一方、**`models/*.md` は自動探索されません。** ルートの `AGENTS.md` に従い、Codexが利用可能なファイル読込ツールで明示的に参照する方式です。

ローカルに導入する場合は、既存の `AGENTS.md` をバックアップしたうえで、ルートの `AGENTS.md` と `models/` ディレクトリを**同じ場所を基準に**配置してください。例：

```text
~/.codex/
├── AGENTS.md
└── models/
    ├── Luna.md
    ├── Terra.md
    ├── Sol.md
    └── Astra.md
```

このGitHubリポジトリは、ローカルのCodex環境へ自動同期されません。

### 振り分けの失敗時

1. 明示的なモデルIDまたは実行環境からの確かなモデル情報を確認します。
2. `gpt-6.2-sol` → `models/Sol.md` のように、確認できた**系列名の末尾**で判断します。
3. 読込できる場合だけ、対応する**1ファイル**を参照します。
4. IDが分からない・曖昧・未対応・ファイル不在の場合は**追加指示なし**で続行します。
5. ルーターは実行モデルを変更せず、勝手にインターネットから指示を取得しません。

**限界:** Codexが実行時のモデルIDをモデルへ確実に伝えるとは限りません。自然言語の読込指示だけでは、毎回正しいファイルを読むことは保証できません。

## 最小スモークテスト

同じCodexバージョン・環境・モデル設定で新規セッションを開始し、参照されたモデル別ファイルをセッションログまたは実際のツール履歴で確認します。モデル名の自己申告だけで合格としません。

- **PASS:** モデルIDが確認でき、対応する1ファイルだけを読んだ
- **FAIL:** 誤った系列ファイルを読んだ
- **UNCERTAIN:** モデルIDやファイル読込の実行履歴を確認できない

振り分けが合格しても、その指示が性能を改善したことにはなりません。指示の改善は別途比較します。

## 変更管理

モデル更新時は、まず今の指示のまま評価し、問題が再現された場合にだけ変更します。モデルID・Codexバージョン・推論設定・評価条件・比較結果をPRまたはIssueに記録してください。詳細は [CONTRIBUTING.md](CONTRIBUTING.md) を参照してください。

公式資料：[Codex AGENTS.md](https://developers.openai.com/codex/guides/agents-md) / [OpenAI モデル選択ガイド](https://developers.openai.com/api/docs/guides/model-selection)

このリポジトリは個人管理の公開プロジェクトであり、OpenAI公式ではありません。

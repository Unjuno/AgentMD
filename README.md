# AgentMD

OpenAI Codex向けの**Luna起点・1段階エスカレーション**実験リポジトリです。目標は、必要なタスクだけを適任モデルへ委譲し、**検証された成果品質を優先**しながら作業コストとコンテキスト負荷を抑えることです。

> **Status: Configuration implemented / runtime unverified（2026-11-24）**  
> AGENTS.mdとCodexカスタムエージェント設定は配置済み。ただし、実際のCodexでのモデル切替・委譲上限・品質改善は未検証です。これは自然言語による制御であり、厳密な権限制御機構ではありません。

## 構成と責務

```text
AgentMD/
├── AGENTS.md                       # 主要タスクの分類と1回限りの委譲方針
├── models/
│   ├── Luna.md                     # Lunaの軽量実行・調整方針
│   ├── Terra.md                    # 視覚・UIワーカーの実行指示
│   ├── Sol.md                      # 一般開発ワーカーの実行指示
│   └── Astra.md                    # 高難度ワーカーの実行指示
├── .codex/agents/
│   ├── agentmd_terra.toml          # Terraを実際に選ぶCodexの役割定義
│   ├── agentmd_sol.toml            # Solを実際に選ぶCodexの役割定義
│   └── agentmd_astra.toml          # Astraを実際に選ぶCodexの役割定義
├── README.md
└── CONTRIBUTING.md
```

`AGENTS.md` **だけ**では別モデルが起動する保証はありません。Codexがサブエージェント役割として認識するTOMLファイルで、対応するモデルIDを指定します。Codex本体が使うモデルやツールが対応していることが前提です。

## 初期ルーティング仮説

| タスクの主要特徴 | 担当 | 理由 | 除外・注意条件 |
| --- | --- | --- | --- |
| 小規模な修正、抽出、明確な定型処理 | Luna自身 | 低単価で十分な可能性 | 仕様が曖昧・影響範囲が広いなら委譲を検討 |
| 画面、画像、視覚的な確認、UI操作 | Terra | 公式に視覚・PC操作への適性が示される | UIツールや実画面が使えないなら停止・報告 |
| 通常の複数ファイル実装、機能追加、デバッグ | Sol | 公式が日常的な開発の起点として推奨 | 複雑なアーキテクチャ判断が主目的ならAstra |
| 高難度設計、重大な整合性、複雑な依存・トレードオフ | Astra | 公式が高難度の専門タスク向けに位置づける | 高価格。難しいという印象だけで選択しない |

[OpenAI公式モデル選択ガイド](https://developers.openai.com/api/docs/guides/model-selection) に基づく**初期仮説**です。実際の最適な割当てやLunaによる分類精度は未検証です。タスクが単純な場合は最初からサブエージェントを作りません。

### API単価（比較の参考情報）

2026-11-24時点の標準API価格、USD/100万テキストトークン。**Codexのサブスクリプション内の使用回数・クレジット単価ではありません。**

| 系列 | 役割に設定したモデルID | 入力 | キャッシュ入力 | 出力 | 推論レベルの初期設定 |
| --- | --- | ---: | ---: | ---: | --- |
| Luna | `gpt-6-luna`（親側で選択） | $0.10 | $0.01 | $0.50 | Codex側の設定に従う |
| Terra | `gpt-6.1-terra` | $1.00 | $0.05 | $5.00 | medium |
| Sol | `gpt-6.2-sol` | $2.00 | $0.10 | $10.00 | medium |
| Astra | `gpt-6.2-astra` | $8.00 | $0.40 | $40.00 | high |

出典：[OpenAI公式モデル一覧](https://developers.openai.com/api/docs/models)・[API料金](https://developers.openai.com/api/docs/pricing)。推論レベルは評価前の**初期設定**であり最適値ではありません。モデルや推論レベルの提供状況はCodexの画面・バージョン・プランによって異なります。

**価格性能の判断:** トークン単価だけでルーティングしません。対象タスクでの完了率、検証品質、再試行数、トークン消費、所要時間を計測し、必要ならルールを変更します。

### 公開ベンチマークと限界

- Cognitionの[FrontierCode 2.0](https://cognition.com/blog/frontier-code-2.0)で、OpenAIはGPT-6.2 SolがAstraから**0.5ポイント差、タスクコスト約1/5**（双方max推論）と公表。[発表資料](https://openai.com/index/introducing-gpt-6-2-astra-sol/)
- 公式の適性判断ではLunaは限定的・反復的な作業、Terraは視覚・PC操作、Solは通常の開発、Astraは複雑な作業に位置づけられています。[モデル選択ガイド](https://developers.openai.com/api/docs/guides/model-selection)

**注意:** ベンチマークはモデルの能力特性を説明する資料であり、AgentMDのルーティングやプロンプトの改善効果を証明する資料ではありません。条件の異なるベンチマークの点数を合算して総合順位を作りません。

## 委譲プロトコル

1. 初期モデル（想定：Luna）がタスクの目的、制約、検証条件を確認する。
2. Lunaで対応できる限定的なタスクは自分で処理する。
3. より適切な作業モデルが必要なら、`agentmd_terra`、`agentmd_sol`、`agentmd_astra` の**どれか1つ**に委譲する。直接そのモデルを設定した役割を選ぶ。
4. 委譲には、目的・必要な前提・関連ファイル・成功条件だけ渡す。V2の`fork_turns: "none"`、V1の`fork_context: false`など、実行環境が対応する新規コンテキストを使う。
5. Workerは自分の`models/*.md`だけ読み、結果を`DONE / FAILED_VALIDATION / BLOCKED`、検証証拠、変更内容、残るリスクで返す。
6. 親は根拠を確認する。**同一ユーザータスクで2回目の自動委譲は行わず**、失敗・未検証ならその旨をユーザーに報告する。

**委譲回数の制限はAGENTS.mdと役割指示による運用上の制約です。** Codexがサブエージェントを起動できるか、workerが再委譲しないかは、ローカルのログで検証してください。これだけで物理的に無限再委譲を禁止できるわけではありません。

## ローカルで導入する

[Codexのカスタムエージェント仕様](https://developers.openai.com/codex/subagents)により、ユーザー共通設定は`~/.codex/agents/`に置けます。以下は`AgentMD`リポジトリのルートで実行する例です。

**既存の`AGENTS.md`・同名エージェント設定があれば必ずバックアップし、上書きの影響を確認してください。** 自動同期・自動導入はしていません。

```sh
export CODEX_HOME="${CODEX_HOME:-$HOME/.codex}"
mkdir -p "$CODEX_HOME/models" "$CODEX_HOME/agents"
cp AGENTS.md "$CODEX_HOME/AGENTS.md"
cp models/*.md "$CODEX_HOME/models/"
cp .codex/agents/*.toml "$CODEX_HOME/agents/"
codex --model gpt-6-luna
```

`AGENTS.md` が自動的に読み込まれるのに対し、`models/*.md` は通常のMarkdownであり、ルーターまたは役割指示に従う追加のファイル読込です。

自分の別プロジェクトで使う場合には、そのプロジェクトのルートに`models/`をコピーする必要はありません。グローバル導入先である`CODEX_HOME`から参照します。AgentMDリポジトリ自身で試す場合はプロジェクト直下の`models/`を利用できます。

## スモークテスト（未実施）

1. **小規模タスク:** Lunaが追加Workerを起動せず完了すること。
2. **UIタスク:** `agentmd_terra`でTerraモデルが起動すること。
3. **通常開発:** `agentmd_sol`でSolが起動すること。
4. **複雑な設計:** `agentmd_astra`でAstraが起動すること。
5. **Worker失敗:** Workerからの再委譲がなく、証拠付きの失敗報告に戻ること。
6. **環境不備:** 役割・権限が利用できないとき、架空の起動結果を報告しないこと。

モデル自己申告ではなく、**サブエージェント実行履歴の実際のモデルID・読んだファイル・検証結果**を確認してください。CLIでは`/subagents`でサブエージェント状態を参照できます。

## キャッシュと運用上の限界

同じモデルと一致するprefixならプロンプトキャッシュの再利用余地がありますが、**別モデル間で共有されることや毎回ヒットすることは保証されません**。固定の小さなモデル別ファイルを使い、調査資料や料金表は実行指示に含めない設計にしています。[OpenAI Prompt Caching](https://developers.openai.com/api/docs/guides/prompt-caching)

更新時のルールは[CONTRIBUTING.md](CONTRIBUTING.md)を参照してください。これはOpenAI公式のリポジトリではありません。

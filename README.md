# LLM Evaluation Input Design Guideline

LLM出力評価に使用する **Input Datasetを網羅的かつ再現可能に設計するためのガイドライン** です。

## 目的

本ガイドラインは、評価用Inputの具体的な分類内容を標準化するものではありません。

ユースケースごとに異なるInput空間を整理し、評価に必要なInput Datasetを設計するための **手順（HOW）** を標準化します。

### 標準化するもの

- Input Datasetを設計するプロセス
- 各ステップの目的・入力・成果物
- 設計結果を記録するフォーマット
- 設計内容を確認するためのチェックポイント

### 標準化しないもの

- Inputを分類する具体的な軸
- 各軸が取り得る具体的なパターン
- すべてのユースケースに共通する固定的なテストケース
- Outputの評価観点・評価基準

具体的な分類軸やパターンは、対象ユースケースの要件・データ・リスクに応じて設計します。

## Input設計標準

1. ユースケースを定義する
2. Inputを構成する要素・条件を洗い出す
3. 各要素について取り得るパターンを分類する
4. パターンの組み合わせを整理する
5. 評価に必要な代表Inputを選定する
6. 評価用Input Datasetとして整理する

詳細は [Input設計プロセス](docs/input-design-process.md) を参照してください。

## 成果物

本プロセスでは、次の成果物を作成します。

| 成果物 | 内容 |
|---|---|
| ユースケース定義 | 誰が、何を入力し、何を達成するか |
| Input Dimension一覧 | Inputを構成する独立した要素・条件 |
| Input Pattern一覧 | 各Dimensionが取り得る分類・値域 |
| 組み合わせ一覧 | 評価対象とするPatternの組み合わせ |
| 代表Input一覧 | 評価に採用する具体的なInput |
| Evaluation Input Dataset | 実行・評価に利用できる形式のデータセット |

設計時は [Input設計テンプレート](templates/input-design-template.md) を利用できます。

## Output評価との関係

本ガイドラインが扱うのは、LLMに **何を入力して評価するか** です。

Outputの評価観点・評価基準・判定方法は本ガイドラインの対象外とし、Input設計とは分離して管理します。

```text
Use Case
   ├── Input Design
   │      └── Evaluation Input Dataset
   └── Evaluation Design
          └── Criteria / Rubric / Metrics
                    ↓
              LLM Evaluation
```

## リポジトリ構成

```text
.
├── README.md
├── docs/
│   └── input-design-process.md
├── templates/
│   └── input-design-template.md
└── examples/
    └── README.md
```

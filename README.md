# AI 評価ツール

このリポジトリは、Azure OpenAI サービス等の出力を検証するツールです。

## 主な機能

- **Azure OpenAI サービス**: 入力データに基づいてテキスト生成を行います。
- **Azure PII サービス**: 入力データから個人情報を識別します。
- **評価機能**: サービスの出力を以下の基準で評価します。
  - 期待される出力との類似度スコア
  - 完全一致かどうかのチェック
  - ユーザーが定義可能な評価基準に基づくスコア
- **GitHub Actions**: 自動的に出力生成と評価を実行します。

## 必要条件
- .NET 8.0 以上
- Azure OpenAI Serviceと Azure PII Detection サービスへのアクセス権

## 使用方法
1) Clone the repo
2) Save the test data in the /data/input folder
3) Deploy the Azure resources defined in bicep
4) Run code that calls either Azure OpenAI or Azure PII detection with the input data and saves the results in /data/output
5) Evaluates the results, and saves the results in /data/evaluations

## GitHub Actions
本リポジトリには、定期的に自動実行する GitHub Actions ワークフローが含まれています。

### 主要なステップ

1. リポジトリのコードをチェックアウト
2. 必要な NuGet パッケージのインストール
3. Azure OpenAI と Azure PII Detection の実行
4. 評価結果を生成し、GitHub Actions の成果物として保存

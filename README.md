# AI 評価ツール

このリポジトリは、Azure OpenAI サービス等の出力を評価するツールです。

## 主な機能

- **Azure OpenAI サービス**: 入力データに基づいてテキスト生成を行います。
- **Azure PII サービス**: 入力データから個人情報を識別します。
- **評価機能**: サービスの出力を以下の基準で評価します。
  - 期待される出力との類似度スコア
  - 完全一致かどうかのチェック
  - ユーザーが定義可能な評価基準に基づくスコア
- **GitHub Actions**: 自動的に出力生成と評価を実行します。

## 必要条件

- .NET 6.0 以上
- Azure OpenAI Serviceと Azure PII Detection サービスへのアクセス権

## 使用方法

### コマンド例

#### Azure OpenAI サービスの実行

```bash
dotnet run -- openai "私の住所は東京都港区港南 2-16-3 品川グランドセントラルタワーです"
```

#### Azure PII Detection サービスの実行

```bash
dotnet run -- pii "私の住所は東京都港区港南 2-16-3 品川グランドセントラルタワーです"
```

### 出力

- 実行結果は `output/` ディレクトリ内に保存されます。

## GitHub Actions

本リポジトリには、定期的に自動実行する GitHub Actions ワークフローが含まれています。

### 主要なステップ

1. リポジトリのコードをチェックアウト
2. 必要な NuGet パッケージのインストール
3. Azure OpenAI と Azure PII Detection の実行
4. 評価結果を生成し、GitHub Actions の成果物として保存

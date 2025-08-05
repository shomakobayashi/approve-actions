# GitHub Actions 承認フロー

このプロジェクトは GitHub Actions の承認フローを実装したサンプルです。

## 機能

- 手動トリガー（workflow_dispatch）でワークフローを実行
- Environment Protection Rules による承認フロー
- 実行者以外のユーザーが承認可能

## セットアップ手順

### 1. Environment の作成

GitHub リポジトリで以下の設定を行います：

1. リポジトリの **Settings** → **Environments** に移動
2. **New environment** をクリック
3. Environment name: `approval-required` を入力
4. **Configure environment** をクリック

### 2. Protection Rules の設定

Environment の設定画面で：

1. **Required reviewers** にチェックを入れる
2. 承認者を追加（実行者以外のユーザー/チーム）
3. **Prevent self-review** にチェックを入れる（重要！）
4. **Save protection rules** をクリック

### 3. 実行方法

1. GitHub リポジトリの **Actions** タブに移動
2. **Manual Approval Workflow** を選択
3. **Run workflow** をクリック
4. メッセージを入力（オプション）
5. **Run workflow** で実行開始

### 4. 承認プロセス

1. ワークフローが開始されると承認待ち状態になります
2. 実行者以外のユーザーが承認する必要があります
3. 承認後、ワークフローが続行されます

## 注意事項

- **Prevent self-review** の設定により、実行者は自分で承認できません
- Environment Protection Rules は GitHub の有料プランまたはパブリックリポジトリで利用可能です
- プライベートリポジトリの場合は GitHub Pro 以上のプランが必要です

## カスタマイズ

- 承認者の数を変更: Required reviewers の数を調整
- 承認タイムアウト: Environment settings で Wait timer を設定
- 承認者の指定: 特定のユーザーやチームを指定可能
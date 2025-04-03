# Valheim サーバー

Dockerを使用してValheimサーバーを簡単にセットアップ・管理するためのリポジトリです。

## 必要条件

- Docker
- Docker Compose

## セットアップ方法

1. リポジトリをクローンします：
```bash
git clone [リポジトリURL]
cd valheim-server
```

2. 環境変数ファイルを作成します：
```bash
cp .env.example .env
```

3. `.env`ファイルを編集して、以下の設定を行います：
- `SERVER_NAME`: サーバー名
- `SERVER_PASS`: サーバーパスワード
- `SERVER_PUBLIC`: パブリックサーバーかどうか（true/false）
- `WORLD_NAME`: ワールド名
- `TZ`: タイムゾーン（デフォルト: Asia/Tokyo）
- `BACKUPS_DIRECTORY`: バックアップディレクトリ
- `BACKUPS_MAX_COUNT`: 保持するバックアップの最大数
- `DATA_PATH`: データ保存先のパス
- `CONFIG_PATH`: 設定ファイル保存先のパス

4. サーバーを起動します：
```bash
docker-compose up -d
```

## ポート設定

- 2456/udp: ゲームサーバー
- 2457/udp: サーバーリスト

## バックアップ

サーバーは自動的にバックアップを作成します。バックアップは`BACKUPS_DIRECTORY`で指定されたディレクトリに保存され、`BACKUPS_MAX_COUNT`で指定された数のバックアップが保持されます。

## サーバーの停止

```bash
docker-compose down
```

## 注意事項

- サーバーを初めて起動する際は、ワールドの生成に時間がかかる場合があります
- サーバーのパフォーマンスは、ホストマシンのリソースに依存します
- 定期的なバックアップを取ることを推奨します 
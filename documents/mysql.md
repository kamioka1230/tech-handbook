TOC
- [セットアップ](#セットアップ)
- [ダンプ](#ダンプ)
- [トラブルシューティング](#トラブルシューティング)

## セットアップ

インストール
```bash
brew install mysql
```

バージョン確認
```bash
mysql --version
```

mysqlサーバのコマンド
```bash
#状態確認
mysql.server status

#起動
mysql.server start

#停止
mysql.server stop

#リロード(設定ファイルの再読み込み）
mysql.server reload

#再起動
mysql.server restart

#ログイン
mysql -uroot
```

## ダンプ
https://qiita.com/PlanetMeron/items/3a41e14607a65bc9b60c

## トラブルシューティング

### ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/tmp/mysql.sock' (2)

MySQLサーバにsocket接続できてない。サーバ起動してるか？



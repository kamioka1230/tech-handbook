TOC
- [セットアップ](#セットアップ)
- [ユーザ](#ユーザ)
- [権限]（#権限)
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

## ユーザ

`CREATE USER 'uwl'@'localhost' IDENTIFIED WITH mysql_native_password BY 'uwl'`

## 権限

`GRANT ALL ON db_name.* TO user;`

## ダンプ
https://qiita.com/PlanetMeron/items/3a41e14607a65bc9b60c

## トラブルシューティング

### ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/tmp/mysql.sock' (2)

MySQLサーバにsocket接続できてない。サーバ起動してるか？



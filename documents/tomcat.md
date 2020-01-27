## Tomcat

### Windows

**インストール**

- 公式からzipファイルをダウンロードして解凍
- server.xml, web.xmlを設定
- start.batで起動する

Windowsの場合は、windowsのService(?)としても実行できる。cygwinからの実行はややこしいのでサーバ起動/停止はコマンドプロンプトから行った。

**プロキシサーバを使用するTomcatの設定**

下記の内容を設定。`socksProxyHost`でJDBCもプロキシ接続できるようになる

setenv.bat
```bat
rem Tomcat Proxy Property
set JAVA_OPTS=%JAVA_OPTS% ^
-Dhttp.proxySet=true ^
-Dhttp.proxyHost=[hostname] ^
-Dhttp.proxyPort=[port] ^
-Dhttp.nonProxyHosts=localhost ^
-DsocksProxyHost=[hostname] ^
```

## Tomcat

**xxxxのリソースをキャッシュに追加できませんエントリ - キャッシュの最大サイズを増やすことを検討してください**

キャッシュサイズ不足で生じる問題。Tomcat7では表示されなかった警告がTomcat8で表示されるようになった。
キャッシュサイズを増やして対応する。設定は`TOMCAT_DIR/conf/context.xml`に下記を追加すれば良い。

```xml
<Resources cacheMaxSize="51200" />
```

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

**Tomcatのコンソールに表示されるログが文字化けする問題**

おおかたエンコードがUTF-8とかSJISかの違い。`TOMCAT_DIR/conf/logging.properties`の`java.util.logging.ConsoleHandler.encoding = SJIS`のようにして設定できる。（TomcatのデフォルトはUTF-8で、windows側のデフォルトがSJISになっていて食い違うことが多い）

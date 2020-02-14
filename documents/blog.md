## WordPress

### 構成
- Amazon LightSail
- Bitnami Apache + WordPress

### 証明書
- Let’s Encrypt
- 参考：[AWS LightsailのWordPressでLet’s Encryptを使ってSSL化する方法](https://debugging-code.com/2019/07/31/110/)

## Blogger

### 広告
- headでだけadsbygoogle.jsを読み込んで、設置したい場所にinline-adsタグを置く。ウィジェットでJavaScriptを実行して広告タグをレンダリングしてる。

## Nuxt.js

### Server

開発環境では `nuxt dev`、本番環境では`nuxt start`。静的ファイルとして出力する場合は`nuxt generate`を使う。
このコマンドをpackage.jsonのscriptsの項目に登録すると（デフォルトでdevとstartは書いてある）、`npm run dev`のようにしてサーバを起動できる。
デフォルトだと`localhost:3000`で起動する。

本番環境では事前に`nuxt build`(`npm run build`)を実行する。各ファイルは`.nuxt`フォルダに出力される。

ターミナルを終了するとサーバが停止してしまうので本番環境ではデーモンとして起動する必要あり。`forever`が使える（という情報があったが、foreverを使うと停止してもnuxtのプロセスが残ってしまう（？））

foreverのコマンド
```bash
sudo forever -c "npm run start" ./&
```

### 設定ファイル

head内の設定やプロジェクト全体で読み込むファイルは`nuxt.config.js`で設定することができる。

nuxt.config.js
```javascript
export default {
  head: {
    script: [
      { src: 'https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js' }
    ],
    link: [
      { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css?family=Roboto&display=swap' }
    ]
  },
  css: [
    '~/assets/style/app.scss',
  ],
}
```

### Template

ページ固有のテンプレートを適用したい場合は、layoutにテンプレートを作成して下記のように読み込む。

```javascript
export default {
  layout: 'hoge',
```

### style
- Vueファイル内のstyleに`scoped`をつけるとそのVueファイルだけにスタイルが適用されるようになる

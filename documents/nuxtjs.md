## Nuxt.js

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

### style
- Vueファイル内のstyleに`scoped`をつけるとそのVueファイルだけにスタイルが適用されるようになる

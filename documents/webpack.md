## webpack

モジュール間の依存関係を**bundle**する役目。

モジュールとは`.js`ファイルのこと。あるJSファイルで別のJSファイルを読み込む必要があるなどの依存関係を、特定の起点ファイルをはじめとして解決し、ひとつのJSファイルにまとめることができる。

### インストール

```
npm install webpack
```

### 設定 - webpack.config.js

- `entry` にバンドルの起点となるファイル
- `output` に出力情報

```javascript
module.exports = {
  entry: './src/index.js', 
  output: {
    path: __dirname + '/dist',
    filename: 'sample.js'
  }
};
```

### 実行、基本操作
```
npx webpack
npx webpack <src> -o <dist>
npx webpack --config <config>
```

上記コマンドを実行すると`/src/index.js`を起点ファイルとして、`/dist/main.js`にバンドルしたファイルを出力する。入出力ファイルを指定することもできる。

`package.json`に登録して利用する

```json
{
  "scripts": {
    "start": "webpack -w --config webpack.dev.config",
    "build": "webpack --config webpack.pro.config"
  },
}
```



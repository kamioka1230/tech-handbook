## Node.js
サーバサイドJavaScriptの実行環境。

Table of Contents
- 環境構築
  - [インストール](#nodebrew)
  - [package.json](#packagejson)
- [Express](#express)
  - [express-generator](#express-generator)

## 環境構築

### node

### npm
node package manager
- パッケージレジストリ
  - Node.jsのパッケージが集められたレポジトリ
- CLI
  - パッケージを操作するためのCLI。Node.jsに付属している
  - Facebookが開発した yarn というCLIもある
  
### package.json

`npm install`を実行するとpackage.jsonに指定されたバージョンのパッケージがインストールされる。

```js
{
  "name": "my-package",
  "description": "my first package ever",
  "license": "MIT",
  "version": "1.0.0",
  "bin": "./cli.js",
  "main": "index.js",
  "main": "index.js",
  "scripts": { // コマンドのエイリアス npm run <command> で実行できる。
    "build-client-ts": "tc",
    "start": "node index.js", // 一部の予約語は npm start のように実行できる
  },
  "dependencies": { // 実行環境で必要なパッケージ
    "axios": "^0.18.0"
  },
  "devDependencies": { // 開発・テスト環境で必要なパッケージ
    "eslint": "^5.14.1"
  }
}
```

packageのインストール方法
```
npm install <package>
npm install -D <package>
npm install <package>@<version>
npm uninstall <package>
```

- https://qiita.com/righteous/items/e5448cb2e7e11ab7d477
- [フロントエンド開発の３ステップ（npmことはじめ）](https://qiita.com/hashrock/items/15f4a4961183cfbb2658)

### nodebrew
複数バージョンのnodeを一元管理するできる。

インストール

```
brew install nodebrew
```

バージョン確認

```
nodebrew -v
```

環境変数

```
export PATH=$HOME/.nodebrew/current/bin:$PATH
```

nodeインストール

```
# インストール可能なnodeバージョンを確認
nodebrew ls-remote

# バージョンを指定してインストール
nodebrew install-binary <version>

# インストール済みのバージョンを確認
nodebrew ls

# 使用するバージョンを指定
nodebrew use <version>
```

## Express
- Express実践入門 https://gist.github.com/mitsuruog/fc48397a8e80f051a145

```
npm install express
```

### 静的ファイル

```
app.use(express.static('public'));
```

index.jsに上記のように書くとpublic以下を静的ファイルとして参照できる。
https://expressjs.com/ja/starter/static-files.html

### express-generator
Expressjsを使ったプロジェクトを簡単に始められる。

```
# install
npm install -g express-generator

# create project
express --view=pug myapp
npm install
npm start
```

- [参考](https://expressjs.com/ja/starter/generator.html)


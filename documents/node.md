## Node.js
サーバサイドJavaScriptの実行環境。

## node

## npm
node package manager
- パッケージレジストリ
  - Node.jsのパッケージが集められたレポジトリ
- CLI
  - パッケージを操作するためのCLI。Node.jsに付属している
  - Facebookが開発した yarn というCLIもある
  
## package.json

`npm install`を実行するとpackage.jsonに指定されたバージョンのパッケージがインストールされる。

```json
{
  "name": "my-package",
  "description": "my first package ever",
  "license": "MIT",
  "version": "1.0.0",
  "bin": "./cli.js",
  "main": "index.js",
  "main": "index.js",
  "scripts": {
    "start": "node index.js"
  },
  "dependencies": {
    "axios": "^0.18.0"
  },
  "devDependencies": {
    "eslint": "^5.14.1"
  }
}
```

### dependencies/devDependencies
依存関係。実行環境で必要/開発やテストでのみに必要なパッケージ。

```
npm install <package>
npm install -D <package>
npm install <package>@<version>
npm uninstall <package>
```

### scripts
コマンドのエイリアス。`npm run <name>`で実行できる

### 参考
- https://qiita.com/righteous/items/e5448cb2e7e11ab7d477

## nodebrew
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

# Express.js

Table of Contents

- [パスに含まれるパラメータを取得する](#パスに含まれるパラメータを取得する)
- [GETで送信されたパラメータを取得する](#GETで送信されたパラメータを取得する)
- [POSTされたパラメータを取得する](#POSTされたパラメータを取得する)

## パスに含まれるパラメータを取得する

- `/path/12345`
- req.paramsで取得

```js
app.get('/path/:id', (req, res) => {
  res.send(req.params.id);
});
// > 12345
```

## GETで送信されたパラメータを取得する

- `/path?name=John` の場合
- req.queryで取得

```js
app.get('/path', (req, res) => {
  res.send(req.query.name);
});
// > John
```

## POSTされたパラメータを取得する

- body-parserモジュールを使う
- req.bodyで取得

```js
import bodyParser from "body-parser";

// どちらか
app.use(bodyParser.urlencoded({ extended: true }));
app.use(bodyParser.json);

app.post('/path', (req, res) => {
  res.send(req.body.name);
});
// > John
```
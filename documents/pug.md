# Pug

Table of Contents
- [styleタグを使う](#styleタグを使う)

## hrefに変数を使う

```
a(href=`/path/to/${variable}`)
```

## 三項演算子

`=`を使う。

```
// string
button.btn.btn-round= image ? "Change Image" : "Add Image"

// attribute
button(class= image ? "green" : "red")
```

## styleタグを使う

`.` をつけるとpug内でstyleタグが使える

```
style(type="text/css").
  body {
    ...
  }
  main {
    ...
  }
```
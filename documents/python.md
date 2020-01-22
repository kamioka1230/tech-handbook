## Python

### 辞書
- `iteritems()`はPython3では廃止済み。`items（）`で同じことができる

tupleからdict
```python
>>> t = ((1, 'a'),(2, 'b'))
>>> dict((y, x) for x, y in t)
{'a': 1, 'b': 2}

>>> t = ((1, 'a'),(2, 'b'))
>>> dict(map(reversed, t))
{'a': 1, 'b': 2}
```

### 正規表現
- splitはゼロ幅アサーション(zero-length assertion)をサポートしない

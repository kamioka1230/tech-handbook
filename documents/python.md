## Python

### SSH


paramikoでコマンドを実行する
```python
import paramiko

ssh = paramiko.SSHClient()
ssh.connect(host, port, user)
stdin, stdout, _ = ssh.exec_command(COMMAND)

stdin.write('m\n') # これは対話的な処理
stdin.flush()

output = stdout.readline()
```

### range
- 3系の`range()`は2系の`xrange()`、2系の`range()`は3系には存在しない

### 辞書
- `iteritems()`はPython3では廃止済み。`items（）`で同じことができる
- `has_key()`のPython3には存在しない。`key in dict`で同じことができる

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

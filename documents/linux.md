## Linux

### ssh

渡す公開鍵を選択する
```bash
ssh-copy-id -i id_rsa_dev.pub user@host
```

多段sshするときの `.ssh/config`

```bash
Host fumidai
  User user
  HostName x.xxx.x.xxx
  IdentityFile ~/.ssh/some.pem
  
Host app
  User user
  IdentityFile ~/.ssh/some.pem
  ProxyCommand ssh -W %h:%p fumidai
```

### password

`brew install pwgen` でインストールして使う。

```bash
#16文字のパスワードを一つ生成
pwgen 16 1

#記号付き
pwgen -y

#数字なし
pwgen -0 

#大文字なし
pwgen -A
```

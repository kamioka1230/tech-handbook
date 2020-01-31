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

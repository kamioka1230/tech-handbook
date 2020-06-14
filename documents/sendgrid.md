# SendGrid

SendGridを使ってDM配信を行う。

SendGridのAPIのリポジトリ 

sendgrid / sendgrid-nodejs  
https://github.com/sendgrid/sendgrid-nodejs


https://github.com/sendgrid/sendgrid-nodejs/blob/master/docs/use-cases/README.md#email-use-cases

## SendGrid上でのステータスの見方
ログイン後、Activityタブから確認できる。
https://sendgrid.kke.co.jp/docs/User_Manual_JP/email_activity.html
- Processed: SendGridがリクエストを受け付けた
- Delivered: 送信済み
- Deffered: 先方のクライアント側からストップがかかってる。SendGridが勝手に送り直す
- Drops: 送らないリストにある送信先
- Bounces/Blocks: 送れなかった。次回以降はSendGridが自動で送らないようにする

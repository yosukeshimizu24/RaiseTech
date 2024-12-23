# 第7回課題

## リスク
- EC2のアウトバウンドルールの送信先を、全てのポートすべてのプロトコルに対して「0.0.0.0/0」に設定しているから、これは情報漏洩の原因の一つだと考えられる。対策としては、全てのポート全てのプロトコルではなく、例えば特定のデータベースに接続する場合、3306を開放しデータベースサーバーのIPアドレスのみに通信を許可などの対策をするべき。

- http通信であるため、これも情報漏洩の原因の一つだと考えられる。対策としては、AWS ACMを使い証明書を発行し、インターネットからALBへの接続をhttps通信にすることで防げると考えられる。


## 感想・疑問
- インターネットからALB(ELB)への通信をhttpsにすることは情報漏洩を防ぐ一つということは、ALBからEC2やEC2からRDSなどの通信も、https通信にするべきなのかなと疑問に思った。
- 自分が作成した環境は、特に情報漏洩のリスクがあるなのかなと今回の課題で思った。
- ニュースでも情報漏洩などよく耳にするので、今回のセキュリティに関しての内容はすごく重要なものなのだなと感じた。
- AWS ACMなど第5回課題の最中、目にしたものが出てきてより理解が増した。
thubでpushできるようにする

#gitのインストール
1.yum install git

2.sshキー作成
ssh-keygen -t rsa -C "kikituki@gmail.com"
｛｛｛
[vagrant@localhost .ssh]$ ssh-keygen -t rsa -C "kikituki@gmail.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/home/vagrant/.ssh/id_rsa): [何も入力せずにEnter]
Enter passphrase (empty for no passphrase): [任意のパスワード]
Enter same passphrase again: [任意のパスワード]
Your identification has been saved in /home/vagrant/.ssh/id_rsa.
Your public key has been saved in /home/vagrant/.ssh/id_rsa.pub.
The key fingerprint is:
bf:33:38:e6:18:78:4a:5d:1f:a9:61:03:31:a7:70:a5 kikituki@gmail.com
The key's randomart image is:
+--[ RSA 2048]----+
|    . +.o        |
|     o *         |
|      E          |
|       .   .     |
|        S o      |
|     o o * .     |
|    o + ..o      |
|   . o o+ o.     |
|    . .o...o     |
+-----------------+
｝｝｝

3．作成したKeyを登録
githubのアカウント設定画面より

4．設定ファイルの修正
/home/vagrant/rails_app/.git/config

[remote "origin"]
        fetch = +refs/heads/*:refs/remotes/origin/*
        #url = https://kikituki@github.com:kikituki/rails_app.git
        url = ssh://git@github.com/kikituki/rails_app.git


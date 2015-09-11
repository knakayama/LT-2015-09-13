layout: true

class: center, middle

---
# Ansibleを使って
# さくらのクラウド上に
# サーバ作れるようにしたい件
## knakayama

---
# 自己紹介

---
# 中山 幸治
# [knakayama](https://github.com/knakayama)

---
# さくらインターネットで
# レンタルサーバの
# 運用を担当

---
# ところでさくらのクラウド
# 使ってますか？

---
# 心の声が聴こえる

---
# こんなこと社内で
# ないですか？

---
# オンプレ環境を
# パブリッククラウドへ
# 移行する計画

---
# ありそうな光景

---
### 中立的なAさん
## 「どのパブリッククラウド使おうかな〜
## とりあえずAWS検証してみるか〜」

---
### イベントでさくらのクラウド無料チケットもらったBさん
## 「そういえばさくらのクラウド無料
## チケット持ってるのでそれ使って
## 検証してみましょうか〜」

---
### AWSに毒されてるCさん
## 「いやそういうの時間の
## 無駄なんでいいです」

---
# こういう悲しみの
# 連鎖を止めたい

---
# なぜAWSは強いのか

---
# いろいろ理由ある

---
# 強さの一つに周辺ツールの
# エコサイクルがある

---
# 多くの企業/コミュニティが
# AWS対応のツールを
# 勝手に作ってくれる

---
# vagrant/packer/terraform
# chef/Ansible/puppet
# etc...

---
# だったらエコサイクルを
# 自分で作ればいいのでは

---
# じゃあ最近良く使っている
# Ansibleでさくらのクラウドに
# サーバ作れるツールが
# あったら便利では

---
# なので作ってみた

---
# [ansible-sacloud](https://github.com/knakayama/ansible-sacloud)

---
# どんなツールなのか

---
# Ansibleで
# さくらのクラウドに
# サーバ作れる

---
# 何が嬉しいのか

---
# APIの知識無くても
# プログラマブルに
# サーバ作れる

---
# 他の利点は？

---
# ブートストラップから
# オーケストレーションまで
# インフラの状態を
# コードとして表現できる

---
# Still in heavily development!!!111

---
# 冪等性が
# ガバガバ

---
# 素人には
# おすすめできない

---
# Demo

---
# 参考にしたツール

---
# [vagrant-sakura](https://github.com/tsahara/vagrant-sakura)
# [sakurraform](https://github.com/higanworks/sakurraform)

---
# Ansibleのモジュール開発

---
# とりあえず公式ドキュメント
# 読んだ方がいい
# [Developing Modules](http://docs.ansible.com/ansible/developing_modules.html)

---
# [core module](https://github.com/ansible/ansible-modules-core)
# [extra core module](https://github.com/ansible/ansible-modules-extras)
# Ansibleの公式モジュールを
# 見ると大体分かる

---
# 言語はなんでもOK

---
# ただpythonで作ると
# いろいろとモジュール
# 使えて便利

---
## ansible/lib/ansible/module_utils
## ↑に便利モジュールある

---
name: python

```python
unko
```

---
# 本当はリソース毎に
# (disk/network/server/etc...)
# モジュール分けたかった

---
## sacloud_disk.py
## sacloud_server.py
## sacloud_network.py
## etc...

---
# site_facts 使うと
# できるっぽい

---
```code
A good idea might be make a module called ‘site_facts’ and always call it at the top of each playbook, though
we’re always open to improving the selection of core facts in Ansible as well.
```

---
# プルリク募集中です！

---
# いろいろとしゃべり
# ましたけど

---
# 言いたいことは

---
# さくらのクラウド
# もっと使ってくれ！

---
background-image: url(images/end-scaled.jpg)
ackground-position: center center;
ackground-size: cover;
ackground-repeat: no-repeat;
ackground-attachment: fixed;

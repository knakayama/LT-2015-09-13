layout: true

class: center, middle

---
# Ansibleを使って
# さくらのクラウド上に
# サーバ作れるようにした~~い~~件
## knakayama

---
# 自己紹介

---
# 中山 幸治
# [knakayama](https://github.com/knakayama)
![knakayama](images/knakayama.png)

---
# さくらインターネットで
# レンタルサーバの
# 運用を担当

---
# アジェンダ

---
# さくらのクラウドの話
# Ansibleの話

---
# さくらのクラウド
# 使ってますか？

---
# 大声援が聞こえる

---
# 圧倒的感謝

---
# ところで
# こんなこと社内で
# ないですか？

---
# オンプレ環境を
# パブリッククラウドへ
# 移行する計画

---
# ありそうな光景

---
# Aさん

---
## 「どのパブリッククラウド使おうかな〜
## とりあえずAWS検証してみるか〜」

---
# イベントで
# さくらのクラウド
# 無料チケットもらったBさん

---
## 「そういえばさくらのクラウド無料
## チケット持ってるのでそれ使って
## 検証してみましょうか〜」

---
# デファクト厨Cさん

---

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
# Chef/Ansible/Puppet
# fluentd/logstash
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
# YAMLに必要な設定を
# 記述すればいいだけ

---
# 他の利点は？

---
# ブートストラップから
# プロビジョニングまで
# インフラの状態を
# コードとして表現できる

---
# under heavy
# development!!!!

---
# 冪等性が
# ガバガバ

---
# 素人には
# おすすめできない

---
# 参考にしたツール

---
# [vagrant-sakura](https://github.com/tsahara/vagrant-sakura)
# [sakurraform](https://github.com/higanworks/sakurraform)

---
# 素直にこっち
# 使った方がいい

---
# [Demo](https://github.com/knakayama/ansible-sacloud-demo)

---
# Ansibleにおける
# モジュール開発

---
# トップディレクトリの
# `library` 以下に置く
# [Best Practices](http://docs.ansible.com/ansible/playbooks_best_practices.html)

---
# JSONでSTDOUTに
# 出力すれば
# 言語はなんでもOK

---
# ただpythonで作ると
# 便利モジュールを
# 利用できる

---
## `ansible/lib/ansible/module_utils/*`
## 特に `basic.py` は必須

---
# YAMLパースして
# いい感じに引数を
# 扱ってくれる

---
## `module = AnsibleModule(argument_spec=dict(...))`
## `hoge = module.params["hoge"]`

---
# モジュールの成功/失敗を
# いい感じに出力してくれる

---
## `module.exit_json(changed=True, msg=msg)`
## `module.fail_json(msg=msg)`

---
# 冪等性の担保は
# モジュールの開発者に
# 責任がある

---
# インフラがすでに
# 「あるべき状態」か
# 常に確認

---
# `--check` オプション指定時に
# インフラが変更されるか
# 表示することも必要

---
# `if module.check_mode:`

---
# モジュールの中で
# `facts` を追加できるので
# 後から参照可能

---
## `module.exit_json(..., ansible_facts=dict(hoge=fuga))`
## `{{ hoge }}` #=> fuga

---
# 後は単なる
# pythonスクリプト

---
# 実際のコード

---
# 公式ドキュメント
# [Developing Modules](http://docs.ansible.com/ansible/developing_modules.html)

---
# Ansibleの公式モジュール
# [core module](https://github.com/ansible/ansible-modules-core)
# [extra core module](https://github.com/ansible/ansible-modules-extras)

---
# この辺見ておけば
# 結構簡単に作れる

---
# 公式モジュールだけでは
# 物足りない時にぜひどうぞ

---
# いろいろとしゃべり
# ましたけど

---
# 言いたいことは

---
# さくらのクラウド
# もっと使ってくれ！

---
background-image: url(images/end.jpg)

---
background-image: url(images/end.jpg)
# **終**

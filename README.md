## zabbix4.0_ansible 概要
ansible2.7を用いてZabbix-server 4.0を構築する。

## 環境
* ansibleサーバ
  + CentOS7
  + ansible2.7
  
* Zabbixサーバ
  + CentOS7
  + インターネット接続可能
  + SELINUX無効

## 設定内容
* zabbix-server
  + firewall設定
  + zabbixリポジトリ登録
  + zabbix-serverインストール
  + zabbixデータベース作成
  + zabbix-server設定

* zabbix-agent
  + firewall設定
  + zabbixリポジトリ登録
  + zabbix-agentインストール
  + zabbix-agent設定
  
## 変数一覧
* role/zabbix-server/defaults/main.yml
  + zabbix_mariadb_password ... zabbixデータベースのパスワード
  + php_timezone ... タイムゾーン
  
* role/zabbix-agent/defaults/main.yml
  + zabbix_server_ip ... ZabbixサーバのIPアドレス
  + zabbix_server_active_ip ... Zabbixサーバ（アクティブ）のIPアドレス
  + allow_root ... Zabbixからサーバへのアクセス時にrootユーザを許可するなら 1 しないなら 0   
  
## 実行方法
```
git clone https://github.com/AkihikoTakahashi/zabbix4.0_ansible.git
vi zabbix4.0_ansible/production
IPをZabbixサーバのIPに変更してください

ansible-playbook -i zabbix4.0_ansible/production zabbix4.0_ansible/site.yml --ask-pass
```

完了すると http://ZabbixIP/zabbix でアクセスできます。

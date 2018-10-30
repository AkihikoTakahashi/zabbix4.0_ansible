# zabbix4.0_ansible 概要
ansible2.7を用いてZabbix-server 4.0を構築する。

## 環境
* CentOS7
* Zabbix4.0

## 設定内容
* zabbix-server
  + zabbixリポジトリ登録
  + zabbix-serverインストール
  + zabbixデータベース作成
  + zabbix-server設定

* zabbix-agent
  + zabbixリポジトリ登録
  + zabbix-agentインストール
  + zabbix-agent設定
  
# 変数一覧
* role/zabbix-server/defaults/main.yml
  + zabbix_mariadb_password ... zabbixデータベースのパスワード
  + php_timezone ... タイムゾーン
  
* role/zabbix-agent/defaults/main.yml
  + zabbix_server_ip ... ZabbixサーバのIPアドレス
  + zabbix_server_active_ip ... Zabbixサーバ（アクティブ）のIPアドレス
  + allow_root ... Zabbixからサーバへのアクセス時にrootユーザを許可するなら 1 しないなら 0   
  

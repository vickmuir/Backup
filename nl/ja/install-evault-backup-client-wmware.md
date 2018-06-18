---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-03"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# VMware 用の EVault バックアップ・クライアントのインストール

EVault バックアップ・クライアントは、ターゲットの ESX サーバー内のシェルまたは端末で一連のコマンドを実行することにより、VMware サーバーにインストールすることができます。この手順では、VMware サーバーに EVault バックアップ・クライアントをインストールするために必要なステップの概要を示します。

エージェントをインストールするには、以下のコマンドを使用して、`Agent-VMware-ESX-Server-6.71.<version-info>.tar.gz` パッケージをターゲットの ESX サーバーにダウンロードおよびコピーします。

`wget -N http://downloads.service.softlayer.com/evault/archive/Agent-VMware-ESX-Server-6.71.2105.tar.gz`

**注**: 以下のステップは、ターゲットの ESX サーバー上でローカルに実行する必要があります。

1. パッケージからファイルを抽出します。このためには、次のコマンドを実行します (「PACKAGENAME」は「Agent-VMware-ESX-Server-6.71」などにすることができます)。
    `tar xvfz PACKAGENAME.tar.gz`
2. パッケージを抽出したディレクトリーに移動します。
3. 次のインストール・スクリプトを実行します。
    `# ./install.sh`

    **注**: インストール・スクリプトにより、Web 登録などの構成情報 (アドレス、ポート番号、および認証) とログ・ファイル名を求めるプロンプトが対話式に出されます。
     
    - このサーバーの WebCC ユーザー名を入力します。
    - このサーバーの WebCC パスワードを入力します。
     
4. WebCC ユーザー名を要求するプロンプトの入力として、**EVault Backup Username** を入力します。 
5. WebCC パスワードを要求するプロンプトの入力として、**EVault Backup Password** を入力します。
6. インストールが終了すると完了メッセージが表示され、エージェント・デーモンが稼働中になります。


### インストールに関するその他の注:
インストールが成功した場合、Install.log はインストール・ディレクトリー内にあります。
例: `/opt/BUAgent/Install.log`

インストールが失敗してロールバックした場合、インストール・ログは `<Installation Failure directory>` 内にあります。
インストールが失敗してロールバックしなかった場合、インストール・ログは `<Installation Kit directory>` 内にあります。

詳しくは、[VMware_Agent_User_Guide](http://downloads.service.softlayer.com/evault/Documentation/VMware_Agent_User_Guide.pdf){:new_window} をダウンロードしてください。このリンクを表示するためには、{{site.data.keyword.BluVPN}} に接続していることを確認してください。

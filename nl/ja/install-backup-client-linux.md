---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup, EVault, Carbonite, backup, install agent, Linux

subcollection: Backup

---
{:codeblock: .codeblock}
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Linux でのバックアップ・クライアントのインストール
{: #InstallinLinux}

{{site.data.keyword.backup_full}} クライアントは、OS のシェルまたは端末で一連のコマンドを実行することにより、Linux ベースのオペレーティング・システムにインストールすることができます。 この手順では、以下の Linux ベースのオペレーティング・システムのいずれかにクライアントをインストールするために必要なステップの概要を示します。

- RHEL
- CentOS
- CloudLinux

手順を完了すると、自動化されたプロセスによりエージェント・サービスが {{site.data.keyword.backup_notm}} ポータルに登録され、サービスの実行に必要なファイルがダウンロードおよびインストールされます。

[{{site.data.keyword.cloud_notm}} カタログ](https://{DomainName}/catalog){: external}または {{site.data.keyword.cloud_notm}} コンソールでサーバーを注文した時に {{site.data.keyword.backup_notm}} を購入した場合、ソフトウェアは自動的にインストールされます。 本書で説明する手順を使用する必要はありません。
{:tip}

{{site.data.keyword.cloud_notm}} コンソールでアップグレードとして {{site.data.keyword.backup_notm}} を購入した場合は、以下のステップに従ってソフトウェアをインストールしてください。

## ターゲット・デバイス・サーバーへのログイン
{: #logintargetLin}

1. [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}){: external}にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。
2. メインメニューから**「デバイス」**>**「デバイス・リスト」**を選択して使用可能なサーバー・デバイスのリストを表示します。
3. {{site.data.keyword.backup_notm}} サービスの購入対象であるデバイスを検索し、そのパブリック IP アドレスをメモします。
  - この IP アドレスは、UNIX または Linux のコマンド・ラインからデバイスにログインするときに使用します。 ステップ 5 に示すコマンドでは、<publicIpAddress> を実際のパブリック IP アドレスに置き換えてください。
4. 右向きの矢印をクリックし、デバイスの詳細情報 (ユーザー名、パスワードなど) を表示します。
  - パスワードが表示されない場合は、**「パスワードの表示 (Show Password)」**をクリックするとパスワードを表示できます。 ユーザー名とパスワードは、次のステップでテスト・デバイスにログインする際に使用します。 `<user name>` を実際のユーザー名に置き換えます。
5. UNIX または Linux のコマンド・ラインから次のコマンドを入力して、ターゲット・デバイスにログインします。
   ```
   ssh <user name>@<publicIpAddress>
   ```
   {: pre}

   これまでにこのユーザー名を使用してこのサーバーにログインしたことがない場合は、ホストの真正性に関するメッセージが表示されます。 また、続行するかどうかの確認を求められます。 **yes** で応答して続行します。
   {:note}

6. このサーバーにアクセスするための SSH 鍵を設定していない場合は、パスワードの入力が求められます。

## インストールの準備としての OS の更新 (RHEL のみ)

このステップは RHEL の場合に必要ですが、その他の Linux ディストリビューションではオプションです。
{:tip}

- サーバー・プロンプトで以下のコマンドを実行します。
  ```
  yum update
  ```
  {: pre}

  プロンプトが出されたら、ダウンロード・サイズに問題がないことを確認します。 更新が進行して終了すると、「完了」のメッセージが表示されます。

## インストール・スクリプトの取得

- サーバー・プロンプトで以下のコマンドを実行します。
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}

## インストール・スクリプトの実行

1. サーバー・プロンプトで以下のコマンドを実行します。
   ```
   sh ./evault_manual.sh
   ```
   {: pre}

2. {{site.data.keyword.backup_notm}} ポータルのユーザー名とパスワードを入力します。

   {{site.data.keyword.backup_notm}} ユーザー名とパスワードの表示について詳しくは、[バックアップ・サービス入門](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)を参照してください。
   {:tip}

3. ユーザー名とパスワードの入力後は、入力を必要とするものはありません。 インストールの進行に伴い画面に表示されるプロンプトは、無視して問題ありません。

   これらのプロンプトを生成しているのは、`evault_manual.sh` スクリプトによって開始されるサブスクリプトです。 これらのプロンプトの入力は、`evault_manual.sh` スクリプトによって提供されます。
   {:note}

4. 以下のメッセージが表示されると、インストールは完了です。

   ```
   Starting VVAgent: [  OK  ]
   Starting buagent: [  OK  ]
   ```
   {: codeblock}

## インストールが成功したかどうかの確認

1. インストールの出力に「Registered to The Portal」というメッセージが表示されることを確認します。 確認するには、画面でこのメッセージを探すか、以下のコマンドの出力を調べます。
   ```
   grep 'Registered'  /opt/BUAgent/Install.log
   ```
   {: pre}

2. 以下のコマンドを実行し、出力を監視します。
   ```
   service vvagent status
   ```
   {: pre}

   以下のメッセージが表示されます。
   ```
   VVAgent is running (PID xxxxx).
   buagent is running (PID xxxxx).
   ```
   {: codeblock}

  `xxxxx` で表されるプロセス ID は、インストールごとに異なります。
  {:tip}

**次のステップ**

{{site.data.keyword.backup_notm}} ポータルにログインし、バックアップ・エージェントを構成および管理します。 詳しくは、[入門チュートリアル](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)および [Linux での単純なファイル・レベルのバックアップの構成](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup)を参照してください。

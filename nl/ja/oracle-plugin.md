---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, oracle, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Oracle プラグインについて
{: #Oracleplugin}

Oracle プラグインはアドオンで、Windows エージェントまたは Linux エージェントとともに Oracle データベース・ホスト上にインストールされます。 {{site.data.keyword.backup_notm}} ポータルを使用して、ジョブの構成、セキュアなリモート・ボールトへの Oracle データベースのバックアップ、および Oracle データベースのリストアを行うことができます。 Oracle プラグインは、既存のアーキテクチャーに統合されます。

## 提供されている機能
{: #Oraclecapabilities}

- Oracle データベースのバックアップおよびリカバリーのサポート。
- Oracle プラグインでは、オンライン・データベース・インスタンス全体の ARCHIVELOG ベースの非 RMAN バックアップが提供されます。 すべての非一時表スペースおよびインスタンス・パラメーター・ファイルは、自動的にバックアップされます。 Oracle では、データベース・アクティビティーが少ない期間にバックアップを実行することを推奨しています。
- ユーザー管理の通常の Oracle リカバリー・メカニズムによって、データベース全体およびデータベースの一部がリストアされます。

## 制限
{: #Oraclelimitations}
- ローカル・データベース、単一インスタンス・データベース、ディスク・ベース・データベースのみがバックアップされます。
- データベース・クラスターはバックアップされません。
- ロー・デバイスはバックアップされません。
- リモート・データベースはバックアップされません。
- データベースは ARCHIVELOG モードで実行する必要があり、このような状況でバックアップが構成されている場合、ユーザーには SYSDBA 特権が必要です。
- データベース・パスワードは、スクリプト・ベースの方式によってセキュリティーを強化するために暗号化されます。

## Windows 用プラグインのインストール
{: #installOracleWin}

Windows 用の Oracle プラグインは、32 ビットまたは 64 ビットの Windows エージェントとともにインストールされます。 プラグインをインストールするには、エージェント・インストール・キットを実行します。 プラグインが、**「カスタム・セットアップ (Custom Setup)」**ページにオプションとして表示されます。 詳しくは、[Windows での {{site.data.keyword.backup_notm}} クライアントのインストール](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)を参照してください。

プラグインをインストールする前に、`services.msc` で両方の {{site.data.keyword.backup_notm}} サービスを停止します。
{:tip}

1. `c:\installs\evault` フォルダーを参照し、より新しい改訂番号の .exe ファイルを実行します。
2. 言語画面で、**「OK」**をクリックします。
3. 初期画面で、**「次へ」**をクリックします。
4. **「インストールの変更 (Modify installation)」**を選択して、**「次へ」**をクリックします。
5. **「未変更のままにする (Leave Unchanged)」**を選択して、**「次へ」**をクリックします。
6. カスタム・セットアップ画面で、購入した各プラグインを選択し、**「この機能のインストール先 (This feature will be installed on...)」**を選択して、**「次へ」**をクリックします。
7. **「現在の登録を保持する (Keep my current registration)」**を選択し、**「次へ」**をクリックします。
8. **「インストール (Install)」**をクリックします。
9. インストールが完了したら、両方のサービスが有効で実行中であることを確認してください。
10. {{site.data.keyword.backup_notm}} ポータルがデータベースにアクセスできるか、またはデータベースを参照できる場合、インストールは正常に完了しています。

## Linux 用プラグインのインストール
{: #installOracleLin}

Oracle プラグインは Linux エージェントに対するアドオンで、エージェントを使用してデータベース・ホスト上にインストールされます。 Linux エージェント・アプリケーションは、プラグインより前にインストールしておく必要があります。 エージェントは 32 ビットと 64 ビットのアプリケーションとして使用できます。 詳しくは、[Linux での {{site.data.keyword.backup_notm}} クライアントのインストール](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)を参照してください。

Oracle プラグインのインストール・キットは tar.gz ファイル形式です。

1. ホストで、インストール・パッケージをダウンロードします。
   ```
   http://downloads.softlayer.com/evault/Oracle-Plugin-Linux-x64-8.10.5249.tar.gz
   ```
   {: pre}

2. パッケージからファイルを抽出します。
   ```
   # cd /tmp
   # tar xvf Oracle-Plugin-Linux-x64-8.10.5249.tar
   ```
   {: pre}

3. フォルダーに移動します。
   ```
   # cd Oracle-Plugin-Linux-x64-8.10.5249.xxxx
   ```
   {: pre}

4. インストレーション・スクリプトを実行します。
   ```
   # ./install.sh
   ```
   {: pre}

5. 画面に表示されるインストールの指示に従います。

Oracle プラグインはデータベース全体のバックアップを不整合な状態で実行するため、ARCHIVELOG モードでデータベースを実行する必要があります。 DBA は、バックアップ開始前にデータベースが ARCHIVELOG モードであることを確認する必要があります。 詳しくは、「ユーザー・ガイド」を参照してください。
{:important}


## ユーザー・ガイドのダウンロード
{: #OracleUserGuide}

{{site.data.keyword.BluVPN}} を使用して {{site.data.keyword.cloud}} ネットワークに接続すると、[ダウンロード可能な {{site.data.keyword.backup_notm}} 資料](http://downloads.service.softlayer.com/evault/Documentation/){: external}からユーザーズ・ガイドをダウンロードすることができます。

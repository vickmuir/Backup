---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, Exchange, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Exchange プラグインについて
{: #Exchangeplugin}

Exchange プラグインは、Windows エージェントとともにホスト上にインストールされます。 {{site.data.keyword.backup_notm}} ポータルを使用して、ジョブの構成、セキュアなリモート・ボールトへの Exchange データベースのバックアップ、および Exchange データベースのリストアを行うことができます。 プラグインは、既存のアーキテクチャーに統合されます。

**提供されている機能**

- Microsoft Exchange データベースをバックアップおよびリストアする機能

## プラグインのインストール
{: #installExchangePlugin}

Exchange プラグインは、Windows エージェント 64 ビットのインストール時にインストールされます。 プラグインは、エージェントのインストール時にインストールすることも、あるいは後で**「変更」**を選択してインストールを再実行することでインストールすることもできます。

Microsoft Windows サーバー用のプラグインをインストールする前に、`services.msc` で両方の {{site.data.keyword.backup_notm}} サービスを停止します。
{:tip}

1. `c:\installs\{{site.data.keyword.backup_notm}}` フォルダーを参照し、より新しい改訂番号の .exe ファイルを実行します。
2. 言語画面で、**「OK」**をクリックします。
3. 初期画面で、**「次へ」**をクリックします。
4. **「インストールの変更 (Modify installation)」**を選択して、**「次へ」**をクリックします。
5. **「未変更のままにする (Leave Unchanged)」**を選択して、**「次へ」**をクリックします。
6. カスタム・セットアップ画面で、購入した各プラグインを選択します。
7. **「この機能のインストール先 (This feature will be installed on...)」**を選択して、**「次へ」**をクリックします。
8. **「現在の登録を保持する (Keep my current registration)」**を選択し、**「次へ」**をクリックします。
9. **「インストール (Install)」**をクリックします。
10. インストール後、両方のサービスが有効で実行中であることを確認してください。
11. {{site.data.keyword.backup_notm}} ポータルがデータベースにアクセスできるか、またはデータベースを参照できる場合、インストールは正常に完了しています。

## ユーザー・ガイドのダウンロード
{: #ExchangeUserGuide}

{{site.data.keyword.BluVPN}} を使用して {{site.data.keyword.cloud}} ネットワークに接続すると、[ダウンロード可能な {{site.data.keyword.backup_notm}} 資料](http://downloads.service.softlayer.com/evault/Documentation/){: external}からユーザーズ・ガイドにアクセスしてダウンロードすることができます。 このガイドでは、Exchange プラグインを使用して Microsoft Exchange データベースをバックアップおよびリストアする方法について説明しています。 また、このガイドでは DR バックアップ・セーフセットを共有する方法についても説明します。 DR バックアップ・セーフセットでは、Granular Restore for Microsoft Exchange アプリケーションを使用して、特定のメールボックス、メッセージ、または他のオブジェクトを .pst ファイルにリストアできます。

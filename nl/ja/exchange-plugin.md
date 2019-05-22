---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, Exchange, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Exchange プラグインのインストール
{: #Exchangeplugin}

Exchange プラグインは、Windows エージェントとともにホスト上にインストールされます。 {{site.data.keyword.backup_notm}} ポータルを使用して、ジョブの構成、セキュアなリモート・ボールトへの Exchange データベースのバックアップ、および Exchange データベースのリストアを行うことができます。 プラグインは、既存のアーキテクチャーに統合されます。

**提供されている機能**

- Microsoft Exchange データベースをバックアップおよびリストアする機能

## プラグインの注文
{: #orderingExchangePlugin}

1. [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}){: external} にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。<br/>
   あるいは、[{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external} にログインします。
2. **「ストレージ」**>**「バックアップ」**をクリックして、バックアップ・サービスを備えたサーバーを表示します。
3. アカウントを選択して、**「プラグインの注文」**をクリックします。
4. **「{{site.data.keyword.backup_notm}} プラグイン - Exchange」**を選択し、**「続行」**をクリックします。
5. 割引コードがある場合は入力し、**「再計算」**をクリックします。
6. 更新された料金が表示されます。 注文を確認します。
7. サード・パーティー・サービス契約を読んで同意することを示すため、このボックスにチェック・マークを付けます。
8. **「注文」**をクリックします。

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

{{site.data.keyword.BluVPN}} を使用して {{site.data.keyword.BluSoftlayer_full}} ネットワークに接続すると、[ダウンロード可能な {{site.data.keyword.backup_notm}} 資料](http://downloads.service.softlayer.com/evault/Documentation/){: external} からユーザーズ・ガイドにアクセスしてダウンロードすることができます。 このガイドでは、Exchange プラグインを使用して Microsoft Exchange データベースをバックアップおよびリストアする方法について説明しています。 また、このガイドでは DR バックアップ・セーフセットを共有する方法についても説明します。 DR バックアップ・セーフセットでは、Granular Restore for Microsoft Exchange アプリケーションを使用して、特定のメールボックス、メッセージ、または他のオブジェクトを .pst ファイルにリストアできます。

---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# ベアメタル・リストア・プラグインについて
{: #BMRplugin}

ベアメタル・リストアは災害復旧ソリューションです。 BMR では、オペレーティング・システムやハードウェアの障害などの災害が発生した場合に、ベアメタル状態からサーバーをリストアできます。 BMR により、{{site.data.keyword.cloud}} で管理される安全で保護された場所からシステム・イメージを迅速にリストアできます。

BMR は、物理サーバー上の Windows 専用の製品です。 仮想サーバーには使用できません。 Linux ディストリビューション用のベアメタルのリストアはサポートされていません。 {:important}

## 提供されている機能
{: #BMRcapabilities}

- 選択したポイント・イン・タイムにシステムをリストアします。
- イメージまたはファイル・ベース・バックアップからシステムをリストアします。
- {{site.data.keyword.backup_notm}} 上に保管されたバックアップからシステムをリストアします。
- ブート可能システムなしでデータをリストアするために使用できるリカバリー・トランザクションを開始します。

## BMR プラグインのインストール
{: #installingBMR}

プラグインは、Windows エージェントのインストール時にインストールされます。 プラグインは、エージェントのインストール時にインストールすることも、あるいは後で**「変更」**を選択してインストールを再実行することでインストールすることもできます。

## BMR バックアップ・ジョブの構成
{: #configBMRplugin}

詳しくは、[BMR バックアップ・ジョブの構成](/docs/infrastructure/Backup?topic=Backup-configureBMR)を参照してください。

## BMR システム・ボリューム・イメージのリストア
{: #restoringBMimage}
詳細については、[BMR システム・ボリューム・イメージのリストア](/docs/infrastructure/Backup?topic=Backup-restoreBMR) を参照してください。

## ユーザー・ガイドのダウンロード
{: #BMRUserGuide}

{{site.data.keyword.BluVPN}} を使用して {{site.data.keyword.cloud}} ネットワークに接続すると、[ダウンロード可能な {{site.data.keyword.backup_notm}} 資料](http://downloads.service.softlayer.com/evault/Documentation/){: external}からユーザーズ・ガイドにアクセスしてダウンロードすることができます。

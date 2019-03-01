---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# ベアメタル・リストア・プラグインのインストール
{: #BMRplugin}

BMR は、Microsoft Windows 向け災害復旧ソリューションです。 BMR では、オペレーティング・システムやハードウェアの障害などの災害が発生した場合に、ベアメタル状態からサーバーをリストアできます。 BMR により、{{site.data.keyword.BluSoftlayer_full}} で管理される安全で保護された場所からシステム・イメージを迅速にリストアできます。

BMR は、物理サーバー上の Microsoft Windows 専用の製品です。 仮想サーバーには使用できません。 Linux ディストリビューション用のベアメタルのリストアはサポートされていません。 BMR はバックアップ・エージェント 8.30 以前のバージョンでのみサポートされます。 (2018 年 6 月 30 日)。
{:important}

**提供されている機能**

- 選択したポイント・イン・タイムにシステムをリストアします。
- イメージまたはファイル・ベース・バックアップからシステムをリストアします。
- {{site.data.keyword.backup_notm}} 上に保管されたバックアップからシステムをリストアします。
- ブート可能システムなしでデータをリストアするために使用できる、起動可能なリカバリー・トランザクションです。

## プラグインの注文
{: #orderingBMR}

1. [{{site.data.keyword.cloud_notm}} コンソール ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}){:new_window} にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。 <br/>
   あるいは、[{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} にログインします。
2. **「ストレージ」**>**「バックアップ」**をクリックして、バックアップ・サービスを備えたサーバーを表示します。
3. アカウントを選択して、**「プラグインの注文」**をクリックします。
4. **{{site.data.keyword.backup_notm}}「プラグイン - BMR (ベアメタルのリストア) (EVault plug-in - BMR (Bare Metal Restore))」**を選択して、**「続行」**をクリックします。
5. 割引コードがある場合は入力し、**「再計算」**をクリックします。
6. 更新された料金が表示されます。 注文を確認します。
7. サード・パーティー・サービス契約を読んで同意したことを示すため、このボックスにチェック・マークを付けます。
8. **「注文」**をクリックします。

## ユーザー・ガイドのダウンロード
{: #BMRUserGuide}

{{site.data.keyword.BluVPN}} を使用して {{site.data.keyword.BluSoftlayer_full}} ネットワークに接続すると、[ダウンロード可能な {{site.data.keyword.backup_notm}} 資料 ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} からユーザーズ・ガイドにアクセスしてダウンロードすることができます。

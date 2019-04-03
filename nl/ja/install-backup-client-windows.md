---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, install agent, Windows

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Windows でのバックアップ・クライアントのインストール
{: #InstallinWindows}

Windows で {{site.data.keyword.backup_full}} クライアントをインストールするには、{{site.data.keyword.backup_notm}} サービス用に指定されているサーバーで一連の対話式作業を行います。

Windows 2016 サーバーでのバックアップについて詳しくは、[Windows 2016 での {{site.data.keyword.backup_notm}} の構成](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016)を参照してください。
{:tip}

## ターゲット・デバイス・サーバーへのログイン
{: #logintargetWin}

1. [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}/catalog){:new_window}にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。 <br/>
   あるいは、[{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} にログインします。
2. メインメニューから**「デバイス」**>**「デバイス・リスト」**を選択して使用可能なサーバーのリストを表示します。
3. {{site.data.keyword.backup_notm}} サービスの購入対象であるデバイスを検索し、そのパブリック IP アドレスをメモします。
4. 右向き矢印をクリックし、展開してデバイスに関する詳細情報 (ユーザー名、パスワードなど) を表示します。 パスワードが表示されない場合は、**「パスワードの表示 (Show Password)」**をクリックすると表示されます。
5. リモート・デスクトップ接続を使用してターゲット・デバイスにログインします。

## バックアップ・クライアントのダウンロード

1. ターゲット・サーバーでブラウザー・セッションを開き、以下の URL を入力して {{site.data.keyword.backup_notm}} クライアントの実行可能ファイルをダウンロードします。 <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}

2. ダウンロードしたファイルをダブルクリックします。
3. **「実行 (Run)」**をクリックします。


## バックアップ・エージェントのインストールおよび登録

1. ネットワーク・アドレスを入力します。 <br />
  ```
  https://ev-webcc01.service.softlayer.com
  ```
  {: pre}

2. **「ユーザー名」**フィールドに、ユーザー名を入力します。
3. **「パスワード」**フィールドに、パスワードを入力します。
6. **「次へ」**をクリックします。
7. **「インストール (Install)」**をクリックしてインストールを完了します。

## バックアップ・エージェントの構成

{{site.data.keyword.backup_notm}} ポータルにログインし、バックアップ・エージェントを構成および管理します。 詳しくは、[入門チュートリアル](/docs/infrastructure/Backup?topic=Backup-gettingstarted#gettingstarted)を参照してください。

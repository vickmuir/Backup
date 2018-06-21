---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# EVault Oracle プラグインのインストール

Oracle プラグインは、Windows エージェントとともに Oracle データベース・ホスト上にインストールされます。WebCC ポータルを使用して、ジョブの構成、Oracle データベースのセキュアなリモート・ボールトへのバックアップ、および Oracle データベースのリストアを行うことができます。Oracle プラグインは、既存のアーキテクチャーに統合されます。

## 提供されている機能

- Oracle データベースのバックアップおよびリカバリーのサポート。
- Oracle プラグインでは、オンライン・データベース・インスタンス全体の ARCHIVELOG ベースの非 RMAN バックアップが提供されます。すべての非一時表スペースおよびインスタンス・パラメーター・ファイルは、自動的にバックアップされます。Oracle では、データベース・アクティビティーが少ない期間にバックアップを実行することを推奨しています。
- ユーザー管理の通常の Oracle リカバリー・メカニズムによって、データベース全体およびデータベースの一部がリストアされます。

## プラグインの注文

1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}にログインします。
2. **「ストレージ」** > **「バックアップ」**をクリックします。
3. EVault アカウントを選択して、**「プラグインの注文」**をクリックします。
4. **「EVault プラグイン - Oracle (EVault Plugin - Oracle)」**を選択して、**「続行」**をクリックします。
5. 割引コードがある場合は入力し、**「再計算」**をクリックします。
6. 更新された料金が表示されます。注文を確認します。
7. マスター・サービス契約を確認したことを示すボックスにチェック・マークを付けて、サード・パーティーのソフトウェアご利用条件に同意します。 
8. **「注文」**をクリックします。

## Oracle プラグインのインストール

Windows 用の Oracle プラグインは、32 ビットまたは 64 ビットの Windows エージェントとともにインストールされます。Windows 用の Oracle プラグインをインストールするには、エージェント・インストール・キットを実行します。Oracle プラグインが、**「カスタム・セットアップ (Custom Setup)」**ページにオプションとして表示されます。

**注**: Microsoft Windows サーバー用のプラグインをインストールする前に、`services.msc` で両方の EVault サービスを停止します。  

1. `c:\installs\evault` フォルダーを参照し、より新しい改訂番号の .exe ファイルを実行します。
2. 言語画面で**「OK」**をクリックします。
3. 初期画面で**「次へ」**をクリックします。
4. **「インストールの変更 (Modify installation)」**を選択して、**「次へ」**をクリックします。
5. **「未変更のままにする (Leave Unchanged)」**を選択して、**「次へ」**をクリックします。
6. カスタム・セットアップ画面で、購入した各プラグインを選択し、**「この機能のインストール先 (This feature will be installed on...)」**を選択して、**「次へ」**をクリックします。
7. **「現在の登録を保持する (Keep my current registration)」**ラジオ・ボタンを選択して、**「次へ」**をクリックします。
8. **「インストール (Install)」**をクリックします。
9. インストール後、両方のサービスが有効で実行中であることを確認してください。
10. WebCC がデータベースにアクセス可能 (データベースを表示可能) である場合、インストールは成功です。 

## ユーザー・ガイド

{{site.data.keyword.BluVPN}} を使用して {{site.data.keyword.BluSoftlayer_full}} ネットワークに接続すると、[ダウンロード可能な EVault 資料](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}から、EVault Agent v8.0 for Microsoft Windows - Oracle Plug-in Guide.pdf をダウンロードできます。

## よくある質問

### Oracle プラグインの制限は何ですか。
- ローカル・データベース、単一インスタンス・データベース、ディスク・ベース・データベースのみがバックアップされます。
- データベース・クラスターはバックアップされません。
- ロー・デバイスはバックアップされません。
- リモート・データベースはバックアップされません。
- データベースは ARCHIVELOG モードで実行する必要があり、このような状況でバックアップが構成されている場合、ユーザーには SYSDBA 特権が必要です。
- データベース・パスワードは、スクリプト・ベースの方式によってセキュリティーを強化するために暗号化されます。
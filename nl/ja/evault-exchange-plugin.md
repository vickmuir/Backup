---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# EVault Exchange プラグインのインストール

Exchange プラグインは、Windows エージェントとともにホスト上にインストールされます。WebCC ポータルを使用して、ジョブの構成、Oracle データベースのセキュアなリモート・ボールトへのバックアップ、および Oracle データベースのリストアを行うことができます。Oracle プラグインは、既存のアーキテクチャーに統合されます。

## 提供されている機能

- Microsoft Exchange データベースをバックアップおよびリストアする機能

## プラグインの注文

1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}にログインします。
2. **「ストレージ」** > **「バックアップ」**をクリックします。
3. EVault アカウントを選択して、**「プラグインの注文」**をクリックします。
4. **「EVault プラグイン - Exchange (EVault Plugin - Exchange)」**を選択して、**「続行」**をクリックします。
5. 割引コードがある場合は入力し、**「再計算」**をクリックします。
6. 更新された料金が表示されます。注文を確認します。
7. マスター・サービス契約を確認したことを示すボックスにチェック・マークを付けて、サード・パーティーのソフトウェアご利用条件に同意します。 
8. **「注文」**をクリックします。

## Exchange プラグインのインストール

Exchange プラグインは、Windows エージェント 64 ビットのインストール時にインストールされます。プラグインは、エージェントのインストール時にインストールすることも、変更の選択肢を使用してインストールを再実行することで後からインストールすることもできます。

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

{{site.data.keyword.BluVPN}} を使用して {{site.data.keyword.BluSoftlayer_full}} ネットワークに接続すると、[ダウンロード可能な EVault 資料](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}から EVault Agent v8.0 for Microsoft Windows (64-bit) - Exchange Plug-in Guide.pdf をダウンロードできます。このガイドでは、Exchange プラグインを使用して Microsoft Exchange データベースをバックアップおよびリストアする方法について説明しています。また、このガイドでは、Granular Restore for Microsoft Exchange アプリケーションを使用して特定のメールボックス、メッセージ、またはその他のオブジェクトを .pst ファイルにリストアできるように、DR バックアップのセーフセットを共有する方法についても説明しています。



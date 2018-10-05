---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-27"

---
{:new_window: target="_blank"}

# EVault Exchange プラグインのインストール

Exchange プラグインは、Windows エージェントとともにホスト上にインストールされます。 WebCC ポータルを使用して、ジョブの構成、セキュアなリモート・ボールトへの Oracle データベースのバックアップ、および Oracle データベースのリストアを行うことができます。 Oracle プラグインは、既存のアーキテクチャーに統合されます。

**提供されている機能**

- Microsoft Exchange データベースをバックアップおよびリストアする機能

## プラグインの注文

1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}にログインします。
2. **「ストレージ」** > **「バックアップ」**をクリックします。
3. EVault アカウントを選択して、**「プラグインの注文」**をクリックします。
4. **「EVault プラグイン - Exchange (EVault plug-in - Exchange)」**を選択して、**「続行」**をクリックします。
5. 割引コードがある場合は入力し、**「再計算」**をクリックします。
6. 更新された料金が表示されます。 注文を確認します。
7. サード・パーティー・サービス契約を読んで同意することを示すため、このボックスにチェック・マークを付けます。 
8. **「注文」**をクリックします。

## Exchange プラグインのインストール

Exchange プラグインは、Windows エージェント 64 ビットのインストール時にインストールされます。 プラグインは、エージェントのインストール時にインストールすることも、あるいは後で**「変更」**を選択してインストールを再実行することでインストールすることもできます。

**注**: Microsoft Windows サーバー用のプラグインをインストールする前に、`services.msc` で両方の EVault サービスを停止します。  

1. `c:\installs\evault` フォルダーを参照し、より新しい改訂番号の .exe ファイルを実行します。
2. 言語画面で、**「OK」**をクリックします。
3. 初期画面で、**「次へ」**をクリックします。
4. **「インストールの変更 (Modify installation)」**を選択して、**「次へ」**をクリックします。
5. **「未変更のままにする (Leave Unchanged)」**を選択して、**「次へ」**をクリックします。
6. カスタム・セットアップ画面で、購入した各プラグインを選択します。 
7. **「この機能のインストール先 (This feature will be installed on...)」**を選択して、**「次へ」**をクリックします。
8. **「現在の登録を保持する (Keep my current registration)」**を選択し、**「次へ」**をクリックします。
9. **「インストール (Install)」**をクリックします。
10. インストール後、両方のサービスが有効で実行中であることを確認してください。
11. WebCC がデータベースにアクセスできる (つまり、WebCC にデータベースが表示される) 場合、インストールは正常に完了しています。 

## ユーザー・ガイドのダウンロード

{{site.data.keyword.BluVPN}} を使用して {{site.data.keyword.BluSoftlayer_full}} ネットワークに接続すると、[ダウンロード可能な EVault 資料](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}から EVault Agent v8.0 for Microsoft Windows (64-bit) - Exchange plug-in Guide.pdf をダウンロードできます。 このガイドでは、Exchange プラグインを使用して Microsoft Exchange データベースをバックアップおよびリストアする方法について説明しています。 また、このガイドでは DR バックアップ・セーフセットを共有する方法についても説明します。 DR バックアップ・セーフセットでは、Granular Restore for Microsoft Exchange アプリケーションを使用して、特定のメールボックス、メッセージ、またはその他のオブジェクトを .pst ファイルにリストアできます。


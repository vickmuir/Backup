---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-05"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Windows 2016 での EVault の構成

現在、EVault WebCC は Windows 2016 では正式にはサポートされていません。Windows 2016 で実行されているサーバーは、Windows Central Control ソフトウェアを使用する必要があります。

## EVault バックアップ・エージェントのインストール

1. ターゲット・サーバーでブラウザー・セッションを開き、以下の URL を入力して実行可能ファイルをダウンロードします。
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
2. ダウンロードしたファイルをダブルクリックし、表示されるポップアップ・ボックスで**「実行 (Run)」**をクリックします。
3. インストールの言語を選択し、**「OK」**をクリックします。
4. 「セットアップ・タイプ (Setup Type)」で**「標準 (Typical)」**を選択します。**「次へ」**をクリックします。
5. 「ポータルにエージェントを登録 (Register Agent with Portal)」画面で、**「登録をスキップ (Skip Registration)」**を選択します。 
6. **「次へ」**をクリックしてから、**「完了」**をクリックします。

## EVault ソフトウェア CentralControl のインストール

1. ターゲット・サーバーでブラウザー・セッションを開き、以下の URL を入力して実行可能ファイルをダウンロードします。

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. ダウンロードしたファイルをダブルクリックし、表示されるポップアップ・ボックスで**「実行 (Run)」**をクリックします。
3. 「標準 (Typrical)」セットアップのインストール・ステップに従います。

## CentralControl の構成

このタスクは、EVault バックアップ・サービス用に指定されているサーバーにログイン中に、一連の対話を介して完了します。

1. RDP を介してサーバーをリモート制御します。
2. CentralControl を開始します。
3. ワークスペースで**「エージェント」**を右クリックし、**「エージェント構成 (Agent Configuration)」**を選択します。
4. **「新規」**をクリックします。
5. **「新規コンピューターとして登録 (Register as a new computer)」**を選択し、**「次へ」**をクリックします。
6. ネットワーク・アドレスを入力して**「追加」**をクリックしてから、**「次へ」**をクリックします。
7. 新規ポート値を入力し、**「追加」**、**「次へ」**の順にクリックします。
8. 「接続設定 (Connection Settings)」画面で、目的の秒数または分数を入力します。 
9. 「認証」画面で資格情報を入力し、**「次へ」**をクリックします。
10. 「登録済みコンピューター (Registered Computers)」ウィンドウに、サーバーのホスト名が表示されます。**「次へ」**をクリックします。
11.	「ボールト構成ウィザード (Vault Configuration Wizard)」による情報収集が終了したら、**「完了」**をクリックして登録を完了します。



---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, reregister

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# ボールトの再登録
{: #reregister}

このタスクは、サーバーのオペレーティング・システムの再ロード後に最もよく利用されます。 これらのステップは、[1 つのサーバーのバックアップを使用して、別のサーバー上にデータをリストアする場合](/docs/infrastructure/Backup?topic=Backup-restorefromotherVSI)に使用することもできます。
{:tip}

1. {{site.data.keyword.backup_notm}} ポータルを開始してログインします。 詳しくは、[入門チュートリアル](/docs/infrastructure/Backup?topic=Backup-gettingstarted#getting-started)を参照してください。

   {{site.data.keyword.backup_notm}} ポータルには、{{site.data.keyword.BluVPN}} を介してのみアクセスできることを忘れないでください。
   {:tip}
2. 左側にある**「すべてのエージェント」**をクリックします。
3. 右上で、**「編集」**をマウスオーバーします。
4. **「ボールト設定 (Vault Settings)」**を選択します。
5. **「再登録 (Reregister)」**をクリックします。
6. フォームに入力します。
  - ボールト名 (Vault name)
  - ボールト・アドレス (Vault address)
  - アカウント

    「アカウント」は [{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} の「アカウント名」と同等です。 通常、「SLE[account ID]」のようになります。
    {:tip}
  - ユーザー名
  - パスワード
7. **「コンピューターのロード (Load Computers)」**をクリックして、ロードするコンピューターを選択します。
8. **「変更の保存」**をクリックします。
9. Web サイトを最新表示して、以前のバックアップ・ジョブをリストアします。
10. 各バックアップ・ジョブを同期して、セーフセットの履歴をリストアします。
11. 暗号化パスワードを使用してバックアップ・ジョブが作成されている場合、データをリストしたり、バックアップを続行したりするには、暗号化パスワードを入力する必要があります。
12. **「閉じる」**をクリックします。

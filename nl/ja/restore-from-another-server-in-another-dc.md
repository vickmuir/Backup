---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 異なるデータ・センターの VSI 間でのデータのリストア
{: #restoreVSIotherlocation}

別のサーバーからデータをリストアすることが必要な場合があります。 この手順は、OS 以外のファイルのファイル・レベルのリストアに適用されますｓ。 システム・イメージをリストアするには、[Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR) の手順に従ってください。

このプロセスには、1 番目のサーバーのボールトの場所にアクセスするために 2 番目のサーバーにバックアップ・エージェントを再登録する作業と、**「別のコンピューターからのリストア (Restore from another Computer)」**の実行が伴います。

**前提条件**

- Server1 と Server2 が同じ OS を搭載していること。 クロスプラットフォーム・リストアはサポートされていません。
- Server1 と Server2 でバックアップ・エージェントが構成済みであること。 バックアップ・エージェントの構成について詳しくは、[{{site.data.keyword.backup_notm}} ポータルでのバックアップ・エージェントの構成](/docs/infrastructure/Backup?topic=Backup-gettingstarted#gettingstarted)を参照してください。
- Server1 のバックアップ・ジョブにより、Server1 のボールトの場所にバックアップが作成されていること。

競合を回避するために、両方のサーバーですべてのスケジュール済みタスクを無効にしてください。
{:important}

## Server2 の {{site.data.keyword.backup_notm}} ポータルの開始
{: #startWebCCotherDC}

{{site.data.keyword.BluSoftlayer_full}} プライベート・ネットワークにアクセスするには、{{site.data.keyword.BluVPN}} 接続を開始してください。このようにしないと {{site.data.keyword.backup_notm}} ポータル・リンクが機能しません。
{:tip}

1. [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}/){:new_window}にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。 <br/>
   あるいは、[{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} にログインします。
2. **「ストレージ」**>**「バックアップ」**をクリックして、バックアップ・サービスを備えたサーバーを表示します。
3. Server2 を選択します。 右向きの展開矢印をクリックし、{{site.data.keyword.backup_notm}} ポータル・リンクを表示します。
4. **「{{site.data.keyword.backup_notm}} ポータル・ログイン」**をクリックし、ブラウザーでポータル・クライアントを開始します。

## ボールトの再登録
{: #reregistervaultotherDC}

1. **「すべてのエージェント」**をクリックして、変更する特定のエージェントを開きます。
2. **「編集」**をクリックし、**「ボールト設定 (Vault Settings)」**を選択します。
3. **「再登録 (Reregister)」**をクリックし、Server1 を Server2 に接続します。
4. **「ボールト・プロファイルの使用 (Use a Vault Profile)」**エントリーの**「ボールトの再登録 (Re-register Vault)」**画面で、**「ボールト設定の入力 (Enter Vault Settings)」**を選択します。
5. 「ボールト名 (Vault name)」を入力します。これは Server1 のボールト名と同じにします。
6. Server1 のボールトにログインするための、Server1 の資格情報を入力します。
7. **「コンピューターのロード (Load Computers)」**をクリックします。このアクションにより、ボールトの場所に接続されているサーバーが表示されます。
8. **「変更の保存」**をクリックします。
9. プロンプトが出されたら、**「はい」**をクリックしてボールトの再登録を確認します。

## Server1 のバックアップ・ジョブの Server2 のリストア・ジョブとしての実行
{: #runbackuprestoreotherDC}

1. **「すべてのエージェント」**をクリックします。

   Server1 で定義されたジョブが Server2 の**「ジョブ」**タブにアクセス可能および同期済みとして表示されるようにするには、ページのリフレッシュが必要な場合があります。
   {:tip}
2. **「拡張」**に移動し、**「別のコンピューターからのリストア (Restore from another Computer)」**を選択します。
3. **「別のコンピューターからのリストア (Restore from another Computer)」**画面で**「追加」**をクリックします。 フィールドにデフォルト値が自動的に取り込まれるので、デフォルト値を変更します。
4. 「ボールト(Vault)」フィールドで**「ボールト設定の入力 (Enter Vault Settings)」**を選択し、Server1 のボールトの IP アドレスを入力します。 **「追加」**をクリックします。
5. 資格情報を、Server1 の資格情報に更新します。
6. **「変更の保存」**をクリックします。 この操作により、Server1 のボールトに接続します。
7. **「別のコンピューターからのリストア (Restore from another Computer)」**画面に戻り、「コンピューター (Computer)」フィールドと「ジョブ (Job)」フィールドを更新します。
  - コンピューター (Computer) - リストア元のバックアップ・コンピューターとして Server1 を選択します。
  - ジョブ - Server1 のバックアップ・ジョブを選択します。
8. **「次へ」**をクリックし、別のデータ・センターにある Server2 へのリストア・プロセスを開始します。
9. プロンプトでバックアップ・パスワードを入力し、**「次へ」**をクリックします。
10. 正しいバックアップ・ジョブが選択されていることを確認し、**「次へ」**をクリックします。 これで、Server2 でリストア・ジョブが構成されました。
11. 新たに構成したジョブを選択し、**「リストアの実行 (Run Restore)」**をクリックします。
12. リストアするファイルを選択します。
13. 正符号をクリックして、ファイル選択を展開します。
14. Server1 から Server2 にリストアする個々のファイルまたはフォルダーのチェック・ボックスをクリックします。 次に**「追加 (Include)」**をクリックします。
15. 右側の「バックアップ・セット (Backup Set)」ウィンドウにファイルが取り込まれます。 **「次へ」**をクリックします。
16. データの選択が完了したら、オプションの選択に進みます。
    - **「元の場所にリストアする (Restore to the original location)」**を選択します。
    - **「既存のファイルを上書きする (Overwrite existing files)」**を選択します。
17. **「リストアの実行 (Run Restore)」**をクリックします。 「プロセスの詳細 (Process Details)」ウィンドウに、実行中のバックアップ・ジョブのステータスが表示されます。 バックアップが完了したら、**「閉じる」**をクリックします。


## リストアの確認
{: #verifyrestoreotherDC}

1. SSH 経由で Server2 のルートに接続します。
2. ファイルおよびすべてのディレクトリー・エントリーを長形式でリストします。
  ```
  ls -la
  ```
  {: pre}

3. 出力を比較します。

## 通常のバックアップ・スケジュールの再開
{: #resumescheduleotherCD}

1. リストアが完了したら、データのリストア元である server1 の登録情報を削除します。
2. 現在の server2 の登録を入力し、スケジュール・タスクを有効にします。

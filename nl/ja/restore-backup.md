---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, restore

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# バックアップからのリストア
{: #simplerestore}

{{site.data.keyword.backup_full}} でファイル・リストアを実行するには、以下の手順に従います。 システム・イメージをリストアするには、[Windows BMR](https://cloud.ibm.com/docs/infrastructure/Backup?topic=Backup-restoreBMR#restoreBMR) の手順に従ってください。

## {{site.data.keyword.backup_notm}} ポータルの開始
{: #startWebCCsimple}

{{site.data.keyword.BluSoftlayer_full}} プライベート・ネットワークにアクセスするには、{{site.data.keyword.BluVPN}} 接続を開始してください。 開始しないと、{{site.data.keyword.backup_notm}} ポータル・リンクが機能しません。
{:important}

1. [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}/){:new_window}にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。 <br/>
   あるいは、[{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} にログインします。
2. **「ストレージ」**>**「バックアップ」**をクリックして、バックアップ・サービスを備えたサーバーを表示します。
3. リストア対象のファイルが存在するサーバーを選択します。 矢印をクリックし、{{site.data.keyword.backup_notm}} ポータル・リンクを表示します。
4. **「IBM Cloud バックアップ・ポータル ({{site.data.keyword.backup_notm}} portal)」**をクリックし、ブラウザーで {{site.data.keyword.backup_notm}}・ポータル・クライアントを開始します。

## データのリストア

1. 左のナビゲーション・ペインで**「すべてのエージェント」**をクリックします。
2. 「エージェント」をクリックし、ジョブを表示します。
3. 必要なデータが格納されているジョブをクリックします。
4. **「リストアの実行 (Run Restore)」**をクリックします。
5. リストアのソースを選択します。
6. バックアップ・バージョンを選択します。
7. 暗号化パスワードを入力します。
8. **「次へ」**をクリックして先に進みます。
9. 含めるファイルとディレクトリーの横にあるチェック・ボックスを選択します。 次に、**「含める (Include)」**をクリックして選択項目を保存します。
10. 表示されるウィンドウを使用して、選択内容をさらにフィルタリングできます。選択内容をそのまま使用する場合は**「OK」**をクリックします。
ファイルとディレクトリーを選択して含めた後は、データ・ファイル・ペインでそれ以上ファイルを選択できなくなります。 それらは、右側のバックアップ・セット・ペインに表示されます。

   ステップ 10 を繰り返して、ファイルを追加するか、以前に追加したファイルを (**「除外 (Exclude)」**を使用して) 削除することができます。 また、**「削除」**を使用して**「バックアップ・セット (Backup Set)」**ペインから任意の行アイテムを削除することもできます。
   {:tip}

11. バックアップ・セットを希望どおりに構成したら、**「次へ」**をクリックして続行します。
12. 次のペインではデフォルト設定のままにするか、好みに応じてリストアをカスタマイズします。 次に、**「リストアの実行 (Run Restore)」**をクリックします。
13. **「プロセスの詳細 (Process Details)」**画面で、「状況」に**「リストア完了 (Restore completed)」**と表示された場合、ファイルがリストアされています。

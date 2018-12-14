---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Windows 版バックアップ・ソフトウェア・エージェントのアップグレード

Windows サーバーで {{site.data.keyword.backup_notm}} エージェントをアップグレードするには、次の手順を使用します。

1. RDP を介して、{{site.data.keyword.backup_notm}} のアップグレードが必要な {{site.data.keyword.BluSoftlayer_full}} サーバーをリモート制御します。
2. ブラウザーを開き、次のアドレスに移動します。
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. 必要なファイルをクリックします。 (例: Agent-Windows-x64-6-72-1072a.exe)

   バージョン番号はファイル名に含まれます。 最新のものを選択してください。 <br/>32 ビットと 64 ビットのそれぞれ別個のインストーラーがあります。64 ビット・オペレーティング・システムをご使用の場合は、名前に x64 が含まれるファイルをダウンロードしてください。
   {:tip}
4. ダウンロード画面で**「実行 (Run)」**をクリックし、ダウンロードした後もう一度「実行 (Run)」をクリックします。
5. **「はい」**をクリックして、**EVault ソフトウェア・エージェント**をアップグレードします。

   インストーラーは、ロード中にしばらく非表示になる場合があります。
   {:note}
6. **「現在の登録を保持する (Keep my current registration)」**を選択して、**「次へ」**をクリックします。
7. **「次へ」**をクリックします。 エージェントがアップグレード・プロセスを開始します。 これには数分かかることがあります。
8. 完了画面で、**「完了」**をクリックします。

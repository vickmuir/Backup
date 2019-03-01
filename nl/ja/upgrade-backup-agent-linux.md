---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Linux 版バックアップ・ソフトウェア・エージェントのアップグレード
{: #UpgradeinLinux}

最新のバックアップ・エージェントを、{{site.data.keyword.backup_notm}}・ポータルの「ダッシュボード」クイック・リンク・セクションからダウンロードできます。
{:tip}

このアップグレード・プロセスに従うと、登録を失うことなく {{site.data.keyword.backup_notm}}・エージェントをアップグレードすることができます

1. root レベルでホストにログインします。
2. 最新バージョンのエージェントをダウンロードします。
   ```
   wget -N downloads.service.softlayer.com/evault/Agent-Linux-x64-8.11.5251.tar.gz2
   ```
   {:pre}

3. ダウンロードしたファイルの内容を解凍します。

   ```
   tar -xzvf Agent-Linux-x64-8.11.5251.tar.gz3
   ```
4. 最新のインストール・ディレクトリーに移動します。
   ```
   cd Agent-Linux-x64-8.11.5251/4
   ```

5. インストレーション・スクリプトを実行します。
   ```
   ./install.sh
   ```
   {:pre}

6. 各プロンプトに応答します。言語を選択し、コンピューターを新規ホストとして登録しないように `N` を選択し、統合暗号化方式を使用してデータを暗号化するために `A` を選択します。

7. インストールに成功すると、そのことが `/opt/BUAgent/Install.log` に記録されます。

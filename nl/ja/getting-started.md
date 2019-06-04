---

copyright:
  years: 1994, 2019
lastupdated: "2019-05-14"

keywords: IBM Cloud backup, EVault, Carbonite, backup, getting started, setup, configure, run backup

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# 入門チュートリアル
{: #getting-started}

バックアップにより、デバイスの外部でデータを確実かつ安全に保存でき、紛失した場合にも保護できます。 {{site.data.keyword.backup_full}} は、{{site.data.keyword.backup_notm}} ポータル・ブラウザー・ベースの管理ユーティリティーにより管理される、エージェント・ベースの自動化されたバックアップ・システムです。 {{site.data.keyword.backup_notm}} は、{{site.data.keyword.cloud}} ネットワーク上の 1 つ以上のデータ・センターにあるサーバー間でデータをバックアップするための手段を提供します。 管理者は、フル・システムや特定のディレクトリー、あるいは個別のファイルを対象とした日次スケジュール、週次スケジュール、またはカスタム・スケジュールに従うバックアップを設定できます。 追加のプラグインを使用すると、[Microsoft Exchange](/docs/infrastructure/Backup?topic=Backup-Exchangeplugin)、[Microsoft SQL](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin)、[Oracle](/docs/infrastructure/Backup?topic=Backup-Oracleplugin#Oracleplugin)、[VMware vSphere](/docs/infrastructure/Backup?topic=Backup-VRA) などのソフトウェアとの互換性を確保でき、ユーザーは必要に応じて[ベアメタル・リストア](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin)を実行できるようになります。
{:shortdesc}

## 依頼する前に
{: #prereqs}

IBM Cloud Backup の利用は有効なライセンスが必要です。{{site.data.keyword.backup_notm}} サービスは 2 とおりの方法で購入できます。

- [サーバーの注文時におけるバックアップの購入](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingwithserver)
- [アップグレードとしてのバックアップの購入](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingasupgrade)

ご注文と価格について詳しくは、 [{{site.data.keyword.backup_notm}} のプロビジョニング](/docs/infrastructure/Backup?topic=Backup-ordering) を参照してください。

## {{site.data.keyword.backup_notm}} エージェントのインストール
{: #installagentgettingstarted}

{{site.data.keyword.backup_notm}} エージェントは以下の OS でサポートされています。

**Windows**
 - Windows Server 2016
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

ご使用の OS に適切な説明に従ってください。
- [Linux でのバックアップ・クライアントのインストール](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)
- [Windows でのバックアップ・クライアントのインストール](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)
- [Windows 2016 でのバックアップ・クライアントのインストール](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016)

## {{site.data.keyword.backup_notm}}・ポータル (旧称 WebCC) へのアクセス
{: #accessingWebCC}

{{site.data.keyword.backup_notm}} ポータルは、{{site.data.keyword.cloud}} が提供する {{site.data.keyword.backup_notm}} サービスとの対話式操作に使用されます。{{site.data.keyword.backup_notm}} ポータルは、{{site.data.keyword.cloud}} プライベート・ネットワークで実行されるブラウザー・ベースのクライアントであり、これによって、構成やリストアなどすべての {{site.data.keyword.backup_notm}} サービスを完全に制御することができます。

1. VPN 経由でプライベート・ネットワークにアクセスします。

   パブリック・ネットワーク上で {{site.data.keyword.backup_notm}} ポータルにアクセスすることはできません。 VPN 接続を最初に確立する必要があります。
   {:important}
2. [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}){: external}にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。<br/>
あるいは、[{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external} にログインします。
2. **「ストレージ」**>**「バックアップ」**をクリックして、バックアップ・サービスを備えたサーバーを表示します。
3. バックアップ対象のファイルが存在するサーバーを選択します。 右向きの展開矢印をクリックし、{{site.data.keyword.backup_notm}} ポータル・リンクを表示します。
4. **「{{site.data.keyword.backup_notm}} ポータル・ログイン」**をクリックし、ブラウザーでポータル・クライアントを開始します。

## バックアップ・エージェントとバックアップ・スケジュールの構成
{: #configureagentschedule}

{{site.data.keyword.backup_notm}} を注文し、エージェントがサーバーにインストールされた後、データのバックアップの作成を開始できます。 エージェントと保存スケジュールを構成するには、以下のステップに従ってください。

1. {{site.data.keyword.backup_notm}} ポータルにログインします。
2. **「すべてのエージェント」** > **「未構成のエージェント (Unconfigured Agents)」**をクリックします。
3. **「これは構成対象の新しいエージェントです (This is a new Agent I would like to configure)」**リンクをクリックします。 プロセスに従って以下の情報を入力します。
   1. エージェント構成 (Agent configuration) - エージェントの説明を入力し、**「次へ」**をクリックします。
   2. ジョブ・タイプの選択 (Job type selection) - ジョブ名、ジョブの説明、およびバックアップ・ソース・タイプを入力し、**「次へ」**をクリックします。
   3. 選択 (Selection) - ディレクトリーを選択し、**「包含 (Include...)」**をクリックします。
   4. オプション - パスワードを入力します。
   5. スケジュール - **「追加」**をクリックしてスケジュールを作成し、**「次へ」**をクリックします。
   6. デフォルトのボールトを選択し、**「OK」**をクリックします。
   7. **「保存」**をクリックします。
4. 保存スケジュールを作成します。
   1. **「編集」** > **「エージェント設定 (Agent Settings)」**を選択します。
   2. **「追加」**をクリックします。
   3. 保存の詳細を入力します。
   4. **「OK」**をクリックします。
   5. **「保存」**をクリックします。

      保存スキームについて詳しくは、[FAQ](/docs/infrastructure/Backup?topic=Backup-faqs#faqs) を参照してください。
      {:tip}

      アーカイブはサポートされていません。保存スキームを作成したり既存のスキームを変更したりするには、「アーカイブ (Archiving)」オプションが選択されて**いない**ことを確認してください。{:important}

## 最初のバックアップ・ジョブの実行
{: #runfirstbackup}

1. {{site.data.keyword.backup_notm}} ポータルにログインします。
2. **「すべてのエージェント」**をクリックしてから、構成したエージェントを選択します。
3. **「バックアップの実行 (Run Backup)」**をクリックします。
4. 「宛先」を確認し、保存スキームを選択します。
5. **「バックアップの開始 (Start Backup)」**をクリックします。 プロセスの稼働中、バックアップの詳細を表示できます。
6. バックアップが完了したら、**「閉じる」**をクリックします。

詳しくは、[Linux での単純なファイル・レベルのバックアップの構成](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup)を参照してください。
{:tip}

## {{site.data.keyword.backup_notm}} のストレージの詳細へのコンソールでのアクセスと表示
{: #viewingdetailsinconsole}

サービスのストレージに関する詳細は、いつでも [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}){: external}と {{site.data.keyword.slportal}}で確認できます。 確認できる詳細には、選択されている {{site.data.keyword.backup_notm}} サービスに関連付けられているパスワード、ストレージ・アドレス、および使用状況などがあります。

1. [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}){: external}にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。</br>あるいは、[{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external} にログインします。
2. **「ストレージ」**をクリックし、リストから**「バックアップ」**を選択します。
2. ストレージの詳細を確認するボールトの行の任意の位置をクリックします。 このビューでは「パスワード」は表示可能ではありません。
3. **「パスワード」**フィールドの横にある**「表示」**チェック・ボックスをクリックし、選択した {{site.data.keyword.backup_notm}} サービスのパスワードを表示します。

{{site.data.keyword.slportal}}内で {{site.data.keyword.backup_notm}} のパスワードに加える変更は、サービス自体に対して加えられます。 パスワードをリセットするには、[バックアップ・サービスのパスワードの変更](/docs/infrastructure/Backup?topic=Backup-changePassword)のステップに従ってください。
{:important}

## その他のオンライン・ヘルプの表示
{: #onlinehelp}

{{site.data.keyword.backup_notm}} ポータルのシステムは完全に文書化されており、アプリケーションのサポートには {{site.data.keyword.backup_notm}} ポータル内からアクセス可能です。 **「ヘルプ」**を表示するには、右上にある青い円の中の白い疑問符をクリックします。 左側にあるナビゲーション・バーで任意の記事やトピックをクリックすると、詳細情報が表示されます。

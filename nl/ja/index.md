---

copyright:
  years: 2014, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# {{site.data.keyword.backup_notm}} サービス入門

バックアップにより、デバイスの外部でデータを確実かつ安全に保存でき、紛失した場合にも保護できます。 {{site.data.keyword.backup_full}} は、{{site.data.keyword.backup_notm}} ポータル・ブラウザー・ベースの管理ユーティリティーにより管理される、エージェント・ベースの自動化されたバックアップ・システムです。 {{site.data.keyword.backup_notm}} は、{{site.data.keyword.BluSoftlayer_full}} ネットワーク上の 1 つ以上のデータ・センターにあるサーバー間でデータをバックアップするための手段を提供します。 管理者は、フル・システムや特定のディレクトリー、あるいは個別のファイルを対象とした日次スケジュール、週次スケジュール、またはカスタム・スケジュールに従うバックアップを設定できます。 追加のプラグインにより、Microsoft Exchange や Microsoft SQL などのソフトウェアや、その他のタイプのサード・パーティー・ソフトウェアとの互換性が確保され、ユーザーは必要に応じてベアメタル・リストアを実行できるようになります。

## {{site.data.keyword.backup_notm}} の注文

{{site.data.keyword.backup_notm}} サービスは 2 とおりの方法で購入できます。

- [サーバーの注文時における {{site.data.keyword.backup_notm}} の購入](#purchasing-ibm-cloud-backup-when-you-order-a-server)
- [アップグレードとしての {{site.data.keyword.backup_notm}} の購入](#purchasing-ibm-cloud-backup-as-an-upgrade)

価格設定について詳しくは、[{{site.data.keyword.backup_notm}} ストレージ ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/cloud/backup-and-restore){:new_window} および [{{site.data.keyword.backup_notm}} on IBM Cloud ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/cloud/evault/pricing){:new_window} を参照してください。

### サーバーの注文時における {{site.data.keyword.backup_notm}} の購入

1. [IBM Cloud カタログ ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/catalog/){:new_window} または [{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} にログインします。
2. 月次課金のベアメタル・サーバーを注文します。 ベアメタル・サーバーの注文について詳しくは、[カスタム・ベアメタル・サーバーの作成](bare-metal/baremetal-provision.html){:new_window}を参照してください。
   1. 数量と課金オプションを選択してください。 ホストとドメインの名前を入力します。 任意のホスト名とドメイン名を選択できます。

      {{site.data.keyword.backup_notm}} サービスは、時間課金サーバーを注文する際には選択できません。 ただし、アップグレードとして後からサービスを追加できます。
      {:tip}
   2. 場所を選択します。
   3. サーバー構成と OS イメージのタイプを選択します。 複数のアドオンを選択することもできます。
   4. **「ストレージ・ディスク」**セクションで**「アドオン」**をクリックし、**「{{site.data.keyword.backup_notm}} バックアップ」**を選択します。 必要な条件に一致するオプションを選択します。
   5. **「ネットワーク・インターフェース」**の下から、必要なアップリンク・ポート速度とアドオンを選択します。
3. 右側で、注文の要約を確認します。
4. ご使用条件を確認した後、**「サード・パーティー・サービス契約を読み、同意します」**ボックスにチェック・マークを付けます。
5. **「プロビジョン」**をクリックします。 プロビジョニング注文番号が表示された画面にリダイレクトされます。 これはプロビジョニング注文の受信も兼ねているので、画面を印刷することができます。

   **「見積もりとして保存」**をクリックして購入せずにこの注文を保存することもできます。
   {:tip}

プロビジョニング注文の受領確認、プロビジョニング注文の承認と処理、およびプロビジョニングの完了といった一連の E メールが管理者に送信されます。 プロビジョニングの完了 E メールには、*[デバイスの詳細」*ページへのリンクが記載されています。このページには、{{site.data.keyword.cloud_notm}} にログインした後にアクセスできます。 また、{{site.data.keyword.slportal}}に直接ログインすることもできます。

#### {{site.data.keyword.backup_notm}} 購入の確認
1. [{{site.data.keyword.cloud_notm}} コンソール ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/){:new_window} で、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。</br>
   あるいは、[{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} にログインします。
2. **「デバイス」**>**「デバイス・リスト」**をクリックします。
2. 注文した新規サーバーを見つけます。
  - URL の横に時計アイコンがある場合は、{{site.data.keyword.backup_notm}} の購入確認に進む前に待つ必要があります。ページを最新表示して、新規サーバーに関する状況が更新されるか確認します。 時計アイコンが表示されなくなったら、{{site.data.keyword.backup_notm}} サービスの購入を確認する以降のステップに進むことができます。
  - 該当のサーバーに対して時計アイコンが表示されなくなったら、リンク (サーバーの URL) をクリックして、**「デバイスの詳細」**ページに進みます。
3. **「ストレージ」**タブをクリックし、{{site.data.keyword.backup_notm}} の情報を表示します。
4. 「{{site.data.keyword.backup_notm}}」セクションを検査し、購入処理時に選択したサイズが表示されていることを確認します。

### アップグレードとしての {{site.data.keyword.backup_notm}} の購入

#### {{site.data.keyword.backup_notm}} をインストールするサーバーの選択

1. [{{site.data.keyword.cloud_notm}} コンソール ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}){:new_window} にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。</br>
   あるいは、[{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} にログインします。
2. メインメニューから**「デバイス」** > **「デバイス・リスト」**を選択します。 {{site.data.keyword.cloud_notm}} バックアップ・サービスを追加するデバイスを検索します。
3. デバイス名をクリックして、**「デバイスの詳細」**ページに進みます。

#### {{site.data.keyword.backup_notm}} サービスの追加 (購入)
1. **「ストレージ (Storage)」**タブをクリックし、スクロールダウンして「{{site.data.keyword.backup_notm}}」セクションを見つけます。
2. **「追加」**リンクをクリックします。
3. ウィンドウでロケーションを選択し、サイズを選択します。
4. 支払タイプを選択し、**「続行」**をクリックします。
5. **割引コード**がある場合は入力し、**「再計算」**をクリックします。
6. 注文内容を確認し、リンクをクリックして契約条件を読みます。
7. ご利用条件に同意する場合はチェック・ボックスをクリックします。
7. **「注文」**をクリックします。

#### {{site.data.keyword.backup_notm}} アップグレード購入の確認
1. **「デバイスの詳細」**ページを最新表示し、**「ストレージ」**タブが選択されていることを確認します。
2. 「{{site.data.keyword.backup_notm}}」セクションを検査し、購入処理時に選択したサイズが表示されていることを確認します。

   バックアップ・ストレージ・サイズとして引き続き容量ゼロが表示される場合は、ページの 2 回目のリフレッシュが必要になることがあります。
   {:tip}

## {{site.data.keyword.backup_notm}} ストレージの詳細へのアクセスと表示

{{site.data.keyword.backup_notm}} サービスのストレージに関する詳細は、いつでも [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}/catalog/){:new_window}と {{site.data.keyword.slportal}}で確認できます。確認できる詳細には、選択されている {{site.data.keyword.backup_notm}} サービスに関連付けられているパスワード、ストレージ・アドレス、および使用状況などがあります。

1. [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}){:new_window}にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。</br>
   あるいは、[{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} にログインします。
2. **「ストレージ」**をクリックし、リストから**「バックアップ」**を選択します。
2. ストレージの詳細を確認するボールトの行の任意の位置をクリックします。 このビューでは「パスワード」は表示可能ではありません。 次のステップに進み、{{site.data.keyword.backup_notm}} サービスに関連付けられているパスワードを表示します。
3. **「パスワード」**フィールドの横にある**「表示」**チェック・ボックスをクリックし、選択した {{site.data.keyword.backup_notm}} サービスのパスワードを表示します。

多くの {{site.data.keyword.BluSoftlayer_full}} 製品およびサービスでは、{{site.data.keyword.slportal}}内でのパスワード・ストレージ機能はパスワードの保管またはトラッキングのみのために使用されます。 これらの製品およびサービスでは、{{site.data.keyword.slportal}}で行った変更が製品またはサービスに適用されません。

{{site.data.keyword.backup_notm}} には当てはまり_ません_。 {{site.data.keyword.slportal}}内で {{site.data.keyword.backup_notm}} のパスワードに加える変更は、サービス自体に対して加えられます。 パスワードを変更するときには、この変更がサービスに直接影響することに注意してください。 パスワードをリセットするには、[{{site.data.keyword.slportal}}での {{site.data.keyword.backup_notm}} のパスワードの変更方法](change-password.html)のステップに従ってください。
{:important}

## {{site.data.keyword.backup_notm}} エージェントのインストール

{{site.data.keyword.backup_notm}} エージェントは以下の OS でサポートされています。

**Windows**
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
- [Linux でのバックアップ・クライアントのインストール](install-backup-client-linux.html)
- [Windows でのバックアップ・クライアントのインストール](install-backup-client-windows.html)
- [Windows 2016 でのバックアップ・クライアントのインストール](install-windows2016.html)
- [VMware でのバックアップ・クライアントのインストール](https://{DomainName}/docs/infrastructure/vmware/install-backup-client-vmware.html)

## {{site.data.keyword.backup_notm}}・ポータル (旧称 WebCC) へのアクセス

{{site.data.keyword.backup_notm}}・ポータルは、{{site.data.keyword.BluSoftlayer_full}} が提供する {{site.data.keyword.backup_notm}} サービスとの対話式操作に使用されます。{{site.data.keyword.backup_notm}} ポータルは、{{site.data.keyword.BluSoftlayer_full}} プライベート・ネットワークで実行されるブラウザー・ベースのクライアントであり、これによって、構成やリストアなどすべての {{site.data.keyword.backup_notm}} サービスを完全に制御することができます。

1. VPN 経由でプライベート・ネットワークにアクセスします。

   パブリック・ネットワーク上で {{site.data.keyword.backup_notm}} ポータルにアクセスすることはできません。 VPN 接続を最初に確立する必要があります。
   {:important}
2. [{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} のバックアップ・ストレージ画面にアクセスします。
3. 表示する {{site.data.keyword.backup_notm}} サービスの行の任意の場所をクリックし、ビューを展開します。
4. **「{{site.data.keyword.backup_notm}} ポータル・ログイン」**をクリックし、ブラウザーで {{site.data.keyword.backup_notm}} ポータル・クライアントを開始します。

## バックアップ・エージェントとバックアップ・スケジュールの構成

{{site.data.keyword.backup_notm}} を注文し、エージェントがサーバーにインストールされた後、データのバックアップの作成を開始できます。 エージェントと保存スケジュールを構成し、最初のバックアップ・ジョブを開始するには、以下のステップに従うことができます。

1. WebCC にログインします。
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

      保存スキームについて詳しくは、[FAQ](faqs.html) を参照してください。
      {:tip}
5. エージェントを実行し、バックアップを開始します。
   1. **「すべてのエージェント」**をクリックしてから、構成したエージェントを選択します。
   2. **「バックアップの実行 (Run Backup)」**をクリックします。
   3. 「宛先」を確認し、保存スキームを選択します。
   4. **「バックアップの開始 (Start Backup)」**をクリックします。 プロセスの稼働中、バックアップの詳細を表示できます。
   5. バックアップが完了したら、**「閉じる」**をクリックします。

Linux でのファイル・レベルのバックアップについて詳しくは、[Linux での単純なファイル・レベルのバックアップの構成](configure-simple-file-backup-linux.html)を参照してください。
{:tip}

## オンライン・ヘルプの表示

{{site.data.keyword.backup_notm}} ポータルのシステムは完全に文書化されており、アプリケーションのサポートには {{site.data.keyword.backup_notm}} ポータル内からアクセス可能です。 **「ヘルプ」**を表示するには、右上にある青い円の中の白い疑問符をクリックします。 左側にあるナビゲーション・バーで任意の記事やトピックをクリックすると、詳細情報が表示されます。

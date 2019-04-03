---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud backup, EVault, Carbonite, IBM Cloud backup, Enterprise backup

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# {{site.data.keyword.backup_notm}} のプロビジョニング
{: #ordering}

{{site.data.keyword.backup_notm}} サービスは 2 とおりの方法で購入できます。

- [サーバーの注文時におけるバックアップの購入](#purchasingwithserver)
- [アップグレードとしてのバックアップの購入](#purchasingasupgrade)

価格設定について詳しくは、[{{site.data.keyword.backup_notm}} ストレージ ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/cloud/backup-and-restore){:new_window} および [{{site.data.keyword.backup_notm}} on IBM Cloud ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/cloud/backup/pricing){:new_window} を参照してください。

## サーバーの注文時における {{site.data.keyword.backup_notm}} の購入
{: #purchasingwithserver}

1. [IBM Cloud カタログ ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/catalog){:new_window} または [{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} にログインします。
2. 月次課金のベアメタル・サーバーを注文します。 ベアメタル・サーバーの注文について詳しくは、[カスタム・ベアメタル・サーバーの作成](https://{DomainName}/docs/bare-metal/baremetal-provision.html){:new_window}を参照してください。
   1. 数量と課金オプションを選択してください。 ホストとドメインの名前を入力します。 任意のホスト名とドメイン名を選択できます。

      {{site.data.keyword.backup_notm}} サービスは、時間課金サーバーを注文する際には選択できません。 ただし、アップグレードとして後からサービスを追加できます。
      {:tip}
   2. 場所を選択します。
   3. サーバー構成と OS イメージのタイプを選択します。 複数のアドオンを選択することもできます。
   4. **「ストレージ・ディスク」**セクションで**「アドオン」**をクリックし、**「{{site.data.keyword.backup_notm}}」**を選択します。 必要な条件に一致するオプションを選択します。
   5. **「ネットワーク・インターフェース」**の下から、必要なアップリンク・ポート速度とアドオンを選択します。
3. 右側で、注文の要約を確認します。
4. ご使用条件を確認した後、**「サード・パーティー・サービス契約を読み、同意します」**ボックスにチェック・マークを付けます。
5. **「プロビジョン」**をクリックします。 プロビジョニング注文番号が表示された画面にリダイレクトされます。 これはプロビジョニング注文の受信も兼ねているので、画面を印刷することができます。

   **「見積もりとして保存」**をクリックして購入せずにこの注文を保存することもできます。
   {:tip}

プロビジョニング注文の受領確認、プロビジョニング注文の承認と処理、およびプロビジョニングの完了といった一連の E メールが管理者に送信されます。 プロビジョニングの完了 E メールには、*[デバイスの詳細」*ページへのリンクが記載されています。このページには、{{site.data.keyword.cloud_notm}} にログインした後にアクセスできます。 また、{{site.data.keyword.slportal}}に直接ログインすることもできます。

### {{site.data.keyword.backup_notm}} 購入の確認
1. [{{site.data.keyword.cloud_notm}} コンソール ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/){:new_window} で、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。</br>
   あるいは、[{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} にログインします。
2. **「デバイス」**>**「デバイス・リスト」**をクリックします。
2. 注文した新規サーバーを見つけます。
  - URL の横に時計アイコンがある場合は、{{site.data.keyword.backup_notm}} の購入確認に進む前に待つ必要があります。 ページを最新表示して、新規サーバーに関する状況が更新されるか確認します。 時計アイコンが表示されなくなったら、{{site.data.keyword.backup_notm}} サービスの購入を確認する以降のステップに進むことができます。
  - 該当のサーバーに対して時計アイコンが表示されなくなったら、リンク (サーバーの URL) をクリックして、**「デバイスの詳細」**ページに進みます。
3. **「ストレージ」**タブをクリックし、{{site.data.keyword.backup_notm}} の情報を表示します。
4. 「{{site.data.keyword.backup_notm}}」セクションを検査し、購入処理時に選択したサイズが表示されていることを確認します。

## アップグレードとしての {{site.data.keyword.backup_notm}} の購入
{: #purchasingasupgrade}

### {{site.data.keyword.backup_notm}} をインストールするサーバーの選択

1. [{{site.data.keyword.cloud_notm}} コンソール ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}){:new_window} にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。</br>
   あるいは、[{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} にログインします。
2. メインメニューから**「デバイス」** > **「デバイス・リスト」**を選択します。 バックアップ・サービスを追加するデバイスを検索します。
3. デバイス名をクリックして、**「デバイスの詳細」**ページに進みます。

### {{site.data.keyword.backup_notm}} サービスの追加 (購入)
1. **「ストレージ (Storage)」**タブをクリックし、スクロールダウンして「{{site.data.keyword.backup_notm}}」セクションを見つけます。
2. **「追加」**リンクをクリックします。
3. ウィンドウでロケーションを選択し、サイズを選択します。
4. 支払タイプを選択し、**「続行」**をクリックします。
5. **割引コード**がある場合は入力し、**「再計算」**をクリックします。
6. 注文内容を確認し、リンクをクリックして契約条件を読みます。
7. ご利用条件に同意する場合はチェック・ボックスをクリックします。
7. **「注文」**をクリックします。

### {{site.data.keyword.backup_notm}} アップグレード購入の確認
1. **「デバイスの詳細」**ページを最新表示し、**「ストレージ」**タブが選択されていることを確認します。
2. 「{{site.data.keyword.backup_notm}}」セクションを検査し、購入処理時に選択したサイズが表示されていることを確認します。

   バックアップ・ストレージ・サイズとして引き続き容量ゼロが表示される場合は、ページの 2 回目のリフレッシュが必要になることがあります。
   {:tip}

準備ができたら、続いて当該ソフトウェア・エージェントをサーバーにインストールし、{{site.data.keyword.backup_notm}} ポータルでバックアップ・スケジュールを設定することができます。詳しくは、[入門チュートリアル](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)を参照してください。

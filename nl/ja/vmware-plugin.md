---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# vSphere Recovery Agent のインストール
{: #VRA}

vSphere Recovery Agent (VRA) は、最大 10 TB の VMDK のバックアップとリストアを実行できる Windows アプリケーションです。 vSphere Recovery Agent は、保護する対象の vCenter へのローカル・ネットワーク・アクセスがある、物理マシンまたは仮想マシンにインストールできます。 最高のパフォーマンスを得るには、vCenter と同じサブネットにあるマシンに VRA をインストールしてください。 ワークロードを分散するため、最大 5 つの VRA を使用して、単一の vCenter に接続されている複数の VM を保護できます。

vSAN 拡張クラスターでは、VM ごとに優先サイトがあります。 サイトごとに 1 つのローカル VRA をインストールし、各サイトの優先 VM がバックアップされるようにするのが理想的です。 VM が (保守または障害のために) 別のサイトに移動されると、バックアップのパフォーマンスが低下する可能性がありますが、許容レベルの低下にとどまります。


## プラグインの注文
{: #orderingVRAPlugin}

{{site.data.keyword.cloud_notm}} は、vSphere Recovery Agent (VRA) を無料で提供しています。 現行の {{site.data.keyword.backup_notm}} サブスクリプションをお持ちの場合、このプラグインを {{site.data.keyword.backup_notm}} ポータルからダウンロードできます。

## プラグインのインストール
{: #installVRAPlugin}

VRA のインストール先となるサーバーで、電源管理が無効になっていることを確認してください。
{: important}

1. `http://downloads.service.softlayer.com/evault/` からインストール・キットをダウンロードします。 そして、そのインストール・キットをダブルクリックします。
2. 確認メッセージで**「はい」**をクリックします。
3. ウェルカム・ページで、**「次へ」**をクリックします。
4. 「エンド・ユーザー使用許諾契約書 (End-User-License Agreement)」ページで、使用許諾契約書を確認します。 条項に同意する場合は、**「使用許諾契約の条項に同意します (I accept the terms in the License Agreement)」**をクリックし、**「次へ」**をクリックします。
5. 「宛先フォルダー (Destination Folder)」ページで、以下のいずれかのアクションを実行します。
   * VRA をデフォルトの場所にインストールする場合は、**「次へ」**をクリックします。
   * VRA を別の場所にインストールする場合は、**「変更」**をクリックします。 「宛先フォルダーの変更 (Change destination folder)」ダイアログ・ボックスで、新規インストール・フォルダーを参照するか、「フォルダー名」ボックスに入力します。 **「OK」**をクリックします。 「宛先フォルダー (Destination Folder)」ページで、**「次へ」**をクリックします。
6. 「ポータルにエージェントを登録 (Register Agent with Portal)」ページで、以下の情報を指定します。
   * **「ネットワーク・アドレス」**フィールドに、`ev-webcc01.service.softlayer.com` と入力します。
   * **「ポート」**フィールドに、`8086` を入力します。
   * **「ユーザー名」**フィールドに、VRA を管理する {{site.data.keyword.backup_notm}} ユーザー名を入力します。
   * **「パスワード」**フィールドに、指定した {{site.data.keyword.backup_notm}} ユーザーのパスワードを入力します。
7.	**「次へ」**をクリックします。 インストールが完了したら、**「完了」**をクリックします。

## vSphere Recovery Agent の構成
{: #configureVRA}

VRA をインストールした後、{{site.data.keyword.backup_notm}} ポータルで VRA を構成する必要があります。

1. {{site.data.keyword.backup_notm}} ポータルにログインします。 {{site.data.keyword.backup_notm}} ポータルにアクセスする方法について詳しくは、[入門チュートリアル](/docs/infrastructure/Backup?topic=Backup-getting-started#accessingWebCC)を参照してください。
2. 「コンピューター」タブで、バックアップするサーバーを選択します。
3. ボールト情報を構成します。

   ボールト情報は、**自動**または**手動**の 2 とおりの方法で構成できます。<br/>初めてこのエージェントを構成する場合は、[自動構成](#VRAautoconfig)オプションを使用して構成することができます。<br/>以前にコンピューターがボールトに登録されている場合は、自動構成が機能しないため、ボールトを[手動で構成](#VRAmanualconfig)する必要があります。
   {: tip}

4. [vCenter 設定](#vCenterSettingsconfig)の構成   

### ボールトの自動構成
{: #VRAautoconfig}

ボールト設定を自動的に構成するには、**「自動構成 (Configure Automatically)」**をクリックします。 構成ウィザードが実行され、ボールト設定が自動的に構成されます。 完了したら、**「エージェントに移動 (Go To Agent)」**をクリックして、**「ボールト設定 (Vault Settings)」**タブで情報を確認します。
 

### ボールトの手動構成
{: #VRAmanualconfig}

ボールト設定を手動で構成するには、**「手動で構成」**をクリックします。   
1. **「ボールト設定 (Vault Settings)」**をクリックします。
2. **「ボールトの追加 (Add Vault)」**をクリックします。 「ボールト設定 (Vault Settings)」ウィンドウが表示されます。 **「ボールト・プロファイル (Vault Profile)」**オプションから、適切なボールトを選択します。
   以前にコンピューターが {{site.data.keyword.backup_notm}} ボールトに登録されている場合は、「ボールト・プロファイル (Vault Profile)」からボールトを選択すると、すべての情報が自動設定されます。
   {:note}

3. 「ボールト設定 (Vault Settings)」ページですべての情報を確認し、**「保存」**をクリックします。
4. ボールト設定を保存すると、**「ボールト設定 (Vault Settings)」**タブにボールト情報が表示されるようになります。


### vCenter Agent 設定の構成
{: #vCenterSettingsconfig}
ボールトが正常に登録された後、バックアップ・ジョブを作成して実行するには、その前に vCenter 設定を構成する必要があります。

1. **「vCenter 設定 (vCenter Settings)」**タブをクリックします。
2. 保護する vCenter の IP アドレス、ドメイン・ネーム、および資格情報を指定します。
   ユーザーがこのタスクを正常に実行するには、vCenter に対する管理アクセス権限を持っている必要があります。
   {:note}

3. Change Block Tracking (CBT) を無効にするために、チェック・マークを外します。 CBT は、変更されたディスク・セクターを追跡し、VM バックアップのパフォーマンスを向上させる VMware 機能です。この機能は、vSphere Agent によって自動的に有効にされます。
4. **「vCenter 接続のテスト (Test vCenter Connection)」**をクリックします。 新規ウィンドウに結果が表示されます。 指定されたログイン情報が正しければ、「vCenter 資格情報が正常に検証されました (The vCenter credentials have been validated successfully)」というメッセージが表示されます。
5. **「保存」**をクリックして、設定を保存します。

## 次のステップ
{: #VRAnextteps}
1. [バックアップ・ジョブを構成し、スケジュールし、実行します](/docs/infrastructure/Backup?topic=Backup-ConfigureVRA#VConfigureVRA)
2. [vSphere データをリストアします](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore)

{{site.data.keyword.BluVPN}} を使用して {{site.data.keyword.BluSoftlayer_full}} ネットワークに接続すると、[ダウンロード可能な {{site.data.keyword.backup_notm}} 資料 ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} からユーザーズ・ガイドにアクセスしてダウンロードすることができます。
{:tip}
